# Pódio Post

App web (site que funciona como app no celular) para atletas transformarem a foto do treino ou da prova em uma imagem pronta para o Instagram, no formato Story (9:16) ou Feed (4:5).

## Público
Atletas de corrida, ciclismo, HYROX, CrossFit e futebol. Organizadores de corridas são parceiros pagantes: cada corrida parceira ganha um pacote com a arte oficial dela dentro do app.

## Como o atleta usa
1. Início: escolhe a foto (ou usa a foto de exemplo).
2. Modelo: escolhe um dos 8 modelos em cards (Percurso, Peito, Gigante, Discreto, Relógio, Medalha, Recibo, TV), já mostrados com a foto dele, e toca em Editar.
3. Editor: ajusta tudo pela barra de ferramentas (Foto, Treino, Mapa, Estilo, Logo, Corrida, Legenda) e salva/compartilha.

## Funções principais
- Mapa do percurso a partir do arquivo GPX do Strava/Garmin, com 6 estilos (Linha, Radar, Carta antiga, Metrô, Navegação, 8-bit).
- Imagem do Strava (a figurinha salva ao compartilhar, a das parciais, um print): a pessoa escolhe entre **Arte do Strava** (a imagem inteira vira o modelo "Arte do Strava", sem o fundo vazio, com a logo e a arte da corrida; com o recorte, fica atrás do atleta), **Dados e mapa** (o app lê o percurso e os números e monta no modelo escolhido) ou **Os dois** (a arte por cima do modelo, no espaço mais livre). A escolha fica guardada no aparelho. Se a imagem não tiver mapa nem números legíveis, ela entra como arte.
- Números do treino: distância, tempo, ritmo, elevação e data (preenchidos pelo GPX ou à mão).
- Todos os itens podem ser movidos, aumentados e girados com os dedos.
- Foto: zoom, escurecer, degradê de baixo para cima (cor, intensidade, início e fim).
- Recorte de atleta automático (MediaPipe no próprio aparelho): números e mapa atrás da pessoa, logos na frente. Ajuste da borda (mais justa ou mais solta), pincel e borracha com zoom de dois dedos.
- Imagem salva na resolução da foto original (até ~16 MP) ou leve (1080 px).
- Logo padrão do fotógrafo Bruno Aires em 4 versões, pequena e discreta no canto; logo extra liberada por código de acesso.
- Itens escondidos pelo olho voltam pelo botão “Mostrar ocultos”.
- Pacote da corrida: logo da corrida, faixa de patrocinadores, moldura oficial (story e feed), nome, data, distâncias, cor, hashtag e @ nas legendas.
- Cada corrida tem link próprio (/c/nome-da-corrida) e pode aparecer na lista de corridas parceiras.
- Futebol: nome e cor dos times, placar e tempo de jogo, em 3 modelos (TV, Telão e Gigante).
- Adesivos holográficos (aba Adesivo): Eu vou / Eu fui / Tô dentro (no adesivo redondo holográfico do Bruno, com data e o nome da corrida parceira na borda), Tá pago, 10 km, 5 km e 3 km (a distância da prova recortada como adesivo, inclinada, com a etiqueta KM), Ritmo (ingresso com o tempo no canhoto) e Recorde (PR). O km embaixo do Eu vou e do Recorde é digitado pela pessoa na aba (vazio = sem km); o canto fica descolando e eles ficam na frente do atleta, movidos e girados com os dedos.
- Legendas prontas, sugestões de música e dicas de pose.

## Corridas parceiras
- Movimento com Conexão — link: /c/movimento-com-conexao (logo, moldura story e feed, faixa de patrocinadores)

## Tecnologia
- Site estático, sem build: HTML, CSS e JavaScript puro em um único index.html, desenho feito em canvas.
- Hospedagem: Vercel.
- Sem servidor: tudo roda no celular do atleta; a foto não é enviada para lugar nenhum.

## Estrutura
- `index.html` — o app inteiro
- `corridas/corridas.js` — lista das corridas parceiras (`window.PODIO_RACES`)
- `corridas/<id>/` — artes de cada corrida (`logo.png`, `patrocinadores.png`, `moldura-story.png`, `moldura-feed.png`)
- `adesivos/` — o adesivo holográfico redondo (`holo-circulo.webp`) e a textura holográfica (`holo-textura.jpg`) usada nos outros adesivos
- `icons/` — ícones do app
- `manifest.webmanifest` — instalação na tela inicial do celular
- `og.jpg` — imagem de prévia do link
- `vercel.json` — rotas (`/c/:id`) e cabeçalhos

## Próximos passos
- Story animado (vídeo curto).
- Fotos da prova dentro do app, buscadas pelo número de peito.
