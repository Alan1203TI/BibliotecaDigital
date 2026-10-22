# Biblioteca SESI – Acervo Pergamum (V3)

Catálogo para consulta em totem da Escola SESI Dom Bosco. Fonte: Relatório Pergamum de 22/10/2026, 536 páginas.

- 5.362 registros bibliográficos, 7.230 exemplares; inclui DVDs e outros materiais, não somente livros.
- Cada entrada tem quantidade, número(s) de exemplar, código de acervo, classificação e referência bibliográfica.
- Busca por título, autor, ISBN e códigos. Listagem paginada para desempenho do totem.
- Capas carregadas no navegador pela Open Library apenas quando há ISBN formalmente válido. `?default=false` faz exibir a capa genérica se a edição não constar na base. **Não há validação visual de 4.000+ capapas da Open Library podem divergir em diferentes tiragens mesmo sob ISBN similar.
- A biblioteca tem ISBNs com erros ou ausentes e alguns títulos extraídos de forma imperfeita; confira `revisarCadastro` e o campo `bibliografia` antes de correções.
- `prateleira` é 'Consultar bibliotecário': o relatório tem classificação, mas não posição física da prateleira.
- A quantidade representa exemplares cadastrados no relatório; não é situação de empréstimo/disponibilidade em tempo real.
- A área de gerenciamento armazena importações apenas no navegador local; não é admin autenticado nem banco central.

## Executar

Na pasta com index.html: `python -m http.server 8080` e acesse `http://localhost:8080`. Para testar via nuvem, envie a pasta ao Firebase Hosting ou GitHub Pages.

## Dados

`acervo-pergamum.json` – catálogo principal. `estatisticas-acervo.json` – métricas e notas de qualidade. `acervo.json` – os 33 registros de demonstração da versão anterior, preservados separadamente e não contados como inventário Pergamum.

Referência de capas: https://openlibrary.org/dev/docs/api/covers
