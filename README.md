<h1 align="center"> Modelo de recomendación de Juegos de Steam</h1>

<h4 align="center"> Este repositorio alberga el Proyecto Individual de Machine Learning realizado durante el Master de DataScience & IA en Evolve Academy. </h4>


 <p align="center">
  <img src="https://img.shields.io/badge/Python-green">
  <img src="https://img.shields.io/badge/Numpy-aqua">
  <img src="https://img.shields.io/badge/Pandas-blue">
  <img src="https://img.shields.io/badge/Matplotlib-grey">
  <img src="https://img.shields.io/badge/Seaborn-aquamarine">
  <img src="https://img.shields.io/badge/Scikitlearn-orange">
  <img src="https://img.shields.io/badge/Render-cyan">
  <img src="https://img.shields.io/badge/TextBlob-black">
</p>


<p align="center">
  <img src="./imagen/steam.png" alt="STEAM" width="400">
</p>


<h1 align="center"> Desarrollo del Sistema de Recomendación para STEAM </h1>

## Descripción del Proyecto

Este proyecto se centra en el desarrollo de un sistema de recomendación para la plataforma de videojuegos STEAM, asumiendo el rol de MLOps Engineer. Se ha implementado un proceso de Extracción, Transformación y Carga (ETL), así como un Análisis Exploratorio de Datos (EDA). El objetivo principal es desplegar una API que incorpore un modelo de Machine Learning capaz de realizar análisis de sentimiento sobre los comentarios de los usuarios. Este modelo también sirve como base para ofrecer recomendaciones personalizadas de videojuegos, con el propósito de mejorar la experiencia de usuario en la plataforma.

## Fases del Proyecto

El desarrollo del proyecto ha seguido una estructura fundamentada en etapas clave:

- **ETL (Extracción, Transformación y Carga)**: Preparación y depuración de los datos para su correcto procesamiento.  

- **EDA (Análisis Exploratorio de Datos)**: Análisis exhaustivo para comprender las características esenciales del conjunto de datos.  

- **Implementación de funciones (endpoints) para la API**: Desarrollo de funciones fundamentales que permiten el funcionamiento del sistema.  

- **Modelado con Machine Learning**: Diseño y desarrollo de modelos de aprendizaje automático enfocados en el análisis de sentimiento y la recomendación.  


## ETL (Extracción, Transformación y Carga)

Durante esta fase, se abordó el desafío de convertir archivos en formato JSON a CSV, lo cual implicó la detección y corrección de errores de codificación, la transformación y limpieza de los datos, así como el desanidado de estructuras. Este proceso requirió una investigación exhaustiva para asegurar la coherencia y calidad de los datos generados.

## EDA (Análisis Exploratorio de Datos)

Se llevó a cabo un análisis detallado del conjunto de datos, abordando la limpieza de valores nulos y la generación de representaciones gráficas. Este proceso permitió una comprensión profunda de la integridad, estructura y comportamiento de los datos, sentando una base sólida para las fases posteriores.

### Feature Engineering

Dentro del conjunto de datos **user_reviews**, se recolectaron reseñas de diversos usuarios. Se implementó una columna adicional para clasificar el sentimiento de cada reseña utilizando la librería de Procesamiento de Lenguaje Natural (NLP) **TextBlob**. La categorización se realizó en una escala: '0' para sentimiento negativo, '1' para neutral y '2' para positivo. Este análisis aportó un valor adicional al dataset, permitiendo una visión más enriquecida del comportamiento de los usuarios.

## Desarrollo de la API

La API fue desarrollada utilizando el framework **FastAPI**. A continuación, se describen los endpoints implementados:

1. **PlayTimeGenre(género)**: Retorna el año con la mayor cantidad de horas jugadas para un género específico.
2. **UserForGenre(género)**: Identifica el usuario con mayor tiempo de juego en el género especificado y muestra la distribución por año.
3. **UsersRecommend(año)**: Devuelve el top 3 de juegos más recomendados por los usuarios en un año determinado (reseñas positivas o neutras con alta puntuación).
4. **UsersNotRecommend(año)**: Retorna el top 3 de juegos menos recomendados (reseñas negativas y críticas).
5. **sentiment_analysis(año)**: Proporciona una distribución de reseñas positivas, negativas y neutrales por año de lanzamiento.

Estas funciones son esenciales para el correcto funcionamiento de la API y permiten realizar consultas eficientes sobre el sistema de recomendación.

## Modelado (Machine Learning)

El sistema de recomendación fue desarrollado mediante técnicas de similitud del coseno, bajo dos enfoques principales:

- **Recomendación item-item**: A partir del ID de un juego, se generan recomendaciones de juegos similares.
- **Recomendación user-item**: Dado un ID de usuario, se sugieren juegos basados en usuarios con gustos afines.

El primer modelo evalúa la relación entre ítems para encontrar similitudes, mientras que el segundo analiza patrones de comportamiento entre usuarios para predecir preferencias.


## Ejecución de la API con FastAPI

Para ejecutar la API localmente, se deben seguir los siguientes pasos:

1. Clonar el repositorio:  
   - `git clone git@github.com:tpadrinp/Recomendaciones-Steam.git`
2. Navega al directorio del proyecto:
   - `cd Recomendaciones-Steam`

3. Crea un entorno virtual (opcional pero recomendado):
   - `python -m venv venv`
   - `source venv/bin/activate`  #En Windows: `venv\Scripts\activate`

4. Instala las dependencias necesarias:
   - `pip install -r requirements.txt`

## Conclusión

Este proyecto ha sido una experiencia profundamente formativa. No solo ha fortalecido mis habilidades técnicas en áreas como ETL, EDA, modelado con Machine Learning y despliegue de APIs, sino que también ha resaltado la importancia de una planificación estructurada y un tratamiento riguroso de los datos. La posibilidad de implementar una solución de principio a fin, desde el procesamiento de datos hasta su publicación en la nube, ha sido clave para comprender el ciclo completo de desarrollo de un sistema de recomendación.

En definitiva, este trabajo ha consolidado conocimientos y competencias esenciales para el desarrollo de aplicaciones inteligentes orientadas al usuario final.