
# 🏛️ Public Policy Causal Impact

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Python Version](https://img.shields.io/badge/python-3.9+-blue.svg)
![Docs: Passing](https://img.shields.io/badge/docs-passing-brightgreen)

Framework para avaliação causal de políticas públicas com métodos quasi-experimentais.  
Este projeto fornece uma implementação inicial do método **Controle Sintético**, aplicada a um caso ilustrativo sobre o impacto do **Programa Bolsa Família** na mortalidade infantil na região Norte do Brasil.

---

## 📑 Tabela de Conteúdos

- [Visão Geral](#visão-geral)
- [Exemplo Prático](#exemplo-prático)
- [Instalação](#instalação)
- [Uso](#uso)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Requisitos](#requisitos)
- [Contribuição](#contribuição)
- [Licença](#licença)

---

## 🎯 Visão Geral

O objetivo do `public-policy-causal-impact` é disponibilizar ferramentas para análise de impacto de políticas públicas com base em métodos estatísticos replicáveis, acessíveis a pesquisadores e gestores públicos.

### ✔️ Funcionalidades:

- Estimativa do impacto causal de políticas públicas
- Geração de contrafatuais
- Visualização gráfica dos resultados
- Base de dados ilustrativa embutida

---

## 🧪 Exemplo Prático: Bolsa Família

### Cenário

Avaliar se a mortalidade infantil na região Norte foi impactada após a implementação do programa Bolsa Família (a partir de 2005), comparando com uma unidade sintética construída a partir da região Sudeste.

---

## ⚙️ Instalação

### Pré-requisitos

- Python 3.9+
- `pip` instalado

### Instalação

Clone o repositório e instale as dependências:

```bash
git clone https://github.com/seu-usuario/public-policy-causal-impact.git
cd public-policy-causal-impact
pip install -r requirements.txt


---

🚀 Uso

Execute o script de exemplo:

python scripts/exemplo_bolsa_familia.py

Saída esperada

Gráfico comparando o valor observado e o contrafactual

Impressão no terminal com a estimativa do impacto médio:


Efeito Causal Estimado: -2.30


---

📁 Estrutura do Projeto

public-policy-causal-impact/
│
├── causal_impact/
│   ├── synthetic_control.py        # Lógica do controle sintético
│   └── datasets/
│       ├── __init__.py
│       └── bolsa_familia.csv      # Dados simulados
│
├── scripts/
│   └── exemplo_bolsa_familia.py   # Roda o exemplo de uso
│
├── requirements.txt
├── setup.py
└── README.md


---

📦 Requisitos

Instalados via requirements.txt:

pandas

scikit-learn

matplotlib



---

🤝 Contribuição

Contribuições são bem-vindas! Para colaborar:

1. Fork este repositório


2. Crie uma branch (git checkout -b feature/nova-funcionalidade)


3. Commit suas alterações (git commit -m 'Adiciona nova funcionalidade')


4. Push para a branch (git push origin feature/nova-funcionalidade)


5. Abra um Pull Request




---

📄 Licença

Distribuído sob a Licença MIT. Veja o arquivo LICENSE para mais detalhes.


---

📬 Contato

Projeto de exemplo criado por Roberto Cunha com apoio do ChatGPT.
Inspirado em aplicações reais de avaliação de políticas públicas no Brasil.

