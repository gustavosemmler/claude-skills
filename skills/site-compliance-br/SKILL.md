---
name: site-compliance-br
description: Use ao criar ou revisar qualquer site, landing page ou loja para o Brasil: aplica o checklist de LGPD, CDC, acessibilidade, cookies e transparência pra o site não gerar processo.
---

# Site em conformidade (Brasil)

Toda vez que eu criar ou revisar um site, landing page, loja ou app web voltado pro público brasileiro, sigo este checklist. Ele vale mesmo quando o pedido não fala nada de jurídico: a conformidade faz parte do site pronto.

Leis de referência: LGPD (Lei 13.709/2018), Código de Defesa do Consumidor (Lei 8.078/1990), Decreto do e-commerce (Decreto 7.962/2013), Lei Brasileira de Inclusão (Lei 13.146/2015, art. 63), Marco Civil da Internet (Lei 12.965/2014) e Lei de Direitos Autorais (Lei 9.610/1998).

## Regra de ouro: nunca inventar dados

Razão social, CNPJ, endereço, e-mail do encarregado (DPO), prazos e políticas reais vêm do usuário. Se eu não tiver esses dados, uso placeholders bem visíveis, como `[CNPJ DA EMPRESA]`, e listo tudo que falta no final. Nunca preencho com dados fictícios que pareçam reais.

## 1. Documentos legais (páginas próprias, linkadas no rodapé)

1. **Política de privacidade**, com: quem é o controlador (razão social, CNPJ, contato); quais dados coleta e por quê (finalidade de cada um); base legal; com quem compartilha (ex.: Google Analytics, Meta, gateway de pagamento); por quanto tempo guarda; direitos do titular (art. 18 da LGPD: acesso, correção, exclusão, portabilidade, revogação do consentimento) e como exercer; contato do encarregado (DPO); data da última atualização.
2. **Termos de uso**: regras de uso do site, responsabilidades, propriedade intelectual, foro.
3. **Política de troca e reembolso** (se vender algo online): direito de arrependimento de 7 dias para compras fora do estabelecimento (art. 49 do CDC), com devolução integral; prazo e forma de reembolso; como solicitar.
4. Aviso no fim de cada documento: "Modelo gerado como ponto de partida. Revise com um advogado antes de publicar."

## 2. Cookies e scripts de rastreamento

5. **Banner de cookies** na primeira visita, com botões "Aceitar" e "Rejeitar" de mesmo destaque visual, mais um link pra configurar por categoria (necessários, estatística, marketing).
6. **Nenhum script não essencial carrega antes do consentimento**: Google Analytics, Meta Pixel, TikTok Pixel, Hotjar etc. só rodam depois do "Aceitar" da categoria correspondente. Implemento esse bloqueio de verdade no código, não só o banner visual.
7. A escolha fica salva e pode ser alterada depois (link "Preferências de cookies" no rodapé).

## 3. Formulários e dados pessoais (LGPD)

8. **Só os campos necessários** pra finalidade. Sem CPF, data de nascimento ou telefone se o objetivo não exigir.
9. Cada formulário diz **pra que os dados serão usados** e linka a política de privacidade.
10. **Consentimento pra marketing** (newsletter, WhatsApp) é um checkbox separado e **desmarcado por padrão**.
11. Dados enviados por HTTPS; nada de dados pessoais em parâmetros de URL.

## 4. Acessibilidade (LBI art. 63 + WCAG 2.1 AA)

12. **Contraste** de no mínimo 4.5:1 pra texto normal e 3:1 pra texto grande. Confiro as cores que eu escolher.
13. **Navegação por teclado**: tudo clicável funciona com Tab e Enter, com foco visível e ordem lógica.
14. **Alt text** descritivo em toda imagem que transmite informação (`alt=""` só nas decorativas).
15. HTML semântico (`header`, `nav`, `main`, `footer`, títulos em ordem), `lang="pt-BR"` no `<html>`, `label` em todo campo de formulário, botões com nome acessível.
16. Texto redimensionável sem quebrar o layout; vídeos com legenda quando houver fala.

## 5. Conteúdo honesto (CDC art. 37: publicidade enganosa)

17. **Sem avaliações ou depoimentos falsos.** Uso só depoimentos reais fornecidos pelo usuário. Sem eles, deixo a seção com placeholder ou removo, nunca invento nomes e falas.
18. **Sem promessas falsas**: nada de "resultado garantido", números ou selos que o usuário não comprovou, nem contador de urgência falso.
19. Preço, condições, frete e prazos claros antes da compra.

## 6. Imagens e direitos autorais

20. Só imagens próprias do usuário, de bancos com licença de uso comercial (com crédito quando exigido) ou geradas sem reproduzir marcas, personagens ou obras protegidas.
21. Nada de logos ou marcas de terceiros sem autorização.

## 7. Identificação da empresa (Decreto 7.962/2013)

22. No rodapé: razão social ou nome, CNPJ (ou CPF, se pessoa física vendendo), endereço físico e e-mail ou telefone de contato. Em loja virtual isso é obrigatório.

## Entrega

Ao terminar o site, incluo na resposta um resumo curto:
- **Feito:** os itens implementados.
- **Pendente com você:** cada dado real que falta (CNPJ, endereço, contato do DPO, política de reembolso real, depoimentos reais) e onde ele entra.
- **Riscos:** qualquer item que não deu pra cumprir e por quê.
- Lembrete de uma linha: os textos legais são modelos e devem ser revisados por um advogado.
