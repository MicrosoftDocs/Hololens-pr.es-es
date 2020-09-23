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
ms.openlocfilehash: c2be1123d0e8a09d6955fb6e5da782daebc96bcf
ms.sourcegitcommit: 89ce6cdc0fc6d70a88217791c5f6d613778af614
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "11052629"
---
# Acceso asignado global: quiosco

Esta característica configura el dispositivo Hololens 2 para varias aplicaciones en modo de pantalla completa que es aplicable a nivel del sistema, no tiene afinidad con ninguna identidad del sistema y se aplica a cualquier usuario que inicie sesión en el dispositivo. 

> [!NOTE]
> Actualmente, esta característica solo está disponible en las compilaciones de Windows Insider. Si desea probar esta característica antes de que esté disponible de forma generalizada en las versiones de HoloLens, obtenga más información sobre las compilaciones de [Windows Insider](hololens-insider.md).
 
## ¿Cómo usar esto en Intune? 

> [!NOTE]
> Tenga en cuenta las áreas marcadas con "<!-". Estas áreas requieren que realice modificaciones en función de sus preferencias. 

1.  Cree un perfil de configuración de dispositivo OMA URI personalizado como se indica a continuación y aplíquelo al grupo de dispositivos HoloLens: ![OMA-URI de acceso asignado global en Intune](images/global-assigned-access-omauri.png)

2.  Para obtener un valor, actualice y pegue el siguiente contenido: 

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## ¿Cómo usar esto en el diseñador de configuraciones de Windows? 
 
1.  Actualice y guarde el blob XML indicado anteriormente como archivo XML. 

2.  Siga los pasos que se indican en [Usar un paquete de aprovisionamiento para configurar un quiosco de aplicación única o de varias aplicaciones](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), en concreto en la sección "Paquete de aprovisionamiento, paso 2: agregue el archivo XML de configuración de quiosco a un paquete de aprovisionamiento" y use el archivo XML que guardó en el paso anterior. 

## ¿Puedo crear una configuración en la que global se aplique a todos los usuarios y se aplique una configuración aparte a 1 cuenta de AAD o grupo de AAD? 

Sí, consulte a continuación el blob XML de ejemplo. El perfil de acceso asignado global se aplica en Hololens cuando no se encuentra uno específico para el usuario que ha iniciado sesión, por lo que es la configuración predeterminada del modo de pantalla completa para el usuario que ha iniciado sesión. Este es un ejemplo de blob XML que se usará: 

> [!NOTE]
> Tenga en cuenta las áreas resaltadas con <!-. Estas áreas requieren que realice modificaciones en función de sus preferencias. 

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## Exclusión de DeviceOwners de un perfil de acceso asignado global

Esta característica permite que los usuarios considerados como "[Propietario del dispositivo](security-adminless-os.md)" estén excluidos del acceso asignado global. Para aprovechar esta característica, en el blob XML para la configuración de un quiosco de varias aplicaciones, asegúrese de que se agregan las líneas resaltadas: 

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::
 
