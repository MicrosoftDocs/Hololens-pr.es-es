---
title: Paquete de aprovisionamiento
description: Obtenga información sobre el empaquetado, el aprovisionamiento, la implementación y la implementación de aplicaciones empresariales para HoloLens dispositivos.
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
ms.openlocfilehash: d071f4326a35a9ea61e2069618da7107bb808f04
ms.sourcegitcommit: f480d3cc8d549fa356e05df6ce15e9517f5b978a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2021
ms.locfileid: "123610996"
---
# <a name="provisioning-package"></a>Paquete de aprovisionamiento

Los paquetes de aprovisionamiento se pueden usar para preparar y configurar dispositivos en un entorno sin acceso a la administración de puntos de conexión. También se pueden implementar en un dispositivo independientemente de la identidad del usuario, el estado de inscripción, durante la experiencia rápida (OOBE) o mediante la aplicación de un paquete de aprovisionamiento durante la [instalación.](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)

## <a name="provisioning-packages-considerations"></a>Consideraciones sobre el aprovisionamiento de paquetes

* Aplicaciones no públicas
* Solo carga lateral USB
* Sin actualización automática (requiere actualizaciones manuales a través de PPKG)

Las aplicaciones instaladas a través de un paquete de aprovisionamiento deben estar firmadas por un certificado en el almacén de la máquina local. Los paquetes de aprovisionamiento solo pueden instalar certificados en el almacén del dispositivo (equipo local). Por lo tanto, una aplicación y un certificado se pueden instalar a través del mismo paquete de aprovisionamiento. Si va a implementar el certificado desde MDM o a instalarlo a través del Administrador de [certificados,](certificate-manager.md)asegúrese de implementar el certificado en el almacén de la máquina local para firmar las aplicaciones instaladas de esta manera.

Para obtener información sobre los conceptos básicos de la creación de un paquete de aprovisionamiento para HoloLens dispositivos, [visite HoloLens Provisioning](/hololens/hololens-provisioning). Para implementar una aplicación, debe empezar con el aprovisionamiento avanzado.

> [!NOTE]
> HoloLens (1.ª generación) tiene compatibilidad limitada con la instalación de aplicaciones **(UniversalAppInstall)** mediante un paquete de aprovisionamiento. HoloLens dispositivos (1.ª generación) solo admiten la instalación de una aplicación a través de PPKG solo durante la OOBE y solo con las instalaciones de contexto de usuario.

## <a name="setup"></a>Configurar

En [Windows diseñador de configuración,](https://www.microsoft.com/store/productId/9NBLGGH4TX22) siga estos cuatro pasos.

1. Establezca ApplicationManagement/AllowAllTrustedApps en "Sí". Vea: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. Vaya a **UniversalAppInstall**  >  **UserContextApp (UniversalAppInstalar UserContextApp)** y escriba **packageFamilyName**. Vea [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall).

   Puede usar Portal de dispositivos en un dispositivo en el que ya haya instalado la aplicación. Visite la página Aplicaciones y mire la línea PackageRelativeID, toda la información anterior a "!". Es **packageFamilyName.**

3. A continuación, verá que tiene una nueva sección, **ApplicationFile**. Use esta área para cargar el paquete appx.

4. En función de si ha adquirido la aplicación o ha creado su propia aplicación de LOB, deberá cargar el archivo de licencia o el certificado de seguridad.

    - Para el archivo de licencia: vaya a **UniversalAppInstall**  >  **UserContextAppLicence** y escriba el identificador de producto de la licencia. Se creará una nueva sección <b>LicenseProductID:</b><i>yourlicenseproductid,</i> seleccione esta nueva sección y vaya a la ubicación de la licencia y cárbala.
        - Vea [UserContextAppLicense.](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)
    - Para el archivo de seguridad, vaya **a Certificados** y seleccione el certificado que desea instalar junto con el paquete .appx.

Asegúrese de guardar el proyecto en una ubicación segura. A **continuación,** exporte como un **paquete de aprovisionamiento**.  

Consulte también: [Aplicar el paquete de aprovisionamiento a HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).
