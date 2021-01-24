---
title: Administrar actualizaciones de HoloLens
description: Obtenga información sobre cómo los administradores pueden usar la administración de dispositivos móviles para administrar las actualizaciones de los dispositivos HoloLens.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 10/13/2020
ms.reviewer: jarrettr
manager: jarrettr
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: fa31ab20b149ab62fa59e334f6710b98f2e826ff
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284061"
---
# Administrar actualizaciones de HoloLens

HoloLens usa Windows Update de la misma manera que otros dispositivos con Windows 10. Cuando una actualización esté disponible, se descargará e instalará automáticamente la próxima vez que el dispositivo se conecte a Internet. En este artículo se describe cómo administrar actualizaciones en un entorno empresarial u otro administrado. Para obtener información sobre cómo administrar las actualizaciones de los dispositivos HoloLens individuales, vea [Actualizar HoloLens](hololens-update-hololens.md).

## Administrar las actualizaciones automáticamente

### Administrar las actualizaciones con Windows Update para empresas

Windows Holographic empresarial puede usar [Windows Update empresarial](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) para administrar las actualizaciones. Todos los dispositivos HoloLens 2 pueden usar Windows Holographic empresarial. Asegúrese de que usan Windows Holographic empresarial compilación 10.0.18362.1042 o una compilación superior. Si tiene dispositivos HoloLens (1ª gen.), debe [actualizarlos a Windows Holographic para empresas](hololens1-upgrade-enterprise.md) para administrar sus actualizaciones.

Windows Update empresarial conecta dispositivos HoloLens directamente al servicio de Windows Update. Al usar Windows Update empresarial, podrá controlar varios aspectos del proceso de actualización&mdash;es decir, los dispositivos que obtienen las actualizaciones en cada momento. Por ejemplo, puede lanzar actualizaciones en un subconjunto de dispositivos para probarlos y luego lanzar las actualizaciones a los dispositivos restantes. O puede definir diferentes programaciones de actualización para diferentes tipos de actualizaciones.

> [!NOTE]  
> Para los dispositivos HoloLens, puede administrar las actualizaciones de características automáticamente (publicadas dos veces al año) y las actualizaciones de calidad (publicadas mensualmente o cuando es necesario, incluyendo las actualizaciones de seguridad crítica). Para obtener más información sobre los tipos de actualización, vea [Tipos de actualizaciones administradas por Windows Update empresarial](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).

Puede configurar las opciones de configuración de Windows Update empresarial para HoloLens mediante las directivas en una solución de administración de dispositivos móviles (MDM) como Microsoft Intune.

### Administrar Windows Update para empresas con Microsoft Intune.

