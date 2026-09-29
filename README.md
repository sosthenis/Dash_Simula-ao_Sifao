# Painel Técnico — Sifões Lote 4 / Eixão das Águas

Aplicativo estático preparado para publicação no **GitHub Pages**. Consolida o dossiê técnico, a análise de transientes, a metodologia de medição de vazão e as geometrias relevantes do arquivo `SISTEMA geral.kmz`.

## Estrutura

- `index.html` — aplicação principal.
- `assets/app.css` — identidade visual institucional e layout responsivo.
- `assets/app.js` — simulações, gráficos, mapa e animação.
- `data/eixao-data.js` — geometrias KMZ embarcadas em JavaScript para funcionar também localmente.
- `data/eixao_lote4.geojson` — cópia GeoJSON das geometrias extraídas.
- `.github/workflows/pages.yml` — deploy automático no GitHub Pages.
- `.nojekyll` — evita processamento pelo Jekyll.

## Publicar no GitHub Pages

1. Crie um repositório no GitHub, por exemplo `eixao-sifoes-lote4`.
2. Envie todos os arquivos desta pasta para a branch `main`.
3. Em **Settings → Pages**, selecione **GitHub Actions** como fonte.
4. O workflow incluído publicará o site automaticamente a cada `push` em `main`.

## Premissas importantes

O simulador usa os resultados documentais do HAMMER e da fórmula de Allievi para 1–16 min. Para tempos maiores, aplica extrapolação de screening aproximadamente inversa ao tempo. Para vazões diferentes de 9,5 m³/s, a componente transitória é escalada linearmente pela razão de vazões/velocidades. Essas aproximações são exploratórias e **não substituem** nova rodada do modelo oficial com os dados `as built` e condições de contorno reais.

O mapa foi convertido para um renderizador vetorial SVG próprio, 100% offline, usando diretamente as geometrias extraídas do KMZ. Não há dependência de Leaflet, OpenStreetMap, servidores de tiles ou chaves de API; portanto, o erro HTTP 403 de tiles não ocorre mais.


## Mapa offline

- Zoom por roda do mouse e botões +/-.
- Pan por arraste.
- Filtros para canais, trechos tubulares, seis sifões e proteção catódica.
- Clique em pontos/linhas para detalhes.
- Coordenadas aproximadas exibidas no rodapé do mapa.
- Geometrias provenientes de `data/eixao_lote4.geojson`, extraídas do KMZ fornecido.
