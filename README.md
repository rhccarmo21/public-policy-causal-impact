# 🔍 Public Policy Causal Impact

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXX)
![Tests](https://github.com/seu-usuario/public-policy-causal-impact/actions/workflows/tests.yml/badge.svg)

Framework para avaliação causal de políticas públicas usando métodos quasi-experimentais e aprendizado de máquina.

## 📌 Tabela de Conteúdos
- [Visão Geral](#-visão-geral)
- [Métodos Implementados](#-métodos-implementados)
- [Instalação](#-instalação)
- [Uso Básico](#-uso-básico)
- [Exemplo Prático](#-exemplo-prático)
- [Fluxo de Análise](#-fluxo-de-análise)
- [Dataset de Exemplo](#-dataset-de-exemplo)
- [Roadmap](#-roadmap)
- [Contribuição](#-contribuição)
- [Publicações](#-publicações)
- [Licença](#-licença)
- [Contato](#-contato)

## 🌐 Visão Geral
Este projeto implementa técnicas avançadas para:
- Identificar relações causais em políticas públicas
- Medir efeitos de intervenções governamentais
- Contabilizar vieses de seleção e confundimento
- Gerar contrafatuais confiáveis

## 🧮 Métodos Implementados
| Método | Descrição | Melhor Para |
|--------|-----------|-------------|
| **Differences-in-Differences** | Comparação antes/depois entre grupos | Intervenções escalonadas |
| **Synthetic Control** | Construção de grupo de controle sintético | Poucas unidades tratadas |
| **Matching** | Pareamento por propensity score | Dados observacionais |
| **RDD** | Regression Discontinuity Design | Elegibilidade com cutoff |
| **Causal Forests** | Métodos baseados em árvores | Efeitos heterogêneos |

## ⚙️ Instalação
```bash
# Via pip
pip install policy-causal-impact

# Ou para desenvolvimento
git clone https://github.com/seu-usuario/public-policy-causal-impact.git
cd public-policy-causal-impact
pip install -e .

🚀 Uso Básico

from causal_impact import PolicyEvaluator

# Carregar dados
evaluator = PolicyEvaluator(
    data="dados.csv",
    treatment="municipio_tratado",
    outcome="indicador_social",
    time="ano"
)

# Estimar efeito causal
result = evaluator.estimate_effect(
    method="did",
    covariates=["pib_per_capita", "educacao"]
)

# Visualizar resultados
result.plot_effect()
print(result.summary)

📊 Exemplo Prático
Avaliação do impacto do programa Bolsa Família na mortalidade infantil:
import pandas as pd
from causal_impact import SyntheticControl

df = pd.read_csv("bolsa_familia.csv")
sc = SyntheticControl(
    data=df,
    treatment_unit="Municipio_A",
    outcome="mortalidade_infantil",
    time="ano"
)

sc.fit(predictors=["pib", "populacao", "esgoto_sanitario"])
sc.plot(plot_type="counterfactual")

🔄 Fluxo de Análise

graph TD
    A[Coleta de Dados] --> B[Pré-processamento]
    B --> C[Seleção de Método Causal]
    C --> D[Estimativa de Efeito]
    D --> E[Testes de Robustez]
    E --> F[Visualização]
    F --> G[Relatório Automático]

📂 Dataset de Exemplo
Incluímos dados simulados no diretório examples/ com:

100 municípios brasileiros

5 anos de dados pré-intervenção

3 anos pós-intervenção

Variáveis socioeconômicas chave

🗺️ Roadmap
Implementação dos métodos básicos (v1.0)

Adição de Bayesian Structural Time Series (em desenvolvimento)

Integração com dados do IPEA

Dashboard interativo

Módulo de sensibilidade a vieses

🤝 Contribuição
Siga nosso guia de contribuição. Principais áreas necessárias:

Novos métodos causais

Testes de robustez

Visualizações

Documentação

📚 Publicações Relacionadas
Abadie, A. (2021). Using Synthetic Controls - JEL

Cunningham, S. (2021). Causal Inference: The Mixtape

📜 Licença
MIT License - Veja LICENSE para detalhes.

📧 Contato
Equipe de Pesquisa em Políticas Públicas
research@policylab.org
@PolicyLabBR

