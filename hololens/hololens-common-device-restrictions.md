---
title: Restricciones comunes de dispositivos
description: Manténgase al día con las restricciones y la configuración de dispositivos comunes para HoloLens dispositivo de realidad mixta.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2021
ms.reviewer: aboeger
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 12dd061565c88fed65d1152c224be9ebbc7185d4
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924302"
---
# <a name="common-device-restrictions"></a>Restricciones comunes de dispositivos

Esta guía ayuda a los profesionales de TI a comprender las opciones de administración más usadas disponibles para Windows 10 Holographic sistema operativo en la empresa. Consulta la documentación del sistema MDM para comprender cómo habilita estas directivas el proveedor de MDM. No todos los sistemas MDM admiten todas las configuraciones descritas en esta guía. Algunos admiten las directivas personalizadas a través de archivos XML OMA-URI. Consulta [Soporte de Microsoft Intune para directivas personalizadas](/mem/intune/configuration/custom-settings-windows-10). Las convenciones de nomenclatura también pueden variar entre distintos proveedores de MDM.

## <a name="prevent-changing-of-settings"></a>Impedir la modificación de la configuración

Generalmente, se permite a los empleados cambiar determinadas opciones de configuración de los dispositivos personales que es posible que desees bloquear en los dispositivos corporativos. Los empleados pueden ajustar interactivamente determinadas configuraciones del HoloLens a través de la interfaz de usuario de configuración. Con el sistema MDM, puedes limitar lo que los usuarios pueden cambiar.
A continuación se enumeran las opciones de MDM que se usan Windows 10 Holographic admiten para configurar restricciones de configuración:

- [Permitir VPN:](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Permite al usuario cambiar la configuración de VPN.
- [Permitir configuración wi-fi manual:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Permite a los usuarios realizar conexiones Wi-Fi fuera de las redes aprovisionadas de MDM
- [Permitir la anulación manual de la inscripción de MDM](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Si los usuarios pueden eliminar la cuenta del área de trabajo (es decir, anuló la inscripción del dispositivo del sistema MDM).

Se ha agregado [Windows Holographic, versión 20H2](hololens-release-notes.md#windows-holographic-version-20h2) para HoloLens 2 dispositivos:

- [Permitir agregar paquete de aprovisionamiento:](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Alterne si los usuarios pueden agregar nuevos paquetes de aprovisionamiento, sobrescribiendo con nuevos valores.
- [Permitir quitar paquete de aprovisionamiento:](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Alterne si los usuarios pueden quitar paquetes de aprovisionamiento, lo que les permite alternar la configuración bloqueada previamente.

Se ha agregado [Windows Holographic, versión 21H2:](hololens-release-notes.md#windows-holographic-version-21h2)

- [La directiva RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly) permite configurar la aplicación Microsoft Store para mostrar solo la tienda privada configurada para su organización, lo que limita el acceso solo a las aplicaciones que ha puesto a disposición.

Encontrará más detalles sobre las opciones de directiva en los HoloLens de [directiva admitidos.](/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="hardware-restrictions"></a>Restricciones de hardware

Windows 10 Holographic dispositivos usan tecnología de última generación que incluye características de hardware populares, como cámaras, micrófonos, altavoces, interfaces USB, interfaces Bluetooth y Wi-Fi. Puedes usar restricciones de hardware para controlar la disponibilidad de estas funciones.
A continuación se enumeran las opciones de MDM que se usan Windows 10 Holographic admiten para configurar restricciones de hardware:

> [!NOTE]
> Algunas de estas restricciones de hardware afectan a la conectividad y ayudan en la protección de datos.

- [Permitir Wi-Fi:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Si los usuarios pueden habilitar y usar la radio Wi-Fi en sus dispositivos.
- [Permitir conexión USB:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Si la conexión USB está habilitada (no afecta a la carga USB).
- [Permitir Bluetooth:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Si los usuarios pueden habilitar y usar la Bluetooth radio en sus dispositivos.
- [Restringir cámara:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Especifica si Windows aplicaciones pueden acceder a la cámara.
- [Restringir micrófonos:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Especifica si Windows aplicaciones pueden acceder al micrófono.

Se ha agregado [Windows Holographic, versión 20H2](hololens-release-notes.md#windows-holographic-version-20h2) para HoloLens 2 dispositivos:

- [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Establezca la cantidad de tiempo hasta que se apague la pantalla y, al desactivar la pantalla, bloqueará el dispositivo.
- [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Establezca la cantidad de tiempo hasta que se apague la pantalla y, al desactivar la pantalla, bloqueará el dispositivo.
