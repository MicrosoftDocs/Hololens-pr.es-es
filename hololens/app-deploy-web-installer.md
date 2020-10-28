---
title: Cómo instalar aplicaciones a través de web Installer
description: Instalar aplicaciones a través de web Installer para el instalador de aplicaciones
keywords: App Management, App, hololens, instalador de aplicaciones, instalación Web
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 9/17/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 186cbefb2822455dcf922804ea09533b833b8663
ms.sourcegitcommit: a3e53f0e5070d0538f3ed74259914c59413eafd0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135453"
---
# <span data-ttu-id="07a3d-104">Instalar aplicaciones desde una página web</span><span class="sxs-lookup"><span data-stu-id="07a3d-104">Installing apps from a web page</span></span>

<span data-ttu-id="07a3d-105">Los usuarios pueden instalar una aplicación directamente desde un servidor Web.</span><span class="sxs-lookup"><span data-stu-id="07a3d-105">Users can install an app directly from a web server.</span></span> <span data-ttu-id="07a3d-106">Esto usa el instalador de aplicaciones combinado con un método de distribución de instalación fácil de descargar e instalar.</span><span class="sxs-lookup"><span data-stu-id="07a3d-106">This takes use of the App Installer combined with an easy download and install distribution method.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="07a3d-107">Actualmente, esta característica solo avalible en Windows Insider compila 19041.1366 +.</span><span class="sxs-lookup"><span data-stu-id="07a3d-107">This feature is currently only avalible in Windows Insider builds 19041.1366+.</span></span> <span data-ttu-id="07a3d-108">[Obtenga más información sobre cómo inscribirse en compilaciones de Windows Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="07a3d-108">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

## <span data-ttu-id="07a3d-109">Cómo configurar esto:</span><span class="sxs-lookup"><span data-stu-id="07a3d-109">How to set this up:</span></span>
1.  <span data-ttu-id="07a3d-110">Asegúrate de que la aplicación esté correctamente configurada para instalarse.</span><span class="sxs-lookup"><span data-stu-id="07a3d-110">Ensure your app is correctly configured to install.</span></span>
1.  <span data-ttu-id="07a3d-111">Siga estos [pasos para habilitar esta opción en una página web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span><span class="sxs-lookup"><span data-stu-id="07a3d-111">Follow these [steps to enable this on a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span> 
1.  <span data-ttu-id="07a3d-112">Elija un método de implementación de certificados.</span><span class="sxs-lookup"><span data-stu-id="07a3d-112">Pick a certificate deployment method.</span></span> 
    1.  <span data-ttu-id="07a3d-113">Los [paquetes de aprovisionamiento](hololens-provisioning.md) pueden aplicarse a dispositivos locales.</span><span class="sxs-lookup"><span data-stu-id="07a3d-113">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
    1.  <span data-ttu-id="07a3d-114">MDM se puede usar para [aplicar certificados con configuraciones de dispositivos](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span><span class="sxs-lookup"><span data-stu-id="07a3d-114">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
    1.  <span data-ttu-id="07a3d-115">Use el en el [Administrador de certificados](hololens-insider.md#certificate-manager)de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="07a3d-115">Use the on device [Certificate Manager](hololens-insider.md#certificate-manager).</span></span> 

## <span data-ttu-id="07a3d-116">Experiencia de usuario final:</span><span class="sxs-lookup"><span data-stu-id="07a3d-116">End User Experience:</span></span>
1.  <span data-ttu-id="07a3d-117">El usuario recibe e instala el certificado en el dispositivo con un método previamente seleccionado.</span><span class="sxs-lookup"><span data-stu-id="07a3d-117">User receives and installs certificate to the device using a method previously chosen above.</span></span> 
1.  <span data-ttu-id="07a3d-118">El usuario visita la dirección URL creada a partir del paso anterior.</span><span class="sxs-lookup"><span data-stu-id="07a3d-118">User visits the URL created from the step above.</span></span>

<span data-ttu-id="07a3d-119">La aplicación se instalará en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="07a3d-119">The app will now install to the device.</span></span> <span data-ttu-id="07a3d-120">Para buscar la aplicación, abre el **menú Inicio** y selecciona el botón **todas las aplicaciones** para encontrar tu aplicación.</span><span class="sxs-lookup"><span data-stu-id="07a3d-120">To find the app open the **Start menu** and select the **All apps** button to find your app.</span></span> 

-   <span data-ttu-id="07a3d-121">Para obtener ayuda con la solución de problemas de este método de instalación, visite [solucionar problemas del instalador](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="07a3d-121">For help troubleshooting this installation method please visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span> 

> [!NOTE]
> <span data-ttu-id="07a3d-122">No se admite la interfaz de usuario durante el proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="07a3d-122">UI during the update process is not supported.</span></span> <span data-ttu-id="07a3d-123">Por lo tanto, no se admite la opción ShowPrompt de [esta página](https://docs.microsoft.com/windows/msix/app-installer/update-settings) ni las opciones relacionadas.</span><span class="sxs-lookup"><span data-stu-id="07a3d-123">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>
