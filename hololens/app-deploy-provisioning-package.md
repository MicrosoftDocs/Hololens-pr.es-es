---
title: Paquete de aprovisionamiento
description: aplicación, implementación de aplicaciones, aplicación empresarial demployment, aprovisionamiento
keywords: aplicación, implementación de aplicaciones, aplicación empresarial demployment, aprovisionamiento
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
ms.openlocfilehash: 60efc454f9e1221372279401da9f8ee918e061e7
ms.sourcegitcommit: efa3fb7e353c5e56ee467cc7fd94ffdfaf46e2e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "11219227"
---
# Paquete de aprovisionamiento

Los paquetes de aprovisionamiento se pueden usar para preparar y configurar dispositivos en un entorno sin acceso a administración de extremos. También se pueden implementar en un dispositivo, independientemente de la identidad del usuario, el estado de inscripción, durante la configuración rápida (OOBE) o [aplicando un paquete de aprovisionamiento durante la configuración](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).

## Consideraciones sobre los paquetes de aprovisionamiento:
* Aplicaciones no públicas
* Solo carga del lado USB
* No hay ninguna actualización automática (requiere actualizaciones manuales a través de PPKGs)

Las aplicaciones instaladas a través de un paquete de aprovisionamiento deben estar firmadas por un certificado del almacén de la máquina local. Los paquetes de aprovisionamiento solo pueden instalar certificados en el almacén del dispositivo (equipo local), por lo tanto, la aplicación y el certificado se pueden instalar a través del mismo paquete de aprovisionamiento. Si va a implementar su certificado desde MDM o mediante el administrador de [certificados](certificate-manager.md), asegúrese de implementar el certificado en el almacén de la máquina local para firmar las aplicaciones instaladas de esta manera.

Para obtener información sobre los conceptos básicos de la creación de un paquete de aprovisionamiento para dispositivos HoloLens, visite la [configuración de hololens](https://docs.microsoft.com/hololens/hololens-provisioning). Para implementar una aplicación, debe empezar con el aprovisionamiento avanzado.

> [!NOTE]
> HoloLens (1º gen) tiene un soporte limitado para instalar aplicaciones (**UniversalAppInstall**) mediante un paquete de aprovisionamiento. Los dispositivos HoloLens (1. ª gen) solo admiten la instalación de una aplicación a través de PPKG solo durante OOBE y solo con instalaciones de contexto de usuario.

## Programa de instalación

En el [Diseñador de configuración de Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22) , siga 4 pasos.

1. Establece ApplicationManagement/AllowAllTrustedApps en "sí". Consulte: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. En **UniversalAppInstall**  >  **UserContextAppLicense** introduce el **PackageFamilyName**. Consulta [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall). Vea también: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   Puede usar Device portal en un dispositivo en el que ya haya instalado la aplicación. Visite la página aplicaciones y mire la línea PackageRelativeID, toda la información antes de la "!" Es tu **PackageFamilyName**.
    
3. Verá que tiene una nueva sección, **ApplicationFile**. Usa este área para cargar tu paquete appx.

4. En función de si ha comprado la aplicación o ha creado su propia aplicación de LOB, tendrá que cargar el archivo de licencia o el certificado de seguridad.

    - Para el archivo de licencia: en **UniversalAppInstall**  >  **UserContextAppLience** y vaya a la ubicación de su licencia y cargarla. 
    - Para el archivo de seguridad, navegue hasta **certificados** y seleccione el certificado para instalar junto a su paquete. appx.

Asegúrese de guardar el proyecto en una ubicación segura. A continuación, **expórtelo** como un **paquete de aprovisionamiento**.  
    
Consulta también: [aplicar tu paquete de provisiong a HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).
