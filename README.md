# Asistentes virtuales y reconocimiento de imágenes - Cloud & Data Asunción 2019

<p align="center">
  <img src="recursos/watson.png" width="150" length="200">
</p>

## Itinerario

* Bienvenida
* Prerrequisitos
* Watson Assistant
* Watson Visual Recognition
* Integración entre los servicios
* Conclusiones

## Bienvenida

Durante este hands-on estaremos conociendo dos de los principales servicios que ofrece Watson en IBM Cloud. Estos servicios son: Watson Assistant, que permite desarrollar asistentes virtuales de forma fácil y rápida, y Watson Visual Recognition, que ofrece la posibilidad de entrenar modelos de clasificación y detección de objetos en imágenes como también utilizar modelos pre-entrenados.

En primera instancia se realizará un práctico para cada servicio con el objetivo de entender cómo funcionan y también conocer los conceptos básicos que estos involucran. 

Dentro de Watson Assistant construiremos un asistente virtual para vuelos que permitirá reservar pasajes y realizar el check-in para un vuelo específico. 

En el caso de Watson Visual Recognition, se entrenará un modelo para reconocimiento de partes dañadas en vehículos a través de imágenes y luego, mediante la interfaz gráfica de IBM Cloud como también mediante código, se realizarán consultas al modelo entrenado.

Para terminar el hands-on se mostrará un aplicación que integra los servicios anteriores.

## Prerrequisitos 


### 1 Crear una cuenta en IBM Cloud

Es necesario tener creada una cuenta de IBM Cloud para poder realizar el hands-on.

Si aún no tiene cuenta de IBM Cloud, haga clic [aqui](https://ibm.biz/CD-PY19) para crear una. 

### 2 Descargar este repositorio

Para descargar el repositorio haga clic en el botón **Clone or download**, que se encuentra en la parte superior derecha de la pantalla dentro GitHub.

## Watson Assistant

Watson Assistant es el servicio que ofrece IBM Cloud para el desarrollo de asistentes virtuales. Su interfaz gráfica amigable con el usuario le permite a este construir chatbots fácilmente y de forma rápida.

En este hands-on importaremos un asistente virtual ya desarrollado, que permite reservar pasajes para viajes aéreos. A medida que recorramos la solución entenderemos algunos conceptos básicos sobre asistentes virtuales y luego agregaremos una funcionalidad que permita a los usuarios consultar el estado de su vuelo.

Los pasos a seguir son los siguientes:

1. Ingresar a [IBM Cloud](https://cloud.ibm.com/login).
2. Hacer clic en la pestaña **Catalog**, que se encuentra en la zona superior de la pantalla.
3. Ingresar a la sección *AI* y seleccionar el servicio **Watson Assistant**.
4. Hacer clic en el botón **Create**, que se encuentra en la zona derecha de la pantalla. Esto creará por defecto una instancia con el plan gratuito de Watson Assistant.
5. Hacer clic en el botón **Launch Watson Assistant**.
6. Entrar a la pestaña *Skills*, que se encuentra en la zona izquierda de la pantalla, y hacer clic en el botón **Create skill**.
7. Seleccionar la opción **Dialog skill** y hacer clic en *Next*.
8. Ingresar a la pestaña *Import skill*	y presionar el botón **Choose JSON file**. El archivo que se debe seleccionar es **c&d_py_skill.json**, que se encuentra dentro de la carpeta *code/assistant* del repositorio.
9. Agregar en la pestaña *Intents* una intención bajo el nombre *estado* con 5 ejemplos, que va a representar la intención del usuario en el momento en que consulte el estado de su vuelo.
10. Agregar en la pestaña *Dialog* un nuevo nodo con el nombre *Consultar estado*. Este nodo se debe activar cuando el usuario quiera conocer su estado, por lo que le asignaremos la intención *estado*. Para esto último debe seleccionar la intención en la sección *If assistant recognizes*. A este nodo se le pueden asignar diferentes respuestas y que éstas sean seleccionadas de forma aleatoria. 
11. Probar el asistente haciendo clic en el botón **Try it**, que se encuentra en la esquina superior derecha. 

## Watson Visual Recognition

Watson Visual Recognition es el servicio que ofrece IBM Cloud para el desarrollo de modelos de machine learning para clasificación y detección de objetos en imágenes. 

Además de permitirle al usuario crear sus propios modelos para casos de uso particulares, el servicio también ofrece la posibilidad de utilizar modelos que ya están entrenados en la nube. 

Estos modelos pre-entrenados son:

* General
* Comida
* Explícito

En este hands-on entrenaremos un modelo que permite reconocer partes de vehículos que se encuentran dañadas.\
El modelo podrá reconocer:

* Paragolpes rotos
* Vidrio frontal roto

Los pasos que se deben seguir para crear este modelo son los siguientes:

1. Ingresar a [IBM Cloud](https://cloud.ibm.com/login).
2. Hacer clic en la pestaña **Catalog**, que se encuentra en la zona superior de la pantalla.
3. Ingresar a la sección *AI* y seleccionar el servicio **Visual Recognition**.
4. Hacer clic en el botón **Create**, que se encuentra en la zona derecha de la pantalla. Esto creará por defecto una instancia con el plan gratuito de Visual Recognition.
5. Hacer clic en el botón **Create a Custom Model**.
6. Hacer clic en el botón **Create model**, que se encuentra dentro de *Classify images*. 
7. Se abrirá una interfaz en la que debemos crear un proyecto para que contenga nuestra instancia del servicio. A este proyecto le debemos asignar un nombre y nuestra instancia de Visual Recognition.
8. Se abrirá una vista y es aquí donde podremos cargar imágenes para el entrenamiento de nuestro modelo. Le debemos asignar un nombre al modelo en la entrada que se encuentra en la zona superior izquierda.
9. Hacer clic en el botón **Browse**, que se encuentra en el panel de la derecha. Aquí debemos cargar los tres archivos .zip que se encuentran en *codigo/visual/entrenamiento*. Esta acción nos cargará tres nuevas clases en nuestro modelo, pero debemos borrar la clase vehiculos_sanos_entrenamiento, ya que esas imágenes las utilizaremos para la clase *Negative*. En el proceso de borrado, marcar la opción para que se borren también las fotos.
10. Desde el panel de la derecha, arrastar *vehiculos_sanos_entrenamiento.zip* a la clase **Negative**.
11. Ahora que se tienen completas las clases del modelo se debe hacer clic en el botón **Train model**, que se encuentra en la zona superior de la pantalla. El proceso de entrenamiento puede demorar varios minutos.
12. Dentro de la carpeta *codigo/visual/test* tenemos varias fotos con las que podremos probar nuestro modelo una vez que el proceso de entrenamiento haya finalizado.

## Integración entre los servicios

Pasos:

1. Abrir aplicación **Pipo** y mostrar. (no se si lo uso yo o se lo doy a ellos para que prueben)
