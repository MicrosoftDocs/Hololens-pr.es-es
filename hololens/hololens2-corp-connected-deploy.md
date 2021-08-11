---
title: 'Guía de implementación: HoloLens 2 con conexión corporativa con Dynamics 365 Guides: implementación'
description: Aprenda a configurar implementaciones de dispositivos HoloLens 2 a través de una red conectada corporativa con Dynamics 365 Guides.
keywords: HoloLens, administración, con conexión corporativa, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Administración de dispositivos
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f9435ce94986a851bb7744eeea48fa6e411454f5090d7ae11c869ba6f27dc942
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660206"
---
# <a name="deploy---corporate-connected-guide"></a>Implementación: Guía de conexión corporativa

Una parte importante de cada implementación es asegurarse de que la implementación está configurada correctamente antes de probarla usted mismo para garantizar una experiencia sin problemas para el usuario final.

Dado que estamos implementando el certificado de Wi-Fi a través de MDM, es necesario configurar inicialmente HoloLens e inscribir dispositivos en una red Wi-Fi abierta o en una red que no requiera el certificado. Una vez que el HoloLens haya finalizado la OOBE y la inscripción, el dispositivo recibirá el certificado de red y el LOB configurados previamente y podremos validar que el dispositivo recibió ambos.

Después, podrá confirmar que puede crear y usar una guía de prueba.

## <a name="enrollment-validation"></a>Validación de inscripción

Ahora que todo está configurado correctamente para la Azure AD y la inscripción de MDM, el resto debería ser ahora un poco. Necesitará una conexión de Wi-Fi y el dispositivo HoloLens, y una de las cuentas de usuario Azure AD configuradas previamente.

