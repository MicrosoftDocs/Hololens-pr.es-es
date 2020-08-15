---
title: Pantallas de HoloLens 2
description: Expectativas de las pantallas de HoloLens 2. Instrucciones para la configuración de las pantallas para obtener la mejor calidad de imagen.
author: BrandonBray
ms.author: branbray
ms.date: 8/13/2020
ms.topic: article
keywords: pantalla, calibración, comodidad, elementos visuales, calidad, ipd
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: bf0f293fac531045e50bee9a9dd153eb9dd2b377
ms.sourcegitcommit: bdbaed42dd9ecbd0ed9517de2e98a0465f584c1d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "10929925"
---
# Pantalla de HoloLens 2

La pantalla de HoloLens 2 es una combinación de guías de onda y proyectores de luz. Los usuarios ven a través de las guías de onda (las lentes dentro del visor) cuando usan el casco. Los proyectores de luz se encuentra dentro del contenedor por encima de la frente. HoloLens 2 usa luz láser para iluminar la pantalla.

## Solución de problemas

Para HoloLens 2, sigue los pasos a continuación para asegurarte de que se muestre la calidad visual más alta de los hologramas presentados:

* **Aumenta el brillo de la pantalla.** Los hologramas se ven mejor cuando la pantalla está en su nivel de mayor brillo.
* **Acerca el visor a tus ojos.** Gira el visor hacia abajo hasta la posición más cercana a tus ojos.
* **Baja el visor.** Intenta mover la almohadilla de la frente hacia abajo, lo que hará que el visor se acerque a tu nariz.
* **Ejecuta la calibración ocular.** La pantalla usa tu distancia interpupilar (IPD) y tu mirada para optimizar las imágenes en la pantalla. Si no ejecutas la calibración ocular, es posible que la calidad de la imagen empeore. Para ejecutar la calibración ocular, vaya a **Configuración** ➔ **Sistema** ➔ **Calibración** ➔ **Ejecutar calibración ocular**.

## Preguntas más frecuentes

### ¿Cuáles son los patrones que en ocasiones parpadean en las esquinas inferiores de la pantalla?

En ocasiones, en la pantalla de HoloLens 2 se mostrarán diferentes patrones en la esquina inferior izquierda y derecha. A continuación se muestran algunos ejemplos (GIF animados). Este patrón forma parte del funcionamiento normal de su dispositivo HoloLens 2 para calibrar la pantalla y obtener una experiencia óptima.

![Patrón bifásico](./images/DAT-Biphase-Fiducial.gif) ![Patrón GEO](./images/DAT-GEO-Fiducial.gif)

### ¿Por qué no puedo hacer una fotografía precisa de la pantalla de HoloLens 2?

La pantalla de HoloLens 2 está diseñada para que la vean los ojos humanos. El dispositivo tiene un sistema de corrección del color activo que se adapta a los ojos del usuario. En comparación con el ojo humano, las cámaras ven los entornos de otra forma y, a continuación, se muestran algunos factores que pueden afectar cualquier incoherencia entre lo que captura una cámara y lo que ve un usuario.

