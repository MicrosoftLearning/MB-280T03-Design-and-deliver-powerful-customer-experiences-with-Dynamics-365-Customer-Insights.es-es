---
lab:
  title: 'Laboratorio 3.2: Crear un correo electrónico'
---

# Ruta de aprendizaje 3: Administración de clientes y recursos en Dynamics 365 Customer Insights - Journeys

## Laboratorio 3.2: Crear un correo electrónico

### Descripción general del laboratorio

#### Escenario
Para esta campaña, el equipo de marketing planea hacer una gran blitz alrededor de su máquina de café inteligente más reciente. Planean enviar una serie de tres correos electrónicos. El primer correo electrónico promoverá la cafetera inteligente de Contoso. El segundo correo electrónico está pensado para animar a los propietarios del Airpot normal a actualizar a la nueva máquina inteligente. El tercer correo electrónico es un recordatorio sobre el nuevo lanzamiento del producto. 

### Descripción general del laboratorio
Este laboratorio consta de tres ejercicios:
1. En este ejercicio, creará un correo electrónico mediante una plantilla de correo electrónico.
2. En este ejercicio, creará un correo electrónico copiando otro correo electrónico.
3. En este ejercicio, creará un correo electrónico copiando otro correo electrónico.

### Qué necesitarás:
- Un equipo con un entorno Dynamics 365 Customer Insights - Journeys

## Ejercicio: Crear una página de marketing
### Tarea 1: Crear una nueva plantilla de correo electrónico
1. Inicia sesión en Dynamics 365 Customer Insights - Journeys. Asegúrate de que te encuentras en el área Recorridos en tiempo real.
2. Vaya a **Correos electrónicos** en el grupo Canales.
3. Haga clic en **Nuevo** para crear un activo nuevo:
4. En la galería de plantillas, desplácese hacia abajo hasta la **sección Diseños** . sSelect 1-2 column (Seleccionar **1-2 columna** ) y **Select (Seleccionar).**
5. En la esquina superior izquierda, cambie el nombre del correo electrónico de *Correo electrónico 1* a *Correo electrónico de campaña de máquina inteligente.* (Al mantener el puntero sobre **Correo electrónico 1** en la esquina superior izquierda, debería poder escribir en ese cuadro de texto).
6. Seleccione el **cuadro** From Name/Subject (Desde nombre/asunto) en el diseñador para mostrar los detalles del encabezado Correo electrónico.
   - Escriba lo siguiente en el Asunto: "Finalmente, una cafetera que me obtiene".
   - Seleccione **Contoso Coffee** como remitente (si aún no lo está). El nombre del origen y el correo electrónico desde deben rellenarse y deben ser de solo lectura.
7. Busque el **menú Cuadro de herramientas** en el extremo derecho, que se mostrará como una serie de iconos. Al mantener el puntero sobre los iconos, se mostrará el nombre de cada pestaña. Seleccione la **pestaña Tema** , que tiene el aspecto de un pincel.
   - **Nota:** Los detalles de esta sección afectan a todo el correo electrónico. Si agrega nuevos elementos de texto al correo electrónico, el valor predeterminado será la fuente, el tamaño y el color que se muestran aquí. A continuación, puede actualizar esos elementos según sea necesario.
   - Cambie la Familia de fuentes a Segoe UI.
   - Cambie el Color del texto del cuerpo a #404040.
   - Cambie el fondo** del **correo electrónico a: #CCCCCC.
8. En el propio correo electrónico, busque la primera sección y selecciónela. Aparecerá una pestaña Editar diseño. Cambie el color de fondo sección a un tono de gris.

## Tarea 2: Actualizar imágenes
En esta tarea, actualizaremos el logotipo.

