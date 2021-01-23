---
title: Usar Microsoft Endpoint Manager Intune para administrar dispositivos HoloLens
description: Aprende a usar MDM para configurar CSP, directivas y administrar dispositivos de realidad mixta de HoloLens a escala con Intune.
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
ms.openlocfilehash: ce288afdcb112c17ffde75078d641f3637a8448c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283961"
---
# Usar Microsoft Endpoint Manager Intune para administrar dispositivos HoloLens

Hay muchas opciones de configuración diferentes que puedes administrar a través de MDM. El uso de dispositivos Intune se puede agrupar y las configuraciones se pueden implementar en esos grupos de usuarios o dispositivos. Las aplicaciones también se pueden implementar y administrar, configurar dispositivos para conectarse a la red, así como configurar las actualizaciones para que se produzcan en el momento deseado y en el anillo de actualización necesario. 

## Cómo administrar a través de Intune

### Categorías y grupos de dispositivos
Con Intune, puedes crear categorías de dispositivos para agregar automáticamente dispositivos a grupos en función de las categorías que crees, como Ingeniería, Médicos, Desarrolladores, entre otras. La idea es facilitar la administración de los dispositivos que ejecutan Windows Holographic for Business.
Más información: Clasificar [dispositivos en grupos](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping)

### Perfiles de configuración de dispositivos
Intune incluye opciones de configuración y características que puedes habilitar o deshabilitar en diferentes dispositivos de la organización. Estas opciones de configuración y características se administran mediante perfiles. Por ejemplo, puedes crear un perfil que habilita Cortana o usar la pantalla inteligente de Microsoft Defender en los dispositivos que ejecutan Windows Holographic for Business.
En tus perfiles, puedes usar OMA-URI para personalizar algunas opciones de configuración, crear restricciones de dispositivo y configurar una red privada virtual (VPN) y Wi-Fi.
[Introducción a los perfiles de configuración](https://docs.microsoft.com/mem/intune/configuration/device-profiles)y a la [introducción a los perfiles.](https://docs.microsoft.com/mem/intune/configuration/device-profile-create)

## Ejemplos de lo que se puede administrar y configurar

El uso de MDM para administrar dispositivos ofrece una amplia variedad de elementos que se pueden seleccionar. 

### Wi-Fi
[La configuración de Wi-Fi](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure) asigna la configuración de red inalámbrica a usuarios y dispositivos. Al asignar un perfil de Wi-Fi, los usuarios obtienen acceso a los Wi-Fi corporativos sin tener que configurarlo ellos mismos.
Obtenga más información [sobre cómo configurar la red para HoloLens](hololens-commercial-infrastructure.md)

### Certificados
Los certificados ayudan a mejorar la seguridad proporcionando autenticación de cuenta, Wi-Fi autenticación, cifrado VPN y cifrado SSL de contenido web. Aunque los administradores pueden administrar certificados en dispositivos manualmente a través de paquetes de aprovisionamiento, es un procedimiento recomendado usar el sistema MDM para administrar esos certificados durante todo su ciclo de vida, desde la inscripción hasta la renovación y la revocación. El sistema MDM puede implementar automáticamente estos certificados en los almacenes de certificados de los dispositivos después de inscribir el dispositivo (siempre que el sistema MDM admita el Protocolo simple de inscripción de certificados (SCEP) o los estándares de criptografía de clave pública #12 (PKCS#12)). MDM también puede consultar y eliminar certificados de cliente inscritos o desencadenar una nueva solicitud de inscripción antes de que el certificado actual haya expirado. 

### Proxy
La mayoría de las redes de intranet corporativas aprovechan un proxy para administrar el tráfico interno. Con HoloLens 2 puede configurar un servidor proxy para conexiones ethernet y Wi-Fi web. Esta configuración no se aplica a las conexiones VPN. Para obtener más información sobre la configuración de proxy para Windows 10, consulta [NetworkProxy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

### VPN
Con frecuencia, las organizaciones usan una VPN para controlar el acceso a las aplicaciones y los recursos de la intranet de la empresa. HoloLens 2 admite conexiones VPN SSL, que requieren un complemento descargable de Microsoft Store y son específicas del proveedor de VPN que elijas. 
- Obtenga más información [sobre VPN en HoloLens.](hololens-network.md#vpn)
- Para obtener más información sobre los perfiles de VPN, consulta [VPNv2 CSP.](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)

### Implementar y administrar aplicaciones
Con Intune, puedes agregar aplicaciones a los dispositivos que ejecutan Windows Holographic for Business. Una solución MDM permite a los responsables de la toma de decisiones de TI y a los administradores instalar automáticamente (insertar) de forma privada sus aplicaciones de línea de negocio, o comprar aplicaciones a través de la tienda para un grupo de usuarios. Hay muchas formas de implementar aplicaciones, entre las que se incluyen:
-   [Intune y portal de empresa]( app-deploy-intune.md)
-   [Microsoft Store para Business]( app-deploy-store-business.md)

Obtenga más información sobre la administración de aplicaciones a través de Intune.
-   [Agregar aplicaciones a Intune](https://docs.microsoft.com/mem/intune/apps/apps-add)
-   [Agregar aplicaciones de Microsoft Store](https://docs.microsoft.com/mem/intune/apps/store-apps-windows)
-   [Agregar aplicaciones que cree](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
- [Asignar aplicaciones a grupos](https://docs.microsoft.com/mem/intune/apps/apps-deploy)

### Actualizaciones de software
Intune incluye una característica denominada anillos de actualización para dispositivos Windows 10. Estos anillos de actualización incluyen un grupo de configuraciones que determinan cómo se instalan las actualizaciones. Por ejemplo, puede elegir entre crear una ventana de mantenimiento para instalar actualizaciones o reiniciar el dispositivo cuando estas sean instaladas Se puede aplicar un anillo de actualización a varios dispositivos que ejecutan Windows Holographic for Business.
Obtenga más información sobre cómo [administrar las actualizaciones de HoloLens](hololens-updates.md) y administrar las actualizaciones de software a través de [Intune.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)

### Configurar el modo de pantalla completa
Con las características de equipo compartido o invitado disponibles en Intune, puedes configurar dispositivos Windows Holographic for Business para que se ejecuten como quiosco. Estos dispositivos pueden ejecutar una aplicación (modo de pantalla completa de una sola aplicación) o ejecutar varias aplicaciones (modo de pantalla completa de varias aplicaciones). El modo de pantalla completa es una interfaz de usuario para controlar qué identidades tienen acceso a qué aplicaciones de forma predeterminada.
Más información sobre [cómo configurar HoloLens como quiosco]( hololens-kiosk.md)

