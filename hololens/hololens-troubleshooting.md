---
title: HoloLens Solución de problemas de dispositivos
description: Manténgase al día sobre las soluciones más comunes para HoloLens problemas de dispositivos y técnicas de solución de problemas.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: issues, bug, troubleshoot, fix, help, support, HoloLens, emulator
ms.openlocfilehash: b07514e73e43d267aa856c0fb9a256448e565000
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635456"
---
# <a name="device-troubleshooting"></a><span data-ttu-id="a3e3e-104">Solución de problemas de dispositivos</span><span class="sxs-lookup"><span data-stu-id="a3e3e-104">Device Troubleshooting</span></span>

<span data-ttu-id="a3e3e-105">En este artículo se describe cómo resolver varios problemas HoloLens comunes.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-105">This article describes how to resolve several common HoloLens issues.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="a3e3e-106">Antes de iniciar cualquier procedimiento de solución de problemas, asegúrese de que el dispositivo tenga entre un **20 y un 40 por ciento** de batería, si es posible.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="a3e3e-107">Las [luces indicadoras de batería](hololens2-setup.md#lights-that-indicate-the-battery-level) que se encuentran debajo del botón de encendido son una manera rápida de comprobar la capacidad de la batería sin iniciar sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<a id="list"></a>

<span data-ttu-id="a3e3e-108">**Problemas conocidos**</span><span class="sxs-lookup"><span data-stu-id="a3e3e-108">**Known Issues**</span></span>
- [<span data-ttu-id="a3e3e-109">Remote Assist vídeo se bloquea después de 20 minutos</span><span class="sxs-lookup"><span data-stu-id="a3e3e-109">Remote Assist video freezes after 20 minutes</span></span>](#remote-assist-video-freezes-after-20-minutes)
- [<span data-ttu-id="a3e3e-110">Inicio de sesión automático pide inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="a3e3e-110">Auto-login asks for log-in</span></span>](#auto-login-asks-for-log-in)
- [<span data-ttu-id="a3e3e-111">Microsoft Edge no se puede iniciar</span><span class="sxs-lookup"><span data-stu-id="a3e3e-111">Microsoft Edge fails to launch</span></span>](#microsoft-edge-fails-to-launch)
- [<span data-ttu-id="a3e3e-112">El teclado no cambia a caracteres especiales</span><span class="sxs-lookup"><span data-stu-id="a3e3e-112">Keyboard doesn't switch to special characters</span></span>](#keyboard-doesnt-switch-to-special-characters)
- [<span data-ttu-id="a3e3e-113">La descarga de archivos bloqueados no muestra el error</span><span class="sxs-lookup"><span data-stu-id="a3e3e-113">Downloading locked files doesn't show error</span></span>](#downloading-locked-files-doesnt-error)
- [<span data-ttu-id="a3e3e-114">Portal de dispositivos de carga y descarga de archivos</span><span class="sxs-lookup"><span data-stu-id="a3e3e-114">Device Portal file upload/download times out</span></span>](#device-portal-file-uploaddownload-times-out)
- [<span data-ttu-id="a3e3e-115">Pantalla azul después de la inscripción de la versión preliminar de Insider en un dispositivo parpadeado con una compilación de Insider</span><span class="sxs-lookup"><span data-stu-id="a3e3e-115">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [<span data-ttu-id="a3e3e-116">OneDrive no carga automáticamente imágenes</span><span class="sxs-lookup"><span data-stu-id="a3e3e-116">OneDrive doesn't automatically upload pictures</span></span>](#onedrive-doesnt-automatically-upload-pictures)

<span data-ttu-id="a3e3e-117">**General**</span><span class="sxs-lookup"><span data-stu-id="a3e3e-117">**General**</span></span>
- [<span data-ttu-id="a3e3e-118">HoloLens no responde o no se inicia</span><span class="sxs-lookup"><span data-stu-id="a3e3e-118">HoloLens is unresponsive or won't start</span></span>](#hololens-is-unresponsive-or-wont-start)
- [<span data-ttu-id="a3e3e-119">Error "Espacio en disco bajo"</span><span class="sxs-lookup"><span data-stu-id="a3e3e-119">"Low Disk Space" error</span></span>](#low-disk-space-error)
- [<span data-ttu-id="a3e3e-120">Error de calibración</span><span class="sxs-lookup"><span data-stu-id="a3e3e-120">Calibration Fails</span></span>](#calibration-fails)
- [<span data-ttu-id="a3e3e-121">No se puede iniciar sesión porque mi HoloLens se ha configurado previamente para otra persona</span><span class="sxs-lookup"><span data-stu-id="a3e3e-121">Can't sign in because my HoloLens was previously set up for someone else</span></span>](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [<span data-ttu-id="a3e3e-122">Unity no funciona</span><span class="sxs-lookup"><span data-stu-id="a3e3e-122">Unity isn't working</span></span>](#unity-isnt-working)
- [<span data-ttu-id="a3e3e-123">Windows Portal de dispositivos no funciona correctamente</span><span class="sxs-lookup"><span data-stu-id="a3e3e-123">Windows Device Portal isn't working correctly</span></span>](#windows-device-portal-isnt-working-correctly)
- [<span data-ttu-id="a3e3e-124">El HoloLens Emulator no funciona</span><span class="sxs-lookup"><span data-stu-id="a3e3e-124">The HoloLens Emulator isn't working</span></span>](#the-hololens-emulator-isnt-working)

<span data-ttu-id="a3e3e-125">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="a3e3e-125">**Input**</span></span>
- [<span data-ttu-id="a3e3e-126">Los comandos de voz no funcionan</span><span class="sxs-lookup"><span data-stu-id="a3e3e-126">Voice commands aren't working</span></span>](#voice-commands-arent-working)
- [<span data-ttu-id="a3e3e-127">La entrada de mano no funciona</span><span class="sxs-lookup"><span data-stu-id="a3e3e-127">Hand input isn't working</span></span>](#hand-input-isnt-working)

<span data-ttu-id="a3e3e-128">**Conectividad**</span><span class="sxs-lookup"><span data-stu-id="a3e3e-128">**Connectivity**</span></span>
- [<span data-ttu-id="a3e3e-129">No se puede conectar a Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="a3e3e-129">Can't connect to Wi-Fi</span></span>](#cant-connect-to-wi-fi)

<span data-ttu-id="a3e3e-130">**Dispositivos externos**</span><span class="sxs-lookup"><span data-stu-id="a3e3e-130">**External Devices**</span></span> 
- [<span data-ttu-id="a3e3e-131">Bluetooth dispositivos no están emparejados</span><span class="sxs-lookup"><span data-stu-id="a3e3e-131">Bluetooth devices aren't pairing</span></span>](#bluetooth-devices-arent-pairing)
- [<span data-ttu-id="a3e3e-132">El micrófono USB-C no funciona</span><span class="sxs-lookup"><span data-stu-id="a3e3e-132">USB-C Microphone isn't working</span></span>](#usb-c-microphone-isnt-working)
- [<span data-ttu-id="a3e3e-133">Los dispositivos que aparecen como Configuración no funcionan</span><span class="sxs-lookup"><span data-stu-id="a3e3e-133">Devices listed as available in Settings don't work</span></span>](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a><span data-ttu-id="a3e3e-134">Remote Assist vídeo se bloquea después de 20 minutos</span><span class="sxs-lookup"><span data-stu-id="a3e3e-134">Remote Assist video freezes after 20 minutes</span></span>

> [!NOTE]
> <span data-ttu-id="a3e3e-135">Hay una versión más reciente de Remote Assist que tiene una corrección para este problema.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-135">There is a newer version of Remote Assist which has a fix for this issue.</span></span> <span data-ttu-id="a3e3e-136">Actualice [Remote Assist](holographic-store-apps.md#update-apps) a la versión más reciente para evitar este problema.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-136">Please [update Remote Assist](holographic-store-apps.md#update-apps) to the latest version to avoid this issue.</span></span>

> [!NOTE]
> <span data-ttu-id="a3e3e-137">Debido a la gravedad de este problema conocido, hemos pausado temporalmente la disponibilidad de Windows Holographic, versión 21H1.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-137">Due to this Known Issue's severity we had temporarily paused the availability of Windows Holographic, version 21H1.</span></span> <span data-ttu-id="a3e3e-138">La compilación 21H1 ahora está disponible de nuevo, por lo que los dispositivos pueden actualizarse una vez más a la compilación 21H1 más reciente.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-138">The 21H1 build is now available again, so devices may once again be updated to the latest 21H1 build.</span></span>

<span data-ttu-id="a3e3e-139">En la versión más reciente de [Windows Holographic, versión 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)algunos usuarios de Remote Assist han experimentado la inmovilización de vídeo durante las llamadas durante más de 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-139">On the latest release of [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), some users of Remote Assist have experienced video freezing during calls over 20 minutes.</span></span> <span data-ttu-id="a3e3e-140">Se trata de **un problema conocido.**</span><span class="sxs-lookup"><span data-stu-id="a3e3e-140">This is a **known issue**.</span></span>

### <a name="workarounds"></a><span data-ttu-id="a3e3e-141">Soluciones alternativas</span><span class="sxs-lookup"><span data-stu-id="a3e3e-141">Workarounds</span></span>

<span data-ttu-id="a3e3e-142">Si no puede actualizar la versión Remote Assist a una compilación más reciente, pruebe a trabajar con lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-142">If you are unable to update Remote Assist to a newer build try the following work around.</span></span>

#### <a name="restart-in-between-calls"></a><span data-ttu-id="a3e3e-143">Reinicio entre llamadas</span><span class="sxs-lookup"><span data-stu-id="a3e3e-143">Restart in between calls</span></span>

<span data-ttu-id="a3e3e-144">Si las llamadas tienen una duración de 20 minutos y está experimentando este problema, intente reiniciar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-144">If your calls are going over a length of 20 minutes and you are experiencing this issue, try rebooting your device.</span></span> <span data-ttu-id="a3e3e-145">Reiniciar el dispositivo entre Remote Assist llamadas actualizará el dispositivo y lo volverá a poner en un buen estado.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-145">Rebooting your device between Remote Assist calls will refresh your device and put it back into a good state.</span></span>

<span data-ttu-id="a3e3e-146">Para reiniciar rápidamente un dispositivo en Windows Holographic, la versión [21H1](hololens-release-notes.md#windows-holographic-version-21h1) abre el menú Inicio y selecciona el icono de usuario y, a continuación, **selecciona Reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-146">To quickly restart a device on [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) open the start menu, and select the user icon, then select **Restart**.</span></span>

[<span data-ttu-id="a3e3e-147">Volver a la lista</span><span class="sxs-lookup"><span data-stu-id="a3e3e-147">Back to list</span></span>](#list)

## <a name="auto-login-asks-for-log-in"></a><span data-ttu-id="a3e3e-148">Inicio de sesión automático pide inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="a3e3e-148">Auto-login asks for log-in</span></span>

<span data-ttu-id="a3e3e-149">Un HoloLens 2 se puede configurar para iniciar sesión automáticamente a través de las opciones de inicio de sesión de cuentas de **Configuración**  ->    ->    -> y, en Requerido, establecer el valor en **Nunca**.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-149">A HoloLens 2 device can be configured to automatically login in via **Settings** -> **Accounts** -> **Sign-in Options** -> and under **Required** setting the value to **Never**.</span></span> <span data-ttu-id="a3e3e-150">Es posible que algunos usuarios deba iniciar sesión de nuevo en el dispositivo al actualizar un dispositivo con una actualización considerablemente grande, como una actualización de características.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-150">Some users may be required to log-in to the device again when updating a device with a substantially large update, such as a feature update.</span></span> <span data-ttu-id="a3e3e-151">Se trata de **un problema conocido.**</span><span class="sxs-lookup"><span data-stu-id="a3e3e-151">This is a **known issue**.</span></span>

<span data-ttu-id="a3e3e-152">Ejemplo de cuándo podría ocurrir:</span><span class="sxs-lookup"><span data-stu-id="a3e3e-152">Example of when this could occur:</span></span>

- <span data-ttu-id="a3e3e-153">Actualización de un dispositivo de Windows Holographic, versión 2004 (compilación 19041.xxxx) a Windows Holographic, versión 21H1 (compilación 20346.xxxx)</span><span class="sxs-lookup"><span data-stu-id="a3e3e-153">Updating a device from Windows Holographic, version 2004 (Build 19041.xxxx) to Windows Holographic, version 21H1 (Build 20346.xxxx)</span></span>
- <span data-ttu-id="a3e3e-154">Actualización de un dispositivo para realizar una actualización grande en la misma compilación principal, por ejemplo, Windows Holographic, versión 2004 a Windows Holographic, versión 20H2</span><span class="sxs-lookup"><span data-stu-id="a3e3e-154">Updating a device to take a large update on the same major build, e.g. Windows Holographic, version 2004 to Windows Holographic, version 20H2</span></span>
- <span data-ttu-id="a3e3e-155">Actualización de un dispositivo de una imagen de fábrica a la imagen más reciente</span><span class="sxs-lookup"><span data-stu-id="a3e3e-155">Updating a device from a factory image to the latest image</span></span>

<span data-ttu-id="a3e3e-156">Esto no debe ocurrir durante:</span><span class="sxs-lookup"><span data-stu-id="a3e3e-156">This should not occur during:</span></span>

- <span data-ttu-id="a3e3e-157">Dispositivos que toman una actualización de mantenimiento mensual</span><span class="sxs-lookup"><span data-stu-id="a3e3e-157">Devices taking a monthly servicing update</span></span>

<span data-ttu-id="a3e3e-158">Métodos de trabajo:</span><span class="sxs-lookup"><span data-stu-id="a3e3e-158">Work around methods:</span></span>

- <span data-ttu-id="a3e3e-159">Métodos de inicio de sesión como pin, contraseña, iris, autenticación web o claves FIDO2.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-159">Sign-in methods such as PIN, Password, Iris, Web Authentication, or FIDO2 keys.</span></span>
- <span data-ttu-id="a3e3e-160">Si no se puede recordar el PIN del dispositivo y no hay otros métodos de autenticación disponibles, un usuario puede usar el [modo de reflashación manual](hololens-recovery.md#manual-procedure).</span><span class="sxs-lookup"><span data-stu-id="a3e3e-160">If device PIN cannot be remembered, and other authentication methods are not available, then a user can use [manual reflashing mode](hololens-recovery.md#manual-procedure).</span></span>

[<span data-ttu-id="a3e3e-161">Volver a la lista</span><span class="sxs-lookup"><span data-stu-id="a3e3e-161">Back to list</span></span>](#list)

## <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="a3e3e-162">Microsoft Edge no se puede iniciar</span><span class="sxs-lookup"><span data-stu-id="a3e3e-162">Microsoft Edge fails to launch</span></span>

> [!NOTE]
> <span data-ttu-id="a3e3e-163">Este problema se creó originalmente con la versión de envío Microsoft Edge en mente.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-163">This issue was originally created with the shipping version of Microsoft Edge in-mind.</span></span> <span data-ttu-id="a3e3e-164">Este problema se puede resolver en el [nuevo Microsoft Edge](hololens-new-edge.md).</span><span class="sxs-lookup"><span data-stu-id="a3e3e-164">This issue may be resolved in the [new Microsoft Edge](hololens-new-edge.md).</span></span> <span data-ttu-id="a3e3e-165">Si no es así, envíe sus comentarios.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-165">If it is not, please file feedback.</span></span>

<span data-ttu-id="a3e3e-166">Algunos clientes han notificado un problema por el Microsoft Edge no se puede iniciar.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-166">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="a3e3e-167">Para estos clientes, el problema persiste durante el reinicio y no se resuelve con Windows o actualizaciones de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-167">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="a3e3e-168">Si tiene este problema y ha confirmado que [Windows](hololens-updates.md#manually-check-for-updates)está actualizado, envíe un error desde la aplicación [Centro de opiniones](hololens-feedback.md) con la siguiente categoría y subcategoría: Instalar y actualizar > Descarga, instalación y configuración de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-168">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="a3e3e-169">No hay ninguna solución alternativa conocida, ya que hasta ahora no hemos podido resolver la causa principal del problema.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-169">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="a3e3e-170">La presentación de un error mediante Centro de opiniones ayudará a nuestra investigación.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-170">Filing a bug via Feedback Hub will help our investigation!</span></span> <span data-ttu-id="a3e3e-171">Se trata de **un problema conocido.**</span><span class="sxs-lookup"><span data-stu-id="a3e3e-171">This is a **known issue**.</span></span>

[<span data-ttu-id="a3e3e-172">Volver a la lista</span><span class="sxs-lookup"><span data-stu-id="a3e3e-172">Back to list</span></span>](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a><span data-ttu-id="a3e3e-173">El teclado no cambia a caracteres especiales</span><span class="sxs-lookup"><span data-stu-id="a3e3e-173">Keyboard doesn't switch to special characters</span></span>

<span data-ttu-id="a3e3e-174">Hay un problema durante la OOBE, donde una vez que el usuario ha elegido una cuenta de trabajo o educativa y escribe su contraseña, intenta cambiar a los caracteres especiales del teclado pulsando el botón &123 no cambia a caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-174">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> <span data-ttu-id="a3e3e-175">Se trata de **un problema conocido.**</span><span class="sxs-lookup"><span data-stu-id="a3e3e-175">This is a **known issue**.</span></span>

<span data-ttu-id="a3e3e-176">Entornos de trabajo:</span><span class="sxs-lookup"><span data-stu-id="a3e3e-176">Work-arounds:</span></span>
-   <span data-ttu-id="a3e3e-177">Cierre el teclado y vuelva a abrirlo pulsando en el campo de texto.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-177">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="a3e3e-178">Escriba incorrectamente la contraseña.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-178">Incorrectly enter your password.</span></span> <span data-ttu-id="a3e3e-179">Cuando el teclado se vuelva a iniciar la próxima vez, funcionará según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-179">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="a3e3e-180">Autenticación web, cierre el teclado y seleccione **Iniciar sesión desde otro dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="a3e3e-180">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span>
-   <span data-ttu-id="a3e3e-181">Si solo escribe números, un usuario puede presionar y mantener presionadas ciertas teclas para abrir un menú expandido.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-181">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="a3e3e-182">Uso de un teclado USB.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-182">Using a USB keyboard.</span></span>

<span data-ttu-id="a3e3e-183">Esto no afecta a:</span><span class="sxs-lookup"><span data-stu-id="a3e3e-183">This does not affect:</span></span>
- <span data-ttu-id="a3e3e-184">Usuarios que deciden usar una cuenta personal.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-184">Users who choose to use a personal account.</span></span>

[<span data-ttu-id="a3e3e-185">Volver a la lista</span><span class="sxs-lookup"><span data-stu-id="a3e3e-185">Back to list</span></span>](#list)

## <a name="downloading-locked-files-doesnt-error"></a><span data-ttu-id="a3e3e-186">No se produce un error al descargar archivos bloqueados</span><span class="sxs-lookup"><span data-stu-id="a3e3e-186">Downloading locked files doesn't error</span></span>

> [!NOTE]
> <span data-ttu-id="a3e3e-187">Se trata de **un problema conocido** que se ha corregido en la Windows Insider, versión 20348.1403.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-187">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span>

<span data-ttu-id="a3e3e-188">En compilaciones anteriores de Windows Holographic, al intentar descargar un archivo bloqueado, el resultado sería una página de error HTTP.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-188">In previous builds of Windows Holographic, when attempting to download a locked file, the result would be an HTTP error page.</span></span> <span data-ttu-id="a3e3e-189">En la actualización Windows Holographic, versión 21H1, al intentar descargar un archivo bloqueado no ocurre nada visible: el archivo no se descarga y no hay ningún error.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-189">In the Windows Holographic, version 21H1 update, trying to download a locked file results in nothing visible happening—the file doesn’t download and there’s no error.</span></span>

[<span data-ttu-id="a3e3e-190">Volver a la lista</span><span class="sxs-lookup"><span data-stu-id="a3e3e-190">Back to list</span></span>](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a><span data-ttu-id="a3e3e-191">Portal de dispositivos de carga y descarga de archivos</span><span class="sxs-lookup"><span data-stu-id="a3e3e-191">Device Portal file upload/download times out</span></span>
> [!NOTE]
> <span data-ttu-id="a3e3e-192">Se trata de **un problema conocido** que se ha corregido en la Windows Insider, versión 20348.1403.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-192">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span> <span data-ttu-id="a3e3e-193">Si anteriormente deshabilitó la conexión SSL como parte de la solución alternativa, se recomienda encarecidamente volver a habilitarla.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-193">If you previously disabled SSL Connection as part of the workaround, we highly recommend you re-enable it.</span></span>


<span data-ttu-id="a3e3e-194">Algunos clientes han descubierto que, al intentar cargar o descargar archivos, la operación puede parecer que se ha quedado y, a continuación, se ha completado el tiempo de espera o nunca se ha completado.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-194">Some customers have found, when attempting to upload or download files, the operation might appear to hang and then time out or never complete.</span></span> <span data-ttu-id="a3e3e-195">Esto es independiente[](#downloading-locked-files-doesnt-error) del problema conocido de "archivo bloqueado": esto afecta Windows compilaciones en el mercado de holographic, versiones 2004, 20H2 y 21H1.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-195">This is separate from the '[file locked' known issue](#downloading-locked-files-doesnt-error) -- this affects Windows Holographic, versions 2004, 20H2 and 21H1 in-market builds.</span></span> <span data-ttu-id="a3e3e-196">El problema se ha originado en un error en el control de Portal de dispositivos de determinadas solicitudes y se produce de forma más coherente al usar https, que es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-196">The problem has been root caused to a bug in Device Portal's handling of certain requests, and is most consistently hit when using https, which is the default.</span></span> 

### <a name="workaround"></a><span data-ttu-id="a3e3e-197">Solución alternativa</span><span class="sxs-lookup"><span data-stu-id="a3e3e-197">Workaround</span></span>

<span data-ttu-id="a3e3e-198">Esta solución alternativa, que se aplica igualmente a Wi-Fi y UsbNcm, consiste en deshabilitar la opción "obligatorio" en "Conexión SSL".</span><span class="sxs-lookup"><span data-stu-id="a3e3e-198">This workaround, which applies equally to Wi-Fi and UsbNcm, is to disable the "required" option under "SSL Connection".</span></span> <span data-ttu-id="a3e3e-199">Para ello, vaya a Portal de dispositivos, **Sistema** y seleccione la **página Preferencias.**</span><span class="sxs-lookup"><span data-stu-id="a3e3e-199">To do so, navigate to Device Portal, **System**, and select the **Preferences** page.</span></span> <span data-ttu-id="a3e3e-200">En la **sección Seguridad del dispositivo,** busque **Conexión SSL** y desactive para deshabilitar **Requerido.**</span><span class="sxs-lookup"><span data-stu-id="a3e3e-200">In the **Device Security** section, locate **SSL Connection**, and uncheck to disable **Required**.</span></span>

<span data-ttu-id="a3e3e-201">A continuación, el usuario debe ir a http://, no https:// (dirección IP) y características como la carga y descarga de archivos funcionarán.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-201">The user should then go to http://, not https:// (IP address) and features like file upload and download will work.</span></span>

[<span data-ttu-id="a3e3e-202">Volver a la lista</span><span class="sxs-lookup"><span data-stu-id="a3e3e-202">Back to list</span></span>](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a><span data-ttu-id="a3e3e-203">Pantalla azul después de la inscripción de la versión preliminar de Insider en un dispositivo parpadeado con una compilación de Insider</span><span class="sxs-lookup"><span data-stu-id="a3e3e-203">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>

<span data-ttu-id="a3e3e-204">Se trata de un problema que afecta a los usuarios que se encontraban en una compilación en versión preliminar de Insider, han reflashado su HoloLens 2 con una nueva compilación en versión preliminar de Insider y, a continuación, se han inscrito en el programa Insider.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-204">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> <span data-ttu-id="a3e3e-205">Se trata de **un problema conocido.**</span><span class="sxs-lookup"><span data-stu-id="a3e3e-205">This is a **known issue**.</span></span>

<span data-ttu-id="a3e3e-206">Esto no afecta a:</span><span class="sxs-lookup"><span data-stu-id="a3e3e-206">This does not affect:</span></span>
- <span data-ttu-id="a3e3e-207">Usuarios que no están inscritos en Windows Insider</span><span class="sxs-lookup"><span data-stu-id="a3e3e-207">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="a3e3e-208">Insiders:</span><span class="sxs-lookup"><span data-stu-id="a3e3e-208">Insiders:</span></span>
    - <span data-ttu-id="a3e3e-209">Si un dispositivo se ha inscrito desde las compilaciones de Insider, era la versión 18362.x</span><span class="sxs-lookup"><span data-stu-id="a3e3e-209">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="a3e3e-210">Si se ha publicado una compilación 19041.x firmada por Insider, permanezca inscrito en el programa Insider.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-210">If they flashed an Insider signed 19041.x build AND stay enrolled in the Insider program</span></span>

<span data-ttu-id="a3e3e-211">Trabajo:</span><span class="sxs-lookup"><span data-stu-id="a3e3e-211">Work-around:</span></span> 
- <span data-ttu-id="a3e3e-212">Evitar el problema</span><span class="sxs-lookup"><span data-stu-id="a3e3e-212">Avoid the issue</span></span> 
    - <span data-ttu-id="a3e3e-213">Flash en una compilación que no es de insider.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-213">Flash a non-insider build.</span></span> <span data-ttu-id="a3e3e-214">Una de las actualizaciones mensuales normales.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-214">One of the regular monthly updates.</span></span>
    - <span data-ttu-id="a3e3e-215">Permanecer en la versión preliminar de Insider</span><span class="sxs-lookup"><span data-stu-id="a3e3e-215">Stay on Insider Preview</span></span>
- <span data-ttu-id="a3e3e-216">Reflash the device (Volver a actualizar el dispositivo)</span><span class="sxs-lookup"><span data-stu-id="a3e3e-216">Reflash the device</span></span>

    1. <span data-ttu-id="a3e3e-217">Coloque el [HoloLens 2 en modo de parpadeo](hololens-recovery.md) manualmente; para hacerlo, apague completamente sin conectarse.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-217">Put the [HoloLens 2 into flashing mode](hololens-recovery.md) manually by fully powering down while not connect.</span></span> <span data-ttu-id="a3e3e-218">A continuación, mientras mantiene presionado Volumen, pulse el botón De encendido.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-218">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="a3e3e-219">Conectar al equipo y abra Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-219">Connect to the PC and open Advanced Recovery Companion.</span></span>
    
    1. <span data-ttu-id="a3e3e-220">Flash el HoloLens 2 a la compilación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-220">Flash the HoloLens 2 to the default build.</span></span>

[<span data-ttu-id="a3e3e-221">Volver a la lista</span><span class="sxs-lookup"><span data-stu-id="a3e3e-221">Back to list</span></span>](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a><span data-ttu-id="a3e3e-222">OneDrive no carga automáticamente imágenes</span><span class="sxs-lookup"><span data-stu-id="a3e3e-222">OneDrive doesn't automatically upload pictures</span></span>

<span data-ttu-id="a3e3e-223">La OneDrive aplicación para HoloLens no admite la carga automática de cámaras para cuentas de trabajo o educativas.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-223">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span> <span data-ttu-id="a3e3e-224">Se trata de **un problema conocido.**</span><span class="sxs-lookup"><span data-stu-id="a3e3e-224">This is a **known issue**.</span></span>

<span data-ttu-id="a3e3e-225">Soluciones alternativas:</span><span class="sxs-lookup"><span data-stu-id="a3e3e-225">Workarounds:</span></span>

- <span data-ttu-id="a3e3e-226">Si es viable para su empresa, la carga automática de la cámara se admite en las cuentas microsoft del consumidor.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-226">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="a3e3e-227">Puede iniciar sesión en su cuenta Microsoft además de la cuenta profesional o educativa (la aplicación OneDrive admite el inicio de sesión dual).</span><span class="sxs-lookup"><span data-stu-id="a3e3e-227">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="a3e3e-228">Desde el perfil de la cuenta Microsoft OneDrive puede habilitar la carga automática de la cámara en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-228">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="a3e3e-229">Si no puede usar de forma segura una cuenta Microsoft de consumidor para cargar las fotos automáticamente, puede cargar manualmente las fotos en su cuenta de trabajo o educativa desde la OneDrive aplicación.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-229">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="a3e3e-230">Para ello, asegúrese de que ha iniciado sesión en su cuenta de trabajo o educativa en la OneDrive aplicación.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-230">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="a3e3e-231">Seleccione el **+** botón y elija **Upload**.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-231">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="a3e3e-232">Para buscar las fotos o vídeos que desea cargar, vaya a **Imágenes > Camera Roll**.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-232">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="a3e3e-233">Seleccione las fotos o vídeos que desea cargar y, a continuación, seleccione el **botón** Abrir.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-233">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

[<span data-ttu-id="a3e3e-234">Volver a la lista</span><span class="sxs-lookup"><span data-stu-id="a3e3e-234">Back to list</span></span>](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a><span data-ttu-id="a3e3e-235">HoloLens no responde o no se inicia</span><span class="sxs-lookup"><span data-stu-id="a3e3e-235">HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="a3e3e-236">Si el HoloLens no se inicia:</span><span class="sxs-lookup"><span data-stu-id="a3e3e-236">If your HoloLens won't start:</span></span>

- <span data-ttu-id="a3e3e-237">Si los LED situados junto al botón de encendido no se encienden o solo un LED parpadea brevemente, es posible que deba cargar el [HoloLens.](hololens2-charging.md#charging-the-device)</span><span class="sxs-lookup"><span data-stu-id="a3e3e-237">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens2-charging.md#charging-the-device)</span></span>
- <span data-ttu-id="a3e3e-238">Si los LED se encienden al presionar el botón de encendido, pero no puede ver nada en las pantallas, realice un restablecimiento de forma fuerte [del dispositivo.](hololens-recovery.md#hard-reset-procedure)</span><span class="sxs-lookup"><span data-stu-id="a3e3e-238">If the LEDs light up when you press the power button but you can't see anything on the displays, [do a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="a3e3e-239">Si el HoloLens se inmoviliza o deja de responder:</span><span class="sxs-lookup"><span data-stu-id="a3e3e-239">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="a3e3e-240">Para desactivar el HoloLens, presione el botón de encendido hasta que los cinco LED se apaguen o durante 15 segundos si los LED no responden.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-240">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="a3e3e-241">Para iniciar la HoloLens, vuelva a presionar el botón de encendido.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-241">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="a3e3e-242">Si estos pasos no funcionan, [](hololens-recovery.md) puede intentar recuperar el HoloLens 2 o HoloLens [(1.ª generación).](hololens1-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="a3e3e-242">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

[<span data-ttu-id="a3e3e-243">Volver a la lista</span><span class="sxs-lookup"><span data-stu-id="a3e3e-243">Back to list</span></span>](#list)

## <a name="low-disk-space-error"></a><span data-ttu-id="a3e3e-244">Error "Espacio en disco bajo"</span><span class="sxs-lookup"><span data-stu-id="a3e3e-244">"Low Disk Space" error</span></span>

<span data-ttu-id="a3e3e-245">Deberá liberar espacio de almacenamiento haciendo uno o varios de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="a3e3e-245">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="a3e3e-246">Elimine algunos espacios no usados.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-246">Delete some unused spaces.</span></span> <span data-ttu-id="a3e3e-247">Vaya a **Configuración** Espacios del sistema, seleccione un espacio que ya no necesite  >    >  y, a continuación, **seleccione Quitar**.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-247">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="a3e3e-248">Quite algunos de los hologramas que ha colocado.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-248">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="a3e3e-249">Elimine algunas imágenes y vídeos de la Fotos aplicación.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-249">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="a3e3e-250">Desinstale algunas aplicaciones del HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-250">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="a3e3e-251">En la **lista Todas las** aplicaciones, mantenga presionada la aplicación que desea desinstalar y, a continuación, seleccione **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-251">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

[<span data-ttu-id="a3e3e-252">Volver a la lista</span><span class="sxs-lookup"><span data-stu-id="a3e3e-252">Back to list</span></span>](#list)

## <a name="calibration-fails"></a><span data-ttu-id="a3e3e-253">Error de calibración</span><span class="sxs-lookup"><span data-stu-id="a3e3e-253">Calibration fails</span></span>

<span data-ttu-id="a3e3e-254">La calibración debería funcionar para la mayoría de las personas, pero hay casos en los que se produce un error en la calibración.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-254">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="a3e3e-255">Entre los posibles motivos del error de calibración se incluyen:</span><span class="sxs-lookup"><span data-stu-id="a3e3e-255">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="a3e3e-256">Distraerse y no seguir los objetivos de calibración</span><span class="sxs-lookup"><span data-stu-id="a3e3e-256">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="a3e3e-257">Visor de dispositivos o visores de dispositivos desnuciados o rascados que no están correctamente posicionados</span><span class="sxs-lookup"><span data-stu-id="a3e3e-257">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="a3e3e-258">Gafas desnuciadas o rayadas</span><span class="sxs-lookup"><span data-stu-id="a3e3e-258">Dirty or scratched glasses</span></span>
- <span data-ttu-id="a3e3e-259">Ciertos tipos de lentes de contacto y gafas (lentes de contacto coloreadas, algunas lentes de contacto toréricas, gafas de bloqueo de IR, gafas de sol de alta graduación, gafas de sol o similares)</span><span class="sxs-lookup"><span data-stu-id="a3e3e-259">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="a3e3e-260">Una composición más pronunciada y algunas extensiones de pestañas</span><span class="sxs-lookup"><span data-stu-id="a3e3e-260">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="a3e3e-261">Marcos de gafas gruesas o de vello si impiden que el dispositivo vea los ojos</span><span class="sxs-lookup"><span data-stu-id="a3e3e-261">Hair or thick eyeglass frames if they're blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="a3e3e-262">Cierta fisonología ocular, condiciones oculares o cáncer de ojo, como ojos estrechos, pestañas largas, amblyopia, nistagmus, algunos casos de LASIK u otras operaciones oculares</span><span class="sxs-lookup"><span data-stu-id="a3e3e-262">Certain eye physiology, eye conditions, or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="a3e3e-263">Si la calibración no se realiza correctamente, pruebe:</span><span class="sxs-lookup"><span data-stu-id="a3e3e-263">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="a3e3e-264">Limpieza del visor del dispositivo</span><span class="sxs-lookup"><span data-stu-id="a3e3e-264">Cleaning your device visor</span></span>
- <span data-ttu-id="a3e3e-265">Limpieza de las gafas</span><span class="sxs-lookup"><span data-stu-id="a3e3e-265">Cleaning your glasses</span></span>
- <span data-ttu-id="a3e3e-266">Insertar el visor del dispositivo lo más cerca posible de los ojos</span><span class="sxs-lookup"><span data-stu-id="a3e3e-266">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="a3e3e-267">Mover objetos en el visor fuera del camino (por ejemplo, el vello)</span><span class="sxs-lookup"><span data-stu-id="a3e3e-267">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="a3e3e-268">Encender una luz en la habitación o salir de la luz directa</span><span class="sxs-lookup"><span data-stu-id="a3e3e-268">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="a3e3e-269">Si ha seguido todas las directrices y la calibración sigue teniendo errores, puede deshabilitar la solicitud de calibración en Configuración.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-269">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="a3e3e-270">Háganoslo saber también mediante la presentación de comentarios [en Centro de opiniones](hololens-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="a3e3e-270">Also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="a3e3e-271">Consulte también información relacionada para la solución [de problemas de color de imagen o brillo.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span><span class="sxs-lookup"><span data-stu-id="a3e3e-271">Also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="a3e3e-272">La configuración de IPD no es aplicable HoloLens 2, ya que el sistema calcula las posiciones de los ojos.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-272">Setting IPD is not applicable for HoloLens 2, since eye positions are computed by the system.</span></span> 

[<span data-ttu-id="a3e3e-273">Volver a la lista</span><span class="sxs-lookup"><span data-stu-id="a3e3e-273">Back to list</span></span>](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a><span data-ttu-id="a3e3e-274">No se puede iniciar sesión porque mi HoloLens se ha configurado previamente para otra persona</span><span class="sxs-lookup"><span data-stu-id="a3e3e-274">Can't sign in because my HoloLens was previously set up for someone else</span></span>

<span data-ttu-id="a3e3e-275">Puede poner [el dispositivo en modo de **flashing y** usar Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) para recuperar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-275">You can [put the device into **Flashing Mode** and use Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) to recover the device.</span></span>

[<span data-ttu-id="a3e3e-276">Volver a la lista</span><span class="sxs-lookup"><span data-stu-id="a3e3e-276">Back to list</span></span>](#list)


## <a name="unity-isnt-working"></a><span data-ttu-id="a3e3e-277">Unity no funciona</span><span class="sxs-lookup"><span data-stu-id="a3e3e-277">Unity isn't working</span></span>

- <span data-ttu-id="a3e3e-278">Consulte [Instalación de las herramientas](/windows/mixed-reality/install-the-tools) para obtener la versión más actualizada de Unity recomendada para HoloLens desarrollo.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-278">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="a3e3e-279">Los problemas conocidos de Unity HoloLens Technical Preview se documentan en [los HoloLens de Unity.](https://forum.unity3d.com/threads/known-issues.394627/)</span><span class="sxs-lookup"><span data-stu-id="a3e3e-279">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

[<span data-ttu-id="a3e3e-280">Volver a la lista</span><span class="sxs-lookup"><span data-stu-id="a3e3e-280">Back to list</span></span>](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a><span data-ttu-id="a3e3e-281">Windows Portal de dispositivos no funciona correctamente</span><span class="sxs-lookup"><span data-stu-id="a3e3e-281">Windows Device Portal isn't working correctly</span></span>

- <span data-ttu-id="a3e3e-282">La característica Live Preview de Mixed Reality captura puede presentar varios segundos de latencia.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-282">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="a3e3e-283">En la página Entrada virtual, los controles Gesto y Desplazamiento de la sección Gestos virtuales no son funcionales.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-283">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="a3e3e-284">Su uso no tendrá ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-284">Using them will have no effect.</span></span> <span data-ttu-id="a3e3e-285">El teclado virtual de la página de entrada virtual funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-285">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="a3e3e-286">Después de habilitar el modo de desarrollador Configuración, puede tardar unos segundos antes de que el conmutador active el Portal de dispositivos está habilitado.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-286">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

[<span data-ttu-id="a3e3e-287">Volver a la lista</span><span class="sxs-lookup"><span data-stu-id="a3e3e-287">Back to list</span></span>](#list)

## <a name="the-hololens-emulator-isnt-working"></a><span data-ttu-id="a3e3e-288">El HoloLens Emulator no funciona</span><span class="sxs-lookup"><span data-stu-id="a3e3e-288">The HoloLens Emulator isn't working</span></span>

<span data-ttu-id="a3e3e-289">La información sobre HoloLens emulator se encuentra en nuestra documentación para desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-289">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="a3e3e-290">Obtenga más información sobre [la solución de problemas HoloLens emulador](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="a3e3e-290">Read more about [troubleshooting the HoloLens emulator](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).</span></span>


- <span data-ttu-id="a3e3e-291">No todas las aplicaciones del Microsoft Store son compatibles con el emulador.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-291">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="a3e3e-292">Por ejemplo, Young Conker y Fragments no se pueden reproducir en el emulador.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-292">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="a3e3e-293">No puede usar la cámara web del equipo en el Emulator.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-293">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="a3e3e-294">La característica Live Preview del Windows Portal de dispositivos no funciona con el emulador.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-294">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="a3e3e-295">Todavía puede capturar vídeos Mixed Reality imágenes.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-295">You can still capture Mixed Reality videos and images.</span></span>

[<span data-ttu-id="a3e3e-296">Volver a la lista</span><span class="sxs-lookup"><span data-stu-id="a3e3e-296">Back to list</span></span>](#list)

## <a name="voice-commands-arent-working"></a><span data-ttu-id="a3e3e-297">Los comandos de voz no funcionan</span><span class="sxs-lookup"><span data-stu-id="a3e3e-297">Voice commands aren't working</span></span>

<span data-ttu-id="a3e3e-298">Si Cortana no responde a los comandos de voz, asegúrese de Cortana esté activado.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-298">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="a3e3e-299">En la lista Todas las aplicaciones, seleccione **Cortana**  >  **menú**  >  **Notebook**  >  **Configuración** para realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-299">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="a3e3e-300">Para más información sobre lo que puede decir, consulte [Uso de la voz con HoloLens](hololens-cortana.md).</span><span class="sxs-lookup"><span data-stu-id="a3e3e-300">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

<span data-ttu-id="a3e3e-301">En HoloLens (1ª generación), el reconocimiento de voz integrado no es configurable.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-301">On HoloLens (1st gen), built-in speech recognition is not configurable.</span></span> <span data-ttu-id="a3e3e-302">Siempre está activado.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-302">It is always turned on.</span></span> <span data-ttu-id="a3e3e-303">En HoloLens 2, puede elegir si quiere activar el reconocimiento de voz y Cortana durante la configuración del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-303">On HoloLens 2, you can choose whether to turn on both speech recognition and Cortana during device setup.</span></span>

<span data-ttu-id="a3e3e-304">Si el HoloLens 2 no responde a su voz, asegúrese de que el reconocimiento de voz está activado.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-304">If your HoloLens 2 is not responding to your voice, make sure Speech recognition is turned on.</span></span> <span data-ttu-id="a3e3e-305">Vaya a **Inicio Configuración**  >    >  **Voz**  >  **de privacidad** y active Reconocimiento **de voz.**</span><span class="sxs-lookup"><span data-stu-id="a3e3e-305">Go to **Start** > **Settings** > **Privacy** > **Speech** and turn on **Speech recognition**.</span></span>

[<span data-ttu-id="a3e3e-306">Volver a la lista</span><span class="sxs-lookup"><span data-stu-id="a3e3e-306">Back to list</span></span>](#list)

## <a name="hand-input-isnt-working"></a><span data-ttu-id="a3e3e-307">La entrada de mano no funciona</span><span class="sxs-lookup"><span data-stu-id="a3e3e-307">Hand input isn't working</span></span>

<span data-ttu-id="a3e3e-308">Para asegurarse de HoloLens puede ver las manos, debe mantenerlas en el marco de gestos.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-308">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="a3e3e-309">El Mixed Reality Home proporciona comentarios que le permiten saber cuándo se realiza el seguimiento de las manos.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-309">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="a3e3e-310">Los comentarios son diferentes en las distintas versiones de HoloLens:</span><span class="sxs-lookup"><span data-stu-id="a3e3e-310">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="a3e3e-311">En HoloLens (1ª generación), el cursor de mirada cambia de un punto a un anillo</span><span class="sxs-lookup"><span data-stu-id="a3e3e-311">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="a3e3e-312">En HoloLens 2, aparece un cursor de dedo cuando la mano está cerca de una pizarra y aparece un rayo cuando las pizarras están más alejadas</span><span class="sxs-lookup"><span data-stu-id="a3e3e-312">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="a3e3e-313">Muchas aplicaciones envolventes siguen patrones de entrada similares a Mixed Reality Inicio.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-313">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="a3e3e-314">Obtenga más información sobre el uso de la entrada [a mano HoloLens (1.ª generación)](hololens1-basic-usage.md#use-hololens-with-your-hands) [y HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span><span class="sxs-lookup"><span data-stu-id="a3e3e-314">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="a3e3e-315">Si va a llevar unas gafas, tenga en cuenta que algunos tipos de gafas no funcionan con el seguimiento de las manos.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-315">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="a3e3e-316">Un ejemplo común es el de la almohadilla negra, que tiende a absorber la luz de las cámaras de profundidad y no la recoge.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-316">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="a3e3e-317">Si el trabajo implica una insondación de ruedas, se recomienda probar un color más claro, como azul o gris.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-317">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="a3e3e-318">Otro ejemplo es una bolsa grande, que tiende a ocultar la forma de la mano.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-318">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="a3e3e-319">Se recomienda usar el mayor ajuste posible para obtener los mejores resultados.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-319">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="a3e3e-320">Si el visor tiene huellas digitales o marcas, use el limpiador de limpieza de microfibras que se incluye con el HoloLens para limpiar el visor.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-320">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

[<span data-ttu-id="a3e3e-321">Volver a la lista</span><span class="sxs-lookup"><span data-stu-id="a3e3e-321">Back to list</span></span>](#list)

## <a name="cant-connect-to-wi-fi"></a><span data-ttu-id="a3e3e-322">No se puede conectar a Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="a3e3e-322">Can't connect to Wi-Fi</span></span>

<span data-ttu-id="a3e3e-323">Estas son algunas de las cosas que debe intentar si no puede conectar HoloLens a una red Wi-Fi:</span><span class="sxs-lookup"><span data-stu-id="a3e3e-323">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

- <span data-ttu-id="a3e3e-324">Asegúrese de que la Wi-Fi está activada.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-324">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="a3e3e-325">Para comprobarlo, use el gesto Iniciar y, a continuación, **seleccione Configuración**  >  **Red &amp;**  >  **Wi-Fi de Internet.**</span><span class="sxs-lookup"><span data-stu-id="a3e3e-325">To check, use the Start gesture, then select **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="a3e3e-326">Si la Wi-Fi está activada, intente desactivarla y volver a activarla.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-326">If Wi-Fi is on, try turning it off and then on again.</span></span>
- <span data-ttu-id="a3e3e-327">Acérquese al enrutador o al punto de acceso.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-327">Move closer to the router or access point.</span></span>
- <span data-ttu-id="a3e3e-328">Reinicie el enrutador Wi-Fi y, a continuación, [reinicie HoloLens](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="a3e3e-328">Restart your Wi-Fi router, then [restart HoloLens](hololens-recovery.md).</span></span> <span data-ttu-id="a3e3e-329">Try connecting again (Intente conectarse de nuevo).</span><span class="sxs-lookup"><span data-stu-id="a3e3e-329">Try connecting again.</span></span>
- <span data-ttu-id="a3e3e-330">Si ninguna de estas cosas funciona, asegúrese de que el enrutador usa el firmware más reciente.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-330">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="a3e3e-331">Puede encontrar esta información en el sitio web del fabricante.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-331">You can find this information on the manufacturer website.</span></span>

[<span data-ttu-id="a3e3e-332">Volver a la lista</span><span class="sxs-lookup"><span data-stu-id="a3e3e-332">Back to list</span></span>](#list)

## <a name="bluetooth-devices-arent-pairing"></a><span data-ttu-id="a3e3e-333">Bluetooth dispositivos no se emparejan</span><span class="sxs-lookup"><span data-stu-id="a3e3e-333">Bluetooth devices aren't pairing</span></span>

<span data-ttu-id="a3e3e-334">Si tiene problemas para emparejar [un Bluetooth,](hololens-connect-devices.md)pruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a3e3e-334">If you're having problems [pairing a Bluetooth device](hololens-connect-devices.md), try the following:</span></span>

- <span data-ttu-id="a3e3e-335">Vaya a **Configuración**  >  **Dispositivos** y asegúrese de que Bluetooth está activado.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-335">Go to **Settings** > **Devices**, and make sure that Bluetooth is turned on.</span></span> <span data-ttu-id="a3e3e-336">Si es así, descándalo y vuelva a activarlo.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-336">If it is, turn it off and on again.</span></span>
- <span data-ttu-id="a3e3e-337">Asegúrese de que el dispositivo Bluetooth está totalmente cargado o tiene baterías nuevas.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-337">Make sure that your Bluetooth device is fully charged or has fresh batteries.</span></span>
- <span data-ttu-id="a3e3e-338">Si todavía no puede conectarse, [reinicie el HoloLens](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="a3e3e-338">If you still can't connect, [restart the HoloLens](hololens-recovery.md).</span></span>

[<span data-ttu-id="a3e3e-339">Volver a la lista</span><span class="sxs-lookup"><span data-stu-id="a3e3e-339">Back to list</span></span>](#list)

## <a name="usb-c-microphone-isnt-working"></a><span data-ttu-id="a3e3e-340">El micrófono USB-C no funciona</span><span class="sxs-lookup"><span data-stu-id="a3e3e-340">USB-C Microphone isn't working</span></span>
<span data-ttu-id="a3e3e-341">Tenga en cuenta que algunos micrófonos USB-C se informan incorrectamente como micrófono *y* altavoz.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-341">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="a3e3e-342">Se trata de un problema con el micrófono y no con HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-342">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="a3e3e-343">Al conectar uno de estos micrófonos a HoloLens, es posible que se pierda el sonido.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-343">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="a3e3e-344">Afortunadamente, hay una corrección sencilla.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-344">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="a3e3e-345">En **Configuración** del sistema , establezca explícitamente los altavoces integrados (controlador de audio de características  ->    ->   **análogas)** como **el dispositivo predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-345">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="a3e3e-346">HoloLens recordar esta configuración incluso si el micrófono se quita y se vuelve a conectar más adelante.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-346">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![Solución de problemas de micrófonos USB-C](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a><span data-ttu-id="a3e3e-348">Los dispositivos que aparecen como Configuración no funcionan</span><span class="sxs-lookup"><span data-stu-id="a3e3e-348">Devices listed as available in Settings don't work</span></span>

<span data-ttu-id="a3e3e-349">HoloLens (1.ª generación) no admite Bluetooth perfiles de audio.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-349">HoloLens (1st gen) doesn't support Bluetooth audio profiles.</span></span> <span data-ttu-id="a3e3e-350">Bluetooth dispositivos de audio, como altavoces y cascos, pueden aparecer como disponibles en HoloLens configuración, pero no se admiten.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-350">Bluetooth audio devices, such as speakers and headsets, may appear as available in HoloLens settings, but they aren't supported.</span></span>

<span data-ttu-id="a3e3e-351">HoloLens 2 admite el perfil de audio Bluetooth A2DP para la reproducción estéreo.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-351">HoloLens 2 supports the Bluetooth A2DP audio profile for stereo playback.</span></span> <span data-ttu-id="a3e3e-352">El Bluetooth hands free que permite la captura de micrófono desde un periférico Bluetooth no se admite en HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-352">The Bluetooth Hands Free profile which enables microphone capture from a Bluetooth peripheral is not supported on HoloLens 2.</span></span>

<span data-ttu-id="a3e3e-353">Si tiene problemas para usar un Bluetooth, asegúrese de que es un dispositivo compatible.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-353">If you're having trouble using a Bluetooth device, make sure that it's a supported device.</span></span> <span data-ttu-id="a3e3e-354">Entre los dispositivos admitidos se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a3e3e-354">Supported devices include the following:</span></span>

- <span data-ttu-id="a3e3e-355">QWERTY en inglés Bluetooth teclados (puede usarlos en cualquier lugar en el que use el teclado holográfico).</span><span class="sxs-lookup"><span data-stu-id="a3e3e-355">English-language QWERTY Bluetooth keyboards (you can use these anywhere that you use the holographic keyboard).</span></span>
- <span data-ttu-id="a3e3e-356">Bluetooth mouse.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-356">Bluetooth mice.</span></span>
- <span data-ttu-id="a3e3e-357">El [HoloLens de clics .](hololens1-clicker.md)</span><span class="sxs-lookup"><span data-stu-id="a3e3e-357">The [HoloLens clicker](hololens1-clicker.md).</span></span>

<span data-ttu-id="a3e3e-358">Puede emparejar otros dispositivos BLUETOOTH HID y GBP junto con su HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-358">You can pair other Bluetooth HID and GATT devices together with your HoloLens.</span></span> <span data-ttu-id="a3e3e-359">Sin embargo, es posible que tenga que instalar las aplicaciones complementarias correspondientes Microsoft Store usar realmente los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-359">However, you may have to install corresponding companion apps from Microsoft Store to actually use the devices.</span></span>

[<span data-ttu-id="a3e3e-360">Volver a la lista</span><span class="sxs-lookup"><span data-stu-id="a3e3e-360">Back to list</span></span>](#list)
