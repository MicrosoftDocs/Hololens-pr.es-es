---
title: Paquete de aprovisionamiento
description: Obtén información sobre el empaquetado, el aprovisionamiento, la implementación y la implementación de aplicaciones empresariales para dispositivos HoloLens.
keywords: aplicación, implementación de aplicaciones, implementación de aplicaciones empresariales, aprovisionamiento
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283701"
---
# Paquete de aprovisionamiento

Los paquetes de aprovisionamiento se pueden usar para preparar y configurar dispositivos en un entorno sin acceso a la administración de puntos de conexión. También se pueden implementar en un dispositivo independientemente de la identidad del usuario, el estado de inscripción, durante la configuración rápida (OOBE) o aplicando un paquete de aprovisionamiento durante la [instalación.](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)

## Consideraciones sobre paquetes de aprovisionamiento:

* Aplicaciones no públicas
* Solo carga lateral USB
* No hay actualización automática (requiere actualizaciones manuales a través de PPKG)

Las aplicaciones instaladas a través de un paquete de aprovisionamiento deben estar firmadas por un certificado en el almacén del equipo local. Los paquetes de aprovisionamiento solo pueden instalar certificados en el almacén del dispositivo (equipo local), por lo que es posible que se instalen una aplicación y un certificado a través del mismo paquete de aprovisionamiento. Si vas a implementar el certificado desde MDM o instalarlo a través del Administrador de [certificados,](certificate-manager.md)asegúrate de implementar el certificado en el almacén del equipo local para firmar las aplicaciones instaladas de esta forma.

Para obtener información sobre los conceptos básicos de la creación de un paquete de aprovisionamiento para dispositivos HoloLens, visita [Aprovisionamiento de HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning) Para implementar una aplicación, debes empezar con el aprovisionamiento avanzado.

> [!NOTE]
> HoloLens (1.ª generación) tiene compatibilidad limitada para instalar aplicaciones (**UniversalAppInstall**) mediante un paquete de aprovisionamiento. Los dispositivos HoloLens (1.ª generación) solo admiten la instalación de una aplicación a través de PPKG solo durante la OOBE y solo con las instalaciones de contexto de usuario.

## Programa de instalación

En [el Diseñador de configuraciones de Windows,](https://www.microsoft.com/store/productId/9NBLGGH4TX22) siga estos cuatro pasos.

1. Establezca ApplicationManagement/AllowAllTrustedApps en "Sí". Vea: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. Vaya a **UniversalAppInstall**  >  **UserContextAppLicense** y escriba **PackageFamilyName**. Vea [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall). Vea también: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   Puedes usar Device Portal en un dispositivo en el que ya has instalado la aplicación. Visita la página Aplicaciones y mira la línea PackageRelativeID, toda la información antes de "!". Es **packageFamilyName**.

3. A continuación, verá que tiene una nueva sección, **ApplicationFile**. Usa esta área para cargar el lote appx.

4. Dependiendo de si has comprado la aplicación o creado tu propia aplicación de LÍNEA de negocio, deberás cargar el archivo de licencia o el certificado de seguridad.

    - Para el archivo de licencia: vaya a **UniversalAppInstall**  >  **UserContextAppLicence** y vaya a la ubicación de la licencia y cárbala.
    - Para el archivo de seguridad, ve **a Certificados** y selecciona el certificado que quieres instalar junto con la agrupación .appx.

Asegúrese de guardar el proyecto en una ubicación segura. A **continuación,** exportarlo como un paquete **de aprovisionamiento**.  

Vea también: [Aplicar el paquete de aprovisionamiento a HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)
