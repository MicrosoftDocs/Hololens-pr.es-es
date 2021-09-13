---
title: Uso compartido de HoloLens con varias personas
description: Puede configurar las HoloLens que compartan varias cuentas Azure Active Directory o por varios usuarios que usen una sola cuenta.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e3acd2665e93e44bce2c5dad467c825dc768bfed
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033909"
---
# <a name="share-your-hololens-with-multiple-people"></a>Uso compartido de HoloLens con varias personas

## <a name="overview"></a>Información general
A menudo, las empresas invierten en muchos dispositivos HoloLens compartidos. La forma de HoloLens es flexible en función de sus requisitos individuales. Este es un ejemplo de algunas experiencias de varios usuarios: 

- Los dispositivos que se cobran y tienen Dynamics 365 Guides y permiten a los empleados abrir la aplicación Configuración para realizar ajustes en Wi-Fi necesarios, pero la directiva visibilidad de Configuración de página está habilitada para limitar la cantidad de páginas disponibles en la aplicación Configuración.
- Dispositivos que son para Remote Assist y la aplicación de línea de negocio que se alquilan a otras empresas. Estos dispositivos tienen quioscos que incluyen solo la aplicación y Remote Assist. WDAC se usa para evitar que la aplicación Configuración y Microsoft Edge inicien. Se incluye con el alquiler una batería USB-C para mantener los dispositivos a carga completa en varios turnos.
- Todos los dispositivos están configurados para Autopilot y descargan todas las aplicaciones de la empresa. Ha configurado varios perfiles de quiosco, dirigidos a distintos grupos Azure AD pantalla completa. Cada usuario inicia sesión en el HoloLens mediante claves FIDO2 e inicia sesión en su propia cuenta de Azure AD y se presenta una experiencia personalizada.



## <a name="share-with-multiple-people-each-using-their-own-account"></a>Compartir con varias personas, cada una con su propia cuenta

**Requisito** previo: el HoloLens debe ejecutarse Windows 10 versión 1803 o posterior.  HoloLens (1.ª generación) también se deben [actualizar a Windows Holographic for Business](hololens-upgrade-enterprise.md).

Cuando usan sus propias Azure Active Directory (Azure AD), varios usuarios pueden mantener su propia configuración de usuario y sus propios datos de usuario en el dispositivo.

Para asegurarse de que varias personas pueden usar sus propias cuentas en HoloLens, siga estos pasos para configurarlo:

1. Asegúrese de que el dispositivo se ejecuta Windows 10 versión 1803 o posterior.
   > [!IMPORTANT]
   > Si usa un dispositivo HoloLens (1ª generación), actualice el dispositivo a [Windows Holographic for Business](hololens1-upgrade-enterprise.md).
1. Al configurar el dispositivo, seleccione Mi trabajo o escuela **es** el propietario e inicie sesión con una cuenta Azure AD usuario.
1. Una vez que termine la instalación, asegúrese de que la configuración de la cuenta (**Configuración**  >  **Accounts**) **incluye Otros usuarios.**

Para usar HoloLens, cada usuario sigue estos pasos:

1. Si otro usuario ha estado usando el dispositivo, elija una de las siguientes opciones:
   - Presione el botón de encendido una vez para pasar al modo de espera y, a continuación, vuelva a presionar el botón de encendido para volver a la pantalla de bloqueo.
   - HoloLens 2 usuarios pueden seleccionar el icono de usuario del menú Inicio cerrar la sesión del usuario actual.

1. Use sus Azure AD de cuenta para iniciar sesión en el dispositivo.  
    Si es la primera vez que usa el dispositivo, debe [calibrar](hololens-calibration.md) los HoloLens sus propios ojos.

Para ver una lista de los usuarios del dispositivo o quitar un usuario del dispositivo, vaya a Configuración Cuentas de otros  >    >  **usuarios.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Compartir con varias personas, todas con la misma cuenta

Varios usuarios también pueden compartir un dispositivo HoloLens mientras se usa una sola cuenta de usuario.

**En HoloLens 2**, cuando un nuevo usuario coloca el dispositivo en la cabeza por primera vez (mientras mantiene la misma cuenta con la sesión firmada), el dispositivo solicita al nuevo usuario que calibra y personalice rápidamente la experiencia de visualización. El dispositivo puede almacenar la información de calibración para que, en el futuro, el dispositivo pueda optimizar automáticamente la calidad y la comodidad de la experiencia de visualización de cada usuario. Los usuarios no necesitan calibrar el dispositivo de nuevo.

**En HoloLens (1.ª generación)** los usuarios que comparten una cuenta tendrán que pedir que vuelvan a Configuración aplicación.  Obtenga más información sobre la [calibración](hololens-calibration.md).