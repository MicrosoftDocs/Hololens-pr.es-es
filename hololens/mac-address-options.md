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
ms.openlocfilehash: fe365248332f8e78b15ab362f169b84e48dfe594
ms.sourcegitcommit: 07ffe1bf2f45dcb2ba9d7fbe54b4773a0fb9d525
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393844"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>Inscripción para la empresa de dispositivos HoloLens en un entorno Wi-Fi restringido de direcciones MAC

Este documento describirá un escenario común que hemos identificado dentro de los entornos de clientes en los que la Wi-Fi está restringida por direcciones MAC, o bien se requiere los certificados para unirse a las redes inalámbricas.

## <a name="example-scenario"></a>Escenario de ejemplo

Un gran número de clientes en entornos seguros tienen restricciones en sus redes inalámbricas o alámbricas que solo permitirán que los dispositivos aprobados (basados en direcciones MAC) se conecten correctamente. Esto puede aplicarse a través del filtrado de direcciones MAC en un punto de acceso inalámbrico o a través de un servidor DHCP. Además, algunas redes inalámbricas se pueden proteger con PEAP, lo que requiere que se aplique un certificado al dispositivo antes de poder autenticar la red inalámbrica.

En este escenario, dos requisitos clave pueden introducir retrasos o requerir una intervención manual al unir dispositivos HoloLens a la red:

- El certificado inalámbrico PEAP debe aplicarse al dispositivo antes de que el dispositivo haya sido incorporado correctamente a la red inalámbrica.
- Debe registrarse la dirección MAC del adaptador Wi-Fi de HoloLens.

Los principales desafíos con los requisitos anteriores son:

1. Actualmente, la dirección MAC solo puede ser identificada desde la aplicación Configuración del dispositivo, o bien desde Intune después de una inscripción completa.
2. Sin la dirección MAC, el dispositivo no puede unirse a la red Wi-Fi para comenzar la inscripción.
3. Las soluciones alternativas manuales a estos desafíos requieren que un técnico interactúe con el dispositivo.

## <a name="solutions"></a>Soluciones

Existen muchas maneras de mejorar esta situación, en función de la infraestructura disponible en el entorno.

| Solución | Ventajas | Requisitos |
| --- | --- | --- |
| Paquete de aprovisionamiento con adaptador Ethernet | Mejora la experiencia de OOBE y permite obtener una experiencia técnica más rápida. | Concentrador USB-C Hub + adaptador de Ethernet compatible con HoloLens, el técnico aún deberá interactuar con el dispositivo para la captura del MAC y la finalización del OOBE |
| Piloto automático con registro de Intune por Ethernet | Se trata de una conexión y registro en un solo paso del dispositivo en el entorno del cliente. La captura de MAC se puede completar sin necesidad de interactuar con el dispositivo | Intune habilitado para el espacio empresarial de AAD del cliente y un adaptador de Ethernet USB-C compatible con HoloLens |
| Creación de informes automatizada de direcciones MAC | Cuando los dispositivos se registran con el espacio empresarial de Intune, un script puede notificar la dirección de MAC al técnico. | Commandlets de Intune PowerShell |

## <a name="provisioning-package-with-ethernet-adaptor"></a>Paquete de aprovisionamiento con adaptador Ethernet

> [!NOTE] 
> Si la red cableada también está sujeta a restricciones de MAC, entonces la dirección MAC del concentrador USB-C Hub + adaptador de Ethernet también deberá ser aprobada previamente. Se debe tener cuidado con este adaptador ya que permitirá el acceso a la red desde otros dispositivos.

### <a name="requirements"></a>Requisitos

- Puerto de red conectado con acceso a la red del cliente
- Concentrador USB-C compatible con HoloLens con adaptador Ethernet: cualquier adaptador que no requiera que se instalen controladores adicionales o instalaciones de aplicaciones debería servir.
- Paquete de aprovisionamiento que contiene lo siguiente:
  - Contiene información de red inalámbrica y un certificado
  - Puede contener información de inscripción para Azure AD de la organización.
  - Contiene otras opciones de configuración de aprovisionamiento necesarias

