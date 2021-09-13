---
title: Configuración de HoloLens como un quiosco multimedia
description: Aprenda a configurar y usar una configuración de quiosco para bloquear las aplicaciones en HoloLens dispositivos.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e856ac74e959743e8d05ea6acf583700a6450373
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033198"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Configuración de HoloLens como un quiosco multimedia

## <a name="what-is-kiosk-mode"></a>¿Qué es el modo quiosco?

El modo de pantalla completa es una característica en la que puede controlar qué aplicaciones se muestran en el menú Inicio cuando un usuario inicia sesión en HoloLens. Hay dos escenarios admitidos:

1. **Modo de pantalla completa de aplicación** única: no se muestra ningún menú inicio y se inicia automáticamente una sola aplicación cuando el usuario inicia sesión. <br> *En el ejemplo* se usa : un dispositivo que solo se ejecuta Dynamics 365 Guides aplicación.
2. **Modo de pantalla completa de** varias aplicaciones: menú Inicio muestra solo las aplicaciones que se especificaron en la configuración de quiosco cuando un usuario inicia sesión. Se puede elegir que una aplicación se inicie automáticamente si lo desea. <br> *En el ejemplo* se usa : un dispositivo que muestra solo la aplicación de la Tienda, Centro de opiniones y Configuración en el menú Inicio.

    <img alt="Multi app kiosk example" src=".\images\multi-app-kiosk.jpg" width="411" height="500" />

## <a name="description-of-kiosk-mode-experience-when-a-user-signs-in"></a>Descripción de la experiencia en pantalla completa cuando un usuario inicia sesión

En la tabla siguiente se enumeran las funcionalidades de características en los distintos modos de quiosco.

| &nbsp; |Menú Inicio |Menú Acciones rápidas |Cámara y vídeo |Miracast |Cortana |Comandos de voz integrados |
| --- | --- | --- | --- | --- | --- | --- |
|Quiosco de aplicación única |Disabled |Disabled |Disabled |Disabled   |Disabled |Habilitado* |
|Pantalla completa con varias operaciones |habilitado |Habilitado*  |Disponible*  |Disponible* |Disponible*   |Habilitado*  |

\*Para obtener más información sobre cómo habilitar las características deshabilitadas o cómo interactúan los comandos de voz con las características deshabilitadas y Cortana consulte HoloLens [AUMIDs for apps (AUMIDs para aplicaciones).](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)

## <a name="key-general-considerations-before-configuring-kiosk-mode"></a>Consideraciones generales clave antes de configurar el modo de pantalla completa

1. Determine el tipo de cuenta de usuario que inicia sesión en HoloLens en su entorno: HoloLens admite cuentas de Azure Active Directory (AAD), cuentas Microsoft (MSA) y cuentas locales. Además, también se admiten cuentas creadas temporalmente denominadas invitados o visitantes (solo para dispositivos de unión a AAD). Obtenga más información en [Administración de identidades de usuario e inicio de](hololens-identity.md)sesión para HoloLens .
2. Determinar los destinos de la experiencia del modo de pantalla completa: tanto si es todo el mundo, un solo usuario, determinados usuarios o usuarios que son miembros de grupos de AAD, etc.
3. Para el modo de pantalla completa de varias aplicaciones, determine las aplicaciones que se mostrarán en el menú Inicio. Para cada aplicación, se necesita su identificador de modelo de [usuario de aplicación (AUMID).](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)
4. Determine si el modo de pantalla completa se aplicará a HoloLens a través de paquetes de aprovisionamiento en tiempo de ejecución o Administración de dispositivos móvil (MDM).

## <a name="security-considerations"></a>Consideraciones de seguridad

El modo de pantalla completa no debe considerarse como un método de seguridad, sino como un medio para controlar la experiencia de inicio en el inicio de sesión del usuario. Puede combinar la experiencia del modo de pantalla completa con las opciones que se mencionan a continuación si hay necesidades específicas relacionadas con la seguridad:

