---
title: Acceso asignado global
description: Introducción a nuestra guía sobre el uso de OMA-URI para las pantallas completas de acceso asignado global con Intune y el Diseñador de configuración de Windows.
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
ms.openlocfilehash: d36192e7f65f7fe2ccc7ff8699484a19b3d5d3a7ccab0167d2dbdcaf64bb5880
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664023"
---
# <a name="global-assigned-access--kiosk"></a>Acceso asignado global: pantalla completa

Esta característica configura el dispositivo HoloLens 2 para el modo de pantalla completa de varias aplicaciones, que es aplicable en el nivel del sistema, no tiene afinidad con ninguna identidad en el sistema y se aplica a todos los usuarios que inician sesión en el dispositivo.

> [!NOTE]
> Actualmente, esta característica solo está disponible en las compilaciones de Windows Insider. Si deseas probar esta característica antes de que esté disponible de forma generalizada en las versiones de HoloLens, obtén más información sobre las compilaciones de [Windows Insider](hololens-insider.md).

## <a name="how-to-use-global-assigned-access-in-intune"></a>¿Cómo se usa el acceso asignado global en Intune?

> [!NOTE]
> Tenga en cuenta las áreas marcadas con "<!-". Estas áreas requieren que realice modificaciones en función de sus preferencias.

1. Cree un perfil de configuración de dispositivo OMA URI personalizado como se indica a continuación y aplíquelo al grupo de dispositivos HoloLens:

    Valor URI: ./Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![OMA-URI de acceso asignado global en Intune](images/global-assigned-access-omauri.png)

2. Para obtener un valor, actualice y pegue el siguiente contenido:

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a>¿Cómo se usa el acceso asignado global en el Diseñador de configuración de Windows?

1. Actualice y guarde el blob XML indicado anteriormente como un archivo XML. 

2. Siga los pasos descritos en [Uso de un paquete de aprovisionamiento para configurar una pantalla completa de una o varias aplicaciones](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), en concreto la sección "Paquete de aprovisionamiento, paso 2: Adición del archivo XML de configuración de pantalla completa a un paquete de aprovisionamiento" y use el archivo XML que guardó en el paso anterior.

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a>¿Puedo crear una configuración en la que "global" se aplique a todos los usuarios y una configuración aparte se aplique a una cuenta de Azure AD o un grupo de Azure AD? 

Sí, consulte el ejemplo de blob XML a continuación. El perfil de acceso asignado global se aplica en HoloLens cuando no se encuentra uno específico para el usuario que ha iniciado sesión, por lo que es la configuración predeterminada del modo de pantalla completa para el usuario que ha iniciado sesión.
Este es un ejemplo de blob XML que se usará:

> [!NOTE]
> Tenga en cuenta las áreas resaltadas marcadas con `<!-`. Estas áreas requieren que realice modificaciones en función de sus preferencias.

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a>Exclusión de DeviceOwners del perfil de acceso asignado global

Esta característica permite que un usuario que se considera "[Propietario del dispositivo](security-adminless-os.md)" en HoloLens se excluya del acceso asignado global. Para aprovechar esta característica, en el blob XML para la configuración de pantalla completa de varias aplicaciones, asegúrese de que se agregan las líneas resaltadas:

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a>Ejemplos adicionales de acceso asignado global

Este es un ejemplo de pantalla completa de acceso asignado global en que, al iniciar sesión un usuario, tendrá una pantalla completa de varias aplicaciones con la aplicación Configuración, el Centro de opiniones y Microsoft Edge.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

Este es un ejemplo de pantalla completa de acceso asignado global que excluye al propietario del dispositivo. Cuando otro usuario de Azure AD inicie sesión, tendrá una pantalla completa de varias aplicaciones con la aplicación Configuración, el Centro de opiniones y Microsoft Edge. Esta pantalla completa también incluye la configuración de una pantalla completa secundaria para una cuenta de visitante, en la que puede iniciar sesión cualquier usuario en la pantalla de bloqueo. Si un usuario inicia sesión en la cuenta de visitante, tendrá un quiosco de varias aplicaciones que solo incluirá la aplicación Centro de opiniones.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
