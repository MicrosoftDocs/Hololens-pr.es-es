---
title: Inscripción para la empresa de dispositivos HoloLens en un entorno Wi-Fi restringido de direcciones MAC
description: Cómo obtener la dirección MAC para la red en los dispositivos HoloLens 2
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2b0ed266389ccc5a21117a604a6eb0abd214d4d1
ms.sourcegitcommit: 1793f53f9e1cc63ac40edc09e65bb4beb80a4575
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "11093252"
---
# Inscripción para la empresa de dispositivos HoloLens en un entorno Wi-Fi restringido de direcciones MAC

Este documento describirá un escenario común que hemos identificado dentro de los entornos de clientes en los que la Wi-Fi está restringida por direcciones MAC, o bien se requiere los certificados para unirse a las redes inalámbricas.

## Ejemplo de escenario

Un gran número de clientes en entornos seguros tienen restricciones en sus redes inalámbricas o alámbricas que solo permitirán que los dispositivos aprobados (basados en direcciones MAC) sean conectados con éxito (ya sea con filtrado de direcciones MAC en un punto de acceso inalámbrico o en un servidor DHCP). Además, algunas redes inalámbricas se pueden proteger con PEAP, lo que requiere que se aplique un certificado al dispositivo antes de poder autenticar correctamente la red inalámbrica.

Para los dispositivos HoloLens pueden surgir dos problemas clave, que pueden ocasionar retrasos y trabajo manual al unirse de los dispositivos HoloLens a la red.

- El certificado inalámbrico PEAP debe aplicarse al dispositivo antes de que el dispositivo haya sido incorporado correctamente a la red inalámbrica.
- Debe registrarse la dirección MAC del adaptador Wi-Fi de HoloLens.

Los principales desafíos son:

1. Actualmente, la dirección MAC solo puede ser identificada desde la aplicación Configuración del dispositivo, o bien desde Intune después de una inscripción completa de Intune.
2. Sin la dirección MAC, el dispositivo no puede unirse a la red Wi-Fi para comenzar la inscripción.
3. Las soluciones manuales a estos desafíos necesitan de la participación de los técnicos en los dispositivos.

## Soluciones

Hay varias formas de mejorar esta situación, en función de la infraestructura disponible en el entorno.

| Solución | Ventajas | Requisitos |
| --- | --- | --- |
| Paquete de aprovisionamiento con adaptador Ethernet | Mejora la experiencia de OOBE y permite obtener una experiencia más rápida en lo técnico. | Las HubTechnician USB compatibles con HoloLens aún deberán interactuar con el dispositivo para la captura del MAC y la finalización del OOBE. |
| Piloto automático con registro de Intune por Ethernet | La conexión y el registro del dispositivo en el entorno del cliente en un solo paso puede completarse sin interactuar con el dispositivo. | Intune habilitado para el adaptador de red compatible con TenantHoloLens USB-C compatible con el cliente AAD |
| Información automatizada de las direcciones MAC | Una vez que los dispositivos hayan sido registrados en el espacio empresarial de Intune, escriba el reporte de la dirección MAC al técnico. | Intune PowerShell Commandlets |

## Paquete de aprovisionamiento con adaptador Ethernet

> [!NOTE] 
> Si la red cableada también está sujeta a restricciones de MAC, entonces la dirección MAC del adaptador Ethernet USB-C / Hub deberá ser aprobada previamente. Se debe tener cuidado con este concentrador ya que permitirá el acceso a la red desde otros dispositivos.

### Requisitos

- Puerto de red conectado con acceso a la red del cliente
- Contenedor USB-C compatible con HoloLens que contiene un adaptador Ethernet: cualquier concentrador que no &#39; requiera que se instalen controladores adicionales o instalaciones de aplicaciones debe ser apropiado.
- Paquete de aprovisionamiento que contiene lo siguiente:
  - Contiene información de red inalámbrica y un certificado
  - , opcionalmente, contiene información de inscripción para la organización, &#39; Azure AD
  - Contiene otras opciones de configuración de aprovisionamiento necesarias

### Proceso

