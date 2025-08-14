---
lab:
  title: 'Laboratorio 2.1: Ingesta de un conjunto de datos'
---

# Módulo 2: Ingesta de datos en Dynamics 365 Customer Insights - Data

## Escenario de laboratorio: Contoso Coffee
Contoso Coffee fabrica cafeteras y café de gran calidad, que venden a través de canales, entre los que se incluyen sus nuevas tiendas minoristas Contoso en las mejores ubicaciones, proveedores de alimentos premium y el sitio web de Contoso Coffee. Contoso tiene previsto ampliar aún más sus ofertas con Contoso Cafés y una nueva cafetera conectada, que puede activar pedidos de recarga y alertar al servicio de Contoso sobre cualquier incidencia. Esta nueva oferta ayudará a la empresa a establecer relaciones directas con sus clientes y obtener más información sobre cómo los clientes consumen sus productos.

### Desafíos de Contoso Coffee
- **Relación transaccional:** su modelo de negocio existente significa que carecen de una relación directa con sus clientes.
- **Silos de datos:** no pueden ofrecer experiencias personalizadas de los clientes.

### Panorama de datos existente de Contoso
- **Datos de clientes fracturados:** al tener varios sistemas, Contoso tiene varios registros para la misma persona. Esto produce una experiencia inconexa del cliente que espera ser tratado como una persona independientemente del canal en el que realice transacciones.
- **Varias plataformas:** la arquitectura de Contoso ha evolucionado a través de adquisiciones y sistemas heredados, lo que significa que los datos pueden residir en no solo sistemas diferentes, sino en plataformas distintas en varias nubes y en el entorno local.
- **Datos que no son de cliente:** Contoso está sacando correlaciones entre los datos que no son de los clientes y el impacto que tienen en las experiencias de los clientes, incluidos los datos de terceros, como los datos meteorológicos.

### Proyecto Customer Insights de Contoso Coffee
Te han seleccionado como el jefe de proyecto para la implementación de Dynamics 365 Customer Insights en Contoso Coffee. Como eres un jefe de proyecto con experiencia, elaboras el siguiente plan:
1. Crear un entorno de Customer Insights.
2. Ingesta de datos de orígenes de datos de máxima prioridad de la empresa:
   - Punto de venta (PDV)
   - Datos de fidelización
   - Clientes de comercio electrónico
   - Compras en la web
3. Configurar un perfil unificado del cliente a partir de los datos ingeridos

## Introducción del módulo

### Requisitos previos del laboratorio:
Para poder comenzar este ejercicio, debes haber completado el laboratorio 0 para configurar el entorno.

### Ingesta y unificación de datos
Como jefe de proyecto de Contoso Retail, crearás un perfil unificado del cliente ingiriendo orígenes clave de datos de clientes y siguiendo el proceso de asignación, coincidencia y combinación. En este laboratorio, ingeriremos los datos. En el siguiente laboratorio, unificaremos los datos.

**Tiempo aproximado para completarlo:** 45 minutos

### Familiarizarte con Customer Insights - Data
En esta tarea, explorarás el entorno de demostración preconfigurado para familiarizarte con la navegación por la aplicación Customer Insights – Data.
1. Inicie sesión en Customer Insights - Data en https://home.ci.ai.dynamics.com si aún no has iniciado sesión.
2. En el selector Entorno de la esquina superior derecha, confirma que está seleccionada **Prueba de marketing**.
3. Explora las opciones de menú de la izquierda para familiarizarte con la navegación:
   - **Inicio:** página principal
   - **Clientes:** mira las tarjetas de los perfiles unificados del cliente (aún no podrás ver esto; es necesario ingerir y unificar los datos primero).
   - **Datos > Orígenes de datos:** ingiere datos demográficos, transaccionales o de comportamiento en silos. Asigna, haz coincidir y combina en un perfil unificado del cliente. Mira las entidades y define los tipos de actividad y sus relaciones con los clientes.
   - **Datos > Enriquecimiento:** ve más allá de tu perfil unificado y enriquece los perfiles de cliente con datos de propiedad de Microsoft. Aprovecha los datos sobre afinidades para cientos de marcas y docenas de categorías de intereses. Estas afinidades se extraen de perfiles que pueden ser similares a los de tus clientes.
   - **Información > Segmentos, medidas y predicciones:** mira segmentos, configura medidas y usa modelos de predicción predefinidos (o crear los tuyos). (Aún no podrás ver esta sección).
   - **Configuración**: administra roles, permisos, API y destinos de exportación para los segmentos de clientes.

