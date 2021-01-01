---
title: Cómo cargar y instalar aplicaciones a través del instalador de aplicaciones de HoloLens 2
description: Descargar diapositivas e instalar aplicaciones a través de la interfaz de usuario
keywords: App Management, App, hololens, instalador de aplicaciones
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: e52cc2f031c284b619c61ffa04f259f76397faf5
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253097"
---
# Instalar aplicaciones en HoloLens 2 a través del instalador de la aplicación

Estamos **agregando una nueva función (instalador de aplicaciones) para que pueda instalar aplicaciones más fácilmente** en sus dispositivos HoloLens 2. La característica estará **activada de forma predeterminada en los dispositivos no administrados**. Para evitar interrupciones en las empresas, el instalador **de aplicaciones no estará disponible para los dispositivos administrados** en este momento.  

> [!NOTE]
> Esta característica está disponible en [Windows Holographic, versión 20H2: diciembre de 2020](hololens-release-notes.md). Asegúrese de que el dispositivo está [actualizado](hololens-update-hololens.md) para usar esta característica.

Hemos **agregado una nueva función (instalador de aplicaciones) que te permite instalar aplicaciones de forma más fluida** en tus dispositivos HoloLens 2. La característica estará **activada de forma predeterminada en los dispositivos no administrados**. Para evitar interrupciones en las empresas, el instalador **de aplicaciones no estará disponible para los dispositivos administrados** en este momento.  

Un dispositivo se considera "administrado" si se cumple **alguna** de las condiciones siguientes:

- MDM [inscrito](hololens-enroll-mdm.md)
- Configurado con el [paquete de aprovisionamiento](hololens-provisioning.md)
- La [identidad](hololens-identity.md) del usuario es Azure ad

Ahora puede instalar aplicaciones sin necesidad de habilitar el modo de desarrollador ni el uso de Device portal.  Descarga (a través de USB o a través de Microsoft Edge) el paquete appx en el dispositivo y navega hasta el paquete appx en el explorador de archivos para que se le solicite que inicie la instalación.  También puede [iniciar una instalación desde una página web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  Al igual que las aplicaciones que se instalan desde Microsoft Store o mediante la instalación de prueba con la aplicación LOB de MDM, las aplicaciones tienen que estar firmadas digitalmente con la [herramienta firmar](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) y el [certificado usado para firmar debe ser de confianza para](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) el dispositivo HoloLens antes de que se pueda implementar la aplicación.

## Requisitos

### Para los dispositivos:

 la característica está actualmente disponible en las compilaciones 20H2 de Windows Holographic para dispositivos HoloLens 2. Asegúrese de que se [actualizan](hololens-update-hololens.md)todos los dispositivos que usan este método.

### Para sus aplicaciones: 
La configuración de la solución de la aplicación debe ser **Master** o **Release** , ya que el instalador de la aplicación usará las dependencias de la tienda. Más información sobre cómo [crear paquetes de aplicaciones](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).

Las aplicaciones que se instalen a través de este método deben estar firmadas digitalmente. Tendrás que usar un certificado para firmar la aplicación. Puede obtener un certificado desde la lista de [CA de confianza de MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), en cuyo caso no tendrá que realizar ninguna acción adicional. También puede firmar su propio certificado, sin embargo, el certificado deberá insertarse en el dispositivo.

- Cómo firmar aplicaciones [con la herramienta firmar.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Opciones de certificado:**

- [Lista de CA de confianza de MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Elija un método de implementación de certificados.**

- Los [paquetes de aprovisionamiento](hololens-provisioning.md) pueden aplicarse a dispositivos locales.
- MDM se puede usar para [aplicar certificados con configuraciones de dispositivos](https://docs.microsoft.com/mem/intune/protect/certificates-configure).
- Use el en el [Administrador de certificados](certificate-manager.md)de dispositivo.

## Método de instalación

1. Compruebe que el dispositivo no se considere administrado.
1. Verifica que tu dispositivo HoloLens 2 esté encendido y que hayas iniciado sesión.
1. En su equipo, navegue hasta la aplicación personalizada y copie SUAPLICACIÓN. appxbundle a yourdevicename\Internal Storage\Downloads.
    Una vez que haya terminado de copiar el archivo, puede desconectar el dispositivo y finalizar la instalación más tarde.
1. Desde tu dispositivo HoloLens 2 abre el **menú Inicio**, selecciona **todas las aplicaciones** e inicia la aplicación **Explorador de archivos** .
1. Vaya a la carpeta descargas. Es posible que tenga que estar en el panel izquierdo de la aplicación, seleccione **este dispositivo** en primer lugar y, a continuación, vaya a descargas.
1. Seleccione el archivo SUAPLICACIÓN. appxbundle.
1. Se iniciará el instalador de la aplicación. Seleccione el botón **instalar** para instalar la aplicación.

La aplicación instalada se iniciará automáticamente al finalizar la instalación.

![Instalación de MRTK ejemplos mediante el instalador de aplicaciones](images/hololens-app-installer-picture.jpg)

### Solución de problemas de instalación

Si la aplicación no se instaló correctamente, compruebe lo siguiente para solucionar el problema:

- Tu aplicación es una compilación de lanzamiento o maestra.
- El dispositivo se actualizará a una compilación en la que está disponible esta característica.
- Estás [conectado a Internet](hololens-network.md).
- Los [puntos de conexión de Microsoft Store](hololens-offline.md) están correctamente configurados.  

## Instalador Web

Los usuarios pueden instalar una aplicación directamente desde un servidor Web. Este flujo usa el instalador de aplicaciones combinado con un método de distribución de fácil descarga e instalación.

### Cómo configurar la instalación en Internet:

1. Asegúrate de que la aplicación esté correctamente configurada para instalarse.
1. Siga estos [pasos para habilitar la instalación desde una página web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).

### Experiencia de usuario final:

1. El usuario recibe e instala el certificado en el dispositivo con un método previamente seleccionado.
1. El usuario visita la dirección URL creada a partir del paso anterior.

La aplicación se instalará en el dispositivo. Para buscar la aplicación, abra el **menú Inicio** y seleccione el botón **todas las aplicaciones** para buscar la aplicación.

- Para obtener más ayuda con la solución de problemas del método de instalación del instalador de aplicaciones, visite [solucionar problemas del instalador](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)de la aplicación.

> [!NOTE]
> No se admite la interfaz de usuario durante el proceso de actualización. Por lo tanto, no se admite la opción ShowPrompt de [esta página](https://docs.microsoft.com/windows/msix/app-installer/update-settings) ni las opciones relacionadas.

## Aplicaciones de ejemplo

Para probar el instalador de la aplicación con algunas aplicaciones de ejemplo, eche un vistazo a algunos de nuestros ejemplos disponibles:

- [Hub de ejemplos de MRTK](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [Surge](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [Aplicaciones de muestra para UWP que se pueden usar para pruebas](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
