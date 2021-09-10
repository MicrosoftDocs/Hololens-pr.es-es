---
title: Inscripción Enterprise de dispositivos HoloLens en un entorno Wi-Fi restringido de direcciones MAC
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
ms.openlocfilehash: d21a63aae94f5ea5269f61fe319a9036626de1b4
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428405"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>Inscripción Enterprise de dispositivos HoloLens en un entorno Wi-Fi restringido de direcciones MAC

En este documento se describirá un escenario común que hemos identificado en entornos de cliente en que la Wi-Fi está restringida por direcciones MAC, o bien se requieren certificados para unirse a redes inalámbricas.

## <a name="example-scenario"></a>Escenario de ejemplo

Un gran número de clientes en entornos seguros tienen restricciones en sus redes inalámbricas o cableadas que solo permitirán que los dispositivos aprobados (basados en direcciones MAC) se conecten correctamente. Esto puede aplicarse a través del filtrado de direcciones MAC en un punto de acceso inalámbrico o a través de un servidor DHCP. Además, algunas redes inalámbricas se pueden proteger con PEAP, lo que requiere que se aplique un certificado al dispositivo para poder autenticar la red inalámbrica.

En este escenario, dos requisitos clave pueden introducir retrasos o requerir una intervención manual al unir dispositivos HoloLens a la red:

- El certificado inalámbrico PEAP debe aplicarse al dispositivo antes de que el dispositivo se una correctamente a la red inalámbrica.
- Debe registrarse la dirección MAC del adaptador Wi-Fi de HoloLens.

Los principales desafíos de los requisitos anteriores son:

1. Actualmente, la dirección MAC solo puede identificarse desde la aplicación Configuración del dispositivo, o bien desde Intune después de una inscripción correcta.

2. Sin la dirección MAC, el dispositivo no puede unirse a la red Wi-Fi para comenzar la inscripción.

3. Las soluciones alternativas manuales a estos desafíos requieren que un técnico interactúe con el dispositivo.

## <a name="solutions"></a>Soluciones

Existen muchas maneras de mejorar esta situación, en función de la infraestructura disponible en el entorno.

| Solución | Ventajas | Requisitos |
| --- | --- | --- |
| Paquete de aprovisionamiento con adaptador Ethernet | Mejora la experiencia OOBE y permite lograr una experiencia técnica más rápida. | Centro de conectividad USB-C Hub + adaptador Ethernet compatibles con HoloLens; el técnico aún deberá interactuar con el dispositivo para la captura de la dirección MAC y la finalización de la experiencia OOBE. |
| Autopilot con registro de Intune a través de Ethernet | Se trata de un proceso de conexión y registro en un solo paso del dispositivo en el entorno del cliente. La captura de la dirección MAC se puede completar sin necesidad de interactuar con el dispositivo. | Intune habilitado para inquilino de AAD del cliente y un adaptador Ethernet USB-C compatible con HoloLens |
| Generación de informes automatizada de direcciones MAC | Cuando los dispositivos se registran con el inquilino de Intune, un script puede notificar la dirección MAC al técnico. | Cmdlets de PowerShell de Intune |

## <a name="provisioning-package-with-ethernet-adaptor"></a>Paquete de aprovisionamiento con adaptador Ethernet

> [!NOTE] 
> Si la red cableada también está sujeta a restricciones de direcciones MAC, la dirección MAC del centro de conectividad USB-C Hub + adaptador Ethernet también deberá aprobarse previamente. Se debe tener cuidado con este adaptador ya que permitirá el acceso a la red desde otros dispositivos.

### <a name="requirements"></a>Requisitos

- Puerto de red conectado con acceso a la red del cliente
- Centro de conectividad USB-C compatible con HoloLens con adaptador Ethernet: cualquier adaptador que no requiera que se instalen aplicaciones o controladores adicionales debería servir.
- Paquete de aprovisionamiento que contiene lo siguiente:
  - Contiene información de red inalámbrica y un certificado.
  - Puede contener información de inscripción de la instancia de Azure AD de la organización.
  - Contiene otras opciones de configuración de aprovisionamiento necesarias.

### <a name="process"></a>Proceso

