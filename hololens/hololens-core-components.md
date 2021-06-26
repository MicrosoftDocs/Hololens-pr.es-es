---
title: Planeación HoloLens 2 implementación en un entorno comercial
description: Obtenga información sobre las necesidades básicas para implementar y administrar HoloLens en entornos empresariales, como la infraestructura, Azure Active Directory y la administración de dispositivos móviles.
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
ms.openlocfilehash: 684059b1ab91860dc6af63cbd6f0927876fefb8c
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961479"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>Planeación HoloLens 2 implementación en un entorno comercial

## <a name="overview"></a>Información general
> [!NOTE]
> Esta información general está pensada para ayudar a los profesionales de TI a comprender las consideraciones para implementar y administrar Microsoft HoloLens 2 dispositivos dentro de una organización. Para los usuarios finales del dispositivo, [consulte Los aspectos básicos](hololens2-setup.md) para empezar.

HoloLens 2 ejecuta en Windows 10 Holographic que proporciona a las organizaciones tecnologías sólidas, flexibles y integradas de administración de aplicaciones y dispositivos móviles. Windows 10 Holographic admite la administración del ciclo de vida de los dispositivos de un extremo a otro para proporcionar a las empresas el control sobre sus dispositivos, datos y aplicaciones. La HoloLens 2 se puede incorporar fácilmente a las prácticas estándar del ciclo de vida, desde la inscripción de dispositivos, la configuración y la administración de aplicaciones hasta el mantenimiento y la retirada mediante una completa solución de administración de dispositivos móviles.

Los pasos siguientes pueden ayudarle a través del proceso de adopción HoloLens 2 dentro de su organización.

| | |
|--|--|
| ![Paso 1](images/1green.png)| <br/> **[Escenarios de implementación comunes:](hololens-requirements.md)** comprenda los escenarios de implementación y explore los componentes principales necesarios para implementar HoloLens 2 dispositivos. |
| ![Paso 2](images/2green.png)| <br/> **[Preparar:](#prepare)** familiarícese con los aspectos básicos de la infraestructura necesarios para HoloLens 2. |
| ![Paso 3](images/3green.png) | <br/> **[Configurar:](#configure)** aprenda a configurar los componentes esenciales para una implementación basada en la nube. |
| ![Paso 4](images/4green.png) | <br/> **[Implementar:](#deploy)** descubra cómo implementar los dispositivos y distribuir las aplicaciones de forma segura y eficaz. |
| ![Paso 5](images/5green.png) | <br/> **[Mantener:](#maintain)** descubra lo que se necesita para mantener correctamente el estado de los dispositivos HoloLens 2 y garantizar el cumplimiento de la directiva corporativa. |

## <a name="prepare"></a>Preparación

Obtenga información sobre los servicios de infraestructura esenciales necesarios para admitir el conjunto completo de HoloLens 2 funcionalidades. 

| Componente | Descripción |
|-----------|------------|
| [Azure AD](hololens-identity.md) | Proporciona administración de identidades y acceso para el HoloLens 2  |
| [Administración de dispositivos móviles](hololens-mdm-configure.md)| Administra HoloLens 2 dispositivos conectados al inquilino  |
| [Red Wi-Fi](hololens-commercial-infrastructure.md)| Wi-Fi está disponible y los dispositivos se pueden conectar a Internet  |

## <a name="configure"></a>Configuración

Use Intune y Autopilot como soluciones poco táctiles para inscribir y configurar HoloLens 2 en el inquilino de Azure AD de la organización y MDM.

| Componente | Descripción |
|-----------|------------|
| [Inscripción automática](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | Después del inicio de sesión inicial, los dispositivos se registran automáticamente con Azure AD se inscriben en MDM.  |
| [Licencias de aplicación](hololens2-cloud-connected-configure.md#application-licenses)| Se puede aplicar a usuarios, grupos de usuarios o grupos de dispositivos  |
| [Usuarios y grupos de Azure](hololens2-cloud-connected-configure.md#azure-users-and-groups) | Ayuda a asignar configuraciones y licencias para el HoloLens 2  |

## <a name="deploy"></a>Implementar

Distribuya los HoloLens 2 y valide su configuración. 

| Componente | Descripción |
|-----------|------------|
| [Validación de inscripción](hololens2-corp-connected-deploy.md#enrollment-validation) | Validación de que el dispositivo Azure AD unido desde la configuración o Azure Portal |
| [Validación de certificados](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | Comprobar la configuración y validar que se han distribuido correctamente |
| [Validación de las instalaciones de aplicaciones](hololens2-corp-connected-deploy.md#validate-lob-app-install) | Confirme que la aplicación está presente y trabajando en su HoloLens 2 |

## <a name="maintain"></a>Mantenimiento

Use Windows Update para empresas junto con el sistema MDM o el Microsoft Store para mantener actualizada la flota de HoloLens 2 y las aplicaciones.

| Componente | Descripción |
|-----------|------------|
| [Actualizar HoloLens 2](hololens-updates.md) | Configurar las actualizaciones según sea necesario a través de Actualizaciones de Windows para empresas |
| [Actualización de aplicaciones](app-deploy-overview.md) | Configuración mediante el sistema MDM o la Microsoft Store
