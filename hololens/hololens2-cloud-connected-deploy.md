---
title: 'Guía de implementación: implementación de HoloLens 2 en la nube a escala con Remote Assist- Implementación'
description: Obtenga información sobre cómo validar la inscripción Remote Assist dispositivos HoloLens a través de una red conectada a la nube.
keywords: HoloLens, administración, conexión a la nube, Remote Assist, AAD, Azure AD, MDM, Mobile Administración de dispositivos
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
ms.openlocfilehash: 4183bde30673f5147683e16b4d625f73b063c529
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310225"
---
# <a name="deploy---cloud-connected-guide"></a>Implementación: Guía conectada a la nube

Ahora que tiene todo configurado, debe estar listo para distribuir los dispositivos. Sin embargo, ahora es la primera vez que debe validar la configuración. En primer lugar, Azure AD se debe validar el proceso de inscripción de MDM y, a continuación, comprobar que se puede Remote Assist llamada a mdm.

## <a name="enrollment-validation"></a>Validación de inscripción

Ahora que todo está configurado correctamente para la Azure AD y la inscripción de MDM, el resto debería ser ahora un complemento. Necesitará&#39;conexión de Wi-Fi y el dispositivo HoloLens, así como una de las cuentas de usuario de AAD configuradas previamente.

Si el dispositivo no&#39;actualmente en un estado de configuración de fábrica, sería un buen momento para volver a actualizar [el dispositivo.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)

1. Una vez que el dispositivo esté en la configuración rápida,&#39;tendrá que empezar a interactuar y seguir las indicaciones. 
1. El mensaje crítico será cuando se le pregunte **¿Quién es el propietario de HoloLens?** Seleccione **My work or school own it (Mi** trabajo o escuela es el propietario) y escriba sus credenciales Azure AD cuenta.
1. Cuando la inscripción se realiza correctamente,&#39;se le pedirá que configure un PIN. Este PIN es único para este dispositivo para este usuario. También se le pedirán exámenes de Iris, datos de voz y configuración de telemetría y, por último,&#39;podrá aprender a abrir el menú Inicio y completar la configuración rápida.
1. Una vez que haya empezado a Mixed Reality inicio, abra menú Inicio con el **gesto Iniciar que** acaba de aprender.
1. Seleccione la **aplicación Configuración** y seleccione **Sistema.** La primera parte de la información que&#39;verá es el nombre del dispositivo, que para el dispositivo HoloLens 2 será HOLOLENS, seguido de una cadena de &quot; &quot; seis caracteres.
1. Tome nota de este nombre.

![HoloLens 2 configuración: acerca de](./images/hololens2-settings-about.jpg)

7. Puede comprobar que el dispositivo está inscrito correctamente en el Azure AD en la aplicación Configuración. En **Configuración,** seleccione **Cuentas Acceder** a trabajo o  ->  **escuela.** En esta pantalla puede comprobar que se inscribió correctamente; para ello, vea Conectado a &quot; _nameofAAD_&#39;de Azure AD. Conectado por el nombredeusuarioofAAD  @ .onmicrosoft.com &quot; .


Para validar que el dispositivo Azure AD unido, podemos comprobar [](https://portal.azure.com/#home)la Azure Active Directory desde Azure Portal  ->  **Azure Active Directory**  ->  **Dispositivos** todos los dispositivos y buscar el nombre  ->  del dispositivo. También&#39;podrá ver que el dispositivo forma parte de la Azure Active Directory.


![Azure Active Directory: dispositivo](./images/aad-enrollment.png)

A continuación&#39;tendrá que iniciar sesión en el Centro de administración de [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home). Inicie sesión y seleccione **Dispositivos y, a** **continuación, Todos los dispositivos.** Desde aquí puede buscar en el dispositivo HoloLens&#39;nombre. Debería poder ver que HoloLens aparece en Intune.

![Intune: dispositivo](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Remote Assist validación de llamadas

Una vez&#39;que el dispositivo está inscrito en AAD y MDM, es&#39;es el momento de realizar una prueba Remote Assist llamada. Para esta validación,&#39;tendrá que tener el dispositivo HoloLens y un equipo Windows 10, así como una segunda cuenta de Azure AD usuario del equipo.

En este paso de validación se supone que ha completado previamente el último paso de validación y que el dispositivo está inscrito y que Azure AD usuario está en el dispositivo.


1. Si aún no tiene Microsoft Teams instalado en el equipo, puede [descargar Teams aquí.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. Inicie sesión en Teams con la segunda Azure AD de usuario que la que ha iniciado sesión actualmente en HoloLens. Una vez que haya iniciado sesión en el equipo, estará listo para recibir la llamada.
3. Desbloquee HoloLens e inicie sesión.
4. Para iniciar la aplicación Remote Assist, abra el **menú Inicio** y **seleccione Remote Assist**. Remote Assist no solo se agrupa como una aplicación de bandeja de entrada, sino que se ancla al menú HoloLens 2&#39;inicio de la aplicación. En caso de que no&#39;lo vea anclado a la menú Inicio, abra la lista Todas las aplicaciones para buscarla. 
5. Una Remote Assist inicia, debe identificar al usuario del dispositivo a través de [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) e iniciar sesión en la aplicación.
6. Desde dentro de la aplicación, seleccione **Buscar** y busque el segundo usuario en el equipo. Seleccione el usuario para iniciar la llamada.
7. Desde el equipo, responda a la llamada.

Enhorabuena,&#39;se ha conectado correctamente y está en la llamada de asistencia remota. Asegúrese de probar características específicas de asistencia remota, como el uso de:

- [Invocación de anotaciones](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Compartir un archivo y ver en realidad mixta](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Obtener ayuda en otra aplicación de HoloLens](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Paso siguiente

> [!div class="nextstepaction"]
> [Implementación conectada a la nube: mantenimiento](hololens2-cloud-connected-maintain.md)