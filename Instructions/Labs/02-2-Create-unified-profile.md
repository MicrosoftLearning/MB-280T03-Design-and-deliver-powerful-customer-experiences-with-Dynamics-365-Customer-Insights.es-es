---
lab:
  title: 'Laboratorio 2.2: Creación de un perfil unificado del cliente'
---

# Laboratorio 2.2: Creación de un perfil unificado del cliente

## Ruta de aprendizaje 2: Creación de un perfil unificado del cliente en Dynamics 365 Customer Insights - Data

Después de haber introducido los datos sin procesar de los orígenes de datos en las entidades, comenzarás el proceso de asignación, coincidencia y combinación para crear un único perfil unificado del cliente. Para ello, se combinarán los datos de cada origen de perfil de cliente. Para completar este proceso, primero asignarás las entidades introducidas con respecto a un modelo estándar y seleccionarás la clave principal de cada una de las entidades perfiladas. Después de completar esto, crearás la regla de coincidencia que se usará para buscar coincidencias con los contactos de todas las entidades del cliente. Por último, la ejecución del proceso de combinación creará un solo conjunto de clientes únicos que tienen perfiles coincidentes de todas las entidades del cliente mediante las reglas de coincidencia. Tu objetivo es descubrir cuántos perfiles de clientes únicos tiene Contoso Retail en los diferentes orígenes de datos.

## Ejercicio 1: Unificar los datos

### Tarea 1: Asignar contactos a tipos de datos comunes
1. Inicia sesión en Customer Insights - Data en https://home.ci.ai.dynamics.com.
2. En el panel de navegación izquierdo, expande **Datos** y selecciona **Unificar.**
3. En la sección Datos de clientes, selecciona **Comenzar.**
4. En la pantalla **Describir los datos del cliente que se van a unificar**, selecciona **+ Comenzar.**
5. Selecciona las tablas que representarán el perfil de cliente. Esas tablas son:
   - Contacts (eCommerce)
   - Customers (Loyalty)
6. Selecciona **Aplicar**.
7. Ahora se mostrarán las asignaciones de la tabla de origen en comparación con los tipos de modelos estándar. Puedes revisar los tipos en la tabla.
8. Elige una "clave principal" para cada entidad que hayas introducido. La clave principal debe ser una referencia única. En eCommerce Contacts, selecciona **ContactId** como la clave principal.
9. Los datos de eCommerce Contacts contienen una columna denominada **Email Subscriber** que se asignará a un tipo incorrecto, Identity.Service.Email, debido al nombre. Abre el desplegable de esta columna y selecciona la opción vacía (nada/en blanco). Si no lo hacemos, el comportamiento predeterminado del sistema combinará este campo con el campo Correo electrónico, cosa que no queremos que suceda.
10. Selecciona **Loyalty Customers** en Tablas y establece **LoyaltyId** como la clave principal.
11. Selecciona **Guardar columnas de origen** en la esquina superior izquierda.
12. Selecciona el botón **Siguiente** y, después, vuelve a seleccionar **Siguiente** para omitir la comprobación duplicada y pasar al paso Reglas de coincidencia.

### Tarea 2: Especificar el orden de coincidencia
En la siguiente fase, deberás seleccionar el orden en el que combinar los perfiles. Podrás combinar atributos para garantizar que los perfiles unificados estén completos y la prioridad de los orígenes que se usarán para esos atributos.
1. Deberás seleccionar el origen de perfil más completo o preciso como origen principal (primero). Comprueba que **Contacts: eCommerce** es el origen principal (primero) (o muévelo si no lo está).
2. Selecciona la marca de verificación para **Incluir todos los registros.**
3. Comprueba que **Customers: Loyalty** es el segundo origen de la lista. Elige **Incluir todos** los registros.

