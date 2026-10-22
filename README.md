# Biblioteca SESI – Acervo Pergamum (V3)

Catálogo para consulta em totem da Escola SESI Dom Bosco. Fonte: Relatório Pergamum de 22/10/2026, 536 páginas.

- 5.362 registros bibliográficos, 7.230 exemplares; inclui DVDs e outros materiais, não somente livros.
- Cada entrada tem quantidade, número(s) de exemplar, código de acervo, classificação e referência bibliográfica.
- Busca por título, autor, ISBN e códigos. Listagem paginada para desempenho do totem.
- Capas carregadas no navegador pela Open Library apenas quando há ISBN formalmente válido. `?default=false` faz exibir a capa genérica se a edição não constar na base. **Não há validação visual de 4.000+ capas nem download em massa**. Capas da Open Library podem divergir em diferentes tiragens mesmo sob ISBN similar.
- A biblioteca tem ISBNs com erros ou ausentes e alguns títulos extraídos de forma imperfeita; confira `revisarCadastro` e o campo `bibliografia` antes de correções.
- `prateleira` é 'Consultar bibliotecário': o relatório tem classificação, mas não posição física da prateleira.
- A quantidade representa exemplares cadastrados no relatório; não é situação de empréstimo/disponibilidade em tempo real.
- A área de gerenciamento armazena importações apenas no navegador local; não é admin autenticado nem banco central.

## Executar

Na pasta com index.html: `python -m http.server 8080` e acesse `http://localhost:8080`. Para testar via nuvem, envie a pasta ao Firebase Hosting ou GitHub Pages.

## Dados

`acervo-pergamum.json` – catálogo principal. `estatisticas-acervo.json` – métricas e notas de qualidade. `acervo.json` – os 33 registros de demonstração da versão anterior, preservados separadamente e não contados como inventário Pergamum.

Referência de capas: https://openlibrary.org/dev/docs/api/covers


## V4: sistema de capas
- Mantém 23 capas originais vinculadas pelo título aos registros Pergamum (outras capas do acervo original são mantidas na pasta assets).
- Busca primeiro capa por ISBN/edição (Open Library e Google Books); em seguida, quando necessário, busca por título/autor.
- As capas remotas **não estão baixadas no ZIP**: precisam de internet no totem e podem não existir nas fontes externas. Capas por título/autor podem ser de edição diferente.
- Busca por demanda para as capas visíveis, em fila limitada, e registra resultados no `localStorage`.
- Placeholder SVG local sem mensagem 'Aguarde'.
- Para atualizar GitHub Pages, substitua arquivos da raiz preservando a pasta `assets`. Após publicar, use Ctrl+F5 no navegador.

## V5 — fontes e limites reais das capas

- O catálogo foi mantido com todos os 5.362 registros do Pergamum.
- Capas locais anteriores continuam preservadas, e a interface deixa de depender de `assets/default.jpg`.
- Primeiro tenta Google Books por ISBN conferido no campo `industryIdentifiers`; depois Open Library pela edição ISBN. Se não houver imagem, pesquisa Open Library e Google Books por título e autor.
- Resultados por título/autor **podem ser capas de outras edições**: no cache local (`sesi-covers-cache-v5`), o campo `method` registra sua origem e se a edição foi confirmada.
- Se não houver imagem verificada, gera uma capa ilustrativa com o nome da obra, explicitamente marcada `CAPA A CONFIRMAR`. Isso NÃO é uma reprodução da capa verdadeira.
- Os serviços externos podem impor limites, falhar ou ter imagens ausentes. Este ZIP não contém 5.362 capas verificadas e não foi feita coleta em massa. Os serviços consultados precisam estar acessíveis no navegador do totem.
- Fontes oficiais: https://openlibrary.org/dev/docs/api/covers e https://developers.google.com/books/docs/v1/reference/volumes.
- **Atualização:** no GitHub, substitua os arquivos do repositório com o conteúdo extraído desta pasta. Depois abra em janela anônima ou Ctrl+F5. O cache tem nome novo para permitir nova consulta.
