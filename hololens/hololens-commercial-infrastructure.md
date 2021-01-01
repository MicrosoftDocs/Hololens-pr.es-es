---
title: Directrices de infraestructura de HoloLens
description: Directrices de infraestructura para dispositivos HoloLens
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
ms.openlocfilehash: a67aaa5df4c74531b5bed88abaa266b00de5c406
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253167"
---
# Configura tu red para HoloLens

Esta parte del documento necesitará las personas siguientes:

1. Administrador de red con permisos para realizar cambios en el servidor proxy o firewall
2. Administrador de Azure Active Directory
3. Administrador de dispositivos móviles

## Requisitos de infraestructura

HoloLens es, en esencia, un dispositivo Windows Mobile integrado en Azure.  Su funcionamiento es mejor en entornos comerciales con disponibilidad de red inalámbrica (Wi-Fi) y acceso a los servicios Microsoft.

Entre los servicios de nube críticos se incluyen:

- Azure Active Directory (Azure AD)
- Windows Update (WU)

Para administrar los dispositivos HoloLens a escala, los clientes comerciales necesitarán una infraestructura de gestión de movilidad empresarial (EMM) o de gestión de dispositivos móviles (MDM).  En esta guía se usa[Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) como ejemplo, aunque cualquier proveedor compatible con Microsoft Policy es compatible con HoloLens.  Pregunte a su proveedor de administración de dispositivos móviles si son compatibles con HoloLens 2.

HoloLens admite un conjunto limitado de experiencias desconectadas en la nube.

### Compatibilidad con EAP de red inalámbrica

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### Requisitos de red específicos de HoloLens

Asegúrese de que [esta lista](hololens-offline.md) de puntos de conexión se permiten en su Firewall de red. Esto permitirá que HoloLens funcione correctamente.

### Requisitos de la red específicos de Remote Assist

