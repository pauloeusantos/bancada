# O que falta fazer — Bancada

Atualizado em 01/10/2026. A aplicação está no ar, auditada e testada de ponta a ponta.

**Site publicado:** https://blushing-yard-728562.framer.app
**Repositório:** https://github.com/pauloeusantos/bancada
**Cenário no Make:** `Bancada - Triagem`, id 6395845, ativo

---

## Já está pronto

- Cenário no Make no ar: webhook → Claude Haiku → resposta em JSON com CORS. 6 créditos e ~3 s por diagnóstico.
- Componente de triagem em HTML/CSS/JS embutido no Framer nos três breakpoints, com o mesmo código nos três.
- Site no Framer publicado, com capa, serviços, como funciona, diagnóstico, dúvidas e rodapé.
- Título, descrição e idioma do site preenchidos; `pt-BR` no `<html lang>` e redução de movimento ligada nas configurações do Framer.
- Auditoria de acessibilidade no site publicado: **0 violações** de WCAG 2.1 A/AA pelo axe-core a 1200, 900 e 390 px, em tema claro e escuro, nos três estados da tela; **98/100** no Lighthouse.
- Cinco prints em `docs/prints/`, incluindo o relatório do Lighthouse.
- Parte teórica em ABNT no Google Drive, com os dois trechos `[PREENCHER]` já respondidos.
- Roteiro do vídeo cronometrado.

---

## Falta você fazer

### 1. Dar push no repositório — 1 minuto

O commit desta versão **já está feito** no seu computador. Falta só enviar, porque o
envio pede o seu login do GitHub:

```powershell
cd "$env:USERPROFILE\Downloads\RockeSeat\materia 2\bancada"
git push
```

### 2. Um print que só você consegue tirar — 5 minutos

`docs/prints/05-cenario-make.png` — o cenário aberto no Make, com os três módulos
e um histórico de execução em verde. Salve o arquivo com esse nome dentro de
`docs/prints/` e suba:

```powershell
cd "$env:USERPROFILE\Downloads\RockeSeat\materia 2\bancada"
git add -A
git commit -m "Print do cenario no Make"
git push
```

### 2. Formatação ABNT do documento — 10 minutos

No Google Doc **"Bancada - Parte teorica (ABNT)"** o texto já está correto e completo.
Falta só aplicar a formatação (as regras estão listadas no fim do próprio documento):
fonte Arial 12, entrelinha 1,5, recuo de 1,25 cm na primeira linha de cada parágrafo,
margens 3-2-3-2 cm e títulos numerados.

### 3. Gravar o vídeo — até 4 minutos

Roteiro cronometrado no Google Doc **"Bancada - Roteiro do video"**. Grave a tela com o
site publicado aberto, publique como não listado no YouTube e abra o link numa aba
anônima antes de entregar.

**Antes de gravar, confira o saldo de créditos do Make:** cada diagnóstico consome 6.

---

## Uma coisa para resolver com o professor

O enunciado **pula do item 3 para o item 5** — não existe item 4. E a seção chamada
"distribuição da pontuação" não distribui nada: a frase termina em *"totalizando."*.
Vale perguntar quanto vale cada parte.

---

## Opcional, se sobrar tempo

**Fila no Data store do Make.** Hoje o painel interno lê os protocolos do navegador.
Para ler do Make: um segundo cenário com webhook GET → Data store *Search records* →
resposta JSON, e trocar a leitura no componente. Se o prazo apertar, corte — o trabalho
continua completo sem isso.

**Nome do projeto.** O Framer criou o projeto como "Blushing Yard", e isso aparece na URL.
Em Publish → *Get free domain* dá para trocar para algo como `bancada.framer.app`.
Se trocar, atualize a URL no README e na parte teórica.
