---
title: Configuración de HoloLens 2
description: Aprenda a configurar HoloLens 2 por primera vez través de una red Wi-Fi con una cuenta de Microsoft (MSA) o de Azure Active Directory (AAD).
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: ef2f8723868e14beaf19cb057fffbcbd9e9f51f9
ms.sourcegitcommit: 5130823947caffd2a444e9d8fb15cd24cbb6414c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2021
ms.locfileid: "114659355"
---
# <a name="set-up-your-hololens-2"></a>Configuración de HoloLens 2

La primera vez que encienda su HoloLens, se le guiará por la configuración del dispositivo, el inicio de sesión con una cuenta de usuario y la calibración de HoloLens a sus ojos.  En esta sección se explica la experiencia de configuración inicial de HoloLens 2.

En la siguiente sección aprenderá a trabajar con HoloLens y a interactuar con hologramas. Para ir directamente a ese artículo, consulte [Familiarización con HoloLens 2](hololens2-basic-usage.md).

## <a name="before-you-start"></a>Antes de empezar

Antes de empezar, debe asegurarse de que cuenta con lo siguiente:

**Una conexión de red**. Tendrá que conectar su HoloLens a una red para configurarlo. Con HoloLens 2, puede conectarse a una red Wi-Fi o a través de Ethernet (necesitará un adaptador USB-C a Ethernet). La primera vez que se conecte, necesitará una red abierta o protegida por contraseña que no requiera ir a ningún sitio web ni usar certificados para conectarse. [Obtenga más información sobre los sitios web que usa HoloLens](hololens-offline.md).

