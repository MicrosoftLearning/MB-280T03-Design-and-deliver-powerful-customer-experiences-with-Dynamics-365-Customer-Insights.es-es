---
lab:
  title: 'Laboratorio 4.1: Creación de un recorrido basado en desencadenadores'
---

# Ruta de aprendizaje 4: Creación de recorridos

## Laboratorio práctico 4.1: Creación de un recorrido basado en desencadenadores 

### Descripción general del laboratorio

#### Escenario
Ahora que hemos creado los 3 correos electrónicos, es el momento de crear un recorrido para enviarlos a nuestros clientes. Enviaremos el primer correo electrónico a nuestros clientes para informarles sobre la próxima cafetera Airpot Smart Machine.

Los clientes que interactúen con este correo electrónico se dividirán en dos secciones: clientes que ya poseen un modelo antiguo de Airpot y los clientes que no tienen uno. A los propietarios de Airpot existentes, les enviaremos un correo electrónico animándoles a actualizar. Si interactúan con el vínculo en este correo electrónico, haremos que un vendedor se ponga en contacto con ellos directamente.

Los propietarios existentes que no hagan clic en el vínculo recibirán otro correo electrónico con publicidad del producto. Este correo electrónico también se enviará a los propietarios que no tienen un Airpot.


### Qué necesitarás:
- Un equipo con un entorno Dynamics 365 Customer Insights - Journeys

## Ejercicio 1: Crear un recorrido en tiempo real

### Tarea 1: Crear un recorrido
1.  Inicia sesión en Dynamics 365 Customer Insights - Journeys.
2.  Ve al área de trabajo **Recorridos en tiempo real**.
3.  En **Involucración**, selecciona **Recorridos.**
4.  Haz clic en **+ Nuevo recorrido** en la barra de comandos. Si se te pide que uses Copilot para crear el recorrido, selecciona **Omitir y crear desde cero.**
5.  En **Nombre del recorrido**, escribe *Airpot Smart Machine Launch Campaign.*
6.  En **Elegir tipo de recorrido**, selecciona **Basado en desencadenadores.**
7.  En **Elegir un desencadenador**, busca y selecciona **Vínculo de correo electrónico en el que se ha hecho clic.**
8.  En **Elegir un correo electrónico,** busca y selecciona tu **correo electrónico de Smart Machine Campaign.**
9.  Haga clic en **Crear**.

### Tarea 2: Configurar la entrada del recorrido
1. Ve a la sección **configuración del recorrido**, que se expandirá en el lado derecho de la pantalla. La sección **Entrada** debe estar abierta.
2. Deja **Excluir por segmentos** en blanco.
3. En la sección **Repetir**, selecciona Inmediatamente.
4. En la sección **Zona horaria**, elige la zona horaria.
5. En **Inicio,** selecciona hoy. Establece el tiempo en 15 minutos a partir de ahora. (Puede escribir directamente en este campo).
6. En **Fin,** selecciona mañana.

### Tarea 3: Configurar el objetivo del recorrido
1.  Ve a la configuración del recorrido a la derecha, que tendrá un aspecto similar a una lista de iconos. Mantén el puntero sobre cada icono para ver el nombre de cada pestaña. Selecciona la sección **Objetivo**.
2.  En *El objetivo de este recorrido es*, selecciona **Enviar una notificación general.**
3.  En *El objetivo se cumple cuando,* selecciona **Una persona haga clic en al menos un vínculo.**
4.  En *La cantidad de personas necesarias,* especifica *50.* Deja el porcentaje seleccionado.

### Tarea 4: Agregar una rama de atributo
1. En el diseñador de recorridos, haz clic en el **icono más (+)** en el icono **Correo electrónico en el que se hecho clic.**
2. Selecciona **Rama de atributo** en la sección *Condiciones*.
3. En **Nombre para mostrar** a la derecha, escribe *Already owns airpot.*
4. Selecciona **Rama 1**. En Nombre para mostrar, escribe *Owns airpot.*
5. Selecciona **Agregar condiciones.**
6. aEn **Elegir un atributo**, busque **Descripción (descripción)** en Contacto.
7. Cambia el valor de Equals a Contains.
8. En **Valor,** escribe *Airpot.*
9. Vuelve al diseñador de recorridos. Haz clic en el **icono más (+)** en Rama 1.
  - Selecciona **Correo electrónico**.
  - En **Seleccionar correo electrónico,** elige **Upgrade Airpot Email.**
10.  Haz clic en el **icono de más (+)** en el icono Enviar un correo electrónico.
  - Selecciona **Esperar desencadenador.**
  - En **Elegir un tipo de condición de rama**, selecciona **El mensaje anterior obtiene una interacción.**
  - En **Elegir una interacción**, selecciona **Se ha hecho clic en el vínculo del correo electrónico.**
  - En **¿Cuál es el límite de tiempo?,** escribe 10 minutos.
11. En la ruta de acceso **Sí**, haz clic en el **icono más (+).**
  - En la sección Actividades, selecciona **Tarea**.
  - En Elegir una plantilla, selecciona **Seguimiento con el cliente.**
  - El asunto y Asignar a se rellenarán automáticamente.
  - Cambia **Después** de *2 semanas.*
12. En la ruta de acceso **No** correspondiente (debajo de la rama si/entonces se ha hecho clic en el vínculo del correo electrónico), haz clic en el **icono más (+).**
  - Selecciona **Enviar un correo electrónico**.
  - En **Seleccionar correo electrónico,** elige **Smart Machine Campaign Reminder.**
13. Vuelve al diseñador de recorridos. Busque el icono de **Atributo**. Ahora configuraremos la rama **No**. A los clientes que aún no poseen un Airpot, les enviaremos el tercer correo electrónico.
  - Selecciona el signo **+** en **Otros.**
  - Selecciona **Correo electrónico**.
  - En Seleccionar correo electrónico, selecciona **Smart Machine Campaign Reminder.**
14. **Guarda** el recorrido.
15. Revisa el recorrido. Realiza los cambios finales.
16. Haz clic en **Publicar**. Espera a que se publique el recorrido.
