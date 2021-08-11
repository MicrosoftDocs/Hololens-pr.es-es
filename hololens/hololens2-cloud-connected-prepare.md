---
title: 'Guía de implementación: implementación de HoloLens 2 en la nube a escala con Remote Assist- Preparación'
description: Aprenda a prepararse para inscribir dispositivos HoloLens a través de una red conectada a la nube mediante Azure Active Directory y administración de identidades.
keywords: HoloLens, administración, conexión a la nube, Remote Assist, AAD, Azure AD, MDM, Mobile Administración de dispositivos
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f6c2e514024a171661b182a310145e26280e114a1cff65ef5b03b16feae8371a
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660163"
---
# <a name="prepare---cloud-connected-guide"></a>Preparación: Guía conectada a la nube

Al final de este artículo, habrá configurado Azure AD, MDM y comprenderá más sobre el uso de Azure AD y los requisitos de red. Esta sección de la guía le ayudará a usted y a su organización a prepararse para implementar HoloLens 2 en la nube y usar Dynamics 365 Remote Assist. Se rebaría la importancia de cada parte de la infraestructura, además de proporcionar vínculos a guías que le ayudarán a configurar esas piezas según sea necesario.

## <a name="infrastructure-essentials"></a>Aspectos básicos de la infraestructura

En escenarios de implementación personal y corporativa, un sistema MDM es la infraestructura esencial necesaria para implementar y administrar Windows 10 Holographic dispositivos. Se recomienda una suscripción a Azure AD Premium como proveedor de identidades, que además es necesaria para que se admitan ciertas funcionalidades.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD es un servicio de directorio en la nube que proporciona administración de identidades y acceso. Las organizaciones que usan Microsoft Office 365 o Intune ya usan Azure AD, que tiene tres ediciones: Gratis, Premium P1 y Premium P2 (consulte [Azure Active Directory ediciones](https://azure.microsoft.com/documentation/articles/active-directory-editions)). Todas las ediciones admiten Azure AD de dispositivos, pero Premium P1 es necesario para habilitar la inscripción automática de MDM que usaremos en esta guía más adelante.

> [!IMPORTANT]
> Es esencial tener una Azure Active Directory ya HoloLens dispositivos no admiten la unión a AD local. Si aún no&#39;una Azure Active Directory, vaya a Crear un nuevo inquilino [en Azure Active Directory](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## <a name="identity-management"></a>Administración de identidades

Los empleados solo pueden usar una cuenta para inicializar un dispositivo, por lo&#39;que la organización controle qué cuenta está habilitada en primer lugar. La cuenta elegida determinará quién controla el dispositivo e influirá en las funcionalidades de administración.

En esta guía hemos elegido [](/hololens/hololens-identity) que, para la identidad usada, usaremos Azure AD cuentas o Azure Active Directory cuentas. Hay varias ventajas para las Azure AD que nos gustaría usar, como:

- Los empleados usan su cuenta de Azure AD para registrar el dispositivo en Azure AD e inscribirlo automáticamente en la solución MDM de la organización&#39;(Azure AD+MDM: requiere Azure AD Premium).
- Azure AD admiten [el inicio de sesión único.](/azure/active-directory/manage-apps/what-is-single-sign-on) Cuando un usuario inicia sesión en Remote Assist, se reconocerá su identidad desde el usuario con sesión Azure AD y el usuario se inicia sesión en la aplicación para una experiencia simplificada.
- Azure AD cuentas tienen opciones de [autenticación adicionales](/hololens/hololens-identity) [a través de Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification). Además de Iris, los usuarios de inicio de sesión pueden iniciar sesión desde otro dispositivo o usar claves de seguridad FIDO.

### <a name="mobile-device-management"></a>Administración de dispositivos móviles

Microsoft [Intune,](/mem/intune/fundamentals/what-is-intune)parte de la Enterprise Mobility + Security, es un sistema MDM basado en la nube que administra los dispositivos conectados al inquilino. Al Office 365, Intune usa Azure AD para la administración de identidades, por lo que los empleados usan las mismas credenciales para inscribir dispositivos en Intune que usan para iniciar sesión Office 365. Intune también admite dispositivos que ejecutan otros sistemas operativos, como iOS y Android, para proporcionar una solución MDM completa. Para los fines de esta guía,&#39;nos centraremos en el uso de Intune para habilitar una implementación en la nube a escala con HoloLens 2.

> [!IMPORTANT]
> Es esencial tener mobile Administración de dispositivos. Si aún no&#39;la configuración, siga esta guía e [Introducción a Intune.](/mem/intune/fundamentals/free-trial-sign-up)

> [!NOTE]
> Muchos sistemas MDM admiten Windows 10, y la mayoría también admiten los escenarios de implementación de dispositivos personales y corporativos. Los proveedores de MDM que admiten Windows 10 Holographic actualmente incluyen: AirWatch, MobileIron y otros. La mayoría de los principales proveedores de sistemas MDM del sector ya admiten la integración con Azure AD. Puedes encontrar los proveedores de sistemas MDM que admiten Azure AD en [Azure Marketplace](https://azure.microsoft.com/marketplace/).

## <a name="network"></a>Red

En esta configuración, se prevé que HoloLens 2 dispositivos que se conectan a Internet desde cualquier red abierta Wi-Fi disponible. Dado que un usuario podría necesitar cambiar la conexión de red en función de la ubicación, debe aprender a conectar HoloLens [dispositivos a Wi-Fi.](/hololens/hololens-network)

Por Dynamics 365 Remote Assist hay una variedad de condiciones de red, como ancho de banda, latencia, vibración y pérdida de paquetes, que pueden afectar a la experiencia de videollamada. Aunque es posible realizar llamadas de audio y vídeo en entornos con ancho de banda reducido, es posible que experimente una degradación de las características. Al usar Dynamics 365 Remote Assist en HoloLens estos son los requisitos de red que debe tener en cuenta:

**Mínimo:** se requieren 1,5 Mbps de subida y bajada para las llamadas de vídeo de calidad HD punto a punto con resolución de HD 1080p a 30 fps.

**Óptimo:** En el caso de las llamadas de vídeo de calidad HD punto a punto con resolución de HD 1080p, se deben esperar 4-5 Mbps de arriba y abajo.

Más información:

- [Requisitos de red](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Recomendaciones de optimización de red](/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>Opcional: Conectar la HoloLens a VPN

Los dispositivos que se conectan en esta guía se conectarán a la red a través de y la red en la nube externa. Puede ser que para acceder a los recursos de la&#39;necesite conectar los dispositivos a través de VPN. Hay varias maneras diferentes de conectar los dispositivos a VPN, tanto donde el usuario final puede conectarse mediante la interfaz de usuario del dispositivo como los dispositivos se pueden administrar y recibir el perfil de VPN desde un PPKG o MDM. En este artículo no se explica cómo configurar vpn&#39;, por lo que si&#39;desea obtener más información sobre los distintos protocolos VPN o formas de administrar VPN, visite estas guías para obtener información sobre [HoloLens y VPN.](/hololens/hololens-network#vpn)

## <a name="next-step"></a>Paso siguiente

> [!div class="nextstepaction"]
> [Implementación conectada a la nube: configuración](hololens2-cloud-connected-configure.md)
