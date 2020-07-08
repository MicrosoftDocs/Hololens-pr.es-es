---
title: Preguntas más frecuentes sobre seguridad
description: Preguntas más frecuentes sobre la seguridad de hololens
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: pawinfie
ms.author: pawinfie
ms.date: 02/19/2020
keywords: hololens, Windows Mixed Reality, seguridad
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: high
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: bradke
ms.openlocfilehash: e6f8a2c579010b27f5336cb072727d12430c6e8a
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857849"
---
# Preguntas más frecuentes sobre seguridad

## Preguntas acerca de la seguridad de HoloLens (1.ª generación)

1. **¿Qué tipo de red inalámbrica se usa?**
    1. 802.11 AC y Bluetooth 4.1 LE
1. **¿Qué tipo de arquitectura está incorporada?  Por ejemplo: punto a punto, malla u otra.**
    1. La conexión Wi-Fi se puede usar en el modo de infraestructura para la comunicación con otros puntos de acceso inalámbrico.
    1. Bluetooth se puede usar para la comunicación de punto a punto entre varios HoloLens, si la aplicación es compatible, o con otros dispositivos Bluetooth.
1. **¿Cuál es el Id. de FCC?**
    1. C3K1688
1. **¿En qué rangos de frecuencia y canales opera el dispositivo? ¿Es configurable?**
    1. Wi-Fi: el usuario no puede configurar el rango de frecuencia y este varía en función del país de uso. En Estados Unidos, Wi-Fi usa los canales de 2,4 GHz (1-11) y los canales de 5 GHz (36-64, 100-165).
    1. Bluetooth: usa el rango estándar de 2,4 a 2,48 GHz.
1. **¿Puede el dispositivo permitir o bloquear frecuencias específicas?**
    1. El usuario o dispositivo no puede controlar esto.
