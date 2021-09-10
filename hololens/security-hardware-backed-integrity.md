---
title: Atestación de tiempo de ejecución e integridad respaldada por hardware
description: Atestación de tiempo de ejecución e integridad respaldada por hardware
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: seguridad, hololens, integridad respaldada por hardware, atestación de tiempo de ejecución, UEFI, arranque seguro UEFI, arranque seguro, TPM, protección contra amenazas, garantía antipersistencia de Windows, integridad de código, protección de código
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 037f9325555244314518c81d7814bf983c345af6
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2021
ms.locfileid: "124429016"
---
# <a name="hardware-backed-integrity-and-runtime-attestation"></a>Atestación de tiempo de ejecución e integridad respaldada por hardware

La atestación de tiempo de ejecución e integridad respaldada por hardware protege contra las amenazas que se originan antes de iniciar un sistema operativo, durante el tiempo de ejecución, cuando el dispositivo usa hardware y servicios de atestación remota, para garantizar que la integridad se mantiene desde el inicio y durante todo el tiempo de ejecución.

## <a name="uefi-secure-boot"></a>Arranque seguro UEFI

HoloLens 2 siempre aplica el arranque seguro UEFI (Unified Extensible Firmware Interface). UEFI solo inicia Windows Holographic for Business.
El arranque seguro garantiza la comprobación de la integridad de toda la cadena de arranque y que Windows siempre se inicie con las directivas de seguridad correctas aplicadas. Más información sobre el [arranque seguro](/windows-hardware/design/device-experiences/oem-secure-boot).

## <a name="tpm"></a>TPM

El Módulo de plataforma segura (TPM) es un chip especializado en un dispositivo de punto de conexión. HoloLens 2 usa TPM 2.0 que proporciona un aislamiento de clave impuesto por hardware. Obtenga más información sobre los [aspectos básicos de TPM](/windows/security/information-protection/tpm/tpm-fundamentals).

## <a name="persistence-access-threat-protection"></a>Protección contra amenazas de acceso persistente

El objetivo de la mayoría de los ataques cibernéticos es mantener el acceso persistente a un dispositivo. En caso de ciberdelito, mantener esta persistencia permite que un dispositivo Windows en peligro se una a una red de robots (botnet), venda el acceso al dispositivo u otros usuarios maliciosos, o habilite el robo repetido de datos. En el mundo de los ataques dirigidos, la persistencia es esencial para lograr un ataque cibernético exitoso, tanto si se trata de un dispositivo como de una red entera (lo que es más habitual).  

De hecho, los ataques dirigidos se consideran "amenazas persistentes avanzadas", ya que su estrategia necesita mantener el acceso a un dispositivo o una red de destino. Por este motivo, Windows Holographic for Business considera absolutamente crucial la defensa contra la persistencia y usa tecnología antipersistencia para ofrecer una firme promesa de seguridad de cliente.

### <a name="secure-boot"></a>Arranque seguro

HoloLens 2 aplica el arranque seguro UEFI (Unified Extensible Firmware Interface) en todo el estado del sistema operativo principal. UEFI solo inicia plataformas de confianza de Microsoft, lo que garantiza que se compruebe la integridad de toda la cadena de arranque y que Windows siempre se inicie con las directivas de seguridad correctas aplicadas. HoloLens 2 no garantiza que el arranque seguro pueda desactivarse, ni tampoco permite cargadores de arranque de terceros.

> [!Tip]
> Obtenga más información sobre el [arranque seguro](/windows-hardware/design/device-experiences/oem-secure-boot).

### <a name="windows-anti-persistence-assurance"></a>Garantía antipersistencia de Windows

La antipersistencia de HoloLens 2 garantiza a sus usuarios que, incluso en la rara situación de que se produzca una amenaza del sistema en tiempo de ejecución (por ejemplo, una vulnerabilidad de seguridad remota), el evento se mitigaría con todo el código malicioso eliminado del sistema, simplemente apagando el dispositivo. Para reforzar aún más su antipersistencia, HoloLens 2 ha agregado una protección eficaz de la integridad y ha implementado protecciones de solo lectura.

La persistencia para datos del sistema operativo en forma de datos aún es posible, a menos que el usuario realice un restablecimiento rápido (PBR) del dispositivo que borre todas las particiones mutables. Aunque la persistencia para las particiones inmutables es mucho más complicada, el usuario necesita restablecer rápidamente HoloLens 2 para eliminar cualquier posible persistencia de amenaza de las partes mutables.

## <a name="code-integrity-protection"></a>Protección de la integridad de código

La integridad de código (CI) es una propiedad de seguridad clave de un sistema operativo moderno. Exigir la CI permite tomar decisiones de seguridad acertadas, ya que garantiza que el origen del código es transparente tanto para el usuario como para el sistema operativo. La integridad de código completa necesita ampliar la firma de imágenes binarias anteriores e incluir la aplicación del tiempo de ejecución, como la integridad del control de flujo y las restricciones de código dinámico. La CI es fundamental para evitar múltiples clases de ataques, entre los que se incluyen el malware con ingeniería social, como ransomware, vulnerabilidades de seguridad de ejecución de código remoto y algunas otras clases de ataques.
