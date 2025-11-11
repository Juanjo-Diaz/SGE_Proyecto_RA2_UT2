# Manual de Odoo — Juan José Díaz Ruiz
**Reto:** Manual_Odoo_JuanJose_DiazRuiz  
**Proyecto:** Proyecto_RA2_UT2  
**Fecha:** 2025 10 8


# Índice

1. [Introducción](./02-introduccion.md)
2. [Instalación y prueba](./03-instalacion.md)
3. [Ajustes generales](./04-ajustes_generales.md)
4. [Integración con Gmail](./05-integracion_gmail.md)
5. [Contactos](./06-contactos.md)
6. [Calendario y Citas](./07-calendario_y_citas.md)
7. [Proyectos](./08-proyectos.md)
8. [Documentos, Firma e Información](./09-documentos_firma_info.md)
9. [Ediciones y costes](./10-ediciones_y_costes.md)
10. [Tips & Checklist](./11-tips_y_checklist.md)
11. [Referencias](./99-referencias.md)


# 02 — Introducción


> **Objetivo:** Entender qué es Odoo, por qué elegirlo y qué encontrará el lector en este manual práctico.

Odoo es una suite empresarial modular que agrupa aplicaciones para gestionar CRM, ventas, facturación y contabilidad, inventario, proyectos, documentación y marketing, además de funcionalidades colaborativas como calendario, citas y firma electrónica. Esa modularidad permite arrancar con un conjunto reducido de apps y ampliar funcionalidades conforme cambian las necesidades del negocio, lo que lo hace apto tanto para pruebas rápidas como para despliegues a mayor escala.

La oferta de Odoo se presenta en dos líneas principales: Community, que es gratuita y adecuada para quien desea control total sobre el código y el alojamiento; y Enterprise, que aporta soporte, actualizaciones gestionadas, aplicaciones adicionales y una experiencia más “llave en mano”. En este manual explicamos las diferencias prácticas para ayudar a elegir la edición más adecuada según el caso de uso.

Las ventajas más relevantes que tratamos aquí son la integración nativa entre módulos (por ejemplo, pasar de ventas a facturación o a proyectos sin duplicar datos), la posibilidad de personalización y la escalabilidad funcional. También señalamos limitaciones habituales: el rendimiento depende del hosting y la configuración, y algunos módulos Community pueden tener menos maturidad o soporte que sus equivalentes de pago.

Se insiste en buenas prácticas sencillas: utilizar una base de datos de pruebas para validar cambios, programar copias de seguridad antes de acciones riesgosas (por ejemplo desinstalar apps), y revisar permisos de usuario antes de abrir accesos en producción. Al final del manual hay un checklist y una sección de referencias para profundizar.

Está pensado para administradores y usuarios responsables de poner en marcha una instancia de prueba o configurar flujos operativos; durante la lectura encontrarás recomendaciones para minimizar riesgos (usar una base de datos de pruebas, hacer copias de seguridad y revisar permisos) y una checklist práctica para la puesta en marcha. Para información técnica más profunda consulte la sección de referencias al final del manual.


# 03 — Instalación y prueba (15 días) / Alta e instalación de apps

## Requisitos previos

- Navegador actualizado.
- Cuenta de correo para alta.

## Pasos

1. **Selección de applicaciones** (hay un máximo de 10 aplicaciones en la prueba gratuita).
   Lo primero que debes de hacer es crear una cuenta de odoo, una vez la tengas debes de hacer click en el apartado de la zona superior derecha donde dice "Pruébalo gratis".
   Tras esto se abrirá una pestaña de selección de precios. En esta guía de instalación he usado la versión standard con su preuba gratuita de 15 días.
   ![precios](../assets/img/03-instalacion/precios.png)
   Después, se abrirá la pestaña de selccion de aplicaciones, donde nosotros vamos a elegir las siguientes: *Sitio web, Eventos, CRM, Ventas, Facturación, Contabilidad, Proyecto, Documentos, Marketing por correo electrónico y Marketing Social*.
   ![modulos](../assets/img/03-instalacion/modulos.png)
   Tras seleccionar los modulos deseados (con un maximo de 10 por la prueba gratuita), se muestra una pantalla donde debes de introducir los datos de la empresa y personales.
   ![datos de la empresa](../assets/img/03-instalacion/datos_empresa.png)
