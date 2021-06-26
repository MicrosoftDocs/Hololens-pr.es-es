---
title: Actualizar HoloLens 2
description: Obtenga información sobre cómo comprobar el número de compilación de HoloLens, mantenerse al día con las actualizaciones del dispositivo, unirse al programa Insiders y revertir las actualizaciones.
keywords: cómo, actualizar, revertir, HoloLens, comprobar compilación, número de compilación
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
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924118"
---
# <a name="update-hololens-2"></a>Actualizar HoloLens 2

HoloLens usa Windows Update, al igual que otros Windows 10 dispositivos. HoloLens descargará e instalará automáticamente las actualizaciones del sistema cada vez que esté conectado a la alimentación y conectado a Internet, incluso cuando esté en espera.

En este artículo se leen las herramientas de HoloLens para:

- ver la versión actual del sistema operativo (número de compilación)
- comprobar si hay actualizaciones
- actualización manual de HoloLens
- revertir a una actualización anterior

## <a name="check-your-operating-system-version-build-number"></a>Comprobación de la versión del sistema operativo (número de compilación)

Puede comprobar el número de versión del sistema (número de compilación) abriendo la aplicación Configuración y **seleccionando Sistema**  >  **acerca de**.

## <a name="check-for-updates-and-manually-update"></a>Buscar actualizaciones y actualizar manualmente

Puede buscar actualizaciones en cualquier momento en la configuración.  Para ver las actualizaciones disponibles y buscar nuevas actualizaciones:

1. Abra la aplicación **Configuración**.
1. Vaya **a Actualizar & seguridad**  >  **Windows Update**.
1. Haga clic en **Buscar actualizaciones**.

Si hay una actualización disponible, comenzará a descargar la nueva versión. Una vez completada la descarga, seleccione el **botón Reiniciar** ahora para desencadenar la instalación. Si el dispositivo está por debajo del 40 % y no está conectado, el reinicio no iniciará la instalación de la actualización.

Mientras HoloLens instala la actualización, mostrará engranajes giratorios y un indicador de progreso. No apague HoloLens durante este tiempo. Se reiniciará automáticamente una vez que haya completado la instalación.

HoloLens aplica una actualización a la vez.  Si HoloLens tiene más de una versión detrás de la versión más reciente, es posible que deba ejecutar el proceso de actualización varias veces para actualizarlo por completo.

## <a name="go-back-to-a-previous-version"></a>Volver a una versión anterior

En algunos casos, es posible que quiera volver a una versión anterior del software HoloLens. Los pasos recomendados son:

1. Póngase en contacto con el soporte técnico para ver si puede corregir el problema.
    1. Asegúrese de **que la** **telemetría** opcional o completa está habilitada, lo que hace que el error sea más fácil de diagnosticar para los ingenieros.
    1. [Los comentarios de archivo](hololens-feedback.md) son tan descriptivos como sea posible. Tome nota del título o use la característica de uso compartido para poder compartir el error con el soporte técnico.
    1. Póngase en [contacto con el soporte técnico.](https://aka.ms/hlsupport) Si el problema es uno que debe resolverse volviendo a una versión anterior, pueden proporcionar la FFU para que el dispositivo se flashee.

1. Si esto no funciona, restablezca o vuelva a actualizar el [HoloLens 2 con el complemento de recuperación avanzada](hololens-recovery.md).
    1. En el equipo, descargue advanced [recovery companion (Complemento de](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) recuperación avanzada) desde Microsoft Store.
    1. Asegúrese de que no tiene ningún teléfono o dispositivo Windows conectado al equipo.
    1. Elija la versión a la que desea flash:
        1. Puede descargar la [versión de HoloLens 2 más reciente.](https://aka.ms/hololens2download)
        1. Puede usar la compilación predeterminada que hospeda ARC. (Si elige esta opción, omita el paso siguiente).
        1. Puede usar una compatibilidad de compilación proporcionada con .
    1. Cuando haya terminado estas descargas, abra **Explorador de archivos**  >  **descargas.** Haga clic con el botón derecho en la carpeta comprimida que acaba de descargar y seleccione **Extraer todo**  >  **extraer** para descomprimirla.
    1. Conecte HoloLens al equipo mediante un cable USB-A a USB-C. (Incluso si ha estado usando otros cables para conectar holoLens, este funciona mejor).
    1. Advanced Recovery Companion detecta automáticamente holoLens. Seleccione el **icono Microsoft HoloLens.**
    1. En la siguiente pantalla, seleccione **Selección** manual del paquete y, a continuación, seleccione el archivo de instalación contenido en la carpeta que descomprimió en el paso 4. (Busque un archivo con la extensión .ffu).
    1. Seleccione **Instalar software** y siga las instrucciones.

> [!NOTE]
> Al volver a una versión anterior, se eliminan los archivos personales y la configuración.

Además, si desea permanecer en la versión instalada actualmente, también puede pausar manualmente [las actualizaciones](hololens-updates.md#pause-updates-via-device). Esto dará tiempo al equipo de ingeniería para corregir el problema.

## <a name="windows-insider-program-on-hololens"></a>Programa Windows Insider en HoloLens

¿Quiere ver las características más recientes de HoloLens?  Si es así, una el Programa Windows Insider; Tendrá acceso a las compilaciones de versión preliminar de las actualizaciones de software de HoloLens antes de que estén disponibles para el público general.

[Obtenga Windows Insider vista previa de Microsoft HoloLens](hololens-insider.md).
