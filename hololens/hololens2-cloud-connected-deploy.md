---
title: 'Guía de implementación: implementación HoloLens 2 en la nube a escala con Remote Assist- Implementación'
description: Aprenda a validar la inscripción y la Remote Assist para HoloLens dispositivos a través de una red conectada a la nube.
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
ms.openlocfilehash: 519770badab9f260316fe4cfff4bf453a7c971a7
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033537"
---
# <a name="deploy---cloud-connected-guide"></a>Implementación: Guía conectada a la nube

Ahora que tiene todo configurado, debe estar listo para distribuir los dispositivos. Sin embargo, ahora es la primera vez que debe validar la configuración. En primer Azure AD se debe validar el proceso de unión a la suscripción y la inscripción de MDM, seguido de la comprobación Remote Assist se puede realizar una llamada a .

## <a name="enrollment-validation"></a>Validación de inscripción

Ahora que todo está configurado correctamente para la Azure AD y la inscripción de MDM, el resto debería ser ahora un complemento. Necesitará&#39;conexión de Wi-Fi y el dispositivo HoloLens, así como una de las cuentas de usuario de AAD configuradas previamente.

Si el dispositivo no&#39;actualmente en un estado de configuración de fábrica, ahora sería un buen momento para volver a [actualizar el dispositivo.](/hololens/hololens-recovery#clean-reflash-the-device)

1. Una vez que el dispositivo está en OOBE,&#39;tendrá que empezar a interactuar y seguir las indicaciones. 
1. El mensaje crítico será cuando se le pregunte **si Quién posee este HoloLens?** Seleccione **My work or school owns it** (Mi trabajo o escuela es el propietario) y escriba sus Azure AD de cuenta.
1. Cuando la inscripción se realiza correctamente,&#39;se le pedirá que configure un PIN. Este PIN es único para este dispositivo para este usuario. También se le pedirán exámenes de Iris, datos de voz y configuración de telemetría y, por último,&#39;podrá aprender a abrir el menú inicio y completar OOBE.
1. Una vez que haya pasado a Mixed Reality inicio, abra menú Inicio con el **gesto Iniciar** que acaba de aprender.
1. Seleccione la **Configuración** aplicación y seleccione **Sistema.** La primera parte de la información que&#39;verá es el nombre del dispositivo, que para el dispositivo HoloLens 2 será HOLOLENS, seguido de una cadena de seis &quot; &quot; caracteres.
1. Tome nota de este nombre.

![HoloLens 2 Configuración: Acerca de.](./images/hololens2-settings-about.jpg)

7. Puede comprobar que el dispositivo está inscrito correctamente en el Azure AD dentro de la Configuración aplicación. En **Configuración** seleccione **Cuentas Acceder** a trabajo o  ->  **escuela.** En esta pantalla puede comprobar que se inscribió correctamente; para ello, vea Conectado a &quot; _nameofAAD_&#39;de Azure AD. Conectado por sunombredeusuarioofAAD  @ .onmicrosoft.com &quot; .


Para validar que el dispositivo Azure AD unido, podemos comprobar [](https://portal.azure.com/#home)la Azure Active Directory desde Azure Portal Azure Active Directory Devices Todos los dispositivos y buscar el nombre  ->    ->    ->  del dispositivo. También&#39;podrá ver que el dispositivo forma parte de la Azure Active Directory.


![Azure Active Directory: dispositivo.](./images/aad-enrollment.png)

A continuación&#39;tendrá que iniciar sesión en el centro [Microsoft Endpoint Manager administración de .](https://endpoint.microsoft.com/#home) Inicie sesión y seleccione **Dispositivos y, a** **continuación, Todos los dispositivos.** Desde aquí puede buscar el nombre HoloLens dispositivo&#39;dispositivo. Debería poder ver la lista de HoloLens en Intune.

![Intune: dispositivo.](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Remote Assist validación de llamadas

Una vez&#39;que el dispositivo está inscrito en AAD y MDM, es&#39;es el momento de realizar una prueba Remote Assist llamada. Para esta validación,&#39;tendrá que tener el dispositivo HoloLens y un equipo Windows 10, así como una segunda cuenta de Azure AD usuario del equipo.

En este paso de validación se supone que ha completado previamente el último paso de validación y que el dispositivo está inscrito y que el usuario Azure AD está en el dispositivo.


1. Si aún no tiene instalado Microsoft Teams en el equipo, puede descargar Teams [aquí.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. Inicie sesión Teams con la segunda cuenta Azure AD usuario que la que ha iniciado sesión actualmente en su HoloLens. Una vez que haya iniciado sesión en el equipo, estará listo para recibir la llamada.
3. Desbloquee HoloLens e inicie sesión.
4. Para iniciar la aplicación Remote Assist, abra el **menú Inicio** y **seleccione Remote Assist**. Remote Assist no solo se incluye como una aplicación de bandeja de entrada, sino que se ancla al menú HoloLens 2&#39;inicio de la aplicación. En caso de que no&#39;lo vea anclado al menú Inicio,  abra la lista Todas las aplicaciones para buscarla.
5. Una Remote Assist se debe identificar al usuario del dispositivo a través del [inicio](/azure/active-directory/manage-apps/what-is-single-sign-on) de sesión único e iniciar sesión en la aplicación.
6. Desde dentro de la aplicación, seleccione **Buscar** y busque el segundo usuario en el equipo. Seleccione el usuario para iniciar la llamada.
7. Desde el equipo, responda a la llamada.

Enhorabuena,&#39;se ha conectado correctamente y está en la llamada de asistencia remota. Asegúrese de probar características específicas de asistencia remota, como el uso de:

- [Anotaciones de entrada](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Compartir un archivo y una vista en realidad mixta](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Obtener ayuda en otra aplicación HoloLens aplicación](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Paso siguiente

> [!div class="nextstepaction"]
> [Implementación conectada a la nube: mantenimiento](hololens2-cloud-connected-maintain.md)