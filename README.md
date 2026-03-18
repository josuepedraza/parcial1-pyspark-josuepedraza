# Analisis Exploratorio de Enfermedades Cardiovasculares con PySpark y Docker

Este proyecto presenta un analisis exploratorio de datos sobre factores de estilo de vida relacionados con enfermedades cardiovasculares. El trabajo se realiza utilizando PySpark dentro de un entorno Docker que incluye Jupyter Lab.

- Estructura del proyecto

El proyecto esta organizado en tres partes principales. La carpeta data contiene el archivo CVD_cleaned.csv que es el dataset utilizado. La carpeta notebooks contiene el archivo analisis_exploratorio.ipynb donde se desarrolla todo el analisis. En la raiz se encuentran los archivos docker-compose.yml y README.md.
 

PARCIAL1-PYSPARK-JOSUEPEDRAZA
│
├── data/
│   └── CVD_cleaned.csv
│
├── notebooks/
│   ├── analisis_exploratorio.ipynb
│   ├── .ipynb_checkpoints/
│   │   └── analisis_exploratorio-checkpoint.ipynb
│   └── spark-warehouse/
│
├── docker-compose.yml
├── README.md

- Ejecucion del proyecto

Ejecucion del proyecto

Para ejecutar el proyecto es necesario tener instalado Docker Desktop.

Primero, se debe clonar el repositorio en tu computador utilizando el siguiente comando:

git clone https://github.com/josuepedraza/parcial1-pyspark-josuepedraza.git

despues ingresar a la carpeta del proyecto:

cd parcial1-pyspark-josuepedraza

Una vez ubicado en la carpeta raiz del proyecto, se debe ejecutar el comando:

docker-compose up

Finalmente, se puede acceder a Jupyter desde el navegador en la siguiente direccion:

http://localhost:8888


- Explicacion del archivo docker-compose.yml

La version indica el formato del archivo de Docker Compose que se esta utilizando

La seccion de services define los contenedores que se van a ejecutar. En este caso, se crea un servicio que contiene Jupyter junto con PySpark

La imagen jupyter/pyspark-notebook es una imagen oficial que ya incluye Python, PySpark, Jupyter y librerias necesarias para analisis de datos.

El mapeo de puertos 8888:8888 significa que el puerto 8888 del contenedor se conecta con el puerto 8888 del computador local. Esto permite acceder a Jupyter desde el navegador.

Los volumes permiten compartir archivos entre el computador y el contenedor. Esto es importante porque permite guardar los notebooks y evitar que se pierdan al detener el contenedor.

La variable de entorno JUPYTER_ENABLE_LAB permite habilitar Jupyter Lab que  ofrece una interfaz mas moderna y organizada.

- Descripcion del dataset

El dataset utilizado proviene del sistema BRFSS que es una encuesta de salud en Estados Unidos. Este dataset contiene informacion sobre habitos de vida, enfermedades cronicas y factores de riesgo. Se seleccionaron variables relacionadas con actividad fisica, consumo de alcohol, alimentacion, estado de salud y presencia de enfermedad cardiovascular.

- Analisis realizado

Se realizo un analisis exploratorio que incluye lectura de datos con PySpark, revision del esquema, identificacion de valores nulos, estadistica descriptiva, analisis de correlaciones, identificacion de outliers y analisis de variables categoricas mediante frecuencias, tablas de contingencia y correlaciones entre variables.

- Resultados principales

Se encontro que la actividad fisica esta relacionada con menor presencia de enfermedad cardiovascular. El estado de salud general muestra una relacion clara con la enfermedad. El consumo de alcohol no presenta una relacion fuerte.

- Limitaciones del analisis

El dataset proviene de encuestas, lo que puede generar sesgos en las respuestas.

No se analizan variables médicas más profundas, lo que limita el análisis a factores generales.   

El dataset es de Estados Unidos, por lo que los resultados pueden no representar otras poblaciones.

- Trabajo futuro

Se propone desarrollar modelos predictivos para estimar el riesgo de enfermedad cardiovascular. tambien se pueden aplicar tecnicas de machine learning para identificar variables mas importantes. Otra opcion es realizar analisis de agrupamiento para encontrar perfiles de riesgo.

