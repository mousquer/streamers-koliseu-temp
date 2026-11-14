# Lista de streamers da extensão Koliseu Live

A extensão lê o arquivo `canais.json` deste repositório.
Mudou aqui, todo mundo recebe em poucos minutos (o GitHub pode levar até ~5 min para atualizar).

## Como mexer (pelo site do GitHub)

1. Abra `canais.json` e clique no lápis (Edit).
2. Faça a mudança e clique em **Commit changes**.

### Adicionar um streamer

Copie uma linha e troque os dados. Vírgula entre as linhas, **sem vírgula depois da última**.

```json
{ "platform": "twitch", "login": "login_do_canal", "name": "Nome que aparece" },
```

- `platform`: `twitch` ou `kick`
- `login`: o que vem depois de `twitch.tv/` ou `kick.com/` (minúsculas)
- Quem tem os dois: uma linha para cada plataforma, com o mesmo `name`.

### Pausar alguém (fora de contrato, férias...)

Acrescente `"active": false` na linha dele. Para voltar, apague esse pedaço.

```json
{ "platform": "twitch", "login": "phziin_stx", "name": "Phziin", "active": false },
```

### Aviso para todo mundo

Escreva no campo `"message"` lá em cima (até 200 caracteres). Ex.: `"message": "War hoje às 21h!"`.
Para tirar, deixe `"message": ""`.

## Cuidados

- Antes de salvar, cole o conteúdo em https://jsonlint.com para conferir se não quebrou nada.
  Se o arquivo quebrar, a extensão continua usando a última lista boa que ela já baixou.
- A extensão ignora logins inválidos e monta os links sozinha (twitch.tv/... e kick.com/...),
  então ninguém consegue usar esta lista para mandar a galera para outro site.
- Proteja a conta do GitHub com verificação em duas etapas: quem consegue editar este arquivo
  escolhe quem aparece na extensão.

Quando o site do KoliseuOT tiver o endereço `/api/streamer/extensao`, a extensão passa a usar o
cadastro do site e esta lista vira só reserva.
