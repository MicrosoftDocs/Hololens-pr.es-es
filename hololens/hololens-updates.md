---
title: Administración de actualizaciones de HoloLens
description: Descubra cómo sus administradores pueden usar la administración de dispositivos móviles para administrar las actualizaciones de dispositivos HoloLens.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 10/12/2021
ms.reviewer: jarrettr
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 854e867238de6c87732970fba75abdc8e1fb2c64
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924338"
---
# <a name="manage-hololens-updates"></a>Administración de actualizaciones de HoloLens

HoloLens usa Windows Update de la misma manera que otros dispositivos con Windows 10. Cuando haya una actualización disponible, se descargará e instalará automáticamente la próxima vez que el dispositivo se encienda y se conecte a Internet. En este artículo se describe cómo administrar actualizaciones en una empresa u otro entorno administrado. Para obtener información sobre cómo administrar las actualizaciones de dispositivos HoloLens específicos, consulte [Actualizar el HoloLens](hololens-update-hololens.md).

## <a name="manage-updates-automatically"></a>Administrar las actualizaciones automáticamente

### <a name="managing-updates-by-using-windows-update-for-business"></a>Administración de las actualizaciones con Windows Update para empresas

Windows Holographic for Business puede usar [Windows Update para empresas](/windows/deployment/update/waas-manage-updates-wufb) con el fin de administrar las actualizaciones. Todos los dispositivos HoloLens 2 pueden usar Windows Holographic for Business. Asegúrese de que usen 10.0.18362.1042 o una compilación posterior de Windows Holographic for Business. Si tiene dispositivos HoloLens (1.ª generación), tendrá que [actualizarlo a Windows Holographic for Business](hololens1-upgrade-enterprise.md) para administrar sus actualizaciones.

Windows Update para empresas conecta los dispositivos HoloLens directamente al servicio Windows Update. Usando Windows Update para empresas, puede controlar varios aspectos del proceso de actualización &mdash;es decir, los dispositivos que obtienen actualizaciones en cada momento—. Por ejemplo, puede lanzar actualizaciones en un subconjunto de dispositivos para probarlas y lanzarlas posteriormente en los dispositivos restantes. También puede definir diferentes programaciones de actualización para diferentes tipos de actualizaciones.

> [!NOTE]  
> En el caso de los dispositivos HoloLens, puede administrar automáticamente las actualizaciones de características (publicadas dos veces al año) y las actualizaciones de calidad (publicadas mensualmente o cuando sea necesario, incluidas actualizaciones de seguridad críticas). Para obtener más información sobre los tipos de actualizaciones, consulte [Tipos de actualizaciones administradas por Windows Update para empresas](/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).

Puede configurar las opciones de Windows Update para empresas con relación a HoloLens usando directivas en una solución de administración de dispositivos móviles (MDM) como Microsoft Intune.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>Administración de Windows Update para empresas con Microsoft Intune

