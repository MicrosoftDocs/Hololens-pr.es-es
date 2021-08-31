---
title: Modo de plataformas móviles de HoloLens 2
description: Uso de HoloLens en plataformas móviles
keywords: plataformas móviles, movimiento dinámico, hololens, modo de plataformas móviles
author: evmill
ms.author: v-evmill
ms.reviewer: yabahman
ms.date: 8/10/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: high
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: cd46e162971ea709d865b2ac998cc7a517d231ec
ms.sourcegitcommit: 18f6c00a57a6b4608dadcec418d1970455d8ee3a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "122989214"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>Modo de plataformas móviles en plataformas móviles con movimiento dinámico bajo

En la **compilación 20348.1411 de Insider**, hemos agregado compatibilidad beta para el seguimiento de plataformas móviles con movimiento dinámico bajo en HoloLens 2. Después de instalar la compilación y habilitar el modo de plataformas móviles, podrá usar su HoloLens 2 en entornos anteriormente inaccesibles, como grandes navíos y grandes buques. Actualmente, la característica está destinada a habilitar únicamente estas plataformas móviles específicas, aunque nada le impide intentar usar la característica en otros entornos. Esta característica se centra primero en agregar compatibilidad con estos entornos.

> [!NOTE]
> Actualmente, esta característica solo está disponible para [usuarios de Windows Insider](hololens-insider.md).

![Ejemplo de plataforma móvil.](./images/mpm-compare.gif)

En este artículo se describe:

