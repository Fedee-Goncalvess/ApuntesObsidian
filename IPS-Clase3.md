# Sistemas Lineales
## Convolución Continua
- Sistema lineal continuo con operador H que satisface superposicion
- Representamos el SVIC en términos de impulsos
- Aplicamos H 

**La convolución me da salida de SLIT o SLVT**
![[Pasted image 20250909143130.png]]
Integral del producto de dos señales donde una esta reflejada respecto de la otra es convolución. 
LA CONVOLUCIÓN ES EL AREA ANASHI
Es decir la formula de arriba NO ES UNA CONVOLUCION

1. Dibujar x(t) y dejar fija
2. Obtener h(.)
3. Reflejar h(.)
4. Desplazar el origen de h al punto de observación t
5. Multiplicar punto a punto e integrar, da y(t)
6. Repetir 4 y 5 hasta obtener todos los puntos.

EJEMPLO:
![[Pasted image 20250909143241.png]]
1. x y h son dos señales
2. Definición de  convolución
3. Graficamos x(ŧ)
4. Graficamos h(ŧ)
5. Reflejamos h con -> h(-ŧ)
6. Graficamos h(t-ŧ)

y(t) = {
		o ; t<0
		integral de 0 a t de e a la alfa por 
}

![[Pasted image 20250909144958.png]]
La parte entre de Tao < 0 es cero debido a que las fronteras de integracion es de 0 a t. Y de >5 es porque el t se va desplazando
Soporte siempre es mayor igual en caso continuo de la suma de los dos soporte. Como máximo es infinito, como mínimo es la suma de los dos. En este caso es infinito. 

# Propiedades de la Convolución
- Conmutativa
	- y={x* h}={h* x}
- Asociativa
	- y={{x* h}* ħ}={{x* {h* ħ}}
- Distributiva
	- y={x* {h + ħ}}= {x* h} + {x* ħ}

Un sistema puede ser h_tot= h+ħ

Investigar SOPORTE relacionado a AUDIO, Un audio de 10ms se procesa con una convolusion que tarda 1 ms pues el audio final sera 11ms pero por que depende del soporte?

# Caracterizando SLIT o SLIT por sus propiedades con la convolución

## Causalidad
Se aplica impulso en cero y NO sale nada antes de cero. -> Respuesta impulsional unilateral a derecha.
¿Por que en cero? -> Definimos en SLID o SLIT se aplican impulsos en cero

## Memoria
Se aplica impulso en cero y SOLO sale una respuesta en cero. 
## Estabilidad en SLID
Un SLID es estable en sentido EA/SA si su respuesta impulsional es absolutamente sumable:
![[Pasted image 20250909151006.png]]


**Ejemplo de estabilidad de un ejercicio**

- SLIT -> h(t) ?= e^(-t) . u(t)
- ¿Causal? -> Si, h(t) = 0 para todo t<0
- ¿Memoria? -> Si, h(t) -=- 0 para t -=- 0
	- No tiene delta multiplicando es decir. Yo una señal la multiplico por un delta en cero y tengo UN solo valor como resultado. 
	- Si no tiene delta en este caso multiplico dos funciones pero me dan varios valores. Me exploto el ojete?
- ¿Estable? -> absolutamente integrable (-inf , +inf) de |e^(-t) . u(t)| = Valor Real 


---

# Continuacion clase 3

# Tipos de representación de Slit y Slid
![[Pasted image 20250916143708.png]]

Ordinaria -> Una sola variable (t)
Coeficientes constantes que pueden ser funciones de i o de j o constantes.

**Esto es un slit**
Se debe comprobar los items debajo de la fórmula.
- El orden de la salida debe ser mayor que el de la entrada. N>= M. Esto justifica que sea causal.



![[Pasted image 20250916143722.png]]

y(t) homogenea es la solución del sistema. 
y(t) particular es la solución del sistema causada por una entrada x(t)
La particular cuenta un régimen transitorio y un régimen permanente. 


![[Pasted image 20250916143943.png]]


## Ecuaciones de estado
Formas de representar sistemas (NO LAS VAMOS A VER)
La diferencia entre lo que vimos y estos.
Acá la ecuación diferencial es solo una y no de mayor orden.

# Diagrama en bloques

![[Pasted image 20250916150004.png]]

![[Pasted image 20250916150147.png]]
Si se reemplaza x(n) (la entrada) con un impulso, se puede ver que se obtienen los coeficientes. 