1. **¿Cuál es el nivel de energía para transmitir y recibir? ¿Es ajustable? ¿Cuál es el rango de operación?**
    1. Se pueden encontrar nuestros estándares de prueba de emisiones [aquí](https://fccid.io/C3K1688). El rango de operación depende en gran medida del punto de acceso y el entorno, pero es aproximadamente equivalente al de otros teléfonos, tabletas o PC de alta calidad.
1. **¿Cuál es el ciclo de trabajo o la duración de un funcionamiento normal?**
    1. 2 a 3 horas de uso activo y 2 semanas en modo de espera.
    1. La duración de la batería no está disponible.
1. **¿Cuál es el comportamiento de transmisión y recepción cuando una herramienta está fuera de rango?**
    1. La transmisión y la recepción de HoloLens siguen el patrón estándar de Wi-Fi/Bluetooth. En el extremo de su rango, es probable que observe que la entrada se entrecorta hasta que se desconecta completamente, pero cuando se está en el rango nuevamente, debería debe volver a conectarse rápidamente.
1. **¿Cuál es la densidad de implementación por metro cuadrado?**
    1. Esto depende de la infraestructura de red.
1. **¿Puede el dispositivo usar la infraestructura como cliente?**
    1. Sí
1. **¿Qué protocolo se usa?**
    1. HoloLens no usa ningún protocolo de su propiedad.
1. **Frecuencia de actualización de SO: ¿Cuál es la frecuencia de las actualizaciones de SO para el HL?  ¿Hay una programación definida?  ¿Microsoft publica revisiones de seguridad u otros según las necesidades?**
    1. Microsoft ofrece actualizaciones de SO para el HoloLens exactamente de la misma forma que lo hace para Windows 10. Por lo general, hay dos actualizaciones principales al año: una en primavera y otra en otoño. Como HoloLens es un dispositivo Windows, el concepto de actualización es el mismo que para cualquier otro dispositivo Windows. Microsoft publica revisiones de seguridad según sea necesario y sigue el mismo concepto que con cualquier otro dispositivo Windows.
1. **Endurecimiento del SO: ¿Qué opciones hay para endurecer el SO?  ¿Podemos quitar o cerrar las aplicaciones o los servicios que no sean necesarios?**
    1. HoloLens se comporta como un smartphone. Es comparable a otros dispositivos Windows modernos. HoloLens se puede administrar con Microsoft Intune u otras soluciones modernas de administración de dispositivos, como MobileIron, Airwatch o SOTI. Se pueden establecer directivas en estos sistemas de administración para incluir directivas de seguridad en el dispositivo con el fin de endurecerlo. También existe la opción de eliminar las aplicaciones innecesarias si se quiere.
1. **¿Cómo se administran y actualizan las aplicaciones de software? ¿Qué control tenemos para definir qué aplicaciones se cargan y qué proceso se sigue en la actualización de las aplicaciones de Microsoft Store?**
    1. HoloLens obtiene aplicaciones de software solo a través de la tienda Windows. Solo se pueden instalar paquetes de aplicación Appx, desarrollados para el uso de HoloLens. Puede verificar esto en Microsoft Store mediante un pequeño logotipo que aparece junto a la aplicación y que muestra el dispositivo HoloLens. Cualquier control que tenga en la administración de las aplicaciones de Microsoft Store también se aplica a HoloLens. Puede usar el concepto de la tienda oficial o de la tienda para empresas. Las aplicaciones se pueden cargar lateralmente (proceso manual para cargar una aplicación en un dispositivo Windows) o se pueden administrar mediante MDM, de modo que se extraigan automáticamente de la tienda cuando sea necesario.
1. **¿Cuál es la frecuencia de las actualizaciones de las aplicaciones de la tienda para HoloLens?**
    1. Dado que seguimos el mismo concepto de Microsoft Store y extraemos las aplicaciones desde allí, el ciclo de actualización lo determina el desarrollador de la aplicación. Todas las opciones de administración que tenga para controlar el mecanismo de actualización en la tienda también se aplican a HoloLens.
1. **¿Existe alguna función de arranque seguro para HoloLens?**
    1. Sí
1. **¿Hay alguna posibilidad de deshabilitar o desconectar la compatibilidad con periféricos del dispositivo?**
    1. Sí
1. **¿Existe alguna posibilidad de controlar o deshabilitar el uso de puertos en el dispositivo?**
    1. HoloLens solo tiene dos puertos (uno para auriculares y otro para cargar o conectar a PC). No hay capacidad para deshabilitar el puerto por motivos de recuperación y funcionalidad.
1. **Antivirus, detección de puntos finales, IPS, lista de permisos de control de aplicaciones. Cualquier habilidad para ejecutar antivirus, detección de puntos finales, IPS, lista de permisos de control de aplicaciones, etc.**
    1. Windows Holographic for Business (Commercial Suite) es compatible con SmartScreen de Windows Defender. Si una empresa antivirus creara y publicara su aplicación en la Plataforma universal de Windows, podría descargarse en HoloLens. Por el momento, ninguna empresa lo ha hecho para HoloLens.
    1. Permitir aplicaciones es posible mediante el uso de Microsoft Enterprise Store, donde se puede elegir sólo qué aplicaciones específicas se pueden descargar. Además, a través de MDM puede bloquear qué aplicaciones específicas se pueden ejecutar o incluso ver en el dispositivo.
1. **¿Podemos poner en cuarentena el dispositivo en la red de producción hasta que el dispositivo se actualice en caso de que haya estado sin conexión durante un período de tiempo prolongado?  P. ej. El dispositivo ha estado en un cajón y no se ha encendido durante un tiempo (6 meses) y no ha recibido actualizaciones, parches, etc.  Cuando intente acceder a la red, ¿podemos marcarlo y notificarle que debe primero actualizarse en otra red a fin de cumplir con los requisitos para unirse a esta red?**
    1. Este es un caso que se puede administrar en el nivel de infraestructura mediante MDM o un servidor local. El dispositivo se puede marcar como no compatible si no cumple con el requisito de versión de actualización específica.
1. **¿Se incluyen puertas traseras o acceso a los servicios que permitan que Microsoft pueda conectarse al dispositivo para compartir la pantalla o acceder de forma remota a voluntad?**
    1. No
1. **Cuando se genera un certificado PKI para las comunicaciones de confianza, el certificado debe generarse en el dispositivo, de modo que sepamos que solo se encuentra en ese dispositivo, es único para ese dispositivo y no se puede exportar ni usar para representar al dispositivo. ¿Es ese el caso en HoloLens? Si no es así, ¿existe alguna medida de mitigación?**
    1. La CSR para SCEP se genera en el propio dispositivo. Intune y el conector de SCEP local pueden proteger las solicitudes al agregar y verificar una cadena de comprobación que se envía al cliente.
    1. Dado que HoloLens (1.ª y 2.ª generación) tiene un módulo TPM, estos certificados se almacenarán en el módulo TPM y no se podrán extraer. Además, incluso si se pudieran extraer, las cadenas de comprobación no se podrían verificar en un dispositivo diferente, lo que hace que los certificados y claves no se puedan usar en otros dispositivos.

## Preguntas acerca de la seguridad de HoloLens (2.ª generación)

1. **¿Qué tipo de red inalámbrica se usa?**
    1. 802.11 AC y Bluetooth 5.0 LE
1. **¿Qué tipo de arquitectura está incorporada?  Por ejemplo: punto a punto, malla u otra.**
    1. La conexión Wi-Fi se puede usar en el modo de infraestructura para la comunicación con otros puntos de acceso inalámbrico.
    1. Bluetooth se puede usar para la comunicación de punto a punto entre varios HoloLens, si la aplicación es compatible, o con otros dispositivos Bluetooth.
1. **¿Cuál es el Id. de FCC?**
    1. C3K1855
1. **¿En qué rangos de frecuencia y canales opera el dispositivo? ¿Es configurable?**
    1. Wi-Fi: el usuario no puede configurar el rango de frecuencia y este varía en función del país de uso. En Estados Unidos, Wi-Fi usa los canales de 2,4 GHz (1-11) y los canales de 5 GHz (36-64, 100-165).
1. **¿Puede el dispositivo permitir o bloquear frecuencias específicas?**
    1. El usuario o dispositivo no puede controlar esto.
1. **¿Cuál es el nivel de energía para transmitir y recibir? ¿Es ajustable? ¿Cuál es el rango de operación?**
    1. Los niveles de energía inalámbrica dependen del canal de operación. Los dispositivos se calibran para funcionar en el nivel más alto permitido por los reglamentos de la región.
1. **¿Cuál es el ciclo de trabajo o la duración de un funcionamiento normal?**
    1. *No está disponible.*
1. **¿Cuál es el comportamiento de transmisión y recepción cuando una herramienta está fuera de rango?**
    1. La transmisión y la recepción de HoloLens siguen el patrón estándar de Wi-Fi/Bluetooth. En el extremo de su rango, es probable que observe que la entrada se entrecorta hasta que se desconecta completamente, pero cuando se está en el rango nuevamente, debería debe volver a conectarse rápidamente.
1. **¿Cuál es la densidad de implementación por metro cuadrado?**
    1. Esto depende de la infraestructura de red.
1. **¿Puede el dispositivo usar la infraestructura como cliente?**
    1. Sí
1. **¿Qué protocolo se usa?**
    1. HoloLens no usa ningún protocolo de su propiedad.
1. **Frecuencia de actualización de SO: ¿Cuál es la frecuencia de las actualizaciones de SO para el HL?  ¿Hay una programación definida?  ¿Microsoft publica revisiones de seguridad u otros según las necesidades?**
    1. Microsoft ofrece actualizaciones de SO para el HoloLens exactamente de la misma forma que lo hace para Windows 10. Por lo general, hay dos actualizaciones principales al año: una en primavera y otra en otoño. Como HoloLens es un dispositivo Windows, el concepto de actualización es el mismo que para cualquier otro dispositivo Windows. Microsoft publica revisiones de seguridad según sea necesario y sigue el mismo concepto que con cualquier otro dispositivo Windows.
1. **Endurecimiento del SO: ¿Qué opciones hay para endurecer el SO?  ¿Podemos quitar o cerrar las aplicaciones o los servicios que no sean necesarios?**
    1. HoloLens se comporta como un smartphone. Es comparable a otros dispositivos Windows modernos. HoloLens se puede administrar con Microsoft Intune u otras soluciones modernas de administración de dispositivos, como MobileIron, Airwatch o SOTI. Se pueden establecer directivas en estos sistemas de administración para incluir directivas de seguridad en el dispositivo con el fin de endurecerlo. También existe la opción de eliminar las aplicaciones innecesarias si se quiere.
1. **¿Cómo se administran y actualizan las aplicaciones de software? ¿Qué control tenemos para definir qué aplicaciones se cargan y qué proceso se sigue en la actualización de las aplicaciones de Microsoft Store?**
    1. HoloLens obtiene aplicaciones de software solo a través de la tienda Windows. Solo se pueden instalar paquetes de aplicación Appx, desarrollados para el uso de HoloLens. Puede verificar esto en Microsoft Store mediante un pequeño logotipo que aparece junto a la aplicación y que muestra el dispositivo HoloLens. Cualquier control que tenga en la administración de las aplicaciones de Microsoft Store también se aplica a HoloLens. Puede usar el concepto de la tienda oficial o de la tienda para empresas. Las aplicaciones se pueden cargar lateralmente (proceso manual para cargar una aplicación en un dispositivo Windows) o se pueden administrar mediante MDM, de modo que se extraigan automáticamente de la tienda cuando sea necesario.
1. **¿Cuál es la frecuencia de las actualizaciones de las aplicaciones de la tienda para HoloLens?**
    1. Dado que seguimos el mismo concepto de Microsoft Store y extraemos las aplicaciones desde allí, el ciclo de actualización lo determina el desarrollador de la aplicación. Todas las opciones de administración que tenga para controlar el mecanismo de actualización en la tienda también se aplican a HoloLens.
1. **¿Existe alguna función de arranque seguro para HoloLens?**
    1. Sí
1. **¿Hay alguna posibilidad de deshabilitar o desconectar la compatibilidad con periféricos del dispositivo?**
    1. Sí
1. **¿Existe alguna posibilidad de controlar o deshabilitar el uso de puertos en el dispositivo?**
    1. HoloLens solo tiene dos puertos (uno para auriculares y otro para cargar o conectar a PC). No hay capacidad para deshabilitar el puerto por motivos de recuperación y funcionalidad.
1. **Antivirus, detección de punto final, IPS, permitir control de aplicaciones. Cualquier capacidad de ejecutar antivirus, detección de punto final, IPS, permitir control de aplicaciones, etc.**
    1. HoloLens (2.ª generación) es compatible con SmartScreen de Windows Defender. Si una empresa antivirus creara y publicara su aplicación en la Plataforma universal de Windows, podría descargarse en HoloLens. Por el momento, ninguna empresa lo ha hecho para HoloLens.
    1. Permitir aplicaciones es posible mediante el uso de Microsoft Enterprise Store, donde se puede elegir sólo qué aplicaciones específicas se pueden descargar. Además, a través de MDM puede bloquear qué aplicaciones específicas se pueden ejecutar o incluso ver en el dispositivo.
1. **¿Podemos poner en cuarentena el dispositivo en la red de producción hasta que el dispositivo se actualice en caso de que haya estado sin conexión durante un período de tiempo prolongado?  P. ej. El dispositivo ha estado en un cajón y no se ha encendido durante un tiempo (6 meses) y no ha recibido actualizaciones, parches, etc.  Cuando intente acceder a la red, ¿podemos marcarlo y notificarle que debe primero actualizarse en otra red a fin de cumplir con los requisitos para unirse a esta red?**
    1. Este es un caso que se puede administrar en el nivel de infraestructura mediante MDM o un servidor local. El dispositivo se puede marcar como no compatible si no cumple con el requisito de versión de actualización específica.
1. **¿Se incluyen puertas traseras o acceso a los servicios que permitan que Microsoft pueda conectarse al dispositivo para compartir la pantalla o acceder de forma remota a voluntad?**
    1. No
1. **Cuando se genera un certificado PKI para las comunicaciones de confianza, el certificado debe generarse en el dispositivo, de modo que sepamos que solo se encuentra en ese dispositivo, es único para ese dispositivo y no se puede exportar ni usar para representar al dispositivo. ¿Es ese el caso en HoloLens? Si no es así, ¿existe alguna medida de mitigación?**
    1. La CSR para SCEP se genera en el propio dispositivo. Intune y el conector de SCEP local pueden proteger las solicitudes al agregar y verificar una cadena de comprobación que se envía al cliente.
    1. Dado que HoloLens (1.ª y 2.ª generación) tiene un módulo TPM, estos certificados se almacenarán en el módulo TPM y no se podrán extraer. Además, incluso si se pudieran extraer, las cadenas de comprobación no se podrían verificar en un dispositivo diferente, lo que hace que los certificados y claves no se puedan usar en otros dispositivos.
