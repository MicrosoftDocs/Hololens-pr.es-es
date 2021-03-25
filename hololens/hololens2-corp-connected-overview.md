---
title: 'Guía de implementación: HoloLens 2 conectado corporativamente con guías de Dynamics 365: información general'
description: Obtenga información sobre cómo inscribir dispositivos HoloLens 2 con guías de Dynamics 365 a través de una red conectada corporativa.
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
ms.openlocfilehash: 3041a31e6a4f8b51385fa02dfddc21d56993721d
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448627"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>Guía de implementación: HoloLens conectado corporativo 2 con guías de Dynamics 365: información general

Esta guía ayudará a los profesionales de TI a planear e implementar dispositivos de Microsoft HoloLens 2 con guías de Dynamics 365 en su organización. Esta guía es ideal para pilotos, así como para implementaciones de producción y es similar a la Guía de red de escenario [B: Implementar](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) dentro de la organización. Después de probar la prueba de concepto, use esta guía para avanzar en la integración de HoloLens en su organización.

En esta guía, se explica cómo inscribir los dispositivos en la administración de dispositivos existente, aplicar licencias según sea necesario y validar que los usuarios finales puedan operar una Guía de Dynamics 365, así como usar aplicaciones de línea de negocio personalizadas, después de configurar el dispositivo. 

## <a name="prerequisites"></a>Requisitos previos

La siguiente infraestructura ya debe estar en su lugar:
- Wi-Fi
    - Red corporativa interna con acceso a recursos internos y acceso limitado a internet o servicios en la nube
    - Autenticación de certificados basada en dispositivos.
- Azure Active Directory (Azure AD) Únase a la inscripción automática mdm (se necesita[una suscripción a Azure AD P1)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
- Mdm (Intune) administrado
    - Una o varias aplicaciones se implementan a través de MDM.
- Red 
    - Certificados (SCEP o PKCS)
    - Configuración de proxy
- Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)
    - Se admiten usuarios individuales o múltiples por dispositivo.
- Distintos niveles de configuraciones de bloqueo de dispositivos aplicadas en función de casos de uso específicos, desde Totalmente abierto hasta Quiosco de aplicación única.

## [<a name="guides-licensing-and-requirements"></a>Guías de licencias y requisitos](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- Cuenta de Azure AD
- Dynamics 365 Guía aplicaciones PC y HoloLens
- Suscripción a Guías de Dynamics 365
    - Microsoft Dataverse (incluido)
    - Power Apps (incluido)
- Power BI Desktop
- Conectividad de red

![Diagrama de red conectada corp](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a>Fases de implementación
### <a name="prepare"></a>Preparar
> [!div class="checklist"]
>- [Obtenga información sobre los aspectos esenciales de la infraestructura para dispositivos HoloLens 2.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Obtenga más información sobre Azure AD y configure uno si no lo tiene.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [Obtenga información sobre la administración de identidades y cómo configurar mejor las cuentas de Azure AD.](hololens2-corp-connected-prepare.md#identity-management)
>- [Obtén más información sobre MDM y configura con Intune si aún no tienes uno listo.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [Familiarícese con el Wi-Fi basado en certificados.](hololens2-corp-connected-prepare.md#certificates)
>- [Familiarícese con proxy.](hololens2-corp-connected-prepare.md#proxy)
>- [Comprenda cómo puede usar line of business apps.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [Obtenga más información sobre la forma en que puede usar guías para su organización.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>Configurar
> [!div class="checklist"]
>- [Cómo crear usuarios y grupos.](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [Cómo configurar la inscripción automática.](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [Cómo configurar Wi-Fi certificados y perfiles para la conectividad Wi-Fi corporativa.](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [Cargar y asignar paquetes de aplicaciones de línea de negocio (LOB).](hololens2-corp-connected-configure.md#app-deployment)
>- [Configurar guías de Dynamics 365.](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [Cómo configurar el modo de pantalla completa (opcional).](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [Cómo configurar WDAC (opcional).](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>Implementar
> [!div class="checklist"]
>-  [Validar la inscripción a través del dispositivo y MDM.](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Validar Wi-Fi certificados.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [Validar la instalación de la aplicación de LOB.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [Validar guías a través de la creación y el funcionamiento.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>Mantener
> [!div class="checklist"]
>- [Actualizar HoloLens 2.](hololens2-corp-connected-maintain.md#update-hololens)
>- [Cómo actualizar guías (almacenar aplicaciones).](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [Cómo actualizar aplicaciones de LOB.](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [Plan de desarrollo.](hololens2-corp-connected-maintain.md#development-plan) 
>- [Crear un plan de soporte técnico.](hololens2-corp-connected-maintain.md#support-plan)
>- [Opciones de administración de dispositivos.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>Paso siguiente 
> [!div class="nextstepaction"]
> [Implementación conectada corporativa: preparar](hololens2-corp-connected-prepare.md)