## Ejercicio 1: Ingesta de datos
En este ejercicio te familiarizarás con la ingesta de datos de varios orígenes. Como jefe de proyecto de Contoso Retail, ya has identificado que los orígenes de los datos principales incluyen datos obtenidos de clientes de comercio electrónico, compras en línea, compras realizadas en los puntos de venta de las tiendas y datos del esquema de la tarjeta de fidelización de Contoso Retail.

### Tarea 1: Ingerir datos de clientes de una plataforma de comercio electrónico
1. Inicia sesión en Customer Insights en http://home.ci.ai.dynamics.com y comprueba que está seleccionada la **Prueba de marketing** en el menú desplegable de la esquina superior derecha.
2. En Customer Insights, amplía la opción **Datos** situada en el menú de navegación izquierdo y selecciona **Orígenes de datos.**
3. Selecciona **+ Agregar un origen de datos**. Mira los métodos disponibles de ingesta de datos. Para este laboratorio, elige Microsoft Power Query, denomina el origen *eCommerce* y selecciona **Siguiente.**
4. Se mostrará una vista de los orígenes de datos de Power Query que Customer Insights puede ingerir. Toma nota de los tipos de conectores disponibles. Selecciona el conector **Texto o CSV**.
5. Escribe https://aka.ms/CI-ILT/Contacts en Ruta de acceso o dirección URL del archivo y selecciona **Siguiente.** Los datos pueden tardar unos instantes en mostrarse.cargarse.
6. Ahora deberías ver los datos del origen en formato de tabla. Selecciona **Transformar datos** para configurar los tipos de datos y los formatos de los datos que ingieres.
7. Verás que el encabezado de la columna ha aparecido en la primera fila de los datos. Para corregirlo, selecciona **Transformar > Usar la primera fila como encabezados** en la pestaña Inicio o selecciona la pestaña **Transformar** y, después , **Usar la primera fila como encabezados.**
8. Dado que hemos ingerido datos de un origen de Texto o CSV, todas las columnas han adoptado de forma predeterminada un tipo de datos de "Texto". Para ingerir y modelar correctamente los datos, podemos establecer el tipo de datos de las columnas sin texto. Para cambiar el tipo de datos, selecciona el icono ABC del encabezado de la columna. Actualiza el tipo de datos para estas columnas:
   - **DateOfBirth**: fecha
   - **CreatedOn:** fecha
   - **Income:** moneda
9. Comprueba que el campo Nombre del panel de configuración de consulta está establecido en Contactos. Selecciona **Siguiente**. Seleccione **Guardar**.
   - Enhorabuena. Has creado correctamente el primer origen de datos con un conjunto de datos. Continuaremos con la importación del siguiente conjunto de datos en la próxima tarea.

## Tarea 2: Ingerir datos de compras en línea
En esta tarea, ingeriremos los datos de las compras en línea, que representan las compras realizadas a través del sitio web de Contoso Coffee.

1. En Customer Insights, amplía la opción **Datos** situada en el menú de la izquierda y selecciona **Orígenes de datos.**
2. En *Administrado por mí (1),* selecciona el conjunto de datos **eCommerce** y selecciona **Editar**. Selecciona **Siguiente**.
   - **Nota:** si los datos todavía se están actualizando, deberás esperar a que finalice el proceso antes de editarlos. Puedes ir directamente a la tarea 3 y volver a la tarea 2 después de haber completado las tareas 3 a 5.
