# Simulação de ensaio de fungicida em soja

Pipeline reprodutível com publicação automática via GitHub Actions e GitHub Pages.

A cada push no repositório, o workflow executa a simulação dos dados e publica o relatório atualizado automaticamente.

## Estrutura do projeto

```
soja_actions/
├── .github/
│   └── workflows/
│       └── pipeline.yml
├── R/
│   └── 01_simular_dados.R
├── report/
│   └── relatorio_simulacao.qmd
├── data/
└── README.md
```

## O que o pipeline faz

1. Instala R 4.4.1 e Quarto no Ubuntu
2. Instala os pacotes via Posit Package Manager (binários pré-compilados)
3. Roda o script de simulação e gera os dados
4. Renderiza o relatório Quarto
5. Publica o HTML no GitHub Pages automaticamente

## Como ativar o GitHub Pages

1. Vá em Settings > Pages no repositório
2. Em Source, selecione **GitHub Actions**
3. Faça um push qualquer para disparar o primeiro workflow

O relatório estará disponível em:

```
https://seu-usuario.github.io/soja_actions/relatorio_simulacao.html
```

## Como reproduzir localmente

```r
source("R/01_simular_dados.R")
quarto::quarto_render("report/relatorio_simulacao.qmd")
```

## Pacotes utilizados

| Pacote | Função |
|---|---|
| `tidyverse` | Manipulação e visualização de dados |
| `ggplot2` | Gráficos |
| `knitr` | Tabelas no relatório |
| `quarto` | Relatório reprodutível |

## Autora

Jennifer Luz Lopes
