---
title: Administrador de certificados
description: Aprende a instalar, administrar y quitar certificados manualmente en dispositivos holoLens 2 de realidad mixta.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 9d221321adcb8062206695e3e610d35dee14523e
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283691"
---
# Administrador de certificados

- Herramientas mejoradas de auditoría, diagnóstico y validación para la seguridad y el cumplimiento de dispositivos a través del nuevo Administrador de certificados. Esta funcionalidad le permitirá implementar, solucionar problemas y validar los certificados a escala en entornos comerciales.

En Windows Holographic, versión 20H2, estamos agregando un Administrador de certificados en la aplicación Configuración de HoloLens 2. Vaya a **Configuración > actualizar & seguridad > certificados.** Esta característica proporciona una forma sencilla y fácil de usar para ver, instalar y quitar certificados en el dispositivo. Con el nuevo Administrador de certificados, los administradores y usuarios ahora tienen herramientas mejoradas de auditoría, diagnóstico y validación para garantizar que los dispositivos sigan siendo seguros y compatibles. 

-   **Auditoría:** Capacidad para validar que un certificado se implementó correctamente o para confirmar que se quitó correctamente. 
-   **Diagnóstico:** Cuando surgen problemas, validar que existen los certificados adecuados en el dispositivo ahorra tiempo y ayuda a solucionar problemas. 
-   **Validación:** Comprobar que un certificado cumple el propósito previsto y es funcional, puede ahorrar mucho tiempo, especialmente en entornos comerciales antes de implementar certificados a mayor escala.

Para buscar rápidamente un certificado específico en la lista, hay opciones para ordenar por nombre, almacén o fecha de expiración. Los usuarios también pueden buscar directamente un certificado. Para ver propiedades de certificado individuales, seleccione el certificado y haga clic en **Información.** 

La instalación de certificados admite actualmente archivos .cer y .crt. Los propietarios de dispositivos pueden instalar certificados en el equipo local y en el usuario actual;  todos los demás usuarios solo pueden instalar en el usuario actual. Los usuarios solo pueden quitar certificados instalados directamente desde la interfaz de usuario de configuración. Si un certificado se ha instalado a través de otros medios, también debe quitarse mediante el mismo mecanismo.

## Para instalar un certificado: 

1.  Conecta HoloLens 2 a un equipo.
1.  Coloque el archivo de certificado que desea instalar en una ubicación de HoloLens 2.
1.  Vaya a **Configuración de la aplicación > actualizar & seguridad > certificados**y seleccione Instalar un certificado.
1.  Haga **clic en Importar** archivo y vaya a la ubicación donde guardó el certificado.
1.  Seleccione **Ubicación de la tienda.**
1.  Seleccione **Almacén de certificados.**
1.  Haz clic en **Instalar**.

El certificado ahora debe instalarse en el dispositivo.

## Para quitar un certificado: 
1. Vaya a **Configuración de la aplicación > actualización y seguridad > certificados.**
1. Busque el certificado por su nombre en el cuadro de búsqueda.
1. Seleccione el certificado.
1. Haga clic **en Quitar**
1. Seleccione **Sí** cuando se le pida confirmación.


![Visor de certificados en la aplicación Configuración en Ceritifcates](images/certificate-viewer-device.jpg)

![Imagen que muestra cómo usar la interfaz de usuario de certificado para instalar un certificado en Configuración.](images/certificate-device-install.jpg)