### Tarea 3: Crear una regla de coincidencia
En esta tarea crearás una regla que se utilizará para combinar los registros. Las reglas pueden consistir de una condición (por ejemplo, basadas en el id.) o de varias condiciones (por ejemplo, FullName, PostCode, fecha de nacimiento, etc.). Para obtener más información sobre las reglas de coincidencia, consulta la documentación de Customer Insights.
1. Hay un indicador de advertencia en la **línea Customers: Loyalty**. Selecciona **+ Agregar regla** o selecciona el icono **+** de la derecha.
2. Agrega la primera condición con FullName:
   - Para la tabla Contacts: eCommerce, selecciona el campo **FullName**.
   - En la tabla Customers: Loyalty, selecciona el campo **FullName**.
   - Deja el desplegable Normalizar en blanco.
   - Establece el nivel de precisión en **Básico** mediante el campo desplegable.
   - Establece el valor de precisión en **Alto** mediante el control deslizante.
3. Especifica el nombre **FullName, Email** para la regla.
4. Selecciona **+ Agregar** y elige **Agregar condición** para agregar una segunda condición para la dirección de correo electrónico.
   - Para la tabla Contacts: eCommerce, selecciona el campo **Email**.
   - En la tabla Customers: Loyalty, selecciona el campo **Email**.
   - Deja el desplegable Normalizar en blanco.
   - Establece el nivel de precisión en **Básico.**
   - Establece el valor de precisión en **Alto.**
5. Selecciona **Listo.**
6. Selecciona **Siguiente,** **Siguiente** y **Crear perfiles de cliente.**

Customer Insights ahora hará coincidir los datos de clientes de tus orígenes de información de clientes con el fin de identificar cuántos perfiles de clientes únicos tendrías según tus reglas. Consultar la clase: ¿Cuántos clientes únicos tienes al combinar los conjuntos de datos?

### Tarea 4: Precisión
En la tarea 3, usamos la precisión Alta en la regla de coincidencia con el nombre completo. En esta tarea, ajustarás el nivel de precisión para crear un número mayor de coincidencias mediante la inclusión de coincidencias de una confianza inferior (lo que da lugar a un número inferior de perfiles únicos).

**Notas sobre la precisión:**
- Exacto en el lado derecho de la escala hará coincidir los registros en los que la condición tenga una coincidencia exacta. Selecciona uno de los otros niveles para que coincidan con los registros que no son idénticos al 100 %.
- Los casos de coincidencia alta en los que la precisión es más importante que el alcance, como un servicio financiero con un cliente específico.
- Los casos de coincidencia baja en los que lo contrario es cierto, como una campaña de marketing.
- El nivel Medio sirve como una opción intermedia.

1. En Customer Insights, expande **Datos** en el menú de navegación izquierdo. Selecciona **Unificar.**
2. En Reglas de coincidencia, selecciona **Editar.**
3. Expanda la regla **Customers: Loyalty** y selecciona el botón **Editar** para abrir el panel de condiciones **FullName, Email**.
4. En Condición 1, selecciona **Vista previa** y anota los valores. Mueve el control deslizante Precisión de la Condición 1 de **Alto** a **Bajo**. Selecciona **Listo.**
5. Selecciona **Siguiente**, **Siguiente** y **Crear perfiles de cliente.**
6. Espera hasta que se complete el proceso de coincidencia.
7. Una vez completado el proceso de coincidencia, haz clic en **Editar** en las reglas de coincidencia. Selecciona el **menú de puntos verticales** situado junto a la regla **FullName, Email** y selecciona **Vista previa** para ver los resultados de coincidencia y la puntuación. Esto muestra cómo Customer Insights hizo coincidir las tablas de datos en función de las reglas que has definido. Algunos perfiles se han creado con una menor confianza de coincidencia.
8. Cierra la vista previa y selecciona Editar. Selecciona el botón Vista previa debajo de Condición 1. Aquí puedes obtener una vista previa del número de registros no coincidentes y coincidentes para la condición FullName.
9. Selecciona **Vista previa de datos** en No coincidentes o Coincidentes para obtener una vista previa de las coincidencias. Observa cómo las puntuaciones altas tienen ortografía exacta, pero pueden coincidir incluso si el formato de nombre (Nombre, Apellidos/ Apellidos, Nombre) es diferente. Con las puntuaciones bajas, observa cómo se realizan las coincidencias incluso cuando los nombres no están escritos de forma idéntica.
10. Cierra el panel de vista previa de criterios y selecciona **Cancelar.**

