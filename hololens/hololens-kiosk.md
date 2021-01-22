---
title: Configurar HoloLens como un quiosco multimedia
description: Aprende a configurar y usar una configuración de quiosco para bloquear las aplicaciones en dispositivos HoloLens.
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
ms.openlocfilehash: 245de50fcaaf1235cce02cd1b6cae921b64f2851
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283991"
---
# Configurar HoloLens como un quiosco multimedia

Puedes configurar un dispositivo HoloLens para que funcione como un dispositivo de propósito fijo, también denominado quiosco de pantalla *completa,* configurando el dispositivo para que se ejecute en modo de pantalla completa. El modo de pantalla completa limita las aplicaciones (o los usuarios) que están disponibles en el dispositivo. El modo de pantalla completa es una característica práctica que puedes usar para dedicar un dispositivo HoloLens a aplicaciones empresariales o para usar el dispositivo HoloLens en una demostración de la aplicación.

En este artículo se proporciona información sobre aspectos de la configuración de quiosco que son específicos de los dispositivos HoloLens. Para obtener información general sobre los diferentes tipos de quioscos basados en Windows y cómo configurarlos, consulta Configurar quioscos y [signos digitales](https://docs.microsoft.com/windows/configuration/kiosk-methods)en las ediciones de escritorio de Windows.  

> [!IMPORTANT]  
> El modo de pantalla completa determina qué aplicaciones están disponibles cuando un usuario inicia sesión en el dispositivo. Sin embargo, el modo de pantalla completa no es un método de seguridad. No detiene que una aplicación "permitida" abra otra aplicación que no está permitida. Para bloquear la apertura de aplicaciones o procesos, usa Windows Defender CSP de Control de aplicaciones [(WDAC) para](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) crear directivas adecuadas.
>
> Obtenga más información sobre los servicios Microsoft para proporcionar a los usuarios un nivel avanzado de seguridad que HoloLens 2 usa, lea más sobre separación y aislamiento de estado: protecciones [de Defender.](security-state-separation-isolation.md#defender-protections) O aprenda a usar WDAC y Windows PowerShell para permitir o bloquear aplicaciones en [dispositivos HoloLens 2 con Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)

Puedes usar el modo de pantalla completa en una configuración de una sola aplicación o de varias aplicaciones, y puedes usar uno de los tres procesos para configurar e implementar la configuración de quiosco.

> [!IMPORTANT]  
> Al eliminar la configuración de varias aplicaciones, se quitan los perfiles de bloqueo de usuario que creó la característica de acceso asignado. Sin embargo, no revierte todos los cambios de directiva. Para revertir estas directivas, debes restablecer el dispositivo a la configuración de fábrica.

## Planear la implementación de quiosco

Al planear el quiosco, deberás poder responder a las siguientes preguntas. Estas son algunas decisiones que se deben tener en cuenta al leer esta página y algunas consideraciones para estas preguntas.
1. **¿Quién va a usar su quiosco y qué tipo de [cuenta(s)](hololens-identity.md) va a usar?** Esta es una decisión que probablemente ya has tomado y que no debería ajustarse por el bien de tu quiosco, pero afectará a cómo se asigna el quiosco más adelante.
1. **¿Necesitas tener quioscos distintos por usuario o grupo o un quiosco no habilitado para algunos?** Si es así, querrás crear el quiosco a través de XML. 
1. **¿Cuántas aplicaciones habrá en el quiosco?** Si tienes más de 1 aplicación, necesitarás un quiosco de varias aplicaciones. 
1. **¿Qué aplicaciones estarán en el quiosco?** Usa nuestra lista de AUMIDs a continuación para agregar cualquier In-Box aplicaciones además de las tuyas.
1. **¿Cómo planea implementar el quiosco?** Si estás inscribiendo el dispositivo en MDM, te sugerimos usar MDM para implementar el quiosco. Si no usas MDM, la implementación con el paquete de aprovisionamiento estará disponible.  

### Requisitos del modo de pantalla completa

Puedes configurar cualquier dispositivo HoloLens 2 para usar el modo de pantalla completa.

> [!IMPORTANT]
> El modo de pantalla completa solo está disponible si el dispositivo tiene Windows Holographic for Business. Todos los dispositivos HoloLens 2 se envían con Windows Holographic for Business y no hay otras ediciones. Todos los dispositivos HoloLens 2 pueden ejecutar el modo de pantalla completa de forma automática.
>
> Los dispositivos HoloLens (1.ª generación) deben actualizarse tanto en términos de compilación del sistema operativo como en la edición del sistema operativo. Aquí tiene más información sobre cómo actualizar un HoloLens (1.ª generación) a [Windows Holographic for Business](hololens1-upgrade-enterprise.md) Edition. Para actualizar un dispositivo HoloLens (1.ª generación) para usar el modo de pantalla completa, primero debes asegurarte de que el dispositivo ejecuta Windows 10, versión 1803 o una versión posterior. Si usó la Herramienta de recuperación de dispositivos windows para recuperar el dispositivo HoloLens (1.ª generación) en su compilación predeterminada, o si ha instalado las actualizaciones más recientes, el dispositivo está listo para configurarlo.

> [!IMPORTANT]  
> Para ayudar a proteger los dispositivos que se ejecutan en pantalla completa, considera la posibilidad de agregar directivas de administración de dispositivos que desactiven características como la conectividad USB. Además, comprueba la configuración del anillo de actualización para asegurarte de que las actualizaciones automáticas no se produzcan durante el horario comercial.

### Decidir entre un quiosco de una sola aplicación o un quiosco de varias aplicaciones

Un quiosco de una sola aplicación inicia la aplicación especificada cuando el usuario inicia sesión en el dispositivo. El menú Inicio está deshabilitado, al igual que Cortana. Un dispositivo HoloLens 2 no responde al gesto [Inicio.](hololens2-basic-usage.md#start-gesture) Un dispositivo HoloLens (1.ª generación) no responde al gesto [de bloom.](hololens1-basic-usage.md) Dado que solo se puede ejecutar una aplicación, el usuario no puede colocar otras aplicaciones.

Un quiosco de varias aplicaciones muestra el menú Inicio cuando el usuario inicia sesión en el dispositivo. La configuración de quiosco determina qué aplicaciones están disponibles en el menú Inicio. Puedes usar un quiosco de varias aplicaciones para proporcionar una experiencia fácil de entender para los usuarios presentándolos solo las cosas que tienen que usar y quitando las cosas que no necesitan usar.

En la tabla siguiente se enumeran las funciones de los diferentes modos de pantalla completa.

| &nbsp; |Menú Inicio |Menú Acciones rápidas |Cámara y vídeo |Miracast |Cortana |Comandos de voz integrados |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|Quiosco de una sola aplicación |Deshabilitada |Deshabilitada   |Deshabilitada |Deshabilitada   |Deshabilitada |Habilitado <sup> 1</sup> |
|Pantalla completa de varias aplicaciones |Habilitado |Habilitado <sup> 2</sup> |Disponible <sup> 2</sup> |Disponible <sup> 2</sup> |Disponible <sup> 2, 3</sup>  |Habilitado <sup> 1</sup> |

> <sup>1 </sup> Los comandos de voz relacionados con características deshabilitadas no funcionan.  
> <sup>2 </sup> Para obtener más información sobre cómo configurar estas características, consulta Seleccionar aplicaciones de [quiosco.](#plan-kiosk-apps)  
> <sup>3 </sup> Incluso si Cortana está deshabilitada, los comandos de voz integrados están habilitados.

En la tabla siguiente se enumeran las características de soporte técnico del usuario de los diferentes modos de pantalla completa.

| &nbsp; |Tipos de usuario admitidos | Inicio de sesión automático | Varios niveles de acceso |
| --- | --- | --- | --- |
|Quiosco de una sola aplicación |Cuenta de servicio administrada (MSA) en Azure Active Directory (Azure AD) o cuenta local |Sí |No |
|Pantalla completa de varias aplicaciones |Cuenta de Azure AD |No |Sí |

Para obtener ejemplos de cómo usar estas funcionalidades, consulte la tabla siguiente.

|Usa un quiosco de una sola aplicación para: |Usa un quiosco de varias aplicaciones para: |
| --- | --- |
|Un dispositivo que ejecuta solo una Guía de Dynamics 365 para nuevos empleados. |Un dispositivo que ejecuta guías y asistencia remota para una variedad de empleados. |
|Un dispositivo que ejecuta solo una aplicación personalizada. |Un dispositivo que funciona como quiosco para la mayoría de los usuarios (solo ejecuta una aplicación personalizada), pero funciona como un dispositivo estándar para un grupo específico de usuarios. |

### Planear aplicaciones de quiosco

Para obtener información general sobre cómo elegir aplicaciones de quiosco, consulta directrices para elegir una aplicación para el [acceso asignado (modo de pantalla completa).](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)

Si usas Windows Device Portal para configurar un quiosco de una sola aplicación, seleccionas la aplicación durante el proceso de configuración.  

Si usas un sistema de administración de dispositivos móviles (MDM) o un paquete de aprovisionamiento para configurar el modo de pantalla completa, usas el proveedor de servicios de configuración [(CSP) AssignedAccess](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) para especificar aplicaciones. El CSP usa [id. de modelo de usuario de aplicación (AUMIDs) para](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) identificar aplicaciones. En la tabla siguiente se enumeran los AUMID de algunas aplicaciones que puedes usar en un quiosco de varias aplicaciones.

> [!IMPORTANT]
> El modo de pantalla completa determina qué aplicaciones están disponibles cuando un usuario inicia sesión en el dispositivo. Sin embargo, el modo de pantalla completa no es un método de seguridad. No detiene que una aplicación "permitida" abra otra aplicación que no está permitida. Dado que no se restringe este comportamiento, las aplicaciones aún se pueden iniciar desde Edge, el Explorador de archivos y las aplicaciones de Microsoft Store. Si hay aplicaciones específicas que no quieres iniciar desde un quiosco, usa Windows Defender CONTROL DE APLICACIONES [(WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) para crear directivas adecuadas. 
> 
> Además, la página principal de realidad mixta no puede establecerse como una aplicación de quiosco.

<a id="aumids"></a>

|Nombre de la aplicación |AUMID |
| --- | --- |
|Visor 3D |Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\! Microsoft.Microsoft3DViewer |
|Calendario |microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\!microsoft.windowslive.calendar |
|Cámara <sup> 1, 2</sup> |HoloCamera\_cw5n1h2txyewy\! HoloCamera |
|Cortana <sup> 3</sup> |Microsoft.549981C3F5F10\_8wekyb3d8bbwe\! Aplicación |
|Selector de dispositivos en HoloLens (1.ª generación) |HoloDevicesFlow\_cw5n1h2txyewy\! HoloDevicesFlow |
|Selector de dispositivos en HoloLens 2 |Microsoft.Windows.DevicesFlowHost\_cw5n1h2txyewy\! Microsoft.Windows.DevicesFlowHost |
|Dynamics 365 Guides |Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\! Microsoft.RemoteAssist |
|Centro de &nbsp; opiniones |Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\! Aplicación |
|Explorador de archivos |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Correo |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast <sup> 4</sup> |&nbsp; |
|Películas y TV |Microsoft.ZuneVideo\_8wekyb3d8bbwe\! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive\_8wekyb3d8bbwe\! Aplicación |
|Fotos |Microsoft.Windows.Fotos\_8wekyb3d8bbwe\! Aplicación |
|Configuración |HolographicSystemSettings\_cw5n1h2txyewy\! Aplicación |
|Sugerencias |Microsoft.HoloLensTips\_8wekyb3d8bbwe\! HoloLensTips |

> <sup>1 Para habilitar la captura de fotos o vídeos, tienes que habilitar la aplicación </sup> Cámara como una aplicación de quiosco.  
> <sup>2 </sup> Cuando habilites la aplicación Cámara, ten en cuenta las siguientes condiciones:
> - El menú Acciones rápidas incluye los botones De foto y vídeo.  
> - También debe habilitar una aplicación (como Fotos, Correo o OneDrive) que pueda interactuar con o recuperar imágenes.  
>  
> <sup>3 Incluso si no habilitas Cortana como una aplicación de quiosco, se habilitan los comandos de voz </sup> integrados. Sin embargo, los comandos relacionados con las características deshabilitadas no tienen ningún efecto.  
> <sup>4 </sup> No puedes habilitar Miracast directamente. Para habilitar Miracast como una aplicación de quiosco, habilita la aplicación Cámara y la aplicación Selector de dispositivos.

### Planeación de perfiles de quiosco para usuarios o grupos

Al crear el archivo xml o usar la interfaz de usuario de Intune para configurar un quiosco, tendrás que tener en cuenta quién será el usuario del quiosco. Una configuración de quiosco puede limitarse a una cuenta individual o grupos de Azure AD. 

Normalmente, los quioscos están habilitados para un usuario o grupo de usuarios. Sin embargo, si tienes previsto escribir tu propio quiosco XML, es posible que quieras tener en cuenta el acceso asignado global, en el que el quiosco se aplica en el nivel de dispositivo independientemente de la identidad. Si esto es atractivo para ti, [lee más sobre quioscos de acceso asignado global.](hololens-global-assigned-access-kiosk.md)

#### Si va a crear un archivo XML:
-   Muchos de ellos crean varios perfiles de quiosco y los asignan a distintos usuarios o grupos. Por ejemplo, un quiosco de pantalla completa para el grupo de Azure AD que tiene muchas aplicaciones y un visitante que tiene un quiosco de varias aplicaciones con una aplicación singular.
-   La configuración de quiosco se denominará **Id. de** perfil y tendrá un GUID.
-   Asignará ese perfil en la sección configs especificando el tipo de usuario y usando el mismo GUID para el **identificador DefaultProfile**.
- Se puede crear un archivo XML, pero seguir aplicó a un dispositivo a través de MDM mediante la creación de un perfil de configuración de dispositivo OMA URI personalizado y su aplicación al grupo de dispositivos HoloLens con el valor de URI: ./Device/Vendor/MSFT/AssignedAccess/Configuration

#### Si va a crear un quiosco en Intune.
-   Cada dispositivo solo puede recibir un único perfil de quiosco, de lo contrario creará un conflicto y no recibirá ninguna configuración de quiosco. 
    -   Otros tipos de perfiles y directivas, como las restricciones de dispositivo que no están relacionadas con el perfil de configuración de quiosco multimedia, no entren en conflicto con el perfil de configuración de quiosco multimedia.
-   El quiosco se habilitará para todos los usuarios que forman parte del tipo de inicio de sesión de usuario, que se establecerá con un usuario o grupo de Azure AD. 
-   Una vez establecida la configuración de quiosco y el tipo de inicio de sesión de usuario **(los** usuarios que pueden iniciar sesión en la pantalla completa) y las aplicaciones seleccionadas, la configuración de dispositivo debe asignarse a un grupo. Los grupos asignados determinan qué dispositivos reciben la configuración del dispositivo de quiosco, pero no interactúa con ellos si el quiosco está habilitado o no. 
    - Para obtener una explicación completa de los efectos de asignar perfiles de configuración en Intune, vea Asignar perfiles de usuario y dispositivo [en Microsoft Intune.](https://docs.microsoft.com/intune/configuration/device-profile-assign)

### Seleccionar un método de implementación

Puedes seleccionar uno de los siguientes métodos para implementar configuraciones de quiosco:

- [Microsoft Intune u otro servicio de administración de dispositivos móviles (MDM)](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Paquete de aprovisionamiento](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Device Portal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Dado que este método requiere que el modo de desarrollador esté habilitado en el dispositivo, te recomendamos que lo uses solo para demostraciones.

En la tabla siguiente se enumeran las capacidades y las ventajas de cada uno de los métodos de implementación.

| &nbsp; |Implementar con Windows Device Portal |Implementar mediante un paquete de aprovisionamiento |Implementar con MDM |
| --------------------------- | ------------- | -------------------- | ---- |
|Implementar quioscos de una sola aplicación   | Sí           | Sí                  | Sí  |
|Implementar quioscos multia app    | No            | Sí                  | Sí  |
|Implementar solo en dispositivos locales | Sí           | Sí                  | No   |
|Implementar con el modo de desarrollador |Obligatorio       | No obligatorio            | No obligatorio   |
|Implementación mediante Azure Active Directory (Azure AD)  | No obligatorio            | No obligatorio                   | Obligatorio  |
|Implementar automáticamente      | No            | No                   | Sí  |
|Velocidad de implementación            | Fast       | Fast                 | Nivel lento |
|Implementar a escala | No recomendado    | Recomendaciones        | Recomendaciones |

## Usar Microsoft Intune u otro SISTEMA MDM para configurar un quiosco de una sola aplicación o de varias aplicaciones

Para configurar el modo de pantalla completa mediante Microsoft Intune u otro sistema MDM, sigue estos pasos.

1. [Prepárese para inscribir los dispositivos.](#mdmenroll)
1. [Crear un perfil de configuración de quiosco.](#mdmprofile)
1. Configurar el quiosco.
   - [Configure las opciones para un quiosco de una sola aplicación.](#mdmconfigsingle)
   - [Configura las opciones de un quiosco de varias aplicaciones.](#mdmconfigmulti)
1. [Asignar el perfil de configuración de quiosco a un grupo.](#mdmassign)
1. Implementa los dispositivos.
   - [Implementar un quiosco de una sola aplicación.](#mdmsingledeploy)
   - [Implementar un quiosco de varias aplicaciones.](#mdmmultideploy)

### <a id="mdmenroll"></a>MDM, paso 1 &ndash; Prepararse para inscribir los dispositivos

Puedes configurar el sistema MDM para inscribir dispositivos HoloLens automáticamente cuando el usuario inicie sesión por primera vez o hacer que los usuarios inscriban dispositivos manualmente. Los dispositivos también deben unirse a tu dominio de Azure AD y asignarse a los grupos adecuados.

Para obtener más información sobre cómo inscribir los [dispositivos, consulta Inscribir HoloLens](hololens-enroll-mdm.md) en los métodos de inscripción de MDM e [Intune para dispositivos Windows.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)

### <a id="mdmprofile"></a>MDM, paso 2 &ndash; Crear un perfil de configuración de quiosco

1. Abre [Azure](https://portal.azure.com/) Portal e inicia sesión en tu cuenta de administrador de Intune.
1. Selecciona **Configuración de dispositivo**de Microsoft  >  **Intune: perfiles**  >  **crear perfil.**
1. Escriba un nombre de perfil.
1. Selecciona **Plataforma**  >  **Windows 10 y versiones posteriores**y, a continuación, selecciona **Restricciones**de dispositivo  > **de tipo de perfil.**
1. Seleccione **Configurar**  >  **quiosco**y, a continuación, seleccione una de las siguientes opciones:
   - Para crear un quiosco de una sola aplicación, selecciona **Quiosco de**pantalla completa de  >  **aplicación única.**
   - Para crear un quiosco de varias aplicaciones, selecciona **Quiosco**de pantalla completa  >  **de varias aplicaciones.**
1. Para empezar a configurar el quiosco, seleccione **Agregar**.

Los pasos siguientes varían en función del tipo de quiosco que quieras. Para obtener más información, seleccione una de las siguientes opciones:  

- [Quiosco de una sola aplicación](#mdmconfigsingle)
- [Pantalla completa de varias aplicaciones](#mdmconfigmulti)

Para obtener más información sobre cómo crear un perfil de configuración de quiosco, consulta la configuración de dispositivos Windows [10](https://docs.microsoft.com/intune/configuration/kiosk-settings)y Windows Holographic for Business para ejecutarse como quiosco dedicado con Intune.

### <a id="mdmconfigsingle"></a>MDM, paso 3 (aplicación única) Configurar las &ndash;  opciones para un quiosco de una sola aplicación

En esta sección se resume la configuración que requiere un quiosco de una sola aplicación. Para obtener más información, consulte los artículos siguientes:

- Para obtener información sobre cómo configurar un perfil de configuración de quiosco en Intune, consulta Cómo configurar el modo de pantalla [completa con Microsoft Intune.](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)
- Para obtener más información sobre la configuración disponible para quioscos de una sola aplicación en Intune, consulta [Quioscos](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks) de una sola aplicación de pantalla completa
- Para ver otros servicios de MDM, consulte la documentación de su proveedor para obtener las instrucciones. Si tienes que usar una configuración XML personalizada para configurar un quiosco en el servicio MDM, crea un archivo XML que [defina la configuración de quiosco.](#ppkioskconfig)

1. Seleccione **El tipo de**inicio de sesión de usuario Cuenta de usuario local y, a continuación, escriba el nombre de usuario de la cuenta local (dispositivo) o la cuenta de Microsoft (MSA) que puede iniciar sesión en el  >  **** quiosco.
   > [!NOTE]  
   > **Los tipos de cuenta** de usuario de inicio de sesión automático no se admiten en Windows Holographic for Business.
1. Selecciona **aplicación de la**Tienda de tipo de aplicación  >  **** y, a continuación, selecciona una aplicación de la lista.

El siguiente paso es [asignar el](#mdmassign) perfil a un grupo.

### <a id="mdmconfigmulti"></a>MDM, paso 3 (varias aplicaciones) Configurar las &ndash; opciones de un quiosco de varias aplicaciones

En esta sección se resume la configuración que requiere un quiosco de varias aplicaciones. Para obtener información más detallada, vea los artículos siguientes:

- Para obtener información sobre cómo configurar un perfil de configuración de quiosco en Intune, consulta Cómo configurar el modo de pantalla [completa con Microsoft Intune.](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)
- Para obtener más información sobre la configuración disponible para quioscos de varias aplicaciones en Intune, consulta [Quioscos de varias aplicaciones](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- Para ver otros servicios de MDM, consulte la documentación de su proveedor para obtener las instrucciones. Si necesitas usar una configuración XML personalizada para configurar un quiosco en el servicio MDM, crea un archivo XML que [defina la configuración de quiosco.](#ppkioskconfig) Si usa un archivo XML, asegúrese de incluir el diseño [de la pantalla Inicio.](#start-layout-for-hololens)  
- Opcionalmente, puedes usar un diseño de inicio personalizado con Intune u otros servicios MDM. Para obtener más información, consulta El archivo [de diseño de la pantalla Inicio para MDM (Intune y otros).](#start-layout-file-for-mdm-intune-and-others)

1. Selecciona **Windows 10 de destino en dispositivos en modo S**  >  **No**.  
   >[!NOTE]  
   > El modo S no se admite en Windows Holographic for Business.
1. Seleccione **Usuario de tipo de**inicio de sesión usuario usuario o grupo de Azure AD o usuario tipo de inicio de sesión  >  **** ****  >  **holoLens**visitante y, a continuación, agregue uno o más grupos de usuarios o cuentas.  

   Solo los usuarios que pertenecen a los grupos o cuentas que especifique en el tipo de inicio de sesión **de** usuario pueden usar la experiencia de pantalla completa.

1. Selecciona una o más aplicaciones mediante las siguientes opciones:
   - Para agregar una aplicación de línea de negocio cargada, selecciona **Agregar** aplicación de la Tienda y, a continuación, selecciona la aplicación que quieras.
   - Para agregar una aplicación especificando su AUMID, selecciona Agregar por **AUMID** y, a continuación, escribe el AUMID de la aplicación. [Consulta la lista de AUMIDs disponibles](#aumids)

El siguiente paso es [asignar el](#mdmassign) perfil a un grupo.

### <a id="mdmassign"></a>MDM, paso 4 Asignar &ndash; el perfil de configuración de quiosco a un grupo

Usa la **página Asignaciones del** perfil de configuración de quiosco para establecer dónde quieres que se implemente la configuración de quiosco. En el caso más sencillo, asignas el perfil de configuración de quiosco a un grupo que contendrá el dispositivo HoloLens cuando el dispositivo se inscriba en MDM.

### <a id="mdmsingledeploy"></a>MDM, paso 5 (aplicación única) Implementar &ndash; un quiosco de una sola aplicación

Cuando usas un sistema MDM, puedes inscribir el dispositivo en MDM durante la OOBE. Una vez que finaliza la OOBE, es fácil iniciar sesión en el dispositivo.

Durante la OOBE, siga estos pasos:

1. Inicia sesión con la cuenta que especificaste en el perfil de configuración de quiosco.
1. Inscribe el dispositivo. Asegúrate de que el dispositivo se agrega al grupo al que está asignado el perfil de configuración de quiosco.
1. Espera a que finalice la OOBE, a que la aplicación de la Tienda se descargue e instale y a que se apliquen directivas. A continuación, reinicia el dispositivo.

La próxima vez que inicies sesión en el dispositivo, la aplicación de pantalla completa debería iniciarse automáticamente.

Si no ve la configuración de quiosco en este momento, [compruebe el estado de asignación.](https://docs.microsoft.com/intune/configuration/device-profile-monitor)

### <a id="mdmmultideploy"></a>MDM, paso 5 (varias aplicaciones) Implementar &ndash; un quiosco de varias aplicaciones

Cuando usas un sistema MDM, puedes unir el dispositivo a tu inquilino de Azure AD e inscribir el dispositivo en MDM durante la OOBE. Si corresponde, proporcione la información de inscripción a los usuarios para que la tengan disponible durante el proceso de OOBE.

> [!NOTE]  
> Si has asignado el perfil de configuración de quiosco a un grupo que contiene usuarios, asegúrate de que una de esas cuentas de usuario sea la primera cuenta en iniciar sesión en el dispositivo.

Durante la OOBE, siga estos pasos:

1. Inicie sesión con la cuenta que pertenece al grupo **de tipos de inicio de sesión de** usuario.
1. Inscribe el dispositivo.
1. Espera a que las aplicaciones que forman parte del perfil de configuración de quiosco se descarguen e instalen. Además, espere a que se apliquen directivas.  
1. Una vez que finalice la OOBE, puedes instalar aplicaciones adicionales desde Microsoft Store o mediante la instalación de instalación local. [Aplicaciones necesarias](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) para que el grupo al que pertenece el dispositivo se instale automáticamente.
1. Una vez finalizada la instalación, reinicia el dispositivo.

La próxima vez que inicies sesión en el dispositivo con una cuenta que pertenezca al tipo de inicio de sesión **usuario,** la aplicación de pantalla completa debería iniciarse automáticamente.

Si no ve la configuración de quiosco en este momento, [compruebe el estado de asignación.](https://docs.microsoft.com/intune/configuration/device-profile-monitor)

## Usar un paquete de aprovisionamiento para configurar un quiosco de una sola aplicación o de varias aplicaciones

Para configurar el modo de pantalla completa mediante un paquete de aprovisionamiento, sigue estos pasos.

1. [Cree un archivo XML que defina la configuración de quiosco.](#ppkioskconfig), incluido [un diseño de inicio.](#start-layout-for-hololens)
2. [Agrega el archivo XML a un paquete de aprovisionamiento.](#ppconfigadd)
3. [Aplica el paquete de aprovisionamiento a HoloLens.](#ppapply)

### <a id="ppkioskconfig"></a>Paquete de aprovisionamiento, paso 1 &ndash; Crear un archivo XML de configuración de quiosco

Sigue las instrucciones generales para crear un archivo XML de configuración de pantalla completa para el escritorio de [Windows,](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)excepto para lo siguiente:

- No incluyas aplicaciones clásicas de Windows (Win32). HoloLens no admite estas aplicaciones.
- Usa el xml [de diseño de inicio](#start-layout-for-hololens) de marcador de posición para HoloLens.
- Opcional: agregar acceso de invitado a la configuración de quiosco

#### <a id="ppkioskguest"></a>Opcional: agregar acceso de invitado a la configuración de quiosco

En la [ **sección Configs** del archivo XML,](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)puedes configurar un grupo especial denominado **Visitor** para permitir que los invitados usen el quiosco. Cuando el quiosco está configurado para admitir el **grupo** especial Visitantes, se agrega una opción **"** Invitado " a la página de inicio de sesión. La **cuenta** de invitado no requiere una contraseña y los datos asociados con la cuenta se eliminan cuando la cuenta cierra sesión.

Para habilitar la **cuenta de** invitado, agregue el siguiente fragmento de código al XML de configuración de quiosco:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a id="start-layout-for-hololens"></a>Diseño de inicio de marcador de posición para HoloLens

Si usas un paquete [de aprovisionamiento](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) para configurar un quiosco de varias aplicaciones, el procedimiento requiere un diseño de Inicio. La personalización del diseño de la pantalla Inicio no es compatible con Windows Holographic for Business. Por lo tanto, tendrás que usar un diseño de inicio de marcador de posición.

> [!NOTE]  
> Dado que un quiosco de una sola aplicación inicia la aplicación de quiosco cuando un usuario inicia sesión, no usa un menú Inicio y no tiene que tener un diseño de Inicio.

> [!NOTE]  
> Si [usas MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) para configurar un quiosco de varias aplicaciones, opcionalmente puedes usar un diseño de Inicio. Para obtener más información, consulta el archivo de diseño de inicio de marcador de posición [para MDM (Intune y otros).](#start-layout-file-for-mdm-intune-and-others)

Para el diseño de La pantalla Inicio, agrega la siguiente **sección StartLayout** al archivo XML de aprovisionamiento de quiosco:

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

#### <a id="start-layout-file-for-mdm-intune-and-others"></a>Archivo de diseño de inicio de marcador de posición para MDM (Intune y otros)

Guarde el ejemplo siguiente como un archivo XML. Puedes usar este archivo al configurar el quiosco de varias aplicaciones en Microsoft Intune (o en otro servicio MDM que proporciona un perfil de quiosco).

> [!NOTE]
> Si tienes que usar una configuración personalizada y una configuración XML completa para configurar un quiosco en el servicio MDM, usa las instrucciones de diseño de inicio [para un paquete de aprovisionamiento.](#start-layout-for-hololens)

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

### <a id="ppconfigadd"></a>Prov. paquete, paso 2 Agregar el archivo XML de configuración &ndash; de quiosco a un paquete de aprovisionamiento

1. Abra [el Diseñador de configuraciones de Windows](https://www.microsoft.com/store/apps/9nblggh4tx22).
1. Seleccione **Aprovisionamiento avanzado,** escriba un nombre para el proyecto y, a continuación, **seleccione Siguiente**.
1. Seleccione **Windows 10 Holographic**y, a continuación, seleccione **Siguiente**.
1. Seleccione **Finalizar**. Se abrirá el área de trabajo para el paquete.
1. Seleccione **Configuración de tiempo de**ejecución  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**.
1. En el panel central, selecciona **Examinar para** buscar y seleccionar el archivo XML de configuración de quiosco que creaste.

   ![Captura de pantalla del campo MultiAppAssignedAccessSettings en el Diseñador de configuración de Windows](./images/multiappassignedaccesssettings.png)

1. **Opcional**. (Si quieres aplicar el paquete de aprovisionamiento después de la configuración inicial del dispositivo y ya hay un usuario administrador disponible en el dispositivo de pantalla completa, omite este paso). Seleccione **Configuración de tiempo de** ejecución &gt; **Usuarios** &gt; **de**cuentas y, a continuación, cree una cuenta de usuario. Proporcione un nombre de usuario y una contraseña y, a continuación, **seleccione Administradores de grupo de**  >  **usuarios.**  
  
     Con esta cuenta, puede ver el estado de aprovisionamiento y los registros.  
1. **Opcional**. (Si ya tienes una cuenta que no es de administrador en el dispositivo de quiosco, omite este paso). Seleccione **Configuración de tiempo de** ejecución &gt; **Usuarios** &gt; **de**cuentas y, a continuación, cree una cuenta de usuario local. Asegúrese de que el nombre de usuario sea el mismo que para la cuenta que especifique en el XML de configuración. Seleccione **Usuarios estándar de UserGroup**  >  ****.
1. Seleccione **Guardar**  >  **archivo.**
1. Seleccione **Exportar paquete**de  >  **aprovisionamiento**y, a continuación, seleccione Administrador **de**  >  **TI propietario.** Esto establece la prioridad de este paquete de aprovisionamiento más alta que los paquetes de aprovisionamiento que se aplican a este dispositivo desde otros orígenes.
1. Selecciona **Siguiente**.
1. En la página **Seguridad del paquete de** aprovisionamiento, selecciona una opción de seguridad.
   > [!IMPORTANT]  
   > Si seleccionas **Habilitar firma de paquete,** también tienes que seleccionar un certificado válido para firmar el paquete. Para ello, seleccione **Examinar** y seleccione el certificado que desea usar para firmar el paquete.
   
   > [!CAUTION]  
   > No seleccione Habilitar **cifrado de paquete.** En los dispositivos HoloLens, esta configuración hace que el aprovisionamiento falle.
1. Selecciona **Siguiente**.
1. Especifica la ubicación de salida donde quieres que vaya el paquete de aprovisionamiento cuando se cree. De forma predeterminada, el Diseñador de configuraciones de Windows usa la carpeta de proyecto como la ubicación de salida. Si desea cambiar la ubicación de salida, seleccione **Examinar**. Cuando haya terminado, seleccione **Siguiente**.
1. Selecciona **Generar** para empezar a compilar el paquete. El paquete de aprovisionamiento no tarda mucho tiempo en compilarse. La página de compilación muestra la información del proyecto y la barra de progreso indica el estado de la compilación.

### <a id="ppapply"></a>Paquete de aprovisionamiento, paso 3 &ndash; Aplicar el paquete de aprovisionamiento a HoloLens

El artículo "Configurar HoloLens mediante un paquete de aprovisionamiento" proporciona instrucciones detalladas para aplicar el paquete de aprovisionamiento en las siguientes circunstancias:

- Puedes aplicar inicialmente [un paquete de aprovisionamiento a HoloLens durante la instalación.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

- También puedes aplicar [un paquete de aprovisionamiento a HoloLens después de la configuración.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)

## Usar Windows Device Portal para configurar un quiosco de una sola aplicación

Para configurar el modo de pantalla completa mediante Windows Device Portal, sigue estos pasos.

1. [Configurar el dispositivo HoloLens para usar Windows Device Portal.](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal) Device Portal es un servidor web en el dispositivo HoloLens al que puedes conectarte desde un navegador web del equipo.

    > [!CAUTION]
    > Cuando configuras HoloLens para usar Device Portal, tienes que habilitar el modo de desarrollador en el dispositivo. El modo de desarrollador en un dispositivo que tiene Windows Holographic for Business te permite cargar localmente aplicaciones. Sin embargo, esta configuración crea un riesgo de que un usuario pueda instalar aplicaciones que no hayan sido certificadas por Microsoft Store. Los administradores pueden bloquear la capacidad de habilitar el modo de desarrollador mediante la configuración **ApplicationManagement/AllowDeveloper Unlock** en el [CSP de directivas.](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) [Obtén más información acerca del modo de desarrollador.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. En un equipo, conéctese a HoloLens mediante [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) o [USB.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)

1. Realiza una de las siguientes acciones:
   - Si vas a conectarte a Windows Device Portal por primera vez, [crea un nombre de usuario y una contraseña](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Escriba el nombre de usuario y la contraseña que ha configurado anteriormente.

    > [!TIP]
    > Si aparece un error de certificado en el navegador, sigue [estos pasos de solución de problemas](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate) (vínculo en inglés).

1. En Windows Device Portal, selecciona Modo **de pantalla completa.**

1. Selecciona **Habilitar modo de pantalla completa,** selecciona una aplicación para que se ejecute cuando se inicie el dispositivo y, a continuación, selecciona **Guardar.**

    ![Pantalla completa](images/kiosk.png)
1. Reinicie HoloLens. Si aún tienes abierta la página de Device Portal, puedes seleccionar **Reiniciar** en la parte superior de la página.

> [!NOTE]
> El modo de pantalla completa se puede establecer a través de la API de REST de Device Portal haciendo una solicitud POST en /api/holographic/kioskmode/settings con un parámetro de cadena de consulta necesario ("kioskModeEnabled" con un valor de "true" o "false") y un parámetro opcional ("startupApp" con un valor de nombre de paquete). Ten en cuenta que Device Portal está pensado solo para desarrolladores y no debe estar habilitado en dispositivos que no sean de desarrollador. La API de REST está sujeta a cambios en futuras actualizaciones o versiones.

## Más información

### Observa cómo configurar un quiosco con un paquete de aprovisionamiento.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### Acceso asignado global: modo de pantalla completa
- Reducción de la administración de identidades para quiosco, habilitando un nuevo método de quiosco que aplica el modo de pantalla completa en el nivel del sistema.

Esta nueva característica permite a un administrador de TI configurar un dispositivo HoloLens 2 para el modo de pantalla completa de varias aplicaciones que se aplica a nivel del sistema, no tiene afinidad con ninguna identidad en el sistema y se aplica a todos los usuarios que inician sesión en el dispositivo. Consulta la [documentación de quiosco](hololens-global-assigned-access-kiosk.md) de acceso asignado global de HoloLens para obtener más información sobre esta nueva característica.

### Inicio automático de una aplicación en modo de pantalla completa de varias aplicaciones 
- Experiencia centrada con el inicio automático de la aplicación, aumentando aún más la interfaz de usuario y las selecciones de aplicaciones elegidas para las experiencias de modo de pantalla completa.

Solo se aplica al modo de pantalla completa de varias aplicaciones y solo se puede designar una aplicación para el inicio automático mediante el atributo resaltado siguiente en la configuración de acceso asignado. 

La aplicación se inicia automáticamente cuando el usuario inicia sesión. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### Cambios en el comportamiento del modo de pantalla completa para controlar errores
- Modo de pantalla completa más seguro al eliminar las aplicaciones disponibles en los errores del modo de pantalla completa. 

Anteriormente, al encontrar errores al aplicar el modo de pantalla completa, HoloLens se usaba para mostrar todas las aplicaciones en el menú Inicio. Ahora en Windows Holographic versión 20H2 en caso de errores, no se mostrará ninguna aplicación en el menú inicio como se muestra a continuación: 

![Imagen del aspecto que tiene ahora el modo de pantalla completa cuando se produce un error.](images/hololens-kiosk-failure-behavior.png )

### Almacenar en caché la pertenencia a grupos de Azure AD para quiosco sin conexión
- Quioscos sin conexión habilitados para usarse con grupos de Azure AD durante un máximo de 60 días.

Esta directiva controla durante cuántos días se permite usar la memoria caché de pertenencia a grupos de Azure AD para las configuraciones de acceso asignado destinadas a grupos de Azure AD para usuarios que han iniciado sesión. Una vez que este valor de directiva se establece en un valor mayor que 0, solo se usa la memoria caché; de lo contrario, no se usa la memoria caché.  

Nombre: Valor uri AADGroupMembershipCacheValidityInDays: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Mínimo: 0 días  
Máximo: 60 días 

Pasos para usar esta directiva correctamente: 
1. Crea un perfil de configuración de dispositivo para quiosco de pantalla completa destinado a grupos de Azure AD y asígnelo a dispositivos HoloLens. 
1. Crea una configuración de dispositivo personalizada basada en OMA URI que establece este valor de directiva en el número de días deseado (> 0) y asígnelo a dispositivos HoloLens. 
    1. El valor uri debe especificarse en el cuadro de texto OMA-URI como ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. El valor puede estar entre mínimo/máximo permitido.
1. Inscribe dispositivos HoloLens y comprueba que ambas configuraciones se apliquen al dispositivo. 
1. Permitir que el usuario 1 de Azure AD inicie sesión cuando Internet esté disponible, una vez que el usuario inicie sesión y la pertenencia al grupo de Azure AD se confirme correctamente, se creará la memoria caché. 
1. Ahora, el usuario 1 de Azure AD puede desconectar HoloLens y usarlo para el modo de pantalla completa siempre que el valor de la directiva permita X número de días. 
1. Los pasos 4 y 5 se pueden repetir para cualquier otro usuario de Azure AD N. El punto clave aquí es que cualquier usuario de Azure AD debe iniciar sesión en el dispositivo con Internet, por lo que al menos una vez podemos determinar que son miembros del grupo de Azure AD al que está destinada la configuración de quiosco. 
 
> [!NOTE]
> Hasta que se realice el paso 4 para un usuario de Azure AD experimentará el comportamiento de error mencionado en entornos "desconectados". 


## Ejemplos de código de quiosco xml para HoloLens

### Modo de pantalla completa de varias aplicaciones destinado a un grupo de Azure AD. 
Este quiosco implementa un quiosco que, para los usuarios del grupo de Azure AD, tendrá habilitado un quiosco que incluye las 3 aplicaciones: Configuración, Asistencia remota y Centro de opiniones. Para modificar este ejemplo para que se utilice inmediatamente, asegúrese de cambiar el GUID resaltado a continuación para que coincida con un grupo de Azure AD propio. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### Modo de pantalla completa de varias aplicaciones destinado a la cuenta de Azure AD.
Este quiosco implementa un quiosco para un solo usuario, tendrá habilitado un quiosco que incluye las 3 aplicaciones: Configuración, Asistencia remota y Centro de opiniones. Para modificar este ejemplo para que se utilice inmediatamente, asegúrate de cambiar la cuenta resaltada a continuación para que coincida con una cuenta de Azure AD propia. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

