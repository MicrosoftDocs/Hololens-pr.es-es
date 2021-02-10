---
title: Versión preliminar de Insider para Microsoft HoloLens
description: Aprende a empezar con las compilaciones de Insider y a proporcionar comentarios valiosos para nuestra próxima actualización principal del sistema operativo para HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 2/2/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 4573f3b2e88af36c397fd1735ec9c6a96b4c52d6
ms.sourcegitcommit: 76a99370ab841c06e533cc2f4a0c78c1fb7eac70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "11324803"
---
# Versión preliminar de Insider para Microsoft HoloLens

Te damos la bienvenida a las compilaciones más recientes de Insider Preview para HoloLens. Es fácil empezar y [proporcionar comentarios](hololens-insider.md#start-receiving-insider-builds) valiosos para nuestra próxima actualización principal del sistema operativo para HoloLens.

## Notas de la versión de Windows Insider

Estamos encantados de empezar a usar nuevas características para los usuarios de Windows Insider de nuevo. We will be flighting to the Dev Channel for the latest updates. Seguiremos actualizando esta página a medida que agreguemos más características y actualizaciones a nuestras compilaciones de Windows Insider.  Prepárate para mezclar estas actualizaciones en tu realidad.

> [!IMPORTANT]
> Si anteriormente usaste la aplicación Configuración o la aplicación Microsoft Edge en un quiosco, hemos reemplazado estas aplicaciones por nuevas aplicaciones que usan un identificador de aplicación diferente. Te animamos encarecidamente a leer [los nuevos AUMID para las nuevas aplicaciones en el modo de pantalla completa a](#use-the-new-settings-and-edge-apps-in-kiosk-modes) continuación. Esto garantizará que sigas teniendo la aplicación Configuración en el quiosco o incluyas la nueva aplicación de Microsoft Edge.

<br>

| Nombre de la característica                                              | Descripción corta                                                                      | Disponible en la compilación |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Nuevo Microsoft Edge](#introducing-the-new-microsoft-edge) | El nuevo Microsoft Edge basado en Chromium ya está disponible para HoloLens 2                         | 20279.1006 |
| [WebXR y visor 360](#webxr-and-360-viewer)             | Probar experiencias web envolventes y reproducción de vídeo 360                                           | 20289.1000 |
| [Aplicación Nueva configuración](#new-settings-app)                     | La aplicación Configuración heredada se está reemplazando por una versión actualizada con nuevas características y configuración | 20279.1006 |
| [Selector de aplicaciones predeterminado](#default-app-picker)                 | Elegir qué aplicación debe iniciarse para cada tipo de archivo o vínculo                                      | 20279.1006 |
| [Aplicación web de Office](#office-web-app)                         | Ahora se muestra un acceso directo a la aplicación web de Office en "Todas las aplicaciones"                                   | 20279.1006 |
| [Deslizar el dedo para escribir](#swipe-to-type)                           | Usar la punta del dedo para "deslizar rápidamente" palabras en el teclado holográfico                        | 20279.1006 |
| [Compatibilidad con micrófono externo USB-C](#usb-c-external-microphone-support) | Usa micrófonos USB-C para aplicaciones y/o asistencia remota.| 20279.1006 |
| [Nuevos AUMID para nuevas aplicaciones en modo de pantalla completa](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | AUMIDs para nuevas aplicaciones de Configuración y Edge | 20279.1006 |
| [Entrega de errores en el modo de pantalla completa mejorada](#kiosk-mode-behavior-changes-for-handling-of-failures) | El modo de pantalla completa busca el acceso asignado global antes del menú inicio vacío. | 20279.1006 |
| [Configurar diagnósticos de reserva](#configuring-fallback-diagnostics-via-settings-app) | Establecer el comportamiento de diagnóstico de reserva en la aplicación Configuración | 20279.1006 |
| [Compartir cosas con dispositivos cercanos](#share-things-with-nearby-devices) | Compartir archivos o direcciones URL de un HoloLens a un equipo | 20279.1006 |
| [Nuevo solucionador de problemas de actualización del sistema operativo](#new-os-update-troubleshooter) | Nuevo solucionador de problemas en configuración para actualizaciones del sistema operativo | 20279.1006 |
| [Mejoras y correcciones en la actualización](#improvements-and-fixes-in-the-update) | Correcciones adicionales en la actualización. | 20279.1006 |

### Presentación del nuevo Microsoft Edge

![Animación del logotipo heredado de Microsoft Edge al nuevo logotipo de Microsoft Edge](images/new-edge.gif)

El nuevo Microsoft Edge adopta el proyecto de código [abierto chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) para crear una mejor compatibilidad para los clientes y una menor fragmentación de la web para desarrolladores web.

Con esta versión preliminar de Insider, el nuevo Microsoft Edge está disponible para los clientes de HoloLens 2 por primera vez. Aunque el nuevo Microsoft Edge reemplazará finalmente a Microsoft Edge heredado en HoloLens 2, ambos exploradores están disponibles actualmente para los usuarios de Insider. Comparta comentarios y errores con nuestro equipo a través de la característica Enviar **comentarios** en el nuevo Microsoft Edge o a través del Centro [de opiniones.](hololens-feedback.md)

![Nueva captura de pantalla de Microsoft Edge](images/new-edge-ui.png)

#### Iniciar el nuevo Microsoft Edge

Hay dos versiones de Microsoft Edge disponibles para los usuarios de Insider: el nuevo icono de Microsoft Edge (representado por un icono de remolino azul y verde) y Microsoft Edge heredado (representado por el icono ![ ](images/new_edge_logo.png) blanco "e"). El nuevo Microsoft Edge se ancla al menú Inicio y se iniciará automáticamente al activar un vínculo web. Si quieres volver a usar Microsoft Edge heredado como explorador web predeterminado, consulta las instrucciones siguientes para restablecer [las aplicaciones predeterminadas.](#default-app-picker)

> [!NOTE]
> Cuando inicies por primera vez el nuevo Microsoft Edge en HoloLens 2, la configuración y los datos se importarán desde Microsoft Edge heredado. Si sigue usando Microsoft Edge heredado después de iniciar el nuevo Microsoft Edge, los nuevos datos no se sincronizarán de Microsoft Edge heredado al nuevo Microsoft Edge.

#### Configuración de opciones de directiva para el nuevo Microsoft Edge

El nuevo Microsoft Edge ofrece a los administradores de TI un conjunto mucho más amplio de directivas de explorador en HoloLens 2 que estaban disponibles anteriormente con Microsoft Edge heredado.

Estos son algunos recursos útiles para obtener más información sobre cómo administrar la configuración de directivas para el nuevo Microsoft Edge:

- [Configurar la directiva de Microsoft Edge con Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Asignación de directiva de Microsoft Edge (versión anterior) a Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Asignación de directivas de Google Chrome a Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Documentación [completa de Microsoft Edge Enterprise](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> Debido al volumen de directivas de explorador admitidas por el nuevo Microsoft Edge, nuestro equipo no puede garantizar que cada nueva directiva funcione en HoloLens 2. Sin embargo, hemos probado y confirmado que el nuevo equivalente de Microsoft Edge de cada directiva heredada de Microsoft Edge anteriormente compatible con HoloLens 2 funciona según lo esperado. Consulta [la asignación](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) de directivas heredadas de Microsoft Edge a Microsoft Edge para encontrar el nuevo equivalente de Microsoft Edge de cada directiva de explorador de Microsoft Edge heredada que usaste con HoloLens 2.
>
> Hay al menos dos nuevas directivas de Microsoft Edge que sabemos *que no funcionarán* con HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### Qué esperar del nuevo Microsoft Edge en HoloLens 2

Dado que el nuevo Microsoft Edge es una aplicación nativa de Win32 con una nueva capa de adaptador para UWP que permite ejecutarse en dispositivos solo para UWP como HoloLens 2, es posible que algunas características no estén disponibles inmediatamente. We'll be supporting new scenarios and features over the coming months, so please check this space for up-to-date information.

**Escenarios y características que se espera que funcionen:**
- Experiencia de primera ejecución, inicio de sesión en el perfil y sincronización
- Los sitios web deben representarse y comportarse según lo esperado
- La mayoría de las funciones del explorador (Favoritos, Historial, etc.) deberían funcionar según lo esperado
- Modo oscuro
- Instalación de aplicaciones web en el dispositivo
- Instalación de extensiones (háganos saber si usa extensiones que no funcionan correctamente en HoloLens 2)
- Ver y marcar un PDF
- Sonido espacial desde una sola ventana del explorador
- Actualización automática y manual del explorador
- Guardar un PDF desde el menú Imprimir (con la opción "Guardar en PDF")

**Próximamente, se ofrece información sobre escenarios y características:**
- Extensión WebXR y visor 360
- Restauración de contenido para corregir la ventana al examinar varias ventanas colocadas en el entorno

**No se espera que los escenarios y las características funcionen:**
- Sonido espacial de varias ventanas con secuencias de audio simultáneas
- "Véalo, digalo"
- Impresión

**Principales problemas conocidos del explorador:**
- Restablecer el dispositivo quitará el nuevo Microsoft Edge
- La vista previa de lupa en el teclado holográfico muestra contenido incorrecto

#### Canales de Microsoft Edge Insider

El equipo de Microsoft Edge pone tres canales de vista previa a disposición de la comunidad de Edge Insider: Beta, Dev y Canary. La instalación de un canal de vista previa no desinstala la versión publicada de Microsoft Edge en holoLens 2 y puede instalar más de una al mismo tiempo. 

Visita la [página principal de Microsoft Edge Insider](https://www.microsoftedgeinsider.com) para obtener más información sobre la comunidad de Edge Insider. Para obtener más información sobre los diferentes canales de Edge Insider y empezar a trabajar, visita la página de descarga [de Edge Insider.](https://www.microsoftedgeinsider.com/download)

Hay un par de métodos disponibles para instalar los canales de Microsoft Edge Insider en HoloLens 2:

**Instalación directa en el dispositivo (actualmente solo está disponible para dispositivos no administrados)**
  1. En HoloLens 2, visita la página de descarga [de Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Selecciona el **botón Descargar para HoloLens 2** para el canal Edge Insider que quieras instalar.
  1. Inicia el archivo .msix descargado desde la cola de descarga de Edge o desde la carpeta "Descargas" del dispositivo (mediante el Explorador de archivos).
  1. [Se iniciará el instalador](app-deploy-app-installer.md) de la aplicación.
  1. Seleccione el **botón** Instalar.
  1. Después de instalar correctamente, encontrarás Microsoft Edge Beta, Dev **** o Canary como una entrada independiente en la lista Todas las aplicaciones del menú Inicio.

**Instalar a través del equipo con Windows Device Portal (requiere que [el modo de](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) desarrollador esté habilitado en HoloLens 2)**
  1. En el equipo, visita la [página de descarga de Edge Insider.](https://www.microsoftedgeinsider.com/download)
  1. Selecciona el **botón de flecha** desplegable junto al botón "Descargar para Windows 10" para el canal de Edge Insider que quieras instalar.
  1. Seleccione **HoloLens 2** en el menú desplegable.
  1. Guarda el archivo .msix en la carpeta "Descargas" del equipo (u otra carpeta que puedas encontrar fácilmente).
  1. Usa [Windows Device Portal en](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) el equipo para instalar el archivo .msix descargado en HoloLens 2.
  1. Después de instalar correctamente, encontrarás Microsoft Edge Beta, Dev **** o Canary como una entrada independiente en la lista Todas las aplicaciones del menú Inicio.

> [!NOTE]
> Durante esta versión preliminar de Windows Insider para HoloLens 2, la versión de Microsoft Edge en el dispositivo puede ser superior a la disponible en algunos (o todos) los canales de Microsoft Edge Insider. Esto es para asegurarnos de que las nuevas características y correcciones destinadas específicamente al explorador web en HoloLens 2 están obteniendo acceso a nuestros usuarios de Windows Insider lo más rápido posible. Poco después del lanzamiento público de la próxima actualización de Windows, las compilaciones del canal de Microsoft Edge Insider superarán y se adelantarán a la versión de Microsoft Edge en holoLens 2.

### WebXR y visor 360

*Agregado en la compilación 20289.1000 de Windows Insider*

El nuevo Microsoft Edge incluye compatibilidad con WebXR, que es el nuevo estándar para crear experiencias web envolventes (reemplazando WebVR). Muchas experiencias web envolventes se diseñaron pensando en la realidad virtual (reemplazan el campo de vista por un entorno virtual), pero HoloLens 2 también admite estas experiencias. El estándar WebXR también permite experiencias web envolventes de realidad aumentada y mixta que aprovechan tu entorno físico. A medida que los desarrolladores pasan más tiempo con WebXR, prevemos que las nuevas experiencias envolventes de realidad mixta y aumentada llegarán para que lo prueben los clientes de HoloLens 2.

La extensión visor 360 se basa en WebXR e se instala automáticamente junto con el nuevo Microsoft Edge en HoloLens 2. Esta extensión web le ofrece la posibilidad de inmersarse en vídeos de 360 grados. YouTube ofrece la mayor selección de 360 vídeos, por lo que te animamos a empezar allí.

#### Cómo usar WebXR

1. Navegue a un sitio web con compatibilidad con WebXR.
1. Selecciona el **botón Entrar VR** en el sitio web. La ubicación y la representación visual de este botón pueden variar según el sitio web, pero puede ser similar a:

    ![Ejemplo de botón Escribir VR](images/75px-enter-vr.png)

1. La primera vez que intentes iniciar una experiencia WebXR en un dominio específico, el explorador pedirá su consentimiento para entrar en una vista envolvente, selecciona **Permitir.**
1. Usa [los gestos de HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame) para manipular la experiencia.
1. Si la experiencia no tiene un botón **Salir,** usa el gesto [Inicio](hololens2-basic-usage.md#start-gesture) para volver a casa.

**Ejemplos de WebXR recomendados**
- Visor 360 (vea la sección siguiente)
- [Dinosaurios XR](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### Cómo usar 360 Viewer

1. Ve a un vídeo de 360 grados en YouTube.
1. En el marco de vídeo, selecciona el botón de auriculares de realidad mixta:

    ![Botón para activar el Visor 360](images/enter-360-viewer.jpg)

1. La primera vez que intentes iniciar el Visor 360 en un dominio específico, el explorador pedirá su consentimiento para entrar en una vista envolvente. Seleccione **Permitir**.
1. [Pulsa en el](hololens2-basic-usage.md#select-using-air-tap) aire para que se activen los controles de reproducción. Usa los rayos de mano y [la](hololens2-basic-usage.md#select-using-air-tap) pulsación del aire para reproducir/pausar, saltar hacia adelante o atrás, activar/desactivar los títulos o detener la experiencia (que sale de la vista envolvente). Los controles de reproducción desaparecerán después de unos segundos de inactividad.

#### Principales problemas conocidos de WebXR y 360 Viewer
- En las experiencias webXR, los hologramas pueden desplazarse o inclinarse al inclinar la cabeza o moverse por el entorno.
- En función de la complejidad de la experiencia de WebXR, la velocidad de fotogramas puede bajar o entrecortar.
- Las uniones de mano articuladas aún no están disponibles en WebXR.
- Al salir de una experiencia de Visor de WebXR o 360, pueden tardar 30 segundos o más en volver a aparecer hologramas en la casa de realidad mixta.
- Es posible que 360 vídeos de sitios web distintos de YouTube no funcionen como se esperaba.
- Si los vídeos 360 no entran en la vista envolvente (o no aparece el botón de los auriculares de realidad mixta), prueba a actualizar la página.
- Los títulos aún no están visibles en 360 Viewer en HoloLens 2.
- Pausar un vídeo en 360 Viewer detiene la representación del vídeo (pero al seleccionar el botón reproducir correctamente se reanuda la reproducción).
- El botón "siguiente vídeo" en el Visor 360 no funciona actualmente.
- Puedes reproducir vídeos 2D en un modo envolvente de "teatro", pero la velocidad de fotogramas será inferior a 30 fps.

#### Proporcionar comentarios sobre WebXR y visor 360

Comparta comentarios y errores con nuestro equipo a través de la **característica Enviar comentarios** en el nuevo Microsoft Edge.

### Aplicación Nueva configuración

Con esta versión, presentamos una nueva versión de la aplicación Configuración. La nueva aplicación Configuración incluye nuevas características y opciones de configuración expandidas para HoloLens 2 en las siguientes áreas: Sonido, Suspensión de Power &, Red & Internet, Aplicaciones, Cuentas, Facilidad de acceso y mucho más.

> [!NOTE]
> Dado que la nueva aplicación Configuración es distinta de la aplicación Configuración heredada, las ventanas de configuración que colocaste anteriormente en el entorno se quitarán al actualizarse.

![Página principal de la aplicación Nueva configuración](images/new-settings-app.png)

**Nuevas características y configuración**
- Búsqueda de configuración: busque la configuración en la página principal de Configuración con palabras clave o el nombre de la configuración.
- Sonido > sistema:
  - Dispositivos de audio de entrada y salida: elige de forma independiente los dispositivos de audio de entrada y salida (por ejemplo, escucha audio a través de auriculares Bluetooth o usa un micrófono USB-C para la entrada de audio). 
    > [!NOTE]
    > Bluetooth holoLens 2 no admite los micrófonos.
  - Volumen de la aplicación: ajusta de forma independiente el volumen de cada aplicación.
- Sistema > power & suspensión: elige cuándo el dispositivo debe ir a suspensión después de un período de inactividad.
- Sistema > batería: habilita manualmente el modo de ahorro de batería o establece un umbral de batería en el que el modo de ahorro de batería se activa automáticamente.
- Dispositivos > USB: puedes deshabilitar las conexiones USB de forma predeterminada.
- Red & Internet:
  - Los adaptadores Ethernet USB-C ahora aparecerán en Red & Internet.
  - La configuración del adaptador Ethernet USB-C ya está disponible, incluida su dirección IP.
  - Ahora puedes habilitar el modo avión en HoloLens 2.
- Aplicaciones: puedes restablecer las aplicaciones predeterminadas usadas para los tipos de archivos y vínculos. Consulta [El selector de aplicaciones predeterminado](#default-app-picker) para obtener más información.
- Cuentas > otros usuarios: los propietarios de dispositivos pueden agregar usuarios, actualizar usuarios estándar a propietarios de dispositivos, degradar los propietarios de dispositivos a usuarios estándar y quitar usuarios.
- Facilidad de acceso: cambiar el tamaño del texto y algunos efectos visuales.

**Problemas conocidos**
- Se quitarán las ventanas de configuración colocadas anteriormente (consulta la nota anterior).
- Visitar la página Notificaciones puede bloquear la aplicación Configuración (investigando).
- La página Ethernet no aparece actualmente (se solucionará próximamente).
- Ya no puedes cambiar el nombre de tu dispositivo con la aplicación Configuración (los administradores de TI pueden usar paquetes de aprovisionamiento o MDM para cambiar el nombre de los dispositivos).
- Es posible que el uso de la batería para el nuevo Microsoft Edge no sea preciso, debido a su naturaleza como una aplicación de escritorio Win32 compatible con una capa de adaptador para UWP (no se prevé una corrección pronto).

### Selector de aplicaciones predeterminado

Cuando activas un hipervínculo o abres un tipo de archivo con más de una aplicación instalada que lo admite, verás una nueva ventana abierta en la que se te pedirá que selecciones qué aplicación instalada debe controlar el tipo de archivo o vínculo. En esta ventana también puedes elegir que la aplicación seleccionada controle el tipo de archivo o vínculo "Una vez" o "Siempre".

![Ventana del selector de aplicaciones](images/default-app-picker.png)

Si eliges "Siempre" pero más adelante quieres cambiar qué aplicación controla un tipo de archivo o vínculo determinado, puedes restablecer los valores predeterminados guardados en Configuración **> Aplicaciones.** Desplácese hasta la parte inferior **** de la página y seleccione el botón Borrar en "Aplicaciones predeterminadas para tipos de archivo" o "Aplicaciones predeterminadas para tipos de vínculos". A diferencia de la configuración similar en equipos de escritorio, no puedes restablecer valores predeterminados de tipos de archivo individuales.

### Aplicación web de Office

La aplicación web de Office se ha agregado a la lista "Todas las aplicaciones" en el menú Inicio. Esta aplicación web también se puede anclar a Inicio o desinstalarse. Dado que se trata de una aplicación web, su funcionalidad coincide exactamente con lo que experimentarías visitando https://www.office.com . La funcionalidad de la aplicación web de Office solo está disponible cuando holoLens 2 tiene una conexión a Internet activa.

### Deslizar el dedo para escribir

A algunos clientes les resulta más rápido "escribir" en teclados virtuales deslizando el dedo por la forma de la palabra que pretenden escribir y estamos previsualizando esta característica para el teclado holográfico. Puedes deslizar el dedo una palabra a la vez pasando la punta del dedo a través del plano del teclado holográfico, deslizando el dedo por la forma de la palabra y, a continuación, retirando la punta del dedo del plano del teclado. Puedes deslizar rápidamente las palabras de seguimiento sin necesidad de presionar la barra espaciadora quitando el dedo del teclado entre palabras. Sabrás que la característica funciona si ves una pista de deslizar el dedo después del movimiento del dedo en el teclado.

Ten en cuenta que esta característica puede ser difícil de usar y dominar debido a la naturaleza de un teclado holográfico en el que no sientas resistencia contra el dedo (a diferencia de una pantalla de teléfono móvil). Estamos evaluando esta característica para la versión pública, por lo que sus comentarios son importantes; si encuentras la característica útil o tienes comentarios sobre la regeneración, háganoslo saber a través del Centro [de opiniones.](hololens-feedback.md)

### Compatibilidad con micrófono externo USB-C

> [!IMPORTANT]
> Conectar un **micrófono USB no lo establecerá automáticamente como el dispositivo de entrada.** Al conectar un conjunto de auriculares USB-C, los usuarios observarán que el audio de los auriculares se redirigirá automáticamente a los auriculares, pero el sistema operativo HoloLens da prioridad a la matriz de micrófonos internos por encima de cualquier otro dispositivo de entrada. **Para usar un micrófono USB-C, sigue los pasos siguientes.**

Los usuarios pueden seleccionar micrófonos externos conectados a USB-C mediante el panel **de** configuración de sonido. Los micrófonos USB-C se pueden usar para llamar, grabar, etc.

Abra la **aplicación Configuración** y seleccione **Sonido del**  ->  **sistema.**

![Configuración de sonido](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Para usar micrófonos externos con **asistencia remota,** los usuarios tendrán que hacer clic en el hipervínculo "Administrar dispositivos de sonido".
>
> A continuación, use la lista desplegable para establecer el micrófono externo como **Predeterminado** o **Predeterminado de comunicaciones.** Elegir Predeterminado **significa** que el micrófono externo se usará en todas partes.
>
> Elegir **El** valor predeterminado de comunicaciones significa que el micrófono externo se usará en asistencia remota y otras aplicaciones de comunicaciones, pero la matriz de micrófonos de HoloLens puede seguir usándose para otras tareas.

![Administrar dispositivos de sonido](images/usbc-mic-2.png)

<br>

![Establecer el valor predeterminado del micrófono](images/usbc-mic-3.jpg)

#### ¿Qué pasa Bluetooth compatibilidad con micrófonos?

Desafortunadamente Bluetooth los micrófonos aún no se admiten actualmente en HoloLens 2.

#### Solución de problemas de micrófonos USB-C

Ten en cuenta que algunos micrófonos USB-C se informan incorrectamente como micrófono *y* altavoz. Esto es un problema con el micrófono y no con HoloLens. Al conectar uno de estos micrófonos a HoloLens, es posible que se pierda el sonido. Afortunadamente, hay una corrección simple.  

En **Configuración**de sonido del sistema, establezca explícitamente los altavoces integrados (controlador de audio de característica  ->  ****  ->  **** **analógica)** como **dispositivo predeterminado.** HoloLens debe recordar esta configuración incluso si el micrófono se quita y se vuelve a conectar más adelante.

![Solución de problemas de micrófonos USB-C](images/usbc-mic-4.png)

### Usar la nueva configuración y las aplicaciones perimetrales en los modos de pantalla completa

Al incluir aplicaciones [](hololens-kiosk.md)en quioscos, un administrador de TI a menudo agrega la aplicación al quiosco, pero con su id. de modelo de usuario de aplicación (AUMID). Dado que tanto la aplicación Configuración como la aplicación de Microsoft Edge se consideran nuevas aplicaciones y son diferentes a las antiguas pantallas de pantalla completa que usan AUMIDs para esas aplicaciones, tendrán que actualizarse para usar el nuevo AUMID.

Al modificar un quiosco para incluir las nuevas aplicaciones, te recomendamos agregar el nuevo AUMID, así como dejar el antiguo. Esto creará una transición sencilla cuando los usuarios actualicen el sistema operativo y no tendrán que recibir nuevas directivas para seguir usando el quiosco según lo previsto.

| Aplicación                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Aplicación configuración anterior       | HolographicSystemSettings_cw5n1h2txyewy! Aplicación            |
| Nueva aplicación de configuración       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! Aplicación |
| Antigua aplicación de Microsoft Edge | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| Nueva aplicación de Microsoft Edge | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### Cambios en el comportamiento del modo de pantalla completa para controlar errores

En compilaciones anteriores, si un dispositivo tuviera una configuración de quiosco, que es una combinación de acceso asignado global y acceso asignado a un miembro del grupo de AAD, si se hubiera fallado la determinación de la pertenencia al grupo de AAD, el usuario vería["no](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)se muestra nada en el menú inicio".

A partir de la versión de Windows Insider, la experiencia de pantalla completa volverá a la configuración global de quiosco (si está presente) en caso de errores durante el modo de pantalla completa de grupo de AAD.

### Configuración de diagnósticos de reserva mediante la aplicación Configuración

Ahora, en la aplicación Configuración, un usuario puede configurar el comportamiento de diagnóstico [de reserva.](hololens-diagnostic-logs.md) En la aplicación Configuración, ve a la **página Solución**de problemas  ->  **** de privacidad para configurar esta opción.

> [!NOTE]
> Si hay una directiva MDM configurada para el dispositivo, el usuario no podrá invalidar ese comportamiento.  

### Compartir cosas con dispositivos cercanos

Comparte cosas con dispositivos cercanos a Windows 10, incluidos los equipos y otros dispositivos HoloLens 2 que ejecutan HoloLens Insider compilaciones 20279.1006+. Puedes probarlo en **** Experiencias compartidas del sistema de configuración para compartir archivos o direcciones  ->  ****  ->  **** URL de un HoloLens a un equipo. Para obtener más información, lee más sobre cómo [compartir cosas con dispositivos cercanos en Windows 10.](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)

Esta característica se puede administrar [a través de Connectivity/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices).

### Nuevo solucionador de problemas de actualización del sistema operativo

Además de los solucionadores de problemas anteriores de la aplicación Configuración, se ha agregado un nuevo solucionador de problemas con la adición de la nueva aplicación Configuración para actualizaciones del sistema operativo. Vaya a **Configuración**  ->  **de seguridad de actualización &amp; para**  ->  **solucionar**  ->  **problemas de Windows Update** y seleccione **Inicio.** Esto le permite recopilar seguimientos mientras reproduce el problema con las actualizaciones del sistema operativo para ayudar a solucionar mejor problemas con el departamento de TI o soporte técnico.

### Mejoras y correcciones en la actualización:

- [Los diagnósticos sin](hololens-diagnostic-logs.md#offline-diagnostics) conexión también incluirán información adicional del dispositivo para el número de serie y la versión del sistema operativo.






## Empezar a recibir compilaciones de Insider

> [!NOTE]
> Si no has actualizado recientemente, reinicia el dispositivo para actualizar el estado y obtener la compilación más reciente.
> - El comando de voz "Reiniciar dispositivo" funciona bien. 
> - También puedes elegir el botón reiniciar en Configuración/Programa Windows Insider.
>
> Hemos detectado un error en el back-end que puede que haya encontrado y esto le permitirá volver a realizar el seguimiento.

En un dispositivo HoloLens **** 2, ve a Actualización de configuración & Seguridad del  >  ****  >  **Programa Windows Insider** y selecciona **Introducción.** Vincula la cuenta que usó para registrarte como Windows Insider.

Windows Insider ahora se está moviendo a Canales. El anillo rápido se convertirá en **** el Canal **de desarrollo,** **** el anillo lento se convertirá en el canal **beta**y el anillo **de** vista previa de versión se convertirá en el canal de vista previa **de versión.** Este es el aspecto de esa asignación:

![Explicación de los canales de Windows Insider](images/WindowsInsiderChannels.png)

Para obtener más información, consulta [Introducción a los canales de Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) en blogs de Windows.

A continuación, selecciona Desarrollo activo de **Windows,** elige si quieres recibir compilaciones del Canal **de desarrollo** o del **Canal beta** y revisa los términos del programa.

Seleccione **Confirmar > Reiniciar ahora** para finalizar. Una vez reiniciado el dispositivo, ve a Configuración > Actualización & **Seguridad > Buscar** actualizaciones para obtener la compilación más reciente.

### Corrección de errores 0x80070490 actualización
Si se produce un error de actualización 0x80070490 al actualizar en el canal Dev o Beta, prueba el siguiente trabajo a corto plazo. Implica mover el canal de Insider, seleccionar la actualización y, a continuación, volver a mover el canal de Insider.

#### Fase uno: versión preliminar
1.  Configuración, Actualización & seguridad, Programa Windows Insider, seleccione **Liberar canal de vista previa.**
2.  Configuración, Actualización & seguridad, Windows Update, **Buscar actualizaciones.** Después de la actualización, continúe con la fase dos.

#### Fase dos: Canal de desarrollo
1. Configuración, Actualizar & seguridad, Programa Windows Insider, selecciona **Canal de desarrollo.**
2. Configuración, Actualización & seguridad, Windows Update, **Buscar actualizaciones.**

## Instrucciones de descarga e flash FFU
Para probar con un ffu firmado de piloto, primero tienes que desbloquear el dispositivo antes de parpadear el ffu firmado del piloto.
1. En pc:

    1. Descargar ffu en el equipo desde [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Instalar ARC (Advanced Recovery Companion) desde Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. En HoloLens - Desbloqueo **** piloto: Abre la actualización de configuración  >  **& Seguridad del**Programa  >  **Windows Insider** y, a continuación, regístrate y reinicia el dispositivo.

1. Flash FFU: ahora puedes flashear la FFU firmada del piloto con ARC.

## Proporcionar comentarios e informar sobre problemas

Use la [aplicación Centro de opiniones](hololens-feedback.md) en su HoloLens para proporcionar comentarios y notificar problemas. El uso del Centro de opiniones garantiza que se incluya toda la información de diagnóstico necesaria para ayudar a nuestros ingenieros a depurar y resolver el problema rápidamente.  Los problemas con la versión en chino y japonés de HoloLens deben informarse del mismo modo.

> [!NOTE]
> Asegúrate de aceptar el mensaje que te pregunta si quieres que el Centro de opiniones tenga acceso a la carpeta Documentos (selecciona **Sí** cuando se te solicite).

## Nota para desarrolladores

Le damos la bienvenida y le animamos a que pruebe a desarrollar sus aplicaciones con compilaciones de Insider de HoloLens.  Consulte la documentación [para desarrolladores de HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) para empezar. Esas mismas instrucciones funcionan con compilaciones de Insider de HoloLens.  Puedes usar las mismas compilaciones de Unity Visual Studio que ya estás usando para el desarrollo de HoloLens.

## Dejar de recibir compilaciones de Insider

Si ya no quieres recibir compilaciones de Insider de Windows Holographic, puedes optar por no [](hololens-recovery.md) participar cuando HoloLens ejecute una compilación de producción o puedes recuperar el dispositivo con advanced Recovery Companion para recuperar el dispositivo en una versión que no sea insider de Windows Holographic.

> [!CAUTION]
> Hay un problema conocido en el que los usuarios que no se inscriban en las compilaciones de Insider Preview después de reinstalar manualmente una nueva compilación de vista previa experimentarían una pantalla azul. Posteriormente, deben recuperar manualmente su dispositivo. Para obtener información completa sobre si se verían afectados o no, vea más información sobre [este problema conocido.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)

Para comprobar que HoloLens ejecuta una compilación de producción:

1. Ve a **Configuración > Información > sistema**y busca el número de compilación.

1. [Vea las notas de la versión de los números de compilación de producción.](hololens-release-notes.md)

Para optar por no participar en las compilaciones de Insider:

1. En un HoloLens que ejecuta una compilación de producción, ve a Configuración **> Actualizar & Seguridad > Programa Windows Insider**y selecciona Detener **compilaciones de Insider.**

1. Sigue las instrucciones para desactivar el dispositivo.