El proceso puede variar según el nivel de software del dispositivo. Si el dispositivo tiene la [actualización de mayo de 2004](hololens-release-notes.md#windows-holographic-version-2004), realice los estos siguientes.

1. Coloque el paquete de aprovisionamiento en la raíz de una memoria USB y conéctelo al centro de conectividad.
2. Conecte el cable Ethernet al centro de conectividad + adaptador Ethernet.
3. Conecte el centro de conectividad USB-C al dispositivo HoloLens.
4. Active HoloLens y póngase el dispositivo.
5. Presione el **botón de bajar volumen y encendido** para aplicar el paquete de aprovisionamiento.
6. El técnico ya puede seguir la experiencia OOBE y, una vez completada, abrir la aplicación Configuración y recuperar la dirección MAC del dispositivo.

Si el dispositivo tiene una compilación de sistema operativo antes de la [actualización de mayo de 2004](hololens-release-notes.md#windows-holographic-version-2004), siga los pasos que se indican a continuación.

1. Active HoloLens y conecte el dispositivo a un equipo.
2. El dispositivo debería aparecer en el equipo como un dispositivo de almacenamiento de archivos.
3. Copie el paquete de aprovisionamiento en el dispositivo
4. Conecte el cable Ethernet al centro de conectividad.
5. Conecte el centro de conectividad USB-C al dispositivo HoloLens.
6. Póngase el dispositivo HoloLens 2
7. Presione el botón de **bajar volumen y encendido** para aplicar el paquete de aprovisionamiento.
8. El técnico ya puede seguir la experiencia OOBE y, una vez completada, abrir la aplicación Configuración y recuperar la dirección MAC del dispositivo.

### <a name="benefits"></a>Ventajas

De esta forma, con un "simple toque" del dispositivo, se puede aplicar el paquete de aprovisionamiento correcto y recuperar la dirección MAC del dispositivo. [Los paquetes de aprovisionamiento pueden crear siguiendo estas instrucciones.](hololens-provisioning.md)

## <a name="autopilot-with-intune-enrollment"></a>Autopilot con inscripción de Intune

### <a name="requirements"></a>Requisitos

- Puerto de red cableada con acceso a la red del cliente
- Dispositivos HoloLens que ejecutan Windows Holographic 2004
- Adaptador Ethernet USB-C compatible con HoloLens
- Intune configurado y habilitado para el inquilino del cliente
- Dispositivo registrado para Autopilot importado en el inquilino del cliente
- Directivas de Intune definidas para el dispositivo:
   - Contiene información de red inalámbrica y un certificado.
   - Contiene otras opciones de configuración de aprovisionamiento necesarias.

Esto permitirá a un cliente con requisitos de red avanzados inscribir los dispositivos con un enfoque automático y escalable.

Se aplicarán los requisitos previos adicionales que se indican a continuación:
1. [Habilitar el inquilino para la versión preliminar de Autopilot](hololens2-autopilot.md).
1. Crear las directivas de HoloLens para reemplazar el paquete de aprovisionamiento en Intune.
1. Cree las directivas de Intune de HoloLens.
1. Asigne los dispositivos al grupo correcto.

### <a name="process"></a>Proceso

1. Conecte el cable Ethernet al adaptador y conecte el adaptador al puerto USB-C en el dispositivo HoloLens 2.

2. Encienda el dispositivo HoloLens 2.

3. El dispositivo debería conectarse automáticamente a Internet durante la experiencia OOBE a través del adaptador Ethernet. Debería detectar la configuración de Autopilot y registrarse automáticamente con Azure AD e Intune.

4. El dispositivo aplicará los certificados de Wi-Fi y otras opciones de configuración que sean necesarios mediante Intune.

5. Cuando termine, el técnico podrá cargar el portal de Intune (Endpoint Manager) y explorar la página de propiedades del dispositivo, en **Inicio -> Dispositivos -> NombreDeDispositivo -> Hardware**.

6. La dirección MAC Wi-Fi estará visible en el Portal de Intune.

   ![Dirección MAC a través de Intune.](images/mac-address-intune.jpg)

7. El técnico agregará esta dirección MAC como un dispositivo permitido.

### <a name="benefits"></a>Ventajas

Esto permitirá una experiencia de implementación "sin supervisión" para el técnico, en que el dispositivo podrá inscribirse directamente en Azure AD e Intune sin tener que ponérselo o interactuar manualmente con el entorno de HoloLens.

## <a name="reporting-of-mac-addresses-to-the-technician"></a>Notificación de direcciones MAC al técnico

### <a name="requirements"></a>Requisitos

- Autorización de "PowerShell de Intune Graph" en el inquilino del cliente
- Instalación de PowerShell de Intune Graph en la máquina de los técnicos.
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Acceso de lectura a los elementos de "Dispositivos administrados" de Intune. (Operador de asistencia o superior, o bien un rol personalizado)

En la actualidad, no hay una manera sencilla de desencadenar un comando de automatización basado en el registro de un nuevo dispositivo en Intune. Por lo tanto, este comando proporcionará al técnico una forma sencilla de recuperar la dirección MAC sin tener que iniciar sesión en el portal y recuperarla de forma manual.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

Devolverá el nombre y la dirección MAC de todos los dispositivos HoloLens que se hayan inscrito en los últimos 30 días.

![Dirección MAC a través de PowerShell.](images/mac-address-powershell.jpg)

### <a name="process"></a>Proceso

Una vez completada la inscripción en Intune, el técnico deberá ejecutar el script anterior para recuperar la dirección MAC.