* **Posición del ojo.** La pantalla de HoloLens 2 está diseñada específicamente para la posición de los ojos del usuario. HoloLens 2 emplea tecnología de seguimiento de ojos para adaptarse a la posición de los ojos del usuario. Una cámara que está colocada en una posición incorrecta por unos pocos milímetros puede dar lugar a distorsiones de imagen. El posicionamiento exacto de una cámara es difícil y necesita coincidir con la ubicación exacta y el alivio del ojo para los que el dispositivo está realiza la corrección del color.
* **Movimiento ocular.** La pantalla se adapta al movimiento del ojo del usuario para ajustar los colores. Lo que se muestra en la pantalla puede diferir según si el usuario está mirando al centro, al borde o a la esquina de la pantalla. Una sola captura de imagen puede, en el mejor de los casos, mostrar solo cómo se ve la pantalla para el eje que coincide con la dirección de una mirada.
* **Vista binocular.** La pantalla de HoloLens 2 está diseñada para que se la vea con ambos ojos. El cerebro se adapta a ver dos imágenes y las junta. Las imágenes de una sola pantalla ignoran la información de la otra pantalla.
* **Tiempo de exposición de la cámara.** El tiempo de exposición de la cámara tiene que ser un múltiplo exacto de 1/120 de segundo. Los fotogramas por de la pantalla de HoloLens es de 120 Hz. Debido a la forma en que HoloLens 2 dibuja las imágenes, capturar un único marco tampoco es suficiente para igualar la experiencia visual humana. Al mismo tiempo, si el dispositivo se mueve un poco, incluso movimientos muy pequeños, el sistema reproyecta la imagen en la pantalla para estabilizar los hologramas. La captura de varios marcos, a la vez que se mantiene a HoloLens sin moverse, generalmente requiere una configuración de laboratorio.
* **Tamaño de abertura de la cámara.** El tamaño de abertura de la cámara debe ser de al menos 3 mm para capturar una imagen precisa. Las cámaras de los teléfonos celulares con aberturas pequeñas integran la luz de un área más pequeña que la del ojo humano. El dispositivo aplica la corrección del color para los patrones que observan las aberturas mayores. Con aberturas pequeñas, los patrones de uniformidad son más nítidos y permanecen visibles a pesar de las correcciones del color que aplica el sistema.
* **Pupila de entrada de la cámara.** La pupila de entrada de la cámara debe tener como mínimo 3 mm de diámetro para capturar una imagen precisa. En caso contrario, la cámara captura algunos patrones de alta frecuencia no visibles para el ojo. La posición de la pupila de entrada debe estar frente a la cámara y a la distancia de alivio del ojo para evitar la introducción de anormalidades y otras variaciones en la imagen capturada.
* **La posición de la cámara.** Las cámaras que cumplen los requisitos para ver la pantalla de HoloLens 2 son más grandes y es difícil posicionar la cámara lo suficientemente cerca a la pantalla de HoloLens 2 para observar la imagen con los colores corregidos. Si la cámara se encuentra en un sitio incorrecto, la corrección del color puede afectar negativamente la captura de la pantalla de HoloLens 2.
* **Corrección de la imagen.** Las cámaras digitales y las cámaras de los smartphones típicas aplican una curva de reproducción tonal (TRC) que aumenta el contraste y color para ofrecer un resultado más ágil. Al aplicarse a la pantalla de HoloLens 2, esta curva tonal amplifica las no uniformidades.

Por lo demás, aún es posible que las cámaras industriales especializadas puedan capturar imágenes representativas de la pantalla de HoloLens 2. Desafortunadamente, las cámaras de los smartphones, usuarios y profesionales no capturan imágenes que se corresponden con lo que un usuario ve en HoloLens 2.

### ¿Qué hace la calibración ocular para mostrar la calidad de la imagen?

La pantalla de HoloLens 2 corrige los colores de forma activa en función de la posición de los ojos del usuario. [La calibración ocular](hololens-calibration.md) ofrece dos entradas importantes: (1) la distancia interpupilar del usuario (IPD) y (2) la dirección a la que está mirando cada ojo. Sin la calibración ocular, el sistema usa de forma predeterminada una posición ocular nominal sin movimiento ocular. La diferencia entre la corrección del color activa frente a ninguna corrección depende de la fisiología de cada usuario. Por ejemplo, los usuarios que tengan el mismo IPD que el predeterminado por el sistema, verán menos mejoras en la corrección del color. Mientras que los usuarios que tienen un valor de IPD mucho más alto o más bajo que el predeterminado por el sistema, verán más cambios en la imagen que se muestra.

