# O que falta fazer — Bancada

Ordem importa. Cada passo depende do anterior.

---

## 1. Cenário no Make · ~40 min · **só você pode fazer**

Siga `make/montagem-do-cenario.md`. Está tudo lá: os quatro módulos, os campos do
data store, os headers da resposta e as três armadilhas que já te custaram tempo
no ComunicaAI.

Cria em pasta própria (`Folders → +` → `Bancada`). Não encosta no ComunicaAI.

**Você termina com:** a URL do webhook.

## 2. Ligar o site no Make · 2 min

Abra `bancada-diagnostico.html`, procure no início do script:

```js
var WEBHOOK = "";
```

Cole a URL entre as aspas. O selo no canto muda de "Protótipo" para "Ao vivo"
sozinho, e o modo de demonstração desliga.

## 3. Site no Framer · ~1h30 · **só você pode fazer**

1. Conta gratuita em framer.com
2. Seções montadas visualmente: capa, serviços, como funciona, dúvidas, rodapé
3. Um bloco **Embed** com o conteúdo inteiro de `bancada-diagnostico.html`
4. Conferir nos três tamanhos (desktop, tablet, celular)
5. Publicar

**Você termina com:** a URL pública `.framer.website`.

## 4. Leitura da fila · ~30 min · opcional, mas é o diferencial

Segundo cenário no Make: webhook (GET) → *Data store → Search records* →
webhook response em JSON. Depois trocar, no painel interno, a leitura do
`localStorage` por um `fetch` nesse webhook.

Se o prazo apertar, **corte este passo**. O painel continua funcionando com os
dados locais e o trabalho continua completo — só perde um argumento no vídeo.

## 5. Evidências · ~20 min

Os cinco prints listados no README, em `docs/prints/`. O do Lighthouse é o que
mais conta: no Chrome, F12 → Lighthouse → Accessibility → Analyze.

## 6. README · 5 min

Já está escrito. Falta só colar a URL do Framer no topo e conferir se os nomes
dos prints batem.

## 7. Documento da parte teórica

Está no Google Docs, na pasta do Drive, com os seis itens que o enunciado exige.
Cinco já estão escritos. O que falta preencher só existe depois dos passos 1 e 3:
o que o Framer te impediu de fazer, e o que você aprendeu montando o cenário.

## 8. Vídeo · até 4 min

Roteiro cronometrado em `docs/roteiro-video.md`. Grave a tela com o site real
aberto, publique como não listado e **abra o link numa aba anônima** antes de
entregar.

---

## Duas coisas para resolver fora daqui

**O enunciado pula do item 3 para o item 5** — não existe item 4. E a seção que
se chama "distribuição da pontuação" não distribui nada: a frase termina em
*"totalizando."*. Pergunte ao professor quanto vale cada parte.

**Créditos do Make:** 799,5 de 1000, renovando em 7 dias. Cada diagnóstico com
log custa cerca de 7. Dá para uns 100 testes — suficiente, mas não fique
enviando formulário à toa, e confira o saldo antes de gravar o vídeo.
