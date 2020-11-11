---
title: Restricciones comunes de dispositivos
description: Restrctions del dispositivo que se suele configurar en HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 744d54a344867c5c38681781580f5357e0a0da70
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162960"
---
# Restricciones comunes de dispositivos 

Esta guía ayuda a los profesionales de ti a comprender las opciones de administración más usadas disponibles para el sistema operativo Windows 10 Holographic en la empresa. Consulta la documentación del sistema MDM para comprender cómo habilita estas directivas el proveedor de MDM. No todos los sistemas MDM admiten todas las configuraciones descritas en esta guía. Algunos admiten las directivas personalizadas a través de archivos XML OMA-URI. Consulta [Soporte de Microsoft Intune para directivas personalizadas](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10). Las convenciones de nomenclatura también pueden variar entre distintos proveedores de MDM.

## Impedir la modificación de la configuración
Generalmente, se permite a los empleados cambiar determinadas opciones de configuración de los dispositivos personales que es posible que desees bloquear en los dispositivos corporativos. Los empleados pueden ajustar de forma interactiva ciertas opciones de configuración de HoloLens a través de la interfaz de usuario de configuración. Con el sistema MDM, puedes limitar lo que los usuarios pueden cambiar. En la siguiente lista se usan con frecuencia opciones de configuración de MDM que Windows 10 Holographic admite para establecer restricciones de configuración:
-   [Permitir VPN:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Permite al usuario cambiar la configuración de VPN
-   [Permitir la configuración de WiFi manual:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Permite a los usuarios realizar conexiones Wi-Fi fuera de las redes aprovisionadas de MDM
-   [Permitir la anulación manual de MDM](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Si los usuarios pueden eliminar la cuenta del área de trabajo (es decir, anular la inscripción del dispositivo desde el sistema MDM)

Agregado en [Windows Holographic, versión 20H2](hololens-release-notes.md#windows-holographic-version-20h2) para dispositivos HoloLens 2:
- [Permitir Agregar paquete de aprovisionamiento:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Activar o desactivar si los usuarios pueden agregar nuevos paquetes de aprovisionamiento y sobrescribir con nuevos valores.
- [Permitir quitar paquete de aprovisionamiento:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Activar o desactivar si los usuarios pueden quitar los paquetes de aprovisionamiento, lo que les permite alternar la configuración de bloqueo anterior.

Más información sobre las opciones de directiva en la Directiva admitida de los [CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2) de HoloLens

## Restricciones de hardware
Los dispositivos Windows 10 Holographic usan tecnología de vanguardia que incluye características de hardware populares, como cámaras, micrófonos, altavoces, interfaces USB, interfaces Bluetooth y Wi-Fi. Puedes usar restricciones de hardware para controlar la disponibilidad de estas funciones.
En la siguiente lista se usan con frecuencia opciones de configuración de MDM que Windows 10 Holographic admite para configurar restricciones de hardware:

> [!NOTE]
> Algunas de estas restricciones de hardware afectan a la conectividad y ayudan en la protección de datos.

-   [Permitir Wi-Fi:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Si los usuarios pueden habilitar y usar la radio WiFi en sus dispositivos.
-   [Permitir conexión USB:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Si la conexión USB está habilitada (no afecta la carga de USB).
-   [Permitir Bluetooth:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Si los usuarios pueden habilitar y usar la radio Bluetooth en sus dispositivos.
-   [Restringir la cámara:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Especifica si las aplicaciones de Windows pueden acceder a la cámara.
-   [Restringir micrófonos:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Especifica si las aplicaciones de Windows pueden acceder al micrófono.

Agregado en [Windows Holographic, Verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) para dispositivos HoloLens 2. 
- [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Establezca la cantidad de tiempo hasta que la pantalla se desactive y desactive la pantalla, bloquea el dispositivo. 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Establezca la cantidad de tiempo hasta que la pantalla se desactive y desactive la pantalla, bloquea el dispositivo. 
