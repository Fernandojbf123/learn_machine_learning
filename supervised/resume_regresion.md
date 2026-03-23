# Modelos y métricas
Existen muchos modelos de regresión (ver tabla 1.)

Cuando se entrena un modelo, siempre se sigue la misma lógica:
1. Elegir el modelo
2. Entrenar el modelo (fit)
3. Predecir la salida
4. Calcular la métrica

Ahora vamos a explorar dos casos: 
1. Cuando los datos tienen una única partición. Se puede ver en el notebook "single_split_lin_reg.ipynb".
2. Cuando los datos son particionados multiples veces Kfold. Se puede ver en el notebook "kfold_split_lin_reg.ipynb".






### Tabla 1: Modelos de regresión y sus métricas.
| Modelo                    | Tipo de regresión        | Métrica | Función (sklearn.metrics)                        | Qué mide                 | Interpretación                          |
| ------------------------- | ------------------------ | ------- | ------------------------------------------------ | ------------------------ | --------------------------------------- |
| LinearRegression          | Lineal (OLS)             | R²      | `r2_score(y_true, y_pred)`                       | Varianza explicada       | → 1: perfecto; 0: no explica            |
|                           |                          | MSE     | `mean_squared_error(y_true, y_pred)`             | Error cuadrático medio   | → 0: perfecto; penaliza errores grandes |
|                           |                          | RMSE    | `mean_squared_error(..., squared=False)`         | Error en escala original | Magnitud promedio del error             |
|                           |                          | MAE     | `mean_absolute_error(y_true, y_pred)`            | Error absoluto medio     | Robusto a outliers                      |
|                           |                          | MedAE   | `median_absolute_error(y_true, y_pred)`          | Mediana del error        | Muy robusto                             |
|                           |                          | MAPE    | `mean_absolute_percentage_error(y_true, y_pred)` | Error porcentual         | Sensible a valores cercanos a 0         |
| Ridge                     | Lineal regularizado (L2) | R²      | `r2_score(y_true, y_pred)`                       | Varianza explicada       | Igual que LinearRegression              |
|                           |                          | MSE     | `mean_squared_error(y_true, y_pred)`             | Error cuadrático         | Penaliza errores grandes                |
|                           |                          | RMSE    | `mean_squared_error(..., squared=False)`         | Error en escala original | Interpretación directa                  |
|                           |                          | MAE     | `mean_absolute_error(y_true, y_pred)`            | Error absoluto           | Más robusto                             |
|                           |                          | MedAE   | `median_absolute_error(y_true, y_pred)`          | Error mediano            | Alta robustez                           |
|                           |                          | MAPE    | `mean_absolute_percentage_error(y_true, y_pred)` | Error relativo           | En porcentaje                           |
| Lasso                     | Lineal regularizado (L1) | R²      | `r2_score(y_true, y_pred)`                       | Varianza explicada       | Puede hacer selección de variables      |
|                           |                          | MSE     | `mean_squared_error(y_true, y_pred)`             | Error cuadrático         | Puede introducir sesgo                  |
|                           |                          | RMSE    | `mean_squared_error(..., squared=False)`         | Error en escala original | Interpretación directa                  |
|                           |                          | MAE     | `mean_absolute_error(y_true, y_pred)`            | Error absoluto           | Robusto                                 |
|                           |                          | MedAE   | `median_absolute_error(y_true, y_pred)`          | Error mediano            | Muy robusto                             |
|                           |                          | MAPE    | `mean_absolute_percentage_error(y_true, y_pred)` | Error relativo           | Sensible a ceros                        |
| DecisionTreeRegressor     | No lineal (árbol)        | R²      | `r2_score(y_true, y_pred)`                       | Varianza explicada       | Puede sobreajustar                      |
|                           |                          | MSE     | `mean_squared_error(y_true, y_pred)`             | Error cuadrático         | Métrica interna típica                  |
|                           |                          | RMSE    | `mean_squared_error(..., squared=False)`         | Error en escala original | Magnitud del error                      |
|                           |                          | MAE     | `mean_absolute_error(y_true, y_pred)`            | Error absoluto           | Alternativa robusta                     |
|                           |                          | MedAE   | `median_absolute_error(y_true, y_pred)`          | Error mediano            | Reduce impacto de outliers              |
|                           |                          | MAPE    | `mean_absolute_percentage_error(y_true, y_pred)` | Error relativo           | Interpretación porcentual               |
| RandomForestRegressor     | Ensemble (bagging)       | R²      | `r2_score(y_true, y_pred)`                       | Varianza explicada       | Mejora generalización                   |
|                           |                          | MSE     | `mean_squared_error(y_true, y_pred)`             | Error cuadrático         | Reduce varianza                         |
|                           |                          | RMSE    | `mean_squared_error(..., squared=False)`         | Error en escala original | Interpretación directa                  |
|                           |                          | MAE     | `mean_absolute_error(y_true, y_pred)`            | Error absoluto           | Muy usado en producción                 |
|                           |                          | MedAE   | `median_absolute_error(y_true, y_pred)`          | Error mediano            | Alta robustez                           |
|                           |                          | MAPE    | `mean_absolute_percentage_error(y_true, y_pred)` | Error relativo           | Negocio                                 |
| GradientBoostingRegressor | Ensemble (boosting)      | R²      | `r2_score(y_true, y_pred)`                       | Varianza explicada       | Alto poder predictivo                   |
|                           |                          | MSE     | `mean_squared_error(y_true, y_pred)`             | Error cuadrático         | Sensible a tuning                       |
|                           |                          | RMSE    | `mean_squared_error(..., squared=False)`         | Error en escala original | Interpretación directa                  |
|                           |                          | MAE     | `mean_absolute_error(y_true, y_pred)`            | Error absoluto           | Alternativa robusta                     |
|                           |                          | MedAE   | `median_absolute_error(y_true, y_pred)`          | Error mediano            | Robustez                                |
|                           |                          | MAPE    | `mean_absolute_percentage_error(y_true, y_pred)` | Error relativo           | Porcentaje                              |
| SVR                       | Kernel (SVM regresión)   | R²      | `r2_score(y_true, y_pred)`                       | Varianza explicada       | Depende del kernel                      |
|                           |                          | MSE     | `mean_squared_error(y_true, y_pred)`             | Error cuadrático         | Sensible a hiperparámetros              |
|                           |                          | RMSE    | `mean_squared_error(..., squared=False)`         | Error en escala original | Magnitud del error                      |
|                           |                          | MAE     | `mean_absolute_error(y_true, y_pred)`            | Error absoluto           | Evaluación alternativa                  |
|                           |                          | MedAE   | `median_absolute_error(y_true, y_pred)`          | Error mediano            | Robustez                                |
|                           |                          | MAPE    | `mean_absolute_percentage_error(y_true, y_pred)` | Error relativo           | Uso en negocio                          |


Cuando se usa