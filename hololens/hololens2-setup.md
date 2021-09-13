---
title: Preparar un nuevo HoloLens 2
description: Obtenga información sobre cómo configurar y ajustar un dispositivo HoloLens 2 por primera vez, incluidas sugerencias sobre salud y seguridad y guías de hardware.
keywords: hololens, luces, ajuste, comodidad, piezas
ms.assetid: 02692dcf-aa22-4d1e-bd00-f89f51048e32
ms.date: 9/17/2019
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 77c061c53806e7410d73ecf3aaa20d74c217ea33
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034527"
---
# <a name="get-your-hololens-2-ready-to-use"></a>Preparación de HoloLens 2 para su uso

Los siguientes procedimientos le ayudarán a configurar un HoloLens 2 por primera vez.

## <a name="charge-your-hololens"></a>Cargar el HoloLens

Conecte la fuente de alimentación al puerto de carga usando el cable USB-C (incluido). Conecte la fuente de alimentación a una toma de corriente. La fuente de alimentación y el cable de USB C a USB C que se incluyen con el dispositivo son la mejor forma de cargar el HoloLens 2. El cargador suministra 18 W de potencia (9 V a 2 A). Con el cargador de pared suministrado, los dispositivos HoloLens 2 pueden realizar una carga completa de la batería en menos de 65 minutos cuando el dispositivo está en modo de espera.

La velocidad y la tasa de carga pueden variar en función del entorno en el que se ejecute el dispositivo.

- Cuando el dispositivo se está cargando, se ilumina el indicador de la batería para señalar el nivel de carga.  La última luz parpadea para indicar que se está cargando.
- Cuando el HoloLens está activado, el indicador de la batería muestra el nivel de la batería en incrementos.
- Si solo hay encendida una de las cinco luces, el nivel de la batería está por debajo del 20 por ciento.
- Si el nivel de la batería es demasiado bajo y se intenta encender el dispositivo, una luz parpadeará brevemente y después se apagará.

