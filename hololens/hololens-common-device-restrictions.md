---
title: Restricciones comunes de dispositivos
description: Manténgase al día con las restricciones y configuraciones de dispositivo comunes para el dispositivo de realidad mixta de HoloLens.
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
ms.openlocfilehash: e9c44466da375611f8864eae1b6e6ceea3ef9b09
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283361"
---
# Restricciones comunes de dispositivos 

Esta guía ayuda a los profesionales de TI a comprender las opciones de administración más usadas disponibles para el sistema operativo Holográfico de Windows 10 en la empresa. Consulta la documentación del sistema MDM para comprender cómo habilita estas directivas el proveedor de MDM. No todos los sistemas MDM admiten todas las configuraciones descritas en esta guía. Algunos admiten las directivas personalizadas a través de archivos XML OMA-URI. Consulta [Soporte de Microsoft Intune para directivas personalizadas](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10). Las convenciones de nomenclatura también pueden variar entre distintos proveedores de MDM.

## Impedir la modificación de la configuración
Generalmente, se permite a los empleados cambiar determinadas opciones de configuración de los dispositivos personales que es posible que desees bloquear en los dispositivos corporativos. Los empleados pueden ajustar de forma interactiva determinadas configuraciones de HoloLens a través de la interfaz de usuario de configuración. Con el sistema MDM, puedes limitar lo que los usuarios pueden cambiar. En la siguiente lista se enumeran las configuraciones de MDM usadas habitualmente que Windows 10 Holographic admite para configurar las restricciones de configuración:
-   [Permitir VPN:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Permite al usuario cambiar la configuración de VPN
-   [Permitir configuración wi-fi manual:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Permite a los usuarios establecer conexiones Wi-Fi fuera de las redes aprovisionadas por MDM
-   [Permitir la anulación manual de la inscripción de MDM](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Indica si los usuarios pueden eliminar la cuenta de área de trabajo (es decir, deshacer la inscripción del dispositivo del sistema MDM).

Se agregó [en Windows Holographic, versión 20H2](hololens-release-notes.md#windows-holographic-version-20h2) para dispositivos HoloLens 2:
- [Permitir agregar paquete de aprovisionamiento:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Alterna si los usuarios pueden agregar nuevos paquetes de aprovisionamiento, sobrescribiendo con nuevos valores.
- [Permitir quitar paquete de aprovisionamiento:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Alterna si los usuarios pueden quitar paquetes de aprovisionamiento, lo que les permite alternar la configuración previamente bloqueada.

Encontrar más detalles sobre las opciones de directiva en los [CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2) de directivas compatibles con HoloLens

## Restricciones de hardware
Los dispositivos Holográficos de Windows 10 usan tecnología de última generación que incluye características de hardware populares como cámaras, micrófonos, altavoces, interfaces USB, interfaces Bluetooth y Wi-Fi. Puedes usar restricciones de hardware para controlar la disponibilidad de estas funciones.
En la siguiente lista se enumeran las configuraciones de MDM que windows 10 Holographic admite con frecuencia para configurar restricciones de hardware:

> [!NOTE]
> Algunas de estas restricciones de hardware afectan a la conectividad y ayudan a la protección de datos.

-   [Permitir Wi-Fi:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Indica si los usuarios pueden habilitar y usar la radio WiFi en sus dispositivos.
-   [Permitir conexión USB:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Indica si la conexión USB está habilitada (no afecta a la carga USB).
-   [Permitir Bluetooth:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Indica si los usuarios pueden habilitar y usar la Bluetooth radio en sus dispositivos.
-   [Restringir cámara:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Especifica si las aplicaciones de Windows pueden acceder a la cámara.
-   [Restringir micrófonos:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Especifica si las aplicaciones de Windows pueden acceder al micrófono.

Se agregó [en Windows Holographic, versión 20H2](hololens-release-notes.md#windows-holographic-version-20h2) para dispositivos HoloLens 2. 
- [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Establece la cantidad de tiempo hasta que la pantalla se apague y, al desactivar la pantalla, bloquea el dispositivo. 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Establece la cantidad de tiempo hasta que la pantalla se apaga y, al desactivar la pantalla, bloquea el dispositivo. 
