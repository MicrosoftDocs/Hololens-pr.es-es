---
title: Batería y carga de HoloLens 2
description: Cómo cargar HoloLens y usar baterías externas.
ms.assetid: E0AB903E-454E-46F6-AB25-4DFA0A475B0C
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 05/14/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: a0ae0ccade01d7df520cd6cb142a9b51e63a2b05
ms.sourcegitcommit: c73cdefbdb4411f6a187cc38bb2570dadeb156bf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2021
ms.locfileid: "129163988"
---
# <a name="hololens-2-battery-and-charging"></a>Batería y carga de HoloLens 2

En esta página se ofrecen detalles sobre la carga de HoloLens 2 y el uso de baterías externas.

## <a name="charging-the-device"></a>Carga del dispositivo

Use el [cable y cargador USB-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) incluidos con HoloLens 2, ya que esa es la mejor manera de cargar el dispositivo. El cargador incluido con HoloLens 2 proporciona hasta 9 V a 2 A (18 W). Con el cargador de pared suministrado, los dispositivos HoloLens 2 pueden cargar la batería por completo en menos de 65 minutos cuando están en espera. Si esos accesorios no están disponibles, asegúrese de que el cargador disponible admita al menos 15 W de potencia.

> [!NOTE]
> Si es posible, evite usar un equipo para cargar el dispositivo por USB, ya que eso es lento.

## <a name="checking-the-battery-charge-level"></a>Comprobación del nivel de carga de la batería
Si el dispositivo se ha encendido correctamente y está en funcionamiento, hay tres formas de comprobar el nivel de carga de la batería:

- Desde el menú principal de la interfaz de usuario del dispositivo HoloLens.
- Los LED situados junto al botón de encendido (para una carga de un 40 %, debería ver al menos dos LED fijos).
    - Cuando el dispositivo se está cargando, se ilumina el indicador de la batería para señalar el nivel de carga actual.  La última luz parpadea para indicar que se está cargando.
    - Cuando HoloLens está encendido, el indicador de la batería muestra el nivel de esta en cinco incrementos.
    - Si solo hay encendida una de las cinco luces, el nivel de la batería está por debajo del 20 por ciento.
    - Si el nivel de la batería es demasiado bajo y se intenta encender el dispositivo, una luz parpadea brevemente y después se apaga.
- En el equipo host, abra **Explorador de archivos** y busque el dispositivo HoloLens 2 en el lado izquierdo, en **Este equipo**. Haga clic con el botón derecho en el dispositivo y seleccione **Propiedades**. Un cuadro de diálogo muestra el nivel de carga de la batería.

   ![Una pantalla de propiedades de HoloLens 2 muestra el nivel de carga de la batería.](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>Especificaciones de carga alternativas

HoloLens 2 se puede cargar mediante fuentes de [suministro de energía USB](https://www.usb.org/usb-charger-pd) de hasta 27 vatios. Si la fuente puede suministrar al menos 10 vatios, el tiempo de funcionamiento de HoloLens se puede ampliar (es posible que de manera indefinida para algunas cargas de trabajo). 

> [!NOTE]
> El uso de un cable de carga USB-A a USB-C limita la carga a 7,5 vatios. El tiempo de funcionamiento se amplía, pero no igual que si se usa USB-C a C.

Cuando HoloLens está en espera, 18 vatios bastan para alcanzar la tasa de carga máxima de la batería interna. Cuando HoloLens está en uso, la tasa de carga se puede reducir, ya que HoloLens da prioridad al funcionamiento sobre la carga.

> [!IMPORTANT]
> Se recomienda cargar HoloLens 2 a 5 V/1,5 A como mínimo. No se deben usar cargadores que no puedan suministrar al menos 5 V/1,5 A. 

### <a name="external-battery-packs"></a>Baterías externas

Las baterías que cumplen las especificaciones anteriores se pueden usar con HoloLens 2. Sin embargo, tenga en cuenta que algunas baterías USB-C recargan y suministran energía a través del mismo puerto USB-C. Es importante que estas baterías implementen [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) para garantizar que carguen HoloLens en lugar de cargar de él. 

### <a name="managing-heat"></a>Administración del calor

Como ocurre con cualquier dispositivo, la carga de HoloLens genera calor. Cuanto más rápida es la carga, más calor se genera. Además, cargar una batería descargada genera más calor que hacerlo cuando la batería está prácticamente cargada. Los clientes que necesitan usar HoloLens durante largos períodos de tiempo en entornos cálidos pueden usar las técnicas siguientes:

- Es aceptable conectar HoloLens 2 a una fuente de alimentación externa aunque la batería interna esté totalmente cargada.
- Cuando se agota una batería externa, HoloLens sigue funcionando con su batería interna.    
- Si el calor sigue siendo un problema después de seguir los pasos anteriores, considere la posibilidad de usar un cargador o una batería que limite la carga a 1,5 A. Tenga en cuenta que esta opción no ofrece tanto tiempo de funcionamiento, ya que la batería interna sigue agotándose lentamente.

## <a name="troubleshooting"></a>Solución de problemas


### <a name="hololens-charges-external-battery"></a>HoloLens carga una batería externa
Si HoloLens 2 carga una batería externa en lugar de cargarse, esto indica que la batería no implementa [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). La manera recomendada de resolver este problema es cambiar a una batería más reciente, pero también puede intentar cambiar a un cable USB-A a USB-C. Tenga en cuenta que esto limita la tasa de carga a 7,5 vatios.
