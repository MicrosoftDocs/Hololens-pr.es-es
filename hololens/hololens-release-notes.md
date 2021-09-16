---
title: Notas de la versión de HoloLens 2
description: Manténgase al día con todas las actualizaciones de cada versión HoloLens 2 nueva.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 80b23e1cc851081179e6deee2e5fd13d374946f1
ms.sourcegitcommit: f1c50b39430026fd5e3c92ac1a09f07b69733325
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2021
ms.locfileid: "127862483"
---
# <a name="hololens-2-release-notes"></a>Notas de la versión de HoloLens 2

Para asegurarse de que tiene una experiencia productiva con los dispositivos HoloLens, seguimos lanzando actualizaciones de características, errores y seguridad. En esta página, puede ver las novedades de los HoloLens cada mes. Para obtener la actualización HoloLens 2 más reciente, puede buscar actualizaciones y actualizar manualmente u obtener la actualización flash completa (FFU) para flashear el dispositivo a través de Advanced [Recovery Companion](hololens-recovery.md#clean-reflash-the-device). [](hololens-update-hololens.md#check-for-updates-and-manually-update) La [descarga](https://aka.ms/hololens2download) se mantiene actualizada y proporciona la compilación más reciente disponible con carácter general.

> [!NOTE]
> El anuncio reciente sobre Windows 11 se centraba en la versión para equipos de Windows. Recientemente hemos lanzado una [actualización importante del sistema operativo](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) de HoloLens 2 en mayo de 2021 y estamos trabajando en una próxima versión basada en los comentarios de los clientes para el próximo otoño.

> [!IMPORTANT]
> Debido a un problema conocido resuelto en nuestra compilación [21H1](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)que afectaba a los usuarios de Remote Assist, pausamos temporalmente la oferta de actualizaciones de Windows Holographic, versión 21H1. También hemos cambiado la compilación predeterminada de Advanced Recovery Companion (ARC) a Windows [Holographic, versión 20H2– Actualización de junio de 2021](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update). La compilación de ARC se reanudará ahora con la compilación 21H1 como destino.

## <a name="windows-holographic-version-21h1---september-2021-update"></a>Windows Holographic, versión 21H1: actualización de septiembre de 2021

- Compilación 20348.1018

Mejoras y correcciones en la actualización:

- Correcciones para resolver el problema en el que la hora del sistema puede saltar inesperadamente.

## <a name="windows-holographic-version-20h2---september-2021-update"></a>Windows Holographic, versión 20H2: actualización de septiembre de 2021

- Compilación 19041.1165

Mejoras y correcciones en la actualización:

- Correcciones para resolver el problema en el que la hora del sistema puede saltar inesperadamente.

## <a name="windows-holographic-version-21h1---august-2021-update"></a>Windows Holographic, versión 21H1: actualización de agosto de 2021

- Compilación 20348.1014

Mejoras y correcciones en la actualización:

- Se ha corregido un problema que impedía que los controladores de Xbox funcionara en aplicaciones inmersivas con compatibilidad con controladores.
- Diagnóstico mejorado para errores de actualización de dispositivos.

## <a name="windows-holographic-version-20h2---august-2021-update"></a>Windows Holographic, versión 20H2: actualización de agosto de 2021

- Compilación 19041.1161

Mejoras y correcciones en la actualización:

- Esta actualización de calidad mensual no contiene ningún cambio importante, le recomendamos que pruebe la compilación más reciente, Windows Holographic, versión 21H1.

## <a name="windows-holographic-version-21h1---july-2021-update"></a>Windows Holographic, versión 21H1: actualización de julio de 2021

- Compilación 20348.1010

Mejoras y correcciones en la actualización:

- Portal de dispositivos métodos mejorados para notificar al cliente cuando Explorador de archivos problemas al abrir archivos bloqueados.
- La carga, descarga, cambio de nombre y eliminación de archivos ahora se ha corregido cuando se usa https en todos los exploradores compatibles.
- Se ha corregido un problema por el que Wi-Fi Wi-Fi no se podía guardar el proxy cuando se iniciaba una interfaz de usuario de propiedades de **Configuración -> Network & Internet -> Status -> Properties**.
- Se ha corregido un problema en torno a la eliminación de certificados eSIM en las actualizaciones del sistema operativo. Esta corrección garantiza que los certificados eSIM y los componentes relacionados se quitan al actualizar a la versión 21H1.
- Se ha corregido un problema que afectaba a las aplicaciones preinstaladas en los restablecimientos del sistema operativo.
- Rendimiento de carga de la batería optimizado para aumentar el tiempo de ejecución al cargar con mayor carga de CPU. Al cargar HoloLens 2 dispositivos, si se detecta que el dispositivo se está ejecutando en caliente, la batería interna se cargará más lentamente para reducir el calor. El saldo positivo es que es menos probable que un dispositivo se apague debido a problemas térmicos, con el impacto de que el dispositivo se ejecute más tiempo. Si el dispositivo se está ejecutando con es cool, la tasa de cargos no se verán afectadas.

## <a name="windows-holographic-version-20h2--july-2021-update"></a>Windows Holographic, versión 20H2: actualización de julio de 2021

- Compilación 19041.1157

Mejoras y correcciones en la actualización:

- Portal de dispositivos métodos mejorados para notificar al cliente cuando Explorador de archivos problemas al abrir archivos bloqueados.
- La carga, descarga, cambio de nombre y eliminación de archivos ahora se ha corregido cuando se usa https en todos los exploradores compatibles.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographic, versión 21H1: actualización de junio de 2021

- Compilación 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive carga de la cámara para trabajo o escuela

Hemos agregado una nueva característica a la aplicación HoloLens 2 Configuración, que permite a los clientes cargar automáticamente fotos y vídeos de realidad mixta desde la carpeta Pictures > Camera Roll del dispositivo en la carpeta OneDrive correspondiente para trabajo o escuela. Esta característica soluciona una brecha de características dentro de la aplicación [de OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) en HoloLens 2, que solo admite la carga automática de camera roll en la cuenta microsoft personal de un cliente (y no en su cuenta de trabajo o educativa).

**Funcionamiento**

- Visite **Configuración > System > Cámara de realidad mixta** para habilitar la "carga de la cámara".
- Al establecer esta  característica en la posición En, las fotos o vídeos de realidad mixta capturados en el dispositivo se pondrán automáticamente en cola para cargarse en la carpeta Imágenes > Camera Roll de la cuenta de OneDrive for work o school.
    >[!NOTE]
    >Fotos y los vídeos capturados  antes de habilitar esta característica no se pondrán en cola para la carga y seguirán teniendo que cargarse manualmente.
- Un mensaje de estado en la página Configuración mostrará el número de archivos pendientes de carga (o leerá "OneDrive está actualizado" cuando se hayan cargado todos los archivos pendientes).
- Si le preocupa el ancho de banda o quiere "pausar" la carga por cualquier motivo, puede cambiar la característica a la **posición Desactivado.** Deshabilitar temporalmente la característica garantiza que la cola de carga seguirá aumentando a medida que agregue nuevos archivos a la carpeta Camera Roll, pero los archivos no se cargarán hasta que vuelva a habilitar la característica.
- Los archivos más nuevos se cargarán primero (último en, primero en salir).
- Si la OneDrive cuenta tiene problemas (por ejemplo, después  de cambiar la contraseña), aparecerá un botón Corregir ahora en la Configuración usuario.
- No hay ningún tamaño de archivo máximo, pero tenga en cuenta que los archivos grandes tardan más tiempo en cargarse (especialmente si el ancho de banda de carga está restringido). Si "pausa" o desactiva la carga mientras se carga un archivo grande, se conservará la carga parcial. Si la carga se vuelve a habilitar en un plazo de varias horas después de que se haya "pausado" o desactivado, la carga continuará desde donde lo dejó. Sin embargo, si la carga se vuelve a habilitar después de varias horas, la carga del archivo grande se reiniciará desde el principio.

**Problemas conocidos y advertencias**

- Esta configuración no tiene ninguna limitación integrada en función del uso actual del ancho de banda. Si necesita maximizar el ancho de banda para otro escenario, desactive la configuración manualmente. Upload se pausará, pero la característica seguirá supervisando los archivos recién agregados al lanzamiento de cámara. Vuelva a habilitar la carga cuando esté listo para que continúe.
- Esta característica debe estar habilitada para cada cuenta de usuario del dispositivo y solo puede cargar archivos de forma activa para el usuario que ha iniciado sesión actualmente en el dispositivo.
- Si va a tomar fotos o vídeos mientras observa el número de cargas en la página Configuración en tiempo real, tenga en cuenta que es posible que el recuento de archivos pendientes no cambie hasta que se haya completado la carga del archivo actual.
- Upload se pausará si el dispositivo se queda apagado o se queda apagado. Para asegurarse de que las cargas pendientes se completan, use activamente el dispositivo hasta que la página Configuración lea "OneDrive is up to date" (OneDrive está actualizado) o ajuste la configuración de suspensión de **Power &.**

### <a name="added-support-for-some-telemetry-policies"></a>Se ha agregado compatibilidad con algunas directivas de telemetría.

Ahora se admiten las siguientes directivas de telemetría en el HoloLens 2:

- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

Tanto System\AllowTelemetry como System\ConfigureTelemetryOptInSettingsUx deben usarse conjuntamente para tener un control completo sobre la telemetría y el comportamiento en la Configuración aplicación.

Mejoras y correcciones en la actualización:

- Corrige daños importantes en el vídeo con calibración de color.
- Soluciona un problema por el que el texto podría truncarse en el menú Energía.
- Habilita la compatibilidad con la directiva RequirePrivateStoreOnly.

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows Holographic, versión 20H2: actualización de junio de 2021

- Compilación 19041.1154

### <a name="added-support-for-some-telemetry-policies"></a>Se ha agregado compatibilidad con algunas directivas de telemetría.

Ahora se admiten las siguientes directivas de telemetría en el HoloLens 2:

- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

Tanto System\AllowTelemetry como System\ConfigureTelemetryOptInSettingsUx deben usarse conjuntamente para tener un control completo sobre la telemetría y el comportamiento en la Configuración aplicación.

Le recomendamos que pruebe la compilación más reciente, Windows Holographic, versión 21H1.

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows Holographic, versión 1903: actualización de junio de 2021

- Compilación 18362.1116

Mejoras y correcciones en la actualización:

- Esta actualización de calidad mensual no contiene ningún cambio importante, le recomendamos que pruebe la compilación más reciente, Windows Holographic, versión 21H1.

>[!IMPORTANT]
> Esta compilación ya no se atenderá.

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
> Con la introducción de Windows Holographic versión 21H1, se van a interrumpir las actualizaciones de mantenimiento mensuales para Windows **Holographic versión 1903.** Esto nos permite centrarse en versiones más recientes y seguir entregando mejoras valiosas.


| Nombre de la característica                                              | Descripción breve                                                                      | Público de destino | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Nuevo Microsoft Edge](#introducing-the-new-microsoft-edge)  | El nuevo Chromium basado en Microsoft Edge está disponible para HoloLens 2. | Usuario final | 
[WebXR y 360 Viewer](#webxr-and-360-viewer) | Pruebe las experiencias web envolventes y la reproducción de vídeo 360. | Usuario final | 
[Nueva aplicación Configuración](#new-settings-app) | La aplicación de Configuración heredada se reemplaza por una versión actualizada con nuevas características y configuraciones. | Usuario final |
[Calibración del color de la pantalla](#display-color-calibration) | Seleccione un perfil de color alternativo para la pantalla de HoloLens 2. | Usuario final |
[Selector de aplicaciones predeterminadas](#default-app-picker) | Elija qué aplicación debe iniciarse para cada tipo de archivo o vínculo. | Usuario final |
[Control de volumen por aplicación](#per-app-volume-control) | Controlar el volumen de nivel de aplicación independientemente del volumen del sistema. | Usuario final |
[Instalación de aplicaciones web](#install-web-apps) | Instale aplicaciones web en HoloLens 2, como Microsoft Office, con el nuevo Microsoft Edge explorador. | Usuario final |
[Deslizamiento para escribir](#swipe-to-type) | Use la punta del dedo para "deslizar" las palabras en el teclado holográfico. | Usuario final |
[Menú de encendido desde Inicio](#power-menu-from-start) | En el menú Inicio, reinicie y apague HoloLens dispositivo. | Usuario final |
[Varios usuarios enumerados en la pantalla de inicio de sesión](#multiple-users-listed-on-sign-in-screen) | Mostrar varias cuentas de usuario en la pantalla Inicio de sesión. | Usuario final |
[Compatibilidad con micrófono externo USB-C](#usb-c-external-microphone-support) | Use micrófonos USB-C para aplicaciones y/o Remote Assist. | Usuario final |
[Inicio de sesión automático de visitante para quioscos](#visitor-auto-logon-for-kiosks) | Permite que el inicio de sesión automático en las cuentas de visitante se utilice para los modos de quiosco. | Administración de TI |
[Nuevos AUMID para nuevas aplicaciones en pantalla completa](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | AUMIDs para nuevas aplicaciones Configuración y Edge. | Administración de TI |
[Entrega de errores en modo de pantalla completa mejorada](#kiosk-mode-behavior-changes-for-handling-of-failures) | El modo de pantalla completa busca Acceso asignado global antes de un menú de inicio vacío. | Administración de TI |
[Nueva configuraciónDI para la visibilidad de Configuración página](#new-settings-uris-for-page-settings-visibility) | Más de 20 opciones de configuración nuevas para Configuración/PageVisibilityList. | Administración de TI |
[Configuración de diagnósticos de reserva](#configuring-fallback-diagnostics-via-settings-app) | Establecer el comportamiento de diagnóstico de reserva Configuración aplicación. | Administración de TI |
[Compartir cosas con dispositivos cercanos](#share-things-with-nearby-devices) | Compartir archivos o direcciones URL de un HoloLens a un equipo. | Todo |
[Nuevos seguimientos de diagnóstico del sistema operativo](#new-os-diagnostic-traces) | Nuevo solucionador de problemas en Configuración actualizaciones del sistema operativo. | Administración de TI |
[Versión preliminar de la optimización de la distribución](#delivery-optimization-preview) | Reduzca el consumo de ancho de banda para las descargas de HoloLens dispositivos. | Administración de TI |

Consulte las notas de la versión relacionadas:

- [Visite el archivo HoloLens Emulator.](/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Presentación de la nueva versión de Microsoft Edge

![Animación del cambio del logotipo de la versión anterior de Microsoft Edge al logotipo de la nueva versión.](images/new-edge.gif)

La nueva versión de Microsoft Edge [adopta el proyecto Chromium de código abierto](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) con el fin de conseguir una mejor compatibilidad para los clientes y una menor fragmentación de la web para los desarrolladores web.

> [!IMPORTANT]
> Esta nueva versión de Microsoft Edge reemplaza automáticamente a la versión anterior, que ya no se [admite](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) en los nuevos lanzamientos.

![Captura de pantalla de la nueva versión de Microsoft Edge.](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Inicio de la nueva versión de Microsoft Edge

La nueva versión de Microsoft Edge ![Icono de la nueva versión de Microsoft Edge.](images/new_edge_logo.png) (representada por un icono de espiral azul y verde) se ancla al menú Inicio y se inicia automáticamente al activar un vínculo web.

> [!NOTE]
> La primera vez que inicie la nueva versión de Microsoft Edge en su HoloLens 2, se importarán la configuración y los datos de la versión anterior. Si sigue usando el Microsoft Edge heredado después de iniciar el nuevo Microsoft Edge, los nuevos datos no se sincronizarán de la Microsoft Edge heredada a la nueva Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Configuración de las opciones de directiva para la nueva versión de Microsoft Edge

La nueva versión de Microsoft Edge ofrece a los administradores de TI un conjunto mucho más amplio de directivas de explorador en HoloLens 2 de las que estaban disponibles previamente con la versión anterior de Microsoft Edge.

Estos son algunos recursos útiles para obtener más información sobre cómo administrar la configuración de directivas para la nueva versión de Microsoft Edge:

- [Configurar la directiva de Microsoft Edge con Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Asignación de directivas de Microsoft Edge (versión anterior) a Microsoft Edge](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Asignación de directivas de Google Chrome a Microsoft Edge](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- [Documentación completa de Microsoft Edge Enterprise](/deployedge/)

> [!IMPORTANT]
> Debido al volumen de directivas de explorador compatibles con la nueva versión de Microsoft Edge, nuestro equipo no puede garantizar que cada nueva directiva funcione en HoloLens 2. Sin embargo, hemos probado y confirmado que el equivalente en la nueva versión de Microsoft Edge de cada directiva de la versión anterior de Microsoft Edge admitida anteriormente en HoloLens 2 funciona según lo previsto. Consulte [Asignación de directivas de Microsoft Edge (versión anterior) a Microsoft Edge](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) para encontrar el equivalente en la nueva versión de Microsoft Edge de cada directiva de explorador de la versión anterior de Microsoft Edge que se usaba con HoloLens 2.
>
> Hay al menos dos directivas de la nueva versión de Microsoft Edge que sabemos que *no* funcionarán con HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Qué esperar de la nueva versión de Microsoft Edge en HoloLens 2

Dado que la nueva versión de Microsoft Edge es una aplicación Win32 nativa con un nuevo nivel de adaptador de UWP que le permite ejecutarse en dispositivos solo para UWP como HoloLens 2, es posible que algunas características no estén disponibles inmediatamente. En los próximos meses se admitirán nuevos escenarios y características, así que no deje de consultar este espacio para obtener información actualizada.

**Escenarios y características que se espera que funcionen:**
- Experiencia de primera ejecución, inicio de sesión en el perfil y sincronización
- Los sitios web deberían representarse y comportarse según lo previsto
- La mayoría de las funcionalidades del explorador (Favoritos, Historial, etc.) deberían funcionar según lo previsto
- Modo oscuro
- Instalación de aplicaciones web en el dispositivo
- Instalación de extensiones (si usa extensiones que no funcionan correctamente en HoloLens 2, háganoslo saber)
- Visualización y marcado de archivos PDF
- Sonido espacial desde una sola ventana del explorador
- Actualización automática y manual del explorador
- Guardado en un PDF en el menú de impresión, con la opción "Save to PDF" (Guardar en PDF)
- Extensiones WebXR y 360 Viewer
- Restauración del contenido en la ventana correcta al explorar varias ventanas del entorno

**Escenarios y características que no se espera que funcionen:**
- Sonido espacial procedente de varias ventanas con secuencias de audio simultáneas
- "Verlo, decirlo"
- Impresión

**Principales problemas conocidos del explorador:**

- La vista previa de lupa en el teclado holográfico se ha deshabilitado en la nueva versión de Microsoft Edge. Esperamos poder volver a poder usar esta característica en una futura actualización, cuando la ampliación funcione correctamente.
- Si hay otra ventana del explorador abierta y activa, puede que se reproduzca el audio de la ventana del explorador incorrecta. Para evitar este problema, cierre la otra ventana activa que no debería estar reproduciendo audio.
- Al reproducir audio desde una ventana del explorador en modo ["Sígueme",](hololens2-basic-usage.md#follow-me-stop-following)el audio continuará reproduciendo si deshabilita el modo "Sígueme". Para evitar este problema, detenga la reproducción de audio antes de deshabilitar el modo "Sígueme" o cierre la ventana con el **botón X.**
- La interacción con ventanas activas de Microsoft Edge puede hacer que las ventanas de otras aplicaciones 2D dejen de estar activas inesperadamente. Puede reactivarlas interactuando de nuevo con ellas.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider Channels

El equipo de Microsoft Edge pone a disposición de la comunidad de Edge Insider tres canales de versión preliminar: Beta, Dev y Canary. La instalación de un canal de versión preliminar no desinstala la versión publicada de Microsoft Edge en su HoloLens 2, y puede instalar más de uno simultáneamente. 

Visite la [página principal de Microsoft Edge Insider](https://www.microsoftedgeinsider.com) para obtener más información sobre la comunidad de Edge Insider. Para obtener más información sobre los diferentes canales de Edge Insider y empezar a utilizarlos, visite la [página de descarga de Edge Insider](https://www.microsoftedgeinsider.com/download).

Hay un par de métodos disponibles para instalar Microsoft Edge Insider Channels en su HoloLens 2:

**Instalación directa en el dispositivo (actualmente solo disponible para dispositivos no administrados)**
  1. En su HoloLens 2, visite la [página de descarga de Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Seleccione el botón **Download for HoloLens 2** (Descargar para HoloLens 2) en el canal de Edge Insider que desee instalar.
  1. Inicie el archivo .msix descargado desde la cola de descarga de Edge o desde la carpeta "Descargas" del dispositivo (mediante el Explorador de archivos).
  1. Se iniciará el [instalador de la aplicación](app-deploy-app-installer.md).
  1. Seleccione el botón **Instalar**.
  1. Después de la instalación correcta, encontrará Microsoft Edge Beta, Dev o Canary como entradas independientes en la lista **Todas las aplicaciones** del menú Inicio.

**Instalación desde el equipo con el Portal de dispositivos Windows (requiere que el [modo de desarrollador](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) esté habilitado en HoloLens 2)**
  1. En su PC, visite la [página de descarga de Edge Insider](https://www.microsoftedgeinsider.com/download).
  1. Seleccione el **botón de flecha desplegable** situado junto al botón "Descargar para Windows 10" del canal de Edge Insider que desee instalar.
  1. Seleccione **HoloLens 2** en el menú desplegable.
  1. Guarde el archivo .msix en la carpeta "Descargas" del equipo (u otra carpeta que pueda encontrar fácilmente).
  1. Use el [Portal de dispositivos de Windows ](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) del equipo para instalar el archivo .msix descargado en su HoloLens 2.
  1. Después de la instalación correcta, encontrará Microsoft Edge Beta, Dev o Canary como entradas independientes en la lista **Todas las aplicaciones** del menú Inicio.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Uso de WDAC para bloquear la nueva versión de Microsoft Edge

Los administradores de TI que quieran actualizar la [directiva WDAC](windows-defender-application-control-wdac.md) para bloquear la nueva versión de Microsoft Edge deberán agregar el siguiente contenido a la directiva.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Administración de puntos de conexión para la nueva versión de Microsoft Edge

Algunos entornos pueden tener restricciones de red que deberán tenerse en cuenta. Para garantizar una experiencia sin problemas con la nueva versión de Edge, [habilite estos puntos de conexión de Microsoft](/deployedge/microsoft-edge-security-endpoints).

Obtenga más información sobre los [puntos de conexión disponibles actualmente para HoloLens](hololens-offline.md).

### <a name="install-web-apps"></a>Instalación de aplicaciones web
 > [!Note]
>A partir de [Windows Holographic, versión 21H1](hololens-release-notes.md#windows-holographic-version-21h1), la aplicación web de Office ya no vendrá preinstalada.

Puede usar la nueva versión de Edge para instalar aplicaciones web junto con aplicaciones de Microsoft Store. Por ejemplo, puede instalar la aplicación web de Microsoft Office para ver y editar archivos hospedados en SharePoint o OneDrive. Para instalar la aplicación web de Office, visite https://www.office.com y seleccione el botón **Aplicación disponible** o **Instalar Office** en la barra de direcciones. Seleccione **Instalar** para confirmar.

> [!IMPORTANT]
> La funcionalidad de la aplicación web de Office solo está disponible cuando su HoloLens 2 tiene una conexión activa a Internet.

### <a name="webxr-and-360-viewer"></a>WebXR y 360 Viewer

La nueva versión de Microsoft Edge es compatible con WebXR, el nuevo estándar para crear experiencias web envolventes que reemplaza a WebVR. Muchas experiencias web envolventes se diseñaron pensando en la realidad virtual (reemplazan el campo de vista por un entorno virtual), pero también son compatibles con HoloLens 2. El estándar WebXR también permite experiencias web envolventes de realidad aumentada y mixta que usan su entorno físico. A medida que los desarrolladores dediquen más tiempo a WebXR, se prevé que lleguen nuevas experiencias envolventes de realidad mixta y aumentada que los clientes de HoloLens 2 podrán probar.

La extensión 360 Viewer se basa en WebXR y se instala automáticamente junto con la nueva versión de Microsoft Edge en HoloLens 2. Esta extensión web le ofrece la posibilidad de sumergirse en vídeos en 360 grados. YouTube ofrece la mayor selección de vídeos en 360°, por lo que le recomendamos que empiece ahí.

#### <a name="how-to-use-webxr"></a>Cómo se usa WebXR

1. Vaya a un sitio web compatible con WebXR.
1. Seleccione el botón **Enter VR** (Entrar en VR) en el sitio web. La ubicación y la representación visual de este botón pueden variar según el sitio web, pero puede tener un aspecto similar al siguiente:

    ![Ejemplo del botón para entrar a VR.](images/75px-enter-vr.png)

1. La primera vez que intente iniciar una experiencia de WebXR en un dominio específico, el explorador pedirá su consentimiento para acceder a una vista inmersiva; seleccione **Permitir**.
1. Use [gestos de HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame) para manipular la experiencia.
1. Si la experiencia no tiene un botón **Salir**, use el [gesto Inicio](hololens2-basic-usage.md#start-gesture) para volver al inicio.

**Ejemplos recomendados de WebXR**
- 360 Viewer (consulte la sección siguiente)
- [XR Dinosaurs](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>Uso de 360 Viewer

1. Vaya a un vídeo en 360 grados en YouTube.
1. En el fotograma de vídeo, seleccione el botón de casco de realidad mixta:

    ![Botón para activar 360 Viewer.](images/enter-360-viewer.jpg)

1. La primera vez que intente iniciar 360 Viewer en un dominio específico, el explorador pedirá su consentimiento para acceder a una vista inmersiva. seleccione **Permitir**.
1. [Pulse en el aire](hololens2-basic-usage.md#select-using-air-tap) para abrir los controles de reproducción. Use los [haces de mano y pulse en el aire](hololens2-basic-usage.md#select-using-air-tap) para reproducir o pausar, avanzar o retroceder, activar o desactivar subtítulos, o detener la experiencia (y salir de la vista inmersiva). Los controles de reproducción desaparecerán después de unos segundos de inactividad.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Principales problemas conocidos de WebXR y 360 Viewer
- En función de la complejidad de la experiencia de WebXR, puede que la velocidad de fotogramas oscile o se reduzca.
- La compatibilidad con las articulaciones de las manos en WebXR no está habilitada de forma predeterminada. Los desarrolladores pueden habilitar la compatibilidad `edge://flags` a través de activando "WebXR Hand Input".
- Es posible que los vídeos en 360° de sitios web que no sean YouTube no funcionen según lo previsto.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Comentarios sobre WebXR y 360 Viewer

Comparta los comentarios y errores con nuestro equipo por medio de la característica **Enviar comentarios** de la nueva versión de Microsoft Edge.

### <a name="new-settings-app"></a>Nueva aplicación Configuración

Con esta versión, vamos a presentar una nueva versión de la aplicación Configuración aplicación. Esta nueva aplicación incluye nuevas características y configuraciones expandidas para HoloLens 2 en áreas como Sonido, Inicio/apagado y suspensión, Red e Internet, Aplicaciones, Cuentas o Accesibilidad, entre otras.

> [!NOTE]
> Dado que la nueva aplicación Configuración es distinta de su versión anterior, las ventanas de Configuración que se colocaron anteriormente en el entorno se quitarán tras la actualización.

![Página principal de la nueva aplicación Configuración.](images/new-settings-app.png)

**Nuevas características y opciones**
- Búsqueda de opciones: puede buscar opciones en la página principal de Configuración mediante palabras clave o el nombre de la opción.
- Sistema > Sonido:
  - Dispositivos de audio de entrada y salida: elija de forma independiente los dispositivos de audio de entrada y salida (por ejemplo, escuche audio a través de auriculares Bluetooth o use un micrófono USB-C para la entrada de audio).
    > [!NOTE]
    > HoloLens 2 no admite micrónfonos Bluetooth.
  - Volumen de la aplicación: puede ajustar el volumen de cada aplicación de forma independiente. Consulte [Control de volumen por aplicación](#per-app-volume-control).
- Sistema > Inicio/apagado y suspensión: elija si desea que el dispositivo entre en suspensión tras un período de inactividad.
- Sistema > Batería: habilite manualmente el modo de ahorro de batería o establezca un umbral de batería a partir del cual se active automáticamente el modo de ahorro de batería.
- Dispositivos > USB: puede deshabilitar las conexiones USB de forma predeterminada.
- Red e Internet:
  - Ahora los adaptadores Ethernet USB-C aparecerán en Red e Internet.
  - La configuración del adaptador Ethernet USB-C ya está disponible, incluida su dirección IP.
  - Ahora puede habilitar el modo avión en HoloLens 2.
- Aplicaciones: puede restablecer las aplicaciones predeterminadas que se usan para los tipos de archivo y de vínculo. Para obtener más información, consulte [Selector de aplicaciones predeterminadas](#default-app-picker).
- Cuentas > Otros usuarios: los propietarios de dispositivos pueden agregar usuarios, actualizar usuarios estándar a propietarios de dispositivos, degradar los propietarios de dispositivos a usuarios estándar y quitar usuarios.
- Accesibilidad: se puede cambiar el tamaño del texto y algunos efectos visuales.

**Problemas conocidos**
- Se quitarán las ventanas de Configuración colocadas anteriormente (consulte la nota anterior).
- Ya no puede cambiar el nombre del dispositivo con la aplicación Configuración. Los administradores de TI pueden cambiar el nombre de los dispositivos mediante la plantilla de nombres de dispositivo [Windows Autopilot para HoloLens 2](hololens2-autopilot.md) o el nodo Ext/Microsoft/DNSComputerName del [CSP DevDetail](/windows/client-management/mdm/devdetail-csp) de MDM.
- La página Ethernet muestra un dispositivo Ethernet virtual ("UsbNcm") en todo momento.
- Puede que la información sobre el uso de batería de la nueva versión de Microsoft Edge no sea precisa, debido a su naturaleza como una aplicación de escritorio Win32 compatible con un nivel de adaptador de UWP (no se prevé ninguna corrección en breve).

#### <a name="display-color-calibration"></a>Calibración del color de la pantalla



Con esta nueva configuración, puede seleccionar un perfil de color alternativo para la HoloLens 2 pantalla. Esto puede ayudar a que los colores se vean más precisos, especialmente con niveles de brillo de pantalla inferiores. La calibración de color para mostrar se puede encontrar en Configuración aplicación, en la página System > Calibration (Calibración del sistema).

> [!NOTE]
> Dado que esta opción guarda un nuevo perfil de color en el firmware de la pantalla, se trata de una opción por dispositivo (y no única de cada cuenta de usuario).

##### <a name="how-to-use-display-color-calibration"></a>Uso de la calibración de color de la pantalla

1. Inicie la aplicación **Configuración** y vaya a **Sistema > Calibración**.
1. En **Calibración de color de la pantalla**, seleccione el botón **Run display color calibration** (Ejecutar calibración de color de la pantalla).
1. Se inicia la experiencia de calibración de color de la pantalla y se le apremia a asegurarse de que el visor está en la posición correcta.
1. Después de avanzar por los cuadros de diálogo de instrucciones, la pantalla se atenúa automáticamente al 30 % de brillo.
    > [!TIP]
    > Si tiene problemas para ver la escena atenuada en el entorno, puede ajustar manualmente el nivel de brillo de HoloLens 2 mediante los botones de brillo del lado izquierdo del dispositivo.
1. Seleccione los botones 1 a 6 para probar al instante cada perfil de color; busque el que sea mejor para su vista (suele ser el perfil que ayuda a que la escena parezca más neutra, con el patrón de escala de grises y los tonos de la máscara con el aspecto esperado).

    ![Escena de calibración de color de la pantalla.](images/color-cal-ui.png)
    
1. Cuando esté satisfecho con el perfil seleccionado, seleccione el botón **Guardar y salir**.
1. Si prefiere no realizar cambios, seleccione el botón **Cancelar y salir** para que se reviertan los cambios.

> [!TIP]
> Estas son algunas recomendaciones útiles que debe tener en cuenta al usar la configuración de calibración de color de la pantalla:
> - Puede volver a ejecutar la calibración de color de la pantalla desde Configuración cada vez que quiera.
> - Si algún usuario del dispositivo ha usado antes la configuración para cambiar perfiles de color, la fecha y hora del cambio más reciente se refleja en la página Configuración.
> - Al volver a ejecutar la calibración de color de la pantalla, se resalta el perfil de color que se guardó anteriormente y el perfil 0 no aparece (ya que el perfil 0 representa el perfil de color original de la pantalla).
> - Si quiere revertir al perfil de color original de la pantalla, puede hacerlo desde la página Configuración (vea [Restablecimiento del perfil de color)](#how-to-reset-color-profile).

##### <a name="how-to-reset-color-profile"></a>Restablecimiento del perfil de color 

Si no está satisfecho con el perfil de color personalizado guardado en HoloLens 2, puede restaurar el perfil de color original del dispositivo:
1. Inicie la aplicación **Configuración** y vaya a **Sistema > Calibración**.
1. En **Calibración de color de la pantalla**, seleccione el botón **Reset to default color profile** (Restablecer perfil de color predeterminado).
1. Cuando se abra el cuadro de diálogo, si está listo para reiniciar HoloLens 2 y aplicar los cambios, seleccione **Reiniciar**.

#### <a name="top-display-color-calibration-known-issues"></a>Principales problemas conocidos de calibración de color de la pantalla

- En la página Configuración, la cadena de estado que le indica cuándo se cambió por última vez el perfil de color estará des actualizada hasta que vuelva a cargar esa página de Configuración.
    - Solución alternativa: seleccione otra página de Configuración y luego vuelva a seleccionar la página Calibración.

#### <a name="default-app-picker"></a>Selector de aplicaciones predeterminadas

Al activar un hipervínculo o abrir un tipo de archivo con más de una aplicación instalada, que lo admite, verá una nueva ventana abierta en la que se le pedirá que seleccione qué aplicación instalada debe controlar el tipo de archivo o vínculo. En esta ventana, también puede elegir que la aplicación seleccionada controle el tipo de archivo o vínculo "Una vez" o "Siempre".

Si elige "Siempre" pero más adelante quiere cambiar la aplicación que controla un tipo de archivo o vínculo determinado, puede restablecer los valores predeterminados guardados en **Configuración > Aplicaciones**. Desplácese hasta la parte inferior de la página y seleccione el botón **Borrar** en "Default apps for file types" (Aplicaciones predeterminadas para tipos de archivos) o "Default apps for link types" (Aplicaciones predeterminadas para tipos de vínculos). A diferencia de la configuración similar en equipos de escritorio, no se pueden restablecer los valores predeterminados de un tipo de archivo individual.

#### <a name="per-app-volume-control"></a>Control de volumen por aplicación

Ahora, en Windows compilación, los usuarios pueden ajustar manualmente el nivel de volumen de cada aplicación. Esto permite a los usuarios centrarse mejor en las aplicaciones que lo necesitan o escuchar mejor cuando usan varias aplicaciones. Por ejemplo, cuando se tiene que bajar el volumen de una aplicación mientras se llama a alguien para conseguir asistencia remota en otra.

Para establecer el volumen de una aplicación individual, vaya a **Configuración** -> **Sistema** -> **Sonido** y en Advanced sound options (Opciones avanzadas de sonido), seleccione **App volume and device preferences** (Volumen de la aplicación y preferencias del dispositivo).<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Deslizamiento para escribir

A algunos clientes les resulta más rápido "escribir" en teclados virtuales al deslizar la forma de la palabra que pretenden escribir y estamos haciendo una vista previa de esta característica para el teclado holográfico. Puede deslizar una palabra a la vez pasando la punta del dedo por el plano del teclado holográfico, deslizando la forma de la palabra y, a continuación, retirando la punta del dedo del plano del teclado. Puede deslizar las palabras que siguen sin necesidad de presionar la barra espaciadora si quita el dedo del teclado entre palabras. Se sabe que la característica funciona si se ve una estela de deslizamiento que sigue el movimiento del dedo sobre el teclado.

Tenga en cuenta que esta característica puede ser difícil de usar y dominar debido a la naturaleza del teclado holográfico, donde no se siente resistencia contra el dedo (a diferencia de la pantalla de un teléfono móvil). 

### <a name="power-menu-from-start"></a>Menú de encendido desde Inicio

Un nuevo menú que permite al usuario cerrar sesión, apagar y reiniciar el dispositivo. Un indicador de la pantalla Inicio de HoloLens que muestra si hay disponible una actualización del sistema.

#### <a name="how-to-use"></a>Cómo se usa

1. Abra la pantalla Inicio de HoloLens con el [gesto Inicio](hololens2-basic-usage.md#start-gesture) o diga "Ir a Inicio".

2. Observe el icono de puntos suspensivos (...) junto a la imagen de perfil del usuario:<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Seleccione la imagen de perfil del usuario con las manos o el comando de voz "Encender".

4. Aparece un menú con opciones para cerrar sesión, reiniciar o apagar el dispositivo:<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Seleccione las opciones de menú para cerrar sesión, reiniciar o apagar HoloLens. Es posible que la opción Cerrar sesión no esté disponible si el dispositivo está configurado para una [única cuenta Microsoft (MSA) o local](hololens-identity.md).

6. Descarte el menú mediante un toque en cualquier otro lugar o cierre el menú Inicio con el gesto Inicio.

#### <a name="update-indicator"></a>Indicador de actualización

Cuando hay una actualización disponible, el icono de puntos suspensivos se enciende para indicar que un reinicio instalará la actualización Las opciones de menú también cambian para reflejar la presencia de la actualización.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Varios usuarios enumerados en la pantalla de inicio de sesión

Anteriormente, en la pantalla Inicio de sesión solo se mostraba el usuario que ha iniciado sesión más recientemente, así como un punto de entrada "Otro usuario". Hemos recibido comentarios de los clientes que no son suficientes si varios usuarios han iniciado sesión en el dispositivo. Todavía tenían que volver a escribir su nombre de usuario, etc.

Introducido en esta compilación Windows, al  seleccionar Otro usuario que se encuentra a la derecha del campo de entrada del PIN, la pantalla Inicio de sesión mostrará varios usuarios con que han iniciado sesión previamente en el dispositivo. Esto permite a los usuarios seleccionar su perfil de usuario y, a continuación, iniciar sesión con sus credenciales Windows Hello usuario. También se puede agregar un nuevo usuario al dispositivo desde esta página Otros usuarios mediante el **botón Agregar** cuenta.

En el menú Otros usuarios, el botón Otros usuarios mostrará el último usuario que ha iniciado sesión en el dispositivo. Seleccione este botón para volver a la pantalla Inicio de sesión de este usuario.

![Pantalla de inicio de sesión predeterminada.](./images/multiusers1.jpg)

<br>

![Pantalla de inicio de sesión de otros usuarios.](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Compatibilidad con micrófono externo USB-C

> [!IMPORTANT]
> La conexión de **un micrófono USB no lo establecerá automáticamente como dispositivo de entrada**. Al conectar un conjunto de cascos USB-C, los usuarios observarán que el audio del micrófono se redirigirá automáticamente a los cascos, pero el sistema operativo HoloLens da prioridad a la matriz de micrófonos interna por encima de cualquier otro dispositivo de entrada. **Para usar un micrófono USB-C, siga los pasos que se indican a continuación.**

Los usuarios pueden seleccionar micrófonos externos conectados a USB-C mediante el panel de configuración **Sonido**. Los micrófonos USB-C se pueden usar para llamar, grabar, etc.

Abra la aplicación **Configuración** y seleccione **Sistema** > **Sonido**.

![Configuración de Sonido.](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Para usar micrófonos externos con **Remote Assist**, los usuarios tendrán que hacer clic en el hipervínculo "Manage sound devices" (Administrar dispositivos de sonido).
>
> A continuación, use la lista desplegable para establecer el micrófono externo como **Predeterminado** o **Communications Default (Predeterminado de comunicaciones)** . Si elige **Predeterminado**, el micrófono externo se usará en todas partes.
>
> Si elige **Communications Default** (Predeterminado de comunicaciones), el micrófono externo se usará en Remote Assist y en otras aplicaciones de comunicaciones, pero en las demás tareas se podrá seguir usando la matriz de micrófonos de HoloLens.

![Administrar dispositivos de sonido.](images/usbc-mic-2.png)

<br>

![Establecer el valor predeterminado del micrófono.](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>¿Se admiten los micrófonos Bluetooth?

Desafortunadamente Bluetooth todavía no se admiten micrófonos en HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Solución de problemas de micrófonos USB-C

Tenga en cuenta que algunos micrófonos USB-C se informan incorrectamente como micrófono *y* como altavoz. Se trata de un problema con el micrófono y no con HoloLens. Al conectar uno de estos micrófonos a HoloLens, es posible que se pierda el sonido. Afortunadamente, hay una corrección simple.  

En **Configuración** sonido del sistema , establezca explícitamente los altavoces integrados (controlador de audio de características  ->    ->   **análogas)** como **el dispositivo predeterminado**. HoloLens recordar esta configuración incluso si el micrófono se quita y se vuelve a conectar más adelante.

![Solución de problemas de micrófonos USB-C.](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Inicio de sesión automático de visitante para quioscos

Esta nueva característica permite usar el inicio de sesión automático en las cuentas de visitante para los modos de quiosco.

Para una configuración que no es de AAD, para configurar un dispositivo para el inicio de sesión automático del visitante:

1. Cree un paquete de aprovisionamiento que:
    1. Configura los valores **de Runtime/AssignedAccess para** permitir las cuentas de visitante.
    1. Opcionalmente, inscribe el dispositivo en MDM (Configuración del entorno de **ejecución/Área de trabajo/Inscripciones)** para que se pueda administrar más adelante.
    1. No crear una cuenta local
1. [Aplique el paquete de aprovisionamiento](hololens-provisioning.md).

En el caso de una configuración de AAD, los usuarios pueden lograr algo parecido a esto hoy sin este cambio. Los dispositivos unidos a AAD configurados para el modo de pantalla completa pueden iniciar sesión en una cuenta de visitante con un solo clic en la pantalla de inicio de sesión. Una vez que haya iniciado sesión en la cuenta de visitante, el dispositivo no volverá a solicitar el inicio de sesión hasta que el visitante haya iniciado sesión explícitamente desde el menú Inicio o se reinicie el dispositivo.

El inicio de sesión automático del visitante se puede administrar a través [de la directiva OMA-URI](/mem/intune/configuration/custom-settings-windows-10) personalizada:

- Valor de URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Directiva  | Descripción   | Configurations  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Permite que un visitante inicie sesión automáticamente en un quiosco.   | 1 (Sí), 0 (No, valor predeterminado).  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Uso de las nuevas aplicaciones Configuración y Edge en los modos de pantalla completa

Al incluir [](hololens-kiosk.md)aplicaciones en quioscos, un administrador de TI suele agregar la aplicación al quiosco, pero con su identificador de modelo de usuario de aplicación (AUMID). Dado que la aplicación Configuración y la aplicación Microsoft Edge se consideran nuevas aplicaciones y son diferentes de las aplicaciones anteriores, los quioscos que usan AUMID para esas aplicaciones tendrán que actualizarse para usar el nuevo AUMID.

Al modificar un quiosco para incluir las nuevas aplicaciones, se recomienda agregar en el nuevo AUMID, así como dejar la antigua. Esto creará una transición sencilla cuando los usuarios actualicen el sistema operativo y no necesitarán recibir nuevas directivas para seguir usando la pantalla completa según lo previsto.

| Aplicación                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Aplicación Configuración anterior       | HolographicSystemSettings_cw5n1h2txyewy! Aplicación            |
| Nueva Configuración app       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! Aplicación |
| Aplicación Microsoft Edge anterior | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| Nueva Microsoft Edge aplicación | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Cambios de comportamiento del modo de pantalla completa para el control de errores

En compilaciones anteriores, si un dispositivo tuviera una configuración de quiosco, que es una combinación de acceso asignado global y acceso asignado a miembros del grupo de AAD, si se genera un error en la determinación de la pertenencia a un grupo de AAD, el usuario vería["no](hololens-kiosk.md#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode)se muestra nada en el menú inicio".

A partir de esta Windows, la experiencia de quiosco se reservará a la configuración global de quiosco (si existe) en caso de errores durante el modo de pantalla completa del grupo de AAD.

### <a name="new-settings-uris-for-page-settings-visibility"></a>Nuevos Configuración URI para la visibilidad de Configuración página

En [Windows Holographic, versión 20H2,](hololens-release-notes.md#windows-holographic-version-20h2) agregamos la directiva [Configuración/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir las páginas que se ven en la Configuración aplicación. PageVisibilityList es una directiva mediante la cual los administradores de TI pueden evitar que páginas específicas de la aplicación Configuración del sistema sean visibles o accesibles, o bien aplicar dicha restricción a todas las páginas salvo las especificadas.

Si visita [Page Configuración Visibility](settings-uri-list.md), puede encontrar instrucciones para usar este CSP y la lista de URI disponibles en versiones anteriores.

Vamos a ampliar la lista de los URI de Configuración disponibles, que los administradores de TI pueden administrar. Algunos de estos URI son para las áreas recién disponibles dentro de la nueva Configuración aplicación. Si usa la directiva Configuración/PageVisibilityList, revise la lista siguiente y ajuste las páginas permitidas o bloqueadas según sea necesario.

> [!NOTE]
> **En desuso: ms-settings:network-proxy**
>
> Una página de configuración está en desuso en estas compilaciones más recientes. La antigua **página & proxy de Internet** ya no está disponible como configuración  >   global. La nueva configuración de proxy por conexión se puede encontrar en Propiedades de Red **&**  >  **Wi-Fi** de Internet o Propiedades de Red  >   & Ethernet de   >    >  **Internet.**

<br>

| Página Configuración                                        | Identificador URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Características > Aplicaciones & aplicaciones                               | `ms-settings:appsfeatures`                         |
| Aplicaciones > Aplicaciones & características > opciones avanzadas          | `ms-settings:appsfeatures-app`                     |
| Aplicaciones > sin conexión                                  | `ms-settings:maps`                                 |
| Aplicaciones > sin conexión > descargar mapas                  | `ms-settings:maps-downloadmaps`                    |
| Dispositivos > Mouse                                      | `ms-settings:mouse`                                |
| Dispositivos > USB                                        | `ms-settings:usb`                                  |
| Modo & conexión a Internet > avión                   | `ms-settings:network-airplanemode`                 |
| Privacidad > general                                    | `ms-settings:privacy-general`                      |
| Personalización de > ink & privacidad             | `ms-settings:privacy-speechtyping`                 |
| Movimiento de > privacidad                                     | `ms-settings:privacy-motion`                       |
| Bordes de > captura de pantalla de privacidad                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Aplicaciones y capturas > privacidad                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Batería del > sistema                                     | `ms-settings:batterysaver`                         |
| Batería del > sistema                                     | `ms-settings:batterysaver-settings`                |
| Sonido de > sistema                                       | `ms-settings:sound`                                |
| System > Sound > App volume and device preferences (Preferencias de volumen y dispositivo de System > Sound > App) | `ms-settings:apps-volume`                          |
| System > Sound > Manage sound devices              | `ms-settings:sound-devices`                        |
| System > Storage > Configure Storage Sense         | `ms-settings:storagepolicies`                      |
| Hora & idioma > fecha & hora                        | `ms-settings:dateandtime`                          |
| Time & Language > Keyboard                           | `ms-settings:keyboard`                             |
| Idioma & idioma de > tiempo                           | `ms-settings:language`                             |
| Idioma & idioma de > tiempo                           | `ms-settings:regionlanguage-languageoptions`       |
| Actualización de & seguridad > restablecimiento & recuperación               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>URI actualizados

Anteriormente, los dos URI siguientes no llevarían a un usuario directamente a las páginas indicadas, sino que solo bloqueaban la página de actualizaciones principales. Los siguientes elementos se han actualizado para dirigirse a sus páginas:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Configuración de diagnósticos de reserva mediante Configuración aplicación

Ahora, Configuración aplicación, un usuario puede configurar el comportamiento de [Diagnósticos de reserva.](hololens-diagnostic-logs.md) En la Configuración, vaya a la página **Solución** de problemas  ->  **de** privacidad para configurar esta opción.

> [!NOTE]
> Si hay una directiva MDM configurada para el dispositivo, el usuario no podrá invalidar ese comportamiento.  

### <a name="share-things-with-nearby-devices"></a>Compartir cosas con dispositivos cercanos

Comparta cosas con dispositivos cercanos Windows 10, incluidos los equipos y otros HoloLens 2 dispositivos. Puede probarlo en experiencias compartidas Configuración sistema para compartir archivos o direcciones URL de un HoloLens  ->    ->   a un equipo. Para obtener más información, lea más sobre cómo compartir [cosas con dispositivos cercanos en Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Esta característica se puede administrar a [través de Connectivity/AllowConnectedDevices.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)

### <a name="new-os-diagnostic-traces"></a>Nuevos seguimientos de diagnóstico del sistema operativo

Además de los solucionadores de problemas anteriores dentro de la aplicación Configuración, se ha agregado un nuevo solucionador de problemas con la adición de la nueva aplicación Configuración para las actualizaciones del sistema operativo. Vaya **a** Configuración  ->  **solución de problemas &amp; de seguridad**  >    >  **de Windows update y** seleccione **Iniciar.** Esto le permite recopilar seguimientos mientras reproduce el problema con las actualizaciones del sistema operativo para ayudar a solucionar mejor problemas con el equipo de TI o el soporte técnico.

### <a name="delivery-optimization-preview"></a>Versión preliminar de la optimización de la distribución

Con esta HoloLens, Windows Holographic for Business la configuración de optimización de entrega para reducir el consumo de ancho de banda para las descargas de varios HoloLens dispositivos. Puede obtener una descripción más completa de esta funcionalidad junto con la configuración de red recomendada en [Optimización de distribución para actualizaciones de Windows 10](/windows/deployment/update/waas-delivery-optimization).

Las siguientes opciones se habilitan como parte de la superficie de administración y [se pueden configurar desde Intune](/mem/intune/configuration/delivery-optimization-settings):

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Algunas advertencias sobre esta oferta en versión preliminar:

- La compatibilidad de HoloLens está limitada en esta versión preliminar a actualizaciones del sistema operativo.
- Windows Holographic for Business solo admite modos de descarga HTTP y descargas desde un [punto de conexión de Caché conectada de Microsoft](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache); en estos momentos no se admiten modos de descarga punto a punto ni asignaciones de grupos para dispositivos HoloLens.
- HoloLens no admite la optimización de la implementación ni de la entrega para puntos de conexión de Windows Server Update Services.
- Para solucionar el problema, será necesario realizar un diagnóstico en el servidor de Caché conectada o recopilar un seguimiento en HoloLens mediante **Configuración** > **Actualización y seguridad** >  **Solución de problemas** >  **Windows Update**.

### <a name="it-admin---update-checklist"></a>Administrador de TI: lista de comprobación de actualización

Esta lista de comprobación le ayudará a conocer los nuevos elementos que se van a agregar en esta actualización de características que pueden afectar a las configuraciones actuales de administración de dispositivos o a las nuevas características que podría empezar a usar.

#### <a name="updates-to-kiosk-mode"></a>Actualizaciones en pantalla completa

✔️ nuevos [**AUMID para nuevas aplicaciones en pantalla completa:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Si anteriormente usaba la aplicación Configuración o Microsoft Edge en un quiosco, hemos reemplazado estas aplicaciones por nuevas aplicaciones que usan un identificador de aplicación diferente. Le recomendamos encarecidamente que lea [a continuación Nuevos AUMID para nuevas aplicaciones en el modo de pantalla](#use-the-new-settings-and-edge-apps-in-kiosk-modes) completa. Esto garantizará que sigue teniendo la aplicación Configuración en el quiosco o que incluye la nueva aplicación Microsoft Edge pantalla. Estos cambios se pueden realizar ahora, implementarse en todos los dispositivos y permitir una transición más fluida en la actualización.

✔️ [**inicio de sesión automático del visitante para quioscos:**](#visitor-auto-logon-for-kiosks) 

Ahora, los visitantes pueden iniciar sesión automáticamente en un quiosco. Este comportamiento está en modo predeterminado, pero se puede administrar y deshabilitar.

✔️ se [**ha mejorado el modo de pantalla completa al entregar**](#kiosk-mode-behavior-changes-for-handling-of-failures):

Si no se determina correctamente la pertenencia a un grupo de AAD del usuario de AAD que ha iniciado sesión, se usa la configuración global de quiosco para el menú Inicio (si está presente). De lo contrario, el usuario se presenta con el menú inicio vacío. Aunque el menú de inicio vacío no es una configuración que se puede establecer directamente, este nuevo control puede ser algo para informar al departamento de soporte técnico si usa quioscos, ya que esto puede aplicarse a las configuraciones o puede que desee realizar nuevos ajustes en las configuraciones de acceso asignadas.

#### <a name="updates-to-page-settings-visibility"></a>Actualizaciones de la visibilidad Configuración página

✔️ [**nuevos Configuración URI para la visibilidad de Configuración página**](#new-settings-uris-for-page-settings-visibility)

Si actualmente usa Page [Configuración Visibility,](settings-uri-list.md) es posible que desee realizar ajustes en los URI existentes que haya permitido o bloqueado.

#### <a name="updates-for-your-wdac-policy"></a>Actualizaciones de la directiva WDAC
✔️ Si anteriormente estaba bloqueando Microsoft Edge a través de WDAC, querrá actualizar la directiva de WDAC. Revise lo siguiente y use el código de ejemplo proporcionado.
#### <a name="enable-new-endpoints-for-edge"></a>Habilitación de nuevos puntos de conexión para Edge
✔️ Si tiene una infraestructura que implica la configuración de puntos de conexión de red como proxy o firewall, habilite estos nuevos puntos de conexión para la nueva Microsoft Edge aplicación.

#### <a name="newly-configurable-items"></a>Elementos recién configurables

✔️ configurar [diagnósticos de reserva:](#configuring-fallback-diagnostics-via-settings-app)puede configurar si y quién puede recopilar diagnósticos de reserva.

✔️ compartir[cosas con dispositivos cercanos:](#share-things-with-nearby-devices)puede deshabilitar la nueva característica de uso compartido cercano.

✔️ configuración de directivas para el nuevo [Microsoft Edge:](#configuring-policy-settings-for-the-new-microsoft-edge)revise las configuraciones recién disponibles para Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Nueva herramienta de diagnóstico

✔️ nuevos[seguimientos de diagnóstico del](#new-os-diagnostic-traces)sistema operativo: recopile registros relacionados con las actualizaciones del sistema operativo.

### <a name="improvements-and-fixes-in-the-update"></a>Mejoras y correcciones en la actualización:

- [Los diagnósticos sin](hololens-diagnostic-logs.md#offline-diagnostics) conexión también incluirán información adicional del dispositivo para el número de serie y la versión del sistema operativo.
- Corrige un problema en torno a la implementación de aplicaciones de línea de negocio a través de paquetes de aprovisionamiento en tiempo de ejecución.
- Corrige un problema en torno a los informes de estado de instalación de aplicaciones de línea de negocio.
- Corrige un problema en torno a la persistencia de los nuevos paquetes de aplicación en los restablecimientos de dispositivo.
- Corrige un problema que podría dar lugar a que se escriban símbolos incorrectos en Edge para los clientes japoneses.
- Mejora la resistencia de las actualizaciones del sistema operativo en torno a aplicaciones preinstaladas, como Edge. 
- Aborda una confiabilidad de actualizaciones que afecta a la instalación de Microsoft Edge. 


## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic, versión 20H2: actualización de mayo de 2021
- Compilación 19041.1146

Mejoras y correcciones en la actualización:
- Esta actualización de calidad mensual no contiene ningún cambio importante, le recomendamos que pruebe nuestra compilación más reciente, Windows Holographic, versión 21H1.

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

- Soluciona un problema por el que la Configuración se bloquea al intentar cambiar una contraseña para una cuenta local.


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
- Soluciona un problema en torno a las actualizaciones y los vuelos de versiones HoloLens versiones posteriores.
- Se han quitado los certificados preinstalados no usados del almacén raíz de eSIM de HoloLens dispositivos.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, versión 1903: actualización de febrero de 2021
- Compilación 18362.1098

Esta actualización de calidad mensual no contiene ningún cambio importante, le recomendamos que pruebe nuestras compilaciones más recientes para Windows Holographic, versión 2004.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, versión 20H2: actualización de enero de 2021
- Compilación 19041.1134

Mejoras y correcciones en la actualización:

- Se ha mejorado el rendimiento durante el inicio, la reanudación y el cambio de usuario cuando hay muchos usuarios en el dispositivo.
- Se ha agregado compatibilidad con arm32 para el [modo de investigación](/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode).

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, versión 1903: actualización de enero de 2021
- Compilación 18362.1091

Esta actualización de calidad mensual no contiene ningún cambio importante, le recomendamos que pruebe nuestras compilaciones más recientes para Windows Holographic, versión 2004.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, versión 20H2: actualización de diciembre de 2020
- Compilación 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalación de aplicaciones en HoloLens 2 a través de Instalador de aplicación

Vamos a **agregar una nueva funcionalidad (Instalador de aplicación)** para que pueda instalar aplicaciones más fácilmente en los dispositivos HoloLens 2 dispositivos. La característica estará en **modo predeterminado para dispositivos no administrados.** Para evitar interrupciones en las empresas, el instalador de aplicaciones no **estará disponible para dispositivos administrados** en este momento.  

Un dispositivo se considera "administrado" si **se** cumple alguna de las siguientes condiciones:
- Inscrito [en](hololens-enroll-mdm.md) MDM
- Configurado con el [paquete de aprovisionamiento](hololens-provisioning.md)
- Identidad [de usuario](hololens-identity.md) Azure AD

Ahora puede instalar aplicaciones sin necesidad de habilitar el modo de desarrollador ni usar Portal de dispositivos.  Simplemente descargue (a través de USB o a través de Edge) el paquete de Appx en el dispositivo y vaya al paquete de Appx en el Explorador de archivos para que se le pida que arranque la instalación.  Como alternativa, [inicie una instalación desde una página web](/windows/msix/app-installer/installing-windows10-apps-web).  Al igual que las aplicaciones que instala desde Microsoft Store o la instalación local mediante la funcionalidad de [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) implementación de [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) aplicaciones LOB de MDM, las aplicaciones deben estar firmadas digitalmente con la herramienta de firma y el certificado que se usa para firmar debe ser de confianza para el dispositivo HoloLens antes de que se pueda implementar la aplicación.

**Instrucciones de instalación de la aplicación.**

1.  Asegúrese de que el dispositivo no se considera administrado.
1.  Asegúrese de que HoloLens 2 dispositivo esté encendido y conectado al equipo.
1.  Asegúrese de que ha iniciado sesión en el HoloLens 2 dispositivo.
1.  En el equipo, vaya a la aplicación personalizada y copie yourapp.appxbundle en yourdevicename\Internal Storage\Downloads.   Una vez que haya terminado de copiar el archivo, puede desconectar el dispositivo.
1.  En el HoloLens 2, abra el menú Inicio, seleccione Todas las aplicaciones e inicie Explorador de archivos aplicación.
1.  Vaya a la carpeta Descargas. En el panel izquierdo de la aplicación, seleccione Este dispositivo en primer lugar y, a continuación, vaya a Descargas.
1.  Seleccione el archivo yourapp.appxbundle.
1.  La Instalador de aplicación se iniciará. Seleccione el botón Instalar para instalar la aplicación.
La aplicación instalada se iniciará automáticamente al finalizar la instalación.

Puede encontrar aplicaciones de ejemplo en [Windows ejemplos universales GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) probar este flujo.

Obtenga información sobre el proceso completo de [instalación de aplicaciones en HoloLens 2 con el Instalador de aplicación](app-deploy-app-installer.md).  

![Instalación de ejemplos de MRTK mediante Instalador de aplicación.](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Mejoras y correcciones en la actualización:

- El seguimiento de manos ahora mantiene el seguimiento en muchos casos nuevos en los que se habría perdido la mano anteriormente.  En algunos de estos nuevos casos, solo la posición de la mano sigue actualando en función de la mano real del usuario, mientras que las demás uniones se deducen en función de una posición anterior.  Este cambio ayuda a mejorar la coherencia del seguimiento en movimientos como abofeteos, lanzamientos, arrobaciones y alachas.  También ayuda en los casos en los que la mano está cerca de una superficie o donde se mantiene un objeto.  Cuando se inferan las [](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) uniones de mano, el valor de precisión por conjunto se establecerá en "Aproximado" en lugar de "Alto".
- Se ha corregido un problema por el que el restablecimiento del PIN Azure AD las cuentas mostraría un error "Algo salió mal.
- Los usuarios deben ver mucho menos bloqueos de OOBE posteriores al arranque al iniciar ET, Iris desde la aplicación de configuración, nuevo usuario o notificación del sistema.
- Los usuarios deben tener una zona horaria correcta que salga de OOBE.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, versión 1903: actualización de diciembre de 2020
- Compilación 18362.1088

Esta actualización de calidad mensual no contiene ningún cambio importante, le recomendamos que pruebe nuestra última actualización de Windows Holographic, versión 20H2 - Diciembre de 2020 y la nueva característica Instalador de aplicación agregada en la compilación.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, versión 20H2
- Compilación 19041.1128

Windows Holographic, versión 20H2 ya está disponible y ofrece un gran conjunto de nuevas características para HoloLens 2 usuarios y profesionales de IT. Desde el posicionamiento automático de los ojos, hasta el Administrador de certificados en Configuración, la funcionalidad mejorada del modo quiosco y las nuevas funcionalidades de configuración de Autopilot. Esta nueva actualización permite a los equipos de IT tomar un control más pormenorizados para configurar y administrar dispositivos HoloLens y ofrece a los usuarios experiencias holográficas aún más fluidas. 

Esta versión más reciente es una actualización mensual de la versión 2004, pero esta vez se incluyen nuevas características. El número de compilación principal seguirá siendo el mismo y Windows Update indicará una versión mensual de la versión 2004 (compilación 19041). Puede ver el número de compilación en la pantalla Configuración > Acerca de para confirmar que se encuentra en la última compilación disponible 19041.1128+. Para actualizar a la versión más reciente, abra la aplicación Configuración, vaya a Actualizar & Seguridad y pulse Buscar actualizaciones. Para obtener más información sobre cómo administrar HoloLens actualizaciones, visite [Administrar HoloLens actualizaciones.](hololens-updates.md)

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Novedades de Windows Holographic, versión 20H2  

| Característica                                              | Descripción                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Compatibilidad con posicionamiento automático de los ojos](hololens-release-notes.md#auto-eye-position-support) | Calcula activamente las posiciones de los ojos sin que los usuarios pasen por la calibración de Eye Tracking.   |
| [Administrador de certificados](hololens-release-notes.md#certificate-manager)   | Permite que los nuevos métodos más sencillos instalen y quiten certificados de la Configuración aplicación.     |
| [Aprovisionamiento de inicio automático desde USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | El aprovisionamiento de paquetes en unidades USB solicita automáticamente la página de aprovisionamiento en OOBE.                                                         |
| [Confirmación automática de paquetes de aprovisionamiento en OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Los paquetes de aprovisionamiento se aplican automáticamente durante la OOBE desde la página de aprovisionamiento.                                                         |
| [Aprovisionamiento automático sin usar la interfaz de usuario](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Cómo combinar el inicio automático de aprovisionamiento y la confirmación automática juntos. |
| [Uso de Autopilot con Wi-Fi conexión](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Use Autopilot desde el dispositivo Wi-Fi sin necesidad de adaptador Ethernet. |
| [TenantLockdown CSP y Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Una vez aplicada la inscripción de inquilinos y la directiva, el dispositivo solo se puede inscribir en ese inquilino cada vez que se restablezca o se vuelva a parpadear el dispositivo. |
| [Acceso asignado global](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Nuevo método de configuración para el modo de pantalla completa de varias aplicaciones que aplica la pantalla completa en el nivel del sistema, lo que lo hace aplicable a todos.                  |
| [Inicio automático de una aplicación en quiosco de varias aplicaciones](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Establece una aplicación que se iniciará automáticamente al iniciar sesión en un modo de pantalla completa de varias aplicaciones.                                                        |
| [Cambios de comportamiento del modo de pantalla completa para el control de errores](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | El error del modo de pantalla completa ahora tiene una reserva restrictiva.                                                                                                |
| [HoloLens Políticas](hololens-release-notes.md#hololens-policies)                                    | Nuevas directivas para HoloLens.     |
| [Pertenencia a grupos Azure AD caché para quiosco sin conexión](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | La nueva directiva permite a los usuarios usar la caché de pertenencia a grupos para usar el modo quiosco sin conexión durante un número establecido de días.                                        |
| [Nuevas directivas de restricción de dispositivos para HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Directivas de administración de dispositivos habilitadas recientemente para HoloLens 2.                                                                                |
| [Nuevas directivas de energía para HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Directivas recién admitidas para la configuración de tiempo de espera de energía.  |
| [Actualizar directivas](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Directivas recién habilitadas que permiten el control de las actualizaciones.           |
| [Se ha Configuración visibilidad de página para HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Directiva para elegir qué páginas se ven en Configuración aplicación.             |
| [Modo de investigación](hololens-release-notes.md#research-mode) | Uso del modo investigación en HoloLens 2. |
| [Se ha aumentado la longitud de la grabación](hololens-release-notes.md#recording-length-increased) | Las grabaciones de MRC ya no se han límite a 5 minutos. |
| [Mejoras y correcciones en la actualización](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Correcciones adicionales en la actualización.   |

### <a name="auto-eye-position-support"></a>Compatibilidad con posicionamiento automático de los ojos

En HoloLens 2, las posiciones de los ojos permiten un posicionamiento preciso del holograma, una experiencia de visualización cómoda y una calidad de visualización mejorada. Las posiciones de los ojos se calculan internamente como parte del análisis del seguimiento ocular. Sin embargo, para ello es necesario que cada usuario complete la calibración del seguimiento ocular, incluso en aquellos casos en los que la experiencia no requiera una entrada con la mirada.

El **posicionamiento automático de los ojos** posibilita estos escenarios sin necesidad de interacción para calcular las posiciones de los ojos del usuario. La posición del ojo automático comienza a funcionar en segundo plano automáticamente desde el momento en que el usuario coloca el dispositivo. Si el usuario no tiene una calibración de seguimiento de los ojos anterior, la posición del ojo automático comenzará a proporcionar las posiciones de los ojos del usuario al sistema de visualización después de un tiempo de procesamiento de 20 a 30 segundos. Los datos de usuario no se conservan en el dispositivo y, por lo tanto, este proceso se repite si el usuario despeda y vuelve a activar el dispositivo o si el dispositivo se reinicia o se reactiva de la suspensión.

Cuando un usuario sin calibrar se coloca el dispositivo, la característica de posicionamiento automático de los ojos provoca algunos cambios en el comportamiento del sistema. En este contexto, un usuario sin problemas hace referencia a alguien que no ha pasado por el proceso de calibración del seguimiento de los ojos en el dispositivo anteriormente.

| Aplicación activa | Comportamiento anterior | Comportamiento a partir de la versión 20H2 Update de Windows Holographic |
|:-------------------|:-----------------|:-----------------------------------|
| Aplicación no habilitada para la mirada o shell de Holographic |Se muestra el cuadro de diálogo de solicitud de calibración del seguimiento ocular. | No se muestra ningún mensaje. |
| Aplicación habilitada para la mirada | Se muestra el cuadro de diálogo de solicitud de calibración del seguimiento ocular. | La solicitud de calibración del seguimiento ocular solo se muestra cuando la aplicación accede a la secuencia de mirada. |

Si el usuario pasa de una aplicación con la opción de mirada no habilitada a otra que tiene acceso a los datos de mirada, se mostrará la solicitud de calibración. 

El resto del comportamiento del sistema será similar a cuando el usuario actual no tenga una calibración de seguimiento de los ojos activa. Por ejemplo, el gesto De inicio con una mano no se habilitará. No se cambiará la experiencia inmediata de la configuración inicial.

En el caso de las experiencias que requieren datos de mirada con los ojos o una posición holográfica muy precisa, se recomienda que los usuarios sin problemas ejecuten la calibración del seguimiento de los ojos. Es accesible desde el símbolo del sistema de calibración de seguimiento de los ojos o iniciando la aplicación Configuración desde el menú Inicio y seleccionando **System > Calibration > Eye Calibration > Run eye calibration**.

Esta información se puede encontrar más adelante con [otra información de calibración](hololens-calibration.md#auto-eye-position-support). 

### <a name="certificate-manager"></a>Administrador de certificados

- Se han mejorado las herramientas de auditoría, diagnóstico y validación para la seguridad y el cumplimiento de dispositivos mediante el nuevo Administrador de certificados. Esta funcionalidad le permitirá implementar, solucionar problemas y validar los certificados a escala en entornos comerciales.

En Windows holographic versión 20H2, vamos a agregar un administrador de certificados en la HoloLens 2 Configuración aplicación. Vaya a **Configuración > Update & Security > Certificates**. Esta característica proporciona una manera sencilla y fácil de ver, instalar y quitar certificados en el dispositivo. Con el nuevo Administrador de certificados, los administradores y los usuarios ahora tienen herramientas mejoradas de auditoría, diagnóstico y validación para garantizar que los dispositivos sigan siendo seguros y compatibles. 

-   **Auditoría:** Capacidad de validar que un certificado se ha implementado correctamente o de confirmar que se quitó correctamente. 
-   **Diagnóstico:** Cuando surgen problemas, validar que existen los certificados adecuados en el dispositivo ahorra tiempo y ayuda a solucionar problemas. 
-   **Validación:** Comprobar que un certificado cumple el propósito previsto y es funcional, puede ahorrar mucho tiempo, especialmente en entornos comerciales antes de implementar certificados a mayor escala.

Para buscar rápidamente un certificado específico en la lista, hay opciones para ordenar por nombre, almacén o fecha de expiración. Los usuarios también pueden buscar directamente un certificado. Para ver las propiedades de certificado individuales, seleccione el certificado y haga clic en **Información**. 

La instalación de certificados admite actualmente archivos .cer y .crt. Los propietarios de dispositivos pueden instalar certificados en la máquina local y el usuario actual.  todos los demás usuarios solo pueden instalar en el usuario actual. Los usuarios solo pueden quitar certificados instalados directamente desde la interfaz Configuración usuario. Si un certificado se ha instalado a través de otros medios, también debe quitarse mediante el mismo mecanismo.

#### <a name="to-install-a-certificate"></a>Para instalar un certificado: 

1.  Conectar el HoloLens 2 a un equipo.
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

![Visor de certificados en la Configuración aplicación.](images/certificate-viewer-device.jpg)

![Imagen que muestra cómo usar la interfaz de usuario de certificado para instalar un certificado.](images/certificate-device-install.jpg)

Esta información se puede encontrar más adelante [en una nueva página del Administrador de certificados](certificate-manager.md).

### <a name="auto-launch-provisioning-from-usb"></a>Aprovisionamiento de inicio automático desde USB

- Procesos automatizados que permiten una menor interacción del usuario cuando se usan unidades USB con paquetes de aprovisionamiento durante la OOBE.

Antes de esta versión, los usuarios tenían que iniciar la pantalla de aprovisionamiento manualmente durante la OOBE para aprovisionar mediante una combinación de botones. Ahora los usuarios pueden omitir la combinación de botones mediante un paquete de aprovisionamiento en una unidad de almacenamiento USB. 

1. Conecte la unidad USB con el paquete de aprovisionamiento durante el primer momento interactuable de OOBE.
1. Cuando el dispositivo esté listo para aprovisionarse, se abrirá automáticamente el símbolo del sistema con la página de aprovisionamiento. 

Nota: Si una unidad USB se deja conectada mientras el dispositivo arranca, OOBE enumerará el dispositivo de almacenamiento USB existente, así como observará si hay otras adicionales conectadas.

Para obtener más información sobre cómo aplicar paquetes de aprovisionamiento durante la OOBE, visite la [HoloLens de aprovisionamiento.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Puede encontrar información adicional [sobre el aprovisionamiento de](hololens-provisioning.md#auto-launch-provisioning-from-usb) inicio automático desde un USB en la HoloLens de aprovisionamiento.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Confirmación automática de paquetes de aprovisionamiento en OOBE
- Proceso automatizado que permite una menor interacción del usuario; cuando se muestra la página Paquete de aprovisionamiento, se aplicarán automáticamente todos los paquetes enumerados.

Cuando aparece la pantalla principal de aprovisionamiento, la OOBE se cuenta como 10 segundos antes de empezar automáticamente a aplicar todos los paquetes de aprovisionamiento. Los usuarios todavía [pueden confirmar o cancelar en](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) estos 10 segundos después de comprobar los paquetes que esperaban.

### <a name="automatic-provisioning-without-using-ui"></a>Aprovisionamiento automático sin usar la interfaz de usuario
- Procesos automáticos combinados para interacciones reducidas de dispositivos para el aprovisionamiento. 

Al combinar el inicio automático del aprovisionamiento desde dispositivos USB y la confirmación automática de los paquetes de aprovisionamiento, un usuario puede aprovisionar dispositivos HoloLens 2 automáticamente sin usar la interfaz de usuario del dispositivo ni siquiera llevar el dispositivo. Puede seguir usando la misma unidad USB y el mismo paquete de aprovisionamiento para varios dispositivos. Esto resulta útil para implementar varios dispositivos a la vez en la misma área. 

1. [Cree un paquete de aprovisionamiento](hololens-provisioning.md) [mediante Windows Diseñador de configuración](https://www.microsoft.com/store/productId/9NBLGGH4TX22)de . 
1. Copie el paquete en una unidad de almacenamiento USB.
1. [Flash your HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) to [19041.1361 or newer build](https://aka.ms/hololens2previewdownload). 
1. Cuando [Advanced Recovery Companion haya](https://www.microsoft.com/store/productId/9P74Z35SFRS8) terminado de parpadear el dispositivo, desconecte el cable USB-C. 
1. Conecte la unidad USB al dispositivo.
1. Cuando el HoloLens 2 arranque en OOBE, detectará automáticamente el paquete de aprovisionamiento en la unidad USB e iniciará la página de aprovisionamiento.
1. Después de 10 segundos, el dispositivo aplicará automáticamente el paquete de aprovisionamiento. 

El dispositivo ya está configurado y mostrará [la pantalla Aprovisionamiento correcto](hololens-provisioning.md#automatic-provisioning-without-using-ui).

### <a name="using-autopilot-with-wi-fi-connection"></a>Uso de Autopilot con Wi-Fi conexión
- Se ha quitado la necesidad de adaptadores USB-C a Ethernet, lo que reduce las necesidades de hardware, ya que permite que Autopilot funcione en Wi-Fi dispositivos conectados.

Ahora, durante la OOBE, una vez que HoloLens 2 con Wi-Fi, OOBE buscará un perfil de Autopilot para el dispositivo. Si se encuentra uno, se usará para completar el resto del flujo de inscripción y unión de AAD. En otras palabras, el uso de ethernet a USB-C o el adaptador Wi-Fi a USB-C ya no es un requisito, pero siguen funcionando si se proporcionan al principio de OOBE. Obtenga más información sobre [Autopilot para HoloLens 2 dispositivos](hololens2-autopilot.md).

### <a name="tenantlockdown-csp-and-autopilot"></a>TenantLockdown CSP y Autopilot
- Mantiene los dispositivos en el inquilino de la organización bloqueándolos en el inquilino incluso a través del restablecimiento o el reflash del dispositivo. Con mayor seguridad al no permitir la creación de cuentas a través del aprovisionamiento. 

HoloLens 2 dispositivos ahora admiten csp de TenantLockdown a partir [Windows holographic versión 20H2.](hololens-release-notes.md#windows-holographic-version-20h2) 

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP permite que HoloLens 2 se vincule a la inscripción de MDM usando solo Autopilot. Una vez que el nodo RequireNetworkInOOBE de TenantLockdown CSP se establezca con un valor "true" o "false" (establecido inicialmente) en HoloLens 2, el valor permanecerá en el dispositivo incluso en caso de reprogramación, actualización del sistema operativo, etc. 

Si el nodo RequireNetworkInOOBE de TenantLockdown CSP se establece con un valor "true" en HoloLens 2, la OOBE esperará indefinidamente a que el perfil de Autopilot se descargue y aplique correctamente, después de conectarse a la red. 

Si el nodo RequireNetworkInOOBE de TenantLockdown CSP se establece con un valor "true" en HoloLens 2, no se permitirán las siguientes operaciones en la OOBE: 
- Creación de usuarios locales mediante aprovisionamiento en el tiempo de ejecución 
- Realización de operaciones de unión de Azure AD mediante aprovisionamiento en el tiempo de ejecución 
- Selección del propietario del dispositivo en la experiencia OOBE 

#### <a name="how-to-set-this-using-intune"></a>¿Cómo se configura con Intune? 
1. Cree un perfil de configuración de dispositivos OMA-URI personalizado y especifique "true" para el nodo RequireNetworkInOOBE, tal y como se muestra a continuación.
El valor OMA-URI debe ser "./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE".

   > [!div class="mx-imgBorder"]
   > ![Configuración de un bloqueo de inquilinos mediante OMA-URI.](images/hololens-tenant-lockdown.png)

1. Cree un grupo de dispositivos y asígnele el perfil de configuración de dispositivos. 

1. Haga que el dispositivo HoloLens 2 sea miembro del grupo creado en el paso anterior y desencadene la sincronización.  

Compruebe en el portal de Intune que la configuración de dispositivos se haya aplicado correctamente. Una vez que la configuración de dispositivos se aplique correctamente al dispositivo HoloLens 2, se activarán los efectos de TenantLockdown.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>¿Cómo se desactiva el nodo RequireNetworkInOOBE de TenantLockdown en HoloLens 2 usando Intune? 
1. Quite HoloLens 2 del grupo de dispositivos al que ha asignado anteriormente la configuración creada. 

1. Cree un perfil de configuración de dispositivos basado en OMA-URI personalizado y especifique "false" para RequireNetworkInOOBE, tal y como se muestra a continuación. El valor OMA-URI debe ser "./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE".

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla en la que RequireNetworkInOOBE se establece en "false" mediante OMA-URI en Intune.](images/hololens-tenant-lockdown-false.png)

1. Cree un grupo de dispositivos y asígnele el perfil de configuración de dispositivos.

1. Haga que el dispositivo HoloLens 2 sea miembro del grupo creado en el paso anterior y desencadene la sincronización.

Compruebe en el portal de Intune que la configuración de dispositivos se haya aplicado correctamente. Una vez que la configuración de dispositivos se aplique correctamente al dispositivo HoloLens 2, se desactivarán los efectos de TenantLockdown.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>¿Qué sucedería durante la OOBE si el perfil de Autopilot no está asignado a un HoloLens después de haber establecido en "true" TenantLockdown? 
La OOBE esperará indefinidamente a que se descargue el perfil de Autopilot y se mostrará el siguiente cuadro de diálogo. Para eliminar los efectos de TenantLockdown, el dispositivo debe haberse inscrito primero con su inquilino usando únicamente Autopilot, y RequireNetworkInOOBE debe haberse desactivado tal y como se describe en el paso anterior, antes de que se eliminen las restricciones introducidas por TenantLockdown CSP.

![Vista en el dispositivo cuando se aplica en este la directiva.](images/hololens-autopilot-lockdown.png)

Esta información se puede encontrar junto con el resto de Autopilot en [TENANTLOCKDOWN CSP y Autopilot](hololens2-autopilot.md#tenant-lockdown-csp-and-autopilot).

### <a name="global-assigned-access--kiosk-mode"></a>Acceso asignado global: pantalla completa
- Se ha reducido la administración de identidades para quiosco, al habilitar el nuevo método de quiosco que aplica el modo de pantalla completa en el nivel del sistema.

Esta nueva característica permite a un administrador de TI configurar un dispositivo HoloLens 2 para el modo de pantalla completa de varias aplicaciones que es aplicable en el nivel del sistema, no tiene afinidad con ninguna identidad en el sistema y se aplica a todos los usuarios que inician sesión en el dispositivo. Obtenga información detallada sobre esta nueva característica en HoloLens [pantalla completa](hololens-kiosk.md).

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Inicio automático de una aplicación en pantalla completa con varias aplicaciones 
- Experiencia centrada en el inicio automático de aplicaciones, lo que aumenta aún más la interfaz de usuario y las selecciones de aplicaciones elegidas para las experiencias de pantalla completa.

Solo se aplica al modo de pantalla completa de varias aplicaciones y solo se puede designar una aplicación para el inicio automático mediante el atributo resaltado a continuación en la configuración de acceso asignado.

La aplicación se inicia automáticamente cuando el usuario inicia sesión.

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Cambios de comportamiento del modo de pantalla completa para el control de errores
- Modo quiosco más seguro mediante la eliminación de las aplicaciones disponibles en los errores de pantalla completa. 

Anteriormente, al encontrar errores en la aplicación del modo de pantalla completa, HoloLens para mostrar todas las aplicaciones en el menú Inicio. Ahora, Windows holographic versión 20H2 en caso de errores, no se mostrará ninguna aplicación en el menú inicio como se indica a continuación:

![Imagen del modo de pantalla completa que ahora se ve cuando se produce un error.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens Políticas

- Opciones de administración de dispositivos específicamente HoloLens creadas para administrar el dispositivo. 

Se han creado nuevas directivas de realidad mixta para HoloLens 2 dispositivos en Windows Holographic versión 20H2. Entre las nuevas opciones controlables se incluyen: establecer el brillo, establecer el volumen, deshabilitar la grabación de audio en capturas de realidad mixta, establecer cuándo se pueden recopilar diagnósticos y la caché de pertenencia a grupos de AAD.  

| Nueva directiva HoloLens directiva                                | Descripción                                                                               | Notas                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Permite deshabilitar los botones de brillo para que al presionarlo no cambie el brillo.       | 1 Sí, 0 No (valor predeterminado)                                                |
| MixedReality\VolumeButtonDisabled                  | Permite deshabilitar los botones de volumen para que al presionarlo no cambie el volumen.               | 1 Sí, 0 No (valor predeterminado)                                                |
| MixedReality\MicrophoneDisabled                    | Deshabilita el micrófono para que no sea posible grabar audio en HoloLens 2.                      | 1 Sí, 0 No (valor predeterminado)                                                |
| MixedReality\FallbackDiagnostics                   | Controla el comportamiento de cuando se pueden recopilar registros de diagnóstico.                               | 0 Deshabilitado, 1 Habilitado para propietarios de dispositivos, 2 Habilitado para todos (valor predeterminado) |
| MixedReality\HeadTrackingMode                      | Reservado para uso futuro.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Controla cuántos días se Azure AD caché de pertenencia a grupos para la pantalla completa que tiene como destino Azure AD grupos. | Véase a continuación.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Pertenencia a grupos Azure AD caché para quiosco sin conexión
- Quioscos sin conexión habilitados para usarse con grupos de AAD durante un máximo de 60 días.

Esta directiva controla durante cuántos días se puede usar Azure AD caché de pertenencia a grupos para las configuraciones de acceso asignado que tienen como destino Azure AD grupos de usuarios que han iniciado sesión. Una vez que este valor de directiva se establece en un valor mayor que 0, solo se usa la memoria caché; de lo contrario, no.  

Nombre: AADGroupMembershipCacheValidityInDays VALOR DE URI: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Mín. - 0 días  
Máximo: 60 días 

Pasos para usar esta directiva correctamente: 
1. Cree un perfil de configuración de dispositivo para la pantalla completa Azure AD grupos y asígnelo a HoloLens dispositivos. 
1. Cree una configuración de dispositivo personalizada basada en uri de OMA que establece este valor de directiva en el número deseado de días (> 0) y asígnelo a HoloLens dispositivos. 
    1. El valor uri debe especificarse en el cuadro de texto OMA-URI como ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. El valor puede estar entre mínimo y máximo permitido.
1. Inscriba HoloLens dispositivos y compruebe que ambas configuraciones se aplican al dispositivo. 
1. Deje Azure AD inicio de sesión del usuario 1 cuando Internet esté disponible, una vez que el usuario inicie sesión y Azure AD la pertenencia Azure AD un grupo se confirme correctamente, se creará la memoria caché. 
1. Ahora Azure AD usuario 1 puede desconectar HoloLens y usarlo para el modo de pantalla completa siempre que el valor de directiva permita X número de días. 
1. Los pasos 4 y 5 se pueden repetir para cualquier otro usuario de Azure AD N. La clave aquí es que cualquier usuario de Azure AD debe iniciar sesión en el dispositivo mediante Internet, por lo que al menos una vez podemos determinar Azure AD que son miembros de un grupo al que está destinada la configuración de quiosco. 
 
> [!NOTE]
> Hasta que se realice el paso 4 para un Azure AD usuario experimentará un comportamiento de error mencionado en entornos "desconectados". 

### <a name="new-device-restriction-policies-for-hololens-2"></a>Nuevas directivas de restricción de dispositivos para HoloLens 2
- Permite a los usuarios administrar directivas de administración de dispositivos específicas, como bloquear la adición o eliminación de paquetes de aprovisionamiento.

Directivas recién habilitadas que permiten más opciones de administración de HoloLens 2 dispositivos. 
- [AllowAddProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](/windows/client-management/mdm/remotelock-csp)

Estas dos nuevas políticas para AllowAddProvisioningPackage y AllowRemoveProvisioningPackage se agregan a nuestras [restricciones de dispositivos comunes.](hololens-common-device-restrictions.md)

> [!NOTE]
> En lo que respecta [a RemoteLock,](/windows/client-management/mdm/remotelock-csp)HoloLens solo admitirá la configuración ./Vendor/MSFT/RemoteLock/Lock. No se admiten las configuraciones que se tratan con el PIN, como el restablecimiento y la recuperación.

### <a name="new-power-policies-for-hololens-2"></a>Nuevas directivas de energía para HoloLens 2
- Más opciones para cuando HoloLens suspensión o bloqueos a través de directivas de energía. 

Estas directivas recién agregadas permiten a los administradores controlar los estados de energía, como el tiempo de espera de inactividad. Para obtener más información sobre cada directiva individual, haga clic en el vínculo de esa directiva.

|     Vínculo a la documentación de la directiva                |     Notas                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Valor de ejemplo que se usará en Windows Configuration Designer, es decir,`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Valor de ejemplo que se usará en Windows Configuration Designer, es decir,`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Valor de ejemplo que se usará Windows Diseñador de configuración, es decir, 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Valor de ejemplo que se usará Windows Diseñador de configuración, es decir, 100                                                                          |
|     [StandbyTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Valor de ejemplo que se usará en Windows Configuration Designer, es decir,`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Valor de ejemplo que se usará en Windows Configuration Designer, es decir,`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Estas dos nuevas políticas para DisplayOffTimeoutOnBattery y DisplayOffTimeoutPluggedIn se agregan a nuestras [restricciones de dispositivos comunes.](hololens-common-device-restrictions.md)

> [!NOTE]
> Para obtener una experiencia coherente HoloLens 2, asegúrese de que los valores de DisplayOffTimeoutOnBattery y StandbyTimeoutOnBattery se establecen como el mismo valor. Lo mismo se aplica a DisplayOffTimeoutPluggedIn y StandbyTimeoutPluggedIn. Consulte [Visualización, suspensión e hibernación de temporizadores inactivos](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) para obtener más detalles sobre el modo de espera moderno.

### <a name="newly-enabled-update-policies-for-hololens"></a>Directivas de actualización recién habilitadas para HoloLens
- Más opciones para cuando se instalan actualizaciones o deshabilita el botón Pausar actualizaciones para garantizar las actualizaciones.

Estas directivas de actualización ahora están habilitadas en HoloLens 2 dispositivos:
-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Los detalles completos sobre estas directivas de actualización y cómo usarlas para HoloLens dispositivos se pueden leer aquí en Administración de [HoloLens actualizaciones.](hololens-updates.md)

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Se ha Configuración visibilidad de página para HoloLens 2
- Mayor control de la interfaz de usuario Configuración aplicación, que puede confundirse para mostrar una selección limitada de páginas.

Ahora hemos habilitado una directiva que permite a los administradores de TI impedir que páginas específicas de la aplicación System Configuración sean visibles o accesibles, o bien hacerlo para todas las páginas excepto las especificadas. Para obtener información sobre cómo personalizar completamente esta característica, haga clic en el vínculo siguiente.

- [PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Para saber qué configuración de página puede personalizar en HoloLens 2, visite nuestra página de Configuración [URI.](settings-uri-list.md) 
 
![Captura de pantalla de la modificación de las horas activas en la aplicación Configuración.](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Modo de investigación
Mientras está en el modo de investigación, el HoloLens 2 se convierte en una herramienta para la investigación de computer vision. En comparación con las ediciones anteriores, el modo de investigación HoloLens 2 tiene las siguientes ventajas:
-   Además de los sensores expuestos en el modo de investigación HoloLens (1.ª generación), ahora se proporciona acceso al sensor IMU, incluido un acelerómetro, un giroscopio y un magnetómetro.
-   HoloLens 2 proporciona nuevas funcionalidades que se pueden usar junto con el modo de investigación. En concreto, el acceso a las API de seguimiento de manos y seguimiento de los ojos articuladas que pueden ofrecer un conjunto más completo de experimentos.

Los investigadores ahora tienen la opción de habilitar el modo de investigación en sus dispositivos HoloLens acceder a todos estos flujos de sensores de imagen sin procesar orientados externamente. El modo de investigación HoloLens 2 también proporciona acceso a las lecturas del acelerómetro, el giroscopio y el magnetómetro. Para proteger la privacidad de los usuarios, las imágenes de cámara de seguimiento de los ojos sin procesar no están disponibles a través del modo de investigación, pero la dirección de la mirada con los ojos está disponible a través de las API existentes.

Consulte la documentación [del modo de investigación para](/windows/mixed-reality/research-mode) obtener más detalles técnicos.

### <a name="recording-length-increased"></a>Se ha aumentado la longitud de la grabación
Debido a los comentarios de los clientes, hemos aumentado la longitud de grabación de las capturas [de realidad mixta.](holographic-photos-and-videos.md) Las capturas de realidad mixta ya no se limitarán a 5 minutos de forma predeterminada, sino que calcularán la longitud máxima de grabación en función del espacio disponible en disco. El dispositivo calculará la duración máxima de la grabación de vídeo en función del espacio en disco disponible hasta el 80 % del espacio total en disco.

> [!NOTE]
> El HoloLens la grabación de vídeo predeterminada (5 minutos) si se produce una de las siguientes situaciones:
> - La duración máxima estimada de la grabación es menor que los 5 minutos predeterminados.
> - El espacio en disco disponible es inferior al 20 % del espacio total en disco.

Puede encontrar todos los requisitos en nuestra documentación [de fotos y vídeos holográficos.](holographic-photos-and-videos.md#maximum-recording-length) 

### <a name="improvements-and-fixes-in-the-update"></a>Mejoras y correcciones en la actualización:
- Ahora hay más pantallas en modo oscuro en OOBE.
- Más información sobre el contenido debe apuntar a la declaración de privacidad más reciente en línea.
- Se ha corregido un problema por el que los usuarios no podían aprovisionar perfiles de VPN a través de paquetes de aprovisionamiento.
- Se ha corregido un problema de configuración de proxy para la conexión VPN.
- Se ha actualizado la directiva para deshabilitar la enumeración de funciones USB a través de MDM para NCM para AllowUsbConnection.
- Se ha corregido un problema que impedía que un dispositivo HoloLens se mostrara en Explorador de archivos a través del Protocolo de transferencia multimedia (MTP) cuando el dispositivo se configuraba como un quiosco de una sola [aplicación.](hololens-kiosk.md) Tenga en cuenta que MTP (y la conexión USB en general) todavía se pueden deshabilitar mediante la [directiva AllowUSBConnection.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
- Se ha corregido un problema por el que los iconos del menú Inicio se escalaban correctamente en modo de pantalla completa.
- Se ha corregido un problema debido a que el almacenamiento en caché HTTP interfiere con el modo de pantalla completa destinado a Azure AD grupos.
- Se ha corregido un problema por el que los usuarios no podían usar el botón Emparejar después de habilitar el modo de desarrollador con paquetes de aprovisionamiento a menos que se deshabilitara y se vuelva a habilitar el modo de desarrollador.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, versión 1903: actualización de noviembre de 2020
- Compilación 18362.1085

Esta actualización de calidad mensual no contiene ningún cambio importante; le recomendamos que pruebe nuestra última compilación de la versión de características Windows Holographic, versión 20H2.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic, versión 2004: actualización de octubre de 2020
- Compilación 19041.1124
 
Mejoras y correcciones en la actualización:

- Se ha quitado una comprobación innecesaria que produjo un error del sistema en tiempo de ejecución.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic, versión 1903: actualización de octubre de 2020
- Compilación 18362.1081

Esta actualización de calidad mensual no contiene ningún cambio importante, le recomendamos que pruebe nuestras compilaciones más recientes para Windows Holographic, versión 2004.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, versión 2004: actualización de septiembre de 2020
- Compilación 19041.1117

Mejoras y correcciones en la actualización:

- Soluciona un problema que impedía Visual Studio depurar una aplicación cuando SupportsMultipleInstances="true" está presente en appxmanifest.
- Esta versión incluye la corrección de detección de proxy NCSI para solucionar la detección de Internet con errores a través del proxy de red. NCSI puede usar el proxy de máquina y el proxy por perfil para la detección de conectividad a Internet. El proxy por usuario será compatible con NCSI en una versión futura.
- En la mayoría Windows Mixed Reality dispositivos, el vector de dirección hacia delante es paralelo al suelo cuando la cabeza del usuario está en una posición neutra mirando hacia delante. Sin embargo, las versiones anteriores de HoloLens 2 alineaban el vector para que fuera horizontal a los paneles de visualización, que se inclina hacia abajo unos grados en relación con la orientación ideal. Las versiones más recientes HoloLens 2 lo han corregido para garantizar la coherencia semántica entre los factores de forma.
- Se ha mejorado la solidez del seguimiento de las manos, lo que dará lugar a menos pérdidas de seguimiento en escenarios específicos.
- Esta versión contiene una corrección para mejorar la calidad de la marca de tiempo de audio que puede haber contribuido a problemas de captura de vídeo.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, versión 1903: actualización de septiembre de 2020
- Compilación 18362.1079

Mejoras y correcciones en la actualización:

- En la mayoría Windows Mixed Reality dispositivos, el vector de dirección hacia delante es paralelo al suelo cuando la cabeza del usuario está en una posición neutra mirando hacia delante. Sin embargo, las versiones anteriores de HoloLens 2 alineaban el vector para que fuera horizontal a los paneles de visualización, que se inclina hacia abajo unos grados en relación con la orientación ideal. Las versiones más recientes HoloLens 2 lo han corregido para garantizar la coherencia semántica entre los factores de forma.
- Se ha mejorado la solidez del seguimiento de las manos, lo que dará lugar a menos pérdidas de seguimiento en escenarios específicos.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, versión 2004: actualización de agosto de 2020
- Compilación 19041.1113

Mejoras y correcciones en la actualización:

- Configuración aplicación ya no seguirá al usuario en las experiencias de inscripción de Iris o calibración de seguimiento de los ojos.
- Se ha corregido un error por el que al aplicar un paquete de aprovisionamiento durante la operación de OOBE que cambia el nombre del dispositivo y realiza otras acciones (como conectarse a una red), no se realizarían las demás acciones después del reinicio del dispositivo debido al cambio de nombre.
- Se ha modificado la combinación de colores de los flujos de configuración inicial del dispositivo para mejorar la calidad visual.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, versión 1903: actualización de agosto de 2020
- Compilación 18362.1074

Esta actualización de calidad mensual no contiene ningún cambio importante, le recomendamos que pruebe nuestras compilaciones más recientes para Windows Holographic, versión 2004.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, versión 2004: actualización de julio de 2020
- Compilación 19041.1109

Mejoras y correcciones en la actualización:

- Los desarrolladores ahora pueden elegir entre habilitar o deshabilitar Portal de dispositivos requieren una conexión segura.
- Se ha mejorado la confiabilidad para los inicios de aplicaciones después de las actualizaciones del sistema operativo.
- Se ha cambiado el brillo predeterminado de la bandeja de entrada al 100 %.
- Se ha corregido un problema sobre el reenvío HTTPS para el Windows Portal de dispositivos en HoloLens 2.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, versión 1903: actualización de julio de 2020
- Compilación 18362.1071

Mejoras y correcciones en la actualización:

- Se ha corregido un problema que podía hacer que los hologramas desapareciera en las aplicaciones de Unity al perder o recuperar el seguimiento.
- Se ha corregido un problema que provocaba que HoloLens aplicaciones exclusivas se bloqueara de nuevo en el shell mientras se usaba el HoloLens Emulator con aceleración de hardware en determinados dispositivos.
- Se ha corregido un problema relativo al reenvío HTTPS para el Windows Portal de dispositivos en HoloLens 2.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, versión 2004: actualización de junio de 2020
- Compilación 19041.1106

Mejoras y correcciones en la actualización:

- Las grabadoras MRC personalizadas ahora tienen nuevos valores predeterminados para determinadas propiedades si no se especifican.
  - En el *efecto de vídeo de MRC:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (casco envolvente))
  - En el *efecto de audio de MRC*:
    - LoopbackGain (el valor "Ganancia de audio de la aplicación" actual en la Captura de realidad mixta en Windows Portal de dispositivos)
    - MicrophoneGain (el valor actual de "Ganancia de audio de micrófono" en la página Captura de realidad mixta en Windows Portal de dispositivos)
- Se ha corregido un error para mejorar la calidad del audio en escenarios de captura de realidad mixta. En concreto, esta corrección debe eliminar los problemas de audio en la grabación cuando se muestra **el** menú Inicio.
- Se ha mejorado la estabilidad del holograma en los vídeos grabados.
- Se ha resuelto un problema por el que la captura de realidad mixta no podía grabar vídeo después de que el dispositivo se dejara en estado de espera durante varios días.
- La API HolographicSpace.UserPresence está deshabilitada generalmente para las aplicaciones de Unity. Este comportamiento evita un problema que provocaba que algunas aplicaciones se pausase cuando se volteó el visor, incluso si la configuración "Ejecutar en segundo plano" estaba habilitada. La API ahora está habilitada para las versiones 2018.4.18 y posteriores de Unity y 2019.3.4 y versiones posteriores.
- Al acceder a Portal de dispositivos a través de Wi-Fi conexión, un explorador web podría impedir el acceso a debido a un certificado no válido. El explorador podría notificar un error como "ERR_SSL_PROTOCOL_ERROR", incluso si el certificado del dispositivo era de confianza previa. En este caso, no puede avanzar a Portal de dispositivos, ya que no hay ninguna opción para omitir las advertencias de seguridad. Esta actualización resolvió el problema. Si el certificado de dispositivo se descargó previamente y era de confianza en un equipo para quitar las advertencias de seguridad del explorador y se produce el error SSL, el nuevo certificado debe descargarse y ser de confianza para solucionar las advertencias de seguridad del explorador.
- Se ha habilitado la capacidad de crear un paquete de aprovisionamiento en tiempo de ejecución que puede instalar una aplicación mediante paquetes MSIX.
- Se ha agregado una configuración **Configuración** system Hologramas que permite a los usuarios quitar automáticamente todos los hologramas de Mixed Reality inicio cuando el  >    >   dispositivo se apaga.
- Se ha corregido un problema que provocaba que HoloLens aplicaciones que cambiaran su formato de píxel para representarse en negro en el HoloLens emulador.
- Se ha corregido un error que provocaba un bloqueo durante el inicio de sesión de Iris.
- Se ha corregido un problema sobre las descargas repetidas de la tienda para las aplicaciones ya actuales.
- Se ha corregido un error para impedir que las aplicaciones inmersivas Microsoft Edge varias veces.
- Se ha corregido un problema con los inicios de Fotos aplicación en arranques iniciales después de actualizar desde la versión 1903.
- Rendimiento y confiabilidad mejorados.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, versión 1903: actualización de junio de 2020
- Compilación 18362.1064

Mejoras y correcciones en la actualización:

- Las grabadoras MRC personalizadas tienen nuevos valores predeterminados para determinadas propiedades si no se especifican.
  - En el *efecto de vídeo de MRC:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (casco envolvente))
  - En el *efecto de audio de MRC*:
    - LoopbackGain (el valor "Ganancia de audio de la aplicación" actual en la Captura de realidad mixta en Windows Portal de dispositivos)
    - MicrophoneGain (el valor actual de "Ganancia de audio de micrófono" en la página Captura de realidad mixta en Windows Portal de dispositivos)
- La API HolographicSpace.UserPresence está deshabilitada generalmente para las aplicaciones de Unity. Este comportamiento evita un problema que hace que algunas aplicaciones se detengan cuando se voltear el visor, incluso si la configuración para ejecutarse en segundo plano está habilitada. La API ahora está habilitada para las versiones 2018.4.18 y posteriores de Unity, y 2019.3.4 y versiones posteriores.
- Se ha corregido un problema que provocaba HoloLens aplicaciones que cambiaban su formato de píxel para representarse en negro en el HoloLens Emulator.
- Se ha corregido un problema sobre los inicios de Fotos aplicación en arranques iniciales después de actualizar desde la versión 1903.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, versión 2004  
- Compilación: 19041.1103

La actualización de software principal de mayo de 2020 para HoloLens 2, *Windows Holographic, versión 2004* incluye una gran cantidad de nuevas funcionalidades interesantes, como la compatibilidad con Windows Autopilot, el modo oscuro de la aplicación, la compatibilidad con USB Ethernet para zonas activas 5G/HOTSPOT y mucho más. Para actualizar a la versión más reciente, abra la aplicación **Configuración,** vaya a Update & Security y seleccione el   botón  **Buscar** ****   actualizaciones. 

|             Característica                              |          Descripción                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Configurar previamente y configurar sin problemas nuevos dispositivos para producción mediante Windows AutoPilot                 |
|       Compatibilidad con FIDO 2                             |          Compatibilidad con las claves de seguridad FIDO2 para habilitar la autenticación rápida y segura para dispositivos compartidos            |
|       Aprovisionamiento mejorado                      |          Aplicar sin problemas un paquete de aprovisionamiento desde una unidad USB a la HoloLens                              |
|       Estado de instalación de la aplicación                 |          Compruebe el estado de instalación en la Configuración aplicación para aplicaciones se han insertado en HoloLens 2 a través de MDM.               |
|       Proveedores de servicios de configuración (CSP)   |          Se han agregado nuevos proveedores de servicios de configuración para mejorar las funcionalidades de control de administración.                 |
|       Compatibilidad con USB 5G/LTE                       |          La funcionalidad Ethernet USB ampliada permite la compatibilidad con 5G/GIGABIT.                                    |
|       Modo de aplicación oscura                              |          Modo de aplicación oscura disponible para las aplicaciones que admiten los modos oscuro y claro, lo que mejora la experiencia de visualización.        |
|       Comandos de voz                             |          Compatibilidad con comandos de voz del sistema adicionales para controlar HoloLens manos libres                           |
|       Mejoras en el seguimiento de manos                 |          Las mejoras de seguimiento de manos hacen que los botones y las interacciones de pizarra 2D sea más precisa                        |
|       Mejoras y correcciones de calidad                 |          Diversas mejoras de rendimiento y confiabilidad del sistema en toda la plataforma                            |

### <a name="support-for-windows-autopilot"></a>Compatibilidad con Windows Autopilot

Windows Autopilot for HoloLens 2 permite que el canal de ventas del dispositivo se inscriba previamente HoloLens en el inquilino de Intune. Cuando llegan los dispositivos, están listos para implementarse automáticamente como dispositivos compartidos en el inquilino. Para aprovechar las ventajas de la implementación propia, el dispositivo debe conectarse a una red durante la primera pantalla de la configuración mediante un USB de C a Ethernet.

Una vez que un usuario inicia el proceso de implementación automática de Autopilot, el proceso completa los pasos siguientes:

1. Unir el dispositivo a Azure Active Directory (Azure AD).
1. Use Azure AD para inscribir el dispositivo en Microsoft Intune (u otro servicio MDM).
1. Descargue las directivas de destino del dispositivo, los certificados y los perfiles de red.
1. Aprovisionar el dispositivo.
1. Mostrar la pantalla de inicio de sesión al usuario.

Obtenga más información en la [Windows autopilot for HoloLens 2 evaluation guide](hololens2-autopilot.md)(Guía de evaluación de autopilot for HoloLens 2 ).

*Póngase en contacto con el administrador de cuentas para unirse ahora a la versión preliminar de AutoPilot. Los dispositivos listos para Autopilot comenzarán a enviarse pronto.*

### <a name="fido2-security-key-support"></a>Compatibilidad con la clave de seguridad FIDO2

Algunos usuarios comparten un HoloLens con otros en un entorno laboral o educativo. Por lo tanto, es importante que los usuarios puedan fácilmente sin escribir nombres de usuario y contraseñas largos. Fast Identity Online (FIDO) permite que cualquier usuario de su organización (inquilino de Azure AD) inicie sesión sin problemas en HoloLens sin escribir un nombre de usuario o contraseña.

Las claves de seguridad FIDO2 son un método de autenticación sin contraseña basado en estándares que puede estar en cualquier factor de forma. FIDO es un estándar abierto para la autenticación sin contraseña. Permite a los usuarios y organizaciones iniciar sesión en sus recursos sin un nombre de usuario o contraseña. En su lugar, usan una clave de seguridad externa o una clave de plataforma integrada en un dispositivo.

Para empezar, consulte Habilitación del inicio de sesión con clave [de seguridad sin contraseña.](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Inscripción de MDM mejorada a través del paquete de aprovisionamiento

Los paquetes de aprovisionamiento le permiten HoloLens configuración mediante un archivo de configuración en lugar de a través de HoloLens de serie. Anteriormente, los paquetes de aprovisionamiento tenían que copiarse en HoloLens memoria interna. Ahora pueden estar en una unidad USB, por lo que son más fáciles de reutilizar en varios dispositivos HoloLens y puede aprovisionar dispositivos en paralelo. Los paquetes de aprovisionamiento ahora también admiten un campo para inscribirse en la administración de dispositivos, por lo que no hay ninguna configuración manual después del aprovisionamiento.

Para probarlo:

1. Descargue la versión más reciente de Windows Configuration Designer desde Windows store en el equipo.
1. Seleccione **Aprovisionar HoloLens dispositivos**  >  **aprovisionar HoloLens 2 dispositivos**.
2. Compile el perfil de configuración. A continuación, copie todos los archivos que se crearon en un dispositivo de almacenamiento USB-C.
3. Conecte el dispositivo USB-C a cualquier HoloLens. A continuación, **presione los**  +  **botones de encendido del volumen** para aplicar el paquete de aprovisionamiento.

### <a name="line-of-business-application-install-status"></a>Estado de instalación de la aplicación de línea de negocio

La implementación y administración de aplicaciones MDM para aplicaciones de línea de negocio es fundamental para HoloLens. Los administradores y usuarios deben ver el estado de instalación de la aplicación para la auditoría y el diagnóstico. En esta versión, se han agregado más detalles en Configuración Cuentas de acceso a trabajo o escuela Haga  >    >    >  **clic en la información de su**  >  **cuenta.**

### <a name="additional-csps-and-policies"></a>Directivas y CSP adicionales

Un [proveedor de servicios de configuración (CSP)](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) es una interfaz para leer, establecer, modificar o eliminar valores de configuración en un dispositivo. En esta versión, se agrega compatibilidad con más directivas para aumentar el control que los administradores tienen sobre los dispositivos HoloLens implementados. Para obtener la lista de CSP compatibles con HoloLens, vea [CSP networkQoSPolicy](/windows/client-management/mdm/networkqospolicy-csp).

Novedades en esta versión:

**Policy CSP** 

El proveedor de servicios de configuración de directivas permite a la empresa configurar directivas en Windows dispositivos. En esta versión, hemos agregado nuevas directivas para HoloLens, que se enumeran aquí. Para más información, consulte [Policy CSPs supported by HoloLens 2](/windows/client-management/mdm/policies-supported-by-hololens2).  

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

El proveedor de servicios de configuración NetworkQoSPolicy crea directivas de calidad de servicio (QoS) de red. Una directiva de QoS realiza un conjunto de acciones en el tráfico de red en función de un conjunto de condiciones de coincidencia. Para más información, consulte [Csp de NetworkQoSPolicy](/windows/client-management/mdm/networkqospolicy-csp).

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Compatibilidad con Ethernet USB ampliada para dispositivos tethered 5G/NFC

Se agregó compatibilidad para habilitar determinados dispositivos de banda ancha móvil, como teléfonos 5G/NFC y zonas activas de Wi-Fi, cuando están conectados a la red HoloLens 2 a través de USB. Estos dispositivos se muestran ahora en la **configuración de red** como otra conexión Ethernet. (No se admiten los dispositivos de banda ancha móvil que requieren un controlador externo). Esta funcionalidad permite conexiones de ancho de banda alto Wi-Fi no está disponible y Wi-Fi tethering no tiene el rendimiento suficiente. Para obtener más información sobre los dispositivos USB compatibles, [consulte Conectar para Bluetooth dispositivos USB-C.](hololens-connect-devices.md)  

### <a name="hand-tracking-improvements"></a>Mejoras en el seguimiento de manos

Esta versión incluye varias mejoras de seguimiento de manos:

- **Apuntando la estabilidad de la posición:** El sistema ahora se resistirá a inclinar el dedo índice cuando la mano lo ocluse. Este cambio mejora la precisión al insertar botones, escribir, desplazar contenido, etc. 
- **Pulsaciones de aire accidentales reducidas:** Se ha mejorado la detección del gesto de pulsar en el aire. Ahora hay menos activaciones accidentales en varios escenarios comunes, como al colocar las manos en los lados.
- **Confiabilidad del conmutador de usuario:** El sistema ahora es más rápido y confiable a la hora de actualizar el tamaño de la mano al compartir un dispositivo.
- **Se ha reducido el robo con las manos:** Hemos mejorado el control de los casos en los que hay más de dos manos a la vista de los sensores. Si varias personas trabajan juntas, ahora hay una probabilidad mucho menor de que la mano con seguimiento "salte" del usuario a la mano de otra persona de la escena.
- **Confiabilidad del sistema:** Se ha corregido un problema que provocaba que el seguimiento manual dejara de funcionar cuando el dispositivo estaba bajo una carga elevada.

### <a name="dark-mode"></a>Modo oscuro

Muchas Windows aplicaciones ahora admiten los modos oscuro y claro. HoloLens 2 usuarios pueden elegir el modo predeterminado para las aplicaciones que admiten ambos. Después de la actualización, el modo de aplicación predeterminado es "oscuro", pero puede cambiar fácilmente esta configuración: Vaya a **Configuración** Colores del sistema Elija el  >    >    >  **modo de aplicación predeterminado.** 

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

![Ventanas en mosaico en modo oscuro.](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Comandos de voz del sistema

Ahora puede usar comandos de voz con cualquier aplicación en el dispositivo. Para obtener más información, [consulte Uso de la voz para HoloLens](hololens-cortana.md). Consulte también [Idiomas admitidos para HoloLens 2](hololens2-language-support.md).  

### <a name="cortana-updates"></a>Cortana actualizaciones

La aplicación actualizada se integra con Microsoft 365 para ayudarle a realizar más cosas en los dispositivos (actualmente solo US-English). En HoloLens 2, Cortana ya no admite determinados comandos específicos del dispositivo, como ajustar el volumen o reiniciar. Estas opciones ahora son compatibles con los nuevos comandos de voz del sistema. Obtenga más información sobre la nueva aplicación Cortana en nuestro [blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### <a name="quality-improvements-and-fixes"></a>Mejoras y correcciones de calidad

Mejoras y correcciones también en la actualización:  
- Se introdujo un sistema de calibración de pantalla activo. Esta característica mejora la estabilidad y alineación de los hologramas. Ahora permanecen en su lugar cuando mueve la cabeza de lado a lado.
- Se ha corregido un error que Wi-Fi streaming a HoloLens interrumpía periódicamente. Si una aplicación indica que necesita streaming de baja latencia, implemente la corrección llamando a la [función SetSocketMediaStreamingMode](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Se ha corregido un error de dispositivo que se produjo durante el streaming en modo de investigación.
- Se ha corregido un error por el que, en algunos casos, el usuario correcto no se mostraría en la pantalla de inicio de sesión al reanudar una sesión.
- Se ha corregido un problema por el que los usuarios no podían exportar registros de MDM a través **Configuración**.
- Se ha corregido un problema por el que la precisión del seguimiento de los ojos inmediatamente después de la configuración rápida podría ser inferior a la esperada.
- Se ha corregido un problema por el que el subsistema de seguimiento de los ojos no se inicializaba o realizaba la calibración en determinadas condiciones.
- Se ha corregido un problema por el que se solicitaba la calibración de los ojos para un usuario ya calibrado.
- Se ha corregido un problema por el que un controlador se bloqueaba durante la calibración de los ojos.
- Se ha corregido un problema por el que las pulsaciones repetidas del botón de encendido podían provocar un tiempo de espera del sistema de 60 segundos y un bloqueo del shell.
- Estabilidad mejorada para búferes de profundidad.
- Se ha agregado un **botón Compartir** en el Centro de opiniones para que los usuarios puedan compartir comentarios más fácilmente.
- Se ha corregido un error por el que RoboRaid wan no se instalaba correctamente.

### <a name="known-issues"></a>Problemas conocidos

- Un problema con el lenguaje del sistema zh-CN impide que los comandos de voz capturen la realidad mixta o muestren la dirección IP del dispositivo.
- Un problema requiere que inicie la aplicación Cortana después de iniciar el dispositivo para usar la activación de voz "Hey Cortana". Si ha actualizado desde una compilación 18362, es posible que también vea un segundo icono de aplicación para la versión anterior de la aplicación Cortana que ya no funciona en **Iniciar**.

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, versión 1903: actualización de mayo de 2020 
- Compilación 18362.1061

Esta actualización de calidad mensual no contiene ningún cambio importante porque el equipo estaba trabajando en la actualización de mayo de Windows Holographic, versión 2004, como se describió anteriormente.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, versión 1903: actualización de abril de 2020
- Compilación 18362.1059

**Modo oscuro para aplicaciones admitidas** 

Muchas Windows aplicaciones admiten el modo oscuro y claro. HoloLens 2 clientes pueden elegir ahora el modo predeterminado para las aplicaciones que admiten ambos esquemas de color. En función de los comentarios de los clientes, establecemos el modo de aplicación predeterminado en "oscuro", pero puede cambiar fácilmente esta configuración en cualquier momento: vaya **a Configuración > System > Colors** para buscar **"Choose your default app mode"** (Elegir el modo de aplicación predeterminado).

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

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic, versión 1903: actualización de febrero de 2020 
- Compilación 18362.1053

Mejoras y correcciones en la actualización:

- Deshabilitó temporalmente la API HolographicSpace.UserPresence para aplicaciones de Unity. Este cambio evita un problema que provocaba que algunas aplicaciones se pausase cuando se volteó el visor, incluso si la configuración "Ejecutar en segundo plano" estaba habilitada.
- Se ha corregido un bloqueo de HUP aleatorio causado por el seguimiento de las manos, en el que el usuario observó una inmovilización de la interfaz de usuario y, después de varios segundos, vuelve al shell.
- Se ha mejorado el seguimiento de las manos para que, cuando se desenreda con el dedo índice, la parte superior de ese dedo tenga menos probabilidades de rizarse inesperadamente.
- Confiabilidad mejorada del seguimiento de la cabeza, la asignación espacial y otros entornos de ejecución.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, versión 1903: actualización de enero de 2020 
- Compilación 18362.1043
 
Mejoras y correcciones en la actualización:

- Se ha mejorado la estabilidad de las aplicaciones exclusivas al trabajar con HoloLens 2 emulador.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, versión 1903: actualización de diciembre de 2019 
- Compilación 18362.1042

Mejoras y correcciones en la actualización:

- Se han introducido correcciones de reproducción de la última fase (LSR). Se ha mejorado la representación visual de los hologramas para que parezcan más estables y nítidos al tener en cuenta con más precisión su profundidad. Este síntoma será más evidente después de esta actualización si las aplicaciones no establecen correctamente la profundidad de los hologramas.
- Se ha corregido la estabilidad de las aplicaciones exclusivas y la navegación entre aplicaciones exclusivas.
- Se ha resuelto un problema por el que la captura de realidad mixta no podía grabar vídeo después de que el dispositivo estaba en estado de espera durante varios días.
- Estabilidad mejorada del holograma.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, versión 1903: actualización de noviembre de 2019 
- Compilación 18362.1039

Mejoras y correcciones en la actualización:

- Se ha corregido la **funcionalidad de Seleccionar** comandos de voz durante la configuración inicial para en-CA y en-AU.
- Calidad visual mejorada de los objetos colocados lejos en las versiones más recientes de Unity Mixed Reality Toolkit (MRTK).
- Se han corregido problemas de direccionamiento con aplicaciones holográficas que se atascaban en un estado en pausa durante el inicio hasta menú Inicio se abrió y, a continuación, se cerró.
- Correcciones y mejoras de conformidad en tiempo de ejecución de OpenXR para HoloLens 2 y el emulador.
