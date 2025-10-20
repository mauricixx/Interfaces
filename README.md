##### Introducción a Processing y Arduino para el desarrollo de una interfaz interactiva  Humano-Máquina (humacchina) como pieza artística.

1. [Hola Mundo](#void-setup) <br>
1. [Void Setup()](#void-setup) <br>
2. [Void Draw()](#void-draw)  <br>
3. [Hola Mundo :)](#hola-mundo) <br> 
4.  [Conceptos Básicos](#conceptos-básicos) <br>
   4.1 [ejemplo](#por-ejemplo) <br>
5. [Sistema de Coordenada en Processing](#sistema-de-coordenadas-en-processing) <br>
   5.1 [Razones históricas y prácticas](#razones-históricas-y-prácticas) <br>
   5.2 [Ejemplo visual](#ejemplo-visual) <br>
   5.3 [Localizador de puntos en el plano Cartesiano (p5js)](https://mauricixx.github.io/intro_processing/cartesiano/index.html) <br>
6. [Colores](#ii-colores)
7. [Interactividad](#interactividad) <br>
   7.1 [I. Uso del Mouse](#i-uso-del-ratón) <br>
   7.2 [II. Eventos del Mouse](#ii--eventos-del-ratón) <br>
   7.2.1 [mousePressed()](#mousepressed) <br>
   7.2.2 [mouseReleased()](#mousereleased) <br>
   7.2.3 [mouseDragged()](#mousedragged) <br>
   7.2.4 [mouseMoved](#mousemoved) <br>
   7.2.5 [Ejemplo 1](#ejemplo-de-uso-de-estas-funciones) <br>
   7.2.6 [Ejemplo 2](#en-este-ejemplo) <br>
8. [Animación](#animación) <br>
   8.1 [Concepto de Draw](#i-concepto-de-draw) <br>
   8.2 [Variables y Control](#ii-variables-y-control) <br>
9. [Cambiar Color del fondo en tiempo real](#cambiar-color-del-fondo-en-tiempo-real) <br>
10. [Guardar una imagen en Processing](#guardar-una-imagen-en-processing) <br>
    10.1 [I. Guardar una imagen en un momento especifico](#1-guardar-una-imagen-en-un-momento-específico) <br>
    10.2 [II. Guardar una secuencia de imágenes](#2-guardar-una-secuencia-de-imágenes) <br>
11. [Capturar un video en Processing](#capturar-un-video-en-processing) <br>
    11.1. [I. Instalación de la biblioteca video export en Processing 3](#i-instalación-de-la-biblioteca-video-export-en-processing-3) <br>
    11.2. [II Guardar video en Processing 4](#guardar-un-video-en-processing-4) <br>
    11.3. [Convertir imágenes en video usandosela ffmpeg](#ii-convertir-imágenes-en-video-usando-ffmpeg) <br>
12. [Creación de perilla en Processing](#creación-de-perilla-processing) <br>
13. [Creación de perilla en P5JS](#creación-de-perilla-p5js) <br>
14. [Movimiento cubo con perilla con Processing](#movimiento-cubo--perilla-processing) <br>
15. [Movimiento cubo con perilla con P5js](#movimiento-cubo--perilla-p5js) <br>
16. [Movimiento 1 cubo con 3 perillas. (PROCESSING)](#movimiento-1-cubo-con--3-perillas-processing) <br>
17. [Movimiento 1 cubo con 3 perillas. (P5JS)](#movimiento-1-cubo-con--3-perillas-p5js) <br>
18. [INTERFAZ II](#interfaz-ii)
19. [ARDUINO A PROCESSING](#arduino-a-processing)
20. [Hola Mundo](#hola-mundo-1)
21. [Led Intermitente - blink](#led-intermitente-blink)
22. [Control por pulsador](#control-por-pulsador)
23. [Led con potenciometro](#led-con-potenciómetro)
24. [Semáforo](#semáforo)
25. [Elipse Interactivo](#elipse-interactivo-controlar-un-circulo-en-processing-mediante-un-potenciometro-conectado-a-un-arduino-uno)
26. [Arduino + Botón + Processing:](#arduino--botón--processing)
27. [Arduino + Botón + Potenciometro + Processing:](#arduino--botón--potenciometro--processing)
28. [Estructuras de control:](#estructuras-de-control-en-arduino)
29. [Botonera:](#botonera)
30. [Sensor Sharp:](#conectar-un-sensor-de-distancia-sharp-a-arduino-sigue-estos-pasos)
31. [Sensor Humedad:](#sensor-de-humedad-dfrobot)


### **Void Setup()**:

En **Processing**, el método **void setup()** es una función fundamental que se utiliza para inicializar los valores y configuraciones del programa antes de que empiece a ejecutarse el bucle principal de dibujo, que está contenido en la función void draw().

1.	Inicialización: void setup() se ejecuta una sola vez al comienzo del programa. Es el lugar ideal para inicializar variables, configurar el tamaño de la ventana, y establecer cualquier configuración inicial necesaria para el programa.
2.	Configuración de la Ventana: A menudo, se utiliza para definir el tamaño de la ventana de visualización con la función size(ancho, alto).
3.	Configuraciones Iniciales: Puedes definir el color de fondo inicial con background(), establecer el modo de color con colorMode(), y configurar otros parámetros como la velocidad de fotogramas con frameRate(), entre otros.

###### Ejemplo básico que muestra cómo se utiliza void setup():

```js 
void setup() {
  // Configurar el tamaño de la ventana de visualización
  size(800, 600);
  
  // Establecer el color de fondo
  background(255);
  
  // Configurar el modo de color
  colorMode(RGB);
  
  // Configurar la velocidad de fotogramas
  frameRate(30);
}
```

1.	void setup() {:
	•	Declara la función setup(). Esta función se ejecuta una vez al inicio del programa y se utiliza para realizar configuraciones iniciales.
2.	// Configurar el tamaño de la ventana de visualización:
	•	Este es un comentario que describe la siguiente línea de código. Los comentarios no son ejecutados por el programa y se usan para explicar o anotar el código.
3.	size(800, 600);:
	•	Establece el tamaño de la ventana de visualización en 800 píxeles de ancho y 600 píxeles de alto.
4.	// Establecer el color de fondo:
	•	Comentario que describe la siguiente línea de código.
5.	background(255);:
	•	Establece el color de fondo de la ventana en blanco. El parámetro 255 corresponde al valor máximo de blanco en la escala de grises (0 es negro, 255 es blanco).
6.	// Configurar el modo de color:
	•	Comentario que describe la siguiente línea de código.
7.	colorMode(RGB);:
	•	Configura el modo de color a RGB (Rojo, Verde, Azul). Esto significa que los colores se especificarán en términos de sus componentes rojo, verde y azul.
8.	// Configurar la velocidad de fotogramas:
	•	Comentario que describe la siguiente línea de código.
9.	frameRate(30);:
	•	Configura la velocidad de fotogramas a 30 cuadros por segundo. Esto significa que la función draw() se ejecutará 30 veces por segundo.
10.	}:
	•	Cierra la función setup().

### **Void Draw()**:

```js
void draw() {
  // Dibujar un círculo en la posición del ratón
  fill(0);
  ellipse(mouseX, mouseY, 50, 50);
}
```

11.	void draw() {:
	•	Declara la función draw(). Esta función se ejecuta continuamente, una vez por cada fotograma, permitiendo la animación y la actualización continua de la pantalla.
12.	// Dibujar un círculo en la posición del ratón:
	•	Comentario que describe las siguientes líneas de código.
13.	fill(0);:
	•	Establece el color de relleno para las formas que se dibujen a continuación. El parámetro 0 corresponde al color negro en la escala de grises.
14.	ellipse(mouseX, mouseY, 50, 50);:
	•	Dibuja una elipse (círculo) en la posición actual del ratón (mouseX, mouseY). La elipse tiene un ancho y una altura de 50 píxeles. Como el ancho y la altura son iguales, se dibuja un círculo.
15.	}:
	•	Cierra la función draw().

En este ejemplo, setup() se utiliza para configurar la ventana de visualización, el color de fondo, el modo de color y la velocidad de fotogramas. Luego, draw() contiene el código que se ejecuta repetidamente para dibujar en la pantalla.
Este código crea una ventana de 800x600 píxeles con un fondo blanco y dibuja un círculo negro en la posición del ratón, actualizando la posición del círculo continuamente a medida que el ratón se mueve.

#### HOLA MUNDO:

```js
void setup() {
  // Esta función se ejecuta una sola vez al inicio del programa.
  
  size(400, 400);
  // Define el tamaño de la ventana de visualización en 400x400 píxeles.
  
  background(255);
  // Establece el color de fondo de la ventana en blanco (255 en escala de grises).
  
  textSize(32);
  // Define el tamaño de la fuente del texto en 32 píxeles.
  
  fill(0);
  // Establece el color de relleno en negro (0 en escala de grises).
  
  text("Hola Mundo", 100, 200);
  // Dibuja el texto "Hola Mundo" en las coordenadas (100, 200).
}
```

 ___________________________________________________________________________________________________________________________________


#### **CONCEPTOS BÁSICOS**.

##### I.	**Dibujar Formas Simples**:

•	Explicar la función size() para definir el tamaño de la ventana.
•	Introducir las funciones line(), rect(), ellipse() y point() para dibujar líneas, rectángulos, elipses y puntos.

```js
void setup() {
  size(400, 400);
}

void draw() {
  background(255); // Fondo blanco
  line(50, 50, 350, 350);
  rect(100, 100, 200, 200);
  ellipse(200, 200, 100, 100);
  point(200, 200);
}
```
###### Por ejemplo: 
1.	line(:
	•	Este es el comando de Processing para dibujar una línea. La función line() requiere cuatro parámetros que especifican las coordenadas de los puntos inicial y final de la línea.
2.	50, 50,:
	•	Estos son los primeros dos parámetros de la función line(). El 50 primero es la coordenada x del punto inicial de la línea, y el segundo 50 es la coordenada y del punto inicial de la línea.
	•	En este caso, la línea comienza en el punto (50, 50) en la ventana de visualización.
3.	350, 350:
	•	Estos son los segundos dos parámetros de la función line(). El 350 primero es la coordenada x del punto final de la línea, y el segundo 350 es la coordenada y del punto final de la línea.
	•	En este caso, la línea termina en el punto (350, 350) en la ventana de visualización.
4.	);:
	•	Cierra la función line().

<img src="https://raw.githubusercontent.com/mauricixx/intro_processing/main/img/dibujar_linea_img.jpg"/>

En resumen, **line(50, 50, 350, 350)**; dibuja una línea que empieza en el punto (50, 50) y termina en el punto (350, 350). Estos puntos se refieren a coordenadas en la ventana de visualización de Processing, donde (0, 0) es la esquina superior izquierda y las coordenadas aumentan hacia la derecha y hacia abajo. La línea resultante es diagonal, yendo de la esquina superior izquierda a la inferior derecha dentro de los límites especificados.

#### Sistema de Coordenadas en Processing.

En Processing, el sistema de coordenadas de la pantalla es diferente al tradicional sistema de coordenadas cartesianas que se usa en matemáticas. Aquí está una explicación del por qué y cómo funciona este sistema en Processing:



##### 1.	Origen en la esquina superior izquierda:
•	En Processing, el punto (0, 0) está ubicado en la esquina superior izquierda de la ventana.
•	Esta convención proviene del diseño de gráficos en computadoras y pantallas, donde las coordenadas de los píxeles se cuentan a partir de la esquina superior izquierda.

##### 2.	Eje X:
•	El eje X aumenta hacia la derecha.
•	Esto es consistente con el sistema de coordenadas cartesianas.

##### 3.	Eje Y:
•	El eje Y aumenta hacia abajo.
•	Esto es opuesto al sistema de coordenadas cartesianas, donde el eje Y positivo va hacia arriba.
•	La razón para esto es histórica y práctica: las pantallas de las computadoras y los sistemas gráficos tempranos se diseñaron de esta manera, ya que es más intuitivo para representar imágenes y textos que se leen de arriba hacia abajo.

##### Razones Históricas y Prácticas

•	Pantallas de Raster:
•	Las pantallas de raster, que se utilizan en la mayoría de los monitores de computadora, escanean de izquierda a derecha y de arriba hacia abajo. Así que fue natural definir el origen en la esquina superior izquierda y hacer que las coordenadas y aumenten hacia abajo.
•	Facilidad de Uso en Gráficos:
•	Cuando se dibujan elementos gráficos y textos, a menudo es más conveniente empezar desde la parte superior de la pantalla e ir bajando, especialmente para interfaces de usuario, textos, y otras representaciones visuales que siguen un flujo de arriba hacia abajo.

##### Ejemplo Visual

##### Imaginemos una ventana de Processing de 100x100 píxeles:

•	El punto (0, 0) está en la esquina superior izquierda.
•	El punto (100, 0) está en la esquina superior derecha.
•	El punto (0, 100) está en la esquina inferior izquierda.
•	El punto (100, 100) está en la esquina inferior derecha.

```js
size(100, 100);
point(0, 0);     // Esquina superior izquierda
point(100, 0);   // Esquina superior derecha
point(0, 100);   // Esquina inferior izquierda
point(100, 100); // Esquina inferior derecha
```

<a href="https://mauricixx.github.io/intro_processing/cartesiano/index.html">Enlace para localizar puntos en un plano cartesiano y generar una línea.</a>

.___________________________________________________________________________________________________________________________________

##### II.	**Colores**:

•	Introducir background(), fill(), stroke() y noFill(), noStroke() para cambiar colores de fondo, relleno y contorno.

```js
void setup() {
  size(400, 400);
  background(255);
}

void draw() {
  fill(255, 0, 0); // Color rojo
  rect(100, 100, 200, 200);

  noFill(); // Sin relleno
  stroke(0, 0, 255); // Contorno azul
  ellipse(200, 200, 100, 100);
}
```

* En Processing, la función **background()** se puede utilizar tanto en void setup() como en void draw(), pero cada ubicación tiene un propósito diferente y afecta el comportamiento de la animación de distintas maneras:

1.	Usar **background()** en **void setup()**:
	•	La función setup() se ejecuta una sola vez al inicio del programa.
	•	Si colocas background() en setup(), se establecerá un color de fondo al inicio y no se actualizará nuevamente durante la ejecución del programa. Esto significa que cualquier dibujo hecho en void draw() se acumulará sobre el fondo inicial, creando un efecto de superposición.

```js
void setup() {
  size(400, 400);
  background(200);  // El fondo se establece una sola vez al inicio
}

void draw() {
  ellipse(mouseX, mouseY, 50, 50);  // Los elipses se dibujan sobre el fondo sin borrarse
}
```

2.	**Usar background() en void draw():**
	•	La función draw() se ejecuta continuamente en un bucle, permitiendo la actualización constante de la pantalla.
	•	Si colocas background() en draw(), se establecerá el color de fondo en cada frame. Esto significa que cada nuevo dibujo en draw() se hará sobre un fondo limpio, creando la apariencia de movimiento y eliminando los dibujos anteriores.

```js
void setup() {
  size(400, 400);
}

void draw() {
  background(200);  // El fondo se actualiza en cada frame
  ellipse(mouseX, mouseY, 50, 50);  // Los elipses se dibujan y se "mueven" con el ratón
}
```

En resumen, usar background() en setup() establece un fondo fijo y todo lo que dibujes en draw() se acumulará sobre ese fondo. Usar background() en draw() actualiza el fondo en cada frame, creando un efecto de movimiento y eliminando los dibujos anteriores. La elección entre uno y otro depende del efecto visual que desees lograr en tu animación.


 ____________________________________________________________________________________________________________________

### <span style="color:green">**Interactividad.**</span>

##### I.	**Uso del Ratón**:

•	Introducir variables predefinidas como mouseX, mouseY.
•	Crear una simple interacción donde una forma sigue al ratón.

```js
void setup() {
  size(400, 400);
}

void draw() {
  background(255);
  ellipse(mouseX, mouseY, 50, 50);
}
```

##### II.	 **Eventos del Ratón**:

•	Explicar mousePressed(), mouseReleased(), mouseDragged(), mouseMoved().
Estas funciones están diseñadas para detectar e interactuar con los eventos del ratón.

###### mousePressed()
```js
void mousePressed() {
  // Código que se ejecuta cuando se presiona un botón del ratón
}
```
1.	void mousePressed() {:
	•	Declara la función mousePressed(). Esta función se llama automáticamente cuando se presiona cualquier botón del ratón.
2.	// Código que se ejecuta cuando se presiona un botón del ratón:
	•	Dentro de esta función, puedes escribir cualquier código que deseas ejecutar cuando el ratón se presiona. Esto podría ser para iniciar una acción, como dibujar un punto o iniciar un arrastre.
3.	}:
	•	Cierra la función mousePressed().

###### mouseReleased()
```js
void mouseReleased() {
  // Código que se ejecuta cuando se libera un botón del ratón
}
```
1.	void mouseReleased() {:
	•	Declara la función mouseReleased(). Esta función se llama automáticamente cuando se libera cualquier botón del ratón.
2.	// Código que se ejecuta cuando se libera un botón del ratón:
	•	Dentro de esta función, puedes escribir cualquier código que deseas ejecutar cuando el ratón se libera. Esto podría ser para detener una acción iniciada por mousePressed(), como dejar de dibujar.
3.	}:
	•	Cierra la función mouseReleased().

###### mouseDragged()
```js
void mouseDragged() {
  // Código que se ejecuta cuando el ratón se mueve mientras se presiona un botón
}
```
1.	void mouseDragged() {:
	•	Declara la función mouseDragged(). Esta función se llama automáticamente cuando el ratón se mueve mientras se mantiene presionado cualquier botón del ratón.
2.	// Código que se ejecuta cuando el ratón se mueve mientras se presiona un botón:
	•	Dentro de esta función, puedes escribir cualquier código que deseas ejecutar mientras arrastras el ratón. Esto se usa comúnmente para dibujar o arrastrar objetos en la pantalla.
3.	}:
	•	Cierra la función mouseDragged().


```js
void mouseDragged() {
  // Código que se ejecuta cuando el ratón se mueve mientras se presiona un botón
}
```
1.	void mouseDragged() {:
	•	Declara la función mouseDragged(). Esta función se llama automáticamente cuando el ratón se mueve mientras se mantiene presionado cualquier botón del ratón.
2.	// Código que se ejecuta cuando el ratón se mueve mientras se presiona un botón:
	•	Dentro de esta función, puedes escribir cualquier código que deseas ejecutar mientras arrastras el ratón. Esto se usa comúnmente para dibujar o arrastrar objetos en la pantalla.
3.	}:
	•	Cierra la función mouseDragged().

###### mouseMoved()
```js
void mouseMoved() {
  // Código que se ejecuta cuando el ratón se mueve sin presionar ningún botón
}
```
1.	void mouseMoved() {:
	•	Declara la función mouseMoved(). Esta función se llama automáticamente cuando el ratón se mueve sin presionar ningún botón.
2.	// Código que se ejecuta cuando el ratón se mueve sin presionar ningún botón:
	•	Dentro de esta función, puedes escribir cualquier código que deseas ejecutar cuando el ratón se mueve libremente. Esto podría ser para actualizar la posición de un cursor o realizar una acción en función de la posición del ratón.
3.	}:
	•	Cierra la función mouseMoved().

###### Ejemplo de uso de estas funciones

Ejemplo completo que utiliza estas funciones para cambiar el color del fondo y dibujar círculos según las acciones del ratón:
```js
void setup() {
  size(400, 400);
  background(255);
}

void draw() {
  // Nada se actualiza continuamente en este ejemplo
}

void mousePressed() {
  fill(0, 0, 255); // Azul
  ellipse(mouseX, mouseY, 50, 50);
}

void mouseReleased() {
  fill(255, 0, 0); // Rojo
  ellipse(mouseX, mouseY, 50, 50);
}

void mouseDragged() {
  fill(0, 255, 0); // Verde
  ellipse(mouseX, mouseY, 50, 50);
}

void mouseMoved() {
  fill(255, 255, 0); // Amarillo
  ellipse(mouseX, mouseY, 50, 50);
}
```
###### En este ejemplo:

•	**mousePressed()** dibuja un círculo azul donde se presiona el ratón.
•	**mouseReleased()** dibuja un círculo rojo donde se libera el ratón.
•	**mouseDragged()** dibuja círculos verdes mientras se arrastra el ratón.
•	**mouseMoved()** dibuja círculos amarillos cuando el ratón se mueve sin presionar ningún botón.


###### Ejemplo de cómo cambiar el color de una forma cuando se presiona el ratón.

```js
boolean isPressed = false;

void setup() {
  size(400, 400);
}

void draw() {
  background(255);
  if (isPressed) {
    fill(0, 255, 0); // Verde
  } else {
    fill(255, 0, 0); // Rojo
  }
  ellipse(mouseX, mouseY, 50, 50);
}

void mousePressed() {
  isPressed = true;
}

void mouseReleased() {
  isPressed = false;
}
```

```js
boolean isPressed = false;
```
1.	boolean:
	•	boolean es un tipo de dato en Java (y Processing) que puede tener uno de dos valores: true o false. Los valores booleanos se utilizan típicamente para representar condiciones o estados que pueden ser verdaderos o falsos.
2.	isPressed:
	•	isPressed es el nombre de la variable que estamos declarando. Este nombre puede ser cualquier identificador válido en Java, pero isPressed es un nombre descriptivo que sugiere que la variable se utilizará para verificar si algo está presionado o no (por ejemplo, una tecla o un botón).
3.	=:
	•	El operador de asignación = se utiliza para asignar un valor a una variable. En este caso, estamos asignando el valor false a la variable isPressed.
4.	false:
	•	false es uno de los dos valores posibles para un tipo de dato booleano. Aquí, indica que inicialmente, la condición representada por isPressed no es verdadera. Es decir, lo que sea que isPressed está representando (por ejemplo, si un botón está presionado), inicialmente no está ocurriendo.
5.	;:
	•	El punto y coma ; se utiliza para terminar la declaración en Java y Processing.

En resumen, boolean isPressed = false; declara una variable booleana llamada isPressed y le asigna el valor inicial false. Esto podría ser utilizado en un programa para rastrear si un botón, una tecla, o alguna otra condición está actualmente activa (presionada) o no. Por ejemplo, más adelante en el código podrías tener algo como:
```js
if (mousePressed) {
  isPressed = true;
} else {
  isPressed = false;
}
```
Esto actualizaría el valor de isPressed según el estado del ratón.



_________________________________________________________________________________________________________________________________________

#### Animación

##### I.	**Concepto de draw()**:

•	Explicar que la función draw() se ejecuta en un bucle continuo.
•	Crear una simple animación.

```js
float x = 0;

void setup() {
  size(400, 400);
}

void draw() {
  background(255);
  ellipse(x, height/2, 50, 50);
  x += 2; // Mover hacia la derecha
  if (x > width) {
    x = 0; // Reiniciar posición
  }
}
```

##### II.	**Variables y Control**:

•	Introducir variables y estructuras de control como if, for, while.

```js
int y = 0;

void setup() {
  size(400, 400);
}

void draw() {
  background(255);
  for (int i = 0; i < width; i += 50) {
    ellipse(i, y, 25, 25);
  }
  y += 2;
  if (y > height) {
    y = 0;
  }
}
```

##### Cambiar Color del fondo en tiempo real.

```js
int sliderX;  // Posición x del slider
int sliderY;  // Posición y del slider
int sliderWidth;  // Ancho del slider
int sliderHeight;  // Altura del slider
int sliderValue;  // Valor del slider (posición de la perilla)

void setup() {
  size(400, 400);
  colorMode(HSB, 360, 100, 100);  // Configura el modo de color a HSB (Hue, Saturation, Brightness)
  
  // Inicializa las dimensiones del slider
  sliderX = 50;
  sliderY = height - 50;
  sliderWidth = 300;
  sliderHeight = 20;
  sliderValue = sliderX;  // El valor inicial del slider coincide con la posición x inicial
}

void draw() {
  // Calcula el color de fondo basado en la posición del slider
  float hue = map(sliderValue, sliderX, sliderX + sliderWidth, 0, 360);
  background(hue, 100, 100);
  
  // Dibuja el slider
  fill(255);
  rect(sliderX, sliderY, sliderWidth, sliderHeight);
  
  // Dibuja la perilla del slider
  fill(0);
  rect(sliderValue, sliderY, 10, sliderHeight);
}

void mouseDragged() {
  // Si el ratón está sobre el slider, actualiza la posición del valor del slider
  if (mouseX >= sliderX && mouseX <= sliderX + sliderWidth && mouseY >= sliderY && mouseY <= sliderY + sliderHeight) {
    sliderValue = mouseX;
  }
}
```


#### Guardar una imagen en Processing.

Para capturar y guardar una imagen en Processing, puedes usar la función save() o saveFrame() dependiendo de tus necesidades. Aquí te explico cómo utilizarlas:

##### 1. Guardar una Imagen en un Momento Específico

Si quieres guardar una imagen en un momento específico (por ejemplo, cuando se presiona una tecla), puedes usar la función save(). Este método guarda la pantalla actual como un archivo de imagen.

```js
void setup() {
  size(400, 400);
}

void draw() {
  background(255);
  ellipse(mouseX, mouseY, 50, 50);
}

void keyPressed() {
  if (key == 's' || key == 'S') { // Presiona 'S' para guardar la imagen
    save("imagen_guardada.png");
  }
}
```

```js
void setup() {
  size(400, 400);
}

void draw() {
  background(255);
  ellipse(mouseX, mouseY, 50, 50);

  // Guarda cada cuadro como una imagen numerada
  //saveFrame("output/imagen-####.png");
}

void keyPressed() {
  if (key == 's' || key == 'S') { // Presiona 'S' para guardar la imagen
    save("output/imagen_1.png");
  }
}
```


##### 2. Guardar una Secuencia de Imágenes

Si deseas capturar y guardar una secuencia de imágenes (por ejemplo, para crear una animación), puedes usar saveFrame(). Esta función guarda automáticamente una secuencia de imágenes numeradas.

```js
void setup() {
  size(400, 400);
}

void draw() {
  background(255);
  ellipse(mouseX, mouseY, 50, 50);

  // Guarda cada cuadro como una imagen numerada
  saveFrame("output/imagen-####.png");
}
```

##### En este caso, #### se reemplaza por el número del fotograma (por ejemplo, imagen-0001.png, imagen-0002.png, etc.).

Notas:

•	Asegúrate de que la carpeta donde se guardarán las imágenes (output/ en el ejemplo) exista. De lo contrario, Processing la creará automáticamente.
•	Los archivos de imagen se guardan en el mismo directorio donde se encuentra el sketch de Processing.



##### Capturar un video en Processing.

Guardar un video directamente desde Processing no es tan directo como guardar imágenes. Processing no tiene una función incorporada para exportar video, pero puedes usar la biblioteca Video Export para lograrlo. Aquí te muestro cómo hacerlo:

##### I. Instalación de la Biblioteca Video Export en Processing 3

1.	Abre Processing.
2.	Ve a Sketch > Import Library > Add Library….
3.	Busca Video Export y haz clic en Install.

II. Código para Guardar un Video

Una vez que hayas instalado la biblioteca, puedes usar el siguiente código para capturar y guardar un video:
```js
import com.hamoid.*;

VideoExport videoExport;

void setup() {
  size(640, 480);
  videoExport = new VideoExport(this, "output_video.mp4"); // Nombre del archivo de video
  videoExport.startMovie(); // Inicia la grabación del video
}

void draw() {
  background(255);
  ellipse(mouseX, mouseY, 50, 50);

  videoExport.saveFrame(); // Guarda cada cuadro en el video
}

void keyPressed() {
  if (key == 'q' || key == 'Q') {
    videoExport.endMovie(); // Finaliza la grabación del video al presionar 'Q'
    exit(); // Cierra el programa
  }
}
```

III. Explicación del Código

•	VideoExport videoExport;: Declara una variable para manejar la exportación de video.
•	videoExport = new VideoExport(this, "output_video.mp4");: Inicializa la exportación de video con el nombre del archivo donde se guardará.
•	videoExport.startMovie();: Comienza la grabación del video.
•	videoExport.saveFrame();: Guarda el cuadro actual en el video. Esta función debe ser llamada dentro de draw() para capturar cada fotograma.
•	videoExport.endMovie();: Termina la grabación del video y guarda el archivo. Puedes asociar esta función a una tecla, como se muestra en el ejemplo, para detener la grabación cuando lo desees.

IV. Notas Importantes

•	El video se guardará en la misma carpeta que contiene tu sketch de Processing.
•	Asegúrate de no omitir videoExport.endMovie();, ya que es necesario para finalizar y guardar el video correctamente.
•	Si tu sketch es largo o tiene un alto número de cuadros por segundo (fps), el archivo de video podría ser grande. Ajusta la calidad y duración según tus necesidades.

****

##### Guardar un video en Processing 4.	
Si estás usando Processing 4, la forma más confiable de guardar un video es exportando los cuadros como imágenes (saveFrame()) y luego unirlos en un video con una herramienta externa como FFmpeg.

##### V. Código en Processing 4 para guardar cuadros por segundos.	
```js
void setup() {
  size(640, 480);
  frameRate(30);  // 30 fps
}

void draw() {
  background(0);
  fill(255);
  ellipse(frameCount % width, height/2, 50, 50);

  // Guardar hasta 300 cuadros (10 segundos a 30fps)
  if (frameCount <= 300) {
    saveFrame("output/frame-####.png");
  }
}
```
Esto creará una carpeta output con 300 imágenes nombradas como frame-0001.png, frame-0002.png, etc.

##### II. Convertir imágenes en video usando FFmpeg.
```bash
ffmpeg -framerate 30 -i frame-%04d.png -c:v libx264 -pix_fmt yuv420p mi_video.mp4

```
	•	-framerate 30: tasa de cuadros (igual que frameRate() en tu sketch)
	•	-i output/frame-%04d.png: indica el patrón de nombres
	•	mi_video.mp4: nombre del archivo final

💡 Puedes cambiar mi_video.mp4 por video.mov si prefieres formato para Mac.

##### ¿No tienes FFmpeg?
Descarga [aquí](https://ffmpeg.org/download.html)
O en Mac puedes usar Homebrew:
 
 ```bash
 brew install ffmpeg
```

🎁 ##### BONUS: Eliminar imágenes después de crear el video.
Si quieres borrar las imágenes automáticamente después de crear el video:
 ```bash
rm output/*.png
```
(En Windows: del output\*.png)

##### creación de perilla (PROCESSING)
```js
float angle = 0; // Knob angle
float radius = 50; // Radius of the knob
float centerX, centerY; // Center of the knob
boolean dragging = false; // Is the knob being dragged?

void setup() {
  size(400, 400);
  centerX = width / 2;
  centerY = height / 2;
}

void draw() {
  background(255);
  
  // Draw the knob
  fill(200);
  ellipse(centerX, centerY, radius * 2, radius * 2);
  
  // Draw the knob pointer
  float knobX = centerX + cos(angle) * radius;
  float knobY = centerY + sin(angle) * radius;
  stroke(0);
  strokeWeight(4);
  line(centerX, centerY, knobX, knobY);
  
  // Detect dragging
  if (dragging) {
    float dx = mouseX - centerX;
    float dy = mouseY - centerY;
    angle = atan2(dy, dx); // Update angle based on mouse position
  }
  
  // Display the angle value
  fill(0);
  textSize(16);
  text("Angle: " + degrees(angle), 10, height - 20);
}

void mousePressed() {
  float dx = mouseX - centerX;
  float dy = mouseY - centerY;
  if (sqrt(dx*dx + dy*dy) < radius) { // Check if the mouse is within the knob's radius
    dragging = true;
  }
}

void mouseReleased() {
  dragging = false;
}
```
#### creación de perilla (P5js):
##### Para realizar tu primer ejercicio en p5.js, sigue estos pasos básicos:
- Ve al editor web de [p5.js:](https://editor.p5js.org)
- Crea una cuenta o inicia sesión (opcional, pero útil para guardar proyectos).
- Verás un código base con setup() y draw(). (Puedes borrarlo o comenzar a editar sobre el mismo)
- Copia y pega el siguiente ejercicio en la consla de P5js.

  
```js
let angle = 0; // Ángulo del knob
let radius = 50; // Radio del knob
let centerX, centerY; // Centro del knob
let dragging = false; // ¿Se está arrastrando el knob?

function setup() {
  createCanvas(400, 400);
  centerX = width / 2;
  centerY = height / 2;
}

function draw() {
  background(255);
  
  // Dibujar el knob
  fill(200);
  ellipse(centerX, centerY, radius * 2, radius * 2);
  
  // Dibujar el indicador del knob
  let knobX = centerX + cos(angle) * radius;
  let knobY = centerY + sin(angle) * radius;
  stroke(0);
  strokeWeight(4);
  line(centerX, centerY, knobX, knobY);
  
  // Detectar si se está arrastrando
  if (dragging) {
    let dx = mouseX - centerX;
    let dy = mouseY - centerY;
    angle = atan2(dy, dx); // Actualizar el ángulo basado en la posición del mouse
  }
  
  // Mostrar el valor del ángulo
  fill(0);
  textSize(16);
  text("Angle: " + degrees(angle).toFixed(2), 10, height - 20);
}

function mousePressed() {
  let dx = mouseX - centerX;
  let dy = mouseY - centerY;
  if (sqrt(dx * dx + dy * dy) < radius) { // Verificar si el mouse está dentro del radio del knob
    dragging = true;
  }
}

function mouseReleased() {
  dragging = false;
}
```

##### Movimiento cubo + perilla (PROCESSING):

```js
int knobX = 100;  // Posición de la perilla.
int knobY = 100;
int knobRadius = 50;
float angle = 0;  // ángulo inicial de la perilla
boolean dragging = false;

float cubeX = 300;  // Posición inicial del cubo
float cubeY = 200;

void setup() {
  size(600, 400, P3D);
}

void draw() {
  background(255);
  
  // Dibujar la perilla (knob)
  pushMatrix();
  translate(knobX, knobY);
  stroke(0);
  fill(200);
  ellipse(0, 0, knobRadius * 2, knobRadius * 2);
  
  // Dibuja el indicador de la perilla
  float indicatorX = cos(angle) * knobRadius;
  float indicatorY = sin(angle) * knobRadius;
  stroke(0);
  line(0, 0, indicatorX, indicatorY);
  popMatrix();
  
  // Actualiza la posición del cubo basada en el ángulo de la perilla.
  cubeX = map(angle, -PI, PI, 50, width - 50);
  
  // Dibuja el cubo
  pushMatrix();
  translate(cubeX, cubeY);
  rotateY(angle);
  fill(150, 100, 250);
  box(50);
  popMatrix();
}

void mousePressed() {
  // Chequea si el mouse esta presionado en la perilla
  if (dist(mouseX, mouseY, knobX, knobY) < knobRadius) {
    dragging = true;
  }
}

void mouseDragged() {
  if (dragging) {
    // Calcula el angulo basado en la posición del mouse
    float dx = mouseX - knobX;
    float dy = mouseY - knobY;
    angle = atan2(dy, dx);
  }
}

void mouseReleased() {
  dragging = false;
}
```
##### Movimiento cubo + perilla (P5js):
```js
let knobX = 100;  // Posición de la perilla.
let knobY = 100;
let knobRadius = 50;
let angle = 0;  // Ángulo inicial de la perilla
let dragging = false;

let cubeX = 300;  // Posición inicial del cubo
let cubeY = 200;

function setup() {
  createCanvas(600, 400, WEBGL);
}

function draw() {
  background(255);
  
  // Dibujar la perilla (knob)
  push();
  translate(knobX - width / 2, knobY - height / 2);  // Ajuste para coordenadas WEBGL
  stroke(0);
  fill(200);
  ellipse(0, 0, knobRadius * 2, knobRadius * 2);
  
  // Dibujar el indicador de la perilla
  let indicatorX = cos(angle) * knobRadius;
  let indicatorY = sin(angle) * knobRadius;
  stroke(0);
  line(0, 0, indicatorX, indicatorY);
  pop();
  
  // Actualizar la posición del cubo basada en el ángulo de la perilla
  cubeX = map(angle, -PI, PI, 50, width - 50);
  
  // Dibujar el cubo
  push();
  translate(cubeX - width / 2, cubeY - height / 2);
  rotateY(angle);
  fill(150, 100, 250);
  box(50);
  pop();
}

function mousePressed() {
  // Chequear si el mouse está presionado en la perilla
  if (dist(mouseX, mouseY, knobX, knobY) < knobRadius) {
    dragging = true;
  }
}

function mouseDragged() {
  if (dragging) {
    // Calcular el ángulo basado en la posición del mouse
    let dx = mouseX - knobX;
    let dy = mouseY - knobY;
    angle = atan2(dy, dx);
  }
}

function mouseReleased() {
  dragging = false;
}
```


#### Movimiento 1 cubo con  3 perillas. (PROCESSING)
```js
int knobX1 = 100, knobY1 = 100;  // Posición del primer knob
int knobX2 = 100, knobY2 = 200;  // Posición del segundo knob
int knobX3 = 100, knobY3 = 300;  // Posición del tercer knob
int knobRadius = 50;  // Radio de los knobs

float angle1 = 0, angle2 = 0, angle3 = 0;  // Ángulos para los knobs
boolean dragging1 = false, dragging2 = false, dragging3 = false;  // Para detectar si se está arrastrando un knob

float cubeX = 300, cubeY = 200, cubeZ = -200;  // Posición inicial del cubo

void setup() {
  size(600, 400, P3D);  // Tamaño del lienzo en 3D
}

void draw() {
  background(255);  // Fondo blanco
  
  // Dibujar el primer knob
  drawKnob(knobX1, knobY1, angle1);
  // Dibujar el segundo knob
  drawKnob(knobX2, knobY2, angle2);
  // Dibujar el tercer knob
  drawKnob(knobX3, knobY3, angle3);
  
  // Actualizar la posición del cubo según los ángulos de los knobs
  cubeX = map(angle1, -PI, PI, 50, width - 50);  // Mueve el cubo en el eje X
  cubeY = map(angle2, -PI, PI, 50, height - 50);  // Mueve el cubo en el eje Y
  cubeZ = map(angle3, -PI, PI, -300, 300);  // Mueve el cubo en el eje Z
  
  // Dibujar el cubo
  pushMatrix();
  translate(cubeX, cubeY, cubeZ);
  rotateY(angle1);  // Rotación del cubo en el eje Y
  rotateX(angle2);  // Rotación del cubo en el eje X
  rotateZ(angle3);  // Rotación del cubo en el eje Z
  fill(150, 100, 250);  // Color del cubo
  box(50);  // Tamaño del cubo
  popMatrix();
}

void drawKnob(int x, int y, float angle) {
  // Función para dibujar cada knob
  pushMatrix();
  translate(x, y);
  stroke(0);
  fill(200);
  ellipse(0, 0, knobRadius * 2, knobRadius * 2);  // Dibuja el círculo del knob
  
  // Dibuja el indicador del knob
  float indicatorX = cos(angle) * knobRadius;
  float indicatorY = sin(angle) * knobRadius;
  stroke(0);
  line(0, 0, indicatorX, indicatorY);  // Línea que muestra el ángulo del knob
  popMatrix();
}

void mousePressed() {
  // Detectar si el mouse presiona el primer knob
  if (dist(mouseX, mouseY, knobX1, knobY1) < knobRadius) {
    dragging1 = true;
  }
  // Detectar si el mouse presiona el segundo knob
  if (dist(mouseX, mouseY, knobX2, knobY2) < knobRadius) {
    dragging2 = true;
  }
  // Detectar si el mouse presiona el tercer knob
  if (dist(mouseX, mouseY, knobX3, knobY3) < knobRadius) {
    dragging3 = true;
  }
}

void mouseDragged() {
  // Ajustar el ángulo del primer knob mientras se arrastra
  if (dragging1) {
    float dx = mouseX - knobX1;
    float dy = mouseY - knobY1;
    angle1 = atan2(dy, dx);
  }
  // Ajustar el ángulo del segundo knob mientras se arrastra
  if (dragging2) {
    float dx = mouseX - knobX2;
    float dy = mouseY - knobY2;
    angle2 = atan2(dy, dx);
  }
  // Ajustar el ángulo del tercer knob mientras se arrastra
  if (dragging3) {
    float dx = mouseX - knobX3;
    float dy = mouseY - knobY3;
    angle3 = atan2(dy, dx);
  }
}

void mouseReleased() {
  // Dejar de arrastrar los knobs
  dragging1 = false;
  dragging2 = false;
  dragging3 = false;
}
```

#### Movimiento 1 cubo con  3 perillas. (P5JS)
```js
let knobX1 = 100, knobY1 = 100;  // Posición del primer knob
let knobX2 = 100, knobY2 = 200;  // Posición del segundo knob
let knobX3 = 100, knobY3 = 300;  // Posición del tercer knob
let knobRadius = 50;  // Radio de los knobs

let angle1 = 0, angle2 = 0, angle3 = 0;  // Ángulos para los knobs
let dragging1 = false, dragging2 = false, dragging3 = false;  // Para detectar si se está arrastrando un knob

let cubeX = 300, cubeY = 200, cubeZ = -200;  // Posición inicial del cubo

function setup() {
  createCanvas(600, 400, WEBGL);  // Tamaño del lienzo en 3D
}

function draw() {
  background(255);  // Fondo blanco
  
  // Dibujar el primer knob
  drawKnob(knobX1, knobY1, angle1);
  // Dibujar el segundo knob
  drawKnob(knobX2, knobY2, angle2);
  // Dibujar el tercer knob
  drawKnob(knobX3, knobY3, angle3);
  
  // Actualizar la posición del cubo según los ángulos de los knobs
  cubeX = map(angle1, -PI, PI, 50, width - 50);  // Mueve el cubo en el eje X
  cubeY = map(angle2, -PI, PI, 50, height - 50);  // Mueve el cubo en el eje Y
  cubeZ = map(angle3, -PI, PI, -300, 300);  // Mueve el cubo en el eje Z
  
  // Dibujar el cubo
  push();
  translate(cubeX - width/2, cubeY - height/2, cubeZ);
  rotateY(angle1);  // Rotación del cubo en el eje Y
  rotateX(angle2);  // Rotación del cubo en el eje X
  rotateZ(angle3);  // Rotación del cubo en el eje Z
  fill(150, 100, 250);  // Color del cubo
  box(50);  // Tamaño del cubo
  pop();
}

function drawKnob(x, y, angle) {
  // Función para dibujar cada knob
  push();
  translate(x - width/2, y - height/2);  // Ajuste para sistema de coordenadas WEBGL
  stroke(0);
  fill(200);
  ellipse(0, 0, knobRadius * 2, knobRadius * 2);  // Dibuja el círculo del knob
  
  // Dibuja el indicador del knob
  let indicatorX = cos(angle) * knobRadius;
  let indicatorY = sin(angle) * knobRadius;
  stroke(0);
  line(0, 0, indicatorX, indicatorY);  // Línea que muestra el ángulo del knob
  pop();
}

function mousePressed() {
  // Detectar si el mouse presiona el primer knob
  if (dist(mouseX, mouseY, knobX1, knobY1) < knobRadius) {
    dragging1 = true;
  }
  // Detectar si el mouse presiona el segundo knob
  if (dist(mouseX, mouseY, knobX2, knobY2) < knobRadius) {
    dragging2 = true;
  }
  // Detectar si el mouse presiona el tercer knob
  if (dist(mouseX, mouseY, knobX3, knobY3) < knobRadius) {
    dragging3 = true;
  }
}

function mouseDragged() {
  // Ajustar el ángulo del primer knob mientras se arrastra
  if (dragging1) {
    let dx = mouseX - knobX1;
    let dy = mouseY - knobY1;
    angle1 = atan2(dy, dx);
  }
  // Ajustar el ángulo del segundo knob mientras se arrastra
  if (dragging2) {
    let dx = mouseX - knobX2;
    let dy = mouseY - knobY2;
    angle2 = atan2(dy, dx);
  }
  // Ajustar el ángulo del tercer knob mientras se arrastra
  if (dragging3) {
    let dx = mouseX - knobX3;
    let dy = mouseY - knobY3;
    angle3 = atan2(dy, dx);
  }
}

function mouseReleased() {
  // Dejar de arrastrar los knobs
  dragging1 = false;
  dragging2 = false;
  dragging3 = false;
}
```

### INTERFAZ-II

#### ARDUINO

#### Hola Mundo

```js
void setup() {
  Serial.begin(9600); // Inicia la comunicación serie a 9600 bps
  Serial.println("Hola, Mundo!"); // Envía "Hola, Mundo!" al monitor serial
}

void loop() {
  // No es necesario poner nada en el loop para este ejemplo
}
```

```js
unsigned int ADCValue;
void setup(){
    Serial.begin(9600);
}

void loop(){

 int val = analogRead(0);
   val = map(val, 0, 300, 0, 255);
    Serial.println(val);
delay(50);
}
```
#### Qué son los Baudios:
En Arduino, los baudios (o baud rate) son la velocidad de transmisión de datos en una comunicación serial, medida en bits por segundo (bps).

Por ejemplo, cuando escribes en el código:
```js
Serial.begin(9600);
```
Eso significa que el Arduino y el dispositivo con el que se comunica (por ejemplo, tu computador a través del monitor serial) intercambian información a 9600 bits por segundo.
#### Puntos clave sobre los baudios en Arduino:
	•	Baudios ≈ bits por segundo (aunque técnicamente, 1 baudio es 1 cambio de señal por segundo, que normalmente equivale a 1 bit en comunicaciones seriales simples).
	•	El valor debe coincidir en ambos extremos de la comunicación (Arduino y computador), si no, los datos se verán corruptos.
	•	Valores comunes: 300, 1200, 2400, 4800, 9600, 19200, 57600, 115200 baudios.
	•	Si se usa un valor muy alto y el cable o conexión no es buena, puede haber errores en la transmisión.

El símbolo ≈ significa “aproximadamente igual a”.

Se usa cuando dos valores no son exactamente iguales, pero son muy parecidos o equivalentes en la práctica.

En el caso de los baudios, puse:

Baudios ≈ bits por segundo

Porque, en la mayoría de las comunicaciones seriales simples, un baudio corresponde a un bit por segundo, pero técnicamente no siempre es exacto: en protocolos más complejos, un baudio puede representar más de un bit (o menos, dependiendo del esquema de codificación).

Es como decir: “No son exactamente lo mismo, pero para la mayoría de los casos prácticos en Arduino, podemos tratarlos como iguales.”

#### LED Intermitente (Blink)

```js
void setup() {  // Configuración inicial (ej: pines como entrada/salida)
  pinMode(13, OUTPUT);  // Pin 13 como salida
}

void loop() {   // Se repite infinitamente
  digitalWrite(13, HIGH);  // Encender LED
  delay(1000);             // Esperar 1 segundo
  digitalWrite(13, LOW);   // Apagar LED
  delay(1000);             // Esperar 1 segundo
}
```

####  Control por Pulsador
Objetivo: Encender un LED solo al presionar un botón.
Circuito:
Pulsador en pin 2 (con resistencia pull-down de 10k Ω).
LED en pin 13.
```js
void setup() {
  pinMode(2, INPUT);  // Botón como entrada
  pinMode(13, OUTPUT);
}
void loop() {
  if (digitalRead(2) == HIGH) {  // Si se presiona el botón
    digitalWrite(13, HIGH);
  } else {
    digitalWrite(13, LOW);
  }
}
```

#### LED con Potenciómetro 
Objetivo: Regular brillo de un LED con un potenciómetro.
Circuito:
Potenciómetro: Patas extremas a +5V y GND, central a pin A0.
LED en pin 9 (con resistencia 220 Ω).
```js
void setup() {
  pinMode(9, OUTPUT);  // Pin PWM (símbolo ~)
}
void loop() {
  int valor = analogRead(A0);           // Leer potenciómetro (0-1023)
  int brillo = map(valor, 0, 1023, 0, 255);  // Convertir a rango PWM
  analogWrite(9, brillo);               // Ajustar brillo
}
```


#### Semáforo

```js
// C++ code - Semáforo Autos y Peatones

// Definición de pines
int LED_1 = 6;  // Luz roja autos
int LED_2 = 7;  // Luz amarilla autos
int LED_3 = 8;  // Luz verde autos
int LED_4 = 9;  // Luz verde peatones
int LED_5 = 10; // Luz roja peatones

void setup() {
  // Configuramos todos los pines como salida
  pinMode(LED_1, OUTPUT);
  pinMode(LED_2, OUTPUT);
  pinMode(LED_3, OUTPUT);
  pinMode(LED_4, OUTPUT);
  pinMode(LED_5, OUTPUT);
}

void loop() {
  // 🚦 Fase 1: Autos en verde, peatones en rojo
  digitalWrite(LED_1, LOW);   // Rojo autos apagado
  digitalWrite(LED_2, LOW);   // Amarillo autos apagado
  digitalWrite(LED_3, HIGH);  // Verde autos encendido
  digitalWrite(LED_4, LOW);   // Verde peatones apagado
  digitalWrite(LED_5, HIGH);  // Rojo peatones encendido
  delay(5000); // 5 segundos

  // 🚦 Fase 2: Amarillo autos, peatones siguen en rojo
  digitalWrite(LED_3, LOW);   // Verde autos apagado
  digitalWrite(LED_2, HIGH);  // Amarillo autos encendido
  delay(2000); // 2 segundos
  digitalWrite(LED_2, LOW);   // Amarillo autos apagado

  // 🚦 Fase 3: Rojo autos, verde peatones
  digitalWrite(LED_1, HIGH);  // Rojo autos encendido
  digitalWrite(LED_5, LOW);   // Rojo peatones apagado
  digitalWrite(LED_4, HIGH);  // Verde peatones encendido
  delay(5000); // 5 segundos

  // 🚦 Fase 4: Rojo autos, rojo peatones (tiempo intermedio)
  digitalWrite(LED_4, LOW);   // Verde peatones apagado
  digitalWrite(LED_5, HIGH);  // Rojo peatones encendido
  delay(2000); // 2 segundos
}
```
##### Resistencias para  proyecto Semáforo:
##### Para los LEDs Rojos (LED_1 y LED_5):
Usando un voltaje promedio de 2V para el LED rojo.
Resistencia = (5V - 2V) / 0.02A = 3V / 0.02A = 150 Ω

##### Para el LED Amarillo (LED_2):
Usando un voltaje promedio de 2.2V para el LED amarillo.
Resistencia = (5V - 2.2V) / 0.02A = 2.8V / 0.02A = 140 Ω

##### Para el LED Verde (LED_3 y LED_4):
Usando un voltaje promedio de 2.4V para el LED verde.
Resistencia = (5V - 2.4V) / 0.02A = 2.6V / 0.02A = 130 Ω

-----------------------------------------------------------------

#### Elipse Interactivo: controlar un circulo en Processing mediante un potenciometro conectado a un Arduino UNO.
###### Código de Arduino:

```js
unsigned int ADCValue;
void setup(){
    Serial.begin(9600);
}

void loop(){

 int val = analogRead(0);
   val = map(val, 0, 300, 0, 255);
    Serial.println(val);
delay(50);
}
```
#####Led +  potenciometro + processing

```js
unsigned int ADCValue;
void setup() {
  Serial.begin(9600);
  pinMode(9, OUTPUT);  // Pin PWM (símbolo ~)
}
void loop() {
  int val = analogRead(A0);           // Leer potenciómetro (0-1023)
  int brillo = map(val, 0, 1023, 0, 255);  // Convertir a rango PWM
  analogWrite(9, brillo);               // Ajustar brillo
      Serial.println(val);
delay(50);
}
```

##### Código de Processing:

```js
import processing.serial.*;

Serial myPort;  // Crear objeto de la clase Serial
static String val;    // Datos recibidos desde el puerto serial
int sensorVal = 0;

void setup()
{
  background(0); 
  //fullScreen(P3D);
   size(1080, 720);
   noStroke();
  noFill();
  String portName = "COM3";// Cambia el número (en este caso) para que coincida con el puerto correspondiente conectado a tu Arduino. 

  //myPort = new Serial(this, "/dev/cu.usbmodem1101", 9600);
  myPort = new Serial(this, Serial.list()[0], 9600);

}

void draw()
{
  if ( myPort.available() > 0) {  // Si hay datos disponibles,
  val = myPort.readStringUntil('\n'); 
  try {
   sensorVal = Integer.valueOf(val.trim());
  }
  catch(Exception e) {
  ;
  }
  println(sensorVal); // léelos y guárdalos en vals!
  }  
 //background(0);
  // Escala el valor de mouseX de 0 a 640 a un rango entre 0 y 175
  float c = map(sensorVal, 0, width, 0, 400);
  // Escala el valor de mouseX de 0 a 640 a un rango entre 40 y 300
  float d = map(sensorVal, 0, width, 40,500);
  fill(255, c, 0);
  ellipse(width/2, height/2, d, d);   
}
```

#### Arduino + Botón + Processing
#### código Arduino:
```js
int buttonPin = 2;  // Pin del botón
int buttonState = 0;

void setup() {
  pinMode(buttonPin, INPUT_PULLUP); // Botón con resistencia interna
  Serial.begin(9600);
}

void loop() {
  buttonState = digitalRead(buttonPin);

  if (buttonState == HIGH) {   // Botón presionado
    Serial.println(1);        // Enviar un "1" a Processing
    delay(200);               // Evitar rebotes
  }
}
```
##### código Processing:
```js
import processing.serial.*;

Serial myPort;
ArrayList<PVector> circles; 

void setup() {
  size(1920, 1080);
  background(0);
  
  // Ajusta el nombre del puerto según tu Arduino
  println(Serial.list());
  myPort = new Serial(this, "/dev/cu.usbmodem1101", 9600);
  //myPort = new Serial(this, Serial.list()[0], 9600);
  
  circles = new ArrayList<PVector>();
}

void draw() {
  //background(0);
  
  // Dibujar círculos almacenados
  fill(0, 0, 0);
  //noStroke();
  stroke(255, 0, 0);
  for (PVector c : circles) {
    ellipse(c.x, c.y, 30, 30);
  }
  
  // Revisar si llega algo de Arduino
  if (myPort.available() > 0) {
    String val = myPort.readStringUntil('\n');
    if (val != null) {
      val = trim(val);
      if (val.equals("1")) {
        // Cada vez que se aprieta el botón, agregar un círculo en posición aleatoria
        circles.add(new PVector(random(width), random(height)));
      }
    }
  }
}
```
### Arduino + botón + potenciometro + Processing
#### código Arduino:
```js
int buttonPin = 2;       // Pin del botón
int potPin = A0;         // Pin del potenciómetro
int buttonState = 0;

void setup() {
  pinMode(buttonPin, INPUT_PULLUP); // Botón con resistencia interna
  Serial.begin(9600);
}

void loop() {
  buttonState = digitalRead(buttonPin);

  if (buttonState == HIGH) {   // Botón presionado
    int potValue = analogRead(potPin);   // 0 - 1023
    Serial.print("BTN,");     // etiqueta para Processing
    Serial.println(potValue); // mando el valor junto con el evento
    delay(200);               // debounce simple
  }
}
```

#### código Processing:
```js
import processing.serial.*;

Serial myPort;
ArrayList<CircleData> circles; 

void setup() {
  size(1200, 720);
  background(0);
  
  // Ajusta el puerto según tu Arduino
  println(Serial.list());
  myPort = new Serial(this, "/dev/cu.usbmodem1101", 9600);
  //myPort = new Serial(this, Serial.list()[0], 9600);
  
  circles = new ArrayList<CircleData>();
}

void draw() {
  //background(0);
  
  // Dibujar todos los círculos guardados
  //fill(0, 150, 255);
  //noStroke();
  fill(0, 0, 0);
  stroke(255, 0, 0);
  for (CircleData c : circles) {
    ellipse(c.x, c.y, c.size, c.size);
  }
  
  // Leer datos de Arduino
  if (myPort.available() > 0) {
    String val = myPort.readStringUntil('\n');
    if (val != null) {
      val = trim(val);
      if (val.startsWith("BTN")) {
        // Extraer el valor del potenciómetro
        String[] parts = split(val, ',');
        if (parts.length == 2) {
          float potVal = float(parts[1]);
          float circleSize = map(potVal, 0, 1023, 10, 100); // tamaño 10-100 px
          circles.add(new CircleData(random(width), random(height), circleSize));
        }
      }
    }
  }
}

// Clase para guardar datos de cada círculo
class CircleData {
  float x, y, size;
  CircleData(float x, float y, float size) {
    this.x = x;
    this.y = y;
    this.size = size;
  }
}
```

### Estructuras de control en Arduino:
Es el conjunto de herramientas del lenguaje de programación que permiten organizar la lógica de un programa, ya sea repitiendo instrucciones (ciclos) o tomando decisiones (condicionales), con el fin de controlar dispositivos electrónicos de manera eficiente y adaptable.
En Arduino (C/C++) se usan estructuras de control como for, if, else if y else para repetir instrucciones y tomar decisiones. 

##### 1. For
Sirve para repetir un bloque de código un número determinado de veces.
##### Estructura:
```js
for (inicialización; condición; incremento) {
  // código que se repite
}
```
##### Ejemplo:
```js
for (int i = 0; i < 5; i++) {
  Serial.println(i);  // imprime 0,1,2,3,4
}
```
	•	int i = 0; → la variable empieza en 0
	•	i < 5; → se repite mientras i sea menor a 5
	•	i++ → aumenta de 1 en cada vuelta

##### A. se ejecuta una vez al iniciar la placa y se define en el setup():
 ```js
void setup() {
  Serial.begin(9600);   // Inicia la comunicación serial

  for (int i = 0; i < 5; i++) {
    Serial.println(i);  // imprime 0,1,2,3,4
  }
}

void loop() {
  // vacío porque no necesitamos repetir
}
```
##### B. Se ejecua cada vez en bucle y se define en el loop():
```js
void setup() {
  Serial.begin(9600);   // Inicia la comunicación serial
}

void loop() {
  for (int i = 0; i < 5; i++) {
    Serial.println(i);  // imprime 0,1,2,3,4
    delay(500);         // medio segundo entre cada número
  }
}
```

##### 2. if, else if, else:
Se usan para tomar decisiones.

##### Estructura:
```js
if (condición1) {
  // si condición1 es verdadera
} else if (condición2) {
  // si condición1 es falsa, pero condición2 es verdadera
} else {
  // si ninguna condición es verdadera
}
```
##### Ejemplo con un sensor:
```js
int valor = analogRead(A0);

if (valor < 200) {
  Serial.println("Muy bajo");
} else if (valor < 500) {
  Serial.println("Medio");
} else {
  Serial.println("Alto");
}
```
##### código completo:
```js
int valor;  // aquí guardaremos la lectura del sensor

void setup() {
  Serial.begin(9600);   // Inicia la comunicación serial
}

void loop() {
  valor = analogRead(A0);   // lee el pin analógico A0

  if (valor < 200) {
    Serial.println("Muy bajo");
  } else if (valor < 500) {
    Serial.println("Medio");
  } else {
    Serial.println("Alto");
  }

  delay(500); // medio segundo entre lecturas
}
```
##### Donde va cada cosa:
	•	setup() → se ejecuta una sola vez al iniciar la placa. Aquí ponemos Serial.begin(9600); para abrir la comunicación con el PC.
	•	loop() → se ejecuta infinitamente. Aquí ponemos el analogRead() y el if/else if/else.

 Este ejemplo lo puedes probar aunque no tengas sensor:
si en lugar de analogRead(A0) escribes un número (por ejemplo valor = 350;), vas a ver cómo cambia lo que imprime el if/else.


##### 3. Combinar for con if/else
Puedes usar ambas estructuras juntas. Por ejemplo, encender LEDs de forma secuencial con condiciones:
```js
int leds[] = {2, 3, 4, 5}; // Creamos un arreglo con los pines donde van conectados los LEDs

void setup() {
  // Esta función corre solo una vez al iniciar Arduino
  for (int i = 0; i < 4; i++) {         // Recorre el arreglo desde i = 0 hasta i = 3
    pinMode(leds[i], OUTPUT);           // Configura cada pin del arreglo como salida (para controlar LEDs)
  }
}

void loop() {
  // Esta función corre en bucle infinito
  for (int i = 0; i < 4; i++) {         // Recorre los 4 LEDs, uno por uno
    if (i % 2 == 0) {                   // Si el índice es par (0, 2)...
      digitalWrite(leds[i], HIGH);      // Enciende el LED correspondiente
    } else {                            // Si el índice es impar (1, 3)...
      digitalWrite(leds[i], LOW);       // Apaga el LED correspondiente
    }
    delay(500);                         // Espera 0,5 segundos antes de pasar al siguiente
  }
}
```

##### Resumen de lo que hace el código
	1.	Define 4 LEDs conectados a los pines 2, 3, 4 y 5.
	2.	En setup() configura esos pines como salidas.
	3.	En loop(), recorre los LEDs uno por uno con for.
	•	Si la posición es par → enciende el LED.
	•	Si la posición es impar → apaga el LED.
	4.	Espera 0,5 segundos y sigue al siguiente LED.
	5.	Al terminar, vuelve a empezar infinitamente.

##### ¿Qué hace el módulo %?
Devuelve el resto de una división entera.
Es decir, divide dos números y se queda con lo que sobra.

##### Ejemplo:
```js
	0 % 2 = 0 → par → LED encendido
	1 % 2 = 1 → impar → LED apagado
	2 % 2 = 0 → par → LED encendido
	3 % 2 = 1 → impar → LED apagado

```
###### ¿Cómo se usa en el código?:
esta linea:
```js
if (i % 2 == 0) {
```
	•	Aquí se pregunta si el resto de dividir i entre 2 es igual a 0.
	•	Eso significa que i es par (0, 2, 4, …).
	•	Si no es 0, entonces i es impar (1, 3, 5, …).

 En el ejemplo, el % sirve para decidir si el LED que toca en ese momento es par (lo enciende) o impar (lo apaga).


### Botonera: 
##### Código para Arduino.
 ```js
// --- Configuración de botones ---
const int numButtons = 3;
const int buttonPins[numButtons] = {2, 4, 7};
const int ledButtonPins[numButtons] = {9, 10, 11}; // LEDs botones

// --- Configuración de potenciómetros ---
const int numPots = 2;
const int potPins[numPots] = {A0, A1};
const int ledPotPins[numPots] = {3, 5}; // LEDs PWM

// Variables de estados previos
int lastButtonState[numButtons];
int lastPotValue[numPots];

void setup() {
  Serial.begin(9600);

  // Configurar botones y LEDs
  for (int i = 0; i < numButtons; i++) {
    pinMode(buttonPins[i], INPUT_PULLUP);
    pinMode(ledButtonPins[i], OUTPUT);
    lastButtonState[i] = digitalRead(buttonPins[i]);
  }

  // Configurar LEDs de potenciómetros
  for (int i = 0; i < numPots; i++) {
    pinMode(ledPotPins[i], OUTPUT);
    lastPotValue[i] = analogRead(potPins[i]);
  }
}

void loop() {
  // Leer y enviar botones
  for (int i = 0; i < numButtons; i++) {
    int buttonState = digitalRead(buttonPins[i]);

    // LED se enciende cuando botón está presionado
    digitalWrite(ledButtonPins[i], buttonState == LOW ? HIGH : LOW);

    if (buttonState != lastButtonState[i]) {  // enviar cambios
      Serial.print("B");
      Serial.print(i); 
      Serial.print(":");
      Serial.println(buttonState);
      lastButtonState[i] = buttonState;
    }
  }

  // Leer y enviar potenciómetros
  for (int i = 0; i < numPots; i++) {
    int potValue = analogRead(potPins[i]); // 0–1023
    int pwmValue = potValue / 4;           // 0–255

    // Ajustar LED según valor
    analogWrite(ledPotPins[i], pwmValue);

    if (abs(pwmValue - lastPotValue[i]) > 2) { // evitar ruido
      Serial.print("P");
      Serial.print(i);
      Serial.print(":");
      Serial.println(pwmValue);
      lastPotValue[i] = pwmValue;
    }
  }

  delay(10);
}
```
##### Botonera ejemplo código para Processing:
** Guarda tres archivos de audio en la carpeta data: audio1.mp3, audio2.mp3, audio3.mp3.

```js
// Importamos librería para comunicación serial
import processing.serial.*;
// Importamos librería Minim para manejar audio
import ddf.minim.*;

// Declaramos el objeto serial para comunicarnos con Arduino
Serial myPort;
// Objeto principal de Minim
Minim minim;
// Array de reproductores de audio (3 pistas)
AudioPlayer[] players;
// Variable para guardar el índice de la pista que está sonando
int currentTrack = -1;  // -1 significa que no hay pista activa al inicio

void setup() {
  size(400, 200); // Ventana de 400x200 píxeles
  
  // --- Configuración del puerto serial ---
  printArray(Serial.list()); // Muestra en consola la lista de puertos disponibles
  myPort = new Serial(this, Serial.list()[0], 9600); // Abrimos el primer puerto de la lista a 9600 baudios
  
  // --- Configuración de audio ---
  minim = new Minim(this); // Inicializamos Minim
  players = new AudioPlayer[3]; // Creamos un array de 3 reproductores
  
  // Cargamos los 3 archivos de audio desde la carpeta "data"
  players[0] = minim.loadFile("audio1.mp3", 2048); 
  players[1] = minim.loadFile("audio2.mp3", 2048); 
  players[2] = minim.loadFile("audio3.mp3", 2048); 
}

void draw() {
  background(0); // Fondo negro
  fill(255);     // Color blanco para el texto
  textSize(16);  // Tamaño del texto
  
  // Mostramos en pantalla qué botón está activo
  text("Botón actual: " + (currentTrack == -1 ? "ninguno" : currentTrack), 20, 40);
}

void serialEvent(Serial myPort) {
  // Leemos la cadena que llega desde Arduino hasta el salto de línea
  String inString = trim(myPort.readStringUntil('\n'));
  
  // Si no llega nada, salimos
  if (inString == null) return;

  // --- Si el mensaje recibido empieza con "B" significa que es un botón ---
  if (inString.startsWith("B")) {
    // Quitamos la letra "B" y separamos el mensaje en partes (ejemplo "0:0")
    String[] parts = split(inString.substring(1), ':');
    
    // Si realmente recibimos dos partes (índice y estado)
    if (parts.length == 2) {
      int buttonIndex = int(parts[0]); // Número del botón (0,1,2)
      int state = int(parts[1]);       // Estado del botón (0 = presionado, 1 = suelto)
      
      // Si el botón fue presionado (LOW = 0 en Arduino)
      if (state == 0) { 
        playTrack(buttonIndex); // Llamamos a la función para reproducir la pista correspondiente
      }
    }
  }
}

// --- Función que reproduce una pista según el botón ---
void playTrack(int index) {
  // Si ya había una pista sonando, la pausamos y la rebobinamos al inicio
  if (currentTrack != -1 && players[currentTrack].isPlaying()) {
    players[currentTrack].pause();
    players[currentTrack].rewind();
  }
  
  // Reproducimos en bucle la pista seleccionada
  players[index].loop();
  
  // Actualizamos la variable para saber cuál es la pista activa
  currentTrack = index;
}
```
##### Funcionamiento:
    •	Arduino: manda B0:0, B1:0, B2:0 cuando presionas los botones.
	•	Processing:
	•	Si recibe B0:0 → reproduce audio1.mp3.
	•	Si recibe B1:0 → reproduce audio2.mp3.
	•	Si recibe B2:0 → reproduce audio3.mp3.
	•	Si ya había un audio sonando, lo pausa y arranca el nuevo.

 ```js
if (state == 0) { // LOW = presionado
  playTrack(buttonIndex);
}
```
	•	Solo entra cuando el estado es 0 (botón presionado).
	•	Ignora el state == 1 (cuando se suelta).


⸻

##### ¿Qué significa 2048?
##### 2048 corresponde al tamaño del buffer de audio que usa Minim para procesar los datos de sonido.
```js
players[0] = minim.loadFile("audio1.mp3", 2048);
```

##### ¿Qué es un buffer?
	•	El buffer es como una “ventana” de datos de audio que Minim carga en memoria para procesar el sonido en bloques.
	•	En este caso, cada bloque contiene 2048 muestras de audio.
	•	Mientras se reproduce el archivo, Minim va leyendo y cargando bloques de 2048 muestras de manera continua.

##### ¿Por qué 2048?
	•	Es un valor estándar en procesamiento de audio digital (una potencia de 2).
	•	Valores más grandes (ej. 4096, 8192) → mayor estabilidad, pero más latencia.
	•	Valores más pequeños (ej. 512, 1024) → menor latencia, pero más carga para el procesador.

##### En este ejemplo, 2048 es un equilibrio:
	•	Suficientemente grande para que el audio se reproduzca sin cortes.
	•	Suficientemente pequeño para que la respuesta al control sea rápida.

##### Si no se especifica nada, Minim usa un valor por defecto (generalmente 1024).
##### En nuestro caso, se puso explícitamente 2048 para darle un poco más de seguridad y estabilidad al audio.
______________________________________________________________________


### Conectar un sensor de distancia Sharp a Arduino, sigue estos pasos:

Materiales:

•	Arduino (por ejemplo, Arduino Uno)
•	Sensor de distancia Sharp (GP2Y0A21YK o similar)
•	Cables de conexión
•	Fuente de alimentación para Arduino (puede ser un cable USB)

Conexiones del Sensor Sharp:

El sensor Sharp tiene tres pines:

1.	VCC: Alimentación (5V)
2.		2.	GND: Tierra (GND)
3.	Vo: Salida de señal analógica (se conecta a un pin analógico de Arduino)

Pasos para conectar el sensor:

1.	Conectar el pin VCC del sensor a 5V de Arduino:
	•	Usa un cable de conexión para conectar el pin VCC del sensor Sharp al pin de 5V en el Arduino.
	
 2.	Conectar el pin GND del sensor a GND de Arduino:
	•	Conecta el pin GND del sensor Sharp al pin GND del Arduino.
3.	Conectar el pin de señal (Vo) a un pin analógico en Arduino:
	•	Conecta el pin Vo (salida de señal) del sensor al pin analógico A0 en Arduino.

Diagrama de conexiones:

•	Sensor Sharp VCC → Arduino 5V

### Sensor Distancia Visual
#####código Arduino:
```js
// Definir el pin del sensor Sharp
int sharpPin = A0;

void setup() {
  Serial.begin(9600); // Iniciar comunicación serial
}

void loop() {
  int sensorValue = analogRead(sharpPin); // Leer valor del sensor
  Serial.println(sensorValue); // Enviar valor a Processing
  delay(100); // Esperar un momento
}
```

##### código Processing:

```js
import processing.serial.*;

Serial myPort;  // Create object from Serial class
static String val;    // Data received from the serial port
int sensorVal = 0;

void setup()
{
  background(0); 
  //fullScreen(P3D);
   size(1080, 720);
   noStroke();
  noFill();
  String portName = "COM5";// Change the number (in this case ) to match the corresponding port number connected to your Arduino. 

  myPort = new Serial(this, "/dev/cu.usbmodem1101", 9600);
}

void draw()
{
  if ( myPort.available() > 0) {  // If data is available,
  val = myPort.readStringUntil('\n'); 
  try {
   sensorVal = Integer.valueOf(val.trim());
  }
  catch(Exception e) {
  ;
  }
  println(sensorVal); // read it and store it in vals!
  }  
 //background(0);
  // Scale the mouseX value from 0 to 640 to a range between 0 and 175
  float c = map(sensorVal, 0, width, 0, 400);
  // Scale the mouseX value from 0 to 640 to a range between 40 and 300
  float d = map(sensorVal, 0, width, 40,500);
  fill(255, c, 0);
  ellipse(width/2, height/2, d, d);   

}
```
### Sensor de humedad (DFRobot).
<img src="https://raw.githubusercontent.com/DFRobot/DFRobotMediaWikiImage/master/Image/Stream_Sensor_CD_UNO.png" width="290" height="173" />

Conexión:
VCC-5V
GND-GND
S-Analog pin A0

Puedes ponder el sensor en la palma de tu mano
para sensar la humedad de  tu palma.

 ```js

void setup()
{
  Serial.begin(9600);// abre el puerto serial y Establece la velocidad en baudios a 9600 bps
}
void loop()
{
  int sensorValue;
  sensorValue = analogRead(0);   //conectar el sensor de humedad al pin analogo 0
  Serial.println(sensorValue); //imprime el valor a serial.
  delay(200);
}
```

###### Promedio de Imágenes.
### código de Arduino:
```js
void setup() {
  Serial.begin(9600);
}

void loop() {
  int potValue = analogRead(A0);
  Serial.println(potValue);
  delay(20);
}
```

### código de Processing:

```js
import processing.serial.*;

Serial myPort;
PImage[] imgs;
int numImages = 3;
PImage avgImg;
float mixAmount = 0;

void setup() {
  size(800, 600);
  println(Serial.list());
  
  //Cambia el índice según tu puerto (0, 1, 2, etc.)
  myPort = new Serial(this, Serial.list()[0], 9600);
  //myPort = new Serial(this, "/dev/cu.usbmodem1101", 9600);
  myPort.bufferUntil('\n');

  // Cargar imágenes
  imgs = new PImage[numImages];
  imgs[0] = loadImage("img1.jpg");
  imgs[1] = loadImage("img2.jpg");
  imgs[2] = loadImage("img3.jpg");

  avgImg = createImage(imgs[0].width, imgs[0].height, RGB);
}

void draw() {
  // Dibujar la imagen promedio según el valor del potenciómetro
  background(0);
  calcAverage(mixAmount);
  image(avgImg, 0, 0, width, height);
  
  fill(255);
  textSize(20);
  text("Mezcla: " + nf(mixAmount, 1, 2), 20, height - 20);
}

void serialEvent(Serial p) {
  String val = p.readStringUntil('\n');
  if (val != null) {
    val = trim(val);
    float sensor = float(val);
    mixAmount = map(sensor, 0, 1023, 0, 1); // 0 a 1
  }
}

void calcAverage(float t) {
  avgImg.loadPixels();

  for (int i = 0; i < avgImg.pixels.length; i++) {
    color c1 = imgs[0].pixels[i];
    color c2 = imgs[1].pixels[i];
    color c3 = imgs[2].pixels[i];

    // Promedio ponderado según el potenciómetro
    float r = red(c1)*(1-t) + red(c2)*t*0.5 + red(c3)*t*0.5;
    float g = green(c1)*(1-t) + green(c2)*t*0.5 + green(c3)*t*0.5;
    float b = blue(c1)*(1-t) + blue(c2)*t*0.5 + blue(c3)*t*0.5;

    avgImg.pixels[i] = color(r, g, b);
  }
  avgImg.updatePixels();
}
```







