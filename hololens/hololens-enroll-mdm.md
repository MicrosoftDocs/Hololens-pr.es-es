---
title: Inscripción de HoloLens en la MDM
description: Inscribe HoloLens en la administración de dispositivos móviles (MDM) para facilitar la administración de varios dispositivos.
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
ms.openlocfilehash: 5adc1b48c4603f3a9d3145bef4f1d8aa1867a9d1
ms.sourcegitcommit: 5877c3e51de49f949b35ab840a3312a009a4487a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "11102329"
---
# Inscripción de HoloLens en la MDM

Puede administrar varios dispositivos de Microsoft HoloLens a la vez mediante soluciones como [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business). Podrás administrar la configuración, seleccionar qué aplicaciones se instalarán y establecer las opciones de configuración de seguridad adaptadas a las necesidades de tu organización. Consulta [Administrar dispositivos que ejecuten Windows Holographic con Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), los [proveedores de servicios de configuración (CSP) que se admiten en Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) y las [directivas compatibles con Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> La administración de dispositivos móviles (MDM), por ejemplo, las características VPN, BitLocker y de modo de pantalla completa, solo está disponible cuando actualizas a [Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## Requisitos

 Para administrar dispositivos HoloLens, tu organización debe tener configurada la configuración de la administración de dispositivos móviles (MDM). El proveedor de MDM puede ser Microsoft InTune o un proveedor externo que use las API de MDM de Microsoft.
 
## Diferentes formas de inscribirse

Según el tipo de identidad elegido durante la OOBE o el inicio de sesión de post, existen diferentes métodos de inscripción. Para obtener más información sobre cada tipo de identidad en HoloLens, visita [esta página](hololens-identity.md).

- Si Identity es AAD, entonces durante el acceso a la **aplicación de configuración**de Oobe o del  ->  botón**trabajo de la escuela**  ->  **Connect** .
    - Para AAD, la inscripción automática de MDM solo se produce si AAD se ha configurado con direcciones URL de inscripción.
- Si Identity es AAD y el dispositivo se ha preregistrado con el servidor MDM de Intune y tiene asignado un perfil de configuración específico, entonces AAD: unirse e inscripción se producirá automáticamente durante OOBE.
    - También se denomina [flujo piloto automático](hololens2-autopilot.md) disponible en las [compilaciones de 19041.1103 +](hololens-release-notes.md#windows-holographic-version-2004).
- Si Identity es MSA, use **Settings**  ->  **Access App Connect Work o**el botón School  ->  **Connect** .
    - También se conoce como agregar flujo de trabajo (AWA).
- Si se trata de una identidad de usuario local, use la configuración de la **aplicación**  ->  **Access o la escuela**  ->  **inscribirse solo en el vínculo administración de dispositivos** .
    - También se denomina flujo de inscripción de MDM puro.

Una vez que el dispositivo se haya inscrito en el servidor MDM, la aplicación configuración reflejará ahora que el dispositivo se ha inscrito en la administración de dispositivos.

## Inscripción automática en la MDM

Si la organización usa Azure Active Directory (Azure AD) y una solución de MDM que acepte un token de AAD para la autenticación (actualmente, solo se admite en Microsoft Intune y AirWatch), el administrador de TI puede configurar Azure AD para permitir automáticamente la inscripción en la MDM después de que el usuario inicie sesión con su cuenta de Azure AD. [Aprende a configurar la inscripción de Azure AD.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Cuando se habilita la inscripción automática, no es necesaria ninguna inscripción manual adicional. Si el usuario inicia sesión con una cuenta de Azure AD, el dispositivo se inscribe en la MDM después de completar la primera ejecución.

Cuando un dispositivo está unido a AAD, puede afectar a la persona que consideró al [propietario del dispositivo](security-adminless-os.md#device-owner).

## Anular inscripción de HoloLens de Intune

Para obtener más información acerca de cómo anular la inscripción a un dispositivo, visita [esta página](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment). 
