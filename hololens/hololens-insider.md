---
title: Versión preliminar de Insider para Microsoft HoloLens
description: Obtenga información sobre cómo empezar a trabajar con compilaciones de Insider y proporcionar comentarios valiosos para nuestra próxima actualización principal del sistema operativo para HoloLens.
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
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: ebd3992458daa94726e73742b1fba4d7fa97a48b
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310187"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Versión preliminar de Insider para Microsoft HoloLens

Le damos la bienvenida a las últimas compilaciones de Insider Preview para HoloLens. Es fácil empezar a trabajar [y proporcionar](hololens-insider.md#start-receiving-insider-builds) comentarios valiosos para nuestra próxima actualización importante del sistema operativo para HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Insider notas de la versión

Nos complace empezar a pasar nuevas características a Windows Insiders de nuevo. Las nuevas compilaciones pasarán al canal de desarrollo para obtener las actualizaciones más recientes. Seguiremos actualizando esta página a medida que agreguemos más características y actualizaciones a nuestras Windows Insider compilaciones.  Prepárese para mezclar estas actualizaciones en su realidad.

Esta actualización de características contiene características para dos audiencias de destino. Características que puede usar cualquier usuario en un dispositivo por el usuario final y nuevas opciones de administración de dispositivos que pueden configurar los administradores de TI. En la tabla de características siguiente se especifica el público con quién puede usar cada nueva característica. Si es un administrador de TI, consulte nuestra lista de comprobación de actualización del administrador [de TI.](#it-admin---update-checklist)

> [!IMPORTANT]
> Si anteriormente usaba la aplicación Configuración o Microsoft Edge en un quiosco, hemos reemplazado estas aplicaciones por nuevas aplicaciones que usan un identificador de aplicación diferente. Le recomendamos encarecidamente que lea [AUMID nuevos](#use-the-new-settings-and-edge-apps-in-kiosk-modes) para las nuevas aplicaciones en pantalla completa a continuación. Esto garantizará que sigue teniendo la aplicación Configuración en el quiosco o que incluye la nueva aplicación Microsoft Edge pantalla completa.

<br>

| Nombre de la característica                                              | Descripción breve                                                                      | Público de destino | Disponible en la compilación |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|------|
| [Nuevo Microsoft Edge](#introducing-the-new-microsoft-edge) | La nueva versión basada en Chromium Microsoft Edge ahora está disponible para HoloLens 2                         | Usuario final | 20279.1006 |
| [WebXR y visor 360](#webxr-and-360-viewer)             | Prueba de experiencias web envolventes y reproducción de vídeo de 360                                           | Usuario final | 20289.1000 |
| [Nueva aplicación de configuración](#new-settings-app)                     | La aplicación de configuración heredada se está reemplazando por una versión actualizada con nuevas características y configuraciones. | Usuario final | 20279.1006 |
| [Calibración del color de la pantalla](#display-color-calibration)   | Selección de un perfil de color alternativo para la HoloLens 2 pantalla                                | Usuario final | 20293.1000 |
| [Selector de aplicaciones predeterminado](#default-app-picker)                 | Elegir qué aplicación debe iniciarse para cada tipo de archivo o vínculo                                      | Usuario final | 20279.1006 |
| [Control de volumen por aplicación](#per-app-volume-control) |  Control del volumen de nivel de aplicación independientemente del volumen del sistema | Usuario final | 20293.1000 |
| [Aplicación web de Office](#office-web-app)                         | Ahora se muestra un acceso directo a la aplicación web de Office en "Todas las aplicaciones".                                   | Usuario final | 20279.1006 |
| [Deslizar el dedo para escribir](#swipe-to-type)                           | Use la punta del dedo para "deslizar" las palabras en el teclado holográfico                        | Usuario final | 20279.1006 |
| [Menú De encendido desde Inicio](#power-menu-from-start) | En el menú Inicio, reinicie y apague el dispositivo HoloLens. | Usuario final | 20293.1000 |
| [Varios usuarios enumerados en la pantalla de inicio de sesión](#multiple-users-listed-on-sign-in-screen) | Mostrar varias cuentas de usuario en la pantalla Inicio de sesión | Usuario final | 20293.1000 |
| [Compatibilidad con micrófono externo USB-C](#usb-c-external-microphone-support) | Use micrófonos USB-C para aplicaciones y/o Remote Assist.| Usuario final | 20279.1006 |
| [Inicio de sesión automático del visitante para quioscos](#visitor-auto-logon-for-kiosks)                          | Permite que el inicio de sesión automático en las cuentas de visitante se utilice para los modos de quiosco.                         | Administración de TI | 20279.1006                 |
| [Nuevos AUMID para nuevas aplicaciones en pantalla completa](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | AUMIDs para nuevas aplicaciones de Configuración y Edge | Administración de TI | 20279.1006 |
| [Entrega de errores en pantalla completa mejorada](#kiosk-mode-behavior-changes-for-handling-of-failures) | El modo de pantalla completa busca Acceso asignado global antes del menú inicio vacío. | Administración de TI | 20279.1006 |
| [Nueva configuraciónDI para la visibilidad de la configuración de página](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | Más de 20 nuevas configuracionesDI para la directiva Settings/PageVisibilityList | Administración de TI | 20289.1000 |
| [Configuración de diagnósticos de reserva](#configuring-fallback-diagnostics-via-settings-app) | Establecer el comportamiento de diagnóstico de reserva en la aplicación configuración | Administración de TI | 20279.1006 |
| [Compartir cosas con dispositivos cercanos](#share-things-with-nearby-devices) | Compartir archivos o direcciones URL desde HoloLens a un equipo | All | 20279.1006 |
| [Nuevo solucionador de problemas de actualización del sistema operativo](#new-os-update-troubleshooter) | Nuevo solucionador de problemas en Configuración de actualizaciones del sistema operativo | Administración de TI | 20279.1006 |
| [Optimización de distribución versión preliminar](#delivery-optimization-preview) | Reducir el consumo de ancho de banda para las descargas de varios dispositivos HoloLens | Administración de TI | 20301.1000 |
| [Mejoras y correcciones en la actualización](#improvements-and-fixes-in-the-update) | Correcciones adicionales en la actualización. | All | 20279.1006 |

### <a name="it-admin---update-checklist"></a>Administrador de TI: lista de comprobación de actualización

Esta lista de comprobación le ayudará a conocer los nuevos elementos que se van a agregar en esta actualización de características que pueden afectar a las configuraciones actuales de administración de dispositivos o a las nuevas características que podría empezar a usar.

#### <a name="updates-to-kiosk-mode"></a>Actualizaciones en pantalla completa

[**Nuevos AUMID para nuevas aplicaciones en pantalla completa**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Si anteriormente usaba la aplicación Configuración o Microsoft Edge en un quiosco, hemos reemplazado estas aplicaciones por nuevas aplicaciones que usan un identificador de aplicación diferente. Le recomendamos encarecidamente que lea [AUMID nuevos](#use-the-new-settings-and-edge-apps-in-kiosk-modes) para las nuevas aplicaciones en pantalla completa a continuación. Esto garantizará que sigue teniendo la aplicación Configuración en el quiosco o que incluye la nueva aplicación Microsoft Edge pantalla completa.

Estos cambios se pueden realizar ahora, implementarse en todos los dispositivos y permitir una transición más fluida en la actualización.

[**Inicio de sesión automático del visitante para quioscos**](#visitor-auto-logon-for-kiosks)

Ahora, los visitantes pueden iniciar sesión automáticamente en un quiosco. Este comportamiento está habilitado de forma predeterminada, pero se puede administrar y deshabilitar.

[**Entrega de errores en pantalla completa mejorada**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Si no se determina correctamente la pertenencia al grupo de AAD del usuario de AAD que ha iniciado sesión, se usa la configuración de pantalla completa global para el menú inicio (si está presente). De lo contrario, el usuario se presenta con el menú inicio vacío. Aunque el menú inicio vacío no es una configuración que se puede establecer directamente, este nuevo control puede ser algo que informe al departamento de soporte técnico si usa quioscos, ya que esto puede aplicarse a las configuraciones o puede que desee realizar nuevos ajustes en las configuraciones de acceso asignadas.

#### <a name="updates-to-page-settings-visibility"></a>Actualizaciones de visibilidad de la configuración de página

[**Nueva configuraciónDI para la visibilidad de la configuración de página**](hololens-insider.md#new-settingsuris-for-page-settings-visibility)

Si actualmente usa visibilidad [de](settings-uri-list.md) la configuración de página, es posible que desee realizar ajustes en los URI existentes que ha permitido o bloqueado.

#### <a name="updates-for-your-wdac-policy"></a>Actualizaciones de la directiva wdac

Si anteriormente estaba bloqueando Microsoft Edge a través de WDAC, querrá actualizar la directiva de WDAC. Revise [lo siguiente y](#using-wdac-to-block-new-microsoft-edge) use el código de ejemplo proporcionado.

#### <a name="enable-new-endpoints-for-edge"></a>Habilitación de nuevos puntos de conexión para Edge

Si tiene una infraestructura que implica la configuración de puntos de conexión de red como proxy o firewall, habilite estos nuevos puntos de conexión para la [nueva Microsoft Edge aplicación.](#managing-endpoints-for-the-new-microsoft-edge)

#### <a name="newly-configurable-items"></a>Elementos recién configurables

- [Configuración de diagnósticos de reserva](#configuring-fallback-diagnostics-via-settings-app)
  - Puede configurar si y quién puede recopilar diagnósticos de reserva.
- [Compartir cosas con dispositivos cercanos](#share-things-with-nearby-devices)
  - Puede deshabilitar la nueva característica de uso compartido cercano.
- [Configuración de las opciones de directiva para el nuevo Microsoft Edge](#configuring-policy-settings-for-the-new-microsoft-edge)
  - Revise las configuraciones recién disponibles para Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Nueva herramienta de diagnóstico

- [Nuevo solucionador de problemas de actualización del sistema operativo](#new-os-update-troubleshooter)
  - Recopilación de registros relacionados con las actualizaciones del sistema operativo

### <a name="introducing-the-new-microsoft-edge"></a>Presentación de la nueva Microsoft Edge

![Animación del logotipo de Microsoft Edge heredado al nuevo logotipo Microsoft Edge personalizado](images/new-edge.gif)

El nuevo Microsoft Edge adopta el proyecto de código abierto [Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) para crear una mejor compatibilidad para los clientes y una menor fragmentación de la web para desarrolladores web.

Con esta versión preliminar de Insider, el nuevo Microsoft Edge está disponible para HoloLens 2 clientes por primera vez. Aunque el nuevo Microsoft Edge reemplazará a los Microsoft Edge heredados en HoloLens 2, ambos exploradores están disponibles actualmente para insiders. Comparta comentarios y errores con  nuestro equipo a través de la característica Enviar comentarios en la nueva Microsoft Edge o a través [de Centro de opiniones](hololens-feedback.md).

![Nueva captura Microsoft Edge pantalla](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Inicio de la nueva Microsoft Edge

Hay dos versiones de Microsoft Edge disponibles para insiders: el nuevo icono Microsoft Edge Microsoft Edge (representado por un icono de remolino azul y verde) y el Microsoft Edge heredado (representado por el icono ![ ](images/new_edge_logo.png) "e" blanco). La nueva Microsoft Edge se ancla al menú Inicio y se iniciará automáticamente al activar un vínculo web. Si desea revertir al uso de aplicaciones heredadas Microsoft Edge como explorador web predeterminado, consulte las instrucciones siguientes para restablecer [las aplicaciones predeterminadas.](#default-app-picker)

> [!NOTE]
> La primera vez que inicie el nuevo Microsoft Edge en HoloLens 2, la configuración y los datos se importarán desde la base de datos Microsoft Edge. Si sigue usando los Microsoft Edge heredados después de iniciar el nuevo Microsoft Edge, los nuevos datos no se sincronizarán de la Microsoft Edge heredada a la nueva Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Configuración de las opciones de directiva para el nuevo Microsoft Edge

La nueva Microsoft Edge ofrece a los administradores de TI un conjunto mucho más amplio de directivas de explorador en HoloLens 2 que estaban disponibles previamente con el Microsoft Edge.

Estos son algunos recursos útiles para obtener más información sobre cómo administrar la configuración de directivas para el nuevo Microsoft Edge:

- [Configuración Microsoft Edge configuración de directivas con Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Microsoft Edge (versión anterior) para Microsoft Edge directiva](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome para asignar Microsoft Edge directiva](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Documentación [Microsoft Edge Enterprise](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> Debido al volumen de directivas de explorador admitidas por el nuevo Microsoft Edge, nuestro equipo no puede garantizar que cada nueva directiva funcione en HoloLens 2. Sin embargo, hemos probado y confirmado que el nuevo Microsoft Edge equivalente de cada directiva de Microsoft Edge heredada admitida anteriormente en HoloLens 2 funcionan según lo previsto. Consulte Microsoft Edge (versión anterior) para [Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) asignación de directivas para encontrar el nuevo Microsoft Edge equivalente de cada directiva de explorador de Microsoft Edge heredada que estaba usando con HoloLens 2.
>
> Hay al menos dos nuevas directivas Microsoft Edge que sabemos *que no funcionarán* con HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Qué esperar de la nueva Microsoft Edge en HoloLens 2

Dado que el nuevo Microsoft Edge es una aplicación Win32 nativa con una nueva capa de adaptador de UWP que le permite ejecutarse en dispositivos solo para UWP como HoloLens 2, es posible que algunas características no estén disponibles inmediatamente. En los próximos meses se admitirán nuevos escenarios y características, así que compruebe este espacio para obtener información actualizada.

**Escenarios y características que se espera que funcionen:**
- Experiencia de primera ejecución, inicio de sesión en el perfil y sincronización
- Los sitios web deben representarse y comportarse según lo previsto
- La mayoría de las funcionalidades del explorador (Favoritos, Historial, etc.) deben funcionar según lo previsto.
- Modo oscuro
- Instalación de aplicaciones web en el dispositivo
- Instalación de extensiones (háganos saber si usa extensiones que no funcionan correctamente en HoloLens 2)
- Visualización y marcado de un PDF
- Sonido espacial desde una sola ventana del explorador
- Actualización automática y manual del explorador
- Guardar un PDF en el menú Imprimir (con la opción "Guardar en PDF")
- Extensión WebXR y visor 360
- Restauración del contenido a la ventana correcta, al examinar varias ventanas colocadas en el entorno

**Escenarios y características que no se espera que funcionen:**
- Sonido espacial de varias ventanas con secuencias de audio simultáneas
- "See it, say it" (Verlo, decir)
- Impresión

**Principales problemas conocidos del explorador:**
- Wi-Fi configuraciones de proxy, que son directivas de proxy destinadas a conexiones de Wi-Fi individuales, no funcionan actualmente con el nuevo Microsoft Edge. Estamos trabajando activamente para desbloquear este problema antes del lanzamiento público de la actualización del sistema operativo.
- La vista previa de lupa en el teclado holográfico se ha deshabilitado para el nuevo Microsoft Edge. Esperamos volver a crear esta característica en una actualización futura, una vez que la ampliación funcione correctamente.
- Dos caracteres en el teclado japonés no funcionan como se esperaba en el nuevo Microsoft Edge. Este problema se ha producido en la raíz y debe solucionarse pronto.
- Es posible que los vínculos web Microsoft Store aplicación no inicien el explorador
- El audio puede reproducirse desde la ventana del explorador incorrecta si tiene otra ventana del explorador abierta y activa. Para evitar este problema, cierre la otra ventana activa que no se supone que esté reproduciendo audio.
- Al reproducir audio desde una ventana del explorador en modo ["Sígueme",](hololens2-basic-usage.md#follow-me-stop-following)el audio seguirá reproduciendo si deshabilita el modo "Sígueme". Para evitar este problema, detenga la reproducción de audio antes de deshabilitar el modo "Sígueme" o cierre la ventana con el **botón X.**
- La interacción con ventanas Microsoft Edge activas puede hacer que otras ventanas de aplicaciones 2D se vuelvan inactivas inesperadamente. Para reactivar estas ventanas, vuelva a interactuar con ellas.
- La apertura de un vínculo web desde otra aplicación, o determinados tipos de documentos como archivos PDF, puede hacer que se abra una segunda pestaña en blanco en el explorador (además de la nueva pestaña creada con el contenido del vínculo web o el vínculo de archivo). Para evitar este problema, cierre la pestaña en blanco adicional.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge canales insider

El Microsoft Edge hace que tres canales de versión preliminar estén disponibles para la comunidad de Edge Insider: Beta, Dev y Canary. La instalación de un canal de versión preliminar no desinstala la versión publicada de Microsoft Edge en el HoloLens 2, y puede instalar más de una al mismo tiempo. 

Visite la [página principal Microsoft Edge Insider para](https://www.microsoftedgeinsider.com) obtener más información sobre la comunidad de Edge Insider. Para obtener más información sobre los diferentes canales de Edge Insider y empezar a trabajar, visite la página de descarga [de Edge Insider](https://www.microsoftedgeinsider.com/download).

Hay un par de métodos disponibles para instalar canales Microsoft Edge Insider para HoloLens 2:

**Instalación directa en el dispositivo (actualmente solo disponible para dispositivos no administrados)**
  1. En la HoloLens 2, visite la página [de descarga de Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Seleccione el **botón Descargar HoloLens 2** para el canal de Edge Insider que desea instalar.
  1. Inicie el archivo .msix descargado desde la cola de descarga de Edge o desde la carpeta "Descargas" del dispositivo (mediante Explorador de archivos).
  1. [Se iniciará el instalador](app-deploy-app-installer.md) de la aplicación.
  1. Seleccione el botón **Instalar**.
  1. Después de una instalación correcta, encontrará Microsoft Edge Beta, Dev o Canary  como una entrada independiente en la lista Todas las aplicaciones de la menú Inicio.

**Instalación mediante PC con Portal de dispositivos Windows (requiere que [el modo de](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) desarrollador esté habilitado en HoloLens 2)**
  1. En el equipo, visite la página [de descarga de Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Seleccione el **botón de flecha desplegable** situado junto al botón "Descargar para Windows 10" del canal de Edge Insider que desea instalar.
  1. Seleccione **HoloLens 2** en el menú desplegable.
  1. Guarde el archivo .msix en la carpeta "Descargas" del equipo (u otra carpeta que pueda encontrar fácilmente).
  1. Use [Portal de dispositivos Windows](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) en el equipo para instalar el archivo .msix descargado en HoloLens 2.
  1. Después de una instalación correcta, encontrará Microsoft Edge Beta, Dev o Canary  como una entrada independiente en la lista Todas las aplicaciones de la menú Inicio.

> [!NOTE]
> Durante esta Windows Insider versión preliminar para HoloLens 2, la versión de Microsoft Edge en el dispositivo puede ser mayor que la disponible en algunos (o todos) de los canales de Microsoft Edge Insider. Esto es para garantizar que las nuevas características y correcciones dirigidas específicamente al explorador web en HoloLens 2 están corriendo a nuestros usuarios de Windows Insider lo antes posible. Poco después del lanzamiento público de la próxima actualización de Windows, las compilaciones del canal de Microsoft Edge Insider superarán y se mantendrán por delante de la versión de Microsoft Edge en el HoloLens 2.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Uso de WDAC para bloquear nuevas Microsoft Edge

Para los administradores de TI que buscan actualizar su directiva [WDAC](windows-defender-application-control-wdac.md) para bloquear la nueva aplicación Microsoft Edge, deberá agregar lo siguiente a la directiva.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Administración de puntos de conexión para la nueva Microsoft Edge

Algunos entornos pueden tener restricciones de red para tener en cuenta como consideración. Para garantizar una experiencia sin problemas con el nuevo edge, habilite [estos puntos de conexión de Microsoft.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

Obtenga más información sobre los puntos de [conexión disponibles actualmente para HoloLens.](hololens-offline.md)

### <a name="webxr-and-360-viewer"></a>WebXR y visor 360

*Se ha agregado Windows Insider compilación 20289.1000*

La nueva Microsoft Edge compatibilidad con WebXR, que es el nuevo estándar para crear experiencias web envolventes (reemplazando WebVR). Muchas experiencias web envolventes se diseñaron pensando en la realidad virtual (reemplazan el campo de vista por un entorno virtual), pero estas experiencias también son compatibles con HoloLens 2. El estándar WebXR también permite experiencias web envolventes de realidad aumentada y mixta que usan su entorno físico. A medida que los desarrolladores dedican más tiempo con WebXR, se prevé que lleguen nuevas experiencias envolventes de realidad mixta y aumentada para que los clientes HoloLens 2 prueben.

La extensión 360 Viewer se basa en WebXR y se instala automáticamente junto con el nuevo Microsoft Edge en HoloLens 2. Esta extensión web le ofrece la posibilidad de inmersarse en vídeos de 360 grados. YouTube ofrece la mayor selección de 360 vídeos, por lo que le recomendamos que empiece allí.

#### <a name="how-to-use-webxr"></a>Uso de WebXR

1. Vaya a un sitio web con compatibilidad con WebXR.
1. Seleccione el **botón Enter VR (Escribir VR)** en el sitio web. La ubicación y la representación visual de este botón pueden variar según el sitio web, pero puede tener un aspecto similar al siguiente:

    ![Ejemplo de botón Escribir VR](images/75px-enter-vr.png)

1. La primera vez que intente iniciar una experiencia de WebXR en un dominio específico, el explorador le pedirá su consentimiento para entrar en una vista inmersiva y seleccione **Permitir**.
1. Use [HoloLens 2 gestos para](hololens2-basic-usage.md#the-hand-tracking-frame) manipular la experiencia.
1. Si la experiencia no tiene un botón **Salir,** use el gesto [Iniciar](hololens2-basic-usage.md#start-gesture) para volver a casa.

**Ejemplos recomendados de WebXR**
- Visor 360 (consulte la sección siguiente)
- [Dinosaurios XR](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>Uso del Visor 360

1. Vaya a un vídeo de 360 grados en YouTube.
1. En el fotograma de vídeo, seleccione el botón mixed reality headset (Casco de realidad mixta):

    ![Botón para activar el Visor 360](images/enter-360-viewer.jpg)

1. La primera vez que intente iniciar el Visor 360 en un dominio específico, el explorador le pedirá su consentimiento para entrar en una vista inmersiva. seleccione **Permitir**.
1. [Pulse en el](hololens2-basic-usage.md#select-using-air-tap) aire para abrir los controles de reproducción. Use [los rayos de](hololens2-basic-usage.md#select-using-air-tap) las manos y el toque de aire para reproducir/pausar, omitir hacia delante y atrás, activar o desactivar subtítulos o detener la experiencia (que sale de la vista inmersiva). Los controles de reproducción desaparecerán después de unos segundos de inactividad.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Principales problemas conocidos de WebXR y 360 Viewer
- En función de la complejidad de la experiencia de WebXR, la velocidad de fotogramas puede despeinar o despeinar.
- La compatibilidad con las uniones de manos articuladas en WebXR no está habilitada de forma predeterminada. Los desarrolladores pueden habilitar la compatibilidad `edge://flags` a través de activando "WebXR Hand Input".
- Al salir de una experiencia de Visor de WebXR o 360, los hologramas del ambiente principal pueden tardar 30 segundos o más en volver a aparecer.
- Es posible que 360 vídeos de sitios web que no son YouTube no funcionen según lo previsto.
- Los títulos están deshabilitados actualmente en el Visor 360 HoloLens 2. Tenemos previsto habilitar esta característica en una actualización futura.
- Pausar un vídeo en el Visor 360 impide que se reproteja el vídeo (pero al seleccionar el botón de reproducción se reanuda correctamente la reproducción).
- El botón "Siguiente vídeo" del Visor 360 no funciona actualmente.
- Puede reproducir vídeos 2D en un modo envolvente de "cine", pero la velocidad de fotogramas puede ser inferior a 30 fps.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Proporcionar comentarios sobre WebXR y 360 Viewer

Comparta comentarios y errores con nuestro equipo a través de **la característica Enviar** comentarios de la nueva Microsoft Edge.

### <a name="new-settings-app"></a>Nueva aplicación de configuración

Con esta versión, presentamos una nueva versión de la aplicación Configuración. La nueva aplicación Configuración incluye nuevas características y configuraciones expandidas para HoloLens 2 en las áreas siguientes: Sonido, Suspensión de Power &, Red & Internet, Aplicaciones, Cuentas, Accesibilidad, etc.

> [!NOTE]
> Dado que la nueva aplicación Configuración es distinta de la aplicación configuración heredada, las ventanas de configuración que se colocaron anteriormente en el entorno se quitarán al actualizarse.

![Página principal de la aplicación Nueva configuración](images/new-settings-app.png)

**Nuevas características y configuración**
- Búsqueda de configuración: busque la configuración en la página principal Configuración mediante palabras clave o el nombre de la configuración.
- Sonido > sistema:
  - Dispositivos de audio de entrada y salida: elija de forma independiente los dispositivos de audio de entrada y salida (por ejemplo, escuche audio a través de auriculares Bluetooth o use un micrófono USB-C para la entrada de audio).
    > [!NOTE]
    > Los micrófonos Bluetooth no son compatibles con HoloLens 2.
  - Volumen de la aplicación: ajuste de forma independiente el volumen de cada aplicación. Vea [por control de volumen de aplicación.](#per-app-volume-control)
- Sistema > Power & suspensión: elija cuándo debe entrar en suspensión el dispositivo después de un período de inactividad.
- Batería > sistema: habilite manualmente el modo ahorro de batería o establezca un umbral de batería en el que ahorro de batería modo se active automáticamente.
- Dispositivos > USB: puede deshabilitar las conexiones USB de forma predeterminada.
- Red & Internet:
  - Los adaptadores Ethernet USB-C aparecerán ahora en Red & Internet.
  - La configuración del adaptador Ethernet USB-C ya está disponible, incluida su dirección IP.
  - Ahora puede habilitar el modo avión en HoloLens 2.
- Aplicaciones: puede restablecer las aplicaciones predeterminadas que se usan para los tipos de archivo y vínculo. Para obtener más información, [vea Selector de aplicaciones predeterminado.](#default-app-picker)
- Cuentas > otros usuarios: los propietarios de dispositivos pueden agregar usuarios, actualizar usuarios estándar a propietarios de dispositivos, degradar los propietarios de dispositivos a usuarios estándar y quitar usuarios.
- Accesibilidad: cambiar el tamaño del texto y algunos efectos visuales.

**Problemas conocidos**
- Se quitarán las ventanas de configuración colocadas anteriormente (consulte la nota anterior).
- Ya no puede cambiar el nombre del dispositivo con la aplicación Configuración. Los administradores de TI pueden cambiar el nombre de los dispositivos mediante Windows Autopilot para una [HoloLens 2 plantilla](https://docs.microsoft.com/hololens/hololens2-autopilot) de nombre de dispositivo o el nodo MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- La página Ethernet muestra un dispositivo Ethernet virtual ("UsbNcm") en todo momento.
- El uso de batería para el nuevo Microsoft Edge puede no ser preciso, debido a su naturaleza como una aplicación de escritorio Win32 compatible con una capa de adaptador de UWP (no se prevé ninguna corrección pronto).

### <a name="display-color-calibration"></a>Calibración del color de la pantalla

*Se agregó en Windows Insider compilación 20293.1000*

Con esta nueva configuración, puede seleccionar un perfil de color alternativo para la HoloLens 2 pantalla. Esto puede ayudar a que los colores parezcan más precisos, especialmente en los niveles inferiores de brillo de la pantalla. La calibración del color de pantalla se puede encontrar en la aplicación Configuración, en la página System > Calibration (Calibración del sistema).

> [!NOTE]
> Dado que esta configuración guarda un nuevo perfil de color en el firmware para mostrar, es una configuración por dispositivo (y no es única para cada cuenta de usuario).

#### <a name="how-to-use-display-color-calibration"></a>Uso de la calibración del color de la pantalla

1. Inicie la **aplicación Settings** (Configuración) y vaya a System > **Calibration (Calibración del sistema).**
1. En **Display color calibration (Calibración de color** para mostrar), seleccione el botón Run display color calibration **(Ejecutar calibración del color de presentación).**
1. Se iniciará la experiencia de calibración del color de la pantalla y se le animará a asegurarse de que el visor está en la posición correcta.
1. Después de continuar con los cuadros de diálogo de instrucciones, la pantalla se atenuará automáticamente hasta un 30 % de brillo.
    > [!TIP]
    > Si tiene problemas para ver la escena atenuada en su entorno, puede ajustar manualmente el nivel de brillo de HoloLens 2 mediante los botones de brillo del lado izquierdo del dispositivo.
1. Seleccione los botones 1 a 6 para probar al instante cada perfil de color y busque uno que se parezca mejor a los ojos (esto suele significar que el perfil que ayuda a que la escena parezca más neutra, con el patrón de escala de grises y los tonos de la máscara con el aspecto esperado).

    ![Visualización de la escena de calibración de color](images/color-cal-ui.png)
    
1. Cuando esté satisfecho con el perfil seleccionado, seleccione el botón **& Salir.**
1. Si prefiere no realizar cambios, seleccione el botón **Cancelar & Salir** y los cambios se revertirán.

> [!TIP]
> Estas son algunas sugerencias útiles que debe tener en cuenta al usar la configuración de calibración del color de la pantalla:
> - Puede volver a ejecutar la calibración del color de la pantalla desde Configuración siempre que quiera.
> - Si alguien del dispositivo ha usado previamente la configuración para cambiar los perfiles de color, la fecha y hora del cambio más reciente se reflejará en la página Configuración.
> - Al volver a ejecutar la calibración del color de presentación, se resaltará el perfil de color que se guardó anteriormente y el perfil 0 no aparecerá (ya que el perfil 0 representa el perfil de color original de la pantalla).
> - Si desea revertir al perfil de color original de la pantalla, puede hacerlo desde la página Configuración (consulte cómo restablecer el perfil [de color).](#how-to-reset-color-profile)

#### <a name="how-to-reset-color-profile"></a>Restablecimiento del perfil de color

Si no está satisfecho con el perfil de color personalizado guardado en la HoloLens 2, puede restaurar el perfil de color original del dispositivo:
1. Inicie la **aplicación Settings** (Configuración) y vaya a System > **Calibration (Calibración del sistema).**
1. En **Display color calibration (Calibración de** color para mostrar), seleccione el botón Reset to default color profile **(Restablecer el perfil de color** predeterminado).
1. Cuando se abra el cuadro de diálogo, **seleccione Reiniciar** si está listo para reiniciar HoloLens 2 aplicar los cambios.

#### <a name="top-display-color-calibration-known-issues"></a>Principales problemas conocidos de calibración del color de la pantalla

- En la página Configuración, la cadena de estado que indica cuándo se cambió por última vez el perfil de color estará sin actualizar hasta que vuelva a cargar esa página de Configuración.
    - Solución alternativa: seleccione otra página Configuración y, a continuación, vuelva a seleccionar la página Calibración.

### <a name="default-app-picker"></a>Selector de aplicaciones predeterminado

Al activar un hipervínculo o abrir un tipo de archivo con más de una aplicación instalada, que lo admite, verá una nueva ventana abierta que le pedirá que seleccione qué aplicación instalada debe controlar el tipo de archivo o vínculo. En esta ventana, también puede elegir que la aplicación seleccionada controle el archivo o el tipo de vínculo "Once" o "Always".

![Ventana del selector de aplicaciones](images/default-app-picker.png)

Si elige "Siempre" pero más adelante quiere cambiar qué aplicación controla un tipo de archivo o vínculo determinado, puede restablecer los valores predeterminados guardados en Configuración **> Aplicaciones**. Desplácese hasta la parte inferior  de la página y seleccione el botón Borrar en "Aplicaciones predeterminadas para tipos de archivo" o "Aplicaciones predeterminadas para tipos de vínculo". A diferencia de la configuración similar en equipos de escritorio, no se pueden restablecer valores predeterminados de tipo de archivo individual.

### <a name="per-app-volume-control"></a>Control de volumen por aplicación

Ahora, en Windows Insider compilación, los usuarios pueden ajustar manualmente el nivel de volumen de cada aplicación. Esto permite a los usuarios centrarse mejor en las aplicaciones que necesitan o escuchar mejor al usar varias aplicaciones. Por ejemplo, tener que desactivar el volumen de una aplicación mientras se llama a otra persona para obtener asistencia remota en otra.

Para establecer el volumen de una aplicación individual, vaya a Configuración Sonido del sistema y, en Opciones avanzadas de sonido, seleccione Volumen de la aplicación y preferencias  ->    ->   **del dispositivo.**

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

### <a name="office-web-app"></a>Aplicación web de Office

>[!NOTE]
>A partir Windows Insider de la compilación 20325.1000 de la compilación 20325.1000, la aplicación web de Office ya no estará preinstalada (y no se instalará previamente para la próxima versión pública de la actualización del sistema operativo). Para instalar la aplicación web de Office, visite y seleccione el botón Aplicación disponible o https://www.office.com **Instalar Office** en la barra de direcciones.  Seleccione **Instalar para** confirmar.

La aplicación web de Office se ha agregado a la lista "Todas las aplicaciones" de la menú Inicio. Esta aplicación web también se puede anclar a Iniciar o desinstalar. Dado que se trata de una aplicación web, su funcionalidad coincide exactamente con lo que se experimentaría visitando https://www.office.com . La funcionalidad de la aplicación web de Office solo está disponible cuando HoloLens 2 tiene una conexión a Internet activa.

**Problema conocido**
- Al restablecer el dispositivo, se quitará la aplicación web de Office.

### <a name="swipe-to-type"></a>Deslizar el dedo para escribir

A algunos clientes les resulta más rápido "escribir" en teclados virtuales al deslizar la forma de la palabra que pretenden escribir, y estamos haciendo una vista previa de esta característica para el teclado holográfico. Puede deslizar una palabra a la vez pasando la punta del dedo por el plano del teclado holográfico, deslizando la forma de la palabra y retirando la punta del dedo del plano del teclado. Puede deslizar el dedo de las palabras de seguimiento sin necesidad de presionar la barra espaciador quitando el dedo del teclado entre palabras. Sabrá que la característica funciona si ve una pista de deslizar el dedo después del movimiento del dedo en el teclado.

Tenga en cuenta que esta característica puede ser difícil de usar y maestra debido a la naturaleza de un teclado holográfico en el que no se siente resistencia contra el dedo (a diferencia de una pantalla de teléfono móvil). Estamos evaluando esta característica para la versión pública, por lo que sus comentarios son importantes. si la característica le resulta útil o si tiene comentarios muy útiles, háganoslo saber a [través de Centro de opiniones](hololens-feedback.md).

### <a name="power-menu-from-start"></a>Menú De encendido desde Inicio

Un nuevo menú que permite al usuario cerrar sesión, apagar y reiniciar el dispositivo. Indicador en el cuadro de pantalla Inicio HoloLens que muestra cuándo está disponible una actualización del sistema.

#### <a name="how-to-use"></a>Cómo se usa

1. Abra el pantalla Inicio HoloLens con el gesto [Iniciar](hololens2-basic-usage.md#start-gesture) o con el mensaje "Ir a Inicio".

2. Observe el icono de puntos suspensivos (...) junto a la imagen de perfil de usuario:

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Seleccione la imagen de perfil de usuario con las manos o el comando de voz "Power".

4. Aparece un menú con las opciones Cerrar sesión, Reiniciar o Apagar el dispositivo:

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Seleccione las opciones de menú para cerrar sesión, reiniciar o apagar HoloLens. Es posible que la opción Cerrar sesión no esté disponible si el dispositivo está configurado para una sola cuenta [Microsoft (MSA) o una cuenta local.](hololens-identity.md)

6. Cierre el menú tocándose en cualquier otro lugar o menú Inicio con el gesto Iniciar.

#### <a name="update-indicator"></a>Indicador de actualización

Cuando hay una actualización disponible, el icono de puntos suspensivos se enciende para indicar que un reinicio instalará la actualización Las opciones de menú también cambian para reflejar la presencia de la actualización.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Varios usuarios enumerados en la pantalla de inicio de sesión

Anteriormente, en la pantalla Inicio de sesión solo se mostraba el usuario que ha iniciado sesión más recientemente, así como un punto de entrada "Otro usuario". Hemos recibido comentarios de los clientes que no son suficientes si varios usuarios han iniciado sesión en el dispositivo. Todavía tenían que volver a escribir su nombre de usuario, etc.

Introducido en esta compilación de Windows Insider, al seleccionar Otro usuario que se encuentra a la derecha del campo de entrada del PIN, la pantalla Inicio de sesión mostrará varios usuarios con que han iniciado sesión previamente en el dispositivo.  Esto permite a los usuarios seleccionar su perfil de usuario y, a continuación, iniciar sesión con sus Windows Hello credenciales. También se puede agregar un nuevo usuario al dispositivo desde esta página Otros usuarios mediante el **botón Agregar** cuenta.

Cuando se encuentra en el menú Otros usuarios, el botón Otros usuarios mostrará el último usuario que ha iniciado sesión en el dispositivo. Seleccione este botón para volver a la pantalla Inicio de sesión de este usuario.

![Pantalla de inicio de sesión predeterminada](./images/multiusers1.jpg)

<br>

![Pantalla de inicio de sesión de otros usuarios](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Compatibilidad con micrófono externo USB-C

> [!IMPORTANT]
> La conexión de **un micrófono USB no lo establecerá automáticamente como el dispositivo de entrada**. Al conectar un conjunto de auriculares USB-C, los usuarios observarán que el audio del casco se redirigirá automáticamente a los auriculares, pero el sistema operativo HoloLens da prioridad a la matriz de micrófonos interna por encima de cualquier otro dispositivo de entrada. **Para usar un micrófono USB-C, siga estos pasos.**

Los usuarios pueden seleccionar micrófonos externos conectados a USB-C mediante el panel **Configuración** de sonido. Los micrófonos USB-C se pueden usar para llamar, grabar, etc.

Abra la **aplicación Configuración** y seleccione System Sound   >  **(Sonido del sistema).**

![Configuración de sonido](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Para usar micrófonos externos con **Remote Assist**, los usuarios tendrán que hacer clic en el hipervínculo "Administrar dispositivos de sonido".
>
> A continuación, use la lista desplegable para establecer el micrófono externo como **Predeterminado o** Predeterminado **de comunicaciones.** Elegir Predeterminado **significa** que el micrófono externo se usará en todas partes.
>
> Elegir **Comunicaciones predeterminada** significa que el micrófono externo se usará en Remote Assist y otras aplicaciones de comunicaciones, pero la matriz de micrófonos de HoloLens todavía se puede usar para otras tareas.

![Administración de dispositivos de sonido](images/usbc-mic-2.png)

<br>

![Establecer el valor predeterminado del micrófono](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>¿Qué sucede con la compatibilidad con micrófonos Bluetooth?

Desafortunadamente, los micrófonos Bluetooth todavía no se admiten actualmente en HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Solución de problemas de micrófonos USB-C

Tenga en cuenta que algunos micrófonos USB-C se informan incorrectamente como micrófono *y* altavoz. Se trata de un problema con el micrófono y no con HoloLens. Al conectar uno de estos micrófonos a HoloLens, es posible que se pierda el sonido. Afortunadamente, hay una corrección sencilla.  

En **Configuración** de sonido del sistema , establezca explícitamente los altavoces integrados (controlador de audio de características  ->    ->   **análogas)** como **el dispositivo predeterminado**. HoloLens debe recordar esta configuración incluso si el micrófono se quita y se vuelve a conectar más adelante.

![Solución de problemas de micrófonos USB-C](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Inicio de sesión automático de visitante para quioscos

Esta nueva característica permite usar el inicio de sesión automático en las cuentas de visitante para los modos de quiosco.

Para una configuración que no es de AAD, para configurar un dispositivo para el inicio de sesión automático del visitante:

1. Cree un paquete de aprovisionamiento que:
    1. Configura los valores **de Runtime/AssignedAccess para** permitir las cuentas de visitante.
    1. Opcionalmente, inscribe el dispositivo en MDM (Configuración del entorno de **ejecución/Área de trabajo/Inscripciones)** para que se pueda administrar más adelante.
    1. No crear una cuenta local
1. [Aplique el paquete de aprovisionamiento](hololens-provisioning.md).

En el caso de una configuración de AAD, los usuarios pueden lograr algo parecido a esto hoy sin este cambio. Los dispositivos unidos a AAD configurados para el modo de pantalla completa pueden iniciar sesión en una cuenta de visitante con un solo clic en la pantalla de inicio de sesión. Una vez que haya iniciado sesión en la cuenta de visitante, el dispositivo no volverá a solicitar el inicio de sesión hasta que el visitante haya iniciado sesión explícitamente desde el menú Inicio o se reinicie el dispositivo.

El inicio de sesión automático del visitante se puede administrar a través [de la directiva OMA-URI](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) personalizada:

- Valor de URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Directiva  | Descripción   | Configurations  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Permite que un visitante inicie sesión automáticamente en un quiosco.   | 1 (Sí), 0 (No, valor predeterminado).  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Uso de las nuevas aplicaciones de Configuración y Edge en los modos de pantalla completa

Al incluir [](hololens-kiosk.md)aplicaciones en quioscos, un administrador de TI suele agregar la aplicación al quiosco, pero con su identificador de modelo de usuario de aplicación (AUMID). Dado que la aplicación Configuración y la aplicación Microsoft Edge se consideran nuevas aplicaciones y son diferentes de las aplicaciones anteriores, los quioscos que usan AUMID para esas aplicaciones tendrán que actualizarse para usar el nuevo AUMID.

Al modificar un quiosco para incluir las nuevas aplicaciones, se recomienda agregar en el nuevo AUMID, así como salir de la antigua. Esto creará una transición sencilla cuando los usuarios actualicen el sistema operativo y no tendrá que recibir nuevas directivas para seguir usando la pantalla completa según lo previsto.

| Aplicación                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Aplicación de configuración anterior       | HolographicSystemSettings_cw5n1h2txyewy! Aplicación            |
| Nueva aplicación de configuración       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! Aplicación |
| Aplicación Microsoft Edge anterior | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| Nueva Microsoft Edge aplicación | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Cambios de comportamiento del modo de pantalla completa para el control de errores

En compilaciones anteriores, si un dispositivo tuviera una configuración de quiosco, que es una combinación de acceso asignado global y acceso asignado a miembros del grupo de AAD, si no se pudo determinar la pertenencia al grupo de AAD, el usuario vería["no](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)se muestra nada en el menú inicio".

A partir Windows Insider versión, la experiencia de pantalla completa se reservará a la configuración global de quiosco (si está presente) en caso de errores durante el modo de quiosco de grupo de AAD.

### <a name="new-settingsuris-for-page-settings-visibility"></a>Nueva configuraciónDI para la visibilidad de la configuración de página

En [Windows Holographic, versión 20H2](hololens-release-notes.md#windows-holographic-version-20h2) agregamos la directiva [Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir las páginas que se ven en la aplicación Configuración. PageVisibilityList es una directiva que permite a los administradores de TI impedir que páginas específicas de la aplicación Configuración del sistema sean visibles o accesibles, o bien hacerlo para todas las páginas excepto las especificadas.

Si visita [visibilidad de la configuración de](settings-uri-list.md)página, puede encontrar instrucciones para usar este CSP y la lista de URI disponibles en versiones anteriores.

En Windows Insider compilaciones estamos ampliando la lista de URI de configuración disponibles, que los administradores de TI pueden administrar. Algunos de estos URI son para las áreas recién disponibles dentro de la nueva aplicación Configuración. Si usa la directiva Settings/PageVisibilityList, revise la lista siguiente y ajuste las páginas permitidas o bloqueadas según sea necesario.

> [!NOTE]
> **En desuso: ms-settings:network-proxy**
>
> Una página de configuración está en desuso en estas compilaciones más recientes. La antigua **página & proxy de Internet** ya no está disponible como configuración  >   global. La nueva configuración de proxy por conexión se puede encontrar en Propiedades de Red **&**  >  **Wi-Fi** de Internet o Propiedades de Red  >   & Ethernet de   >    >  **Internet.**

<br>

| Página Configuración                                        | Identificador URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Características > aplicaciones & aplicaciones                               | `ms-settings:appsfeatures`                         |
| Aplicaciones > Aplicaciones & características > opciones avanzadas          | `ms-settings:appsfeatures-app`                     |
| Aplicaciones > sin conexión                                  | `ms-settings:maps`                                 |
| Aplicaciones > sin conexión > descargar mapas                  | `ms-settings:maps-downloadmaps`                    |
| Dispositivos > Mouse                                      | `ms-settings:mouse`                                |
| Dispositivos > USB                                        | `ms-settings:usb`                                  |
| Modo avión & internet > red                   | `ms-settings:network-airplanemode`                 |
| Privacidad > general                                    | `ms-settings:privacy-general`                      |
| Personalización de > ink & privacidad             | `ms-settings:privacy-speechtyping`                 |
| Movimiento de > privacidad                                     | `ms-settings:privacy-motion`                       |
| Límites de > captura de pantalla de privacidad                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Aplicaciones y capturas > privacidad                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Batería de > sistema                                     | `ms-settings:batterysaver`                         |
| Batería de > sistema                                     | `ms-settings:batterysaver-settings`                |
| System > Sound                                       | `ms-settings:sound`                                |
| System > Sound > App volume and device preferences | `ms-settings:apps-volume`                          |
| System > Sound > Manage sound devices              | `ms-settings:sound-devices`                        |
| System > Storage > Configurar Sensor de almacenamiento         | `ms-settings:storagepolicies`                      |
| Hora & idioma de > fecha & hora                        | `ms-settings:dateandtime`                          |
| Teclado & idioma > tiempo                           | `ms-settings:keyboard`                             |
| Idioma & idioma > tiempo                           | `ms-settings:language`                             |
| Idioma & idioma > tiempo                           | `ms-settings:regionlanguage-languageoptions`       |
| Actualización de & seguridad > restablecimiento & recuperación               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>URI actualizados

Anteriormente, los dos URI siguientes no tomaban un usuario directamente a las páginas indicadas, sino que solo bloqueaban la página principal de actualizaciones. Los elementos siguientes se han actualizado para dirigirse a sus páginas:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Configuración de diagnósticos de reserva mediante la aplicación Configuración

Ahora, en la aplicación Configuración, un usuario puede configurar el comportamiento de [Diagnóstico de reserva](hololens-diagnostic-logs.md). En la aplicación Configuración, vaya a **la página Solución** de problemas  ->  **de** privacidad para configurar esta opción.

> [!NOTE]
> Si hay una directiva MDM configurada para el dispositivo, el usuario no podrá invalidar ese comportamiento.  

### <a name="share-things-with-nearby-devices"></a>Compartir cosas con dispositivos cercanos

Comparta cosas con dispositivos cercanos a Windows 10, incluidos los equipos y otros dispositivos HoloLens 2 que ejecutan HoloLens Insider compilaciones 20279.1006 y posteriores. Puede probarlo en Settings System Shared Experiences **(Experiencias** compartidas del sistema de configuración) para compartir archivos o direcciones URL desde  ->    ->   holoLens a un equipo. Para obtener más información, lea más sobre cómo compartir [cosas con dispositivos cercanos en Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Esta característica se puede administrar a [través de Connectivity/AllowConnectedDevices.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)

### <a name="new-os-update-troubleshooter"></a>Nuevo solucionador de problemas de actualización del sistema operativo

Además de los solucionadores de problemas anteriores dentro de la aplicación Configuración, se ha agregado un nuevo solucionador de problemas con la adición de la nueva aplicación Configuración para las actualizaciones del sistema operativo. Vaya a **Configuración Actualizar** solución de  ->  **problemas &amp; de**  >    >  **Windows Update** y seleccione **Iniciar.** Esto le permite recopilar seguimientos mientras reproduce el problema con las actualizaciones del sistema operativo para ayudar a solucionar mejor problemas con el equipo de TI o el soporte técnico.

### <a name="delivery-optimization-preview"></a>Optimización de distribución versión preliminar

Con esta actualización de HoloLens Insider, Windows Holographic for Business una versión preliminar anticipada de la configuración de optimización de entrega para reducir el consumo de ancho de banda para las descargas de varios dispositivos HoloLens. Puede obtener una descripción más completa de esta funcionalidad junto con la configuración de red recomendada aquí: Optimización de distribución [para Windows 10 actualizaciones.](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)

Las siguientes opciones están habilitadas como parte de la superficie de administración y [se pueden configurar desde Intune](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings):

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Algunas advertencias sobre esta oferta de versión preliminar:

- La compatibilidad con HoloLens está limitada en esta versión preliminar solo a las actualizaciones del sistema operativo.
- Windows Holographic for Business solo admite modos de descarga HTTP y descargas desde un punto [de conexión de Microsoft Caché conectada ;](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) Los modos de descarga punto a punto y las asignaciones de grupo no se admiten para dispositivos HoloLens en este momento.
- HoloLens no admite la implementación ni la optimización de entrega para Windows Server Update Services de conexión.
- La solución de problemas requerirá diagnósticos en el servidor de Caché conectada o la recopilación de un seguimiento en HoloLens en HoloLens mediante la actualización de configuración & solución de problemas de  >    >     >   **seguridad Windows Update**.

### <a name="improvements-and-fixes-in-the-update"></a>Mejoras y correcciones en la actualización:

- [Los diagnósticos sin conexión](hololens-diagnostic-logs.md#offline-diagnostics) también incluirán información adicional del dispositivo para el número de serie y la versión del sistema operativo.

### <a name="known-issues-and-work-around"></a>Problemas conocidos y trabajo

#### <a name="pairing-hololens-to-pc"></a>Emparejamiento de HoloLens con PC

Antes de la compilación de Windows Insider 20325.1000, cuando un usuario había establecido credenciales de emparejamiento en [Windows Holographic, versión 20H2](hololens-release-notes.md#windows-holographic-version-20h2) o [Windows Holographic, versión 2004](hololens-release-notes.md#windows-holographic-version-2004) y se actualizaba a las compilaciones de Windows Insider, sus credenciales establecidas anteriores para emparejar HoloLens con el equipo con fines de implementación y depuración de aplicaciones como a través de Visual Studio ya no funcionaban. Windows Insider compilación 20325.1000 corrige este problema y no requiere ninguna acción adicional para reanudar el uso del portal de dispositivos.

Los usuarios que han flashed su dispositivo con una compilación [de Insider](#ffu-download-and-flash-directions) ahora tendrán que volver a actualizar sus dispositivos (a 20325.1000+ o una compilación de GA) para emparejar sus dispositivos con su PC.

Los usuarios que no se han inscrito en Windows Insider y que van a realizar la actualización de características cuando esté disponible con carácter general no se verán afectados.


## <a name="start-receiving-insider-builds"></a>Empezar a recibir compilaciones de Insider

> [!NOTE]
> Si no ha actualizado recientemente, reinicie el dispositivo para actualizar el estado y obtener la compilación más reciente.
> - El comando de voz "Reiniciar dispositivo" funciona bien. 
> - También puede elegir el botón reiniciar en Configuración/Programa Windows Insider.
>
> Hemos tenido un error en el back-end que puede haber encontrado y esto le permitirá volver a realizar el seguimiento.

En un dispositivo HoloLens 2, vaya a **Configuración**  >  **Update & Security** Programa Windows Insider y  >   seleccione **Introducción.** Vincule la cuenta que usó para registrarse como Windows Insider.

Windows Insider ahora se mueve a Canales. El **anillo** rápido se convertirá en  el canal **de desarrollo,** el  anillo lento se convertirá en el **Canal beta** y el anillo versión preliminar se convertirá en el canal de versión preliminar de la **versión .** Este es el aspecto de esa asignación:

![Windows Insider channels explanation](images/WindowsInsiderChannels.png)

Para obtener más información, vea [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs (Introducción a Windows Insider canales en blogs de Windows).

A continuación, seleccione Desarrollo activo de **Windows,** elija si desea recibir canal **de** desarrollo o Canal beta **compilaciones** y revise los términos del programa.

Seleccione **Confirmar > Reiniciar ahora** para finalizar. Una vez reiniciado el dispositivo, vaya a Configuración **> Actualización** de & Seguridad > Busque actualizaciones para obtener la compilación más reciente.

### <a name="update-error-0x80070490-work-around"></a>Actualización del 0x80070490 de trabajo
Si se produce un error de actualización 0x80070490 al actualizar en el canal Dev o Beta, pruebe el siguiente trabajo a corto plazo. Implica mover el canal insider, seleccionar la actualización y, a continuación, volver a mover el canal insider.

#### <a name="stage-one---release-preview"></a>Fase uno: versión preliminar
1.  Configuración, Actualizar & Seguridad, Programa Windows Insider, seleccione **Canal de versión preliminar.**
2.  Settings, Update & Security, Windows Update, **Check for updates**. Después de la actualización, continúe con la fase dos.

#### <a name="stage-two---dev-channel"></a>Fase dos: Canal de desarrollo
1. Configuración, Actualizar & Seguridad, Programa Windows Insider, seleccione **Canal de desarrollo.**
2. Settings, Update & Security, Windows Update, **Check for updates**.

## <a name="ffu-download-and-flash-directions"></a>Instrucciones de descarga y flash de FFU
Para realizar pruebas con un ffu firmado por un vuelo, primero debe desbloquear el dispositivo en vuelo antes de que se abra el ffu firmado por el vuelo.
1. En pc:

    1. Descargue ffu en el equipo desde [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Instale ARC (Advanced Recovery Companion) desde la Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. En HoloLens - Desbloqueo de vuelos: abra La actualización de & seguridad Programa Windows Insider y, a continuación,  >    >   regístrese y reinicie el dispositivo.

1. Flash FFU: ahora puede flashear el vuelo firmado por FFU mediante ARC.

## <a name="provide-feedback-and-report-issues"></a>Proporcionar comentarios e informar de problemas

Use la [aplicación Centro de opiniones en](hololens-feedback.md) HoloLens para proporcionar comentarios y notificar problemas. El Centro de opiniones garantiza que se incluye toda la información de diagnóstico necesaria para ayudar a nuestros ingenieros a depurar y resolver rápidamente el problema.  Los problemas con la versión en chino y japonés de HoloLens deben informarse de la misma manera.

> [!NOTE]
> Asegúrese de aceptar el mensaje que le pregunta si desea Centro de opiniones acceder a la carpeta Documentos (seleccione **Sí** cuando se le solicite).

## <a name="note-for-developers"></a>Nota para desarrolladores

Le recomendamos que pruebe a desarrollar sus aplicaciones mediante compilaciones insider de HoloLens.  Consulte la documentación [para desarrolladores de HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) para empezar. Esas mismas instrucciones funcionan con compilaciones de Insider de HoloLens.  Puede usar las mismas compilaciones de Unity Visual Studio que ya usa para el desarrollo de HoloLens.

## <a name="stop-receiving-insider-builds"></a>Dejar de recibir compilaciones de Insider

Si ya no quiere recibir compilaciones de Insider de Windows Holographic, puede optar por no [](hololens-recovery.md) recibir cuando HoloLens ejecuta una compilación de producción, o bien puede recuperar el dispositivo mediante advanced recovery Companion para recuperar el dispositivo en una versión que no sea Insider de Windows Holographic.

> [!CAUTION]
> Hay un problema conocido en el que los usuarios que desascriban las compilaciones de Insider Preview después de volver a instalar manualmente una nueva compilación de versión preliminar experimentarían una pantalla azul. Después, deben recuperar manualmente su dispositivo. Para obtener información completa sobre si se vería afectado o no, consulte más información sobre [este problema conocido.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)

Para comprobar que HoloLens ejecuta una compilación de producción:

1. Vaya a **Configuración > sistema > acerca de** y busque el número de compilación.

1. [Consulte las notas de la versión de los números de compilación de producción.](hololens-release-notes.md)

Para no participar en las compilaciones de Insider:

1. En un dispositivo HoloLens que ejecuta una compilación de producción, vaya a Configuración **> Update & Security > Programa Windows Insider** y seleccione Detener compilaciones de **Insider.**

1. Siga las instrucciones para no participar en el dispositivo.
