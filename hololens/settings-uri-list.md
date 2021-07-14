---
title: Visibilidad de la configuración de páginas
description: Manténgase al día con nuestra lista de URI compatibles con PageVisibilityList y nuestra guía sobre dispositivos de realidad mixta HoloLens.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, acceso asignado, quiosco, página de configuración
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d28994d911532a940d82756aa45609571ee80ac3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924339"
---
# <a name="page-settings-visibility"></a><span data-ttu-id="3b914-104">Visibilidad de la configuración de páginas</span><span class="sxs-lookup"><span data-stu-id="3b914-104">Page Settings Visibility</span></span>

<span data-ttu-id="3b914-105">Una de las características administrables para dispositivos HoloLens es usar la directiva [Configuración/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir las páginas que se ven en la aplicación Configuración.</span><span class="sxs-lookup"><span data-stu-id="3b914-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="3b914-106">PageVisibilityList es una directiva mediante la cual los administradores de TI pueden evitar que páginas específicas de la aplicación Configuración del sistema sean visibles o accesibles, o bien aplicar dicha restricción a todas las páginas salvo las especificadas.</span><span class="sxs-lookup"><span data-stu-id="3b914-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="3b914-107">Esta característica solo está disponible en la [versión 20H2 de Windows Holographic](hololens-release-notes.md#windows-holographic-version-20h2) o versiones posteriores para dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3b914-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="3b914-108">Asegúrese de que los dispositivos para los que tenga intención de usar la característica estén actualizados.</span><span class="sxs-lookup"><span data-stu-id="3b914-108">Please ensure devices you intend to use this for are updated.</span></span>

<span data-ttu-id="3b914-109">En el ejemplo siguiente se muestra una directiva que únicamente proporcionaría acceso a las páginas "Acerca de" y "Bluetooth", cuyos URI son "ms-settings:network-wifi" y "ms-settings:bluetooth", respectivamente:</span><span class="sxs-lookup"><span data-stu-id="3b914-109">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="3b914-110">Para definir esta directiva a través de un paquete de aprovisionamiento:</span><span class="sxs-lookup"><span data-stu-id="3b914-110">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="3b914-111">Al crear el paquete en el Diseñador de configuración de Windows, vaya a **Directivas > Configuración > PageVisibilityList**.</span><span class="sxs-lookup"><span data-stu-id="3b914-111">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="3b914-112">Escriba la siguiente cadena: **`showonly:network-wifi;network-proxy;bluetooth`** .</span><span class="sxs-lookup"><span data-stu-id="3b914-112">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="3b914-113">Exporte el paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="3b914-113">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="3b914-114">Aplique el paquete al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3b914-114">Apply the package to your device.</span></span>
<span data-ttu-id="3b914-115">Para obtener información completa sobre cómo crear y aplicar un paquete de aprovisionamiento, visite [esta página](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="3b914-115">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="3b914-116">Esta operación se puede realizar a través de Intune usando OMA-URI. Para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="3b914-116">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="3b914-117">Cree una **directiva personalizada**.</span><span class="sxs-lookup"><span data-stu-id="3b914-117">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="3b914-118">Al establecer el OMA-URI, use la siguiente cadena: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`** .</span><span class="sxs-lookup"><span data-stu-id="3b914-118">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="3b914-119">Al seleccionar los datos, elija **Cadena**.</span><span class="sxs-lookup"><span data-stu-id="3b914-119">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="3b914-120">Al escribir el valor, use lo siguiente: **`showonly:network-wifi;network-proxy;bluetooth`** .</span><span class="sxs-lookup"><span data-stu-id="3b914-120">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="3b914-121">Asegúrese de asignar la configuración de dispositivos personalizada a un grupo al que esté previsto que pertenezca el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3b914-121">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="3b914-122">Consulte [Configuración de MDM de HoloLens](hololens-mdm-configure.md) para obtener más información sobre los grupos y las configuraciones de dispositivos de Intune.</span><span class="sxs-lookup"><span data-stu-id="3b914-122">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="3b914-123">Independientemente del método elegido, su dispositivo ya debería recibir los cambios. Por su parte, los usuarios se encontrarán con la siguiente aplicación Configuración.</span><span class="sxs-lookup"><span data-stu-id="3b914-123">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Captura de pantalla de la modificación de las horas activas en la aplicación Configuración](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="3b914-125">Para configurar las páginas de la aplicación Configuración con el fin de mostrar u ocultar su propia selección de páginas, eche un vistazo a los URI de configuración disponibles en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3b914-125">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="3b914-126">URI de configuración</span><span class="sxs-lookup"><span data-stu-id="3b914-126">Settings URIs</span></span>

<span data-ttu-id="3b914-127">Los dispositivos HoloLens y Windows 10 tienen una selección de páginas diferente en la aplicación Configuración.</span><span class="sxs-lookup"><span data-stu-id="3b914-127">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="3b914-128">En esta página, solo encontrará la configuración de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3b914-128">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="3b914-129">Cuentas</span><span class="sxs-lookup"><span data-stu-id="3b914-129">Accounts</span></span>
| <span data-ttu-id="3b914-130">Página Configuración</span><span class="sxs-lookup"><span data-stu-id="3b914-130">Settings page</span></span>           | <span data-ttu-id="3b914-131">Identificador URI</span><span class="sxs-lookup"><span data-stu-id="3b914-131">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="3b914-132">Obtener acceso a trabajo o escuela</span><span class="sxs-lookup"><span data-stu-id="3b914-132">Access work or school</span></span> | `ms-settings:workplace`                         |
| <span data-ttu-id="3b914-133">Inscripción de iris</span><span class="sxs-lookup"><span data-stu-id="3b914-133">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="3b914-134">Opciones de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="3b914-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="3b914-135">Aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3b914-135">Apps</span></span>
| <span data-ttu-id="3b914-136">Página Configuración</span><span class="sxs-lookup"><span data-stu-id="3b914-136">Settings page</span></span> | <span data-ttu-id="3b914-137">Identificador URI</span><span class="sxs-lookup"><span data-stu-id="3b914-137">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="3b914-138">Aplicaciones y características<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-138">Apps & features<sup>2</sup></span></span>     | `ms-settings:appsfeatures` <br> |
| <span data-ttu-id="3b914-139">Aplicaciones y características > Opciones avanzadas <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-139">Apps & features > Advanced Options <sup>2</sup></span></span>     | `ms-settings::appsfeatures-app` <br> |
| <span data-ttu-id="3b914-140">Aplicaciones y características > Mapas sin conexión <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-140">Apps & features > Offline Maps <sup>2</sup></span></span>     | `ms-settings:maps-maps` <br> |
| <span data-ttu-id="3b914-141">Aplicaciones y características > Mapas sin conexión > Descargar mapas <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-141">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="3b914-142">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="3b914-142">Devices</span></span>
| <span data-ttu-id="3b914-143">Página Configuración</span><span class="sxs-lookup"><span data-stu-id="3b914-143">Settings page</span></span> | <span data-ttu-id="3b914-144">Identificador URI</span><span class="sxs-lookup"><span data-stu-id="3b914-144">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="3b914-145">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="3b914-145">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| <span data-ttu-id="3b914-146">Mouse <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-146">Mouse <sup>2</sup></span></span>      | `ms-settings:mouse` <br>  |
| <span data-ttu-id="3b914-147">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-147">USB <sup>2</sup></span></span>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="3b914-148">Privacidad</span><span class="sxs-lookup"><span data-stu-id="3b914-148">Privacy</span></span>
| <span data-ttu-id="3b914-149">Página Configuración</span><span class="sxs-lookup"><span data-stu-id="3b914-149">Settings page</span></span>            | <span data-ttu-id="3b914-150">Identificador URI</span><span class="sxs-lookup"><span data-stu-id="3b914-150">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="3b914-151">Información de cuenta</span><span class="sxs-lookup"><span data-stu-id="3b914-151">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="3b914-152">Diagnósticos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3b914-152">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="3b914-153">Aplicaciones en segundo plano</span><span class="sxs-lookup"><span data-stu-id="3b914-153">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="3b914-154">Calendario</span><span class="sxs-lookup"><span data-stu-id="3b914-154">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="3b914-155">Historial de llamadas</span><span class="sxs-lookup"><span data-stu-id="3b914-155">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="3b914-156">Cámara</span><span class="sxs-lookup"><span data-stu-id="3b914-156">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |
| <span data-ttu-id="3b914-157">Contactos</span><span class="sxs-lookup"><span data-stu-id="3b914-157">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="3b914-158">Comentarios y diagnósticos</span><span class="sxs-lookup"><span data-stu-id="3b914-158">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="3b914-159">Documentos</span><span class="sxs-lookup"><span data-stu-id="3b914-159">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="3b914-160">Correo electrónico</span><span class="sxs-lookup"><span data-stu-id="3b914-160">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="3b914-161">Sistema de archivos</span><span class="sxs-lookup"><span data-stu-id="3b914-161">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="3b914-162">General <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-162">General <sup>2</sup></span></span>             | `ms-settings:privacy-general`       |
| <span data-ttu-id="3b914-163">Personalización de entrada manuscrita y escritura <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-163">Ink & typing personalization <sup>2</sup></span></span>             | `ms-settings:privacy-speechtyping`       |
| <span data-ttu-id="3b914-164">Location</span><span class="sxs-lookup"><span data-stu-id="3b914-164">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="3b914-165">Mensajería</span><span class="sxs-lookup"><span data-stu-id="3b914-165">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="3b914-166">Micrófono</span><span class="sxs-lookup"><span data-stu-id="3b914-166">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="3b914-167">Movimiento <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-167">Motion <sup>2</sup></span></span>               | `ms-settings:privacy-motion`                  |
| <span data-ttu-id="3b914-168">Notificaciones</span><span class="sxs-lookup"><span data-stu-id="3b914-168">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="3b914-169">Otros dispositivos</span><span class="sxs-lookup"><span data-stu-id="3b914-169">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="3b914-170">Imágenes</span><span class="sxs-lookup"><span data-stu-id="3b914-170">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="3b914-171">Señales de radio</span><span class="sxs-lookup"><span data-stu-id="3b914-171">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="3b914-172">Bordes de capturas de pantalla <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-172">Screenshot borders <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="3b914-173">Capturas de pantalla y aplicaciones <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-173">Screenshots and apps <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="3b914-174">Voz</span><span class="sxs-lookup"><span data-stu-id="3b914-174">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="3b914-175">Tareas</span><span class="sxs-lookup"><span data-stu-id="3b914-175">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="3b914-176">Movimientos de usuario</span><span class="sxs-lookup"><span data-stu-id="3b914-176">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="3b914-177">Vídeos</span><span class="sxs-lookup"><span data-stu-id="3b914-177">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="3b914-178">Activación por voz</span><span class="sxs-lookup"><span data-stu-id="3b914-178">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="3b914-179">Red e Internet</span><span class="sxs-lookup"><span data-stu-id="3b914-179">Network & Internet</span></span>
| <span data-ttu-id="3b914-180">Página Configuración</span><span class="sxs-lookup"><span data-stu-id="3b914-180">Settings page</span></span> | <span data-ttu-id="3b914-181">Identificador URI</span><span class="sxs-lookup"><span data-stu-id="3b914-181">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="3b914-182">Modo avión <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-182">Airplane Mode <sup>2</sup></span></span> | `ms-settings:network-airplanemode`        |
| <span data-ttu-id="3b914-183">Proxy</span><span class="sxs-lookup"><span data-stu-id="3b914-183">Proxy</span></span> | `ms-settings:network-proxy`        |
| <span data-ttu-id="3b914-184">VPN</span><span class="sxs-lookup"><span data-stu-id="3b914-184">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="3b914-185">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="3b914-185">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="3b914-186">Sistema</span><span class="sxs-lookup"><span data-stu-id="3b914-186">System</span></span>
| <span data-ttu-id="3b914-187">Página Configuración</span><span class="sxs-lookup"><span data-stu-id="3b914-187">Settings page</span></span>      | <span data-ttu-id="3b914-188">Identificador URI</span><span class="sxs-lookup"><span data-stu-id="3b914-188">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="3b914-189">Batería <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-189">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver`<br>|
| <span data-ttu-id="3b914-190">Batería <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-190">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver-settings`<br>|
| <span data-ttu-id="3b914-191">Colores</span><span class="sxs-lookup"><span data-stu-id="3b914-191">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="3b914-192">Hologramas <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-192">Holograms <sup>2</sup></span></span>  |  `ms-settings:holograms`  |
| <span data-ttu-id="3b914-193">Calibración <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-193">Calibration <sup>2</sup></span></span> |  `ms-settings:calibration` |
| <span data-ttu-id="3b914-194">Notificaciones y acciones</span><span class="sxs-lookup"><span data-stu-id="3b914-194">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="3b914-195">Experiencias compartidas</span><span class="sxs-lookup"><span data-stu-id="3b914-195">Shared Experiences</span></span> | `ms-settings:crossdevice` 
| <span data-ttu-id="3b914-196">Sonido <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-196">Sound <sup>2</sup></span></span>           | `ms-settings:sound`<br>|
| <span data-ttu-id="3b914-197">Sonido > Volumen de aplicaciones y preferencia de dispositivos <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-197">Sound > App volume and device preference <sup>2</sup></span></span>           | `ms-settings:apps-volume`<br>|
| <span data-ttu-id="3b914-198">Sonido > Administrar dispositivos de sonido <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-198">Sound > Manage sound devices <sup>2</sup></span></span>           | `ms-settings:sound-devices`<br>|
| <span data-ttu-id="3b914-199">Storage</span><span class="sxs-lookup"><span data-stu-id="3b914-199">Storage</span></span>            | `ms-settings:storagesense`           |
| <span data-ttu-id="3b914-200">Almacenamiento > Configurar sensor de almacenamiento <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-200">Storage > Configure Storage Sense <sup>2</sup></span></span>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="3b914-201">Hora e idioma</span><span class="sxs-lookup"><span data-stu-id="3b914-201">Time & Language</span></span>
| <span data-ttu-id="3b914-202">Página Configuración</span><span class="sxs-lookup"><span data-stu-id="3b914-202">Settings page</span></span> | <span data-ttu-id="3b914-203">Identificador URI</span><span class="sxs-lookup"><span data-stu-id="3b914-203">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="3b914-204">Fecha y hora <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-204">Date & time <sup>2</sup></span></span> | `ms-settings:dateandtime`                  |
| <span data-ttu-id="3b914-205">Teclado <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-205">Keyboard <sup>2</sup></span></span> | `ms-settings:keyboard`                  |
| <span data-ttu-id="3b914-206">Idioma <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-206">Language <sup>2</sup></span></span> | `ms-settings:language`                  |
| <span data-ttu-id="3b914-207">Idioma <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-207">Language <sup>2</sup></span></span> | `ms-settings:regionlanguage-languageoptions`                  |
| <span data-ttu-id="3b914-208">Idioma</span><span class="sxs-lookup"><span data-stu-id="3b914-208">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="3b914-209">Region</span><span class="sxs-lookup"><span data-stu-id="3b914-209">Region</span></span>        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="3b914-210">Actualización y seguridad</span><span class="sxs-lookup"><span data-stu-id="3b914-210">Update & Security</span></span>
| <span data-ttu-id="3b914-211">Página Configuración</span><span class="sxs-lookup"><span data-stu-id="3b914-211">Settings page</span></span>                         | <span data-ttu-id="3b914-212">Identificador URI</span><span class="sxs-lookup"><span data-stu-id="3b914-212">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="3b914-213">Opciones avanzadas</span><span class="sxs-lookup"><span data-stu-id="3b914-213">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |
| <span data-ttu-id="3b914-214">Restablecimiento y recuperación <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3b914-214">Reset & Recovery <sup>2</sup></span></span>      | `ms-settings:reset`         |
| <span data-ttu-id="3b914-215">Programa Windows Insider</span><span class="sxs-lookup"><span data-stu-id="3b914-215">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="3b914-216">Windows Update</span><span class="sxs-lookup"><span data-stu-id="3b914-216">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><span data-ttu-id="3b914-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="3b914-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span></span><br><span data-ttu-id="3b914-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="3b914-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="3b914-219">Windows Update (búsqueda de actualizaciones)</span><span class="sxs-lookup"><span data-stu-id="3b914-219">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |


- <span data-ttu-id="3b914-220"><sup>1</sup> - En el caso de versiones de Windows Holographic anteriores a la 21H1, los dos URI siguientes no llevan realmente a las páginas **Opciones avanzadas** u **Opciones**; solo bloquearán o mostrarán la página principal de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="3b914-220"><sup>1</sup> - For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
  -  <span data-ttu-id="3b914-221">ms-settings:windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="3b914-221">ms-settings:windowsupdate-options</span></span>
  -  <span data-ttu-id="3b914-222">ms-settings:windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="3b914-222">ms-settings:windowsupdate-restartoptions</span></span>

- <span data-ttu-id="3b914-223"><sup>2</sup> - Disponible en Windows Holographic 21H1 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="3b914-223"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="3b914-224">Para obtener una lista completa de los URI de Configuración de Windows 10, consulte la documentación de la [configuración de inicio](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference).</span><span class="sxs-lookup"><span data-stu-id="3b914-224">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