- Cuando Configuración aplicación esté configurada para mostrarse en pantalla completa y quiera controlar qué páginas se muestran en la aplicación Configuración, consulte Visibilidad de Configuración [página.](settings-uri-list.md)
- Si desea controlar el acceso a determinadas funcionalidades de hardware, por ejemplo, cámara, Bluetooth, etc., para determinadas aplicaciones, etc., consulte Directivas en CSP de directiva compatible con [HoloLens 2 - Windows Client Management](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2). Puede revisar las ideas sobre [las restricciones comunes de dispositivos.](hololens-common-device-restrictions.md)
- El modo de pantalla completa no bloquea que una aplicación (configurada como parte de la experiencia de pantalla completa) inicie otras aplicaciones. Si desea bloquear completamente el inicio de determinadas aplicaciones o procesos en HoloLens, consulte Uso de Windows Defender Application Control en HoloLens 2 [dispositivos en Microsoft Intune- Azure](/mem/intune/configuration/custom-profile-hololens)

## <a name="key-technical-considerations-for-kiosk-mode-for-hololens"></a>Consideraciones técnicas clave para el modo de pantalla completa para HoloLens

Solo se aplica si planea usar paquetes de aprovisionamiento en tiempo de ejecución o crear configuraciones de quiosco manualmente. La configuración del modo de pantalla completa usa una estructura jerárquica basada en XML:

- Un perfil de acceso asignado define qué aplicaciones se muestran en el menú Inicio en pantalla completa. Puede definir varios perfiles en la misma estructura XML, a los que se puede hacer referencia más adelante.
- Una configuración de acceso asignada hace referencia a un perfil y a los usuarios de destino de ese perfil, por ejemplo, un usuario específico, un grupo o visitante de AAD, etc. Puede definir varias configuraciones en la misma estructura XML en función de la complejidad de los escenarios de uso (consulte la sección escenarios admitidos a continuación).
- Para obtener más información, consulte AssignedAccess CSP ( [CSP de AssignedAccess).](/windows/client-management/mdm/assignedaccess-csp)

## <a name="supported-scenarios-for-kiosk-mode-based-on-identity-type"></a>Escenarios admitidos para el modo de quiosco en función del tipo de identidad

