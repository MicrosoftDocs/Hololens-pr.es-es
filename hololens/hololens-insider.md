---
title: Insider Preview para Microsoft HoloLens
description: Obtenga información sobre cómo empezar a trabajar con compilaciones de Insider y proporcionar comentarios valiosos para nuestra próxima actualización del sistema operativo principal para HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 87b606e634d4035da02802ddd1a8e1a980f1f1d6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636100"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="9b668-103">Insider Preview para Microsoft HoloLens</span><span class="sxs-lookup"><span data-stu-id="9b668-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="9b668-104">Le damos la bienvenida a las últimas compilaciones de Insider Preview para HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9b668-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="9b668-105">Es fácil empezar a trabajar [y proporcionar](hololens-insider.md#start-receiving-insider-builds) comentarios valiosos para nuestra próxima actualización importante del sistema operativo para HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9b668-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="9b668-106">Windows Notas de la versión de Insider</span><span class="sxs-lookup"><span data-stu-id="9b668-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="9b668-107">Nos complace empezar a usar nuevas características para Windows Insiders.</span><span class="sxs-lookup"><span data-stu-id="9b668-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="9b668-108">Las nuevas compilaciones pasarán a los canales de desarrollo y beta para las actualizaciones más recientes.</span><span class="sxs-lookup"><span data-stu-id="9b668-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="9b668-109">Seguiremos actualizando esta página a medida que agreguemos más características y actualizaciones a nuestras compilaciones Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="9b668-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="9b668-110">Prepárese para mezclar estas actualizaciones en su realidad.</span><span class="sxs-lookup"><span data-stu-id="9b668-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="9b668-111">Característica</span><span class="sxs-lookup"><span data-stu-id="9b668-111">Feature</span></span>                 | <span data-ttu-id="9b668-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b668-112">Description</span></span>                | <span data-ttu-id="9b668-113">Usuario o escenario</span><span class="sxs-lookup"><span data-stu-id="9b668-113">User or Scenario</span></span> | <span data-ttu-id="9b668-114">Compilación introducida</span><span class="sxs-lookup"><span data-stu-id="9b668-114">Build introduced</span></span> |
|-------------------------|----------------------------|--------------|------------------|
| [<span data-ttu-id="9b668-115">Cambios de CSP para los informes HoloLens detalles</span><span class="sxs-lookup"><span data-stu-id="9b668-115">CSP changes for reporting HoloLens details</span></span>](#csp-changes-for-reporting-hololens-details) | <span data-ttu-id="9b668-116">Nuevos CSP para para consultar datos</span><span class="sxs-lookup"><span data-stu-id="9b668-116">New CSPs for to query data</span></span> | <span data-ttu-id="9b668-117">Administradores de TI</span><span class="sxs-lookup"><span data-stu-id="9b668-117">IT Admins</span></span>    | <span data-ttu-id="9b668-118">20348.1403</span><span class="sxs-lookup"><span data-stu-id="9b668-118">20348.1403</span></span>                 |
| [<span data-ttu-id="9b668-119">Directiva de inicio de sesión automático controlada por CSP</span><span class="sxs-lookup"><span data-stu-id="9b668-119">Auto login policy controlled by CSP</span></span>](#auto-login-policy-controlled-by-csp) | <span data-ttu-id="9b668-120">Se usa para iniciar sesión automáticamente en una cuenta</span><span class="sxs-lookup"><span data-stu-id="9b668-120">Used to log in an account automatically</span></span> | <span data-ttu-id="9b668-121">Administradores de TI</span><span class="sxs-lookup"><span data-stu-id="9b668-121">IT Admins</span></span> | <span data-ttu-id="9b668-122">20348.1405</span><span class="sxs-lookup"><span data-stu-id="9b668-122">20348.1405</span></span> |
| [<span data-ttu-id="9b668-123">Compatibilidad con archivos PFX para el Administrador de certificados</span><span class="sxs-lookup"><span data-stu-id="9b668-123">PFX file support for Certificate Manager</span></span>](#pfx-file-support-for-certificate-manager) | <span data-ttu-id="9b668-124">Adición de certificados PFX a través de Configuración interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="9b668-124">Add PFX certs via Settings UI</span></span> | <span data-ttu-id="9b668-125">Usuario final</span><span class="sxs-lookup"><span data-stu-id="9b668-125">End User</span></span> | <span data-ttu-id="9b668-126">20348.1405</span><span class="sxs-lookup"><span data-stu-id="9b668-126">20348.1405</span></span> |
| [<span data-ttu-id="9b668-127">Ver el informe de diagnóstico avanzado en Configuración en HoloLens</span><span class="sxs-lookup"><span data-stu-id="9b668-127">View advanced diagnostic report in Settings on HoloLens</span></span>](#view-advanced-diagnostic-report-in-settings-on-hololens) | <span data-ttu-id="9b668-128">Visualización de registros de diagnóstico de MDM en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="9b668-128">View MDM diagnostic logs on device</span></span> | <span data-ttu-id="9b668-129">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="9b668-129">Troubleshooting</span></span> | <span data-ttu-id="9b668-130">20348.1405</span><span class="sxs-lookup"><span data-stu-id="9b668-130">20348.1405</span></span> |
| [<span data-ttu-id="9b668-131">Notificaciones de diagnóstico sin conexión</span><span class="sxs-lookup"><span data-stu-id="9b668-131">Offline Diagnostics notifications</span></span>](#offline-diagnostics-notifications) | <span data-ttu-id="9b668-132">Comentarios de resalte para la recopilación de registros</span><span class="sxs-lookup"><span data-stu-id="9b668-132">Audiovisual feedback for log collection</span></span> | <span data-ttu-id="9b668-133">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="9b668-133">Troubleshooting</span></span> | <span data-ttu-id="9b668-134">20348.1405</span><span class="sxs-lookup"><span data-stu-id="9b668-134">20348.1405</span></span> |


### <a name="csp-changes-for-reporting-hololens-details"></a><span data-ttu-id="9b668-135">Cambios de CSP para los informes HoloLens detalles</span><span class="sxs-lookup"><span data-stu-id="9b668-135">CSP changes for reporting HoloLens details</span></span>

- <span data-ttu-id="9b668-136">Introducido en la Windows Insider, 20348.1403</span><span class="sxs-lookup"><span data-stu-id="9b668-136">Introduced in Windows Insider build, 20348.1403</span></span>

<span data-ttu-id="9b668-137">Los siguientes CSP se han actualizado con nuevas formas de informar de la información de los HoloLens dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9b668-137">The following CSPs have been updated with new ways to report information from your HoloLens devices.</span></span>

#### <a name="devdetail-csp---free-storage"></a><span data-ttu-id="9b668-138">CSP de DevDetail: Storage</span><span class="sxs-lookup"><span data-stu-id="9b668-138">DevDetail CSP - Free Storage</span></span>

<span data-ttu-id="9b668-139">Csp de DevDetail ahora también notifica espacio de almacenamiento libre en HoloLens dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9b668-139">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="9b668-140">Debe coincidir aproximadamente con el valor que se muestra en Configuración página de Storage aplicación.</span><span class="sxs-lookup"><span data-stu-id="9b668-140">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="9b668-141">A continuación se muestra el nodo específico que contiene esta información.</span><span class="sxs-lookup"><span data-stu-id="9b668-141">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="9b668-142">./DevDetail/Ext/Microsoft/FreeStorage (solo operación GET)</span><span class="sxs-lookup"><span data-stu-id="9b668-142">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp---ssid-and-bssid"></a><span data-ttu-id="9b668-143">CSP de DeviceStatus: SSID y BSSID</span><span class="sxs-lookup"><span data-stu-id="9b668-143">DeviceStatus CSP - SSID and BSSID</span></span>

<span data-ttu-id="9b668-144">Csp de DeviceStatus ahora también notifica SSID y BSSID de Wi-Fi red con la HoloLens está conectada activamente.</span><span class="sxs-lookup"><span data-stu-id="9b668-144">DeviceStatus CSP now also reports SSID and BSSID of Wi-Fi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="9b668-145">A continuación se incluyen los nodos específicos que contienen esta información.</span><span class="sxs-lookup"><span data-stu-id="9b668-145">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="9b668-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*dirección mac del Wi-Fi /SSID*</span><span class="sxs-lookup"><span data-stu-id="9b668-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="9b668-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*dirección mac de Wi-Fi adaptador*/BSSID</span><span class="sxs-lookup"><span data-stu-id="9b668-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="9b668-148">Ejemplo de blob syncml (para proveedores de MDM) para consultar NetworkIdentifiers</span><span class="sxs-lookup"><span data-stu-id="9b668-148">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a><span data-ttu-id="9b668-149">Directiva de inicio de sesión automático controlada por CSP</span><span class="sxs-lookup"><span data-stu-id="9b668-149">Auto login policy controlled by CSP</span></span>

<span data-ttu-id="9b668-150">Esta nueva directiva AutoLogonUser controla si un usuario iniciará sesión automáticamente.</span><span class="sxs-lookup"><span data-stu-id="9b668-150">This new AutoLogonUser policy controls whether a user will be automatically logged on.</span></span> <span data-ttu-id="9b668-151">Algunos clientes quieren configurar dispositivos que están vinculados a una identidad, pero no quieren ninguna experiencia de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="9b668-151">Some customers want to set up devices that are tied to an identity but don't want any sign-in experience.</span></span> <span data-ttu-id="9b668-152">Imagine seleccionar un dispositivo y usar asistencia remota inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="9b668-152">Imagine picking up a device and using remote assist immediately.</span></span> <span data-ttu-id="9b668-153">O bien, tener la ventaja de poder distribuir rápidamente HoloLens dispositivos y permitir a sus usuarios finales acelerar el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="9b668-153">Or have a benefit of being able to rapidly  distribute HoloLens devices and enable their end users to expedite login.</span></span>

<span data-ttu-id="9b668-154">Cuando la directiva se establece en un valor no vacío, especifica la dirección de correo electrónico del usuario de inicio de sesión automático.</span><span class="sxs-lookup"><span data-stu-id="9b668-154">When the policy is set to a non-empty value, it specifies the email address of the auto-logon user.</span></span> <span data-ttu-id="9b668-155">El usuario especificado debe iniciar sesión en el dispositivo al menos una vez para habilitar el inicio de sesión automático.</span><span class="sxs-lookup"><span data-stu-id="9b668-155">The specified user must logon to the device at least once to enable auto-logon.</span></span>

<span data-ttu-id="9b668-156">El OMA-URI del nuevo valor de `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` cadena de directiva</span><span class="sxs-lookup"><span data-stu-id="9b668-156">The OMA-URI of new policy `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` String value</span></span>

- <span data-ttu-id="9b668-157">El usuario con la misma dirección de correo electrónico tendrá habilitado el inicio de sesión automático.</span><span class="sxs-lookup"><span data-stu-id="9b668-157">User with the same email address will have auto logon enabled.</span></span>

<span data-ttu-id="9b668-158">En un dispositivo donde se configura esta directiva, el usuario especificado en la directiva tendrá que iniciar sesión al menos una vez.</span><span class="sxs-lookup"><span data-stu-id="9b668-158">On a device where this policy is configured, the user specified in the policy will need to logon at least once.</span></span> <span data-ttu-id="9b668-159">Los reinicios posteriores del dispositivo después del primer inicio de sesión harán que el usuario especificado inicie sesión automáticamente.</span><span class="sxs-lookup"><span data-stu-id="9b668-159">Subsequent reboots of the device after the first logon will have the specified user automatically logged on.</span></span> <span data-ttu-id="9b668-160">Solo se admite un usuario de inicio de sesión automático.</span><span class="sxs-lookup"><span data-stu-id="9b668-160">Only a single auto-logon user is supported.</span></span> <span data-ttu-id="9b668-161">Una vez habilitado, el usuario que ha iniciado sesión automáticamente no podrá cerrar sesión manualmente.</span><span class="sxs-lookup"><span data-stu-id="9b668-161">Once enabled, the automatically logged on user will not be able to log out manually.</span></span> <span data-ttu-id="9b668-162">Para iniciar sesión como un usuario diferente, la directiva debe deshabilitarse primero.</span><span class="sxs-lookup"><span data-stu-id="9b668-162">To logon as a different user, the policy must first be disabled.</span></span>

> [!NOTE]
> - <span data-ttu-id="9b668-163">Algunos eventos, como las actualizaciones principales del sistema operativo, pueden requerir que el usuario especificado vuelva a iniciar sesión en el dispositivo para reanudar el comportamiento de inicio de sesión automático.</span><span class="sxs-lookup"><span data-stu-id="9b668-163">Some events such as major OS updates may require the specified user to logon to the device again to resume auto-logon behavior.</span></span> 
> - <span data-ttu-id="9b668-164">El inicio de sesión automático solo es compatible con usuarios de MSA y AAD.</span><span class="sxs-lookup"><span data-stu-id="9b668-164">Auto-logon is only supported for MSA and AAD users.</span></span>

### <a name="pfx-file-support-for-certificate-manager"></a><span data-ttu-id="9b668-165">Compatibilidad con archivos PFX para el Administrador de certificados</span><span class="sxs-lookup"><span data-stu-id="9b668-165">PFX file support for Certificate Manager</span></span>

<span data-ttu-id="9b668-166">Se introdujo en Windows Insider 20348.1405.</span><span class="sxs-lookup"><span data-stu-id="9b668-166">Introduced in Windows Insider build 20348.1405.</span></span> <span data-ttu-id="9b668-167">Hemos agregado compatibilidad con el Administrador [de](certificate-manager.md) certificados para usar ahora certificados .pfx.</span><span class="sxs-lookup"><span data-stu-id="9b668-167">We’ve added support to the [Certificate Manager](certificate-manager.md) to now use .pfx certificates.</span></span> <span data-ttu-id="9b668-168">Cuando los usuarios navegan a **Configuración** actualizar & certificados de seguridad y seleccionan Instalar un certificado, la interfaz de usuario ahora admite el archivo de certificado  >    >  .pfx. </span><span class="sxs-lookup"><span data-stu-id="9b668-168">When users navigate to **Settings** > **Update & Security** > **Certificates**, and select **Install a certificate** the UI now supports .pfx certificate file.</span></span>
<span data-ttu-id="9b668-169">Los usuarios pueden importar el certificado .pfx, con clave privada, al almacén de usuarios o al almacén de máquinas.</span><span class="sxs-lookup"><span data-stu-id="9b668-169">Users can import .pfx certificate, with private key, to user store or machine store.</span></span>

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a><span data-ttu-id="9b668-170">Ver el informe de diagnóstico avanzado en Configuración en HoloLens</span><span class="sxs-lookup"><span data-stu-id="9b668-170">View advanced diagnostic report in Settings on HoloLens</span></span>

<span data-ttu-id="9b668-171">En el caso de los dispositivos administrados al solucionar problemas de comportamiento, confirmar que se aplica una configuración de directiva esperada es un paso importante.</span><span class="sxs-lookup"><span data-stu-id="9b668-171">For managed devices when troubleshooting behavior, confirming that an expected policy configuration is applied is an important step.</span></span> <span data-ttu-id="9b668-172">Antes de esta nueva característica, esto se tenía que hacer fuera del dispositivo a través de MDM o cerca del dispositivo después de exportar los registros de diagnóstico de MDM recopilados a través de Configuración Accounts Access work or school (Acceso a cuentas de Configuración trabajo o escuela), y seleccione Export your management logs and viewed on **a** nearby PC (Exportar los registros de administración y verlos en un equipo  ->    >  cercano). </span><span class="sxs-lookup"><span data-stu-id="9b668-172">Previously to this new feature, this had to be done off device via MDM or near the device after exporting MDM diagnostic logs gathered via **Settings** -> **Accounts** > **Access work or school**, and select **Export your management logs** and viewed on a nearby PC.</span></span>

<span data-ttu-id="9b668-173">Ahora los diagnósticos de MDM se pueden ver en el dispositivo mediante el explorador Edge.</span><span class="sxs-lookup"><span data-stu-id="9b668-173">Now the MDM Diagnostics can be viewed on device using the Edge browser.</span></span> <span data-ttu-id="9b668-174">Para ver más fácilmente el informe de diagnóstico de MDM, vaya a la página Acceso profesional o educativo y seleccione **Ver informe de diagnóstico avanzado**.</span><span class="sxs-lookup"><span data-stu-id="9b668-174">To more easily view the MDM Diagnostic report navigate to the Access work or school page, and select **View advanced diagnostic report**.</span></span> <span data-ttu-id="9b668-175">Esto generará y abrirá el informe en una nueva ventana de Edge.</span><span class="sxs-lookup"><span data-stu-id="9b668-175">This will generate and open the report in a new Edge window.</span></span>

![Vea el informe de diagnóstico avanzado en Configuración aplicación.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a><span data-ttu-id="9b668-177">Notificaciones de diagnóstico sin conexión</span><span class="sxs-lookup"><span data-stu-id="9b668-177">Offline Diagnostics notifications</span></span>

<span data-ttu-id="9b668-178">Se trata de una actualización de una característica existente denominada [Diagnósticos sin conexión.](hololens-diagnostic-logs.md#offline-diagnostics)</span><span class="sxs-lookup"><span data-stu-id="9b668-178">This an update for an existing feature called [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span> <span data-ttu-id="9b668-179">Anteriormente, no había ningún indicador claro para los usuarios de que habían desencadenado la recopilación de diagnóstico o que se había completado.</span><span class="sxs-lookup"><span data-stu-id="9b668-179">Previously, there was no clear indicator to users that they had triggered diagnostic collection or it had completed.</span></span>
<span data-ttu-id="9b668-180">Ahora agregados en Windows compilaciones de Insider, hay dos formas de comentarios sobre el diagnóstico sin conexión.</span><span class="sxs-lookup"><span data-stu-id="9b668-180">Now added in Windows Insider builds, there are two forms of audiovisual feedback for Offline Diagnostics.</span></span> <span data-ttu-id="9b668-181">El primero es notificaciones del sistema que se muestran para cuando se inicia y se completa la recopilación.</span><span class="sxs-lookup"><span data-stu-id="9b668-181">The first being toasts notifications displayed for both when collection starts and completes.</span></span> <span data-ttu-id="9b668-182">Se mostrarán cuando el usuario haya iniciado sesión y tenga objetos visuales.</span><span class="sxs-lookup"><span data-stu-id="9b668-182">These will be displayed when the user is logged in and has visuals.</span></span>

![Notificación del sistema para recopilar registros.](./images/logcollection1.jpg)

![Notificación del sistema cuando se completa la recopilación de registros.](./images/logcollection2.jpg)
 
<span data-ttu-id="9b668-185">Dado que los usuarios a menudo usan diagnósticos sin conexión como mecanismo de recopilación de registros de reserva para cuando no tienen acceso a una pantalla, no pueden iniciar sesión o todavía están en la OOBE, también habrá una indicación de audio que se reproducirá cuando se recopilibrán los registros.</span><span class="sxs-lookup"><span data-stu-id="9b668-185">Because users often use Offline Diagnostics as a fallback log gathering mechanism for when they don’t have access to a display, can’t log-in or are still in OOBE there will also be an audio cue played when logs are gathered.</span></span> <span data-ttu-id="9b668-186">Este sonido se reproducirá además de la notificación del sistema.</span><span class="sxs-lookup"><span data-stu-id="9b668-186">This sound will be played in addition to the toast notification.</span></span>

<span data-ttu-id="9b668-187">Esta nueva característica se habilitará cuando el dispositivo se actualice y no es necesario habilitarla ni administrarla.</span><span class="sxs-lookup"><span data-stu-id="9b668-187">This new feature will be enabled when your device updates, and doesn’t need to be enabled or managed.</span></span> <span data-ttu-id="9b668-188">En cualquier caso de que no se puedan mostrar ni escuchar estos nuevos comentarios, se seguirá generando diagnóstico sin conexión.</span><span class="sxs-lookup"><span data-stu-id="9b668-188">In any event that this new feedback cannot be displayed or heard, Offline Diagnostics will still be generated.</span></span>

<span data-ttu-id="9b668-189">Esperamos que con esta adición más reciente de comentarios sobre el lenguaje sea más fácil recopilar datos de diagnóstico y poder solucionar los problemas más rápidamente.</span><span class="sxs-lookup"><span data-stu-id="9b668-189">We hope with this newer addition of audiovisual feedback it is easier to gather diagnostic data, and more quickly be able to troubleshoot your problems.</span></span>



### <a name="fixes-and-improvements"></a><span data-ttu-id="9b668-190">Correcciones y mejoras:</span><span class="sxs-lookup"><span data-stu-id="9b668-190">Fixes and improvements:</span></span>

- <span data-ttu-id="9b668-191">Se ha [corregido un problema conocido Portal de dispositivos donde no había ningún mensaje que descargara archivos bloqueados.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="9b668-191">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="9b668-192">Se ha corregido un problema conocido para Portal de dispositivos con tiempos de espera de carga y descarga [de archivos.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="9b668-192">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>


## <a name="start-receiving-insider-builds"></a><span data-ttu-id="9b668-193">Empezar a recibir compilaciones de Insider</span><span class="sxs-lookup"><span data-stu-id="9b668-193">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="9b668-194">Si no ha actualizado recientemente, reinicie el dispositivo para actualizar el estado y obtener la compilación más reciente.</span><span class="sxs-lookup"><span data-stu-id="9b668-194">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="9b668-195">El comando de voz "Reiniciar dispositivo" funciona bien.</span><span class="sxs-lookup"><span data-stu-id="9b668-195">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="9b668-196">También puede elegir el botón reiniciar en Configuración/Windows Programa Insider.</span><span class="sxs-lookup"><span data-stu-id="9b668-196">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="9b668-197">Hemos tenido un error en el back-end que puede haber encontrado y esto le permitirá volver a realizar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9b668-197">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="9b668-198">En un dispositivo HoloLens 2, vaya **a Configuración** Update & Security Windows Programa Insider y  >    >   seleccione **Introducción.**</span><span class="sxs-lookup"><span data-stu-id="9b668-198">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="9b668-199">Vincule la cuenta que usó para registrarse como Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="9b668-199">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="9b668-200">Windows insider ahora se mueve a Canales.</span><span class="sxs-lookup"><span data-stu-id="9b668-200">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="9b668-201">El **anillo** rápido se convertirá en  el canal **de** desarrollo, el  anillo lento se convertirá en el **Canal beta** y el anillo versión preliminar se convertirá en el canal de versión preliminar **de versión** preliminar.</span><span class="sxs-lookup"><span data-stu-id="9b668-201">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="9b668-202">Este es el aspecto de esa asignación:</span><span class="sxs-lookup"><span data-stu-id="9b668-202">Here is what that mapping looks like:</span></span>

![Windows Explicación de Los canales de Insider](images/WindowsInsiderChannels.png)

<span data-ttu-id="9b668-204">Para obtener más información, vea [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) (Introducción a los canales de Insider) Windows blogs.</span><span class="sxs-lookup"><span data-stu-id="9b668-204">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="9b668-205">A continuación, seleccione Desarrollo activo **de Windows**, elija si desea recibir canal **de** desarrollo o Canal beta **compilaciones** y revise los términos del programa.</span><span class="sxs-lookup"><span data-stu-id="9b668-205">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="9b668-206">Seleccione **Confirmar > Reiniciar ahora** para finalizar.</span><span class="sxs-lookup"><span data-stu-id="9b668-206">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="9b668-207">Una vez reiniciado el dispositivo, vaya a Configuración > **Update & Security > Buscar** actualizaciones para obtener la compilación más reciente.</span><span class="sxs-lookup"><span data-stu-id="9b668-207">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="9b668-208">Actualización de errores 0x80070490 de trabajo</span><span class="sxs-lookup"><span data-stu-id="9b668-208">Update error 0x80070490 work-around</span></span>

<span data-ttu-id="9b668-209">Si se produce un error de actualización 0x80070490 al actualizar en el canal Dev o Beta, pruebe el siguiente trabajo a corto plazo.</span><span class="sxs-lookup"><span data-stu-id="9b668-209">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="9b668-210">Implica mover el canal insider, seleccionar la actualización y, a continuación, volver a mover el canal de Insider.</span><span class="sxs-lookup"><span data-stu-id="9b668-210">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>

#### <a name="stage-one---release-preview"></a><span data-ttu-id="9b668-211">Fase uno: versión preliminar</span><span class="sxs-lookup"><span data-stu-id="9b668-211">Stage one - Release Preview</span></span>

1.  <span data-ttu-id="9b668-212">Configuración, Actualizar & seguridad, Windows Programa Insider, seleccione Release Preview Channel ( **Canal de versión preliminar de versión preliminar).**</span><span class="sxs-lookup"><span data-stu-id="9b668-212">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>

2.  <span data-ttu-id="9b668-213">Configuración, Update & Security, Windows Update, **Check for updates**.</span><span class="sxs-lookup"><span data-stu-id="9b668-213">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="9b668-214">Después de la actualización, continúe con la fase dos.</span><span class="sxs-lookup"><span data-stu-id="9b668-214">After the update, continue on to Stage two.</span></span>

#### <a name="stage-two---dev-channel"></a><span data-ttu-id="9b668-215">Fase dos: Canal de desarrollo</span><span class="sxs-lookup"><span data-stu-id="9b668-215">Stage two - Dev Channel</span></span>

1. <span data-ttu-id="9b668-216">Configuración, Actualizar & seguridad, Windows Programa Insider, seleccione Canal **de desarrollo.**</span><span class="sxs-lookup"><span data-stu-id="9b668-216">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>

2. <span data-ttu-id="9b668-217">Configuración, Update & Security, Windows Update, **Check for updates**.</span><span class="sxs-lookup"><span data-stu-id="9b668-217">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>

## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="9b668-218">Instrucciones de descarga y flash de FFU</span><span class="sxs-lookup"><span data-stu-id="9b668-218">FFU download and flash directions</span></span>

<span data-ttu-id="9b668-219">Para realizar pruebas con un ffu firmado por un vuelo, primero debe desbloquear el dispositivo en vuelo antes de que se abra el ffu firmado por el vuelo.</span><span class="sxs-lookup"><span data-stu-id="9b668-219">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>

1. <span data-ttu-id="9b668-220">En pc:</span><span class="sxs-lookup"><span data-stu-id="9b668-220">On PC:</span></span>
    1. <span data-ttu-id="9b668-221">Descargue ffu en el equipo desde [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .</span><span class="sxs-lookup"><span data-stu-id="9b668-221">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="9b668-222">Instale ARC (Advanced Recovery Companion) desde la Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .</span><span class="sxs-lookup"><span data-stu-id="9b668-222">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="9b668-223">En HoloLens- Desbloqueo de vuelos: abra **Configuración** Update & Security Windows Programa Insider y, a continuación, regístrese  >    >   y reinicie el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9b668-223">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="9b668-224">Flash FFU: ahora puede flashear el vuelo firmado por FFU mediante ARC.</span><span class="sxs-lookup"><span data-stu-id="9b668-224">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="9b668-225">Proporcionar comentarios e informar de problemas</span><span class="sxs-lookup"><span data-stu-id="9b668-225">Provide feedback and report issues</span></span>

<span data-ttu-id="9b668-226">Use la [aplicación Centro de opiniones en](hololens-feedback.md) su HoloLens para proporcionar comentarios y notificar problemas.</span><span class="sxs-lookup"><span data-stu-id="9b668-226">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="9b668-227">El Centro de opiniones garantiza que se incluye toda la información de diagnóstico necesaria para ayudar a nuestros ingenieros a depurar y resolver rápidamente el problema.</span><span class="sxs-lookup"><span data-stu-id="9b668-227">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="9b668-228">Los problemas con la versión en chino y japonés HoloLens deben notificase de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="9b668-228">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="9b668-229">Asegúrese de aceptar el mensaje que le pregunta si desea Centro de opiniones acceder a la carpeta Documentos (seleccione **Sí** cuando se le solicite).</span><span class="sxs-lookup"><span data-stu-id="9b668-229">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <a name="note-for-developers"></a><span data-ttu-id="9b668-230">Nota para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="9b668-230">Note for developers</span></span>

<span data-ttu-id="9b668-231">Le recomendamos que pruebe a desarrollar sus aplicaciones mediante compilaciones de Insider de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9b668-231">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="9b668-232">Consulte la documentación [HoloLens developer para](https://developer.microsoft.com/windows/mixed-reality/development) comenzar.</span><span class="sxs-lookup"><span data-stu-id="9b668-232">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="9b668-233">Esas mismas instrucciones funcionan con compilaciones de Insider de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9b668-233">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="9b668-234">Puede usar las mismas compilaciones de Unity Visual Studio que ya usa para el HoloLens desarrollo.</span><span class="sxs-lookup"><span data-stu-id="9b668-234">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="9b668-235">Dejar de recibir compilaciones de Insider</span><span class="sxs-lookup"><span data-stu-id="9b668-235">Stop receiving Insider builds</span></span>

<span data-ttu-id="9b668-236">Si ya no quiere recibir compilaciones de Insider de Windows Holographic, puede optar por no recibir cuando [](hololens-recovery.md) HoloLens ejecuta una compilación de producción, o bien puede recuperar el dispositivo mediante advanced recovery Companion para recuperar el dispositivo en una versión que no sea Insider de Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="9b668-236">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="9b668-237">Hay un problema conocido en el que los usuarios que desascriban las compilaciones de Insider Preview después de volver a instalar manualmente una nueva compilación de versión preliminar experimentarían una pantalla azul.</span><span class="sxs-lookup"><span data-stu-id="9b668-237">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="9b668-238">Después, deben recuperar manualmente su dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9b668-238">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="9b668-239">Para obtener información completa sobre si se vería afectado o no, consulte más información sobre [este problema conocido.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)</span><span class="sxs-lookup"><span data-stu-id="9b668-239">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>

<span data-ttu-id="9b668-240">Para comprobar que el HoloLens está ejecutando una compilación de producción:</span><span class="sxs-lookup"><span data-stu-id="9b668-240">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="9b668-241">Vaya a **Configuración > System > Acerca de** y busque el número de compilación.</span><span class="sxs-lookup"><span data-stu-id="9b668-241">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="9b668-242">[Consulte las notas de la versión de los números de compilación de producción.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="9b668-242">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="9b668-243">Para rechazar las compilaciones de Insider:</span><span class="sxs-lookup"><span data-stu-id="9b668-243">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="9b668-244">En un HoloLens una compilación de producción, vaya a **Configuración > Update & Security > Windows Programa Insider** y seleccione Stop Insider builds (Detener compilaciones de **Insider).**</span><span class="sxs-lookup"><span data-stu-id="9b668-244">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="9b668-245">Siga las instrucciones para rechazar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9b668-245">Follow the instructions to opt out your device.</span></span>
