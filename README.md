Telecom X – Parte 2: Prevendo Churn

📖 Visão Geral

Este projeto é a segunda parte do desafio Telecom X, focado na previsão de evasão de clientes (churn) utilizando técnicas de Machine Learning. O objetivo é construir e avaliar modelos preditivos para identificar clientes com alta probabilidade de churn, analisando fatores-chave que influenciam a evasão e propondo estratégias de retenção baseadas nos resultados.
O projeto utiliza um pipeline completo de pré-processamento, modelagem e análise, implementado em Python no Google Colab, com dados tratados fornecidos no arquivo dados_transformados.csv (gerado na Parte 1 do desafio).

🎯 Objetivos

Pré-processamento: Limpar e preparar os dados, incluindo remoção de IDs, one-hot encoding, imputação de valores faltantes e balanceamento de classes com SMOTE.
Análise Exploratória: Investigar proporção de churn, correlações e relações entre variáveis como tempo de contrato (customer_tenure) e total gasto (account_Charges.Total) com a evasão.
Modelagem: Treinar dois modelos (Regressão Logística e Random Forest) para prever churn, com avaliação via métricas como acurácia, precisão, recall e F1-score.
Interpretação: Identificar as variáveis mais importantes para o churn e propor estratégias de retenção baseadas nos insights.

📂 Estrutura do Repositório

Telecom-X-Churn-Prediction/
├── dados_transformados.csv        # Dados tratados (entrada)
├── Telecom_X2.ipynb               # Notebook principal com o pipeline
├── relatorio_churn_final.md       # Relatório final com resultados e sugestões
├── linhas_dropped_target_missing.csv  # (Opcional) Linhas removidas com target inválido
├── correlation_matrix.png         # Heatmap da matriz de correlação
├── tenure_vs_churn.png            # Boxplot de tempo de contrato vs churn
├── total_charges_vs_churn.png     # Boxplot de total gasto vs churn
├── feature_importance_rf.png      # Importância das variáveis (Random Forest)
├── coef_logistic.png              # Coeficientes (Regressão Logística)
├── cm_logistic.png                # Matriz de confusão (Regressão Logística)
├── cm_rf.png                      # Matriz de confusão (Random Forest)
└── README.md                      # Este arquivo

🚀 Como Executar

Pré-requisitos

Python 3.6+ (recomendado via Google Colab para compatibilidade).
Dependências (instaladas automaticamente no notebook, se necessário):

pandas
numpy
matplotlib
seaborn
scikit-learn
imbalanced-learn

Para instalar localmente:

pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn

Passos

Clone o repositório:

git clone https://github.com/<seu-usuario>/Telecom-X-Churn-Prediction.git

Acesse o diretório:

cd Telecom-X-Churn-Prediction

Carregue no Google Colab:

Faça upload do arquivo Telecom_X2.ipynb e do dados_transformados.csv no Google Colab.
Execute as células do notebook em sequência.

Resultados:
O notebook gera gráficos (salvos como PNG) e o relatório final (relatorio_churn_final.md).
Linhas com target inválido, se houver, são salvas em linhas_dropped_target_missing.csv.

📊 Resultados

Proporção de Churn: Aproximadamente 26.53% dos clientes evadiram.

Modelos:

Regressão Logística: Interpretável, mas menos robusta em dados desbalanceados.
Random Forest: Melhor desempenho (maior F1-score na classe churn).

Principais Fatores de Churn:

Tempo de Contrato (customer_tenure): Clientes com menor tenure têm maior churn.
Total Gasto (account_Charges.Total): Gastos altos associados a maior evasão.
Método de Pagamento (Electronic check): Forte indicador de churn.
Contrato (Two year, One year): Contratos longos reduzem churn.
Internet (Fiber optic): Alta taxa de churn, possivelmente por preço ou qualidade.

Estratégias de Retenção:

Ofertas para novos clientes (aumentar tenure).
Incentivar métodos de pagamento automáticos.
Pacotes personalizados para usuários de fibra óptica.
Descontos para contratos longos.
Monitoramento proativo com o modelo Random Forest.

📈 Visualizações

Matriz de Correlação: Identifica variáveis mais correlacionadas com churn.
Boxplots: Mostram que clientes com menor tenure e maiores gastos evadem mais.
Matrizes de Confusão: Avaliam desempenho dos modelos.
Gráficos de Importância: Destacam variáveis-chave para churn.

🛠️ Metodologia

Pré-processamento:

Remoção de IDs (customerID).
One-hot encoding para variáveis categóricas.
Imputação de valores faltantes (mediana).
Balanceamento com SMOTE (apenas no treino).
Padronização para Regressão Logística.

Análise Exploratória:

Proporção de churn.
Matriz de correlação.
Boxplots para customer_tenure e account_Charges.Total.

Modelagem:

Regressão Logística (com StandardScaler).
Random Forest (200 estimadores, sem scaling).

Avaliação:

Métricas: acurácia, precisão, recall, F1-score.
Matrizes de confusão.

Interpretação:

Importância das variáveis (Random Forest: feature_importances_; Logistic: coeficientes).
Relatório final com insights e sugestões.

📝 Relatório Final

O relatório completo está em relatorio_churn_final.md, com:

Resumo dos resultados.
Fatores principais de churn.
Análise crítica (desempenho, overfitting, underfitting).
Sugestões estratégicas de retenção.

🤝 Contribuições

Contribuições são bem-vindas! Para sugerir melhorias:

Faça um fork do repositório.
Crie uma branch (git checkout -b feature/nova-ideia).
Faça commit das mudanças (git commit -m 'Adiciona nova ideia').
Envie um pull request.

📅 Data

Projeto finalizado em 14 de agosto de 2025.

📧 Contato

Para dúvidas ou sugestões, entre em contato via GitHub Issues.
