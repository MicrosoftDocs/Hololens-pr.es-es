---
title: Inscripción de HoloLens en la MDM
description: Obtenga información sobre cómo inscribir HoloLens administración de dispositivos móviles (MDM) para facilitar la administración de varios dispositivos.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/15/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b6206f7121d1ba78908d96f71c5c809ec97b06d5
ms.sourcegitcommit: 6c8406bbcc79c1f624736cc68e1aaeab70436902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2021
ms.locfileid: "127904351"
---
# <a name="enroll-hololens-in-mdm"></a>Inscripción de HoloLens en la MDM

Puede administrar varios dispositivos Microsoft HoloLens simultáneamente mediante soluciones [como Microsoft Intune](/intune/windows-holographic-for-business). Podrás administrar la configuración, seleccionar qué aplicaciones instalar y establecer las opciones de configuración de seguridad adaptadas a las necesidades de su organización. Consulte Administración de dispositivos que ejecutan [Windows Holographic](/intune/windows-holographic-for-business)con Microsoft Intune , los proveedores de servicios de configuración [(CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)que se admiten en Windows Holographic y las directivas admitidas [por Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> La administración de dispositivos móviles (MDM), incluidas las características VPN, BitLocker y el modo de pantalla completa, solo está disponible cuando se actualiza [a Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## <a name="requirements"></a>Requisitos

 Su organización tendrá que configurar mobile Administración de dispositivos (MDM) para administrar HoloLens dispositivos. El proveedor de MDM puede ser Microsoft Intune o un proveedor externo que use las API de MDM de Microsoft.

## <a name="different-ways-to-enroll"></a>Distintas formas de inscribirse

Según el tipo de identidad [elegido durante](hololens-identity.md) la OOBE o después del inicio de sesión, hay diferentes métodos de inscripción.

- Si identity está Azure AD, durante OOBE o **Configuración App** Access Work  ->  **o School**  ->  **Conectar** botón.
    - Por Azure AD, [la inscripción automática de MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) solo se produce si Azure AD se ha configurado con direcciones URL de inscripción.

- Si identity es Azure AD y el dispositivo se ha registrado previamente con el servidor MDM de Intune con un perfil de configuración específico asignado, azure AD-Join y la inscripción automática de [MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) se producirán durante la OOBE.
    - También se [denomina flujo de Autopilot](hololens2-autopilot.md) disponible en [las compilaciones 19041.1103+.](hololens-release-notes.md#windows-holographic-version-2004)


- Si Identity es MSA, use Configuración **App**  ->  **Access Work or School**  ->  **Conectar** botón.
    - También se denomina agregar flujo de cuenta de trabajo (AWA).
- Si Identity es Usuario local, use el vínculo **Configuración App** Access Work o School Enroll only in device management (Inscribir solo en la administración  ->    ->  **de dispositivos).**
    - También se denomina flujo de inscripción mdm pura.

Una vez inscrito el dispositivo con el servidor MDM, la aplicación Configuración ahora reflejará que el dispositivo está inscrito en la administración de dispositivos.

## <a name="auto-enrollment-in-mdm"></a>Inscripción automática en la MDM

Si su organización tiene una suscripción [de Azure Premium](https://azure.microsoft.com/overview/), usa Azure Active Directory (Azure AD) y una solución MDM que acepta un token de Azure AD para la autenticación (actualmente solo se admite en Microsoft Intune y AirWatch), el administrador de TI puede configurar Azure AD para permitir automáticamente la inscripción de MDM después de que el usuario inicie sesión con su cuenta de Azure AD. [Aprende a configurar la inscripción de Azure AD.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Cuando la inscripción automática está habilitada, no se necesita ninguna inscripción manual adicional. Si el usuario inicia sesión con una cuenta de Azure AD, el dispositivo se inscribe en la MDM después de completar la primera ejecución.

Cuando un dispositivo está Azure AD unido, puede afectar a quién consideró [el propietario del dispositivo.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>Desenrollar HoloLens de Intune

Dependiendo del método de inscripción, es posible que la inscripción del dispositivo no esté disponible.

Si el dispositivo se inscribió con una cuenta Azure AD o Autopilot, no se puede inscribir desde Intune. Si desea unirse HoloLens de Azure AD o volver a unirse a un inquilino diferente Azure AD, debe restablecer o [volver](hololens-recovery.md#reset-the-device) a actualizar el dispositivo.

Si el dispositivo se inscribió desde una cuenta de MSA que agregó una cuenta de trabajo o desde una cuenta local que solo se inscribió en la administración de dispositivos, puede deshacer la inscripción del dispositivo. Abra el menú Inicio y, a continuación, **seleccione Configuración App** Access Work or  ->  **School**  ->  *YourAccount*  ->  **Disconnect (Desconectar** de la cuenta de su cuenta).

## <a name="enrollment-troubleshooting"></a>Solución de problemas de inscripción

### <a name="ensure-valid-license-is-assigned-to-the-user"></a>Asegúrese de que la licencia válida está asignada al usuario.

Consulte Solución de Windows problemas de inscripción de dispositivos [en Microsoft Intune](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors) específicamente en las secciones siguientes, es decir, Compruebe las [restricciones](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#check-device-type-restrictions) de tipo de dispositivo y Asigne una licencia válida [al usuario.](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#assign-a-valid-license-to-the-user)

### <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>Asegúrese de que la inscripción de MDM no está bloqueada para Windows dispositivos

Para que la inscripción se realice correctamente, deberá asegurarse de que los dispositivos HoloLens pueden inscribirse. Dado que HoloLens se considera un dispositivo Windows, no tendrá que haber ninguna restricción de inscripción que pueda bloquear la implementación. [Revise esta lista de restricciones](/mem/intune/enrollment/enrollment-restrictions-set) y asegúrese de que podrá inscribir los dispositivos.