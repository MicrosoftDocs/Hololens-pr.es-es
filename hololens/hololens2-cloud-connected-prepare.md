---
title: 'Guía de implementación: implementación de la nube conectada a HoloLens 2 a escala con asistencia remota: prepararse'
description: Cómo prepararse para inscribir dispositivos HoloLens en una red conectada en la nube
keywords: HoloLens, administración, nube conectada, asistencia remota, AAD, Azure AD, MDM, administración de dispositivos móviles
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
ms.openlocfilehash: 0e9222df2c387fab8f61a585d3a7f3966b9ecd31
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196382"
---
# Preparación: Guía de conexión a la nube

Al final de este artículo, tendrá que configurar AAD, MDM y obtener más información sobre el uso de las cuentas y los requisitos de red de AAD. Esta sección de la guía le ayudará a usted y a su organización a prepararse para implementar HoloLens 2 en la nube y usar el asistente remoto de Dynamics 365. Repasaremos la importancia de cada parte de la infraestructura y también proporcionarle vínculos a las guías para ayudarle a configurar esas piezas según sea necesario.

## Conceptos básicos de la infraestructura

Para escenarios de implementación tanto personales como corporativas, un sistema MDM es la infraestructura esencial necesaria para implementar y administrar dispositivos Windows 10 Holographic. Se recomienda una suscripción a Azure AD Premium como proveedor de identidades, que además es necesaria para que se admitan ciertas funcionalidades.

### Azure Active Directory

Azure AD es un servicio de directorio en la nube que proporciona administración de identidades y acceso. Las organizaciones que usan Microsoft Office 365 o Intune ya usan Azure AD, que tiene tres ediciones: gratis, Premium P1 y Premium P2 (vea [Azure Active Directory Editions](https://azure.microsoft.com/documentation/articles/active-directory-editions)). Todas las ediciones son compatibles con el registro de dispositivos de Azure AD, pero se necesita la Premium P1 para habilitar la inscripción automática de MDM que usaremos más adelante en esta guía.

> [!IMPORTANT]
> Es esencial tener un Azure Active Directory como dispositivos HoloLens no admite la Unión local de AD. Si no&#39;ya tiene una configuración de Azure Active Directory, siga las instrucciones de este vínculo para empezar a usar y [crear un nuevo inquilino en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## Administración de identidades

Los empleados solo pueden usar una cuenta para inicializar un dispositivo, por lo que&#39;s es imprescindible que la organización controle qué cuenta está habilitada en primer lugar. La cuenta elegida determinará quién controla el dispositivo e influirá en las funcionalidades de administración.

En esta guía, elegimos que para la [identidad](https://docs.microsoft.com/hololens/hololens-identity) usada, usaremos cuentas de AAD o cuentas de Azure Active Directory. Hay varias ventajas para las cuentas de AAD que queremos usar, como:

- Los empleados usan su cuenta de Azure AD para registrar el dispositivo en Azure AD e inscribirse automáticamente con la solución MDM&#39;s de la organización (AAD + MDM; requiere Azure AD Premium).
- Las cuentas de AAD admiten [Inicio de sesión único](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on). Cuando un usuario inicia sesión en asistencia remota, se reconoce su identidad del usuario de AAD firmado y el usuario inicia sesión en la aplicación para obtener una experiencia optimizada.
- Las cuentas de AAD tienen [Opciones de autenticación](https://docs.microsoft.com/hololens/hololens-identity) adicionales a través [de Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). Además de los usuarios con el inicio de sesión de iris, los usuarios pueden iniciar sesión desde otro dispositivo o usar claves de seguridad de FIDO.

### Administración de dispositivos móviles

Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune), parte de la seguridad y movilidad de la empresa, es un sistema MDM basado en la nube que administra los dispositivos conectados a su inquilino. Al igual que Office 365, Intune usa Azure AD para la administración de identidades, por lo que los empleados usan las mismas credenciales para inscribir dispositivos en Intune que usan para iniciar sesión en Office 365. Intune también admite dispositivos que ejecutan otros sistemas operativos, como iOS y Android, para proporcionar una solución MDM completa. Para los fines de esta guía,&#39;mos concentrarnos en el uso de Intune para habilitar una implementación en la nube a escala con HoloLens 2.

> [!IMPORTANT]
> Es esencial disponer de la administración de dispositivos móviles. Si no&#39;ya está configurado, siga esta guía y empiece a usar [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up).

> [!NOTE]
> Muchos sistemas MDM admiten Windows10, y la mayoría también admiten los escenarios de implementación de dispositivos personales y corporativos. Los proveedores MDM que admiten Windows 10 Holographic actualmente son: electrowatch, MobileIron y otros. La mayoría de los principales proveedores de sistemas MDM del sector ya admiten la integración con Azure AD. Puedes encontrar los proveedores de sistemas MDM que admiten Azure AD en [Azure Marketplace](https://azure.microsoft.com/marketplace/).

## Red

En esta configuración, prevemos que los dispositivos HoloLens 2 se conectan a Internet desde cualquier red disponible de Wi-Fi abierta. Dado que es posible que un usuario tenga que cambiar la conexión de red en función de la ubicación, debe aprender a [conectar los dispositivos HoloLens a la red Wi-Fi.](https://docs.microsoft.com/hololens/hololens-network)

Para Dynamics 365 Remote Assist existen diversas condiciones de red, como el ancho de banda, la latencia, la vibración y la pérdida de paquetes, que pueden influir en la experiencia de las videollamadas. Aunque las llamadas de audio y vídeo pueden ser posibles en entornos con ancho de banda reducido, es posible que se produzca una degradación de características. Al usar el asistente remoto de Dynamics 365 en HoloLens, estos son los requisitos de red que debe tener en cuenta:

**Mínimo** : para las videollamadas de punto a punto de alta definición con la resolución de alta definición de HD 1080p de 30 fps, se necesita un máximo de 1,5 Mbps de carga/desactiva.

**Óptimo:** Para las videollamadas de calidad HD de par a par con resolución de HD 1080p, se esperarán arriba/abajo de 4-5 Mbps.

Más información:

- [Requisitos de red](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Recomendaciones de optimización de red](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### Opcional: conecta tu HoloLens a VPN

Los dispositivos que se conectan a esta guía se van a conectar a la red a través de una red de nube externa. Es posible que pueda tener acceso a los recursos de la empresa a los que&#39;necesite conectar sus dispositivos a través de VPN. Hay varias formas diferentes de conectar sus dispositivos a VPN, tanto en el caso de que el usuario final se conecte por medio de la interfaz de usuario del dispositivo, como en administrar y recibir el perfil de VPN desde PPKG o MDM. Cómo configurar VPN ganó&#39;se tratarán en este artículo, por lo que si&#39;d desea obtener más información sobre los diferentes protocolos VPN o formas de administrar la VPN, visite [estas guías para obtener información sobre HoloLens y VPN.](https://docs.microsoft.com/hololens/hololens-network#vpn)

## Paso siguiente

> [!div class="nextstepaction"]
> [Implementación de nube conectada: configurar](hololens2-cloud-connected-configure.md)
