---
title: Actualizar HoloLens
description: Aprende a comprobar el número de compilación de HoloLens, mantenerte al día con las actualizaciones del dispositivo, unirte al Programa Insider y revertir las actualizaciones.
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283941"
---
# Actualizar HoloLens

HoloLens usa Windows Update, al igual que otros dispositivos Windows 10. HoloLens descargará e instalará automáticamente las actualizaciones del sistema siempre que esté conectado a la alimentación y conectado a Internet, incluso cuando esté en modo de espera.

En este artículo se mostrarán las herramientas de HoloLens para:

- visualización de la versión actual del sistema operativo (número de compilación)
- buscar actualizaciones
- actualización manual de HoloLens
- revertir a una actualización anterior

## Comprobar la versión del sistema operativo (número de compilación)

Puedes comprobar el número de versión del sistema (número de compilación) abriendo la aplicación Configuración y **seleccionando Sistema**  >  **acerca de**.

## Buscar actualizaciones y actualizar manualmente

Puede buscar actualizaciones en cualquier momento en la configuración.  Para ver las actualizaciones disponibles y buscar actualizaciones nuevas:

1. Abre la **aplicación** Configuración.
1. Vaya a **Actualización & Seguridad de**Windows  >  **Update**.
1. Seleccione **Buscar actualizaciones.**

Si hay una actualización disponible, empezará a descargar la nueva versión. Una vez completada la descarga, seleccione el botón Reiniciar **ahora** para desencadenar la instalación. Si el dispositivo está por debajo del 40 % y no está conectado, el reinicio no empezará a instalar la actualización.

Mientras holoLens instala la actualización, mostrará engranajes giratorios y un indicador de progreso. No desactives HoloLens durante este tiempo. Se reiniciará automáticamente una vez que haya completado la instalación.

HoloLens aplica una actualización cada vez.  Si su HoloLens tiene más de una versión detrás de la versión más reciente, es posible que deba ejecutar el proceso de actualización varias veces para actualizarlo por completo.

## Volver a una versión anterior - HoloLens 2

En algunos casos, es posible que quiera volver a una versión anterior del software HoloLens. Para ello, usa Advanced Recovery Companion para restablecer HoloLens a la versión anterior.

> [!NOTE]
> Al volver a una versión anterior, se eliminan los archivos y la configuración personales.

Para volver a una versión anterior de HoloLens 2, siga estos pasos:

1. Asegúrate de que no tienes ningún teléfono o dispositivo Windows conectado a tu equipo.
1. En el equipo, descarga [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) desde Microsoft Store.
1. Descarga la [versión más reciente de HoloLens 2](https://aka.ms/hololens2download).
1. Cuando haya terminado estas descargas, abra **Descargas del explorador de**  >  **archivos.** Haz clic con el botón derecho en la carpeta comprimida que acabas de descargar y selecciona **Extraer todo** > **Extraer** para descomprimirlo.
1. Conecta HoloLens a tu PC mediante un cable USB-A a USB-C. (Incluso si has estado usando otros cables para conectar tu HoloLens, este es el que mejor funciona).
1. El Advanced Recovery Companion detecta automáticamente su HoloLens. Seleccione el icono de **Microsoft HoloLens**
1. En la siguiente pantalla, **seleccione** La selección manual del paquete y, a continuación, seleccione el archivo de instalación incluido en la carpeta que descomprimió en el paso 4. (Busque un archivo con la extensión .ffu).
1. Seleccione **Instalar software**y siga las instrucciones.

## Volver a una versión anterior- HoloLens (1.ª generación)

En algunos casos, es posible que quiera volver a una versión anterior del software HoloLens. Para ello, usa la Herramienta de recuperación de dispositivos windows para restablecer HoloLens a la versión anterior.

> [!NOTE]
> Al volver a una versión anterior, se eliminan los archivos y la configuración personales.

Para volver a una versión anterior de HoloLens 1, siga estos pasos:

1. Asegúrate de que no tienes ningún teléfono o dispositivo Windows conectado a tu equipo.
1. En el equipo, descarga la Herramienta [de recuperación de dispositivos windows (WDRT).](https://support.microsoft.com/help/12379)
1. Descargue el [Paquete de recuperación de la actualización de aniversario de HoloLens](https://aka.ms/hololensrecovery).
1. Cuando finalicen las descargas, abra **Descargas del explorador de**  >  **archivos.** Haga clic con el botón secundario en la carpeta comprimida que acaba de descargar y seleccione **Extraer todo**  >  **extraer** para descomprimirla.
1. Conecta tu HoloLens a tu PC con el cable micro USB que viene. (Incluso si has estado usando otros cables para conectar tu HoloLens, este es el que mejor funciona).
1. WdRT detectará automáticamente tu HoloLens. Seleccione el icono de **Microsoft HoloLens**
1. En la siguiente pantalla, seleccione **Selección manual** del paquete y elija el archivo de instalación incluido en la carpeta que descomprimió en el paso 4. (Busque un archivo con la extensión .ffu).
1. Seleccione **Instalar software**y siga las instrucciones.

> [!NOTE]
> Si WDRT no detecta holoLens, intenta reiniciar el equipo. Si esto no funciona, seleccione **No se ha detectado Mi dispositivo**, **Microsoft HoloLens** y, a continuación, siga las instrucciones.

## Programa Windows Insider en HoloLens

¿Quieres ver las últimas características de HoloLens?  Si es así, únete al Programa Windows Insider; tendrá acceso a las versiones preliminares de las actualizaciones de software de HoloLens antes de que estén disponibles para el público en general.

[Obtener la vista previa de Windows Insider para Microsoft HoloLens](hololens-insider.md).
