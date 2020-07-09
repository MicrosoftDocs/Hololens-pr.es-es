---
title: Versión preliminar de Insider para Microsoft HoloLens
description: Es fácil comenzar con las compilaciones de Insider y proporcionar comentarios valiosos para nuestra próxima actualización importante del sistema operativo para HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 6/29/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: b054b61b269522d673be104ffbda9abc1bc85415
ms.sourcegitcommit: 168a7659420525e5f3e3088d7ce0b5e03c969029
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2020
ms.locfileid: "10860610"
---
# Versión preliminar de Insider para Microsoft HoloLens

Te agradecemos las compilaciones más recientes de Insider Preview para HoloLens.  Es fácil comenzar y proporciona comentarios valiosos para nuestra próxima actualización importante del sistema operativo para HoloLens.

Windows Insider se está moviendo a los canales. El timbre **rápido** se convertirá en el **canal de desarrollo**, el anillo **lento** se convertirá en el canal de la **versión beta**y el anillo de **versión preliminar** se convertirá en el **canal de versión preliminar**de la versión. Este es el aspecto de la asignación:

![Explicación de Windows Insider Channels](images/WindowsInsiderChannels.png)

Para obtener más información: [entrada de blog de Windows](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)

## Empezar a recibir compilaciones de Insider

En un dispositivo HoloLens 2, vaya a **configuración**  ->  **Update & seguridad**de  ->  **Windows Insider** y seleccione **Introducción**. Vincule la cuenta que usó para registrarse como Windows Insider.

Después, selecciona **desarrollo activo de Windows**, elige si deseas recibir las compilaciones de **canal** de **desarrollo** o beta, y revisa las condiciones del programa.

Seleccione **confirmar, > reiniciar ahora** para finalizar. Después de reiniciar el dispositivo, vaya a **configuración-> actualización & seguridad: > comprobar si hay actualizaciones** para obtener la compilación más reciente.

## Dejar de recibir compilaciones de Insider

Si ya no desea recibir compilaciones de Insider de Windows Holographic, puede deshabilitarlas cuando HoloLens esté ejecutando una compilación de producción, o puede [recuperar el dispositivo](hololens-recovery.md) con el Asistente de recuperación avanzada para recuperar el dispositivo a una versión no Insider de Windows Holographic.

> [!CAUTION]
> Hay un problema conocido por el que los usuarios que cancelan la inscripción de las compilaciones de Insider Preview después de volver a instalar manualmente una versión preliminar nueva se vería una pantalla azul. Después, deben recuperar manualmente su dispositivo. Para obtener información completa sobre si se vería afectado o no, consulte más información sobre este [problema conocido](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).

Para comprobar que HoloLens está ejecutando una compilación de producción:

1. Vaya a **configuración > sistema >** y busque el número de compilación.
1. [Consulte las notas de la versión de los números de compilación de producción.](hololens-release-notes.md)

Para no participar en las compilaciones de Insider:

1. En un HoloLens que ejecute una compilación de producción, vaya a **configuración > actualizar & seguridad > programa Windows Insider**y seleccione **detener compilaciones de Insider**.
1. Siga las instrucciones para cancelar el dispositivo.


## Proporcionar comentarios e informar de problemas

Usa [la aplicación centro de opiniones](hololens-feedback.md) de tu HoloLens para proporcionar comentarios e informar de problemas. El uso del centro de opiniones asegura que se incluya toda la información de diagnóstico necesaria para ayudar a nuestros ingenieros a depurar y resolver el problema rápidamente.  Los problemas con la versión China y japonesa de HoloLens se deben notificar de la misma manera.

> [!NOTE]
> Asegúrese de aceptar el mensaje que le pregunta si desea que el centro de comentarios acceda a su carpeta de documentos (seleccione **sí** cuando se le solicite).

## Nota para los desarrolladores

Te recomendamos que intentes desarrollar tus aplicaciones con las compilaciones de Insider de HoloLens.  Consulta la [documentación para desarrolladores de HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) para comenzar. Las mismas instrucciones funcionan con las compilaciones de Insider de HoloLens.  Puedes usar las mismas compilaciones de Unity y Visual Studio que ya usas para el desarrollo de HoloLens.


