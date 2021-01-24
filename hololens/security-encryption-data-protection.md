---
title: Protección y cifrado de datos
description: Obtén información sobre el cifrado y la protección de datos en dispositivos HoloLens 2, incluida la integración de BitLocker y Azure.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: seguridad, hololens, Cifrado, Protección de datos, Dispositivo BitLocker, BitLocker, bitlocker, cifrado bitlocker, integración con azure,
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: e005f04088127a0e38a4dd978cd63e5d4e5c0ab9
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284111"
---
# Protección y cifrado de datos

El cifrado y la protección de datos protegen los datos en caso de extravío o robo del dispositivo y evita que las aplicaciones no autorizadas puedan acceder a la información confidencial.

## Cifrado de dispositivo de BitLocker

BitLocker es una característica de cifrado de volumen completo para la protección de la integridad de los medios de solo lectura y la protección de la privacidad de los medios grabables.  Desde el principio, ha sido un escudo eficaz contra el acceso no autorizado a los datos durante los ataques sin conexión. HoloLens 2 habilita el cifrado de dispositivo de BitLocker de forma predeterminada para proteger los datos de los accesos físicos no autorizados al dispositivo. Microsoft sigue invirtiendo en esta tecnología y mejorándola en todo momento para satisfacer las necesidades futuras.

El cifrado de dispositivo de BitLocker es una característica de protección de datos que implementa el cifrado AES-XTS-256 en todos los volúmenes en el diseño de dispositivo independiente. El cifrado de dispositivo de BitLocker proporciona el cifrado a nivel de dispositivo en un diseño de separación por estado. El cifrado de dispositivo BitLocker se habilita automáticamente en el sistema operativo y en volúmenes de datos fijos, y no lo pueden desactivar ni siquiera los administradores de TI, de modo que el dispositivo siempre estará protegido.

Las claves de cifrado de dispositivo de BitLocker se usan para descifrar de forma transparente archivos binarios y los datos necesarios para arrancar el dispositivo. Cuando se desbloquea el volumen del sistema operativo y se arranca un sistema, se obtiene acceso a otros volúmenes con una versión específica del volumen del protector de desbloqueo automático. No hay otros protectores disponibles que conserven la privacidad del usuario y la unidad solo se puede desbloquear en el mismo dispositivo. La aplicación de solo lectura en los volúmenes necesarios se aplica y exige inmediatamente, a partir del primer arranque.

## Integración de Azure 

HoloLens 2 permite a los clientes integrar sus dispositivos con los servicios de Azure. Las comunicaciones entre los dispositivos HoloLens 2 y Azure usan el protocolo TLS (Seguridad de la capa de transporte) para proteger los datos que viajan entre él y los servicios en la nube, lo que ofrece una autenticación robusta, privacidad de mensajes e integridad. Todos los servicios de Azure son totalmente compatibles con TLS 1.2 y cualquier servicio en el que los clientes solo usen TLS 1.2 y solo acepten el tráfico de TLS 1.2. Los estándares de cifrado de Azure para los datos en tránsito se detallan en [Información general sobre el cifrado de Azure](https://docs.microsoft.com/azure/security/fundamentals/encryption-overview). Vea la documentación de Azure para obtener más información sobre los [procedimientos recomendados para el cifrado y la seguridad de los datos de Azure](https://docs.microsoft.com/azure/security/fundamentals/data-encryption-best-practices). 

OneDrive, un ejemplo de integración en la nube con HoloLens 2, tiene una característica de carga automática en la que sus archivos y documentos se pueden cargar automáticamente en la nube al conectarse a Internet. No se puede desactivar la pausa de la sincronización automática de archivos a través de la directiva, pero se puede configurar directamente mediante la experiencia de usuario. 