Si el dispositivo no está actualmente en un estado de configuración de fábrica, ahora sería un buen momento para volver a [actualizar el dispositivo.](/hololens/hololens-recovery#clean-reflash-the-device)

1. Una vez que el dispositivo esté en OOBE, deberá empezar a interactuar y seguir las indicaciones.

2. Conectar a una red Wi-Fi que no requiera certificados para unirse a la red Wi-Fi. Esto permitirá que el dispositivo descargue el certificado para que se utilice en el equipo de la Wi-Fi después de la configuración inicial.

3. El mensaje crítico será cuando se le pregunte **si Quién posee este HoloLens?** Seleccione **My work or school owns it (Mi** trabajo o escuela es el propietario) y escriba sus credenciales Azure AD cuenta.

4. Cuando la inscripción se realiza correctamente, se le pedirá que configure un PIN. Este PIN es único para este dispositivo para este usuario. También se le pedirán exámenes de Iris, datos de voz y configuración de telemetría y, por último, podrá obtener información sobre cómo abrir el menú Inicio y completar OOBE.

5. Una vez que haya pasado a Mixed Reality inicio, abra el menú Inicio con el **gesto Iniciar** que acaba de aprender.

6. Seleccione la **Configuración** y seleccione **Sistema**. La primera parte de la información que verá es el nombre del dispositivo, que para el dispositivo HoloLens 2 será HOLOLENS, seguido de una cadena &quot; &quot; de seis caracteres.

7. Tome nota de este nombre.

    ![HoloLens 2 Configuración pantalla](./images/hololens2-settings-about.jpg)

8. Compruebe que el dispositivo se ha unido correctamente a Azure AD. Hay dos maneras:

    1.  La Configuración aplicación. En **Configuración seleccione** **Cuentas Acceder** a trabajo o  ->  **escuela.** En esta pantalla, puede comprobar que se inscribió correctamente; para ello, vea Conectado a &quot; nameofAAD&#39;de Azure AD. Conectado por *yourusername@nameofAAD.onmicrosoft.com* . Esto comprobará que el dispositivo está unido a la organización&#39;de Azure AD.

    1. [Azure Portal](https://portal.azure.com/#home) Vaya a **Azure Active Directory**  ->  **dispositivos todos** los  ->  **dispositivos** y busque el nombre del dispositivo. En Tipo de combinación, se mostrará como "Azure AD Unido".
        ![Comprobar el tipo de combinación en Azure AD](./images/hololens2-devices-all-devices.png)

9. Compruebe que el dispositivo está inscrito con MDM. Hay dos maneras:

    1. En **Configuración**, seleccione **Cuentas Acceder** a trabajo o  ->  **escuela.** En esta pantalla, puede comprobar que se inscribió correctamente; para ello, vea Conectado a &quot; nameofAAD&#39;de Azure AD. Conectado por *yourusername@nameofAAD.onmicrosoft.com* . En esta cuenta de trabajo o educativa de Access, seleccione &quot; Conectado a nameofAAD&#39;de Azure AD. Conectado por yourusername@nameofAAD.onmicrosoft.com &quot; y seleccione el **botón** Información.

    1. [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home). Inicie sesión y seleccione **Dispositivos y, a** **continuación, Todos los dispositivos.** Desde aquí, puede buscar en el HoloLens dispositivo&#39;nombre. Debería poder ver la lista de HoloLens en Intune.

        ![Comprobación administrada por Intune en Azure AD](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi de certificados

Por ahora, el dispositivo debería haber recibido el Wi-Fi certificado. La validación más sencilla que puede hacer es intentar conectarse a la conexión Wi-Fi para la que&#39;ha recibido el certificado. Abra la aplicación **Configuración,** vaya a **Red &amp; Wi-Fi** de Internet  ->   y seleccione la conexión Wi-Fi. Una vez conectado, abra la aplicación Microsoft Edge y confirme que puede navegar a un sitio web.

Para confirmar que ha recibido el certificado en el dispositivo, puede usar el Administrador [de certificados](/hololens/certificate-manager).

## <a name="validate-lob-app-install"></a>Validación de la instalación de la aplicación lob

Para ver el progreso de la instalación de una aplicación administrada, puede ver si la aplicación está instalada o comprobar Configuración. Al configurar una aplicación de LOB como una instalación necesaria para nuestro grupo, después de inscribir el HoloLens con un usuario en el grupo asignado, la aplicación se descargará automáticamente en el HoloLens.

Abra el menú Inicio y seleccione **Todas las aplicaciones.** Dependiendo del número de aplicaciones que tenga,  puede que tenga que usar los botones subir o **bajar página.**

Para validar la instalación de la aplicación en el dispositivo, puede hacerlo a través de **acceso a** cuentas de Configuración profesionales o educativas; seleccione la cuenta y luego el botón Información y desplácese hacia abajo para ver diferentes configuraciones y aplicaciones aplicadas al dispositivo desde  ->    ->  MDM. 

Para validar la instalación desde [](https://endpoint.microsoft.com/#home)Intune, vaya a la página de estado de instalación aplicaciones -> de mem. Todas las  ->   aplicaciones   -> *TheNameOfYourApp*  ->  **Device.**

Vea más: [Implementación de aplicaciones de Intune para HoloLens](/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Validar Dynamics 365 Guides

Hay modos para la aplicación Guides en HoloLens, creación y funcionamiento. Deberá terminar de crear una guía antes de operarla.

### <a name="authoring-the-guide"></a>Creación de la guía

No es necesario hacer mucho para esta validación rápida. Solo tiene que seleccionar la guía que preparó en el equipo. Deberá delimitar la [guía,](/dynamics365/mixed-reality/guides/hololens-app-anchor)para una validación rápida puede usar un delimitador holográfico. Después, debe colocar [los pasos y modelos](/dynamics365/mixed-reality/guides/hololens-app-orientation).

>[!NOTE]
> Necesitará el rol **de creación para iniciar** sesión en el equipo y crear en el HoloLens. El rol Operador es de solo lectura y no tiene acceso a la aplicación de PC.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Funcionamiento de la guía

Una vez que los hologramas estén en su lugar, puede probar el funcionamiento de la guía. 
- Seleccionar **modo de operador**
- Haga clic en los pasos de la guía.

Para obtener instrucciones más detalladas sobre cómo usar una guía, consulte estos recursos:

[Introducción al funcionamiento de una guía en Dynamics 365 Guides](/dynamics365/mixed-reality/guides/operator-overview)

[Orientación con la tarjeta Paso como operador en Dynamics 365 Guides](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Paso siguiente 
> [!div class="nextstepaction"]
> [Implementación conectada corporativa: mantener](hololens2-corp-connected-maintain.md)
