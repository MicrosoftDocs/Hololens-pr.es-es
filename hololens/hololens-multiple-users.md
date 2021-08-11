---
title: Uso compartido de HoloLens con varias personas
description: Puede configurar las HoloLens que compartan varias Azure Active Directory o varios usuarios que usen una sola cuenta.
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
ms.openlocfilehash: 821ef2d17531226177e508b1428af82012c16406e9fbce3ed1a5617c767adfe8
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663075"
---
# <a name="share-your-hololens-with-multiple-people"></a>Uso compartido de HoloLens con varias personas

Es habitual compartir una HoloLens con muchas personas o hacer que muchas personas compartan un conjunto de HoloLens dispositivos.  En este artículo se describen las distintas formas de compartir un dispositivo.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Compartir con varias personas, cada una con su propia cuenta

**Requisito** previo: el HoloLens debe ejecutarse Windows 10 versión 1803 o posterior.  HoloLens (1.ª generación) también se deben [actualizar a Windows Holographic for Business](hololens-upgrade-enterprise.md).

Cuando usan sus propias Azure Active Directory (Azure AD), varios usuarios pueden mantener su propia configuración de usuario y sus propios datos de usuario en el dispositivo.

Para asegurarse de que varias personas pueden usar sus propias cuentas en HoloLens, siga estos pasos para configurarlo:

1. Asegúrese de que el dispositivo se ejecuta Windows 10 versión 1803 o posterior.
   > [!IMPORTANT]
   > Si usa un dispositivo HoloLens (1ª generación), actualice el dispositivo [a Windows Holographic for Business](hololens1-upgrade-enterprise.md).
1. Al configurar el dispositivo, seleccione **Mi** trabajo o escuela es propietario de él e inicie sesión con una cuenta Azure AD usuario.
1. Una vez que termine la instalación, asegúrese de que la configuración de la cuenta (**Configuración**  >  **Accounts**) incluye **Otros usuarios.**

Para usar HoloLens, cada usuario sigue estos pasos:

1. Si otro usuario ha estado usando el dispositivo, realice una de las siguientes acciones:
   - Presione el botón de encendido una vez para pasar al modo de espera y, a continuación, vuelva a presionar el botón de encendido para volver a la pantalla de bloqueo.
   - HoloLens 2 usuarios pueden seleccionar el icono de usuario de la menú Inicio cerrar la sesión del usuario actual.

1. Use las credenciales Azure AD cuenta de usuario para iniciar sesión en el dispositivo.  
    Si es la primera vez que usa el dispositivo, tendrá que [calibrar](hololens-calibration.md) HoloLens sus propios ojos.

Para ver una lista de los usuarios del dispositivo o para quitar un usuario del dispositivo, vaya a cuentas Configuración  >    >  **Otros usuarios.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Compartir con varias personas, todas con la misma cuenta

Varios usuarios también pueden compartir un dispositivo HoloLens mientras se usa una única cuenta de usuario.

**En HoloLens 2**, cuando un nuevo usuario coloca el dispositivo en la cabeza por primera vez (mientras mantiene la misma cuenta con la sesión firmada), el dispositivo solicita al nuevo usuario que calibra y personalice rápidamente la experiencia de visualización. El dispositivo puede almacenar la información de calibración para que, en el futuro, el dispositivo pueda optimizar automáticamente la calidad y la comodidad de la experiencia de visualización de cada usuario. Los usuarios no necesitan calibrar el dispositivo de nuevo.

**En HoloLens (1ª generación)** los usuarios que comparten una cuenta tendrán que pedir que vuelvan a Configuración aplicación.  Obtenga más información sobre la [calibración](hololens-calibration.md).
