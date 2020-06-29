---
title: Compartir HoloLens con varias personas
description: Puede configurar HoloLens para que lo compartan varias cuentas de Azure Active Directory o por varios usuarios que usen una sola cuenta.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829609"
---
# Compartir HoloLens con varias personas

Es común compartir un HoloLens con muchas personas o que muchas personas compartan un conjunto de dispositivos HoloLens.  En este artículo se describen las diferentes maneras en las que puede compartir un dispositivo.

## Compartir con varias personas, cada una usando su propia cuenta

**Requisito previo**: el dispositivo HoloLens debe ejecutar Windows 10, versión 1803 o posterior.  Además, es necesario actualizar HoloLens (1ª generación) [a Windows Holographic para empresas](hololens-upgrade-enterprise.md).

Cuando usan sus propias cuentas de Azure Active Directory (Azure AD), varios usuarios pueden mantener su propia configuración de usuario y datos de usuario en el dispositivo.

Para asegurarse de que varias personas puedan usar sus propias cuentas en HoloLens, siga estos pasos para configurarlo:

1. Asegúrese de que el dispositivo ejecuta Windows 10, versión 1803 o posterior.
   > [!IMPORTANT]
   > Si está usando un dispositivo HoloLens (1ª generación), [actualice el dispositivo a Windows Holographic para empresas](hololens1-upgrade-enterprise.md).
1. Cuando configure el dispositivo, seleccione **mi trabajo o escuela propietario** e inicie sesión con una cuenta de Azure ad.
1. Una vez finalizada la instalación, asegúrese de que la configuración de la cuenta (cuentas de**configuración**  >  **Accounts**) incluye **otros usuarios**.

Para usar HoloLens, cada usuario sigue estos pasos:

1. Si otro usuario ha estado usando el dispositivo, siga uno de estos procedimientos:
   - Presione el botón de encendido una vez para ir a standby y, a continuación, presione el botón de encendido de nuevo para volver a la pantalla de bloqueo
   - Los usuarios de HoloLens 2 pueden seleccionar el icono de usuario desde el menú Inicio para cerrar la sesión del usuario actual.

1. Usa las credenciales de tu cuenta de Azure AD para iniciar sesión en el dispositivo.  
    Si esta es la primera vez que usas el dispositivo, debes [calibrar](hololens-calibration.md) HoloLens a tus ojos.

Para ver una lista de los usuarios del dispositivo o para quitar un usuario del dispositivo, vaya a **configuración**  >  **cuentas**  >  **otros usuarios**.

## Compartir con varias personas, todas usando la misma cuenta

Varios usuarios también pueden compartir un dispositivo HoloLens al usar una sola cuenta de usuario.

**En HoloLens 2**, cuando un nuevo usuario coloca el dispositivo en su cabeza por primera vez (manteniendo la misma cuenta iniciada), el dispositivo pide al nuevo usuario que calibre rápidamente y personalice la experiencia de visualización. El dispositivo puede almacenar la información de calibración para que, en el futuro, el dispositivo pueda optimizar automáticamente la calidad y comodidad de la experiencia de visualización de cada usuario. Los usuarios no tienen que calibrar el dispositivo de nuevo.

**En HoloLens (1ª generación)** , los usuarios que compartan una cuenta necesitarán solicitar la recalibra en la aplicación configuración.  Más información sobre la [calibración](hololens-calibration.md).
