---
title: 'Guía de implementación: implementación de HoloLens 2 conectada en la nube a escala con asistencia remota: preparar'
description: Aprende a prepararte para inscribir dispositivos HoloLens a través de una red conectada a la nube mediante Azure Active Directory y la administración de identidades.
keywords: HoloLens, administración, conectado a la nube, Asistencia remota, AAD, Azure AD, MDM, Administración de dispositivos móviles
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
ms.openlocfilehash: 067917396631f9a89a50b13ef1b7dcca8b631f52
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283871"
---
# Preparar: Guía conectada a la nube

Al final de este artículo habrás configurado Azure AD, MDM y más información sobre cómo usar las cuentas de Azure AD y los requisitos de red. Esta sección de la guía le ayudará a usted y a su organización a prepararse para implementar HoloLens 2 en la nube y usar Dynamics 365 Remote Assist. Se trata de la importancia de cada parte de la infraestructura, así como de vínculos a guías que le ayudarán a configurar esas piezas según sea necesario.

## Infrastructure Essentials

Para escenarios de implementación personal y corporativa, un sistema MDM es la infraestructura esencial necesaria para implementar y administrar dispositivos Holográficos de Windows 10. Se recomienda una suscripción a Azure AD Premium como proveedor de identidades, que además es necesaria para que se admitan ciertas funcionalidades.

### Azure Active Directory

Azure AD es un servicio de directorio en la nube que proporciona administración de identidades y acceso. Las organizaciones que usan Microsoft Office 365 o Intune ya usan Azure AD, que tiene tres ediciones: gratuita, Premium P1 y Premium P2 (vea las ediciones de [Azure Active Directory).](https://azure.microsoft.com/documentation/articles/active-directory-editions) Todas las ediciones admiten el registro de dispositivos de Azure AD, pero se requiere Premium P1 para habilitar la inscripción automática de MDM que usaremos en esta guía más adelante.

> [!IMPORTANT]
> Es esencial tener Azure Active Directory, ya que los dispositivos HoloLens no admiten la unión a AD local. Si aún no&#39;una configuración de Azure Active Directory, siga las instrucciones de este vínculo para empezar y crear un nuevo inquilino [en Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)

## Administración de identidades

Los empleados solo pueden usar una cuenta para inicializar un dispositivo, por lo que es&#39;imperativo que la organización controle qué cuenta está habilitada en primer lugar. La cuenta elegida determinará quién controla el dispositivo e influirá en las funcionalidades de administración.

En esta guía, hemos [](https://docs.microsoft.com/hololens/hololens-identity) elegido que para la identidad usada usaremos cuentas de Azure AD o cuentas de Azure Active Directory. Hay varias ventajas para las cuentas de Azure AD que nos gustaría usar, como:

- Los empleados usan su cuenta de Azure AD para registrar el dispositivo en Azure AD e inscribirlo automáticamente en la solución MDM de la organización&#39;(Azure AD+MDM, requiere Azure AD Premium).
- Las cuentas de Azure AD [admiten el inicio de sesión único.](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) Cuando un usuario inicia sesión en asistencia remota, se reconocerá su identidad del usuario que ha iniciado sesión en Azure AD y el usuario inicia sesión en la aplicación para una experiencia optimizada.
- Las cuentas de Azure AD tienen opciones [de autenticación adicionales](https://docs.microsoft.com/hololens/hololens-identity) [a través de Windows Hello para empresas.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) Además de iris, los usuarios de inicio de sesión pueden iniciar sesión desde otro dispositivo o usar claves de seguridad FIDO.

### Administración de dispositivos móviles

Microsoft [Intune,](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)parte de Enterprise Mobility + Security, es un sistema MDM basado en la nube que administra los dispositivos conectados a su inquilino. Al igual que Office 365, Intune usa Azure AD para la administración de identidades, por lo que los empleados usan las mismas credenciales para inscribir dispositivos en Intune que usan para iniciar sesión en Office 365. Intune también admite dispositivos que ejecutan otros sistemas operativos, como iOS y Android, para proporcionar una solución MDM completa. Para los fines de esta guía,&#39;nos centraremos en el uso de Intune para habilitar una implementación en la nube a escala con HoloLens 2.

> [!IMPORTANT]
> Es esencial tener administración de dispositivos móviles. Si aún no&#39;la configuración, siga esta guía y [introducción a Intune.](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)

> [!NOTE]
> Muchos sistemas MDM admiten Windows10, y la mayoría también admiten los escenarios de implementación de dispositivos personales y corporativos. Los proveedores de MDM que admiten Windows 10 Holographic actualmente incluyen: AirWatch, MobileIron y otros. La mayoría de los principales proveedores de sistemas MDM del sector ya admiten la integración con Azure AD. Puedes encontrar los proveedores de sistemas MDM que admiten Azure AD en [Azure Marketplace](https://azure.microsoft.com/marketplace/).

## Red

En esta configuración, anticipamos que los dispositivos HoloLens 2 se conectan a Internet desde cualquier red Wi-Fi abierta disponible. Dado que un usuario podría necesitar cambiar la conexión de red en función de la ubicación, debe aprender a conectar [dispositivos HoloLens a Wi-Fi.](https://docs.microsoft.com/hololens/hololens-network)

Para dynamics 365 Remote Assist hay una variedad de condiciones de red, como ancho de banda, latencia, vibración y pérdida de paquetes, que pueden afectar a su experiencia de videollamada. Aunque las llamadas de audio y vídeo pueden ser posibles en entornos con ancho de banda reducido, es posible que experimente una degradación de las características. Al usar Dynamics 365 Remote Assist en HoloLens, estos son los requisitos de red a tener en cuenta:

**Mínimo:** 1,5 Mbps arriba/abajo es necesario para videollamadas de calidad HD punto a punto con resolución de HD 1080p a 30 fps.

**Óptimo:** Para videollamadas de calidad HD punto a punto con resolución de HD 1080p, debe esperarse un aumento/bajada de 4-5 Mbps.

Más información:

- [Requisitos de red](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Recomendaciones de optimización de red](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### Opcional: Conectar HoloLens a VPN

Los dispositivos que se conectan a esta guía se conectarán a la red a través de una red en la nube externa. Puede ser que para acceder a los recursos de la empresa&#39;que necesites conectar los dispositivos a través de VPN. Hay varias formas de conectar los dispositivos a vpn, tanto donde el usuario final puede conectarse a través de la interfaz de usuario del dispositivo, como los dispositivos pueden administrarse y recibir el perfil de VPN desde un PPKG o MDM. La configuración de VPN&#39;no se trata en este artículo, por lo que si&#39;quieres obtener más información sobre los diferentes protocolos de VPN o formas de administrar VPN, visita estas guías para obtener información sobre [HoloLens](https://docs.microsoft.com/hololens/hololens-network#vpn) y VPN.

## Paso siguiente

> [!div class="nextstepaction"]
> [Implementación conectada a la nube: configurar](hololens2-cloud-connected-configure.md)