2. **Creación de la Base de Datos de Odoo**
   Tras haber seleccionado los modulos deseados se abrirá una pestaña con una selección de configuración básica, ahí debes elegir lo que mejor se ajuste a tus necesidades.
   ![configuración básica](../assets/img/03-instalacion/config_basica.png)
   En esta guía de instalación he elegido la opción de saltar y empezar desde cero.
   Es importante que al llegar a este paso confirmes tu cuenta de Odoo, pues sino tu Base de Datos se borrará a las 3 horas.
   También se puede realizar una instalación local, bajando a la parte inferior de la página web hay un apartado con el nombre "Descargas" donde tan solo tienes que introducir tus datos y los de tu empresa, y elegir tu sistema operativo.
3. **Instalar/Desinstalar apps** desde *Aplicaciones* (¡cuidado con los datos al desinstalar!).
   Para instalar o desinstalar aplicaciones tan solo tienes que ir al tablero de tu base de datos de odoo y seleccionar la opción de aplicaciones, lo cual abrirá una pestaña donde elegir qué aplicaciones quieres añadir.
   ![tablero](../assets/img/03-instalacion/tablero.png)
   ![Tienda de las aplicaciones](../assets/img/03-instalacion/tienda_aplicaciones.png)
   Para instalar nuevas aplicaciones, tan solo hay que hacer click en el botón "Instalar" en la aplicación deseada. Y para desinstalar una aplicación debes de hacer click en los tres puntos situados en la esquina superior derecha del recuadro de la aplicación deseada, lo cual mostrará un overlay con la opción desinstalar. Al introducir esa opción, debes de elegir qué documentos borrar, así cómo confirmar que quieres desinstalar la aplicación.
   ![desinstalar app](../assets/img/03-instalacion/desinstalar.png)

## Resultado esperado

- Acceso al panel principal con las apps instaladas.
- Ser capáz de desinstalar aplicaciones.


# 04 — Ajustes generales

1. **Activar **notificaciones** y (opcional) **PWA**.**
   Para activar las notificaciones tan solo tienes que hacer click en la opción con el mismo nobre en el apartado de notificaciones.
   ![notificaciones](../assets/img/04-ajustes_generales/notificaciones.png)
   Para activar el PWA habría que hacer lo mismo pero con la opción de "descargar Odoo" la cual no descarga la base de datos de forma local, sino que permite un más facil acceso a la base de datos creada.
2. **Perfil: modo oscuro, datos, **2FA**, firma email, notificaciones en Odoo.**
   Para configurar tu perfil tan solo debes de hacer click en el icono del mismo, y desde el overlay que se abre hay disponibles multiples opciones las cuales voy a explicar a continuación.
   Modo oscuro: para activar el modo oscuro debes de ir a preferencias, y en tema darle al que prefieras. En esta pestaña también puedes activar las notificaciones en Odoo y la firma email.
3. ![modo oscuro](../assets/img/04-ajustes_generales/oscuro.png)
   Datos personales: para añadir los datos personales en Odoo 19 debes de irte al apartado de contactos, donde, si haces click en tu perfil puedes editar información pública tales como el puesto.
   ![datos personales](../assets/img/04-ajustes_generales/datos.png)
   La función de 2FA (Two Factor Authentification) está disponible en el apartado de seguridad, dentro de la zona de preferencias, y para activarlo tan solo tienes que scannear un código QR en tu aplicación de autenticación elegida.
4. ****Usuarios y compañías**: roles por módulo; en Enterprise se paga por usuario.**
   Desde el apartado de ajustes, en Odoo, puedes crear compañías, dentro de las cuales tienes a los usuarios, que les puedes asignar roles, los cuales determinan sus permisos dentro de cada módulo. Además, en los planes de pago de Odoo se paga por cada usuario.
   ![permisos usarios por modulo](../assets/img/04-ajustes_generales/usuario.png)
