# Entendiendo los casos de uso (use cases)

Los casos de uso (use cases) son unos artefactos muy recomendados para el entendimiento, descripción, documentación y trazabilidad de los requerimientos funcionales de un sistema. Hacer un modelo de casos de uso es un primer paso en el análisis de requerimientos para describir el comportamiento del sistema desde la perspectiva de los actores y los objetivos a realizar con él. Ivar Jacobson el creador de los casos de uso los describe de la siguiente manera:

Un caso de uso son todas las maneras en las que se usa un sistema para lograr una meta particular para un usuario particular. Si juntamos el conjunto de todos los casos de uso te da todas las maneras útiles para usar el sistema, e ilustra el valor que el sistema proporciona
El modelo de casos de uso es una de las vistas del modelo de arquitectura 4+1 de Philippe Kruchten, como en la siguiente imagen, el modelo de casos de uso es la quinta vista (+1).



Los casos de uso se emplean en muchos procesos de ingeniería de software entre todos ellos dos de los más ampliamente utilizados son: MSF (Microsoft Solution Framework) y RUP (Rational Unified Process).

Aunque ambos procesos cumplen el mismo objetivo (proyectos de software con éxito) cada uno de ellos ubica el modelo de casos de uso de forma un poco distinta.

En MSF se tienen 5 fases:

Envisioning (Visualizar)
Planning (Planear)
Developing (Desarrollar)
Stabilizing (Estabilizar)
Deploying (Despliegue)
Los casos de uso (algunas veces en MSF los nombran usage cases en vez de use case), estos se crean en la fase Planning en la etapa de diseño conceptual (Conceptual Design).

En RUP se tienen 4 fases:

Inception (Inicio)
Elaboration (Elaboración)
Construction (Construcción)
Transition (Transición)
En RUP el modelo de casos de uso se crea durante la fase de inicio. en la disciplina de requisitos.

A un caso de uso informalmente se le conoce como una colección de escenarios. Un escenario es una secuencia especifica de acciones e interacciones exitosas y erróneas entre actores y el sistema bajo diferentes condiciones de operación.

A los escenarios también se le conocen como instancias de casos de uso.

Formatos para casos de uso
Los casos de uso de caja negra son la clase más común ya que no describen el funcionamiento interno del sistema sino sus responsabilidades, especifican la interacción entre el sistema y el mundo exterior en este contexto el mundo exterior se refiere a los actores, un actor en este contexto es alguien que interactua con el sistema.

Las responsabilidades del sistema en este tipo de casos de uso describen siempre que es lo que hace el sistema sin decidir como lo hace (esto le corresponde al diseño). Los tipos de casos de uso son:

Formato breve (brief): Es la historia del uso del sistema en un solo párrafo, por ejemplo:
Crear una nueva cita: una persona entra al sitio del sistema en el menú de creación de citas, el sistema despliega la pantalla de creación de citas solicitando los siguientes datos: fecha, hora, servicio solicitado, nombre, apellido, teléfono de casa, teléfono celular, email. La persona ingresa los datos y ejecuta la acción guardar. El sistema valida los datos, una cita fue creada en el sistema.

Formato casual (casual version): es un un formato informal que cubre varios escenarios, este es el más ampliamente utilizado. Ejemplo:

Historial de versiones
Fecha	Descripción	Autor
Noviembre 6, 2002	Initial draft	Heidi Steen
Titulo (Title):	Creación de una cita
Identificador (ID):	UC1
Breve descripción (Summary):	Este caso de uso inicia cuando la persona entra al menú creación de citas del sistema, el sistema ingresa los siguientes datos: fecha, hora, servicio, nombre, apellido, email, teléfono de casa, teléfono celular. Entonces ejecuta la acción guardar entonces el sistema hace la validación y la cita es creada.
Actores/Actors (no siempre son seres humanos, pueden ser otros sistemas informáticos o procesos se incluye el propio sistema):

Persona, sistema médico

Precondiciones/Preconditions (establecen lo que siempre debe cumplirse antes de iniciar el caso de uso, se asume que son verdaderas):

La persona tiene acceso a Internet
La persona entro en el sitio de la aplicación
Los catálogos esta online y trabajan bien.
Postcondiciones/Postconditions (establecen que debe cumplirse cuando el caso de uso termina con éxito):

Se creo la cita en la base de datos del sistema.

Flujo básico/Basic flow: (por lo regular no incluye ninguna condición o bifurcación, se incluyen interacción entre actores, validaciones y cambios de estados)

Actor	Sistema
1-. La persona entra a la aplicación y elije crear una nueva cita.	
2-.El sistema solicita los siguientes datos: fecha, hora, servicio, nombre, apellido, email, teléfono de casa y teléfono celular.
3-.La persona ingresa todos los datos solicitados y ejecuta la acción de guardar.	
4-. El sistema recibe la petición, realiza la validación de los datos si no existe un error entonces crea una la cita en la base de datos y despliega un mensaje de éxito.
5-. La persona ha creado una nueva cita.	
Flujos alternos/Alternate flows/extensions (indican los otros escenarios de éxito, las bifurcaciones del flujo básico se registran poniendo el número del paso):


3a Ingresa solo los datos requeridos.

3a1. La persona ingresa solo los datos mínimos requeridos: fecha, hora, servicio, nombre, apellido y al menos uno de los teléfonos: home phone y cel phone.


Flujos de excepción: (Exception flows: Indican los escenarios de fallo, esta sección también puede incluirse dentro de los flujos alternos)

3b Selecciona una fecha anterior a la fecha actual.

3b1. El sistema envía el mensaje “No se permite una fecha anterior a la actual”


4b. Faltan campos requeridos

4b1 El sistema envía el mensaje indicando los campos requeridos que faltan.


Requerimientos no funcionales/Non functional requirements:(aqui van los atributos de calidad que se relacionan con el caso de uso)

El modulo de citas debe ser visible desde cualquier dispositivo móvil.
La interfaz de usuario debe funcionar en cualquier navegador.
El tiempo de respuesta para guardar no debe sobrepasar los 10 segs.
Formato completo (Fully Dressed): como ejemplos de este tipo de formatos, visitar el sitio usecases.org

Elementos gráficos
El formato de casos de uso tiene una sección para prototipos gráficos (opcionales en algunas ocasiones) llamada “Pantallas del prototipo” en caso de que el sistema tenga GUI.

Por ejemplo el prototipo del ejemplo quedaría mas o menos así:



Una excelente herramienta para realizar prototipos es el proyecto pencil pencil es un proyecto open-source que incluye versiones para Linux, MacOSX y Windows.



Escritura del caso de uso en estilo esencial (Olvidarse de la GUI)
La idea de No considerar la interfaz de usuario sino concentrase en la intensión según el libro Writing effective use cases de Alistair Cockburn se deben de evitar los detalles de la GUI, recomienda hacer la narración a nivel de las intenciones del usuario y las responsabilidades del sistema suena lógico ya que el GUI cambia con más frecuencia que los procesos de negocio EBP (Elementary Business Process). La definición de EBP según el libro Applying UML and patterns de Craig Larman es:

Una tarea realizada por una persona en un lugar, en un instante, como respuesta aun evento del negocio, que añade un valor cuantificable para el negocio y deja los datos en un estado consistente.

Hay que ser claros lo esencial de los casos de uso son historias y narrativas, el producto de esta técnica son documentos de texto, los diagramas y prototipos son únicamente un complemento.
