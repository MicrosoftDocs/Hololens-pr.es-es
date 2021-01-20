---
title: Cómo realizar una instalación de prueba de la carga e instalación de aplicaciones a través del Instalador de aplicación de HoloLens 2
description: Carga de diapositivas e instalación de aplicaciones a través de la interfaz de usuario
keywords: administración de aplicaciones, aplicación, hololens, instalador de aplicación
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
ms.openlocfilehash: ab0c58d5a97d5dbaf83adf321d1f9fbc01b3ad03
ms.sourcegitcommit: 37910c10f0f98aa9cbdc29124cd8f14ee0af3fbd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2021
ms.locfileid: "11280659"
---
# Instalar aplicaciones en HoloLens 2 mediante el Instalador de aplicación

> [!NOTE]
> Esta característica estaba disponible en [Windows Holographic, versión 20H2 – Actualización de diciembre de 2020](hololens-release-notes.md). Asegúrate de que el dispositivo [esté actualizado](hololens-update-hololens.md) para usar esta característica.

Hemos agregado una nueva funcionalidad (Instalador de **aplicación)** para permitirle instalar aplicaciones de forma más sencilla en sus dispositivos HoloLens 2. La característica estará en **modo predeterminado para dispositivos no administrados.** Para evitar interrupciones en las empresas, el instalador de aplicación no **estará disponible para dispositivos administrados** en este momento.  

Un dispositivo se considera "administrado" si **se** cumple alguna de las siguientes condiciones:

- MDM [inscrito](hololens-enroll-mdm.md)
- Configurado con el [paquete de aprovisionamiento](hololens-provisioning.md)
- Identidad [de usuario](hololens-identity.md) es Azure AD

Ahora puedes instalar aplicaciones sin tener que habilitar el modo de desarrollador o usar Device Portal.  Descarga (a través de USB o a través de Microsoft Edge) la agrupación Appx en el dispositivo y navega a la agrupación Appx en el Explorador de archivos para que se te pida que arranques la instalación.  Como alternativa, [inicie una instalación desde una página web.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)  Al igual que las aplicaciones que instalas desde Microsoft Store o la instalación de instalación local [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) con la [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) funcionalidad de implementación de la aplicación LOB de MDM, las aplicaciones deben estar firmadas digitalmente con la Herramienta de firma y el certificado que se usa para firmar debe ser de confianza para el dispositivo HoloLens antes de que se pueda implementar la aplicación.

## Requisitos

### Para los dispositivos:

 actualmente está disponible en compilaciones de Windows Holographic 20H2 para dispositivos HoloLens 2. Asegúrese de que todos los dispositivos que usan este método se [actualizan.](hololens-update-hololens.md)

### Para las aplicaciones: 
La configuración de la solución de la aplicación debe ser **Principal** o **Versión,** ya que el Instalador de aplicación usará dependencias de la tienda. Consulta más sobre cómo [crear paquetes de aplicaciones.](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)

Las aplicaciones que se instalan a través de este método deben estar firmadas digitalmente. Tendrás que usar un certificado para firmar la aplicación. Puede obtener un certificado de la lista de CA de confianza de [MS,](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)en cuyo caso no tendrá que realizar ninguna acción adicional. O bien, puedes firmar tu propio certificado, pero ese certificado tendrá que insertarse en el dispositivo.

- Cómo firmar aplicaciones con [la Herramienta de inicio de sesión.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Opciones de certificado:**

- [Lista de CA de confianza de MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Elige un método de implementación de certificados.**

- [Los paquetes de](hololens-provisioning.md) aprovisionamiento se pueden aplicar a dispositivos locales.
- MDM puede usarse para [aplicar certificados con configuraciones de dispositivo.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)
- Usa el Administrador de certificados [en el dispositivo.](certificate-manager.md)

## Método de instalación

1. Comprueba que el dispositivo no se considera administrado.
1. Comprueba que el dispositivo HoloLens 2 esté encendido y que has iniciado sesión.
1. En el equipo, ve a la aplicación personalizada y copia tuapp.appxbundle en tudevicename\Internal Storage\Downloads.
    Cuando termines de copiar el archivo, puedes desconectar el dispositivo y finalizar la instalación más adelante.
1. En el dispositivo HoloLens 2, abra el **menú Inicio,** seleccione Todas las **aplicaciones** e inicie la aplicación **Explorador de** archivos.
1. Vaya a la carpeta Descargas. Es posible que deba seleccionar primero **** este dispositivo en el panel izquierdo de la aplicación y, a continuación, ir a Descargas.
1. Selecciona el archivo yourapp.appxbundle.
1. Se iniciará el Instalador de aplicación. Selecciona el **botón** Instalar para instalar la aplicación.

La aplicación instalada se iniciará automáticamente al finalizar la instalación.

![Instalación de ejemplos de MRTK a través del Instalador de aplicación](images/hololens-app-installer-picture.jpg)

### Solución de problemas de las instalaciones

Si la aplicación no se pudo instalar, comprueba lo siguiente para solucionar problemas:

- La aplicación es una compilación maestra o de versión.
- El dispositivo se actualiza a una compilación en la que esta característica está disponible.
- Está conectado [a Internet.](hololens-network.md)
- Los [puntos de conexión de Microsoft Store](hololens-offline.md) están configurados correctamente.  

## Instalador web

Los usuarios pueden instalar una aplicación directamente desde un servidor web. Este flujo usa el Instalador de aplicación combinado con un método de distribución fácil de descargar e instalar.

### Cómo configurar la instalación web:

1. Asegúrate de que la aplicación esté configurada correctamente para instalarse.
1. Siga estos [pasos para habilitar la instalación desde una página web.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)

### Experiencia del usuario final:

1. El usuario recibe e instala el certificado en el dispositivo mediante un método previamente elegido anteriormente.
1. El usuario visita la dirección URL creada a partir del paso anterior.

La aplicación se instalará ahora en el dispositivo. Para encontrar la aplicación, abre el **menú Inicio** y selecciona **el** botón Todas las aplicaciones para encontrar la aplicación.

- Para obtener más ayuda con la solución de problemas del método de instalación del instalador de aplicaciones, visita [solucionar problemas del instalador de la aplicación.](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)

> [!NOTE]
> No se admite la interfaz de usuario durante el proceso de actualización. Por lo tanto, la opción ShowPrompt de [esta página y](https://docs.microsoft.com/windows/msix/app-installer/update-settings) las opciones relacionadas no son compatibles.

## Aplicaciones de ejemplo

Para probar el Instalador de aplicación con algunas aplicaciones de ejemplo, echa un vistazo a algunas de nuestras muestras disponibles:

- [Centro de ejemplos de MRTK](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [Superficies](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [Aplicaciones de muestra para UWP que se pueden usar para pruebas](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
