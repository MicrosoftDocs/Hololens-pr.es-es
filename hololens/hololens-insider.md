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
ms.date: 7/17/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 11915bd6b2293be4491af2a7231b258b12d7b314
ms.sourcegitcommit: 7c16570839893f4a4432286b13ae6d84c665d376
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "10902322"
---
# Versión preliminar de Insider para Microsoft HoloLens

Te agradecemos las compilaciones más recientes de Insider Preview para HoloLens.  Es fácil comenzar y proporciona comentarios valiosos para nuestra próxima actualización importante del sistema operativo para HoloLens.

Windows Insider se está moviendo a los canales. El timbre **rápido** se convertirá en el **canal de desarrollo**, el anillo **lento** se convertirá en el canal de la **versión beta**y el anillo de **versión preliminar** se convertirá en el **canal de versión preliminar**de la versión. Este es el aspecto de la asignación:

![Explicación de Windows Insider Channels](images/WindowsInsiderChannels.png)

Para obtener más información, vea Introducción a los [canales de Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) en blogs de Windows.

## Notas de la versión de Windows Insider

Si busca una característica que ya no aparece aquí, ahora está disponible para el público. Revise las notas de la [versión](hololens-release-notes.md) para ver qué compilación tiene las características que está emocionando. Asegúrate de [actualizar tu HoloLens](hololens-update-hololens.md) para obtener todas las características más recientes.

Actualizaremos esta página con nuevas características, ya que las liberaremos para compilaciones de Windows Insider.

| Característica                                              | Descripción                                                                                   | Disponible en compilaciones de Insider |
|------------------------------------------------------|-----------------------------------------------------------------------------------------------|-----------------------------|
| Soporte de posición de ojos automático                            | Encuentra de forma activa posiciones de la vista y permite un posicionamiento preciso del holograma.                       | 19041.1339 +                 |
| Visor de certificados                                   | Ver certificados de usuarios y dispositivos en la aplicación configuración.                                        | 19041.1346 +                 |
| Directivas de HoloLens                                    | Nuevas directivas para dispositivos de realidad mixta.                                                       | 19041.1349 +                 |
| Caché de pertenencia a grupo AAD para el quiosco desconectado         | Directiva sobre cuántos días se permite que la caché de pertenencia a grupos de AAD se use para el modo de pantalla completa.     | 19041.1356 +                 |
| Nuevas directivas de restricción de dispositivo para HoloLens 2       | Directivas de administración de dispositivos habilitadas recientemente para HoloLens 2.                              | 19041.1349 +                 |
| Nuevas directivas de energía para HoloLens 2                    | Directivas que se han admitido recientemente para la configuración del tiempo de espera.                                          | 19041.1349 +                 |
| Actualizar directivas                                      | Directivas habilitadas recientemente que permiten controlar las actualizaciones.                                           | 19041.1352 +                 |
| Visibilidad de la página de configuración habilitada para HoloLens 2      | Directiva para elegir qué páginas se ven en la aplicación configuración.                                          | 19041.1349 +                 |
| Acceso asignado global                               | Configure el dispositivo HoloLens 2 para el modo de pantalla completa de varias aplicaciones, que es aplicable en el nivel del sistema.  | 19041.1356 +                 |
| Iniciar automáticamente una aplicación en quiosco de varias aplicaciones                | Configura una aplicación para que se inicie automáticamente al iniciar sesión en un modo quiosco de varias aplicaciones. | 19041.1346 +                 |
| Cambios en el comportamiento del modo de pantalla completa para el tratamiento de errores | Los cambios en la forma en que se maneja el error de modo quiosco.                                             | 19041.1356 +                 |

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
 - Estamos investigando un problema por el que el proceso de hospedaje del controlador del seguimiento ocular podría bloquearse al ejecutarse en una carga pesada de la memoria. El proceso de hospedaje del controlador de seguimiento ocular debe recuperarse automáticamente.

### Visor de certificados

En Windows Insider Build 19041.1346 + estamos agregando un visor de certificados en la aplicación de configuración de HoloLens 2. Esta característica proporciona una forma fácil y sencilla de comprobar los certificados de tu dispositivo. Para encontrar un certificado específico rápidamente, hay opciones para ordenar por nombre, almacén o fecha de expiración. Los usuarios también pueden buscar un certificado directamente. Con el nuevo visor de certificados, los administradores y los usuarios han mejorado las herramientas de auditoría, diagnóstico y validación para asegurarse de que los dispositivos siguen siendo seguros y cumplen con las normas.  Para obtener más información sobre un certificado individual, seleccione el certificado y haga clic en información.

