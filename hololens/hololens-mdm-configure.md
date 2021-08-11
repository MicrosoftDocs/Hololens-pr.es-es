---
title: Uso de Microsoft's Endpoint Manager Intune para administrar HoloLens dispositivos
description: Obtenga información sobre cómo usar MDM para configurar CSP, directivas y administrar HoloLens dispositivos de realidad mixta a escala mediante Intune.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/9/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 0a0f26750ff6ea881babfab44af95cbbefa0574674336934ccf1443df1701a96
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663256"
---
# <a name="using-microsofts-endpoint-manager-intune-to-manage-hololens-devices"></a>Uso de Microsoft's Endpoint Manager Intune para administrar HoloLens dispositivos

Hay numerosas configuraciones diferentes que puede administrar a través de MDM. El uso de dispositivos de Intune se puede agrupar y las configuraciones se pueden implementar en esos grupos de usuarios o dispositivos. Las aplicaciones también se pueden implementar y administrar, configurar dispositivos para conectarse a la red, así como configurar las actualizaciones para que se produzcan en el momento deseado y en el anillo de actualización necesario. 

## <a name="how-to-manage-via-intune"></a>Cómo administrar a través de Intune

### <a name="device-categories-and-groups"></a>Categorías de dispositivos y grupos
Con Intune, puede crear categorías de dispositivos para agregar automáticamente dispositivos a grupos en función de las categorías que cree, como Ingeniería, Médicos, Desarrolladores, entre otras. La idea es facilitar la administración de los dispositivos que ejecutan Windows Holographic for Business.
Más información: Clasificar [dispositivos en grupos](/mem/intune/enrollment/device-group-mapping)

### <a name="device-configuration-profiles"></a>Perfiles de configuración de dispositivos
Intune incluye opciones y características que se pueden habilitar o deshabilitar en distintos dispositivos dentro de la organización. Estos valores de configuración y características se administran mediante perfiles. Por ejemplo, puede crear un perfil que habilite Cortana o que use Microsoft Defender Smart Screen en los dispositivos con Windows Holographic for Business.
En los perfiles, puede usar OMA-URI para personalizar algunas opciones, crear restricciones de dispositivos y configurar una red privada virtual (VPN) y Wi-Fi.
[Introducción a los perfiles de configuración](/mem/intune/configuration/device-profiles)y a la [introducción al perfil](/mem/intune/configuration/device-profile-create).

## <a name="examples-of-what-can-be-managed-and-configured"></a>Ejemplos de lo que se puede administrar y configurar

El uso de MDM para administrar dispositivos proporciona una amplia gama de elementos que se pueden seleccionar. 

### <a name="wi-fi"></a>Wi-Fi
La [configuración de Wi-Fi](/mem/intune/configuration/wi-fi-settings-configure) asigna valores de configuración de red inalámbrica a los usuarios y los dispositivos. Al asignar un perfil de Wi-Fi, los usuarios obtienen acceso a los Wi-Fi corporativos sin tener que configurarlo ellos mismos.
Obtenga más información [sobre cómo configurar la red para HoloLens](hololens-commercial-infrastructure.md)

### <a name="certificates"></a>Certificados
Los certificados ayudan a mejorar la seguridad al proporcionar autenticación de cuenta, Wi-Fi, cifrado VPN y cifrado SSL de contenido web. Aunque los administradores pueden administrar certificados en dispositivos manualmente a través de paquetes de aprovisionamiento, es un procedimiento recomendado usar el sistema MDM para administrar esos certificados a lo largo de todo su ciclo de vida, desde la inscripción hasta la renovación y revocación. El sistema MDM puede implementar automáticamente estos certificados en los almacenes de certificados de los dispositivos después de inscribir el dispositivo (siempre que el sistema MDM admita los estándares de criptografía de clave pública (Protocolo de inscripción de certificados simple) o public key cryptography standards #12 (PKCS #12)). MDM también puede consultar y eliminar certificados de cliente inscritos o desencadenar una nueva solicitud de inscripción antes de que el certificado actual haya expirado. 

### <a name="proxy"></a>Proxy
La mayoría de las redes de intranet corporativas aprovechan un proxy para administrar el tráfico interno. Con HoloLens 2 puede configurar un servidor proxy para conexiones Ethernet Wi-Fi conexión. Esta configuración no se aplica a las conexiones VPN. Para más información sobre la configuración de proxy Windows 10, consulte [CSP de NetworkProxy.](/windows/client-management/mdm/networkproxy-csp)

### <a name="vpn"></a>VPN
Con frecuencia, las organizaciones usan una VPN para controlar el acceso a las aplicaciones y los recursos de la intranet de la empresa. HoloLens 2 admite conexiones VPN SSL, que requieren un complemento descargable desde el Microsoft Store y son específicos del proveedor de VPN de su elección. 
- Obtenga más información sobre [VPN en HoloLens](hololens-network.md#vpn).
- Para obtener más información sobre los perfiles de VPN, consulte [EL CSP de VPNv2.](/windows/client-management/mdm/vpnv2-csp)

### <a name="deploy-and-manage-apps"></a>Implementación y administración de aplicaciones
Con Intune, puede agregar aplicaciones a los dispositivos con Windows Holographic for Business. Una solución MDM permite a los responsables de la toma de decisiones de TI y a los administradores instalar automáticamente (insertar) de forma privada sus aplicaciones de línea de negocio interna o comprar aplicaciones a través de la tienda para un grupo de usuarios. Hay muchas maneras de implementar aplicaciones, por ejemplo:
-   [Intune y Portal de empresa]( app-deploy-intune.md)
-   [Microsoft Store para Empresas]( app-deploy-store-business.md)

Obtenga más información sobre la administración de aplicaciones a través de Intune.
-   [Agregar aplicaciones a Intune](/mem/intune/apps/apps-add)
-   [Agregar aplicaciones de Microsoft Store](/mem/intune/apps/store-apps-windows)
-   [Agregar aplicaciones que cree](/mem/intune/apps/lob-apps-windows)
- [Asignar aplicaciones a grupos](/mem/intune/apps/apps-deploy)

### <a name="software-updates"></a>Actualizaciones de software
Intune incluye una característica denominada anillos de actualización para dispositivos de Windows 10. Estos anillos de actualización incluyen un grupo de opciones que determinan cómo se instalan las actualizaciones. Por ejemplo, puede crear una ventana de mantenimiento para instalar actualizaciones u optar por reiniciar después de instalar las actualizaciones. Un anillo de actualización se puede aplicar a varios dispositivos con Windows Holographic for Business.
Obtenga más información sobre cómo administrar [actualizaciones de HoloLens y](hololens-updates.md) Administrar actualizaciones de software a través de [Intune](/mem/intune/protect/windows-update-for-business-configure).

### <a name="configure-kiosk-mode"></a>Configuración del modo de pantalla completa
Mediante las características de PC compartidas o de invitado disponibles en Intune, puede configurar los dispositivos Windows Holographic for Business para que se ejecuten como un quiosco. Estos dispositivos pueden ejecutar una aplicación (modo de pantalla completa con una sola aplicación) o varias (modo de pantalla completa con varias aplicaciones). El modo de pantalla completa es una interfaz de usuario para controlar qué identidades tienen acceso a qué aplicaciones de forma predeterminada.
Obtenga información sobre [cómo configurar HoloLens pantalla completa]( hololens-kiosk.md)

