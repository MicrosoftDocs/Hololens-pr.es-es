---
title: Actualización de HoloLens
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310166"
---
# <a name="update-hololens"></a>Actualización de HoloLens

HoloLens usa Windows Update, al igual que otros Windows 10 dispositivos. HoloLens descargará e instalará automáticamente las actualizaciones del sistema cada vez que esté conectado a la alimentación y conectado a Internet, incluso cuando esté en espera.

En este artículo se leen las herramientas de HoloLens para:

- ver la versión actual del sistema operativo (número de compilación)
- comprobar si hay actualizaciones
- actualización manual de HoloLens
- revertir a una actualización anterior

## <a name="check-your-operating-system-version-build-number"></a>Comprobación de la versión del sistema operativo (número de compilación)

Puede comprobar el número de versión del sistema (número de compilación) abriendo la aplicación Configuración y **seleccionando Sistema**  >  **acerca de**.

## <a name="check-for-updates-and-manually-update"></a>Buscar actualizaciones y actualizar manualmente

Puede buscar actualizaciones en cualquier momento en la configuración.  Para ver las actualizaciones disponibles y comprobar si hay nuevas actualizaciones:

1. Abra la aplicación **Configuración**.
1. Vaya a **Update & Security**  >  **Windows Update**.
1. Haga clic en **Buscar actualizaciones**.

Si hay una actualización disponible, empezará a descargar la nueva versión. Una vez completada la descarga, seleccione el **botón Reiniciar** ahora para desencadenar la instalación. Si el dispositivo está por debajo del 40 % y no está conectado, el reinicio no iniciará la instalación de la actualización.

Mientras HoloLens instala la actualización, mostrará engranajes giratorios y un indicador de progreso. No apague HoloLens durante este tiempo. Se reiniciará automáticamente una vez que haya completado la instalación.

HoloLens aplica una actualización a la vez.  Si HoloLens tiene más de una versión detrás de la versión más reciente, es posible que deba ejecutar el proceso de actualización varias veces para actualizarlo por completo.

## <a name="go-back-to-a-previous-version---hololens-2"></a>Vuelva a una versión anterior: HoloLens 2

En algunos casos, es posible que quiera volver a una versión anterior del software HoloLens. Para ello, use advanced recovery companion (Complemento de recuperación avanzada) para restablecer HoloLens a la versión anterior.

> [!NOTE]
> Al volver a una versión anterior, se eliminan los archivos personales y la configuración.

Para volver a una versión anterior de HoloLens 2, siga estos pasos:

1. Asegúrese de que no tiene ningún teléfono o dispositivo Windows conectado al equipo.
1. En el equipo, descargue el [complemento de recuperación](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) avanzada desde el Microsoft Store.
1. Descargue la [versión de HoloLens 2 más reciente.](https://aka.ms/hololens2download)
1. Cuando haya terminado estas descargas, abra el Explorador **de archivos**  >  **Descargas**. Haga clic con el botón derecho en la carpeta comprimida que acaba de descargar y seleccione **Extraer todo**  >  **extraer** para descomprimirla.
1. Conecte HoloLens al equipo mediante un cable USB-A a USB-C. (Incluso si ha estado usando otros cables para conectar holoLens, este funciona mejor).
1. Advanced Recovery Companion detecta automáticamente HoloLens. Seleccione el **icono Microsoft HoloLens.**
1. En la siguiente pantalla, seleccione **Selección** manual del paquete y, a continuación, seleccione el archivo de instalación contenido en la carpeta que descomprimió en el paso 4. (Busque un archivo con la extensión .ffu).
1. Seleccione **Instalar software** y siga las instrucciones.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Volver a una versión anterior: HoloLens (1.ª generación)

En algunos casos, es posible que quiera volver a una versión anterior del software HoloLens. Para ello, use la Herramienta de recuperación de dispositivos Windows para restablecer HoloLens a la versión anterior.

> [!NOTE]
> Al volver a una versión anterior, se eliminan los archivos y la configuración personales.

Para volver a una versión anterior de HoloLens 1, siga estos pasos:

1. Asegúrese de que no tiene ningún teléfono o dispositivo Windows conectado al equipo.
1. En el equipo, descargue la Herramienta [de recuperación de dispositivos Windows (WDRT).](https://support.microsoft.com/help/12379)
1. Descargue el paquete [de recuperación de la actualización de aniversario de HoloLens](https://aka.ms/hololensrecovery).
1. Cuando finalicen las descargas, abra El **Explorador de archivos**  >  **descarga**. Haga clic con el botón derecho en la carpeta comprimida que acaba de descargar y seleccione **Extraer toda**  >  **la extracción** para descomprimirla.
1. Conecte holoLens al equipo mediante el cable micro USB con el que se incluye. (Aunque haya estado usando otros cables para conectar HoloLens, este funciona mejor).
1. WDRT detectará automáticamente HoloLens. Seleccione el **icono Microsoft HoloLens.**
1. En la siguiente pantalla, seleccione **Selección manual** de paquetes y elija el archivo de instalación incluido en la carpeta que descomprimió en el paso 4. (Busque un archivo con la extensión .ffu).
1. Seleccione **Instalar software** y siga las instrucciones.

> [!NOTE]
> Si WDRT no detecta HoloLens, intente reiniciar el equipo. Si eso no funciona, seleccione Mi dispositivo no se detectó, **seleccione** Microsoft HoloLens y, a continuación, siga las instrucciones.

## <a name="windows-insider-program-on-hololens"></a>Programa Windows Insider en HoloLens

¿Quiere ver las características más recientes de HoloLens?  Si es así, una el Programa Windows Insider; Tendrá acceso a las compilaciones de versión preliminar de las actualizaciones de software de HoloLens antes de que estén disponibles para el público general.

[Obtenga Windows Insider versión preliminar de Microsoft HoloLens](hololens-insider.md).
