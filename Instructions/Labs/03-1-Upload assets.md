---
lab:
  title: 'Laboratorio 3.1: Carga de recursos'
---

# Módulo 3: Administración de clientes y recursos en Dynamics 365 Customer Insights - Journeys

## Laboratorio 3.1: Carga de recursos

### Descripción general del laboratorio

#### Escenario
Contoso Coffee vende cafeteras de nivel industrial y para consumidores a los propietarios de empresas de café que usan cafeteras Contoso en sus tiendas individuales; empresas que tienen cafeteras Contoso en sus oficinas corporativas; y clientes individuales que usan cafeteras Contoso en sus hogares. Este año, la empresa lanza un nuevo producto llamado Airpot XL Smart Coffee Machine. Planea comercializar este nuevo producto tanto para empresas como para individuos.

El equipo de marketing decide preparar una campaña de venta cruzada para animar a los clientes actuales a considerar la posibilidad de cambiar a su nueva cafetera inteligente. Tiene previsto enviar una serie de correos electrónicos con una llamada a la acción para que el cliente haga clic en un vínculo que desencadenará una llamada telefónica de un representante de ventas. Además, planea ejecutar esta campaña durante 2 meses.


Para esta campaña, el Coordinador de marketing deberá:
- Cargar los recursos de marketing para usarlos en las campañas de correo electrónico.
- Crear los correos electrónicos de marketing para enviar a los clientes.
- Crear el recorrido que automatizará el envío del contenido de la campaña.

Para empezar, el Coordinador de marketing debe cargar los recursos digitales que se usarán en la campaña. También deben cargar los nuevos contactos de ventas que la empresa ha adquirido recientemente y actualizar los detalles de los contactos y las cuentas existentes.

## Descripción general del laboratorio
Este laboratorio consta de cuatro tareas:
1. En la primera tarea, cargarás los archivos de imagen que se usarán en los correos electrónicos de marketing. Estos archivos se cargarán en la biblioteca de recursos en tiempo real.
2. En la segunda tarea, actualizarás los detalles de los contactos existentes en Dynamics 365 Customer Insights - Journeys.
3. En la tercera tarea, crearás una plantilla de tarea que se usará en el recorrido.
4. En la cuarta tarea, configurarás el perfil de marca predeterminado que se usará en los recursos de marketing (como los correos electrónicos).

### Qué necesitarás:
- Un equipo o una máquina virtual con un entorno Dynamics 365 Customer Insights - Journeys
- Los archivos de imagen que se usarán en el contenido de marketing. Estos se pueden encontrar en el host de laboratorio autorizado o en el archivo **MB-280T03-Assets.zip** en la carpeta Instructions/Labs/Media del repositorio de GitHub. Pregunta al instructor si tienes problemas para encontrarlos.

### Ejercicio 1: Preparar los recursos de marketing 
## Tarea 1: Cargar las imágenes en la biblioteca de recursos
1. Descarga los archivos de imagen de los documentos de recursos. Extrae el archivo zip a una carpeta en tu escritorio.
2. Inicia sesión en Dynamics 365 Customer Insights - Journeys con tus credenciales de administrador.
3. De forma predeterminada, debes estar en el área Recorridos en tiempo real. Comprueba que estás en el área Recorridos en tiempo real abriendo el selector de área en la parte inferior izquierda de la pantalla.
4. En el menú de la izquierda, a la sección Recursos. Selecciona **Biblioteca**. Selecciona el botón **+ Nuevo** para abrir la ventana cargar archivos.
5. Selecciona **Cargar archivos**, busca los archivos de imagen en el equipo local y selecciónalos.
6. Mientras la ventana de carga está abierta, agrega una etiqueta de logotipo a contosologo.png. (Comienza escribiendo el logotipo en el cuadro de texto debajo del nombre del archivo de imagen. Después de escribir el *logotipo*, selecciona lo que acabas de escribir. Se agregará una etiqueta debajo del nombre de archivo).
7. Selecciona **Cargar**. Asegúrate de que se han cargado los archivos de imagen cargados; aparecerá una marca de verificación verde con Listo para cada archivo. (El archivo puede tardar varios minutos en cargarse). Selecciona **Cerrar.**
8. Con el cuadro de búsqueda Filtrar por palabra clave, escribe *con* y pulsa entrar. De forma predeterminada, este filtro busca por el nombre de archivo. Comprueba que contosologo.png aparece en los resultados de la búsqueda.

Estos archivos estarán ahora disponibles para que los usuarios los incorporen a sus operaciones de marketing.