## Notas de la versión de Windows Insider

A partir de la versión de [actualización de Windows Holographic 2020](hololens-release-notes.md) , ahora están disponibles todas las características de la versión preliminar. Asegúrate de [actualizar tu HoloLens](hololens-update-hololens.md) para obtener todas las características más recientes.

Volveremos a actualizar esta página con nuevas características a medida que las liberaremos para compilaciones de Windows Insider.


### Soporte de posición de ojos automático

En HoloLens 2, las posiciones de ojo permiten un posicionamiento preciso del holograma, una experiencia de visualización cómoda y una mejor calidad de visualización. Las posiciones de los ojos se calculan como parte del resultado del seguimiento ocular. Sin embargo, esto requiere que cada usuario pase por la calibración del seguimiento de los ojos, incluso cuando la experiencia no requiera una entrada de ojo.

La **posición de ojo automático (AEP)** permite que estos escenarios tengan una forma sin interacción que calcule las posiciones de la vista para el usuario.  La posición del ojo automático comienza a funcionar en segundo plano automáticamente desde el momento en el que el usuario coloca el dispositivo. Si el usuario no tiene una calibración de seguimiento de ojos anteriores, la posición de la vista automática comenzará a proporcionar las posiciones de ojo del usuario en el sistema de visualización después de un pequeño tiempo de procesamiento. Este tiempo de procesamiento suele estar entre 20-60 segundos. Los datos de usuario no se conservan en el dispositivo y, por lo tanto, este proceso se repite si el usuario desconecta y vuelve a poner el dispositivo o si el dispositivo se reinicia o se reactiva desde la suspensión.  

Hay algunos cambios en el comportamiento del sistema con la característica posición del ojo automático cuando un usuario no calibrado coloca el dispositivo. Un usuario no calibrado se refiere a alguien que no ha pasado por el proceso de calibración de seguimiento ocular en el dispositivo anteriormente.

|     Aplicación activa                           |     Comportamiento actual                                   |     Comportamiento de la compilación de Windows Insider 19041.1339 +                                                      |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     Aplicación no habilitada para la mirada o shell holográfica    |     Se muestra la pregunta de calibración del seguimiento ocular.    |     No se muestra ningún mensaje.                                                                                |
|     Aplicación de fijamente                             |     Se muestra la pregunta de calibración del seguimiento ocular.    |     La pregunta de calibración de seguimiento ocular se muestra solo cuando la aplicación accede a la secuencia de ojo.     |

 Si el usuario realiza una transición de una aplicación con la opción de no estar habilitada a una persona que tiene acceso a los datos de fijamente, se mostrará la solicitud de calibración. No se cambiará el flujo de la experiencia de la caja. 
 
Para las experiencias que requieren datos de ojo ocular o un holograma muy preciso, recomendamos que los usuarios no calibrados ejecuten la calibración del seguimiento ocular desde la solicitud de calibración de seguimiento ocular o iniciando la aplicación configuración desde el menú Inicio y seleccionando **> calibración del sistema > calibración de ojos > ejecutar**la calibración de ojos.

**Problemas conocidos**
1.  Estamos investigando un problema por el que el proceso de hospedaje del controlador del seguimiento ocular podría bloquearse al ejecutarse en una carga pesada de la memoria. El proceso de hospedaje del controlador de seguimiento ocular debe recuperarse automáticamente.

## FFU de descarga y de Flash
Para probar con un FFU firmado de vuelo, primero debe desbloquear el dispositivo antes de hacer parpadear la FFU con firma de vuelo.
1. En PC
    1. Descarga FFU en tu PC desde:[https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload)
    1. Instale ARC (Asistente para recuperación avanzada) en Microsoft Store:[https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
1. En HoloLens-desbloqueo de vuelo: abrir **configuración**  >  **Actualizar & seguridad**  >  **Windows Insider** , después registrarse, reiniciar el dispositivo
1. Flash FFU: ahora puedes Flash el vuelo con firma de FFU con arco
