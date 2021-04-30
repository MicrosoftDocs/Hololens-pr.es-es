---
title: Configuración de HoloLens (1ª generación)
description: Aprenda a configurar HoloLens (1ª generación) por primera vez en una red Wi-Fi con una cuenta de Microsoft (MSA) o Azure Active Directory (AAD).
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f0ec62e55f15fda6d5a8304ea2bb77039d644b9e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310129"
---
# <a name="set-up-your-hololens-1st-gen"></a>Configuración de HoloLens (1ª generación)

La primera vez que actives HoloLens, se te guiará a través de la calibración del dispositivo, la configuración del dispositivo y el inicio de sesión.  Este artículo le guía por la primera experiencia de inicio y configuración de HoloLens (1.ª generación).

En la sección siguiente, aprenderá a trabajar con HoloLens e interactuar con hologramas. Para ir directamente a ese artículo, consulte [Introducción a HoloLens (1.ª generación).](hololens1-basic-usage.md)

## <a name="before-you-start"></a>Antes de comenzar

Antes de empezar, asegúrese de que tiene lo siguiente disponible:

**Una Wi-Fi de conexión**. Deberá conectar HoloLens a una red Wi-Fi para configurarlo. La primera vez que se conecte, necesitará una red abierta o protegida con contraseña que no requiera navegar a un sitio web o usar certificados para conectarse. [Obtenga más información sobre los sitios web que HoloLens usa](hololens-offline.md).

**Una cuenta Microsoft o una cuenta de trabajo**. También deberá usar una cuenta Microsoft (o una cuenta de trabajo, si su organización posee el dispositivo) para iniciar sesión en HoloLens. Si no tiene una cuenta Microsoft, vaya a account.microsoft.com [y](https://account.microsoft.com) configure una de forma gratuita.

Un espacio seguro y bien encendido sin riesgos **de carreras.** [Información de seguridad y estado](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Los accesorios de confort opcionales** que se incluyeron con HoloLens, para ayudarle a obtener el ajuste más cómodo. [Más información sobre ajuste y comodidad.](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)

> [!NOTE]
>  
> - La primera vez que usas HoloLens, [Cortana](hololens-cortana.md) ya está activa y lista para guiarte (aunque no podrá responder a tus preguntas hasta después de configurar el dispositivo). Puede desactivar Cortana en cualquier momento en la configuración de Cortana.
> - Para cambiar a la versión en chino o japonés de HoloLens, deberá descargar la compilación del idioma en un equipo y, a continuación, instalarla en holoLens. Para más información, consulte [Instalación de versiones localizadas de HoloLens (1.ª generación).](hololens1-install-localized.md)

## <a name="start-your-hololens-and-set-up-windows"></a>Inicio de Hololens y configuración de Windows

La primera vez que inicie HoloLens, la primera tarea consiste en configurar Windows Holographic en el dispositivo.

1. Conéctese a Internet (HoloLens le guía para seleccionar Wi-Fi red).

1. Inicie sesión en su cuenta de usuario. Elija entre **Mi trabajo o escuela es el** propietario y el propietario es **.**
    - Cuando elige Mi trabajo o escuela es el **propietario,** inicia sesión con una cuenta Azure AD trabajo. Si su organización usa Azure AD Premium ha configurado la inscripción automática de MDM, HoloLens se inscribe automáticamente en MDM. Si su organización no usa Azure AD Premium, la inscripción automática de MDM no está disponible, por lo que deberá inscribir manualmente HoloLens en la administración [de dispositivos.](hololens-enroll-mdm.md#different-ways-to-enroll) Para iniciar sesión en el dispositivo la primera vez mediante una cuenta de trabajo o educativa, siga estos pasos:
        1. Escriba la información de la cuenta de la organización.
        1. Acepte la declaración de privacidad.
        1. Inicie sesión con sus Azure AD credenciales. Esto puede redirigirte a la página de inicio de sesión de tu organización.
        1. Siga configurando el dispositivo.
    - Al elegir **Soy el propietario,** inicia sesión con una cuenta Microsoft. Una vez completada la instalación, puede [inscribir manualmente HoloLens en la administración de dispositivos.](hololens-enroll-mdm.md#different-ways-to-enroll)
        1. Escriba la información de la cuenta Microsoft.
        1. Especifique la contraseña. Si tu cuenta de Microsoft requiere una [comprobación de dos pasos (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/) (vínculo en inglés), completa el proceso de comprobación.

1. El dispositivo establece la zona horaria en función de la información que obtiene de Wi-Fi red.

## <a name="calibration"></a>Calibración

Después de que Cortana se presente, el siguiente paso de configuración es la calibración. Para obtener la mejor experiencia de HoloLens, debe completar el proceso de calibración durante la instalación.

HoloLens (1.ª generación) usa la distancia entre las alumnos (IPD o [distancia interpupillaria)](https://en.wikipedia.org/wiki/Interpupillary_distance)para que los hologramas se borren y interactúen fácilmente. Si el IPD no es correcto, los hologramas pueden parecer inestables o a una distancia incorrecta.

Durante la calibración, HoloLens le pide que alinee el dedo con una serie de seis destinos por ojo. HoloLens usa este proceso para establecer el IPD correcto para los ojos. Si la calibración debe actualizarse o ajustarse para un nuevo usuario, el nuevo usuario puede ejecutar la aplicación calibración fuera de la configuración.

![Pantalla de alineación de los dedos de IPD en el segundo paso](./images/ipd-finger-alignment-300px.jpg)

*Pantalla de alineación de los dedos de IPD en el segundo paso*

¡Enhorabuena! La instalación se ha completado y puede empezar a usar HoloLens.

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Introducción a HoloLens (1ª generación)](hololens1-basic-usage.md)