Tenga en cuenta que una nueva característica disponible en una actualización futura del sistema operativo comenzará a [detectar automáticamente la posición del ojo](hololens-insider.md#auto-eye-position-support). Para probar esta característica ahora, los usuarios pueden inscribirse en la [versión preliminar de Insider](hololens-insider.md).

### ¿Cuáles son las diferencias en la pantalla de HoloLens (1ª gen.) y la pantalla de HoloLens 2?

Entre las principales solicitudes que los clientes dieron a Microsoft luego de haber usado HoloLens 1 fue (1) aumentar el campo de visión y (2) aumentar el brillo. Los desarrollos tecnológicos permitían a Microsoft producir guías de onda que doblaban el área del campo de visión y producían proyectores de luz con una pantalla que era hasta tres veces más brillante. El hardware define la línea base de un trío de compensaciones para la calidad de la imagen de pantalla: (1) campo de visión, (2) brillo y (3) uniformidad de color. El continuo avance tecnológico permite mejorar todas las áreas sin sacrificar ninguna otra. Mientras tanto, la tecnología existente define los límites disponibles para estas compensaciones.

### ¿Qué mejoras se aplicarán para mejorar la calidad de imagen de HoloLens 2?

Aunque se están llevando a cabo numerosas investigaciones para mejorar la calidad de la imagen, se espera que las mejoras en las siguientes áreas lleguen en las próximas actualizaciones:

* **Posición del ojo automática.** Esta característica permitirá que los procedimientos de calibración ocular se realicen en segundo plano. Los usuarios ya no tendrán que ejecutar la calibración ocular para que funcione la corrección del color activa. En su lugar, solo funcionará.
* **Mejoras en la calibración de color.** Esta actualización se centra en los valores de color de los colores más oscuros (por ejemplo, gris oscuro). Ahora mismo, los colores más tenues seleccionan un tono rojo. Este problema también se produce cuando la pantalla completa está atenuada. En estos casos, la pantalla completa selecciona colores rojos. Este problema es resultado de demasiada actividad en el canal de color rojo para estos colores más oscuros. Hemos caracterizado las curvas de iluminación láser en estos colores más tenues y estamos trabajando para ofrecer un procedimiento de calibración del usuario. El resultado será más precisión de color en el espectro de brillo. No cambiará la apariencia de los fondos blancos con el brillo al máximo. Seguimos recomendando el uso de patrones de diseño en modo oscuro en las aplicaciones.
* **Modo de lectura.** Es posible que los desarrolladores de aplicaciones compensen el campo de visión de la pantalla para lograr una resolución angular mayor. Los desarrolladores de aplicaciones pueden invalidar la matriz de proyección para que el contenido se represente en la resolución de dibujo de la pantalla. Esta característica da como resultado un 30% de reducción en el campo de visión y un aumento correspondiente en la resolución angular. Estamos trabajando para introducir esta capacidad en el kit de herramientas de realidad mixta. Cuando esté disponible, el modo de lectura funcionará en cualquier sistema operativo de HoloLens 2. No dependerá de una actualización del sistema operativo.

Las actualizaciones del sistema operativo se entregan automáticamente. También puede probar versiones tempranas de mejoras del software con el programa de versión preliminar de Insider.

### ¿Qué instrucciones están disponibles para que los desarrolladores apliquen los principios de diseño en modo oscuro?

Microsoft está preparando instrucciones para desarrolladores sobre los principios de diseño en modo oscuro. Las instrucciones estarán disponibles próximamente en la [documentación para desarrolladores](https://docs.microsoft.com/windows/mixed-reality/). Un resumen de los consejos:

* Usar colores oscuros para el fondo de la interfaz de usuario
* Usar espesores de fuente negrita o seminegrita.
* Usar el material HolographicBackplate del kit de herramientas de realidad mixta

### ¿Cómo se limpia la pantalla de HoloLens 2?

Use un paño de microfibra para limpiar suavemente el visor. Para desinfectar el visor, use alcohol isopropílico al 70% para humedecer suavemente un paño y, a continuación, limpie el visor. Lea las instrucciones completas en [Preguntas frecuentes sobre cómo limpiar HoloLens 2](hololens2-maintenance.md).