En caso necesario, [aquí](hololens2-charging.md#charging-the-device) puede consultar la información completa sobre cómo cargar dispositivos. 

## <a name="adjust-fit"></a>Regular el ajuste

Colóquese el HoloLens 2 en la cabeza. Si lleva gafas, no hace falta que se las quite.  Acomódese correctamente la almohadilla de la frente y colóquese la banda trasera en la parte central de la cabeza.

Si es necesario, extienda la banda de la cabeza girando la rueda de regulación y, a continuación, afloje la correa.

![Ajuste y regulación de HoloLens 2.](images/hololens2-fit.png)

### <a name="attach-and-detach-the-overhead-strap"></a>Fijar y quitar la correa

Aunque no hace falta ponerse la correa, puede hacer que resulte más cómodo llevar el HoloLens 2 durante períodos prolongados de uso.

Para quitar la parte delantera de la correa, desenganche la correa y deslícela por el cierre retráctil de la almohadilla de la frente. Para volver a ponerla, tire del cierre y deslice de nuevo la correa por él.

Para quitar la parte posterior de la correa, presione el botón situado debajo de cada lengüeta de contacto y tire con suavidad. Para volver a colocarla, presione las lengüetas de contacto hasta que se introduzcan de nuevo en las ranuras (sonará un clic).

![Colocar o quitar la correa de la cabeza de HoloLens 2.](images/hololens2-headstrap.png)

## <a name="turn-on-the-hololens-2"></a>Encender el HoloLens 2

Para encender el HoloLens 2, presione el botón de encendido.  Las luces LED situadas debajo del botón de encendido muestran el nivel de la batería.

> [!NOTE]
> Para encender el HoloLens 2 por primera vez, una vez desembalado, mantenga presionado el botón de encendido durante un mínimo de cuatro segundos. La próxima vez que encienda el HoloLens 2, se iniciará después de presionar brevemente el botón de encendido.

### <a name="power-button-actions-for-different-power-transitions"></a>Acciones del botón de encendido para diferentes transiciones de energía

| Para hacer esto | Ejecutar esta acción | HoloLens 2 hará esto |
| - | - | - |
| Encender el dispositivo | Presionar una sola vez el botón. | Las cinco luces se encienden y luego cambian para indicar el nivel de la batería. Después de cuatro segundos, se reproduce un sonido. |
| Suspender el dispositivo | Presionar una sola vez el botón. | Las cinco luces se encienden y van apagándose una a una. Una vez que se apagan las luces, se reproduce un sonido y se muestra "Adiós" en la pantalla. |
| Reactivar un dispositivo suspendido | Presionar una sola vez el botón. | Las cinco luces se encienden y luego cambian para indicar el nivel de la batería. Se reproduce un sonido inmediatamente. |
| Apagar el dispositivo | Mantener presionado el botón durante cinco segundos. |  Las cinco luces se encienden y van apagándose una a una. Una vez que se apagan las luces, se reproduce un sonido y se muestra "Adiós" en la pantalla. |
| Forzar el reinicio del dispositivo si no responde | Mantener presionado el botón durante diez segundos. | Las cinco luces se encienden y van apagándose una a una. Una vez que se apagan las luces, |

## <a name="hololens-behavior-reference"></a>Referencia de comportamientos de HoloLens

¿No sabe con certeza qué significan los indicadores luminosos del HoloLens? ¿Quiere saber cómo se debe comportar el HoloLens mientras se carga?  Aquí encontrarás ayuda.

### <a name="charging-behavior"></a>Comportamiento de carga

| Estado del dispositivo | Acción | HoloLens 2 hará esto |
| - | - | - |
| Apagado | Conectar el cable USB | El dispositivo pasa a estar ENCENDIDO; las luces indicadoras muestran el nivel de la batería y el dispositivo comienza a cargarse.
| ACTIVAR | Quitar el cable USB | El dispositivo deja de cargarse.
| ACTIVAR | Conectar el cable USB | El dispositivo comienza a cargarse.
| SUSPENDIDO | Conectar el cable USB | El dispositivo comienza a cargarse.
| SUSPENDIDO | Desconectar el cable USB | El dispositivo deja de cargarse.
| ENCENDIDO con el cable USB conectado | Apagar el dispositivo | El dispositivo pasa a estar ENCENDIDO; las luces indicadoras muestran el nivel de la batería y el dispositivo comienza a cargarse. |

### <a name="lights-that-indicate-the-battery-level"></a>Luces que indican el nivel de la batería

| Número de luces | Nivel de la batería |
| - | - |
| Cuatro luces fijas y otra que se va encendiendo y apagando | Entre un 100 y un 81 % (totalmente cargado) |
| Tres luces fijas y otra que se va encendiendo y apagando | Entre un 80 y un 61 % |
| Dos luces fijas y otra que se va encendiendo y apagando | Entre un 60 y un 41 % |
| Una luz fija y otra que se va encendiendo y apagando | Entre un 40 y un 21 % |
| Una luz que se va encendiendo y apagando | Entre un 20 y un 5 % o menos (nivel crítico) |

### <a name="sleep-behavior"></a>Comportamiento de suspensión

| Estado del dispositivo | Acción | HoloLens 2 hará esto |
| - | - | - |
| ACTIVAR | Presionar una sola vez el botón de encendido | El dispositivo pasa a estar SUSPENDIDO y se apagan todas las luces indicadoras. |
| ACTIVAR | Sin movimiento durante tres minutos | El dispositivo pasa a estar SUSPENDIDO y se apagan todas las luces indicadoras. |
| SUSPENDIDO | Presionar una sola vez el botón de encendido | El dispositivo pasa a estar ENCENDIDO y se encienden las luces indicadoras. |

### <a name="lights-to-indicate-problems"></a>Luces para indicar problemas

| Si hace esto | Las luces hacen esto | Significa esto |
| - | - | - |
| Presionar el botón de encendido. | Una luz parpadea cinco veces y, a continuación, se apaga. | El nivel de la batería del HoloLens es crítico. Cargue el dispositivo. |
| Presionar el botón de encendido. | Las cinco luces parpadean cinco veces y luego se apagan. |  HoloLens no puede iniciarse correctamente y se encuentra en un estado de error. [Vuelva a instalar el sistema operativo](hololens-recovery.md) para recuperar el dispositivo. |
| Presionar el botón de encendido. | Las luces 1.ª, 3.ª y 5.ª parpadean juntas de manera continua. |  Es posible que se haya producido un error de hardware en el HoloLens. Póngase en contacto con el [soporte](https://support.microsoft.com/en-us/supportforbusiness/productselection?sapid=3ec35c62-022f-466b-3a1e-dbbb7b9a55fb). |

## <a name="safety-and-comfort"></a>Seguridad y comodidad

### <a name="use-hololens-in-safe-surroundings"></a>Use el HoloLens en un entorno seguro

Use el HoloLens en un espacio seguro, sin obstrucciones ni posibilidad de tropezarse. No lo use cuando necesite un campo de visión amplio y no pueda prestar toda su atención, por ejemplo, conduciendo o realizando otras actividades potencialmente peligrosas.

### <a name="stay-comfortable"></a>Mantenga la comodidad

Asegúrese de que las primeras sesiones con el HoloLens no sean muy largas y haga pausas. Si experimenta molestias, deje de usarlo y descanse hasta que se sienta mejor. Por ejemplo, puede experimentar temporalmente náuseas, mareo, vértigo, desorientación, dolor de cabeza, cansancio y fatiga o sequedad ocular.

Consulte las [instrucciones y advertencias de seguridad del producto](https://support.microsoft.com/help/4558037/product-safety-warnings-and-instructions).

> [!div class="nextstepaction"]
> [Configuración de HoloLens 2](hololens2-start.md)