Para obtener una explicación detallada sobre cómo usar Intune para configurar Windows Update empresarial, vea [Administrar actualizaciones de software de Windows 10 en Intune](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure). Para obtener más información sobre la funcionalidad de Intune específica compatible con HoloLens, vea [las funciones de administración de actualizaciones de Intune que son compatibles con HoloLens](#intune-update-management-functions-that-hololens-supports).

> [!IMPORTANT]  
> Intune ofrece dos tipos de directivas para administrar las actualizaciones: *el círculo de actualizaciones de Windows 10* y *la actualización de características de Windows 10*. El tipo de directiva de actualización de características de Windows 10 en la versión preliminar pública en este momento no es compatible con HoloLens.
>  
> Puede usar las directivas de circulo de actualización de Windows 10 para administrar las actualizaciones de HoloLens 2.

### Configurar directivas de actualización para HoloLens 2 u HoloLens (1ª gen.)

Esta sección describe las directivas que puede usar para administrar las actualizaciones de HoloLens 2 u HoloLens (1ª gen). Para obtener información sobre la funcionalidad que está disponible para HoloLens 2, vea [Planificar y configurar los lanzamientos de actualizaciones para HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).

[La directiva de CSP - Actualización](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) define las directivas que configuran Windows Update para empresas.

> [!NOTE]  
> Para obtener una lista de los proveedores de servicios de configuración (CSP) de directivas específicos que son compatibles con las ediciones específicas de HoloLens, vea [Directiva de CSP compatible con los dispositivos HoloLens](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices).

#### Configure las comprobaciones automáticas para las actualizaciones

Puede usar la directiva **Update/AllowAutoUpdate** para administrar el comportamiento de las actualizaciones automáticas así como analizar, descargar e instalar actualizaciones. Para obtener más información sobre la configuración disponible para esta directiva, vea [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> En Microsoft Intune, puede usar **comportamiento de actualización automática** para cambiar esta directiva. Para obtener más información, vea [Administrar las actualizaciones de software de Windows 10 en Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).

#### Configurar una programación de actualización

Para configurar cómo y cuándo se aplican las actualizaciones, use las siguientes directivas:

- [Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Valores: **0**–**7** (0 = todos los días, 1 = domingo, 7 = sábado)
  - Valor predeterminado: **0** (todos los días)
- [Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Valores: entre 0–23 (0 = medianoche, 23 = 11 p. m.)
  - Valor predeterminado: 3 p. m.

#### Configurar las horas activas
A partir de la [versión 20H2 de Windows Holographic](hololens-release-notes.md#windows-holographic-version-20h2), un administrador de TI puede especificar el rango de horas activas de los dispositivos HoloLens 2.

Las horas activas identifican el período en el que se prevé que el dispositivo estará en uso. Los reinicios automáticos después de una actualización se producirán fuera de las horas activas. El intervalo especificado se contará desde la hora de inicio de las horas activas. Puede usar MDM, como se describe en [Configurar las horas activas con MDM](https://docs.microsoft.com/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm). MDM usa las opciones Update/ActiveHoursStart y Update/ActiveHoursEnd y Update/ActiveHoursMaxRange en la directiva de CSP para configurar las horas activas.

-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend) : este valor define la hora de finalización. Hay un máximo de 12 horas desde la hora de inicio.
    -   Los valores admitidos son de 0 a 23, donde 0 es 12 a. m., 1 es 1 a. m., etc.
    -   El valor predeterminado es 17 (5 p. m.).
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange): este valor establece el número máximo de horas activas a partir de la hora de inicio.
    -   Los valores admitidos son de 8 a 18.
    -   El valor predeterminado es 18 (horas).
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart) : este valor establece la hora de inicio. Hay un máximo de 12 horas desde la hora de finalización.
    -   Los valores admitidos son de 0 a 23, donde 0 es 12 a. m., 1 es 1 a. m., etc.
    -   El valor predeterminado es 8 (8 a. m.).

#### Solo para dispositivos que ejecutan Windows 10, versión 1607

Puede usar las siguientes directivas de actualización para configurar dispositivos para recibir actualizaciones de Windows Server Update Services (WSUS), en lugar de Windows Update:

- [Update/AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Actualización/UpdateServiceUrl](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### Planificar y configurar los lanzamientos de actualizaciones para HoloLens 2

HoloLens 2 admite más características de automatización de actualizaciones que HoloLens (1º gen.). Esto es así sobre todo si usa Microsoft Intune para administrar las directivas de Windows Update para empresas. Esta características hacen que sea más fácil planificar e implementar los lanzamientos de actualizaciones en toda su organización.

#### Planificar la estrategia de actualización

Las actualizaciones de Windows empresarial admiten directivas de fraccionamiento. Después de que Microsoft publica una actualización, puede usar una directiva de fraccionamiento para definir cuánto tiempo debe esperar antes de instalar esa actualización en los dispositivos. Al asociar subconjuntos de sus dispositivos (también conocidos como *círculos de actualización*) con diferentes directivas de fraccionamiento, puede coordinar una estrategia de lanzamiento de actualizaciones para su organización.

Por ejemplo, imagine una organización que tiene mil dispositivos y tiene que actualizar los dispositivos en cinco grupos. La organización puede crear cinco círculos de actualización, como se muestra en la siguiente tabla.

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

Una directiva de fraccionamiento especifica el número de días que hay entre la fecha en la que una actualización está disponible y la fecha en que se ofrece esa actualización a un dispositivo.

Puede configurar diferentes fraccionamientos para actualizaciones de características y actualizaciones de calidad. En la siguiente tabla se enumeran las directivas específicas que puede usar para cada tipo, así como el máximo fraccionamiento para cada uno.

|Categoría |Directiva |Aplazamiento máximo |
| --- | --- | --- |
|Actualizaciones de características |DeferFeatureUpdatesPeriodInDays |365 días |
|Actualizaciones de calidad |DeferQualityUpdatesPeriodInDays |30 días |

#### Pausar actualizaciones a través del dispositivo

Si un usuario no tiene acceso a MDM puede pausar manualmente las actualizaciones durante un máximo de 35 días en un dispositivo HoloLens 2 en la versión [Windows Holographic, versión 2004](hololens-release-notes.md#windows-holographic-version-2004) o posterior. Los usuarios pueden acceder a esta configuración navegando a **Configuración -> Actualización y seguridad -> Opciones avanzadas** y desplazándose hacia abajo hasta **Pausar las actualizaciones** y seleccione la fecha en la que se detendrán las actualizaciones. Una vez que el usuario ha alcanzado el límite de la pausa, el dispositivo necesita obtener nuevas actualizaciones porque puede volver a pausar. 

A partir de [Windows Holographic, versión 20H2](hololens-release-notes.md#windows-holographic-version-20h2), esta función de pausa se puede administrar desde los dispositivos HoloLens 2. 
- [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (valor predeterminado): habilitado
    - 1: deshabilitado

#### Funciones de administración de actualizaciones de Intune compatibles con HoloLens

Puede usar las siguientes funciones de administración de actualizaciones de Intune para administrar las actualizaciones de HoloLens.

- **Crear** y **asignar**: estas funciones agregan un círculo de actualización de Windows 10 a la lista de círculos de actualización. Para obtener más información, vea [Crear y asignar círculos de actualización](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).

- **Pausa**: si se produce un problema al implementar una actualización de característica o una actualización de calidad, puede pausar la actualización por 35 días (a partir de la fecha especificada). Esta pausa impide que otros dispositivos instalen la actualización hasta que usted resuelva o mitigue el problema. Si pausa una actualización de características, las actualizaciones de calidad se seguirán ofreciendo a los dispositivos para asegurar que permanezcan seguras. Cuando un tipo de actualización está en pausa, el panel de información general del círculo muestra el número de días que quedan antes de que ese tipo de actualización se reanude. Después de que transcurra el tiempo especificado, la pausa caduca automáticamente y el proceso de actualización se reanuda.

  Mientras el círculo de actualización está en pausa, puede seleccionar cualquiera de las siguientes opciones:

  - **Extender**: extiende el período de pausa de un tipo de actualización por 35 días.
  - **Reanudar**: restaura las actualizaciones del círculo a la operación activa. Puede volver a pausar el círculo de actualizaciones si es necesario.

  > [!NOTE]  
  > La operación **Desinstalar** para círculos de actualización no es compatible con los dispositivos HoloLens 2.

## Comprobar actualizaciones manualmente

Aunque HoloLens comprueba periódicamente las actualizaciones del sistema, es posible que haya casos en los que desee realizar una comprobación manual.

Para comprobar las actualizaciones manualmente, vaya a **Configuración** > **Actualización y seguridad** > **Comprobar actualizaciones**. Si la aplicación configuración indica que su dispositivo está actualizado, tiene todas las actualizaciones que está disponible actualmente.

## Revertir una actualización manualmente

En algunos casos, es posible que quiera volver a una versión anterior del software HoloLens. El proceso para realizar esto depende de si usa HoloLens 2 u HoloLens (1º gen).

### Volver a una versión anterior (HoloLens 2)

Puede revertir las actualizaciones y volver a una versión anterior de HoloLens 2 usando la [Herramienta de recuperación avanzada](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) para restablecer HoloLens a la versión anterior.

> [!NOTE]
> Si revierte a una versión anterior, se eliminará su configuración y archivos personales.

Para volver a una versión anterior de HoloLens 2, siga estos pasos:

1. Asegúrese de que no haya ningún teléfono o dispositivo Windows conectado a su equipo.
1. En su equipo, descargue el [Herramienta de recuperación avanzada](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) de Microsoft Store.
1. Descarga la [versión más reciente de HoloLens 2](https://aka.ms/hololens2download).
1. Cuando estas descargas hayan terminado, abra el **Explorador de archivos** > **Descargas**, haga clic con el botón derecho en la carpeta comprimida (.zip) que acaba de descargar y seleccione **Extraer todo** > **Extraer** para expandir el archivo.
1. Use un cable USB-A y USB-C para conectar su dispositivo HoloLens al equipo. Incluso si ha estado usando otros cables para conectar su HoloLens, este es el que mejor funciona
1. La herramienta de recuperación avanzada detecta automáticamente su dispositivo HoloLens. Seleccione el icono de **Microsoft HoloLens**
1. En la siguiente pantalla, seleccione **Selección manual de paquetes** y, a continuación, abra la carpeta que expandió previamente.
1. Seleccione el archivo de instalación (.ffu).
1. Seleccione **Instalar software** y siga las instrucciones.

### Volver a una versión anterior (HoloLens (1ª gen.)).

Puede revertir las actualizaciones y volver a una versión anterior de HoloLens (1ª gen.) usando [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) para restablecer su HoloLens a la versión anterior.

> [!NOTE]
> Si vuelve a una versión anterior de HoloLens, se eliminarán su configuración y archivos personales.

Para volver a una versión anterior de HoloLens (1ª gen.), siga estos pasos:

1. Asegúrese de que no haya ningún teléfono o dispositivo Windows conectado a su equipo.
1. En su equipo, descargue [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)
1. Descargue el [Paquete de recuperación de la actualización de aniversario de HoloLens](https://aka.ms/hololensrecovery).
1. Cuando estas descargas hayan terminado, abra el **Explorador de archivos** > **Descargas**, haga clic con el botón derecho en la carpeta comprimida (.zip) que acaba de descargar y seleccione **Extraer todo** > **Extraer** para expandir el archivo.
1. Use el cable micro-USB que vino con su dispositivo HoloLens para conectarlo a su equipo. Incluso si ha estado usando otros cables para conectar su HoloLens, este es el que mejor funciona.
1. WDRT detecta automáticamente su dispositivo HoloLens. Seleccione el icono de **Microsoft HoloLens**
1. En la siguiente pantalla, seleccione **Selección manual de paquetes** y, a continuación, abra la carpeta que expandió previamente.
1. Seleccione el archivo de instalación (.ffu).
1. Seleccione **Instalar software** y siga las instrucciones.

**Qué hacer si WDRT no detecta su dispositivo**

Si WDRT no detecta su dispositivo HoloLens, pruebe reiniciar su equipo. Si esto no funciona, seleccione **No se ha detectado Mi dispositivo**, **Microsoft HoloLens** y, a continuación, siga las instrucciones.

## Artículos relacionados

- [Notas de la versión de HoloLens 2](https://docs.microsoft.com/hololens/hololens-release-notes)
- [¿Qué es Windows Update para empresas?](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [Asignar dispositivos a las ramas de mantenimiento de actualizaciones de Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Administrar actualizaciones de software de Windows 10 en Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
