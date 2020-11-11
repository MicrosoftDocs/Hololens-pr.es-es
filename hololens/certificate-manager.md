---
title: Administrador de certificados
description: Más información sobre la administración de certificados manualmente en HoloLens 2.
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
ms.openlocfilehash: 04d7e8cb78357b5398c58e0a0c55e6e530fa363a
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163230"
---
# Administrador de certificados

- Auditoría, diagnóstico y herramientas de validación mejoradas para la seguridad y el cumplimiento de los dispositivos a través del nuevo administrador de certificados. Esta capacidad le permitirá implementar, solucionar problemas y validar sus certificados a escala en entornos comerciales.

En Windows Holographic, versión 20H2, agregamos un administrador de certificados en la aplicación de configuración de HoloLens 2. Vaya a **configuración > actualizar & certificados > de seguridad**. Esta característica proporciona una forma sencilla y fácil de usar para ver, instalar y quitar certificados en el dispositivo. Con el nuevo administrador de certificados, los administradores y los usuarios han mejorado las herramientas de auditoría, diagnóstico y validación para asegurarse de que los dispositivos siguen siendo seguros y cumplen con las normas. 

-   **Auditoría:** Posibilidad de validar que un certificado se ha implementado correctamente o para confirmar que se ha eliminado correctamente. 
-   **Diagnóstico:** Cuando surjan problemas, validar que los certificados adecuados existen en el dispositivo ahorra tiempo y ayuda con la solución de problemas. 
-   **Validación:** Comprobar que un certificado tiene el propósito pretendido y es funcional, puede ahorrar mucho tiempo, especialmente en entornos comerciales antes de implementar certificados a mayor escala.

Para buscar rápidamente un certificado específico en la lista, hay opciones para ordenar por nombre, almacén o fecha de expiración. Los usuarios también pueden buscar un certificado directamente. Para ver las propiedades de certificado individuales, seleccione el certificado y haga clic en **información**. 

La instalación de certificados admite actualmente archivos. cer y. CRT. Los propietarios de dispositivos pueden instalar certificados en la máquina local y en el usuario actual;  el resto de los usuarios solo pueden instalarse en el usuario actual. Los usuarios solo pueden quitar certificados instalados directamente desde la interfaz de usuario de configuración. Si se ha instalado un certificado por otros medios, también debe ser eliminado por el mismo mecanismo.

## Para instalar un certificado: 

1.  Conecta tu HoloLens 2 a un equipo PC.
1.  Coloca el archivo de certificado que deseas instalar en una ubicación de tu HoloLens 2.
1.  Vaya a **configuración de la aplicación > actualizar & certificados > de seguridad**y seleccione instalar un certificado.
1.  Haga clic en **Importar archivo** y vaya a la ubicación donde guardó el certificado.
1.  Seleccione **Ubicación**de la tienda.
1.  Seleccione **almacén de certificados**.
1.  Haz clic en **Instalar**.

El certificado debe instalarse ahora en el dispositivo.

## Para quitar un certificado: 
1. Vaya a **configuración > la actualización y los certificados de > de seguridad**.
1. Busque el certificado por el nombre en el cuadro de búsqueda.
1. Seleccione el certificado.
1. Haga clic en **quitar**
1. Seleccione **sí** cuando se le solicite confirmación.


![Visor de certificados de la aplicación configuración en CERITIFCATES](images/certificate-viewer-device.jpg)

![Imagen que muestra cómo usar la interfaz de usuario de certificado para instalar un certificado en configuración.](images/certificate-device-install.jpg)
