---
title: Acceso asignado global
description: Guía para usar OMA-URI para quioscos de acceso asignado global
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, acceso asignado, quiosco
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f91b77be846b585de8d89c17e516923f97304d57
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253207"
---
# Acceso asignado global: quiosco

Esta característica configura el dispositivo HoloLens 2 para varias aplicaciones en modo de pantalla completa, que es aplicable a nivel del sistema, no tiene afinidad con ninguna identidad en el sistema y se aplica a todos los usuarios que inician sesión en el dispositivo.

> [!NOTE]
> Actualmente, esta característica solo está disponible en las compilaciones de Windows Insider. Si deseas probar esta característica antes de que esté disponible de forma generalizada en las versiones de HoloLens, infórmate sobre las compilaciones de [Windows Insider](hololens-insider.md).

## ¿Cómo se usa el acceso asignado global en Intune?

> [!NOTE]
> Tenga en cuenta las áreas marcadas con "<!-". Estas áreas requieren que realice modificaciones en función de sus preferencias.

1. Cree un perfil de configuración de dispositivo OMA URI personalizado como se indica a continuación y aplíquelo al grupo de dispositivos HoloLens:

    Valor URI: ./Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![Acceso asignado global OMA-URI en Intune](images/global-assigned-access-omauri.png)

2. Para obtener un valor, actualice y pegue el siguiente contenido:

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## ¿Cómo se usa el Acceso asignado global en el Diseñador de configuración de Windows?

1. Actualice y guarde el blob XML indicado anteriormente como archivo XML. 

2. Siga los pasos que se indican en [Usar un paquete de aprovisionamiento para configurar un quiosco de aplicación única o de varias aplicaciones](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), en concreto en la sección "Paquete de aprovisionamiento, paso 2: agregue el archivo XML de configuración de quiosco a un paquete de aprovisionamiento" y use el archivo XML que guardó en el paso anterior.

## ¿Puedo crear una configuración en la que "global" se aplique a todos los usuarios y una configuración aparte que se aplique a 1 cuenta de Azure AD o grupo de Azure AD? 

Sí, consulte el ejemplo de BLOB XML a continuación. El perfil de acceso asignado global se aplica en Hololens cuando no se encuentra uno específico para el usuario que ha iniciado sesión, por lo que es la configuración predeterminada del modo de pantalla completa para el usuario que ha iniciado sesión.
Este es un ejemplo de blob XML que se usará:

> [!NOTE]
> Tenga en cuenta las áreas resaltadas marcadas con `<!-`. Estas áreas requieren que realice modificaciones en función de sus preferencias.

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## Exclusión de DeviceOwners de un perfil de acceso asignado global

Esta característica permite que los usuarios considerados como "[Propietario del dispositivo](security-adminless-os.md)" estén excluidos del acceso asignado global. Para aprovechar esta característica, en el blob XML para la configuración de un quiosco de varias aplicaciones, asegúrese de que se agregan las líneas resaltadas:

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## Ejemplos adicionales de Acceso global asignado

Este es el ejemplo de un quiosco de Acceso global asignado en el que, cuando un usuario inicie sesión, tendrá un quiosco de varias aplicaciones con la aplicación Configuración, el Centro de opiniones y Microsoft Edge.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

Este es el ejemplo de un quiosco de Acceso global asignado que excluye al propietario del dispositivo. Cuando cualquier otro usuario de Azure AD inicie sesión, tendrá un quiosco de varias aplicaciones con la aplicación Configuración, el Centro de opiniones y Microsoft Edge. Este quiosco también incluye la configuración de un quiosco secundario para una Cuenta de visitante, a la cual se puede acceder desde la pantalla de bloqueo. Cuando un usuario inicia sesión en la Cuenta de visitante, tendrá un quiosco de varias aplicaciones que solo tendrá la aplicación del Centro de opiniones.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
