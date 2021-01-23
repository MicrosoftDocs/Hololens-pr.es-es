---
title: Configuración de CSP e información general sobre la administración de dispositivos
description: Aprende a configurar los CSP, la directiva y la administración de dispositivos mediante la administración de dispositivos móviles y los paquetes de aprovisionamiento.
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
ms.openlocfilehash: 60e73a9a70a70c5c583edc73a0add2f0f502ef80
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283251"
---
# Configuración de CSP e información general sobre la administración de dispositivos

Los administradores de TI pueden definir e implementar la configuración de directivas en HoloLens 2. Las opciones de configuración que se empleen variarán según el escenario de implementación, siendo los dispositivos corporativos los que ofrecerán al departamento de TI la gama más amplia de control. En Windows 10, los proveedores de servicios de configuración (CSP) son una interfaz para leer, establecer, modificar o eliminar opciones de configuración en el dispositivo. Estas opciones de configuración se asignan a claves del Registro o archivos. Algunos proveedores de servicios de configuración admiten el formato WAP, otros admiten SyncML y otros admiten ambos.

Para obtener más información acerca de los CSP de administración de dispositivos Holográficos de Windows 10, consulta la lista completa de LOSP compatibles con [dispositivos HoloLens.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)
Los administradores de TI también pueden administrar el CSP de directivas en dispositivos, ver la lista completa de CSP de directivas [compatibles con HoloLens 2.](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## Métodos de configuración

### Configurar con MDM

Los CSP y las directivas se pueden administrar fácilmente en cualquier dispositivo personal o corporativo inscrito en un sistema MDM. Una vez que un dispositivo se inscriba en la solución MDM, podrás administrar ese dispositivo o conjunto de dispositivos mediante configuraciones de dispositivo. Obtén más información sobre cómo [administrar los dispositivos HoloLens a través de MDM.](hololens-mdm-configure.md)

### Configurar con paquetes de aprovisionamiento

HoloLens 2 también admite la configuración de un conjunto limitado de configuraciones de CSP para dispositivos HoloLens 2 a través de paquetes de aprovisionamiento personalizados. Normalmente, los paquetes de aprovisionamiento se aprovechan para dispositivos que no son administrados por MDM y requieren que se apliquen manualmente a cada dispositivo. Leer información sobre la creación de paquetes [de aprovisionamiento personalizados para HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).

## Configuraciones

### Restricciones de dispositivo comunes

Algunas restricciones de dispositivos son tan simples y deshabilitan una funcionalidad o conexión al dispositivo. Para obtener más información sobre estas restricciones comunes [de dispositivos.](hololens-common-device-restrictions.md)

### Modos de pantalla completa

Usa el modo de pantalla completa para controlar qué identidades tienen acceso a qué aplicaciones de forma predeterminada. Los quioscos se pueden usar para una sola aplicación o varias experiencias de interfaz de usuario de aplicaciones. Las configuraciones de quiosco van desde una sola aplicación para cualquier usuario que use el dispositivo hasta diferentes selecciones de aplicaciones para distintos grupos. El modo de pantalla completa no detiene que las "aplicaciones permitidas" inicien otras aplicaciones y no estaba pensado para nada. Para obtener más [información, lee los modos de quiosco y cómo usarlos.](hololens-kiosk.md)

### Visibilidad de página de configuración

Usa la directiva de aplicación Configuración para controlar qué identidades tienen acceso a la configuración de forma predeterminada. Con esta directiva, la aplicación Configuración se puede configurar para mostrar solo las páginas seleccionadas u ocultar todas las páginas seleccionadas. [Obtenga información sobre cómo configurar las páginas disponibles.](settings-uri-list.md)

Actualmente, esta característica solo está disponible [en las compilaciones de Windows Insider.](hololens-insider.md) Asegúrate de que los dispositivos para los que quieres usar esta característica se encuentran en la compilación 19041.1349+.

### WDAC

Usa la configuración WDAC para controlar qué aplicaciones o procesos se permiten o no se pueden iniciar independientemente de si el sistema está en modo de pantalla completa o no.
[Consulta nuestra introducción a WDAC.](windows-defender-application-control-wdac.md)
