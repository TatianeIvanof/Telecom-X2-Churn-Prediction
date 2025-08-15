# 📡 Telecom X – Parte 2: Prevendo Churn

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)
![Status](https://img.shields.io/badge/Status-Concluído-success)
![License](https://img.shields.io/badge/Licen%C3%A7a-MIT-green)
![Colab](https://img.shields.io/badge/Google%20Colab-Compatible-orange?logo=googlecolab)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Yes-blueviolet)

## 📖 Visão Geral
Este projeto é a **segunda parte** do desafio **Telecom X**, focado na previsão de evasão de clientes (**churn**) utilizando técnicas de **Machine Learning**.  
O objetivo é construir e avaliar modelos preditivos para identificar clientes com alta probabilidade de churn, analisando fatores-chave que influenciam a evasão e propondo **estratégias de retenção** baseadas nos resultados.

O projeto utiliza um pipeline completo de pré-processamento, modelagem e análise, implementado em **Python** no **Google Colab**, com dados tratados fornecidos no arquivo `dados_transformados.csv` (gerado na Parte 1 do desafio).

---

## 🎯 Objetivos
- **Pré-processamento:** Limpar e preparar os dados (remoção de IDs, one-hot encoding, imputação de valores faltantes e balanceamento com SMOTE).
- **Análise Exploratória:** Investigar proporção de churn, correlações e relações entre variáveis como tempo de contrato (`customer_tenure`) e total gasto (`account_Charges.Total`).
- **Modelagem:** Treinar dois modelos (Regressão Logística e Random Forest) e avaliar por acurácia, precisão, recall e F1-score.
- **Interpretação:** Identificar variáveis mais importantes para o churn e propor estratégias de retenção baseadas nos insights.

---

## 📂 Estrutura do Repositório

```
Telecom-X-Churn-Prediction/
├── dados_transformados.csv             # Dados tratados (entrada)
├── Telecom_X1.ipynb                    # Notebook principal com o pipeline
├── relatorio_churn_final.md            # Relatório final com resultados e sugestões
├── linhas_dropped_target_missing.csv   # (Opcional) Linhas removidas com target inválido
├── correlation_matrix.png              # Heatmap da matriz de correlação
├── tenure_vs_churn.png                  # Boxplot: tempo de contrato vs churn
├── total_charges_vs_churn.png           # Boxplot: total gasto vs churn
├── feature_importance_rf.png            # Importância das variáveis (Random Forest)
├── coef_logistic.png                    # Coeficientes (Regressão Logística)
├── cm_logistic.png                      # Matriz de confusão (Regressão Logística)
├── cm_rf.png                            # Matriz de confusão (Random Forest)
└── README.md                            # Este arquivo
```

---

## 🚀 Como Executar

### 📋 Pré-requisitos

- **Python 3.6+** (ou executar via Google Colab)
- Bibliotecas necessárias:
  
```pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn```

▶ Passos

1. Clone o repositório:

```git clone https://github.com/<seu-usuario>/Telecom-X-Churn-Prediction.git```

2. Acesse o diretório:

```cd Telecom-X-Churn-Prediction```

3. No Google Colab:

- Faça upload do Telecom_X2.ipynb e do dados_transformados.csv
- Execute as células do notebook em sequência

4. Resultados:

- Gráficos (PNG) e relatório final (relatorio_churn_final.md)
- Linhas com target inválido salvas em linhas_dropped_target_missing.csv (se houver)

---

## 📊 Resultados

### 📌 Proporção de Churn

- 26.53% dos clientes evadiram

### 🏆 Modelos

- Regressão Logística: Interpretável, mas menos robusta em dados desbalanceados
- Random Forest: Melhor desempenho (maior F1-score na classe churn)

### 🔍 Principais Fatores de Churn

1. Tempo de Contrato (customer_tenure) → Menor tenure = maior churn  
2. Total Gasto (account_Charges.Total) → Gastos altos = maior evasão  
3. Método de Pagamento (Electronic check) → Forte indicador de churn  
4. Tipo de Contrato (Two year, One year) → Contratos longos reduzem churn  
5. Internet (Fiber optic) → Alta taxa de churn, possivelmente por preço ou qualidade  

### 💡 Estratégias de Retenção

- Ofertas para novos clientes (aumentar tenure)
- Incentivar pagamentos automáticos
- Pacotes personalizados para fibra óptica
- Descontos para contratos longos
- Monitoramento proativo com o Random Forest

---

## 📈 Visualizações

- Matriz de Correlação → Variáveis mais correlacionadas com churn
- Boxplots → Clientes com menor tenure e maiores gastos evadem mais
- Matrizes de Confusão → Avaliam desempenho dos modelos
- Gráficos de Importância → Destacam variáveis-chave para churn

---

## 🛠️ Metodologia

🔹 Pré-processamento

- Remoção de IDs (customerID)
- One-hot encoding para variáveis categóricas
- Imputação de valores faltantes (mediana)
- Balanceamento com SMOTE (apenas no treino)
- Padronização para Regressão Logística

🔹 Análise Exploratória

- Proporção de churn
- Matriz de correlação
- Boxplots para customer_tenure e account_Charges.Total

🔹 Modelagem

- Regressão Logística (com StandardScaler)
- Random Forest (200 estimadores, sem scaling)

🔹 Avaliação

- Métricas: acurácia, precisão, recall, F1-score
- Matrizes de confusão

🔹 Interpretação

- Importância das variáveis:
- Random Forest: feature_importances_
- Regressão Logística: coeficientes
- Relatório final com insights e sugestões

---

## 📝 Relatório Final

O relatório completo está em relatorio_churn_final.md, contendo:

- Resumo dos resultados
- Fatores principais de churn
- Análise crítica (desempenho, overfitting, underfitting)
- Sugestões estratégicas de retenção

---

## 🤝 Contribuições

Contribuições são bem-vindas!

Para sugerir melhorias:

1. Faça um fork
2. Crie uma branch
```git checkout -b feature/nova-ideia```
3. Commit das mudanças
```git commit -m 'Adiciona nova ideia'```
4. Envie um pull request
   
---

##📧 Contato

Para dúvidas ou sugestões, entre em contato via GitHub Issues

