# Financial Time Series ML

Este proyecto esta inspirado en la metodología propuesta en: 
- Hota, H.S., Handa, R., & Shrivas, A.K. (2017).  
  *Time Series Data Prediction Using Sliding Window Based RBF Neural Network*.  
  International Journal of Computational Intelligence Research, 13(5), 1145–1156.

## Metodología

Se realizó un Análisis Exploratorio de Datos (EDA) con el objetivo de identificar patrones, tendencias y posibles anomalías en la serie de tiempo del precio de cierre.

El objetivo de este proyecto es demostrar la efectividad del uso de **ventanas móviles (sliding windows)** junto con **Weighted Moving Average (WMA)** como técnica de preprocesamiento para predecir el precio de cierre de los siguientes 5 días de la acción *KO*.

Dado el comportamiento no lineal de la serie de tiempo, se emplea **WMA** como técnica de suavizado, la cual asigna mayor peso a las observaciones más recientes, permitiendo capturar mejor la dinámica del mercado. Se generaron ventanas de WMA para periodos de 5, 10, 15 y 20 días.

Para el escalamiento de los datos se utilizó `RobustScaler`, una técnica robusta frente a outliers, ya que transforma los datos restando la mediana y escalando con el rango intercuartílico (IQR):

$$
X_{scaled} = \frac{X - \text{Mediana}}{IQR}
$$

Posteriormente, los datos preprocesados se utilizaron como entrada para una red neuronal **LSTM (Long Short-Term Memory)**. Este tipo de arquitectura es adecuada para series de tiempo, ya que modela dependencias temporales mediante secuencias de datos.

La estructura de entrada requerida por el modelo es:

$$
(n\_samples, \; timesteps, \; n\_features)
$$

y la relación aprendida puede representarse como:

$$
y_t = f(x_t, x_{t-1}, \ldots, x_{t-k})
$$

donde el modelo aprende a predecir valores futuros en función del comportamiento pasado de la serie.

### Resultados

El modelo alcanzó los siguientes resultados en la predicción de los siguientes 5 días:

- **MAE:** 3.81  
- **MAPE:** 5.06%


## Autor

Alejandro Zayas
