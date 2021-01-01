---
title: Configuración de CSP e información general sobre la administración de dispositivos
description: Cómo configurar los CSP, la administración de directivas y dispositivos.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: c6da29506035525b1b1b5141a04603f63de1ef24
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252781"
---
# Configuración de CSP e información general sobre la administración de dispositivos

Los administradores de TI pueden definir e implementar la configuración de la Directiva en HoloLens 2. Las opciones de configuración que se empleen variarán según el escenario de implementación, siendo los dispositivos corporativos los que ofrecerán al departamento de TI la gama más amplia de control. En Windows 10, los proveedores de servicios de configuración (CSP) s son una interfaz para leer, establecer, modificar o eliminar la configuración en el dispositivo. Estas opciones de configuración se asignan a claves del Registro o archivos. Algunos proveedores de servicios de configuración son compatibles con el formato WAP, algunos admiten SyncML y otros admiten ambos.

Para obtener más información sobre los CSP de administración de dispositivos de Windows 10 Holographic, consulte la lista completa de [CSP admitidos en los dispositivos HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).
Los administradores de ti también pueden administrar el CSP de directiva en los dispositivos; consulta la lista completa de directivas de CSP [compatibles con HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).

## Métodos de configuración

### Configurar con MDM

Los CSP y las directivas se pueden administrar fácilmente en cualquier dispositivo personal o empresarial inscrito en un sistema MDM. Una vez que un dispositivo se haya inscrito en la solución MDM, podrá administrar ese dispositivo o conjunto de dispositivos mediante la configuración de los dispositivos. Más información sobre cómo [administrar tus dispositivos HoloLens a través de MDM](hololens-mdm-configure.md).

### Configurar con paquetes de aprovisionamiento

HoloLens 2 también admite la configuración de un conjunto limitado de configuraciones de CSP para dispositivos HoloLens 2 a través de paquetes de aprovisionamiento personalizados. Los paquetes de aprovisionamiento generalmente se aprovechan para dispositivos no administrados con MDM y requieren que se apliquen de forma manual a cada dispositivo. Para obtener información sobre cómo crear [paquetes de aprovisionamiento personalizado para HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning), consulte.

## Configuraciones

### Restricciones de dispositivos comunes

Algunas restricciones de dispositivo son tan sencillas y deshabilitan una funcionalidad o conexión al dispositivo. Para obtener más información sobre las [restricciones de dispositivos comunes.](hololens-common-device-restrictions.md)

### Modos de pantalla completa

Use el modo de pantalla completa para controlar qué identidades tienen acceso a qué aplicaciones de forma predeterminada. Los quioscos se pueden usar para una sola aplicación o para la experiencia de la interfaz de usuario de varias aplicaciones. Las configuraciones de quiosco van desde una sola aplicación para cualquier usuario que use el dispositivo, hasta distintas selecciones de aplicaciones para diferentes grupos. El modo de pantalla completa no impide que las "aplicaciones permitidas" inicien otras aplicaciones y no estaba prevista para nunca. Obtenga más información [acerca de los modos de quiosco y cómo usarlos](hololens-kiosk.md).

### Visibilidad de la página de configuración

Use la Directiva de aplicación de configuración para controlar qué identidades tienen acceso a la configuración de forma predeterminada. Con esta Directiva, la aplicación configuración puede estar configurada para mostrar solo las páginas seleccionadas u ocultar todas las páginas seleccionadas. [Obtenga información sobre cómo configurar las páginas disponibles](settings-uri-list.md).

Esta característica solo está disponible actualmente en [compilaciones de Windows Insider](hololens-insider.md). Asegúrese de que los dispositivos para los que desea usar esta característica están en la compilación 19041.1349 +.

### WDAC

Use la configuración de WDAC para controlar qué aplicaciones/procesos tienen permitido o no un inicio, independientemente de si el sistema está en modo de pantalla completa o no.
[Consulte nuestra información general de WDAC.](windows-defender-application-control-wdac.md)
