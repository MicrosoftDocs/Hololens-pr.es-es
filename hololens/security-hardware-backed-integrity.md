---
title: Atestación de tiempo de ejecución e integridad respaldada por hardware
description: Atestación de tiempo de ejecución e integridad respaldada por hardware
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: seguridad, hololens, integridad respaldada por hardware, atestación de tiempo de ejecución, UEFI, arranque seguro UEFI, arranque seguro, TPM, protección contra amenazas, garantía antipersistencia de Windows, integridad de código, protección de código,
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: befd2d892403b7b6c7050f48ba9beffb45b241fe
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016684"
---
# Atestación de tiempo de ejecución e integridad respaldada por hardware

La atestación tiempo de ejecución e integridad respaldada por hardware protege contra las amenazas que se originan antes de iniciar un sistema operativo, durante el tiempo de ejecución, cuando el dispositivo usa hardware y servicios de atestación remota, para asegurar que la integridad se mantiene desde el inicio y durante todo el tiempo de ejecución.

## Arranque seguro UEFI

HoloLens 2 exige el arranque seguro UEFI (Unified Extensible Firmware Interface o Interfaz de Firmware Extensible Unificada) en todo momento y UEFI solo inicia Windows Holographic for Business.
El Arranque seguro garantiza que toda la cadena de arranque se compruebe por identidad y que Windows siempre se inicie con las directivas de seguridad correctas que se le aplican. Para más información sobre el Arranque seguro, vaya aquí.

## TPM

El Módulo de plataforma segura (TPM) es un chip especializado en un dispositivo de punto de conexión. HoloLens 2 usa un TPM 2.0 que proporciona un aislamiento de clave impuesto por hardware.

## Protección contra amenazas de acceso persistente

El objetivo de la mayoría de los ataques cibernéticos es mantener un acceso persistente a un dispositivo. Para el ciberdelito, mantener esta persistencia permite que un dispositivo Windows en peligro se una a una red de robots (botnet), venda el acceso al dispositivo u otros usuarios maliciosos, o habilite el robo repetido de datos. En el mundo de los ataques dirigidos, la persistencia es esencial para lograr un ataque cibernético exitoso, tanto si se trata de un dispositivo como de una red entera (lo que es más habitual).  

De hecho, los ataques dirigidos se consideran "amenazas persistentes avanzadas", ya que su estrategia necesita mantener el acceso a un dispositivo o red dirigidos. Por este motivo, Windows Holographic for Business considera absolutamente crucial la defensa contra la persistencia y usa tecnología antipersistencia para ofrecer una robusta promesa de seguridad de cliente.

### Arranque seguro 

HoloLens 2 exige el Arranque seguro UEFI (Unified Extensible Firmware Interface) en todo el estado central del sistema operativo. UEFI solo inicia plataformas de confianza de Microsoft, lo que garantiza que toda la cadena de arranque se compruebe por integridad y que Windows siempre se inicie con las directivas de seguridad correctas que se le aplican. HoloLens 2 no garantiza que el arranque seguro pueda desactivarse, ni tampoco permite cargadores de arranque de terceros.

> [!Tip]
> Obtenga más información sobre el [Arranque seguro](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).

### Garantía antipersistencia de Windows

La protección contra la persistencia de HoloLens 2 garantiza a sus usuarios que, incluso en la rara situación de que se produzca una amenaza del sistema en tiempo de ejecución, por ejemplo, una vulnerabilidad de seguridad remota, se mitigaría el evento con todo el código malicioso eliminado del sistema, simplemente al apagar el dispositivo. Para fortalecer aún más su protección antipersistencia, HoloLens 2 ha agregado una potente protección de integridad y ha establecido protecciones de solo lectura.

La persistencia para datos de sistema operativo en forma de datos aún es posible, a menos que el usuario realice un restablecimiento del botón de comando (PBR) del dispositivo que borre todas las particiones mutables. Aunque la persistencia para las particiones inmutables sea mucho más complicada, el usuario necesita restablecer el botón de comando de Hololens 2 para eliminar cualquier posible persistencia de amenaza de las partes mutables.

## Protección de integridad de código 

La integridad de código (CI) es una propiedad de clave de seguridad de un sistema operativo moderno. Exigir la CI permite tomar decisiones de seguridad acertadas, ya que garantiza que el código es transparente tanto para el usuario como para el sistema operativo. La integridad de código completa necesita extender la firma de imágenes binarias anteriores e incluir el cumplimiento de tiempo de ejecución, como la integridad de control de flujo y restricciones de código dinámico. La CI es fundamental para evitar múltiples clases de ataques, entre los que se incluyen el malware con ingeniería social, como ransomware, los ataques de ejecución de código remoto y otras clases de ataques.
