---
title: Preparar un nuevo HoloLens 2
description: Esta guía explica la configuración por primera vez y la guía de hardware.
keywords: hololens, lights, fit, comfort, parts, luces, comodidad, partes, ajuste
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
ms.openlocfilehash: b2d95839ff394d61eec8f5c76baf9a151855794a
ms.sourcegitcommit: e3056a433aeebb8bc45dc3f6db9a75f212fdf53b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2020
ms.locfileid: "10996408"
---
# Obtener tu HoloLens 2 listo para usar

Los procedimientos siguientes te ayudarán a configurar un HoloLens 2 por primera vez.

## Cargar tu HoloLens

Conecta la fuente de alimentación al puerto de carga con el cable USB-C (incluido). Conecta la fuente de alimentación a una toma de corriente. La fuente de alimentación y el cable USB C a C incluidos con el dispositivo son la mejor forma de cargar tu HoloLens 2. El cargador suministra 18W de potencia (9V a 2A).

La velocidad y la tasa de carga pueden variar en función del entorno en el que se ejecute el dispositivo.

- Cuando se cargue el dispositivo, se iluminará el indicador de la batería para señalar el nivel de carga actual.  La última luz aparecerá y desaparecerá gradualmente para indicar la carga activa.
- Cuando HoloLens está activado, el indicador de la batería muestra el nivel de la batería en incrementos.
- Cuando solo está encendida una de las cinco luces, significa que el nivel de batería se encuentra por debajo del 20 por ciento.
- Si el nivel de la batería es críticamente bajo e intentas activar el dispositivo, una luz parpadeará brevemente y después se apagará.

