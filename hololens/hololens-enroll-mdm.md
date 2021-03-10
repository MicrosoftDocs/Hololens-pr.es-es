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
ms.openlocfilehash: 4042cce40bea2c3d52d6ffc5d2908f6fde7cf222
ms.sourcegitcommit: 1f3ad5b099e72491f436d851738d2b6f3d4dff31
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400680"
---
# <a name="enroll-hololens-in-mdm"></a>Inscripción de HoloLens en la MDM

Puedes administrar varios dispositivos de Microsoft HoloLens simultáneamente con soluciones como [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business). Podrás administrar la configuración, seleccionar qué aplicaciones se instalarán y establecer las opciones de configuración de seguridad adaptadas a las necesidades de tu organización. Consulta [Administrar dispositivos que ejecuten Windows Holographic con Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), los [proveedores de servicios de configuración (CSP) que se admiten en Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) y las [directivas compatibles con Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> La administración de dispositivos móviles (MDM), por ejemplo, las características VPN, BitLocker y de modo de pantalla completa, solo está disponible cuando actualizas a [Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## <a name="requirements"></a>Requisitos

 Tu organización tendrá que configurar la Administración de dispositivos móviles (MDM) para administrar dispositivos HoloLens. El proveedor de MDM puede ser Microsoft InTune o un proveedor externo que use las API de MDM de Microsoft.
 
## <a name="different-ways-to-enroll"></a>Distintas formas de inscribirse

Según el tipo de identidad [elegido durante](hololens-identity.md) la OOBE o después del inicio de sesión, hay diferentes métodos de inscripción.

- Si Identity es Azure AD, ya sea durante OOBE o **configuración app**Access Work o el  ->  **botón School**  ->  **Connect.**
    - Para Azure AD, [la inscripción automática de MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) solo se produce si Azure AD se ha configurado con direcciones URL de inscripción. 
     
- Si Identity es Azure AD y el dispositivo se ha registrado previamente con el servidor MDM de Intune con un perfil de configuración específico asignado a él, se producirá la inscripción de Azure AD-Join [y MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) automática durante la OOBE.
    - También denominado [Flujo de Piloto automático](hololens2-autopilot.md) Disponible en [compilaciones 19041.1103+.](hololens-release-notes.md#windows-holographic-version-2004)
    

- Si Identity es MSA, usa **configuración App**  ->  **Access Work o el botón School**  ->  **Connect.**
    - También se denomina flujo Agregar cuenta de trabajo (AWA).
- Si Identity es Usuario local, usa **Configuración App**Access Work  ->  **o School**Enroll solo en el vínculo de administración de  ->  **dispositivos.**
    - También se denomina flujo de inscripción MDM puro.

Una vez que el dispositivo esté inscrito en el servidor MDM, la aplicación Configuración ahora reflejará que el dispositivo está inscrito en la administración de dispositivos.

## <a name="auto-enrollment-in-mdm"></a>Inscripción automática en la MDM

Si su organización tiene una suscripción a [Azure Premium](https://azure.microsoft.com/overview/), usa Azure Active Directory (Azure AD) y una solución MDM que acepta un token de Azure AD para la autenticación (actualmente, solo se admite en Microsoft Intune y AirWatch), el administrador de TI puede configurar Azure AD para permitir automáticamente la inscripción de MDM después de que el usuario inicie sesión con su cuenta de Azure AD. [Aprende a configurar la inscripción de Azure AD.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Cuando se habilita la inscripción automática, no es necesaria ninguna inscripción manual adicional. Si el usuario inicia sesión con una cuenta de Azure AD, el dispositivo se inscribe en la MDM después de completar la primera ejecución.

Cuando un dispositivo está unido a Azure AD, puede afectar a quién consideró el [propietario del dispositivo](security-adminless-os.md#device-owner).

## <a name="unenroll-hololens-from-intune"></a>Desenroll HoloLens de Intune

Aunque HoloLens 2 es un dispositivo Windows 10, no se puede simplemente deshacer la inscripción de Intune. Si desea desasoyar HoloLens de Azure AD o volver a unirse a otro inquilino de Azure AD, debe [restablecer o reflash](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) el dispositivo.