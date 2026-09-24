# Vídeo pitch — Bancada (máximo 4 minutos)

O enunciado pede seis coisas no vídeo: problema e solução, aplicação
funcionando, plataforma no-code usada, personalizações com padrões web,
integração/IA, e o diferencial. O roteiro abaixo cobre as seis, nessa ordem,
com tempo de sobra.

Grave a tela com o site aberto de verdade. Sem slide.

---

## 0:00 – 0:25 · O problema (tela: rede social de uma assistência qualquer)

> "Toda assistência técnica de bairro perde cliente no mesmo ponto: a pessoa
> chega no direct perguntando 'quanto custa trocar a tela?' e a resposta
> honesta é 'depende'. Aí ela some. A Bancada resolve isso: o cliente descreve
> o problema com as palavras dele e recebe um diagnóstico antes de sair de
> casa."

## 0:25 – 1:15 · A aplicação funcionando (tela: o site, no celular)

Mostre, sem narrar cada clique: escolher o aparelho, ditar o problema por voz,
enviar. Enquanto carrega:

> "O que ele acabou de fazer foi falar. A descrição veio pelo microfone, usando
> a Web Speech API do próprio navegador."

Quando a ficha aparecer, pare em cada bloco:

> "Provável causa, o quanto o sistema confia nessa leitura, faixa de preço,
> prazo, e — esse é o ponto — o que ele entendeu do relato. O cliente consegue
> conferir se foi entendido."

## 1:15 – 1:45 · A plataforma no-code

> "O site é feito no Framer. As seções institucionais são visuais, montadas
> arrastando. Mas o Framer não tem um componente de triagem técnica — e é aí
> que a disciplina começa."

## 1:45 – 2:35 · As personalizações com padrões web

Mostre o painel de Embed no Framer com o código dentro.

> "Esse bloco inteiro é HTML, CSS e JavaScript escritos à mão, embutidos no
> Framer. Sem biblioteca nenhuma. As abas seguem o padrão de acessibilidade do
> W3C e andam com as setas do teclado; o resultado é anunciado por leitor de
> tela; os erros do formulário viram uma lista clicável; o tema claro e escuro
> vem de tokens CSS; e nada disso quebra em 390 pixels de largura."

Passe o Tab algumas vezes na tela para mostrar o foco visível.

## 2:35 – 3:20 · A IA e a automação

Mostre o cenário do Make rodando.

> "O formulário envia o relato para um cenário no Make, que chama o Claude. E
> aqui está a decisão de projeto mais importante: a IA não escreve o texto que
> o cliente lê. Ela devolve JSON — categoria, confiança, os fatos que extraiu,
> e as perguntas que o técnico precisa confirmar naquele caso. Quem desenha a
> tela é o JavaScript."

> "Preço e prazo não passam pela IA. Saem do catálogo da loja. Assim o modelo
> não tem como inventar um valor para o cliente."

## 3:20 – 3:50 · O diferencial

Mostre a aba Bancada interna.

> "E a mesma triagem alimenta a fila do técnico, já ordenada por urgência. O
> caso que piora sozinho sobe para o topo. A automação não é enfeite no site —
> ela organiza a operação."

## 3:50 – 4:00 · Fecho

> "Bancada. Feito em plataforma no-code, mas com os padrões da web fazendo o
> trabalho que a ferramenta visual não faz."

---

## Antes de gravar

- Rode um diagnóstico uma vez para aquecer o cenário; o primeiro costuma demorar mais.
- Confira o saldo de créditos do Make — sem crédito, a demonstração falha ao vivo.
- Se for gravar com o celular na mão, use o site publicado, não o arquivo local.
- Publique como **não listado** no YouTube e abra o link numa aba anônima para conferir que abre.
