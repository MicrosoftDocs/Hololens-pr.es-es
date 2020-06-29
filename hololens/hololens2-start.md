---
title: Configurar tu HoloLens 2
description: Esta guía explica la configuración por primera vez.  Necesitarás una red Wi-Fi y una cuenta de Microsoft (MSA) o de Azure Active Directory (AAD).
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 9/17/2019
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 8c3d9a10533432b3e8489ffa297c16061abb9eaf
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828975"
---
# Configurar tu HoloLens 2

La primera vez que enciendas HoloLens, se te guiará a través de la configuración del dispositivo, iniciando sesión con una cuenta de usuario y calibrando HoloLens a tus ojos.  En esta sección explica la experiencia de configuración inicial de HoloLens 2.

En la siguiente sección, aprenderás a trabajar con HoloLens y a interactuar con hologramas. Para ir directamente a ese artículo, consulta [Introducción a HoloLens 2](hololens2-basic-usage.md).

## Antes de empezar

Antes de empezar, debes asegurarte de que cuentas con lo siguiente:

**Una conexión de red**. Tendrás que conectar tu HoloLens a una red para configurarlo. Con HoloLens 2, puedes conectarte a una red Wi-Fi o a través de Ethernet (necesitarás un adaptador USB-C a Ethernet). La primera vez que te conectes, necesitarás una red abierta o protegida por contraseña que no requiera ir a ningún sitio web ni usar certificados para conectarse. [Más información sobre los sitios web que HoloLens usa](hololens-offline.md).

**Una cuenta de Microsoft**. También tendrás que iniciar sesión en HoloLens con una cuenta de Microsoft (o con tu cuenta profesional, si el dispositivo es propiedad de tu organización). Si no dispones de una cuenta de Microsoft, ve a [account.microsoft.com](https://account.microsoft.com) y crea una de manera gratuita.

**Un espacio seguro y bien iluminado, sin riesgo de tropezones**. [Información de salud y seguridad](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Los accesorios de comodidad opcionales** incluidos con tu HoloLens, que te ayudarán a obtener el ajuste más cómodo. [Más información sobre el ajuste y la comodidad](hololens2-setup.md#adjust-fit).

## Configurar Windows

La primera vez que inicies HoloLens 2, la primera tarea es configurar Windows Holographic.  Cuando inicies HoloLens, oirás música y verás un logotipo de Windows.

![Primera pantalla durante el primer arranque](images/01-magic-moment.png)

HoloLens 2 te guiará por los siguientes pasos:

1. Elige tu idioma.
    ![Seleccionar idioma](images/04-language.png)

1. Elige tu región.
    ![Seleccionar región](images/05-region.png)

1. Calibra HoloLens a tus ojos.  Si optas por omitir la calibración, se te pedirá la próxima vez que inicies sesión.

    Para calibrar, veremos un conjunto de objetivos (denominados gemas). Está bien si parpadeas o cierras los ojos durante la calibración, pero intenta no mirar a otros objetos de la sala o del espacio físico. HoloLens usa este proceso para obtener información acerca de la posición de tu ojo para que pueda representar mejor tu mundo holográfico. Tras la calibración, los hologramas aparecerán correctamente incluso a medida que el visor se desplace en tu cabeza.

    La información de calibración se almacena localmente en el dispositivo y no está asociada a ninguna información de la cuenta. Para obtener más información, consulta [Seguridad y datos de calibración](hololens-calibration.md#calibration-data-and-security).

    ![Pantalla de selección de calibración](images/06-et-corners.png)

1. Conéctate a Internet (selecciona Wi-Fi o tu conexión Ethernet).
     HoloLens establece tu zona horaria automáticamente en función de la información obtenida de la red Wi-Fi. Una vez finalizada la instalación, puedes cambiar la zona horaria con la aplicación Configuración.

    ![Conectarte a Wi-Fi](images/11-network.png)
> [!NOTE] 
> Si progresas más allá del paso de Wi-Fi y necesitas cambiar más tarde a una red diferente mientras te encuentras en la configuración, puedes presionar los botones **Bajar el volumen** y **Inicio/apagado** a la vez para regresar a este paso si estás ejecutando una versión de sistema operativo de octubre de 2019 o posterior. En versiones anteriores, es posible que tengas que [restablecer el dispositivo](hololens-recovery.md) o reiniciarlo en una ubicación en la que la red Wi-Fi no esté disponible para impedir que se conecte automáticamente.
> 
> Ten en cuenta también que durante la configuración de HoloLens, hay un tiempo de espera de credenciales de dos minutos. El nombre de usuario y la contraseña se deben escribir en un intervalo de dos minutos, de lo contrario, el campo de nombre de usuario se borrará automáticamente.

1. Inicia sesión con tu cuenta de usuario. Elige entre **Pertenece a mi trabajo o escuela** y **Es mía**.
    - Si eliges **Pertenece a mi trabajo o escuela**, inicia sesión con una cuenta de Azure AD. Si tu organización usa Azure AD Premium y ha configurado la inscripción automática de MDM, HoloLens se inscribe automáticamente en MDM. Si tu organización no usa Azure AD Premium, la inscripción automática de MDM no está disponible. En ese caso, debes [inscribir HoloLens manualmente en la administración de dispositivos](hololens-enroll-mdm.md#enroll-through-settings-app).
        1. Escribe la información de la cuenta de la organización.
        1. Acepta la declaración de privacidad y el contrato de licencia para el usuario final.
        1. Inicia sesión con tus credenciales de Azure AD. Esto puede redirigirte a la página de inicio de sesión de tu organización.
        1. Continúa configurando el dispositivo.
    - Si eliges **Es mía**, iniciarás sesión con una cuenta de Microsoft. Una vez completada la configuración, puedes [inscribir HoloLens manualmente en la administración de dispositivos](hololens-enroll-mdm.md#enroll-through-settings-app).
        1. Escribe la información de tu cuenta de Microsoft.
        2. Escribe tu contraseña. Si tu cuenta de Microsoft requiere una [verificación en dos pasos (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), completa el proceso de comprobación.

    ![Establecer usuario](images/13-device-owner.png)

1. Selecciona si quieres habilitar la voz en HoloLens 2 y si quieres enviar telemetría de diagnóstico.
    ![Habilitar Cortana](images/22-do-more-with-voice.png)

1. Selecciona el nivel de telemetría. Si puedes, habilita la telemetría completa. Esta información realmente ayuda al equipo de ingeniería de HoloLens.
     ![Nivel de telemetría](images/24-telemetry.png)

1. Más información sobre cómo usar el gesto Inicio en HoloLens 2.
     ![Más información sobre cómo usar el gesto Inicio, imagen 1](images/26-01-startmenu-learning.png) ![Más información sobre cómo usar el gesto Inicio, imagen 2](images/26-02-startmenu-learning.png)

¡Enhorabuena!  La configuración se ha completado y ya puedes usar HoloLens.

## Pasos siguientes

> [!div class="nextstepaction"]
> [Introducción a HoloLens 2](hololens2-basic-usage.md)
