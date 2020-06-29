---
title: Actualizar HoloLens
description: Consulta el número de compilación, la actualización y la reversión de las actualizaciones de HoloLens.
keywords: procedimientos, actualizar, revertir, HoloLens, comprobar compilación, número de compilación
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
ms.openlocfilehash: ee007b00b350ea0f80cda34964d32a57dc6dc0c6
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828595"
---
# Actualizar HoloLens

HoloLens usa Windows Update, como otros dispositivos de Windows 10. HoloLens descargará e instalará automáticamente actualizaciones del sistema siempre que se conecten a Internet y se conecten a Internet, incluso cuando esté en modo de suspensión.

Este artículo le guiará a través de las herramientas de HoloLens para:

- visualización de la versión del sistema operativo actual (número de compilación)
- comprobando actualizaciones
- actualización manual de HoloLens
- volver a una actualización anterior

## Comprobar la versión del sistema operativo (número de compilación)

Puede comprobar el número de versión del sistema (número de compilación) abriendo la aplicación configuración y seleccionando **sistema**  >  **acerca de**.

## Comprobar si hay actualizaciones y actualizar manualmente

Puede comprobar si hay actualizaciones en cualquier momento en configuración.  Para ver las actualizaciones disponibles y comprobar si hay nuevas actualizaciones:

1. Abra la aplicación **configuración** .
1. Vaya a **Actualizar & seguridad**de  >  **Windows Update**.
1. Seleccione **Buscar actualizaciones**.

Si hay una actualización disponible, empezará a descargar la nueva versión. Una vez completada la descarga, seleccione el botón **reiniciar ahora** para desencadenar la instalación. Si tu dispositivo está por debajo del 40% y no conectado, el reinicio no comenzará a instalar la actualización.

Mientras tu HoloLens esté instalando la actualización, mostrará artes de giro y un indicador de progreso. No apagues tu HoloLens durante este tiempo. Se reiniciará automáticamente una vez completada la instalación.

HoloLens aplica una actualización a la vez.  Si tu HoloLens es más de una versión que se encuentra detrás de lo más reciente, es posible que tengas que ejecutar el proceso de actualización varias veces para que quede completamente actualizado.

## Volver a una versión anterior: HoloLens 2

En algunos casos, es posible que desee volver a una versión anterior del software HoloLens. Puedes hacerlo usando el Asistente de recuperación avanzada para restablecer tu HoloLens a la versión anterior.

> [!NOTE]
> Al volver a una versión anterior, se eliminan los archivos personales y la configuración.

Para volver a una versión anterior de HoloLens 2, siga estos pasos:

1. Asegúrese de que no tiene ningún teléfono o dispositivo Windows conectado a su PC.
1. En su equipo, descargue el [complemento de recuperación avanzada](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) desde Microsoft Store.
1. Descarga la [versión más reciente de HoloLens 2](https://aka.ms/hololens2download).
1. Cuando hayas terminado estas descargas, abre descargas del **Explorador de archivos**  >  **Downloads**. Haz clic con el botón derecho en la carpeta comprimida que acabas de descargar y selecciona **Extraer todo** > **Extraer** para descomprimirlo.
1. Conecta tu HoloLens a tu PC con un cable USB-a a USB-C. (Incluso si has estado usando otros cables para conectar tu HoloLens, este es el que mejor funciona).
1. El Asistente de recuperación avanzada detecta automáticamente HoloLens. Selecciona el icono de **Microsoft HoloLens** .
1. En la siguiente pantalla, seleccione **selección de paquetes manual** y, a continuación, seleccione el archivo de instalación contenido en la carpeta que descomprime en el paso 4. (Busque un archivo con la extensión. FFU).
1. Seleccione **instalar software**y siga las instrucciones.

## Volver a una versión anterior: HoloLens (1ª generación)

En algunos casos, es posible que desee volver a una versión anterior del software HoloLens. Puedes hacerlo usando la herramienta de recuperación de dispositivos de Windows para restablecer tu HoloLens a la versión anterior.

> [!NOTE]
> Al volver a una versión anterior, se eliminan los archivos personales y la configuración.

Para volver a una versión anterior de HoloLens 1, siga estos pasos:

1. Asegúrese de que no tiene ningún teléfono o dispositivo Windows conectado a su PC.
1. En su equipo, descargue la [herramienta de recuperación de dispositivos de Windows (WDRT)](https://support.microsoft.com/help/12379).
1. Descarga el [paquete de recuperación](https://aka.ms/hololensrecovery)de la actualización de aniversario de HoloLens.
1. Cuando finalicen las descargas, abra el **Explorador de archivos**  >  **descargas**. Haga clic con el botón derecho en la carpeta comprimida que acaba de descargar y seleccione **extraer todos los**  >  **extractos** para descomprimirlo.
1. Conecta tu HoloLens a tu equipo con el cable micro-USB con el que venía. (Incluso si has estado usando otros cables para conectar tu HoloLens, este es el que mejor funciona).
1. WDRT detectará automáticamente HoloLens. Selecciona el icono de **Microsoft HoloLens** .
1. En la siguiente pantalla, seleccione **selección manual de paquetes** y elija el archivo de instalación contenido en la carpeta que descomprime en el paso 4. (Busque un archivo con la extensión. FFU).
1. Seleccione **instalar software**y siga las instrucciones.

> [!NOTE]
> Si el WDRT no detecta HoloLens, intenta reiniciar el equipo. Si eso no funciona, **no se detectó seleccionar mi dispositivo**, seleccione **Microsoft HoloLens**y, a continuación, siga las instrucciones.

## Programa Windows Insider en HoloLens

¿Quieres ver las características más recientes de HoloLens?  Si es así, Únete al programa Windows Insider; Obtendrá acceso a versiones preliminares de las actualizaciones del software HoloLens antes de que estén disponibles para el público en general.

[Obtén Windows Insider Preview para Microsoft HoloLens](hololens-insider.md).