### Tarea 2: Actualizar los contactos existentes
1. Inicia sesión en Dynamics 365 Customer Insights - Journeys. Asegúrate de que te encuentras en el área Recorridos en tiempo real.
2. En el panel de navegación izquierdo, selecciona **Contactos** en el grupo de Audiencia.
3. Abre el contacto **Alva Tharaldsen.**
   - En Nombre de cuenta, selecciona **Bellows College**. A continuación, ve al registro de cuenta de Bellows College.
   - Desplázate hacia abajo hasta la subcuadrícula **Contactos**. Aquí se enumerarán todos los contactos asociados con Bellows College. Haz clic en los puntos suspensivos verticales de la parte superior de la subcuadrícula. Haz clic en **Seleccionar** y usa las casillas para seleccionar todos los contactos de la lista a la vez.
   - En la parte superior de la subcuadrícula Contactos, selecciona los **puntos suspensivos verticales.** Después, selecciona **Editar.**
   - En la pestaña Detalles, busca el campo Notas personales. Escribe "Airpot owner" en el campo. Selecciona **Guardar**.
   - Selecciona un contacto distinto a Alva. Ve a la pestaña **Detalles**. Comprueba que "Airpot owner" aparece en el campo Notas personales.
4. Vuelva a la entidad **Contactos** en el grupo de Audiencia. 
5. Establece un filtro en Nombre de empresa:
   - Selecciona la **flecha desplegable** situada junto a Nombre de empresa. Selecciona **Filtrar por.** Elige **Equals** y, a continuación, selecciona **Lucerne Publishing, Southridge Video** y **Wingtip Toys.** (Puedes seleccionar las cuentas seleccionando el nombre directamente de la lista o empezando a escribir el nombre y seleccionando el nombre cuando aparezca). Selecciona **Aplicar.**
   - Selecciona todos los contactos de esas 3 cuentas. (Puedes seleccionar la marca de verificación junto a Nombre completo en el encabezado de vista para seleccionar todos los contactos a la vez).
   - Selecciona **Editar** en la barra de comandos. Escribe lo siguiente:
     - **Dirección 1: Ciudad:** Bellevue
     - **Dirección 1: Estado o provincia:** Washington
     - **Detalles > Notas personales:** Airpot owner
     - Selecciona **Guardar**.
6. Cambia el filtro en Nombre de empresa:
   - Selecciona la **flecha desplegable** situada junto a Nombre de empresa. Selecciona **Borrar filtro**.
   - Vuelve a seleccionar la **flecha desplegable**. Selecciona **Filtrar por**. Selecciona **Adatum Corporation** y **Northwind Traders**. Selecciona **Aplicar**.
   - Selecciona todos los contactos de esas 2 cuentas.
   - Selecciona **Editar** en la barra de comandos. Escribe lo siguiente:
     - **Dirección 1: Ciudad:** Redmond
     - **Dirección 1: Estado o provincia:** Washington
     - **Detalles > Notas personales:** Airpot owner
     - Selecciona **Guardar**.
7. Cambia el filtro en Nombre de empresa:
   - Selecciona la **flecha desplegable** situada junto a Nombre de empresa. Selecciona **Borrar filtros.**
   - Vuelve a seleccionar la flecha desplegable y selecciona **Filtrar por**. Selecciona **Trey Research**, **The Phone Company** y **Wide World Importers.** Selecciona **Aplicar**.
   - Selecciona todos los contactos de esas 3 cuentas.
   - Selecciona Editar en la barra de comandos. Escribe lo siguiente:
     - **Dirección 1: Ciudad:** Seattle
     - **Dirección 1: Estado o provincia:** Washington
     - **Detalles > Notas personales:** Airpot owner
     - Selecciona **Guardar**.

### Tarea 3: Crear una plantilla de tarea
1. Inicia sesión en Dynamics 365 Customer Insights - Journeys con tus credenciales de administrador.
2. En el grupo **Recursos**, ve a **Plantillas de tareas**.
3. Selecciona **+ Nuevo**.
   - Nombre: Seguimiento del cliente.
   - Asunto: Upgrade from Airpot a Airpot XL Smart Coffee Machine
   - Tipo de programación: Retraso (en días).
   - Inicio de retraso: 0
4. En la sección Hora de inicio, selecciona **01** para la Hora. Deja Minuto en blanco.
4. Selecciona **Guardar y cerrar.**

### Ejercicio 4: Configurar el perfil de marca predeterminado
1. Inicia sesión en Dynamics 365 Customer Insights - Journeys. Cambia al área **Configuración**.
2. En el grupo **Involucración del cliente**, ve a **Perfiles de marca**.
3. Selecciona el **Perfil de marca predeterminado.**
4. Ve a la pestaña **Remitentes**. Debes ver el registro de remitente predeterminado en la subcuadrícula. 
5. Selecciona la pestaña Vínculos sociales. Rellena lo siguiente:
    - Dirección URL de LinkedIn: https://www.linkedin.com/company/contoso12345/about/
    - Dirección URL de Twitter: https://twitter.com/ContosoInc
    - Dirección URL de Facebook: https://www.facebook.com/Contoso-102137176602590/
6. Selecciona **Guardar y cerrar.**

