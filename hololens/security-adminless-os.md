---
title: Seguridad del sistema operativo sin administrador
description: Obtenga información acerca de los sistemas operativos sin administrador, los propietarios de dispositivos y la seguridad en los dispositivos de realidad mixta de HoloLens.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: seguridad, hololens, sin administrador, sin administradores, sistema operativo, sistema operativo sin administrador, so de administrador, so sin administrador, hololens 2, seguridad de hololens2
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f4fc79b7f51933418cdda8368c6b4b070e854dd0978754647ce864075c772cfd
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665546"
---
# <a name="admin-less-operating-system"></a>Sistema operativo sin administrador

HoloLens 2 minimiza el área de superficie para la elevación de privilegios al deshabilitar la compatibilidad del grupo de administradores y limitar todo el código de la aplicación para UWP de terceros para que solo se ejecute como usuarios estándar en el espacio aislado de AppContainer. Este código únicamente tiene acceso a los recursos protegidos por capacidades explícitamente manifestadas en la aplicación para un usuario sin permisos elevados, así como a los recursos accesibles para todas las instancias de AppContainer.
Estas funcionalidades de la aplicación siguen teniendo el modelo de clasificación de tres niveles:
  * General
  * Restringidos
  * Windows

Los componentes de Windows también pueden usar el espacio aislado de AppContainer mediante las instancias de UWP del sistema. Para obtener más información sobre la Plataforma universal de Windows (UWP), consulta la [documentación de UWP](/windows/uwp/). Además, los componentes de Windows con mayores necesidades de reducción de privilegios (como páginas de contenido del explorador o analizadores) usan el espacio aislado AppContainer con menos privilegios (LPAC), que corta el acceso al conjunto de recursos accesible para todas las instancias de AppContainer.

## <a name="device-owner"></a>Propietario del dispositivo

Por último, la ejecución de operaciones específicas de todo el dispositivo, como unir el dispositivo a una administración de inquilino o usuario, solo se permite a "propietarios de dispositivos". Este grupo lo rellenan los usuarios del dispositivo mediante uno de los siguientes pasos:
  * El primer usuario del dispositivo siempre se designa como propietario. 
> [!IMPORTANT]
>Para los usuarios de Azure AD, la excepción a esta regla es que, si el dispositivo está unido a Azure AD a través de Autopilot o la inscripción masiva de Azure AD, se usa un usuario no real. En este caso, es posible que el primer usuario de AAD que inicie sesión en el dispositivo no se convierta en propietario del dispositivo automáticamente, a menos que tenga asignado el rol de "administrador global" o "administrador de dispositivos" en Azure Portal. Para obtener más información, vea la nota siguiente.  

  * Cuando otro propietario del dispositivo promociona a un usuario como propietario desde la experiencia de usuario de configuración.
  * Si el propietario del dispositivo ya no está disponible (deja la compañía) y el dispositivo está unido a Azure AD, el administrador de inquilinos puede cambiar el propietario del dispositivo a un nuevo usuario en Azure Portal. Los administradores globales y los administradores de dispositivos de un inquilino de Azure AD inician la sesión implícitamente como propietarios en el dispositivo sin necesidad de ninguno de los pasos anteriores.  

 Los administradores de TI pueden administrar qué aplicaciones pueden acceder a través de las directivas de [privacidad](/windows/client-management/mdm/policy-csp-privacy). 

> [!NOTE]
> Para comprender mejor a quién se hace propietario de un dispositivo en un dispositivo unido a Azure AD, vea la [documentación de "Asignación del administrador local"](/azure/active-directory/devices/assign-local-admin) (interprete "administrador local" como "propietario del dispositivo", ya que el rol de administrador no existe en HoloLens).