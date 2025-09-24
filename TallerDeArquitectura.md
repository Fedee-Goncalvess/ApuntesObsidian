# Funciones

## Sintaxis
``` vhdl
FUNCTION Centigrados_A_Fahrenhait(c: real) RETURN real IS
VARIABLE f: real;
BEGIN
f:= c* 9.0/5.0 + 32.0;
RETURN(f);
END FUNCTION;
```

**Pure**: Devuelve el mismo valor para las mismas entradas
**Impure:** Puede no devolver el mismo valor para las mismas entradas
*Por omisión, si no se define, una función es pura*

# Señales
La forma de comunicarse las *cajas negras* (procesos) son con señales. Estas cajas son las entity con una descripción interna (arquitectura).

**Libreria std_ulogic_1164**
	Definen un tipo de dato STD_ULOGIC que representa una señal binaria con 8 estados. 
``` vhdl
	TYPE std_ulogic IS('U', -- Uninitialized
'X', -- Forcing Unknown
'0', -- Forcing 0
'1', -- Forcing 1
'Z', -- High Impedance
'W', -- Weak Unknown
'L', -- Weak 0
'H', -- Weak 1
'-' -- Don't care
);
```

## Caracterización
### Transacciones (valor,tiempo)
A la señal se le asigna un valor para un tiempo determinado

### Eventos 
Un evento se produce cuando en una asignación se produce un cambio en el valor de la señal.
- **Hay transacciones que no produce eventos**
### Propagación de señales 
Desde un tiempo cero, se describe como es la propagación de la señal.
```vhdl 
s<= ‘0’, ‘1’ AFTER 15 NS, ‘0’ AFTER 33 NS,
‘1’ AFTER 38 NS, ‘0’ AFTER 63 NS, ‘1’ AFTER 108 NS;
```
### Drivers 
Cada señal que se declara, se la asocia con un driver. 
Una cola (vector) empleada para almacenar la forma de onda, que proyecta los valores futuros de la señal
Mientras vaya simulando, voy a ir sacando valores de la cola de driver, y actualizando los valores.

Una señal genera un driver. El driver es un vector que contiene los eventos de esa señal, donde tiene el tiempo y el valor de la señal. Para simular, se va recorriendo el vector de entrada, y va generando otro driver, es decir otro vector con las respuestas. 
Ejemplo señal S -> not S
La señal S es invariable, y la que se genera es variable ya que puede modificarse por otra. En el caso que dos señales S1 y S2 modifiquen en not S en un mismo instante se hace uso de la STD_ULOGIC para discriminar quien "gana".


# Retardo
## Retardo delta
Se asume por defecto cuando no se especifica un retardo concreto en la asignación a una señal (causalidad) 
Es un tiempo diferencial es decir por defecto debe ser 1 fentosegundo aprox

Para evitar el retardo del delta se le especifica un retardo específico

## Retardo Inercial
Se especifica con la palabra reservada AFTER
- Un pulso de duración menor del retardo (tiempo de conmutación del circuito) no se transmite
``` vhdl
ARCHITECTURE --- OF --- IS
---
BEGIN
salida<= entrada AFTER 5 NS;
---
END ---;
```
ELDIVBUJOESTAMAL

## Retardo Transporte
Se especifica con la palabra reservada TRANSPORT
- Se transmite la señal íntegra independientemente de cual sean la duración de los pulsos

``` vhdl
ARCHITECTURE --- OF --- IS
---
BEGIN
salida<= TRANSPORT entrada AFTER 5 NS;
---
END ---;
```

# Realización del Test
- Entidad sin puertos
- Arquitectura estilo estructural, instanciando el componente a testear
``` vhdl 
ENTITY testInversor IS
END testInversor;
```
``` vhdl
ARCHITECTURE una OF testInversor IS
	SIGNAL s, not_s: BIT;
	COMPONENT inversor
		PORT(s: IN BIT; not_s: OUT BIT);
	END COMPONENT;
	FOR com: inversor USE
		ENTITY WORK.inversor(arqInversor);
BEGIN
	com: inversor PORT MAP(s, not_s);
	s<= ‘0’, ‘1’ AFTER 15 NS,
		‘0’ AFTER 33 NS, ‘1’ AFTER 38 NS,
		‘0’ AFTER 63 NS, ‘1’ AFTER 108 NS;
END una;
```

## Modelo de simulación
- Funcionamiento de hardware es paralelo
- Salida de sistema puede cambiar **solamente cuando cambien sus entradas** *(eventos)*
- VHDL entiende cada sentencia concurrente como un proceso, y los procesos se comunican mediante señales. 

**Consideraciones previas**
- Al poner en funcionamiento, todos sus componentes pueden activarse simultaneamente
- Si tuviesemos una máquina paralela, cada proceso se podría ejecutar en un procesador distinto
	- **Nosotros no disponemos de máquinas paralelas.**
- ¿Como ejecuto modelo paralelo en máquina secuencial?
### Definición de Tiempos
- **Modelo de simulacipon controlado por eventos**
	- Solamente se van a evaluar los procesos cuando haya cambios en las señales que los activan
- **Señales caracterizadas por sus drivers**
	- Esto se actualizan al encontrarse una sentencia WAIT dentro de un process o despues de ejecutar una sentencia concurrente de otro tipo
#### Tipos de tiempos
**Tiempo total de simulación (T)**
- Tiempo durante el cual vamos a observar el funcionamiento del circuito
**Tiempo de simulación (delta T)**
- Tiempo específico para el cual estamos realizando la simulación por producirse un evento
- El tiempo avanza una cantidad delta T, **no fija** según se van consumiento los eventos en el driver.
**Ciclo o paso de simulación (sigma)**
- No supone avance de tiempo físico sino de un retardo de tipo sigma.
DIBUJO ESTÁ MAL. el Sí que sale del cuadrado de *actualiza los valores de la señal*.. sale del rombo de debajo.


