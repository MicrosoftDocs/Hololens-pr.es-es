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
ms.openlocfilehash: a5c86a5420f3a9b0705667161e6b9440134731d7
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284131"
---
# Sistema operativo sin administrador

HoloLens 2 minimiza el área de superficie para ampliar el privilegio al deshabilitar la compatibilidad del grupo de administradores y limitar todo el código de aplicación para UWP de terceros para que solo se ejecute como usuarios estándar en el espacio aislado de AppContainer. Este código únicamente permite el acceso a los recursos protegidos por capacidades explícitamente manifestadas en la solicitud para un usuario no elevado, adicionalmente a los recursos accesibles a todos los AppContainers.
Estas funciones de la aplicación siguen teniendo el modelo de clasificación de tres niveles:
  * General
  * Restricted (Restringida)
  * Windows

Los componentes de Windows también pueden usar el espacio aislado de AppContainer mediante el sistema UWPs. Para obtener más información sobre aplicaciones de la Plataforma universal de Windows (UWP), vea la [documentación UWP](https://docs.microsoft.com/windows/uwp/). Además, los componentes de Windows que tienen mayores necesidades de restricción de privilegios (por ejemplo, las páginas de contenido de los navegadores, los analizadores) usan la caja de arena de AppContainer con menos privilegios (LPAC) la cual corta el acceso al conjunto de recursos accesibles a todos los AppContainers

## Propietario del dispositivo

Por último, la ejecución de operaciones específicas para todo el dispositivo, como unirse al dispositivo a un inquilino o a la administración de usuarios, solo se permite para "propietarios de dispositivos". Este grupo lo rellenan los usuarios del dispositivo mediante uno de los siguientes pasos:
  * El primer usuario del dispositivo siempre se designa como propietario. 
    * La única excepción a esta regla es que si el dispositivo se une a Azure AD, el usuario que realiza la unión se convierte en el propietario del dispositivo. Esto es aplicable, por ejemplo, si un dispositivo se une a Azure AD con un piloto automático, en cuyo caso el primer usuario que se registre en el dispositivo no se unirá a la Azure AD y, por lo tanto, no se convertirá en propietario del dispositivo. Para comprender mejor a quién se hace propietario de un dispositivo en un dispositivo unido a Azure AD, vea [la documentación "Asignar administrador local" ](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin)(pero lea "administrador local" como "propietario del dispositivo", ya que el administrador no existe en HoloLens).
  * Cuando un usuario se convierte en propietario desde la UX de configuración por obra de otro propietario en el dispositivo.
  * Si el propietario del dispositivo no se encuentra disponible (por ejemplo, deja la empresa) y el dispositivo se une a Azure AD, el administrador del espacio empresarial puede cambiar el propietario del dispositivo a un nuevo usuario en el Portal Azure.
En el dispositivo, los administradores globales de un espacio empresarial de Azure AD se registran implícitamente como propietarios sin requerir ninguno de los pasos anteriores. 

Los administradores de TI podrán gestionar el acceso a las aplicaciones a través de las [Directivas](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) de privacidad 
