# Deep Learning para Previsão de Ativos (MSFT)

## Objetivo do Projeto
Este projeto utiliza Redes Neurais Recorrentes (RNN) do tipo **LSTM (Long Short-Term Memory)** para prever o preço de fechamento das ações da Microsoft (MSFT). O foco é capturar dependências temporais não-lineares que modelos estatísticos tradicionais muitas vezes não conseguem identificar.

## Arquitetura do Modelo
O modelo foi construído utilizando a biblioteca **TensorFlow/Keras** com a seguinte estrutura:
* **Camada de Entrada:** Configurada para janelas temporais (Lookback) de 60 dias.
* **Stacked LSTM:** Duas camadas LSTM com 50 unidades cada para capturar padrões complexos.
* **Regularização:** Camadas de **Dropout (20%)** para evitar o overfitting durante o treino.
* **Camada de Saída:** Camada Dense para regressão do preço final.

## Metodologia
1. **Pré-processamento:** Normalização dos dados utilizando `MinMaxScaler` (escala 0 a 1).
2. **Janelamento:** Transformação da série temporal em um problema de aprendizado supervisionado (X = últimos 60 dias, y = próximo dia).
3. **Treinamento:** Utilização do otimizador **Adam** e função de perda **MSE**. Implementação de **Early Stopping** para eficiência computacional.
4. **Avaliação:** Inversão da escala para dólares (USD) e cálculo do erro médio.

## Resultados Alcançados
* **RMSE (Root Mean Squared Error):** 7.38 USD
* O modelo demonstrou alta capacidade de seguir a tendência do ativo, mantendo a estabilidade mesmo em períodos de volatilidade.