5. ****Idiomas.**
   Hay dos formas para añadir idiomas a Odoo, desde tu perfil (cómo ya se ha mostrado) y desde los ajustes generales(lo que permitirá a cualquier usuario acceder a ese idioma.
   ![Seleccion de idiomas desde ajustes generales](../assets/img/04-ajustes_generales/idioma.png)
6. **Diseño de documentos** (plantillas de factura).
   Justo debajo de la opción de idiomas en los ajustes generales, puedes acceder a la pestaña de "compañías", donde hay una opción llamada diseño de documentos. Al abrir esa opción aparece un Overlay que te permite editar la estructura que tomarán tus documentos.
   ![diseño de documentos](../assets/img/04-ajustes_generales/diseño.png)
7. ****Emails de resumen**: periodicidad y destinatarios.**
   La última opción de ajustes generales que voy a reconocer en esta guía es el de los emails de resumen.
   Odoo tiene un a opción en sus ajustes generales (justo debajo del diseño de los documentos) que determina cada cuanto se envian correos de resumen de lo ocurrido con tu aplicación en un periodo espicificado. La frecuencia de estos puede ser cambiada y el predeterminado es diariamente. En este ejemplo lo voy a configurar para que pase de diariamente a mensualmente.
   ![resumen periodico](../assets/img/04-ajustes_generales/resumen.png)


# 05 — Integración con Gmail (OAuth GCP + Add-on)

## Requisitos

- Cuenta Google Cloud (GCP).

## Pasos

1. **Activar plugin de correo** en Odoo e instalar *Odoo Inbox Add-on* en Gmail.
   Para activar el plugin en Odoo, debes dirigirte a ajustes generales, una vez allí debes de bajar hasta la sección de integraciones, y habilitar la opción de "Plugin de Correo"
   ![plugin de correo](../assets/img/05-integracion_gmail/plugin.png)
   Para que funcione el plugon, tienes que ir a tu cuenta de gmail, y desde ahí, en el margen derecho darle a la opción que muestra un "+", lo cual abrirá una tienda de add-ons para gmail. Ahí debes buscar Odoo Inbox Addin, e instalarlo.
   ![plugin gmail](../assets/img/05-integracion_gmail/gmailodoo.png)
2. En **Google Cloud Console**: habilitar *Gmail API*, crear **OAuth Client (Web)**, configurar **redirect URI** de Odoo.
   Lo primero que necesitas para vincular Odoo es marcar la casilla de OAuth en el apartado integraciones de la pestaña de ajustes generales.
   ![Marcar la casilla](../assets/img/05-integracion_gmail/casillaOauth.png)
   Después accede a "Proveedores Oauth (el cual estás justo debajo) y elige Google OAuth2.
   Una vez lo hayas hecho, dirígete a Google Cloud Console, donde debes crear un nuevo proyecto, en este caso lo llamaré Odoo Test. Seleccionalo cómo el proyecto activo, y busca en la barra de búsqueda "Gmail API", dale a "Habilitar" y debería de aparecer la siguiente pestaña: ![gmail api](../assets/img/05-integracion_gmail/gmailApi.png)
   Ahora debes de darle a "Crear credenciales", rellena los campos de "nombre de la aplicación" con el nombre que desees ponerle, y en los correos que te piden debes de ingresar tanto en contacto cómo en empresa el correo que hayas usado para odoo. Al confirmar llegarás a una parte donde te pide "agregar o quitar permisos". En este caso debemois de darle permisos a Odoo para que pueda hacer log-in así cómo los que se muestran en la captura:
   ![permisos odoo parte 1](../assets/img/05-integracion_gmail/permisosodooapi.png)
   ![permisos odoo parte 2](../assets/img/05-integracion_gmail/permisosodooapi2.png)
   Después debes darle a "Actualizar", seguido de "Guardar y Continuar". Acto seguido continua hasta llegar a ID de Cliente de OAuth, donde debes seleccionar "aplicación web" y de poner el nombre de la web. Tal y como se muestra aquí:
   ![api id](../assets/img/05-integracion_gmail/IDcliente.png)
   Lo siguiente es agregar un URl de Redireccionamiento, el cual debe de seguir esta estructura, pero reemplazando "juanjodiazodoo" por el nombre de tu base de datos y darle a "listo".
   ![](../assets/img/05-integracion_gmail/urlredirect.png)
3. Copiar **Client ID/Secret** a Odoo (Gmail server settings) y **Guardar**.
   Tras haber seguido los pasos dictados anteriormente, en el apartado de "Credenciales" deberías de poder acceder a la credencial creada, que al hacerle click te lleva a la siguiente pestaña:
   ![](../assets/img/05-integracion_gmail/secreto.png)
   Ahora, debes copiar el ID de cliente, para ponerlo en la pestaña de "Proovedores de OAuth" que abrimos antes, así cómo darle a "permitido" y guardar los cambios.
   Para lo siguiente debes de volver al apartado de "correos electronicos" de los ajuistes generales y marcar la casilla de "Utilizar servidores de correo electrónico personalizados" tras lo cual se mostrará una opción nueva de Usar un servidor de Gmail, donde debes de pegar tanto el ID de la aplicación, cómo el secreto. Tras esto ultimo debes guardar los cambios.
   ![](../assets/img/05-integracion_gmail/personalizados.png)


# 06 — Contactos

- Asociación automática persona/empresa.
  Al haber enlazado el api de gmail, Odoo agrega automáticamente los contactos de la bandeja de entrada del correo introducido. Los cuales se muestran en la applicación de contactos.Ejemplo de cointacto generado por el add-on de gmail:
  ![](../assets/img/06-contactos/gmail.png)
  Por culpa de esto se puede dar el caso de que se dupliquen contactos, en ese caso tan solo ve a los ajustes de uno de los duplicados y dale a "fusionar", lo cual fusiona ambos contactos.
- **Etiquetas** para segmentar.
  Es importante crear etiquetas para poder filtrar contactos. Para crear una etiqueta tan solo tienes que darle a un contacto, darle a crear en el apartado de etiquetas, ponerle nombre y elegir un color.
  ![](../assets/img/06-contactos/etiquetas_contactos.png)
  Esto ayuda a filtrar no solamente por empresas y personas sino también por cargos, etc.
- Importación CSV (ver `common/ejemplo_csv/`).
  Poder importar los archivos de contacto es muy importante para trasladarse entre ERPs, dico eso, para importar contactos, tan solo hay que seleccionar la opción con el mismo nombre en los ajustes de "contactos":
  ![](../assets/img/06-contactos/importar.png)
  Otra opción es importar hojas de calculo, las cuales son las que genera Odoo al exportar sus contactos.


# 07 — Calendario y Citas

- Calendario (día/semana/mes) + disponibilidad del equipo.

  - El calendario de Odoo tiene una función en la que te permite ver sus contenidos con distintas vistas, por ejemplo la semanal (que es la predeterminada) cómo la mensual. Esto beneficia al usuario, pues cómo puedes ver tanto tus tareas y reuniones, cómo la de tus compañeros, te permite comprobar su disponibilidad sin necesitar preguntar directtamente o dudas.
- **Integración con Google Calendar** (API OAuth GCP).

  - Para integrar el calendario con google calendar hay que seguir los mismos pasos iniciales que para configurar el api de gmail. Estos son: crear un  nuevo proyecto en google cloud, crearle credenciales, nombrarlas de forma distinta para diferenciarlas y por ultimo, darle los permisos, que tendrán que ser los de openid, y todos los permisos de Google Calendar API.
  - Tras completar esa parte ahora tan solo hay que copiar el ID de usuario, y dirigirte a sjustes generales, seguido de ajustes del calendario, donde hay que pegar tanto el user ID como el secreto.
    ![](../assets/img/07-calendario_y_citas/apicalendario.png)
- **Odoo Meet** (videollamadas) o enlaces externos.

  - Puedes crear eventos en el calendario de Odoo muy facilmente tan solo haciendo click derecho sobre un momento en el calendario te muestra las siguientes opciones:
    ![](../assets/img/07-calendario_y_citas/eventos.png)
  - Lo especial de Odoo es el icono de la cámara, pues odoo tiene una alternativa a google meeto o a zoom integrada, pero aun aaí también permite que dopnde está pùesto el enlace coloques otro de una aplicación externa.
- **Módulo Citas** (Enterprise): enlaces públicos, buffers, preguntas previas.
    El modulo citas en Odoo permite simplificar el proceso de crear un evento cómo una cita. Esto lo hace a traves de un acopnfiguración para decir cada cuanto tiempo aceptas citas, así cómo el tiempo de antelación para poder pedir una cita.
    ![](../assets/img/07-calendario_y_citas/citas.png)
    También permite a los usuarios de tu página web reservar citas a través de un calndario que solo muestra los momentos libres:
    ![](../assets/img/07-calendario_y_citas/reserva.png)
    Así como enviar preguntas previas a una cita, todo desde Odoo.


# 08 — Proyectos (Kanban)
El módulo Proyectos en Odoo permite planificar, ejecutar y controlar el trabajo por medio de proyectos, tareas y subtareas. Su interfaz principal es tipo Kanban, similar a herramientas como Trello, pero integrada con el resto del ERP (ventas, facturación, hojas de tiempo, helpdesk). En este capítulo veremos cómo crear proyectos, gestionar tareas, configurar fases (etapas), usar subtareas, dependencias e hitos, y cómo aprovechar las vistas y reportes para controlar la ejecución.
## Crear un proyecto
Para crear un proyecto dirígete a Proyectos > Proyectos y pulsa "Nuevo Proyecto". Se abrirá una ficha donde configurarás los datos básicos:
- Nombre del proyecto.
- Si es facturable y la política de facturación (por tareas, por horas, por hitos).
- Email asociado para crear tareas por correo.
- Plantilla del proyecto (si ya tienes plantillas predefinidas).
![](../assets/img/08-proyectos/crearProyecto.png)
## Interfaz Kanban y etapas
Al entrar en un proyecto accederás a la vista Kanban con las diferentes etapas que representan el flujo de trabajo. Las etapas son configurables y pueden aplicarse a todo el proyecto o a tareas concretas.
Puedes arrastrar y soltar tareas entre etapas para actualizar su estado rápidamente.
![](../assets/img/08-proyectos/etapas.png)
Cada tarjeta de tarea incluye información clave: título, asignado, porcentaje de progreso, etiquetas, fecha de vencimiento y prioridad. Abriendo la tarjeta puedes añadir descripción larga, archivos adjuntos, conversaciones y notas.
## Crear y gestionar tareas
Para añadir una tarea dentro del proyecto pulsa "Nueva Tarea". En la ficha de la tarea puedes:
- Asignar responsable(es).
- Establecer fechas de inicio y fin.
- Añadir etiquetas (tags) y prioridad.
- Añadir subtareas o checklist para dividir el trabajo.
- Vincular horas y hojas de tiempo.
- Establecer la visibilidad (privado o público dentro del proyecto).
Dentro de la tarea encontrarás el registro rápido de actividades (chatter) donde comentar, registrar notas internas o enviar mensajes a colaboradores.
### Subtareas y checklist
Las subtareas permiten dividir una tarea en unidades más pequeñas y asignarlas a distintos miembros. Son útiles para micro-gestión y para generar automáticamente registros de tiempo cuando se registran las horas por subtarea.
Usa checklists cuando necesites una lista de control que no requiera asignación independiente.
## Dependencias y hitos
Odoo Projects permite establecer dependencias entre tareas (p. ej., tarea B no puede comenzar hasta que A termine). Las dependencias ayudan a planificar el cronograma y a detectar bloqueos.
Los hitos (milestones) son tareas especiales que marcan logros importantes del proyecto (entregas, aprobaciones, lanzamientos). Visualízalos en la vista de lista o Gantt para seguimiento estratégico.
## Tareas recurrentes
Si una tarea se repite (mantenimiento, backup, informes), puedes programar recurrencia desde la ficha de tarea. Configura la frecuencia (diaria, semanal, mensual), fecha de finalización y si se generan nuevas tareas automáticamente.
## Vistas y filtros
El módulo ofrece varias vistas para trabajar con tus proyectos:
- Kanban (tarjetas) — ideal para flujos de trabajo visuales.
- Lista — para edición rápida y exportación.


# 09 — Documentos, Firma e Información (Knowledge)

- **Documentos**: repositorio, edición hojas, dividir PDFs, etiquetas/flujo.
Documentos es una extensiónm de Odoo que permite revisar todos los documentos de la base de datos, así cómo la información adjunta a ellos (empleados asignados).
![](../assets/img/09-documentos_firma_info/vistageneral.png)
En el apartado de documentos puedes subir archivos directamente, sin necesidad de asignarlos a nada. Odoo permite dividir pdf's de forma nativa, lo que permite obtener solamente los trozos de información relevantes. También poseé un editor de hojas de calculo nativo, el cual permite facilitar el trabajo colaborativo, a su vez que permite realizar ajustes y cambios en la hojas de calculo.
También permite asignar etiquetas a documentos, y también contactos, ya sean contactos clientes o de la empresa.
- **Firma electrónica**: campos (firma/nombre/fecha), envío y registro.
Odoo permite adjuntar el modulo de firma digital al de documentos, permitiendote editar la firma de documentos, para casi automatizar el proceso, así cómo acelelarlo drásticamente.
![](../assets/img/09-documentos_firma_info/firmadigital.png)
También te permite elegir entre distintos tipos de firma, ya sea la predeterminada, una dibujada directamente en el ordenador, o subir una que hayas escaneado previamente. Además también diferencia los documentos firmados de los que no.

- **Información (Knowledge)**: wiki tipo Notion, permisos y publicación.
El apartado de información funcina de forma muy parecida a wikis estilo notion, pues también trabaja con espacios de trabajo, aunque la estructura de los archivos tiene un ligero parecido a la de Obsidian.
![](../assets/img/09-documentos_firma_info/informacion.png)
El apartado de información permite crear tu propia wiki, para ello tan solo necesitas añadir una estructura básica, la cual deberas de llenar con los articulos relevantes, el formato que usan estos archivos es markdown, pero tiene un editor de markdown nativo:
![](../assets/img/09-documentos_firma_info/funciones.png)
Esto permite organizar la información de una manera más profesional, así cómo añadir documentos, encuestas y hojas de calculo directamente al apartado de información desde el resto de la base de datos, incluyendo los proyectos pendientes.


# 10 — Ediciones y costes


# 10 — Ediciones y costes

- **Community** (gratis, usuarios ilimitados, mantenimiento propio). Odoo Community destaca en proyectos que necesitan flexibilidad técnica y sirve en la situación donde el equipo quiere controlar el código y alojarlo por su cuenta.

- **Enterprise** (SaaS, soporte, actualizaciones, app móvil, Odoo Studio). Odoo Enterprise encaja cuando se busca servicio gestionado, soporte oficial y funcionalidades avanzadas.

- **Contrato anual** aunque el pago sea mensual. Esto viene bien en la situación donde se quiere reducir el coste mensual manteniendo un compromiso estable.

- **Prueba: máx. 10 apps**. Esto viene bien en la situación donde se desea evaluar el sistema antes de contratar.

![](../assets/img/10-ediciones_y_costes/precios.png)


# 11 — Tips & Checklist


## Tips
- Activa **2FA** y define **roles** desde el día 1.
- Etiquetas y seguidores (followers) para notificaciones.
- Copias de seguridad antes de **desinstalar** apps.
- Programa actualizaciones regulares (Odoo y módulos).
- Prueba cambios en una BD de pruebas antes de producción.
- Revisa permisos de usuarios antes de dar accesos a producción.
- Documenta versiones y cambios de módulos instalados.

## Checklist
- [ ] BD de prueba activada
- [ ] Apps iniciales instaladas
- [ ] 2FA y notificaciones configuradas
- [ ] Gmail/Calendar integrados (si aplica)
- [ ] Contactos importados y etiquetados
- [ ] Proyectos/tareas creados
- [ ] Documentos y firma probados
- [ ] Wiki inicial en Información
 - [ ] Actualizaciones programadas configuradas
 - [ ] Pruebas realizadas en la BD de pruebas
 - [ ] Permisos de usuarios revisados


# 99 — Referencias

- Vídeo: *Curso Completo Odoo 2025: De Principiante a Experto en 2 Horas o Otros videos
https://www.youtube.com/watch?v=yE8n9RbLUmo&t=40s
![alt text](../assets/img/99-referencias/referenciaodoo.png)
- Documentación oficial: https://www.odoo.com/es_ES/pricing 
- Odoo Studio: 
- Odoo Knowledge:
- Gmail Add-on: 
- Las que veas necesarias ....
