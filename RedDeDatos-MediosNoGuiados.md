ESP32 se puede comunicar con wifi. LORA es un protocolo de comunicaciones que se comunica en una frecuencia de muy baja taza pero a gran distancia.

Para antenas resonantes el rango está definido debido a que depende del tamaño de la longitud de onda. Es decir el tamaño de la antena depende de la longitud de onda. Si quisiera transmitir 10Hz debería tener una antena aprox 15 kilometros de largo.  Irradiar en bajas frecuencias es poco prácticos. Idealmente irradiar con mayor frecuencia. Ejemplo antenas de auto. 

---

## Antenas Omnidireccionales
Se puede ver en el gráfico que cuando la longitud es de 2L, las direcciones son las más equitativas en cada dirección. En distintas longitudes se puede ver. 
Auriculares de cable pueden funcionar como antena para radio en celulares. No es lo ideal pero mejor que nada. 
Los cables suelen tener un filtro (ejemplo cargador, vga - vga, etc) que filtra el ruido de estas señales de radio que podrían llegar al cable.

Las antenas tienen la misma propiedad para irradiar como para recibir. 
El gráfico de como se distribuye la señal simboliza la dirección donde puede irradiar potencia, pero tambien donde puede recibir. 

## Antentas Directivas
Los directores son pasivos. 
**Interpretación de Directores y Reflectores**:
		Un estanque con agua a la que se le tiran piedras genera circulos de perturbación en el agua. Si ponemos elementos en el agua se generan rebotes. Si podemos estudiar estos rebotes y obtener que elementos y en que posición hacen que las perturbaciones de rebote se desplazen más hacia un lado, podriamos interpretar esto para directores y reflectores.


### Patch
Un celular está diseñado como una antena patch. Por esto consigue altas frecuencias, bajas longitudes de onda.


### Parabólicas
Gigante de Arecibo

## Formas de Propagación 
#### Ondas de Superficie: 
La onda se pega y sigue la curvatura de la tierra, utilizado en frecuencias por debajo de los 2MHz.
Se pega por el campo magnetico de las ondas (Sera del campo magnetico de la tierra?)
#### Ondas Ionosféricas:
Señal reflejada en la ionósfera. Se consiguen grandes distancias. Se utiliza en frecuencias entre 2 y 30 MHz.
Por la ionosfera ser un gas ionizado se puede irradiar o "resonante" con las ondas. Pueden hacer rebotar las ondas perdiendo energía. Esto hace que no afecte la curvatura de la tierra. En este caso los satelites no pueden utilizar esta frecuencia debido a que la ionosfera funciona como "espejo"
#### Ondas Espaciales:
Actua como rayo directo. Se propaga a traves de capas bajas de la atmosfera a frecuencias mayores a 30 MHz. Es necesario una linea de vista entre los dos puntos. En caso contrario, si no se tiene una linea de vista debido a la curvatura de la tierra, se podría poner un satelite intermediario para que haya un rayo directo Antena1 -> Satelite -> Antena2


*"La forma de propagación depende unicamente de la frecuencia y de la forma de la tierra."* 

## Tipos de Enlace

*"La difracción vista cuando una onda golpea un borde, generando otra fuente de onda que se suma o resta con la original, no la vemos con la luz debido a lo hablado en la otra clase. Se toma a la luz como fotones, es decir trazado de razos, y no como onda, debido a la lognitud de onda respecto al contexto"*


*"No tener cobertura o señal se da por la multitrayectoria, donde las señales rebotan, llegan a un mismo lugar con distinta fase, y punto a punto pueden sumarse o restarse y finalmente no tener cobertura"*

--- 
# COSAS DE PRACTICA NOOO

Enviar una señal ejemplo de 1 watt en una esfefa, al momento de emitir la señal abarca una superficie menor. Mientras viaja por el espacio la esfera de onda se hace más grande, por lo tanto está abarcando mayor área. Esto es el fenómeno de atenuación.

-Diapositiva 103. 
Podria preguntarles. Con tal distancia fija, transmisor con potencia fija, y un margen de potencia para el receptor fija. Tengo la opcion de transmitir en 2,4Ghz o en 5,8Ghz. Cual debo elegir? 
Podemos definir las potencias de transmitor y receptor con unidades dBm. Si la atenuación es de 60dB, tendriamos que como mínimo transmitir 60dBm en el transmisor.

La distancia de la radio en LOS (line of sight) depende de la altura de la antena
$$\sqrt{12,74*k*h_1(m)}$$

PREGUNTAR

### Zona de Fresnel
Si tenemos objetos en el medio de transmisión no guiado, podemos calcular la zona de fresnel. Zona donde cualquier radio que rebote en esta zona llegara de manera destructiva al receptor (Desfasado).
Para calcular esto, dado la linea de vista, con distancia fija, se puede calcular el elipse de estos dos puntos que simboliza la curva que equivale a la zona de fresnel. 
Ejemplo zona de fresnel = 3 metros.
Con este dato sabemos que la antena debe tener 3 metros de margen donde no haya ningun tipo de objeto que pueda reflejar.

---

**Presupuesto del enlace** (Antena entre ingenieria e informatica)
1. Linea de Vista
	1. Verificar la distancia entre ingenieria e informatica para tener en cuenta la altura de antenas y objetos de por medio
2. Atenuación del espacio libre
	1. Si ya tenemos la distancia y se puede elegir la frecuencia, podemos saber la atenuación.
3. Zona de Fresnel
	1. Nos quedamos con la altura mínima. 

**Presupuesto del enlace**:
$$P_{Tx} + G_{A_Tx}+G_{A_Rx} - A_{tt} >= S_{Rx}+ M_{Rx}$$
Potencia del transmisor -> $P_{Tx}$
Ganancia de atenuación de Transmisor -> $G_{A_Tx}$
Ganancia de atenuación de Receptor -> $G_{A_Rx}$
Pérdida por atenuación -> $A_{tt}$
Sensibilidad del Receptor -> $S_{Rx}$
Margen del Receptor -> $M_{Rx}$

