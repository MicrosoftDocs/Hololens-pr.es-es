---
title: Administrar actualizaciones de HoloLens
description: Los administradores pueden usar la administración de dispositivos móviles para administrar las actualizaciones de los dispositivos HoloLens.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 03/24/2020
ms.reviewer: jarrettr
manager: jarrettr
ms.custom:
- CI 115825
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 3de48a913779f124c1cee21791af256a41bf45f8
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828616"
---
# Administrar actualizaciones de HoloLens

HoloLens usa Windows Update de la misma manera que otros dispositivos con Windows 10. Cuando una actualización esté disponible, se descargará e instalará automáticamente la próxima vez que el dispositivo se conecte a Internet. En este artículo se describe cómo administrar actualizaciones en un entorno empresarial u otro administrado. Para obtener información sobre cómo administrar las actualizaciones de los dispositivos HoloLens individuales, vea [Actualizar HoloLens](hololens-update-hololens.md).

## Administrar las actualizaciones automáticamente

Windows Holographic empresarial puede usar [Windows Update empresarial](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) para administrar las actualizaciones. Todos los dispositivos HoloLens 2 pueden usar Windows Holographic empresarial. Asegúrese de que usan Windows Holographic empresarial compilación 10.0.18362.1042 o una compilación superior. Si tiene dispositivos HoloLens (1ª gen.), debe [actualizarlos a Windows Holographic empresarial](hololens1-upgrade-enterprise.md) para administrar sus actualizaciones.

Windows Update empresarial conecta dispositivos HoloLens directamente al servicio de Windows Update. Al usar Windows Update empresarial, podrá controlar varios aspectos del proceso de actualización&mdash;es decir, los dispositivos que obtienen las actualizaciones en cada momento. Por ejemplo, puede lanzar actualizaciones en un subconjunto de dispositivos para probarlos y luego desplegar las actualizaciones a los dispositivos restantes en una fecha posterior. O puede definir diferentes programaciones de actualización para diferentes tipos de actualizaciones.

> [!NOTE]  
> Para los dispositivos HoloLens, puede administrar automáticamente las actualizaciones de características (publicadas dos veces al año) y las actualizaciones de calidad (publicadas mensualmente o si es necesario, incluyendo las actualizaciones de seguridad críticas). Para obtener más información sobre los tipos de actualización, vea [Tipos de actualizaciones administradas por Windows Update empresarial](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).

Puede configurar las opciones de configuración de Windows Update empresarial para HoloLens mediante las directivas en una solución de administración de dispositivos móviles (MDM) como Microsoft Intune.

Para obtener una explicación detallada sobre cómo usar Intune para configurar Windows Update empresarial, vea [Administrar actualizaciones de software de Windows 10 en Intune](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure).

> [!IMPORTANT]  
> Intune ofrece dos tipos de directivas para administrar las actualizaciones: *Círculo de actualizaciones de Windows 10* y *Actualizaciones de características de Windows 10*. El tipo de directiva de actualización de características de Windows 10 en la versión preliminar pública en este momento no es compatible con HoloLens.
>  
> Puede usar las directivas de circulo de actualización de Windows 10 para administrar las actualizaciones de HoloLens 2.

### Configurar directivas de actualización para HoloLens 2 u HoloLens (1ª gen.)

Esta sección describe las directivas que puede usar para administrar las actualizaciones de HoloLens 2 u HoloLens (1ª gen). Para obtener información sobre la funcionalidad adicional que está disponible para HoloLens 2, vea [Planificar y configurar los lanzamientos de actualizaciones para HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).

El [Proveedor de servicios de configuración de directivas (CSP)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) define las directivas que configuran Windows Update empresarial.

> [!NOTE]  
> Para obtener más información sobre las directivas específicas que son compatibles con las ediciones específicas de HoloLens, vea [Directivas compatibles con dispositivos HoloLens](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-hololens-devices).

#### Configure las comprobaciones automáticas para las actualizaciones

Puede usar la directiva **Update/AllowAutoUpdate** para administrar el comportamiento de las actualizaciones automáticas así como analizar, descargar e instalar actualizaciones.

Esta directiva admite los siguientes valores:

- **0**: notifica al usuario cuando hay una actualización que esté lista para ser descargada y que se aplique al dispositivo.
- **1**: instala automáticamente la actualización y luego notifica al usuario que debe programar un reinicio del dispositivo.  
- **2**: instala automáticamente la actualización y reinicia el dispositivo. Este es el valor recomendado y es el valor predeterminado de esta directiva.  

- **3**: instala automáticamente la actualización y luego reinicia en un momento determinado. Determina el día y la hora de la instalación. Si no se determina el día y la hora, el valor predeterminado será 3 a. m. diariamente  

- **4**: instala automáticamente la actualización y luego reinicia el dispositivo. Esta opción también establece la página de configuración como de solo lectura.

- **5**: desactivar las actualizaciones automáticas.