1. Seleccione la imagen en la primera sección del diseñador.
2. A la derecha, haga clic en la imagen del marcador de posición. Seleccione **Reemplazar imagen** y, a continuación, elija **Examinar biblioteca.**
3. Seleccione el **logotipo** de Contoso y haga clic en **Seleccionar.**
4. Reemplace el texto Alternativo por *el logotipo* de Contoso.
5. Seleccione la **lista desplegable Vincular a** y, a continuación, seleccione **DIRECCIÓN URL**. Escriba *www.contoso.com.*
6. En la sección Tamaño y alineación, si el ancho automático está activado, use el botón de alternancia para desactivarlo. Escriba *150px* para el ancho. La otra dimensión se actualizará automáticamente.
7. A continuación, actualizaremos la segunda imagen en el correo electrónico. Seleccione la imagen de la sección debajo del logotipo.
8. Seleccione **Reemplazar imagen** y **Examinar biblioteca.**
9. Seleccione la **imagen hero-page.jpg** . Haga clic en **Seleccionar**.

## Tarea 3: Actualizar un titular mediante la personalización
En esta tarea, actualizaremos un titular para reflejar el nombre del contacto del destinatario.
1. Vaya a la sección de texto debajo del logotipo y selecciónela.
2. Coloque el cursor al principio del texto del encabezado y haga clic en **Personalización** en la barra de herramientas de la parte superior del correo electrónico. Seleccione **Nombre** en la lista desplegable. Asegúrese de que **el contacto** está seleccionado y seleccione **Elegir.**
3. Agregue una coma y un espacio después de {{Firstname}}.
4. Cambie el texto del marcador de posición a: "Tenemos las pausas de café cubiertas".
5. Resalte el texto, conversión en negrita y cambie el tamaño de fuente a *26.*
6. Cambiar "Personalizar el correo electrónico..." a "La nueva cafetera airpot XL intelligent es como tener su propio barista personal".
7. Resalte el texto Apellidos y, a continuación, cambie el tamaño de texto a *24*.

