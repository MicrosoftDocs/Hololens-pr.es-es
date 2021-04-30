---
title: Restricciones comunes de dispositivos
description: Manténgase al día con las restricciones de dispositivos comunes y la configuración del dispositivo de realidad mixta de HoloLens.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309088"
---
# <a name="common-device-restrictions"></a>Restricciones comunes de dispositivos 

Esta guía ayuda a los profesionales de TI a comprender las opciones de administración más usadas disponibles para Windows 10 Holographic sistema operativo en la empresa. Consulta la documentación del sistema MDM para comprender cómo habilita estas directivas el proveedor de MDM. No todos los sistemas MDM admiten todas las configuraciones descritas en esta guía. Algunos admiten las directivas personalizadas a través de archivos XML OMA-URI. Consulta [Soporte de Microsoft Intune para directivas personalizadas](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10). Las convenciones de nomenclatura también pueden variar entre distintos proveedores de MDM.

## <a name="prevent-changing-of-settings"></a>Impedir la modificación de la configuración
Generalmente, se permite a los empleados cambiar determinadas opciones de configuración de los dispositivos personales que es posible que desees bloquear en los dispositivos corporativos. Los empleados pueden ajustar interactivamente determinadas configuraciones de HoloLens a través de la interfaz de usuario de configuración. Con el sistema MDM, puedes limitar lo que los usuarios pueden cambiar. A continuación se enumeran las opciones de MDM que se usan Windows 10 Holographic admiten para configurar restricciones de configuración:
-   [Permitir VPN:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Permite al usuario cambiar la configuración de VPN.
-   [Permitir configuración wi-fi manual:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Permite a los usuarios realizar conexiones Wi-Fi fuera de las redes aprovisionadas por MDM
-   [Permitir la anulación manual de la inscripción de MDM](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Si los usuarios pueden eliminar la cuenta del área de trabajo (es decir, anuló la inscripción del dispositivo del sistema MDM).

Se ha agregado [en Windows Holographic, versión 20H2](hololens-release-notes.md#windows-holographic-version-20h2) para HoloLens 2 dispositivos:
- [Permitir agregar paquete de aprovisionamiento:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Alterne si los usuarios pueden agregar nuevos paquetes de aprovisionamiento, sobrescribiendo con nuevos valores.
- [Permitir quitar paquete de aprovisionamiento:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Alterne si los usuarios pueden quitar los paquetes de aprovisionamiento, lo que les permite alternar la configuración bloqueada previamente.

Encontrará más detalles sobre las opciones de directiva en los [CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2) de directiva compatibles con HoloLens.

## <a name="hardware-restrictions"></a>Restricciones de hardware
Windows 10 Holographic dispositivos usan tecnología de última generación que incluye características de hardware populares, como cámaras, micrófonos, altavoces, interfaces USB, interfaces Bluetooth y Wi-Fi. Puedes usar restricciones de hardware para controlar la disponibilidad de estas funciones.
A continuación se enumeran las opciones de MDM que se usan Windows 10 Holographic admiten para configurar restricciones de hardware:

> [!NOTE]
> Algunas de estas restricciones de hardware afectan a la conectividad y ayudan en la protección de datos.

-   [Permitir Wi-Fi:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Si los usuarios pueden habilitar y usar la radio Wi-Fi en sus dispositivos.
-   [Permitir conexión USB:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Si la conexión USB está habilitada (no afecta a la carga USB).
-   [Permitir Bluetooth:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Si los usuarios pueden habilitar y usar la radio Bluetooth en sus dispositivos.
-   [Restringir cámara:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Especifica si las aplicaciones de Windows pueden acceder a la cámara.
-   [Restringir micrófonos:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Especifica si las aplicaciones de Windows pueden acceder al micrófono.

Se ha agregado [en Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) para HoloLens 2 dispositivos. 
- [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Establezca la cantidad de tiempo hasta que se apague la pantalla y, al desactivar la pantalla, bloqueará el dispositivo. 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Establezca la cantidad de tiempo hasta que se apague la pantalla y, al desactivar la pantalla, bloqueará el dispositivo. 
