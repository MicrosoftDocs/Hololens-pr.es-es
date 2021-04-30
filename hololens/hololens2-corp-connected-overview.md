---
title: 'Guía de implementación: información general HoloLens 2 con conexión corporativa con las guías de Dynamics 365'
description: Aprenda a inscribir dispositivos HoloLens 2 con las guías de Dynamics 365 a través de una red conectada corporativa.
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
ms.openlocfilehash: 3041a31e6a4f8b51385fa02dfddc21d56993721d
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310221"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>Guía de implementación: Información general HoloLens 2 con dynamics 365

Esta guía ayudará a los profesionales de TI a planear e implementar Microsoft HoloLens 2 dispositivos con guías (guías) de Dynamics 365 en su organización. Esta guía es excelente para pilotos, así como para implementaciones de producción, y es similar a escenario [B: Implementación](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) dentro de la guía de red de la organización. Después de probar la prueba de concepto, use esta guía para avanzar en la integración de HoloLens en su organización.

En esta guía, se explica cómo inscribir los dispositivos en la administración de dispositivos existente, aplicar licencias según sea necesario y validar que los usuarios finales pueden usar una guía de Dynamics 365, así como usar aplicaciones de línea de negocio personalizadas, después de configurar el dispositivo. 

## <a name="prerequisites"></a>Requisitos previos

La siguiente infraestructura ya debe estar en su lugar:
- Wi-Fi
    - Red corporativa interna con acceso a recursos internos y acceso limitado a Internet o servicios en la nube
    - Autenticación de certificados basada en dispositivos.
- Azure Active Directory (Azure AD) Unirse a la inscripción automática de MDM[(Azure AD suscripción P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) necesaria)
- MDM (Intune) administrado
    - Una o varias aplicaciones se implementan a través de MDM.
- Red 
    - Certificados (SCEP o PKCS)
    - Configuración de proxy
- Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)
    - Se admiten uno o varios usuarios por dispositivo.
- Distintos niveles de configuraciones de bloqueo de dispositivos aplicadas en función de casos de uso específicos, desde Totalmente abierto hasta Pantalla completa de aplicación única.

## <a name="guides-licensing-and-requirements"></a>[Guías de licencias y requisitos](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- Cuenta de Azure AD
- Dynamics 365 Guides aplicaciones PC y HoloLens
- Suscripción a Dynamics 365 Guides
    - Microsoft Dataverse (incluido)
    - Power Apps (incluido)
- Power BI Desktop
- Conectividad de red

![Diagrama de red conectada corp](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a>Fases de implementación
### <a name="prepare"></a>Preparación
> [!div class="checklist"]
>- [Obtenga información sobre los aspectos básicos de la infraestructura HoloLens 2 dispositivos.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Obtenga más información Azure AD y configurar uno si no lo tiene.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [Obtenga información sobre la administración de identidades y cómo configurar mejor Azure AD cuentas.](hololens2-corp-connected-prepare.md#identity-management)
>- [Obtenga más información sobre MDM y configure con Intune si aún no tiene uno listo.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [Familiarícese con la Red Wi-Fi basada en certificados.](hololens2-corp-connected-prepare.md#certificates)
>- [Familiarícese con el proxy.](hololens2-corp-connected-prepare.md#proxy)
>- [Comprenda cómo puede usar aplicaciones de línea de negocio.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [Obtenga más información sobre la forma en que puede usar guías para su organización.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>Configuración
> [!div class="checklist"]
>- [Cómo crear usuarios y grupos.](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [Configuración de la inscripción automática.](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [Configuración de certificados Wi-Fi perfiles para la conectividad de Wi-Fi corporativa.](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [Cargar y asignar paquetes de aplicaciones de línea de negocio (LOB).](hololens2-corp-connected-configure.md#app-deployment)
>- [Configurar las guías de Dynamics 365.](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [Configuración del modo de pantalla completa (opcional).](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [Configuración de WDAC (opcional).](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>Implementar
> [!div class="checklist"]
>-  [Valide la inscripción a través del dispositivo y MDM.](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Valide Wi-Fi certificados.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [Valide la instalación de la aplicación LOB.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [Valide las guías a través de la creación y el funcionamiento.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>Mantenimiento
> [!div class="checklist"]
>- [Actualizar HoloLens 2.](hololens2-corp-connected-maintain.md#update-hololens)
>- [Cómo actualizar guías (almacenar aplicaciones).](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [Actualización de aplicaciones lob.](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [Plan de desarrollo.](hololens2-corp-connected-maintain.md#development-plan) 
>- [Realización de un plan de soporte técnico.](hololens2-corp-connected-maintain.md#support-plan)
>- [Opciones de administración de dispositivos.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>Paso siguiente 
> [!div class="nextstepaction"]
> [Implementación conectada corporativa: preparación](hololens2-corp-connected-prepare.md)
