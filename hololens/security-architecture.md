---
title: Arquitectura de seguridad de HoloLens
description: Arquitectura de seguridad
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, hololens 2, hololens2 security, security overview, security architecture, architecture, hololens 2 architecture
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: fd6409f5087ef7d6e7ab90d6ef8dcb83e1c490746803ad869ef075dace24bae7
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665529"
---
# <a name="security-overview-and-architecture"></a>Introducción y arquitectura de la seguridad

La arquitectura de seguridad de HoloLens 2 se diseñó y fabricó desde la base para no tener problemas de seguridad heredados y, al mismo tiempo, minimizar la superficie de ataque. Esta nueva arquitectura innovadora ofrece ubicaciones de almacenamiento seguras y elementos de seguridad avanzada, con mecanismos capaces de blindar sistemas operativos frente a posibles amenazas y vulnerabilidades.

HoloLens 2 combina hardware, software, redes y servicios para brindar seguridad de un extremo a otro y, al mismo tiempo, proporcionar al usuario una experiencia óptima. Con HoloLens 2, la gran mayoría de las funciones de seguridad se activan automáticamente, lo que minimiza el esfuerzo requerido para configurar correctamente el sistema operativo.

Microsoft HoloLens 2 y la arquitectura del sistema operativo ofrecen estas innovadoras características de seguridad:

  * **Separación y aislamiento de estado**: esta nueva arquitectura protege las partes críticas del sistema operativo de HoloLens 2 de cambios (como las necesarias para que el sistema operativo principal arranque en un estado de confianza). La tecnología de aislamiento se usa para limitar las aplicaciones que no sean de confianza en un área de espacio aislado, lo que garantiza que no pueden afectar a la seguridad del sistema. Todo el sistema operativo se segmenta en secciones seguras, donde cada sección se protege gracias a una combinación de distintas tecnologías de seguridad.
  
  * **Protección de datos**: si se pierde o se roba el dispositivo de un usuario, HoloLens 2 impide que las aplicaciones no autorizadas lean información confidencial mediante el cifrado de datos de BitLocker. 
  
  * **Sistema operativo sin contraseña**: los antiguos sistemas operativos basados en contraseña podían exponer de forma inadvertida a los usuarios a amenazas de phising y a menudo eran responsables de las cuentas comprometidas. Con Windows Holographic for Business se elimina el uso de contraseñas para el inicio de sesión de MSA y Azure AD y se refuerza la protección de la identidad del usuario con Windows Hello™ y el inicio de sesión de FIDO2. 
  
    > [!NOTE]
    > Para poder disfrutar del soporte técnico de FIDO2, el dispositivo debe tener la versión 19041 o posterior. 

  * **Seguridad de red**: HoloLens 2 brinda al usuario una mayor seguridad de red a través de protocolos mejorados y configuraciones predeterminadas.
