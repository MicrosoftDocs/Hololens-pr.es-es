---
title: Configurar HoloLens (1.ª generación)
description: Esta guía explica la configuración por primera vez.  Necesitarás una red Wi-Fi y una cuenta de Microsoft (MSA) o de Azure Active Directory (Azure AD).
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 9a20a2ddd52c08a2b44dad452aac07ad9e69de85
ms.sourcegitcommit: 7edbb99e0972d3d857e5e87c062c3c64cacc1f41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2020
ms.locfileid: "10903236"
---
# Configurar HoloLens (1.ª generación)

La primera vez que enciendas tu HoloLens, te guiará por la calibración de tu dispositivo, configurando el dispositivo e iniciando sesión.  Este artículo te guía por la experiencia de primer inicio y configuración de HoloLens (1.ª generación).

En la siguiente sección, aprenderás a trabajar con HoloLens y a interactuar con hologramas. Para ir directamente a ese artículo, consulta [Introducción a HoloLens (1.ª generación)](hololens1-basic-usage.md).

## Antes de empezar

Antes de empezar, debes asegurarte de que cuentas con lo siguiente:

**Una conexión Wi-Fi**. Deberás conectar HoloLens a una red Wi-Fi para configurarlo. La primera vez que te conectes, necesitarás una red abierta o protegida por contraseña que no requiera ir a ningún sitio web ni usar certificados para conectarse. [Más información sobre los sitios web que HoloLens usa](hololens-offline.md).

**Una cuenta de Microsoft o una cuenta profesional**. También necesitarás usar una cuenta de Microsoft (o una cuenta profesional, si tu organización es propietaria del dispositivo) para iniciar sesión en HoloLens. Si no dispones de una cuenta de Microsoft, ve a [account.microsoft.com](https://account.microsoft.com) y crea una de manera gratuita.

**Un espacio seguro y bien iluminado, sin riesgo de tropezones**. [Información de salud y seguridad](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Los accesorios de comodidad opcionales** incluidos con tu HoloLens, que te ayudarán a obtener el ajuste más cómodo. [Más información sobre el ajuste y la comodidad](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).

> [!NOTE]
>  
> - La primera vez que uses tus HoloLens, [Cortana](hololens-cortana.md) ya está activada y lista para guiarte (aunque no podrá responder a tus preguntas hasta que hayas configurado el dispositivo). Puedes desactivar Cortana en cualquier momento, en la configuración de Cortana.
> - Para poder cambiar a la versión en chino o japonés de HoloLens, tendrás que descargar la compilación del idioma en un PC y, a continuación, instalarla en tu HoloLens. Para obtener más información, consulta [Instalar versiones localizadas de HoloLens (1.ª generación)](hololens1-install-localized.md).

## Iniciar Hololens y configurar Windows

La primera vez que inicias tu HoloLens, la primera tarea es configurar Windows Holographic en tu dispositivo.

1. Conéctate a Internet (HoloLens te guía para seleccionar una red Wi-Fi).

1. Inicia sesión con tu cuenta de usuario. Elige entre **Pertenece a mi trabajo o escuela** y **Es mía**.
    - Cuando eliges **Pertenece a mi trabajo o escuela**, inicia sesión con una cuenta de Azure AD. Si tu organización usa Azure AD Premium y ha configurado la inscripción automática de MDM, HoloLens se inscribe automáticamente en MDM. Si tu organización no usa Azure AD Premium, la inscripción automática de MDM no está disponible, por lo que tendrás que [inscribir HoloLens manualmente en la administración de dispositivos](hololens-enroll-mdm.md#different-ways-to-enroll). Para iniciar sesión en el dispositivo la primera vez con una cuenta profesional o educativa, sigue estos pasos:
        1. Escribe la información de la cuenta de la organización.
        1. Acepta la declaración de privacidad.
        1. Inicia sesión con tus credenciales de Azure AD. Esto puede redirigirte a la página de inicio de sesión de tu organización.
        1. Continúa configurando el dispositivo.
    - Cuando eliges **Es mía**, inicias sesión con una cuenta de Microsoft. Una vez completada la configuración, puedes [inscribir HoloLens manualmente en la administración de dispositivos](hololens-enroll-mdm.md#different-ways-to-enroll).
        1. Escribe la información de tu cuenta de Microsoft.
        1. Escribe tu contraseña. Si tu cuenta de Microsoft requiere una [comprobación de dos pasos (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/) (vínculo en inglés), completa el proceso de comprobación.

1. El dispositivo configura tu zona horaria en función de la información que obtienes de la red Wi-Fi.

## Calibración

Después de que Cortana se presenta, el siguiente paso de la configuración es la calibración. Para obtener la mejor experiencia de HoloLens, debes completar el proceso de calibración durante la instalación.

HoloLens (1.ª generación) usa la distancia entre las pupilas (IPD o la [distancia interpupilar](https://en.wikipedia.org/wiki/Interpupillary_distance)) para que los hologramas sean claros y resulte sencillo interactuar con ellos. Si la IPD no es correcta, es posible que los hologramas parezcan inestables o se encuentren a una distancia incorrecta.

Durante la calibración, HoloLens te pide que alinees el dedo con una serie de seis objetivos por ojo. HoloLens usa este proceso para establecer el valor de IPD correcto para los ojos. Si es necesario actualizar o ajustar la calibración para un nuevo usuario, el nuevo usuario puede ejecutar la aplicación Calibración fuera de la configuración.

![Pantalla de alineación de dedos de IPD en el segundo paso](./images/ipd-finger-alignment-300px.jpg)

*Pantalla de alineación de dedos de IPD en el segundo paso*

Enhorabuena. La configuración ha finalizado y puedes empezar a usar HoloLens.

## Pasos siguientes

> [!div class="nextstepaction"]
> [Introducción a HoloLens (1.ª generación)](hololens1-basic-usage.md)
