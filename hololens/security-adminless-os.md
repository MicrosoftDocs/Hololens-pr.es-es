---
title: Seguridad del sistema operativo sin administrador
description: Obtenga información acerca de los sistemas operativos sin administrador, los propietarios de los dispositivos y la seguridad con los dispositivos de realidad mixta de HoloLens.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: seguridad, hololens, un administrador sin administradores, sin administradores, sistema operativo, sistema operativo sin administradores, administrador, so, so sin administradores, hololens 2, seguridad de hololens2
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 972bbc689505d42993cf47d82351ceeb79a0606b
ms.sourcegitcommit: 257720deb27f3bbc301175ce2a4afa79001862d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2021
ms.locfileid: "11440341"
---
# <a name="admin-less-operating-system"></a>Sistema operativo sin administrador

HoloLens 2 minimiza el área de superficie para ampliar el privilegio al deshabilitar la compatibilidad del grupo de administradores y limitar todo el código de aplicación para UWP de terceros para que solo se ejecute como usuarios estándar en el espacio aislado de AppContainer. Este código únicamente permite el acceso a los recursos protegidos por capacidades explícitamente manifestadas en la solicitud para un usuario no elevado, adicionalmente a los recursos accesibles a todos los AppContainers.
Estas funciones de la aplicación siguen teniendo el modelo de clasificación de tres niveles:
  * General
  * Restricted (Restringida)
  * Windows

Los componentes de Windows también pueden usar el espacio aislado de AppContainer mediante el sistema UWPs. Para obtener más información sobre aplicaciones de la Plataforma universal de Windows (UWP), vea la [documentación UWP](https://docs.microsoft.com/windows/uwp/). Además, los componentes de Windows con mayores necesidades de reducción de privilegios (como páginas de contenido del explorador o analizadores) usan el espacio aislado Descon privilegios de AppContainer (LPAC), que corta el acceso al conjunto de recursos accesibles para todos los AppContainers.

## <a name="device-owner"></a>Propietario del dispositivo

Por último, la ejecución de operaciones específicas para todo el dispositivo, como unirse al dispositivo a un inquilino o a la administración de usuarios, solo se permite para "propietarios de dispositivos". Este grupo lo rellenan los usuarios del dispositivo mediante uno de los siguientes pasos:
  * El primer usuario del dispositivo siempre se designa como propietario. 
> [!IMPORTANT]
>Para los usuarios de Azure AD, la excepción a esta regla es que si el dispositivo está unido a Azure AD a través de Autopilot o la inscripción masiva de Azure AD, que usa un usuario no real. En este caso, es posible que el primer usuario de AAD que inicie sesión en el dispositivo no se haga propietario del dispositivo automáticamente a menos que ese usuario tenga asignado el rol "administrador global" o "administrador de dispositivos" en Azure Portal. Para obtener más información, vea la nota siguiente.  

  * Cuando otro propietario del dispositivo promueve a un usuario como propietario desde la configuración de la experiencia de usuario.
  * Si el propietario del dispositivo ya no está disponible (deja la compañía) y el dispositivo está unido a Azure AD, el administrador de inquilinos puede cambiar el propietario del dispositivo a un nuevo usuario en Azure portal. Los administradores globales y los administradores de dispositivos de un inquilino de Azure AD han iniciado sesión implícitamente como propietarios en el dispositivo sin necesidad de ninguno de los pasos anteriores.  

 Los administradores de TI podrán gestionar el acceso a las aplicaciones a través de las [Directivas](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) de privacidad. 

> [!NOTE]
> Para comprender mejor a quién se hace propietario de un dispositivo en un dispositivo unido a Azure AD, vea [la documentación "Asignar administrador local" ](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin)(pero lea "administrador local" como "propietario del dispositivo", ya que el administrador no existe en HoloLens).