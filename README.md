# Detecção de Fraudes em Cartão de Crédito

Projeto de ciência de dados focado em classificar transações fraudulentas usando o dataset clássico de cartão de crédito (European cardholders, 2 dias de transações, 492 fraudes em ~290 mil operações). O repositório contém um notebook único com análise exploratória, preparação dos dados e comparação de modelos de classificação.

## Notebook

Arquivo: `fraude_cartao.ipynb`

O notebook está dividido em duas partes principais, com alguma duplicação de etapas.

- Parte inicial: EDA básica, padronização de `Time` e `Amount`, treino/teste e modelos de baseline (Random Forest e Decision Tree) com métricas simples.
- Seção “Gabarito”: pipeline mais completo com EDA detalhada, padronização, split estratificado, balanceamento com SMOTE, comparação de múltiplos modelos (Logistic Regression, Random Forest, Gradient Boosting, XGBoost e LightGBM), além de curvas ROC e Precision-Recall.

## Principais passos do fluxo

- Importação do dataset e checagens iniciais.
- Análise exploratória: distribuição de classes, histogramas de `Time` e `Amount`, boxplot e KDE das variáveis `V1`–`V28`.
- Padronização de `Time` e `Amount` com `StandardScaler`.
- Split treino/teste com `stratify`.
- Balanceamento com `SMOTE`.
- Treinamento e avaliação de modelos com `classification_report`, `confusion_matrix`, ROC AUC e PR AUC.

## Requisitos

- Python 3
- Jupyter Notebook
- Bibliotecas: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `imbalanced-learn`, `scikit-plot`, `xgboost`, `lightgbm`, `pydotplus`.

## Como executar

1. Crie um ambiente virtual e instale as dependências.
2. Abra o notebook `fraude_cartao.ipynb` no Jupyter.
3. Atualize o caminho do dataset (ver seção abaixo) e execute as células.

## Dataset e caminhos

O notebook referencia dois caminhos de dados diferentes:

- Um link público no Dropbox: `https://www.dropbox.com/s/b44o3t3ehmnx2b7/creditcard.csv?dl=1`.
- Um caminho local absoluto: `/Users/marcoasilva/Documents/DSNP/fraude_cartao/dados_fraude_cartao.csv`.

Para reprodutibilidade, recomenda-se baixar o dataset do Kaggle (creditcardfraud) e salvar em um caminho relativo, por exemplo `data/creditcard.csv`, ajustando `file_path` no notebook.

## Observações importantes

- O notebook contém métricas e tabelas em Markdown que não são geradas automaticamente a partir da execução. Se você recalcular os modelos, esses valores podem mudar.
