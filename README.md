# Tipología y ciclo de vida de los datos: 
# PR2: ¿Cómo realizar la limpieza y análiis de los datos?

## Descripción 

Este proyecto utiliza Selenium, Requests y BeautifulSoup para automatizar la extracción de datos desde el sitio web de Fleet Europa de la Unión Europea y el registro nacional de la flota pesquera española. El script automatiza la búsqueda de todos los barcos registrados, navega a través de las páginas de resultados y guarda los datos en un archivo CSV.

## Estructura del Proyecto

- **data/**: Contiene los datos generados en la PR1, y los limpios de la PR2.
  - `datos_buques_ESP.csv`: Archivo CSV con los datos extraídos del registro europeo.
  - `data_clean`: Archivo CSV con los datos limpios y listos para el análisis.
    
- **memoria/**: Informes de la PR2.
  - `PR2_Ubeda_Quesada_Julio-Zamora_Vera_Lucas.pdf`: Documento de la memoria del proyecto.

    
- **figues/**: Gráficos de la PR2.
  - `boxplots.png`: Boxplots para la visualizacion de outliers.
  - `histogramas_edadbuque.png`: Distribución del numero de buques por edad.
  - `lineplot_evolucion_esl-arq-pot.png`: Evolución temporal de las caracteristicas tecnicas del buque.
  - `correlacion_heatmap.png`: Matriz de correlacion de las variables numericas.
  - Grafico modelo
  - Grafico modelo
  - ...


- **src/**: Código fuente.
  - `limpieza-analisis_datos.ipynb`: Jupyter notebook de pruebas.
  - `README.md`: Archivo de documentación del proyecto.
  - `requirements.txt`: Lista de dependencias necesarias.
  - `LICENSE.txt`: Licencia bajo la que se distribuye el dataset generado.
    
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
    - Evolución temporal de la eslora, arqueo y potencia de los buques
    - Distribución en las columnas numéricas
    - Correlaciones

## Pasos seguidos en análisis:

- Modelo 1
    - Transformaciones
    - Otros
    - ...
- Modelo 2
    - Transformaciones
    - Otros
    - ...




## Principales resultados y conclusiones



