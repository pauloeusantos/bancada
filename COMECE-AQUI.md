# O que falta fazer — Bancada

Atualizado em 02/10/2026. O trabalho está pronto para entregar: falta só gravar o
vídeo e postar.

**Site publicado:** https://blushing-yard-728562.framer.app
**Repositório:** https://github.com/pauloeusantos/bancada
**Cenário no Make:** `Bancada - Triagem`, id 6395845, ativo

---

## Conferido no site publicado

| O que o enunciado pede | Onde está |
|---|---|
| Parte teórica com os seis itens | `docs/parte-teorica-abnt.pdf` (ABNT) e Google Doc "Bancada - Parte teorica (ABNT)" |
| Interface funcional e responsiva | Site publicado, testado a 1200, 900 e 390 px, sem rolagem horizontal |
| Navegação e interação | Botão da capa leva ao diagnóstico; abas, formulário, ficha, fila interna |
| Personalização com HTML, CSS e JavaScript | `bancada-diagnostico.html`, dentro do Embed do Framer |
| Integração com IA | Make + Claude Haiku: webhook → IA → resposta em JSON, 3 a 4 s, ~6 créditos |
| Evidências da aplicação funcionando | Seis prints em `docs/prints/`, incluindo o Make e o Lighthouse |
| Link público | https://blushing-yard-728562.framer.app |
| README com tudo o que o enunciado lista | `README.md` |
| Vídeo pitch de até 4 minutos | **falta gravar** — roteiro em `docs/roteiro-video.md` |

Acessibilidade medida no site publicado: **0 violações** de WCAG 2.1 A/AA pelo
axe-core a 1200, 900 e 390 px, em tema claro e escuro, em quatro estados da tela;
**98/100** no Lighthouse.

---

## Falta você fazer

### 1. Subir esta versão no GitHub — 1 minuto

O commit já está feito no seu computador; só falta enviar:

```powershell
cd "$env:USERPROFILE\Downloads\RockeSeat\materia 2\bancada"
git push
```

### 2. Gravar o vídeo — uns 40 minutos com ensaio

Siga o Google Doc **"Bancada - Roteiro do video (gravacao)"** (o mesmo conteúdo está
em `docs/roteiro-video.md`): checklist antes de gravar, as seis abas que ficam
abertas, sete cenas com o que mostrar e o que falar, e o que fazer se algo der
errado. Publique no YouTube como **não listado** e teste o link numa aba anônima.

**Antes de gravar, confira o saldo de créditos do Make:** cada diagnóstico consome
cerca de 6,5.

### 3. Postar a entrega — 5 minutos

O texto pronto está na seção 6 do roteiro. Anexe o arquivo
**Bancada - Parte teorica (ABNT).pdf**, que está em `Downloads\RockeSeat\materia 2`.

---

## Uma coisa para resolver com o professor

O enunciado **pula do item 3 para o item 5** — não existe item 4. E a seção chamada
"distribuição da pontuação" não distribui nada: a frase termina em *"totalizando."*.
Vale perguntar quanto vale cada parte.

---

## Opcional, depois da entrega

**Fila compartilhada.** Hoje o painel interno lê os protocolos do próprio navegador.
Para a fila valer entre máquinas: um segundo cenário no Make com webhook GET → Data
store *Search records* → resposta JSON, e trocar a leitura no componente.

**Nome do projeto.** O Framer criou o projeto como "Blushing Yard", e isso aparece na
URL. Em Publish → *Get free domain* dá para trocar. Se trocar, atualize a URL no
README, na parte teórica e no roteiro.
