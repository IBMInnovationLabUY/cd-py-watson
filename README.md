# Asistentes virtuales y reconocimiento de imágenes - Cloud & Data Asunción 2019

<p align="center">
  <img src="imagenes/watson.png" width="150" length="200">
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

* 1. Ingresar a [IBM Cloud](https://cloud.ibm.com/login).

* 2. Hacer clic en la pestaña **Catalog**, que se encuentra en la zona superior de la pantalla.

* 3. Ingresar a la sección *AI* y seleccionar el servicio **Watson Assistant**.

* 4. Hacer clic en el botón **Create**, que se encuentra en la zona derecha de la pantalla. Esto creará por defecto una instancia con el plan gratuito de Watson Assistant.

* 5. Hacer clic en el botón **Launch Watson Assistant**.

6. Entrar a la pestaña *Skills*, que se encuentra en la zona izquierda de la pantalla, y hacer clic en el botón **Create skill**.
7. Seleccionar la opción **Dialog skill** y hacer clic en *Next*.
8. Ingresar a la pestaña *Import skill*	y presionar el botón **Choose JSON file**. El archivo que se debe seleccionar es **c&d_py_skill.json**, que se encuentra dentro de la carpeta *code/assistant* del repositorio.
7. Ir a la sección de *Intenciones* y agregar dos intenciones: - reservar
							       - check-in
8. Ir a la sección *Entidades* y agregar dos entidades: - personas
						        - países
9. Ir a la sección *Diálogo* y agregar nodos: - Bienvenida
						* Variable de contexto para el nombre
					      - Realizar reserva
						* Dar opciones
					      - Realizar check-in
10. Probar el asistente 

## Watson Visual Recognition

Pasos:

1. Ir a catálogo
2. Ingresar a la sección *AI* y abrir **Visual Recognition**
3. Crear una instancia free del servicio
4. Ir a **Create model on Watson Studio**
5. Crear un modelo de clasificación
6. Modelo con dos clases: paragolpes y vidrio frontal roto
7. Negativos: todas las otras imágenes
8. Entrenar --> Yo ya lo tengo entrenado
9. Probar modelo nube
10. Probar modelo con código


## Integración entre los servicios

Pasos:

1. Abrir aplicación **Pipo** y mostrar. (no se si lo uso yo o se lo doy a ellos para que prueben)
