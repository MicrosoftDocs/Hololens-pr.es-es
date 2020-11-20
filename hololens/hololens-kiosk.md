---
title: Configurar HoloLens como un quiosco multimedia
description: Usa una configuración de quiosco para bloquear las aplicaciones en HoloLens.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f560dae725cbce8658bdf2a135c5061b5332f797
ms.sourcegitcommit: 456a88907d606f4c4532b153d5a848e214b6b8e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "11182011"
---
# Configurar HoloLens como un quiosco multimedia

Puede configurar un dispositivo HoloLens para que funcione como un dispositivo de propósito fijo, también denominado *quiosco*, configurando el dispositivo para que se ejecute en el modo de pantalla completa. En el modo de pantalla completa, se limitan las aplicaciones (o usuarios) que están disponibles en el dispositivo. El modo de pantalla completa es una característica muy útil que puedes usar para dedicar un dispositivo HoloLens a aplicaciones empresariales o para usar el dispositivo HoloLens en una demostración de la aplicación.

Este artículo proporciona información sobre aspectos de la configuración de quiosco específicos para dispositivos HoloLens. Para obtener información general sobre los distintos tipos de quioscos basados en Windows y cómo configurarlos, vea [configurar quioscos y señales digitales en las ediciones de escritorio de Windows](https://docs.microsoft.com/windows/configuration/kiosk-methods).  

> [!IMPORTANT]  
> El modo de pantalla completa determina qué aplicaciones estarán disponibles cuando un usuario inicie sesión en el dispositivo. Sin embargo, el modo de pantalla completa no es un método de seguridad. No impide que una aplicación "permitida" abra otra aplicación que no está permitida. Para bloquear la apertura de aplicaciones o procesos, use el [CSP control de aplicaciones de Windows Defender (WDAC)](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) para crear las directivas apropiadas.
>
> Obtenga más información sobre los servicios de Microsoft para ofrecer a los usuarios un nivel avanzado de seguridad que usa HoloLens 2, más información sobre las [protecciones de aislamiento de estado y de separación](security-state-separation-isolation.md#defender-protections). U obtenga información sobre cómo [usar WDAC y Windows PowerShell para permitir o bloquear aplicaciones en dispositivos HoloLens 2 con Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

Puede usar el modo de pantalla completa en una sola aplicación o en una configuración de varias aplicaciones, y puede usar uno de los tres procesos para configurar e implementar la configuración de quiosco.

> [!IMPORTANT]  
> Al eliminar la configuración de varias aplicaciones, se eliminan los perfiles de bloqueo de usuario creados por la característica de acceso asignado. Sin embargo, no revierte todos los cambios de la Directiva. Para revertir estas directivas, debe restablecer el dispositivo a la configuración de fábrica.

## Planear la implementación de quiosco

Cuando diseñes tu exposición, necesitarás poder contestar las siguientes preguntas. A continuación se indican algunas decisiones sobre cómo leer esta página y algunas consideraciones para estas preguntas.
1. **¿Quién va a usar su quiosco y qué [tipo de cuenta van a](hololens-identity.md) usar?** Esta es una decisión que probablemente ya haya hecho y que no debe ajustarse con el fin de su exposición, pero afectará a la forma en que se asigna más tarde.
1. **¿Necesita tener quioscos diferentes por usuario/grupo o un quiosco no habilitado para algunos?** Si es así, desearás crear tu quiosco a través de XML. 
1. **¿Cuántas aplicaciones estarán en tu quiosco?** Si tienes más de 1 aplicación, necesitarás un quiosco de varias aplicaciones. 
1. **¿Qué aplicaciones estarán en tu quiosco?** Use nuestra lista de AUMIDs a continuación para agregar las aplicaciones In-Box además de las suyas propias.
1. **¿Cómo se puede planear la implementación de su quiosco?** Si estás inscribiendo un dispositivo en MDM, te sugerimos que uses MDM para implementar tu quiosco. Si no usa MDM, está disponible la implementación con el paquete de aprovisionamiento.  

### Requisitos del modo de pantalla completa

Puede configurar cualquier dispositivo HoloLens 2 para usar el modo de pantalla completa.

> [!IMPORTANT]
> El modo de pantalla completa solo está disponible si el dispositivo tiene Windows Holographic para empresas. Todos los dispositivos HoloLens 2 se distribuyen con Windows Holographic para empresas y no hay otras ediciones. Cada dispositivo HoloLens 2 puede ejecutar el modo de pantalla completa fuera de la caja.
>
> Los dispositivos HoloLens (1. ª gen) deben actualizarse tanto en cuanto a la compilación de OS y OS Edition. Aquí encontrarás más información sobre cómo actualizar una HoloLens (1ª generación) a [Windows Holographic para empresas](hololens1-upgrade-enterprise.md) . Para actualizar un dispositivo HoloLens (1. gen) para usar el modo de pantalla completa, primero debe asegurarse de que el dispositivo ejecute Windows 10, versión 1803 o una versión posterior. Si ha usado la herramienta de recuperación de dispositivos de Windows para recuperar su dispositivo HoloLens (1 ª generación) a su compilación predeterminada o si ha instalado las actualizaciones más recientes, el dispositivo estará listo para configurar.

> [!IMPORTANT]  
> Para ayudar a proteger los dispositivos que se ejecutan en el modo de pantalla completa, considere la posibilidad de agregar directivas de administración de dispositivos que desactiven características, como la conectividad USB. Además, Compruebe la configuración de Update ring para asegurarse de que las actualizaciones automáticas no se realizan durante el horario laboral.

### Decidir entre un quiosco de una sola aplicación o un quiosco de varias aplicaciones

Un quiosco de una sola aplicación inicia la aplicación especificada cuando el usuario inicia sesión en el dispositivo. El menú Inicio está deshabilitado, como es Cortana. Un dispositivo HoloLens 2 no responde al gesto de [Inicio](hololens2-basic-usage.md#start-gesture) . Un dispositivo HoloLens (1. ª gen) no responde al gesto de la [floración](hololens1-basic-usage.md) . Dado que solo se puede ejecutar una aplicación, el usuario no puede colocar otras aplicaciones.

Una pantalla completa de varias aplicaciones muestra el menú Inicio cuando el usuario inicia sesión en el dispositivo. La configuración de quiosco determina qué aplicaciones están disponibles en el menú Inicio. Puede usar una pantalla completa de varias aplicaciones para ofrecer una experiencia de fácil comprensión a los usuarios al presentarles solo las cosas que tienen que usar y quitar las cosas que no necesitan usar.

En la tabla siguiente se enumeran las funciones de las características de los distintos modos de quiosco.

| &nbsp; |Menú Inicio |Menú acciones rápidas |Cámara y vídeo |Miracast |Cortana |Comandos de voz integrados |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|Quiosco de una sola aplicación |Deshabilitada |Deshabilitada   |Deshabilitada |Deshabilitada   |Deshabilitada |Habilitado <sup> 1</sup> |
|Pantalla completa de varias aplicaciones |Habilitado |Habilitado <sup> 2</sup> |Disponible <sup> 2</sup> |Disponible <sup> 2</sup> |Disponible <sup> 2, 3</sup>  |Habilitado <sup> 1</sup> |

> <sup>1 los </sup> comandos de voz relacionados con características deshabilitadas no funcionan.  
> <sup>2 </sup> para obtener más información sobre cómo configurar estas características, vea [seleccionar aplicaciones de quiosco](#plan-kiosk-apps).  
> <sup>3 </sup> incluso si Cortana está deshabilitada, los comandos de voz integrados están habilitados.

En la siguiente tabla se enumeran las características de compatibilidad con usuarios de los diferentes modos de pantalla completa.

| &nbsp; |Tipos de usuarios admitidos | Inicio de sesión automático | Varios niveles de acceso |
| --- | --- | --- | --- |
|Quiosco de una sola aplicación |Cuenta de servicio administrada (MSA) en Azure Active Directory (AAD) o cuenta local |Sí |No |
|Pantalla completa de varias aplicaciones |Cuenta de AAD |No |Sí |

Para obtener ejemplos de cómo usar estas funciones, consulte la tabla siguiente.

|Use una pantalla de una sola aplicación para: |Use una pantalla de varias aplicaciones para: |
| --- | --- |
|Un dispositivo que solo ejecuta una guía de Dynamics 365 para nuevos empleados. |Un dispositivo que ejecuta tanto guías como asistencia remota para un rango de empleados. |
|Un dispositivo que solo ejecuta una aplicación personalizada. |Un dispositivo que funciona como exposición para la mayoría de los usuarios (solo con una aplicación personalizada), pero funciona como un dispositivo estándar para un grupo de usuarios específico. |

### Planear aplicaciones de quiosco

Para obtener información general sobre cómo elegir las aplicaciones de quiosco, consulte [directrices para elegir una aplicación para el acceso asignado (modo de pantalla completa)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app).

Si usas Windows Device portal para configurar un quiosco de una sola aplicación, seleccionas la aplicación durante el proceso de configuración.  

Si usa un sistema de administración de dispositivos móviles (MDM) o un paquete de aprovisionamiento para configurar el modo de pantalla completa, use el [proveedor de servicios de configuración de AssignedAccess (CSP)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) para especificar las aplicaciones. El CSP usa [identificadores de modelo de usuario de la aplicación (AUMIDs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) para identificar las aplicaciones. En la siguiente tabla se enumeran las AUMIDs de algunas aplicaciones en el cuadro que puede usar en una pantalla de varias aplicaciones.

> [!IMPORTANT]
> El modo de pantalla completa determina qué aplicaciones estarán disponibles cuando un usuario inicie sesión en el dispositivo. Sin embargo, el modo de pantalla completa no es un método de seguridad. No impide que una aplicación "permitida" abra otra aplicación que no está permitida. Dado que no limitamos este comportamiento, las aplicaciones pueden iniciarse desde Edge, el explorador de archivos y las aplicaciones de Microsoft Store. Si hay aplicaciones específicas que no desea iniciar desde una exposición, use el [CSP control de aplicaciones de Windows Defender (WDAC)](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) para crear las directivas apropiadas. 
> 
> Además, la casa de realidad mixta no se puede configurar como una aplicación de quiosco.

<a id="aumids"></a>

|Nombre de la aplicación |AUMID |
| --- | --- |
|Visor 3D |Microsoft. Microsoft3DViewer \ _8wekyb3d8bbwe \! Microsoft. Microsoft3DViewer |
|Calendario |Microsoft. windowscommunicationsapps \ _8wekyb3d8bbwe \! Microsoft. windowslive. Calendar |
|Cámara <sup> 1,2</sup> |HoloCamera \ _cw5n1h2txyewy \! HoloCamera |
|Cortana <sup> 3</sup> |Microsoft. 549981C3F5F10 \ _8wekyb3d8bbwe \! Aplicación |
|Selector de dispositivos en HoloLens (1ª generación) |HoloDevicesFlow \ _cw5n1h2txyewy \! HoloDevicesFlow |
|Selector de dispositivos en HoloLens 2 |Microsoft. Windows. DevicesFlowHost \ _cw5n1h2txyewy \! Microsoft. Windows. DevicesFlowHost |
|Dynamics 365 Guides |Microsoft. Dynamics365. Guides \ _8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft. MicrosoftRemoteAssist \ _8wekyb3d8bbwe \! Microsoft. RemoteAssist |
|Centro de opiniones &nbsp; |Microsoft. WindowsFeedbackHub \ _8wekyb3d8bbwe \! Aplicación |
|Explorador de archivos |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Correo |microsoft.windowscommunicationsapps_8wekyb3d8bbwe! Microsoft. windowslive. mail |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast <sup> 4</sup> |&nbsp; |
|Películas y TV |Microsoft. ZuneVideo \ _8wekyb3d8bbwe \! Microsoft. ZuneVideo |
|OneDrive |Microsoft. microsoftskydrive \ _8wekyb3d8bbwe \! Aplicación |
|Fotos |Microsoft. Windows. photos \ _8wekyb3d8bbwe \! Aplicación |
|Configuración |HolographicSystemSettings \ _cw5n1h2txyewy \! Aplicación |
|Sugerencias |Microsoft. HoloLensTips \ _8wekyb3d8bbwe \! HoloLensTips |

> <sup>1 </sup> para habilitar la captura de vídeos o fotos, debe habilitar la aplicación de cámara como una aplicación de quiosco.  
> <sup>2 </sup> cuando habilita la aplicación cámara, tenga en cuenta las siguientes condiciones:
> - El menú acciones rápidas incluye los botones de foto y de vídeo.  
> - También debe habilitar una aplicación (como fotos, correo o OneDrive) que pueda interactuar con imágenes o recuperarlas.  
>  
> <sup>3 </sup> incluso si no habilita Cortana como aplicación de quiosco, los comandos de voz integrados están habilitados. Sin embargo, los comandos relacionados con características deshabilitadas no tienen ningún efecto.  
> <sup>4 </sup> no puede habilitar Miracast directamente. Para habilitar Miracast como una aplicación de quiosco, habilita la aplicación cámara y la aplicación selector de dispositivos.

### Planear perfiles de quiosco para usuarios o grupos

Cuando cree el archivo XML o use la interfaz de usuario de Intune para configurar un quiosco, tendrá que considerar quién será el usuario de la exposición. Una configuración de quiosco puede limitarse a una cuenta individual o a grupos de Azure AD. 

Normalmente, los quioscos se habilitan para un usuario o un grupo de usuarios. Sin embargo, si tiene pensado escribir su propio quiosco XML, es posible que desee considerar el acceso asignado globalmente, en el que el quiosco se aplica en el nivel de dispositivo independientemente de la identidad. Si esta apelación le interesa, [Lea más información sobre los quioscos de acceso asignados global.](hololens-global-assigned-access-kiosk.md)

#### Si va a crear un archivo XML:
-   Puede crear varios perfiles de quiosco y asignarlos a cada uno de los usuarios o grupos. Como un quiosco para el grupo de AAD que tiene muchas aplicaciones y un visitante que tiene un quiosco de varias aplicaciones con una aplicación singular.
-   La configuración de su quiosco se denominará **ID de perfil** y tendrá un GUID.
-   Asignará ese perfil en la sección de configuraciones especificando el tipo de usuario y usando el mismo GUID para el **identificador de DefaultProfile**.
- Se puede crear un archivo XML pero aún se puede aplicar a un dispositivo a través de MDM creando un perfil de configuración de dispositivo URI de OMA personalizado y aplicándolos a grupo de dispositivos HoloLens con el valor de URI:./Device/Vendor/MSFT/AssignedAccess/Configuration

#### Si está creando una exposición en Intune.
-   Cada dispositivo solo puede recibir un perfil de quiosco, de lo contrario creará un conflicto y no recibirá ninguna configuración de quiosco. 
    -   Otros tipos de perfiles y directivas, como las restricciones de dispositivo que no están relacionados con el perfil de configuración de quiosco, no entran en conflicto con el perfil de configuración de quiosco.
-   El quiosco se habilitará para todos los usuarios que formen parte del tipo de inicio de sesión de usuario, que se establecerá con un usuario o un grupo de AAD. 
-   Después de establecer la configuración de quiosco y de seleccionar el **tipo de inicio de sesión de usuario** (usuarios que pueden iniciar sesión en el quiosco) y las aplicaciones, la configuración del dispositivo se debe asignar a un grupo. El grupo o los grupos asignados determinan los dispositivos que reciben la configuración del dispositivo de quiosco, pero no interactúan con si el quiosco está habilitado o no. 
    - Para obtener una explicación completa de los efectos de asignar perfiles de configuración en Intune, consulte [asignar perfiles de usuario y dispositivo en Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).

### Seleccionar un método de implementación

Puede seleccionar uno de los siguientes métodos para implementar la configuración de quiosco:

- [Microsoft Intune u otro servicio de administración de dispositivos móviles (MDM)](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Paquete de aprovisionamiento](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Device Portal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Dado que este método requiere que el modo de desarrollador esté habilitado en el dispositivo, le recomendamos que lo use solo para demostraciones.

En la tabla siguiente se enumeran las capacidades y las ventajas de cada uno de los métodos de implementación.

| &nbsp; |Implementar mediante Windows Device portal |Implementar mediante un paquete de aprovisionamiento |Implementar mediante MDM |
| --------------------------- | ------------- | -------------------- | ---- |
|Implementar quioscos de una sola aplicación   | Sí           | Sí                  | Sí  |
|Implementar quioscos de varias aplicaciones    | No            | Sí                  | Sí  |
|Implementar solo en dispositivos locales | Sí           | Sí                  | No   |
|Implementar mediante el modo de programador |Obligatorio       | No obligatorio            | No obligatorio   |
|Implementación mediante Azure Active Directory (AAD)  | No obligatorio            | No obligatorio                   | Obligatorio  |
|Implementar automáticamente      | No            | No                   | Sí  |
|Velocidad de implementación            | Fast       | Fast                 | Nivel lento |
|Implementar a escala | No recomendado    | Recomendaciones        | Recomendaciones |

## Usar Microsoft Intune u otro MDM para configurar un quiosco de aplicación única o de varias aplicaciones

Para configurar el modo de pantalla completa con Microsoft Intune u otro sistema MDM, siga estos pasos.

1. [Prepararse para inscribir los dispositivos](#mdmenroll).
1. [Crear un perfil de configuración de quiosco](#mdmprofile).
1. Configure el quiosco.
   - [Configure la configuración de una pantalla de una sola aplicación](#mdmconfigsingle).
   - [Configure la configuración de un quiosco de varias aplicaciones](#mdmconfigmulti).
1. [Asigne el perfil de configuración de quiosco a un grupo](#mdmassign).
1. Implementar los dispositivos.
   - [Implementar una pantalla de una sola aplicación](#mdmsingledeploy).
   - [Implementar una pantalla completa de varias aplicaciones](#mdmmultideploy).

### <a id="mdmenroll"></a>MDM, paso 1 &ndash; preparar la inscripción de los dispositivos

Puede configurar su sistema MDM para que inscriba dispositivos HoloLens automáticamente cuando el usuario inicia sesión por primera vez o para que los usuarios inscriban dispositivos de forma manual. Los dispositivos también deben unirse a su dominio de Azure AD y asignarse a los grupos correspondientes.

Para obtener más información sobre cómo inscribir los dispositivos, consulte [inscribir HoloLens en MDM](hololens-enroll-mdm.md) e [Intune para dispositivos Windows](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods).

### <a id="mdmprofile"></a>MDM, paso 2 &ndash; crear un perfil de configuración de quiosco

1. Abra el portal de [Azure](https://portal.azure.com/) y inicie sesión en su cuenta de administrador de Intune.
1. Seleccione **Microsoft Intune**  >  **configuración de dispositivo de**Microsoft Intune:  >  **crear perfil**para perfiles.
1. Escriba un nombre de perfil.
1. Seleccione **Platform**  >  **Windows 10 y versiones posteriores**y, a continuación, seleccione restricciones de dispositivo de **tipo de perfil**  > **Device restrictions**.
1. Seleccione **configurar**  >  **quiosco**y, a continuación, seleccione una de las opciones siguientes:
   - Para crear una pantalla completa de una sola aplicación **Kiosk Mode**, seleccione  >  **pantalla completa de una sola aplicación**en modo de pantalla completa.
   - Para crear una pantalla completa de varias aplicaciones, seleccione pantalla completa de la aplicación en el **modo de pantalla**completa  >  **Multi-app kiosk**.
1. Para empezar a configurar el quiosco, seleccione **Agregar**.

Los pasos siguientes varían según el tipo de quiosco que desee. Para obtener más información, seleccione una de las siguientes opciones:  

- [Quiosco de una sola aplicación](#mdmconfigsingle)
- [Pantalla completa de varias aplicaciones](#mdmconfigmulti)

Para obtener más información sobre cómo crear un perfil de configuración de quiosco, consulte [configuración de dispositivos de Windows 10 y Windows Holographic para la empresa para que se ejecute como un quiosco dedicado con Intune](https://docs.microsoft.com/intune/configuration/kiosk-settings).

### <a id="mdmconfigsingle"></a>MDM, paso 3 (aplicación única) &ndash;  configurar la configuración de una pantalla de una sola aplicación

En esta sección se resume la configuración que necesita una quiosco de una sola aplicación. Para obtener más información, vea los artículos siguientes:

- Para obtener más información sobre cómo configurar un perfil de configuración de quiosco en Intune, consulte [Cómo configurar el modo de pantalla completa con Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Para obtener más información sobre la configuración disponible para quioscos de una sola aplicación en Intune, vea [quioscos únicos de aplicaciones en pantalla completa](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- Para ver otros servicios de MDM, consulte la documentación de su proveedor para obtener las instrucciones. Si tiene que usar una configuración XML personalizada para configurar un quiosco en el servicio MDM, [cree un archivo XML que defina la configuración de quiosco](#ppkioskconfig).

1. Seleccione **Inicio de sesión de usuario**  >  , escriba la**cuenta de usuario local**y, a continuación, escriba el nombre de usuario de la cuenta local (dispositivo) o de la cuenta de Microsoft (MSA) que puede iniciar sesión en el quiosco.
   > [!NOTE]  
   > Los tipos de cuenta de usuario de **Inicio automático** no se admiten en Windows Holographic para empresas.
1. Seleccione **Application type**aplicación  >  de la**tienda**de tipos y, a continuación, seleccione una aplicación de la lista.

El siguiente paso es [asignar](#mdmassign) el perfil a un grupo.

### <a id="mdmconfigmulti"></a>MDM, paso 3 (aplicación múltiple) &ndash; configurar la configuración de un quiosco de varias aplicaciones

En esta sección se resume la configuración que necesita una pantalla completa de aplicaciones múltiples. Para obtener información más detallada, consulte los artículos siguientes:

- Para obtener más información sobre cómo configurar un perfil de configuración de quiosco en Intune, consulte [Cómo configurar el modo de pantalla completa con Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Para obtener más información sobre la configuración disponible para quioscos de varias aplicaciones en Intune, vea [quioscos de varias aplicaciones](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- Para ver otros servicios de MDM, consulte la documentación de su proveedor para obtener las instrucciones. Si necesita usar una configuración XML personalizada para configurar un quiosco en el servicio MDM, [cree un archivo XML que defina la configuración de quiosco](#ppkioskconfig). Si usa un archivo XML, asegúrese de incluir el diseño de [Inicio](#start-layout-for-hololens).  
- De forma opcional, puede usar un diseño de inicio personalizado con Intune u otros servicios de MDM. Para obtener más información, vea [iniciar el archivo de diseño para MDM (Intune y otros)](#start-layout-file-for-mdm-intune-and-others).

1. Seleccione **destino en Windows 10 en dispositivos de modo S**  >  **No**.  
   >[!NOTE]  
   > No se admite el modo S en Windows Holographic para empresas.
1. Seleccione **Inicio de sesión de usuario**  >  , usuario o grupo o **usuario de inicio de sesión**de**Azure ad**  >  , visitante de**HoloLens**y, a continuación, agregue uno o más grupos de usuarios o cuentas.  

   Solo los usuarios que pertenecen a los grupos o cuentas que especifique en el **tipo de inicio de sesión de usuario** pueden usar la experiencia de quiosco.

1. Seleccione una o más aplicaciones con las siguientes opciones:
   - Para agregar una aplicación de línea de negocio cargada, seleccione **Agregar aplicación** de la tienda y, a continuación, seleccione la aplicación que quiera.
   - Para agregar una aplicación especificando su AUMID, seleccione **Agregar mediante AUMID** y, a continuación, escriba la AUMID de la aplicación. [Ver la lista de AUMIDs disponibles](#aumids)

El siguiente paso es [asignar](#mdmassign) el perfil a un grupo.

### <a id="mdmassign"></a>MDM, paso 4 &ndash; asignar el perfil de configuración de quiosco a un grupo

Use la página **asignaciones** del perfil de configuración de quiosco para establecer dónde quiere que se implemente la configuración de quiosco. En el caso más simple, puedes asignar el perfil de configuración de quiosco a un grupo que contendrá el dispositivo HoloLens cuando el dispositivo se inscriba en MDM.

### <a id="mdmsingledeploy"></a>MDM, paso 5 (una sola aplicación) &ndash; implementar una quiosco de una sola aplicación

Al usar un sistema MDM, puede inscribir el dispositivo en MDM durante OOBE. Una vez que haya finalizado OOBE, es fácil iniciar sesión en el dispositivo.

Durante OOBE, siga estos pasos:

1. Inicie sesión con la cuenta que especificó en el perfil de configuración de quiosco.
1. Inscribir el dispositivo. Asegúrese de que el dispositivo se agrega al grupo al que está asignado el perfil de configuración de quiosco.
1. Espere a que OOBE finalice, para que la aplicación de la tienda se descargue e instale, y para que se apliquen las directivas. Después, reinicie el dispositivo.

La próxima vez que inicie sesión en el dispositivo, la aplicación de quiosco debe iniciarse automáticamente.

Si en este momento no ve la configuración de su quiosco, [Compruebe el estado de la asignación](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

### <a id="mdmmultideploy"></a>MDM, paso 5 (varias aplicaciones) &ndash; implementar una quiosco de varias aplicaciones

Al usar un sistema MDM, puede unir el dispositivo a su inquilino de Azure AD e inscribir el dispositivo en MDM durante OOBE. Si corresponde, proporcione la información de inscripción a los usuarios para que estén disponibles durante el proceso de OOBE.

> [!NOTE]  
> Si ha asignado el perfil de configuración de quiosco a un grupo que contiene usuarios, asegúrese de que una de esas cuentas de usuario es la primera cuenta para iniciar sesión en el dispositivo.

Durante OOBE, siga estos pasos:

1. Inicie sesión con la cuenta que pertenece al grupo de **tipos de inicio de sesión de usuario** .
1. Inscribir el dispositivo.
1. Espere a que las aplicaciones que forman parte del perfil de configuración de quiosco se descarguen e instalen. Además, espera a que se apliquen las directivas.  
1. Una vez que haya finalizado OOBE, puede instalar aplicaciones adicionales desde Microsoft Store o mediante la instalación de prueba. [Aplicaciones necesarias](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) para el grupo al que pertenece el dispositivo para instalarse automáticamente.
1. Cuando finalice la instalación, reinicie el dispositivo.

La próxima vez que inicie sesión en el dispositivo con una cuenta que pertenezca al tipo de **Inicio de sesión de usuario**, la aplicación de quiosco se iniciará automáticamente.

Si en este momento no ve la configuración de su quiosco, [Compruebe el estado de la asignación](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

## Usar un paquete de aprovisionamiento para configurar un quiosco de aplicación única o de varias aplicaciones

Para configurar el modo de pantalla completa con un paquete de aprovisionamiento, siga estos pasos.

1. [Cree un archivo XML que defina la configuración de quiosco.](#ppkioskconfig) [Start layout](#start-layout-for-hololens)
2. [Agregue el archivo XML a un paquete de aprovisionamiento.](#ppconfigadd)
3. [Aplicar el paquete de aprovisionamiento a HoloLens.](#ppapply)

### <a id="ppkioskconfig"></a>Paquete de aprovisionamiento, paso 1 &ndash; crear un archivo XML de configuración de quiosco

Siga [las instrucciones generales para crear un archivo XML de configuración de quiosco para el escritorio de Windows](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file), excepto los siguientes:

- No incluya aplicaciones de Windows clásicas (Win32). HoloLens no admite estas aplicaciones.
- Usa el [XML de diseño de inicio de marcador de posición](#start-layout-for-hololens) para HoloLens.
- Opcional: Agregar acceso de invitado a la configuración de quiosco

#### <a id="ppkioskguest"></a>Opcional: Agregar acceso de invitado a la configuración de quiosco

En la [sección de **configuraciones** del archivo XML](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs), puede configurar un grupo especial denominado **Visitor** para permitir que los invitados usen el quiosco. Cuando el quiosco está configurado para admitir al grupo especial de **visitantes** , se agrega una opción de "**invitado**" a la página de inicio de sesión. La cuenta de **invitado** no requiere una contraseña y los datos asociados a ella se eliminan cuando la cuenta cierra sesión.

Para habilitar la cuenta de **invitado** , agregue el siguiente fragmento de código al XML de configuración de quiosco:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a id="start-layout-for-hololens"></a>Diseño de inicio de marcador de posición para HoloLens

Si usa un [paquete de aprovisionamiento](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) para configurar un quiosco de varias aplicaciones, el procedimiento requiere un diseño de inicio. Iniciar la personalización del diseño no se admite en Windows Holographic para empresas. Por lo tanto, tendrá que usar un diseño de inicio de marcador de posición.

> [!NOTE]  
> Dado que un quiosco de una sola aplicación inicia la aplicación de quiosco cuando inicia sesión, no usa el menú Inicio y no es necesario que tenga un diseño de inicio.

> [!NOTE]  
> Si usa [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) para configurar un quiosco de varias aplicaciones, puede usar un diseño de inicio de forma opcional. Para obtener más información, consulte [archivo de diseño de inicio de marcador de posición para MDM (Intune y otros)](#start-layout-file-for-mdm-intune-and-others).

Para el diseño de inicio, agregue la siguiente sección de **StartLayout** al archivo XML de aprovisionamiento de quiosco:

```xml
<!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
            <StartLayout>
                <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
                      <LayoutOptions StartTileGroupCellWidth="6" />
                      <DefaultLayoutOverride>
                        <StartLayoutCollection>
                          <defaultlayout:StartLayout GroupCellWidth="6">
                            <start:Group Name="">
                              <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
                            </start:Group>
                          </defaultlayout:StartLayout>
                        </StartLayoutCollection>
                      </DefaultLayoutOverride>
                    </LayoutModificationTemplate>
                ]]>
            </StartLayout>
            <!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
```

#### <a id="start-layout-file-for-mdm-intune-and-others"></a>Archivo de diseño iniciar marcador de posición para MDM (Intune y otros)

Guarde el ejemplo siguiente como un archivo XML. Puede usar este archivo al configurar la quiosco de varias aplicaciones en Microsoft Intune (o en otro servicio MDM que proporcione un perfil de quiosco).

> [!NOTE]
> Si tiene que usar una configuración personalizada y la configuración de XML completa para configurar un quiosco en el servicio MDM, use las [instrucciones de inicio del diseño para un paquete de aprovisionamiento](#start-layout-for-hololens).

```xml
<LayoutModificationTemplate
    xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"
    xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout"
    xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout"
    Version="1">
  <RequiredStartGroupsCollection>
    <RequiredStartGroups>
      <AppendGroup Name="">
        <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
      </AppendGroup>
    </RequiredStartGroups>
  </RequiredStartGroupsCollection>
 </LayoutModificationTemplate>
```

### <a id="ppconfigadd"></a>Visión. paquete, paso 2 &ndash; Agregar el archivo XML de configuración de quiosco a un paquete de aprovisionamiento

1. Abra el [Diseñador de configuración de Windows](https://www.microsoft.com/store/apps/9nblggh4tx22).
1. Seleccione **aprovisionamiento avanzado**, escriba un nombre para el proyecto y, a continuación, seleccione **siguiente**.
1. Seleccione **Windows 10 Holographic**y, después, haga clic en **siguiente**.
1. Seleccione **Finalizar**. Se abrirá el área de trabajo para el paquete.
1. Seleccione **configuración de tiempo**de  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**.
1. En el panel central, seleccione **examinar** para buscar y seleccionar el archivo XML de configuración de quiosco que ha creado.

   ![Captura de pantalla del campo MultiAppAssignedAccessSettings en el Diseñador de configuración de Windows](./images/multiappassignedaccesssettings.png)

1. **Opcional**. (Si desea aplicar el paquete de aprovisionamiento después de la configuración inicial del dispositivo y ya hay un usuario administrador disponible en el dispositivo quiosco, omita este paso). Seleccione **configuración de tiempo de ejecución** &gt; **cuentas** &gt; **usuarios**y, a continuación, cree una cuenta de usuario. Proporcione un nombre de usuario y una contraseña y, a continuación, seleccione **usergroup**  >  **Administrators**.  
  
     Al usar esta cuenta, puede ver el estado de aprovisionamiento y los registros.  
1. **Opcional**. (Si ya tiene una cuenta que no es de administrador en el dispositivo de quiosco, omita este paso). Seleccione **configuración de tiempo de ejecución** &gt; **cuentas** &gt; **usuarios**y, a continuación, cree una cuenta de usuario local. Asegúrese de que el nombre de usuario es el mismo que el de la cuenta que especifique en el XML de configuración. Seleccione **UserGroup**  >  **los usuarios estándar**de usergroup.
1. Seleccione **File**  >  **Guardar**archivo.
1. Seleccione **exportar**  >  **paquete de aprovisionamiento**y, a continuación, seleccione **propietario**  >  **it admin**. Esto establece la prioridad de este paquete de aprovisionamiento más alta que los paquetes de aprovisionamiento que se aplican a este dispositivo desde otros orígenes.
1. Selecciona **Siguiente**.
1. En la página **seguridad del paquete de aprovisionamiento** , seleccione una opción de seguridad.
   > [!IMPORTANT]  
   > Si selecciona **Habilitar firma de paquete**, también tendrá que seleccionar un certificado válido para usarlo para firmar el paquete. Para ello, seleccione **examinar** y seleccione el certificado que quiere usar para firmar el paquete.
   
   > [!CAUTION]  
   > No seleccione **Habilitar cifrado de paquetes**. En los dispositivos HoloLens, esta configuración produce errores de aprovisionamiento.
1. Selecciona **Siguiente**.
1. Especifique la ubicación de salida donde quiere que aparezca el paquete de aprovisionamiento al crearlo. De forma predeterminada, el Diseñador de configuraciones de Windows usa la carpeta de proyecto como la ubicación de salida. Si desea cambiar la ubicación de salida, seleccione **examinar**. Cuando haya terminado, seleccione **siguiente**.
1. Seleccione **compilación** para empezar a crear el paquete. El paquete de aprovisionamiento no tarda mucho tiempo en compilarse. En la página compilación se muestra la información del proyecto y la barra de progreso indica el estado de la compilación.

### <a id="ppapply"></a>Paquete de aprovisionamiento, paso 3 &ndash; aplicar el paquete de aprovisionamiento a HoloLens

El artículo "configurar HoloLens usando un paquete de aprovisionamiento" proporciona instrucciones detalladas para aplicar el paquete de aprovisionamiento en las siguientes circunstancias:

- Inicialmente, puedes [aplicar un paquete de aprovisionamiento a HoloLens durante la instalación](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

- También puede [aplicar un paquete de aprovisionamiento a HoloLens después de la instalación](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup).

## Usar Windows Device portal para configurar una pantalla completa de una aplicación

Para configurar el modo de pantalla completa mediante Windows Device portal, siga estos pasos.

1. [Configura el dispositivo HoloLens para usar Windows Device portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal). Device Portal es un servidor web en el dispositivo HoloLens al que puedes conectarte desde un navegador web del equipo.

    > [!CAUTION]
    > Cuando configuras HoloLens para usar el portal de dispositivos, debes habilitar el modo de Desarrollador en el dispositivo. El modo de Desarrollador en un dispositivo con Windows Holographic para empresas le permite cargar aplicaciones de forma simultánea. Sin embargo, esta configuración crea un riesgo de que un usuario pueda instalar aplicaciones que Microsoft Store no ha certificado. Los administradores pueden bloquear la capacidad de habilitar el modo de desarrollador mediante la opción de **desbloqueo ApplicationManagement/AllowDeveloper** en el [CSP de directiva](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider). [Obtén más información acerca del modo de desarrollador.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. En un equipo, conéctate a HoloLens con [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) o [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb).

1. Realiza una de las siguientes acciones:
   - Si es la primera vez que se conecta a Windows Device portal, [cree un nombre de usuario y una contraseña](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password) .
   - Escriba el nombre de usuario y la contraseña que configuró previamente.

    > [!TIP]
    > Si aparece un error de certificado en el navegador, sigue [estos pasos de solución de problemas](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate) (vínculo en inglés).

1. En Windows Device portal, seleccione el **modo de pantalla completa**.

1. Seleccione **Habilitar el modo de pantalla completa**, seleccione una aplicación para que se ejecute cuando se inicie el dispositivo y, a continuación, seleccione **Guardar**.

    ![Pantalla completa](images/kiosk.png)
1. Reinicie HoloLens. Si todavía tiene la página de portal de dispositivos abierta, puede seleccionar **reiniciar** en la parte superior de la página.

> [!NOTE]
> El modo de pantalla completa se puede establecer a través de la API de REST de Device portal mediante una publicación en/API/Holographic/kioskmode/Settings con un parámetro de cadena de consulta obligatorio ("kioskModeEnabled" con un valor de "true" o "false") y un parámetro opcional ("startupApp" con un valor de un nombre de paquete). Ten en cuenta que el portal de dispositivos está pensado solo para desarrolladores y no debe habilitarse en dispositivos ajenos a la programación para desarrolladores. La API de REST está sujeta a cambios en actualizaciones y versiones futuras.

## Más información

### Vea cómo configurar un quiosco con un paquete de aprovisionamiento.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### Acceso asignado global: modo de pantalla completa
- Se redujo la administración de identidades de quiosco al habilitar el nuevo método quiosco que aplica el modo de pantalla completa en el nivel del sistema.

Esta nueva característica permite que un administrador de ti configure un dispositivo HoloLens 2 para el modo de pantalla completa de varias aplicaciones, que es aplicable en el nivel del sistema, no tiene afinidad con ninguna identidad en el sistema y se aplica a todos los usuarios que inician sesión en el dispositivo. [Aquí encontrará](hololens-global-assigned-access-kiosk.md)información sobre esta nueva característica.

### Inicio automático de una aplicación en el modo de pantalla completa de varias aplicaciones 
- Experiencia focalizada con el inicio automático de aplicaciones, el aumento de las selecciones de la interfaz de usuario y aplicaciones elegidas para las experiencias en modo de pantalla completa.

Solo se aplica al modo de pantalla completa de varias aplicaciones y solo se puede designar una aplicación para iniciar automáticamente con el atributo resaltado a continuación en la configuración de acceso asignada. 

La aplicación se inicia automáticamente cuando el usuario inicia sesión. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### Cambios en el comportamiento del modo de pantalla completa para el tratamiento de errores
- Modo de pantalla completa más seguro eliminando las aplicaciones disponibles en errores de modo quiosco. 

Antes de encontrar errores al aplicar el modo de pantalla completa, HoloLens se usó para mostrar todas las aplicaciones en el menú Inicio. Ahora, en Windows Holographic versión 20H2, en caso de errores, no se mostrará ninguna aplicación en el menú Inicio como se indica a continuación: 

![Imagen del modo de quiosco que se muestra ahora cuando se produce un error.](images/hololens-kiosk-failure-behavior.png )

### Caché de pertenencia a grupo AAD para el quiosco desconectado
- Se habilitaron quioscos sin conexión para usarlos con grupos de AAD durante un máximo de 60 días.

Esta directiva controla cuántos días se permite que la caché de pertenencia a grupos de AAD se use para configuraciones de acceso asignadas dirigidas a grupos de AAD para el usuario que ha iniciado sesión. Una vez que este valor de Directiva se establece en un valor mayor que 0, de lo contrario se usa cache.  

Name: AADGroupMembershipCacheValidityInDays URI Value:./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min-0 días  
Máximo: 60 días 

Pasos para usar esta directiva correctamente: 
1. Cree un perfil de configuración de dispositivo para quiosco dirigido a grupos de AAD y asígnelo a dispositivos HoloLens. 
1. Crear un URI de OMA personalizado configuración de dispositivo que establezca este valor de directiva en cantidad deseada de días (> 0) y asignarlo a dispositivos HoloLens. 
    1. El valor del URI debe especificarse en el cuadro de texto OMA-URI como./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. El valor puede estar entre Min/Max permitidos.
1. Inscriba dispositivos HoloLens y verifique que ambas configuraciones se apliquen al dispositivo. 
1. Deje que el inicio de sesión de AAD para el usuario 1 cuando esté disponible Internet, una vez que el usuario inicie sesión y la pertenencia a grupos de AAD se haya confirmado correctamente, se creará la memoria caché. 
1. Ahora, el usuario 1 de AAD puede hacer que HoloLens esté desconectado y usarlo para el modo de pantalla completa, siempre y cuando el valor de la Directiva permita un número de días por X. 
1. Los pasos 4 y 5 se pueden repetir para cualquier otro usuario de AAD. punto clave aquí es que cualquier usuario de AAD debe iniciar sesión en el dispositivo con Internet, por lo menos una vez, podemos determinar que son miembros del grupo de AAD al que se dirige la configuración de quiosco. 
 
> [!NOTE]
> Hasta que se realice el paso 4 para un usuario de AAD experimentará un comportamiento de error mencionado en entornos "desconectados". 


## Muestras de código de quiosco XML para HoloLens

### Modo de pantalla múltiple de la aplicación objetivo de un grupo de AAD. 
Este quiosco implementa un quiosco para los usuarios del grupo de AAD, tendrán una exposición habilitada que incluye las 3 aplicaciones: configuración, asistencia remota y centro de opiniones. Para modificar esta muestra para usarla inmediatamente, asegúrese de cambiar la GUID resaltada a continuación para que coincida con un grupo de AAD. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### El modo de pantalla completa de varias aplicaciones está dirigido a la cuenta de AAD.
Este quiosco implementa un quiosco para un solo usuario, tiene una exposición habilitada que incluye las 3 aplicaciones: configuración, asistencia remota y centro de opiniones. Para modificar esta muestra para usarla inmediatamente, asegúrese de cambiar la cuenta resaltada a continuación para que coincida con una cuenta de AAD suya. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