**Una cuenta de Microsoft**. También tendrá que iniciar sesión en HoloLens con una cuenta de Microsoft (o con la cuenta profesional, si el dispositivo es propiedad de su organización). Si no tiene una cuenta de Microsoft, vaya a [account.microsoft.com](https://account.microsoft.com) y configure una de forma gratuita.

**Un espacio seguro y bien iluminado sin peligro de accidentes**. [Información sobre la salud y la seguridad](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Los accesorios de confort opcionales** que se incluyen con el dispositivo HoloLens, para ayudarle a conseguir el ajuste más cómodo. [Más información sobre el ajuste y la comodidad](hololens2-setup.md#adjust-fit).

## <a name="set-up-windows"></a>Configurar Windows

La primera vez que inicie HoloLens 2, lo primero que hará será configurar Windows Holographic.  Cuando inicie el dispositivo HoloLens, oirá música y verá un logotipo de Microsoft.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGGGk]

<br/>
<img src="images/01-magic-moment.png" width="500px" alt="First screen during first boot">

Verá un colibrí volando por el entorno.

<img src="images/hummingbird-1.png" width="500px" alt="Hummingbird flying">

Seguirá su mano.

<img src="images/hummingbird-2.png" width="500px" alt="Hummingbird flying close up">

Aparecerá un botón con el logotipo de Microsoft. Presione el botón y HoloLens 2 le guiará por los siguientes pasos:

1. Seleccione el idioma.

    <img src="images/04-language.png" width="500px" alt="Select language">

1. Seleccione la región.

    <img src="images/05-region.png" width="500px" alt="Select region">

1. Calibre el dispositivo HoloLens a sus ojos.  Si decide omitir la calibración, se le pedirá la próxima vez que inicie sesión. 

    1. En primer lugar, ajustará el visor.
    
    <img src="images/06-et-corners.png" width="500px" alt="Calibration selection screen">
    
    2. Para calibrar, se le mostrarán un conjunto de objetivos (denominados gemas). No pasa nada si parpadea o cierra los ojos durante la calibración, pero intente no mirar otros objetos de la sala o del espacio físico. HoloLens usa este proceso para obtener información acerca de la posición del ojo para poder representar mejor su mundo holográfico. 

        <img src="images/07-adjust-eyes.png" width="500px" alt="Adjust for your eyes">

        Tras la calibración, los hologramas aparecerán correctamente incluso si el visor se desplaza por la cabeza. La información de calibración se almacena localmente en el dispositivo y no está asociada a ninguna información de la cuenta. Para obtener más información, consulte [Seguridad y datos de calibración](hololens-calibration.md#calibration-data-and-security).

        <img src="images/calibration-complete.png" width="500px" alt="Calibration is complete">

1. Conéctese a Internet (seleccione Wi-Fi o la conexión Ethernet).

     El dispositivo HoloLens establece la zona horaria automáticamente en función de la información obtenida de la red Wi-Fi. Una vez finalizada la instalación, puede cambiar la zona horaria con la aplicación Configuración.

    ![Conexión a Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > Si avanza más allá del paso de Wi-Fi y más tarde necesita cambiar a una red diferente mientras está todavía en el proceso de configuración, puede presionar a la vez los botones de **bajar volumen** y **encendido** para volver a este paso, si ejecuta una versión de sistema operativo de octubre de 2019 o posterior. En versiones anteriores, es posible que debe [restablecer el dispositivo](hololens-recovery.md) o reiniciarlo en una ubicación en la que la red Wi-Fi no esté disponible para impedir que se conecte a ella automáticamente.
    > 
    > Tenga en cuenta también que durante la configuración de HoloLens, hay un tiempo de espera por las credenciales de dos minutos. El nombre de usuario y la contraseña se deben escribir en un intervalo de dos minutos; de lo contrario, el campo de nombre de usuario se borrará automáticamente.

1. HoloLens 2 buscará y aplicará un perfil de Autopilot si existe. No se necesita ninguna acción en esta pantalla.
 
    ![Búsqueda del perfil de Autopilot](images/autopilot-profile-search.png) 

1. Haga clic en **Aceptar** en la pantalla de licencias.

    ![Contrato de licencia de Windows](images/windows-license-agreement.png)

1. Inicie sesión con su cuenta de usuario. Deberá elegir entre **Es propiedad de mi trabajo o escuela** y **Es mío**.

    ![Establecimiento del usuario](images/13-device-owner.png)
    - Si eliges **Es propiedad de mi trabajo o escuela**, iniciarás sesión con una cuenta de Azure AD. Si su organización usa Azure AD Premium y ha configurado la inscripción automática de MDM, HoloLens se inscribe automáticamente en MDM. Si la organización no usa Azure AD Premium, la inscripción automática de MDM no está disponible. En ese caso, debe [inscribir manualmente el dispositivo HoloLens en la administración de dispositivos](hololens-enroll-mdm.md#different-ways-to-enroll).

        1. Escriba la información de la cuenta de la organización.
        1. Acepte la declaración de privacidad y el contrato de licencia para el usuario final.
        1. Inicie sesión con sus credenciales de Azure AD. Esto puede redirigirte a la página de inicio de sesión de tu organización.
        1. Continúe configurando el dispositivo.

    - Si eliges **Es mía**, iniciarás sesión con una cuenta de Microsoft. Una vez completada la configuración, puede [inscribir el dispositivo HoloLens en la administración de dispositivos manualmente](hololens-enroll-mdm.md#different-ways-to-enroll).

        1. Escriba la información de su cuenta de Microsoft.
        2. Especifique la contraseña. Si tu cuenta de Microsoft requiere una [comprobación de dos pasos (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/) (vínculo en inglés), completa el proceso de comprobación.

        
1. Configure el inicio de sesión de Iris: para ello, seleccione **Siguiente**. Pasará por una experiencia similar a la de calibración de los ojos. Seleccione **Listo** cuando se complete el escaneo. También puede seleccionar **Omitir** para saltar este paso.
    
    <img src="images/setup-iris.png" width="500px" alt="Iris setup">

    <img src="images/iris-setup-complete.png" width="500px" alt="Iris setup completion">

     
  
1. Configurará un PIN para iniciar sesión en el dispositivo. Este PIN es específico del dispositivo. 

    ![Configuración de Windows Hello](images/setup-windows-hello.png)

    ![Configuración de PIN de Windows Hello](images/windows-hello-pin.png)

    ![Configuración de Windows Hello correcta](images/windows-hello-successful.png) 

    
1. Seleccione si desea habilitar la voz en HoloLens 2.

    <img src="images/22-do-more-with-voice.png" width="500px" alt="Enable Cortana">

1. Seleccione si desea habilitar la ubicación en HoloLens 2.
    
    <img src="images/setup-location-services.png" width="500px" alt="Enable location services">

1. Seleccione el nivel de telemetría. Si es posible, habilite la telemetría opcional. Esta información es de gran ayuda para el equipo de ingeniería de HoloLens.

    <img src="images/24-telemetry.png" width="500px" alt="Telemetry level">


1. Aprenda a usar el gesto Inicio en HoloLens 2.

    <img src="images/26-01-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 1">

    <img src="images/26-02-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 2">
    
    > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3Wxng]
    
    Enhorabuena.  La configuración se ha completado y ya puede usar el dispositivo HoloLens.

## <a name="next-steps"></a>Pasos siguientes

1. Empiece a interactuar inmediatamente con Mixed Reality y a explorar Windows 10 en su HoloLens: eche un vistazo a la aplicación **Recomendaciones** para ver tutoriales prácticos sobre cómo interactuar con las manos. Use el gesto Inicio para ir a Inicio o diga "Ir a Inicio" y seleccione "Recomendaciones".

1. Haga clic a continuación para seguir leyendo sobre cómo usar HoloLens 2.

> [!div class="nextstepaction"]
> [Familiarización con HoloLens 2](hololens2-basic-usage.md)