Para obtener más información sobre la configuración disponible para esta directiva, vea [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> En Microsoft Intune, puede usar **comportamiento de actualización automática** para cambiar esta directiva. Para obtener más información, vea [Administrar las actualizaciones de software en Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).

#### Configurar una programación de actualización

Para configurar cómo y cuándo se aplican las actualizaciones, use las siguientes directivas:

- [Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday).  
   - Valores: **0**–**7** (0 = todos los días, 1 = domingo, 7 = sábado)
   - Valor predeterminado: **0** (todos los días)
- [Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime).
   - Valores: entre 0–23 (0 = medianoche, 23 = 11 p. m.)
   - Valor predeterminado: 3 p. m.

#### Solo para dispositivos que ejecutan Windows 10, versión 1607

Puede usar las siguientes directivas de actualización para configurar dispositivos para recibir actualizaciones de Windows Server Update Services (WSUS), en lugar de Windows Update:

- [Update/AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Actualización/UpdateServiceUrl](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### Planificar y configurar los lanzamientos de actualizaciones para HoloLens 2

HoloLens 2 admite más características de automatización de las actualizaciones que HoloLens (1º gen.). especialmente si usa Microsoft Intune para administrar la directiva de Windows Update empresarial. Esta características hacen que sea más fácil planificar e implementar los lanzamientos de actualizaciones en toda su organización.

#### Planificar la estrategia de actualización

Las actualizaciones de Windows empresarial admiten directivas de fraccionamiento. Después de que Microsoft publica una actualización, puede usar una directiva de fraccionamiento para definir cuánto tiempo debe esperar antes de instalar esa actualización en los dispositivos. Al asociar subconjuntos de sus dispositivos (conocidos como *círculos de actualización*) con diferentes directivas de fraccionamiento, puede coordinar una estrategia de lanzamiento de actualizaciones para su organización.

Por ejemplo, imagine una organización que tiene 1 000 dispositivos y tiene que actualizarlos de cinco formas. La organización puede crear cinco círculos de actualización, como se muestra en la siguiente tabla.

|Grupo |Número de dispositivos |Fraccionamiento (días) |
| ---| :---: | :---: |
|Grp 1 (personal de TI) |5 |0 |
|Grp 2 (usuarios pioneros) |50 |60 |
|Grp 3 (principal 1) |250 |120 |
|Grp 4 (principal 2) |300 |150 |
|Grp 5 (principal 3) |395 |180 |

Aquí se muestra cómo progresa el lanzamiento a lo largo del tiempo para toda la organización.

![Línea de tiempo para implementar actualizaciones](./images/hololens-updates-timeline.png)

#### Configurar una directiva de fraccionamiento de actualización

Una directiva de fraccionamiento especifica el número de días entre la fecha en la que una actualización está disponible y la fecha en que se ofrece una actualización a un dispositivo.

Puede configurar diferentes fraccionamientos para actualizaciones de características y actualizaciones de calidad. En la siguiente tabla se enumeran las directivas específicas que puede usar para cada tipo, así como el máximo fraccionamiento para cada uno.

|Categoría |Directiva |Aplazamiento máximo |
| --- | --- | --- |
|Actualizaciones de características |DeferFeatureUpdatesPeriodInDays |365 días |
|Actualizaciones de calidad |DeferQualityUpdatesPeriodInDays |30 días |

####  Ejemplos: uso de Intune para administrar las actualizaciones

**Ejemplo 1: crear y asignar un círculo de actualización**

Para obtener una versión más detallada de este ejemplo, vea [Crear y asignar círculos de actualización](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) y desplácese hasta los perfiles de Intune.
1. Seleccione **Actualizaciones de software** > **Círculos de actualización de Windows 10** > **Crear**.
1. En **Datos básicos**, especifique un nombre y una descripción (opcional) y, a continuación, seleccione **Siguiente**.
1. En **Configuración de círculo de actualización** para **Canal de mantenimiento**, seleccione **Canal semestral** y a continuación cambie el **Periodo de fraccionamiento de actualización de características** a **120**. A continuación, seleccione **Siguiente**.
1. En **Asignaciones**, seleccione **+ Seleccionar grupos para incluir** y, a continuación, asigne el círculo de actualizaciones a uno o más grupos. Use **+ Seleccionar grupos para excluir** para ajustar las asignaciones. A continuación, seleccione **Siguiente**.
1. En **Revisar + crear**, revise la configuración. Cuando esté listo para guardar la configuración del círculo de actualización, seleccione **Crear**.

La lista de círculos de actualización ahora incluyen el nuevo círculo de actualización Windows 10.

**Ejemplo 2: pausar un círculo de actualización**

Si se produce un problema al implementar una actualización de característica o calidad, puede pausar la actualización durante 35 días (a partir de la fecha determinada). Esta pausa impide que otros dispositivos instalen la actualización hasta que usted resuelva o mitigue el problema. Si pausa una actualización de características, las actualizaciones de calidad se seguirán ofreciendo a los dispositivos para asegurar que permanezcan seguras. Después de que transcurra el tiempo especificado, la pausa caduca automáticamente. A partir de ese momento, se reanuda el proceso de actualización.

Para pausar un círculo de actualizaciones en Intune, siga estos pasos:

1. En la página de introducción del círculo de actualizaciones, seleccione **Pausar**.
1. Seleccione el tipo de actualización (**Característica** o **Calidad**) para pausar y, a continuación, seleccione **Aceptar**.

Cuando un tipo de actualización está en pausa, el panel de información general del círculo muestra el número de días que quedan antes de que ese tipo de actualización se reanude.

Mientras el círculo de actualización está en pausa, puede seleccionar cualquiera de las siguientes opciones:

- Para extender el período de pausa de un tipo de actualización para 35 días, seleccione **Extender**.
- Para restaurar las actualizaciones del círculo a la operación activa, seleccione **Reanudar**. Puede volver a pausar el círculo de actualizaciones si es necesario.

> [!NOTE]  
> La operación **Desinstalar** para círculos de actualización no es compatible con los dispositivos HoloLens 2.

## Comprobar actualizaciones manualmente

Aunque HoloLens comprueba periódicamente las actualizaciones del sistema para que no tenga que hacerlo usted, es posible que haya casos en los que desee realizar una comprobación manual.

Para comprobar las actualizaciones manualmente, vaya a **Configuración** > **Actualización y seguridad** > **Comprobar actualizaciones**. Si la aplicación configuración indica que su dispositivo está actualizado, tiene todas las actualizaciones que está disponible actualmente.

## Revertir una actualización manualmente

En algunos casos, es posible que quiera volver a una versión anterior del software HoloLens. El proceso para realizar esto depende de si usa HoloLens 2 u HoloLens (1º gen).

### Volver a una versión anterior (HoloLens 2)

Puede revertir las actualizaciones y volver a una versión anterior de HoloLens 2 usando la herramienta de recuperación avanzada para restablecer HoloLens a la versión anterior.

> [!NOTE]
> Si revierte a una versión anterior, se eliminará su configuración y archivos personales.

Para volver a una versión anterior de HoloLens 2, siga estos pasos:

1. Asegúrese de que no haya ningún teléfono o dispositivo Windows conectado a su equipo.
1. En su equipo, descargue el [Herramienta de recuperación avanzada](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) de Microsoft Store.
1. Descarga la [versión más reciente de HoloLens 2](https://aka.ms/hololens2download).
1. Cuando haya terminado estas descargas, abra el **Explorador de archivos** > **Descargas**, haga clic con el botón derecho en la carpeta comprimida (en zip) que acaba de descargar y seleccione **Extraer todo** > **Extraer** para expandir el archivo.
1. Use un cable USB-A y USB-C para conectar su dispositivo HoloLens al equipo. Incluso si ha estado usando otros cables para conectar su HoloLens, este es el que mejor funciona
1. La herramienta de recuperación avanzada detecta automáticamente su dispositivo HoloLens. Seleccione el icono de **Microsoft HoloLens**
1. En la siguiente pantalla, seleccione **Selección manual de paquetes** y, a continuación, abra la carpeta que expandió previamente. 
1. Seleccione el archivo de instalación (el archivo que tiene una extensión .ffu).
1. Seleccione **Instalar software** y siga las instrucciones.

### Volver a una versión anterior (HoloLens (1ª gen.)).

Puede revertir las actualizaciones y volver a una versión anterior de HoloLens (1ª gen.) usando Windows Device Recovery Tool para restablecer su HoloLens a la versión anterior.

> [!NOTE]
> Si revierte a una versión anterior, se eliminará su configuración y archivos personales.

Para volver a una versión anterior de HoloLens (1ª gen.), siga estos pasos:

1. Asegúrese de que no haya ningún teléfono o dispositivo Windows conectado a su equipo.
1. En su equipo, descargue [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)
1. Descargue el [Paquete de recuperación de la actualización de aniversario de HoloLens](https://aka.ms/hololensrecovery).
1. Cuando haya terminado estas descargas, abra el **Explorador de archivos** > **Descargas**, haga clic con el botón derecho en la carpeta comprimida (en zip) que acaba de descargar y seleccione **Extraer todo** > **Extraer** para expandir el archivo.
1. Use el cable micro-USB que vino con su dispositivo HoloLens para conectarlo a su equipo. Incluso si ha estado usando otros cables para conectar su HoloLens, este es el que mejor funciona.
1. WDRT detecta automáticamente su dispositivo HoloLens. Seleccione el icono de **Microsoft HoloLens**
1. En la siguiente pantalla, seleccione **Selección manual de paquetes** y, a continuación, abra la carpeta que expandió previamente. 
1. Seleccione el archivo de instalación (el archivo que tiene una extensión .ffu).
1. Seleccione **Instalar software** y siga las instrucciones.

> [!NOTE]
> Si el WDRT no detecta su dispositivo HoloLens, pruebe a reiniciar su equipo. Si esto no funciona, seleccione **No se ha detectado Mi dispositivo**, **Microsoft HoloLens** y, a continuación, siga las instrucciones.

## Artículos relacionados

- [Implementar actualizaciones con Windows Update para empresas](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [Asignar dispositivos a las ramas de mantenimiento de actualizaciones de Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Administrar actualizaciones de software de Windows 10 en Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
