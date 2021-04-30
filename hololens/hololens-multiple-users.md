---
title: Uso compartido de HoloLens con varias personas
description: Puede configurar HoloLens para que lo compartan varias Azure Active Directory o varios usuarios que usen una sola cuenta.
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310175"
---
# <a name="share-your-hololens-with-multiple-people"></a><span data-ttu-id="5b8b8-103">Uso compartido de HoloLens con varias personas</span><span class="sxs-lookup"><span data-stu-id="5b8b8-103">Share your HoloLens with multiple people</span></span>

<span data-ttu-id="5b8b8-104">Es habitual compartir un dispositivo HoloLens con muchas personas o hacer que muchas personas compartan un conjunto de dispositivos HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-104">It's common to share one HoloLens with many people or to have many people share a set of HoloLens devices.</span></span>  <span data-ttu-id="5b8b8-105">En este artículo se describen las distintas formas de compartir un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-105">This article describes the different ways in which you can share a device.</span></span>

## <a name="share-with-multiple-people-each-using-their-own-account"></a><span data-ttu-id="5b8b8-106">Compartir con varias personas, cada una con su propia cuenta</span><span class="sxs-lookup"><span data-stu-id="5b8b8-106">Share with multiple people, each using their own account</span></span>

<span data-ttu-id="5b8b8-107">**Requisito** previo: el dispositivo HoloLens debe ejecutarse Windows 10, versión 1803 o posterior.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-107">**Prerequisite**: The HoloLens device must be running Windows 10, version 1803 or later.</span></span>  <span data-ttu-id="5b8b8-108">HoloLens (1.ª generación) también debe [actualizarse a Windows Holographic for Business](hololens-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="5b8b8-108">HoloLens (1st gen) also need to be [upgraded to Windows Holographic for Business](hololens-upgrade-enterprise.md).</span></span>

<span data-ttu-id="5b8b8-109">Cuando usan sus propias cuentas de Azure Active Directory (Azure AD), varios usuarios pueden mantener su propia configuración de usuario y sus propios datos de usuario en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-109">When they use their own Azure Active Directory (Azure AD) accounts, multiple users can each keep their own user settings and user data on the device.</span></span>

<span data-ttu-id="5b8b8-110">Para asegurarse de que varias personas pueden usar sus propias cuentas en HoloLens, siga estos pasos para configurarlo:</span><span class="sxs-lookup"><span data-stu-id="5b8b8-110">To make sure that multiple people can use their own accounts on your HoloLens, follow these steps to configure it:</span></span>

1. <span data-ttu-id="5b8b8-111">Asegúrese de que el dispositivo se ejecuta Windows 10 versión 1803 o posterior.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-111">Make sure the the device is running Windows 10, version 1803 or later.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="5b8b8-112">Si usa un dispositivo HoloLens (1.ª generación), [actualice el](hololens1-upgrade-enterprise.md)dispositivo a Windows Holographic for Business .</span><span class="sxs-lookup"><span data-stu-id="5b8b8-112">If you are using a HoloLens (1st gen) device, [upgrade the device to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>
1. <span data-ttu-id="5b8b8-113">Al configurar el dispositivo, seleccione **Mi** trabajo o escuela es el propietario e inicie sesión con una cuenta Azure AD trabajo.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-113">When you set up the device, select **My work or school owns it** and sign in by using an Azure AD account.</span></span>
1. <span data-ttu-id="5b8b8-114">Cuando termine la instalación, asegúrese de que la configuración de la cuenta **(Cuentas**  >  **de configuración**) incluye Otros **usuarios.**</span><span class="sxs-lookup"><span data-stu-id="5b8b8-114">After you finish setup, make sure that the account settings (**Settings** > **Accounts**) includes **Other users**.</span></span>

<span data-ttu-id="5b8b8-115">Para usar HoloLens, cada usuario sigue estos pasos:</span><span class="sxs-lookup"><span data-stu-id="5b8b8-115">To use HoloLens, each user follows these steps:</span></span>

1. <span data-ttu-id="5b8b8-116">Si otro usuario ha estado usando el dispositivo, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="5b8b8-116">If another user has been using the device, do one of the following:</span></span>
   - <span data-ttu-id="5b8b8-117">Presione el botón de encendido una vez para pasar al modo de espera y, a continuación, vuelva a presionar el botón de encendido para volver a la pantalla de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-117">Press the power button once to go to standby, and then press the power button again to return to the lock screen</span></span>
   - <span data-ttu-id="5b8b8-118">HoloLens 2 usuarios pueden seleccionar el icono de usuario en el menú Inicio cerrar la sesión del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-118">HoloLens 2 users may select the user tile from the Start menu to sign out the current user.</span></span>

1. <span data-ttu-id="5b8b8-119">Use sus Azure AD de cuenta para iniciar sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-119">Use your Azure AD account credentials to sign in to the device.</span></span>  
    <span data-ttu-id="5b8b8-120">Si es la primera vez que usa el [](hololens-calibration.md) dispositivo, tendrá que calibrar HoloLens con sus propios ojos.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-120">If this is the first time that you have used the device, you have to [calibrate](hololens-calibration.md) HoloLens to your own eyes.</span></span>

<span data-ttu-id="5b8b8-121">Para ver una lista de los usuarios del dispositivo o quitar un usuario del dispositivo, vaya a Configuración  >  **Cuentas Otros**  >  **usuarios.**</span><span class="sxs-lookup"><span data-stu-id="5b8b8-121">To see a list of the device users or to remove a user from the device, go to **Settings** > **Accounts** > **Other users**.</span></span>

## <a name="share-with-multiple-people-all-using-the-same-account"></a><span data-ttu-id="5b8b8-122">Compartir con varias personas, todas con la misma cuenta</span><span class="sxs-lookup"><span data-stu-id="5b8b8-122">Share with multiple people, all using the same account</span></span>

<span data-ttu-id="5b8b8-123">Varios usuarios también pueden compartir un dispositivo HoloLens mientras se usa una sola cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-123">Multiple users can also share a HoloLens device while using a single user account.</span></span>

<span data-ttu-id="5b8b8-124">**En HoloLens 2**, cuando un nuevo usuario coloca el dispositivo en la cabeza por primera vez (mientras mantiene la misma cuenta de inicio de sesión), el dispositivo solicita al nuevo usuario que calibra y personalice rápidamente la experiencia de visualización.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-124">**On HoloLens 2**, when a new user puts the device on their head for the first time (while keeping the same account signed in), the device prompts the new user to quickly calibrate and personalize the viewing experience.</span></span> <span data-ttu-id="5b8b8-125">El dispositivo puede almacenar la información de calibración para que, en el futuro, el dispositivo pueda optimizar automáticamente la calidad y la comodidad de la experiencia de visualización de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-125">The device can store the calibration information so that in the future, the device can automatically optimize the quality and comfort of each user's viewing experience.</span></span> <span data-ttu-id="5b8b8-126">Los usuarios no necesitan calibrar el dispositivo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-126">The users do not need to calibrate the device again.</span></span>

<span data-ttu-id="5b8b8-127">**En HoloLens (1.ª generación),** los usuarios que comparten una cuenta tendrán que solicitar que se vuelvan a crear en la aplicación Configuración.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-127">**On HoloLens (1st gen)** users sharing an account will need to ask to recalibrate in the Settings app.</span></span>  <span data-ttu-id="5b8b8-128">Obtenga más información sobre la [calibración](hololens-calibration.md).</span><span class="sxs-lookup"><span data-stu-id="5b8b8-128">Read more about [calibration](hololens-calibration.md).</span></span>
