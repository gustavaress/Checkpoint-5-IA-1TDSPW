# 🧠 CP5 – Modelo de Classificação com IA  
### Detecção de Fraudes em Transações Financeiras  
**Autor:** Gustavo Tavares (RM 562827)
**Disciplina:** Inteligência Artificial  
**Data:** 26 de Outubro de 2025  

---

## 🎯 Objetivo do Projeto

Este projeto tem como objetivo aplicar técnicas de **classificação supervisionada** de Machine Learning para **detectar possíveis transações fraudulentas** em um conjunto de dados financeiros.  
O trabalho segue todas as etapas exigidas pela **CP5 – Modelo de Classificação com IA**, incluindo exploração, preparação, modelagem e análise crítica dos resultados.

---

## 🧩 Contexto

A detecção de fraudes é um dos campos mais relevantes da Inteligência Artificial aplicada ao setor financeiro.  
Sistemas capazes de identificar automaticamente padrões suspeitos ajudam a reduzir prejuízos, proteger usuários e aumentar a confiabilidade das instituições.

Neste projeto, foi criado um pipeline completo de IA para identificar, a partir de variáveis como **valor da transação**, **pontuação de crédito**, **renda**, **idade** e **tipo de dispositivo**, quais operações têm maior probabilidade de serem fraudulentas.

---

## 📊 Dataset

- **Nome:** `fraud_detection_dataset.csv`  
- **Registros:** +1.000 transações simuladas  
- **Variável-alvo:** `is_fraud`  
  - `1` → Transação fraudulenta  
  - `0` → Transação legítima  

### Principais variáveis explicativas
| Variável | Descrição |
|-----------|------------|
| `amount` | Valor da transação |
| `age` | Idade do cliente |
| `income` | Renda mensal |
| `credit_score` | Pontuação de crédito |
| `debt` | Dívida total |
| `device_type` | Tipo de dispositivo usado |
| `timestamp` | Data/hora da transação |
| `location` | Local de origem da transação |

O dataset foi limpo, enriquecido e balanceado artificialmente para viabilizar o treinamento supervisionado.

### 📚 Fonte dos Dados
Os dados utilizados foram obtidos a partir do repositório público do Kaggle:  
🔗 [FraudSynth – Credit Fraud Detection Dataset](https://www.kaggle.com/datasets/youssefismail20/fraudsynth-credit-fraud-detection-dataset?resource=download)

---

## ⚙️ Pipeline de Desenvolvimento

### 1. Definição do Problema  
Identificar se uma transação é **fraudulenta (1)** ou **legítima (0)** a partir de variáveis numéricas e categóricas.

### 2. Pré-processamento dos Dados  
- Remoção/tratamento de valores ausentes;  
- Conversão de data/hora (`timestamp`) para `hour`, `dayofweek`, `month`;  
- Criação de novas features derivadas:
  - `debt_to_income_ratio` → relação entre dívida e renda  
  - `amount_credit_interaction` → interação entre valor e crédito  
  - `income_per_age` → relação entre renda e idade  
- Escalonamento de dados numéricos e codificação One-Hot para categóricos.

### 3. Modelagem  
Foram testados **três modelos supervisionados**:
1. **Regressão Logística**  
2. **Random Forest Classifier**  
3. **SVM (Support Vector Machine)**  

### 4. Avaliação  
As métricas utilizadas foram:
- **Acurácia**
- **Precisão**
- **Recall**
- **F1-Score**
- **Matriz de Confusão**

O modelo **Random Forest** apresentou o melhor desempenho geral, equilibrando precisão e recall.

### 5. Interpretação e Conclusão  
O projeto demonstra que, com engenharia de atributos adequada e ajuste de dados, é possível construir modelos eficazes de detecção de fraude, mesmo com dados simulados.  
Contudo, para uso real, é essencial ampliar o dataset e aplicar técnicas de **balanceamento de classes** (ex: SMOTE).

---

## 📈 Principais Resultados

| Modelo | Acurácia | Precisão | Recall | F1-Score |
|---------|-----------|-----------|---------|-----------|
| Regressão Logística | 0.88 | 0.87 | 0.84 | 0.85 |
| Random Forest | **0.92** | **0.91** | **0.90** | **0.90** |
| SVM | 0.89 | 0.88 | 0.85 | 0.86 |

---

## 🧾 Conclusões e Aprendizados

- O **Random Forest** foi o modelo mais eficiente para este tipo de classificação.  
- A **engenharia de features** foi crucial para melhorar o desempenho.  
- **Classes desbalanceadas** prejudicam modelos lineares — o uso de técnicas de oversampling é recomendado.  
- O projeto reforça a importância da IA no combate a fraudes financeiras.

---

## 🚀 Tecnologias Utilizadas

- **Linguagem:** Python  
- **Bibliotecas:**  
  - `pandas`, `numpy` → manipulação de dados  
  - `matplotlib`, `seaborn` → visualização  
  - `scikit-learn` → modelagem e métricas  
- **Ambiente:** Google Collab

---