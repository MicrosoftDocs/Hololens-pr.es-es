---
title: Presentación de la nueva versión de Microsoft Edge
description: Más información sobre la nueva versión de Edge
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, Edge, Internet, explorador
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: 41978c626328903cf480a3315d56841f187bc123
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640192"
---
# <a name="introducing-the-new-microsoft-edge"></a>Presentación de la nueva versión de Microsoft Edge

![Animación del cambio del logotipo de la versión anterior de Microsoft Edge al logotipo de la nueva versión](images/new-edge.gif)

La nueva versión de Microsoft Edge [adopta el proyecto Chromium de código abierto](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) con el fin de conseguir una mejor compatibilidad para los clientes y una menor fragmentación de la web para los desarrolladores web.

Con [Windows Holographic, versión 21H1](hololens-release-notes.md#windows-holographic-version-21h1), la nueva versión de Microsoft Edge está disponible por primera vez para los clientes de HoloLens 2. Comparta los comentarios y errores con nuestro equipo por medio de la característica **Enviar comentarios** de la nueva versión de Microsoft Edge o en el [Centro de opiniones](hololens-feedback.md).

> [!IMPORTANT]
> Esta nueva versión de Microsoft Edge reemplaza automáticamente a la versión anterior, que ya no se [admite](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) en los nuevos lanzamientos.

![Captura de pantalla de la nueva versión de Microsoft Edge](images/new-edge-ui.png)

## <a name="launching-the-new-microsoft-edge"></a>Inicio de la nueva versión de Microsoft Edge

La nueva versión de Microsoft Edge ![icono de la nueva versión de Microsoft Edge](images/new_edge_logo.png) (representada por un icono de espiral azul y verde) se ancla al menú Inicio y se inicia automáticamente al activar un vínculo web.

> [!NOTE]
> La primera vez que inicie la nueva versión de Microsoft Edge en su HoloLens 2, se importarán la configuración y los datos de la versión anterior.

## <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Configuración de las opciones de directiva para la nueva versión de Microsoft Edge

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

## <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Qué esperar de la nueva versión de Microsoft Edge en HoloLens 2

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
- Al reproducir audio desde una ventana del explorador en modo "Sígueme", el audio seguirá reproduciéndose aunque se deshabilite el modo "Sígueme". Para evitar este problema, detenga la reproducción del audio antes de deshabilitar el modo "Sígueme" o cierre la ventana con el botón X.
- La interacción con ventanas activas de Microsoft Edge puede hacer que las ventanas de otras aplicaciones 2D dejen de estar activas inesperadamente. Puede reactivarlas interactuando de nuevo con ellas.

## <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider Channels

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

## <a name="using-wdac-to-block-new-microsoft-edge"></a>Uso de WDAC para bloquear la nueva versión de Microsoft Edge

Los administradores de TI que quieran actualizar la [directiva WDAC](windows-defender-application-control-wdac.md) para bloquear la nueva versión de Microsoft Edge deberán agregar el siguiente contenido a la directiva.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

## <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Administración de puntos de conexión para la nueva versión de Microsoft Edge

Algunos entornos pueden tener restricciones de red que deberán tenerse en cuenta. Para garantizar una experiencia sin problemas con la nueva versión de Edge, [habilite estos puntos de conexión de Microsoft](/deployedge/microsoft-edge-security-endpoints).

Obtenga más información sobre los [puntos de conexión disponibles actualmente para HoloLens](hololens-offline.md).

## <a name="install-web-apps"></a>Instalación de aplicaciones web
 > [!Note]
> A partir de [Windows Holographic, versión 21H1](hololens-release-notes.md#windows-holographic-version-21h1), la aplicación web de Office ya no vendrá preinstalada. 

Puede usar la nueva versión de Edge para instalar aplicaciones web junto con aplicaciones de Microsoft Store. Por ejemplo, puede instalar la aplicación web de Microsoft Office para ver y editar archivos hospedados en SharePoint o OneDrive. Para instalar la aplicación web de Office, visite https://www.office.com y seleccione el botón **Aplicación disponible** o **Instalar Office** en la barra de direcciones. Seleccione **Instalar** para confirmar.
> [!IMPORTANT]
> La funcionalidad de la aplicación web de Office solo está disponible cuando su HoloLens 2 tiene una conexión activa a Internet.

## <a name="webxr-and-360-viewer"></a>WebXR y 360 Viewer


La nueva versión de Microsoft Edge es compatible con WebXR, el nuevo estándar para crear experiencias web envolventes que reemplaza a WebVR. Muchas experiencias web envolventes se diseñaron pensando en la realidad virtual (reemplazan el campo de vista por un entorno virtual), pero también son compatibles con HoloLens 2. El estándar WebXR también permite experiencias web envolventes de realidad aumentada y mixta que usan su entorno físico. A medida que los desarrolladores dediquen más tiempo a WebXR, se prevé que lleguen nuevas experiencias envolventes de realidad mixta y aumentada que los clientes de HoloLens 2 podrán probar.

La extensión 360 Viewer se basa en WebXR y se instala automáticamente junto con la nueva versión de Microsoft Edge en HoloLens 2. Esta extensión web le ofrece la posibilidad de sumergirse en vídeos en 360 grados. YouTube ofrece la mayor selección de vídeos en 360°, por lo que le recomendamos que empiece ahí.

### <a name="how-to-use-webxr"></a>Cómo se usa WebXR

1. Vaya a un sitio web compatible con WebXR.
1. Seleccione el botón **Enter VR** (Entrar en VR) en el sitio web. La ubicación y la representación visual de este botón pueden variar según el sitio web, pero puede tener un aspecto similar al siguiente:

    ![Ejemplo del botón para entrar a VR](images/75px-enter-vr.png)

1. La primera vez que intente iniciar una experiencia de WebXR en un dominio específico, el explorador pedirá su consentimiento para acceder a una vista inmersiva; seleccione **Permitir**.
1. Use [gestos de HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame) para manipular la experiencia.
1. Si la experiencia no tiene un botón **Salir**, use el [gesto Inicio](hololens2-basic-usage.md#start-gesture) para volver al inicio.

**Ejemplos recomendados de WebXR**
- 360 Viewer (consulte la sección siguiente)
- [XR Dinosaurs](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

### <a name="how-to-use-360-viewer"></a>Uso de 360 Viewer

1. Vaya a un vídeo en 360 grados en YouTube.
1. En el fotograma de vídeo, seleccione el botón de casco de realidad mixta:

    ![Botón para activar 360 Viewer](images/enter-360-viewer.jpg)

1. La primera vez que intente iniciar 360 Viewer en un dominio específico, el explorador pedirá su consentimiento para acceder a una vista inmersiva. seleccione **Permitir**.
1. [Pulse en el aire](hololens2-basic-usage.md#select-using-air-tap) para abrir los controles de reproducción. Use los [haces de mano y pulse en el aire](hololens2-basic-usage.md#select-using-air-tap) para reproducir o pausar, avanzar o retroceder, activar o desactivar subtítulos, o detener la experiencia (y salir de la vista inmersiva). Los controles de reproducción desaparecerán después de unos segundos de inactividad.

### <a name="top-webxr-and-360-viewer-known-issues"></a>Principales problemas conocidos de WebXR y 360 Viewer
- En función de la complejidad de la experiencia de WebXR, puede que la velocidad de fotogramas oscile o se reduzca.
- La compatibilidad con las articulaciones de las manos en WebXR no está habilitada de forma predeterminada. Los desarrolladores pueden habilitar la compatibilidad desde edge://flags mediante la activación de "WebXR Hand Input" (Entrada de mano en WebXR).
- Es posible que los vídeos en 360° de sitios web que no sean YouTube no funcionen según lo previsto.

### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Comentarios sobre WebXR y 360 Viewer

Comparta los comentarios y errores con nuestro equipo por medio de la característica **Enviar comentarios** de la nueva versión de Microsoft Edge.
