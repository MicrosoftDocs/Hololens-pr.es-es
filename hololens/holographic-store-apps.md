---
title: Búsqueda, instalación y desinstalación de aplicaciones
description: Microsoft Store es su fuente de aplicaciones y juegos que funcionan con HoloLens.  Obtenga más información sobre cómo buscar, instalar y desinstalar aplicaciones holográficas.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 9/7/2021
manager: jarrettr
keywords: hololens, store, tienda, uwp, aplicación, instalación
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f7d4ddf41f02b083000c1e57f5140c38527826d7
ms.sourcegitcommit: b9cd7ed5edb98249c609b547b90587863ea1cb9e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2021
ms.locfileid: "129364416"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>Búsqueda, instalación y desinstalación de aplicaciones de Microsoft Store

Microsoft Store es su fuente de información para aplicaciones y juegos que funcionan con HoloLens. Cuando vaya a Store en su HoloLens, cualquier aplicación que vea allí funcionará en este.

Las aplicaciones de HoloLens usan la vista 2D o la vista holográfica. Las aplicaciones que usan la vista 2D parecen ventanas y pueden colocarse a su alrededor. Una aplicación que utiliza la vista holográfica lo rodea y se convierte en la única aplicación que ve.

HoloLens es compatible con muchas aplicaciones existentes de Microsoft Store, así como con nuevas aplicaciones compiladas específicamente para HoloLens.  Este artículo se centra en las aplicaciones holográficas de Microsoft Store.

Para más información sobre la instalación y ejecución de aplicaciones personalizadas, lea [Aplicaciones holográficas personalizadas](holographic-custom-apps.md).

## <a name="find-apps"></a>Buscar aplicaciones

Abra Microsoft Store desde el menú **Inicio**. A continuación, busque aplicaciones y juegos. Puede usar [comandos de voz](hololens-cortana.md) para realizar búsquedas. Para ello, diga "Buscar"; cuando se abra la ventana de búsqueda, diga "Iniciar dictado" y, a continuación, cuando se le solicite, empiece a pronunciar los términos de búsqueda.

> [!NOTE]
> Los requisitos del sistema para los dispositivos HoloLens se basan en la arquitectura de la compilación de la aplicación. Si una compilación de la aplicación para HoloLens (1.ª gen) no se ha actualizado con una UWP más reciente en Store para incluir el paquete de arquitectura ARM, no estará disponible para los dispositivos HoloLens 2. Del mismo modo, si una aplicación de HoloLens 2 no incluye el paquete de la arquitectura x86, no estará disponible para los dispositivos HoloLens (1.ª gen). Arquitecturas de dispositivos HoloLens:
>
> - x86 = HoloLens (1.ª generación)
> - ARM = HoloLens 2

> [!NOTE]
> El 12 de enero de 2021, las siguientes aplicaciones dejarán de recibir soporte técnico para los dispositivos HoloLens. Le recomendamos que use el vínculo siguiente en el dispositivo para utilizar la versión web de la aplicación.