Si necesita más información, [aquí se encuentran todos los detalles sobre la carga de dispositivos](hololens-recovery.md#charge-the-device). 

## Realizar ajuste

Coloca HoloLens 2 en tu cabeza. Si llevas puestas gafas, déjatelas puestas.  La almohadilla de la frente debe estar situada cómodamente sobre tu frente y la banda de atrás debe estar colocada en el parte central de atrás de la cabeza.

Si es necesario, extiende la banda de la cabeza girando la rueda de ajuste y, a continuación, afloja la correa.

![Adaptación y ajustes de HoloLens 2](images/hololens2-fit.png)

### Colocar y quitar la correa

No es necesaria la correa, pero puede hacer que sea más cómodo llevar puesto HoloLens 2 durante períodos prolongados de uso.

Para quitar la parte delantera de la correa, desenganche la correa y colócala en el cierre retráctil de la almohadilla de la frente. Para volver a ponerla, tire del cierre y deslice la correa de nuevo hacia su posición.

Para retirar la parte posterior de la correa, presiona el botón situado debajo de cada lengüeta de contacto y tira con suavidad. Para volver a colocarla, empuja de las lengüetas de contacto hacia atrás en las ranuras hasta que hagan clic.

![Colocar o quitar la correa de la cabeza de HoloLens 2](images/hololens2-headstrap.png)

## Encender HoloLens 2

Para encender HoloLens 2, presiona el botón de encendido.  Las luces LED situadas debajo del botón de encendido muestran el nivel de la batería.

> [!NOTE]
> Para encender HoloLens 2 por primera vez, después de desembalarlo, mantén presionado el botón de encendido durante un mínimo de 4 segundos para activarlo. La próxima vez que enciendas HoloLens 2, se iniciará después de presionar brevemente el botón de encendido.

### Acciones de botón de encendido para diferentes transiciones de energía

| Para | Realiza esta acción | HoloLens 2 hará esto |
| - | - | - |
| Para encender | Presionar un solo botón. | Las cinco luces se encienden y luego cambian para indicar el nivel de la batería. Después de cuatro segundos, se reproduce un sonido. |
| Para suspensión | Presionar un solo botón. | Las cinco luces se encienden y van apagándose una a una. Después de apagar las luces, se reproduce un sonido y la pantalla muestra "Adiós". |
| Para reactivar desde suspensión | Presionar un solo botón. | Las cinco luces se encienden y luego cambian para indicar el nivel de la batería. Un sonido se reproduce inmediatamente. |
| Para desactivar | Presionar durante 5segundos. |  Las cinco luces se encienden y se van apagando gradualmente de una en una. Después de que se apaguen las luces, se reproduce un sonido y la pantalla muestra "Adiós". |
| Para forzar el reinicio de Hololens si no responde | Mantener presionado durante 10segundos. | Las cinco luces se encienden y van apagándose una a una. Después de apagar las luces. |

## Referencia de comportamientos de HoloLens

¿No estás seguro de qué significan los indicadores luminosos de tu HoloLens? ¿Quieres saber cómo se debe comportar HoloLens mientras se carga?  Aquí encontrarás ayuda.

### Comportamiento de carga

| Estado del dispositivo | Acción | HoloLens 2 lo hará |
| - | - | - |
| APAGADO | Cable USB enchufable | El dispositivo pasa a estar ENCENDIDO, con luces indicadoras que muestran el nivel de la batería y el dispositivo comienza a cargarse.
| ENCENDIDO | Quitar cable USB | El dispositivo deja de cargarse
| ENCENDIDO | Cable USB enchufable | El dispositivo comienza a cargarse
| SUSPENSIÓN | Cable USB enchufable | El dispositivo comienza a cargarse
| SUSPENSIÓN | Quitar cable USB | El dispositivo deja de cargarse
| ENCENDIDO con cable USB enchufado | Apagar el dispositivo | El dispositivo cambia a ENCENDIDO con luces indicadoras que muestran el nivel de batería y el dispositivo empezará a cargarse |

### Luces que indican el nivel de la batería

| Número de luces | Nivel de la batería |
| - | - |
| Cuatro luces continuas, una luz que enciende y se apaga progresivamente | Entre 100% y 81% (totalmente cargado) |
| Tres luces continuas, una luz que se enciende y se apaga progresivamente | Entre 80% y 61% |
| Dos luces continuas, una luz que se enciende y se apaga progresivamente | Entre 60% y 41% |
| Una luz continua, una luz que se enciende y se apaga progresivamente | Entre 40% y 21% |
| Una luz que se enciende y se apaga progresivamente | Entre el 20 % y el 5 %, o menos (batería crítica) |

### Comportamiento de suspensión

| Estado del dispositivo | Acción | HoloLens 2 hará esto |
| - | - | - |
| ENCENDIDO | Presionar una vez el botón Inicio/Apagado | El dispositivo pasa a estar en SUSPENSIÓN y apaga todas las luces indicadoras |
| ENCENDIDO | Sin movimiento durante 3 minutos | El dispositivo pasa a SUSPENSIÓN y desactiva todas las luces indicadoras |
| SUSPENSIÓN | Presionar una vez el botón Inicio/Apagado | El dispositivo pasa a ENCENDIDO y enciende las luces indicadoras |

### Luces para indicar problemas

| Si haces esto | Las luces hacen esto | Significa esto |
| - | - | - |
| Presiona el botón de encendido. | Una luz parpadea cinco veces y, a continuación, se apaga. | La batería de HoloLens es muy baja. Carga tu HoloLens. |
| Presiona el botón de encendido. | Las cinco luces parpadean cinco veces y luego se apagan. |  HoloLens no puede iniciarse correctamente y se encuentra en un estado de error. [Reinstala el sistema operativo](hololens-recovery.md) para recuperar el dispositivo. |
| Presiona el botón de encendido. | Las luces 1.ª, 3.ª y 5.ª parpadean juntas de manera continua. |  Es posible que se haya producido un error de hardware en HoloLens. Contactar con el [soporte técnico](https://support.microsoft.com/en-us/supportforbusiness/productselection?sapid=3ec35c62-022f-466b-3a1e-dbbb7b9a55fb). |

## Seguridad y comodidad

### Usar HoloLens en un entorno seguro

Usa tu HoloLens en un espacio seguro que no tenga obstrucciones y que no presente riesgos. No lo uses cuando necesites un campo de visión amplio y no puedas prestar toda tu atención, como cuando estés conduciendo un vehículo o realizando otras actividades potencialmente peligrosas.

### Mantente cómodo

Mantén breves tus primeras sesiones con HoloLens y asegúrate de tomar descansos. Si te sientes incómodo, detenlo y descansa hasta que te sientas mejor. Esto puede incluir molestias temporales, como náuseas, mareo, confusión, desorientación, dolor de cabeza, fatiga, cansancio visual o sequedad visual.

Consulta [Instrucciones y advertencias de seguridad del producto](https://support.microsoft.com/help/4558037/product-safety-warnings-and-instructions).

> [!div class="nextstepaction"]
> [Iniciar y configurar tu HoloLens 2](hololens2-start.md)