Consultar la clase : ¿Cuántos perfiles de clientes únicos tienes ahora?

### Tarea 5: Unificar los campos de cliente
Esta es la última fase del proceso de unificación de datos. Tu objetivo es conciliar datos en conflicto y definir los atributos que se utilizarán en el perfil unificado del cliente. Un atributo combinado es un atributo que existe en más de un origen de datos y representa los mismos datos. Por ejemplo, puedes tener "Email Address" tanto en los orígenes de datos de clientes de eCommerce y clientes de Loyalty. Customer Insights intentará identificar los atributos que se van a combinar con los tipos de datos estándar definidos en el paso Campos de origen.

1. En Customer Insights, expande **Datos** en el menú de navegación izquierdo. Selecciona **Unificar.**
2. En vista Datos unificados, selecciona **Editar.**
3. En las columnas de cliente, observa cómo se han combinado los atributos de diferentes orígenes de datos que son del mismo tipo (por ejemplo, FirstName).
4. Expande el atributo combinado **FirstName**. Deberías ver que el atributo FirstName en eCommerce: Contacts es el número 1. Eso denota que, cuando tienes un perfil de cliente coincidente tanto en LoyaltyScheme como en eCommerce, FirstName que se toma de eCommerce: Contacts será el principal.
9. Selecciona **Siguiente** y luego selecciona **Crear perfiles de clientes.**
10. Espera a que finalice el proceso.

Felicidades. Has introducido, asignado, hecho coincidir y combinado y unificado correctamente datos de varios orígenes en Customer Insights para crear un perfil unificado del cliente que puede usarse para obtener información útil sobre toda tu base de clientes.

## Ejercicio 2: Buscar clientes
En este ejercicio, configuraremos los criterios de búsqueda y filtro para permitir que los usuarios de Customer Insights busquen perfiles unificados del cliente para que puedas extraer rápidamente información sobre un cliente específico o grupo de clientes.

### Tarea 1: Configurar las columnas de búsqueda e índice de filtros
1. En Customer Insights, selecciona **Clientes** en el menú de navegación izquierdo.
2. Selecciona **Índice de buscar y filtrar.**
3. Algunos campos específicos de búsqueda de clientes ya se agregan de forma predeterminada y puedes agregar más seleccionando **+ Agregar** en la barra de herramientas.
4. Asegúrate de que **CustomerId, FirstName, LastName, FullName, DateOfBirth, Email, PostCode, Headshot, ContactId (eCommerce_Contacts)** y **LoyaltyId** están seleccionados. Anula la selección de cualquier otro campo que esté activado. Selecciona **Aplicar**.
5. Seleccione **Guardar**.

### Tarea 2: Buscar un registro de cliente
1. En Customer Insights, selecciona **Clientes** en el menú de navegación izquierdo. Te debe aparecer un conjunto de tarjetas de cliente, que representa los perfiles unificados. Puedes expandir las tarjetas para obtener más información sobre el cliente u ordenar las tarjetas por varios campos. Para probarlo, selecciona **Expandir tarjetas** y **Ordenar por** en la barra de herramientas.
2. Puedes usar Buscar clientes para buscar atributos de texto relacionados con los perfiles unificados del cliente. (por ejemplo, la búsqueda de "24502" buscará en todos los atributos de texto y devolverá coincidencias y coincidencias parciales).

Usa la barra de búsqueda para responder a las siguientes preguntas:
- ¿Cuál es la fecha de nacimiento de Brian Gobble? (Busca Brian Gobble)
- ¿Qué cliente tiene el id. de tarjeta de fidelidad LOYID_5707? (Busca LOYID_5707)
- ¿Qué cliente tiene el código postal 24502? (Busca 24502)