3. Deberías aparecer la vista de Power Query de eCommerce Contacts que ingeriste en la Tarea 1. En la pestaña **Inicio**, selecciona **Obtener datos.**
4. Se mostrará una vista de los conectores de orígenes de datos que Customer Insights puede ingerir. Selecciona el conector **Texto o CSV.**
5. Escribe https://aka.ms/CI-ILT/OnlinePurchases en la ruta de acceso o dirección URL del archivo y selecciona **Siguiente**. Selecciona **Crear.**
6. Como antes, selecciona **Transformar** y **Usar la primera fila como encabezados.**
7. Actualiza los tipos de datos de las columnas siguientes:
   - **PurchasedOn**: fecha
   - **TotalPrice**: moneda
8. Denomina esta consulta *Purchases* y selecciona **Guardar.**

## Tarea 3: Ingerir datos de clientes del esquema de fidelización
1. En Customer Insights, amplía la opción **Datos** situada en el menú de la izquierda y selecciona **Orígenes de datos.**
2. Selecciona **+Agregar un origen de datos** y elige **Microsoft Power Query** como método de importación. Denomina el origen *Loyalty* y luego selecciona **Siguiente.**
3. Selecciona el conector **Texto o CSV**.
4. Escribe https://aka.ms/CI-ILT/LoyaltySchemeCustomers en Ruta de acceso o dirección URL del archivo, selecciona **Siguiente** y, después, selecciona **Transformar datos.**
5. Como antes, selecciona Transformar y, después, Usar la primera fila como encabezados.
6. Actualiza el tipo de datos para estas columnas:
   - **DateOfBirth**: fecha
   - **RewardsPoints**: número entero
   - **CreatedOn:** fecha
7. Cambia el nombre de esta consulta a *Customers* en el panel Configuración de consulta y selecciona **Siguiente.**
8. En la pantalla de actualización, selecciona **Guardar.**

## Tarea 4: Ingerir datos de clientes de las compras de punto de venta
1. En Customer Insights, amplía la opción **Datos** situada en el menú de navegación izquierdo y selecciona **Orígenes de datos.**
2. Selecciona **+ Agregar un origen de datos**, elige **Microsoft Power Query** y denomina el origen *PoS* y, después, selecciona **Siguiente.**
3. Selecciona el conector **Texto o CSV**.
4. Escribe https://aka.ms/CI-ILT/POSPurchases en la Ruta de acceso o dirección URL del archivo. Selecciona **Siguiente** y, después, selecciona **Transformar datos.**
5. Como antes, selecciona **Transformar** y, después, **Usar la primera fila como encabezados.**
6. Actualiza el tipo de datos para estas columnas:
   - **PurchasedOn**: fecha
   - **TotalPrice**: moneda
   - **RewardPointsAdded:** número entero
7. En el campo **Nombre** del panel Configuración de consulta, cambia el nombre de la consulta a *Purchases.* Selecciona **Siguiente**.
8. En la pantalla de actualización de datos, selecciona **Guardar.**

## Tarea 5: Ingerir datos de clientes de las opiniones del sitio web
1. En Customer Insights, amplía la opción **Datos** situada en el menú de navegación izquierdo y selecciona **Orígenes de datos.**
2. Selecciona **+ Agregar un origen de datos**. Elige **Microsoft Power Query** y denomina el origen *Website* y, después, selecciona **Siguiente.**
3. Selecciona el conector **Texto o CSV**.
4. Escribe https://aka.ms/CI-ILT/WebReviews en la Ruta de acceso o dirección URL del archivo. Selecciona **Siguiente** y, después, selecciona **Transformar datos.**
5. Como antes, selecciona **Transformar** y, después, **Usar la primera fila como encabezados.**
6. Actualiza el tipo de datos para estas columnas:
   - **ReviewRating**: número entero
   - **ReviewDate**: fecha
7. En el campo **Nombre** del panel Configuración de consulta, cambia el nombre de la consulta a *Reviews.* Selecciona **Siguiente**.
8. En la pantalla Actualizar configuración, selecciona **Guardar.**
