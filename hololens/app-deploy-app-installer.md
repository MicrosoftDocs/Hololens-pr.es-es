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
ms.openlocfilehash: d8be5c2ed7fba38b6710aba9c122557a36073a79
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924135"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalación de aplicaciones en HoloLens 2 a través de Instalador de aplicación

> [!NOTE]
> Esta característica estaba disponible en [Windows Holographic, versión 20H2– Actualización de diciembre de 2020.](hololens-release-notes.md) Asegúrese de que el [dispositivo está actualizado](hololens-update-hololens.md) para usar esta característica.

Hemos agregado **una nueva funcionalidad (Instalador de aplicación)** que le permite instalar aplicaciones de forma más fluida en los dispositivos HoloLens 2 dispositivos. La característica estará en **modo predeterminado para dispositivos no administrados.** Para evitar interrupciones en las empresas, el instalador de aplicaciones no **estará disponible para dispositivos administrados** en este momento.  

Un dispositivo se considera "administrado" si **se** cumple alguna de las siguientes condiciones:

- Inscrito [en](hololens-enroll-mdm.md) MDM
- Configurado con el [paquete de aprovisionamiento](hololens-provisioning.md)
- Identidad [de usuario](hololens-identity.md) Azure AD

Ahora puede instalar aplicaciones sin necesidad de habilitar el modo de desarrollador ni usar Portal de dispositivos.  Descargue (a través de USB o a través de Microsoft Edge) el paquete de Appx en el dispositivo y vaya al paquete de Appx en el Explorador de archivos para que se le pida que arranque la instalación.  Como alternativa, [inicie una instalación desde una página web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  Al igual que las aplicaciones que instala desde Microsoft Store o la instalación local mediante la funcionalidad de [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) implementación de [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) aplicaciones LOB de MDM, las aplicaciones deben estar firmadas digitalmente con la herramienta de firma y el certificado que se usa para firmar debe ser de confianza para el dispositivo HoloLens antes de que se pueda implementar la aplicación.

## <a name="requirements"></a>Requisitos

### <a name="for-your-devices"></a>Para los dispositivos:

Esta característica está disponible actualmente en las compilaciones de Windows Holographic 20H2 para HoloLens 2 dispositivos. Asegúrese de que todos los dispositivos que usan este método se [actualizan.](hololens-update-hololens.md)

### <a name="for-your-apps"></a>Para las aplicaciones:

La configuración de la solución de la aplicación debe ser **Maestra** o **Versión,** ya que el Instalador de aplicación usará dependencias del almacén. Más información sobre la [creación de paquetes de aplicaciones.](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)

Las aplicaciones que se instalan a través de este método deben estar firmadas digitalmente. Deberá usar un certificado para firmar la aplicación. Puede obtener un certificado de la lista de ca de confianza de [MS,](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)en cuyo caso no tendrá que realizar ninguna acción adicional. O bien, puede firmar su propio certificado, pero ese certificado deberá insertarse en el dispositivo.

- Cómo firmar aplicaciones [mediante la herramienta Firmar.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Opciones de certificado:**

- [Lista de ca de confianza de MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Elija un método de implementación de certificado.**

- [Los paquetes de](hololens-provisioning.md) aprovisionamiento se pueden aplicar a dispositivos locales.
- MDM se puede usar para [aplicar certificados con configuraciones de dispositivo.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)
- Use en el dispositivo el [Administrador de certificados](certificate-manager.md).

## <a name="installation-method"></a>Método de instalación

1. Compruebe que el dispositivo no se considera administrado.
1. Compruebe que el HoloLens 2 está encendido y que ha iniciado sesión.
1. En el equipo, vaya a la aplicación personalizada y copie yourapp.appxbundle en yourdevicename\Internal Storage\Downloads.
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
- Los [puntos de conexión de la Microsoft Store](hololens-offline.md) están configurados correctamente.  

## <a name="web-installer"></a>Instalador web

Los usuarios pueden instalar una aplicación directamente desde un servidor web. Este flujo usa el Instalador de aplicación combinado con un método de distribución fácil de descargar e instalar.

### <a name="how-to-set-up-web-install"></a>Configuración de la instalación web:

1. Asegúrese de que la aplicación está configurada correctamente para instalarse.
1. Siga estos [pasos para habilitar la instalación desde una página web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).

### <a name="end-user-experience"></a>Experiencia del usuario final:

1. El usuario recibe e instala el certificado en el dispositivo mediante un método elegido anteriormente.
1. El usuario visita la dirección URL creada en el paso anterior.

La aplicación se instalará ahora en el dispositivo. Para buscar la aplicación, abra **el** menú Inicio y seleccione el botón **Todas las** aplicaciones para buscar la aplicación.

- Para obtener más ayuda con la solución de problemas del método de instalación del instalador de aplicaciones, visite [Solución de problemas del instalador de aplicaciones.](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)

> [!NOTE]
> No se admite la interfaz de usuario durante el proceso de actualización. Por lo tanto, la opción ShowPrompt de [esta página y](https://docs.microsoft.com/windows/msix/app-installer/update-settings) las opciones relacionadas no se admiten.

## <a name="sample-apps"></a>Aplicaciones de ejemplo

Pruebe el Instalador de aplicación con una de nuestras aplicaciones de ejemplo disponibles. 
> [!div class="nextstepaction"]
> [Aplicaciones de ejemplo](https://docs.microsoft.com/windows/mixed-reality/develop/features-and-samples?tabs=unity#sample-apps)
