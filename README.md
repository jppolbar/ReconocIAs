# Proyeto ReconocIAs - Reconocimiento de Personas y Emociones

Este proyecto se ha realizado como proyeto final del Máster en Deep Learning de MIOTI. Reconoce personas y sus emociones en tiempo real o con video
pregrabado o imagen fija, dejando como resultado un video o imagen de salida con las emociones y personas registaradas.

## Contenido y Estrutura del proyecto
El proyeto se divide en 10 notebooks y 10 carpetas:

* **PRY_Almacenamiento_caras_FER.iypnb**  -  En este notebook es donde se encuentra el software que permite registrar y crear las imagenes de las personas para el  modelo de reconocimiento de personas.
* **PRY_Detector_FER.iypnb**  -  En este notebook vamos a probar la combinación de los diferentes modelos generados anteriormente. El objetivo es que en una grabación en tiempo real, el sistema sea capaz de poner el nombre de la persona identificada, si esta ha sido registrada, en caso contrario será 'desconocido' y la emoción de esta persona, esto se realizará para todos los rostros identificados, sean conocidos por el modelo o no.

* **PRY_Detector_FER_M.iypnb**  -  En este notebook vamos a probar la combinación de los diferentes modelos generados anteriormente. El objetivo es que en una grabación en tiempo real, el sistema sea capaz de poner el nombre de la persona identificada, si esta ha sido registrada, en caso contrario será 'desconocido' y la emoción de esta persona, esto se realizará para todos los rostros identificados, sean conocidos por el modelo o no. En el caso del modelo reconocedor de emociones se maneja la emoción Bored.

* **PRY_Entrenamiento_caras_FER.iypnb**  -  En este notebook vamos a realizar el entrenamiento de las imágenes de las personas registradas previamente. Para llevar a cabo esta tarea vamos a utilizar el reconocedor Eigenfaces de openCV del que hablaremos más adelante en el notebook.

* **PRY_Flash_Detector_FER.iypnb**  - Este notebook es necesario para el POC de la solución Móvil. Utiliza Flask para levantar un servidor en local y así se puede consultar una página HTML desde el dispositivo móvil, desde reconocer a la persona y sus emociones 

* **PRY_Preprocessing_FER_M.iypnb**  -  El objetivo es generar una emoción nueva, Bored, a partir de una serie de imagenes de personas recopiladas en internet con la expresión de aburrido (bostecos, cansado, cabeza recostada ...) e incluirla como una emoción adicional al dataset FER2013. Las imagenes serám transformadas en imagenes en escala de grises y con un tamaño de 48x48 y se marcaran con label 7. Nos apoyamos en el modelo preentrenado de Opencv Haarcascade para capturar los rostros. 

* **PRY_VGGFace_MODEL_FER.iypnb**  -  Preparar la estructura de la red neuronal convolucional y entrenarla para que sea capaz de identificar las diferentes emociones clasificadas en el dataset. 

* **PRY_VGGFace_MODEL_FER_M.iypnb**  - En este notebook vamos a definir una nueva emoción 'bored' y nos quedaremos sólo con las emociones más relevantes del modelo original 'angry', 'happy', 'neutral' y generaremos una red igual a la inicial y la entrenaremos con estas clases. 

* **PRY_VGGFace_MODEL_FER_SGD.iypnb**  -  Preparar la estructura de la red neuronal convolucional, con otra estructura más profunda y con más capas Densas. También se usa un optimizer SGD.

* **PRY_VGGFace_MODEL_FER_SGD.iypnb**  -  Preparar la estructura de la red neuronal convolucional, con otra estructura más profunda y con más capas Densas. También se usa un optimizer SGD.

* **PRY_Visualizacion_FER.iypnb**  -  EDA del dataset FER2013.

### Carpeta "data"
En esta carpeta residen los ficheros de datos:
* **fer2013.csv** - Dataset fer2013
* **fer2013_Mioti.csv** - Dataset fer2013 más emoción Bored.
* **bored.csv** - Imagenes Bored.
### Carpeta "img"
Imagenes utilizadas en los notebooks.
### Carpeta "images"
Carpeta donde se situan los videos e imagenes de entrada a procesar, así como las imagenes y videos de salida ya procesados.
### Carpeta "models"
Carpeta donde se situan los ficheros h5, json y xml de los distintos modelos utilizados, tanto los preentrenados de OpenCV como los modelos propios.
### Carpeta "logs"
Carpeta donde se situan los logs de entrenamiento.
### Carpeta "reconocimiento"
Carpeta donde se situan las fotos de las personas registradas que sirven para el entrenamiento del modelo que permite la identificación de las personas.
### Carpeta "droidcam"
Carpeta donde se guarda la aplicación para configurar la conexión entre la cámara del dispositivo móvil y el servidor donde corren los modelos. Esto para el POC.
### Carpeta "ngrok"
Carpeta donde se situan la aplicación que devuelve una url publica del servidor para que pueda consultar los resultados de la ejecución de los modelos. Esto para el POC.
### Carpeta "templates"
Carpeta donde se situan la pagina HTML que se muestra en el dispositivo móvil. Esto para el POC.
### Carpeta "test_faces"
Carpeta donde se situan las 300 fotos de cada una de las personas identificadas para el testeo del modelo previamente entrenado.

## Datos

* [Challenges in Representation Learning: Facial Expression Recognition Challenge](https://www.kaggle.com/c/challenges-in-representation-learning-facial-expression-recognition-challenge/data)
* 

## Principales librerias utilizadas.

* **pandas**
* **numpy**
* **matplotlib**
* **tensorflow**
* **keras**
* **Opencv**
* **Flask**
* **PIL**
* **OS**
* **json**
