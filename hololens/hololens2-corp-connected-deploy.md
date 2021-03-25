---
title: 'Guía de implementación: HoloLens 2 conectado corporativamente con guías de Dynamics 365: implementar'
description: Obtenga información sobre cómo configurar implementaciones de dispositivos HoloLens 2 a través de una red conectada corporativa con guías de Dynamics 365.
keywords: HoloLens, administración, con conexión corporativa, Guías de Dynamics 365, AAD, Azure AD, MDM, Administración de dispositivos móviles
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
ms.openlocfilehash: febf56f94a5cab623fd7ad08ae7abf7050224717
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448629"
---
# <a name="deploy---corporate-connected-guide"></a>Implementar: Guía conectada corporativa

Una parte importante de cada implementación es asegurarse de que la implementación esté configurada correctamente antes de probarla usted mismo para garantizar una experiencia fluida para el usuario final.

Dado que estamos implementando el certificado de Wi-Fi a través de MDM, tendremos que configurar HoloLens e inscribir dispositivos en una red Wi-Fi abierta o en una red que no requiera el certificado. Una vez que HoloLens haya finalizado OOBE y se haya inscrito, el dispositivo recibirá el certificado de red y la LOB configurados anteriormente y podremos validar que el dispositivo haya recibido ambos.

Después, podrás confirmar que puedes crear y usar una guía de prueba.

## <a name="enrollment-validation"></a>Validación de inscripción

Ahora que todo está configurado correctamente para la inscripción de Azure AD y MDM, el resto debería ser ahora un complemento. Necesitará una conexión Wi-Fi y el dispositivo HoloLens y una de las cuentas de usuario de Azure AD configuradas anteriormente.

Si el dispositivo no está actualmente sentado en un estado de configuración de fábrica, ahora sería un buen momento para [reflash el dispositivo](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).

1. Una vez que el dispositivo esté en OOBE, tendrás que empezar a interactuar y seguir las indicaciones.

2. Conéctese a una red Wi-Fi que no requiera certificados para unirse a la red Wi-Fi. Esto permitirá que el dispositivo descargue el certificado que se usará en el servidor de la Wi-Fi después de la configuración inicial.

3. The critical prompt will be when you are asked **Who owns this HoloLens?** Selecciona **Mi trabajo o escuela es el propietario y** escribe las credenciales de tu cuenta de Azure AD.

4. Cuando la inscripción se realiza correctamente, se te pedirá que configures un PIN. Este PIN es único para este dispositivo para este usuario. También se le pedirán exámenes de Iris, datos de voz y configuración de telemetría y, por último, podrá aprender a abrir el menú inicio y completar OOBE.

5. Una vez que haya aterrizado en Mixed Reality Home, abra el menú Inicio con el **gesto Inicio** que acaba de aprender.

6. Selecciona la **aplicación Configuración** y selecciona **Sistema**. La primera información que verás es el nombre del dispositivo, que para el dispositivo HoloLens 2 será HOLOLENS, seguido de una cadena &quot; &quot; de seis caracteres.

7. Tome nota de este nombre.

    ![Pantalla Configuración de HoloLens 2](./images/hololens2-settings-about.jpg)

