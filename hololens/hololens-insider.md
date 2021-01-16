---
title: Versión preliminar de Insider para Microsoft HoloLens
description: Es fácil empezar con las compilaciones de Insider y proporcionar comentarios valiosos para nuestra próxima actualización principal del sistema operativo para HoloLens.
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
ms.date: 1/13/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 6df24d3a8640edeb9196834f940500aa51e85af7
ms.sourcegitcommit: 50e4d61a31b94d5007776064b4012e26cf9ecbbb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271733"
---
# Versión preliminar de Insider para Microsoft HoloLens

Te damos la bienvenida a las compilaciones más recientes de Insider Preview para HoloLens. Es fácil empezar y [proporcionar](hololens-insider.md#start-receiving-insider-builds) comentarios valiosos para nuestra próxima actualización principal del sistema operativo para HoloLens.

## Notas de la versión de Windows Insider

Estamos encantados de empezar a usar nuevas características para los usuarios de Windows Insider de nuevo. We will be flighting to the Dev Channel for the latest updates. Seguiremos actualizando esta página a medida que agreguemos más características y actualizaciones a nuestras compilaciones de Windows Insider.  Prepárate y listo para mezclar estas actualizaciones en tu realidad.

| Nombre de la característica                                              | Descripción corta                                                                      | Disponible en la compilación |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Nuevo Microsoft Edge](#introducing-the-new-microsoft-edge) | El nuevo Microsoft Edge basado en Chromium ya está disponible para HoloLens 2                         | 20279.1006 |
| [Aplicación Nueva configuración](#new-settings-app)                     | La aplicación Configuración heredada se está reemplazando por una versión actualizada con nuevas características y configuración | 20279.1006 |
| [Selector de aplicaciones predeterminado](#default-app-picker)                 | Elegir qué aplicación debe iniciarse para cada tipo de archivo o vínculo                                      | 20279.1006 |
| [Aplicación web de Office](#office-web-app)                         | Ahora se muestra un acceso directo a la aplicación web de Office en "Todas las aplicaciones"                                   | 20279.1006 |
| [Deslizar el dedo para escribir](#swipe-to-type)                           | Usar la punta del dedo para "deslizar rápidamente" palabras en el teclado holográfico                        | 20279.1006 |
| [Compatibilidad con micrófono externo USB-C](#usb-c-external-microphone-support) | Usa micrófonos USB-C para aplicaciones y/o asistencia remota.| 20279.1006 |
| [Nuevos AUMID para nuevas aplicaciones en modo de pantalla completa](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | AUMIDs para nuevas aplicaciones de Configuración y Edge | 20279.1006 |
| [Entrega de errores en el modo de pantalla completa mejorada](#kiosk-mode-behavior-changes-for-handling-of-failures) | El modo de pantalla completa busca el acceso asignado global antes del menú inicio vacío. | 20279.1006 |
| [Configurar diagnósticos de reserva](#configuring-fallback-diagnostics-via-settings-app) | Configuración del comportamiento de diagnóstico de reserva en la aplicación Configuración | 20279.1006 |

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
- Unirse a una llamada de Microsoft Teams a través del explorador con vídeo, captura de realidad mixta o pantalla compartida (unirse a llamadas con audio funciona bien)

**No se espera que los escenarios y las características funcionen:**
- Sonido espacial de varias ventanas con secuencias de audio simultáneas
- "Véalo, digalo"
- Impresión

**Principales problemas conocidos del explorador:**
- Restablecer el dispositivo quitará el nuevo Microsoft Edge
- La vista previa de lupa en el teclado holográfico muestra contenido incorrecto

### Aplicación Nueva configuración

Con esta versión, presentamos una nueva versión de la aplicación Configuración. La nueva aplicación Configuración incluye nuevas características y opciones de configuración expandidas para HoloLens 2 en las siguientes áreas: Sonido, Suspensión de Power &, Red & Internet, Aplicaciones, Cuentas, Facilidad de acceso y mucho más.

> [!NOTE]
> Dado que la nueva aplicación Configuración es distinta de la aplicación Configuración heredada, las ventanas de configuración que colocaste anteriormente en el entorno se quitarán al actualizarse.

![Página principal de la aplicación Nueva configuración](images/new-settings-app.png)

**Nuevas características y configuración**
- Búsqueda de configuración: buscar la configuración de la página principal de configuración con palabras clave o el nombre de la configuración
- Sonido > sistema:
  - Dispositivos de audio de entrada y salida: elige de forma independiente los dispositivos de audio de entrada y salida (por ejemplo, escucha audio a través de auriculares Bluetooth o usa un micrófono USB-C para la entrada de audio). Nota: Bluetooth holoLens 2 no admite los micrófonos.
  - Volumen de la aplicación: ajustar independientemente el volumen de cada aplicación
- Sistema > power & suspensión: elegir cuándo debe ir el dispositivo a suspensión después de un período de inactividad
- Sistema > batería: habilite manualmente el modo de ahorro de batería o establezca un umbral de batería en el que el modo de ahorro de batería se active automáticamente
- Dispositivos > USB: puedes deshabilitar las conexiones USB de forma predeterminada
- Red & Internet:
  - Los adaptadores Ethernet USB-C ahora aparecerán en Red & Internet
  - La configuración del adaptador Ethernet USB-C ya está disponible, incluida su dirección IP
  - Ahora puedes habilitar el modo avión en HoloLens 2
- Aplicaciones: puedes restablecer las aplicaciones predeterminadas usadas para los tipos de archivos y vínculos. Consulta [El selector de aplicaciones predeterminado](#default-app-picker) para obtener más información.
- Cuentas > otros usuarios: los propietarios de dispositivos pueden agregar usuarios, actualizar usuarios estándar a propietarios de dispositivos, degradar los propietarios de dispositivos a usuarios estándar y quitar usuarios.
- Facilidad de acceso: cambiar el tamaño del texto y algunos efectos visuales

**Problemas conocidos**
- Se quitarán las ventanas de configuración colocadas anteriormente (consulta la nota anterior)
- Visitar la página Notificaciones puede bloquear la aplicación Configuración (investigando)
- La página Ethernet no aparece actualmente (se solucionará próximamente)
- Es posible que el uso de la batería para el nuevo Microsoft Edge no sea preciso, debido a su naturaleza como una aplicación de escritorio Win32 compatible con una capa de adaptador para UWP (no se prevé ninguna corrección pronto).

### Selector de aplicaciones predeterminado

Cuando activas un hipervínculo o abres un tipo de archivo con más de una aplicación instalada que lo admite, verás una nueva ventana abierta en la que se te pedirá que selecciones qué aplicación instalada debe controlar el tipo de archivo o vínculo. En esta ventana también puedes elegir que la aplicación seleccionada controle el tipo de archivo o vínculo "Una vez" o "Siempre".

![Ventana del selector de aplicaciones](images/default-app-picker.png)

Si eliges "Siempre" pero más adelante quieres cambiar qué aplicación controla un tipo de archivo o vínculo determinado, puedes restablecer los valores predeterminados guardados en Configuración **> Aplicaciones.** Desplácese hasta la parte inferior **** de la página y seleccione el botón Borrar en "Aplicaciones predeterminadas para tipos de archivo" o "Aplicaciones predeterminadas para tipos de vínculos". A diferencia de la configuración similar en equipos de escritorio, no puedes restablecer valores predeterminados de tipos de archivo individuales.

### Aplicación web de Office

La aplicación web de Office se ha agregado a la lista "Todas las aplicaciones" en el menú Inicio. Esta aplicación web también se puede anclar a Inicio o desinstalarse. Dado que se trata de una aplicación web, su funcionalidad coincide exactamente con lo que experimentarías visitando https://www.office.com . La funcionalidad de la aplicación web de Office solo está disponible cuando holoLens 2 tiene una conexión a Internet activa.

### Deslizar el dedo para escribir

A algunos clientes les resulta más rápido "escribir" en teclados virtuales deslizando el dedo por la forma de la palabra que pretenden escribir y estamos haciendo una vista previa de esta característica para el teclado holográfico. Puedes deslizar el dedo una palabra a la vez pasando la punta del dedo a través del plano del teclado holográfico, deslizando el dedo por la forma de la palabra y, a continuación, retirando la punta del dedo del plano del teclado. Puedes deslizar rápidamente las palabras de seguimiento sin necesidad de presionar la barra espaciadora quitando el dedo del teclado entre palabras. Sabrás que la característica funciona si ves una pista de deslizar el dedo después del movimiento del dedo en el teclado.

Ten en cuenta que esta característica puede ser difícil de usar y usar debido a la naturaleza de un teclado holográfico en el que no sientas resistencia contra el dedo (a diferencia de una pantalla de teléfono móvil). Estamos evaluando esta característica para la versión pública, por lo que sus comentarios son importantes; si encuentras la característica útil o tienes comentarios sobre la regeneración, háganoslo saber a través del Centro [de opiniones.](hololens-feedback.md)

### Compatibilidad con micrófono externo USB-C

> [!IMPORTANT]
> Conectar un **micrófono USB no lo establecerá automáticamente como el dispositivo de entrada.** Al conectar un conjunto de auriculares USB-C, los usuarios observarán que el audio de los auriculares se redirigirá automáticamente a los auriculares, pero el sistema operativo HoloLens da prioridad a la matriz de micrófonos internos por encima de cualquier otro dispositivo de entrada. **Para usar un micrófono USB-C, sigue los pasos siguientes.**

Ahora, los usuarios pueden seleccionar micrófonos externos conectados a USB-C mediante el panel **de** configuración de sonido. Esto permite a los usuarios usar su propio micrófono conectado pero USB en la grabación y las aplicaciones. Los micrófonos USB-C son fáciles de habilitar y usar.

Abra la **aplicación Configuración** y seleccione **Sonido del**  ->  **sistema.**

![Configuración de sonido](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Para usar micrófonos externos con **asistencia remota,** los usuarios tendrán que hacer clic en el hipervínculo "Administrar dispositivos de sonido".
>
> A continuación, use la lista desplegable para establecer el micrófono externo como **Predeterminado** o **Predeterminado de comunicaciones.** Elegir Predeterminado **significa** que el micrófono externo se usará en todas partes.
>
> Elegir Communications **Default** significa que el micrófono externo se usará en asistencia remota y otras aplicaciones de comunicaciones, pero la matriz de micrófono de HoloLens puede seguir usándose para otras tareas.

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

Al incluir aplicaciones [](hololens-kiosk.md)en quioscos, un administrador de TI a menudo agrega la aplicación al quiosco, pero con su id. de modelo de usuario de aplicación (AUMID). Dado que tanto la aplicación Configuración como la aplicación de Microsoft Edge se consideran nuevas aplicaciones y son diferentes a las pantallas de pantalla completa de las aplicaciones anteriores que usan AUMIDs para esas aplicaciones, tendrán que actualizarse para usar el nuevo AUMID.

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






## Empezar a recibir compilaciones de Insider

> [!NOTE]
> Si no has actualizado recientemente, reinicia el dispositivo para actualizar el estado y obtener la compilación más reciente.
> - El comando de voz "Reiniciar dispositivo" funciona bien. 
> - También puedes elegir el botón reiniciar en Configuración/Programa Windows Insider.
>
> Hemos detectado un error en el back-end que puede que haya encontrado y esto le permitirá volver a realizar el seguimiento.

En un dispositivo HoloLens **** 2, ve a Actualización de configuración & Seguridad del  >  ****  >  **Programa Windows Insider** y selecciona **Introducción.** Vincula la cuenta que usó para registrarte como Windows Insider.

Windows Insider ahora se está trasladando a Canales. El **anillo** rápido se convertirá en **** el Canal **de desarrollo,** **** el anillo lento se convertirá en el canal **beta**y el anillo de vista previa de versión se convertirá en el canal de vista previa **de versión.** Este es el aspecto de esa asignación:

![Explicación de Los canales de Windows Insider](images/WindowsInsiderChannels.png)

Para obtener más información, consulta [Introducción a los canales de Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) en blogs de Windows.

A continuación, selecciona Desarrollo activo de **Windows,** elige si quieres recibir compilaciones del Canal **de desarrollo** o **canal beta** y revisa los términos del programa.

Seleccione **Confirmar > Reiniciar ahora** para finalizar. Una vez reiniciado el dispositivo, ve a Configuración > Actualización & Seguridad > **Buscar** actualizaciones para obtener la compilación más reciente.

## Instrucciones de descarga e flash FFU
Para probar con un ffu firmado de piloto, primero tienes que desbloquear el dispositivo antes de parpadear el ffu firmado del piloto.
1. En pc:

    1. Descargar ffu en el equipo desde [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Instala ARC (Advanced Recovery Companion) desde Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. En HoloLens - Desbloqueo **** piloto: Abre la actualización de configuración  >  **& Seguridad del**Programa  >  **Windows Insider** y, a continuación, regístrate y reinicia el dispositivo.

1. Flash FFU: ahora puedes flashear la FFU firmada del piloto con ARC.

## Enviar comentarios e informar sobre problemas

Use la [aplicación Centro de opiniones](hololens-feedback.md) en su HoloLens para proporcionar comentarios y notificar problemas. El uso del Centro de opiniones garantiza que se incluya toda la información de diagnóstico necesaria para ayudar a nuestros ingenieros a depurar y resolver el problema rápidamente.  Los problemas con la versión en chino y japonés de HoloLens deben informarse del mismo modo.

> [!NOTE]
> Asegúrate de aceptar el mensaje que te pregunta si quieres que el Centro de opiniones tenga acceso a la carpeta Documentos **(selecciona** Sí cuando se te solicite).

## Nota para desarrolladores

Le damos la bienvenida y le animamos a que pruebe a desarrollar sus aplicaciones con compilaciones de Insider de HoloLens.  Consulte la documentación [para desarrolladores de HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) para empezar. Esas mismas instrucciones funcionan con compilaciones de Insider de HoloLens.  Puedes usar las mismas compilaciones de Unity Visual Studio que ya estás usando para el desarrollo de HoloLens.

## Dejar de recibir compilaciones de Insider

Si ya no quieres recibir compilaciones de Insider de Windows Holographic, puedes optar por no [](hololens-recovery.md) participar cuando HoloLens ejecute una compilación de producción o puedes recuperar el dispositivo con advanced Recovery Companion para recuperar el dispositivo en una versión que no sea insider de Windows Holographic.

> [!CAUTION]
> Hay un problema conocido en el que los usuarios que desconscriban las compilaciones de Insider Preview después de reinstalar manualmente una nueva compilación de vista previa experimentarían una pantalla azul. Posteriormente, deben recuperar manualmente su dispositivo. Para obtener información completa sobre si se verían afectados o no, vea más información sobre [este problema conocido.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)

Para comprobar que HoloLens ejecuta una compilación de producción:

1. Ve a **Configuración > del > acerca de**y busca el número de compilación.

1. [Vea las notas de la versión de los números de compilación de producción.](hololens-release-notes.md)

Para optar por no participar en las compilaciones de Insider:

1. En un HoloLens que ejecuta una compilación de producción, ve a Configuración **> Actualizar & Seguridad > Programa Windows Insider**y selecciona Detener **compilaciones de Insider.**

1. Sigue las instrucciones para desactivar el dispositivo.
