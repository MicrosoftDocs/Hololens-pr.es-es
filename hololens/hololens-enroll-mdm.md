---
title: Inscripción de HoloLens en la MDM
description: Obtenga información sobre cómo inscribir HoloLens en la administración de dispositivos móviles (MDM) para facilitar la administración de varios dispositivos.
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
ms.openlocfilehash: 624ebd17335820b1d2858f9d39cabb7032a83bfe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310209"
---
# <a name="enroll-hololens-in-mdm"></a>Inscripción de HoloLens en la MDM

Puede administrar varios dispositivos Microsoft HoloLens simultáneamente mediante soluciones [como Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business). Podrás administrar la configuración, seleccionar qué aplicaciones instalar y establecer las opciones de configuración de seguridad adaptadas a las necesidades de su organización. Consulte [Administrar dispositivos](https://docs.microsoft.com/intune/windows-holographic-for-business)que ejecutan Windows Holographic con Microsoft Intune , los proveedores de servicios de configuración [(CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)que se admiten en Windows Holographic y las directivas compatibles [con Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> La administración de dispositivos móviles (MDM), incluidas las características vpn, Bitlocker y pantalla completa, solo está disponible cuando se actualiza [a Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## <a name="requirements"></a>Requisitos

 Su organización tendrá que configurar Mobile Administración de dispositivos (MDM) para administrar dispositivos HoloLens. El proveedor de MDM puede ser Microsoft Intune o un proveedor externo que use las API de MDM de Microsoft.
 
## <a name="different-ways-to-enroll"></a>Distintas formas de inscribirse

En función del tipo de [identidad elegido](hololens-identity.md) durante la OOBE o después del inicio de sesión, hay diferentes métodos de inscripción.

- Si identity está Azure AD, durante el botón OOBE o **Configuración de App** Access Work o  ->  **School**  ->  **Connect.**
    - Por Azure AD, [la inscripción automática de MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) solo se produce si Azure AD se ha configurado con direcciones URL de inscripción.
     
- Si identity es Azure AD y el dispositivo se ha registrado previamente con el servidor MDM de Intune con un perfil de configuración específico asignado, azure AD-Join y la inscripción automática de [MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) se producirán durante la configuración automática.
    - También se [denomina Flujo de Autopilot](hololens2-autopilot.md) disponible [en las compilaciones 19041.1103+](hololens-release-notes.md#windows-holographic-version-2004).
    

- Si Identity es MSA, use el botón **Configuración de App** Access Work o  ->  **School**  ->  **Connect.**
    - También se denomina Agregar flujo de cuenta de trabajo (AWA).
- Si Identity es Usuario local, use Configuración **App**  ->  **Access Work o School** Enroll solo en el vínculo de administración de  ->  **dispositivos.**
    - También se denomina flujo de inscripción mdm pura.

Una vez que el dispositivo se inscriba con el servidor MDM, la aplicación Configuración ahora reflejará que el dispositivo está inscrito en la administración de dispositivos.

## <a name="auto-enrollment-in-mdm"></a>Inscripción automática en la MDM

Si su organización tiene una suscripción de [Azure Premium,](https://azure.microsoft.com/overview/)usa Azure Active Directory (Azure AD) y una solución MDM que acepta un token de Azure AD para la autenticación (actualmente, solo se admite en Microsoft Intune y AirWatch), el administrador de TI puede configurar Azure AD para permitir automáticamente la inscripción de MDM después de que el usuario inicie sesión con su cuenta de Azure AD. [Aprende a configurar la inscripción de Azure AD.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Cuando la inscripción automática está habilitada, no se necesita ninguna inscripción manual adicional. Si el usuario inicia sesión con una cuenta de Azure AD, el dispositivo se inscribe en la MDM después de completar la primera ejecución.

Cuando un dispositivo se Azure AD unido, puede afectar a quién consideró [el propietario del dispositivo.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>Desarollar HoloLens de Intune

Según el método de inscripción, es posible que la inscripción del dispositivo no esté disponible.

Si el dispositivo se inscribió con una Azure AD o Autopilot, no se puede inscribir desde Intune. Si desea desasociar HoloLens de Azure AD o volver Azure AD un inquilino diferente Azure AD, debe restablecer [o](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) volver a actualizar el dispositivo.

Si el dispositivo se inscribió desde una cuenta de MSA que agregó una cuenta de trabajo o desde una cuenta local que solo se inscribió en la administración de dispositivos, puede deshacer la inscripción del dispositivo. Abra el menú Inicio y, a continuación, seleccione el botón **Configuración Acceso** a la aplicación Trabajo  ->  **o Escuela**  ->  *SuCuenta*  ->  **Desconectar.**