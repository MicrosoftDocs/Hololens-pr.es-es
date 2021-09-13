---
title: Información general sobre las aplicaciones conectadas HoloLens 2 la nube con Remote Assist
description: Aprenda a inscribir dispositivos HoloLens 2 a través de una red conectada a la nube mediante Dynamics 365 Remote Assist.
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
ms.openlocfilehash: 66e543dd699edbd54ab41474f3ea86fa313bf6ba
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033519"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Guía de implementación: información general HoloLens 2 conexión a Remote Assist en la nube

Esta guía ayudará a los profesionales de TI a planear e implementar Microsoft HoloLens 2 dispositivos con Remote Assist en su organización. Esto servirá como modelo para las implementaciones de prueba de concepto en su organización en varios HoloLens 2 de uso. La configuración es similar a [Escenario A: Implementación en dispositivos de conexión a la nube.](common-scenarios.md#scenario-a) 

Durante la guía, se explica cómo inscribir los dispositivos en la administración de dispositivos, aplicar licencias según sea necesario y validar que los usuarios finales pueden usar inmediatamente Remote Assist tras la configuración del dispositivo. Para ello, se refirtendrán los elementos importantes de la infraestructura necesarios para configurarse y ejecutarse, con lo que se consigue la implementación a escala con HoloLens 2. No se aplicarán otras restricciones o configuraciones de dispositivos en esta guía; sin embargo, le recomendamos que explore esas opciones después de finalizar.

## <a name="prerequisites"></a>Requisitos previos

La siguiente infraestructura debe estar en su lugar para implementar el HoloLens 2. Si no es así, la configuración de Azure e Intune se incluye en esta guía:

Se trata de una configuración similar a [Escenario A:](/hololens/common-scenarios#scenario-a)Implementación en dispositivos de conexión a la nube, que es una buena opción para muchas implementaciones de prueba de concepto, que incluirá:

- Wi-Fi las redes están totalmente abiertas a Internet y a los servicios en la nube
- Azure AD unirse a la inscripción automática de MDM: administrado por MDM (Intune)
- Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)
    - Se admiten uno o varios usuarios por dispositivo.

:::image type="content" alt-text="Escenario conectado a la nube." source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>Más información sobre Remote Assist

Remote Assist permite el mantenimiento y la reparación colaborativos, la inspección remota, así como el uso compartido de conocimientos y el entrenamiento. Al conectar a personas en diferentes roles y ubicaciones, un técnico que usa Remote Assist puede conectarse con un colaborador remoto en Microsoft Teams. Pueden combinar vídeo, capturas de pantalla y anotaciones para resolver problemas en tiempo real incluso cuando no están en la misma ubicación. Los colaboradores remotos pueden insertar imágenes de referencia, esquemas y otra información útil del espacio físico del técnico para que puedan hacer referencia al esquema mientras trabajan de forma rápida y sin manos en HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>Remote Assist licencias y requisitos

- Cuenta de Azure AD (necesaria para comprar la suscripción y asignar licencias)
- [Suscripción a Remote Assist](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (o [prueba de Remote Assist](/dynamics365/mixed-reality/remote-assist/try-remote-assist))
    
#### <a name="dynamics-365-remote-assist-user"></a>Usuario de Dynamics 365 Remote Assist

- Licencia de Remote Assist
- Conectividad de red

#### <a name="microsoft-teams-user"></a>Usuario de Microsoft Teams

- Microsoft Teams o [Teams Freemium](https://products.office.com/microsoft-teams/free).
- Conectividad de red

Si planea implementar este [escenario entre inquilinos](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), puede que necesite una licencia de Barreras a la información. Para determinar si se requiere una licencia de Barrera de información, consulte [Proveedores y clientes usan funcionalidades Dynamics 365 Remote Assist completa.](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation)

## <a name="in-this-guide-you-will"></a>Esta guía le permitirá:

Preparación:

> [!div class="checklist"]
> - [Obtenga información sobre los aspectos básicos de la infraestructura HoloLens 2 dispositivos.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Obtenga más información Azure AD y configure una si no&#39;la tiene.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Obtenga información sobre la administración de identidades y cómo configurar mejor Azure AD cuentas.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Obtenga más información sobre MDM y configure intune si no&#39;ya tiene uno listo.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Obtenga información sobre los requisitos de red de Remote Assist.](hololens2-cloud-connected-prepare.md#network)
> - [Opcionalmente: VPN para conectarse a recursos de la organización](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Configurar lo siguiente:

> [!div class="checklist"]
> - [Cómo crear usuarios y grupos.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Configuración de la inscripción automática en Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Asignación de licencias de aplicación.](hololens2-cloud-connected-configure.md#application-licenses)

Implementación:

> [!div class="checklist"]
> - [Configure los HoloLens 2 y valide la inscripción.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Valide que puede realizar una Remote Assist llamada.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Mantener:

> [!div class="checklist"]
> - [Cómo actualizar Remote Assist con la Microsoft Store aplicación.](hololens2-cloud-connected-maintain.md#updates)
> - [Realización de un plan de soporte técnico.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Plan de desarrollo.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Paso siguiente

> [!div class="nextstepaction"]
> [Implementación conectada a la nube: preparación](hololens2-cloud-connected-prepare.md)

