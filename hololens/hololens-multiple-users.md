---
title: Compartir HoloLens con varias personas
description: Puede configurar HoloLens para que lo compartan varias cuentas de Azure Active Directory o por varios usuarios que usen una sola cuenta.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829609"
---
# <span data-ttu-id="8ef29-103">Compartir HoloLens con varias personas</span><span class="sxs-lookup"><span data-stu-id="8ef29-103">Share your HoloLens with multiple people</span></span>

<span data-ttu-id="8ef29-104">Es común compartir un HoloLens con muchas personas o que muchas personas compartan un conjunto de dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8ef29-104">It's common to share one HoloLens with many people or to have many people share a set of HoloLens devices.</span></span>  <span data-ttu-id="8ef29-105">En este artículo se describen las diferentes maneras en las que puede compartir un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8ef29-105">This article describes the different ways in which you can share a device.</span></span>

## <span data-ttu-id="8ef29-106">Compartir con varias personas, cada una usando su propia cuenta</span><span class="sxs-lookup"><span data-stu-id="8ef29-106">Share with multiple people, each using their own account</span></span>

<span data-ttu-id="8ef29-107">**Requisito previo**: el dispositivo HoloLens debe ejecutar Windows 10, versión 1803 o posterior.</span><span class="sxs-lookup"><span data-stu-id="8ef29-107">**Prerequisite**: The HoloLens device must be running Windows 10, version 1803 or later.</span></span>  <span data-ttu-id="8ef29-108">Además, es necesario actualizar HoloLens (1ª generación) [a Windows Holographic para empresas](hololens-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="8ef29-108">HoloLens (1st gen) also need to be [upgraded to Windows Holographic for Business](hololens-upgrade-enterprise.md).</span></span>

<span data-ttu-id="8ef29-109">Cuando usan sus propias cuentas de Azure Active Directory (Azure AD), varios usuarios pueden mantener su propia configuración de usuario y datos de usuario en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8ef29-109">When they use their own Azure Active Directory (Azure AD) accounts, multiple users can each keep their own user settings and user data on the device.</span></span>

<span data-ttu-id="8ef29-110">Para asegurarse de que varias personas puedan usar sus propias cuentas en HoloLens, siga estos pasos para configurarlo:</span><span class="sxs-lookup"><span data-stu-id="8ef29-110">To make sure that multiple people can use their own accounts on your HoloLens, follow these steps to configure it:</span></span>

1. <span data-ttu-id="8ef29-111">Asegúrese de que el dispositivo ejecuta Windows 10, versión 1803 o posterior.</span><span class="sxs-lookup"><span data-stu-id="8ef29-111">Make sure the the device is running Windows 10, version 1803 or later.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="8ef29-112">Si está usando un dispositivo HoloLens (1ª generación), [actualice el dispositivo a Windows Holographic para empresas](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="8ef29-112">If you are using a HoloLens (1st gen) device, [upgrade the device to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>
1. <span data-ttu-id="8ef29-113">Cuando configure el dispositivo, seleccione **mi trabajo o escuela propietario** e inicie sesión con una cuenta de Azure ad.</span><span class="sxs-lookup"><span data-stu-id="8ef29-113">When you set up the device, select **My work or school owns it** and sign in by using an Azure AD account.</span></span>
1. <span data-ttu-id="8ef29-114">Una vez finalizada la instalación, asegúrese de que la configuración de la cuenta (cuentas de**configuración**  >  **Accounts**) incluye **otros usuarios**.</span><span class="sxs-lookup"><span data-stu-id="8ef29-114">After you finish setup, make sure that the account settings (**Settings** > **Accounts**) includes **Other users**.</span></span>

<span data-ttu-id="8ef29-115">Para usar HoloLens, cada usuario sigue estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8ef29-115">To use HoloLens, each user follows these steps:</span></span>

1. <span data-ttu-id="8ef29-116">Si otro usuario ha estado usando el dispositivo, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="8ef29-116">If another user has been using the device, do one of the following:</span></span>
   - <span data-ttu-id="8ef29-117">Presione el botón de encendido una vez para ir a standby y, a continuación, presione el botón de encendido de nuevo para volver a la pantalla de bloqueo</span><span class="sxs-lookup"><span data-stu-id="8ef29-117">Press the power button once to go to standby, and then press the power button again to return to the lock screen</span></span>
   - <span data-ttu-id="8ef29-118">Los usuarios de HoloLens 2 pueden seleccionar el icono de usuario desde el menú Inicio para cerrar la sesión del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="8ef29-118">HoloLens 2 users may select the user tile from the Start menu to sign out the current user.</span></span>

1. <span data-ttu-id="8ef29-119">Usa las credenciales de tu cuenta de Azure AD para iniciar sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8ef29-119">Use your Azure AD account credentials to sign in to the device.</span></span>  
    <span data-ttu-id="8ef29-120">Si esta es la primera vez que usas el dispositivo, debes [calibrar](hololens-calibration.md) HoloLens a tus ojos.</span><span class="sxs-lookup"><span data-stu-id="8ef29-120">If this is the first time that you have used the device, you have to [calibrate](hololens-calibration.md) HoloLens to your own eyes.</span></span>

<span data-ttu-id="8ef29-121">Para ver una lista de los usuarios del dispositivo o para quitar un usuario del dispositivo, vaya a **configuración**  >  **cuentas**  >  **otros usuarios**.</span><span class="sxs-lookup"><span data-stu-id="8ef29-121">To see a list of the device users or to remove a user from the device, go to **Settings** > **Accounts** > **Other users**.</span></span>

## <span data-ttu-id="8ef29-122">Compartir con varias personas, todas usando la misma cuenta</span><span class="sxs-lookup"><span data-stu-id="8ef29-122">Share with multiple people, all using the same account</span></span>

<span data-ttu-id="8ef29-123">Varios usuarios también pueden compartir un dispositivo HoloLens al usar una sola cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="8ef29-123">Multiple users can also share a HoloLens device while using a single user account.</span></span>

<span data-ttu-id="8ef29-124">**En HoloLens 2**, cuando un nuevo usuario coloca el dispositivo en su cabeza por primera vez (manteniendo la misma cuenta iniciada), el dispositivo pide al nuevo usuario que calibre rápidamente y personalice la experiencia de visualización.</span><span class="sxs-lookup"><span data-stu-id="8ef29-124">**On HoloLens 2**, when a new user puts the device on their head for the first time (while keeping the same account signed in), the device prompts the new user to quickly calibrate and personalize the viewing experience.</span></span> <span data-ttu-id="8ef29-125">El dispositivo puede almacenar la información de calibración para que, en el futuro, el dispositivo pueda optimizar automáticamente la calidad y comodidad de la experiencia de visualización de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="8ef29-125">The device can store the calibration information so that in the future, the device can automatically optimize the quality and comfort of each user's viewing experience.</span></span> <span data-ttu-id="8ef29-126">Los usuarios no tienen que calibrar el dispositivo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="8ef29-126">The users do not need to calibrate the device again.</span></span>

<span data-ttu-id="8ef29-127">**En HoloLens (1ª generación)** , los usuarios que compartan una cuenta necesitarán solicitar la recalibra en la aplicación configuración.</span><span class="sxs-lookup"><span data-stu-id="8ef29-127">**On HoloLens (1st gen)** users sharing an account will need to ask to recalibrate in the Settings app.</span></span>  <span data-ttu-id="8ef29-128">Más información sobre la [calibración](hololens-calibration.md).</span><span class="sxs-lookup"><span data-stu-id="8ef29-128">Read more about [calibration](hololens-calibration.md).</span></span>
