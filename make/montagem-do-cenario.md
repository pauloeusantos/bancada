# Cenário no Make — Bancada

> **Regra número um:** não abra, não duplique e não edite o cenário do
> ComunicaAI. Tudo aqui é novo: pasta nova, cenário novo, webhook novo, data
> store novo. O ComunicaAI continua no ar sem ser tocado.

Time: `2850909` · zona `us2` · plano Free (799,5 de 1000 créditos, 1 de 2
cenários ativos na última verificação).

## 0. Separar do outro trabalho

Em **Scenarios**, no menu lateral, clique no **+** ao lado de *Folders* e crie
a pasta `Bancada`. Crie o cenário dentro dela.

## 1. Webhook

Módulo **Webhooks → Custom webhook**. Ja criado, com o nome `bancada`:

    https://hook.us2.make.com/fzdmkk59mwst5p2aj8271m2ndcdmnkp5

Essa URL ja esta colada na constante `WEBHOOK` do `bancada-diagnostico.html`.

Campos que o site envia (form-urlencoded): `protocolo`, `nome`, `fone`,
`aparelho`, `idade`, `descricao`. No prompt eles aparecem como `{{2.campo}}`
porque o webhook é o módulo 2 na numeração do Make.

Para o Make aprender a estrutura: clique em *Redetermine data structure*,
abra o site e envie um diagnóstico de teste.

## 2. IA

Módulo **AI by Make → Simple Text Prompt** (o mesmo que funcionou no outro
trabalho). Modelo: **Claude Haiku 4.5**.

> Não use `Recommended: Medium`. No ComunicaAI esse modelo já falhou em seguir
> bloco de instrução estruturada — e aqui a saída precisa ser JSON exato.

Cole o conteúdo de `prompt-triagem.txt` no campo de prompt.

**Cuidado conhecido:** depois de colar, confira se os tokens `{{2.aparelho}}`,
`{{2.idade}}` e `{{2.descricao}}` voltaram **coloridos**. Se aparecerem como
texto cinza, o mapeamento morreu — apague o campo e monte de novo clicando nas
variáveis do painel lateral em vez de colar.

## 3. Resposta ao site

Módulo **Webhooks → Webhook response**.

- Status: `200`
- Body: `{{3.result}}` (o resultado do módulo de IA — confira o número)
- Headers:
  - `Content-Type` = `application/json; charset=utf-8`
  - `Access-Control-Allow-Origin` = `*`

O segundo header não é opcional. Sem ele o navegador bloqueia a resposta e o
site mostra erro mesmo com o cenário funcionando.

## 4. Fila (Data store)

Crie um data store novo chamado **`Bancada - Fila`** — não reaproveite o
`ComunicaAI - Log de Geracoes`.

Campos:

| campo | tipo |
|---|---|
| protocolo | text |
| criadoEm | date |
| nome | text |
| fone | text |
| aparelho | text |
| idade | text |
| descricao | text |
| chave | text |
| confianca | number |
| urgencia | text |
| resumo | text |
| status | text |

Módulo **Data store → Add/replace a record**, depois do webhook response.
Em `status`, valor fixo `Recebido`.

> **Armadilha do outro projeto:** `or` não existe como função no Make.
> `if(or(a;b);x;y)` quebra com *Function 'or' not found* — e o pior é que o
> cenário continua respondendo ao usuário enquanto só o log falha. Use `if`
> aninhado se precisar de condição.

## 5. Testar sem gastar crédito à toa

Cada execução com log custa em torno de 7 créditos. Teste pela linha de
comando antes de testar pelo site:

```bash
curl -X POST "https://hook.us2.make.com/fzdmkk59mwst5p2aj8271m2ndcdmnkp5" \
  --data-urlencode "protocolo=BCD-TESTE-001" \
  --data-urlencode "nome=Teste" \
  --data-urlencode "fone=(31) 90000-0000" \
  --data-urlencode "aparelho=celular" \
  --data-urlencode "idade=medio" \
  --data-urlencode "descricao=caiu na piscina e agora nao liga, tentei ligar e esquentou"
```

> Use `--data-urlencode`, nunca `-F`: com `-F` o valor é cortado no primeiro
> ponto e vírgula e você passa uma hora caçando um bug que não existe.

A resposta tem que ser JSON puro, começando em `{` e terminando em `}`. Se vier
com ```` ```json ```` em volta, reforce no prompt que a saída é só o objeto.

## 6. Ligar

Ative o agendamento. Só então cole a URL na constante `WEBHOOK` do arquivo e
republique o site.