### <a name="process"></a>Proceso

El proceso puede variar según el nivel de software del dispositivo. Si el dispositivo tiene la[actualización de mayo de 2004](hololens-release-notes.md#windows-holographic-version-2004), siga los pasos que se indican a continuación.

1. Coloque el paquete de aprovisionamiento en la raíz de una memoria USB, y conéctelo al concentrador.
2. Conecte el cable de Ethernet al adaptador Concentrador + adaptador de Ethernet.
3. Conecte el concentrador USB-C al dispositivo HoloLens.
4. Active HoloLens y póngase el dispositivo.
5. Pulse el botón de **Bajar volumen y Encendido** para aplicar el paquete de aprovisionamiento.
6. El técnico ya puede seguir OOBE y, una vez completada, abrir la aplicación Configuración y recuperar la dirección MAC del dispositivo.

Si el dispositivo tiene una compilación de sistema operativo antes de la [Actualización de mayo de 2004](hololens-release-notes.md#windows-holographic-version-2004), siga los siguientes pasos que se indican a continuación.

1. Active HoloLens y conéctelo a un equipo.
2. El dispositivo debería aparecer en el equipo como un dispositivo de almacenamiento de archivos.
3. Copie el paquete de aprovisionamiento al dispositivo
4. Conecte el cable de Ethernet al concentrador.
5. Conecte el concentrador USB-C al dispositivo HoloLens.
6. Póngase HoloLens 2
7. Pulse el botón de **Bajar volumen y encender** para aplicar el paquete de aprovisionamiento.
8. El técnico ya puede seguir OOBE y, una vez completada, abrir la aplicación Configuración y recuperar la dirección MAC del dispositivo.

### <a name="benefits"></a>Ventajas

De esta forma, con un &quot;simple toque &quot;del dispositivo, se puede aplicar el paquete de aprovisionamiento correcto y recoger la dirección MAC del dispositivo. [Los paquetes de aprovisionamiento se pueden ser creados siguiendo las instrucciones aquí.](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="autopilot-with-intune-enrollment"></a>Autopiloto con inscripción de Intune

### <a name="requirements"></a>Requisitos

- Puerto de red conectado con acceso a la red del cliente
- Dispositivos HoloLens que ejecutan Windows Holographic 2004
- Adaptador de Ethernet USB-C compatible con HoloLens
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

### <a name="process"></a>Proceso

1. Conecte el cable de ethernet al adaptador y conecte el adaptador al puerto USB-C en el dispositivo HoloLens 2.
2. Active el HoloLens 2
3. El dispositivo debería conectarse automáticamente a Internet durante OOBE a través del adaptador Ethernet. Debería detectar la configuración de Autopilot y registrarse automáticamente con Azure AD e Intune.
4. El dispositivo aplicará los certificados Wi-Fi necesarios y otras opciones de configuración que sean necesarios mediante Intune.
5. Una vez finalizado, el técnico podrá cargar el portal de Intune (Endpoint Manager) y profundizar en la página de propiedades del dispositivo, en **Inicio -> Dispositivos -> NombreDispositivo -> Hardware**
6. La dirección de MAC WiFi estará visible en el portal de Intune.

![Dirección MAC a través de Intune](images/mac-address-intune.jpg)

7. El técnico agregará esta dirección MAC como dispositivo permitido.

### <a name="benefits"></a>Ventajas

Esto permitirá una experiencia de implementación &quot;sin contacto&quot; para el técnico, en la que el dispositivo pueda inscribirse directamente en Azure AD e Intune sin que el técnico tenga que llevar el dispositivo o interactuar manualmente con el entorno del HoloLens.

## <a name="reporting-of-mac-addresses-to-the-technician"></a>Informar de las direcciones MAC al técnico

### <a name="requirements"></a>Requisitos

- Autorización de &quot;Intune Graph Powershell&quot; en el espacio empresarial del cliente
- Instalación de Intune Graph Powershell en el equipo del técnico.
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

### <a name="process"></a>Proceso

Una vez que haya completado la inscripción en Intune, el técnico ejecutaría el script anterior para recuperar la dirección MAC.
