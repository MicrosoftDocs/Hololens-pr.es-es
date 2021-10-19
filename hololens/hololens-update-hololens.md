---
title: Actualizar HoloLens 2
description: Obtenga información sobre cómo comprobar el número HoloLens compilación, mantenerse al día con las actualizaciones del dispositivo, unirse al programa Insiders y revertir las actualizaciones.
keywords: cómo, actualizar, revertir, HoloLens, comprobar compilación, número de compilación
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-beehanson
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/11/2021
audience: ITPro
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: 080fb184c7eca3fdb978e860a29764f5012a179e
ms.sourcegitcommit: f105a770814ccd61e88b650448902a03c95b7a3c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2021
ms.locfileid: "130151699"
---
# <a name="update-hololens-2"></a>Actualizar HoloLens 2

## <a name="overview"></a>Introducción

Siempre estamos trabajando en nuevas características, correcciones de errores y actualizaciones de seguridad. Cuando estas actualizaciones estén listas, se le notificará.

Según sus preferencias, el HoloLens descargará e instalará automáticamente las actualizaciones del sistema cada vez que esté conectado a la alimentación, conectado a Internet e incluso en espera.

Para asegurarse de que HoloLens está siempre actualizado, déjelo conectado con el cargador que viene con él. También quiere que el HoloLens conectado a Internet. De este modo, descargará e instalará automáticamente las actualizaciones del sistema. 

Con Windows update service, controlará varios aspectos del proceso de actualización, como qué dispositivos obtienen las actualizaciones en qué momento. Este control es útil porque puede realizar actualizaciones en un subconjunto de HoloLens dispositivos para pruebas. A continuación, revierte las actualizaciones a las restantes. También puede definir diferentes programaciones de actualización para diferentes tipos de actualizaciones.

## <a name="types-of-updates"></a>Tipos de actualizaciones

Por HoloLens, puede administrar automáticamente dos tipos de actualizaciones.

- Actualizaciones de características: publicadas dos veces al año.
- Actualizaciones de calidad: incluyen actualizaciones de seguridad críticas. Se lanzan mensualmente o según sea necesario.

Use **Update** / **AllowAutoUpdate para** administrar el examen, la descarga y la instalación de actualizaciones. 

## <a name="scheduling-updates"></a>Programación de actualizaciones

También puede establecer una programación de actualización. Puede ser en un día determinado, o cada día, a una hora determinada. Por ejemplo, a las 5 p. m., o fuera del horario de actividad.

Por último, unas pocas palabras sobre cómo planear la estrategia de actualización. Se admiten aplazamientos de actualizaciones, por lo que puede decidir cuánto tiempo se debe esperar después de que Microsoft publica una actualización para instalar esa actualización en los dispositivos.

A veces, a una empresa le gusta probar primero todas las nuevas características para asegurarse de que todo funciona y están familiarizados con las nuevas actualizaciones para que su equipo de soporte técnico esté preparado. Una vez que han confirmado que todo es bueno, se lanzan las actualizaciones a toda la empresa. Al asociar subconjuntos de los dispositivos con diferentes directivas de aplazamiento, conocidas como anillos de actualización, puede coordinar una estrategia de implementación de actualizaciones para su organización.

## <a name="hololens-update-tools"></a>HoloLens de actualización

En esta sección se le ayudará a HoloLens herramientas para:

- comprobar si hay actualizaciones
- actualizar manualmente HoloLens
- ver la versión actual del sistema operativo (número de compilación)
- revertir a una actualización anterior

### <a name="check-for-updates-and-manually-update"></a>Buscar actualizaciones y actualizar manualmente

Puede buscar actualizaciones en cualquier momento en la configuración.  Para ver las actualizaciones disponibles y comprobar si hay nuevas actualizaciones:

1. Abra la aplicación **Configuración**.
1. Vaya **a Update & Security**  >  **Windows Update**.
1. Haga clic en **Buscar actualizaciones**.

Si hay una actualización disponible, empezará a descargar la nueva versión. Una vez completada la descarga, seleccione el **botón Reiniciar** ahora para desencadenar la instalación. Si el dispositivo está por debajo del 40 % y no está conectado, el reinicio no iniciará la instalación de la actualización.

Mientras el HoloLens instala la actualización, mostrará engranajes de giro y un indicador de progreso. No apague el HoloLens durante este tiempo. Se reiniciará automáticamente una vez que haya completado la instalación.

HoloLens aplica una actualización a la vez.  Si el HoloLens tiene más de una versión detrás de la versión más reciente, es posible que deba ejecutar el proceso de actualización varias veces para actualizarlo por completo.

### <a name="check-your-operating-system-version-build-number"></a>Comprobación de la versión del sistema operativo (número de compilación)

Para comprobar el número de versión del sistema (número de compilación), **abra Configuración** seleccione **Sistema**  >  **acerca de**.

### <a name="go-back-to-a-previous-version"></a>Volver a una versión anterior

En algunos casos, es posible que quiera volver a una versión anterior del software HoloLens software. Los pasos recomendados son:

1. Póngase en contacto con el soporte técnico para ver si pueden corregir el problema.
    1. Asegúrese de **que la telemetría** opcional o completa está habilitada, lo que hace que el error sea más fácil de diagnosticar para los ingenieros. 
    1. En [Comentarios de archivo,](hololens-feedback.md) sea lo más descriptivo posible. Tome nota del título o use la característica compartir para que pueda compartir el error con soporte técnico.
    1. Póngase en [contacto con el servicio de](https://aka.ms/hlsupport)soporte técnico. Si el problema es uno que debe resolverse volviendo a una versión anterior, pueden suministrarle la FFU para que flashee el dispositivo.

1. Como alternativa, puede volver [a actualizar el HoloLens 2 con advanced recovery Companion](hololens-recovery.md#clean-reflash-the-device).
    1.  Elija la versión a la que desea flash: 
        1.  Puede descargar la [versión de HoloLens 2 más reciente.](https://aka.ms/hololens2download)
        1.  Puede usar la compilación predeterminada que hospeda ARC.
        1.  Puede usar el soporte técnico de compilación que se le ha proporcionado.

> [!NOTE]
> Al volver a una versión anterior, se eliminan los archivos y la configuración personales.

Además, si desea permanecer en la versión instalada actualmente, también puede pausar manualmente [las actualizaciones](hololens-updates.md#pause-updates-via-device). Esto dará tiempo al equipo de ingeniería para corregir el problema.

## <a name="windows-insider-program-on-hololens"></a>Windows Programa Insider en HoloLens

¿Quiere ver las características más recientes de HoloLens?  Si es así, una el Windows Programa Insider; tendrá acceso a las compilaciones en versión preliminar de HoloLens de software antes de que estén disponibles para el público general.

[Obtenga Windows versión preliminar de Insider para Microsoft HoloLens](hololens-insider.md).