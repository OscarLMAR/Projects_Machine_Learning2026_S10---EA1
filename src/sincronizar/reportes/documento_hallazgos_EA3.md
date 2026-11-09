# Documento de hallazgos

## 1. Pregunta de negocio

¿Es posible identificar el estilo de consumo de los clientes teniendo en cuenta su ubicación geográfica y el valor de su cuota mensual?

## 2. Dataset utilizado

Se utilizó el dataset `hpestrellag/customer_profile`, que contiene información sobre los clientes, su ubicación geográfica, su cuota mensual y su estilo de consumo.

Para el experimento se utilizaron las variables `department`, `locality`, `province` y `monthly_fee_usd`. La variable objetivo fue `consumption_style`.

## 3. Hallazgos principales

Se entrenó un modelo de clasificación Random Forest para identificar los estilos de consumo de los clientes.

El modelo obtuvo una exactitud del **57,64 %**. Sin embargo, al revisar las predicciones se encontró que clasificó todos los registros como `occasional`.

Esto significa que no logró distinguir correctamente los otros estilos de consumo: `casual`, `weekend-viewer`, `binge-watcher` y `heavy-user`.

El F1 macro fue aproximadamente del **15 %**, lo que demuestra que el desempeño del modelo fue bajo al evaluar todas las categorías.

También se realizaron pruebas estadísticas para analizar las variables predictoras:

- No se encontró asociación estadísticamente significativa entre el estilo de consumo y el departamento.
- Tampoco se encontró asociación significativa con la localidad ni con la provincia.
- No se encontraron diferencias estadísticamente significativas en la cuota mensual entre los diferentes estilos de consumo.

## 4. Respuesta a la pregunta de negocio

Con los resultados obtenidos, no fue posible identificar de manera confiable el estilo de consumo de los clientes utilizando únicamente su ubicación geográfica y el valor de su cuota mensual.

El modelo presentó dificultades para diferenciar las cinco categorías, por lo que estas variables no fueron suficientes para obtener una clasificación satisfactoria en el experimento realizado.

## 5. Confiabilidad y limitaciones

Los resultados deben interpretarse con precaución por las siguientes razones:

- Existe un desequilibrio en la cantidad de clientes de cada estilo de consumo.
- La categoría `occasional` representa la mayor parte de los registros.
- El modelo clasificó todos los clientes como `occasional`.
- Las variables utilizadas pueden no contener suficiente información para diferenciar los estilos de consumo.
- Los resultados corresponden al dataset y a la configuración del experimento realizado.

## 6. Recomendaciones

- Incorporar nuevas variables relacionadas con los hábitos y la frecuencia de consumo.
- Analizar otras características de los clientes que permitan diferenciar sus comportamientos.
- Probar otras configuraciones y algoritmos de clasificación.
- Evaluar estrategias para manejar el desequilibrio entre las categorías.
- Comparar los resultados utilizando métricas como F1 macro, precisión y recall.

## 7. Conclusión

El experimento permitió comprobar que la ubicación geográfica y la cuota mensual, por sí solas, no permitieron identificar satisfactoriamente los estilos de consumo de los clientes.

Se recomienda incorporar información adicional sobre los hábitos de consumo para desarrollar un modelo que pueda realizar predicciones más confiables.
