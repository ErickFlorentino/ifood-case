# Projeto IFOOD

## Descrição
Este projeto é composto por três modelos complementares, cada um voltado a um aspecto estratégico do processo de oferta ao cliente:

*** MRO (Modelo de Recomendação de Oferta): responsável por recomendar a oferta mais adequada para cada cliente, com base em seu perfil e histórico comportamental.

*** MPUO (Modelo de Propensão ao Uso da Oferta): prevê a probabilidade de o cliente utilizar uma determinada oferta, auxiliando na priorização e alocação de incentivos.

*** Modelo de Clusterização de Clientes - Identificação de Perfis com Base no Uso das Ofertas: não tem como foco a previsão direta de aceitação ou escolha de ofertas, mas sim a identificação de perfis comportamentais distintos entre os clientes. Essa visão qualitativa enriquece as análises, apoia o direcionamento de campanhas e orienta o desenvolvimento de novas ofertas mais alinhadas a cada perfil identificado.

Juntos, esses modelos proporcionam uma abordagem ampla e integrada, permitindo decisões mais assertivas e personalizadas na jornada de oferta ao cliente.

---

## Requisitos

- Python 3.8 ou superior  
- Bibliotecas necessárias:
	- Manipulação e Análise de Dados: pandas, numpy
	- Datas e Tempo: datetime, calendar
	- Visualização: matplotlib, seaborn
	- Estatística: scipy
	- Pré-processamento e Pipelines: sklearn.preprocessing (LabelEncoder, OneHotEncoder, OrdinalEncoder, StandardScaler), e sklearn.pipeline (Pipeline)
	- Modelagem Supervisionada: sklearn.linear_model (LogisticRegression), sklearn.tree (DecisionTreeClassifier), sklearn.ensemble (RandomForestClassifier), xgboost (XGBClassifier)
	- Avaliação de Modelos: sklearn.metrics (classification_report, precision_score, recall_score, f1_score)
	- Validação Cruzada e Otimização: sklearn.model_selection (train_test_split, GridSearchCV)
	- Agrupamento (Clustering): sklearn.cluster (KMeans)
	- Salvamento de Modelos: joblib, pickle
	- Outros:warnings, os

Instale as dependências com o comando:

```bash
pip install -r requirements.txt

Estrutura do Repositórios

ifood-case/
├── data/ # Datasets
│ ├── raw/ # Dados originais
│ └── processed/ # Dados processados
├── notebooks/ # Jupyter notebooks
│ ├── 1_data_processing.ipynb
│ ├── ifood/models/#modelos salvos
│ ├── ifood/models/results/#resultados dos modelos
│ └── 2_modeling.ipynb
├── presentation/ # Slides para stakeholders
├── src/ # Código fonte (opcional)
├── README.md

Arquivos Existentes: 

- ifood/models/results/
ifood_oferta_resumo_cluster.csv - Resumo do Cluster
probabilidades_por_MPUO.csv - Probabilidade do Modelo de Propensão de Uso de Oferta
probabilidades_por_MRO.csv - Probabilidade do Modelo de Recomendação a Oferta

- ifood/models/
ifood_oferta_kmeans.pkl - Modelo de Clusterização do Uso de Oferta
ifood_oferta_raio_max.csv - Raio do Cluster
ifood_oferta_scaler.pkl - Codificação da base para clusterização
MPUO.pkl -  Modelo de Propensão de Uso de Oferta
MRO.pkl - Modelo de Recomendação a Oferta

-ifood/notebooks/
1_data_processing - Pré-processamento da base
2_modeling - Modelagem
ifood_oferta_centroides - Centroides da Clusterizacao

-ifood/data/raw
offers.json - Base bruta de oferta
profile.json - Base bruta do perfil
transactions.json - Base bruta de transação

-ifood/data/processed
data_processed- Dado processado
ofertas_recebidas - Ofertas recebidas Tratadas (base usada na eng. de features)
transactions_v2 - Transações recebidas Tratadas (base usada na eng. de features)