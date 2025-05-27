# Tipología y ciclo de vida de los datos: 
# PR2: ¿Cómo realizar la limpieza y análiis de los datos?

## Descripción 

En este proyecto analizamos un conjunto de datos técnico-administrativos de la flota pesquera española desde 1987 hasta 2025, utilizando identificadores únicos para garantizar la trazabilidad de cada buque. El objetivo es estudiar la evolución histórica, estructura y distribución geográfica de la flota, identificando patrones en características como tamaño, potencia, antigüedad y modalidad de pesca, para apoyar la toma de decisiones en gestión, sostenibilidad y modernización del sector pesquero.

## Estructura del Proyecto
- **./**
  - `README.md`: Archivo de documentación del proyecto.
  - `requirements.txt`: Lista de dependencias necesarias para la ejecución.
  - `LICENSE.txt`: Licencia bajo la que se distribuye el dataset generado.

- **./data/**: Contiene los datos generados en la PR1, y los limpios de la PR2.
  - `datos_buques_ESP.csv`: Archivo CSV con los datos extraídos del registro europeo.
  - `data_clean`: Archivo CSV con los datos limpios y listos para el análisis.
    
- **./memoria/**: Informes de la PR2.
  - `PR2_Ubeda_Quesada_Julio-Zamora_Vera_Lucas.pdf`: Documento de la memoria del proyecto.

- **./figues/**: Gráficos generados de la PR2.

- **./output/**: Archivos resultantes de la PR2.
  - `modelo_supervisado.pkl`: Archivo pkl del modelo.
  - `modelo_no_supervisado.pkl`: Archivo pkl del modelo.
  - `EstadisticasDescriptivas.cvs`: Dataset descriptivo de las variables.
  - `resultados_cluster`: Dataset con clusters asignados a las embarcaciones.

- **./src/**: Código fuente.
  - `limpieza-datos_V2.ipynb`: Jupyter notebook de la limpieza y análisis de los datos.
  - `Modelado.ipynb`: Jupyter notebook con el proceso de modelado y contraste de hipótesis
    
## Pasos seguidos en la limpieza:

-  Preparación y limpieza inicial de los datos
    -  Revisión de duplicados
    -  Identificación de caracteres especiales, valores vacíos y/o nulos
    -  Simplificación del nombre de las columnas
    -  Corrección de errores de tipo de dato (1)
    -  Corrección de errores de tipo de dato (2)
-  Transformación estructural del dataset
    - Descomposicion de columnas
        -  ‘estado’ en dos: ‘estado_rgfp’ y ‘fc_estado’
        -  ‘puerto_base’ en cuatro: ‘codigopostal’, ‘puerto’, ‘provincia’ y ‘comunidad atutonoma’
    - Estandarización de categorías
-  Tratamiento de valores anómalos y calidad de datos
    -  Identificación y gestión de valores extremos
        - Imputación de los valores 0 e ilógicos
        - Detección de outliers
    -  Eliminación de columnas no relevantes
- Enriquecimiento y análisis exploratorio inicial
    - Creación de la variable ‘edad_buque’
        - Distribución de los buques por su edad
    - Evolución temporal de la eslora, arqueo, potencia y material del cascco de los buques
    - Distribución en las columnas numéricas
    - Correlaciones

## Pasos seguidos en análisis:

- Modelo supervisado (clasificación)
    - Normalización de las variables numéricas
    - Estandarizado de variables numéricas
    - Codificación de variables categóricas
    - Eliminación de identificadores y columnas no relevantes
    - Entrenamiento de 4 modelos base
    - Optimización del mejor modelo
    - Diagnosisi del modelo
    - Modelado redes neuronales densas (deep learning)
    - Comparativa de modelos
    - Representación de resultados y errores
  
- Modelo no supervisado (clustering)
    - Eliminación de columnas no relevantes
    - Estandarizado de variables numéricas
    - Codificación de variables categóricas
    - Generación de clusters (KNN)
    - Diagnosis del modelo
    - Representación de resultados

- Contraste de hipótesis:
    - Comunidad autónoma vs arte de pesca
    - Eslora vs arte de pesca


## Principales resultados y conclusiones

1. Se observa una modernización de la flota pesquera española en los ultimos 10-15 años, con la creación de buques nuevos con mayor tamaño y potencia, así como incorporaciones recientes a la flota. Sin embargo, muchos buques presentan una edad mayor a 30 años de servicio resaltando el envejecimiento de la flota.

2. Las variables eslora, arqueo y potencia presentan distribuciones sesgadas a la derecha: la mayoría son buques pequeños, pero hay algunos casos extremos.  Esto resalta la importancia de los buques de pequeña eslora en relación al tamaño de la flota pesquera española.

3. Las variables eslora, arqueo y potencia están relacionadas de forma coherente, validando tanto los datos como la imputación.

4. El tipo de pesca tiene dependencia de la comunidad autónoma en la que está registrado el buque.

5. El tamaño del buque está relacionado con el tipo de pesca que realiza.

6. El modelo supervisado logra clasificar el buque según si tipo de arte de pesca con una sensibilidad media del 71% y un f1-score de 86%.

7. El modelo no supervisado divide la flota según sus características técnicas en 11 grupos diferenciados con un Silhouette Score de 0.4, habiendo cierto solapamiento en los grupos de buques más pequeños pero con buena diferenciación de los buques medianos y grandes.



