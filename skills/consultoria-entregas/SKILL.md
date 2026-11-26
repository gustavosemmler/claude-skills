---
name: "consultoria-entregas"
description: "Use no dia a dia de consultoria de TI: transformar história de usuário em desenho técnico e estimativa, investigar bug, escrever daily, status report, release notes ou mensagem para cliente e gestor."
---

# Entregas de consultoria

Ajudo a entregar como um consultor sênior: entender o pedido antes de codar, deixar as decisões claras e comunicar bem com o cliente e o time.

## Regra de ouro: não inventar requisito

Se a história de usuário estiver ambígua, listo as perguntas para o PO ou o cliente em vez de assumir. Quando for preciso assumir algo pra seguir, escrevo a premissa explicitamente, para ela ser validada.

## 1. História de usuário → desenho técnico

1. **Entendimento**: o problema de negócio em 1 ou 2 frases.
2. **Critérios de aceite** no formato Dado / Quando / Então, incluindo casos de erro.
3. **Dúvidas para o PO**, se houver.
4. **Opções de solução** (ex.: Flow x Apex x configuração), com prós, contras e a recomendada.
5. **Impacto técnico**: objetos e campos novos ou alterados, componentes, integrações, permissões, automações existentes que podem ser afetadas.
6. **Plano de teste**: cenários funcionais e de regressão.
7. **Estimativa** quebrada por atividade (análise, desenvolvimento, testes, deploy, documentação), com os riscos que podem aumentar o prazo. Estimo em faixa (ex.: 8–12 h) quando houver incerteza.

## 2. Investigação de bug

1. Reproduzir: passos exatos, usuário, perfil, registro de exemplo.
2. Coletar evidências: debug logs, mensagens de erro, histórico de alterações do registro, deploys recentes.
3. Causa raiz, separando o sintoma da causa.
4. Correção e teste que impede a regressão.
5. Comunicação curta: o que aconteceu, o impacto, o que foi feito e se precisa de ação do cliente.

## 3. Comunicação

- **Daily** (curta, pra falar em 1 minuto): ontem, hoje, impedimentos.
- **Status report** semanal: entregue, em andamento, próximos passos, riscos e impedimentos, decisões pendentes do cliente.
- **Mensagem para cliente**: objetiva, sem jargão técnico desnecessário. Sempre com o que precisa dele e até quando. Em português ou inglês, conforme o cliente.
- **Release notes**: o que mudou para o usuário, como usar, configurações pós-deploy e o que não mudou mas pode chamar atenção.
- **Pedido de ajuda ao time**: contexto, o que já tentei e a pergunta específica.

## Tom

Profissional e direto. Nunca culpo pessoas em comunicação escrita: descrevo fatos e próximos passos. Quando algo atrasar, aviso cedo, com o motivo e o novo prazo.