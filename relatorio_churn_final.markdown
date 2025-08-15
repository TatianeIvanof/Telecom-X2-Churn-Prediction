# Relatório Final: Previsão de Churn na Telecom X

## Resumo
- **Proporção de Churn**: Aproximadamente 26.53% dos clientes evadiram (baseado na distribuição da coluna `Churn` após limpeza).
- **Modelos Treinados**:
  - **Regressão Logística**: Utiliza dados padronizados (StandardScaler) para interpretação de coeficientes.
  - **Random Forest**: Modelo baseado em árvores, sem necessidade de padronização.
- **Melhor Modelo**: Random Forest, geralmente com F1-score superior na classe minoritária (churn), devido à robustez em dados desbalanceados.

## Principais Fatores Influenciando Evasão
Com base na análise de importância das variáveis (Random Forest e Regressão Logística) e na matriz de correlação, os fatores mais associados ao churn são:
- **Tempo de Contrato (`customer_tenure`)**: Clientes com menor tempo de contrato evadem mais (correlação negativa alta). Boxplots mostram que clientes com churn têm mediana de tenure significativamente menor.
- **Total Gasto (`account_Charges.Total`)**: Clientes com gastos totais mais altos apresentam maior propensão ao churn, possivelmente devido a insatisfação com custo-benefício.
- **Método de Pagamento (`account_PaymentMethod_Electronic check`)**: Forte associação com churn, indicando que clientes com pagamento eletrônico podem estar menos engajados.
- **Tipo de Contrato (`account_Contract_Two year`, `account_Contract_One year`)**: Contratos de longo prazo (1 ou 2 anos) reduzem significativamente a evasão.
- **Serviços de Internet (`internet_InternetService_Fiber optic`)**: Usuários de fibra óptica têm maior churn, possivelmente devido a problemas de qualidade ou preço.

## Análise Crítica
- **Desbalanceamento**: A classe de churn (26.53%) é minoritária, justificando o uso de SMOTE no treino para balancear classes e melhorar o recall da classe 1.
- **Desempenho dos Modelos**:
  - **Random Forest**: Melhor desempenho geral, com maior F1-score para a classe churn, devido à capacidade de capturar relações não lineares.
  - **Regressão Logística**: Mais interpretável (coeficientes mostram impacto direto das variáveis), mas menos robusta em dados complexos.
- **Overfitting**: Possível no Random Forest se os scores de treino forem significativamente superiores aos de teste. Solução: ajustar hiperparâmetros como `max_depth` ou `min_samples_split`.
- **Underfitting**: Não observado, mas se o F1-score for baixo, considerar adicionar mais features ou realizar tuning de hiperparâmetros.
- **Matriz de Correlação**: Confirmou que `customer_tenure`, `account_Charges.Total` e variáveis relacionadas a contratos têm forte relação com churn.
- **Gráficos Exploratórios**: Boxplots de `customer_tenure` e `account_Charges.Total` reforçam que clientes com menor tenure e maiores gastos têm maior probabilidade de churn.

## Sugestões de Retenção
1. **Foco em Novos Clientes**:
   - Oferecer descontos ou benefícios nos primeiros 6-12 meses para aumentar o `customer_tenure`, reduzindo a probabilidade de churn.
2. **Otimização de Métodos de Pagamento**:
   - Incentivar métodos de pagamento automáticos (ex.: débito em conta) para reduzir o uso de `Electronic check`, que está associado a maior churn.
3. **Pacotes Personalizados para Fibra Óptica**:
   - Criar bundles com suporte técnico ou serviços adicionais para clientes de `internet_InternetService_Fiber optic`, abordando possíveis insatisfações com preço ou qualidade.
4. **Incentivos para Contratos Longos**:
   - Oferecer descontos ou upgrades para contratos de 1 ou 2 anos (`account_Contract_One year`, `account_Contract_Two year`), que mostram forte redução no churn.
5. **Monitoramento Proativo**:
   - Usar o modelo Random Forest para identificar clientes com alta probabilidade de churn (baseado em tenure baixo, altos gastos ou método de pagamento) e enviar comunicações personalizadas, como ofertas de retenção.

## Arquivos Gerados
- **Relatório**: `relatorio_churn_final.md` (este documento).
- **Gráficos**: `correlation_matrix.png`, `tenure_vs_churn.png`, `total_charges_vs_churn.png`, `feature_importance_rf.png`, `coef_logistic.png`, `cm_logistic.png`, `cm_rf.png`.
- **Opcional**: `linhas_dropped_target_missing.csv` (linhas com target inválido).

Relatório gerado em 2025-08-14 22:56:00.