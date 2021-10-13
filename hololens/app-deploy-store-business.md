---
title: Microsoft Store para Empresas
description: Obtenga información sobre cómo trabajar con los Microsoft Store para Empresas publicar sus aplicaciones de realidad mixta en su negocio.
keywords: Microsoft Store para Empresas, msfb, implementación de aplicaciones, tienda
author: evmill
ms.author: v-evmill
ms.date: 10/13/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
ms.openlocfilehash: 5bc719539aaa254b8aacb05e24554152231f7e5a
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924328"
---
# <a name="microsoft-store-for-business"></a>Microsoft Store para Empresas

El [Microsoft Store para Empresas](/microsoft-store/microsoft-store-for-business-overview) está diseñado principalmente para los responsables de la toma de decisiones de TI y los administradores de empresas u organizaciones con una manera flexible de buscar, adquirir, administrar y distribuir aplicaciones gratuitas y de pago en mercados selectos para Windows 10 dispositivos en volumen. 

Puede administrar aplicaciones Microsoft Store y aplicaciones de línea de negocio privadas en un inventario, y asignar y volver a usar licencias según sea necesario. También puede elegir el mejor método de distribución para su organización: asignar aplicaciones directamente a usuarios y equipos, publicar aplicaciones en páginas privadas en Microsoft Store o conectarse con soluciones de administración para obtener más opciones.

Cuando Microsoft Store para Empresas usuario final lo usa, iniciará la Microsoft Store aplicación. Una vez que se haya iniciado, el usuario podrá seleccionar la pestaña con el nombre de su organización y, a continuación, se le presentarán las aplicaciones disponibles para ellos o ese dispositivo.

> [!Note]
> Microsoft Store para Empresas descarga (inserta) automáticamente aplicaciones en los dispositivos. Sin embargo, las aplicaciones del Microsoft Store para Empresas pueden asociarse con el servidor de administración de dispositivos (MDM) para dirigir y sincronizar aplicaciones con dispositivos.

Visite las páginas siguientes para obtener más información sobre cómo usar el Microsoft Store para Empresas:

* [Niveles de permisos usados para instalar aplicaciones](/mem/intune/configuration/device-restrictions-windows-holographic#app-store)
* [Adición de una aplicación a la Tienda para Empresas](/mem/intune/apps/store-apps-windows)
* [Asignación de aplicaciones a grupos de empleados](/mem/intune/apps/windows-store-for-business)

Para asociar la Microsoft Store para Empresas, visite [Asociación de Microsoft Store para Empresas con Intune.](/mem/intune/apps/windows-store-for-business#associate-your-microsoft-store-for-business-account-with-intune)

> [!Tip]
> Obtenga más información sobre [la distribución de aplicaciones sin](/microsoft-store/distribute-offline-apps) conexión al usar aplicaciones como Advanced Recovery Companion (ARC) y Windows Configuration Designer (WCD).

## <a name="use-only-private-store-apps-for-microsoft-store"></a>Usar solo aplicaciones de la tienda privada para Microsoft Store

- Introducido en [Windows Holographic, versión 21H2.](hololens-release-notes.md#windows-holographic-version-21h2)

La directiva RequirePrivateStoreOnly se ha habilitado para HoloLens. Esta directiva permite configurar Microsoft Store aplicación para mostrar solo el almacén privado configurado para su organización. Limitación del acceso solo a las aplicaciones que ha puesto a disposición.

Más información sobre [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

## <a name="smart-retry-for-app-updates"></a>Reintento inteligente para actualizaciones de aplicaciones

- Introducido en [Windows Holographic, versión 21H2.](hololens-release-notes.md#windows-holographic-version-21h2)

Ahora habilitado para HoloLens es una nueva directiva que permite a los administradores de TI establecer una fecha periódica o de una hora para reiniciar las aplicaciones cuya actualización no se pudo realizar debido a que la aplicación está en uso, lo que permite aplicar la actualización. Se pueden establecer en función de algunos desencadenadores diferentes, como una hora programada o un inicio de sesión. Para obtener más información sobre cómo usar esta directiva, vea [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures).