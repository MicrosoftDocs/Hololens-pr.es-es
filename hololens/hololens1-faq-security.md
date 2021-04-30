---
title: Preguntas de seguridad más frecuentes
description: Manténgase al día con las preguntas de seguridad más frecuentes y las respuestas sobre los dispositivos de realidad mixta de HoloLens.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: pawinfie
ms.author: pawinfie
ms.date: 02/19/2020
keywords: hololens, Windows Mixed Reality, seguridad
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: bradke
ms.openlocfilehash: 371c901acbf23feecfe98e72569caeaf63e2198f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310261"
---
# <a name="frequently-asked-hololens-1st-gen-security-questions"></a>Preguntas de seguridad de HoloLens (1.ª generación) más frecuentes

1. **¿Qué nivel de protección de datos ofrece HoloLens 1?**
    1. Consulte Cifrado de BitLocker de [HoloLens (1.ª generación)](hololens1-encryption.md)
1. **¿Qué tipo de conexión inalámbrica se usa?**
    1. 802.11ac y Bluetooth 4.1 LE
1. **¿Qué tipo de arquitectura se incorpora?  Por ejemplo: ¿apuntar a punto, malla o algo más?**
    1. Wi-Fi se puede usar en modo de infraestructura para comunicarse con otros puntos de acceso inalámbrico.
    1. Bluetooth se puede usar para hablar del mismo nivel entre varios HoloLens si la aplicación de los clientes lo admite o con otros dispositivos Bluetooth.
1. **¿Qué es el identificador de FCC?**
    1. C3K1688
1. **¿En qué intervalo de frecuencia y canales funciona el dispositivo y es configurable?**
    1. Wi-Fi: el intervalo de frecuencia no es configurable por el usuario y depende del país de uso. En estados Wi-Fi usa canales de 2,4 GHz (1-11) y de 5 GHz (36-64, 100-165).
    1. Bluetooth: Bluetooth usa el intervalo estándar de 2,4-2,48 GHz.
1. **¿Puede el dispositivo permitir o bloquear frecuencias específicas?**
    1. El usuario o el dispositivo no puede controlarlo.
1. **¿Cuál es el nivel de potencia para transmitir y recibir? ¿Es ajustable? ¿Cuál es el intervalo de operación?**
    1. Nuestros estándares de pruebas de emisión se pueden [encontrar aquí.](https://fccid.io/C3K1688) La gama de operaciones depende en gran medida del punto de acceso y el entorno, pero es aproximadamente equivalente a otros teléfonos, tabletas o equipos de alta calidad.
1. **¿Cuál es el ciclo de servicio/duración del funcionamiento normal?**
    1. De 2 a 3 horas de uso activo y hasta dos semanas de tiempo de espera
    1. La duración de la batería no está disponible.
1. **¿Qué es el comportamiento de transmisión y recepción cuando una herramienta no está dentro del intervalo?**
    1. La transmisión/recepción de HoloLens sigue el patrón estándar de Wi-Fi/Bluetooth. En el borde de su intervalo, probablemente observará que la entrada se está desconectando por completo, pero después de volver al intervalo, debería volver a conectarse rápidamente.
1. **¿Qué es la densidad de implementación por pie cuadrado?**
    1. Esto depende de la infraestructura de red.
1. **¿Puede el dispositivo usar la infraestructura como cliente?**
    1. Yes
1. **¿Qué protocolo se usa?**
    1. HoloLens no usa ningún protocolo propietario
1. **Frecuencia de actualización del sistema operativo: ¿cuál es la frecuencia de las actualizaciones del sistema operativo para hl?  ¿Hay una programación establecida?  Microsoft publica revisiones de seguridad según sea necesario, etc.**
    1. Microsoft proporciona actualizaciones del sistema operativo a HoloLens exactamente de la misma manera que se hace para Windows 10. Normalmente hay dos actualizaciones principales al año, una en la primavera y otra en caída. Como HoloLens es un dispositivo Windows, el concepto de actualización es el mismo que con cualquier otro dispositivo Windows. Microsoft publica las revisiones de seguridad según sea necesario y sigue el mismo concepto que en cualquier otro dispositivo Windows.
1. **Seguridad del sistema operativo: ¿qué opciones hay para mejorar el sistema operativo?  ¿Se pueden quitar o apagar aplicaciones o servicios innecesarios?**
    1. HoloLens se comporta como un smartphone. Es comparable a otros dispositivos Windows modernos. HoloLens se puede administrar mediante Microsoft Intune u otras soluciones de Administración de dispositivos modernas, como MobileIron, Airwatch o Soti. Hay directivas que puede establecer en estos sistemas de administración para colocar directivas de seguridad en el dispositivo y para proteger el dispositivo. También existe la opción de eliminar las aplicaciones innecesarias si se desea.
1. **¿Cómo se administrarán y actualizarán las aplicaciones de software? ¿Qué control tenemos para definir qué aplicaciones se cargan y el proceso de actualización de aplicaciones para las aplicaciones que se encuentran en Microsoft Store?**
    1. HoloLens obtiene aplicaciones de software solo a través de la Tienda Windows. Solo se pueden instalar paquetes de aplicación Appx, que se desarrollan para el uso de HoloLens. Puede ver esto en la Microsoft Store con un pequeño logotipo junto a la aplicación que muestra el dispositivo HoloLens. Cualquier control que tenga sobre la administración de aplicaciones de store también se aplica a HoloLens. Puede usar el concepto de la tienda oficial o la tienda para empresas. Las aplicaciones se pueden cargar en paralelo (proceso manual para cargar una aplicación en un dispositivo Windows) o se pueden administrar a través de una MDM para que las aplicaciones se extran automáticamente de la tienda cuando sea necesario.
1. **¿Cuál es la frecuencia de las actualizaciones de las aplicaciones de la tienda para HoloLens?**
    1. A medida que seguimos el mismo concepto de Microsoft Store y extraer aplicaciones desde allí, el ciclo de actualización viene determinado por el desarrollador de la aplicación. Todas las opciones de administración que tiene para controlar el mecanismo de actualización en la tienda también se aplican a HoloLens.
1. **¿Hay una funcionalidad de arranque seguro para HoloLens?**
    1. Yes
1. **¿Existe la posibilidad de deshabilitar o desconectar la compatibilidad con periféricos del dispositivo?**
    1. Yes
1. **¿Existe la capacidad de controlar o deshabilitar el uso de puertos en el dispositivo?**
    1. HoloLens solo contiene dos puertos (uno para los cascos y otro para cargar o conectarse a equipos). No hay capacidad para deshabilitar el puerto debido a motivos de funcionalidad y recuperación.
1. **Antivirus, detección de puntos de conexión, IPS, lista de permitidos de control de aplicaciones: cualquier capacidad para ejecutar antivirus, detección de puntos de conexión, IPS, lista de permitidos de control de aplicaciones, etc.**
    1. Windows Holographic for Business (conjunto comercial) admite Windows Defender Smart Screen. Si una empresa antivirus creara y publicara su aplicación en el Plataforma universal de Windows, se podría descargar en HoloLens. En la actualidad, ninguna compañía ha hecho esto para HoloLens.
    1. Permitir aplicaciones es posible mediante Microsoft Enterprise Store, donde solo puede elegir qué aplicaciones específicas se pueden descargar. Además, a través de MDM puede bloquear qué aplicaciones específicas se pueden ejecutar o incluso ver en el dispositivo.
1. **¿Podemos poner en cuarentena el dispositivo de la red de producción hasta que actualicemos el dispositivo si ha estado sin conexión durante un largo período de tiempo?  Por ejemplo, el dispositivo ha estado sentado en un cajón sin alimentación durante un período (seis meses) y no ha recibido actualizaciones, revisiones, etc.  Cuando intenta entrar en la red, podemos marcarla y decir que debe actualizar en otra red antes de que se le reensalte para unirse a la red.**
    1. Esto es algo que se puede administrar en el nivel de infraestructura mediante una MDM o un servidor local. El dispositivo se puede marcar como no conforme si no cumple una versión de actualización especificada.
1. **¿Microsoft incluye puertas traseras o acceso a los servicios que permiten a Microsoft conectarse al dispositivo para compartir pantallas o tener soporte remoto a su manera?**
    1. No
1. **Cuando se genera un certificado PKI para la comunicación de confianza, queremos que el certificado se genere en el dispositivo para que sepamos que solo está en ese dispositivo, es único para ese dispositivo y no se puede exportar ni usar para suplantar el dispositivo. ¿Esto es cierto en HoloLens? Si no es así, ¿hay una posible mitigación?**
    1. Csr para SCEP se genera en el propio dispositivo. Intune y el conector SCEP local ayudan a proteger las propias solicitudes agregando y comprobando una cadena de desafío que se envía al cliente.
    1. Dado que HoloLens (1.ª generación y 2.ª generación) tiene un módulo TPM, estos certificados se almacenarían en el módulo TPM y no se pueden extraer. Además, incluso si se pudiera extraer, las cadenas de desafío no se pudieron comprobar en un dispositivo diferente, lo que hace que los certificados o la clave no se puedan usar en distintos dispositivos.
