---
title: Administrador de certificados
description: Obtenga información sobre cómo instalar, administrar y quitar certificados manualmente en HoloLens 2 dispositivos de realidad mixta.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/12/2021
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: af9c6634ddbb40acace9a2abf8dd933ec05704de
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924398"
---
# <a name="certificate-manager"></a>Administrador de certificados

- Se han mejorado las herramientas de auditoría, diagnóstico y validación para la seguridad y el cumplimiento de dispositivos mediante el nuevo Administrador de certificados. Esta funcionalidad le permitirá implementar, solucionar problemas y validar los certificados a escala en entornos comerciales.

En Windows Holographic, versión 20H2, vamos a agregar un administrador de certificados en HoloLens 2 Configuración aplicación. Vaya a **Configuración > Update & Security > Certificates**. Esta característica proporciona una manera sencilla y fácil de ver, instalar y quitar certificados en el dispositivo. Con el nuevo Administrador de certificados, los administradores y los usuarios ahora tienen herramientas mejoradas de auditoría, diagnóstico y validación para garantizar que los dispositivos sigan siendo seguros y compatibles.

-   **Auditoría:** Capacidad de validar que un certificado se ha implementado correctamente o de confirmar que se quitó correctamente.
-   **Diagnóstico:** Cuando surgen problemas, validar que existen los certificados adecuados en el dispositivo ahorra tiempo y ayuda a solucionar problemas.
-   **Validación:** Comprobar que un certificado cumple el propósito previsto y es funcional, puede ahorrar mucho tiempo, especialmente en entornos comerciales antes de implementar certificados a mayor escala.

Para buscar rápidamente un certificado específico en la lista, hay opciones para ordenar por nombre, almacén o fecha de expiración. Los usuarios también pueden buscar directamente un certificado. Para ver las propiedades de certificado individuales, seleccione el certificado y haga clic en **Información**.

La instalación de certificados admite actualmente archivos .cer y .crt. Los propietarios de dispositivos pueden instalar certificados en la máquina local y el usuario actual.  todos los demás usuarios solo pueden instalar en el usuario actual.

## <a name="to-install-a-certificate"></a>Para instalar un certificado:

1.  Conectar el HoloLens 2 a un equipo.
1.  Coloque el archivo de certificado que desea instalar en una ubicación de la HoloLens 2.
1.  Vaya a **Configuración App > Update & Security > Certificates** y seleccione Install a certificate (Instalar un certificado).
1.  Haga **clic en Importar** archivo y vaya a la ubicación en la que guardó el certificado.
1.  Seleccione **Store Location (Ubicación del almacén).**
1.  Seleccione **Almacén de certificados.**
1.  Haga clic en **Instalar**.

El certificado debe estar ahora instalado en el dispositivo.

![Visor de certificados en la Configuración aplicación en Certificados.](images/certificate-viewer-device.jpg)

![Imagen que muestra cómo usar la interfaz de usuario de certificado para instalar un certificado en Configuración.](images/certificate-device-install.jpg)

## <a name="to-remove-a-certificate"></a>Para quitar un certificado:

> [!WARNING]
> Con el Administrador de certificados, los usuarios solo pueden quitar los certificados instalados directamente desde la interfaz Configuración usuario. Si un certificado se ha instalado a través de otros medios, también debe quitarse mediante el mismo mecanismo y no se puede quitar del Administrador de certificados. Aunque puede ver los certificados implementados por MDM en el Administrador de certificados, ahí no puede desinstalarlos. Debe hacerlo por medio de MDM.

1. Vaya a **Configuración App > Update and Security > Certificates**.
1. Busque el certificado por nombre en el cuadro de búsqueda.
1. Seleccione el certificado.
1. Haga clic **en Quitar.**
1. Seleccione **Sí** cuando se pida confirmación.

## <a name="pfx-file-support-for-certificate-manager"></a>Compatibilidad con archivos PFX para el Administrador de certificados

- Introducido en [Windows Holographic, versión 21H2.](hololens-release-notes.md#windows-holographic-version-21h2)

 Hemos agregado compatibilidad con el Administrador de certificados para usar ahora certificados .pfx. Cuando los usuarios navegan a **Configuración** actualizar & certificados de seguridad y seleccionan Instalar un certificado, la interfaz de usuario ahora admite  >    >  el archivo de certificado .pfx. 
Los usuarios pueden importar el certificado .pfx, con clave privada, al almacén de usuarios o al almacén del equipo.