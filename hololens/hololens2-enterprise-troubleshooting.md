---
title: Solución de problemas de implementación y dispositivo administrado de HoloLens 2
description: Solución de problemas de dispositivos HoloLens 2 en un entorno empresarial
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: Solución de problemas
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 911e5b9494eae00ace8007ee6a29b30e6aaf98dd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961508"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="94b4a-104">Solución de problemas de implementación y dispositivos administrados</span><span class="sxs-lookup"><span data-stu-id="94b4a-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="94b4a-105">En este artículo se explica cómo resolver varios problemas o responder a preguntas sobre la implementación y la administración de HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="94b4a-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="94b4a-106">Antes de iniciar cualquier procedimiento de solución de problemas, asegúrese de que el dispositivo tenga entre un **20 y un 40 por ciento** de batería, si es posible.</span><span class="sxs-lookup"><span data-stu-id="94b4a-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="94b4a-107">Las [luces indicadoras de batería](hololens2-setup.md#lights-that-indicate-the-battery-level) que se encuentran debajo del botón de encendido son una manera rápida de comprobar la capacidad de la batería sin iniciar sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="94b4a-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="94b4a-108">Solución de problemas de EAP</span><span class="sxs-lookup"><span data-stu-id="94b4a-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="94b4a-109">Solución de problemas de Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="94b4a-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="94b4a-110">Solución de problemas de red</span><span class="sxs-lookup"><span data-stu-id="94b4a-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="94b4a-111">No se puede iniciar sesión en un dispositivo HoloLens ya configurado</span><span class="sxs-lookup"><span data-stu-id="94b4a-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="94b4a-112">No se puede iniciar sesión después de actualizar a Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="94b4a-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="94b4a-113">Solución de problemas de Autopilot</span><span class="sxs-lookup"><span data-stu-id="94b4a-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="94b4a-114">Preguntas más frecuentes sobre dispositivos HoloLens administrados</span><span class="sxs-lookup"><span data-stu-id="94b4a-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="94b4a-115">Solución de problemas de EAP</span><span class="sxs-lookup"><span data-stu-id="94b4a-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="94b4a-116">Asegúrese de que el perfil de Wi-Fi tiene la configuración adecuada:</span><span class="sxs-lookup"><span data-stu-id="94b4a-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="94b4a-117">El tipo de EAP está configurado correctamente, tipos comunes de EAP: EAP-TLS (13), EAP-TTLS (21) y PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="94b4a-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="94b4a-118">El nombre de Wi-Fi (SSID) es correcto y coincide con la cadena hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="94b4a-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="94b4a-119">En el caso de EAP-TLS, TrustedRootCA contiene el hash SHA-1 del certificado de entidad de certificación raíz de confianza del servidor.</span><span class="sxs-lookup"><span data-stu-id="94b4a-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="94b4a-120">En el caso de un equipo Windows, el comando "certutil.exe -dump cert_file_name" muestra la cadena hash SHA-1 de un certificado.</span><span class="sxs-lookup"><span data-stu-id="94b4a-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="94b4a-121">Recopile la captura de paquetes de red en el punto de acceso o controlador o registros del servidor AAA para averiguar dónde se produce un error en la sesión de EAP.</span><span class="sxs-lookup"><span data-stu-id="94b4a-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="94b4a-122">Si la identidad de EAP proporcionada por HoloLens no es la esperada, compruebe si la identidad se ha aprovisionado correctamente mediante el perfil de Wi-Fi o el certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="94b4a-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="94b4a-123">Si el servidor rechaza el certificado de cliente de HoloLens, compruebe si el certificado de cliente necesario se ha aprovisionado en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="94b4a-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="94b4a-124">Si HoloLens rechaza el certificado de servidor, compruebe si el certificado de entidad de certificación raíz del servidor se ha aprovisionado en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="94b4a-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="94b4a-125">Si el perfil empresarial se aprovisiona mediante el paquete de aprovisionamiento Wi-Fi, considere la posibilidad de aplicar el paquete de aprovisionamiento en un equipo con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="94b4a-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="94b4a-126">Si también se produce un error en un equipo con Windows 10, siga la guía de solución de problemas de autenticación del cliente Windows 802.1X.</span><span class="sxs-lookup"><span data-stu-id="94b4a-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="94b4a-127">Envíe sus comentarios por medio del Centro de opiniones.</span><span class="sxs-lookup"><span data-stu-id="94b4a-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="94b4a-128">Volver a la lista</span><span class="sxs-lookup"><span data-stu-id="94b4a-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="94b4a-129">Solución de problemas de Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="94b4a-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="94b4a-130">Estas son algunas de las cosas que debe intentar si no puede conectar HoloLens a una red Wi-Fi:</span><span class="sxs-lookup"><span data-stu-id="94b4a-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="94b4a-131">Asegúrese de que la Wi-Fi está activada.</span><span class="sxs-lookup"><span data-stu-id="94b4a-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="94b4a-132">Para ello, use el gesto Inicio y seleccione Configuración > Red e Internet > Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="94b4a-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="94b4a-133">Si la Wi-Fi está activada, intente desactivarla y volver a activarla.</span><span class="sxs-lookup"><span data-stu-id="94b4a-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="94b4a-134">Acérquese al enrutador o al punto de acceso.</span><span class="sxs-lookup"><span data-stu-id="94b4a-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="94b4a-135">Reinicie el enrutador Wi-Fi y luego HoloLens.</span><span class="sxs-lookup"><span data-stu-id="94b4a-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="94b4a-136">Try connecting again (Intente conectarse de nuevo).</span><span class="sxs-lookup"><span data-stu-id="94b4a-136">Try connecting again.</span></span>
4. <span data-ttu-id="94b4a-137">Si ninguna de estas cosas funciona, asegúrese de que el enrutador usa el firmware más reciente.</span><span class="sxs-lookup"><span data-stu-id="94b4a-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="94b4a-138">Puede encontrar esta información en el sitio web del fabricante.</span><span class="sxs-lookup"><span data-stu-id="94b4a-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="94b4a-139">Al iniciar sesión en una cuenta empresarial u organizativa en el dispositivo, también puede aplicarse la directiva de Administración de dispositivos móviles (MDM) si el administrador de TI la ha configurado.</span><span class="sxs-lookup"><span data-stu-id="94b4a-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="network-troubleshooting"></a><span data-ttu-id="94b4a-140">Solución de problemas de red</span><span class="sxs-lookup"><span data-stu-id="94b4a-140">Network Troubleshooting</span></span>
<span data-ttu-id="94b4a-141">Si los problemas de red son un obstáculo para implementar y usar correctamente HoloLens 2 en la organización, obtenga información sobre cómo dos conocidas herramientas de diagnóstico de red, Fiddler y Wireshark, pueden ayudarle a examinar, diagnosticar e identificar problemas.</span><span class="sxs-lookup"><span data-stu-id="94b4a-141">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, learn how two well-known network diagnostic tools, Fiddler and Wireshark can help you scan, diagnose, and identify problems.</span></span> <span data-ttu-id="94b4a-142">Vea este [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="94b4a-142">Check out this [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) for more details.</span></span>

[<span data-ttu-id="94b4a-143">Volver a la lista</span><span class="sxs-lookup"><span data-stu-id="94b4a-143">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="94b4a-144">No se puede iniciar sesión en un dispositivo HoloLens ya configurado</span><span class="sxs-lookup"><span data-stu-id="94b4a-144">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="94b4a-145">Si el dispositivo se ha configurado previamente para otra persona, ya sea para un cliente o para un ex-empleado, y no tiene su contraseña para desbloquearlo, puede usar Intune para [borrar](https://docs.microsoft.com/intune/remote-actions/devices-wipe) el dispositivo de forma remota.</span><span class="sxs-lookup"><span data-stu-id="94b4a-145">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](https://docs.microsoft.com/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="94b4a-146">Entonces el dispositivo se reprograma automáticamente.</span><span class="sxs-lookup"><span data-stu-id="94b4a-146">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="94b4a-147">Al borrar el dispositivo, asegúrese de dejar desactivada la opción **Conservar el estado de inscripción y la cuenta de usuario**.</span><span class="sxs-lookup"><span data-stu-id="94b4a-147">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>
[<span data-ttu-id="94b4a-148">Volver a la lista</span><span class="sxs-lookup"><span data-stu-id="94b4a-148">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="94b4a-149">No se puede iniciar sesión después de actualizar a Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="94b4a-149">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="94b4a-150">Síntomas</span><span class="sxs-lookup"><span data-stu-id="94b4a-150">Symptoms</span></span>
- <span data-ttu-id="94b4a-151">Se produce un error en el uso de PIN para iniciar sesión después de escribir el PIN correcto.</span><span class="sxs-lookup"><span data-stu-id="94b4a-151">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="94b4a-152">Se produce un error en el uso del método de inicio de sesión web después de iniciar sesión correctamente en la página web.</span><span class="sxs-lookup"><span data-stu-id="94b4a-152">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="94b4a-153">El dispositivo no aparece como "Unido a Azure AD" en [Azure Portal](https://portal.azure.com/) -> Azure Active Directory -> Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="94b4a-153">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="94b4a-154">Causa</span><span class="sxs-lookup"><span data-stu-id="94b4a-154">Cause</span></span>
<span data-ttu-id="94b4a-155">Es posible que el dispositivo afectado se haya eliminado del inquilino de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="94b4a-155">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="94b4a-156">Por ejemplo, esto puede ocurrir porque:</span><span class="sxs-lookup"><span data-stu-id="94b4a-156">For example, this may happen because:</span></span>

- <span data-ttu-id="94b4a-157">Un administrador o usuario ha eliminado el dispositivo en Azure Portal o mediante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94b4a-157">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="94b4a-158">El dispositivo se ha quitado del inquilino de Azure AD por inactividad.</span><span class="sxs-lookup"><span data-stu-id="94b4a-158">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="94b4a-159">Para tener un entorno administrado de manera eficaz, normalmente se recomienda a los administradores de TI [quitar dispositivos obsoletos e inactivos del inquilino de Azure AD](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).</span><span class="sxs-lookup"><span data-stu-id="94b4a-159">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="94b4a-160">Cuando un dispositivo afectado intenta ponerse en contacto de nuevo con el inquilino de Azure AD después de que se haya eliminado, no puede autenticarse con Azure AD.</span><span class="sxs-lookup"><span data-stu-id="94b4a-160">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="94b4a-161">Este efecto suele ser invisible para el usuario del dispositivo, ya que el inicio de sesión almacenado en caché mediante PIN sigue permitiéndole iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="94b4a-161">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="94b4a-162">Mitigación</span><span class="sxs-lookup"><span data-stu-id="94b4a-162">Mitigation</span></span>
<span data-ttu-id="94b4a-163">Actualmente no hay ninguna manera de volver a agregar un dispositivo HoloLens eliminado a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="94b4a-163">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="94b4a-164">Los dispositivos afectados tienen que reprogramarse con las instrucciones para [Reprogramar el dispositivo](hololens-recovery.md#clean-reflash-the-device).</span><span class="sxs-lookup"><span data-stu-id="94b4a-164">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="94b4a-165">Solución de problemas de Autopilot</span><span class="sxs-lookup"><span data-stu-id="94b4a-165">Autopilot Troubleshooting</span></span>

<span data-ttu-id="94b4a-166">Los siguientes artículos pueden ser un recurso útil para obtener más información y solucionar problemas de Autopilot, pero tenga en cuenta que se basan en el escritorio de Windows 10 y no toda la información puede aplicarse a HoloLens:</span><span class="sxs-lookup"><span data-stu-id="94b4a-166">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="94b4a-167">Windows Autopilot: problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="94b4a-167">Windows Autopilot - known issues</span></span>](https://docs.microsoft.com/mem/autopilot/known-issues)
- [<span data-ttu-id="94b4a-168">Solución de problemas con la inscripción de dispositivos Windows en Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="94b4a-168">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="94b4a-169">Windows Autopilot: conflictos de directivas</span><span class="sxs-lookup"><span data-stu-id="94b4a-169">Windows Autopilot - Policy Conflicts</span></span>](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="94b4a-170">Preguntas más frecuentes sobre dispositivos HoloLens administrados</span><span class="sxs-lookup"><span data-stu-id="94b4a-170">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="94b4a-171">¿Puedo usar System Center Configuration Manager (SCCM) para administrar dispositivos HoloLens?</span><span class="sxs-lookup"><span data-stu-id="94b4a-171">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="94b4a-172">No.</span><span class="sxs-lookup"><span data-stu-id="94b4a-172">No.</span></span> <span data-ttu-id="94b4a-173">Debe usar un sistema de MDM para administrar dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="94b4a-173">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="94b4a-174">¿Puedo usar Active Directory Domain Services (AD DS) para administrar cuentas de usuario de HoloLens?</span><span class="sxs-lookup"><span data-stu-id="94b4a-174">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="94b4a-175">No.</span><span class="sxs-lookup"><span data-stu-id="94b4a-175">No.</span></span> <span data-ttu-id="94b4a-176">Tiene que usar Azure Active Directory (Azure AD) para administrar cuentas de usuario de dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="94b4a-176">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="94b4a-177">¿Es capaz HoloLens de inscribirse automáticamente en Sistemas de captura de datos automatizados (ADCS)?</span><span class="sxs-lookup"><span data-stu-id="94b4a-177">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="94b4a-178">No.</span><span class="sxs-lookup"><span data-stu-id="94b4a-178">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="94b4a-179">¿Puede HoloLens participar en la autenticación de Windows integrada?</span><span class="sxs-lookup"><span data-stu-id="94b4a-179">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="94b4a-180">No.</span><span class="sxs-lookup"><span data-stu-id="94b4a-180">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="94b4a-181">¿HoloLens admite la personalización de marca?</span><span class="sxs-lookup"><span data-stu-id="94b4a-181">Does HoloLens support branding?</span></span>

<span data-ttu-id="94b4a-182">No.</span><span class="sxs-lookup"><span data-stu-id="94b4a-182">No.</span></span> <span data-ttu-id="94b4a-183">Pero puede solucionar este problema si usa uno de los enfoques siguientes:</span><span class="sxs-lookup"><span data-stu-id="94b4a-183">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="94b4a-184">Cree una aplicación personalizada y [habilite el modo de pantalla completa](hololens-kiosk.md).</span><span class="sxs-lookup"><span data-stu-id="94b4a-184">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="94b4a-185">La aplicación personalizada puede tener personalización de marca y puede iniciar otras aplicaciones (como Remote Assist).</span><span class="sxs-lookup"><span data-stu-id="94b4a-185">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="94b4a-186">Cambie todas las imágenes de perfil de usuario de Azure AD por el logotipo de la empresa.</span><span class="sxs-lookup"><span data-stu-id="94b4a-186">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="94b4a-187">Sin embargo, esto puede no ser deseable en todos los escenarios.</span><span class="sxs-lookup"><span data-stu-id="94b4a-187">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="94b4a-188">¿Qué capacidades de registro ofrece HoloLens 2?</span><span class="sxs-lookup"><span data-stu-id="94b4a-188">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="94b4a-189">El registro se limita a los seguimientos que se pueden capturar en escenarios de desarrollo o solución de problemas, o a telemetría que los dispositivos envían a los servidores de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="94b4a-189">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="94b4a-190">Preguntas sobre la protección de los dispositivos HoloLens</span><span class="sxs-lookup"><span data-stu-id="94b4a-190">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="94b4a-191">Vea la [información de seguridad de HoloLens 2](security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="94b4a-191">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="94b4a-192">En el caso de los dispositivos HoloLens de primera generación, revise estas [Preguntas frecuentes](hololens1-faq-security.md).</span><span class="sxs-lookup"><span data-stu-id="94b4a-192">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.md).</span></span>

[<span data-ttu-id="94b4a-193">Volver a la lista</span><span class="sxs-lookup"><span data-stu-id="94b4a-193">Back to list</span></span>](#list)
