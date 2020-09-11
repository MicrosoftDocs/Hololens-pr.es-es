---
title: Uso de Endpoint Manager de Microsoft Intune para administrar dispositivos HoloLens
description: Usar MDM para configurar CSP y directivas y administrar HoloLens a escala.
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
ms.openlocfilehash: 4fda0b271e915e82350f806418d2f02cbdd5a796
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009647"
---
# Uso de Endpoint Manager de Microsoft Intune para administrar dispositivos HoloLens

Hay numerosas configuraciones diferentes que puede administrar a través de MDM. El uso de dispositivos de Intune se puede agrupar y la configuración se puede implementar en esos grupos de usuarios o dispositivos. Las aplicaciones también se pueden implementar y administrar, configurar dispositivos para que se conecten a la red, así como configurar actualizaciones para que se realicen en el momento deseado y en el anillo de actualización necesario. 

## Cómo administrar a través de Intune

### Categorías y grupos de dispositivos
Con Intune, puede crear categorías de dispositivos para agregar automáticamente dispositivos a grupos según las categorías que cree, como ingeniería, medicina, programadores, etc. La idea es facilitar la administración de los dispositivos que ejecutan Windows Holographic para empresas.
Leer más: [clasificar los dispositivos en grupos](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping)

### Perfiles de configuración de dispositivo
Intune incluye la configuración y las características que puede habilitar o deshabilitar en diferentes dispositivos de su organización. Esta configuración y características se administran mediante perfiles. Por ejemplo, puede crear un perfil que habilite Cortana o use la pantalla inteligente de Microsoft defender para empresas.
En sus perfiles, puede usar OMA-URI para personalizar algunos ajustes, crear restricciones de dispositivos y configurar una red privada virtual (VPN) y WiFi.
Introducción [a los perfiles de configuración](https://docs.microsoft.com/mem/intune/configuration/device-profiles)e [información general del perfil](https://docs.microsoft.com/mem/intune/configuration/device-profile-create).

## Ejemplos de lo que se puede administrar y configurar

El uso de MDM para administrar dispositivos ofrece una amplia variedad de elementos que se pueden seleccionar. 

### Wi-Fi
[La configuración de Wi-Fi asigna la](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure) configuración de la red inalámbrica a usuarios y dispositivos. Al asignar un perfil de Wi-Fi, los usuarios obtienen acceso a la red Wi-Fi corporativa sin tener que configurarla por sí mismos.
Más información sobre cómo [configurar tu red para HoloLens](hololens-commercial-infrastructure.md)

### Certificados
Los certificados ayudan a mejorar la seguridad proporcionando autenticación de cuenta, autenticación Wi-Fi, cifrado de VPN y cifrado SSL de contenido Web. A pesar de que los administradores pueden administrar certificados en dispositivos de forma manual mediante paquetes de aprovisionamiento, es recomendable usar su sistema MDM para administrar esos certificados durante todo su ciclo de vida, desde la inscripción a través de la renovación y la revocación. El sistema MDM puede implementar automáticamente estos certificados en los almacenes de certificados de los dispositivos después de inscribir el dispositivo (siempre y cuando el sistema MDM admita el protocolo de inscripción de certificados simple (SCEP) o los estándares de criptografía de clave pública #12 (PKCS # 12)). MDM también puede consultar y eliminar certificados de cliente inscritos o desencadenar una nueva solicitud de inscripción antes de que venza el certificado actual. 

### Proxy
La mayoría de las redes de intranet corporativas aprovechan un proxy para administrar el tráfico interno. Con HoloLens 2 puedes configurar un servidor proxy para conexiones Ethernet y Wi-Fi. Esta configuración no se aplica a las conexiones VPN. Para obtener más información sobre la configuración de proxy para Windows 10, consulte [CSP NetworkProxy](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

### VPN
Con frecuencia, las organizaciones usan una VPN para controlar el acceso a las aplicaciones y los recursos de la intranet de la empresa. HoloLens 2 es compatible con las conexiones SSL VPN, que requieren un complemento que se pueda descargar de la tienda de Microsoft y que sean específicas del proveedor de VPN que elija. 
- Más información sobre [VPN en HoloLens](hololens-network.md#vpn).
- Para obtener más información sobre los perfiles de VPN, consulte el [CSP VPNv2](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).

### Implementar y administrar aplicaciones
Con Intune, puede agregar aplicaciones a los dispositivos que ejecutan Windows Holographic para empresas. Una solución MDM permite que los responsables de tomar decisiones de ti y los administradores se instalen automáticamente (push) sus aplicaciones internas, de línea de negocio o las aplicaciones de compra a través de la tienda para un grupo de usuarios. Hay muchas maneras de implementar aplicaciones, entre las que se incluyen:
-   [Intune y portal de la empresa]( app-deploy-intune.md)
-   [Microsoft Store para Business]( app-deploy-store-business.md)

Obtenga más información sobre la administración de aplicaciones a través de Intune.
-   [Agregar aplicaciones a Intune](https://docs.microsoft.com/mem/intune/apps/apps-add)
-   [Agregar aplicaciones de Microsoft Store](https://docs.microsoft.com/mem/intune/apps/store-apps-windows)
-   [Agregar aplicaciones creadas](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
- [Asignar aplicaciones a grupos](https://docs.microsoft.com/mem/intune/apps/apps-deploy)

### Actualizaciones de software
Intune incluye una característica denominada llamadas de actualización para dispositivos Windows 10. Estos anillos de actualización incluyen un grupo de opciones que determinan cómo se instalan las actualizaciones. Por ejemplo, puede elegir entre crear una ventana de mantenimiento para instalar actualizaciones o reiniciar el dispositivo cuando estas sean instaladas Se puede aplicar un anillo de actualización a varios dispositivos que ejecutan Windows Holographic para empresas.
Más información sobre cómo [administrar las actualizaciones de HoloLens](hololens-updates.md) y [administrar las actualizaciones de software a través de Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).

### Configurar el modo de pantalla completa
Con las características de equipos compartidos o invitados disponibles en Intune, puede configurar los dispositivos de Windows Holographic para empresas para que se ejecuten como quiosco. Estos dispositivos pueden ejecutar una aplicación (modo de pantalla completa) o ejecutar varias aplicaciones (en el modo de pantalla completa de varias aplicaciones). El modo de pantalla completa es una interfaz de usuario para controlar qué identidades tienen acceso a qué aplicaciones de forma predeterminada.
Más información sobre cómo [configurar HoloLens como quiosco]( hololens-kiosk.md)

