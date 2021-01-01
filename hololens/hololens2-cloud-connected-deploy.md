---
title: 'Guía de implementación: implementación de la nube conectada a HoloLens 2 a escala con asistencia remota-implementar'
description: Cómo validar la inscripción y el asistencia remota para dispositivos HoloLens en una red conectada en la nube
keywords: HoloLens, administración, nube conectada, asistencia remota, AAD, Azure AD, MDM, administración de dispositivos móviles
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2b38f4a76ee088d4f892c86de07d8f5a10d2a3bf
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253197"
---
# Implementación: Guía conectada a la nube

Ahora que tienes todo lo configurado, deberías estar listo para distribuir dispositivos. Sin embargo, ahora es cuando debe validar en primer lugar la configuración. En primer lugar, debe validarse el proceso de inscripción de Azure AD join y MDM, seguido de la verificación de que se puede realizar una llamada de asistencia remota.

## Validación de inscripción

Ahora que todo está configurado correctamente para la inscripción de Azure AD y MDM, el resto debería ser ahora un complemento. &#39;necesita una conexión de Wi-Fi y el dispositivo HoloLens, así como una de las cuentas de usuario de AAD previamente configuradas.

Si el dispositivo no&#39;en este momento en un estado de configuración de fábrica, ahora sería un buen momento para volver a [parpadear el dispositivo](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).

1. Una vez que el dispositivo esté en OOBE,&#39;tendrá que iniciar la interactuación y seguir las indicaciones. 
1. La pregunta crítica será cuando se le pregunte ¿ **quién es el propietario de HoloLens?** Seleccione **mi trabajo o escuela propietario** y escriba las credenciales de su cuenta de Azure ad.
1. Cuando la inscripción se realiza correctamente,&#39;se le solicitará que configure un PIN. Este PIN es exclusivo de este dispositivo para este usuario. Además, se le pedirán análisis de iris, datos de voz y configuración de telemetría y, por último,&#39;podrá saber cómo abrir el menú Inicio y completar OOBE.
1. Una vez que estés en la casa de la realidad mixta, abre el menú Inicio con el **gesto de inicio** que acabas de aprender.
1. Seleccione la aplicación **configuración** y seleccione **sistema.** El primer elemento de información que&#39;ver es el nombre del dispositivo, que para tu dispositivo HoloLens 2 será &quot; HoloLens, &quot; seguido de una cadena de seis caracteres.
1. Tome nota de este nombre.

![Configuración de HoloLens 2: acerca de](./images/hololens2-settings-about.jpg)

7. Puede comprobar que el dispositivo se ha inscrito correctamente en Azure AD dentro de la aplicación configuración. En **configuración** , seleccione **cuentas**,  ->  **acceso a trabajo o escuela**. En esta pantalla, puede comprobar que se ha inscrito correctamente viendo &quot; conectado a _nameofAAD_&#39;s Azure ad. Conectado por _YOURUSERNAME_ @ _nameofAAD_. onmicrosoft.com &quot; .


Para validar el dispositivo con Azure ad Unido, podemos comprobar Azure Active Directory desde los dispositivos Azure [portal](https://portal.azure.com/#home)  ->  **Azure Active**Directory  ->  ****  ->  **todos los dispositivos**y buscar en el nombre del dispositivo. &#39;podrá ver que el dispositivo es parte de Azure Active Directory.


![Azure Active Directory: dispositivo](./images/aad-enrollment.png)

A continuación,&#39;tendrá que iniciar sesión en el [centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home). Inicie sesión y seleccione **dispositivos** y, a continuación, **todos los dispositivos**. Desde aquí puedes buscar el nombre de tu dispositivo HoloLens&#39;s. Deberías poder ver tu HoloLens en Intune.

![Intune: dispositivo](./images/endpoint-all-devices-enrolled.png)

## Validación de llamadas de asistencia remota

Una vez&#39;que haya comprobado que su dispositivo está inscrito en sus equipos AAD y MDM,&#39;s para realizar una llamada de asistencia remota de prueba. Para esta validación,&#39;s debe tener el dispositivo HoloLens y un equipo Windows 10, así como una segunda cuenta de usuario de Azure AD para el equipo.

En este paso de validación se supondrá que ha completado previamente el último paso de validación y que el dispositivo está inscrito y que el usuario de Azure AD está en el dispositivo.


1. Si aún no tiene Microsoft Teams instalado en su equipo, puede [Descargar Teams aquí](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).
2. Inicie sesión en Teams con la segunda cuenta de usuario de Azure AD que la que actualmente ha iniciado sesión en HoloLens. Una vez que hayas iniciado sesión en tu equipo, podrás recibir la llamada.
3. Desbloquea HoloLens e inicia sesión.
4. Para iniciar la aplicación de asistencia remota, abra el **menú Inicio** y seleccione **asistencia remota**. Asistencia remota no solo se empaqueta como una aplicación de la bandeja de entrada pero está anclado al menú Inicio de HoloLens 2&#39;s. En un evento que no&#39;ve que está anclado al menú Inicio y, a continuación, abre la lista **todas las aplicaciones** para buscarlo.
5. Una vez que se inicia asistencia remota, debe identificar al usuario del dispositivo a través de [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) e iniciar sesión en la aplicación.
6. Desde dentro de la aplicación, seleccione **Buscar** y busque el segundo usuario en el equipo. Seleccione el usuario para iniciar la llamada.
7. En tu equipo, responde a la llamada.

Te has&#39;conectado correctamente y estás en tu llamada de asistencia remota. Asegúrese de probar las características específicas de asistencia remota, como el uso de:

- [Anotaciones de entrada de lápiz](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Compartir un archivo y ver en Mixed Reality](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Obtener ayuda en otra aplicación de HoloLens](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## Paso siguiente

> [!div class="nextstepaction"]
> [Implementación de conexión en la nube: mantenimiento](hololens2-cloud-connected-maintain.md)