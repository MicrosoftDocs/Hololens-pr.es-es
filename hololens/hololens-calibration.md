---
title: Mejora de la calidad visual y la comodidad
description: Obtenga información sobre cómo calibrar la distancia interpupilar (IPD) para mejorar la calidad de sus objetos visuales en dispositivos HoloLens.
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: calibración, comodidad, objetos visuales, calidad, ipd, HoloLens, Windows Mixed Reality, cascos de VR
ms.openlocfilehash: cdeef216cbf6d1fb165737ae194071c60b31146a
ms.sourcegitcommit: 20ea1ed37772655504ccb11a7e185ed19d85f336
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2021
ms.locfileid: "127833563"
---
# <a name="improve-visual-quality-and-comfort"></a>Mejora de la calidad visual y la comodidad

HoloLens 2 y HoloLens (1.ª generación) funcionan mejor cuando se han calibrado con sus ojos.

Aunque ambos dispositivos necesitan calibrarse para ofrecer una experiencia óptima de visualización de hologramas, usan diferentes tecnologías y técnicas de calibración.  Vaya directamente a [Calibración de HoloLens 2](#calibrating-your-hololens-2) o [Calibración de HoloLens (1.ª generación)](#calibrating-your-hololens-1st-gen).

## <a name="calibrating-your-hololens-2"></a>Calibración de HoloLens 2

HoloLens 2 usa tecnología de seguimiento ocular para mejorar su experiencia al ver el entorno virtual e interactuar con este. La calibración de HoloLens 2 garantiza que pueda realizar un seguimiento exacto de sus ojos (y de los ojos de cualquier otra persona que use el dispositivo). También contribuye a la comodidad del usuario, a la alineación de los hologramas y al seguimiento de manos. Tras la calibración, los hologramas aparecerán correctamente aunque el visor se desplace por la cabeza.

HoloLens 2 pide al usuario que calibre el dispositivo en las siguientes circunstancias:

- El usuario está usando el dispositivo por primera vez.
- El usuario ha optado previamente por no completar el proceso de calibración.
- El proceso de calibración no se realizó correctamente la última vez que el usuario usó el dispositivo.
- El usuario ha eliminado sus perfiles de calibración.
- El usuario se quita el dispositivo y se lo vuelve a poner, y se da cualquiera de las circunstancias anteriores. 

![Mensaje de la calibración para ajustar el dispositivo a los ojos.](./images/07-et-adjust-for-your-eyes.png)

Durante este proceso, verá un conjunto de objetivos (gemas). No pasa nada si parpadea durante la calibración, pero trate de centrarse en las gemas e ignorar otros objetos presentes en la habitación.  Si se centra en las gemas, HoloLens podrá reconocer la posición de sus ojos para representar su mundo holográfico.

![Mensaje de la calibración que indica al usuario que mantenga quieta la cabeza y siga los puntos con los ojos.](./images/07-et-hold-head-still.png)

![Mensaje de la calibración con gemas de ejemplo.](./images/08-et-gems.png)

![Mensaje de la calibración que indica que el ajuste está en curso.](./images/09-et-adjusting.png)

Si la calibración se ha realizado correctamente, aparecerá la pantalla correspondiente.  Si no es así, obtenga más información sobre el [diagnóstico de errores de calibración](hololens2-display.md#troubleshooting).

![Mensaje de la calibración que indica que la calibración se ha realizado correctamente.](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a>Calibración al compartir un dispositivo o una sesión

Varios usuarios pueden compartir un dispositivo HoloLens 2 sin necesidad de que cada persona complete la configuración del dispositivo. Cuando un nuevo usuario se pone el dispositivo en la cabeza por primera vez, el HoloLens 2 le pide automáticamente que calibre los objetos visuales. Cuando un usuario que ha calibrado anteriormente objetos visuales se coloca el dispositivo en la cabeza, la pantalla se ajusta perfectamente para ofrecer una experiencia de visualización cómoda y de calidad.  

### <a name="manually-starting-the-calibration-process"></a>Inicio manual del proceso de calibración

1. Use el gesto de inicio para abrir el [**menú Inicio**](hololens2-basic-usage.md#start-gesture).
1. Si la aplicación Configuración no está anclada a **Inicio**, seleccione **Todas las aplicaciones**.
1. Seleccione **Configuración** y, a continuación, **Sistema** > **Calibración** > **Calibración de los ojos** > **Ejecutar calibración de los ojos**.

   ![Opción Ejecutar calibración de ojos en la aplicación Configuración.](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a>Compatibilidad con posicionamiento automático de los ojos

En HoloLens 2, las posiciones de los ojos permiten un posicionamiento preciso de los hologramas, una experiencia de visualización cómoda y una mejor calidad de visualización. Las posiciones de los ojos se calculan internamente como parte del análisis del seguimiento ocular. Sin embargo, para ello es necesario que cada usuario complete la calibración del seguimiento ocular, incluso en aquellos casos en los que la experiencia no requiera una entrada con la mirada.

El **posicionamiento automático de los ojos** posibilita estos escenarios sin necesidad de interacción para calcular las posiciones de los ojos del usuario. El posicionamiento automático de los ojos empieza a funcionar en segundo plano inmediatamente después de que el usuario se coloque el dispositivo. Si el usuario no ha calibrado previamente el seguimiento ocular, el posicionamiento automático de los ojos comenzará a proporcionar las posiciones de los ojos del usuario al sistema de visualización transcurrido un tiempo de procesamiento de 20-30 segundos. Los datos de usuario no se conservan en el dispositivo, por lo que este proceso se repite si el usuario se quita el dispositivo y se lo vuelve a poner, o bien si el dispositivo se reinicia o reactiva tras haberse suspendido.

Cuando un usuario sin calibrar se coloca el dispositivo, la característica de posicionamiento automático de los ojos provoca algunos cambios en el comportamiento del sistema. En este contexto, un usuario sin calibrar es alguien que no ha completado anteriormente el proceso de calibración del seguimiento ocular en el dispositivo.

| Aplicación activa | Comportamiento anterior | Comportamiento a partir de la versión 20H2 Update de Windows Holographic |
|:-------------------|:-----------------|:-----------------------------------|
| Aplicación no habilitada para la mirada o shell de Holographic |Se muestra el cuadro de diálogo de solicitud de calibración del seguimiento ocular. | No se muestra ningún mensaje. |
| Aplicación habilitada para la mirada | Se muestra el cuadro de diálogo de solicitud de calibración del seguimiento ocular. | La solicitud de calibración del seguimiento ocular solo se muestra cuando la aplicación accede a la secuencia de mirada. |

Si el usuario pasa de una aplicación con la opción de mirada no habilitada a otra que tiene acceso a los datos de mirada, se mostrará la solicitud de calibración. 

Por lo demás, el sistema se comportará de un modo similar a cuando el usuario no tiene una calibración activa del seguimiento ocular. Por ejemplo, el gesto de inicio con una sola mano no estará habilitado. No se cambiará la experiencia inmediata de la configuración inicial.

En el caso de experiencias que requieran datos de mirada o un posicionamiento preciso de hologramas, recomendamos a los usuarios sin calibrar que realicen la calibración del seguimiento ocular. Puede accederse a este proceso desde la solicitud de calibración del seguimiento ocular. También se puede iniciar la aplicación Configuración desde el menú "Inicio" y, a continuación, seleccionar **Sistema > Calibración > Calibración de los ojos > Ejecutar calibración de los ojos**.

#### <a name="deferred-calibration-prompt"></a>Solicitud de calibración diferida

Con el posicionamiento automático de los ojos, el cuadro de diálogo de solicitud de calibración del seguimiento ocular se aplaza hasta que una aplicación solicite datos de mirada. De este modo, se garantiza que no se muestre una solicitud al usuario cuando la aplicación activa no requiera la mirada. Si la aplicación necesita datos de mirada y el usuario actual no ha realizado la calibración, se le mostrará a este una solicitud de calibración. Este comportamiento podría usarse para mostrar la solicitud de calibración del seguimiento ocular en un momento adecuado para la experiencia. Este método se recomienda por los siguientes motivos:

1.  El cuadro de diálogo de solicitud de calibración del seguimiento ocular proporciona al usuario los motivos por los que es necesario el seguimiento ocular.
2.  Muestra al usuario una manera de rechazar la calibración de los ojos.

Si el usuario opta por iniciar la calibración del seguimiento ocular, el foco debería volver a la aplicación original tras completarse la calibración. 

### <a name="calibration-data-and-security"></a>Seguridad y datos de la calibración

La información de la calibración se almacena localmente en el dispositivo y no se asocia a información de la cuenta. No hay ningún registro de quién ha usado el dispositivo sin calibración. Por lo tanto, a los usuarios nuevos se les pedirá que calibren los objetos visuales cuando usen el dispositivo por primera vez. Lo mismo sucederá con los usuarios que hayan optado por no realizar la calibración anteriormente o si esta no se realizó correctamente.

El dispositivo puede almacenar localmente hasta 50 perfiles de calibración. Cuando se alcanza esta cifra, el dispositivo borra automáticamente el perfil más antiguo no utilizado.

La información de calibración se puede eliminar en cualquier momento del dispositivo en **Configuración** > **Privacidad** > **Seguimiento ocular**.  

### <a name="disable-calibration"></a>Deshabilitar la calibración

#### <a name="eye-calibration-behavior-on-hololens-2-builds-20h2-and-newer"></a>Comportamiento de calibración de los ojos en las compilaciones de HoloLens 2 20H2 y más recientes

A partir de Windows Holographic, versión 20H2, con el inicio de la [compatibilidad con el posicionamiento automático de los ojos](hololens-release-notes.md#auto-eye-position-support), no es necesario deshabilitar la calibración. La solicitud de calibración solo aparece automáticamente si se usa una aplicación habilitada para el seguimiento de los ojos.

#### <a name="disabling-eye-calibration-on-hololens-2-older-builds"></a>Deshabilitación de la calibración de los ojos en compilaciones anteriores de HoloLens 2

Puede girar un conmutador de configuración en el casco para deshabilitar la calibración, pero es posible que el estado del conmutador no sea fácil de determinar. Se quitó y se reemplazó por la [compatibilidad con el posicionamiento automático de los ojos](hololens-release-notes.md#auto-eye-position-support), que aplaza la calibración al tiempo que proporciona corrección de color y posicionamiento de hologramas.

#### <a name="disabling-eye-calibration-on-hololens-1st-gen"></a>Deshabilitación de la calibración de los ojos en HoloLens (1.ª generación)

Para la [calibración de HoloLens (1.ª generación)](#calibrating-your-hololens-1st-gen), puede deshabilitar la solicitud de calibración de los ojos siguiendo estos pasos:

1. Seleccione **Configuración** > **Sistema** > **Calibración**.
1. Desactive **Cuando una nueva persona use este HoloLens, pedir automáticamente que ejecute la calibración de los ojos**.

   > [!IMPORTANT]
   > Esta opción puede afectar negativamente a la calidad y comodidad de la representación de los hologramas.  Si desactiva esta opción, las características que dependan del seguimiento ocular (como el desplazamiento de texto) dejarán de funcionar en las aplicaciones envolventes.

### <a name="hololens-2-eye-tracking-technology"></a>Tecnología de seguimiento ocular de HoloLens 2

El dispositivo usa su tecnología de seguimiento ocular para mejorar la calidad de la visualización y garantizar que todos los hologramas estén colocados de manera precisa y sean cómodos de ver en 3D. Al usar los ojos como puntos de referencia, el dispositivo puede regularse para cada usuario y ajustar sus objetos visuales, ya que el casco se mueve ligeramente durante el uso.  Todos los ajustes se producen sobre la marcha sin necesidad de intervención manual.
> [!NOTE]
> El establecimiento de la IPD no es aplicable a HoloLens 2, ya que el sistema calcula las posiciones del ojo.

Las aplicaciones de HoloLens usan seguimiento ocular para hacer un seguimiento de dónde miras en tiempo real. Esta es la principal capacidad que pueden usar los desarrolladores para habilitar un nivel completamente nuevo de contexto, comprensión humana e interacciones dentro de la experiencia de Holographic. Los desarrolladores no tienen que hacer nada para usar esta funcionalidad.

## <a name="calibrating-your-hololens-1st-gen"></a>Calibración de HoloLens (1.ª generación)

HoloLens (1.ª generación) ajusta la visualización de los hologramas según la [distancia interpupilar](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD). Si la IPD no es precisa, los hologramas pueden aparecer inestables o a una distancia incorrecta. Para mejorar la calidad de los objetos visuales, calibre el dispositivo de acuerdo con su distancia interpupilar (IPD).

Al configurar su dispositivo HoloLens (1.ª generación), este le pide que calibre los objetos visuales después de presentarse Cortana. Se recomienda completar el paso de calibración durante esta fase de configuración. Sin embargo, puede omitirlo esperando a la solicitud de Cortana y respondiendo a esta con "Omitir".

Durante el proceso de calibración, HoloLens le pide que alinee el dedo con una serie de seis objetivos por ojo. HoloLens usa este proceso para establecer correctamente la IPD con relación a sus ojos.

![Pantalla de alineación de la IPD mediante el dedo en el segundo paso.](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a>Iniciar manualmente el proceso de calibración

Si necesitas actualizar la calibración o si un nuevo usuario necesita ajustarla, puede ejecutar manualmente la aplicación Calibración en cualquier momento. La aplicación Calibración se instala de forma predeterminada. Para acceder a ella, use el menú **Inicio** o la aplicación Configuración.

Para ejecutar la aplicación Calibración usando el menú **Inicio**, siga estos pasos:

1. Use el gesto de [eclosión](hololens1-basic-usage.md) para abrir el menú **Inicio**.
1. Para ver todas las aplicaciones, seleccione **+** .
1. Seleccione **Calibración**.

   ![Acceso a la aplicación Calibración desde el shell.](./images/calibration-shell.png)

   ![Aplicación Calibración, que aparece como un objeto Live Cube después de iniciarse.](./images/calibration-livecube-200px.png)

Con el fin de usar la aplicación Configuración para ejecutar la aplicación Calibración, siga estos pasos:

1. Use el gesto de [eclosión](hololens1-basic-usage.md) para abrir el menú **Inicio**.
1. Si **Configuración** no está anclada a **Inicio**, seleccione **+** para ver todas las aplicaciones.
1. Haga clic en **Configuración**.
1. Seleccione **Sistema** > **Utilidades** > **Abrir calibración**.

   ![Inicio de la aplicación Calibración desde la aplicación Configuración.](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a>Cascos envolventes

Algunos cascos envolventes ofrecen la posibilidad de personalizar la configuración de IPD. Para cambiar la IPD del casco, abra la aplicación Configuración y seleccione **Realidad mixta** > **Visualización del casco**; a continuación, mueva el control deslizante. Los cambios se mostrarán en tiempo real en el casco. Si conoce su IPD, quizás de una visita al optometrista, también puede indicarla directamente.

También puede ajustar esta opción en su equipo seleccionando **Configuración** > **Realidad mixta** > **Visualización de casco**.

Si el casco no admite la personalización de la IPD, esta opción estará deshabilitada.
