# Pixar em dados: avaliações, bilheterias e prêmios

Projeto final de **Visualização de Dados** | SENAI CIC, Turma Bosch (2026) | **Equipe MARCH**.

## Equipe

- Erich Natal ([@erichnatal](https://github.com/erichnatal))
- Igor Machado ([@igromachado](https://github.com/igromachado))
- Pedro Marinho ([@PedroGM56](https://github.com/PedroGM56))
- Phillipe Mugnaini ([@PhillipeMugnaini](https://github.com/PhillipeMugnaini))
- Thiago Vilhena ([@Thiago-soulz](https://github.com/Thiago-soulz))

## Tema e objetivo

O projeto investiga como se relacionam a aceitação de filmes da Pixar, o desempenho de bilheteria, o gênero e o reconhecimento em premiações. A amostra contém **28 filmes com lançamentos de 1995 a 2024**. As conclusões são **descritivas** e limitadas à amostra.

## Perguntas de pesquisa

1. Como as avaliações e a bilheteria dos filmes da Pixar variaram ao longo dos anos?
2. Quais gêneros apresentam as maiores e menores avaliações médias do público?
3. Quais filmes da Pixar receberam mais indicações e vitórias no Oscar?
4. Existe relação entre a bilheteria mundial e a avaliação dos filmes da Pixar?

## Dados

Os cinco CSVs originais encontram-se em `src/projeto_data_viz_pixar/data/originais/`.

| Dataset | Registros originais | Informações principais |
|:--|--:|:--|
| `pixar_films.csv` | 28 | Filme e data de lançamento |
| `box_office.csv` | 28 | Orçamento e bilheteria mundial |
| `public_response.csv` | 28 | IMDb, Rotten Tomatoes e outras avaliações |
| `genres.csv` | 204 | Gêneros e subgêneros (mais de um por filme) |
| `academy.csv` | 89 | Categoria e status no Oscar |


## Principais resultados

- A correlação linear de Pearson entre nota IMDb e bilheteria mundial foi **r = 0,296**: positiva, porém fraca. Nota alta, por si só, não determina bilheteria alta.
- **WALL-E** e **Coco** são os dois filmes com maior IMDb na amostra (**8,4**).
- **Inside Out 2** tem a maior bilheteria mundial informada (aproximadamente **US$ 1,70 bilhão**).
- Nos registros originais de `academy.csv`, **WALL-E** contabiliza **6 ocorrências de indicação ou vitória**, enquanto **Up** e **Toy Story 3** apresentam **2 vitórias cada**.
- **19 de 28 filmes** têm pontuação de **90 ou mais** no Rotten Tomatoes.



## Como executar

Recomendado: **Python 3.13 ou superior**. Na raiz do repositório:

```bash
python -m venv .venv
# Linux / macOS:
source .venv/bin/activate
# Windows PowerShell:
# .venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python -m pip install jupyterlab
```

Abra os notebooks de acordo com o **diretório de trabalho** usado para os caminhos relativos:

1. `src/projeto_data_viz_pixar/data/treatment.ipynb`: execute com o diretório de trabalho em `src/projeto_data_viz_pixar/data/`. Faz a preparação e salva as bases em `data/limpos/`.
2. `src/projeto_data_viz_pixar/main/main.ipynb`: execute com o diretório de trabalho em `src/projeto_data_viz_pixar/main/`. Produz os gráficos originais em `src/projeto_data_viz_pixar/imgs/`.
3. Para reproduzir os **gráficos revisados da documentação**, execute na raiz:

```bash
python docs/gerar_graficos_etapa4.py
```

Os nove PNGs revisados ficam em `docs/figuras_etapa4/`. O script não modifica os notebooks, os CSVs nem a pasta original `imgs/`.

## Organização

```text
README.md
requirements.txt
pyproject.toml
src/projeto_data_viz_pixar/
  data/
    originais/         # CSVs fonte
    limpos/            # CSVs preparados pelos autores
    treatment.ipynb    # tratamento original
  main/main.ipynb      # nove gráficos originais
  imgs/                # PNGs originais

docs/
  documentacao.pdf
  apresentacao.pdf
  figuras_etapa4/      # nove gráficos revisados
  gerar_graficos_etapa4.py
  roteiro_apresentacao.md
  notas_validacao.md
```

## Documentação e apresentação

- [Documentação técnica (PDF)](src/projeto_data_viz_pixar/docs/DOCUMENTAÇÃO.pdf)
- [Apresentação final (PDF)](src/projeto_data_viz_pixar/docs/apresentacao.pdf)



