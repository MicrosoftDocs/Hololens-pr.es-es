---
title: 'Guía de implementación: HoloLens 2 conectado corporativamente con guías de Dynamics 365: preparar'
description: Obtenga información sobre cómo prepararse para inscribir dispositivos HoloLens 2 a través de una red conectada corporativa con guías de Dynamics 365.
keywords: HoloLens, administración, con conexión corporativa, Guías de Dynamics 365, AAD, Azure AD, MDM, Administración de dispositivos móviles
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
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448625"
---
# <a name="prepare---corporate-connected-guide"></a>Prepare - Corporate Connected Guide
## <a name="infrastructure-essentials"></a>Infrastructure Essentials
Para escenarios de implementación personal y corporativa, un sistema de administración de dispositivos móviles (MDM) es la infraestructura esencial necesaria para implementar y administrar dispositivos Con Windows 10, especialmente holoLens 2. Se [recomienda una suscripción de Azure AD Premium](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium) como proveedor de identidades **y** se requiere para admitir determinadas funcionalidades.

> [!NOTE]
> Aunque HoloLens 2 se implementa y administra como un dispositivo móvil, generalmente se usa como un dispositivo compartido entre muchos usuarios.

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD es un servicio de directorio en la nube que proporciona administración de identidades y acceso. Las organizaciones que usan Microsoft Office 365 o Intune ya usan Azure AD, que tiene tres ediciones: Gratis, Premium P1 y Premium P2 (vea Ediciones de [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions)). Todas las ediciones admiten el registro de dispositivos de Azure AD, pero premium P1 es necesario para habilitar la inscripción automática mdm que usaremos en esta guía más adelante.
> [!Important]
> Es esencial tener un Azure AD ya que los dispositivos HoloLens no admiten la unión a AD local. Si aún no tiene una configuración de Azure AD, siga las instrucciones para empezar y Cree un nuevo inquilino [en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## <a name="identity-management"></a>Administración de identidades
En esta guía, la [identidad usada](https://docs.microsoft.com/hololens/hololens-identity) será cuentas de Azure AD. Hay varias ventajas para las cuentas de Azure AD, como:
- Los empleados usan su cuenta de Azure AD para registrar el dispositivo en Azure AD y pueden inscribirlo automáticamente en la solución MDM de la organización (Azure AD+MDM: requiere una suscripción a [Azure AD Premium).](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium)
- Las cuentas de Azure AD tienen opciones de [autenticación adicionales](https://docs.microsoft.com/hololens/hololens-identity) [a través de Windows Hello para empresas.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) Además del inicio de sesión de Iris, los usuarios pueden iniciar sesión desde otro dispositivo o usar claves de seguridad FIDO.

> [!WARNING] 
> Los empleados solo pueden usar una cuenta para inicializar un dispositivo, por lo que es imperativo que la organización **controle qué cuenta está habilitada en primer lugar**. La cuenta elegida determinará quién controla el dispositivo e influirá en las funcionalidades de administración.

## <a name="mobile-device-management"></a>Administración de dispositivos móviles
Microsoft Intune, parte de Enterprise Mobility + Security, es un sistema MDM basado en la nube que administra los dispositivos conectados al inquilino. Al igual que Office 365, Intune usa Azure AD para la administración de identidades, por lo que los empleados usan las mismas credenciales para inscribir dispositivos en Intune que usan para iniciar sesión en Office 365. Intune también admite dispositivos que ejecutan otros sistemas operativos, como iOS y Android, para proporcionar una solución MDM completa. Para los fines de esta guía, nos centraremos en usar Intune para habilitar una implementación en la red interna con HoloLens 2.
> [!Important] 
> Es esencial tener administración de dispositivos móviles. Si aún no lo tiene configurado, siga esta guía y Introducción a Intune.

> [!Important]
> Para usar guías, se requiere una cuenta de Azure AD.

> [!Note] 
> Muchos sistemas MDM admiten Windows10, y la mayoría también admiten los escenarios de implementación de dispositivos personales y corporativos. Los proveedores MDM compatibles con Windows 10 Holographic incluyen: AirWatch, MobileIron y otros. La mayoría de los principales proveedores de sistemas MDM del sector ya admiten la integración con Azure AD. Puedes encontrar la lista más actual de proveedores mdm que admiten Azure AD en [Azure Marketplace.](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps)

## <a name="network-access"></a>Acceso a la red 
Guías de Dynamics 365 es una aplicación basada en la nube. Si el administrador de red tiene una lista de aprobación, es posible que deba agregar direcciones IP o puntos de conexión necesarios para conectarse a los servidores de Dynamics 365. [Obtenga más información sobre cómo desbloquear direcciones IP y direcciones URL.](https://docs.microsoft.com/power-platform/admin/online-requirements#ip-addresses-and-urls)

## <a name="certificates"></a>Certificados
Los certificados ayudan a mejorar la seguridad proporcionando autenticación de cuentas, Wi-Fi, cifrado VPN y cifrado SSL de contenido web. Aunque los administradores pueden administrar certificados en dispositivos manualmente a través de paquetes de aprovisionamiento, es una práctica recomendada usar el sistema MDM para administrar esos certificados durante todo su ciclo de vida, desde la inscripción hasta la renovación y la revocación. 

El sistema MDM puede implementar automáticamente estos certificados en los almacenes de certificados de los dispositivos después de inscribirlos (siempre que el sistema MDM admita el Protocolo simple de inscripción de certificados **(SCEP)** o los estándares de criptografía de clave **pública #12 (PKCS#12).** [Obtenga información sobre los tipos de certificado y los perfiles que usa con Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/certificates-configure). MDM también puede consultar y eliminar certificados de cliente inscritos o desencadenar una nueva solicitud de inscripción antes de que el certificado actual haya expirado.
 
Si los sistemas MDM ya están configurados para certificados, haga referencia a Preparar certificados y perfiles de red para [HoloLens 2](https://docs.microsoft.com/hololens/hololens-certificates-network) para empezar a implementar certificados y perfiles para sus dispositivos HoloLens 2.

## <a name="scep"></a>SCEP

Los siguientes servicios son necesarios para la implementación de SCEP, a excepción del servidor proxy de aplicación web.
- [Entidad de certificación](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [Rol de servidor NDES](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Conector de Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

También debe publicar la dirección URL de NDES externa a la red corporativa mediante el proxy de aplicación de [Azure AD o el](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-add-on-premises-application)proxy de acceso web . También puede usar otro proxy inverso de su elección.

![Flujo de datos SCEP](./images/hololens2-scep-info-flow.png)

Si la red aún no es compatible con SCEP o no está seguro de si la red está configurada correctamente para SCEP con Intune, haga referencia a Configurar la infraestructura para admitir  [SCEP](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure)con Intune .

Si la infraestructura ya es compatible [](https://docs.microsoft.com/mem/intune/protect/certificates-profile-scep) con [](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-certificate-profiles) SCEP, deberá crear un perfil para cada certificado SCEP que hololens 2 usará. Si tiene problemas con SCEP, use Solucionar problemas de uso de perfiles de certificado [SCEP](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles)para aprovisionar certificados con Microsoft Intune .

## <a name="pkcs"></a>PKCS
Intune también admite el uso de certificados de par de claves públicas y privadas (PKCS). Referencia [Use certificados de clave pública y privada en Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/certificates-pfx-configure) para obtener más información.

## <a name="proxy"></a>Proxy
La mayoría de las redes de intranet corporativas aprovechan un proxy para administrar el tráfico externo. Con HoloLens 2 puede configurar un servidor proxy para conexiones ethernet, Wi-Fi y VPN.

Hay varios tipos diferentes de proxy y formas de configurar el proxy. Para los fines de esta guía, optamos por elegir proxy **Wi-Fi,** establecer a través de la dirección URL de PAC e implementar a través de MDM . Esto incluye las ventajas de implementarse a través de MDM automáticamente, poder actualizar el archivo PAC en lugar de usar una configuración server:port y, por último, usar un proxy Wi-Fi para configurar proxy para que solo se aplique a una única conexión Wi-Fi que permita que los dispositivos se usen aún si están conectados en otra ubicación. 


Para obtener más información sobre la configuración de proxy para Windows 10, consulta Crear un perfil Wi-Fi para dispositivos [en Microsoft Intune - Azure](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure).

## <a name="line-of-business-apps"></a>Línea de aplicaciones empresariales 
Aunque se pueden instalar varias aplicaciones a través de la Microsoft Store, es probable que tenga su propia aplicación personalizada que haya creado específicamente para usarla en realidad mixta. Estas aplicaciones personalizadas distribuidas en toda la organización para su empresa se denominan aplicaciones de línea de negocio (LOB).
  
Hay varias maneras de implementar aplicaciones en dispositivos HoloLens 2. Las aplicaciones se pueden implementar directamente a través de MDM, la Microsoft Store para empresas(MSfB) o se pueden descargar de forma local a través de un paquete de aprovisionamiento. Por el bien de esta guía, implementaremos aplicaciones a través de MDM, mediante el uso de la instalación necesaria de la aplicación. Esto permitirá que las aplicaciones de LOB se descarguen automáticamente en los dispositivos HoloLens una vez que finalicen la inscripción.

Para aquellos que no tengan su propia LOB, proporcionaremos una aplicación de ejemplo para probar este flujo de implementación. Esta aplicación será la aplicación [ejemplos de MRTK](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) y ya se ha precompilado y empaquetado para probar la prueba de concepto.
 
Puede encontrar más detalles sobre la implementación de aplicaciones en [Administración de aplicaciones: Información general.](https://docs.microsoft.com/hololens/app-deploy-overview)

> [!NOTE]
> HoloLens 2 solo admite la ejecución de aplicaciones ARM64 para UWP.

## <a name="guides-playbook"></a>Guías Playbook
Las guías usan un entorno de Microsoft Dataverse como almacén de datos para las aplicaciones de Guías. Es importante comprender la imagen más amplia de cómo interactúa el entorno de Dataverse con las aplicaciones de Guías y el inquilino. No vamos a cubrir cómo administrar el dataverse en esta guía, pero revise Conceptos básicos para implementar Guías de [Dynamics 365 : Dynamics 365 Mixed Reality](https://docs.microsoft.com/dynamics365/mixed-reality/guides/admin-deployment-playbook).

## <a name="next-step"></a>Paso siguiente 
> [!div class="nextstepaction"]
> [Implementación conectada corporativa: configurar](hololens2-corp-connected-configure.md)