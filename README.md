# Financial Time Series ML

Este proyecto implementa un pipeline completo de machine learning para series de tiempo financieras, incluyendo:

- Feature engineering técnico
- Construcción de ventanas móviles (sliding windows)

## Estructura

- `notebooks/`: análisis paso a paso
- `data/`: datasets intermedios (no incluidos)

## Metodología

Se utilizan ventanas móviles para transformar la serie de tiempo en un problema supervisado.  
Todas las variables basadas en ventanas son desplazadas (`shift(1)`) para evitar leakage temporal.


## Autor

Alejandro Zayas
