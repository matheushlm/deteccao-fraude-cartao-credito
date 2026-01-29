# deteccao-fraude-cartao-credito
Projeto de Machine Learning para detetar fraudes usando Python

# 💳 Detecção de Fraudes em Cartões de Crédito



## 📌 Visão Geral do Projeto
Este projeto aplica técnicas avançadas de **Machine Learning** para detectar transações fraudulentas em cartões de crédito. O objetivo principal foi resolver o problema do **desbalanceamento de classes** (onde apenas 0,17% das transações são fraudes) e minimizar falsos positivos para evitar o bloqueio indevido de clientes legítimos.

## 💼 Problema de Negócio
Fraudes financeiras causam prejuízos bilionários anualmente. No entanto, um sistema de detecção ineficiente pode gerar dois problemas graves:
1.  **Falsos Negativos (Perda Financeira):** O banco paga a conta da fraude.
2.  **Falsos Positivos (Perda de Cliente):** O cartão de um cliente honesto é bloqueado, gerando insatisfação e possível cancelamento (Churn).

O desafio foi criar um modelo que maximizasse a detecção de fraudes (Recall) mantendo uma alta precisão (Precision).

## 🛠️ Tecnologias Utilizadas
* **Python** (Linguagem principal)
* **Pandas & NumPy** (Manipulação de dados)
* **Scikit-Learn** (Modelagem e Métricas)
* **Imbalanced-Learn** (Técnica SMOTE para balanceamento)
* **Matplotlib & Seaborn** (Visualização de dados)

## 📊 Metodologia
1.  **Análise Exploratória (EDA):** Identificação de padrões e do desbalanceamento crítico (99.8% normal vs 0.17% fraude).
2.  **Pré-processamento:**
    * Aplicação de `Log Transformation` na variável `Amount` para normalizar a distribuição.
    * Divisão de Treino/Teste estratificada (`Stratified ShuffleSplit`) para manter a proporção de fraudes.
3.  **Balanceamento:** Uso do algoritmo **SMOTE (Synthetic Minority Over-sampling Technique)** apenas nos dados de treino para evitar *Data Leakage*.
4.  **Modelagem:** Comparação entre **Regressão Logística** (Baseline) e **Random Forest** (Modelo Final).

## 📈 Resultados Obtidos

O modelo final (**Random Forest**) apresentou um desempenho superior, equilibrando efetivamente a segurança e a experiência do cliente:

| Métrica (Classe Fraude) | Regressão Logística | Random Forest (Final) |
| :--- | :---: | :---: |
| **Recall (Detecção)** | 92% | **92%** |
| **Precision (Assertividade)** | 6% | **89%** |

> **Impacto:** Com o Random Forest, reduzimos drasticamente os alarmes falsos. De cada 100 alertas de fraude, **89 são reais**, garantindo eficiência operacional para a equipe de análise de risco.

### Principais Variáveis (Insights)
O modelo identificou que as variáveis comportamentais **V10, V14 e V12** são os maiores indicadores de fraude, superando o próprio valor da transação (`Amount`).

## 🚀 Como Executar o Projeto
1. Clone este repositório:
```bash
git clone [https://github.com/SEU-USUARIO/deteccao-fraude-cartao-credito.git](https://github.com/SEU-USUARIO/deteccao-fraude-cartao-credito.git)
