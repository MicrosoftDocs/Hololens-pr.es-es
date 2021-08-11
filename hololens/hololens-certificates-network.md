---
title: Preparación de certificados y perfiles de red para HoloLens 2
description: Obtenga información sobre cómo configurar, usar, implementar y solucionar problemas de certificados de red en dispositivos de realidad mixta HoloLens 2.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d9b752c820af8dbceb2b6b9f3c7a7be4df910805b5a5014bb3e3650551392ce8
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664316"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>Preparación de certificados y perfiles de red para HoloLens 2

Uno de los requisitos comunes de los clientes que utilizan HoloLens 2 es la autenticación basada en certificados. Es posible que necesite un certificado para conectarse a una red Wi-Fi, a soluciones VPN o para acceder a recursos internos de su organización.

Dado que los dispositivos HoloLens 2 suelen vincularse a Azure Active Directory (Azure AD) y se administran mediante Intune u otro proveedor de MDM, necesitará implementar estos certificados con una infraestructura de certificados del protocolo de inscripción de certificados simple (SCEP) o de estándar de criptografía de clave pública (PKCS) que se integre con su solución MDM. 

>[!NOTE]
> Si no tiene un proveedor de MDM, puede implementar certificados por medio de un [paquete de aprovisionamiento](hololens-provisioning.md#steps-for-creating-provisioning-packages) en [Windows Configuration Designer](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) o mediante el [Administrador de certificados](certificate-manager.md). Para ello, vaya a **Configuración > Update & Security (Actualización y seguridad) > Administrador de certificados**.

## <a name="certificate-requirements"></a>Requisitos de certificados
Los certificados raíz son necesarios para implementar certificados a través de una infraestructura SCEP o PKCS. Otras aplicaciones y otros servicios de su organización también pueden requerir la implementación de certificados raíz en los dispositivos HoloLens 2. 

## <a name="wi-fi-connectivity-requirements"></a>Requisitos de conectividad de Wi-Fi
Para permitir que se proporcione automáticamente un dispositivo con la configuración de Wi-Fi necesaria para su red empresarial, necesitará un perfil de configuración de Wi-Fi. Puede configurar Intune u otro proveedor MDM para implementar estos perfiles en sus dispositivos. Si su seguridad de red requiere que los dispositivos formen parte del dominio local, es posible que también necesite evaluar la infraestructura de red Wi-Fi para asegurarse de que sea compatible con los dispositivos HoloLens 2 (que solo se pueden unir a Azure AD).

## <a name="deploy-certificate-infrastructure"></a>Implementación de una infraestructura para certificados
Si aún no existe ninguna infraestructura SCEP o PKCS, la tendrá que preparar. Para admitir la autenticación mediante certificados SCEP o PKCS, Intune requiere el uso de un [conector de certificado](/mem/intune/protect/certificate-connectors).

> [!NOTE]
> Al usar SCEP con una CA de Microsoft, también debe configurar el [servicio de inscripción de dispositivos de red (NDES)](/mem/intune/protect/certificates-scep-configure#set-up-ndes).

Para obtener más información, consulte el artículo sobre [configuración de un perfil de certificado para sus dispositivos en Microsoft Intune](/intune/certificates-configure).

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Implementación de los certificados y del perfil Wi-Fi/VPN
Para implementar certificados y perfiles, siga estos pasos:
1.  Cree un perfil para cada uno de los certificados raíz e intermedios (consulte el artículo sobre [creación de perfiles de certificado de confianza](/intune/protect/certificates-configure#create-trusted-certificate-profiles)). Cada uno de estos perfiles debe tener una descripción que incluya una fecha de expiración con el formato DD/MM/AAAA. **No se implementará ningún perfil de certificado digital sin una fecha de expiración.**
1.  Cree un perfil para cada certificado SCEP o PKCS (consulte cómo [crear un perfil de certificado SCEP o crear un perfil de certificado PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)). Cada uno de estos perfiles debe tener una descripción que incluya una fecha de expiración con el formato DD/MM/AAAA. **No se implementará ningún perfil de certificado digital sin una fecha de expiración.**

    > [!NOTE]
    > Como muchos consideran que HoloLens 2 es un dispositivo compartido, con varios usuarios por dispositivo, se recomienda implementar certificados de dispositivo, en lugar de certificados de usuario para la autentificación de la red Wi-Fi, siempre que sea posible.

3.  Cree un perfil para cada red de Wi-Fi corporativa (consulte el artículo sobre [configuración de Wi-Fi para dispositivos con Windows 10 y versiones posteriores](/intune/wi-fi-settings-windows)). 
    > [!NOTE]
    > Se recomienda que el perfil de Wi-Fi se [asigne](/mem/intune/configuration/device-profile-assign) a grupos de dispositivos, en lugar de hacerlo a grupos de usuarios, siempre que sea posible. 

    > [!TIP]
    > También puede exportar un perfil Wi-Fi de trabajo desde un equipo con Windows 10 en su red corporativa. Esta exportación crea un archivo XML con toda la configuración actual. Después puede importar este archivo en Intune y usarlo como perfil de Wi-Fi para sus dispositivos HoloLens 2. Consulte el artículo sobre [exportación e importación de la configuración de Wi-Fi para dispositivos Windows](/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

4.  Cree un perfil para cada VPN corporativa (consulte el artículo sobre [configuración de dispositivos Windows 10 y Windows Holographic para agregar conexiones VPN mediante Intune](/intune/vpn-settings-windows-10)).

## <a name="troubleshooting-certificates"></a>Solución de problemas de certificados

En el caso de que necesite validar que un certificado se ha implementado correctamente, use el [Administrador de certificados](certificate-manager.md) del dispositivo para comprobar que el certificado está presente.  

>[!WARNING]
> Aunque puede ver los certificados implementados por MDM en el Administrador de certificados, ahí no puede desinstalarlos. Debe hacerlo por medio de MDM.


