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
ms.date: 11/10/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 260b195a18ecb7fe05d819fcd3e86d56fc2022bf
ms.sourcegitcommit: 74e9989240dc0c324df35e8651b2f307f9d42148
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "11201344"
---
# Versión preliminar de Insider para Microsoft HoloLens

Te agradecemos las compilaciones más recientes de Insider Preview para HoloLens. Es fácil [comenzar](hololens-insider.md#start-receiving-insider-builds) y proporciona comentarios valiosos para nuestra próxima actualización importante del sistema operativo para HoloLens.

## Notas de la versión de Windows Insider

Recientemente hemos publicado todas las características de Windows Insider. Puesto que todas estas características están ahora disponibles, te recomendamos que leas nuestras notas de la [versión](hololens-release-notes.md) para ver todas nuestras características más recientes. Mantente al tanto de volver a consultar para ver cuándo empezamos a probar las nuevas características interesantes.

## Empezar a recibir compilaciones de Insider

> [!NOTE]
> Si aún no lo ha actualizado, reinicie el dispositivo para actualizar el estado y obtenga la compilación más reciente.
> - El comando de voz "dispositivo de reinicio" funciona bien. 
> - También puede elegir el botón reiniciar en configuración/programa de Windows Insider.
>
> Tuvimos un error en el back-end que pudiera haber encontrado y esto le volveremos a la pista.

En un dispositivo HoloLens 2, vaya a **configuración**  >  **Update & seguridad**de  >  **Windows Insider** y seleccione **Introducción**. Vincule la cuenta que usó para registrarse como Windows Insider.

Windows Insider se está moviendo a los canales. El timbre **rápido** se convertirá en el **canal de desarrollo**, el anillo **lento** se convertirá en el canal de la **versión beta**y el anillo de **versión preliminar** se convertirá en el **canal de versión preliminar**de la versión. Este es el aspecto de la asignación:

![Explicación de Windows Insider Channels](images/WindowsInsiderChannels.png)

Para obtener más información, vea Introducción a los [canales de Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) en blogs de Windows.

Después, selecciona **desarrollo activo de Windows**, elige si deseas recibir las compilaciones de **canal** de **desarrollo** o beta, y revisa las condiciones del programa.

Seleccione **confirmar > reiniciar ahora** para finalizar. Después de reiniciar el dispositivo, vaya a **configuración > actualizar & seguridad > buscar actualizaciones** para obtener la compilación más reciente.

## FFU de descarga y de Flash
Para probar con un FFU firmado de vuelo, primero debe desbloquear el dispositivo antes de hacer parpadear la FFU con firma de vuelo.
1. En PC:

    1. Descarga FFU en tu PC desde [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Instale ARC (Asistente para recuperación avanzada) en Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. En HoloLens-desbloqueo de vuelo: abrir **configuración**  >  **Actualizar & seguridad**  >  **Windows Insider** después, Regístrese, reiniciar el dispositivo.

1. Flash FFU: ahora puedes hacer parpadear el vuelo con la firma de FFU con arco.

## Proporcionar comentarios e informar de problemas

Usa [la aplicación centro de opiniones](hololens-feedback.md) de tu HoloLens para proporcionar comentarios e informar de problemas. El uso del centro de opiniones asegura que se incluya toda la información de diagnóstico necesaria para ayudar a nuestros ingenieros a depurar y resolver el problema rápidamente.  Los problemas con la versión China y japonesa de HoloLens se deben notificar de la misma manera.

> [!NOTE]
> Asegúrese de aceptar el mensaje que le pregunta si desea que el centro de comentarios acceda a su carpeta de documentos (seleccione **sí** cuando se le solicite).

## Nota para los desarrolladores

Te recomendamos que intentes desarrollar tus aplicaciones con las compilaciones de Insider de HoloLens.  Consulta la [documentación para desarrolladores de HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) para comenzar. Las mismas instrucciones funcionan con las compilaciones de Insider de HoloLens.  Puedes usar las mismas compilaciones de Unity y Visual Studio que ya usas para el desarrollo de HoloLens.

## Dejar de recibir compilaciones de Insider

Si ya no desea recibir compilaciones de Insider de Windows Holographic, puede deshabilitarlas cuando HoloLens esté ejecutando una compilación de producción, o puede [recuperar el dispositivo](hololens-recovery.md) con el Asistente de recuperación avanzada para recuperar el dispositivo a una versión no Insider de Windows Holographic.

> [!CAUTION]
> Hay un problema conocido por el que los usuarios que cancelan la inscripción de las compilaciones de Insider Preview después de volver a instalar manualmente una versión preliminar nueva se vería una pantalla azul. Después, deben recuperar manualmente su dispositivo. Para obtener información completa sobre si se vería afectado o no, consulte más información sobre este [problema conocido](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).

Para comprobar que HoloLens está ejecutando una compilación de producción:

1. Vaya a **configuración > sistema >** y busque el número de compilación.

1. [Consulte las notas de la versión de los números de compilación de producción](hololens-release-notes.md).

Para no participar en las compilaciones de Insider:

1. En un HoloLens que ejecute una compilación de producción, vaya a **configuración > actualizar & seguridad > programa Windows Insider**y seleccione **detener compilaciones de Insider**.

1. Siga las instrucciones para cancelar el dispositivo.