> [!NOTE]
> Existe una limitación conocida en la localización de un idioma que no es de Estados Unidos y estamos trabajando para resolver en versiones posteriores de Windows Insider.

-   **Auditoría:** Posibilidad de validar que un certificado se ha implementado correctamente o para confirmar que se ha eliminado correctamente. 
-   **Diagnóstico:** Cuando surjan problemas, validar que los certificados adecuados existen en el dispositivo ahorra tiempo y ayuda con la solución de problemas. 
-   **Validación:** Comprobar que el certificado sirve para el propósito pretendido y es funcional, puede ahorrar mucho tiempo, especialmente en entornos comerciales antes de implementar certificados a mayor escala.

Para ver los certificados, vaya a **configuración > actualizar & certificados > de seguridad**.

![Visor de certificados de la aplicación configuración](images/hololens-certificate-viewer.png)

### Directivas de HoloLens
Se han creado nuevas directivas de realidad mixta para dispositivos HoloLens 2 en compilaciones 19041.1349 +. La nueva configuración controlable incluye: configuración del brillo, configuración del volumen, desactivación de la grabación de audio en capturas de realidad mixta, configuración de los diagnósticos y caché de pertenencia a grupos de AAD.  

| Nueva política de HoloLens                                | Descripción                                                                               | Notas                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Permite que los botones de brillo estén deshabilitados y, al presionarlos, no cambie el brillo.       | 1 sí, 0 no (valor predeterminado)                                                |
| MixedReality\VolumeButtonDisabled                  | Permite que los botones de volumen estén deshabilitados para que, al presionarlos, no cambie el volumen.               | 1 sí, 0 no (valor predeterminado)                                                |
| MixedReality\MicrophoneDisabled                    | Desactiva el micrófono para que no se pueda grabar audio en HoloLens 2.                      | 1 sí, 0 no (valor predeterminado)                                                |
| MixedReality\FallbackDiagnostics                   | Controla el comportamiento del momento en que se pueden recopilar los registros de diagnóstico.                               | 0 deshabilitado, 1 habilitado para propietarios de dispositivos, 2 habilitado para todos (predeterminado) |
| MixedReality\HeadTrackingMode                      | Reservado para uso futuro.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Controla la cantidad de días en que se usa la caché de pertenencia a grupos de AAD para quioscos segmentados. | Consulta a continuación.                                                           |

### Caché de pertenencia a grupo AAD para el quiosco desconectado

Esta directiva controla cuántos días se permite que la caché de pertenencia a grupos de AAD se use para configuraciones de acceso asignadas dirigidas a grupos de AAD para el usuario que ha iniciado sesión. Una vez que este valor de Directiva se establece en un valor mayor que 0, de lo contrario se usa cache.  

AADGroupMembershipCacheValidityInDays 

Min-0 días  
Máximo: 60 días 

Pasos para usar esta directiva correctamente: 
1. Cree un perfil de configuración de dispositivo para quiosco dirigido a grupos de AAD y asígnelo a dispositivos HoloLens. 
1. Crear un URI de OMA personalizado configuración de dispositivo que establezca este valor de directiva en cantidad deseada de días (> 0) y asignarlo a dispositivos HoloLens. 
1. Inscriba dispositivos HoloLens y verifique que ambas configuraciones se apliquen al dispositivo. 
1. Deje que el inicio de sesión de AAD para el usuario 1 cuando esté disponible Internet, una vez que el usuario inicie sesión y la pertenencia a grupos de AAD se haya confirmado correctamente, se creará la memoria caché. 
1. Ahora, el usuario 1 de AAD puede hacer que HoloLens esté desconectado y usarlo para el modo de pantalla completa, siempre y cuando el valor de la Directiva permita un número de días por X. 
1. Los pasos 4 y 5 se pueden repetir para cualquier otro usuario de AAD. punto clave aquí es que cualquier usuario de AAD debe iniciar sesión en el dispositivo con Internet, por lo menos una vez, podemos determinar que son miembros del grupo de AAD al que se dirige la configuración de quiosco. 
 
