---
title: Directrices de infraestructura para HoloLens
description: Obtenga información sobre las directrices de infraestructura para dispositivos HoloLens, incluida la compatibilidad con redes inalámbricas, la asistencia remota y la administración de dispositivos móviles.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e23bd458e26668f1f4a9a361ffaadf8fc377933e
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427389"
---
# <a name="configure-your-network-for-hololens"></a>Configuración de la red para HoloLens

Esta parte del documento necesitará las personas siguientes:

1. Administrador de red con permisos para realizar cambios en el servidor proxy o firewall
2. Administrador de Azure Active Directory
3. Administrador de dispositivos móviles

## <a name="infrastructure-requirements"></a>Requisitos de infraestructura

HoloLens es, en esencia, un dispositivo móvil con Windows integrado en Azure.  Su funcionamiento es mejor en entornos comerciales con disponibilidad de red inalámbrica (Wi-Fi) y acceso a los servicios de Microsoft.

Entre los servicios en la nube críticos se incluyen:

- Azure Active Directory (Azure AD)
- Windows Update (WU)

Para administrar dispositivos HoloLens a escala, los clientes comerciales necesitarán una infraestructura de administración de movilidad empresarial (EMM) o de administración de dispositivos móviles (MDM).  En esta guía se usa [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) como ejemplo, aunque cualquier proveedor que sea compatible con Directiva de Microsoft lo será también con HoloLens.  Pregunte a su proveedor de administración de dispositivos móviles si admiten HoloLens 2.

HoloLens admite un conjunto limitado de experiencias desconectadas en la nube.

### <a name="wireless-network-eap-support"></a>Compatibilidad con EAP de la red inalámbrica

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### <a name="hololens-specific-network-requirements"></a>Requisitos de red específicos de HoloLens

Asegúrese de que [esta lista](hololens-offline.md) de puntos de conexión se permiten en su firewall de red. Esto permitirá que HoloLens funcione correctamente.

### <a name="remote-assist-specific-network-requirements"></a>Requisitos de la red específicos de Remote Assist