8. Compruebe que el dispositivo se ha unido correctamente a Azure AD. Hay dos maneras;

    1.  La aplicación Configuración. En **Configuración,** seleccione **Acceso a**cuentas trabajo o  ->  **escuela.** En esta pantalla, puede comprobar que se inscribió correctamente al ver Conectado a &quot; nameofAAD&#39;Azure AD. Conectado por *yourusername@nameofAAD.onmicrosoft.com*. Esto comprobará que el dispositivo está unido a la organización&#39;Azure AD.

    1. [Azure Portal](https://portal.azure.com/#home). Vaya a **Dispositivos de Azure Active Directory**Todos los  ->  ****  ->  **dispositivos**y busque el nombre del dispositivo. En Tipo de unión, se mostrará como "Unido a Azure AD".
        ![Comprobar el tipo de unión en Azure AD](./images/hololens2-devices-all-devices.png)

9. Comprueba que el dispositivo está inscrito con MDM. Hay dos maneras;

    1. En **Configuración,** seleccione **Acceso a cuentas**  ->  **laborales o educativas.** En esta pantalla, puede comprobar que se inscribió correctamente al ver Conectado a &quot; nameofAAD&#39;Azure AD. Conectado por *yourusername@nameofAAD.onmicrosoft.com*. En esta cuenta de trabajo o escuela de Access, seleccione &quot; Conectado a nameofAAD&#39;Azure AD. Conectado por yourusername@nameofAAD.onmicrosoft.com &quot; y seleccione el **botón Información.**

    1. [Centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home). Inicie sesión y seleccione  **Dispositivos y,**  **a continuación, Todos los dispositivos**. Desde aquí, puedes buscar en el dispositivo HoloLens&#39;nombre. Debería poder ver los HoloLens enumerados en Intune.

        ![Comprobar administrado por Intune en Azure AD](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi de certificados

Por ahora, el dispositivo debería haber recibido el Wi-Fi certificado. La validación más sencilla que puede hacer es intentar conectarse a la conexión Wi-Fi para la que&#39;ha recibido el certificado. Abre la aplicación **Configuración** y ve a **Red &amp; Internet**  ->  **Wi-Fi** y selecciona la conexión Wi-Fi. Una vez conectado, abre la aplicación Microsoft Edge y confirma que puedes navegar a un sitio web.

Para confirmar que ha recibido el certificado en el dispositivo, puede usar el Administrador [de certificados](https://docs.microsoft.com/hololens/certificate-manager).

## <a name="validate-lob-app-install"></a>Validar la instalación de la aplicación de LOB

Para ver el progreso de la instalación de una aplicación administrada, ves si la aplicación está instalada o compruebas Configuración. Al configurar una aplicación de LOB como una instalación necesaria para nuestro grupo, después de inscribir HoloLens con un usuario en el grupo asignado, la aplicación se descargará automáticamente en HoloLens.

Abra el menú Inicio y **seleccione Todas las aplicaciones**. Según el número de aplicaciones que tenga, **** es posible que deba usar los botones de página arriba o **abajo de la** página.

Para validar la instalación de la aplicación en **** el dispositivo, puedes hacerlo a través de Configuración Cuentas Acceso a trabajo o escuela; selecciona la cuenta y luego el botón Información  ->  ****  ->  **** y **** desplázate hacia abajo para ver diferentes configuraciones y aplicaciones aplicadas al dispositivo desde MDM.

Para validar la instalación desde [](https://endpoint.microsoft.com/#home)Intune, vaya a la página De aplicaciones -> todas las aplicaciones Estado de instalación del dispositivo  ->  **** ****  -> *TheNameOfYourApp.*  ->  ****

Ver más: [Implementación de aplicaciones de Intune para HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Validar guías de Dynamics 365

Hay modos para la aplicación Guías en HoloLens, creación y funcionamiento. Tendrás que terminar de crear una guía antes de operarla.

### <a name="authoring-the-guide"></a>Creación de la guía

No es necesario hacer mucho para esta validación rápida. Simplemente selecciona la guía que preparaste en tu PC. Tendrás que delimitar [la guía,](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor)para una validación rápida puedes usar un delimitador holográfico. Después, debe colocar [los pasos y los modelos](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation).

>[!NOTE]
> Necesitará el rol **De creación** para iniciar sesión en el equipo y crear en HoloLens. El rol Operador es de solo lectura y no tiene acceso a la aplicación de PC.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Funcionamiento de la Guía

Una vez que los hologramas estén en su lugar, puede probar el funcionamiento de la guía. 
- Seleccionar **modo de operador**
- Haga clic en los pasos de la guía.

Para obtener instrucciones más detalladas sobre cómo operar una guía, consulte estos recursos:

[Información general sobre cómo operar una guía en guías de Dynamics 365](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-overview)

[Orientarse con la tarjeta Paso como operador en guías de Dynamics 365](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Paso siguiente 
> [!div class="nextstepaction"]
> [Implementación conectada corporativa: mantener](hololens2-corp-connected-maintain.md)
