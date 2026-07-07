# Worklog — data-mining-churn-prediction

Registo de sessões de trabalho: o que foi feito, próximo passo e notas.
(Session log: what was done, next step, and notes.)

---

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
