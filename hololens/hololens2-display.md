---
title: Solución de problemas de pantalla de HoloLens 2
description: Expectativas de pantalla de HoloLens 2. Instrucciones para la configuración de la pantalla para obtener la mejor calidad de imagen.
author: BrandonBray
ms.author: branbray
ms.date: 8/13/2020
ms.topic: article
keywords: display, calibration, comfort, visuals, quality, ipd
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 38bab16d2d0d4ace5879f00c133d66b9974e4b2a
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034598"
---
# <a name="hololens-2-display-troubleshooting"></a>Solución de problemas de pantalla de HoloLens 2

## <a name="overview"></a>Información general
La pantalla de HoloLens 2 es una combinación de guías de onda y proyectores de luz. Los usuarios miran a través de las guías de onda (las lentes dentro del visor) cuando usan el casco. Los proyectores de luz se encuentran dentro de la estructura por encima de la frente. HoloLens 2 usa luz láser para iluminar la pantalla.

## <a name="troubleshooting"></a>Solución de problemas

Realice los pasos siguientes para garantizar la óptima calidad visual de los hologramas presentados en la pantalla:

* **Aumente el brillo de la pantalla.** Los hologramas se ven mejor si la pantalla está en su nivel de mayor brillo. Al llevar HoloLens, los botones de brillo están en el lado izquierdo del visor, cerca de la sien.
* **Acerque el visor a los ojos.** Gire el visor hacia abajo hasta la posición más cercana a los ojos.
* **Baje el visor.** Intente mover la almohadilla de la frente hacia abajo, lo que hace que el visor se acerque a la nariz.
* **[Ejecute la calibración de los ojos.](hololens-calibration.md#calibrating-your-hololens-2)** La pantalla usa la distancia interpupilar (IPD) y la mirada para optimizar las imágenes en la pantalla. Si no ejecuta la calibración de los ojos, es posible que la calidad de la imagen empeore. Para ejecutar la calibración de los ojos, vaya a **Configuración** > **Sistema** > **Calibración** > **Run eye calibration (Ejecutar calibración de los ojos)** .
* **Ejecute la calibración de color de la pantalla.** En [Windows Holographic, versión 21H1](hololens-release-notes.md#windows-holographic-version-21h1) y posterior, puede **seleccionar un perfil de color alternativo** para la pantalla de HoloLens 2. Esto puede ayudar a que los colores se vean más precisos, especialmente con niveles de brillo de pantalla inferiores. La calibración de color de la pantalla se puede encontrar en la aplicación **Configuración**, en la página **Sistema > Calibración**.

    > [!NOTE]
    > Dado que esta opción guarda un nuevo perfil de color en el firmware de la pantalla, se trata de una opción por dispositivo (y no única de cada cuenta de usuario).

### <a name="how-to-use-display-color-calibration"></a>Uso de la calibración de color de la pantalla
1. Inicie la aplicación **Configuración** y vaya a **Sistema > Calibración**.
1. En **Calibración de color de la pantalla**, seleccione el botón **Run display color calibration** (Ejecutar calibración de color de la pantalla).
1. Se inicia la experiencia de calibración de color de la pantalla y se le apremia a asegurarse de que el visor está en la posición correcta.
1. Después de avanzar por los cuadros de diálogo de instrucciones, la pantalla se atenúa automáticamente al 30 % de brillo.
    > [!TIP]
    > Si tiene problemas para ver la escena atenuada en el entorno, puede ajustar manualmente el nivel de brillo de HoloLens 2 mediante los botones de brillo del lado izquierdo del dispositivo.
1. Seleccione los botones 1 a 6 para probar al instante cada perfil de color; busque el que sea mejor para su vista (suele ser el perfil que ayuda a que la escena parezca más neutra, con el patrón de escala de grises y los tonos de la máscara con el aspecto esperado).

    ![Escena de calibración de color de la pantalla.](images/color-cal-ui.png)
    
6. Cuando esté satisfecho con el perfil seleccionado, seleccione el botón **Guardar y salir**.
1. Si prefiere no realizar cambios, seleccione el botón **Cancelar y salir** para que se reviertan los cambios.

> [!TIP]
> Estas son algunas recomendaciones útiles que debe tener en cuenta al usar la configuración de calibración de color de la pantalla:
> - Puede volver a ejecutar la calibración de color de la pantalla desde Configuración cada vez que quiera.
> - Si algún usuario del dispositivo ha usado antes la configuración para cambiar perfiles de color, la fecha y hora del cambio más reciente se refleja en la página Configuración.
> - Al volver a ejecutar la calibración de color de la pantalla, se resalta el perfil de color que se guardó anteriormente y el perfil 0 no aparece (ya que el perfil 0 representa el perfil de color original de la pantalla).
> - Si quiere revertir al perfil de color original de la pantalla, puede hacerlo desde la página Configuración (vea [Restablecimiento del perfil de color)](#how-to-reset-color-profile).

### <a name="how-to-reset-color-profile"></a>Restablecimiento del perfil de color

Si no está satisfecho con el perfil de color personalizado guardado en HoloLens 2, puede restaurar el perfil de color original del dispositivo:
1. Inicie la aplicación **Configuración** y vaya a **Sistema > Calibración**.
1. En **Calibración de color de la pantalla**, seleccione el botón **Reset to default color profile** (Restablecer perfil de color predeterminado).
1. Cuando se abra el cuadro de diálogo, si está listo para reiniciar HoloLens 2 y aplicar los cambios, seleccione **Reiniciar**.

### <a name="top-display-color-calibration-known-issues"></a>Principales problemas conocidos de calibración de color de la pantalla

- En la página Configuración, la cadena de estado que indica cuándo se ha cambiado por última vez el perfil de color está desactualizada hasta que vuelve a cargar esa página de Configuración 
    - **Solución alternativa**: seleccione otra página de Configuración y luego vuelva a seleccionar la página Calibración.
- Si HoloLens 2 entra en suspensión mientras se ejecuta la calibración de color de la pantalla, más adelante se reanuda en el ambiente principal y el nivel de brillo de la pantalla sigue atenuado.
- Es posible que tenga que presionar los botones de brillo del lado izquierdo del dispositivo arriba o abajo varias veces para que funcionen según lo previsto.
- La localización no está terminada para todos los mercados

## <a name="faq"></a>Preguntas más frecuentes

### <a name="what-are-the-patterns-that-occasionally-flash-in-the-bottom-corners-of-the-display"></a>¿Qué son los patrones que a veces parpadean en las esquinas inferiores de la pantalla?

A veces, en la pantalla de HoloLens 2 se muestran diferentes patrones en las esquinas inferiores izquierda y derecha. A continuación se muestran algunos ejemplos (GIF animados). Este patrón es parte del funcionamiento normal del dispositivo HoloLens 2 para calibrar la pantalla para una experiencia óptima.

![Patrón bifásico.](./images/DAT-Biphase-Fiducial.gif) ![Patrón GEO](./images/DAT-GEO-Fiducial.gif)

### <a name="why-am-i-unable-to-take-an-accurate-photograph-of-my-hololens-2-display"></a>¿Por qué no puedo hacer una fotografía precisa de la pantalla de HoloLens 2?

La pantalla de HoloLens 2 está diseñada para los ojos humanos. El dispositivo tiene un sistema de corrección del color activo que se adapta a los ojos del usuario. Las cámaras ven los entornos de una forma distinta a la del ojo humano; a continuación se indican algunos factores que pueden dar lugar a incoherencias entre lo que captura una cámara y lo que ve un usuario.

* **Posición del ojo.** La pantalla de HoloLens 2 está diseñada específicamente para la posición de los ojos del usuario. HoloLens 2 emplea tecnología de seguimiento de ojos para adaptarse a la posición de los ojos del usuario. Una cámara colocada en una posición incorrecta por unos pocos milímetros puede dar lugar a distorsiones de imagen. El posicionamiento preciso de una cámara es difícil y tiene que coincidir con la posición exacta y la distancia ocular para los que el dispositivo está realizando la corrección del color.
* **Movimiento ocular.** La pantalla se adapta al movimiento del ojo del usuario para ajustar los colores. Lo que se muestra en la pantalla puede diferir en función de si el usuario está mirando al centro, al borde o a la esquina de la pantalla. Una sola captura de imagen puede, en el mejor de los casos, mostrar solo cómo se ve la pantalla para el eje que coincide con la dirección de una mirada.
* **Vista binocular.** La pantalla de HoloLens 2 está diseñada para verse con ambos ojos. El cerebro se adapta a ver dos imágenes y las une. Las imágenes de una sola pantalla pasan por alto la información de la otra.
* **Tiempo de exposición de la cámara.** El tiempo de exposición de la cámara tiene que ser un múltiplo exacto de 1/120º de segundo. Los fotogramas por segundo de la pantalla de HoloLens son 120 Hz. Debido a la forma en que HoloLens 2 dibuja las imágenes, la captura de un único fotograma tampoco basta para igualar la experiencia visual humana. Al mismo tiempo, si el dispositivo se mueve un poco, incluso movimientos muy pequeños, el sistema reproyecta la imagen en la pantalla para estabilizar los hologramas. La captura de varios fotogramas mientras se evita que HoloLens se mueva normalmente requiere una configuración de laboratorio.
* **Tamaño de apertura de la cámara.** El tamaño de apertura de la cámara debe ser de al menos 3 mm para capturar una imagen precisa. Las cámaras de los teléfonos móviles con aperturas pequeñas integran luz de un área más pequeña que el ojo humano. El dispositivo aplica corrección de color a los patrones observados mediante aperturas mayores. Con aperturas pequeñas, los patrones de uniformidad son más nítidos y permanecen visibles a pesar de las correcciones de color que aplica el sistema.
* **Pupila de entrada de la cámara.** La pupila de entrada de la cámara debe tener como mínimo 3 mm de diámetro para capturar una imagen precisa. De lo contrario, la cámara captura algunos patrones de alta frecuencia no visibles para el ojo. La posición de la pupila de entrada debe estar delante de la cámara y colocada en la distancia ocular para evitar la introducción de anomalías y otras variaciones en la imagen capturada.
* **Posición de la cámara.** Las cámaras que cumplen los requisitos para ver la pantalla de HoloLens 2 son más grandes, con lo que es difícil colocarlas lo suficientemente cerca para observar la imagen con los colores corregidos. Si la cámara se encuentra en la posición incorrecta, la corrección del color puede afectar negativamente a la captura de la pantalla de HoloLens 2.
* **Corrección de la imagen.** Las cámaras digitales típicas y las cámaras de los smartphones aplican una curva de reproducción tonal (TRC) que aumenta el contraste y el color para ofrecer un resultado más enérgico. Al aplicarse a la pantalla de HoloLens 2, esta curva tonal amplifica las no uniformidades.

Por lo demás, las cámaras industriales especializadas puedan capturar imágenes representativas de la pantalla de HoloLens 2. Desafortunadamente, las cámaras de los smartphones, de consumo y profesionales no capturan imágenes que se correspondan con lo que un usuario ve en HoloLens 2.

### <a name="what-does-eye-calibration-do-to-display-image-quality"></a>¿Qué hace la calibración de los ojos a la calidad de la imagen de la pantalla?

La pantalla de HoloLens 2 corrige de forma activa el color de las imágenes en función de la posición de los ojos del usuario. La [calibración de los ojos](hololens-calibration.md) proporciona dos entradas importantes: (1) la distancia interpupilar del usuario (IPD) y (2) la dirección en que está mirando cada ojo. Sin calibración ocular, el sistema aplica de manera predeterminada una posición ocular nominal sin movimiento ocular. La diferencia entre corrección de color activa frente a ninguna corrección depende de la fisiología de cada usuario. Por ejemplo, los usuarios con la misma IPD que el valor predeterminado del sistema ven menos mejoras de corrección de color, mientras que los usuarios con una IPD mucho más ancha o estrecha que el valor predeterminado del sistema ven más cambios en la imagen de la pantalla.

Sepa que una nueva característica de [Windows Holographic, versión 20H2](hololens-release-notes.md#windows-holographic-version-20h2) va a empezar a [detectar automáticamente la posición de los ojos](hololens-calibration.md#auto-eye-position-support). 

### <a name="what-are-the-display-differences-between-hololens-1st-gen-and-hololens-2"></a>¿Cuáles son las diferencias entre HoloLens (primera generación) y HoloLens 2?

Algunas de las principales peticiones de los clientes a Microsoft después de haber usado HoloLens 1 fueron (1) aumentar el campo de visión y (2) aumentar el brillo. Los desarrollos tecnológicos han permitido a Microsoft producir guías de onda que doblan el área del campo de visión y producen proyectores de luz con una pantalla que es hasta tres veces más brillante. El hardware establece la base de referencia de un trío de equilibrios para la calidad de la imagen de la pantalla: (1) campo de visión, (2) brillo y (3) uniformidad de color. El continuo avance tecnológico permite mejorar todas las áreas sin sacrificar ninguna. Mientras tanto, la tecnología existente establece los límites disponibles de estos equilibrios.

### <a name="what-improvements-are-coming-that-will-improve-hololens-2-image-quality"></a>¿Cuáles son las próximas mejoras para la calidad de la imagen de HoloLens 2?

Aunque se están llevando a cabo numerosas investigaciones para mejorar la calidad de la imagen, se espera que haya mejoras en las siguientes áreas en próximas actualizaciones:

* **Posición del ojo automática.** Esta característica va a permitir que los procedimientos de calibración de los ojos se realicen en segundo plano. Los usuarios ya no van a tener que realizar la calibración ocular para que funcione la corrección del color activa. Simplemente va a funcionar.
* **Mejoras en la calibración de color.** Esta actualización se centra en los valores de color de los colores más oscuros (por ejemplo, gris oscuro). Ahora mismo, los colores más tenues adoptan un tono rojizo. Este problema también se produce cuando toda la pantalla está atenuada: toda ella adopta colores rojizos. Este problema se debe a que hay demasiada actividad en el canal del color rojo de estos colores más oscuros. Se han caracterizado las curvas de iluminación láser en estos colores más tenues y se está trabajando para ofrecer un procedimiento de calibración de usuario. El resultado será más precisión de color en el espectro de brillo. No cambiará el aspecto de los fondos blancos con el brillo al máximo. Se sigue recomendando el uso de patrones de diseño en modo oscuro en las aplicaciones.
* **Modo de lectura.** Es posible que los desarrolladores de aplicaciones compensen el campo de visión de la pantalla para lograr una mayor resolución angular. Los desarrolladores de aplicaciones pueden invalidar la matriz de proyección para que el contenido se represente en la resolución de dibujo de la pantalla. Esta característica se traduce en un 30 % de reducción del campo visual y un aumento correspondiente de la resolución angular. Se está trabajando para incorporar esta capacidad a [Mixed Reality Toolkit](https://github.com/Microsoft/MixedRealityToolkit-Unity). Cuando esté disponible, el modo de lectura funcionará en cualquier sistema operativo de HoloLens 2 y no dependerá de las actualizaciones del sistema operativo.

Las actualizaciones del sistema operativo se entregan automáticamente. También puede probar versiones anteriores de mejoras de software con el programa de versión preliminar de Insider.

### <a name="what-guidance-is-available-for-developers-to-apply-dark-mode-design-principles"></a>¿Qué instrucciones hay disponibles para que los desarrolladores apliquen los principios de diseño en modo oscuro?

Los usuarios obtienen la mejor experiencia cuando evitan los fondos blancos. El modo oscuro es un principio de diseño empleado por las aplicaciones para usar fondos de color negro u oscuro. El valor predeterminado de configuración del sistema es el modo oscuro y se puede ajustar si se va a **Configuración** > **Sistema** > **Color**.

Se recomienda a los desarrolladores seguir las instrucciones de diseño en modo oscuro:

* [Instrucciones de diseño para desarrolladores de pantallas de HoloLens](/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [Tamaños de fuente recomendados](/windows/mixed-reality/typography#recommended-font-size)

Si un holograma requiere un fondo blanco, mantenga el holograma en un tamaño más pequeño que el campo de visión completo de la pantalla. Este tamaño permite a los usuarios colocar el holograma en el centro de la pantalla.

### <a name="how-do-you-clean-a-hololens-2-display"></a>¿Cómo se limpia una pantalla de HoloLens 2?

Use un paño de microfibra para limpiar suavemente el visor. Para desinfectar el visor, use alcohol isopropílico al 70 % para humedecer suavemente un paño y luego limpie el visor. Lea las instrucciones completas en [Preguntas más frecuentes sobre la limpieza de HoloLens 2](hololens2-maintenance.md).
