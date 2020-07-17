---
title: Acceso asignado global
description: Guía para usar OMA-URI para quioscos de acceso asignado global
author: evmill
ms.author: v-evmill
ms.date: 7/13/2020
ms.topic: article
keywords: hololens, hololens 2, acceso asignado, quiosco
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: ad7f75ccfcae9fb42974abb43d87f2f1ce1571f8
ms.sourcegitcommit: 3db43bc4a007b10901d8edb045f66e1e299c57a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882452"
---
# <span data-ttu-id="a4df3-104">Acceso asignado global: quiosco</span><span class="sxs-lookup"><span data-stu-id="a4df3-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="a4df3-105">Esta característica configura el dispositivo Hololens 2 para varias aplicaciones en modo de pantalla completa que es aplicable a nivel del sistema, no tiene afinidad con ninguna identidad del sistema y se aplica a cualquier usuario que inicie sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a4df3-105">This feature configures Hololens 2 device for multiple app kiosk mode which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span> 

> [!NOTE]
> <span data-ttu-id="a4df3-106">Actualmente, esta característica solo está disponible en las compilaciones de Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="a4df3-106">This feature is currently only avalible in Windows Insider builds.</span></span> <span data-ttu-id="a4df3-107">Si desea probar esta característica antes de que esté disponible de forma generalizada en las versiones de HoloLens, obtenga más información sobre las compilaciones de [Windows Insider](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="a4df3-107">If you would like to try this feature before it is generally avalible in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>
 
## <span data-ttu-id="a4df3-108">¿Cómo usar esto en Intune?</span><span class="sxs-lookup"><span data-stu-id="a4df3-108">How to use this in Intune?</span></span> 

> [!NOTE]
> <span data-ttu-id="a4df3-109">Tenga en cuenta las áreas marcadas con "<!-".</span><span class="sxs-lookup"><span data-stu-id="a4df3-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="a4df3-110">Estas áreas requieren que realice modificaciones en función de sus preferencias.</span><span class="sxs-lookup"><span data-stu-id="a4df3-110">These areas will require you to make modifications based on your preferences.</span></span> 

1.  <span data-ttu-id="a4df3-111">Cree un perfil de configuración de dispositivo OMA URI personalizado como se indica a continuación y aplíquelo al grupo de dispositivos HoloLens: ![OMA-URI de acceso asignado global en Intune</span><span class="sxs-lookup"><span data-stu-id="a4df3-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group: ![Global Assigned Access OMA-URI in Intune</span></span>](images/global-assigned-access-omauri.png)

2.  <span data-ttu-id="a4df3-112">Para obtener un valor, actualice y pegue el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="a4df3-112">For value, update and paste following content:</span></span> 

    ```xml
    <?xml version="1.0" encoding="utf-8" ?> 
    <AssignedAccessConfiguration 
        xmlns="http://schemas.microsoft.com/AssignedAccess/2017/config" 
        xmlns:v2="http://schemas.microsoft.com/AssignedAccess/201810/config" 
        xmlns:v3="http://schemas.microsoft.com/AssignedAccess/2020/config" 
        xmlns:rs5="http://schemas.microsoft.com/AssignedAccess/201810/config" 
    > 
        <Profiles> 
            <Profile Id="{8739C257-184F-45DD-8657-C235819172A3}"> 
                <AllAppsList> 
                    <AllowedApps>                     
                        <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch=”true” /> --> 
                         <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.settingn_8wekyb3d8bbwe!MicrosoftEdge" /> --> 
                     </AllowedApps> 
                </AllAppsList> 
                <StartLayout> 
                    <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"> 
                          <LayoutOptions StartTileGroupCellWidth="6" /> 
                          <DefaultLayoutOverride> 
                            <StartLayoutCollection> 
                              <defaultlayout:StartLayout GroupCellWidth="6"> 
                                <start:Group Name="Life at a glance"> 
                                  <!—This AUMID can be of any app and is not used on Hololens but is required for parity, so you can leave it as is. --> 
                                  <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" />                               
                                </start:Group> 
                              </defaultlayout:StartLayout> 
                            </StartLayoutCollection> 
                          </DefaultLayoutOverride> 
                        </LayoutModificationTemplate> 
                    ]]> 
                </StartLayout> 
                <Taskbar ShowTaskbar="true"/> 
            </Profile> 
        </Profiles> 
        <Configs> 
            <v3:GlobalProfile Id="{8739C257-184F-45DD-8657-C235819172A3}"/> 
        </Configs> 
    </AssignedAccessConfiguration> 
    ```

## <span data-ttu-id="a4df3-113">¿Cómo usar esto en el diseñador de configuraciones de Windows?</span><span class="sxs-lookup"><span data-stu-id="a4df3-113">How to use this in Windows Configuration Designer?</span></span> 
 
1.  <span data-ttu-id="a4df3-114">Actualice y guarde el blob XML indicado anteriormente como archivo XML.</span><span class="sxs-lookup"><span data-stu-id="a4df3-114">Update and save XML blob mentioned above as XML file.</span></span> 

2.  <span data-ttu-id="a4df3-115">Siga los pasos que se indican en [Usar un paquete de aprovisionamiento para configurar un quiosco de aplicación única o de varias aplicaciones](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), en concreto en la sección "Paquete</span><span class="sxs-lookup"><span data-stu-id="a4df3-115">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="a4df3-116">de aprovisionamiento, paso 2: agregue el archivo XML de configuración de quiosco a un paquete de aprovisionamiento" y use el archivo XML que guardó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="a4df3-116">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span> 

## <span data-ttu-id="a4df3-117">¿Puedo crear una configuración en la que global se aplique a todos los usuarios excepto a 1 cuenta de AAD o grupo de AAD?</span><span class="sxs-lookup"><span data-stu-id="a4df3-117">Can I create a configuration where global applies to everyone except 1 AAD account or AAD group?</span></span> 

<span data-ttu-id="a4df3-118">Sí, consulte a continuación el blob XML de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a4df3-118">Yes, please refer to the example XML blob below.</span></span> <span data-ttu-id="a4df3-119">El perfil de acceso asignado global se aplica en Hololens cuando no se encuentra uno específico para el usuario que ha iniciado sesión, por lo que es la configuración predeterminada del modo de pantalla completa para el usuario que ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="a4df3-119">Global Assigned Access profile is applied on Hololens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span> <span data-ttu-id="a4df3-120">Este es un ejemplo de blob XML que se usará:</span><span class="sxs-lookup"><span data-stu-id="a4df3-120">Here is an example of XML blob to be used:</span></span> 

> [!NOTE]
> <span data-ttu-id="a4df3-121">Tenga en cuenta las áreas marcadas con <!-. Estas áreas requieren que realice modificaciones en función de sus preferencias.</span><span class="sxs-lookup"><span data-stu-id="a4df3-121">Please be aware of the areas marked with <!-  these areas will require you to make modifications based on your preferences.</span></span> 

```xml
<?xml version="1.0" encoding="utf-8" ?> 
<AssignedAccessConfiguration xmlns="http://schemas.microsoft.com/AssignedAccess/2017/config" 
    xmlns:v2="http://schemas.microsoft.com/AssignedAccess/201810/config" 
    xmlns:v3="http://schemas.microsoft.com/AssignedAccess/2020/config" 
    xmlns:rs5="http://schemas.microsoft.com/AssignedAccess/201810/config"> 
    <Profiles> 
        <Profile Id="{9A2A490F-10F6-4764-974A-43B19E722C23}"> 
            <!—specify AUMIDs and other nodes as used in example above --> 
        </Profile> 
        <Profile Id="{8739C257-184F-45DD-8657-C235819172A3}"> 
            <!—specify AUMIDs and other nodes as used in example above --> 
        </Profile> 
    </Profiles> 
    <Configs> 
        <v3:GlobalProfile Id="{8739C257-184F-45DD-8657-C235819172A3}"/> 
        <Config> 
           <Account>AzureAD\<!-fully qualified AAD account name></Account> 
           <DefaultProfile Id="{9A2A490F-10F6-4764-974A-43B19E722C23}"/> 
        </Config> 
    </Configs> 
</AssignedAccessConfiguration> 
```
