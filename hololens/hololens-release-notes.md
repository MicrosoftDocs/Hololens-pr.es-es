---
title: HoloLens 2 notas de la versión
description: Manténgase al día con todas las actualizaciones de cada nueva versión HoloLens 2 lanzamiento.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 02/16/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 554dc796ee793a3f7e81108c6eb614a9555f10d7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397346"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 notas de la versión

Para asegurarse de que tiene una experiencia productiva con los dispositivos HoloLens, seguimos lanzando actualizaciones de características, errores y seguridad. En esta página, puede ver las novedades de HoloLens cada mes. Para obtener la actualización de HoloLens 2 más [](hololens-update-hololens.md#check-for-updates-and-manually-update) reciente, puede buscar actualizaciones y actualizar manualmente u obtener la actualización flash completa (FFU) para flashear el dispositivo a través de Advanced [Recovery Companion](hololens-recovery.md#clean-reflash-the-device). La [descarga](https://aka.ms/hololens2download) se mantiene actualizada y proporciona la compilación más reciente disponible con carácter general.

## <a name="windows-holographic-version-21h1"></a>Windows Holographic, versión 21H1
- Compilación 20346.1002

Esta actualización contiene características para dos audiencias de destino; características que cualquier usuario puede usar en un dispositivo por parte del usuario final y nuevas opciones de administración de dispositivos que pueden configurar los administradores de TI. En la tabla siguiente se especifican las características que son relevantes para cada audiencia. Si es administrador de TI, consulte nuestra lista de comprobación de actualización de [administradores de TI.](#it-admin---update-checklist)
>[!IMPORTANT]
>Para actualizar a esta compilación, HoloLens 2 dispositivos deben ejecutar actualmente la actualización de febrero de 2021 (compilación 19041.1136) o posterior. Si no ve esta actualización de características disponible, actualice primero el dispositivo e inténtelo de nuevo.

>[!NOTE]
>Actualmente, Microsoft HoloLens 2 admite actualizaciones de mantenimiento mensuales (correcciones de errores y seguridad) para las siguientes versiones:
>- Windows Holographic, versión 20H2 (compilación 19041.1128+)
>- Windows Holographic, versión 2004 (compilación 19041.1103+)
>- Windows Holographic, versión 1903 (compilación 18362+) 
>
> Con la introducción de la versión 21H1 de Windows Holographic, se van a interrumpir las actualizaciones de mantenimiento mensuales para **Windows Holographic versión 1903.** Esto nos permite centrarse en versiones más recientes y seguir entregando mejoras valiosas. 


| Nombre de la característica                                              | Descripción breve                                                                      | Público de destino | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Nuevo Microsoft Edge](#introducing-the-new-microsoft-edge)  | La nueva versión basada en Chromium Microsoft Edge ahora está disponible para HoloLens 2. | Usuario final | 
[WebXR y visor 360](#webxr-and-360-viewer) | Pruebe las experiencias web envolventes y la reproducción de vídeo en 360. | Usuario final | 
[Nueva aplicación de configuración](#new-settings-app) | La aplicación de configuración heredada se está reemplazando por una versión actualizada con nuevas características y configuraciones. | Usuario final |
[Calibración del color de la pantalla](#display-color-calibration) | Seleccione un perfil de color alternativo para la HoloLens 2 pantalla. | Usuario final |
[Selector de aplicaciones predeterminado](#default-app-picker) | Elija qué aplicación debe iniciarse para cada tipo de archivo o vínculo. | Usuario final |
[Control de volumen por aplicación](#per-app-volume-control) | Controlar el volumen de nivel de aplicación independientemente del volumen del sistema. | Usuario final |
[Instalación de aplicaciones web](#install-web-apps) | Instale aplicaciones web en HoloLens 2, como Microsoft Office, con el nuevo Microsoft Edge explorador. | Usuario final |
[Deslizar el dedo para escribir](#swipe-to-type) | Use la punta del dedo para "deslizar" las palabras en el teclado holográfico. | Usuario final |
[Menú De encendido desde Inicio](#power-menu-from-start) | En el menú Inicio, reinicie y apague el dispositivo HoloLens. | Usuario final |
[Varios usuarios enumerados en la pantalla de inicio de sesión](#multiple-users-listed-on-sign-in-screen) | Muestra varias cuentas de usuario en la pantalla Inicio de sesión. | Usuario final |
[Compatibilidad con micrófono externo USB-C](#usb-c-external-microphone-support) | Use micrófonos USB-C para aplicaciones y/o Remote Assist. | Usuario final |
[Inicio de sesión automático de visitante para quioscos](#visitor-auto-logon-for-kiosks) | Permite que el inicio de sesión automático en las cuentas de visitante se utilice para los modos de quiosco. | Administración de TI |
[Nuevos AUMID para nuevas aplicaciones en pantalla completa](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | AUMIDs para nuevas aplicaciones de Configuración y Edge. | Administración de TI |
[Entrega de errores en modo de pantalla completa mejorada](#kiosk-mode-behavior-changes-for-handling-of-failures) | El modo de pantalla completa busca Acceso asignado global antes de un menú de inicio vacío. | Administración de TI |
[Nueva configuraciónDI para la visibilidad de la configuración de página](#new-settings-uris-for-page-settings-visibility) | Más de 20 nuevas configuracionesDI para la directiva Settings/PageVisibilityList. | Administración de TI |
[Configuración de diagnósticos de reserva](#configuring-fallback-diagnostics-via-settings-app) | Establecer el comportamiento de diagnóstico de reserva en la aplicación configuración. | Administración de TI |
[Compartir cosas con dispositivos cercanos](#share-things-with-nearby-devices) | Compartir archivos o direcciones URL desde HoloLens a un equipo. | All |
[Nuevos seguimientos de diagnóstico del sistema operativo](#new-os-diagnostic-traces) | Nuevo solucionador de problemas en Configuración de actualizaciones del sistema operativo. | Administración de TI |
[Optimización de distribución versión preliminar](#delivery-optimization-preview) | Reduzca el consumo de ancho de banda para las descargas de varios dispositivos HoloLens. | Administración de TI |

Consulte las notas de la versión relacionadas:

- [Visite el archivo del emulador de HoloLens.](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Presentación de la nueva Microsoft Edge

![Animación del logotipo de Microsoft Edge heredado al nuevo logotipo Microsoft Edge imagen](images/new-edge.gif)

El nuevo Microsoft Edge adopta el proyecto de código abierto [Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) para crear una mejor compatibilidad para los clientes y una menor fragmentación de la web para desarrolladores web.

> [!IMPORTANT]
> Esta nueva Microsoft Edge reemplaza automáticamente a los Microsoft Edge heredados, que [ya no se admiten](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) en las nuevas versiones.

![Nueva captura Microsoft Edge pantalla](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Iniciar el nuevo Microsoft Edge

La nueva versión de Microsoft Edge ![icono de Microsoft Edge nuevo](images/new_edge_logo.png) (representado por un icono de remolino azul y verde) se ancla al menú Inicio se inicia automáticamente al activar un vínculo web.

> [!NOTE]
> La primera vez que inicie el nuevo Microsoft Edge en HoloLens 2, la configuración y los datos se importarán desde la base de datos Microsoft Edge. Si sigue usando datos heredados Microsoft Edge después de iniciar el nuevo Microsoft Edge, los nuevos datos no se sincronizarán de la Microsoft Edge heredada a la nueva Microsoft Edge.

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
> Hay al menos dos directivas de Microsoft Edge nuevas que sabemos *que no funcionarán* con HoloLens 2:
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
- Restauración del contenido a la ventana correcta, al examinar varias ventanas colocadas en su entorno

**No se espera que los escenarios y características funcionen:**
- Sonido espacial de varias ventanas con secuencias de audio simultáneas
- "See it, say it" (Verlo, decir)
- Impresión

**Principales problemas conocidos del explorador:**

- La vista previa de lupa en el teclado holográfico se ha deshabilitado para el nuevo Microsoft Edge. Esperamos volver a poder volver a crear esta característica en una actualización futura, una vez que la ampliación funcione correctamente.
- El audio puede reproducirse desde la ventana del explorador incorrecta si tiene otra ventana del explorador abierta y activa. Para evitar este problema, cierre la otra ventana activa que no se supone que esté reproduciendo audio.
- Al reproducir audio desde una ventana del explorador en modo ["Sígueme",](hololens2-basic-usage.md#follow-me-stop-following)el audio seguirá reproduciendo si deshabilita el modo "Sígueme". Para evitar este problema, detenga la reproducción de audio antes de deshabilitar el modo "Sígueme" o cierre la ventana con el **botón X.**
- Interactuar con ventanas de Microsoft Edge activas puede hacer que otras ventanas de aplicaciones 2D se vuelvan inactivas inesperadamente. Para reactivar estas ventanas, vuelva a interactuar con ellas.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge canales insider

El Microsoft Edge hace que tres canales de versión preliminar estén disponibles para la comunidad de Edge Insider: Beta, Dev y Canary. La instalación de un canal de versión preliminar no desinstala la versión publicada de Microsoft Edge en el HoloLens 2, y puede instalar más de una al mismo tiempo. 

Visite la [página principal Microsoft Edge Insider para](https://www.microsoftedgeinsider.com) obtener más información sobre la comunidad de Edge Insider. Para obtener más información sobre los diferentes canales de Edge Insider y empezar a trabajar, visite la página de descarga [de Edge Insider](https://www.microsoftedgeinsider.com/download).

Hay un par de métodos disponibles para instalar canales Microsoft Edge Insider para HoloLens 2:

**Instalación directa en el dispositivo (actualmente solo disponible para dispositivos no administrados)**
  1. En la HoloLens 2, visite la página [de descarga de Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Seleccione el **botón Download for HoloLens 2** (Descargar para HoloLens 2 para el canal de Edge Insider que desea instalar).
  1. Inicie el archivo .msix descargado desde la cola de descarga de Edge o desde la carpeta "Descargas" del dispositivo (mediante Explorador de archivos).
  1. [Se iniciará el instalador](app-deploy-app-installer.md) de la aplicación.
  1. Seleccione el botón **Instalar**.
  1. Después de una instalación correcta, encontrará Microsoft Edge Beta, Dev o Canary  como una entrada independiente en la lista Todas las aplicaciones de la menú Inicio.

**Instalación mediante PC con Portal de dispositivos Windows (requiere que [el modo de](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) desarrollador esté habilitado en HoloLens 2)**
  1. En el equipo, visite la página [de descarga de Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Seleccione el **botón de flecha desplegable** situado junto al botón "Download for Windows 10" (Descargar para Windows 10) del canal Edge Insider que desea instalar.
  1. Seleccione **HoloLens 2** en el menú desplegable.
  1. Guarde el archivo .msix en la carpeta "Descargas" del equipo (u otra carpeta que pueda encontrar fácilmente).
  1. Use [Portal de dispositivos Windows](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) en el equipo para instalar el archivo .msix descargado en HoloLens 2.
  1. Después de una instalación correcta, encontrará Microsoft Edge Beta, Dev o Canary  como una entrada independiente en la lista Todas las aplicaciones de la menú Inicio.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Uso de WDAC para bloquear nuevas Microsoft Edge

Para los administradores de TI que buscan actualizar su directiva [WDAC](windows-defender-application-control-wdac.md) para bloquear la nueva aplicación Microsoft Edge, deberá agregar lo siguiente a la directiva.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Administración de puntos de conexión para la nueva Microsoft Edge

Algunos entornos pueden tener restricciones de red para tener en cuenta como consideración. Para garantizar una experiencia sin problemas con el nuevo edge, [habilite estos puntos de conexión de Microsoft.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

Obtenga más información sobre los puntos de [conexión disponibles actualmente para HoloLens.](hololens-offline.md)

### <a name="install-web-apps"></a>Instalación de aplicaciones web
 > [!Note]
>A partir [de Windows Holographic, versión 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)la aplicación web de Office ya no estará preinstalada.

Puede usar la nueva instancia de Edge para instalar aplicaciones web junto con Microsoft Store aplicaciones. Por ejemplo, puede instalar la aplicación web Microsoft Office para ver y editar archivos hospedados en SharePoint o OneDrive. Para instalar la aplicación web de Office, visite y seleccione el botón Aplicación disponible o https://www.office.com **Instalar Office** en la barra de direcciones.  Seleccione **Instalar para** confirmar.

> [!IMPORTANT]
> La funcionalidad de la aplicación web de Office solo está disponible cuando HoloLens 2 tiene una conexión a Internet activa.

### <a name="webxr-and-360-viewer"></a>WebXR y visor 360

La nueva Microsoft Edge compatibilidad con WebXR, que es el nuevo estándar para crear experiencias web envolventes (reemplazando WebVR). Muchas experiencias web envolventes se diseñaron pensando en la realidad virtual (reemplazan el campo de vista por un entorno virtual), pero estas experiencias también son compatibles con HoloLens 2. El estándar WebXR también permite experiencias web envolventes de realidad aumentada y mixta que usan su entorno físico. A medida que los desarrolladores dedican más tiempo con WebXR, se prevé que lleguen nuevas experiencias envolventes de realidad mixta y aumentada para que los clientes HoloLens 2 prueben.

La extensión 360 Viewer se basa en WebXR y se instala automáticamente junto con el nuevo Microsoft Edge en HoloLens 2. Esta extensión web le ofrece la posibilidad de inmersarse en vídeos de 360 grados. YouTube ofrece la mayor selección de 360 vídeos, por lo que le recomendamos que empiece allí.

#### <a name="how-to-use-webxr"></a>Uso de WebXR

1. Vaya a un sitio web con compatibilidad con WebXR.
1. Seleccione el **botón Enter VR (Escribir VR)** en el sitio web. La ubicación y la representación visual de este botón pueden variar según el sitio web, pero puede tener un aspecto similar al siguiente:

    ![Ejemplo de botón Escribir VR](images/75px-enter-vr.png)

1. La primera vez que intente iniciar una experiencia de WebXR en un dominio específico, el explorador pedirá consentimiento para entrar en una vista inmersiva y seleccione **Permitir**.
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
- Es posible que 360 vídeos de sitios web que no son YouTube no funcionen según lo previsto.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Proporcionar comentarios sobre WebXR y visor 360

Comparta comentarios y errores con nuestro equipo a través de **la característica Enviar** comentarios de la nueva Microsoft Edge.

### <a name="new-settings-app"></a>Nueva aplicación de configuración

Con esta versión, presentamos una nueva versión de la aplicación Configuración. La nueva aplicación Configuración incluye nuevas características y configuraciones expandidas para HoloLens 2 en las áreas siguientes: Sonido, Suspensión de Power &, Red & Internet, Aplicaciones, Cuentas, Accesibilidad, etc.

> [!NOTE]
> Dado que la nueva aplicación Configuración es distinta de la aplicación de configuración heredada, las ventanas de configuración que se colocaron anteriormente en el entorno se quitarán al actualizarse.

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
- Cuentas > Otros usuarios: los propietarios de dispositivos pueden agregar usuarios, actualizar usuarios estándar a propietarios de dispositivos, degradar los propietarios de dispositivos a usuarios estándar y quitar usuarios.
- Accesibilidad: cambiar el tamaño del texto y algunos efectos visuales.

**Problemas conocidos**
- Se quitarán las ventanas de configuración colocadas anteriormente (consulte la nota anterior).
- Ya no puede cambiar el nombre del dispositivo con la aplicación Configuración. Los administradores de TI pueden cambiar el nombre de los dispositivos mediante Windows Autopilot para una [HoloLens 2 plantilla](https://docs.microsoft.com/hololens/hololens2-autopilot) de nombre de dispositivo o el nodo MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- La página Ethernet muestra un dispositivo Ethernet virtual ("UsbNcm") en todo momento.
- El uso de batería para el nuevo Microsoft Edge puede no ser preciso, debido a su naturaleza como una aplicación de escritorio Win32 compatible con una capa de adaptador de UWP (no se prevé ninguna corrección pronto).

#### <a name="display-color-calibration"></a>Calibración del color de la pantalla



Con esta nueva configuración, puede seleccionar un perfil de color alternativo para la HoloLens 2 pantalla. Esto puede ayudar a que los colores parezcan más precisos, especialmente en niveles de brillo de pantalla inferiores. La calibración del color de pantalla se puede encontrar en la aplicación Configuración, en la página System > Calibration (Calibración del sistema).

> [!NOTE]
> Dado que esta configuración guarda un nuevo perfil de color en el firmware para mostrar, es una configuración por dispositivo (y no única para cada cuenta de usuario).

##### <a name="how-to-use-display-color-calibration"></a>Uso de la calibración del color de la pantalla

1. Inicie la **aplicación Configuración** y vaya a System **> Calibration**.
1. En **Display color calibration (Calibración de color** para mostrar), seleccione el botón Run display color calibration **(Ejecutar calibración del color de pantalla).**
1. Se iniciará la experiencia de calibración del color de la pantalla y se le animará a asegurarse de que el visor está en la posición correcta.
1. Después de continuar con los cuadros de diálogo de instrucciones, la pantalla se atenuará automáticamente hasta un 30 % de brillo.
    > [!TIP]
    > Si tiene problemas para ver la escena atenuada en su entorno, puede ajustar manualmente el nivel de brillo de HoloLens 2 mediante los botones de brillo del lado izquierdo del dispositivo.
1. Seleccione los botones 1 a 6 para probar al instante cada perfil de color y busque uno que se parezca mejor a los ojos (esto suele significar el perfil que ayuda a que la escena parezca más neutra, con el patrón de escala de grises y los tonos de máscara con el aspecto esperado).

    ![Visualización de la escena de calibración de color](images/color-cal-ui.png)
    
1. Cuando esté satisfecho con el perfil seleccionado, seleccione el botón **Guardar & Salir.**
1. Si prefiere no realizar cambios, seleccione el botón **Cancelar & salir** y los cambios se revertirán.

> [!TIP]
> Estas son algunas sugerencias útiles que debe tener en cuenta al usar la configuración de calibración del color de la pantalla:
> - Puede volver a ejecutar la calibración del color de la pantalla desde Configuración siempre que quiera.
> - Si alguien del dispositivo ha usado previamente la configuración para cambiar los perfiles de color, la fecha y hora del cambio más reciente se reflejará en la página Configuración.
> - Al volver a ejecutar la calibración del color de presentación, se resaltará el perfil de color que se guardó anteriormente y el perfil 0 no aparecerá (ya que el perfil 0 representa el perfil de color original de la pantalla).
> - Si desea revertir al perfil de color original de la pantalla, puede hacerlo desde la página Configuración (consulte cómo restablecer el perfil [de color).](#how-to-reset-color-profile)

##### <a name="how-to-reset-color-profile"></a>Restablecimiento del perfil de color 

Si no está satisfecho con el perfil de color personalizado guardado en el HoloLens 2, puede restaurar el perfil de color original del dispositivo:
1. Inicie la **aplicación Settings** (Configuración) y vaya a System > **Calibration (Calibración del sistema).**
1. En **Display color calibration (Calibración de** color para mostrar), seleccione el botón Reset to default color profile **(Restablecer el perfil de color** predeterminado).
1. Cuando se abra el cuadro de diálogo, seleccione **Reiniciar** si está listo para reiniciar HoloLens 2 y aplicar los cambios.

#### <a name="top-display-color-calibration-known-issues"></a>Principales problemas conocidos de calibración del color de pantalla

- En la página Configuración, la cadena de estado que indica cuándo se cambió por última vez el perfil de color estará des actualizada hasta que vuelva a cargar esa página de Configuración.
    - Solución alternativa: seleccione otra página Configuración y, a continuación, vuelva a seleccionar la página Calibración.

#### <a name="default-app-picker"></a>Selector de aplicaciones predeterminado

Al activar un hipervínculo o abrir un tipo de archivo con más de una aplicación instalada, que lo admite, verá una nueva ventana abierta en la que se le pedirá que seleccione qué aplicación instalada debe controlar el tipo de archivo o vínculo. En esta ventana, también puede elegir que la aplicación seleccionada controle el archivo o el tipo de vínculo "Once" o "Always".

Si elige "Siempre" pero más adelante quiere cambiar qué aplicación controla un tipo de archivo o vínculo determinado, puede restablecer los valores predeterminados guardados en Configuración **> Aplicaciones**. Desplácese hasta la parte inferior  de la página y seleccione el botón Borrar en "Aplicaciones predeterminadas para tipos de archivo" o "Aplicaciones predeterminadas para tipos de vínculo". A diferencia de la configuración similar en equipos de escritorio, no se pueden restablecer los valores predeterminados de tipo de archivo individual.

#### <a name="per-app-volume-control"></a>Control de volumen por aplicación

Ahora, en esta compilación de Windows, los usuarios pueden ajustar manualmente el nivel de volumen de cada aplicación. Esto permite a los usuarios centrarse mejor en las aplicaciones que necesitan o escuchar mejor al usar varias aplicaciones. Por ejemplo, tener que desactivar el volumen de una aplicación mientras se llama a otra persona para obtener asistencia remota en otra.

Para establecer el volumen de una aplicación individual, vaya a Configuración Sonido del sistema y, en Opciones avanzadas de sonido, seleccione Volumen de la aplicación y preferencias  ->    ->   **del dispositivo.**

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Deslizar el dedo para escribir

A algunos clientes les resulta más rápido "escribir" en teclados virtuales si deslizan la forma de la palabra que pretenden escribir y estamos haciendo una vista previa de esta característica para el teclado holográfico. Puede deslizar una palabra a la vez pasando la punta del dedo por el plano del teclado holográfico, deslizando la forma de la palabra y retirando la punta del dedo del plano del teclado. Puede deslizar el dedo para hacer un seguimiento de las palabras sin necesidad de presionar la barra espaciador quitando el dedo del teclado entre palabras. Sabrá que la característica funciona si ve una pista de deslizar el dedo después del movimiento del dedo en el teclado.

Tenga en cuenta que esta característica puede ser difícil de usar y maestra debido a la naturaleza de un teclado holográfico en el que no se siente resistencia contra el dedo (a diferencia de una pantalla de teléfono móvil). 

### <a name="power-menu-from-start"></a>Menú De encendido desde Inicio

Un nuevo menú que permite al usuario cerrar sesión, apagar y reiniciar el dispositivo. Un indicador en el cuadro de pantalla Inicio HoloLens que muestra cuándo está disponible una actualización del sistema.

#### <a name="how-to-use"></a>Cómo se usa

1. Abra el pantalla Inicio HoloLens con el gesto [Iniciar](hololens2-basic-usage.md#start-gesture) o con el mensaje "Ir a Inicio".

2. Observe el icono de puntos suspensivos (...) junto a la imagen de perfil de usuario:

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Seleccione la imagen de perfil de usuario con las manos o el comando de voz "Power".

4. Aparece un menú con las opciones Cerrar sesión, Reiniciar o Apagar el dispositivo:

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Seleccione las opciones de menú para cerrar sesión, reiniciar o apagar HoloLens. Es posible que la opción Cerrar sesión no esté disponible si el dispositivo está configurado para una única cuenta [Microsoft (MSA) o cuenta local.](hololens-identity.md)

6. Cierre el menú tocándose en cualquier otro lugar o menú Inicio con el gesto Iniciar.

#### <a name="update-indicator"></a>Indicador de actualización

Cuando hay una actualización disponible, el icono de puntos suspensivos se enciende para indicar que un reinicio instalará la actualización Las opciones de menú también cambian para reflejar la presencia de la actualización.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Varios usuarios enumerados en la pantalla de inicio de sesión

Anteriormente, en la pantalla Inicio de sesión solo se mostraba el usuario que ha iniciado sesión más recientemente, así como un punto de entrada "Otro usuario". Hemos recibido comentarios de los clientes que no son suficientes si varios usuarios han iniciado sesión en el dispositivo. Todavía tenían que volver a escribir su nombre de usuario, etc.

Introducido en esta compilación de  Windows, al seleccionar Otro usuario que se encuentra a la derecha del campo de entrada del PIN, la pantalla Inicio de sesión mostrará varios usuarios con que han iniciado sesión previamente en el dispositivo. Esto permite a los usuarios seleccionar su perfil de usuario y, a continuación, iniciar sesión con sus credenciales Windows Hello usuario. También se puede agregar un nuevo usuario al dispositivo desde esta página Otros usuarios mediante el **botón Agregar** cuenta.

En el menú Otros usuarios, el botón Otros usuarios mostrará el último usuario que ha iniciado sesión en el dispositivo. Seleccione este botón para volver a la pantalla Inicio de sesión de este usuario.

![Pantalla de inicio de sesión predeterminada](./images/multiusers1.jpg)

<br>

![Pantalla de inicio de sesión de otros usuarios](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Compatibilidad con micrófono externo USB-C

> [!IMPORTANT]
> La conexión de **un micrófono USB no lo establecerá automáticamente como el dispositivo de entrada**. Al conectar un conjunto de cascos USB-C, los usuarios observarán que el audio del casco se redirigirá automáticamente a los cascos, pero el sistema operativo HoloLens da prioridad a la matriz de micrófonos interna por encima de cualquier otro dispositivo de entrada. **Para usar un micrófono USB-C, siga estos pasos.**

Los usuarios pueden seleccionar micrófonos externos conectados a USB-C mediante el panel **Configuración** de sonido. Los micrófonos USB-C se pueden usar para llamar, grabar, etc.

Abra la **aplicación Configuración** y seleccione **Sonido del**  >  **sistema.**

![Configuración de sonido](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Para usar micrófonos externos con **Remote Assist**, los usuarios tendrán que hacer clic en el hipervínculo "Administrar dispositivos de sonido".
>
> A continuación, use la lista desplegable para establecer el micrófono externo como **Predeterminado o** Predeterminado **de comunicaciones.** Elegir Predeterminado **significa** que el micrófono externo se usará en todas partes.
>
> Elegir Comunicaciones **predeterminada** significa que el micrófono externo se usará en Remote Assist y otras aplicaciones de comunicaciones, pero la matriz de micrófonos de HoloLens todavía se puede usar para otras tareas.

![Administración de dispositivos de sonido](images/usbc-mic-2.png)

<br>

![Establecer el valor predeterminado del micrófono](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>¿Qué sucede con la compatibilidad con micrófonos Bluetooth?

Desafortunadamente, los micrófonos Bluetooth todavía no se admiten actualmente en HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Solución de problemas de micrófonos USB-C

Tenga en cuenta que algunos micrófonos USB-C se informan incorrectamente como micrófono *y* como altavoz. Se trata de un problema con el micrófono y no con HoloLens. Al conectar uno de estos micrófonos a HoloLens, es posible que se pierda el sonido. Afortunadamente, hay una corrección sencilla.  

En **Configuración** de sonido del sistema , establezca explícitamente los altavoces integrados (controlador de audio de características  ->    ->   **análogas)** como **el dispositivo predeterminado**. HoloLens debe recordar esta configuración incluso si el micrófono se quita y se vuelve a conectar más adelante.

![Solución de problemas de micrófonos USB-C](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Inicio de sesión automático de visitante para quioscos

Esta nueva característica permite usar el inicio de sesión automático en las cuentas de visitante para los modos de quiosco.

Para una configuración que no es de AAD, para configurar un dispositivo para el inicio de sesión automático del visitante:

1. Cree un paquete de aprovisionamiento que:
    1. Configura las opciones **de runtime/AssignedAccess para** permitir las cuentas de visitante.
    1. Opcionalmente, inscribe el dispositivo en MDM (configuración en tiempo de **ejecución/Área de trabajo/Inscripciones)** para que se pueda administrar más adelante.
    1. No crear una cuenta local
1. [Aplique el paquete de aprovisionamiento](hololens-provisioning.md).

En el caso de una configuración de AAD, los usuarios pueden lograr algo parecido a esto hoy en día sin este cambio. Los dispositivos unidos a AAD configurados para el modo de pantalla completa pueden iniciar sesión en una cuenta de visitante con un solo botón pulsando en la pantalla de inicio de sesión. Una vez que haya iniciado sesión en la cuenta de visitante, el dispositivo no volverá a solicitar el inicio de sesión hasta que el visitante haya iniciado sesión explícitamente desde el menú Inicio o se reinicie el dispositivo.

El inicio de sesión automático del visitante se puede administrar mediante [una directiva OMA-URI](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) personalizada:

- Valor de URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Directiva  | Descripción   | Configurations  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Permite que un visitante inicie sesión automáticamente en un quiosco.   | 1 (Sí), 0 (No, valor predeterminado).  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Uso de las nuevas aplicaciones de Configuración y Edge en los modos de pantalla completa

Al incluir [](hololens-kiosk.md)aplicaciones en quioscos, un administrador de TI suele agregar la aplicación al quiosco, pero con su identificador de modelo de usuario de aplicación (AUMID). Dado que la aplicación Configuración y la aplicación Microsoft Edge se consideran nuevas aplicaciones y son diferentes de las aplicaciones anteriores, los quioscos que usan AUMID para esas aplicaciones tendrán que actualizarse para usar el nuevo AUMID.

Al modificar un quiosco para incluir las nuevas aplicaciones, se recomienda agregar en el nuevo AUMID, así como dejar la antigua. Esto creará una transición sencilla cuando los usuarios actualicen el sistema operativo y no necesitarán recibir nuevas directivas para seguir usando la pantalla completa según lo previsto.

| Aplicación                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Aplicación de configuración anterior       | HolographicSystemSettings_cw5n1h2txyewy! Aplicación            |
| Nueva aplicación de configuración       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! Aplicación |
| Aplicación Microsoft Edge anterior | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| Nueva Microsoft Edge aplicación | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Cambios de comportamiento del modo de pantalla completa para el control de errores

En compilaciones anteriores, si un dispositivo tuviera una configuración de quiosco, que es una combinación de acceso asignado global y acceso asignado a miembros del grupo de AAD, si se genera un error en la determinación de la pertenencia al grupo de AAD, el usuario vería["no](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)se muestra nada en el menú inicio".

A partir de esta versión de Windows, la experiencia de quiosco se reservará a la configuración global de quiosco (si existe) en caso de errores durante el modo de pantalla completa del grupo de AAD.

### <a name="new-settings-uris-for-page-settings-visibility"></a>Nuevos URI de configuración para la visibilidad de la configuración de página

En [Windows Holographic, versión 20H2,](hololens-release-notes.md#windows-holographic-version-20h2) agregamos la directiva [Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir las páginas que se ven en la aplicación Configuración. PageVisibilityList es una directiva que permite a los administradores de TI impedir que determinadas páginas de la aplicación Configuración del sistema sean visibles o accesibles, o bien hacerlo para todas las páginas excepto las especificadas.

Si visita [visibilidad de la configuración de](settings-uri-list.md)página , puede encontrar instrucciones para usar este CSP y la lista de URI disponibles en versiones anteriores.

Vamos a ampliar la lista de uri de configuración disponibles, que los administradores de TI pueden administrar. Algunos de estos URI son para las áreas recién disponibles dentro de la nueva aplicación Configuración. Si usa la directiva Settings/PageVisibilityList, revise la lista siguiente y ajuste las páginas permitidas o bloqueadas según sea necesario.

> [!NOTE]
> **En desuso: ms-settings:network-proxy**
>
> Una página de configuración está en desuso en estas compilaciones más recientes. La antigua **página Network & Internet**  >  **Proxy** ya no está disponible como configuración global. La nueva configuración de proxy por conexión se puede encontrar en Propiedades de Red **&**  >  **Wi-Fi** de Internet o Propiedades de Red  >   & Ethernet de   >    >  **Internet.**

<br>

| Página Configuración                                        | Identificador URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Características > aplicaciones & aplicaciones                               | `ms-settings:appsfeatures`                         |
| Aplicaciones > aplicaciones & características > opciones avanzadas          | `ms-settings:appsfeatures-app`                     |
| Aplicaciones > sin conexión                                  | `ms-settings:maps`                                 |
| Aplicaciones y > sin conexión > descargar mapas                  | `ms-settings:maps-downloadmaps`                    |
| Dispositivos > Mouse                                      | `ms-settings:mouse`                                |
| Dispositivos > USB                                        | `ms-settings:usb`                                  |
| Modo & conexión a Internet > avión                   | `ms-settings:network-airplanemode`                 |
| Privacidad > general                                    | `ms-settings:privacy-general`                      |
| Privacidad > ink & personalización             | `ms-settings:privacy-speechtyping`                 |
| Movimiento de > privacidad                                     | `ms-settings:privacy-motion`                       |
| Bordes de la > privacidad                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Capturas de > privacidad y aplicaciones                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Batería de > sistema                                     | `ms-settings:batterysaver`                         |
| Batería de > sistema                                     | `ms-settings:batterysaver-settings`                |
| System > Sound                                       | `ms-settings:sound`                                |
| System > Sound > App volume and device preferences | `ms-settings:apps-volume`                          |
| System > Sound > Manage sound devices              | `ms-settings:sound-devices`                        |
| System > Storage > Configure Sensor de almacenamiento         | `ms-settings:storagepolicies`                      |
| Hora & idioma > fecha & hora                        | `ms-settings:dateandtime`                          |
| Time & Language > Keyboard                           | `ms-settings:keyboard`                             |
| Idioma & idioma > tiempo                           | `ms-settings:language`                             |
| Idioma & idioma > tiempo                           | `ms-settings:regionlanguage-languageoptions`       |
| Actualización de & seguridad > restablecimiento & recuperación               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>URI actualizados

Anteriormente, los dos URI siguientes no llevarían a un usuario directamente a las páginas indicadas, sino que solo bloqueaban la página de actualizaciones principales. Los siguientes elementos se han actualizado para dirigirse a sus páginas:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Configuración de diagnósticos de reserva mediante la aplicación Configuración

Ahora, en la aplicación Configuración, un usuario puede configurar el comportamiento de [Diagnósticos de reserva.](hololens-diagnostic-logs.md) En la aplicación Configuración, vaya a **la página Solución** de problemas  ->  **de** privacidad para configurar esta opción.

> [!NOTE]
> Si hay una directiva MDM configurada para el dispositivo, el usuario no podrá invalidar ese comportamiento.  

### <a name="share-things-with-nearby-devices"></a>Compartir cosas con dispositivos cercanos

Comparta cosas con dispositivos cercanos Windows 10, incluidos los equipos y otros HoloLens 2 dispositivos. Puede probarlo en Experiencias compartidas del sistema de configuración para compartir archivos o direcciones URL desde  ->    ->   un dispositivo HoloLens a un equipo. Para obtener más información, lea más sobre cómo compartir [cosas con dispositivos cercanos en Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Esta característica se puede administrar a [través de Connectivity/AllowConnectedDevices.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)

### <a name="new-os-diagnostic-traces"></a>Nuevos seguimientos de diagnóstico del sistema operativo

Además de los solucionadores de problemas anteriores dentro de la aplicación Configuración, se ha agregado un nuevo solucionador de problemas con la adición de la nueva aplicación Configuración para las actualizaciones del sistema operativo. Vaya a **Configuración Actualizar** solución de  ->  **problemas &amp;**  >    >  **Windows Update** seguridad y seleccione **Iniciar.** Esto le permite recopilar seguimientos mientras reproduce el problema con las actualizaciones del sistema operativo para ayudar a solucionar mejor los problemas con el equipo de TI o el soporte técnico.

### <a name="delivery-optimization-preview"></a>Optimización de distribución versión preliminar

Con esta actualización de HoloLens, Windows Holographic for Business configuración de optimización de entrega para reducir el consumo de ancho de banda para las descargas de varios dispositivos HoloLens. Puede obtener una descripción más completa de esta funcionalidad junto con la configuración de red recomendada aquí: Optimización de distribución [para Windows 10 actualizaciones.](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)

Las siguientes opciones se habilitan como parte de la superficie de administración y [se pueden configurar desde Intune](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings):

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
- La solución de problemas requerirá diagnósticos en el servidor Caché conectada o la recopilación de un seguimiento en HoloLens en HoloLens mediante la actualización de configuración & solución de problemas de  >    >     >   **Windows Update**.

### <a name="it-admin---update-checklist"></a>Administrador de TI: lista de comprobación de actualización

Esta lista de comprobación le ayudará a conocer los nuevos elementos que se van a agregar en esta actualización de características que pueden afectar a las configuraciones actuales de administración de dispositivos o a las nuevas características que podría empezar a usar.

#### <a name="updates-to-kiosk-mode"></a>Actualizaciones en pantalla completa

✔️ nuevos [**AUMID para nuevas aplicaciones en pantalla completa:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Si anteriormente usaba la aplicación Configuración o Microsoft Edge en un quiosco, hemos reemplazado estas aplicaciones por nuevas aplicaciones que usan un identificador de aplicación diferente. Le recomendamos encarecidamente que lea [a continuación Nuevos AUMID para nuevas aplicaciones en el modo de pantalla](#use-the-new-settings-and-edge-apps-in-kiosk-modes) completa. Esto garantizará que sigue teniendo la aplicación Configuración en el quiosco o que incluye la nueva aplicación Microsoft Edge pantalla. Estos cambios se pueden realizar ahora, implementarse en todos los dispositivos y permitir una transición más fluida en la actualización.

✔️ inicio [**de sesión automático del visitante para quioscos:**](#visitor-auto-logon-for-kiosks) 

Ahora, los visitantes pueden iniciar sesión automáticamente en un quiosco. Este comportamiento está en modo predeterminado, pero se puede administrar y deshabilitar.

✔️ [**se ha mejorado el modo de pantalla completa al entregar**](#kiosk-mode-behavior-changes-for-handling-of-failures):

Si no se determina correctamente la pertenencia a un grupo de AAD del usuario de AAD que ha iniciado sesión, se usa la configuración global de quiosco para el menú Inicio (si está presente). De lo contrario, el usuario se presenta con el menú inicio vacío. Aunque el menú de inicio vacío no es una configuración que se puede establecer directamente, este nuevo control puede ser algo para informar al departamento de soporte técnico si usa quioscos, ya que esto puede aplicarse a las configuraciones o puede que desee realizar nuevos ajustes en las configuraciones de acceso asignadas.

#### <a name="updates-to-page-settings-visibility"></a>Actualizaciones de la visibilidad de la configuración de página

✔️ URI [**de nueva configuración para la visibilidad de la configuración de página**](#new-settings-uris-for-page-settings-visibility)

Si actualmente usa visibilidad [de](settings-uri-list.md) la configuración de página, es posible que desee realizar ajustes en los URI existentes que haya permitido o bloqueado.

#### <a name="updates-for-your-wdac-policy"></a>Actualizaciones de la directiva WDAC
✔️ Si anteriormente estaba bloqueando Microsoft Edge a través de WDAC, querrá actualizar la directiva wdac. Revise lo siguiente y use el código de ejemplo proporcionado.
#### <a name="enable-new-endpoints-for-edge"></a>Habilitación de nuevos puntos de conexión para Edge
✔️ Si tiene una infraestructura que implica la configuración de puntos de conexión de red como proxy o firewall, habilite estos nuevos puntos de conexión para la nueva Microsoft Edge aplicación.

#### <a name="newly-configurable-items"></a>Elementos recién configurables

✔️ configurar [diagnósticos de reserva:](#configuring-fallback-diagnostics-via-settings-app)puede configurar si y quién puede recopilar diagnósticos de reserva.

✔️ compartir[cosas con dispositivos cercanos:](#share-things-with-nearby-devices)puede deshabilitar la nueva característica de uso compartido cercano.

✔️ configuración de directivas para el nuevo [Microsoft Edge:](#configuring-policy-settings-for-the-new-microsoft-edge)revise las configuraciones recién disponibles para Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Nueva herramienta de diagnóstico

✔️[nuevos seguimientos de diagnóstico del sistema operativo:](#new-os-diagnostic-traces)recopile registros relacionados con las actualizaciones del sistema operativo.

### <a name="improvements-and-fixes-in-the-update"></a>Mejoras y correcciones en la actualización:

- [Los diagnósticos sin](hololens-diagnostic-logs.md#offline-diagnostics) conexión también incluirán información adicional del dispositivo para el número de serie y la versión del sistema operativo.
- Corrige un problema en torno a la implementación de aplicaciones de línea de negocio a través de paquetes de aprovisionamiento en tiempo de ejecución.
- Corrige un problema en torno a los informes de estado de instalación de aplicaciones de línea de negocio.
- Corrige un problema en torno a la persistencia de los nuevos paquetes de aplicación en los restablecimientos de dispositivo.
- Corrige un problema que podía provocar que se escriban símbolos incorrectos en Edge para los clientes japoneses.
- Mejora la resistencia de las actualizaciones del sistema operativo en torno a aplicaciones preinstaladas como Edge. 
- Aborda una confiabilidad de actualizaciones que afecta a la instalación de Microsoft Edge. 


## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic, versión 20H2: actualización de mayo de 2021
- Compilación 19041.1146

Mejoras y correcciones en la actualización:
- Esta actualización de calidad mensual no contiene ningún cambio importante; le recomendamos que pruebe nuestra compilación más reciente, Windows Holographic, versión 21H1.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic, versión 1903: actualización de mayo de 2021
- Compilación 18362.1110

Mejoras y correcciones en la actualización:
- Esta actualización de calidad mensual no contiene ningún cambio importante. **Esta compilación ya no recibirá actualizaciones de servicio mensuales.** Le recomendamos que pruebe nuestra compilación más reciente, Windows Holographic, versión 21H1.



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic, versión 20H2: actualización de abril de 2021
- Compilación 19041.1144

Mejoras y correcciones en la actualización:

- Corrige un problema en torno a los informes de estado de instalación de aplicaciones de línea de negocio.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic, versión 1903: actualización de abril de 2021
- Compilación 18362.1108

Mejoras y correcciones en la actualización:

- Soluciona un problema por el que la aplicación Configuración se bloquea al intentar cambiar una contraseña para una cuenta local.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, versión 20H2: actualización de marzo de 2021
- Compilación 19041.1140

Mejoras y correcciones en la actualización:

- Los clientes que usan AdvancedPhotoCapture o LowObjPhotoCapture para capturar fotos con HoloLens 2 ahora pueden recuperar la posición de la cámara hasta 3 segundos después de capturar la foto.
- Corrección de una pérdida de memoria en Portal de dispositivos Service, el problema provocó un aumento del uso de memoria por parte del servicio que provocó que otras aplicaciones no asignaran memoria.
- Se ha corregido un problema por el que los usuarios inscritos en el lanzamiento por fases no pueden iniciar sesión en el dispositivo.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, versión 1903: actualización de marzo de 2021
- Compilación 18362.1102

Mejoras y correcciones en la actualización:

- Corrección de una pérdida de memoria en Portal de dispositivos Service, el problema provocó un aumento del uso de memoria por parte del servicio que provocó que otras aplicaciones no asignaran memoria.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, versión 20H2: actualización de febrero de 2021
- Compilación 19041.1136

Mejoras y correcciones en la actualización:

- Corrige un problema en torno a la configuración inicial del dispositivo y las actualizaciones de la aplicación de almacenamiento.
- Soluciona un problema en torno a las actualizaciones y los vuelos de versiones posteriores de HoloLens.
- Se han quitado los certificados preinstalados no usados del almacén raíz de eSIM de los dispositivos HoloLens.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, versión 1903: actualización de febrero de 2021
- Compilación 18362.1098

Esta actualización de calidad mensual no contiene ningún cambio importante; le recomendamos que pruebe nuestras compilaciones más recientes para Windows Holographic, versión 2004.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, versión 20H2: actualización de enero de 2021
- Compilación 19041.1134

Mejoras y correcciones en la actualización:

- Rendimiento mejorado durante el inicio, la reanudación y el cambio de usuario cuando hay muchos usuarios en el dispositivo.
- Se ha agregado compatibilidad con arm32 para el [modo de investigación](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode).

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, versión 1903: actualización de enero de 2021
- Compilación 18362.1091

Esta actualización de calidad mensual no contiene ningún cambio importante; le recomendamos que pruebe nuestras compilaciones más recientes para Windows Holographic, versión 2004.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, versión 20H2: actualización de diciembre de 2020
- Compilación 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalación de aplicaciones en HoloLens 2 a través de Instalador de aplicación

Vamos a **agregar una nueva funcionalidad (Instalador de aplicación)** para permitirle instalar aplicaciones más fácilmente en los dispositivos HoloLens 2 dispositivos. La característica estará en **modo predeterminado para dispositivos no administrados.** Para evitar interrupciones en las empresas, el instalador de aplicaciones no **estará disponible para dispositivos administrados** en este momento.  

Un dispositivo se considera "administrado" si **se** cumple alguna de las siguientes condiciones:
- MDM [inscrito](hololens-enroll-mdm.md)
- Configurado con el [paquete de aprovisionamiento](hololens-provisioning.md)
- Identidad [de usuario](hololens-identity.md) Azure AD

Ahora puede instalar aplicaciones sin necesidad de habilitar el modo de desarrollador ni usar Portal de dispositivos.  Simplemente descargue (a través de USB o a través de Edge) el paquete de Appx en el dispositivo y vaya al paquete de Appx en el Explorador de archivos para que se le pida que arranque la instalación.  Como alternativa, [inicie una instalación desde una página web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  Al igual que las aplicaciones que se instalan desde Microsoft Store o la instalación local mediante la [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) funcionalidad de [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) implementación de aplicaciones LOB de MDM, las aplicaciones deben estar firmadas digitalmente con la herramienta de firma y el certificado usado para firmar debe ser de confianza para el dispositivo HoloLens antes de que se pueda implementar la aplicación.

**Instrucciones de instalación de la aplicación.**

1.  Asegúrese de que el dispositivo no se considera administrado.
1.  Asegúrese de que el HoloLens 2 está encendido y conectado al equipo.
1.  Asegúrese de que ha iniciado sesión en el HoloLens 2 dispositivo.
1.  En el equipo, vaya a la aplicación personalizada y copie yourapp.appxbundle en yourdevicename\Internal Storage\Downloads.   Una vez que haya terminado de copiar el archivo, puede desconectar el dispositivo.
1.  En el HoloLens 2, abra el menú Inicio, seleccione Todas las aplicaciones e inicie Explorador de archivos aplicación.
1.  Vaya a la carpeta Descargas. En el panel izquierdo de la aplicación, seleccione Este dispositivo en primer lugar y, a continuación, vaya a Descargas.
1.  Seleccione el archivo yourapp.appxbundle.
1.  La Instalador de aplicación se iniciará. Seleccione el botón Instalar para instalar la aplicación.
La aplicación instalada se iniciará automáticamente al finalizar la instalación.

Puede encontrar aplicaciones de ejemplo en GitHub de ejemplos [universales de Windows](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) para probar este flujo.

Obtenga información sobre el proceso completo de [instalación de aplicaciones en HoloLens 2 con el Instalador de aplicación](app-deploy-app-installer.md).  

![Instalación de ejemplos de MRTK mediante Instalador de aplicación](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Mejoras y correcciones en la actualización:

- El seguimiento de manos ahora mantiene el seguimiento en muchos casos nuevos en los que se habría perdido la mano anteriormente.  En algunos de estos nuevos casos, solo la posición de la mano sigue actualciendo en función de la mano real del usuario, mientras que las demás uniones se deducen en función de una posición anterior.  Este cambio ayuda a mejorar la coherencia del seguimiento en movimientos como las abofetas, el lanzamiento, la desarroba y el abarrote.  También ayuda en casos en los que la mano está cerca de una superficie o que contiene un objeto.  Cuando se inferan las [](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) uniones de mano, el valor de precisión por conjunta se establecerá en "Aproximado" en lugar de "Alto".
- Se ha corregido un problema por el que el restablecimiento del PIN Azure AD las cuentas mostraría el error "Se ha producido un error.
- Los usuarios deben ver mucho menos bloqueos de OOBE posteriores al arranque al iniciar ET, Iris desde la aplicación de configuración, nuevo usuario o notificación del sistema.
- Los usuarios deben tener una zona horaria correcta que salga de la OOBE.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, versión 1903: actualización de diciembre de 2020
- Compilación 18362.1088

Esta actualización de calidad mensual no contiene ningún cambio importante; le recomendamos que pruebe la versión más reciente de Windows Holographic, la versión 20H2 - Actualización de diciembre de 2020 y la nueva característica Instalador de aplicación agregada en la compilación.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, versión 20H2
- Compilación 19041.1128

Windows Holographic, versión 20H2 ya está disponible y ofrece un gran conjunto de nuevas características para HoloLens 2 usuarios y profesionales de IT. Desde el posicionamiento automático de los ojos hasta el Administrador de certificados en Configuración, hasta la funcionalidad mejorada del modo quiosco y las nuevas funcionalidades de configuración de Autopilot. Esta nueva actualización permite a los equipos de IT tomar un control más granular de la configuración y administración de dispositivos HoloLens, y ofrece a los usuarios experiencias holográficas incluso más fluidas. 

Esta versión más reciente es una actualización mensual a la versión 2004, pero esta vez se incluyen nuevas características. El número de compilación principal seguirá siendo el mismo y Windows Update indicará una versión mensual de la versión 2004 (compilación 19041). Puede ver el número de compilación en la pantalla Configuración > Acerca de para confirmar que se encuentra en la última compilación disponible 19041.1128+. Para actualizar a la versión más reciente, abra la aplicación Configuración, vaya a Actualizar & Seguridad y pulse Buscar actualizaciones. Para obtener más información sobre cómo administrar las actualizaciones de HoloLens, visite [esta página](https://docs.microsoft.com/hololens/hololens-updates).

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Novedades de Windows Holographic, versión 20H2  

| Característica                                              | Descripción                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Compatibilidad con la posición automática de los ojos](hololens-release-notes.md#auto-eye-position-support) | Calcula activamente las posiciones de los ojos sin que los usuarios pasen por la calibración de Eye Tracking.   |
| [Administrador de certificados](hololens-release-notes.md#certificate-manager)   | Permite que los nuevos métodos más sencillos instalen y quiten certificados de la aplicación Configuración.     |
| [Aprovisionamiento de inicio automático desde USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | El aprovisionamiento de paquetes en unidades USB solicita automáticamente la página de aprovisionamiento en OOBE.                                                         |
| [Confirmación automática de paquetes de aprovisionamiento en OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Los paquetes de aprovisionamiento se aplican automáticamente durante la OOBE desde la página de aprovisionamiento.                                                         |
| [Aprovisionamiento automático sin usar la interfaz de usuario](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Cómo combinar el inicio automático de aprovisionamiento y la confirmación automática juntos. |
| [Uso de Autopilot con Wi-Fi conexión](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Use Autopilot desde el dispositivo Wi-Fi sin necesidad de adaptador Ethernet. |
| [CSP de Tenantlockdown y Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Una vez aplicada la inscripción de inquilinos y la directiva, el dispositivo solo se puede inscribir en ese inquilino cada vez que se restablezca o se vuelva a parpadear el dispositivo. |
| [Acceso asignado global](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Nuevo método de configuración para el modo de pantalla completa de varias aplicaciones que aplica la pantalla completa en el nivel del sistema, lo que lo hace aplicable a todos.                  |
| [Inicio automático de una aplicación en quiosco de varias aplicaciones](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Establece una aplicación que se iniciará automáticamente al iniciar sesión en un modo de pantalla completa de varias aplicaciones.                                                        |
| [Cambios de comportamiento del modo de pantalla completa para el control de errores](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | El error del modo de pantalla completa ahora tiene una reserva restrictiva.                                                                                                |
| [Directivas de HoloLens](hololens-release-notes.md#hololens-policies)                                    | Nuevas directivas para HoloLens.     |
| [Pertenencia a Azure AD grupo de almacenamiento en caché para quiosco sin conexión](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | La nueva directiva permite a los usuarios usar la memoria caché de pertenencia a grupos para usar el modo quiosco sin conexión durante un número establecido de días.                                        |
| [Nuevas directivas de restricción de dispositivos para HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Directivas de administración de dispositivos habilitadas recientemente para HoloLens 2.                                                                                |
| [Nuevas directivas de energía para HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Directivas recién admitidas para la configuración de tiempo de espera de energía.  |
| [Actualizar directivas](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Directivas recién habilitadas que permiten el control de las actualizaciones.           |
| [Visibilidad de la página Configuración habilitada para HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Directiva para elegir qué páginas se ven en la aplicación Configuración.             |
| [Modo de investigación](hololens-release-notes.md#research-mode) | Uso del modo de investigación en HoloLens 2. |
| [Longitud de grabación aumentada](hololens-release-notes.md#recording-length-increased) | Las grabaciones de MRC ya no se han recortado a 5 minutos. |
| [Mejoras y correcciones en la actualización](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Correcciones adicionales en la actualización.   |

### <a name="auto-eye-position-support"></a>Compatibilidad con la posición automática de los ojos

En HoloLens 2, las posiciones de los ojos permiten un posicionamiento preciso del holograma, una experiencia de visualización cómoda y una calidad de visualización mejorada. Las posiciones de los ojos se calculan internamente como parte del cálculo del seguimiento de los ojos. Sin embargo, esto requiere que cada usuario pase por la calibración del seguimiento de los ojos, incluso cuando la experiencia no requiera la entrada de mirada con los ojos.

**La posición automática de los ojos (AEP)** permite estos escenarios con una manera sin interacción de calcular las posiciones de los ojos para el usuario. La posición del ojo automático comienza a funcionar en segundo plano automáticamente desde el momento en que el usuario coloca el dispositivo. Si el usuario no tiene una calibración de seguimiento de los ojos anterior, la posición del ojo automático comenzará a proporcionar las posiciones de los ojos del usuario al sistema de visualización después de un tiempo de procesamiento de 20 a 30 segundos. Los datos de usuario no se conservan en el dispositivo y, por lo tanto, este proceso se repite si el usuario despeda y vuelve a activar el dispositivo o si el dispositivo se reinicia o se reactiva de la suspensión.

Hay algunos cambios de comportamiento del sistema con la característica Posición automática de los ojos cuando un usuario sin problemas coloca en el dispositivo. En este contexto, un usuario sin problemas hace referencia a alguien que no ha pasado por el proceso de calibración del seguimiento de los ojos en el dispositivo anteriormente.

| Aplicación activa | Comportamiento anterior | Comportamiento de Windows Holographic, versión 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Aplicación habilitada para no mirada o Shell holográfico |Se muestra el cuadro de diálogo del símbolo del sistema de calibración de seguimiento de los ojos. | No se muestra ningún mensaje. |
| Aplicación habilitada para mirada | Se muestra el cuadro de diálogo del símbolo del sistema de calibración de seguimiento de los ojos. | El símbolo del sistema de calibración de seguimiento de los ojos solo se muestra cuando la aplicación accede a la secuencia de mirada con los ojos. |

Si el usuario pasa de una aplicación habilitada para no mirada a una que accede a los datos de mirada, se mostrará el símbolo del sistema de calibración. 

El resto del comportamiento del sistema será similar a cuando el usuario actual no tenga una calibración de seguimiento de los ojos activa. Por ejemplo, el gesto De inicio con una mano no se habilitará. No habrá ningún cambio en la configuración rápida para la configuración inicial.

En el caso de las experiencias que requieren datos de mirada con los ojos o un posicionamiento de holograma muy preciso, se recomienda que los usuarios sin problemas ejecuten la calibración del seguimiento ocular. Es accesible desde el símbolo del sistema de calibración de seguimiento ocular o iniciando la aplicación Configuración desde el menú inicio y seleccionando System **> Calibration > Eye Calibration > Run eye calibration**(Calibración del sistema > calibración de los ojos > Ejecutar calibración de los ojos).

Esta información se puede encontrar más adelante con [otra información de calibración](hololens-calibration.md#auto-eye-position-support). 

### <a name="certificate-manager"></a>Administrador de certificados

- Se han mejorado las herramientas de auditoría, diagnóstico y validación para la seguridad y el cumplimiento de dispositivos mediante el nuevo Administrador de certificados. Esta funcionalidad le permitirá implementar, solucionar problemas y validar los certificados a escala en entornos comerciales.

En Windows Holographic versión 20H2, vamos a agregar un administrador de certificados en la aplicación HoloLens 2 configuración. Vaya a **Configuración > actualizar & seguridad > certificados**. Esta característica proporciona una manera sencilla y fácil de ver, instalar y quitar certificados en el dispositivo. Con el nuevo Administrador de certificados, los administradores y los usuarios ahora tienen herramientas mejoradas de auditoría, diagnóstico y validación para garantizar que los dispositivos sigan siendo seguros y compatibles. 

-   **Auditoría:** Capacidad para validar que un certificado está implementado correctamente o para confirmar que se quitó correctamente. 
-   **Diagnóstico:** Cuando surgen problemas, validar que existen los certificados adecuados en el dispositivo ahorra tiempo y ayuda a solucionar problemas. 
-   **Validación:** Comprobar que un certificado sirve para el propósito previsto y es funcional, puede ahorrar mucho tiempo, especialmente en entornos comerciales antes de implementar certificados a mayor escala.

Para buscar rápidamente un certificado específico en la lista, hay opciones para ordenar por nombre, almacén o fecha de expiración. Los usuarios también pueden buscar directamente un certificado. Para ver las propiedades de certificado individuales, seleccione el certificado y haga clic en **Información**. 

La instalación de certificados admite actualmente archivos .cer y .crt. Los propietarios de dispositivos pueden instalar certificados en la máquina local y el usuario actual.  todos los demás usuarios solo pueden instalar en el usuario actual. Los usuarios solo pueden quitar los certificados instalados directamente desde la interfaz de usuario de configuración. Si un certificado se ha instalado a través de otros medios, también debe quitarse mediante el mismo mecanismo.

#### <a name="to-install-a-certificate"></a>Para instalar un certificado: 

1.  Conecte el HoloLens 2 a un equipo.
1.  Coloque el archivo de certificado que desea instalar en una ubicación de la HoloLens 2.
1.  Vaya a **Configuración App > Update & Security > Certificates** y seleccione Install a certificate (Instalar un certificado).
1.  Haga **clic en Importar** archivo y vaya a la ubicación en la que guardó el certificado.
1.  Seleccione **Store Location (Ubicación del almacén).**
1.  Seleccione **Almacén de certificados.**
1.  Haga clic en **Instalar**.

El certificado debe estar ahora instalado en el dispositivo.

#### <a name="to-remove-a-certificate"></a>Para quitar un certificado: 
1. Vaya a **Configuración App > Update and Security > Certificates**.
1. Busque el certificado por nombre en el cuadro de búsqueda.
1. Seleccione el certificado.
1. Haga clic **en Quitar.**
1. Seleccione **Sí** cuando se pida confirmación.

![Visor de certificados en la aplicación Configuración](images/certificate-viewer-device.jpg)

![Imagen que muestra cómo usar la interfaz de usuario de certificado para instalar un certificado](images/certificate-device-install.jpg)

Esta información se puede encontrar más adelante [en una nueva página del Administrador de certificados](certificate-manager.md).

### <a name="auto-launch-provisioning-from-usb"></a>Aprovisionamiento de inicio automático desde USB

- Procesos automatizados que permiten una menor interacción del usuario, cuando se usan unidades USB con paquetes de aprovisionamiento durante la configuración automática.

Antes de esta versión, los usuarios tenían que iniciar la pantalla de aprovisionamiento manualmente durante la operación de aprovisionamiento mediante una combinación de botones. Ahora los usuarios pueden omitir la combinación de botones mediante un paquete de aprovisionamiento en una unidad de almacenamiento USB. 

1. Conecte la unidad USB con el paquete de aprovisionamiento durante el primer momento interactuable de OOBE.
1. Cuando el dispositivo esté listo para aprovisionarse, se abrirá automáticamente el símbolo del sistema con la página de aprovisionamiento. 

Nota: Si una unidad USB se deja conectada mientras el dispositivo arranca, OOBE enumerará el dispositivo de almacenamiento USB existente, así como observará si hay otras adicionales conectadas.

Para obtener más información sobre cómo aplicar paquetes de aprovisionamiento durante la configuración general, visite la [documentación de aprovisionamiento de HoloLens.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Puede encontrar información adicional [sobre el aprovisionamiento de inicio](hololens-provisioning.md#auto-launch-provisioning-from-usb) automático desde un USB en la documentación de aprovisionamiento de HoloLens.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Confirmación automática de paquetes de aprovisionamiento en OOBE
- Proceso automatizado que permite una menor interacción del usuario, cuando se muestra la página Paquete de aprovisionamiento, se aplicarán automáticamente todos los paquetes enumerados.

Cuando se muestra la pantalla principal de aprovisionamiento, la OOBE se cuenta como un recuento de 10 segundos antes de empezar a aplicar automáticamente todos los paquetes de aprovisionamiento. Los usuarios todavía [pueden confirmar o cancelar en](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) estos 10 segundos después de comprobar los paquetes que esperaban.

### <a name="automatic-provisioning-without-using-ui"></a>Aprovisionamiento automático sin usar la interfaz de usuario
- Procesos automáticos combinados para interacciones reducidas de dispositivos para el aprovisionamiento. 

Al combinar el inicio automático del aprovisionamiento desde dispositivos USB y la confirmación automática de los paquetes de aprovisionamiento, un usuario puede aprovisionar dispositivos HoloLens 2 automáticamente sin usar la interfaz de usuario del dispositivo ni siquiera llevar el dispositivo. Puede seguir usando la misma unidad USB y el mismo paquete de aprovisionamiento para varios dispositivos. Esto es útil para implementar varios dispositivos a la vez en la misma área. 

1. [Cree un paquete de aprovisionamiento](hololens-provisioning.md) mediante el [Diseñador de configuración de Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Copie el paquete en una unidad de almacenamiento USB.
1. [Flash your HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) to [19041.1361 or newer build](https://aka.ms/hololens2previewdownload). 
1. Cuando [Advanced Recovery Companion haya](https://www.microsoft.com/store/productId/9P74Z35SFRS8) terminado de parpadear el dispositivo, desconecte el cable USB-C. 
1. Conecte la unidad USB al dispositivo.
1. Cuando el HoloLens 2 arranque en OOBE, detectará automáticamente el paquete de aprovisionamiento en la unidad USB e iniciará la página de aprovisionamiento.
1. Después de 10 segundos, el dispositivo aplicará automáticamente el paquete de aprovisionamiento. 

El dispositivo ya está configurado y mostrará [la pantalla Aprovisionamiento correcto](hololens-provisioning.md#automatic-provisioning-without-using-ui).

### <a name="using-autopilot-with-wi-fi-connection"></a>Uso de Autopilot con Wi-Fi conexión
- Se ha quitado la necesidad de adaptadores USB-C a Ethernet, lo que reduce las necesidades de hardware, ya que permite que Autopilot funcione en Wi-Fi dispositivos conectados.

Ahora, durante la OOBE, una vez que se conecte HoloLens 2 con Wi-Fi, OOBE buscará un perfil de Autopilot para el dispositivo. Si se encuentra uno, se usará para completar el resto del flujo de inscripción y unión de AAD. En otras palabras, el uso de ethernet a USB-C o el adaptador de Wi-Fi a USB-C ya no es un requisito, pero siguen funcionando si se proporcionan al principio de OOBE. Obtenga más información [sobre Autopilot para HoloLens 2 dispositivos](hololens2-autopilot.md).

### <a name="tenantlockdown-csp-and-autopilot"></a>CSP de Tenantlockdown y Autopilot
- Mantiene los dispositivos en el inquilino de la organización bloqueándolos en el inquilino incluso a través del restablecimiento o el reflash del dispositivo. Con mayor seguridad al no permitir la creación de cuentas en mediante el aprovisionamiento. 

HoloLens 2 dispositivos ahora admiten csp de TenantLockdown a partir de la versión [20H2 de Windows Holographic.](hololens-release-notes.md#windows-holographic-version-20h2) 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP permite HoloLens 2 a la inscripción de MDM solo con Autopilot. Una vez que el nodo RequireNetworkInOOBE del CSP de TenantLockdown está establecido en un valor true o false (establecido inicialmente) en HoloLens 2, ese valor permanece en el dispositivo a pesar de la re flashing, las actualizaciones del sistema operativo, etc. 

Una vez que el nodo RequireNetworkInOOBE de los CSP de TenantLockdown está establecido en true en HoloLens 2, OOBE espera indefinidamente a que el perfil de Autopilot se descargue y aplique correctamente, después de la conectividad de red. 

Una vez que el nodo RequireNetworkInOOBE de los CSP de TenantLockdown está establecido en true en HoloLens 2, las siguientes operaciones no se pueden realizar en la OOBE: 
- Creación de un usuario local mediante el aprovisionamiento en tiempo de ejecución 
- Realización de Azure AD operación de combinación mediante el aprovisionamiento en tiempo de ejecución 
- Selección de quién es el propietario del dispositivo en la experiencia de OOBE 

#### <a name="how-to-set-this-using-intune"></a>¿Cómo se establece esto mediante Intune? 
1. Cree un perfil de configuración de dispositivo OMA URI personalizado y especifique true para el nodo RequireNetworkInOOBE como se muestra a continuación.
El valor de OMA-URI debe ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Establecimiento del bloqueo de tenso mediante OMA-URI](images/hololens-tenant-lockdown.png)

1. Cree un grupo y asigne el perfil de configuración de dispositivo a ese grupo de dispositivos. 

1. Haga que el HoloLens 2 miembro del dispositivo del grupo creado en el paso anterior y desencadene la sincronización.  

Compruebe en el portal de Intune que la configuración del dispositivo se ha aplicado correctamente. Una vez que esta configuración del dispositivo se aplica correctamente en HoloLens 2 dispositivo, los efectos de TenantLockdown estarán activos.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>¿Cómo se desconjunte RequireNetworkInOOBE de TenantLockdown HoloLens 2 mediante Intune? 
1. Quite la HoloLens 2 del grupo de dispositivos al que se asignó anteriormente la configuración de dispositivos creada anteriormente. 

1. Cree un perfil de configuración de dispositivo basado en URI de OMA personalizado y especifique false para RequireNetworkInOOBE, como se muestra a continuación. El valor de OMA-URI debe ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla de la configuración de RequireNetworkInOOBE en false mediante OMA URI en Intune](images/hololens-tenant-lockdown-false.png)

1. Cree un grupo y asigne el perfil de configuración de dispositivo a ese grupo de dispositivos. 

1. Haga que el HoloLens 2 miembro del dispositivo del grupo creado en el paso anterior y desencadene la sincronización.

Compruebe en el portal de Intune que la configuración del dispositivo se ha aplicado correctamente. Una vez que esta configuración del dispositivo se aplique correctamente en HoloLens 2 dispositivo, los efectos de TenantLockdown estarán inactivos. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>¿Qué ocurriría durante la OOBE si el perfil de Autopilot no se ha desasignado en HoloLens después de que TenantLockdown se estableció en true? 
OOBE esperará indefinidamente a que se descargue el perfil de Autopilot y se mostrará el siguiente cuadro de diálogo. Para quitar los efectos de TenantLockdown, el dispositivo debe inscribirse primero con su inquilino original solo con Autopilot y RequireNetworkInOOBE debe quitarse como se describe en el paso anterior antes de que se quiten las restricciones introducidas por el CSP de TenantLockdown. 

![Vista en el dispositivo para cuando se aplica la directiva en el dispositivo.](images/hololens-autopilot-lockdown.png)

Esta información se puede encontrar junto con el resto de Autopilot en [CSP de Tenantlockdown y Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot).

### <a name="global-assigned-access--kiosk-mode"></a>Acceso asignado global: modo de pantalla completa
- Administración de identidades reducida para Quiosco, al habilitar el nuevo método de quiosco que aplica el modo de quiosco en el nivel del sistema.

Esta nueva característica permite a un administrador de TI configurar un dispositivo HoloLens 2 para el modo de pantalla completa de varias aplicaciones, que es aplicable en el nivel del sistema, no tiene afinidad con ninguna identidad en el sistema y se aplica a todos los usuarios que inician sesión en el dispositivo. Obtenga información detallada sobre esta nueva característica en el quiosco de acceso [asignado global de HoloLens.](hololens-global-assigned-access-kiosk.md)

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Inicio automático de una aplicación en pantalla completa de varias aplicaciones 
- Experiencia centrada con el inicio automático de aplicaciones, lo que aumenta aún más la interfaz de usuario y las selecciones de aplicaciones elegidas para las experiencias de pantalla completa.

Solo se aplica al modo de pantalla completa de varias aplicaciones y solo se puede designar una aplicación para el inicio automático mediante el atributo resaltado a continuación en Configuración de acceso asignado. 

La aplicación se inicia automáticamente cuando el usuario inicia sesión. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Cambios de comportamiento del modo de pantalla completa para el control de errores
- Modo de quiosco más seguro mediante la eliminación de las aplicaciones disponibles en los errores de pantalla completa. 

Anteriormente, al encontrar errores al aplicar el modo de pantalla completa, HoloLens solía mostrar todas las aplicaciones en el menú inicio. Ahora, en Windows Holographic versión 20H2 en caso de errores, no se mostrará ninguna aplicación en el menú inicio como se indica a continuación: 

![Imagen de lo que ahora se ve en pantalla completa cuando se produce un error.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>Directivas de HoloLens
- Opciones de administración de dispositivos específicamente para HoloLens creadas para administrar el dispositivo. 

Se han creado nuevas directivas de realidad mixta para HoloLens 2 dispositivos en Windows Holographic versión 20H2. Entre las nuevas opciones controlables se incluyen: establecer el brillo, establecer el volumen, deshabilitar la grabación de audio en capturas de realidad mixta, establecer cuándo se pueden recopilar diagnósticos y la caché de pertenencia a grupos de AAD.  

| Nueva directiva de HoloLens                                | Descripción                                                                               | Notas                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Permite deshabilitar los botones de brillo para que al presionarlo no cambie el brillo.       | 1 Sí, 0 No (valor predeterminado)                                                |
| MixedReality\VolumeButtonDisabled                  | Permite deshabilitar los botones de volumen para que al presionarlo no cambie el volumen.               | 1 Sí, 0 No (valor predeterminado)                                                |
| MixedReality\MicrophoneDisabled                    | Deshabilita el micrófono para que no sea posible grabar audio en HoloLens 2.                      | 1 Sí, 0 No (valor predeterminado)                                                |
| MixedReality\FallbackDiagnostics                   | Controla el comportamiento de cuando se pueden recopilar registros de diagnóstico.                               | 0 Deshabilitado, 1 Habilitado para propietarios de dispositivos, 2 Habilitado para todos (valor predeterminado) |
| MixedReality\HeadTrackingMode                      | Reservado para uso futuro.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Controla cuántos días se Azure AD caché de pertenencia a grupos para la pantalla completa que tiene como destino Azure AD grupos. | Véase a continuación.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Pertenencia a Azure AD grupo de almacenamiento en caché para quiosco sin conexión
- Se ha habilitado quioscos sin conexión que se usarán con grupos de AAD durante un máximo de 60 días.

Esta directiva controla durante cuántos días, Azure AD caché de pertenencia a grupos se puede usar para las configuraciones de acceso asignado que tienen como destino Azure AD grupos para el usuario que ha iniciado sesión. Una vez que este valor de directiva se establece en un valor mayor que 0, solo se usa la memoria caché; de lo contrario, no.  

Nombre: valor de URI AADGroupMembershipCacheValidityInDays: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Mín. - 0 días  
Máximo: 60 días 

Pasos para usar esta directiva correctamente: 
1. Cree un perfil de configuración de dispositivo para pantalla completa Azure AD grupos y asígnelo a dispositivos HoloLens. 
1. Cree una configuración de dispositivo personalizada basada en uri de OMA que establece este valor de directiva en el número deseado de días (> 0) y asígnelo a dispositivos HoloLens. 
    1. El valor uri debe especificarse en el cuadro de texto OMA-URI como ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. El valor puede estar entre mínimo y máximo permitido.
1. Inscriba dispositivos HoloLens y compruebe que ambas configuraciones se aplican al dispositivo. 
1. Deje Azure AD inicio de sesión del usuario 1 cuando Internet esté disponible, una vez que el usuario inicie sesión y Azure AD grupo se confirme correctamente, se creará la memoria caché. 
1. Ahora Azure AD usuario 1 puede desconectar HoloLens y usarlo para el modo de pantalla completa siempre que el valor de directiva permita X número de días. 
1. Los pasos 4 y 5 se pueden repetir para cualquier otro usuario de Azure AD N. El punto clave aquí es que cualquier usuario de Azure AD debe iniciar sesión en el dispositivo mediante Internet, por lo que al menos una vez podemos determinar que son miembros de un grupo Azure AD al que está destinada la configuración de quiosco. 
 
> [!NOTE]
> Hasta que se realice el paso 4 para Azure AD usuario experimentará un comportamiento de error mencionado en entornos "desconectados". 

### <a name="new-device-restriction-policies-for-hololens-2"></a>Nuevas directivas de restricción de dispositivos para HoloLens 2
- Permite a los usuarios administrar directivas de administración de dispositivos específicas, como bloquear la adición o eliminación de paquetes de aprovisionamiento.

Directivas recién habilitadas que permiten más opciones de administración de HoloLens 2 dispositivos. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Estas dos nuevas políticas para AllowAddProvisioningPackage y AllowRemoveProvisioningPackage se agregan a nuestras [restricciones de dispositivos comunes.](hololens-common-device-restrictions.md)

> [!NOTE]
> Con respecto a [RemoteLock,](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)HoloLens solo admitirá la configuración ./Vendor/MSFT/RemoteLock/Lock. No se admiten las configuraciones que se tratan con el PIN, como el restablecimiento y la recuperación.

### <a name="new-power-policies-for-hololens-2"></a>Nuevas directivas de energía para HoloLens 2
- Más opciones para cuando HoloLens se bloquea o se bloquea a través de directivas de energía. 

Estas directivas recién agregadas permiten a los administradores controlar los estados de energía, como el tiempo de espera de inactividad. Para obtener más información sobre cada directiva individual, haga clic en el vínculo de esa directiva.

|     Vínculo de documentación de directiva                |     Notas                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Valor de ejemplo que se usará en el Diseñador de configuración de Windows, es decir,  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Valor de ejemplo que se usará en el Diseñador de configuración de Windows, es decir,  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Valor de ejemplo que se usará en el Diseñador de configuración de Windows, es decir, 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Valor de ejemplo que se usará en el Diseñador de configuración de Windows, es decir, 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Valor de ejemplo que se usará en el Diseñador de configuración de Windows, es decir,   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Valor de ejemplo que se usará en el Diseñador de configuración de Windows, es decir,  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Estas dos nuevas políticas para DisplayOffTimeoutOnBattery y DisplayOffTimeoutPluggedIn se agregan a nuestras [restricciones de dispositivos comunes.](hololens-common-device-restrictions.md)

> [!NOTE]
> Para obtener una experiencia coherente HoloLens 2, asegúrese de que los valores de DisplayOffTimeoutOnBattery y StandbyTimeoutOnBattery se establecen como el mismo valor. Lo mismo se aplica a DisplayOffTimeoutPluggedIn y StandbyTimeoutPluggedIn. Consulte [Visualización, suspensión e hibernación de temporizadores inactivos](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) para obtener más detalles sobre el modo de espera moderno.

### <a name="newly-enabled-update-policies-for-hololens"></a>Directivas de actualización recién habilitadas para HoloLens
- Más opciones para cuando se instalan actualizaciones o deshabilita el botón Pausar actualizaciones para garantizar las actualizaciones.

Estas directivas de actualización ahora están habilitadas en HoloLens 2 dispositivos:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Los detalles completos sobre estas directivas de actualización y cómo usarlas para dispositivos HoloLens se pueden leer aquí en Administración [de actualizaciones de HoloLens.](hololens-updates.md)

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Visibilidad de la página Configuración habilitada para HoloLens 2
- Mayor control de la interfaz de usuario en la aplicación configuración, que puede confundirse para mostrar una selección limitada de páginas.

Ahora hemos habilitado una directiva que permite a los administradores de TI impedir que determinadas páginas de la aplicación Configuración del sistema sean visibles o accesibles, o bien hacerlo para todas las páginas excepto las especificadas. Para obtener información sobre cómo personalizar completamente esta característica, haga clic en el vínculo siguiente.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Para saber qué configuración de página puede personalizar en HoloLens 2, visite nuestra página de [URI de configuración](settings-uri-list.md). 
 
![Captura de pantalla de las horas activas que se modifican en la aplicación Configuración](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Modo de investigación
Mientras está en modo de investigación, el HoloLens 2 se convierte en una herramienta de herramientas para la investigación de computer vision. En comparación con las ediciones anteriores, el modo de investigación HoloLens 2 tiene las siguientes ventajas:
-   Además de los sensores expuestos en el modo de investigación de HoloLens (1ª generación), ahora proporcionamos acceso al sensor IMU, incluido un acelerómetro, un giroscopio y un magnetómetro.
-   HoloLens 2 proporciona nuevas funcionalidades que se pueden usar junto con el modo de investigación. En concreto, el acceso a las API de seguimiento de manos y seguimiento ocular articuladas que pueden ofrecer un conjunto más completo de experimentos.

Los investigadores ahora tienen la opción de habilitar el modo de investigación en sus dispositivos HoloLens para acceder a todos estos flujos de sensores de imagen sin procesar de cara externa. El modo de investigación HoloLens 2 también proporciona acceso a las lecturas de acelerómetro, giroscopio y magnetómetro. Para proteger la privacidad de los usuarios, las imágenes sin procesar de la cámara de seguimiento ocular no están disponibles a través del modo de investigación, pero la dirección de la mirada con los ojos está disponible a través de las API existentes.

Consulte la documentación [del modo de investigación](https://docs.microsoft.com/windows/mixed-reality/research-mode) para obtener más detalles técnicos.

### <a name="recording-length-increased"></a>Longitud de grabación aumentada
Debido a los comentarios de los clientes, hemos aumentado la longitud de grabación de [las capturas de realidad mixta.](holographic-photos-and-videos.md) Las capturas de realidad mixta ya no se limitarán a 5 minutos de forma predeterminada, sino que calcularán la longitud máxima de grabación en función del espacio disponible en disco. El dispositivo calculará la duración máxima de la grabación de vídeo en función del espacio disponible en disco hasta un 80 % del espacio total en disco.

> [!NOTE]
> HoloLens usará la longitud de grabación de vídeo predeterminada (5 minutos) si se produce una de las siguientes situaciones:
> - La duración máxima estimada de la grabación es menor que los 5 minutos predeterminados.
> - El espacio en disco disponible es inferior al 20 % del espacio total en disco.

Puede encontrar todos los requisitos en nuestra [documentación de fotos y vídeos holográficos.](holographic-photos-and-videos.md#maximum-recording-length) 

### <a name="improvements-and-fixes-in-the-update"></a>Mejoras y correcciones en la actualización:
- Ahora hay más pantallas en modo oscuro en OOBE.
- Más información sobre el contenido debe apuntar a la declaración de privacidad más reciente en línea.
- Se ha corregido un problema por el que los usuarios no podían aprovisionar perfiles de VPN a través de paquetes de aprovisionamiento.
- Se ha corregido un problema de configuración de proxy para la conexión VPN.
- Se ha actualizado la directiva para deshabilitar la enumeración de funciones USB a través de MDM para NCM para AllowUsbConnection.
- Se ha corregido un problema que impedía que un dispositivo HoloLens se mostrara en Explorador de archivos a través del Protocolo de transferencia multimedia (MTP) cuando el dispositivo se configuraba como un quiosco de una sola [aplicación.](hololens-kiosk.md) Tenga en cuenta que MTP (y la conexión USB en general) todavía se pueden deshabilitar mediante la [directiva AllowUSBConnection.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
- Se ha corregido un problema por el que los iconos del menú Inicio se escalaban correctamente en modo de pantalla completa.
- Se ha corregido un problema debido a que el almacenamiento en caché HTTP interfiera con el modo de pantalla completa destinado a Azure AD grupos.
- Se ha corregido un problema por el que los usuarios no podían usar el botón Emparejar después de habilitar el modo de desarrollador con paquetes de aprovisionamiento a menos que se deshabilitara y se vuelva a habilitar el modo de desarrollador.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, versión 1903: actualización de noviembre de 2020
- Compilación 18362.1085

Esta actualización de calidad mensual no contiene ningún cambio importante, le recomendamos que pruebe nuestra versión de lanzamiento de características más reciente, Windows Holographic, versión 20H2.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic, versión 2004: actualización de octubre de 2020
- Compilación 19041.1124
 
Mejoras y correcciones en la actualización:

- Se ha quitado una comprobación innecesaria que produjo un error del sistema en tiempo de ejecución.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic, versión 1903: actualización de octubre de 2020
- Compilación 18362.1081

Esta actualización de calidad mensual no contiene ningún cambio importante; le recomendamos que pruebe nuestras compilaciones más recientes para Windows Holographic, versión 2004.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, versión 2004- Actualización de septiembre de 2020
- Compilación 19041.1117

Mejoras y correcciones en la actualización:

- Soluciona un problema que impedía Visual Studio depurar una aplicación cuando SupportsMultipleInstances="true" está presente en appxmanifest.
- Esta versión incluye la corrección de detección de proxy NCSI para solucionar los errores de detección de Internet a través del proxy de red. NCSI puede usar el proxy de máquina y el proxy por perfil para la detección de conectividad a Internet. El proxy por usuario será compatible con NCSI en una versión futura.
- En la mayoría Windows Mixed Reality dispositivos, el vector de dirección hacia delante es paralelo al suelo cuando la cabeza del usuario se encuentra en una posición neutra mirando hacia delante. Sin embargo, las versiones anteriores de HoloLens 2 alineaban el vector para que fuera después de los paneles de visualización, que se inclina hacia abajo unos grados en relación con la orientación ideal. Las versiones más recientes HoloLens 2 lo han corregido para garantizar la coherencia semántica entre los factores de forma.
- Se ha mejorado la solidez del seguimiento de las manos, lo que dará lugar a menos pérdidas de seguimiento en escenarios específicos.
- Esta versión contiene una corrección para mejorar la calidad de la marca de tiempo de audio que puede haber contribuido a los problemas de captura de vídeo.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, versión 1903: actualización de septiembre de 2020
- Compilación 18362.1079

Mejoras y correcciones en la actualización:

- En la mayoría Windows Mixed Reality dispositivos, el vector de dirección hacia delante es paralelo al suelo cuando la cabeza del usuario está en una posición neutra mirando hacia delante. Sin embargo, las versiones anteriores de HoloLens 2 alineaban el vector para que fuera horizontal con los paneles de visualización, que se inclina hacia abajo unos grados en relación con la orientación ideal. Las versiones más recientes HoloLens 2 lo han corregido para garantizar la coherencia semántica entre los factores de forma.
- Se ha mejorado la solidez del seguimiento de las manos, lo que dará lugar a menos pérdidas de seguimiento en escenarios específicos.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, versión 2004: actualización de agosto de 2020
- Compilación 19041.1113

Mejoras y correcciones en la actualización:

- La aplicación de configuración ya no seguirá al usuario en las experiencias de inscripción de Iris o calibración de seguimiento de los ojos.
- Se ha corregido un error por el que al aplicar un paquete de aprovisionamiento durante la operación de OOBE que cambia el nombre del dispositivo y realiza otras acciones (como conectarse a una red), no se realizarían las demás acciones después del reinicio del dispositivo debido al cambio de nombre.
- Se ha modificado la combinación de colores de los flujos de configuración inicial del dispositivo para mejorar la calidad visual.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, versión 1903: actualización de agosto de 2020
- Compilación 18362.1074

Esta actualización de calidad mensual no contiene ningún cambio importante; le recomendamos que pruebe nuestras compilaciones más recientes para Windows Holographic, versión 2004.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, versión 2004: actualización de julio de 2020
- Compilación 19041.1109

Mejoras y correcciones en la actualización:

- Los desarrolladores ahora pueden elegir entre habilitar o deshabilitar tener Portal de dispositivos requieren una conexión segura.
- Se ha mejorado la confiabilidad para los inicios de aplicaciones después de las actualizaciones del sistema operativo.
- Se ha cambiado el brillo predeterminado de la bandeja de entrada al 100 %.
- Se ha corregido un problema sobre el reenvío HTTPS para el Portal de dispositivos Windows en HoloLens 2.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, versión 1903: actualización de julio de 2020
- Compilación 18362.1071

Mejoras y correcciones en la actualización:

- Se ha corregido un problema que podía hacer que los hologramas desapareciera en las aplicaciones de Unity al perder o recuperar el seguimiento.
- Se ha corregido un problema que provocaba que las aplicaciones exclusivas de HoloLens se bloqueara de nuevo en el shell mientras se usaba el emulador de HoloLens con aceleración de hardware en determinados dispositivos.
- Se ha corregido un problema relativo al reenvío HTTPS para el Portal de dispositivos Windows en HoloLens 2.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, versión 2004- Actualización de junio de 2020
- Compilación 19041.1106

Mejoras y correcciones en la actualización:

- Las grabadoras MRC personalizadas ahora tienen nuevos valores predeterminados para determinadas propiedades si no se especifican.
  - En el efecto *de vídeo de MRC:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (casco inmersivo))
  - En el *efecto de audio de MRC*:
    - LoopbackGain (el valor actual de "Ganancia de audio de la aplicación" en la página Captura de realidad mixta en Portal de dispositivos Windows)
    - MicrophoneGain (el valor actual de "Ganancia de audio de micrófono" en la página Captura de realidad mixta en Portal de dispositivos Windows)
- Se ha corregido un error para mejorar la calidad del audio en escenarios de captura de realidad mixta. En concreto, esta corrección debe eliminar los problemas de audio en la grabación cuando **se** muestra el menú Inicio.
- Estabilidad mejorada del holograma en vídeos grabados.
- Se ha resuelto un problema por el que la captura de realidad mixta no podía grabar vídeo después de que el dispositivo quedara en estado de espera durante varios días.
- La API HolographicSpace.UserPresence generalmente está deshabilitada para las aplicaciones de Unity. Este comportamiento evita un problema que provocaba que algunas aplicaciones se pausase cuando se volteó el visor, aunque se habilitara la opción "Ejecutar en segundo plano". La API ahora está habilitada para las versiones de Unity 2018.4.18 y posteriores y 2019.3.4 y posteriores.
- Al acceder a Portal de dispositivos a través de Wi-Fi conexión, un explorador web podría impedir el acceso a debido a un certificado no válido. El explorador podría notificar un error como "ERR_SSL_PROTOCOL_ERROR", incluso si el certificado del dispositivo era de confianza previa. En este caso, no puede avanzar a Portal de dispositivos, ya que no hay ninguna opción para omitir las advertencias de seguridad. Esta actualización resolvió el problema. Si el certificado de dispositivo se descargó previamente y era de confianza en un equipo para quitar las advertencias de seguridad del explorador y se produce el error SSL, el nuevo certificado debe descargarse y ser de confianza para solucionar las advertencias de seguridad del explorador.
- Se ha habilitado la capacidad de crear un paquete de aprovisionamiento en tiempo de ejecución que puede instalar una aplicación mediante paquetes MSIX.
- Se ha agregado una configuración en **Configuración**  >  **Hologramas** del sistema que permite a los usuarios quitar automáticamente todos los hologramas de Mixed Reality inicio cuando el  >   dispositivo se apaga.
- Se ha corregido un problema que provocaba que las aplicaciones de HoloLens que cambiaban su formato de píxel se representaran en negro en el emulador de HoloLens.
- Se ha corregido un error que provocaba un bloqueo durante el inicio de sesión de Iris.
- Se ha corregido un problema sobre las descargas repetidas de la tienda para las aplicaciones ya actuales.
- Se ha corregido un error para impedir que las aplicaciones inmersivas se Microsoft Edge varias veces.
- Se ha corregido un problema con los inicios de la aplicación Photos en los arranques iniciales después de actualizar desde la versión 1903.
- Rendimiento y confiabilidad mejorados.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, versión 1903- Actualización de junio de 2020
- Compilación 18362.1064

Mejoras y correcciones en la actualización:

- Las grabadoras MRC personalizadas tienen nuevos valores predeterminados para determinadas propiedades si no se especifican.
  - En el efecto *de vídeo de MRC:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (casco envolvente))
  - En el *efecto de audio de MRC:*
    - LoopbackGain (el valor actual de "Ganancia de audio de la aplicación" en la página Captura de realidad mixta en Portal de dispositivos Windows)
    - MicrophoneGain (el valor actual de "Ganancia de audio de micrófono" en la página Captura de realidad mixta en Portal de dispositivos Windows)
- La API HolographicSpace.UserPresence generalmente está deshabilitada para las aplicaciones de Unity. Este comportamiento evita un problema que hace que algunas aplicaciones se pausen cuando se voltear el visor, incluso si la configuración para ejecutarse en segundo plano está habilitada. La API ahora está habilitada para las versiones de Unity 2018.4.18 y posteriores, y 2019.3.4 y versiones posteriores.
- Se ha corregido un problema que provocaba que las aplicaciones de HoloLens que cambiaran su formato de píxel se representaran en negro en el emulador de HoloLens.
- Se ha corregido un problema sobre los lanzamientos de la aplicación Fotos en los arranques iniciales después de actualizar desde la versión 1903.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, versión 2004  
- Compilación: 19041.1103

La actualización de software principal de mayo de 2020 para HoloLens 2, *Windows Holographic, versión 2004* incluye una gran cantidad de nuevas funcionalidades interesantes, como la compatibilidad con Windows Autopilot, el modo oscuro de la aplicación, la compatibilidad con Ethernet USB para zonas activas 5G/HOTSPOT y mucho más. Para actualizar a la versión más reciente, abra la aplicación Configuración, vaya a Actualizar & Security y seleccione el   botón **Buscar** ****   actualizaciones. 

|             Característica                              |          Descripción                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Configuración previa y sin problemas de nuevos dispositivos para producción mediante Windows AutoPilot                 |
|       Compatibilidad con FIDO 2                             |          Compatibilidad con las claves de seguridad FIDO2 para habilitar la autenticación rápida y segura para dispositivos compartidos            |
|       Aprovisionamiento mejorado                      |          Aplicación sin problemas de un paquete de aprovisionamiento desde una unidad USB a HoloLens                              |
|       Estado de instalación de la aplicación                 |          Compruebe el estado de instalación en la aplicación Configuración para las aplicaciones que se han HoloLens 2 a través de MDM.               |
|       Proveedores de servicios de configuración (CSP)   |          Se han agregado nuevos proveedores de servicios de configuración para mejorar las funcionalidades de control de administración.                 |
|       Compatibilidad con USB 5G/LTE                       |          La funcionalidad Ethernet USB ampliada permite la compatibilidad con 5G/GIGABIT.                                    |
|       Modo de aplicación oscura                              |          Modo de aplicación oscura disponible para las aplicaciones que admiten los modos oscuro y claro, lo que mejora la experiencia de visualización.        |
|       Comandos de voz                             |          Compatibilidad con comandos de voz del sistema adicionales para controlar HoloLens con manos libres                           |
|       Mejoras en el seguimiento de manos                 |          Las mejoras de seguimiento de manos hacen que los botones y las interacciones de pizarra 2D sea más precisa                        |
|       Mejoras y correcciones de calidad                 |          Diversas mejoras de rendimiento y confiabilidad del sistema en toda la plataforma                            |

### <a name="support-for-windows-autopilot"></a>Compatibilidad con Windows Autopilot

Windows Autopilot para HoloLens 2 permite que el canal de ventas del dispositivo inscriba previamente HoloLens en el inquilino de Intune. Cuando llegan los dispositivos, están listos para implementarse automáticamente como dispositivos compartidos en el inquilino. Para aprovechar las ventajas de la implementación propia, el dispositivo debe conectarse a una red durante la primera pantalla de la configuración mediante un USB de C a Ethernet.

Una vez que un usuario inicia el proceso de implementación automática de Autopilot, el proceso completa los pasos siguientes:

1. Una el dispositivo para Azure Active Directory (Azure AD).
1. Use Azure AD para inscribir el dispositivo en Microsoft Intune (u otro servicio MDM).
1. Descargue las directivas de destino del dispositivo, los certificados y los perfiles de red.
1. Aprovisione el dispositivo.
1. Presente la pantalla de inicio de sesión al usuario.

Obtenga más información en la [guía Windows Autopilot para HoloLens 2 evaluación.](https://docs.microsoft.com/hololens/hololens2-autopilot)

*Póngase en contacto con el administrador de cuentas para unirse ahora a la versión preliminar de AutoPilot. Los dispositivos listos para Autopilot comenzarán a enviarse pronto.*

### <a name="fido2-security-key-support"></a>Compatibilidad con la clave de seguridad FIDO2

Algunos usuarios comparten un dispositivo HoloLens con otros usuarios en un entorno laboral o educativo. Por lo tanto, es importante que los usuarios puedan fácilmente sin escribir nombres de usuario y contraseñas largos. Fast Identity Online (FIDO) permite que cualquier persona de su organización (inquilino de Azure AD) inicie sesión sin problemas en HoloLens sin escribir un nombre de usuario o una contraseña.

Las claves de seguridad FIDO2 son un método de autenticación sin contraseña basado en estándares "nophishable" que puede tener cualquier factor de forma. FIDO es un estándar abierto para la autenticación sin contraseña. Permite a los usuarios y organizaciones iniciar sesión en sus recursos sin un nombre de usuario o contraseña. En su lugar, usan una clave de seguridad externa o una clave de plataforma integrada en un dispositivo.

Para empezar, consulte Habilitación [del inicio de sesión con clave de seguridad sin contraseña.](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Inscripción de MDM mejorada a través del paquete de aprovisionamiento

Los paquetes de aprovisionamiento permiten establecer la configuración de HoloLens a través de un archivo de configuración en lugar de a través de la experiencia de holoLens. Anteriormente, los paquetes de aprovisionamiento tenían que copiarse en la memoria interna de HoloLens. Ahora pueden estar en una unidad USB, por lo que son más fáciles de reutilizar en varios dispositivos HoloLens y puede aprovisionar dispositivos en paralelo. Los paquetes de aprovisionamiento ahora también admiten un campo para inscribirse en la administración de dispositivos, por lo que no hay ninguna configuración manual después del aprovisionamiento.

Para probarlo:

1. Descargue la versión más reciente del Diseñador de configuración de Windows desde la Tienda Windows en el equipo.
1. Seleccione **Aprovisionar dispositivos HoloLens**  >  **Aprovisionar HoloLens 2 dispositivos**.
2. Compile el perfil de configuración. A continuación, copie todos los archivos creados en un dispositivo de almacenamiento USB-C.
3. Conecte el dispositivo USB-C a cualquier HoloLens recién parpadeado. A continuación, **presione los**  +  **botones de encendido del volumen** para aplicar el paquete de aprovisionamiento.

### <a name="line-of-business-application-install-status"></a>Estado de instalación de la aplicación de línea de negocio

La implementación y administración de aplicaciones MDM para aplicaciones de línea de negocio es fundamental para HoloLens. Los administradores y usuarios deben ver el estado de instalación de la aplicación para la auditoría y el diagnóstico. En esta versión, hemos agregado más detalles en Configuración Cuentas acceso a trabajo o escuela Haga  >    >    >  **clic en la información de su**  >  **cuenta.**

### <a name="additional-csps-and-policies"></a>Directivas y CSP adicionales

Un [proveedor de servicios de configuración (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) es una interfaz para leer, establecer, modificar o eliminar valores de configuración en un dispositivo. En esta versión, se agrega compatibilidad con más directivas para aumentar el control que los administradores tienen sobre los dispositivos HoloLens implementados. Para obtener la lista de CSP compatibles con HoloLens, consulte [Csp de NetworkQoSPolicy.](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)

Novedades en esta versión:

**Policy CSP** 

El proveedor de servicios de configuración de directivas permite a la empresa configurar directivas en dispositivos Windows. En esta versión, hemos agregado nuevas directivas para HoloLens, que se enumeran aquí. Para más información, consulte [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessGazeInput 
- LetAppsAccessGazeInput_ForceAllowTheseApps 
- LetAppsAccessGazeInput_ForceDenyTheseApps 
- LetAppsAccessGazeInput_UserInControlOfTheseApps 
- LetAppsAccessMicrophone_ForceAllowTheseApps 
- LetAppsAccessMicrophone_ForceDenyTheseApps 
- LetAppsAccessMicrophone_UserInControlOfTheseApps 
- AllowWiFi 

**NetworkQoSPolicy CSP**

El proveedor de servicios de configuración NetworkQoSPolicy crea directivas de calidad de servicio (QoS) de red. Una directiva qos realiza un conjunto de acciones en el tráfico de red en función de un conjunto de condiciones de coincidencia. Para más información, consulte [CSP de NetworkQoSPolicy.](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Compatibilidad ampliada con Ethernet USB para dispositivos tethered 5G/NFC

Se ha agregado compatibilidad para habilitar determinados dispositivos de banda ancha móvil, como teléfonos 5G/NFC y zonas activas de Wi-Fi, cuando están conectados a la red HoloLens 2 a través de USB. Estos dispositivos ahora se muestran en la **configuración de red** como otra conexión Ethernet. (No se admiten los dispositivos de banda ancha móvil que requieren un controlador externo). Esta funcionalidad permite conexiones de alto ancho de banda cuando Wi-Fi no está disponible y Wi-Fi tethering no es lo suficientemente bueno. Para más información sobre los dispositivos USB compatibles, consulte [Conexión a dispositivos Bluetooth y USB-C.](https://docs.microsoft.com/hololens/hololens-connect-devices)  

### <a name="hand-tracking-improvements"></a>Mejoras en el seguimiento de manos

Esta versión incluye varias mejoras en el seguimiento de las manos:

- **Apuntando la estabilidad de la posición:** El sistema ahora se resistirá a deslizar el dedo índice cuando la mano lo ocluse. Este cambio mejora la precisión al insertar botones, escribir, desplazar contenido, etc. 
- **Pulsaciones de aire accidentales reducidas:** Se ha mejorado la detección del gesto de pulsar en el aire. Ahora hay menos activaciones accidentales en varios escenarios comunes, como cuando se coloca las manos a los lados.
- **Confiabilidad del conmutador de usuario:** El sistema ahora es más rápido y confiable a la hora de actualizar el tamaño de la mano al compartir un dispositivo.
- **Robo a mano reducido:** Hemos mejorado el control de los casos en los que hay más de dos manos a la vista de los sensores. Si varias personas trabajan juntas, ahora hay una probabilidad mucho menor de que la mano con seguimiento "salte" del usuario a la mano de otra persona de la escena.
- **Confiabilidad del sistema:** Se ha corregido un problema que provocaba que el seguimiento de manos dejara de funcionar cuando el dispositivo está bajo una carga elevada.

### <a name="dark-mode"></a>Modo oscuro

Muchas aplicaciones de Windows ahora admiten los modos oscuro y claro. HoloLens 2 usuarios pueden elegir el modo predeterminado para las aplicaciones que admiten ambos. Después de la actualización, el modo de aplicación predeterminado es "oscuro", pero puede cambiar fácilmente esta configuración: Vaya a Configuración Colores del sistema   >    >    >  **Elija el modo de aplicación predeterminado**. 

Estas aplicaciones "in-box" admiten el modo oscuro: 

- Configuración 
- Microsoft Store 
- Correo 
- Calendario 
- Explorador de archivos 
- Centro de opiniones 
- OneDrive 
- Fotos 
- Visor 3D 
- Películas y TV 

![Ventanas en mosaico en modo oscuro](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Comandos de voz del sistema

Ahora puede usar comandos de voz con cualquier aplicación en el dispositivo. Para obtener más información, [consulte Uso de la voz para usar HoloLens.](https://docs.microsoft.com/hololens/hololens-cortana) Consulte también [Idiomas admitidos para HoloLens 2](https://docs.microsoft.com/hololens/hololens2-language-support).  

### <a name="cortana-updates"></a>Actualizaciones de Cortana

La aplicación actualizada se integra con Microsoft 365 para ayudarle a realizar más cosas en los dispositivos (actualmente solo US-English). En HoloLens 2, Cortana ya no admite determinados comandos específicos del dispositivo, como ajustar el volumen o reiniciar. Estas opciones ahora son compatibles con los nuevos comandos de voz del sistema. Obtenga más información sobre la nueva aplicación Cortana en nuestro [blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### <a name="quality-improvements-and-fixes"></a>Mejoras y correcciones de calidad

Mejoras y correcciones también en la actualización:  
- Se introdujo un sistema de calibración de pantalla activo. Esta característica mejora la estabilidad y la alineación de los hologramas. Ahora permanecen en su lugar cuando mueve la cabeza de lado a lado.
- Se ha corregido un error Wi-Fi streaming a HoloLens se interrumpía periódicamente. Si una aplicación indica que necesita streaming de baja latencia, implemente la corrección llamando a la [función SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Se ha corregido un error de dispositivo que se produjo durante el streaming en modo de investigación.
- Se ha corregido un error por el que, en algunos casos, el usuario adecuado no se mostraría en la pantalla de inicio de sesión al reanudar una sesión.
- Se ha corregido un problema por el que los usuarios no podían exportar los registros de MDM a través **de Configuración.**
- Se ha corregido un problema por el que la precisión del seguimiento de los ojos inmediatamente después de la configuración rápida podría ser inferior a la esperada.
- Se ha corregido un problema por el que el subsistema de seguimiento ocular no se inicializaba o realizaba la calibración en determinadas condiciones.
- Se ha corregido un problema por el que se solicitaba calibración de los ojos para un usuario ya calibrado.
- Se ha corregido un problema por el que un controlador se bloqueaba durante la calibración de los ojos.
- Se ha corregido un problema por el que las pulsaciones repetidas del botón de encendido podían provocar un tiempo de espera del sistema de 60 segundos y un bloqueo del shell.
- Estabilidad mejorada para búferes de profundidad.
- Se ha agregado un **botón** Compartir en el Centro de opiniones para que los usuarios puedan compartir comentarios más fácilmente.
- Se ha corregido un error por el que RoboRaid wan no se instalaba correctamente.

### <a name="known-issues"></a>Problemas conocidos

- Un problema con el lenguaje del sistema zh-CN impide que los comandos de voz tome una captura de realidad mixta o muestre la dirección IP del dispositivo.
- Un problema requiere que inicie la aplicación Cortana después de iniciar el dispositivo para usar la activación de voz "Hola Cortana". Si ha actualizado desde una compilación 18362, es posible que también vea un segundo icono de aplicación para la versión anterior de la aplicación Cortana que ya no funciona en **Iniciar**.

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, versión 1903: actualización de mayo de 2020 
- Compilación 18362.1061

Esta actualización de calidad mensual no contiene ningún cambio importante porque el equipo estaba trabajando en la actualización de mayo de Windows Holographic versión 2004, como se describió anteriormente.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, versión 1903: actualización de abril de 2020
- Compilación 18362.1059

**Modo oscuro para aplicaciones admitidas** 

Muchas aplicaciones de Windows admiten el modo oscuro y claro. HoloLens 2 los clientes pueden elegir el modo predeterminado para las aplicaciones que admiten ambos esquemas de color. En función de los comentarios de los clientes, establecemos el modo de aplicación predeterminado en "oscuro", pero puede cambiar fácilmente esta configuración en cualquier momento: vaya a Configuración **> System > Colors** para buscar **"Choose your default app mode"** (Elegir el modo de aplicación predeterminado).

Estas aplicaciones "in-box" admiten el modo oscuro:
- Configuración
- Microsoft Store
- Correo
- Calendario
- Explorador de archivos
- Centro de opiniones
- OneDrive
- Fotos
- Visor 3D
- Películas y TV

**Mejoras y correcciones también en la actualización:** 
- Se ha asegurado de que las superposiciones de shell se incluyen en las capturas de realidad mixta.
- Los desarrolladores de Unreal ahora pueden usar la página Vista 3D Portal de dispositivos probar y depurar sus aplicaciones.
- Se ha mejorado la estabilidad del holograma en la captura de realidad mixta cuando se usa el algoritmo *DepthReprojectionMethod de HolographicDepthReprojectionMethod.*
- Se ha corregido el error "WinRT IStreamSocketListener API Class not registered" (Clase de API IStreamSocketListener no registrada) en aplicaciones arm de 32 bits.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic, versión 1903: actualización de marzo de 2020 
- Compilación 18362.1056

Mejoras y correcciones en la actualización:

- Se ha mejorado la estabilidad del holograma en la captura de realidad mixta cuando se usa el algoritmo *HolographicDepthReprojectionMethod AutoPlanar.*
- Se ha asegurado de que el sistema de coordenadas asociado a un ejemplo de MF de profundidad es coherente con la documentación pública.
- Se ha mejorado la productividad de los desarrolladores al permitir que los clientes peguen grandes cantidades de texto a través del portal del dispositivo.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic, versión 1903- Actualización de febrero de 2020 
- Compilación 18362.1053

Mejoras y correcciones en la actualización:

- Deshabilitada temporalmente la API HolographicSpace.UserPresence para aplicaciones de Unity. Este cambio evita un problema que provocaba que algunas aplicaciones se pausase cuando se volteó el visor, aunque se habilitara la opción "Ejecutar en segundo plano".
- Se ha corregido un bloqueo de HUP aleatorio causado por el seguimiento de las manos, en el que el usuario observó una inmovilización de la interfaz de usuario y, después, vuelve al shell después de varios segundos.
- Se ha mejorado el seguimiento de las manos para que, cuando se desenreda con el dedo índice, es menos probable que la parte superior de ese dedo se curl de forma inesperada.
- Confiabilidad mejorada del seguimiento de la cabeza, la asignación espacial y otros tiempos de ejecución.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, versión 1903: actualización de enero de 2020 
- Compilación 18362.1043
 
Mejoras y correcciones en la actualización:

- Estabilidad mejorada para aplicaciones exclusivas al trabajar con el emulador HoloLens 2 aplicación.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, versión 1903: actualización de diciembre de 2019 
- Compilación 18362.1042

Mejoras y correcciones en la actualización:

- Se han introducido correcciones de reproducción de la última fase (LSR). Se ha mejorado la representación visual de los hologramas para que parezcan más estables y precisos, ya que se tiene en cuenta su profundidad con mayor precisión. Este síntoma será más perceptible después de esta actualización si las aplicaciones no establecen correctamente la profundidad de los hologramas.
- Se ha corregido la estabilidad de las aplicaciones exclusivas y la navegación entre aplicaciones exclusivas.
- Se ha resuelto un problema por el que la captura de realidad mixta no podía grabar vídeo después de que el dispositivo estaba en estado de espera durante varios días.
- Estabilidad mejorada del holograma.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, versión 1903- Actualización de noviembre de 2019 
- Compilación 18362.1039

Mejoras y correcciones en la actualización:

- Se ha corregido la **funcionalidad de Seleccionar** comandos de voz durante la configuración inicial para en-CA y en-AU.
- Calidad visual mejorada de los objetos colocados lejos en las versiones más recientes de Unity y Mixed Reality Toolkit (MRTK).
- Se han corregido problemas de direccionamiento con las aplicaciones holográficas que se atascaban en un estado en pausa durante el inicio hasta que menú Inicio se abre y, a continuación, se cierra.
- Correcciones y mejoras de conformidad en tiempo de ejecución de OpenXR para HoloLens 2 y el emulador.
