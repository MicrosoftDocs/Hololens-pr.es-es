---
title: Planeamiento de la implementación de HoloLens 2 en un entorno comercial
description: Obtenga información sobre las necesidades principales para implementar y administrar HoloLens en entornos empresariales, incluida la infraestructura, Azure Active Directory y la administración de dispositivos móviles.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 43162389eae82bc09135c62acd40d71048d14db1
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639087"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>Planeamiento de la implementación de HoloLens 2 en un entorno comercial

## <a name="overview"></a>Información general

> [!NOTE]
> Esta información general está pensada para ayudar a los profesionales de TI a comprender las consideraciones para implementar y administrar Microsoft HoloLens 2 dispositivos dentro de una organización. Para los usuarios finales del dispositivo, consulte [Get your HoloLens 2 ready to use](hololens2-setup.md) to get started (Preparar la HoloLens 2 para empezar a usar).

HoloLens 2 se ejecuta en Windows 10 Holographic que proporciona a las organizaciones tecnologías de administración de aplicaciones y dispositivos móviles sólidas, flexibles y integradas. Windows 10 Holographic admite la administración del ciclo de vida de los dispositivos de un extremo a otro para proporcionar a las empresas control sobre sus dispositivos, datos y aplicaciones. La HoloLens 2 se puede incorporar fácilmente a los procedimientos estándar del ciclo de vida, desde la inscripción de dispositivos, la configuración y la administración de aplicaciones hasta el mantenimiento y la retirada mediante una solución completa de administración de dispositivos móviles.

Los siguientes pasos y vídeo pueden ayudarle a guiarse por el proceso de adopción HoloLens 2 dentro de su organización.

| &nbsp; | &nbsp; |
|--|--|
| ![Paso 1](images/1green.png)| <br/> **[Escenarios comunes de implementación:](hololens-requirements.md)** comprenda los escenarios de implementación y explore los componentes principales necesarios para implementar HoloLens 2 dispositivos. |
| ![Paso 2](images/2green.png)| <br/> **[Preparar:](#prepare)** familiarícese con los aspectos básicos de la infraestructura necesarios para HoloLens 2. |
| ![Paso 3](images/3green.png) | <br/> **[Configurar](#configure)**: aprenda a configurar los componentes esenciales para una implementación basada en la nube. |
| ![Paso 4](images/4green.png) | <br/> **[Implementar:](#deploy)** descubra cómo implementar los dispositivos y distribuir las aplicaciones de forma segura y eficaz. |
| ![Paso 5](images/5green.png) | <br/> **[Mantener:](#maintain)** descubra lo que se necesita para mantener correctamente el estado de los dispositivos HoloLens 2 y garantizar el cumplimiento de la directiva corporativa. |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a>Preparación

Obtenga información sobre los servicios de infraestructura esenciales necesarios para admitir el conjunto completo de HoloLens 2 funcionalidades.

| Componente | Descripción |
|-----------|------------|
| [Azure AD](hololens-identity.md) | Proporciona administración de identidades y acceso para el HoloLens 2  |
| [Administración de dispositivos móviles](hololens-mdm-configure.md)| Administra HoloLens 2 dispositivos conectados al inquilino  |
| [Red Wi-Fi](hololens-commercial-infrastructure.md)| Wi-Fi está disponible y los dispositivos se pueden conectar a Internet  |

## <a name="configure"></a>Configuración

Use Intune y Autopilot como soluciones poco táctiles para inscribir y configurar HoloLens 2 en el inquilino de Azure AD y MDM de la organización.

| Componente | Descripción |
|-----------|------------|
| [Inscripción automática](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | Después del inicio de sesión inicial, los dispositivos se registran automáticamente con Azure AD se inscriben en MDM.  |
| [Licencias de aplicación](hololens2-cloud-connected-configure.md#application-licenses)| Se puede aplicar a usuarios, grupos de usuarios o grupos de dispositivos  |
| [Usuarios y grupos de Azure](hololens2-cloud-connected-configure.md#azure-users-and-groups) | Ayuda a asignar configuraciones y licencias para el HoloLens 2  |

## <a name="deploy"></a>Implementar

Distribuya los HoloLens 2 y valide su configuración. 

| Componente | Descripción |
|-----------|------------|
| [Validación de inscripción](hololens2-corp-connected-deploy.md#enrollment-validation) | Compruebe que el dispositivo Azure AD unido desde Configuración o Azure Portal |
| [Validación de certificados](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | Compruebe la configuración y compruebe que se han distribuido correctamente. |
| [Validación de las instalaciones de aplicaciones](hololens2-corp-connected-deploy.md#validate-lob-app-install) | Confirme que la aplicación está presente y trabajando en su HoloLens 2 |

## <a name="maintain"></a>Mantenimiento

Use Windows Update for Business junto con el sistema MDM o el Microsoft Store para mantener actualizada la flota de HoloLens 2 aplicaciones y aplicaciones.

| Componente | Descripción |
|-----------|------------|
| [Actualizar HoloLens 2](hololens-updates.md) | Configurar las actualizaciones según sea necesario a través Windows actualizaciones para empresas |
| [Actualización de aplicaciones](app-deploy-overview.md) | Configuración mediante el sistema MDM o el Microsoft Store
