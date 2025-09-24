**Requerimientos**:
	"Un requerimiento o requisito es una caracteristica del sistema o una descripción de algo que el sistema es capaz de hacer con el objeto de satisfacer el proposito del sistema "
	**IEEE**
		Capacidad o condicion que necesita un usuario
		Capacidad o condicion que debe cumplir un sistema

**Que pasa si se toman malos requerimientos**
- Software no satisface usuario
- Desacuerdo entre clientes y desarrolladores
- Gasto de tiempo y dinero

**Solucionar los errores de requerimiento** (Tiempos acumulativos)
- Requerimientos -> 0.1 (Osea no tardas nada en, preguntar de vuelta, obtener el requerimiento correcto, y cambiar la documentación)
- Diseño -> 0.5 (Tardas lo mismo que antes sumado el cambio de diseño que ya tenías en mente) = 0.6
- Codificación -> 1 (Programar con un requisito erroneo, se debe corregir, ahora todo lo anterior sumado todo el código involucrado en ese requisito) = 1.6
- Pruebas de Unidad -> 2 (Hacer las pruebas de unidad ahora erroneas se debe corregir lo anterior y ademas esto) = 3.6
- Pruebas de Aceptación -> 5 (TODO ANASHI)
- Mantenimiento -> 20 (CHAU, esto hace referencia a cuando se hace un mantenimiento del producto ejemplo cada año, en un año se hace el mantenimiento y se ve que habia un error en el producto, CHAU MATATE)

Por esto aparece un nuevo concepto...

# Ingeniería de Requerimientos
"Disciplina para desarrollar una especificación completa, consistente, y no ambiguam la cual sirva como base para acuerdos comunes entre todas las partes involucradas y en donde se describen las funciones que realizara el sistema"

**Importancia**
- Gestion de necesidades de pryoecto en forma estructurada
- Mejor capacidad de predecir cronograma de proyectos
- Disminuye costos y retrasos
- Mejora calidad de software
- Mejora comunicacion entre equipos
- Evita rechazo de usuarios finales

## Procesos
### 1. Estudio de Viabilidad
Analizar si tenemos competencia para desarrollar este producto, el cliente está comprometido a hacer el proyecto con financiación, y que haya interes para llegar al objetivo

**Responde siguientes preguntas del sistema **
- Contribuye objetivos generales de organizacion?
	- Si no lo hace, no tiene valor real en el negocio
- Puede implementar tecnología actual?
- Puede implementar restricciones de costo y tiempo?
- Puede integrarse a otros que existen en la organización?

**Propiedades de los requerimientos**
- **Necesario**
	- Si un requerimiento no está, entonces algo falla. Es necesario para otra funcionalidad
- **Conciso**
	- Fácil de leer y entender
- **Completo**
	- No necesita ampliarse
- **Consistente**
	- No debe contradecir otro
- **No ambiguo**
	- 
- **Verificable**

Ejemplo de clase. Estos todos son requerimientos pero hay que clasificarlos entre funcionalidad, condicion, etc.
- Información de socios y clientes y precio y cosas y cosas
	- No es conciso y es ambiguo!
- Pago de app debe hacerse por transferencia y por tarjeta
	- Dentro de todo está bien, el pago es una funcionalidad
- Que muestre stock disponible que ofrece cada cerveceria y precios de subscripcion
	- El mostrar stock es una funcionalidad adicional
- Soporte y ayuda
	- No es una funcionalidad! 
- Privacidad de datos personales
	- Es una obligacion! no es funcionalidad 
- Comparación de precios
	- Es amiguo necesita mas informacion 
- Expandirse a distintas ciudades
- Ubicaciones de cerverecias 
	- Funcionalidad?
- Mapa de los comercios
	- Funcionalidad
- Conocer ubicacion del usuario

**Tipos de requerimientos**
- **Funcionales**
	- Describen interaccion entre sistema y ambiente, como debe comportarse el sistema ante un estimulo
	- Describen lo que un sistema debe y no debe hacer
	- Describe con detalle la funcionalidad del mismo
	- Independientes de la impementación de la solución
	- Se puede expresar de distintas formas
Ejemplos:
	Poder iniciar sesión
	Si pongo mal los datos, que no me permita iniciar sesión

- **NO Funcionales** *(No es lo que no debe hacer el sistema, eso sería una funcionaloidad, son reestricciones)*
	- Describen una restricción sobre el sistema que limita nuestras elecciones en la construccion de una solución al problema
	- No todo requisito No funcional tiene un requisito funcional
		- "No se pueden vender a menores" -> "Hacer chequeo de edad"
		- "Que sea una plataforma Web" -> No hay funcionalidad
Ejemplo: 
	Plataforma
	Sistema operativo
	Arquitectura
	"No vender a menores de 18 años"

Dentro de los no funcionales
**Del producto:**
	Especifican comportamiento de producto, usabilidad eficinecia rendimiento espacio fiabillidad y portabilidad
		"Implementarse en pagina web"
**Organizacionales:**
	Implementacón, estandares, entrega (es más técnico)
		"Que este hecho en html, javascript"
**Externos:**
	Interoperabilidad, legales, privacidad, seguridad y eticos
		"No vender a menores de edad"

### Especificación de Requerimientos
**Propiedades**
- Correcto
- No ambiguo
- ...

**Documento de definición de requerimientos**
**Documento de espicificación de requerimientos**
**Documento de espicificación de requerimientos de software**
Los datos que nosotros retiramos de todos para explicar lo que debe hacer el programa o algo asi

#### Aspectos básicos de una especificación de requerimientos
**Funcionalidad**
	Que hace el software

**Interfaces Externas**
	Como interactua el software con el medio externo 
	Mucho más amplio hoy en dia no solo interfaz grafica sino cosas como la api 

**Rendimiento**
	Velocidad, disponibilidad, tiempo de respuesta

**Atributos**
	Portabilidad seguridad 

**Restricciones de Diseño**
	Estandares...

### Validación de Requerimientos
NO CONFUNDIR CON VERIFICACION
Verificacion -> Demostrar que se hizo de forma correcta
	Chequeo los requisitos contra lo que hace mi producto 
Validacion -> Demostrar que se hizo algo correcto
	Chequeo que el cliente afirme que lo que hace el producto es correcto

Hasta este punto esto es clave ya que acá es donde se puede resolver todos los errores ya que la corrección solo será un documento, luego de aquí se hace el diseño la implementación y demas.

# Técnicas de especificación de requerimientos
Como diseño soluciones

**Estáticas**
No cambian a lo largo del tiempo 
Aquellos requerimientos que modelo que no se modifican a traves del tiempo
Se define QUE hace pero no COMO


**Dinamicas**