1. El ancho de banda recomendado para un rendimiento óptimo de Remote Assist es 1,5 Mbps. Encontrará información sobre los requisitos de red e información adicional [aquí](https://docs.microsoft.com/MicrosoftTeams/prepare-network).
**(Tenga en cuenta que, si la velocidad de su red no es de al menos 1,5 Mbps, el asistente remoto seguirá funcionando. Sin embargo, es posible que se vea afectada la calidad).**
1. Asegúrese de que estos puertos y URL estén permitidos en el firewall de red. Esto permitirá que Microsoft Teams funcione. La lista más reciente se puede encontrar [aquí](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

- Obtenga más información sobre los [Requisitos de red específicos para la asistencia remota](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements). 
- Obtenga más información sobre cómo [Preparar la red de su organización para Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)

### Requisitos de red específicos de Guías

Las guías solo necesitan acceso de red para descargar y usar la aplicación.

## Instrucciones de Azure Active Directory

> [!NOTE]
> Este paso es necesario solo si su empresa tiene un plan para administrar las aplicaciones HoloLens.

1. Asegúrese de que tiene una licencia de Azure AD.
Para obtener más información, vea los [requisitos de licencias de HoloLens](hololens-licenses-requirements.md).

1. Si tiene previsto usar la inscripción automática, tendrá que [configurar la inscripción a Azure AD.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)

1. Asegúrese de que los usuarios de su empresa se encuentren en Azure Active Directory (Azure AD).
Encontrará instrucciones para agregar usuarios [aquí](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory).

1. Recomendamos que los usuarios que necesiten licencias similares se agreguen al mismo grupo.
    1. [Crear un grupo](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [Agregar usuarios a grupos](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. Asegúrese de que los usuarios (o grupos de usuarios) de su empresa tienen asignadas las licencias necesarias.
Encontrará las instrucciones para asignar licencias [aquí](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).

1. Siga este paso sólo si espera que los usuarios inscriban su dispositivo HoloLens o móvil a través de usted (hay tres opciones). Estos pasos aseguran que los usuarios (o grupo de usuarios) de su empresa puedan agregar dispositivos.
    1. **Opción 1:** Conceder permiso a todos los usuarios para unir dispositivos a Azure AD.
**Inicie sesión en Microsoft Azure Portal como administrador** > **Azure Active Directory** > **Dispositivos** > **Configuración de dispositivos** >
**Establezca Los usuarios puedan unir dispositivos a Azure AD en *Todos***

    1. **Opción 2:** Conceder permisos a los usuarios y grupos seleccionados para unir los dispositivos a Azure AD **Inicie sesión como administrador en el Microsoft Azure Portal** > **Azure Active Directory** > **Dispositivos** > **Configuración de dispositivos** >
**Establecer que los usuarios puedan unir dispositivos a Azure AD en *Seleccionados***
![Imagen que muestra la configuración de los dispositivos unidos a Azure AD](images/azure-ad-image.png)

    1. **Opción 3:** Puede impedir a todos los usuarios que unan sus dispositivos al dominio. Esto quiere decir que todos Ios dispositivos tendrán que ser inscritos de forma manual.

## Instrucciones del administrador de dispositivos móviles

### Administración continua de dispositivos

> [!NOTE]
> Este paso es necesario solo si su empresa tiene un plan para administrar las aplicaciones HoloLens.

La administración continua de los dispositivos dependerá de la infraestructura de la administración de dispositivos móviles.  La mayoría tiene la misma funcionalidad general, pero la interfaz de usuario puede variar considerablemente.

1. [Proveedores de servicios de configuración (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) le permite crear e implementar la configuración de administración de los dispositivos de la red. Encontrará una lista de los CSP para HoloLens [aquí](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices).

1. Las [directivas de cumplimiento](https://docs.microsoft.com/intune/device-compliance-get-started) son las reglas y la configuración que deben tener los dispositivos para cumplir con la infraestructura de su empresa. Use estas directivas con el acceso condicional para bloquear el acceso a los recursos de la compañía en los dispositivos que no sean compatibles. Por ejemplo, puede crear una directiva que requiera que se habilite BitLocker.

1. [crear una directiva de cumplimiento](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).

1. El acceso condicional permite o impide que los dispositivos móviles y las aplicaciones móviles obtengan acceso a los recursos de la empresa. Le puede ser útil disponer de dos documentos [planear la implementación de la entidad emisora de certificados](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) y [procedimientos recomendados](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).

1. [este artículo](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) habla sobre las herramientas de administración de Intune para HoloLens.

1. [Crear un perfil de dispositivo](https://docs.microsoft.com/intune/configuration/device-profile-create)

### Administrar actualizaciones

Intune incluye una función llamada timbres de actualización para los dispositivos de Windows 10, incluyendo HoloLens 2 y HoloLens v1 (con Holographic for Business). Los timbres de actualización incluyen un grupo de configuraciones que determinan cómo y cuándo se instalarán las actualizaciones.

Por ejemplo, puede elegir entre crear una ventana de mantenimiento para instalar actualizaciones o reiniciar el dispositivo cuando estas sean instaladas  También puede optar por pausar las actualizaciones de manera indefinida hasta que esté listo para actualizar.

Obtenga más información sobre la [configuración de los timbres de actualización con Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).

### Administración de aplicaciones

Administrar las aplicaciones de HoloLens a través de:

1. Microsoft Store  
  La Microsoft Store es la mejor forma de distribuir y usar las aplicaciones dentro de HoloLens.  En la tienda hay un gran conjunto de aplicaciones básicas de HoloLens que ya se encuentran disponibles o bien puede [publicar su propia aplicación](https://docs.microsoft.com/windows/uwp/publish/).  
  Todas las aplicaciones de la tienda se encuentran disponibles para el público en general, en caso de que no lo esté, visite Microsoft Store para Empresas.  

1. [Microsoft Store para Business](https://docs.microsoft.com/microsoft-store/)  
  Microsoft Store para Empresas y Education son tiendas personalizadas para el entorno corporativo.  Esto le permite utilizar la Microsoft Store integrada en Windows 10 y HoloLens para buscar, adquirir, distribuir y administrar aplicaciones para su empresa.  También le permite implementar aplicaciones específicas a su entorno comercial pero no a escala mundial.

1. Implementación y administración de aplicaciones a través de Intune u otra solución para la administración de dispositivos móviles  
  La mayoría de las soluciones para la administración de dispositivos móviles, incluyendo a Intune, proporcionan una forma de implementar aplicaciones de la línea de negocios directamente a un conjunto de dispositivos inscritos.  Vea este artículo para [instalar la aplicación Intune](https://docs.microsoft.com/intune/apps-deploy).

1. El portal de dispositivos _no es recomendable_  
  Las aplicaciones también pueden ser instaladas directamente en HoloLens usando el Portal de dispositivos Windows.  Esto no es recomendable ya que el modo de desarrollador tiene que estar habilitado para usar el portal de dispositivos.

Obtenga más información sobre la [instalación de aplicaciones en HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).

### Certificados

Puede distribuir los certificados mediante su proveedor de MDM. Si su empresa requiere certificados, Intune soporta PKCS, PFX, y SCEP. Es importante comprender cuál es el certificado adecuado para su empresa. Visite [este vínculo](https://docs.microsoft.com/intune/protect/certificates-configure) para determinar cuál es el certificado más adecuado para usted. Si tiene previsto usar certificados para la autenticación de HoloLens, puede que PFX o SCEP sean adecuados.

Puede encontrar los pasos requeridos para SCEP [aquí](https://docs.microsoft.com/intune/protect/certificates-profile-scep).

### Cómo actualizar a Holographics for Business Commercial Suite

> [!NOTE]
> Windows Holographics for Business (commercial suite) está destinado exclusivamente para los dispositivos de primera generación de HoloLens. No se aplicará el perfil en los dispositivos HoloLens 2.

Puede encontrar las instrucciones para la actualización a la commercial suite [aquí](https://docs.microsoft.com/intune/configuration/holographic-upgrade).

### Cómo configurar el modo de pantalla completa usando Microsoft Intune

1. Sincronizar Microsoft Store con Intune ([aquí](https://docs.microsoft.com/intune/apps/windows-store-for-business)).

1. Comprobar la configuración de la aplicación
    1. Inicie sesión en su cuenta de empresa de Microsoft Store
    1. **Administrar > Productos y servicios > Aplicaciones y software > Seleccione la aplicación que quiere sincronizar > Disponibilidad en la tienda privada > Seleccione "todos" o "grupos específicos"**
        >[!NOTE]
        >Si no ve la aplicación que quiere, tendrá que "obtenerla" buscándola en la tienda. **Haga clic en la barra de búsqueda de la esquina superior derecha > escriba el nombre de la aplicación > haga clic en la aplicación > seleccione "Obtener"**.
    1. Si no puede ver sus aplicaciones en **Intune > Aplicaciones cliente > Aplicaciones**, es posible que tenga que volver a [sincronizar las aplicaciones](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps).

1. [Crear un perfil de dispositivo para el modo de pantalla completa](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> Puede configurar diferentes usuarios para tener distintas experiencias en el modo de pantalla completa con "Azure AD" como "tipo de inicio de sesión de usuario". Sin embargo, esta opción solo está disponible en el modo de pantalla completa de varias aplicaciones. El modo de pantalla completa de varias aplicaciones funcionará con una sola aplicación y con varias aplicaciones.

![Imagen que muestra la configuración del modo de pantalla completa en Intune](images/aad-kioskmode.png)

Para ver otros servicios de MDM, consulte la documentación de su proveedor para obtener las instrucciones. Si necesita utilizar una configuración personalizada y una configuración XML completa para habilitar la pantalla completa en su servicio de MDM, puede encontrar instrucciones adicionales [aquí](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

## Certificados y autenticación

Los certificados se pueden implementar mediante MDM (vea "certificados" en la sección [MDM](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)). Los certificados también pueden ser agregados a HoloLens a través del aprovisionamiento de paquetes. Para obtener más información, vea el [aprovisionamiento de HoloLens](hololens-provisioning.md).

### Vínculos rápidos de Intune adicionales

1. [Crear perfiles:](https://docs.microsoft.com/intune/configuration/device-profile-create) los perfiles le permiten agregar y configurar las opciones que se enviarán a los dispositivos de su organización.

