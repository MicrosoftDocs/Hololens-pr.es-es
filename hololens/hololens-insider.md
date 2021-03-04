---
title: Versión preliminar de Insider para Microsoft HoloLens
description: Aprende a empezar con las compilaciones de Insider y proporciona comentarios valiosos para nuestra próxima actualización principal del sistema operativo para HoloLens.
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
ms.date: 2/23/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: ac408f100fb6e421a0ed0c85563ed920f1a25a83
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385577"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Versión preliminar de Insider para Microsoft HoloLens

Bienvenido a las últimas compilaciones de Insider Preview para HoloLens. Es sencillo empezar y [proporcionar comentarios](hololens-insider.md#start-receiving-insider-builds) valiosos para nuestra próxima actualización principal del sistema operativo para HoloLens.

## <a name="windows-insider-release-notes"></a>Notas de la versión de Windows Insider

Estamos encantados de empezar a volar nuevas características a Windows Insiders de nuevo. Las nuevas compilaciones se actualizarán al Canal de desarrollo para obtener las actualizaciones más recientes. Seguiremos actualizando esta página a medida que agreguemos más características y actualizaciones a nuestras compilaciones de Windows Insider.  Prepárate para mezclar estas actualizaciones en tu realidad.

Esta actualización de características contiene características para dos audiencias de destino. Características que cualquier usuario puede usar en un dispositivo por el usuario final y nuevas opciones de administración de dispositivos que pueden configurar los administradores de TI. La siguiente tabla de características especifica las audiencias con las que se puede usar cada nueva característica. Si es un administrador de TI, consulte nuestro administrador [de TI: Actualizar lista de comprobación](#it-admin---update-checklist)

> [!IMPORTANT]
> Si anteriormente usaste la aplicación Configuración o la aplicación Microsoft Edge en un quiosco, hemos reemplazado estas aplicaciones por nuevas aplicaciones que usan un identificador de aplicación diferente. Le recomendamos encarecidamente que lea [a continuación nuevos AUMID para nuevas aplicaciones en modo quiosco.](#use-the-new-settings-and-edge-apps-in-kiosk-modes) Esto te asegurará de que continúes teniendo la aplicación Configuración en tu quiosco o incluyas la nueva aplicación de Microsoft Edge.

<br>

| Nombre de la característica                                              | Descripción corta                                                                      | Audiencia de destino | Disponible en la compilación |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|------|
| [Nuevo Microsoft Edge](#introducing-the-new-microsoft-edge) | El nuevo Microsoft Edge basado en Chromium ya está disponible para HoloLens 2                         | Usuario final | 20279.1006 |
| [WebXR y visor de 360](#webxr-and-360-viewer)             | Prueba experiencias web envolventes y reproducción de vídeo 360                                           | Usuario final | 20289.1000 |
| [Nueva aplicación Configuración](#new-settings-app)                     | La aplicación configuración heredada se está reemplazando por una versión actualizada con nuevas características y configuración | Usuario final | 20279.1006 |
| [Calibración de color para mostrar](#display-color-calibration)   | Seleccionar un perfil de color alternativo para la pantalla de HoloLens 2                                | Usuario final | 20293.1000 |
| [Selector de aplicaciones predeterminado](#default-app-picker)                 | Elegir qué aplicación debe iniciarse para cada archivo o tipo de vínculo                                      | Usuario final | 20279.1006 |
| [Control de volumen por aplicación](#per-app-volume-control) |  Controlar el volumen de nivel de aplicación independientemente del volumen del sistema | Usuario final | 20293.1000 |
| [Aplicación web de Office](#office-web-app)                         | Ahora se muestra un acceso directo a la aplicación web de Office en "Todas las aplicaciones"                                   | Usuario final | 20279.1006 |
| [Deslizar el dedo para escribir](#swipe-to-type)                           | Usar la punta del dedo para "deslizar" palabras en el teclado holográfico                        | Usuario final | 20279.1006 |
| [Menú Inicio](#power-menu-from-start) | En el menú Inicio, reinicie y apague el dispositivo HoloLens | Usuario final | 20293.1000 |
| [Varios usuarios enumerados en la pantalla Inicio de sesión](#multiple-users-listed-on-sign-in-screen) | Mostrar varias cuentas de usuario en la pantalla Iniciar sesión | Usuario final | 20293.1000 |
| [Compatibilidad con micrófono externo USB-C](#usb-c-external-microphone-support) | Usa micrófonos USB-C para aplicaciones y/o asistencia remota.| Usuario final | 20279.1006 |
| [Inicio de sesión automático de visitantes para quioscos](#visitor-auto-logon-for-kiosks)                          | Habilita el inicio de sesión automático en las cuentas de visitante para usarse para los modos de quiosco.                         | Administrador de TI | 20279.1006                 |
| [Nuevos AUMID para nuevas aplicaciones en modo quiosco](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | AUMIDs para nuevas aplicaciones perimetrales y configuración | Administrador de TI | 20279.1006 |
| [Entrega de errores en modo quiosco mejorado](#kiosk-mode-behavior-changes-for-handling-of-failures) | El modo quiosco de pantalla completa busca acceso asignado global antes del menú inicio vacío. | Administrador de TI | 20279.1006 |
| [Nueva configuraciónURIs para la visibilidad de la configuración de página](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | Más de 20 nuevos SettingsURIs para la directiva Settings/PageVisibilityList | Administrador de TI | 20289.1000 |
| [Configurar diagnósticos de reserva](#configuring-fallback-diagnostics-via-settings-app) | Configuración del comportamiento de diagnóstico de reserva en la aplicación Configuración | Administrador de TI | 20279.1006 |
| [Compartir cosas con dispositivos cercanos](#share-things-with-nearby-devices) | Compartir archivos o direcciones URL de un HoloLens a un equipo | Todos | 20279.1006 |
| [Nuevo solucionador de problemas de actualización del sistema operativo](#new-os-update-troubleshooter) | Nuevo solucionador de problemas en Configuración para actualizaciones del sistema operativo | Administrador de TI | 20279.1006 |
| [Vista previa de optimización de entrega](#delivery-optimization-preview) | Reducir el consumo de ancho de banda para descargas desde varios dispositivos HoloLens | Administrador de TI | 20301.1000 |
| [Mejoras y correcciones en la actualización](#improvements-and-fixes-in-the-update) | Correcciones adicionales en la actualización. | Todos | 20279.1006 |

### <a name="it-admin---update-checklist"></a>Administrador de TI: lista de comprobación de actualización

Esta lista de comprobación te ayudará a conocer los nuevos elementos que se están agregando en esta actualización de características que pueden afectar a las configuraciones de administración de dispositivos actuales o las nuevas características que podrías empezar a usar.

#### <a name="updates-to-kiosk-mode"></a>Actualizaciones en modo quiosco

[**Nuevos AUMID para nuevas aplicaciones en modo quiosco**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Si anteriormente usaste la aplicación Configuración o la aplicación Microsoft Edge en un quiosco, hemos reemplazado estas aplicaciones por nuevas aplicaciones que usan un identificador de aplicación diferente. Le recomendamos encarecidamente que lea [a continuación nuevos AUMID para nuevas aplicaciones en modo quiosco.](#use-the-new-settings-and-edge-apps-in-kiosk-modes) Esto te asegurará de que continúes teniendo la aplicación Configuración en tu quiosco o incluyas la nueva aplicación de Microsoft Edge.

Estos cambios pueden realizarse ahora e implementarse en todos los dispositivos y permitir una transición más suave al actualizarse.

[**Inicio de sesión automático de visitantes para quioscos**](#visitor-auto-logon-for-kiosks)

Ahora, los visitantes pueden iniciar sesión automáticamente en un quiosco. Este comportamiento está desactivado de forma predeterminada, pero se puede administrar y deshabilitar.

[**Entrega de errores en modo quiosco mejorado**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Esta actualización ahora mantiene los dispositivos más controlados por el modo quiosco, lo que permite que vuelva a los distintos tipos de quioscos antes de simplemente presentar un quiosco vacío. Aunque esto no se puede administrar, esto puede ser algo para informar a su departamento de soporte técnico si está usando quioscos en una forma que esto se pueda aplicar a su configuración.

#### <a name="updates-to-page-settings-visibility"></a>Actualizaciones de visibilidad de configuración de página

[**Nueva configuraciónURIs para la visibilidad de la configuración de página**](hololens-insider.md#new-settingsuris-for-page-settings-visibility)

Si está usando [visibilidad](settings-uri-list.md) de configuración de página, es posible que desee realizar ajustes en los URI existentes que haya permitido o bloqueado.

#### <a name="updates-for-your-wdac-policy"></a>Actualizaciones de la directiva WDAC

Si anteriormente estaba bloqueando Microsoft Edge a través de WDAC, querrá actualizar la directiva WDAC. Revise [lo siguiente y](#using-wdac-to-block-new-microsoft-edge) use el código de ejemplo proporcionado.

#### <a name="newly-configurable-items"></a>Elementos recién configurables

- [Configurar diagnósticos de reserva](#configuring-fallback-diagnostics-via-settings-app)
  - Puede configurar si y quién puede recopilar diagnósticos de reserva.
- [Compartir cosas con dispositivos cercanos](#share-things-with-nearby-devices)
  - Puede deshabilitar la nueva característica de uso compartido cercano.
- [Configuración de la configuración de directivas para el nuevo Microsoft Edge](#configuring-policy-settings-for-the-new-microsoft-edge)
  - Revise las configuraciones disponibles recientemente para Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Nueva herramienta de diagnóstico

- [Nuevo solucionador de problemas de actualización del sistema operativo](#new-os-update-troubleshooter)
  - Recopilar registros relacionados con actualizaciones del sistema operativo

### <a name="introducing-the-new-microsoft-edge"></a>Presentación del nuevo Microsoft Edge

![Animación del logotipo heredado de Microsoft Edge al nuevo logotipo de Microsoft Edge](images/new-edge.gif)

El nuevo Microsoft Edge adopta el proyecto [de código abierto Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) para crear una mejor compatibilidad para los clientes y una menor fragmentación de la web para desarrolladores web.

Con esta vista previa de Insider, el nuevo Microsoft Edge está disponible para los clientes de HoloLens 2 por primera vez. Aunque el nuevo Microsoft Edge reemplazará finalmente a Microsoft Edge heredado en HoloLens 2, ambos exploradores están disponibles actualmente para Insiders. Comparta comentarios y errores con nuestro equipo a través de la **característica Enviar** comentarios en el nuevo Microsoft Edge o a través del Centro [de opiniones.](hololens-feedback.md)

![Nueva captura de pantalla de Microsoft Edge](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Iniciar el nuevo Microsoft Edge

Hay dos versiones de Microsoft Edge disponibles para Insiders: el nuevo icono de Microsoft Edge nuevo de Microsoft Edge (representado por un icono de remolino azul y verde) y Microsoft Edge heredado (representado por el icono ![ ](images/new_edge_logo.png) blanco "e"). El nuevo Microsoft Edge se ancla al menú Inicio y se iniciará automáticamente al activar un vínculo web. Si quieres volver a usar Microsoft Edge heredado como explorador web predeterminado, consulta las instrucciones siguientes para restablecer [las aplicaciones predeterminadas.](#default-app-picker)

> [!NOTE]
> Cuando inicies por primera vez el nuevo Microsoft Edge en HoloLens 2, la configuración y los datos se importarán desde Microsoft Edge heredado. Si sigue usando Microsoft Edge heredado después de iniciar el nuevo Microsoft Edge, los nuevos datos no se sincronizarán de Microsoft Edge heredado al nuevo Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Configuración de la configuración de directivas para el nuevo Microsoft Edge

El nuevo Microsoft Edge ofrece a los administradores de TI un conjunto mucho más amplio de directivas de explorador en HoloLens 2 que antes estaban disponibles con Microsoft Edge heredado.

Estos son algunos recursos útiles para obtener más información sobre cómo administrar la configuración de directivas para el nuevo Microsoft Edge:

- [Configurar la directiva de Microsoft Edge con Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Asignación de directiva de Microsoft Edge (versión anterior) a Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Asignación de directivas de Google Chrome a Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Documentación [completa de Microsoft Edge Enterprise](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> Debido al volumen de directivas de explorador admitidas por el nuevo Microsoft Edge, nuestro equipo no puede garantizar que cada nueva directiva funcione en HoloLens 2. Sin embargo, hemos probado y confirmado que el nuevo equivalente de Microsoft Edge de cada directiva heredada de Microsoft Edge admitida anteriormente en HoloLens 2 funciona como se esperaba. Consulta [Asignación de directivas](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) heredadas de Microsoft Edge a Microsoft Edge para encontrar el nuevo equivalente de Microsoft Edge de cada directiva de explorador de Microsoft Edge heredada que usaste con HoloLens 2.
>
> Existen al menos dos nuevas directivas de Microsoft Edge que sabemos que *no* funcionarán con HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Qué esperar del nuevo Microsoft Edge en HoloLens 2

Dado que el nuevo Microsoft Edge es una aplicación nativa de Win32 con una nueva capa de adaptador para UWP que le permite ejecutarse en dispositivos solo para UWP como HoloLens 2, es posible que algunas características no estén disponibles inmediatamente. Vamos a admitir nuevos escenarios y características en los próximos meses, así que compruebe este espacio para obtener información actualizada.

**Escenarios y características que se espera que funcionen:**
- Experiencia de primera ejecución, inicio de sesión en el perfil y sincronización
- Los sitios web deben representarse y comportarse según lo esperado
- La mayoría de las funciones del explorador (Favoritos, Historial, etc.) deben funcionar según lo esperado
- Modo oscuro
- Instalación de aplicaciones web en el dispositivo
- Instalación de extensiones (por favor, háganos saber si usa extensiones que no funcionan correctamente en HoloLens 2)
- Visualización y marcado de un PDF
- Sonido espacial desde una sola ventana del explorador
- Actualización automática y manual del explorador
- Guardar un PDF en el menú Imprimir (con la opción "Guardar en PDF")

**Escenarios y características próximamente:**
- Extensión WebXR y visor 360
- Restauración de contenido para corregir la ventana al examinar varias ventanas colocadas en el entorno

**No se espera que los escenarios y las características funcionen:**
- Sonido espacial de varias ventanas con secuencias de audio simultáneas
- "See it, say it"
- Impresión

**Principales problemas conocidos del explorador:**
- Al restablecer el dispositivo, se quitará el nuevo Microsoft Edge
- La vista previa de lupa en el teclado holográfico muestra contenido incorrecto

#### <a name="microsoft-edge-insider-channels"></a>Canales insider de Microsoft Edge

El equipo de Microsoft Edge pone a disposición de la comunidad Edge Insider tres canales de vista previa: Beta, Dev y Canary. La instalación de un canal de vista previa no desinstala la versión publicada de Microsoft Edge en holoLens 2 y puede instalar más de uno al mismo tiempo. 

Visita la [página principal de Microsoft Edge Insider](https://www.microsoftedgeinsider.com) para obtener más información sobre la comunidad Edge Insider. Para obtener más información sobre los diferentes canales de Edge Insider y empezar a trabajar, visite la página de descarga [de Edge Insider](https://www.microsoftedgeinsider.com/download).

Hay un par de métodos disponibles para instalar los canales insider de Microsoft Edge en HoloLens 2:

**Instalación directa en el dispositivo (actualmente solo disponible para dispositivos no administrados)**
  1. En HoloLens 2, visite la página de descarga [de Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Selecciona el **botón Descargar para HoloLens 2** para el canal Edge Insider que quieras instalar.
  1. Inicie el archivo .msix descargado desde la cola de descarga perimetral o desde la carpeta "Descargas" del dispositivo (mediante el Explorador de archivos).
  1. [Se iniciará el instalador](app-deploy-app-installer.md) de aplicaciones.
  1. Seleccione el **botón Instalar.**
  1. Después de la instalación correcta, encontrarás Microsoft Edge Beta, Dev **** o Canary como una entrada independiente en la lista Todas las aplicaciones del menú Inicio.

**Instalar a través de PC con Windows Device Portal (requiere que [el modo de desarrollador](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) esté habilitado en HoloLens 2)**
  1. En el equipo, visite la página de descarga [de Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Selecciona el **botón de flecha desplegable** junto al botón "Descargar para Windows 10" para el canal Edge Insider que quieras instalar.
  1. Seleccione **HoloLens 2** en el menú desplegable.
  1. Guarde el archivo .msix en la carpeta "Descargas" del equipo (u otra carpeta que pueda encontrar fácilmente).
  1. Usa [Windows Device Portal en](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) tu PC para instalar el archivo .msix descargado en HoloLens 2.
  1. Después de la instalación correcta, encontrarás Microsoft Edge Beta, Dev **** o Canary como una entrada independiente en la lista Todas las aplicaciones del menú Inicio.

> [!NOTE]
> Durante esta vista previa de Windows Insider para HoloLens 2, la versión de Microsoft Edge en el dispositivo puede ser mayor que la disponible en algunos (o todos) de los canales insider de Microsoft Edge. Esto es para garantizar que las nuevas características y correcciones dirigidas específicamente al explorador web en HoloLens 2 se estén corriendo a nuestros Windows Insiders tan pronto como sea posible. Poco después de la publicación de la próxima actualización de Windows, las compilaciones del canal Insider de Microsoft Edge superarán y se mantendrán por delante de la versión de Microsoft Edge en holoLens 2.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Uso de WDAC para bloquear nuevo Microsoft Edge

Para los administradores de TI que buscan actualizar su directiva [WDAC](windows-defender-application-control-wdac.md) para bloquear la nueva aplicación de Microsoft Edge, tendrás que agregar lo siguiente a la directiva.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

### <a name="webxr-and-360-viewer"></a>WebXR y visor de 360

*Se agregó en la compilación 20289.1000 de Windows Insider*

El nuevo Microsoft Edge incluye compatibilidad con WebXR, que es el nuevo estándar para crear experiencias web envolventes (en sustitución de WebVR). Muchas experiencias web envolventes se diseñaron pensando en la realidad virtual (reemplazan el campo de vista con un entorno virtual), pero holoLens 2 también admite estas experiencias. El estándar WebXR también permite experiencias web envolventes de realidad aumentada y mixta que usan su entorno físico. A medida que los desarrolladores pasan más tiempo con WebXR, anticipamos que las nuevas experiencias envolventes de realidad aumentada y mixta llegarán para que los clientes de HoloLens 2 lo intenten.

La extensión visor 360 se basa en WebXR e se instala automáticamente junto con el nuevo Microsoft Edge en HoloLens 2. Esta extensión web le ofrece la posibilidad de sumergirse en vídeos en 360 grados. YouTube ofrece la selección más grande de 360 vídeos, por lo que te animamos a empezar allí.

#### <a name="how-to-use-webxr"></a>Cómo usar WebXR

1. Navegue a un sitio web con compatibilidad con WebXR.
1. Selecciona el **botón Entrar EN REALIDAD** en el sitio web. La ubicación y la representación visual de este botón pueden variar según el sitio web, pero puede ser similar a:

    ![Ejemplo del botón Escribir REALIDAD](images/75px-enter-vr.png)

1. La primera vez que intente iniciar una experiencia webXR en un dominio específico, el explorador pedirá su consentimiento para entrar en una vista envolvente, seleccione **Permitir**.
1. Usa [los gestos de HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame) para manipular la experiencia.
1. Si la experiencia no tiene un botón **Salir,** usa el gesto [Inicio](hololens2-basic-usage.md#start-gesture) para volver a casa.

**Ejemplos de WebXR recomendados**
- Visor 360 (vea la sección siguiente)
- [Dinosaurios XR](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>Cómo usar 360 Viewer

1. Navega a un vídeo de 360 grados en YouTube.
1. En el marco de vídeo, selecciona el botón de auriculares de realidad mixta:

    ![Botón para activar 360 Viewer](images/enter-360-viewer.jpg)

1. La primera vez que intente iniciar 360 Viewer en un dominio específico, el explorador pedirá su consentimiento para entrar en una vista envolvente. Seleccione **Permitir**.
1. [Pulsa aire](hololens2-basic-usage.md#select-using-air-tap) para abrir los controles de reproducción. Usa [los rayos de](hololens2-basic-usage.md#select-using-air-tap) mano y el toque de aire para reproducir/pausar, saltar hacia delante/atrás, activar/desactivar los títulos o detener la experiencia (que sale de la vista envolvente). Los controles de reproducción desaparecerán después de unos segundos de inactividad.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Principales problemas conocidos de WebXR y visor de 360
- En las experiencias de WebXR, los hologramas pueden desplazarse o inclinarse al inclinar la cabeza o moverse por el entorno.
- Según la complejidad de la experiencia webXR, la velocidad de fotogramas puede caer o tartamudear.
- Las uniones de mano articuladas aún no están disponibles en WebXR.
- Al salir de una experiencia de Visor webXR o 360, los hologramas de la casa de realidad mixta pueden tardar 30 segundos o más en volver a aparecer.
- Es posible que 360 vídeos de sitios web distintos de YouTube no funcionen como se esperaba.
- Si 360 vídeos no entran en la vista envolvente (o no aparece el botón de auriculares de realidad mixta), intenta actualizar la página.
- Los títulos aún no están visibles en 360 Viewer en HoloLens 2.
- Pausar un vídeo en 360 Viewer impide que el vídeo se representa (pero al seleccionar el botón reproducir correctamente se reanuda la reproducción).
- El botón "siguiente vídeo" en 360 Viewer no funciona actualmente.
- Puedes reproducir vídeos 2D en un modo envolvente de "teatro", pero la velocidad de fotogramas será inferior a 30 fps.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Proporcionar comentarios sobre WebXR y visor 360

Comparta comentarios y errores con nuestro equipo a través de la **característica Enviar comentarios** en el nuevo Microsoft Edge.

### <a name="new-settings-app"></a>Nueva aplicación Configuración

Con esta versión, presentamos una nueva versión de la aplicación Configuración. La nueva aplicación Configuración incluye nuevas características y configuraciones expandidas para HoloLens 2 en las siguientes áreas: Sonido, Power & sleep, Red & Internet, Aplicaciones, Cuentas, Facilidad de acceso y mucho más.

> [!NOTE]
> Dado que la nueva aplicación Configuración es distinta de la aplicación configuración heredada, las ventanas de configuración que colocaste anteriormente alrededor del entorno se quitarán al actualizar.

![Página principal de la aplicación Nueva configuración](images/new-settings-app.png)

**Nuevas características y configuración**
- Búsqueda de configuración: busque la configuración de la página principal configuración con palabras clave o el nombre de la configuración.
- Sonido > sistema:
  - Dispositivos de audio de entrada y salida: elija independientemente los dispositivos de audio de entrada y salida (por ejemplo, escuchar audio Bluetooth través de auriculares o usar un micrófono USB-C para la entrada de audio).
    > [!NOTE]
    > Bluetooth holoLens 2 no admite micrófonos.
  - Volumen de la aplicación: ajusta de forma independiente el volumen de cada aplicación. Consulta [por control de volumen de aplicación](#per-app-volume-control).
- Sistema > Power & suspensión: elige cuándo el dispositivo debe ir a reposo después de un período de inactividad.
- Sistema > batería: habilite manualmente el modo de ahorro de batería o establezca un umbral de batería en el que el modo de ahorro de batería se active automáticamente.
- Dispositivos > USB: puedes deshabilitar las conexiones USB de forma predeterminada.
- Red & Internet:
  - Los adaptadores Ethernet USB-C ahora aparecerán en Red & Internet.
  - La configuración del adaptador Ethernet USB-C ya está disponible, incluida su dirección IP.
  - Ahora puedes habilitar el modo avión en HoloLens 2.
- Aplicaciones: puedes restablecer las aplicaciones predeterminadas usadas para los tipos de archivos y vínculos. Para obtener más información, [consulta Selector de aplicaciones predeterminado](#default-app-picker).
- Cuentas > Otros usuarios: los propietarios de dispositivos pueden agregar usuarios, actualizar usuarios estándar a propietarios de dispositivos, degradar los propietarios de dispositivos a usuarios estándar y quitar usuarios.
- Facilidad de acceso: cambiar el tamaño del texto y algunos efectos visuales.

**Problemas conocidos**
- Se quitarán las ventanas de configuración colocadas anteriormente (consulta la nota anterior).
- La página Ethernet muestra un dispositivo Ethernet virtual ("UsbNcm") en todo momento (investigando). Este dispositivo Ethernet virtual también aparecerá en la página Red de configuración del dispositivo, pero puede omitirse (investigando).
- Ya no puedes cambiar el nombre del dispositivo con la aplicación Configuración (los administradores de TI pueden usar paquetes de aprovisionamiento o MDM para cambiar el nombre de los dispositivos).
- Es posible que el uso de batería para el nuevo Microsoft Edge no sea preciso, debido a su naturaleza como una aplicación de escritorio de Win32 compatible con una capa de adaptador para UWP (no se prevé ninguna corrección próximamente).

### <a name="display-color-calibration"></a>Calibración de color para mostrar

*Se agregó en la compilación 20293.1000 de Windows Insider*

Con esta nueva configuración, puedes seleccionar un perfil de color alternativo para la pantalla de HoloLens 2. Esto puede ayudar a que los colores parezcan más precisos, especialmente en niveles de brillo de pantalla inferiores. La calibración de color para mostrar se puede encontrar en la aplicación Configuración, en la página Calibración > sistema.

> [!NOTE]
> Dado que esta configuración guarda un nuevo perfil de color en el firmware de pantalla, es una configuración por dispositivo (y no única para cada cuenta de usuario).

#### <a name="how-to-use-display-color-calibration"></a>Cómo usar la calibración de color de pantalla

1. Inicie la **aplicación Configuración** y vaya a System **> Calibration**.
1. En **Calibración de color para**mostrar, seleccione el botón Ejecutar **calibración de color para** mostrar.
1. La experiencia de calibración de color de pantalla se iniciará y te animará a asegurarte de que el visor está en la posición correcta.
1. Después de continuar con los cuadros de diálogo de instrucciones, la pantalla se atenuará automáticamente al 30 % de brillo.
    > [!TIP]
    > Si tienes problemas para ver la escena atenuada en el entorno, puedes ajustar manualmente el nivel de brillo de HoloLens 2 con los botones de brillo del lado izquierdo del dispositivo.
1. Seleccione los botones 1 a 6 para probar al instante cada perfil de color y busque uno que se vea mejor a los ojos (esto suele significar el perfil que ayuda a que la escena parezca más neutral, con el patrón de escala de grises y los tonos de la piel como se esperaba).

    ![Mostrar escena de calibración de color](images/color-cal-ui.png)
    
1. Cuando esté satisfecho con el perfil seleccionado, seleccione el botón **Guardar & Salir**
1. Si prefiere no realizar cambios, seleccione el botón **Cancelar & Salir** y los cambios se revertirán.

> [!TIP]
> Estas son algunas sugerencias útiles que debe tener en cuenta al usar la configuración de calibración de color de pantalla:
> - Puedes volver a ejecutar la calibración de color de pantalla desde Configuración siempre que quieras
> - Si alguien del dispositivo ha usado anteriormente la configuración para cambiar los perfiles de color, la fecha y hora del cambio más reciente se reflejará en la página Configuración
> - Al volver a ejecutar la calibración de color de presentación, se resaltará el perfil de color guardado anteriormente y no aparecerá el perfil 0 (ya que el perfil 0 representa el perfil de color original de la pantalla)
> - Si desea volver al perfil de color original de la pantalla, puede hacerlo desde la página Configuración (vea cómo restablecer el perfil [de color](#how-to-reset-color-profile))

#### <a name="how-to-reset-color-profile"></a>Cómo restablecer el perfil de color

Si no estás conforme con el perfil de color personalizado guardado en holoLens 2, puedes restaurar el perfil de color original del dispositivo:
1. Inicie la **aplicación Configuración** y vaya a System **> Calibration**.
1. En **Mostrar calibración de color,** seleccione **el botón Restablecer al perfil de color** predeterminado.
1. Cuando se abra el cuadro de diálogo, seleccione **Reiniciar** si está listo para reiniciar HoloLens 2 y aplicar los cambios.

#### <a name="top-display-color-calibration-known-issues"></a>Problemas conocidos de calibración de color de la pantalla superior

- En la página Configuración, la cadena de estado que indica cuándo se cambió por última vez el perfil de color estará desa actualizarse hasta que vuelva a cargar esa página de Configuración. 
    - Solución alternativa: seleccione otra página Configuración y, a continuación, vuelva a seleccionar la página Calibración.
- Si hololens 2 se queda en reposo mientras se ejecuta la calibración del color de la pantalla, se reanudará más tarde en la casa de realidad mixta y el nivel de brillo de la pantalla seguirá atenuado.
- Es posible que deba intentar presionar los botones de brillo del lado izquierdo del dispositivo hacia arriba o hacia abajo unas cuantas veces antes de que funcionen como se esperaba.

### <a name="default-app-picker"></a>Selector de aplicaciones predeterminado

Cuando activas un hipervínculo o abres un tipo de archivo con más de una aplicación instalada, que lo admite, verás una nueva ventana abierta que te pedirá que selecciones qué aplicación instalada debe controlar el archivo o el tipo de vínculo. En esta ventana, también puedes elegir que la aplicación seleccionada controle el archivo o el tipo de vínculo "Once" o "Always".

![Ventana selector de aplicaciones](images/default-app-picker.png)

Si eliges "Siempre" pero más adelante quieres cambiar qué aplicación controla un tipo de archivo o vínculo determinado, puedes restablecer los valores predeterminados guardados en Configuración **> Aplicaciones**. Desplácese hasta la parte inferior **** de la página y seleccione el botón Borrar en "Aplicaciones predeterminadas para tipos de archivo" o "Aplicaciones predeterminadas para tipos de vínculos". A diferencia de la configuración similar en equipos de escritorio, no se pueden restablecer los valores predeterminados de tipo de archivo individual.

### <a name="per-app-volume-control"></a>Control de volumen por aplicación

Ahora, en esta compilación de Windows Insider, los usuarios pueden ajustar manualmente el nivel de volumen de cada aplicación. Esto permite a los usuarios centrarse mejor en las aplicaciones que necesitan o escuchar mejor al usar varias aplicaciones. Por ejemplo, tener que desactivar el volumen de una aplicación mientras se llama a otra persona para obtener asistencia remota en otra.

Para establecer el volumen de una aplicación individual, vaya a **Configuración**sonido del sistema y, en Opciones avanzadas de sonido, seleccione Volumen de la aplicación  ->  ****  ->  **** **y preferencias del dispositivo**.

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

### <a name="office-web-app"></a>Aplicación web de Office

La aplicación web de Office se ha agregado a la lista "Todas las aplicaciones" del menú Inicio. Esta aplicación web también puede anclarse a Inicio o desinstalarse. Dado que se trata de una aplicación web, su funcionalidad coincide exactamente con lo que experimentarías al visitar https://www.office.com . La funcionalidad de la aplicación web de Office solo está disponible cuando HoloLens 2 tiene una conexión a Internet activa.

### <a name="swipe-to-type"></a>Deslizar el dedo para escribir

A algunos clientes les resulta más rápido "escribir" en teclados virtuales deslizando la forma de la palabra que pretenden escribir y estamos previsualizando esta característica para el teclado holográfico. Puedes deslizar una palabra a la vez pasando la punta del dedo por el plano del teclado holográfico, deslizando la forma de la palabra y retirando la punta del dedo del plano del teclado. Puedes deslizar el dedo por las palabras de seguimiento sin necesidad de presionar la barra espaciador quitando el dedo del teclado entre palabras. Sabrás que la característica funciona si ves una pista de deslizar el dedo siguiendo el movimiento del dedo en el teclado.

Ten en cuenta que esta característica puede ser complicada de usar y dominar debido a la naturaleza de un teclado holográfico en el que no sientas resistencia contra el dedo (a diferencia de una pantalla de teléfono móvil). Estamos evaluando esta característica para la versión pública, por lo que sus comentarios son importantes; si encuentra la característica útil o tiene comentarios positivos, háganoslo saber a través del Centro [de opiniones](hololens-feedback.md).

### <a name="power-menu-from-start"></a>Menú Inicio

Un nuevo menú que permite al usuario cerrar sesión, apagar y reiniciar el dispositivo. Indicador de la pantalla Inicio de HoloLens que muestra cuándo está disponible una actualización del sistema.

#### <a name="how-to-use"></a>Cómo usarlo

1. Abra la pantalla Inicio de HoloLens con el gesto [Inicio](hololens2-basic-usage.md#start-gesture) o diciendo "Ir a Inicio".

2. Observe el icono de puntos suspensivos (...) junto a la imagen de perfil de usuario:

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Seleccione la imagen de perfil de usuario con las manos o el comando de voz "Power".

4. Aparece un menú con opciones para Cerrar sesión, Reiniciar o Apagar el dispositivo:

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Seleccione las opciones de menú para cerrar la sesión, reiniciar o apagar HoloLens. Es posible que la opción Cerrar sesión no esté disponible si el dispositivo está configurado para una sola cuenta [de Microsoft (MSA) o una cuenta local](hololens-identity.md).

6. Cierre el menú tocando en cualquier otro lugar o cerrando el menú Inicio con el gesto Inicio.

#### <a name="update-indicator"></a>Indicador de actualización

Cuando hay una actualización disponible, el icono de puntos suspensivos se encenderá para indicar que un reinicio instalará la actualización Las opciones de menú también cambian para reflejar la presencia de la actualización.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Varios usuarios enumerados en la pantalla Inicio de sesión

Anteriormente, la pantalla Iniciar sesión solo mostraba el usuario que ha iniciado sesión más recientemente, así como un punto de entrada "Otro usuario". Hemos recibido comentarios de clientes que no son suficientes si varios usuarios han iniciado sesión en el dispositivo. Seguían siendo necesarios para volver a escribir su nombre de usuario, etc.

Se introdujo en esta compilación **** de Windows Insider, al seleccionar Otro usuario que se encuentra a la derecha del campo de entrada de PIN, la pantalla Iniciar sesión mostrará varios usuarios con los que ha iniciado sesión previamente en el dispositivo. Esto permite a los usuarios seleccionar su perfil de usuario y, a continuación, iniciar sesión con sus credenciales de Windows Hello. También se puede agregar un nuevo usuario al dispositivo desde esta página Otros usuarios mediante el **botón Agregar** cuenta.

Cuando se encuentra en el menú Otros usuarios, el botón Otros usuarios mostrará el último usuario que ha iniciado sesión en el dispositivo. Seleccione este botón para volver a la pantalla Inicio de sesión de este usuario.

![Pantalla de inicio de sesión predeterminada](./images/multiusers1.jpg)

<br>

![Pantalla de inicio de sesión de otros usuarios](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Compatibilidad con micrófono externo USB-C

> [!IMPORTANT]
> Conectar un micrófono USB no **lo establecerá automáticamente como el dispositivo de entrada**. Al conectar un conjunto de auriculares USB-C, los usuarios observarán que el audio de los auriculares se redirigirá automáticamente a los auriculares, pero el sistema operativo HoloLens prioriza la matriz de micrófono interna por encima de cualquier otro dispositivo de entrada. **Para usar un micrófono USB-C, siga los pasos que se indican a continuación.**

Los usuarios pueden seleccionar micrófonos externos conectados a USB-C mediante el panel **Configuración** de sonido. Los micrófonos USB-C se pueden usar para llamar, grabar, etc.

Abre la **aplicación Configuración** y selecciona **Sonido del**  >  **sistema**.

![Configuración de sonido](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Para usar micrófonos externos con **asistencia remota,** los usuarios tendrán que hacer clic en el hipervínculo "Administrar dispositivos de sonido".
>
> A continuación, use la lista desplegable para establecer el micrófono externo como **Predeterminado** o **Predeterminado de comunicaciones.** Elegir Predeterminado **significa** que el micrófono externo se usará en todas partes.
>
> Elegir **Comunicaciones predeterminadas** significa que el micrófono externo se usará en asistencia remota y otras aplicaciones de comunicaciones, pero la matriz de micrófonos HoloLens aún puede usarse para otras tareas.

![Administrar dispositivos de sonido](images/usbc-mic-2.png)

<br>

![Establecer el valor predeterminado del micrófono](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>¿Qué hay Bluetooth compatibilidad con micrófonos?

Desafortunadamente Bluetooth micrófonos aún no se admiten actualmente en HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Solución de problemas de micrófonos USB-C

Ten en cuenta que algunos micrófonos USB-C se informan incorrectamente como micrófono *y* altavoz. Este es un problema con el micrófono y no con HoloLens. Al conectar uno de estos micrófonos a HoloLens, el sonido puede perderse. Afortunadamente, hay una solución sencilla.  

En **Configuración**  ->  **sonido del**  ->  **sistema**, establezca explícitamente los altavoces integrados **(controlador de audio** de característica **analógica)** como el dispositivo predeterminado . HoloLens debe recordar esta configuración incluso si el micrófono se quita y se vuelve a conectar más adelante.

![Solución de problemas de micrófonos USB-C](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Inicio de sesión automático de visitantes para quioscos

Esta nueva característica permite usar el inicio de sesión automático en cuentas de visitantes para los modos de quiosco.

Para una configuración que no es AAD, para configurar un dispositivo para el inicio de sesión automático del visitante:

1. Cree un paquete de aprovisionamiento que:
    1. Configura la configuración **de tiempo de ejecución/AssignedAccess para** permitir cuentas de visitante.
    1. Opcionalmente, inscribe el dispositivo en MDM (configuración de tiempo de **ejecución/Workplace/Enrollments)** para que se pueda administrar más adelante.
    1. No crear una cuenta local
1. [Aplicar el paquete de aprovisionamiento](hololens-provisioning.md).

Para una configuración de AAD, los usuarios pueden lograr algo similar a esto hoy sin este cambio. Los dispositivos unidos a AAD configurados para el modo de pantalla completa pueden iniciar sesión en una cuenta de visitante con un solo botón pulsando desde la pantalla de inicio de sesión. Una vez que haya iniciado sesión en la cuenta de visitante, el dispositivo no volverá a solicitar el inicio de sesión hasta que el visitante haya iniciado sesión explícitamente en el menú inicio o se reinicie el dispositivo.

El inicio de sesión automático de visitantes se puede administrar a [través de una directiva OMA-URI](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) personalizada:

- Valor de URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Directiva  | Descripción   | Configuraciones  |
|---|---|---|
| Realidad mixta/VisitorAutoLogon  | Permite que un visitante inicie sesión automáticamente en un quiosco   | 1 (Sí), 0 (No, predeterminado).  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Usar la nueva configuración y las aplicaciones perimetrales en los modos quiosco

Cuando se [](hololens-kiosk.md)incluyen aplicaciones en quioscos, un administrador de TI suele agregar la aplicación al quiosco, pero se usa el id. de modelo de usuario (AUMID) de la aplicación. Dado que tanto la aplicación Configuración como la aplicación Microsoft Edge se consideran nuevas aplicaciones y distintas de las aplicaciones anteriores, los quioscos que usan AUMID para esas aplicaciones tendrán que actualizarse para usar el nuevo AUMID.

Al modificar un quiosco para incluir las nuevas aplicaciones, se recomienda agregar en el nuevo AUMID, así como dejar la anterior. Esto creará una transición fácil cuando los usuarios actualicen el sistema operativo y no tendrán que recibir nuevas directivas para seguir usando el quiosco de pantalla completa según lo previsto.

| Aplicación                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Aplicación configuración antigua       | HolographicSystemSettings_cw5n1h2txyewy! Aplicación            |
| Nueva aplicación de configuración       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! Aplicación |
| Aplicación antigua de Microsoft Edge | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| Nueva aplicación de Microsoft Edge | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Cambios en el comportamiento del modo quiosco para controlar errores

En compilaciones anteriores, si un dispositivo tuviera una configuración de quiosco, que es una combinación de acceso asignado global y acceso asignado al miembro del grupo de AAD, si la determinación de la pertenencia a un grupo de AAD no se pudo determinar, el usuario vería["nada](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)que se muestra en el menú inicio".

A partir de la versión de Windows Insider, la experiencia del quiosco de pantalla completa volverá a la configuración global de quiosco de pantalla completa (si está presente) en caso de errores durante el modo de quiosco de grupo de AAD.

### <a name="new-settingsuris-for-page-settings-visibility"></a>Nueva configuraciónURIs para la visibilidad de la configuración de página

En [Windows Holographic, versión 20H2,](hololens-release-notes.md#windows-holographic-version-20h2) agregamos la directiva [Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir las páginas vistas en la aplicación Configuración. PageVisibilityList es una directiva mediante la cual los administradores de TI pueden evitar que páginas específicas de la aplicación Configuración del sistema sean visibles o accesibles, o bien pueden hacer lo sean en todas las páginas excepto en aquellas especificadas.

Si visita [visibilidad de configuración de](settings-uri-list.md)página, encontrará instrucciones para usar este CSP y la lista de URI disponibles en versiones anteriores.

En las compilaciones de Windows Insider, estamos expandiendo la lista de URI de configuración disponibles, que los administradores de TI pueden administrar. Algunos de estos URI son para áreas recién disponibles dentro de la nueva aplicación Configuración. Si usa la directiva Settings/PageVisibilityList, revise la siguiente lista y ajuste las páginas permitidas o bloqueadas según sea necesario.

> [!NOTE]
> **En desuso: ms-settings:network-proxy**
>
> Una página de configuración está en desuso en estas compilaciones más recientes. La antigua **página &** proxy de Internet ya no está disponible como  >  **** configuración global. La nueva configuración de proxy por conexión se encuentra en Propiedades de **Red & Internet**  >  **Wi-Fi**o Propiedades de red & Ethernet de  >  **** ****  >  ****  >  **Internet.**

<br>

| Página de configuración                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Aplicaciones > aplicaciones & características                               | `ms-settings:appsfeatures`                         |
| Aplicaciones > aplicaciones & características > opciones avanzadas          | `ms-settings:appsfeatures-app`                     |
| Aplicaciones > mapas sin conexión                                  | `ms-settings:maps`                                 |
| Aplicaciones > mapas sin conexión > Descargar mapas                  | `ms-settings:maps-downloadmaps`                    |
| Dispositivos > mouse                                      | `ms-settings:mouse`                                |
| Dispositivos > USB                                        | `ms-settings:usb`                                  |
| Red & modo > avión                   | `ms-settings:network-airplanemode`                 |
| Privacidad > general                                    | `ms-settings:privacy-general`                      |
| Privacidad > ink & personalización de escritura             | `ms-settings:privacy-speechtyping`                 |
| Movimiento de > privacidad                                     | `ms-settings:privacy-motion`                       |
| Privacidad > bordes de captura de pantalla                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Privacidad > capturas de pantalla y aplicaciones                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Batería > sistema                                     | `ms-settings:batterysaver`                         |
| Batería > sistema                                     | `ms-settings:batterysaver-settings`                |
| System > Sound                                       | `ms-settings:sound`                                |
| System > Sound > Preferencias de dispositivo y volumen de la aplicación | `ms-settings:apps-volume`                          |
| System > Sound > Manage sound devices              | `ms-settings:sound-devices`                        |
| System > Storage > Configure Storage Sense         | `ms-settings:storagepolicies`                      |
| Hora & idioma > fecha & hora                        | `ms-settings:dateandtime`                          |
| Teclado & idioma > teclado                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| Actualizar & seguridad > restablecer & recuperación               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>URI actualizados

Anteriormente, los dos URI siguientes no llevarían a un usuario directamente a las páginas indicadas, sino que solo bloqueaban la página de actualizaciones principales. Los siguientes elementos se han actualizado para dirigir a sus páginas:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Configuración de diagnósticos de reserva a través de la aplicación Configuración

Ahora, en la aplicación Configuración, un usuario puede configurar el comportamiento de [Diagnósticos de reserva.](hololens-diagnostic-logs.md) En la aplicación Configuración, vaya a **la página Solución**de problemas  ->  **de** privacidad para configurar esta configuración.

> [!NOTE]
> Si hay una directiva MDM configurada para el dispositivo, el usuario no podrá invalidar ese comportamiento.  

### <a name="share-things-with-nearby-devices"></a>Compartir cosas con dispositivos cercanos

Comparte cosas con dispositivos cercanos a Windows 10, incluidos equipos y otros dispositivos HoloLens 2 que ejecutan HoloLens Insider compilaciones 20279.1006+. Puedes probarla en **Configuración**Experiencias compartidas del sistema para compartir archivos o  ->  ****  ->  **** direcciones URL desde un HoloLens a un equipo. Para obtener más información, obtenga más información sobre cómo [compartir cosas con dispositivos cercanos en Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Esta característica se puede administrar a [través de Connectivity/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices).

### <a name="new-os-update-troubleshooter"></a>Nuevo solucionador de problemas de actualización del sistema operativo

Además de los solucionadores de problemas anteriores de la aplicación Configuración, se ha agregado un nuevo solucionador de problemas con la adición de la nueva aplicación Configuración para actualizaciones del sistema operativo. Vaya a **Configuración**  ->  **Actualizar seguridad &amp; **  >  **Solucionar problemas de**Windows  >  **Update** y seleccione **Inicio**. Esto le permite recopilar seguimientos mientras reproduce el problema con las actualizaciones del sistema operativo para ayudar mejor a solucionar problemas con su ti o soporte técnico.

### <a name="delivery-optimization-preview"></a>Vista previa de optimización de entrega

Con esta actualización de HoloLens Insider, Windows Holographic para empresas habilita una vista previa de la configuración de optimización de distribución para reducir el consumo de ancho de banda para las descargas de varios dispositivos HoloLens. Una descripción más completa de esta funcionalidad junto con la configuración de red recomendada está disponible aquí: Optimización de distribución para [actualizaciones de Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization).

Las siguientes opciones de configuración están habilitadas como parte de la superficie de administración y [se pueden configurar desde Intune:](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)

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

Algunas advertencias sobre esta oferta de vista previa:

- La compatibilidad con HoloLens está limitada en esta versión preliminar solo a las actualizaciones del sistema operativo.
- Windows Holographic para empresas solo admite modos de descarga HTTP y descargas desde un extremo de caché conectada de [Microsoft;](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) Los modos de descarga punto a punto y las asignaciones de grupo no son compatibles con dispositivos HoloLens en este momento.
- HoloLens no admite la optimización de distribución o implementación para los puntos de conexión de Windows Server Update Services.
- La solución de problemas requerirá diagnósticos en el servidor de caché conectada o **** la recopilación de un seguimiento en HoloLens en HoloLens mediante la actualización de configuración & solución de problemas de  >  ****  >   ****  >   **seguridad de Windows Update**.

### <a name="improvements-and-fixes-in-the-update"></a>Mejoras y correcciones en la actualización:

- [Los diagnósticos sin](hololens-diagnostic-logs.md#offline-diagnostics) conexión también incluirán información adicional del dispositivo para el número de serie y la versión del sistema operativo.






## <a name="start-receiving-insider-builds"></a>Empezar a recibir compilaciones de Insider

> [!NOTE]
> Si no has actualizado recientemente, reinicia el dispositivo para actualizar el estado y obtener la compilación más reciente.
> - El comando de voz "Reiniciar dispositivo" funciona bien. 
> - También puedes elegir el botón reiniciar en Configuración/Programa Windows Insider.
>
> Tuvimos un error en el back-end que puede que haya encontrado y esto le hará volver a la pista.

En un dispositivo HoloLens 2, ve a **Configuración**Actualizar & Seguridad del programa  >  ****  >  **Windows Insider** y selecciona **Introducción.** Vincula la cuenta que usaste para registrarte como Windows Insider.

Windows insider ahora se está moviendo a Canales. El **anillo** rápido se convertirá en **** el **Canal de desarrollo,** **** el anillo lento se convertirá en el canal **beta**y el anillo versión preliminar se convertirá en el Canal de vista previa **de versión.** Este es el aspecto de esa asignación:

![Explicación de Canales de Windows Insider](images/WindowsInsiderChannels.png)

Para obtener más información, consulta [Introducción a los canales de Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) en blogs de Windows.

A continuación, selecciona Desarrollo activo **de Windows,** elige si quieres recibir compilaciones del Canal **de desarrollo** o canal **beta** y revisa los términos del programa.

Seleccione **Confirmar > Reiniciar ahora** para finalizar. Después de reiniciar el dispositivo, ve a Configuración > Actualización & seguridad > **Busca** actualizaciones para obtener la compilación más reciente.

### <a name="update-error-0x80070490-work-around"></a>Actualizar error 0x80070490 de trabajo
Si se produce un error de actualización 0x80070490 al actualizar en el canal Dev o Beta, pruebe el siguiente trabajo a corto plazo. Implica mover el canal insider, recoger la actualización y, a continuación, volver a mover el canal Insider.

#### <a name="stage-one---release-preview"></a>Fase uno: versión preliminar
1.  Configuración, Actualizar & seguridad, Programa Windows Insider, seleccione **Liberar canal de vista previa**.
2.  Configuración, Actualizar & seguridad, Windows Update, **Buscar actualizaciones**. Después de la actualización, continúe con la fase dos.

#### <a name="stage-two---dev-channel"></a>Fase dos: Canal de desarrollo
1. Configuración, Actualizar & seguridad, Programa Windows Insider, seleccione **Canal de desarrollo**.
2. Configuración, Actualizar & seguridad, Windows Update, **Buscar actualizaciones**.

## <a name="ffu-download-and-flash-directions"></a>Instrucciones de descarga e flash FFU
To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.
1. En pc:

    1. Descargar ffu a su PC desde [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Instalar ARC (Advanced Recovery Companion) desde Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. En HoloLens: desbloqueo piloto: **abra**La actualización de configuración & seguridad del programa  >  ****  >  **Windows Insider** y, a continuación, regístrese y reinicie el dispositivo.

1. Flash FFU: ahora puede flashear el vuelo firmado por FFU con ARC.

## <a name="provide-feedback-and-report-issues"></a>Proporcionar comentarios e informar de problemas

Usa la [aplicación Centro de opiniones](hololens-feedback.md) en holoLens para proporcionar comentarios e informar de problemas. El uso del Centro de opiniones garantiza que se incluya toda la información de diagnóstico necesaria para ayudar a nuestros ingenieros a depurar y resolver rápidamente el problema.  Los problemas con la versión en chino y japonés de HoloLens deben informarse del mismo modo.

> [!NOTE]
> Asegúrese de aceptar el mensaje que le pregunta si desea que el Centro de opiniones tenga acceso a la carpeta Documentos (seleccione **Sí** cuando se le pida).

## <a name="note-for-developers"></a>Nota para desarrolladores

Le recomendamos que pruebe a desarrollar sus aplicaciones con las compilaciones de Insider de HoloLens.  Consulte la [Documentación para desarrolladores de HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) para empezar. Esas mismas instrucciones funcionan con las compilaciones de Insider de HoloLens.  Puedes usar las mismas compilaciones de Unity y Visual Studio que ya estás usando para el desarrollo de HoloLens.

## <a name="stop-receiving-insider-builds"></a>Dejar de recibir compilaciones de Insider

Si ya no quieres recibir compilaciones de Insider de Windows Holographic, puedes optar por no [](hololens-recovery.md) participar cuando hololens ejecute una compilación de producción o puedes recuperar el dispositivo con el Complemento de recuperación avanzada para recuperar el dispositivo en una versión que no sea Insider de Windows Holographic.

> [!CAUTION]
> Hay un problema conocido en el que los usuarios que desanscriben las compilaciones de Insider Preview después de reinstalar manualmente una compilación de vista previa nueva experimentarían una pantalla azul. Después, deben recuperar manualmente su dispositivo. Para obtener información completa sobre si se vería afectado o no, vea más información sobre [este problema conocido](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).

Para comprobar que HoloLens ejecuta una compilación de producción:

1. Vaya **a Configuración > System > Acerca de**y busque el número de compilación.

1. [Vea las notas de la versión de los números de compilación de producción.](hololens-release-notes.md)

Para no participar en las compilaciones de Insider:

1. En un HoloLens que ejecuta una compilación de producción, ve a Configuración **> Actualizar & Seguridad > Windows Insider Program**y selecciona Detener compilaciones de **Insider**.

1. Sigue las instrucciones para desactivar el dispositivo.
