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

## Visão Geral

Este projeto tem como objetivo prever a evasão de clientes, também conhecida como **customer churn**, em uma empresa de telecomunicações. O projeto segue a metodologia **CRISP-DM**, passando pelas etapas de entendimento do problema, análise exploratória dos dados, preparação dos dados, modelagem e avaliação dos resultados.

O trabalho começou como parte dos estudos da unidade curricular de **Data Mining**, na Pós-Graduação em Big Data and Decision Making no ISEP, e está sendo desenvolvido como um projeto de portfólio técnico, com foco em reprodutibilidade, documentação e comparação de modelos de classificação.

> 🚧 **Status:** work in progress — EDA, preprocessing and modeling notebooks are being added incrementally.

## Problema de Negócio

A retenção de clientes é um desafio importante para empresas de telecomunicações, pois manter um cliente existente tende a ser mais barato do que adquirir um novo cliente.

O objetivo deste projeto é identificar, a partir de dados contratuais e de utilização dos serviços, quais clientes apresentam maior probabilidade de cancelar o serviço. Essa previsão pode apoiar ações preventivas de retenção, como campanhas direcionadas, revisão de planos, ofertas personalizadas ou contacto proativo com clientes em risco.

Neste tipo de problema, a métrica de **recall** é especialmente importante, pois deixar de identificar um cliente que está prestes a sair pode representar perda direta de receita.

## Dataset

O projeto utiliza o dataset público **Telco Customer Churn**, frequentemente usado em estudos de classificação e previsão de churn.

A descrição detalhada da origem dos dados e das colunas será documentada em:

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

Possíveis limitações do dataset:

- Dados representam um cenário específico de telecomunicações.
- O dataset é público e pode não refletir todas as variáveis usadas por empresas reais.
- Algumas variáveis podem conter vieses relacionados ao perfil dos clientes ou ao período de coleta.
- O projeto tem finalidade educacional e de portfólio, não sendo um modelo pronto para produção.

## Metodologia CRISP-DM

Este projeto segue a metodologia **CRISP-DM**, uma abordagem estruturada para projetos de mineração de dados.

1. **Business Understanding**  
   Definição do problema de negócio, objetivo do modelo e relevância da previsão de churn para ações de retenção.

2. **Data Understanding**  
   Análise inicial do dataset, verificação de tipos de dados, valores ausentes, distribuição da variável-alvo, estatísticas descritivas e análise exploratória.

3. **Data Preparation**  
   Limpeza dos dados, tratamento de valores ausentes, encoding de variáveis categóricas, normalização ou padronização quando necessário e separação entre treino e teste.

4. **Modeling**  
   Treinamento e comparação de diferentes algoritmos de classificação, incluindo:

   - K-Nearest Neighbors
   - Decision Tree
   - Support Vector Machine
   - Gaussian Naive Bayes

5. **Evaluation**  
   Avaliação dos modelos com métricas adequadas para classificação, incluindo accuracy, precision, recall, F1-score, matriz de confusão e curvas ROC/PR.

6. **Deployment**  
   Nesta fase inicial, o projeto não inclui deployment em produção. Como próximos passos, o modelo poderá ser organizado em uma pipeline reutilizável e futuramente exposto por meio de uma API ou dashboard analítico.

## Estrutura do Repositório

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

## Tecnologias

| Camada | Tecnologia |
|---|---|
| Linguagem | Python 3.11 |
| Manipulação de dados | Pandas, NumPy |
| Modelagem | scikit-learn |
| Visualização | Matplotlib, Seaborn |
| Ambiente | Jupyter Notebook |
| Versionamento | Git, GitHub |
| Metodologia | CRISP-DM |

## Instalação e Execução

```bash
git clone https://github.com/aavelarbelo/data-mining-churn-prediction.git
cd data-mining-churn-prediction

python -m venv .venv
.venv\Scripts\activate

pip install -r requirements.txt
jupyter notebook
```

No Linux ou macOS, a ativação do ambiente virtual pode ser feita com:

```bash
source .venv/bin/activate
```

## Resultados e Avaliação dos Modelos

Os resultados serão adicionados após a conclusão da etapa de modelagem e avaliação.

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
