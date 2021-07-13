---
title: Cómo realizar la carga de prueba e instalar aplicaciones a través de HoloLens 2 Instalador de aplicación
description: Aprenda a instalar y solucionar problemas de aplicaciones con el instalador de aplicaciones y a cargar e instalar aplicaciones a través de la interfaz de usuario.
keywords: administración de aplicaciones, aplicación, hololens, instalador de aplicaciones
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
ms.openlocfilehash: 8f236ee27903069b65d3ded8eb7a1f37c65f535e
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635592"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalación de aplicaciones en HoloLens 2 a través de Instalador de aplicación

> [!NOTE]
> Esta característica estaba disponible en [Windows Holographic, versión 20H2 – Actualización de diciembre de 2020.](hololens-release-notes.md) Asegúrese de que el [dispositivo está actualizado](hololens-update-hololens.md) para usar esta característica.

Hemos agregado **una nueva funcionalidad (Instalador de aplicación)** para permitirle instalar aplicaciones de forma más fluida en los dispositivos HoloLens 2 dispositivos. La característica estará en **modo predeterminado para dispositivos no administrados.** Para evitar interrupciones en las empresas, el instalador de aplicaciones no **estará disponible para dispositivos administrados** en este momento.  

Un dispositivo se considera "administrado" si **se** cumple alguna de las siguientes condiciones:

- Inscrito [en](hololens-enroll-mdm.md) MDM
- Configurado con el [paquete de aprovisionamiento](hololens-provisioning.md)
- Identidad [de usuario](hololens-identity.md) Azure AD

Ahora puede instalar aplicaciones sin necesidad de habilitar el modo de desarrollador ni usar Portal de dispositivos.  Descargue (a través de USB o a través de Microsoft Edge) el paquete de Appx en el dispositivo y vaya al paquete de Appx en el Explorador de archivos para que se le pida que arranque la instalación.  Como alternativa, [inicie una instalación desde una página web](/windows/msix/app-installer/installing-windows10-apps-web). Al igual que las aplicaciones que se instalan desde Microsoft Store o la instalación local mediante la funcionalidad [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) de implementación [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) de aplicaciones LOB de MDM, las aplicaciones deben estar firmadas digitalmente con la herramienta firmar y el certificado que se usa para firmar debe ser de confianza para el dispositivo HoloLens antes de poder implementar la aplicación.

## <a name="requirements"></a>Requisitos

### <a name="for-your-devices"></a>Para los dispositivos:

Esta característica está disponible actualmente en Windows compilaciones de Holographic 20H2 para HoloLens 2 dispositivos. Asegúrese de que todos los dispositivos que usan este método se [actualizan.](hololens-update-hololens.md)

### <a name="for-your-apps"></a>Para las aplicaciones:

La configuración de la solución de la aplicación debe ser **Maestra** o **Versión,** ya que el Instalador de aplicación usará dependencias del almacén. Más información sobre la [creación de paquetes de aplicaciones.](/windows/msix/app-installer/create-appinstallerfile-vs)

Las aplicaciones que se instalan a través de este método deben estar firmadas digitalmente. Deberá usar un certificado para firmar la aplicación. Puede obtener un certificado de la lista de ca de confianza de [MS,](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)en cuyo caso no tendrá que realizar ninguna acción adicional. O bien, puede firmar su propio certificado, pero ese certificado deberá insertarse en el dispositivo.

- Cómo firmar aplicaciones [mediante la herramienta Firmar.](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Opciones de certificado:**

- [Lista de ca de confianza de MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Elija un método de implementación de certificado.**

- [Los paquetes de](hololens-provisioning.md) aprovisionamiento se pueden aplicar a dispositivos locales.
- MDM se puede usar para [aplicar certificados con configuraciones de dispositivo.](/mem/intune/protect/certificates-configure)
- Use en el dispositivo el [Administrador de certificados](certificate-manager.md).

## <a name="installation-method"></a>Método de instalación

1. Compruebe que el dispositivo no se considera administrado.
1. Compruebe que el HoloLens 2 está encendido y que ha iniciado sesión.
1. En el equipo, vaya a la aplicación personalizada y copie suapp.appxbundle en yourdevicename\Internal Storage\Downloads.
    Cuando termine de copiar el archivo, puede desconectar el dispositivo y finalizar la instalación más adelante.
1. En el HoloLens 2, abra el **menú Inicio,** seleccione Todas las **aplicaciones** e inicie **Explorador de archivos** aplicación.
1. Vaya a la carpeta Descargas. En el panel izquierdo de la aplicación, seleccione Este **dispositivo** en primer lugar y, a continuación, vaya a Descargas.
1. Seleccione el archivo yourapp.appxbundle.
1. La Instalador de aplicación se iniciará. Seleccione el **botón** Instalar para instalar la aplicación.

La aplicación instalada se iniciará automáticamente al finalizar la instalación.

![Instalación de ejemplos de MRTK mediante Instalador de aplicación](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a>Solución de problemas de instalación

Si la aplicación no se pudo instalar, compruebe lo siguiente para solucionar problemas:

- La aplicación es una compilación maestra o de versión.
- El dispositivo se actualiza a una compilación en la que esta característica está disponible.
- Está conectado [a Internet.](hololens-network.md)
- Los [puntos de conexión del Microsoft Store](hololens-offline.md) están configurados correctamente.  

## <a name="web-installer"></a>Instalador web

Los usuarios pueden instalar una aplicación directamente desde un servidor web. Este flujo usa el Instalador de aplicación combinado con un método de distribución fácil de descargar e instalar.

### <a name="how-to-set-up-web-install"></a>Configuración de la instalación web:

1. Asegúrese de que la aplicación está configurada correctamente para instalarse.
1. Siga estos [pasos para habilitar la instalación desde una página web](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).

### <a name="end-user-experience"></a>Experiencia del usuario final:

1. El usuario recibe e instala el certificado en el dispositivo mediante un método elegido anteriormente.
1. El usuario visita la dirección URL creada en el paso anterior.

La aplicación se instalará ahora en el dispositivo. Para buscar la aplicación, abra **el** menú Inicio y seleccione el botón **Todas las** aplicaciones para buscar la aplicación.

- Para obtener más ayuda con la solución de problemas del método de instalación del instalador de aplicaciones, visite [Solución de problemas del instalador de aplicaciones.](/windows/msix/app-installer/troubleshoot-appinstaller-issues)

> [!NOTE]
> No se admite la interfaz de usuario durante el proceso de actualización. Por lo tanto, la opción ShowPrompt de [esta página y](/windows/msix/app-installer/update-settings) las opciones relacionadas no se admiten.

## <a name="sample-apps"></a>Aplicaciones de ejemplo

Pruebe el Instalador de aplicación con una de nuestras aplicaciones de ejemplo disponibles. 
> [!div class="nextstepaction"]
> [Aplicaciones de ejemplo](/windows/mixed-reality/develop/features-and-samples)