Para obtener una explicación detallada sobre cómo usar Intune para configurar Windows Update para empresas, consulte [Administración de actualizaciones de software Windows 10 en Intune](/intune/protect/windows-update-for-business-configure). Para obtener más información sobre la funcionalidad específica de Intune que admite HoloLens, consulte [Funciones de administración de actualizaciones de Intune compatibles con HoloLens](#intune-update-management-functions-that-hololens-supports).

> [!IMPORTANT]  
> Intune proporciona dos tipos de directivas para administrar actualizaciones: *anillo de actualización de Windows 10* y *actualización de características de Windows 10*. En estos momentos, el tipo de directivas de actualización de características de Windows 10 está en la versión preliminar pública y no es compatible con HoloLens.
>  
> Puede usar las directivas de anillo de actualización de Windows 10 para administrar las actualizaciones de HoloLens 2.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>Configurar directivas de actualización para dispositivos HoloLens 2 o HoloLens (1.ª generación)

En esta sección se describen las directivas que puede usar para administrar las actualizaciones de dispositivos HoloLens 2 o HoloLens (1.ª generación). Para obtener más información sobre la funcionalidad disponible para HoloLens 2, consulte [Planificar y configurar los lanzamientos de actualizaciones para HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).

En [CSP de directiva: actualización](/windows/client-management/mdm/policy-csp-update) se definen las directivas que configuran Windows Update para empresas.

> [!NOTE]  
> Para obtener una lista de proveedores de servicios de configuración de directivas (CSP) específicos que sean compatibles con ediciones concretas de HoloLens, consulte [CSP de directivas compatibles con dispositivos HoloLens](/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices).

#### <a name="configure-automatic-checks-for-updates"></a>Configurar búsquedas automáticas de actualizaciones

Puede usar la directiva **Update/AllowAutoUpdate** para administrar el comportamiento de las actualizaciones automáticas, así como para analizar, descargar e instalar actualizaciones. Para obtener más información sobre la configuración disponible para esta directiva, consulte [Update/AllowAutoUpdate](/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> En Microsoft Intune, puede usar el **comportamiento de actualización automática** para cambiar esta directiva. Para obtener más información, vea [Administración de actualizaciones de software de Windows 10 en Intune](/intune/windows-update-for-business-configure).

#### <a name="configure-an-update-schedule"></a>Configurar una programación de actualizaciones

Para configurar cómo y cuándo se aplican las actualizaciones, use las siguientes directivas:

- [Update/ScheduledInstallDay](/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Valores: **0**-**7** (0 = todos los días; 1 = domingos; y 7 = sábados)
  - Valor predeterminado: **0** (todos los días)
- [Update/ScheduledInstallTime](/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Valores: 0-23 (0 = medianoche y 23 = 23:00)
  - Valor predeterminado: 3:00

#### <a name="configure-active-hours"></a>Configurar las horas activas
A partir de la [versión 20H2 de Windows Holographic](hololens-release-notes.md#windows-holographic-version-20h2), un administrador de TI puede especificar el intervalo de horas activas de dispositivos HoloLens 2.

Las horas activas identifican el período en el que se prevé que el dispositivo estará en uso. Los reinicios automáticos posteriores a una actualización se producirán fuera de las horas activas. El intervalo especificado se contará desde la hora de inicio de las horas activas. Puede usar MDM, tal y como se describe en [Configurar las horas activas con MDM](/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm). MDM usa las opciones "Update/ActiveHoursStart", "Update/ActiveHoursEnd" y "Update/ActiveHoursMaxRange" en el CSP de directivas para configurar las horas activas.

-   [Update/ActiveHoursEnd:](/windows/client-management/mdm/policy-csp-update#update-activehoursend) este valor establece la hora de finalización. Hay un máximo de 12 horas desde la hora de inicio.
    -   Los valores admitidos son de 0 a 23, donde 0 son las 0:00, 1, la 1:00, etc.
    -   El valor predeterminado es 17 (17:00).
-   [Update/ActiveHoursMaxRange:](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) este valor establece el número máximo de horas activas desde la hora de inicio.
    -   Los valores admitidos son de 8 a 18.
    -   El valor predeterminado es 18 (horas).
-   [Update/ActiveHoursStart:](/windows/client-management/mdm/policy-csp-update#update-activehoursstart) este valor establece la hora de inicio. Hay un máximo de 12 horas desde la hora de finalización.
    -   Los valores admitidos son de 0 a 23, donde 0 son las 0:00, 1, la 1:00, etc.
    -   El valor predeterminado es 8 (8:00).

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>Solo en el caso de dispositivos que ejecuten Windows 10, versión 1607

Puede usar las siguientes directivas de actualización para configurar dispositivos, con el fin de recibir actualizaciones de Windows Server Update Services (WSUS) en lugar de Windows Update:

- [Update/AllowUpdateService](/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Actualización/UpdateServiceUrl](/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

#### <a name="improved-update-restart-detection-and-notifications"></a>Mejora en las notificaciones y la detección de reinicio de actualizaciones

- Introducido en la [versión 21H2 de Windows Holographic](hololens-release-notes.md#windows-holographic-version-21h2).

Entre las horas activas y las directivas de tiempo de instalación, es posible evitar el reinicio de los dispositivos HoloLens cuando están en uso. Sin embargo, también se podría retrasar la adopción de actualizaciones si no se producen los reinicios para completar la instalación de una actualización obligatoria. Hemos agregado directivas para permitir que el equipo de TI aplique las fechas límite y los reinicios obligatorios y garantice que la instalación de una actualización se complete de forma oportuna. Los usuarios pueden recibir una notificación antes de que se inicie el reinicio y pueden retrasar el reinicio de acuerdo con la directiva de TI.

Se agregaron las siguientes directivas de actualización:

- [Update/AutoRestartNotificationSchedule](/windows/client-management/mdm/policy-csp-update#update-autorestartnotificationschedule)
- [Update/AutoRestartRequiredNotificationDismissal](/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
- [Update/ConfigureDeadlineForFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)
- [Update/ConfigureDeadlineForQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)
- [Update/ConfigureDeadlineGracePeriod](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)
- [Update/ConfigureDeadlineNoAutoReboot](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)
- [Update/ScheduleImminentRestartWarning](/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)
- [Update/ScheduleRestartWarning](/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)
- [Update/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>Planificar y configurar los lanzamientos de actualizaciones para HoloLens 2

HoloLens 2 admite más características de automatización de actualizaciones que HoloLens (1.ª generación), especialmente si usa Microsoft Intune para administrar las directivas de Windows Update para empresas. Estas características hacen que sea más fácil planificar e implementar los lanzamientos de actualizaciones en toda su organización.

#### <a name="plan-the-update-strategy"></a>Planificar la estrategia de actualización

Windows Update para empresas admite directivas de aplazamiento. Cuando Microsoft publica una actualización, se puede usar una directiva de aplazamiento para definir cuánto tiempo se debe esperar antes de instalar la actualización en los dispositivos. Asociando subconjuntos de sus dispositivos (también conocidos como *anillos de actualización*) a diferentes directivas de aplazamiento, puede coordinar una estrategia de lanzamiento de actualizaciones para su organización.

Por ejemplo, imagine una organización que cuente con 1000 dispositivos y tenga que actualizarlos en cinco fases. La organización puede crear cinco anillos de actualización, tal y como se muestra en la siguiente tabla.

|Group (Grupo) |Número de dispositivos |Aplazamiento (días) |
| ---| :---: | :---: |
|Grupo 1 (personal de TI) |5 |0 |
|Grupo 2 (usuarios pioneros) |50 |60 |
|Grupo 3 (principal 1) |250 |120 |
|Grupo 4 (principal 2) |300 |150 |
|Grupo 5 (principal 3) |395 |180 |

A continuación se muestra el progreso del lanzamiento a lo largo del tiempo para toda la organización.

![Línea de tiempo para implementar actualizaciones.](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>Configurar una directiva de aplazamiento de actualizaciones

Una directiva de aplazamiento especifica el número de días entre la fecha en que una actualización está disponible y la fecha en que se ofrece esa actualización a un dispositivo.

Puede configurar diferentes aplazamientos para actualizaciones de características y actualizaciones de calidad. En la siguiente tabla se enumeran las directivas específicas que puede usar para cada tipo, así como el máximo aplazamiento para cada uno de ellos.

|Category |Directiva |Aplazamiento máximo |
| --- | --- | --- |
|Actualizaciones de características |DeferFeatureUpdatesPeriodInDays |365 días |
|Actualizaciones de calidad |DeferQualityUpdatesPeriodInDays |30 días |

#### <a name="pause-updates-via-device"></a>Pausar actualizaciones a través del dispositivo

Si un usuario no tiene acceso a MDM, puede pausar manualmente actualizaciones por separado durante un máximo de 35 días en un dispositivo HoloLens 2 con la compilación de la [versión 2004 de Windows Holographic](hololens-release-notes.md#windows-holographic-version-2004) u otra posterior. Para llegar a esta opción, los usuarios deben ir a **Configuración > Actualización y seguridad > Opciones avanzadas**, desplazarse hacia abajo hasta **Pausar actualizaciones** y seleccionar la fecha hasta la que quieran tener pausadas las actualizaciones. Una vez que el usuario haya alcanzado el límite de pausa, el dispositivo tendrá que obtener nuevas actualizaciones antes de que pueda pausarse de nuevo. 

A partir de la [versión 20H2 de Windows Holographic](hololens-release-notes.md#windows-holographic-version-20h2), la función de pausa de actualizaciones se puede administrar para dispositivos HoloLens 2. 
- [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (valor predeterminado): habilitada
    - 1: deshabilitada

#### <a name="intune-update-management-functions-that-hololens-supports"></a>Funciones de administración de actualizaciones de Intune compatibles con HoloLens

Puede usar las siguientes funciones de administración de actualizaciones de Intune para administrar las actualizaciones de HoloLens.

- **Crear** y **Asignar**: estas funciones agregan un anillo de actualización de Windows 10 a la lista de anillos de actualización. Para obtener más información, consulte [Crear y asignar anillos de actualización](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).

- **Pausar**: si se produce un problema al implementar una actualización de características o de calidad, puede pausar la actualización durante 35 días (a partir de la fecha especificada). Esta pausa impide que otros dispositivos instalen la actualización hasta que usted resuelva o mitigue el problema. Si pausa una actualización de características, las actualizaciones de calidad se seguirán ofreciendo a los dispositivos para que no dejen de estar protegidos. Cuando se pausa un tipo de actualización, el panel Información genera de ese anillo muestra cuántos días quedan antes de que se reanude ese tipo de actualización. Una vez que transcurra el tiempo especificado, la pausa caducará automáticamente y el proceso de actualización se reanudará.

  Mientras el anillo de actualización está pausado, puede seleccionar cualquiera de las siguientes opciones:

  - **Ampliar**: amplía el período de pausa de un tipo de actualización durante 35 días.
  - **Reanudar**: reactiva las actualizaciones del anillo. Puede volver a pausar el anillo de actualización si es necesario.

  > [!NOTE]  
  > La operación **Desinstalar** para anillos de actualización no es compatible con dispositivos HoloLens 2.

### <a name="delivery-optimization-preview"></a>Versión preliminar de la optimización de la distribución

[La versión 21H1 de Windows Holographic](hololens-release-notes.md#windows-holographic-version-21h1) ha habilitado una versión preliminar de la configuración de optimización de la distribución, con el fin de reducir el consumo de ancho de banda para las descargas de varios dispositivos HoloLens. Puede obtener una descripción más completa de esta funcionalidad junto con la configuración de red recomendada en [Optimización de distribución para actualizaciones de Windows 10](/windows/deployment/update/waas-delivery-optimization).

Las siguientes opciones se habilitan como parte de la superficie de administración y [se pueden configurar desde Intune](/mem/intune/configuration/delivery-optimization-settings):

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Algunas advertencias sobre esta oferta en versión preliminar:

- La compatibilidad de HoloLens está limitada en esta versión preliminar a actualizaciones del sistema operativo.
- Windows Holographic for Business solo admite modos de descarga HTTP y descargas desde un [punto de conexión de Caché conectada de Microsoft](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache); en estos momentos no se admiten modos de descarga punto a punto ni asignaciones de grupos para dispositivos HoloLens.
- HoloLens no admite la optimización de la implementación ni de la entrega para puntos de conexión de Windows Server Update Services.
- Para solucionar el problema, será necesario realizar un diagnóstico en el servidor de Caché conectada o recopilar un seguimiento en HoloLens mediante **Configuración** > **Actualización y seguridad** >  **Solución de problemas** >  **Windows Update**.

## <a name="manually-check-for-updates"></a>Buscar actualizaciones manualmente

Aunque HoloLens busca periódicamente actualizaciones del sistema, es posible que haya casos en los que desee realizar una comprobación manual.

Para buscar actualizaciones manualmente, vaya a **Configuración** > **Actualización y seguridad** > **Buscar actualizaciones**. Si la aplicación Configuración indica que su dispositivo está actualizado, tiene todas las actualizaciones disponibles en ese momento.

## <a name="manually-roll-back-an-update"></a>Revertir una actualización manualmente

En algunos casos, es posible que quiera volver a una versión anterior del software de HoloLens. El proceso para realizar esta operación depende de si usa HoloLens 2 u HoloLens (1.ª generación).

### <a name="revert-to-a-previous-version-hololens-2"></a>Volver a una versión anterior (HoloLens 2)

Puede revertir actualizaciones y volver a una versión anterior de HoloLens 2 usando [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab).

> [!NOTE]
> Si vuelve a una versión anterior, se eliminarán su configuración y sus archivos personales.

Para volver a una versión anterior de HoloLens 2, siga estos pasos:

1. Asegúrese de que no haya ningún teléfono o dispositivo Windows conectado a su equipo.
1. En el equipo, descargue [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) en Microsoft Store.
1. Descargue la [versión más reciente de HoloLens 2](https://aka.ms/hololens2download).
1. Una vez que finalicen estas descargas, abra **Explorador de archivos** > **Descargas**, haga clic con el botón derecho en la carpeta comprimida (.zip) que acaba de descargar y, a continuación, seleccione **Extraer todo** > **Extraer** para expandir el archivo.
1. Use un cable de USB-A a USB-C para conectar su dispositivo HoloLens al equipo. Aunque venga utilizando otros cables para conectar el HoloLens, este es el que mejor funciona.
1. Advanced Recovery Companion detecta automáticamente su dispositivo HoloLens. Seleccione el icono **Microsoft HoloLens**.
1. En la siguiente pantalla, seleccione **Selección manual de paquetes** y, a continuación, abra la carpeta que ha expandido anteriormente.
1. Seleccione el archivo de instalación (.ffu).
1. Seleccione **Instalar software** y, a continuación, siga las instrucciones.

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>Volver a una versión anterior (HoloLens [1.ª generación])

Puede revertir actualizaciones y volver a una versión anterior de HoloLens (1.ª generación) usando [Windows Device Recovery Tool](https://support.microsoft.com/help/12379).

> [!NOTE]
> Si vuelve a una versión anterior de HoloLens, se eliminarán su configuración y sus archivos personales.

Para volver a una versión anterior de HoloLens (1.ª generación), siga estos pasos:

1. Asegúrese de que no haya ningún teléfono o dispositivo Windows conectado a su equipo.
1. En el equipo, descargue [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).
1. Descargue el [paquete de recuperación de la actualización de aniversario de HoloLens](https://aka.ms/hololensrecovery).
1. Una vez que finalicen estas descargas, abra **Explorador de archivos** > **Descargas**, haga clic con el botón derecho en la carpeta comprimida (.zip) que acaba de descargar y, a continuación, seleccione **Extraer todo** > **Extraer** para expandir el archivo.
1. Use el cable micro-USB que vino con su dispositivo HoloLens para conectarlo a su equipo. Aunque venga utilizando otros cables para conectar el dispositivo HoloLens, este es el que mejor funciona.
1. WDRT detecta automáticamente su dispositivo HoloLens. Seleccione el icono **Microsoft HoloLens**.
1. En la siguiente pantalla, seleccione **Selección manual de paquetes** y, a continuación, abra la carpeta que ha expandido anteriormente.
1. Seleccione el archivo de instalación (.ffu).
1. Seleccione **Instalar software** y, a continuación, siga las instrucciones.

**Qué hacer si WDRT no detecta su dispositivo**

Si WDRT no detecta su dispositivo HoloLens, pruebe a reiniciar el equipo. En caso de no funcionar, seleccione **No se ha detectado mi dispositivo** y **Microsoft HoloLens**; a continuación, siga las instrucciones.

## <a name="related-articles"></a>Artículos relacionados

- [Notas de la versión de HoloLens 2](hololens-release-notes.md)
- [¿Qué es Windows Update para empresas?](/windows/deployment/update/waas-manage-updates-wufb)
- [Asignar dispositivos a las ramas de mantenimiento de actualizaciones de Windows 10](/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Administración de actualizaciones de software de Windows 10 en Intune](/mem/intune/protect/windows-update-for-business-configure)