El proceso puede variar según el nivel de software del dispositivo. Si el dispositivo tiene la[actualización de mayo de 2004](hololens-release-notes.md#windows-holographic-version-2004), siga los pasos que se indican a continuación.

1. Coloque el paquete de aprovisionamiento en la raíz de una memoria USB, y conéctelo al concentrador.
2. Conecte el cable de Ethernet al concentrador.
3. Conecte el concentrador USB-C al dispositivo HoloLens.
4. Active el dispositivo HoloLens y lleve el uso del dispositivo.
5. Pulse el **botón de bajar volumen y encender** para aplicar el paquete de aprovisionamiento.
6. El técnico ya puede seguir OOBE y, una vez completada, abra la aplicación configuración y recupere la dirección MAC del dispositivo.

Si el dispositivo tiene una compilación de sistema operativo antes de la [Actualización de mayo de 2004](hololens-release-notes.md#windows-holographic-version-2004), siga los siguientes pasos que se indican a continuación.

1. Active el dispositivo HoloLens y conéctelo a un equipo.
2. El dispositivo debe aparecer en el equipo como un dispositivo de almacenamiento de archivos.
3. Copie el paquete de aprovisionamiento al dispositivo
4. Conecte el cable de Ethernet al concentrador.
5. Conecte el concentrador USB-C al dispositivo HoloLens.
6. Use el dispositivo.
7. Pulse el botón de **Bajar volumen y encender** para aplicar el paquete de aprovisionamiento.
8. El técnico ya puede seguir OOBE y, una vez completada, abra la aplicación configuración y recupere la dirección MAC del dispositivo.

### Ventajas

De esta forma, con un &quot;simple toque &quot;del dispositivo, se puede aplicar el paquete de aprovisionamiento correcto y recoger la dirección MAC del dispositivo. [Los paquetes de aprovisionamiento se pueden ser creados siguiendo las instrucciones aquí.](https://docs.microsoft.com/hololens/hololens-provisioning)

## Piloto automático con inscripción en Intune

### Requisitos

- Puerto de red conectado con acceso a la red del cliente
- Dispositivos HoloLens que ejecutan Windows Holographic 2004
- Concentrador USB-C compatible con HoloLens
- Configuración y habilitación de Intune para el espacio empresarial de cliente
- Dispositivo registrado para el piloto automático e importado en el espacio empresarial del cliente
- Directivas de Intune definidas para el dispositivo:
   - Contiene información de red inalámbrica y un certificado
   - Contiene otras opciones de configuración de aprovisionamiento necesarias

Esto permitirá a un cliente con requisitos de red avanzados inscribir los dispositivos en un enfoque sin contacto y escalable

Los requisitos previos adicionales serán necesarios como se indica a continuación:
1. [Habilitar el espacio empresarial en la versión preliminar del piloto automático](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. Crear las directivas de HoloLens para reemplazar el paquete de aprovisionamiento en Intune.
1. Crear las directivas de HoloLens Intune.
1. Asignar los dispositivos al grupo correcto.

### Proceso

1. Conecte el concentrador USB-C y el cable Ethernet al dispositivo HoloLens 2.
2. Active el HoloLens 2
3. El dispositivo debe conectarse automáticamente a Internet en OOBE mediante el adaptador Ethernet, detectar la configuración del piloto automático y registrarse automáticamente con Azure AD e Intune
4. El dispositivo aplicará los certificados Wi-Fi necesarios y otras opciones de configuración que sean necesarios mediante Intune.
5. Una vez finalizado, el técnico podrá cargar el portal de Intune (Endpoint Manager) y profundizar en la página de propiedades del dispositivo, en **> de dispositivos de Inicio-> el > de hardware**
6. La dirección de MAC WiFi estará visible en el portal de Intune.

![Dirección MAC a través de Intune](images/mac-address-intune.jpg)

7. El técnico agregará esta dirección MAC como dispositivo permitido.

### Ventajas

Esto permitirá una experiencia de implementación &quot;sin contacto&quot; para el técnico, con el dispositivo siendo capaz de ir de la caja a inscribirse en AAD e Intune sin que el técnico tenga que llevar el dispositivo o interactuar manualmente con el entorno del HoloLens.

## Informar de las direcciones MAC al técnico

### Requisitos

- Autorización de &quot;Intune Graph Powershell&quot; contra el cliente Inquilino
- Instalación de Intune Graph PowerShell en el equipo de técnicos.
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Acceso de lectura a los &quot;de dispositivos administrados&quot;de elementos de Intune. (Operador de asistencia o superior o un rol personalizado)

En la actualidad, no hay una manera&quot; sencilla &quot;de activar un comando de automatización basado en el registro de un nuevo dispositivo dentro de Intune. Por lo tanto, este comando le proporcionará al técnico una forma sencilla de recuperar la dirección MAC sin tener que iniciar sesión en el portal y recuperarla de forma manual.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

Se devolverá el nombre y la dirección MAC de cualquier dispositivo HoloLens que haya sido inscrito en los últimos 30 días.

![Dirección MAC mediante PowerShell](images/mac-address-powershell.jpg)

### Proceso

Una vez que haya completado la inscripción en Intune, el técnico ejecutaría el script anterior para recuperar la dirección MAC.
