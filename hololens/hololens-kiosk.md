---
title: Configuración de HoloLens como un quiosco multimedia
description: Aprenda a configurar y usar una configuración de quiosco para bloquear las aplicaciones en HoloLens dispositivos.
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
ms.openlocfilehash: 9d9e521f3e337b3a48a60c19e52bfeb3186507af
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640362"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Configuración de HoloLens como un quiosco multimedia

Puede configurar un dispositivo HoloLens para que funcione como un dispositivo de propósito fijo, también denominado quiosco, configurando el dispositivo para que se ejecute en modo de pantalla completa. El modo de pantalla completa limita las aplicaciones (o usuarios) que están disponibles en el dispositivo. El modo de pantalla completa es una característica práctica que puede usar para dedicar un dispositivo HoloLens a aplicaciones empresariales, o para usar el dispositivo HoloLens en una demostración de aplicación.

En este artículo se proporciona información sobre los aspectos de la configuración de quiosco que son específicos de HoloLens dispositivos. Para obtener información general sobre los distintos tipos de quioscos basados en Windows y cómo configurarlos, consulte Configuración de quioscos y [signos digitales](/windows/configuration/kiosk-methods)en Windows de escritorio.  

> [!IMPORTANT]  
> El modo de pantalla completa determina qué aplicaciones están disponibles cuando un usuario inicia sesión en el dispositivo. Sin embargo, el modo de pantalla completa no es un método de seguridad. No detiene que una aplicación "permitida" abra otra aplicación que no está permitida. Para impedir que se abran aplicaciones o procesos, use Windows Defender CSP de Control de aplicaciones [(WDAC)](/windows/client-management/mdm/applicationcontrol-csp) para crear las directivas adecuadas.
>
> Obtenga más información sobre la servicios Microsoft proporcionar a los usuarios un nivel avanzado de seguridad que HoloLens 2 usa, obtenga más información sobre separación y aislamiento de estado: protecciones [de Defender.](security-state-separation-isolation.md#defender-protections) O bien, aprenda a [usar WDAC y Windows PowerShell para permitir](/mem/intune/configuration/custom-profile-hololens)o bloquear aplicaciones en HoloLens 2 dispositivos con Microsoft Intune .

Puede usar el modo de pantalla completa en una configuración de aplicación única o de varias aplicaciones, y puede usar uno de los tres procesos para configurar e implementar la configuración de quiosco.

> [!IMPORTANT]  
> Al eliminar la configuración de varias aplicaciones, se quitan los perfiles de bloqueo de usuario creados por la característica de acceso asignado. Sin embargo, no revierte todos los cambios de directiva. Para revertir estas directivas, debe restablecer el dispositivo a la configuración de fábrica.

## <a name="plan-the-kiosk-deployment"></a>Planeación de la implementación de quiosco

Al planear el quiosco, deberá poder responder a las siguientes preguntas. Estas son algunas decisiones que se deben tener en cuenta al leer esta página y algunas consideraciones para estas preguntas.
1. **Quién va a usar la pantalla completa y qué [tipo](hololens-identity.md) de cuentas usarán?** Se trata de una decisión que probablemente ya haya tomado y que no se debe ajustar por el bien del quiosco, pero afectará a cómo se asigna el quiosco más adelante.
1. **¿Necesita tener quioscos diferentes por usuario o grupo o un quiosco no habilitado para algunos?** Si es así, querrá crear el quiosco a través de XML. 
1. **¿Cuántas aplicaciones habrá en el quiosco?** Si tiene más de una aplicación, necesitará un quiosco de varias aplicaciones. 
1. **¿Qué aplicaciones estarán en el quiosco?** Use nuestra lista de AUMIDs a continuación para agregar cualquier In-Box aplicaciones, además de las suyas propias.
1. **¿Cómo planea implementar el quiosco?** Si va a inscribir el dispositivo en MDM, se recomienda usar MDM para implementar la pantalla completa. Si no usa MDM, la implementación con el paquete de aprovisionamiento está disponible.  

### <a name="kiosk-mode-requirements"></a>Requisitos del modo de pantalla completa

Puede configurar cualquier dispositivo HoloLens 2 que use el modo de pantalla completa.

> [!IMPORTANT]
> El modo de pantalla completa solo está disponible si el dispositivo tiene Windows Holographic for Business. Todos HoloLens 2 dispositivos se envían con Windows Holographic for Business y no hay ninguna otra edición. Todos HoloLens 2 dispositivos pueden ejecutar el modo de pantalla completa de forma automática.
>
> HoloLens dispositivos (1.ª generación) deben actualizarse tanto en términos de compilación del sistema operativo como de edición del sistema operativo. A continuación se proporciona más información sobre cómo actualizar HoloLens (1.ª generación) [a Windows Holographic for Business](hololens1-upgrade-enterprise.md) edición. Para actualizar un dispositivo HoloLens (1.ª generación) para que use el modo de pantalla completa, primero debe asegurarse de que el dispositivo ejecuta Windows 10, versión 1803 o una versión posterior. Si ha usado la herramienta de recuperación de dispositivos de Windows para recuperar el dispositivo HoloLens (1.ª generación) en su compilación predeterminada, o si ha instalado las actualizaciones más recientes, el dispositivo está listo para configurarse.

> [!IMPORTANT]  
> Para ayudar a proteger los dispositivos que se ejecutan en pantalla completa, considere la posibilidad de agregar directivas de administración de dispositivos que desactiven características como la conectividad USB. Además, compruebe la configuración del anillo de actualización para asegurarse de que las actualizaciones automáticas no se produzcan durante el horario comercial.

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>Decidir entre un quiosco de una sola aplicación o un quiosco de varias aplicaciones

Un quiosco de una sola aplicación inicia la aplicación especificada cuando el usuario inicia sesión en el dispositivo. La menú Inicio está deshabilitada, como se Cortana. Un HoloLens 2 no responde al gesto [Iniciar.](hololens2-basic-usage.md#start-gesture) Un HoloLens (1.ª generación) no responde al gesto [de Bloom.](hololens1-basic-usage.md) Dado que solo se puede ejecutar una aplicación, el usuario no puede colocar otras aplicaciones.

Una pantalla completa con varias aplicaciones muestra menú Inicio cuando el usuario inicia sesión en el dispositivo. La configuración de quiosco determina qué aplicaciones están disponibles en el menú Inicio. Puede usar un quiosco con varias aplicaciones para proporcionar una experiencia fácil de entender para los usuarios si les presenta solo las cosas que tienen que usar y quita las cosas que no necesitan usar.

En la tabla siguiente se enumeran las funcionalidades de características en los distintos modos de quiosco.

| &nbsp; |Menú Inicio |Menú Acciones rápidas |Cámara y vídeo |Miracast |Cortana |Comandos de voz integrados |
| --- | --- | --- | --- | --- | --- | --- | 
|Quiosco de una sola aplicación |Disabled |Disabled |Disabled |Disabled   |Disabled |Habilitado<sup>1</sup> |
|Pantalla completa con varias operaciones |Habilitado |Habilitado<sup>2</sup> |Disponible<sup>2</sup> |Disponible<sup>2</sup> |Disponible<sup>2, 3</sup>  |Habilitado<sup>1</sup> |

> <sup>1 Los</sup> comandos de voz relacionados con las características deshabilitadas no funcionan.  
> <sup>2 Para</sup> obtener más información sobre cómo configurar estas características, vea [Seleccionar aplicaciones de quiosco.](#plan-kiosk-apps)  
> <sup>3</sup> Incluso si Cortana está deshabilitado, se habilitan los comandos de voz integrados.

En la tabla siguiente se enumeran las características de soporte técnico del usuario de los distintos modos de quiosco.

| &nbsp; |Tipos de usuario admitidos | Inicio de sesión automático | Varios niveles de acceso |
| --- | --- | --- | --- |
|Quiosco de una sola aplicación |Cuenta de servicio administrada (MSA) en Azure Active Directory (Azure AD) o cuenta local |Sí |No |
|Pantalla completa con varias operaciones |Cuenta de Azure AD |No |Sí |

Para obtener ejemplos de cómo usar estas funcionalidades, consulte la tabla siguiente.

|Use una pantalla completa de una sola aplicación para: |Use una pantalla completa con varias aplicaciones para: |
| --- | --- |
|Un dispositivo que solo ejecuta una guía de Dynamics 365 para nuevos empleados. |Un dispositivo que ejecuta guías y asistencia remota para una variedad de empleados. |
|Un dispositivo que ejecuta solo una aplicación personalizada. |Un dispositivo que funciona como quiosco para la mayoría de los usuarios (que ejecuta solo una aplicación personalizada), pero que funciona como un dispositivo estándar para un grupo específico de usuarios. |

### <a name="plan-kiosk-apps"></a>Planeación de aplicaciones de quiosco

Para obtener información general sobre cómo elegir aplicaciones de quiosco, consulte Directrices para elegir una aplicación para el acceso asignado [(modo de pantalla completa).](/windows/configuration/guidelines-for-assigned-access-app)

Si usa la aplicación Windows Portal de dispositivos configurar un quiosco de una sola aplicación, seleccione la aplicación durante el proceso de configuración.  

Si usa un sistema Administración de dispositivos móvil (MDM) o un paquete de aprovisionamiento para configurar el modo de pantalla completa, use el proveedor de servicios de configuración [(CSP) AssignedAccess](/windows/client-management/mdm/assignedaccess-csp) para especificar aplicaciones. El CSP usa los id. de modelo de usuario [de aplicación (AUMID)](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) para identificar las aplicaciones. En la tabla siguiente se enumeran los AUMID de algunas aplicaciones que se pueden usar en una pantalla completa con varias aplicaciones.

> [!IMPORTANT]
> El modo de pantalla completa determina qué aplicaciones están disponibles cuando un usuario inicia sesión en el dispositivo. Sin embargo, el modo de pantalla completa no es un método de seguridad. No detiene que una aplicación "permitida" abra otra aplicación que no está permitida. Dado que no se restringe este comportamiento, las aplicaciones todavía se pueden iniciar desde Edge, el Explorador de archivos y Microsoft Store aplicaciones. Si hay aplicaciones específicas que no desea iniciar desde un quiosco, use Windows Defender CSP de Control de aplicaciones [(WDAC)](/windows/client-management/mdm/applicationcontrol-csp) para crear las directivas adecuadas. 
> 
> Además, el Mixed Reality inicio no se puede establecer como una aplicación de quiosco.

<a id="aumids"></a>

|Nombre de la aplicación |AUMID |
| --- | --- |
|Visor 3D |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Calendario |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|Cámara<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! App |
|Selector de dispositivos en HoloLens (1.ª generación) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|Selector de dispositivos en HoloLens 2 |Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows. DevicesFlowHost |
|Dynamics 365 Guides |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft.RemoteAssist |
|Centro de &nbsp; comentarios |Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe \! App |
|Explorador de archivos |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Correo |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Datos Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge |
|Nuevo Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast<sup>4</sup> |&nbsp; |
|Películas y TV |Microsoft.ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! App |
|Fotos |Microsoft. Windows. \_Fotos 8wekyb3d8bbwe \! App |
|Antiguo Configuración |HolographicSystemSettings_cw5n1h2txyewy! Aplicación |
|Nuevo Configuración |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! Aplicación |
|Sugerencias |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1 Para</sup> habilitar la captura de fotos o vídeos, debe habilitar la aplicación Cámara como una aplicación de quiosco.  
> <sup>2</sup> Al habilitar la aplicación Cámara, tenga en cuenta las condiciones siguientes:
> - El menú Acciones rápidas incluye los botones Foto y Vídeo.  
> - También debe habilitar una aplicación (como Fotos, Mail o OneDrive) que pueda interactuar con o recuperar imágenes.  
>  
> <sup>3</sup> Incluso si no habilita la Cortana como una aplicación de pantalla completa, se habilitan los comandos de voz integrados. Sin embargo, los comandos relacionados con las características deshabilitadas no tienen ningún efecto.  
> <sup>4</sup> No puede habilitar Miracast directamente. Para habilitar Miracast como una aplicación de pantalla completa, habilite la aplicación Cámara y la aplicación Selector de dispositivos.

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>Planeación de perfiles de quiosco para usuarios o grupos

Al crear el archivo xml o usar la interfaz de usuario de Intune para configurar un quiosco, deberá tener en cuenta quién será el usuario del quiosco. Una configuración de quiosco se puede limitar a una cuenta individual o a Azure AD grupos. 

Normalmente, los quioscos están habilitados para un usuario o un grupo de usuarios. Sin embargo, si planea escribir su propia pantalla completa XML, es posible que quiera tener en cuenta el acceso asignado global, en el que la pantalla completa se aplica en el nivel de dispositivo independientemente de la identidad. Si esto le preocupa, lea [más sobre los quioscos de acceso asignado global.](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>Si va a crear un archivo XML:
-   Muchos crean varios perfiles de quiosco y los asignan a distintos usuarios o grupos. Por ejemplo, un quiosco para Azure AD grupo que tiene muchas aplicaciones y un visitante que tiene un quiosco de varias aplicaciones con una aplicación singular.
-   La configuración de quiosco se denominará **Id. de** perfil y tendrá un GUID.
-   Asignará ese perfil en la sección configs especificando el tipo de usuario y usando el mismo GUID para **el identificador DefaultProfile**.
- Se puede crear un archivo XML, pero seguir aplicó a un dispositivo a través de MDM mediante la creación de un perfil de configuración de dispositivo uri de OMA personalizado y su aplicación HoloLens un grupo de dispositivos con el valor uri: ./Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Si va a crear una pantalla completa en Intune.
-   Cada dispositivo solo puede recibir un único perfil de quiosco; de lo contrario, creará un conflicto y no recibirá ninguna configuración de quiosco. 
    -   Otros tipos de perfiles y directivas, como las restricciones de dispositivos que no están relacionadas con el perfil de configuración de quiosco, no entra en conflicto con el perfil de configuración de quiosco.
-   La pantalla completa se habilitará para todos los usuarios que forman parte del tipo de inicio de sesión usuario, que se establecerá con un usuario o un grupo Azure AD usuario. 
-   Una vez establecida la configuración de quiosco y el tipo de inicio de sesión de usuario **(los** usuarios que pueden iniciar sesión en la pantalla completa) y las aplicaciones seleccionadas, la configuración del dispositivo todavía debe asignarse a un grupo. Los grupos asignados determinan qué dispositivos reciben la configuración del dispositivo de quiosco, pero no interactúa con si la pantalla completa está habilitada o no. 
    - Para obtener una explicación completa de los efectos de asignar perfiles de configuración en Intune, consulte [Asignación](/intune/configuration/device-profile-assign)de perfiles de usuario y dispositivo en Microsoft Intune .

### <a name="select-a-deployment-method"></a>Selección de un método de implementación

Puede seleccionar uno de los métodos siguientes para implementar configuraciones de quiosco:

- [Microsoft Intune u otro servicio de administración de dispositivos móviles (MDM)](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Paquete de aprovisionamiento](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Portal de dispositivos Windows](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Dado que este método requiere que el modo de desarrollador esté habilitado en el dispositivo, se recomienda usarlo solo para las demostraciones.

En la tabla siguiente se enumeran las funcionalidades y ventajas de cada uno de los métodos de implementación.

| &nbsp; |Implementación mediante Windows Portal de dispositivos |Implementación mediante un paquete de aprovisionamiento |Implementación mediante MDM |
| --------------------------- | ------------- | -------------------- | ---- |
|Implementación de quioscos de aplicación única   | Sí           | Sí                  | Sí  |
|Implementación de quioscos con varias aplicaciones    | No            | Sí                  | Sí  |
|Implementación solo en dispositivos locales | Sí           | Sí                  | No   |
|Implementación mediante el modo de desarrollador |Requerido       | No se requiere            | No se requiere   |
|Implementación mediante Azure Active Directory (Azure AD)  | No se requiere            | No se requiere                   | Obligatorio  |
|Implementación automática      | No            | No                   | Sí  |
|Velocidad de implementación            | Rápido       | Rápido                 | Lento |
|Implementación a escala | No recomendado    | Recomendado        | Recomendado |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>Usar Microsoft Intune u otra MDM para configurar una pantalla completa de una sola aplicación o de varias aplicaciones

Para configurar el modo de pantalla completa mediante Microsoft Intune u otro sistema MDM, siga estos pasos.

1. [Prepárese para inscribir los dispositivos.](#mdmenroll)
1. [Cree un perfil de configuración de quiosco.](#mdmprofile)
1. Configure la pantalla completa.
   - [Configure los valores de un quiosco de una sola aplicación.](#mdmconfigsingle)
   - [Configure los valores de una pantalla completa con varias aplicaciones.](#mdmconfigmulti)
1. [Asigne el perfil de configuración de quiosco a un grupo](#mdmassign).
1. Implemente los dispositivos.
   - [Implemente un quiosco de una sola aplicación.](#mdmsingledeploy)
   - [Implemente una pantalla completa con varias aplicaciones.](#mdmmultideploy)

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM, paso &ndash; 1: Preparación para inscribir los dispositivos

Puede configurar el sistema MDM para inscribir dispositivos HoloLens automáticamente cuando el usuario inicia sesión por primera vez o hacer que los usuarios inscriban dispositivos manualmente. Los dispositivos también deben unirse al dominio Azure AD y asignarse a los grupos adecuados.

Para obtener más información sobre cómo inscribir los dispositivos, vea Inscribir HoloLens en [MDM](hololens-enroll-mdm.md) y métodos de inscripción de [Intune para Windows dispositivos](/mem/intune/enrollment/windows-enrollment-methods).

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM, paso 2: &ndash; Creación de un perfil de configuración de quiosco

1. Abra [Azure Portal](https://portal.azure.com/) e inicie sesión en su Administrador de Intune cuenta.
1. Seleccione **Microsoft Intune**  >  Device configuration - Profiles Create profile (Configuración **del dispositivo: perfiles**  >  **Crear perfil).**
1. Escriba un nombre de perfil.
1. Seleccione **Platform**  >  **Windows 10 y versiones posteriores** y, a continuación, seleccione Profile type Device restrictions **(Restricciones** de  > **dispositivos del tipo de perfil).**
1. Seleccione **Configurar**  >  **quiosco** y, a continuación, seleccione una de las opciones siguientes:
   - Para crear un quiosco de una sola aplicación, seleccione **Quiosco** de pantalla completa con  >  **una sola aplicación.**
   - Para crear un quiosco con varias aplicaciones, seleccione **Quiosco**  >  **de pantalla completa con varias aplicaciones.**
1. Para empezar a configurar la pantalla completa, seleccione **Agregar.**

Los pasos siguientes varían en función del tipo de quiosco que desee. Para obtener más información, seleccione una de las siguientes opciones:  

- [Quiosco de una sola aplicación](#mdmconfigsingle)
- [Pantalla completa con varias operaciones](#mdmconfigmulti)

Para obtener más información sobre cómo crear un perfil de configuración de quiosco, vea Windows 10 y Windows Holographic for Business configuración del dispositivo para ejecutarse como una pantalla completa [dedicada mediante Intune](/intune/configuration/kiosk-settings).

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM, paso 3 (aplicación única) Configuración de la pantalla completa &ndash;  de una sola aplicación

En esta sección se resume la configuración que requiere una pantalla completa de una sola aplicación. Para más información, consulte los artículos siguientes:

- Para obtener información sobre cómo configurar un perfil de configuración de quiosco en Intune, vea [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Para obtener más información sobre la configuración disponible para quioscos de una sola aplicación en Intune, consulte Pantalla completa [con una sola aplicación completa.](/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- Para otros servicios MDM, consulte la documentación del proveedor para obtener instrucciones. Si tiene que usar una configuración XML personalizada para configurar una pantalla completa en el servicio MDM, cree un archivo XML que defina la [configuración de quiosco.](#ppkioskconfig)

1. Seleccione **User logon type** Local user account (Tipo de inicio de sesión de usuario local cuenta de usuario local) y, a continuación, escriba el nombre de usuario de la cuenta local (dispositivo) o la cuenta Microsoft  >  (MSA) que puede iniciar sesión en la pantalla completa.
   > [!NOTE]  
   > Los tipos de cuenta de usuario **Inicio de sesión automático** no se admiten en Windows Holographic for Business.
1. Seleccione **Aplicación tipo de** aplicación Aplicación  >  **de** la Tienda y, a continuación, seleccione una aplicación de la lista.

El siguiente paso consiste en [asignar el](#mdmassign) perfil a un grupo.

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM, paso 3 (varias aplicaciones) Configuración de una pantalla &ndash; completa con varias aplicaciones

En esta sección se resume la configuración que requiere una pantalla completa con varias aplicaciones. Para más información, consulte los artículos siguientes:

- Para obtener información sobre cómo configurar un perfil de configuración de quiosco en Intune, vea [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Para obtener más información sobre la configuración disponible para quioscos con varias aplicaciones en Intune, consulte [Quioscos con varias aplicaciones.](/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- Para otros servicios MDM, consulte la documentación del proveedor para obtener instrucciones. Si necesita usar una configuración XML personalizada para configurar una pantalla completa en el servicio MDM, cree un archivo XML que defina la [configuración de quiosco.](#ppkioskconfig) Si usa un archivo XML, asegúrese de incluir el diseño [de inicio](#start-layout-for-hololens).  
- Opcionalmente, puede usar un diseño de inicio personalizado con Intune u otros servicios MDM. Para obtener más información, vea [Iniciar archivo de diseño para MDM (Intune y otros).](#start-layout-file-for-mdm-intune-and-others)

1. Seleccione **Destino Windows 10 dispositivos en modo S**  >  **No**.  
>[!NOTE]  
> El modo S no se admite en Windows Holographic for Business.

1. Seleccione **Tipo de inicio de** sesión de Azure AD usuario o grupo o Tipo de inicio de sesión de usuario HoloLens visitante y, a continuación, agregue uno o varios grupos de usuarios o  >     >  cuentas.  

   Solo los usuarios que pertenecen a los grupos o cuentas que especifique en Tipo de inicio de sesión **de usuario** pueden usar la experiencia de quiosco.

1. Seleccione una o varias aplicaciones mediante las siguientes opciones:
   - Para agregar una aplicación de línea de negocio cargada, seleccione **Agregar** aplicación de la tienda y, a continuación, seleccione la aplicación que quiera.
   - Para agregar una aplicación especificando su AUMID, seleccione Agregar por **AUMID** y, a continuación, escriba el AUMID de la aplicación. [Consulte la lista de AUMID disponibles.](#aumids)

El siguiente paso consiste en [asignar el](#mdmassign) perfil a un grupo.

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM, paso 4 &ndash; Asignación del perfil de configuración de quiosco a un grupo

Use la **página Asignaciones del** perfil de configuración de quiosco para establecer dónde desea que se implemente la configuración de quiosco. En el caso más sencillo, asigne el perfil de configuración de quiosco a un grupo que contendrá el HoloLens cuando el dispositivo se inscriba en MDM.

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM, paso 5 (aplicación única) &ndash; Implementación de una pantalla completa de una sola aplicación

Cuando se usa un sistema MDM, se puede inscribir el dispositivo en MDM durante la OOBE. Una vez que finaliza la OOBE, es fácil iniciar sesión en el dispositivo.

Durante la OOBE, siga estos pasos:

1. Inicie sesión con la cuenta que especificó en el perfil de configuración de quiosco.
1. Inscriba el dispositivo. Asegúrese de que el dispositivo se agrega al grupo al que está asignado el perfil de configuración de quiosco.
1. Espere a que finalice OOBE, a que la aplicación de la tienda se descargue e instale y a que se apliquen directivas. A continuación, reinicie el dispositivo.

La próxima vez que inicie sesión en el dispositivo, la aplicación de quiosco se iniciará automáticamente.

Si no ve la configuración de quiosco en este momento, [compruebe el estado de asignación](/intune/configuration/device-profile-monitor).

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM, paso 5 (varias aplicaciones) &ndash; Implementación de una pantalla completa con varias aplicaciones

Cuando se usa un sistema MDM, puede unir el dispositivo al inquilino de Azure AD e inscribirlo en MDM durante la OOBE. Si procede, proporcione la información de inscripción a los usuarios para que estén disponibles durante el proceso de OOBE.

> [!NOTE]  
> Si ha asignado el perfil de configuración de quiosco a un grupo que contiene usuarios, asegúrese de que una de esas cuentas de usuario es la primera cuenta que inicia sesión en el dispositivo.

Durante la OOBE, siga estos pasos:

1. Inicie sesión con la cuenta que pertenece al grupo Tipo **de inicio de sesión de** usuario.
1. Inscriba el dispositivo.
1. Espere a que las aplicaciones que forman parte del perfil de configuración de quiosco se descarguen e instalen. Además, espere a que se apliquen directivas.  
1. Una vez que finalice la OOBE, puede instalar aplicaciones adicionales desde Microsoft Store o mediante la instalación local. [Aplicaciones necesarias](/mem/intune/apps/apps-deploy#assign-an-app) para el grupo al que pertenece el dispositivo para instalarse automáticamente.
1. Una vez finalizada la instalación, reinicie el dispositivo.

La próxima vez que inicie sesión en el dispositivo mediante una cuenta que pertenezca al tipo de inicio de sesión usuario **,** la aplicación de pantalla completa se iniciará automáticamente.

Si no ve la configuración de quiosco en este momento, [compruebe el estado de asignación](/intune/configuration/device-profile-monitor).

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>Uso de un paquete de aprovisionamiento para configurar una pantalla completa de aplicación única o de varias aplicaciones

Para configurar el modo de pantalla completa mediante un paquete de aprovisionamiento, siga estos pasos.

1. [Cree un archivo XML que defina la configuración de quiosco.](#ppkioskconfig), incluido [un diseño de inicio](#start-layout-for-hololens).
2. [Agregue el archivo XML a un paquete de aprovisionamiento.](#ppconfigadd)
3. [Aplique el paquete de aprovisionamiento a HoloLens.](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>Paquete de aprovisionamiento, paso &ndash; 1: Creación de un archivo XML de configuración de quiosco

Siga las instrucciones generales para crear un archivo XML de configuración [de quiosco para Windows escritorio](/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file), excepto lo siguiente:

- No incluya aplicaciones de Windows clásicas (Win32). HoloLens no admite estas aplicaciones.
- Use el marcador [de posición Start layout XML](#start-layout-for-hololens) para HoloLens.
- Opcional: Agregar acceso de invitado a la configuración de quiosco

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>Opcional: Agregar acceso de invitado a la configuración de quiosco

En la [ **sección Configs** (Configuraciones) del archivo XML](/windows/configuration/lock-down-windows-10-to-specific-apps#configs), puede configurar un grupo especial denominado **Visitor** para permitir que los invitados usen el quiosco. Cuando la pantalla completa está configurada para admitir el grupo especial **Visitante,** se agrega una opción **"Invitado"** a la página de inicio de sesión. La **cuenta** de invitado no requiere una contraseña y los datos asociados a la cuenta se eliminan cuando la cuenta cierra la sesión.

Para habilitar la **cuenta de** invitado, agregue el siguiente fragmento de código al XML de configuración de quiosco:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```
#### <a name="enable-visitor-autologon"></a>Habilitación del inicio de sesión automático del visitante

En las [compilaciones Windows Holographic, versión 21H1](hololens-release-notes.md#windows-holographic-version-21h1) y versiones adelante:
- Las configuraciones AAD y Non-ADD admiten que las cuentas de visitante se habiliten para el inicio de sesión automático en los modos de quiosco.

##### <a name="non-aad-configuration"></a>Configuración que no es de AAD

1. Cree un paquete de aprovisionamiento que:
    1. Configura los valores de Runtime/AssignedAccess para permitir las cuentas de visitante.
    1. Opcionalmente, inscribe el dispositivo en MDM (Configuración del entorno de ejecución/Área de trabajo/Inscripciones) para que se pueda administrar más adelante.
    1. No crear una cuenta local
2. [Aplique el paquete de aprovisionamiento](hololens-provisioning.md).

##### <a name="aad-configuration"></a>Configuración de AAD

Los dispositivos unidos a AAD configurados para el modo de pantalla completa pueden iniciar sesión en una cuenta de visitante con un solo clic en la pantalla de inicio de sesión. Una vez que haya iniciado sesión en la cuenta de visitante, el dispositivo no volverá a solicitar el inicio de sesión hasta que el visitante haya iniciado sesión explícitamente desde el menú Inicio o se reinicie el dispositivo.

El inicio de sesión automático del visitante se puede administrar a través [de la directiva OMA-URI personalizada:](/mem/intune/configuration/custom-settings-windows-10)

- Valor de URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon


| Directiva |Descripción |Configurations 
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | Permite que un visitante inicie sesión automáticamente en una pantalla completa. | 1 (Sí), 0 (No, valor predeterminado). |

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>Diseño de inicio de marcador de posición para HoloLens

Si usa un paquete [de aprovisionamiento para](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) configurar una pantalla completa con varias aplicaciones, el procedimiento requiere un diseño de inicio. La personalización del diseño de inicio no se admite en Windows Holographic for Business. Por lo tanto, tendrá que usar un marcador de posición Diseño de inicio.

> [!NOTE]  
> Dado que un quiosco de una sola aplicación inicia la aplicación de pantalla completa cuando un usuario inicia sesión, no usa un menú Inicio y no tiene que tener un diseño De inicio.

> [!NOTE]  
> Si usa [MDM para](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) configurar una pantalla completa con varias aplicaciones, puede usar opcionalmente un diseño De inicio. Para obtener más información, vea [Archivo de diseño de inicio de marcador de posición para MDM (Intune y otros).](#start-layout-file-for-mdm-intune-and-others)

Para el diseño De inicio, agregue la siguiente **sección StartLayout** al archivo XML de aprovisionamiento de quiosco:

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

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>Archivo de diseño de inicio de marcador de posición para MDM (Intune y otros)

Guarde el ejemplo siguiente como un archivo XML. Puede usar este archivo al configurar la pantalla completa con varias aplicaciones en Microsoft Intune (o en otro servicio MDM que proporciona un perfil de quiosco).

> [!NOTE]
> Si tiene que usar una configuración personalizada y una configuración XML completa para configurar una pantalla completa en el servicio MDM, use las instrucciones de diseño De [inicio para un paquete de aprovisionamiento.](#start-layout-for-hololens)

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

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>Prov. paquete, paso 2: &ndash; Adición del archivo XML de configuración de quiosco a un paquete de aprovisionamiento

1. Abra [Windows Diseñador de configuración de](https://www.microsoft.com/store/apps/9nblggh4tx22).
1. Seleccione **Aprovisionamiento avanzado,** escriba un nombre para el proyecto y, a continuación, **seleccione Siguiente.**
1. Seleccione **Windows 10 Holographic** y, a continuación, **seleccione Siguiente.**
1. Seleccione **Finalizar**. Se abrirá el área de trabajo para el paquete.
1. Seleccione **Configuración en tiempo de** ejecución  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**.
1. En el panel central, seleccione **Examinar para** buscar y seleccionar el archivo XML de configuración de quiosco que ha creado.

   ![Captura de pantalla del campo MultiAppAssignedAccessSettings en Windows Configuration Designer](./images/multiappassignedaccesssettings.png)

1. **Opcional**. (Si desea aplicar el paquete de aprovisionamiento después de la configuración inicial del dispositivo y ya hay un usuario administrador disponible en el dispositivo de quiosco, omita este paso). Seleccione **Configuración en tiempo de ejecución** &gt; **Cuentas** &gt; **Usuarios** y, a continuación, cree una cuenta de usuario. Proporcione un nombre de usuario y una contraseña y, a continuación, **seleccione UserGroup**  >  **Administrators (Administradores de grupos de usuarios).**  
  
     Con esta cuenta, puede ver el estado de aprovisionamiento y los registros.  
1. **Opcional**. (Si ya tiene una cuenta que no es de administrador en el dispositivo de quiosco, omita este paso). Seleccione **Configuración en tiempo de ejecución** &gt; **Cuentas** &gt; **Usuarios** y, a continuación, cree una cuenta de usuario local. Asegúrese de que el nombre de usuario es el mismo que para la cuenta que especifique en el XML de configuración. Seleccione **UserGroup** Standard Users  >  (Usuarios estándar **de UserGroup).**
1. Seleccione **Archivo** > **Guardar**.
1. Seleccione **Exportar paquete** de  >  **aprovisionamiento** y, a continuación, seleccione Administrador **de** TI  >  **propietario.** Esto establece la prioridad de este paquete de aprovisionamiento mayor que los paquetes de aprovisionamiento que se aplican a este dispositivo desde otros orígenes.
1. Seleccione **Siguiente**.
1. En la **página Seguridad del paquete de** aprovisionamiento, seleccione una opción de seguridad.
   > [!IMPORTANT]  
   > Si selecciona Habilitar **firma de paquetes**, también tendrá que seleccionar un certificado válido para usarlo para firmar el paquete. Para ello, seleccione **Examinar** y seleccione el certificado que desea usar para firmar el paquete.
   
   > [!CAUTION]  
   > No seleccione Habilitar **cifrado de paquetes.** En HoloLens dispositivos, esta configuración hace que se produce un error en el aprovisionamiento.
1. Seleccione **Siguiente**.
1. Especifique la ubicación de salida a la que desea que vaya el paquete de aprovisionamiento cuando se haya creado. De forma predeterminada, Windows Configuration Designer usa la carpeta del proyecto como ubicación de salida. Si desea cambiar la ubicación de salida, seleccione **Examinar.** Cuando haya terminado, seleccione **Siguiente**.
1. Seleccione **Compilar** para empezar a compilar el paquete. El paquete de aprovisionamiento no tarda mucho tiempo en compilarse. La página de compilación muestra la información del proyecto y la barra de progreso indica el estado de compilación.

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>Paquete de aprovisionamiento, paso 3 &ndash; Aplicar el paquete de aprovisionamiento a HoloLens

El artículo "Configurar HoloLens mediante un paquete de aprovisionamiento" proporciona instrucciones detalladas para aplicar el paquete de aprovisionamiento en las siguientes circunstancias:

- Inicialmente, puede aplicar [un paquete de aprovisionamiento a HoloLens durante la instalación de](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

- También puede aplicar [un paquete de aprovisionamiento a HoloLens después de configurar](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>Use el Windows Portal de dispositivos para configurar un quiosco de una sola aplicación

Para configurar el modo de pantalla completa mediante el Windows Portal de dispositivos, siga estos pasos.

1. [Configure el dispositivo HoloLens para usar el Windows Portal de dispositivos](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal). Device Portal es un servidor web en el dispositivo HoloLens al que puedes conectarte desde un navegador web del equipo.

    > [!CAUTION]
    > Al configurar el HoloLens usar el Portal de dispositivos, tendrá que habilitar el modo de desarrollador en el dispositivo. El modo de desarrollador en un dispositivo que Windows Holographic for Business permite realizar una carga lateral de las aplicaciones. Sin embargo, esta configuración crea un riesgo de que un usuario pueda instalar aplicaciones que no hayan sido certificadas por el Microsoft Store. Los administradores pueden bloquear la capacidad de habilitar el modo de desarrollador mediante la configuración **ApplicationManagement/AllowDeveloper Unlock** en el [CSP de directiva.](/windows/client-management/mdm/policy-configuration-service-provider) [Obtén más información sobre el modo de desarrollador.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. En un equipo, conéctese al HoloLens mediante [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) o [USB.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)

1. Realice una de las siguientes acciones:
   - Si se va a conectar a la Windows Portal de dispositivos por primera vez, [cree un nombre de usuario y una contraseña.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Escriba el nombre de usuario y la contraseña que ha configurado anteriormente.

    > [!TIP]
    > Si aparece un error de certificado en el navegador, sigue [estos pasos de solución de problemas](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate) (vínculo en inglés).

1. En la Windows Portal de dispositivos, seleccione **Pantalla completa.**

1. Seleccione **Habilitar pantalla completa,** seleccione una aplicación que se ejecutará cuando se inicie el dispositivo y, a continuación, **seleccione Guardar.**

    ![Pantalla completa](images/kiosk.png)
1. Reinicie HoloLens. Si todavía tiene abierta la Portal de dispositivos, puede seleccionar **Reiniciar** en la parte superior de la página.

> [!NOTE]
> El modo de pantalla completa se puede establecer a través de la API REST de Portal de dispositivos si se realiza una operación POST en /api/holographic/kioskmode/settings con un parámetro de cadena de consulta necesario ("kioskModeEnabled&quot; con un valor de &quot;true&quot; o &quot;false") y un parámetro opcional ("startupApp" con un valor de un nombre de paquete). Tenga en cuenta que Portal de dispositivos está diseñado para desarrolladores y no debe habilitarse en dispositivos que no son de desarrollador. La API REST está sujeta a cambios en futuras actualizaciones o versiones.

## <a name="more-information"></a>Más información

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>Vea cómo configurar una pantalla completa mediante un paquete de aprovisionamiento.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>Acceso asignado global: modo de pantalla completa
- Se ha reducido la administración de identidades para quiosco, al habilitar el nuevo método de quiosco que aplica el modo de pantalla completa en el nivel del sistema.

Esta nueva característica permite a un administrador de TI configurar un dispositivo HoloLens 2 para el modo de pantalla completa de varias aplicaciones que es aplicable en el nivel del sistema, no tiene afinidad con ninguna identidad en el sistema y se aplica a todos los usuarios que inician sesión en el dispositivo. Consulte la documentación HoloLens pantalla completa [de acceso asignado global](hololens-global-assigned-access-kiosk.md) para obtener más detalles sobre esta nueva característica.

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Inicio automático de una aplicación en pantalla completa con varias aplicaciones 
- Experiencia centrada en el inicio automático de aplicaciones, lo que aumenta aún más la interfaz de usuario y las selecciones de aplicaciones elegidas para las experiencias de pantalla completa.

Solo se aplica al modo de pantalla completa de varias aplicaciones y solo se puede designar una aplicación para el inicio automático mediante el atributo resaltado a continuación en la configuración de acceso asignado. 

La aplicación se inicia automáticamente cuando el usuario inicia sesión. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Cambios de comportamiento del modo de pantalla completa para el control de errores
Al encontrar errores en la aplicación del modo de pantalla completa, aparece el comportamiento siguiente:

- Antes de Windows Holographic, la versión 20H2 - HoloLens mostrará todas las aplicaciones del menú Inicio.
- Windows Holographic, versión 20H2: si un dispositivo tiene una configuración de pantalla completa que es una combinación de acceso asignado global y acceso asignado a miembros del grupo de AAD, si se produce un error en la determinación de la pertenencia al grupo de AAD, el usuario verá el menú "No se muestra nada en el inicio".

![Imagen de lo que ahora se ve en pantalla completa cuando se produce un error.](images/hololens-kiosk-failure-behavior.png )


- A partir [Windows Holographic, versión 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)el modo quiosco busca acceso asignado global antes de mostrar un menú de inicio vacío. La experiencia de quiosco se reservará a una configuración global de quiosco (si está presente) en caso de errores durante el modo de quiosco de grupo de AAD.

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Pertenencia a Azure AD grupo de almacenamiento en caché para quiosco sin conexión

- Modo de quiosco más seguro mediante la eliminación de las aplicaciones disponibles en los errores de pantalla completa.
- Quioscos sin conexión habilitados para usarse Azure AD grupos durante un máximo de 60 días.

Esta directiva controla durante cuántos días se puede usar Azure AD caché de pertenencia a grupos para las configuraciones de acceso asignado que tienen como destino Azure AD grupos de usuarios que han iniciado sesión. Una vez que este valor de directiva se establece en un valor mayor que 0, solo se usa la memoria caché; de lo contrario, no.  

Nombre: AADGroupMembershipCacheValidityInDays VALOR DE URI: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Mín. - 0 días  
Máximo: 60 días 

Pasos para usar esta directiva correctamente: 
1. Cree un perfil de configuración de dispositivo para la pantalla completa Azure AD grupos y asígnelo a HoloLens dispositivos. 
1. Cree una configuración de dispositivo personalizada basada en uri de OMA que establece este valor de directiva en el número deseado de días (> 0) y asígnelo a HoloLens dispositivos. 
    1. El valor uri debe especificarse en el cuadro de texto OMA-URI como ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. El valor puede estar entre mínimo y máximo permitido.
1. Inscriba HoloLens dispositivos y compruebe que ambas configuraciones se aplican al dispositivo. 
1. Permita Azure AD inicio de sesión del usuario 1 cuando Internet esté disponible, una vez que el usuario inicie sesión y Azure AD la pertenencia Azure AD un grupo se confirme correctamente, se creará la memoria caché. 
1. Ahora Azure AD usuario 1 puede desconectar HoloLens y usarlo para el modo de pantalla completa siempre que el valor de directiva permita X número de días. 
1. Los pasos 4 y 5 se pueden repetir para cualquier otro usuario de Azure AD N. La clave aquí es que cualquier usuario de Azure AD debe iniciar sesión en el dispositivo mediante Internet, por lo que al menos una vez podemos determinar Azure AD que son miembros de un grupo al que está destinada la configuración de quiosco. 
 
> [!NOTE]
> Hasta que se realice el paso 4 para un Azure AD usuario experimentará un comportamiento de error mencionado en entornos "desconectados". 


## <a name="xml-kiosk-code-samples-for-hololens"></a>Ejemplos de código de quiosco XML para HoloLens

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Modo de pantalla completa de varias aplicaciones que tiene como destino Azure AD grupo. 
Esta pantalla completa implementa un quiosco que, para los usuarios del grupo Azure AD, tendrá habilitado un quiosco que incluye las tres aplicaciones: Configuración, Remote Assist y Centro de opiniones. Para modificar este ejemplo para que se utilice inmediatamente, asegúrese de cambiar el GUID resaltado a continuación para que coincida con un Azure AD grupo propio. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Modo de pantalla completa de varias aplicaciones Azure AD cuenta.
Esta pantalla completa implementa un quiosco para un solo usuario, tendrá un quiosco habilitado que incluye las tres aplicaciones: Configuración, Remote Assist y Centro de opiniones. Para modificar este ejemplo para que se utilice inmediatamente, asegúrese de cambiar la cuenta resaltada a continuación para que coincida con una Azure AD cuenta propia. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

