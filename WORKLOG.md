# Worklog — data-mining-churn-prediction

Registo de sessões de trabalho: o que foi feito, próximo passo e notas.
(Session log: what was done, next step, and notes.)

---

## 2026-07-08
- **FIZ:** Etapa 3 (Modeling) completa — one-hot encoding, split estratificado 80/20,
  4 modelos treinados (KNN, Decision Tree, SVM, Naive Bayes), escalonamento com
  StandardScaler (SVM: 0.000 → 0.803 de accuracy) e validação cruzada 5-fold
  (desvios < 0.03; Naive Bayes com melhor F1 médio 0.597, SVM o mais estável ±0.006).
- **DESCOBERTA DA SESSÃO:** o encoding revelou codificações mistas remanescentes das
  duas fontes do dataset (True/False, 0/1, "No internet service" vs "No service") —
  X inchou para 77 colunas. Corrigi na fase de preparação (notebook 02), re-executei
  o pipeline completo e o X caiu para 46 colunas limpas. Notebook 02 e CSV
  regenerados e re-publicados.
- **CONCLUSÃO DE NEGÓCIO (para o README):** não há um vencedor único — depende do
  custo dos erros. Se falsos alarmes são baratos (ex.: email de retenção), o Naive
  Bayes maximiza clientes salvos (recall 0.846). Se a ação é cara (ex.: desconto
  agressivo), o SVM dá o melhor equilíbrio (F1 0.595, accuracy 0.803).
- **PRÓXIMO PASSO:** Etapa 4/5 — matriz de confusão final, figuras para
  `reports/figures/`, preencher a tabela de Results do README com os números reais
  e retirar o selo WIP.
- **NOTA:** o kernel do Jupyter usa o Python do sistema (não o .venv); instalar
  bibliotecas com `%pip install` dentro do notebook resolve.

## 2026-07-07
- **FIZ:** Etapa 2 (Data Preparation) fechada a 100% — limpeza completa do dataset
  (coluna-índice removida, alvo Churn unificado em No/Yes, TotalCharges convertido
  para numérico, ausentes estruturais tratados como "No service"); dataset limpo
  guardado em `data/processed/telco_churn_clean.csv`.
- **PRÓXIMO PASSO:** criar `notebooks/03_modeling.ipynb` — encoding, train/test split
  e treino dos 4 modelos (KNN, Decision Tree, SVM, Naive Bayes).
- **NOTA:** fluxo de trabalho = Jupyter local + upload pela web do GitHub.
  Ignorar o aviso "diverged" do git local.

## 2026-07-04 a 2026-07-06
- **FIZ:** Etapa 0 (scaffolding: README, LICENSE, .gitignore, requirements, dataset
  + SOURCE.md) e Etapa 1 (Data Understanding: notebook 01 + figuras iniciais).
- Registo iniciado a 07/07; entradas anteriores reconstruídas a partir do histórico
  de commits.