## Tarea 4: Diseñar el resto del correo electrónico
1. Seleccione la sección de dos columnas debajo del texto. Cambie el color de fondo sección a un tono azul.
2. En la columna izquierda, seleccione el marcador de posición Imagen y haga clic en **Reemplazar imagen.** Seleccione **Examinar biblioteca** y seleccione **coffee-machine.jpg.** Haga clic en **Seleccionar**.
3. Reemplace el texto Alt por "Cafetera". (Si el panel para editar la imagen no aparece inmediatamente, puede encontrar las propiedades de la imagen como el icono inferior en la **Menú cuadro de herramientas** .
4. En **Vínculo al** campo, seleccione **DIRECCIÓN URL.** Escriba https://dynamics.microsoft.com/.
5. En la sección Tamaño y alineación, desactive El ancho **automático.** Cambie el ancho a *150px* y deje que el otro conjunto de dimensiones se establezca automáticamente.
6. En la columna derecha debajo del encabezado secundario, seleccione el marcador de posición Imagen y haga clic en **Reemplazar imagen.** Seleccione **Examinar biblioteca** y seleccione **barista.jpg**. Haga clic en **Seleccionar**.
7. Reemplace el texto Alt por *Barista.*
8. En Vínculo al campo, seleccione DIRECCIÓN URL. Escriba https://dynamics.microsoft.com/.
9.  Seleccione la sección con los iconos sociales. Cambie el color de fondo sección a un tono de gris.
10. Seleccione la sección con la información de copyright. Actualice los derechos de autor de *2022 Company Inc.* a *2024 Contoso Coffee.*
11. Realice cualquier otro cambio según sea necesario. No dude en ser creativo y usar cualquier experiencia de diseño que tenga. ¿Qué encuentras cuando recibes un correo electrónico de marketing?

## Tarea 5: Guardar y probar el correo electrónico
16. En la barra de herramientas, haga clic en **Guardar**.
17. Seleccione **Vista previa y prueba.**
18. Haga clic en **Datos de ejemplo**. En el panel Personalización de vista previa, escriba el nombre de un contacto que creó. Seleccione el contacto para ver el cambio de personalización.
19. Vuelva a la **pantalla Vista previa y prueba** . Obtenga una vista previa del correo electrónico en todos los tamaños de pantalla.
20. Haga clic en la flecha de avance para continuar. Ejecute el **comprobador** de accesibilidad para ver si hay otros problemas en el correo electrónico. Mitigue cualquier otro problema que se ajuste.
21. En la barra de herramientas, haga clic en **Listo para enviar.**

### Ejercicio 2: Creación de un correo electrónico copiando un correo electrónico

## Tarea 1: Crear un correo electrónico a los clientes existentes
1. Inicia sesión en Dynamics 365 Customer Insights - Journeys. Asegúrate de que te encuentras en el área Recorridos en tiempo real.
2. Vaya a **Correos electrónicos** en el grupo Canales.
3. Abra el correo electrónico que creó en la tarea 1.
4. En la barra de comandos, haga clic en la **flecha** desplegable situada junto a Guardar. Elija **Guardar como.**
5. En el menú Crear rápido de la derecha, asigne un nombre al correo electrónico Actualizar correo electrónico *de Airpot.*
6. En el campo Asunto, escriba "¿Es hora de una actualización?"
7. Haga clic en **Guardar y cerrar**. Aparecerá un elemento emergente que indica *Que se guardaron* los cambios. Haga clic en **Ver registro** para abrir el nuevo correo electrónico. (También puede volver a **Correos electrónicos** y abra **Actualizar correo electrónico de Airpot).**
8. En el diseñador, cambie el texto del encabezado a: "{{Firstname}}, coffee your way, at your dedo".
9. Cambie la copia debajo del encabezado a: "El pedido de café es tan único como usted. Tiempo para probar nuestra nueva cafetera airpot smart."
10. Seleccione la siguiente sección de dos columnas. Cambie el panel de diseño de  a .
    - En la columna izquierda, realice las siguientes actualizaciones:
      - Quitar el texto.
      - Eliminar el botón
    - En la columna derecha, realice las siguientes actualizaciones:
      - Quite la imagen
      - Cambie el texto a: "Half-caf Americano, or double shot latte? Sin embargo, decide alimentar su día, Contoso Coffee le ha cubierto". ‎ 
      - Cambie el tamaño de fuente a 16 y cursiva.
11. Botón para actualizar el nivel
    - Haz clic en el botón .
    - Cambie Vínculo a dirección URL.
    - Escriba https://dynamics.microsoft.com/.
    - Cambie el texto del botón para *EXPLORAR LA NUEVA MÁQUINA INTELIGENTE.*
    - Expanda **Tamaño y alineación.** Cambie Ajustar al texto a **Desactivado.** Cambie el Ancho a 10 px.
12. En la barra de herramientas, haga clic en **Guardar**.
13. Vista previa del correo.
14. a continuación, haga clic en "Comprobar". Corrija cualquier error, si es necesario.
15. En la barra de herramientas, haga clic en **Listo para enviar.**

### Tarea 2: Crear un correo electrónico de campaña de seguimiento
1. Inicia sesión en Dynamics 365 Customer Insights - Journeys. Asegúrate de que te encuentras en el área Recorridos en tiempo real.
2. Vaya a **Correos electrónicos** en el grupo Canales.
3. Abra el correo electrónico que creó en la tarea 2.
4. En la barra de comandos, haga clic en la flecha desplegable situada junto a **Guardar**. Elija **Guardar como.**
5. En el menú Creación rápida de la derecha, asigne un nombre al aviso *de campaña inteligente de máquina inteligente.*
6. En el campo Asunto, escriba "¿Ha visto las noticias?"
7. Haga clic en **Guardar y cerrar**. Aparecerá un elemento emergente en la esquina superior derecha que indica Que se guardaron los cambios. Haga clic en **Ver registro** para abrir el nuevo correo electrónico. (También puede ir a la lista Correos electrónicos y abrirlo **.Aviso de campaña de** máquina inteligente).
8. Cambie el texto del encabezado a: "El nuevo Airpot Smart Machine: disponible este otoño!"
9. Cambie la copia debajo del encabezado a: "Nuestra nueva máquina inteligente airpot es una nueva manera de hacer café. Obtenga más información sobre la primera cafetera de su tipo hoy."
10. Quite la sección de dos columnas.
11. En la barra de herramientas, haga clic en **Guardar**.
12. Vista previa del correo.
13. a continuación, haga clic en "Comprobar". Corrija cualquier error, si es necesario.
14. En la barra de herramientas, haga clic en **Listo para enviar.**

