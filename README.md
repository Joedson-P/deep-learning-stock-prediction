# Previsão de Preços de Ações (MSFT) com Deep Learning

Este projeto utiliza redes neurais recorrentes do tipo **LSTM (Long Short-Term Memory)** para prever o preço de fechamento das ações da Microsoft (MSFT).

## Metodologia
Foram testadas diversas abordagens para identificar a mais eficaz na predição de séries temporais financeiras:
1. **Baseline Univariado:** Utilizando apenas o histórico de preços.
2. **Multivariado:** Inclusão de indicadores técnicos (Médias Móveis MA7, MA21 e Volume).
3. **Diferenciação (Modelo Vencedor):** Predição da variação diária ($\Delta P$) em vez do preço absoluto, visando contornar a não-estacionariedade dos dados.

## Resultados Finais
O modelo baseado em diferenças superou significativamente as abordagens tradicionais de preço cheio.

| Métrica | Resultado |
| :--- | :--- |
| **RMSE** | **4.78 USD** |
| **MAE** | **3.58 USD** |

## Tecnologias Utilizadas
* Python 3.12.10
* TensorFlow / Keras 3
* Pandas, NumPy e Scikit-learn
* Matplotlib (Visualização de dados)