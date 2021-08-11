---
title: Actualizar HoloLens 2
description: Obtenga información sobre cómo comprobar HoloLens de compilación, mantenerse al día con las actualizaciones del dispositivo, unirse al programa Insiders y revertir las actualizaciones.
keywords: how-to, update, roll back, HoloLens, check build, build number
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: 7e63fcab4c64f151684a634bb24d9fc31826f6805d52b23c5672add0b6269430
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662835"
---
# <a name="update-hololens-2"></a>Actualizar HoloLens 2

HoloLens usa Windows update, al igual que otros Windows 10 dispositivos. El HoloLens descargará e instalará automáticamente las actualizaciones del sistema cada vez que esté conectado a la alimentación y conectado a Internet, incluso cuando esté en espera.

Este artículo le ayudará a HoloLens herramientas para:

- ver la versión actual del sistema operativo (número de compilación)
- comprobar si hay actualizaciones
- actualizar manualmente HoloLens
- revertir a una actualización anterior

## <a name="check-your-operating-system-version-build-number"></a>Comprobación de la versión del sistema operativo (número de compilación)

Puede comprobar el número de versión del sistema (número de compilación) abriendo la aplicación Configuración y **seleccionando Sistema**  >  **acerca de**.

## <a name="check-for-updates-and-manually-update"></a>Buscar actualizaciones y actualizar manualmente

Puede buscar actualizaciones en cualquier momento en la configuración.  Para ver las actualizaciones disponibles y buscar nuevas actualizaciones:

1. Abra la aplicación **Configuración**.
1. Vaya **a Actualizar & seguridad Windows**  >  **actualizar**.
1. Seleccione **Buscar actualizaciones**.

Si hay una actualización disponible, comenzará a descargar la nueva versión. Una vez completada la descarga, seleccione el **botón Reiniciar** ahora para desencadenar la instalación. Si el dispositivo está por debajo del 40 % y no está conectado, el reinicio no iniciará la instalación de la actualización.

Mientras el HoloLens instala la actualización, mostrará engranajes giratorios y un indicador de progreso. No apague el HoloLens durante este tiempo. Se reiniciará automáticamente una vez que haya completado la instalación.

HoloLens aplica una actualización a la vez.  Si el HoloLens tiene más de una versión detrás de la versión más reciente, es posible que tenga que ejecutar el proceso de actualización varias veces para que esté totalmente actualizado.

## <a name="go-back-to-a-previous-version"></a>Volver a una versión anterior

En algunos casos, es posible que quiera volver a una versión anterior del software HoloLens software. Los pasos recomendados son:

1. Póngase en contacto con el soporte técnico para ver si puede corregir el problema.
    1. Asegúrese de **que la** **telemetría** opcional o completa está habilitada; esto hace que el error sea más fácil de diagnosticar para los ingenieros.
    1. [Los comentarios de archivo](hololens-feedback.md) son tan descriptivos como sea posible. Tome nota del título o use la característica de uso compartido para poder compartir el error con el soporte técnico.
    1. Póngase en [contacto con el soporte técnico.](https://aka.ms/hlsupport) Si el problema es uno que debe resolverse volviendo a una versión anterior, pueden proporcionar la FFU para que el dispositivo se flashee.

1. Si esto no funciona, restablezca o vuelva a actualizar el [HoloLens 2 con el complemento de recuperación avanzada](hololens-recovery.md).
    1. En el equipo, descargue advanced [recovery companion (Complemento de](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) recuperación avanzada) desde Microsoft Store.
    1. Asegúrese de que no tiene teléfonos ni dispositivos Windows conectados al equipo.
    1. Elija la versión a la que desea flash:
        1. Puede descargar la [versión más reciente HoloLens 2 versión](https://aka.ms/hololens2download).
        1. Puede usar la compilación predeterminada que hospeda ARC. (Si elige esta opción, omita el paso siguiente).
        1. Puede usar el soporte técnico de compilación que le proporcionó.
    1. Cuando haya terminado estas descargas, abra **Explorador de archivos**  >  **descargas.** Haga clic con el botón derecho en la carpeta comprimida que acaba de descargar y seleccione **Extraer todo**  >  **extraer** para descomprimirla.
    1. Conectar el HoloLens al equipo mediante un cable USB-A a USB-C. (Incluso si ha estado usando otros cables para conectar el HoloLens, este funciona mejor).
    1. Advanced Recovery Companion detecta automáticamente el HoloLens. Seleccione el icono **Microsoft HoloLens**.
    1. En la siguiente pantalla, seleccione **Selección** manual del paquete y, a continuación, seleccione el archivo de instalación contenido en la carpeta que descomprimió en el paso 4. (Busque un archivo con la extensión .ffu).
    1. Seleccione **Instalar software** y siga las instrucciones.

> [!NOTE]
> Al volver a una versión anterior, se eliminan los archivos personales y la configuración.

Además, si desea permanecer en la versión instalada actualmente, también puede pausar manualmente [las actualizaciones](hololens-updates.md#pause-updates-via-device). Esto dará tiempo al equipo de ingeniería para corregir el problema.

## <a name="windows-insider-program-on-hololens"></a>Windows Programa Insider en HoloLens

¿Quiere ver las características más recientes de HoloLens?  Si es así, una el Windows Programa Insider; tendrá acceso a las compilaciones de versión preliminar de HoloLens de software antes de que estén disponibles para el público general.

[Obtenga Windows versión preliminar de Insider para Microsoft HoloLens](hololens-insider.md).
