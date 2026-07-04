# 📊 Customer Churn Prediction

> End-to-end customer churn prediction for a telecom operator using CRISP-DM, exploratory data analysis, preprocessing and supervised machine learning models.

![License](https://img.shields.io/badge/license-MIT-blue)
![Python](https://img.shields.io/badge/python-3.11-blue)

## 📑 Sumário

- [Visão Geral](#visão-geral)
- [Problema de Negócio](#problema-de-negócio)
- [Dataset](#dataset)
- [Metodologia CRISP-DM](#metodologia-crisp-dm)
- [Estrutura do Repositório](#estrutura-do-repositório)
- [Tecnologias](#tecnologias)
- [Instalação e Execução](#instalação-e-execução)
- [Resultados e Avaliação dos Modelos](#resultados-e-avaliação-dos-modelos)
- [Principais Insights](#principais-insights)
- [Limitações e Próximos Passos](#limitações-e-próximos-passos)
- [Autor](#autor)
- [Licença](#licença)

## Overview

This project aims to predict customer loss, also known as **customer churn**, in a telecommunications company. The project follows the **CRISP-DM** methodology, going through the stages of problem understanding, exploratory data analysis, data preparation, modeling, and evaluation of the results.

The work started as part of the studies in the **Data Mining** course unit, in the Post-Graduation in Big Data and Decision Making at ISEP, and is being developed as a technical portfolio project, with a focus on reproducibility, documentation, and comparison of classification models.


> 🚧 **Status:** work in progress — EDA, preprocessing and modeling notebooks are being added incrementally.

## Business Problem

Customer retention is an important challenge for telecommunications companies, because keeping an existing customer is usually cheaper than acquiring a new customer.

The goal of this project is to identify, based on contract data and service usage data, which customers have a higher probability of canceling the service. This prediction can support preventive retention actions, such as targeted campaigns, plan reviews, personalized offers, or proactive contact with customers at risk.

In this type of problem, the **recall** metric is especially important, because failing to identify a customer who is about to leave can represent a direct loss of revenue.

## Dataset

The project uses the public **Telco Customer Churn** dataset, frequently used in classification and churn prediction studies.

The detailed description of the data source and columns will be documented in:

```text
data/raw/SOURCE.md
```

Principais grupos de variáveis presentes no dataset:

| Grupo | Exemplos de Variáveis | Descrição |
|---|---|---|
| Dados demográficos | gender, SeniorCitizen, Partner, Dependents | Informações gerais sobre o cliente |
| Serviços contratados | PhoneService, InternetService, OnlineSecurity, TechSupport | Serviços utilizados pelo cliente |
| Informações contratuais | Contract, PaperlessBilling, PaymentMethod | Tipo de contrato e forma de pagamento |
| Valores financeiros | MonthlyCharges, TotalCharges | Custos mensais e totais |
| Variável-alvo | Churn | Indica se o cliente cancelou ou não o serviço |

Possible limitations of the dataset:

- The data represents a specific telecommunications scenario.
- The dataset is public and may not reflect all variables used by real companies.
- Some variables may contain biases related to the customer profile or the data collection period.
- The project has an educational and portfolio purpose, and is not a production-ready model.

## CRISP-DM Methodology

This project follows the **CRISP-DM** methodology, a structured approach for data mining projects.

1. **Business Understanding**  
   Definition of the business problem, the model objective, and the relevance of churn prediction for retention actions.

2. **Data Understanding**  
   Initial analysis of the dataset, verification of data types, missing values, target variable distribution, descriptive statistics, and exploratory data analysis.

3. **Data Preparation**  
   Data cleaning, treatment of missing values, encoding of categorical variables, normalization or standardization when necessary, and train-test split.

4. **Modeling**  
   Training and comparison of different classification algorithms, including:

   - K-Nearest Neighbors
   - Decision Tree
   - Support Vector Machine
   - Gaussian Naive Bayes

5. **Evaluation**  
   Evaluation of the models using appropriate classification metrics, including accuracy, precision, recall, F1-score, confusion matrix, and ROC/PR curves.

6. **Deployment**  
   In this initial phase, the project does not include production deployment. As next steps, the model may be organized into a reusable pipeline and later exposed through an API or analytical dashboard.

## Repository Structure

```text
data-mining-churn-prediction/

├── data/
│   ├── raw/              # dados brutos e documentação da fonte
│   └── processed/        # dados tratados e preparados
│
├── notebooks/            # EDA, preparação, modelagem e avaliação
│
├── src/                  # código-fonte reutilizável
│   ├── preprocessing.py
│   ├── train_models.py
│   └── evaluate_models.py
│
├── models/               # modelos treinados ou serializados
│
├── reports/
│   └── figures/          # gráficos e visualizações exportadas
│
├── requirements.txt
├── .gitignore
├── LICENSE
└── README.md
```

## Technologies

| Layer | Technology |
|---|---|
| Language | Python 3.11 |
| Data manipulation | Pandas, NumPy |
| Modeling | scikit-learn |
| Visualization | Matplotlib, Seaborn |
| Environment | Jupyter Notebook |
| Version control | Git, GitHub |
| Methodology | CRISP-DM |

## Installation and Execution

```bash
git clone https://github.com/aavelarbelo/data-mining-churn-prediction.git
cd data-mining-churn-prediction

python -m venv .venv
.venv\Scripts\activate

pip install -r requirements.txt
jupyter notebook
```

On Linux or macOS, the virtual environment can be activated with:

```bash
source .venv/bin/activate
```

## Results and Model Evaluation

The results will be added after the modeling and evaluation stage is completed.

| Model | Accuracy | Precision | Recall | F1 | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| KNN | – | – | – | – | – |
| Decision Tree | – | – | – | – | – |
| SVM | – | – | – | – | – |
| Naive Bayes | – | – | – | – | – |

Em problemas de churn, **recall** tende a ser uma métrica especialmente relevante, pois o objetivo é reduzir a quantidade de clientes em risco que o modelo deixa de identificar.

A escolha do melhor modelo não será feita apenas pela accuracy, mas pelo equilíbrio entre precision, recall, F1-score e capacidade de apoiar uma decisão de negócio.

## Principais Insights

Os principais insights serão adicionados após a análise exploratória e a comparação dos modelos.

Exemplos de análises previstas:

- Perfil dos clientes com maior taxa de churn.
- Relação entre tipo de contrato e probabilidade de cancelamento.
- Impacto de serviços adicionais na retenção dos clientes.
- Diferenças entre clientes com contrato mensal e contratos de longo prazo.
- Importância das variáveis financeiras, como mensalidade e valor total pago.

## Limitações e Próximos Passos

Limitações atuais:

- O projeto utiliza um dataset público e limitado.
- Ainda não inclui tuning avançado de hiperparâmetros.
- Ainda não inclui deployment do modelo.
- A análise será conduzida com foco educacional e de portfólio.

Próximos passos:

- Concluir a análise exploratória dos dados.
- Implementar o pipeline de pré-processamento.
- Treinar e comparar os modelos definidos.
- Avaliar os modelos com métricas apropriadas para churn.
- Exportar gráficos e matrizes de confusão para `reports/figures/`.
- Documentar os principais insights de negócio.
- Evoluir o projeto para uma estrutura mais próxima de produção, com scripts reutilizáveis em `src/`.

## Autor

**Andressa Avelar Belo**  
Control & Automation Engineer transitioning into Data Engineering, Big Data and Analytics.

[LinkedIn](https://linkedin.com/in/andressaavelar) · [GitHub](https://github.com/aavelarbelo) · eng.belo@gmail.com

## Licença

Este projeto está sob a licença MIT — veja o arquivo [LICENSE](LICENSE) para detalhes.
