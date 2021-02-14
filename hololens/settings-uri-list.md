---
title: Visibilidad de la configuración de página
description: Manténgase al día con nuestra lista de URI compatibles para PageVisibilityList y guía en dispositivos Microsoft HoloLens de realidad mixta.
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
ms.openlocfilehash: f004f39f4b69748e8c36ad93111f4423d14c40f3
ms.sourcegitcommit: 23ee06b659d7a51f3000d386c8f67cbf212d5aa4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327394"
---
# <span data-ttu-id="a74df-104">Visibilidad de la configuración de página</span><span class="sxs-lookup"><span data-stu-id="a74df-104">Page Settings Visibility</span></span>

<span data-ttu-id="a74df-105">Una de las características que se puede administrar para los dispositivos HoloLens usa la Directiva [Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) para restringir las páginas que se muestran en la aplicación Configuración.</span><span class="sxs-lookup"><span data-stu-id="a74df-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="a74df-106">PageVisibilityList es una directiva mediante la cual los administradores de TI pueden evitar que páginas específicas de la aplicación Configuración del sistema sean visibles o accesibles, o bien pueden hacer lo sean en todas las páginas excepto en aquellas especificadas.</span><span class="sxs-lookup"><span data-stu-id="a74df-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="a74df-107">Esta característica está disponible solo en [Windows Holographic, versión 20H2](hololens-release-notes.md#windows-holographic-version-20h2) para dispositivos HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="a74df-107">This feature is only avalible in [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) for HoloLens 2 devices.</span></span> <span data-ttu-id="a74df-108">Asegúrese de que los dispositivos para los que deseas usar esta versión estén actualizados.</span><span class="sxs-lookup"><span data-stu-id="a74df-108">Please ensure devices you intend to use this for are updated.</span></span>

> [!NOTE]
> <span data-ttu-id="a74df-109">Pronto serán agregadas más de 20 SettingsURIs nuevas,</span><span class="sxs-lookup"><span data-stu-id="a74df-109">20+ new SettingsURIs are being added soon.</span></span> <span data-ttu-id="a74df-110">Consulte[ la página de Windows Insider: nuevas SettingsURIs para la visibilidad de la configuración de la página ](hololens-insider.md#new-settingsuris-for-page-settings-visibility) si está interesado en previsualizar esta configuración en una compilación de [ HoloLens Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="a74df-110">Please view [the Windows Insider page - New SettingsURIs for Page Settings Visibility](hololens-insider.md#new-settingsuris-for-page-settings-visibility) if you are interesting in previewing this setting on a [HoloLens Insider](hololens-insider.md) build.</span></span>

<span data-ttu-id="a74df-111">En el ejemplo siguiente, se muestra una directiva que permitiría el acceso solo a las páginas Acerca de y de Bluetooth, que tienen el URI "ms-settings:network-wifi" y "ms-settings:bluetooth", respectivamente:</span><span class="sxs-lookup"><span data-stu-id="a74df-111">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="a74df-112">Para establecer esto a través de un paquete de aprovisionamiento:</span><span class="sxs-lookup"><span data-stu-id="a74df-112">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="a74df-113">Al crear su paquete en el diseñador de configuración de Windows, desplácese hasta **Directivas > Configuración > PageVisibilityList**</span><span class="sxs-lookup"><span data-stu-id="a74df-113">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="a74df-114">Escriba la cadena: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="a74df-114">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="a74df-115">Exportar el paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="a74df-115">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="a74df-116">Aplicar el paquete a su dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a74df-116">Apply the package to your device.</span></span>
<span data-ttu-id="a74df-117">Para obtener detalles completos sobre cómo crear y aplicar un paquete de aprovisionamiento, e [esta página.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="a74df-117">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="a74df-118">Esto se puede hacer a través de Intune mediante OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="a74df-118">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="a74df-119">Crear una **Directiva personalizada**.</span><span class="sxs-lookup"><span data-stu-id="a74df-119">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="a74df-120">Al establecer el OMA-URI, use la cadena: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="a74df-120">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="a74df-121">Al seleccionar los datos, elija: **Cadena**</span><span class="sxs-lookup"><span data-stu-id="a74df-121">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="a74df-122">Al escribir el valor, use: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="a74df-122">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="a74df-123">Asegúrese de asignar la configuración del dispositivo personalizado a un grupo en el que el dispositivo esté previsto.</span><span class="sxs-lookup"><span data-stu-id="a74df-123">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="a74df-124">Consulte [la configuración de MDM de HoloLens](hololens-mdm-configure.md) para obtener más información sobre las configuraciones de dispositivos y grupos de Intune.</span><span class="sxs-lookup"><span data-stu-id="a74df-124">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="a74df-125">Independientemente del método elegido, su dispositivo debería recibir ahora los cambios y los usuarios se encontrarán con la siguiente aplicación de Configuración.</span><span class="sxs-lookup"><span data-stu-id="a74df-125">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Captura de pantalla de la modificación de las horas activas en la aplicación de Configuración](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="a74df-127">Para configurar las páginas de la aplicación Configuración para mostrar u ocultar su propia selección de páginas, eche un vistazo a las URI de configuración disponibles en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a74df-127">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <span data-ttu-id="a74df-128">URI de configuración</span><span class="sxs-lookup"><span data-stu-id="a74df-128">Settings URIs</span></span>

<span data-ttu-id="a74df-129">Los dispositivos HoloLens y Windows 10 tienen una selección de páginas diferente en la aplicación de Configuración.</span><span class="sxs-lookup"><span data-stu-id="a74df-129">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="a74df-130">En esta página, solo encontrarás la configuración que existe en HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a74df-130">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <span data-ttu-id="a74df-131">Cuentas</span><span class="sxs-lookup"><span data-stu-id="a74df-131">Accounts</span></span>
| <span data-ttu-id="a74df-132">Página de configuración</span><span class="sxs-lookup"><span data-stu-id="a74df-132">Settings page</span></span>           | <span data-ttu-id="a74df-133">URI</span><span class="sxs-lookup"><span data-stu-id="a74df-133">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="a74df-134">Opciones de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="a74df-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |
| <span data-ttu-id="a74df-135">Inscripción de Iris</span><span class="sxs-lookup"><span data-stu-id="a74df-135">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="a74df-136">Obtener acceso a trabajo o escuela</span><span class="sxs-lookup"><span data-stu-id="a74df-136">Access work or school</span></span> | `ms-settings:workplace`                         |

### <span data-ttu-id="a74df-137">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="a74df-137">Devices</span></span>
| <span data-ttu-id="a74df-138">Página de configuración</span><span class="sxs-lookup"><span data-stu-id="a74df-138">Settings page</span></span> | <span data-ttu-id="a74df-139">URI</span><span class="sxs-lookup"><span data-stu-id="a74df-139">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="a74df-140">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="a74df-140">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |

### <span data-ttu-id="a74df-141">Privacidad</span><span class="sxs-lookup"><span data-stu-id="a74df-141">Privacy</span></span>
| <span data-ttu-id="a74df-142">Página de configuración</span><span class="sxs-lookup"><span data-stu-id="a74df-142">Settings page</span></span>            | <span data-ttu-id="a74df-143">URI</span><span class="sxs-lookup"><span data-stu-id="a74df-143">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="a74df-144">Información de cuenta</span><span class="sxs-lookup"><span data-stu-id="a74df-144">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="a74df-145">Diagnóstico de la aplicación</span><span class="sxs-lookup"><span data-stu-id="a74df-145">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="a74df-146">Aplicaciones en segundo plano</span><span class="sxs-lookup"><span data-stu-id="a74df-146">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="a74df-147">Movimientos de usuario</span><span class="sxs-lookup"><span data-stu-id="a74df-147">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="a74df-148">Sistema de archivos</span><span class="sxs-lookup"><span data-stu-id="a74df-148">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="a74df-149">Calendario</span><span class="sxs-lookup"><span data-stu-id="a74df-149">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="a74df-150">Historial de llamadas</span><span class="sxs-lookup"><span data-stu-id="a74df-150">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="a74df-151">Contactos</span><span class="sxs-lookup"><span data-stu-id="a74df-151">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="a74df-152">Otros dispositivos</span><span class="sxs-lookup"><span data-stu-id="a74df-152">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="a74df-153">Documentos</span><span class="sxs-lookup"><span data-stu-id="a74df-153">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="a74df-154">Correo electrónico</span><span class="sxs-lookup"><span data-stu-id="a74df-154">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="a74df-155">Diagnósticos y comentarios</span><span class="sxs-lookup"><span data-stu-id="a74df-155">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="a74df-156">Ubicación</span><span class="sxs-lookup"><span data-stu-id="a74df-156">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="a74df-157">Mensajes</span><span class="sxs-lookup"><span data-stu-id="a74df-157">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="a74df-158">Micrófono</span><span class="sxs-lookup"><span data-stu-id="a74df-158">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="a74df-159">Notificaciones</span><span class="sxs-lookup"><span data-stu-id="a74df-159">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="a74df-160">Imágenes</span><span class="sxs-lookup"><span data-stu-id="a74df-160">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="a74df-161">Señales de radio</span><span class="sxs-lookup"><span data-stu-id="a74df-161">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="a74df-162">Voz</span><span class="sxs-lookup"><span data-stu-id="a74df-162">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="a74df-163">Tareas</span><span class="sxs-lookup"><span data-stu-id="a74df-163">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="a74df-164">Vídeos</span><span class="sxs-lookup"><span data-stu-id="a74df-164">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="a74df-165">Activación por voz</span><span class="sxs-lookup"><span data-stu-id="a74df-165">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |
| <span data-ttu-id="a74df-166">Cámara</span><span class="sxs-lookup"><span data-stu-id="a74df-166">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |

### <span data-ttu-id="a74df-167">Redes e Internet</span><span class="sxs-lookup"><span data-stu-id="a74df-167">Network & Internet</span></span>
| <span data-ttu-id="a74df-168">Página de configuración</span><span class="sxs-lookup"><span data-stu-id="a74df-168">Settings page</span></span> | <span data-ttu-id="a74df-169">URI</span><span class="sxs-lookup"><span data-stu-id="a74df-169">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="a74df-170">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="a74df-170">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |
| <span data-ttu-id="a74df-171">VPN</span><span class="sxs-lookup"><span data-stu-id="a74df-171">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="a74df-172">Proxy</span><span class="sxs-lookup"><span data-stu-id="a74df-172">Proxy</span></span> | `ms-settings:network-proxy`        |

### <span data-ttu-id="a74df-173">Sistema</span><span class="sxs-lookup"><span data-stu-id="a74df-173">System</span></span>
| <span data-ttu-id="a74df-174">Página de configuración</span><span class="sxs-lookup"><span data-stu-id="a74df-174">Settings page</span></span>      | <span data-ttu-id="a74df-175">URI</span><span class="sxs-lookup"><span data-stu-id="a74df-175">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="a74df-176">Experiencias compartidas</span><span class="sxs-lookup"><span data-stu-id="a74df-176">Shared Experiences</span></span> | `ms-settings:crossdevice`            |
| <span data-ttu-id="a74df-177">Colores</span><span class="sxs-lookup"><span data-stu-id="a74df-177">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="a74df-178">Notificaciones y acciones</span><span class="sxs-lookup"><span data-stu-id="a74df-178">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="a74df-179">Almacenamiento</span><span class="sxs-lookup"><span data-stu-id="a74df-179">Storage</span></span>            | `ms-settings:storagesense`           |

### <span data-ttu-id="a74df-180">Hora e idioma</span><span class="sxs-lookup"><span data-stu-id="a74df-180">Time & Language</span></span>
| <span data-ttu-id="a74df-181">Página de configuración</span><span class="sxs-lookup"><span data-stu-id="a74df-181">Settings page</span></span> | <span data-ttu-id="a74df-182">URI</span><span class="sxs-lookup"><span data-stu-id="a74df-182">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="a74df-183">Region</span><span class="sxs-lookup"><span data-stu-id="a74df-183">Region</span></span>        | `ms-settings:regionformatting`                  |
| <span data-ttu-id="a74df-184">Idioma</span><span class="sxs-lookup"><span data-stu-id="a74df-184">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |

### <span data-ttu-id="a74df-185">Actualización y seguridad</span><span class="sxs-lookup"><span data-stu-id="a74df-185">Update & Security</span></span>
| <span data-ttu-id="a74df-186">Página de configuración</span><span class="sxs-lookup"><span data-stu-id="a74df-186">Settings page</span></span>                         | <span data-ttu-id="a74df-187">URI</span><span class="sxs-lookup"><span data-stu-id="a74df-187">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="a74df-188">Programa Windows Insider</span><span class="sxs-lookup"><span data-stu-id="a74df-188">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="a74df-189">Windows Update</span><span class="sxs-lookup"><span data-stu-id="a74df-189">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup><span data-ttu-id="a74df-190">1</span><span class="sxs-lookup"><span data-stu-id="a74df-190">1</span></span></sup>`ms-settings:windowsupdate-options`<br><sup><span data-ttu-id="a74df-191">1</span><span class="sxs-lookup"><span data-stu-id="a74df-191">1</span></span></sup>`ms-settings:windowsupdate-restartoptions` |
| <span data-ttu-id="a74df-192">Windows Update: comprueba si hay actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="a74df-192">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |
| <span data-ttu-id="a74df-193">Opciones avanzadas</span><span class="sxs-lookup"><span data-stu-id="a74df-193">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |

>  <sup><span data-ttu-id="a74df-194">1</sup> Los dos URI siguientes no le llevan a las páginas de **Opciones avanzadas** u **Opciones**. Solo bloquearán o mostrarán la página principal de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="a74df-194">1</sup> The following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
> - <span data-ttu-id="a74df-195">ms-settings:windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="a74df-195">ms-settings:windowsupdate-options</span></span>
> - <span data-ttu-id="a74df-196">ms-settings:windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="a74df-196">ms-settings:windowsupdate-restartoptions</span></span> 

<span data-ttu-id="a74df-197">Para obtener una lista completa de uri de configuración de Windows 10, visita la documentación de [configuración de inicio](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference).</span><span class="sxs-lookup"><span data-stu-id="a74df-197">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
