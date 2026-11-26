# Claude Skills 🇧🇷

Skills prontas pra deixar o Claude melhor em tarefas do dia a dia no Brasil. Cada skill é uma pasta com um `SKILL.md`: instruções que o Claude carrega sozinho quando a tarefa combina com a descrição.

*Ready-to-use Claude skills focused on Brazilian context (LGPD, taxes, CLT/PJ job offers, ATS-friendly resumes). Content in Portuguese.*

## Skills disponíveis

### Para devs e consultores Salesforce

| Skill | Pra que serve |
|---|---|
| [`salesforce-dev`](skills/salesforce-dev/SKILL.md) | Apex, triggers, LWC, Flows, testes e deploy no padrão sênior: código bulkificado, seguro (sharing, CRUD/FLS), sempre com classe de teste e seguindo o padrão do projeto. Inclui checklist de code review. |
| [`sfmc-dev`](skills/sfmc-dev/SKILL.md) | Marketing Cloud: SQL no Automation Studio, AMPscript, SSJS, Data Extensions, Data Views e Journey Builder, com as pegadinhas da plataforma (fuso CST, retenção das Data Views, deduplicação). |
| [`consultoria-entregas`](skills/consultoria-entregas/SKILL.md) | Dia a dia de consultoria: história de usuário → desenho técnico e estimativa, investigação de bug, daily, status report, release notes e mensagens para cliente. |

### Vida, carreira e negócios no Brasil

| Skill | Pra que serve |
|---|---|
| [`site-compliance-br`](skills/site-compliance-br/SKILL.md) | Ao criar um site, aplica o checklist de LGPD, cookies, acessibilidade, CDC e identificação da empresa, pra o site não gerar processo. |
| [`investimentos-br`](skills/investimentos-br/SKILL.md) | Compara CDB, LCI/LCA, Tesouro, poupança, ações e FIIs com dados atuais e rendimento **líquido** calculado em código. Educativa: explica os riscos e não recomenda compra. |
| [`proposta-emprego-br`](skills/proposta-emprego-br/SKILL.md) | Analisa uma proposta de emprego, calcula o pacote total CLT x PJ, compara com o mercado e escreve a mensagem de negociação. |
| [`curriculo-ats`](skills/curriculo-ats/SKILL.md) | Revisa o currículo pra passar em filtros ATS e convencer o recrutador, com palavras-chave da vaga e resultados com número, sem inventar nada. |

## Princípios de todas as skills

- **Nunca inventar dados.** CNPJ, números de currículo, salário atual, depoimentos: se o Claude não sabe, pergunta ou deixa um placeholder visível.
- **Dados atuais.** Impostos, taxas e tabelas mudam, então as skills mandam o Claude pesquisar a regra vigente antes de calcular.
- **Contas em código**, não de cabeça.
- **Honestidade sobre limites.** Não substituem advogado, contador ou consultor de investimentos, e dizem isso.

## Como instalar

**No Claude (app ou site):** baixe a pasta da skill, compacte em `.zip` e envie na área de Skills das configurações. Ou peça direto no chat: "cria essa skill pra mim", colando o conteúdo do `SKILL.md`.

**No Claude Code:** copie a pasta para `~/.claude/skills/` (vale pra todos os projetos) ou para `.claude/skills/` dentro do seu projeto.

```bash
git clone https://github.com/gustavosemmler/claude-skills.git
cp -r claude-skills/skills/site-compliance-br ~/.claude/skills/
```

Depois é só pedir a tarefa normalmente ("cria uma landing page pra minha barbearia") que o Claude usa a skill.

## Criar uma skill nova

```
skills/nome-da-skill/
└── SKILL.md
```

```markdown
---
name: nome-da-skill
description: Quando usar (é isso que faz o Claude escolher a skill). Uma frase clara.
---

# Título

Instruções passo a passo, regras e formato de entrega.
```

Dicas: a `description` decide quando a skill é ativada, então diga **quando** usar, não só o que faz. Escreva as regras como passos verificáveis e diga o que o Claude **não** deve fazer.

Contribuições são bem-vindas: abra um PR com uma skill nova ou melhorias.

## Licença

MIT