Consulte [los vínculos de](hololens-kiosk-reference.md#kiosk-xml-code-samples) referencia para obtener ejemplos basados en su escenario y actualizar según sea necesario antes de pegar la copia.

> [!NOTE]
> Use XML solo si no usa la interfaz de usuario de Intune para crear la configuración de quiosco.

### <a name="for-users-who-sign-in-as-either-local-account-or-msa"></a>Para los usuarios que inician sesión como cuenta local o MSA

| **Experiencia de quiosco deseado** | **Configuración recomendada de quiosco** | **Formas de configurar**  | **Comentarios:** |
| --- | --- | --- | --- |
| Todos los usuarios que inician sesión obtienen experiencia de quiosco. | [Configuración del perfil de acceso asignado global de varias aplicaciones](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune plantilla personalizada](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Aprovisionamiento en tiempo de ejecución: varias aplicaciones](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | El acceso global asignado requiere [20H2 y compilaciones más recientes](hololens-release-notes.md#windows-holographic-version-20h2) |
| Un usuario específico que inicia sesión obtiene la experiencia de quiosco.  | [Configure un perfil de acceso asignado a una o varias aplicaciones (según sea necesario) especificando el nombre del usuario específico.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [Consulte las opciones admitidas a continuación.](#steps-in-configuring-kiosk-mode-for-hololens) | Para el modo de pantalla completa de una sola aplicación, solo se admite la cuenta de usuario local o la cuenta de MSA HoloLens. <br> Para el modo de pantalla completa de varias aplicaciones, solo se admite la cuenta de MSA o la cuenta de AAD HoloLens. |

### <a name="for-users-who-sign-in-as-aad-account"></a>Para los usuarios que inician sesión como cuenta de AAD

| **Experiencia de quiosco deseado** | **Configuración recomendada de quiosco** | **Formas de configurar** | **Comentarios:** |
| --- | --- | --- | --- |
| Todos los usuarios que inician sesión obtienen experiencia de quiosco. | [Configuración del perfil de acceso asignado global de varias aplicaciones](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune plantilla personalizada](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Aprovisionamiento en tiempo de ejecución: varias aplicaciones](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | El acceso global asignado requiere [20H2 y compilaciones más recientes](hololens-release-notes.md#windows-holographic-version-20h2) |
| Todos los usuarios que inician sesión obtienen experiencia de quiosco, excepto determinados usuarios. | Configure el perfil de acceso asignado global de varias [aplicaciones excluyendo determinados usuarios (que deben ser propietarios de dispositivos).](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners) | • [Microsoft Intune plantilla personalizada](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Aprovisionamiento en tiempo de ejecución: varias aplicaciones](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | El acceso global asignado requiere [20H2 y compilaciones más recientes](hololens-release-notes.md#windows-holographic-version-20h2) |
| Cada usuario de AAD obtiene una experiencia de pantalla completa independiente específica para ese usuario. | [Configure la configuración de acceso asignado para cada usuario que especifique su nombre de cuenta de AAD.](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | • [Microsoft Intune plantilla personalizada](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Aprovisionamiento en tiempo de ejecución: varias aplicaciones](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| Los usuarios de distintos grupos de AAD experimentan el modo de pantalla completa que es solo para su grupo. | [Configure la configuración de acceso asignado para cada grupo de AAD deseado.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [Microsoft Intune plantilla personalizada](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Aprovisionamiento en tiempo de ejecución: varias aplicaciones](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | • Cuando un usuario inicia sesión y HoloLens está conectado a Internet, si se encuentra que ese usuario es miembro del grupo de AAD para el que existe la configuración de quiosco, el usuario obtiene la experiencia de pantalla completa para ese grupo de AAD. <br> • Si no hay internet disponible cuando el usuario inicia sesión, el usuario experimentará HoloLens [comportamiento de modo de error.](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode) <br> • Si no se garantiza la disponibilidad de Internet cuando el usuario inicia sesión y se debe usar la pantalla completa basada en grupos de AAD, considere la posibilidad de usar [AADGroupMembershipCacheValidityInDayspolicy](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk). <br> • Para obtener una experiencia óptima con los grupos de AAD durante el inicio de sesión, se recomienda usar [AADGroupMembershipCacheValidityInDayspolicy.](/hololens/hololens-release-notes#cache-azure-ad-group-membership-for-offline-kiosk) |
| Los usuarios que necesitan usar HoloLens con fines temporales obtienen experiencia de quiosco. | [Configuración de la configuración de acceso asignado para los visitantes](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-visitors) | • [Microsoft Intune plantilla personalizada](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Aprovisionamiento en tiempo de ejecución: aplicación única](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens) | • La cuenta de usuario temporal se crea automáticamente HoloLens inicio de sesión y se quita cuando el usuario temporal cierra la sesión. <br> • Considere la posibilidad de [habilitar la directiva de inicio de sesión automático del visitante.](#how-can-visitor-accounts-automatically-logon-to-kiosk-experience) |

## <a name="steps-in-configuring-kiosk-mode-for-hololens"></a>Pasos para configurar el modo de pantalla completa para HoloLens

Las configuraciones de quiosco se pueden crear y aplicar de las maneras siguientes:

1. Con la interfaz de usuario del servidor MDM, por ejemplo, las plantillas de quiosco de Intune o las configuraciones OMA-URI personalizadas, que luego se aplican de forma remota a HoloLens.
2. Con los paquetes de aprovisionamiento en tiempo de ejecución, que se aplican directamente a HoloLens.

Estas son las siguientes maneras de configurar, seleccione la pestaña que coincida con el proceso que le gustaría usar.

1. [Microsoft Intune de pantalla completa de aplicación única](hololens-kiosk.md?tabs=uisak#steps-in-configuring-kiosk-mode-for-hololens)
2. [Microsoft Intune de pantalla completa con varias aplicaciones](hololens-kiosk.md?tabs=uimak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Microsoft Intune plantilla personalizada](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)
1. [Aprovisionamiento en tiempo de ejecución: varias aplicaciones](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Aprovisionamiento en tiempo de ejecución: aplicación única](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens)

[!INCLUDE[](includes/kiosk-configure-steps.md)]

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

### <a name="how-can-visitor-accounts-automatically-logon-to-kiosk-experience"></a>¿Cómo pueden las cuentas de visitante iniciar sesión automáticamente en la experiencia de quiosco?

En las [compilaciones Windows Holographic, versión 21H1](hololens-release-notes.md#windows-holographic-version-21h1) y versiones adelante:

- Las configuraciones de AAD y no ADD admiten que las cuentas de visitante se habiliten automáticamente para los modos de quiosco.

[!INCLUDE[](includes/kiosk-autologin.md)]

### <a name="is-kiosk-experience-supported-on-hololens-1st-gen"></a>¿Se admite la experiencia de pantalla completa HoloLens (1.ª generación)?

El modo de pantalla completa solo está disponible si el dispositivo tiene Windows Holographic for Business. Todos HoloLens 2 dispositivos se envían Windows Holographic for Business y no hay ninguna otra edición. Cada HoloLens 2 dispositivo puede ejecutar el modo de pantalla completa de forma automática.

HoloLens dispositivos (1.ª generación) deben actualizarse tanto en términos de compilación del sistema operativo como de edición del sistema operativo. Aquí tiene más información sobre cómo actualizar una HoloLens (1.ª generación) [a Windows Holographic for Business](hololens1-upgrade-enterprise.md) edición. Para actualizar un dispositivo HoloLens (1ª generación) para que use el modo de pantalla completa, primero debe asegurarse de que el dispositivo ejecuta Windows 10, versión 1803 o una versión posterior. Si ha usado la herramienta de recuperación de dispositivos de Windows para recuperar el dispositivo HoloLens (1ª generación) en su compilación predeterminada, o si ha instalado las actualizaciones más recientes, el dispositivo está listo para configurarse.

### <a name="how-to-use-device-portal-to-configure-kiosk-in-non-production-environments"></a>¿Cómo usar el portal de dispositivos para configurar pantalla completa en entornos que no son de producción?

Configure el dispositivo [HoloLens para usar el Windows Portal de dispositivos](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal). Device Portal es un servidor web en el dispositivo HoloLens al que puedes conectarte desde un navegador web del equipo.

 > [!CAUTION]
 > Al configurar el HoloLens para usar el Portal de dispositivos, debe habilitar el modo de desarrollador en el dispositivo. El modo de desarrollador en un dispositivo que Windows Holographic for Business permite realizar la carga lateral de las aplicaciones. Sin embargo, esta configuración crea un riesgo de que un usuario pueda instalar aplicaciones que no han sido certificadas por el Microsoft Store. Los administradores pueden bloquear la capacidad de habilitar el modo de desarrollador mediante el uso de la configuración **ApplicationManagement/AllowDeveloper Unlock** en [el CSP de directiva](/windows/client-management/mdm/policy-configuration-service-provider). [Obtén más información sobre el modo de desarrollador.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)

El modo de pantalla completa se puede establecer a través de la API REST de Portal de dispositivos si se realiza una operación POST en /api/holographic/kioskmode/settings con un parámetro de cadena de consulta necesario ("kioskModeEnabled" con un valor de "true" o "false") y un parámetro opcional ("startupApp" con un valor de un nombre de paquete). Tenga en cuenta que Portal de dispositivos está diseñado para desarrolladores y no debe habilitarse en dispositivos que no son de desarrollador. La API REST está sujeta a cambios en futuras actualizaciones o versiones.

## <a name="troubleshooting"></a>Solución de problemas

### <a name="issue---no-apps-are-shown-in-start-menu-in-kiosk-mode"></a>Problema: no se muestra ninguna aplicación en el menú Inicio en pantalla completa

**Síntomas**

Al encontrar errores en la aplicación del modo de pantalla completa, aparece el comportamiento siguiente:

- Antes de Windows Holographic, la versión 20H2 - HoloLens mostrará todas las aplicaciones de la menú Inicio.
- Windows Holographic, versión 20H2: si un dispositivo tiene una configuración de pantalla completa, que es una combinación de acceso asignado global y acceso asignado a miembros del grupo de AAD, si se produce un error en la determinación de la pertenencia al grupo de AAD, el usuario verá el menú "no se muestra nada en el inicio".

    ![Imagen del modo de pantalla completa que ahora se ve cuando se produce un error.](images/hololens-kiosk-failure-behavior.png )

- A partir [Windows Holographic, versión 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)el modo de pantalla completa busca acceso asignado global antes de mostrar un menú de inicio vacío. La experiencia de pantalla completa volverá a una configuración global de quiosco (si está presente) si hay errores durante el modo de pantalla completa del grupo de AAD.

**Pasos para solucionar problemas**

- Compruebe que el AUMID de la aplicación se ha especificado correctamente y que no contiene versiones. Consulte el [HoloLens AUMID para](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) aplicaciones de bandeja de entrada para obtener ejemplos.
- Asegúrese de que la aplicación está instalada en el dispositivo para ese usuario.
- Si la configuración de quiosco se basa en grupos de AAD, asegúrese de que la conectividad a Internet está presente cuando el usuario de AAD inicia sesión. Si lo desea, [configure la directiva MixedReality/AADGroupMembershipCacheValidityInDays](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-aadgroupmembershipcachevalidityindays) para que también pueda funcionar sin Internet.

### <a name="issue---building-a-package-with-kiosk-mode-failed"></a>Problema: error al compilar un paquete con pantalla completa

**Síntomas**

Se muestra un cuadro de diálogo como el siguiente.

<kbd>
    <img alt="Kiosk failure to build" src="./images/kiosk-steps/kiosk-ppkg-failure.png"/>
</kbd>

**Pasos para solucionar problemas**

1. Haga clic en el hyper-link que se muestra como en el cuadro de diálogo anterior.
1. Abra ICD.log en un editor de texto y su contenido debe indicar el error.

> [!NOTE]
> Si ha realizado varios intentos, compruebe las marcas de tiempo en el registro. Esto le ayudará a comprobar solo los problemas actuales.

### <a name="issue--provisioning-package-built-successfully-but-failed-to-apply"></a>Problema: el paquete de aprovisionamiento se ha creado correctamente, pero no se pudo aplicar.

**Síntomas**

Se muestra un error al aplicar el paquete de aprovisionamiento en Hololens

**Pasos para solucionar problemas**

1. Vaya a la carpeta donde existe el Windows diseñador de configuración para el paquete de aprovisionamiento en tiempo de ejecución.
1. Abra ICD.log y asegúrese de que no haya errores en el registro al compilar el paquete de aprovisionamiento. Algunos errores no se muestran durante la compilación, pero se siguen registrando en ICD.log

### <a name="issue--multiple-app-assigned-access-to-aad-group-does-not-work"></a>Problema: el acceso asignado a varias aplicaciones al grupo de AAD no funciona

**Síntomas**

En el inicio de sesión de usuario de AAD, el dispositivo no entra en pantalla completa.

**Pasos para solucionar problemas**

- Confirme en XML de configuración de acceso asignado que se usa el GUID del grupo de AAD del que es miembro el usuario que ha iniciado sesión y no el GUID del usuario de AAD.
- Confirme que, en el portal de Intune, el usuario de AAD se muestra realmente como miembro del grupo de AAD de destino.