1. [Por qué es necesario el modo de plataformas móviles](#why-moving-platform-mode-is-necessary)
1. [Habilitación del modo de plataformas móviles](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>Por qué es necesario el modo de plataformas móviles

HoloLens debe poder hacer un seguimiento de la posición de la cabeza con [6 grados de libertad](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) (traslación y rotación de los ejes X, Y, Z) para mostrar hologramas estables. Para ello, HoloLens realiza un seguimiento de dos fragmentos de información similares de dos orígenes independientes:

1. Cámaras de luz visible, que realiza un seguimiento del entorno, por ejemplo, la sala física en la que se usa HoloLens.
1. Unidad de medida inercial (IMU), que consta de un acelerómetro, un giroscopio y un magnetómetro que realizan un seguimiento del movimiento de la cabeza y la orientación con respecto a la Tierra.

La información de estos dos orígenes se combina para realizar un seguimiento de la posición de la cabeza con una baja latencia y una frecuencia lo suficientemente alta para representar hologramas uniformes.

Sin embargo, este enfoque se basa en una suposición crítica: el entorno (controlado por las cámaras) permanece estacionario en relación con la Tierra (donde la IMU puede tomar medidas). Cuando esto no es así, como en el caso de un barco en el agua, la información de ambos orígenes puede entrar en conflicto entre sí y hacer que el rastreador se pierda. Este conflicto genera información de posición incorrecta y da lugar a hologramas inestables o incluso a la pérdida del seguimiento.

El modo de plataformas móviles soluciona este problema. Habilitar el modo de plataformas móviles sirve como sugerencia para que el rastreador no confíe en que las entradas del sensor estarán completamente de acuerdo entre sí en todo momento. En su lugar, necesitamos depender más del seguimiento visual e identificar rápidamente los datos de movimiento inercial incongruentes y filtrarlos en consecuencia antes de poder usar la entrada de la IMU.

## <a name="supported-environments-and-known-limitations"></a>Entornos admitidos y limitaciones conocidas

Aunque el modo de plataformas móviles se desarrolló para controlar de forma inteligente los casos de conflictos de datos inerciales y visuales, actualmente se encuentra limitado a grandes buques que experimentan un movimiento dinámico bajo. Es decir, existen ciertas limitaciones y escenarios no admitidos.

### <a name="known-limitations"></a>Limitaciones conocidas

- Los únicos entornos admitidos para el modo de plataformas móviles (MPM) son grandes navíos que experimentan un movimiento dinámico bajo. En otras palabras, todavía **no** se admiten muchos entornos o situaciones comunes debido a su movimiento de alta frecuencia y a los altos niveles de aceleración y [sobreaceleración](https://en.wikipedia.org/wiki/Jerk_(physics)). Por ejemplo: aviones, trenes, automóviles, bicicletas, autobuses, barcos pequeños, ascensores, etc.
- Puede que los hologramas se bamboleen ligeramente cuando MPM esté habilitado, en especial en aguas agitadas.
- Nada impide a los usuarios intentar usar MPM en entornos no admitidos; sin embargo, puede que se experimenten efectos secundarios no deseados si el dispositivo puede mantener el seguimiento en el espacio no admitido. Por ejemplo, es posible que los usuarios puedan usar MPM en un ascensor mientras cambian de planta, cuando antes esto era imposible. Desafortunadamente, si bien MPM permite que el dispositivo mantenga el seguimiento, no controla la administración de mapas en este momento. Los usuarios descubrirán que el cambio de planta en un ascensor hará que el dispositivo confunda las plantas superior e inferior y afecte negativamente a la calidad del mapa.

## <a name="prerequisites"></a>Requisitos previos

La compatibilidad beta con el modo de plataformas móviles solo requiere algunos requisitos previos:

1. Para instalar la compilación 20348.1411 o posterior, [instale la imagen de la compilación más reciente de Insider a través de ARC](hololens-insider.md#ffu-download-and-flash-directions) o [inscriba y actualice el dispositivo](hololens-insider.md#start-receiving-insider-builds).

   > [!NOTE]
   > Esta compilación solo está disponible actualmente en el [Canal de desarrolladores de Insider](hololens-insider.md#start-receiving-insider-builds).

2. Habilite el [modo de desarrollador y el Portal de dispositivos](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).

## <a name="enabling-moving-platform-mode"></a>Habilitación del modo de plataformas móviles

Para habilitar el modo de plataformas móviles, primero [habilite el Portal de dispositivos](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).

1. Seleccione el acordeón **Sistema** en el menú izquierdo.

   ![Primera imagen](.\images\moving-platform-1w.png)

2. Seleccione la página **Moving Platform Mode** (Modo de plataformas móviles) y active la casilla **Moving Platform Mode**.

    ![Segunda imagen](.\images\moving-platform-2z.png)

3. Cuando aparezca una advertencia, seleccione **Aceptar**.

   ![Tercera imagen](.\images\moving-platform-3w.png)

4. Reinicie el dispositivo, lo que se puede hacer a través del menú **Inicio/apagado** del Portal de dispositivos en la parte superior derecha o mediante el siguiente comando de voz &quot;Reboot the device&quot; (Reiniciar el dispositivo) y seleccione &quot;Sí&quot;.

   ![Cuarta imagen](.\images\moving-platform-4z.png)

Si no puede ver la opción del modo de plataformas móviles en el Portal de dispositivos, es probable que todavía no tenga la compilación adecuada. Consulte la sección [Requisitos previos](#prerequisites).

## <a name="reporting-issues"></a>Problemas de informes

Como se mencionó anteriormente, esta es una característica beta disponible solo en modo de desarrollador, lo que significa que puede encontrar problemas. Si esto sucede, para que podamos investigar y mejorar el producto:

1. Informe del problema a través del [Centro de opiniones](hololens-feedback.md) en la categoría **Hologram accuracy, stability, and reliability** (Precisión, estabilidad y confiabilidad del holograma) e incluya:
    1. una descripción del problema, incluido el comportamiento esperado y el comportamiento experimentado;
    1. una [captura de vídeo](holographic-photos-and-videos.md#capture-a-mixed-reality-video) del problema de realidad mixta.
2.  Abra un caso de soporte técnico en [https://aka.ms/hlsupport](https://aka.ms/hlsupport) y comparta la dirección URL de Centro de opiniones para que podamos ponernos en contacto en caso de que haya preguntas de seguimiento.