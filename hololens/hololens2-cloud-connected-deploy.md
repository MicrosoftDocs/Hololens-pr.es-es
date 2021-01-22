---
title: 'Guía de implementación: implementación de HoloLens 2 conectada en la nube a escala con asistencia remota: implementar'
description: Aprende a validar la inscripción y asistencia remota para dispositivos HoloLens a través de una red conectada a la nube.
keywords: HoloLens, administración, conectado a la nube, Asistencia remota, AAD, Azure AD, MDM, Administración de dispositivos móviles
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11282941"
---
# Implementar: Guía conectada a la nube

Ahora que tiene todo configurado, debería estar listo para distribuir dispositivos. Sin embargo, ahora es cuando primero debe validar la configuración. En primer lugar, se debe validar el proceso de unión a Azure AD y la inscripción de MDM, seguido de comprobar que se puede realizar una llamada de asistencia remota.

## Validación de inscripción

Ahora que todo está configurado correctamente para azure AD y la inscripción en MDM, el resto debería ser ahora un instante. Necesitará&#39;una conexión Wi-Fi y el dispositivo HoloLens, así como una de las cuentas de usuario de AAD configuradas anteriormente.

Si el dispositivo no&#39;actualmente en un estado de configuración de fábrica, ahora sería un buen momento para [reflash el dispositivo.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)

1. Una vez que el dispositivo esté en la OOBE,&#39;tendrás que empezar a interactuar y seguir las indicaciones. 
1. El mensaje crítico será cuando se le pregunte ¿Quién **es el propietario de este HoloLens?** Selecciona El propietario de Mi trabajo **o escuela y escribe** las credenciales de tu cuenta de Azure AD.
1. Cuando la inscripción se realiza correctamente,&#39;se te pedirá que configures un PIN. Este PIN es único para este dispositivo para este usuario. También se te pedirán exámenes del iris, datos de voz y configuración de telemetría y, por último,&#39;podrás aprender a abrir el menú Inicio y completar la configuración rápida.
1. Una vez que haya pasado a la página principal de realidad mixta, abra el menú Inicio con el gesto **Inicio** que acaba de aprender.
1. Selecciona la **aplicación Configuración** y selecciona **Sistema.** La primera información que&#39;verá es el nombre del dispositivo, que para el dispositivo HoloLens 2 será HOLOLENS seguido de una cadena de seis &quot; &quot; caracteres.
1. Tome nota de este nombre.

![Configuración de HoloLens 2: acerca de](./images/hololens2-settings-about.jpg)

7. Puedes comprobar que el dispositivo se inscriba correctamente en Azure AD dentro de la aplicación Configuración. En **Configuración,** seleccione **Acceso a**cuentas trabajo o  ->  **escuela.** Desde esta pantalla puede comprobar que se inscribió correctamente si ve Conectado a &quot; _nameofAAD_&#39;Azure AD. Conectado por _el nombredeusuario_ @ _nameofAAD_.onmicrosoft.com &quot; .


Para validar que el dispositivo tiene Azure AD unido, podemos comprobar Azure Active Directory desde Azure [Portal](https://portal.azure.com/#home)  ->  **Dispositivos de Azure Active Directory**Todos los dispositivos y buscar en el nombre del  ->  ****  ->  **** dispositivo. Puedes&#39;ver que el dispositivo forma parte de Azure Active Directory.


![Azure Active Directory: dispositivo](./images/aad-enrollment.png)

A continuación&#39;tendrá que iniciar sesión en el Centro de administración [de Microsoft Endpoint Manager.](https://endpoint.microsoft.com/#home) Inicie sesión y seleccione **Dispositivos y,** **a continuación, Todos los dispositivos.** Desde aquí, puedes buscar en el dispositivo HoloLens&#39;nombre. Deberías poder ver tu HoloLens en Intune.

![Intune: dispositivo](./images/endpoint-all-devices-enrolled.png)

## Validación de llamadas de asistencia remota

Una vez&#39;haya comprobado que el dispositivo está inscrito en AAD y MDM, es&#39;realizar una llamada de asistencia remota de prueba. Para esta validación,&#39;tendrá que tener el dispositivo HoloLens y un equipo con Windows 10, así como una segunda cuenta de usuario de Azure AD para el equipo.

En este paso de validación se presupone que ya has completado el último paso de validación y que el dispositivo está inscrito y que el usuario de Azure AD está en el dispositivo.


1. Si aún no tiene Microsoft Teams instalado en su equipo, puede [descargar Teams aquí.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. Inicie sesión en Teams con la segunda cuenta de usuario de Azure AD que la que ha iniciado sesión actualmente en Su HoloLens. Una vez que haya iniciado sesión en el equipo, estará listo para recibir la llamada.
3. Desbloquea HoloLens e inicia sesión.
4. Para iniciar la aplicación Asistencia remota, abra el **menú Inicio** y seleccione **Asistencia remota.** Remote Assist no solo se agrupa como una aplicación de la bandeja de entrada, sino que se ancla al menú de inicio&#39;HoloLens 2. En caso de que no&#39;lo veas anclado al **** menú Inicio, abre la lista Todas las aplicaciones para buscarla.
5. Una vez que el asistente remoto se inicia, debe identificar al usuario del dispositivo a través de [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) e iniciar sesión en la aplicación.
6. Desde dentro de la aplicación, selecciona **Buscar** y busca el segundo usuario en el equipo. Seleccione el usuario para iniciar la llamada.
7. Desde el equipo, responde a la llamada.

Enhorabuena,&#39;se ha conectado correctamente y está en la llamada de asistencia remota. Asegúrese de probar características específicas de asistencia remota, como usar:

- [Anotaciones de entrada de entrada](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Compartir un archivo y una vista en realidad mixta](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Obtener ayuda en otra aplicación de HoloLens](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## Paso siguiente

> [!div class="nextstepaction"]
> [Implementación conectada a la nube: mantener](hololens2-cloud-connected-maintain.md)