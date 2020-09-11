---
title: Arquitectura de seguridad de HoloLens
description: Arquitectura de seguridad
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: seguridad, hololens, hololens 2, hololens2 seguridad, introducción a la seguridad, arquitectura de seguridad, arquitectura, arquitectura de hololens 2
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f8434ffe2442f270d6360018bea4b64064168d0c
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009558"
---
# Introducción y arquitectura de la seguridad

La arquitectura de seguridad de la HoloLens 2 se diseñó y fabricó desde la base para no tener problemas de seguridad heredados, creando al mismo tiempo una superficie de ataque minimizada. Esta nueva arquitectura innovadora ofrece ubicaciones de almacenamiento seguras y elementos de seguridad avanzada, con mecanismos capaces de blindar sistemas operativos frente a posibles amenazas y vulnerabilidades.

HoloLens 2 combina hardware, software, redes y servicios para brindar seguridad de un extremo a otro, al tiempo que proporciona al usuario una experiencia óptima. Con el HoloLens 2, la gran mayoría de las funciones de seguridad se activan automáticamente, minimizando el esfuerzo requerido para configurar correctamente el sistema operativo.

El HoloLens 2 de Windows y la arquitectura del sistema operativo ofrecen estas innovadoras características de seguridad:

  * **Separación y el aislamiento de estado**: Esta nueva arquitectura protege partes críticas del sistema operativo de HoloLens 2 de los cambios (como las necesarias para que el sistema operativo arranque en un estado de confianza). La tecnología de aislamiento se usa para limitar las aplicaciones que no sean de confianza en un área de espacio aislado, asegurándose de que no puedan influir en la seguridad del sistema. Todo el sistema operativo se segmenta en secciones seguras, donde cada sección se protege gracias a una combinación de otras tecnologías de seguridad.
  
  * **Protección de datos**: Si se pierde o se roba el dispositivo de un usuario, la HoloLens 2 previene que las aplicaciones no autorizadas lean información confidencial confiando en Bi 
  
  * **Sistema operativo si contraseña**: un antiguo sistema operativo basado en contraseña podría exponer de forma inadvertida a los usuarios ante amenazas de phising y a menudo eran responsables de las cuentas comprometidas. Con Windows Holographic for Business se elimina el uso de contraseñas para el inicio de sesión de MSA y AAD y se refuerza la protección de la identidad del usuario con Windows Hello™ y el inicio de sesión de FIDO2. 
  
    > [!NOTE]
    > Para que FIDO2 soporte técnico, el dispositivo debe estar en la versión 19041 o posterior. 

  * **Seguridad de red**: HoloLens 2 brinda al usuario una mayor seguridad de red a través de protocolos mejorados y configuraciones predeterminadas.
