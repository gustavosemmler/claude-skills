---
name: "sfmc-dev"
description: "Use em tarefas de Salesforce Marketing Cloud: SQL no Automation Studio, AMPscript, SSJS, Data Extensions, Data Views, Journey Builder e e-mails; entrega código testável com as particularidades da plataforma."
---

# Salesforce Marketing Cloud: padrão sênior

## Particularidades que eu sempre considero

- **Fuso horário:** os horários do sistema do Marketing Cloud ficam em CST (UTC-6, sem horário de verão). Em filtros por data e na exibição pro cliente, converto e deixo isso explícito.
- **Data Views** (`_Sent`, `_Open`, `_Click`, `_Bounce`, `_Unsubscribe`, `_Subscribers`, `_Job`, `_JourneyActivity`...) guardam só cerca de 6 meses. Se precisar de histórico maior, sugiro gravar em Data Extension própria.
- **Data Extensions:** chave primária definida é obrigatória pra usar a ação Update numa query e evita duplicidade. Confiro tipos e tamanhos de campo (texto truncado quebra a query) e a retenção de dados.

## SQL (Automation Studio)

- É um subconjunto de T-SQL e a query sempre grava numa Data Extension de destino (Overwrite, Update ou Append). Não há variáveis, temp tables nem procedures. Se eu não tiver certeza de que uma função é suportada, aviso.
- Queries pesadas podem estourar o tempo limite: filtro cedo, junto só o necessário e quebro em etapas (DEs intermediárias) quando a base for grande.
- **Deduplicação:** `ROW_NUMBER() OVER (PARTITION BY SubscriberKey ORDER BY DataAtualizacao DESC)` numa subquery e filtro `= 1`.
- Sempre trato `NULL`, espaços e caixa em e-mails (`LOWER(LTRIM(RTRIM(Email)))`) e evito juntar por e-mail quando existe SubscriberKey.
- Entrego o SQL com: DE de destino, ação (Overwrite/Update/Append), chave primária esperada e a frequência sugerida na automação.

## AMPscript

- Toda personalização tem fallback: `IIF(Empty(@nome), "Olá", Concat("Olá, ", ProperCase(@nome)))`.
- `LookupRows` / `LookupOrderedRows` sempre com checagem de `RowCount` antes de acessar a linha.
- Nada de lookup pesado dentro de loop em envio grande. Prefiro trazer o dado já pronto na DE de envio.
- `RaiseError` só quando o envio daquele contato deve ser pulado, e explico o efeito (o contato não recebe).
- Organizo em Content Blocks reutilizáveis e comento as variáveis principais.

## SSJS

- `Platform.Load("core", "1.1.1")` no início e `try/catch` em tudo, com log numa DE de erros.
- WSProxy para operações em massa (é mais eficiente que as funções Core). Evito SSJS pesado dentro de e-mail; prefiro CloudPages ou Script Activities.
- Credenciais de API (installed packages) nunca ficam fixas no código visível; uso o mecanismo de armazenamento do projeto.

## Journey Builder

- Defino a entrada (Data Extension, evento de API, Salesforce Data), a regra de **reentrada** e o critério de saída (goal/exit criteria) antes de desenhar.
- Decision splits baseados em atributos atualizados; aviso quando o dado pode estar desatualizado no momento da decisão.
- Respeito consentimento (LGPD), opt-out e janelas de envio. Sugiro testar com Test Mode e uma DE de teste antes de ativar.

## Formato da entrega

1. O código (SQL, AMPscript ou SSJS), comentado
2. Onde colocar (atividade, DE, bloco de conteúdo) e as configurações necessárias
3. Plano de teste: dados de exemplo, preview, test send ou execução manual da query
4. Riscos ou limites (volume, fuso, retenção das Data Views)