---
title: 'Guía de implementación: guía de HoloLens 2 con conexión corporativa con las guías de Dynamics 365: preparación'
description: Aprenda a prepararse para inscribir dispositivos HoloLens 2 a través de una red conectada corporativa con las guías de Dynamics 365.
keywords: HoloLens, administración, conexión corporativa, guías de Dynamics 365, AAD, Azure AD, MDM, mobile Administración de dispositivos
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2ab24aeac371b8d4a17d6121c3adf317cac7daf1
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310161"
---
# <a name="prepare---corporate-connected-guide"></a>Preparación: Guía de conexión corporativa
## <a name="infrastructure-essentials"></a>Aspectos básicos de la infraestructura
En los escenarios de implementación personal y corporativa, un sistema mobile Administración de dispositivos (MDM) es la infraestructura esencial necesaria para implementar y administrar dispositivos Windows 10, especialmente el HoloLens 2. Se [recomienda Azure AD Premium suscripción](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium) como proveedor de identidades y se requiere **para** admitir ciertas funcionalidades.

> [!NOTE]
> Aunque el HoloLens 2 se implementa y administra como un dispositivo móvil, se suele usar como un dispositivo compartido entre muchos usuarios.

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD es un servicio de directorio en la nube que proporciona administración de identidades y acceso. Las organizaciones que usan Microsoft Office 365 o Intune ya usan Azure AD, que tiene tres ediciones: Gratis, Premium P1 y Premium P2 (consulte [las ediciones Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions)). Todas las ediciones admiten Azure AD de dispositivos, pero se requiere Premium P1 para habilitar la inscripción automática de MDM que usaremos en esta guía más adelante.
> [!Important]
> Es esencial tener una aplicación Azure AD dispositivos HoloLens no admiten la unión a AD local. Si aún no tiene una Azure AD, siga las instrucciones para empezar a trabajar y Crear un nuevo inquilino [en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## <a name="identity-management"></a>Administración de identidades
En esta guía, la [identidad usada](https://docs.microsoft.com/hololens/hololens-identity) se usará Azure AD cuentas. Hay varias ventajas para las Azure AD, como:
- Los empleados usan su cuenta de Azure AD para registrar el dispositivo en Azure AD y pueden inscribirlo automáticamente en la solución MDM de la organización (Azure AD+MDM: requiere una [suscripción Azure AD Premium](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium)).
- Azure AD cuentas tienen opciones de [autenticación adicionales a](https://docs.microsoft.com/hololens/hololens-identity) través [Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). Además del inicio de sesión de Iris, los usuarios pueden iniciar sesión desde otro dispositivo o usar claves de seguridad FIDO.

> [!WARNING] 
> Los empleados solo pueden usar una cuenta para inicializar un dispositivo, por lo que es imperativo que la organización **controle qué cuenta está habilitada en primer lugar.** La cuenta elegida determinará quién controla el dispositivo e influirá en las funcionalidades de administración.

## <a name="mobile-device-management"></a>Administración de dispositivos móviles
Microsoft Intune, parte de Enterprise Mobility + Security, es un sistema MDM basado en la nube que administra los dispositivos conectados al inquilino. Al igual que Office 365, Intune usa Azure AD para la administración de identidades, por lo que los empleados usan las mismas credenciales para inscribir dispositivos en Intune que usan para iniciar sesión en Office 365. Intune también admite dispositivos que ejecutan otros sistemas operativos, como iOS y Android, para proporcionar una solución MDM completa. Para los fines de esta guía, nos centraremos en el uso de Intune para habilitar una implementación en la red interna con HoloLens 2.
> [!Important] 
> Es esencial tener Mobile Administración de dispositivos. Si aún no lo tiene configurado, siga esta guía y empezar a trabajar con Intune.

> [!Important]
> Para usar guías, se requiere Azure AD cuenta.

> [!Note] 
> Muchos sistemas MDM admiten Windows 10, y la mayoría también admiten los escenarios de implementación de dispositivos personales y corporativos. Los proveedores de MDM que admiten Windows 10 Holographic incluyen: AirWatch, MobileIron y otros. La mayoría de los principales proveedores de sistemas MDM del sector ya admiten la integración con Azure AD. Puede encontrar la lista más reciente de proveedores de MDM que admiten Azure AD en [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps).

## <a name="network-access"></a>Acceso de red 
Dynamics 365 Guides es una aplicación basada en la nube. Si el administrador de red tiene una lista de aprobación, es posible que deba agregar direcciones IP o puntos de conexión necesarios para conectarse a los servidores de Dynamics 365. [Obtenga más información sobre el desbloqueo de direcciones IP y direcciones URL.](https://docs.microsoft.com/power-platform/admin/online-requirements#ip-addresses-and-urls)

## <a name="certificates"></a>Certificados
Los certificados ayudan a mejorar la seguridad al proporcionar autenticación de cuenta, Wi-Fi, cifrado VPN y cifrado SSL de contenido web. Aunque los administradores pueden administrar certificados en dispositivos manualmente a través del aprovisionamiento de paquetes, es un procedimiento recomendado usar el sistema MDM para administrar esos certificados a lo largo de todo su ciclo de vida, desde la inscripción hasta la renovación y la revocación. 

El sistema MDM puede implementar automáticamente estos certificados en los almacenes de certificados de los dispositivos después de inscribirlos (siempre que el sistema MDM admita los estándares de criptografía de clave pública **(SCEP)** o Protocolo de inscripción de certificados simple #12 **(PKCS #12).** [Obtenga información sobre los tipos de certificado y los perfiles que usa con Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/certificates-configure). MDM también puede consultar y eliminar certificados de cliente inscritos o desencadenar una nueva solicitud de inscripción antes de que el certificado actual haya expirado.
 
Si los sistemas MDM ya están configurados para certificados, consulte Preparación de certificados y perfiles de red para [HoloLens 2 para](https://docs.microsoft.com/hololens/hololens-certificates-network) empezar a implementar certificados y perfiles para los dispositivos HoloLens 2 dispositivos.

## <a name="scep"></a>SCEP

Los siguientes servicios son necesarios para la implementación de SCEP, a excepción del servidor web Application Proxy Server.
- [Entidad de certificación](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [Rol de servidor NDES](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Conector de Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

También debe publicar la dirección URL de NDES externa a la red corporativa mediante Azure AD proxy de aplicación [o proxy de acceso web.](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-add-on-premises-application) También puede usar el proxy inverso que prefiera.

![Flujo de datos SCEP](./images/hololens2-scep-info-flow.png)

Si la red aún no admite SCEP o no está seguro de si la red está configurada correctamente para SCEP con Intune, consulte Configuración de la infraestructura para admitir SCEP con [Intune.](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure)

Si la infraestructura ya admite SCEP, [](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-certificate-profiles) deberá crear un perfil para cada certificado SCEP que HoloLens 2 va [a](https://docs.microsoft.com/mem/intune/protect/certificates-profile-scep) usar. Si tiene problemas con SCEP, use Solución de problemas de uso de perfiles de certificado [SCEP](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles)para aprovisionar certificados con Microsoft Intune .

## <a name="pkcs"></a>PKCS
Intune también admite el uso de certificados de par de claves públicas y privadas (PKCS). Referencia [Use certificados de clave pública y](https://docs.microsoft.com/mem/intune/protect/certificates-pfx-configure) privada en Microsoft Intune para obtener más información.

## <a name="proxy"></a>Proxy
La mayoría de las redes de intranet corporativas aprovechan un proxy para administrar el tráfico externo. Con HoloLens 2 puede configurar un servidor proxy para conexiones Ethernet, Wi-Fi VPN.

Hay varios tipos diferentes de proxy y formas de configurar el proxy. Para los fines de esta guía, estamos optando por elegir el **proxy de Wi-Fi,** establecer a través de la dirección URL de PAC e implementar a través de MDM. Esto incluye las ventajas de implementarse a través de MDM automáticamente, poder actualizar el archivo PAC en lugar de usar una configuración server:port y, por último, usar un proxy Wi-Fi para configurar el proxy para que solo se aplique a una única conexión Wi-Fi, lo que permite que los dispositivos se usen todavía si están conectados en otra ubicación. 


Para más información sobre la configuración de proxy Windows 10, consulte Creación de un perfil de Wi-Fi para dispositivos [en Microsoft Intune: Azure.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure)

## <a name="line-of-business-apps"></a>Aplicaciones de línea de negocio 
Aunque se pueden instalar varias aplicaciones a través del Microsoft Store, es probable que tenga su propia aplicación personalizada que ha creado específicamente para usarla en la realidad mixta. Estas aplicaciones personalizadas distribuidas en toda la organización para su empresa se denominan aplicaciones de línea de negocio (LOB).
  
Hay varias maneras de implementar aplicaciones para HoloLens 2 dispositivos. Las aplicaciones se pueden implementar directamente a través de MDM, Microsoft Store para Empresas (MSfB) o se pueden descargar localmente a través de un paquete de aprovisionamiento. Para esta guía, implementaremos aplicaciones a través de MDM, mediante el uso de la instalación de la aplicación necesaria. Esto permitirá que las aplicaciones de LOB se descarguen automáticamente en los dispositivos HoloLens una vez que finalicen la inscripción.

Para aquellos usuarios que no tengan su propio LOB, se proporcionará una aplicación de ejemplo para probar este flujo de implementación. Esta aplicación será la aplicación de ejemplos de [MRTK](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) y ya se ha creado previamente y empaquetado para probar la prueba de concepto.
 
Puede encontrar más detalles sobre la implementación de aplicaciones en [Administración de aplicaciones: Información general.](https://docs.microsoft.com/hololens/app-deploy-overview)

> [!NOTE]
> HoloLens 2 solo admite la ejecución de aplicaciones arm64 para UWP.

## <a name="guides-playbook"></a>Cuaderno de guías
Guides usa un entorno de Microsoft Dataverse como almacén de datos para las aplicaciones guides. Es importante comprender la imagen más amplia de cómo interactúa el entorno de Dataverse con las aplicaciones guides y el inquilino. En esta guía no se explica cómo administrar el inverso de datos, pero se revisan los conceptos básicos para implementar las guías de [Dynamics 365: Dynamics 365 Mixed Reality](https://docs.microsoft.com/dynamics365/mixed-reality/guides/admin-deployment-playbook).

## <a name="next-step"></a>Paso siguiente 
> [!div class="nextstepaction"]
> [Implementación conectada corporativa: configurar](hololens2-corp-connected-configure.md)