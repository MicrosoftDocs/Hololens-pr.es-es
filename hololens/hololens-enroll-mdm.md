---
title: Inscripción de HoloLens en la MDM
description: Aprende a inscribir HoloLens en la administración de dispositivos móviles (MDM) para facilitar la administración de varios dispositivos.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b9473f4e80f6438ef4c438711ac0de342c5327e1
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283191"
---
# Inscripción de HoloLens en la MDM

Puede administrar varios dispositivos Microsoft HoloLens simultáneamente con soluciones como [Microsoft Intune.](https://docs.microsoft.com/intune/windows-holographic-for-business) Podrás administrar la configuración, seleccionar qué aplicaciones se instalarán y establecer las opciones de configuración de seguridad adaptadas a las necesidades de tu organización. Consulta [Administrar dispositivos que ejecuten Windows Holographic con Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), los [proveedores de servicios de configuración (CSP) que se admiten en Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) y las [directivas compatibles con Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> La administración de dispositivos móviles (MDM), por ejemplo, las características VPN, BitLocker y de modo de pantalla completa, solo está disponible cuando actualizas a [Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## Requisitos

 Tu organización deberá tener configurada la Administración de dispositivos móviles (MDM) para poder administrar dispositivos HoloLens. El proveedor de MDM puede ser Microsoft InTune o un proveedor externo que use las API de MDM de Microsoft.
 
## Diferentes formas de inscribirse

Según el tipo de identidad elegido durante la OOBE o después del inicio de sesión, hay diferentes métodos de inscripción. Para obtener más información sobre cada tipo de identidad en HoloLens, visite [esta página.](hololens-identity.md)

- Si Identity es Azure AD, durante la OOBE o el botón Configuración **de Acceso**a la aplicación trabajo  ->  **o School**  ->  **Connect.**
    - Para Azure AD, la inscripción automática de MDM solo se produce si Azure AD se ha configurado con direcciones URL de inscripción.
- Si Identity es Azure AD y el dispositivo se ha registrado previamente con el servidor MDM de Intune con un perfil de configuración específico asignado, azure AD-Join y la inscripción se producirán automáticamente durante la OOBE.
    - También denominado [flujo de Autopilot](hololens2-autopilot.md) disponible en [compilaciones 19041.1103+.](hololens-release-notes.md#windows-holographic-version-2004)
- Si Identity es MSA, usa el botón Configuración **de Acceso**a la aplicación  ->  **Trabajo o School**  ->  **Connect.**
    - También denominado flujo Agregar cuenta de trabajo (AWA).
- Si Identity es Un usuario local, use Configuración **de acceso**a la aplicación Trabajo o  ->  **Escuela**  ->  **inscribirse solo en el vínculo de administración de** dispositivos.
    - También se denomina flujo de inscripción de MDM puro.

Una vez que el dispositivo se inscriba en el servidor MDM, la aplicación Configuración reflejará ahora que el dispositivo está inscrito en la administración de dispositivos.

## Inscripción automática en la MDM

Si tu organización usa Azure Active Directory (Azure AD) y una solución MDM que acepta un token de Azure AD para la autenticación (actualmente, solo se admite en Microsoft Intune y AirWatch), el administrador de TI puede configurar Azure AD para permitir automáticamente la inscripción en MDM después de que el usuario inicie sesión con su cuenta de Azure AD. [Aprende a configurar la inscripción de Azure AD.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Cuando se habilita la inscripción automática, no es necesaria ninguna inscripción manual adicional. Si el usuario inicia sesión con una cuenta de Azure AD, el dispositivo se inscribe en la MDM después de completar la primera ejecución.

Cuando un dispositivo está unido a Azure AD, puede afectar a quién considera [el propietario del dispositivo.](security-adminless-os.md#device-owner)

## Deshacer la inscripción de HoloLens en Intune

Para obtener más información sobre cómo deshacer la inscripción de un dispositivo, visita [esta página.](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment) 
