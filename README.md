Public Policy Causal Impact
https://img.shields.io/badge/License-MIT-yellow.svg
https://img.shields.io/badge/python-3.9+-blue.svg
https://github.com/seu-usuario/public-policy-causal-impact/actions/workflows/tests.yml/badge.svg
https://img.shields.io/badge/docs-passing-brightgreen

Tabela de Conteúdos
Visão Geral

Métodos Implementados

Instalação

Uso Básico

Exemplo Prático

Roadmap

Contribuição

Licença

Visão Geral
O Public Policy Causal Impact é um framework avançado para avaliação de políticas públicas utilizando métodos quasi-experimentais. Desenvolvido para pesquisadores e gestores públicos, permite:

✔️ Medição precisa do impacto real de intervenções governamentais
✔️ Distinção entre correlação e causalidade
✔️ Geração de contrafatuais confiáveis
✔️ Análise de efeitos heterogêneos

Principais características:

Implementação dos principais métodos de inferência causal

Integração com bases governamentais (IBGE, IPEA, DATASUS)

Visualizações interativas e relatórios automatizados

Métodos Implementados
1. Differences-in-Differences (DiD)
python
from causal_impact import DifferencesInDifferences

did = DifferencesInDifferences(
    data=df,
    treatment='grupo_tratado',
    outcome='resultado',
    time='ano'
)
did.estimate().summary()
2. Synthetic Control
python
from causal_impact import SyntheticControl

sc = SyntheticControl(
    treatment_unit="São Paulo",
    outcome="taxa_emprego",
    predictors=["pib", "educação"]
)
sc.fit().plot()
3. Regression Discontinuity (RDD)
python
from causal_impact import RegressionDiscontinuity

rdd = RegressionDiscontinuity(
    data=df,
    cutoff=0.5,
    running_variable="score",
    outcome="beneficio"
)
Instalação
Pré-requisitos
Python 3.9+

pip 20.0+

Git (para instalação de desenvolvimento)

Via pip
bash
pip install policy-causal-impact
Desenvolvimento
bash
git clone https://github.com/seu-usuario/public-policy-causal-impact.git
cd public-policy-causal-impact
pip install -e ".[dev]"
Dependências principais
pandas >= 1.3

numpy >= 1.21

statsmodels >= 0.13

scikit-learn >= 1.0

Uso Básico
1. Carregamento de dados
python
import pandas as pd
from causal_impact import PolicyEvaluator

df = pd.read_csv("dados_politicas.csv")
2. Configuração da análise
python
evaluator = PolicyEvaluator(
    data=df,
    treatment="município_tratado",
    outcome="indicador_social",
    time="ano",
    covariates=["pib_per_capita", "educação"]
)
3. Estimação do efeito
python
result = evaluator.estimate_effect(
    method="did",
    robustness_checks=True
)
4. Visualização
python
result.plot_effect()
result.export_report("relatório.pdf")
Exemplo Prático
Avaliação do Programa Bolsa Família
python
from causal_impact.datasets import load_bolsa_familia
from causal_impact import SyntheticControl

# Carregar dados de exemplo
df = load_bolsa_familia()

# Configurar análise
sc = SyntheticControl(
    treatment_unit="Norte",
    outcome="mortalidade_infantil",
    time="ano",
    predictors=["pib", "esgoto_sanitario"]
)

# Resultados
results = sc.fit()
results.plot_counterfactual()
print(results.estimate)
Saída esperada:

text
Efeito Causal Estimado: -2.3 (IC95%: -3.1, -1.5)
Redução de 2.3 pontos na mortalidade infantil
Roadmap
Versão 1.0 (Atual)
Métodos básicos (DiD, Synthetic Control)

Integração com dados do IBGE

Relatórios automatizados

Versão 2.0 (Em desenvolvimento)
Bayesian Structural Time Series

Dashboard interativo

Módulo de sensibilidade

Versão 3.0 (Planejado)
Modelos espaciais

Previsão de impacto

API REST

Contribuição
Contribuições são bem-vindas! Siga os passos:

Abra uma issue descrevendo sua proposta

Faça fork do repositório

Crie um branch para sua feature (git checkout -b feature/nova-feature)

Commit suas mudanças (git commit -m 'Adiciona nova feature')

Push para o branch (git push origin feature/nova-feature)

Abra um Pull Request

Padrões requeridos:

Testes unitários para novas funcionalidades

Documentação atualizada

Código seguindo PEP 8

Licença
Distribuído sob a licença MIT. Veja LICENSE para mais informações.

text
MIT License

Copyright (c) [ano] [nome]

Permission is hereby granted...
Contato
Equipe de Pesquisa em Políticas Públicas
pesquisa@policialab.org
@PolicyLabBR

Para suporte técnico:
suporte@policialab.org
