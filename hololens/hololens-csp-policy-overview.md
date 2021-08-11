---
title: Configuración de CSP e introducción a la administración de dispositivos
description: Obtenga información sobre cómo configurar LOSP, directivas y administración de dispositivos mediante mobile Administración de dispositivos paquetes de aprovisionamiento.
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
ms.openlocfilehash: ed28033f10f7a6d0e826775e95d040d0cac7f9e9c6266acd6975d3532f6d8067
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664242"
---
# <a name="configure-csps-and-device-management-overview"></a>Configuración de CSP e introducción a la administración de dispositivos

Los administradores de TI pueden definir e implementar la configuración de directivas en HoloLens 2. Las opciones de configuración que se empleen variarán según el escenario de implementación, siendo los dispositivos corporativos los que ofrecerán al departamento de TI la gama más amplia de control. En Windows 10, los proveedores de servicios de configuración (CSP) son una interfaz para leer, establecer, modificar o eliminar valores de configuración en el dispositivo. Estas opciones de configuración se asignan a claves del Registro o archivos. Algunos proveedores de servicios de configuración admiten el formato WAP, otros admiten SyncML y otros admiten ambos.

Para más información sobre los Windows 10 Holographic de administración de dispositivos, consulte la lista completa de LOS QUE se admiten [en HoloLens dispositivos](/windows/client-management/mdm/configuration-service-provider-reference#hololens).
Los administradores de TI también pueden administrar csp de directiva en dispositivos; consulte la lista completa de CSP de directiva [compatibles con HoloLens 2](/windows/client-management/mdm/policy-csps-supported-by-hololens2).

## <a name="configuration-methods"></a>Métodos de configuración

### <a name="configure-with-mdm"></a>Configuración con MDM

Los CSP y las directivas se pueden administrar fácilmente en cualquier dispositivo personal o corporativo inscrito en un sistema MDM. Una vez que un dispositivo esté inscrito en la solución MDM, podrá administrar ese dispositivo o conjunto de dispositivos mediante configuraciones de dispositivo. Obtenga más información sobre cómo [administrar los dispositivos HoloLens a través de MDM.](hololens-mdm-configure.md)

### <a name="configure-with-provisioning-packages"></a>Configuración con paquetes de aprovisionamiento

HoloLens 2 también admite la configuración de un conjunto limitado de configuraciones de CSP para HoloLens 2 dispositivos mediante paquetes de aprovisionamiento personalizados. Normalmente, los paquetes de aprovisionamiento se aprovechan para dispositivos administrados que no son MDM y deben aplicarse manualmente a cada dispositivo. Lea información sobre la creación de paquetes [de aprovisionamiento personalizados para HoloLens](hololens-provisioning.md).

## <a name="configurations"></a>Configurations

### <a name="common-device-restrictions"></a>Restricciones comunes de dispositivos

Algunas restricciones de dispositivos son tan sencillas como deshabilitar una funcionalidad o conexión al dispositivo. Para obtener más información sobre estas restricciones de [dispositivos comunes,](hololens-common-device-restrictions.md) lea este artículo.

### <a name="kiosk-modes"></a>Modos de pantalla completa

Use el modo quiosco para controlar qué identidades tienen acceso a qué aplicaciones de forma predeterminada. Los quioscos se pueden usar para una sola aplicación o varias experiencias de interfaz de usuario de aplicaciones. Las configuraciones de quiosco van desde una sola aplicación para cualquier usuario que use el dispositivo hasta diferentes selecciones de aplicaciones para distintos grupos. El modo de pantalla completa no detiene que las "aplicaciones permitidas" inicien otras aplicaciones y no estaba pensado para nunca. Obtenga más información [al leer sobre los modos de quiosco y cómo usarlos.](hololens-kiosk.md)

### <a name="settings-page-visibility"></a>Configuración Visibilidad de páginas

Use Configuración directiva de aplicación para controlar qué identidades tienen acceso a la configuración de forma predeterminada. Con esta directiva, Configuración la aplicación se puede configurar para mostrar solo las páginas seleccionadas u ocultar todas las páginas seleccionadas. [Obtenga información sobre cómo configurar las páginas disponibles.](settings-uri-list.md)

Esta característica solo está disponible actualmente en [Windows Insider compila](hololens-insider.md). Asegúrese de que los dispositivos para los que piensa usar esta característica se encuentran en la compilación 19041.1349+.

### <a name="wdac"></a>WDAC

Use la configuración de WDAC para controlar qué aplicaciones o procesos se permiten o no se pueden iniciar con independencia de si el sistema está en pantalla completa o no.
[Consulte nuestra introducción a WDAC.](windows-defender-application-control-wdac.md)
