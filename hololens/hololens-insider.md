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
ms.date: 4/21/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: e00c043f7de1142e4d2e08e41ff0d91123d4a98b
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828615"
---
# Versión preliminar de Insider para Microsoft HoloLens

Te agradecemos las compilaciones más recientes de Insider Preview para HoloLens.  Es fácil comenzar y proporciona comentarios valiosos para nuestra próxima actualización importante del sistema operativo para HoloLens.

## Empezar a recibir compilaciones de Insider

En un dispositivo HoloLens 2, vaya a **configuración**  ->  **Update & seguridad**de  ->  **Windows Insider** y seleccione **Introducción**. Vincule la cuenta que usó para registrarse como Windows Insider.

Después, seleccione **desarrollo activo de Windows**, elija si desea recibir compilaciones **rápidas** o **lentas** , y revise los términos del programa.

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

A partir de nuestra versión de [actualización de Windows Holographic 2020](hololens-release-notes.md) , Feautres ahora avalible. Asegúrate de [actualizar tu HoloLens](hololens-update-hololens.md) para obtener todas las características más recientes.  

Volveremos a actualizar esta página con nuevas características a medida que las liberaremos para compilaciones de Windows Insider. 

### FFU de descarga y de Flash
Para probar con un FFU firmado de vuelo, primero debe desbloquear el dispositivo antes de hacer parpadear la FFU con firma de vuelo.
1. En PC
    1. Descarga FFU en tu PC desde:[https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload)
    1. Instale ARC (Asistente para recuperación avanzada) en Microsoft Store:[https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 
1. En HoloLens-desbloqueo de vuelo: abrir **configuración**  >  **Actualizar & seguridad**  >  **Windows Insider** , después registrarse, reiniciar el dispositivo
1. Flash FFU: ahora puedes Flash el vuelo con firma de FFU con arco 
