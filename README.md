# Bancada

Triagem técnica inteligente para uma assistência de celulares e notebooks.
O cliente descreve o defeito com as próprias palavras — digitando ou falando —
e recebe um diagnóstico com provável causa, faixa de preço, prazo e o que fazer
antes de sair de casa. A mesma triagem alimenta a fila interna do técnico,
ordenada por urgência.

Trabalho da disciplina **Padrões Web para No Code e Low Code** —
Faculdade de Tecnologia Rocketseat / UniFECAF.

**Aplicação publicada:** `[COLAR A URL DO FRAMER AQUI]`

---

## O problema

Uma assistência técnica de bairro não tem equipe de desenvolvimento e vive de
atendimento no direct e no WhatsApp. O cliente pergunta "quanto custa trocar a
tela?" e a resposta honesta — *depende do modelo, do tipo de dano e do que o
técnico encontrar* — não cabe numa mensagem. A conversa morre ali.

**Público:** quem quebrou o aparelho e precisa decidir, ainda em casa, se vale a
pena consertar.

**Solução:** um diagnóstico em um minuto, sem cadastro, que responde a pergunta
real do cliente ("compensa?") e já entrega o caso classificado para a oficina.

## Funcionalidades

- Diagnóstico a partir de texto livre ou de voz
- Ficha com provável causa, confiança da leitura, hipótese alternativa, faixa de
  preço, prazo e veredito de "compensa consertar"
- Lista dos fatos que o sistema extraiu do relato, para o cliente conferir se foi
  entendido
- Cuidados imediatos e perguntas que o técnico vai confirmar, específicos do caso
- Protocolo e acompanhamento de status
- Painel interno com a fila ordenada por urgência, contadores e troca de status

## Tecnologias e ferramentas

| Camada | Escolha |
|---|---|
| Plataforma no-code | **Framer** (plano gratuito, publica em `.framer.website`) |
| Componente personalizado | HTML, CSS e JavaScript escritos à mão, sem biblioteca |
| Automação | **Make** — webhook, módulo de IA e data store |
| IA | **Claude Haiku** via AI by Make, como classificador |

O Webflow foi descartado na escolha: o *Code Embed* não funciona no plano
gratuito, o que inviabilizaria a exigência central do trabalho.

## Personalizações com padrões web

O que o Framer entrega pronto são as seções institucionais. Tudo abaixo é código
próprio, dentro de um Embed:

- **Web Speech API** para ditar o relato, com degradação silenciosa onde o
  navegador não suporta
- **Padrão ARIA de abas** (`tablist`/`tab`/`tabpanel`) com navegação por setas,
  Home e End, e `tabindex` rotativo
- **Validação própria** com resumo de erros focável, links para o campo com
  problema e `aria-invalid`
- **`aria-live`** anunciando o diagnóstico quando ele chega
- **Tokens CSS** cobrindo tema claro e escuro nos três estados (sistema, claro
  forçado, escuro forçado)
- **`prefers-reduced-motion`** desligando as animações
- **`localStorage`** guardando os protocolos daquele visitante, sempre dentro de
  `try/catch` porque em aba anônima ele falha
- Layout em `flex`/`grid` com `gap`, sem rolagem horizontal a 390 px

## O recurso inteligente

A IA **não escreve o texto que o cliente lê.** Ela recebe o relato e devolve
JSON: categoria (de uma lista fechada de sete), confiança, hipótese alternativa,
urgência, os fatos que extraiu do relato, as perguntas de checagem daquele caso e
um resumo para o técnico. Quem desenha a interface é o JavaScript.

Preço, prazo e o veredito de "compensa consertar" **não passam pela IA** — saem
do catálogo da loja, no próprio código. Isso elimina a possibilidade de o modelo
inventar um valor para o cliente.

O prompt está em [`make/prompt-triagem.txt`](make/prompt-triagem.txt) e o
contrato de saída em [`make/contrato-saida.json`](make/contrato-saida.json).

## Responsividade e acessibilidade

Verificado em Chromium a 390 px e a 1280 px: sem rolagem horizontal em nenhum
estado, inclusive com a ficha aberta. Navegação completa por teclado com foco
visível. Cores definidas por token para os dois temas. Nenhum erro de console na
jornada completa.

## Prints

| | |
|---|---|
| `docs/prints/01-formulario.png` | Formulário no celular |
| `docs/prints/02-diagnostico.png` | Ficha de diagnóstico |
| `docs/prints/03-painel.png` | Fila interna por urgência |
| `docs/prints/04-cenario-make.png` | Cenário rodando no Make |
| `docs/prints/05-lighthouse.png` | Lighthouse de acessibilidade |

## Como testar

1. Abra a aplicação publicada (link no topo).
2. Escolha o aparelho, descreva um problema — ou use o botão **Usar um exemplo**.
3. Envie e veja a ficha.
4. Abra **Bancada interna** para ver o caso entrar na fila já classificado.

Para rodar o componente sozinho, sem o Make: abra `bancada-diagnostico.html` no
navegador. Com a constante `WEBHOOK` vazia, ele roda em modo demonstração com a
triagem simulada no próprio navegador, no mesmo formato que o Make devolve.

## Estrutura

```
bancada-diagnostico.html      componente completo, pronto para o Embed do Framer
make/prompt-triagem.txt       prompt do classificador
make/contrato-saida.json      formato de saída aceito pelo site
make/montagem-do-cenario.md   como montar o cenário no Make
docs/roteiro-video.md         roteiro do vídeo pitch
```
