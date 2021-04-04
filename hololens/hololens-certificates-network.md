---
title: Preparación de certificados y perfiles de red para HoloLens 2
description: Obtenga información sobre cómo configurar, usar, implementar y solucionar problemas de certificados de red en dispositivos mixtos de HoloLens 2.
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
ms.openlocfilehash: de9f2c4f136a26a5956ba8a8f3b9faba1e90ea66
ms.sourcegitcommit: 86dba9e8a5e25f0bf29f4c0580970c25c44b7359
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470058"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>Preparación de certificados y perfiles de red para HoloLens 2

Uno de los requisitos comunes que utilizan los clientes de HoloLens 2 es la autenticación basada en certificados. Es posible que necesite un certificado para conectarse a una red Wi-Fi, a soluciones VPN o para acceder a recursos internos de su organización.

Dado que los dispositivos HoloLens 2 suelen vincularse a Azure Active Directory (Azure AD) y se administran mediante el portal de empresa de Intune u otro proveedor de MDM, necesitará implementar estos certificados con una infraestructura de certificados del servicio de inscripción de dispositivos de red (SCEP) o criptografía de clave pública (PKCS) que se integre con su solución MDM. 

>[!NOTE]
> Si no tiene un proveedor MDM, puede implementar certificados por medio de un [paquete de aprovisionamiento](https://docs.microsoft.com/hololens/hololens-provisioning#steps-for-creating-provisioning-packages) en el [Diseñador de configuraciones de Windows](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) o a través del [Administrador de certificados](https://docs.microsoft.com/hololens/certificate-manager) yendo a **Configuración > Actualizar y Seguridad > Administrador de certificados**.

## <a name="certificate-requirements"></a>Requisitos de certificados
Los certificados de raíz son necesarios para implementar certificados a través de una infraestructura servicio de inscripción de dispositivos de red o de criptografía de clave pública. Otras aplicaciones y otros servicios de su organización también pueden requerir la implementación de certificados raíz en los dispositivos HoloLens 2. 

## <a name="wi-fi-connectivity-requirements"></a>Requisitos de conectividad de Wi-Fi
Para permitir que se proporcione automáticamente un dispositivo con la configuración de Wi-Fi necesaria para tu red empresarial, necesitará un perfil de configuración de Wi-Fi. Puede configurar el portal de empresa de Intune u otro proveedor MDM para implementar estos perfiles en sus dispositivos. Si su seguridad de red requiere que los dispositivos sean parte del dominio local, es posible que también necesite evaluar la infraestructura de red Wi-Fi para asegurarse de que sea compatible con los dispositivos HoloLens 2 (que solo se pueden unir a Azure AD).

## <a name="deploy-certificate-infrastructure"></a>Implementar una infraestructura para certificados digitales
Si aún no existe ninguna infraestructura de servicio de inscripción de dispositivos de red, la tendrá que preparar. Para admitir la autenticación mediante certificados SCEP o PKCS, Intune requiere el uso de un [conector de certificados](https://docs.microsoft.com/mem/intune/protect/certificate-connectors).

> [!NOTE]
> Si utiliza un servicio de inscripción de dispositivos de red (SCEP) con una entidad de certificación de Microsoft, también tendrá que configurar el [servicio de inscripción de dispositivos de red (NDES)](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes)

Para obtener más información, consulte [Configuración de un perfil de certificado para sus dispositivos en Microsoft Intune.](https://docs.microsoft.com/intune/certificates-configure)

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Implementación de los certificados y del perfil Wi-Fi/VPN
Para implementar estos certificados y perfiles siga estos pasos:
1.  Cree un perfil para cada uno de los certificados raíz e intermedios (consulte [Creación de perfiles de certificado de confianza](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles)). Cada uno de estos perfiles debe tener una descripción que incluya una fecha de expiración en el formato DD/MM/AAAA. **No se implementará ningún perfil de certificado digital sin una fecha de expiración.**
1.  Cree un perfil para cada uno de los certificados SCEP o PKCS (consulte [Crear perfiles de certificado SCEP o Crear perfiles de certificado PKCS](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)). Cada uno de estos perfiles debe tener una descripción que incluya una fecha de expiración en el formato DD/MM/AAAA. **No se implementará ningún perfil de certificado digital sin una fecha de expiración.**

    > [!NOTE]
    > Como muchos consideran que HoloLens 2 es un dispositivo compartido, con varios usuarios por dispositivo, se recomienda implementar certificados de dispositivo, en lugar de certificados de usuario para la autentificación de la red Wi-Fi, siempre que sea posible.

3.  Cree un perfil para cada red corporativa Wi-Fi (consulte [Configuración de Wi-Fi para dispositivos Windows 10 y versiones posteriores](https://docs.microsoft.com/intune/wi-fi-settings-windows)). 
    > [!NOTE]
    > Se recomienda que el perfil de Wi-Fi se [asigne](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) a grupos de dispositivo, en lugar de a grupos de usuario, siempre que sea posible. 

    > [!TIP]
    > También puede exportar un perfil Wi-Fi de trabajo desde un equipo con Windows 10 en su red corporativa. Esta exportación crea un archivo XML con toda la configuración. Luego, importe este archivo en Intune y úselo como perfil de Wi-Fi para sus dispositivos HoloLens 2. Consulte [Exportación e importación de la configuración de Wi-Fi para dispositivos Windows.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  Cree un perfil para cada VPN corporativo (consulte [Configuración de dispositivos con Windows 10 y Windows Holographic para agregar conexiones VPN mediante Intune](https://docs.microsoft.com/intune/vpn-settings-windows-10)).

## <a name="troubleshooting-certificates"></a>Solución de problemas de certificados

En el caso de que necesite validar que un certificado se ha implementado correctamente, use el [Administrador de certificados](certificate-manager.md) del dispositivo para comprobar que el certificado está presente.  