1. El ancho de banda recomendado para un rendimiento óptimo de Remote Assist es de 1,5 Mbps. Consulte los [requisitos de red detallados](/MicrosoftTeams/prepare-network) para obtener información adicional.
**(Tenga en cuenta que, si la velocidad de su red no es de al menos 1,5 Mbps, Remote Assist seguirá funcionando. Sin embargo, la calidad puede verse afectada).**
1. Asegúrese de que estos puertos y estas direcciones URL están permitidos en el firewall de red para que Microsoft Teams pueda funcionar. Manténgase al día con la [lista de puertos más reciente](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

- Obtenga más información sobre los [requisitos de red específicos para Remote Assist](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements). 
- Obtenga más información sobre cómo [preparar la red de su organización para Microsoft Teams](/MicrosoftTeams/prepare-network).

### <a name="guides-specific-network-requirements"></a>Requisitos de red específicos de Guides

Guides solo requiere acceso de red para descargar y usar la aplicación.

## <a name="azure-active-directory-guidance"></a>Instrucciones de Azure Active Directory

> [!NOTE]
> Este paso solo es necesario si su empresa tiene un plan para administrar HoloLens.

1. Asegúrese de que tiene una licencia de Azure AD.
Consulte [Requisitos de licencias de HoloLens](hololens-licenses-requirements.md) para obtener información adicional.

1. Si planea usar la inscripción automática, tendrá que [configurar la inscripción de Azure AD.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)

1. Asegúrese de que los usuarios de su empresa se encuentran en Azure Active Directory (Azure AD).
Consulte las [instrucciones](/azure/active-directory/fundamentals/add-users-azure-active-directory) siguientes para agregar usuarios.

1. Recomendamos que los usuarios que necesiten licencias similares se agreguen al mismo grupo.
    1. [Crear un grupo](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [Agregar usuarios a grupos](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. Asegúrese de que los usuarios (o grupos de usuarios) de su empresa tienen asignadas las licencias necesarias.
Si necesita asignar licencias, siga estas [indicaciones](/azure/active-directory/fundamentals/license-users-groups).

1. Siga este paso solo si espera que los usuarios inscriban su dispositivo HoloLens o móvil a través de usted (hay tres opciones). Estos pasos garantizan que los usuarios (o el grupo de usuarios) de su empresa puedan agregar dispositivos.
    1. **Opción 1:** Conceder permiso a todos los usuarios para unir dispositivos a Azure AD.
**Inicie sesión en Azure Portal como administrador.**  > **Azure Active Directory** > **Dispositivos** > **Configuración del dispositivo** >
**Establezca Los usuarios pueden inscribir dispositivos en Azure AD en *Todos***

    1. **Opción 2:** Conceder a los usuarios o grupos seleccionados permiso para unir dispositivos a Azure AD **Inicie sesión en Azure Portal como administrador** > **Azure Active Directory** > **Dispositivos** > **Configuración del dispositivo** Establezca Los usuarios pueden inscribir dispositivos en Azure AD en  >
***Seleccionados***
![Imagen que muestra Configurar dispositivos unidos a Azure AD.](images/azure-ad-image.png)

    1. **Opción 3:** Puede impedir a todos los usuarios que unan sus dispositivos al dominio. Esto quiere decir que todos Ios dispositivos tendrán que inscribirse de forma manual.

## <a name="mobile-device-manager-guidance"></a>Instrucciones del administrador de dispositivos móviles

### <a name="ongoing-device-management"></a>Administración continua de dispositivos

> [!NOTE]
> Este paso es necesario solo si su empresa tiene un plan para administrar HoloLens.

La administración continua de los dispositivos dependerá de la infraestructura de administración de dispositivos móviles.  La mayoría tiene la misma funcionalidad general, pero la interfaz de usuario puede variar considerablemente.

1. Los [CSP (proveedores de servicios de configuración)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) le permiten crear e implementar la configuración de administración para los dispositivos de la red. Consulte la [lista de CSP de HoloLens](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) como referencia.

1. Las [directivas de cumplimiento](/intune/device-compliance-get-started) son las reglas y la configuración que deben tener los dispositivos para cumplir con la infraestructura de su empresa. Use estas directivas con el acceso condicional para impedir el acceso a los recursos de la compañía en los dispositivos que no sean conformes. Por ejemplo, puede crear una directiva que exija la habilitación de Bitlocker.

1. [Creación de la directiva de cumplimiento](/intune/protect/compliance-policy-create-windows).

1. El acceso condicional permite o impide que los dispositivos móviles y las aplicaciones móviles accedan a los recursos de la empresa. Dos documentos que pueden resultar útiles son [Planeamiento de la implementación de la entidad de certificación](/azure/active-directory/conditional-access/plan-conditional-access) y [Procedimientos recomendados](/azure/active-directory/conditional-access/best-practices).

1. En [este artículo](/intune/fundamentals/windows-holographic-for-business) se habla de las herramientas de administración de Intune para HoloLens.

1. [Creación del perfil de un dispositivo](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a>Administración de actualizaciones

Intune incluye una característica llamada anillos de actualización para los dispositivos con Windows 10, incluyendo HoloLens 2 y HoloLens v1 (con Holographic for Business). Los anillos de actualización incluyen un grupo de configuraciones que determinan cómo y cuándo se instalarán las actualizaciones.

Por ejemplo, puede crear una ventana de mantenimiento para instalar actualizaciones u optar por reiniciar después de instalar las actualizaciones.  También puede optar por pausar las actualizaciones de manera indefinida hasta que esté listo para aplicarlas.

Obtenga más información sobre la [configuración de anillos de actualización con Intune](/intune/windows-update-for-business-configure).

### <a name="application-management"></a>Administración de aplicaciones

Administre las aplicaciones de HoloLens a través de:

1. Microsoft Store  
  Microsoft Store es la mejor forma de distribuir y usar las aplicaciones en HoloLens.  En la tienda hay un gran conjunto de aplicaciones básicas de HoloLens que ya se encuentran disponibles o bien puede [publicar las suyas propias](/windows/uwp/publish/).  
  Todas las aplicaciones de la tienda se encuentran disponibles para el público en general; si no lo acepta, visite Microsoft Store para Empresas.  

1. [Microsoft Store para Empresas](/microsoft-store/)  
  Microsoft Store para Empresas y Education es una tienda personalizada para su entorno corporativo.  Esto le permite utilizar Microsoft Store integrado en Windows 10 y HoloLens para buscar, adquirir, distribuir y administrar aplicaciones para su organización.  También le permite implementar aplicaciones específicas para su entorno comercial pero no a escala mundial.

1. Implementación y administración de aplicaciones a través de Intune u otra solución para la administración de dispositivos móviles  
  La mayoría de las soluciones para la administración de dispositivos móviles, incluyendo Intune, proporcionan una forma de implementar aplicaciones de la línea de negocio directamente en un conjunto de dispositivos inscritos.  Consulte este artículo sobre la [instalación de aplicaciones de Intune](/intune/apps-deploy).

1. Portal de dispositivos _no recomendado_  
  Las aplicaciones también pueden instalarse directamente en HoloLens usando el Portal de dispositivos Windows.  Esto no se recomienda, ya que el modo de desarrollador tiene que estar habilitado para usar el portal de dispositivos.

Obtenga más información sobre la [instalación de aplicaciones en HoloLens](hololens-install-apps.md).

### <a name="certificates"></a>Certificados

Puede distribuir certificados a través de su proveedor de MDM. Si su empresa requiere certificados, Intune admite PKCS, PFX y SCEP. Es importante comprender cuál es el certificado adecuado para su empresa. Visite la documentación de [configuraciones de certificados](/intune/protect/certificates-configure) para determinar qué certificado es mejor para usted. Si tiene previsto usar certificados para la autenticación de HoloLens, puede que PFX o SCEP sean adecuados.

Siga los siguientes pasos para usar [SCEP](/intune/protect/certificates-profile-scep).

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a>Cómo actualizar a Holographics for Business Commercial Suite

> [!NOTE]
> Windows Holographics for Business (Commercial Suite) está destinado exclusivamente a los dispositivos HoloLens de primera generación. El perfil no se aplicará a los dispositivos HoloLens 2.

Puede encontrar instrucciones para actualizar a Commercial Suite en la documentación de [actualización holográfica](/intune/configuration/holographic-upgrade).

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a>Cómo configurar el modo de pantalla completa usando Microsoft Intune

1. Sincronice Microsoft Store con Intune (consulte las siguientes [instrucciones](/intune/apps/windows-store-for-business)).

1. Compruebe la configuración de la aplicación:
    1. Inicie sesión en su cuenta de empresa de Microsoft Store.
    1. **Administrar > Productos y servicios > Aplicaciones y software > Seleccione la aplicación que quiere sincronizar > Disponibilidad en la tienda privada > Seleccione "Todos" o "Grupos específicos"**
        >[!NOTE]
        >Si no ve la aplicación que quiere, tendrá que buscarla en la tienda para "obtenerla". **Haga clic en la barra "Buscar" de la esquina superior derecha > escriba el nombre de la aplicación > haga clic en la aplicación > seleccione "Obtener"** .
    1. Si no ve las aplicaciones en **Intune > Aplicaciones cliente > Aplicaciones**, es posible que tenga que volver a [sincronizar las aplicaciones](/intune/apps/windows-store-for-business#synchronize-apps).

1. [Crear un perfil de dispositivo para el modo de pantalla completa](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> Puede configurar diferentes usuarios para tener distintas experiencias en el modo de pantalla completa con "Azure AD" como "Tipo de inicio de sesión de usuario". Sin embargo, esta opción solo está disponible en el modo de pantalla completa de varias aplicaciones. El modo de pantalla completa de varias aplicaciones funcionará con una sola aplicación y también con varias aplicaciones.

![Imagen que muestra la configuración del modo de pantalla completa en Intune.](images/aad-kioskmode.png)

En el caso de otros servicios de MDM, consulte la documentación de su proveedor para obtener instrucciones. Consulte las instrucciones de [pantalla completa de HoloLens](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) si necesita usar una configuración personalizada y una configuración XML completa para configurar una pantalla completa en el servicio de MDM.

## <a name="certificates-and-authentication"></a>Certificados y autenticación

Los certificados se pueden implementar mediante MDM (vea "certificados" en la [Sección de MDM](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)). Los certificados también pueden implementarse en HoloLens a través del aprovisionamiento de paquetes. Consulte [Aprovisionamiento de HoloLens](hololens-provisioning.md) para obtener información adicional.

### <a name="additional-intune-quick-links"></a>Vínculos rápidos de Intune adicionales

1. [Crear perfiles:](/intune/configuration/device-profile-create) los perfiles le permiten agregar y configurar las opciones de configuración que se enviarán a los dispositivos de su organización.

