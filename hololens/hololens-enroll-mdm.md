---
title: Inscribir HoloLens en MDM
description: Inscribe HoloLens en la administración de dispositivos móviles (MDM) para facilitar la administración de varios dispositivos.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 054c4ded7496957671c055e3161a1297de7abc1a
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828695"
---
# Inscripción de HoloLens en la MDM

Puede administrar varios dispositivos de Microsoft HoloLens a la vez mediante soluciones como [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business). Podrás administrar la configuración, seleccionar qué aplicaciones se instalarán y establecer las opciones de configuración de seguridad adaptadas a las necesidades de tu organización. Consulta [Administrar dispositivos que ejecuten Windows Holographic con Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), los [proveedores de servicios de configuración (CSP) que se admiten en Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) y las [directivas compatibles con Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> La administración de dispositivos móviles (MDM), por ejemplo, las características VPN, BitLocker y de modo de pantalla completa, solo está disponible cuando actualizas a [Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## Requisitos

 Para administrar dispositivos HoloLens, tu organización debe tener configurada la configuración de la administración de dispositivos móviles (MDM). El proveedor de MDM puede ser Microsoft InTune o un proveedor externo que use las API de MDM de Microsoft.

## Inscripción automática en la MDM

Si la organización usa Azure Active Directory (Azure AD) y una solución de MDM que acepte un token de AAD para la autenticación (actualmente, solo se admite en Microsoft Intune y AirWatch), el administrador de TI puede configurar Azure AD para permitir automáticamente la inscripción en la MDM después de que el usuario inicie sesión con su cuenta de Azure AD. [Aprende a configurar la inscripción de Azure AD.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Cuando se habilita la inscripción automática, no es necesaria ninguna inscripción manual adicional. Si el usuario inicia sesión con una cuenta de Azure AD, el dispositivo se inscribe en la MDM después de completar la primera ejecución.

## Inscripción mediante la aplicación Configuración

 Si el dispositivo no se inscribe en la MDM durante la primera ejecución, el usuario puede inscribirlo manualmente en el servidor de MDM de la organización mediante la aplicación Configuración.

1. Dirígete a **Configuración** > **Cuentas** > **Obtener acceso al trabajo**.
1. Selecciona **Inscribirse en la administración de dispositivos** y especifica la cuenta de la organización. Se te redirigirá a la página de inicio de sesión de la organización.
1. Una vez que te hayas autenticado debidamente en el servidor de MDM, se mostrará un mensaje de confirmación.

El dispositivo ya estará inscrito en el servidor de MDM. Ahora la aplicación Configuración reflejará que el dispositivo está inscrito en la administración de dispositivos.

## Anular inscripción de HoloLens de Intune

No es posible [anular la inscripción](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows) de HoloLens de Intune de manera remota. Si el administrador anula la inscripción del dispositivo con MDM, el dispositivo expirará y luego se eliminará del panel de Intune.