> [!NOTE]
> Hasta que se realice el paso 4 para un usuario de AAD experimentará un comportamiento de error que se menciona a continuación en entornos "desconectados". 

### Nuevas directivas de restricción de dispositivo para HoloLens 2
Directivas habilitadas recientemente que permiten más opciones de administración de los dispositivos HoloLens 2. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone) 

### Nuevas directivas de energía para Hololens 2
Estas directivas recién agregadas permiten a los administradores controlar Estados de energía, como el tiempo de espera de inactividad. Para obtener más información sobre cada directiva individual, haga clic en el vínculo de esa Directiva.

|     Vínculo de documentación de Directiva                |     Notas                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Valor de ejemplo para usar en el diseñador de configuración de Windows, es decir,  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Valor de ejemplo para usar en el diseñador de configuración de Windows, es decir,  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Valor de ejemplo para usar en el diseñador de configuración de Windows, es decir, 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Valor de ejemplo para usar en el diseñador de configuración de Windows, es decir, 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Valor de ejemplo para usar en el diseñador de configuración de Windows, es decir,   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Valor de ejemplo para usar en el diseñador de configuración de Windows, es decir,  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

### Nuevas directivas de actualización habilitadas para HoloLens
Estas directivas de actualización ahora están habilitadas en los dispositivos HoloLens 2:
-   [Actualizar/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Actualizar/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Actualizar/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Actualizar/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

### Visibilidad de la página de configuración habilitada para HoloLens 2
Hemos habilitado una directiva que permite a los administradores de ti evitar que determinadas páginas de la aplicación configuración del sistema sean visibles o accesibles, o para hacerlo en todas las páginas excepto en las especificadas. Para obtener información sobre cómo personalizar completamente esta característica, haz clic en el vínculo a continuación.
 
- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)
 
![Captura de pantalla de horas activas que se están modificando en la aplicación configuración](images/hololens-page-visibility-list.jpg)

### Acceso asignado global: modo de pantalla completa
Esta nueva característica permite que un administrador de ti configure un dispositivo HoloLens 2 para el modo de pantalla completa de varias aplicaciones, que es aplicable en el nivel del sistema, no tiene afinidad con ninguna identidad en el sistema y se aplica a todos los usuarios que inician sesión en el dispositivo. [Aquí encontrará](hololens-global-assigned-access-kiosk.md)información sobre esta nueva característica.

### Inicio automático de una aplicación en el modo de pantalla completa de varias aplicaciones 
Solo se aplica al modo de pantalla completa de varias aplicaciones y solo se puede designar una aplicación para iniciar automáticamente con el atributo resaltado a continuación en la configuración de acceso asignada. 

La aplicación se inicia automáticamente cuando el usuario inicia sesión. 

```xml
<AllowedApps>                     
    <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Cambios en el comportamiento del modo de pantalla completa para el tratamiento de errores

Antes de encontrar errores al aplicar el modo de pantalla completa, HoloLens se usó para mostrar todas las aplicaciones en el menú Inicio. A partir de esta compilación de Windows Insider, en caso de errores, no se mostrará ninguna aplicación en el menú Inicio como en el siguiente ejemplo: 

![Imagen del modo de quiosco que se muestra ahora cuando se produce un error.](images/hololens-kiosk-failure-behavior.png )

## Empezar a recibir compilaciones de Insider

En un dispositivo HoloLens 2, vaya a **configuración**  >  **Update & seguridad**de  >  **Windows Insider** y seleccione **Introducción**. Vincule la cuenta que usó para registrarse como Windows Insider.

Después, selecciona **desarrollo activo de Windows**, elige si deseas recibir las compilaciones de **canal** de **desarrollo** o beta, y revisa las condiciones del programa.

Seleccione **confirmar > reiniciar ahora** para finalizar. Después de reiniciar el dispositivo, vaya a **configuración > actualizar & seguridad > buscar actualizaciones** para obtener la compilación más reciente.

## FFU de descarga y de Flash
Para probar con un FFU firmado de vuelo, primero debe desbloquear el dispositivo antes de hacer parpadear la FFU con firma de vuelo.
1. En PC:

    1. Descarga FFU en tu PC desde [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Instale ARC (Asistente para recuperación avanzada) en Microsoft Store:[https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
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
