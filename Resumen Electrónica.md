# Circuitos en Alterna
**Tensión alterna senoidal**
$$u(t) = U_{max} . sen(wt)$$

## Como se comportan los elementos al ser excitados por una tensión senoidal
**Resistencia**
Ley de Ohm 
Como la resistencia no es capaz de almacenar energía, sino que la disipa instantaneamente, su respuesta está en fase con la tensión alterna. 

**Capacitor**
Ecuación Constitutiva
*"Inteligente con down"*
$$i_c(t) = C \frac{du}{dt}$$
La tensión del capacitor está atrasada 90° que la tensión original. 
CIUDAD -> *"En un sistema capacitivo la corriente adelanta 90° a la tensión"*
**Inductor**
Ecuación Constitutiva
*"Una licuadora distinta"*
$$u_l(t) = L \frac{di}{dt}$$
La tensión del inductor está adelantada 90° que la tensión original.
LUIS -> *"En un sistema inductivo la tensión adelanta 90° a la corriente"* 

## Fasor
Para facilitar la resolución de circuitos en corriente alterna hacemos uso de la herramienta de fasores.
El fasor es una función armónica compleja dependiente del tiempo compuesta por la función seno y coseno. Ésta se representa mediante la identidad de euler, que surge de los números complejos. 

$$\dot{U} = U_{máx} \mathbf{e}^{j(\omega t + \varphi)} = U_{máx} \cos(\omega t + \phi) + j U_{máx}. sen(\omega t + \varphi)$$
Parte Real 
$$Re(\dot{U})=  U_{máx} \cos(\omega t + \phi) $$
Parte Imaginaria 
$$Im(\dot{U})=    U_{máx}. sen(\omega t + \varphi)$$

### Diferencias entre Vector y Fasor
- Un vector es la representación de una magnitud física en un espacio físico como un plano real, mientras que un fasor no tiene representación física, sino que reprsenta una mangitud matemática en un plano complejo.
- Un vector puede ser estático mientras que un fasor es dependiente del tiempo
- Hacer uso de los números complejos para los fasores lo diferencia del vector que tiene sus operaciones como producto cruz o producto punto, cosa que carecen los fasores.

**El fasor es una función que permite relacionar una función sinusoidal (corriente o tensión) con un número complejo equivalente**

## Impedancia Compleja
**La impedancia es siempre un número complejo, NO es un fasor.**

La impedancia compleja es una expresión que caracteriza el comportamiento de una red
pasiva en función de la relación entre la tensión y la corriente cuando éstas son de forma senodial.

**Ley de Ohm para alterna -> Otra forma de expresar Impedancia compleja**
$$\frac{\dot{U}}{\dot{I}}=\underline{Z} = R+j(\omega{}L-\frac{1}{\omega{}C})$$
**Reactancia Inductiva**
$$ \omega{}L=X_L$$
**Reactancia Capacitiva**
$$ \frac{1}{\omega{}C}=X_C$$