| Aplicación        | Vínculo                                          |
|------------|-----------------------------------------------|
| Excel Mobile      | [https://office.live.com/start/Excel.aspx](https://office.live.com/start/Excel.aspx)      |
| Word Mobile       | [https://office.live.com/start/Word.aspx](https://office.live.com/start/Word.aspx)       |
| PowerPoint Mobile | [https://office.live.com/start/PowerPoint.aspx](https://office.live.com/start/PowerPoint.aspx) |

> [!NOTE]
> La aplicación OneDrive no se admite actualmente para las cuentas de Azure AD en HoloLens. Se recomienda descargar la aplicación PWA de Microsoft OneDrive. [Siga estos pasos para descargar la aplicación].

## <a name="install-apps"></a>Instalar aplicaciones

Para descargar aplicaciones, tendrá que iniciar sesión con una cuenta de Microsoft. Algunas aplicaciones son gratuitas y pueden descargarse de inmediato. Para las aplicaciones que requieren una compra, debe iniciar sesión en Store con su cuenta de Microsoft y tener un método de pago válido.

> [!NOTE]
> La cuenta que utilice en Microsoft Store no tiene que ser la misma que la cuenta con la que ha iniciado sesión. Si está usando una cuenta profesional o educativa en HoloLens, tal vez tendrá que iniciar sesión con su cuenta personal en la aplicación Store para hacer una compra.

> [!TIP]
> Para configurar un método de pago, vaya a [account.microsoft.com](https://account.microsoft.com/) y seleccione **Pago y facturación** > **Opciones de pago** > **Agregar una opción de pago**.

1. Para abrir el [menú **Inicio**](holographic-home.md), realice un [gesto de inicio](/hololens/hololens2-basic-usage#start-gesture) o un gesto de [eclosión](hololens1-basic-usage.md) en HoloLens (1.ª generación).

1. Seleccione la aplicación Microsoft Store. Una vez que la aplicación Store se abra:
   1. Utilice la barra de búsqueda para buscar aplicaciones.
   1. Seleccione aplicaciones esenciales o creadas específicamente para HoloLens de una de las categorías seleccionadas.
   1. En la parte superior derecha de la aplicación Store, seleccione el botón **"..."** y luego seleccione **Mi biblioteca** para ver las aplicaciones compradas anteriormente.

1. Seleccione **Obtener** o **Instalar** en la página de la aplicación (puede ser necesaria una compra).

### <a name="install-microsoft-onedrive-pwa-app"></a>Instalación de la aplicación PWA de Microsoft OneDrive

Requisitos previos: el usuario ya ha unido el dispositivo HoloLens 2 dispositivo a su inquilino de trabajo.

1. Abra el menú Inicio e inicie el explorador Edge.

    ![Menú Inicio](images/office-pwa-1.jpg)

1. En el dispositivo HoloLens vaya a [https://onedrive.live.com/about/signin](https://onedrive.live.com/about/signin) y escriba las credenciales de su cuenta profesional.

    ![Inicio de sesión de trabajo](images/office-pwa-2.jpg)

1. Después de iniciar sesión correctamente en el portal web de OneDrive, espere entre 30 y 60 segundos a que se muestre el botón de descarga de PWA.

    ![Botón de instalación de PWA](images/office-pwa-3.jpg)

1. Seleccione el botón de descarga de PWA e instale la aplicación.

    ![Mensaje de instalación](images/office-pwa-4.jpg)

1. Cierre el explorador Edge y, en el menú Inicio, seleccione el botón **Todas las aplicaciones** e inicie la aplicación PWA de OneDrive con la etiqueta **Microsoft OneDrive**

    ![Cuadro de diálogo Todas las aplicaciones donde se muestran ambas aplicaciones.](images/office-pwa-5.jpg)

    > [!NOTE]
    > "Microsoft OneDrive" es la aplicación PWA cuya aplicación para UWP antigua es "OneDrive".

1. A continuación, podrá ver sus archivos de OneDrive.

    ![PWA de OneDrive](images/office-pwa-6.jpg)

Consulte también: [Habilitación de cargas automáticas en OneDrive para la Empresa](hololens-release-notes.md#onedrive-for-work-or-school-camera-roll-upload).

## <a name="update-apps"></a>Actualizar aplicaciones

### <a name="manual-updates"></a>Actualizaciones manuales

Puede utilizar la aplicación Microsoft Store para actualizar una aplicación que ha instalado desde Microsoft Store. En el caso de las aplicaciones instaladas para Microsoft Store para Empresas, también puede actualizar esas aplicaciones desde Microsoft Store para Empresas.

1. Para abrir el [menú **Inicio**](holographic-home.md), realice un [gesto de inicio](/hololens/hololens2-basic-usage#start-gesture) o un gesto de [eclosión](hololens1-basic-usage.md) en HoloLens (1.ª generación).

1. Seleccione la aplicación Store.

1. Mire la parte superior derecha de la aplicación Store.

1. Seleccione el botón **"..."** o "Ver más".

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla de la aplicación Microsoft Store.](images/store-update-1.png)

1. Seleccione **Descargas y actualizaciones**.
    1. Si el dispositivo ha identificado previamente actualizaciones, puede que vea una flecha hacia abajo y un número que representa las actualizaciones pendientes.

1. Seleccione **Obtener actualizaciones**. El dispositivo ahora buscará actualizaciones y las configurará para descargar e instalar.

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla de cómo obtener actualizaciones de la aplicación Microsoft Store.](images/store-update-2.png.jpg)

> [!NOTE]
> Si las aplicaciones del dispositivo las distribuyó su organización, podrán actualizarse a través de los mismos métodos de administración de aplicaciones comerciales. Si esto se aplica a su situación, obtenga más información a través de nuestra [introducción a la implementación de aplicaciones comerciales.](app-deploy-overview.md)
>
> Si desea actualizar una aplicación personalizada que se ha instalado de prueba o implementado, tendrá que usar el mismo método con la versión actualizada de la aplicación. Para más información sobre cómo instalar y ejecutar aplicaciones personalizadas, lea [Aplicaciones holográficas personalizadas](holographic-custom-apps.md).

### <a name="automatic-app-updates"></a>Actualizaciones automáticas de aplicaciones

Las actualizaciones automáticas se aplican a las aplicaciones Microsoft Store o Microsoft Store para Empresas, y solo se pueden aplicar automáticamente si se han instalado directamente desde Store. Si se instalan desde Intune, el equipo de TI puede insertar actualizaciones desde MDM mediante la sincronización con Microsoft Store para Empresas para obtener la versión más reciente disponible de la aplicación.

> [!NOTE]
> En el caso de las aplicaciones procedentes de Microsoft Store para Empresas, debe haber iniciado sesión en Store y haberse autenticado con el mismo inquilino asociado al catálogo de Microsoft Store para Empresas que se usa en el dispositivo.

#### <a name="how-automatic-updates-work"></a>Cómo funcionan las actualizaciones automáticas

Las actualizaciones automáticas de aplicaciones están programadas para producirse diariamente (aproximadamente cada 24 horas) en función de la disponibilidad de la red. Mantenga el dispositivo activo o conectado a la alimentación de CA para recibir actualizaciones. Aunque las actualizaciones de aplicaciones se descarguen durante el uso diario activo, solo se aplicarán cuando la aplicación que se va a actualizar ya no esté en uso.

> [!TIP]
> Si es posible, cargue el dispositivo durante la noche mientras esté conectado a la red corporativa. Si las actualizaciones se pueden descargar e instalar durante la noche, es menos probable que interrumpan el uso activo del dispositivo.

#### <a name="how-it-administrators-can-control-automatic-updates"></a>Cómo pueden controlar los administradores de TI las actualizaciones automáticas

Los administradores de TI pueden controlar las actualizaciones automáticas de aplicaciones mediante la directiva [ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate). Esta directiva les permite habilitar o deshabilitar completamente las actualizaciones automáticas de aplicaciones, pero no controla cuándo se producen las actualizaciones.

A partir de la versión [21H2](hololens-release-notes.md#windows-holographic-version-21h1), los administradores de TI también pueden usar la directiva [ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures) para controlar cuándo se debe forzar el reinicio de las aplicaciones que estaban en uso, pero que no se pudieron actualizar en intentos anteriores.

## <a name="uninstall-apps"></a>Desinstalar aplicaciones

Hay tres formas de desinstalar aplicaciones. Puede desinstalar aplicaciones a través de Microsoft Store, del menú Inicio o de Configuración.

> [!WARNING]
> No se puede desinstalar una aplicación del sistema ni Microsoft Store.

> [!IMPORTANT]
> Si el dispositivo HoloLens 2 tiene varios usuarios, debe iniciar sesión como el usuario que instaló la aplicación para desinstalarla.

### <a name="uninstall-from-the-microsoft-store"></a>Desinstalar aplicaciones desde Microsoft Store

Abra Microsoft Store desde el menú **Inicio** y, a continuación, busque la aplicación que desea desinstalar.  En la página de Store, cada aplicación instalada tiene un botón **Desinstalar**.

### <a name="uninstall-from-the-start-menu"></a>Desinstalación desde el menú Inicio

En el menú **Inicio** o en la lista **Todas las aplicaciones**, vaya a la aplicación. Mantenga presionado hasta que aparezca el menú y, después, seleccione **Desinstalar**.

### <a name="uninstall-from-settings"></a>Desinstalación desde Configuración

En el menú **Inicio**, seleccione **Configuración -> Aplicaciones**. Busque la aplicación en la lista, selecciónela y, después, haga clic en **Desinstalar**.

Si no puede desinstalar una aplicación, envíe sus [comentarios](/hololens/hololens-feedback) mediante el Centro de opiniones.
