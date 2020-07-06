---
title: Use el mando de HoloLens
description: Este artículo describe cómo usar el mando HoloLens, incluyendo el apareamiento del mando, la carga y la recuperación.
ms.assetid: 7d4a30fd-cf1d-4c9a-8eb1-1968ccecbe59
ms.date: 09/16/2019
manager: jarrettr
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 13b86c049ba8bb6ed67be202609d27c8d47ffc53
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829648"
---
# Usar el mando en HoloLens (1ª generación)

El mando fue diseñado específicamente para el HoloLens (1 era generación) y le da otra forma de interactuar con los hologramas. Viene con los HoloLens (1 era generación), en una caja separada.

Úselo en lugar de los gestos con la mano para seleccionar, desplazar, mover y cambiar el tamaño de las aplicaciones.

## El hardware del mando y apareamiento

El mando de HoloLens (1 era generación) tiene un lazo en el dedo para que sea más fácil de sujetar, y una luz indicadora.

![Mando de HoloLens](images/use-hololens-clicker-1.png)

### Luces indicadoras del mando

Esto es lo que significan las luces del mando.

- ** Blanco parpadeante**. El mando está en modo de apareamiento.
- ** Blanco parpadeando rápido**. Apareamiento completado.
- **Blanco sólido**. El mando se está cargando.
- **Ámbar parpadeante**. La batería está baja.
- **Ámbar sólido**. El mando tuvo un error y tendrá que reiniciarlo. Mientras se presiona el botón de apareamiento, haga clic y manténgalo presionado durante 15 segundos.

### Aparee el mando con su HoloLens (1 era generación)

1. Utilice el gesto de eclosión para ir a **Inicio**, luego seleccione **Ajustes** > **Dispositivos** y verifique que el Bluetooth esté activado.
1. En el mando, mantenga presionado el botón de apareamiento hasta que la luz de estado parpadee en blanco.
1. En la pantalla de apareamiento, seleccione**Comando** > **Emparejamiento**.

### Cargue el mando

Cuando la batería del mando esté baja, el indicador de la batería parpadeará en ámbar. Enchufe el cable Micro USB en una fuente de alimentación USB para cargar el dispositivo.

## Use el mando con el HoloLens (1 era generación)

### Mantenga el mando

Para ponerlo en el mando, deslice el bucle sobre su dedo anular o medio de manera que el puerto Micro USB quede orientado hacia su muñeca. Apoye su pulgar en la hendidura.

![Cómo sostener el mando](images/use-hololens-clicker-2.png)

### Movimientos del mando

Los movimientos del mando son pequeñas rotaciones de muñeca, no los grandes movimientos usados para los movimientos de mano de la HoloLens. Y HoloLens reconoce sus movimientos y clics incluso si el mando está fuera del[marco del movimiento](hololens1-basic-usage.md), así que puede mantener el mando en la posición que le resulte más cómoda.

- **Seleccione**. Para seleccionar un holograma, botón u otro elemento, mírelo y haga clic.

- **Haga clic y mantenga**. Haga clic y mantenga el pulgar en el botón para hacer algunas de las mismas cosas que haría al mantener pulsado, como mover o cambiar el tamaño de un holograma.

- **Desplazarte**. En la barra de aplicaciones, seleccione**Herramienta de desplazamiento**. Mantenga pulsado el botón y gire la palanca hacia arriba, hacia abajo, hacia la izquierda o hacia la derecha. Para desplazarse más rápido, mueva su mano más lejos del centro de la herramienta de desplazamiento.

- **Zoom**. En la barra de aplicaciones, seleccione**Herramienta de zoom**. Mantenga pulsado el botón y gire la palanca hacia arriba para acercar o hacia abajo para alejar.

> [!TIP]
> Para acercar o alejar el zoom al usar Microsoft Edge, mire una página y haga doble clic.

## Reinicie o restaure el mando

Aquí tiene algunas cosas que puede probar si el mando del HoloLens no responde o no funciona bien.

### Reiniciar el mando

Use la punta de un bolígrafo para presionar y mantener el botón de emparejamiento. Al mismo tiempo, haga clic y mantenga el mando durante 15 segundos. Si el mando ya estaba apareado con su HoloLens, seguirá apareado después de que se reinicie.

Si el mando no se enciende o no se reinicia, intente cargarlo usando el cargador HoloLens. Si la batería está muy baja, puede tardar unos minutos en encenderse la luz blanca del indicador.

### Aparear de nuevo el mando

Seleccione **Ajustes ** > **Dispositivos **y seleccione el mando. Seleccione**Eliminar**, espere unos segundos y vuelva a aparear el mando.

### Restaurar el mando

Si al reiniciar y volver a aparear el mando no se soluciona el problema, la Herramienta de recuperación de dispositivos de Windows puede ayudarle a recuperarlo. El proceso de recuperación puede llevar algún tiempo, e instalará la última versión del software del mando. Para usar la herramienta, necesitará un ordenador con Windows 10 o posterior que tenga al menos 4 GB de espacio de almacenamiento libre.

Para restaurar el mando:

1. Descargue e instale [Windows Device Recovery Tool](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/)en su ordenador.
1. Conecte el mando a su ordenador usando el cable Micro USB que viene con su HoloLens.
1. Ejecute Windows Device Recovery Tool y siga las instrucciones.

Si el mando no se detecta automáticamente, seleccione**Mi dispositivo no fue detectado**y siga las instrucciones para poner su dispositivo en modo de recuperación.
