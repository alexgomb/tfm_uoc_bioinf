# Código del Trabajo Final de Máster (TFM) - Bioinformática y Bioestadística

Este repositorio contiene los scripts de análisis, preprocesamiento de datos y modelado estadístico desarrollados para el Trabajo Final de Máster: **[Análisis de NGS del TCR y uso de algoritmos para la clasificación de pacientes con CPNM]**.

El proyecto se centra en el análisis de datos clínicos y ómicos (TCR), incluyendo limpieza de datos, cálculo de índices de diversidad ecológica, reducción de dimensiones y modelado predictivo mediante Machine Learning.

## Estructura del Repositorio

Los archivos principales del proyecto se describen a continuación:

### 1. Documentación y Preprocesamiento
* **`Documentacion_variables.Rmd`**: Script principal de RMarkdown que contiene el flujo de trabajo de ingeniería de datos.
    * Descripción detallada de las variables clínicas y moleculares.
    * Definición y filtrado de la cohorte de estudio.
    * Cálculo de índices ecológicos (Shannon, Simpson, riqueza, etc.) aplicados al repertorio de TCR.
    * Fusión (*merge*) de datasets multimodales (clínico + secuenciación).
    * Estrategia e implementación de imputación de valores faltantes (NA).
* **`BLIO_Documentacion.pdf`**: Documento compilado generado a partir del script anterior. Sirve como referencia estática de la calidad del dato y las decisiones tomadas durante el preprocesamiento.

### 2. Análisis No Supervisado
* **`pca.Rmd`**: Script dedicado al análisis exploratorio de datos mediante técnicas de reducción de dimensionalidad.
    * Análisis de Componentes Principales (PCA).
    * Evaluación de la varianza explicada y proyección de las muestras.

### 3. Modelado Predictivo (Machine Learning)
* **`modelos_ml.Rmd`**: Código fuente para el entrenamiento y validación de modelos predictivos.
    * Partición de datos (Train/Test).
    * Entrenamiento de algoritmos (especificar aquí si usas Random Forest, SVM, glmnet, etc.).
    * Evaluación de métricas de rendimiento (AUC, sensibilidad, especificidad).

## Requisitos y Dependencias

El código ha sido desarrollado en **R**. Para reproducir los análisis, se requiere la instalación de las siguientes librerías principales:

* **Manipulación de datos:** `tidyverse`, `dplyr`, `tidyr`.
* **Análisis ecológico:** `inmunarch`.
* **Visualización:** `ggplot2`.
* **Modelado y ML:** `caret`, `tidymodels` (o paquetes específicos como `randomForest`, `glmnet`).
* **Imputación:** `mice`, `missForest`
* **Reportes:** `knitr`, `rmarkdown`.

## Instrucciones de Uso

Para regenerar los reportes o ejecutar el código:

1.  Clonar este repositorio.
2.  Abrir el proyecto en RStudio.
3.  Asegurarse de que los archivos de datos brutos estén en el directorio de trabajo (o ajustar las rutas relativas en los scripts).
4.  Renderizar los archivos `.Rmd` individualmente:

```r
rmarkdown::render("Documentacion_variables.Rmd")
rmarkdown::render("pca.Rmd")
rmarkdown::render("modelos_ml.Rmd")
```

# Autor

[Alejandro Gombau García] Máster en Bioinformática y Bioestadística Universitat Oberta de Catalunya (UOC) / Universitat de Barcelona (UB)
