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
ms.openlocfilehash: e819dfb95a6735d0eae6287d97f5856856a33526
ms.sourcegitcommit: 7f48e7103f869a22a0d20a54dc8f9b708b22484c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "10963676"
---
# Versión preliminar de Insider para Microsoft HoloLens

Te agradecemos las compilaciones más recientes de Insider Preview para HoloLens. Es fácil [comenzar](hololens-insider.md#start-receiving-insider-builds) y proporciona comentarios valiosos para nuestra próxima actualización importante del sistema operativo para HoloLens.

## Notas de la versión de Windows Insider

A continuación encontrará una lista de las próximas características que puede probar hoy en nuestra compilación de Windows Insider.

| Característica                                                | Descripción                                                                                    | Disponible en compilaciones de Insider |
|--------------------------------------------------------|------------------------------------------------------------------------------------------------|-----------------------------|
| [Soporte de posición de ojos automático](hololens-insider.md#auto-eye-position-support)                              | Encuentra de forma activa posiciones de la vista y permite un posicionamiento preciso del holograma.                        | 19041.1339 +                 |
| [Administrador de certificados](hololens-insider.md#certificate-manager)                                     | Los usuarios pueden ver, instalar y quitar certificados certificados de usuario y de máquina local actuales en la aplicación configuración.                                         | 19041.1361 +                 |
| [Iniciar automáticamente el aprovisionamiento desde USB](hololens-insider.md#auto-launch-provisioning-from-usb)                      | OOBE detecta automáticamente paquetes de aprovisionamiento en unidades USB.                                | 19041.1361 +                 |
| [Confirmar automáticamente paquetes de aprovisionamiento en OOBE](hololens-insider.md#auto-confirm-provisioning-packages-in-oobe)             | Aplicar automáticamente paquetes de aprovisionamiento en OOBE.                                             | 19041.1361 +                 |
| [Usar el piloto automático con conexión Wi-Fi](hololens-insider.md#using-autopilot-with-wi-fi-connection)                  | Usa el autopiloto de la Wi-Fi del dispositivo sin necesidad de un adaptador Ethernet.                             | 19041.1364 +                 |
|[Tenantlockdown CSP y AutoPilot](hololens-insider.md#tenantlockdown-csp-and-autopilot) | Después de la inscripción al espacio empresarial y se aplica la policiy, el dispositivo solo se puede inscribir en ese inquilino siempre que el dispositivo se restablezca o se vuelva a parpadear. | 19041.1366 +|
| [Acceso asignado global](hololens-insider.md#global-assigned-access--kiosk-mode)                                 | Configure el dispositivo HoloLens 2 para el modo de pantalla completa de varias aplicaciones, que es aplicable en el nivel del sistema. | 19041.1356 +                 |
| [Iniciar automáticamente una aplicación en la pantalla completa de varias aplicaciones](hololens-insider.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                  | Configura una aplicación para que se inicie automáticamente al iniciar sesión en un modo quiosco de varias aplicaciones.     | 19041.1346 +                 |
| [Inicio de sesión automático de los visitantes para quioscos](hololens-insider.md#visitor-auto-logon-for-kiosks)                          | Permite que el inicio de sesión automático en las cuentas de visitante se use para los modos de pantalla completa.                         | 19041.1361 +                 |
| [Cambios en el comportamiento del modo de pantalla completa para el tratamiento de errores](hololens-insider.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Los cambios en la forma en que se maneja el error de modo quiosco.                                              | 19041.1356 +                 |
| [Directivas de HoloLens](hololens-insider.md#hololens-policies)                                      | Nuevas directivas para dispositivos de realidad mixta.                                                        | 19041.1349 +                 |
| [Caché de pertenencia a grupo AAD para el quiosco desconectado](hololens-insider.md#cache-aad-group-membership-for-offline-kiosk)           | Directiva sobre cuántos días se permite que la caché de pertenencia a grupos de AAD se use para el modo de pantalla completa.    | 19041.1356 +                 |
| [Nuevas directivas de restricción de dispositivo para HoloLens 2](hololens-insider.md#new-device-restriction-policies-for-hololens-2)         | Directivas de administración de dispositivos habilitadas recientemente para HoloLens 2.                               | 19041.1349 +                 |
| [Nuevas directivas de energía para HoloLens 2](hololens-insider.md#new-power-policies-for-hololens-2)                      | Directivas que se han admitido recientemente para la configuración del tiempo de espera.                                           | 19041.1349 +                 |
| [Actualizar directivas](hololens-insider.md#newly-enabled-update-policies-for-hololens)                                        | Directivas habilitadas recientemente que permiten controlar las actualizaciones.                                            | 19041.1352 +                 |
| [Visibilidad de la página de configuración habilitada para HoloLens 2](hololens-insider.md#enabled-settings-page-visibility-for-hololens-2)        | Directiva para elegir qué páginas se ven en la aplicación configuración.                                           | 19041.1349 +                 |
| [Mejoras y correcciones de la actualización](hololens-insider.md#improvements-and-fixes-in-the-update)                   | Correcciones adicionales de la actualización.                                                                | 19041.1361 +                 |

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

### Administrador de certificados

En Windows Insider Build 19041.1361 + estamos agregando un administrador de certificados en la aplicación de configuración de HoloLens 2. Vaya a **configuración > actualizar & certificados > de seguridad**. Esta característica proporciona una forma sencilla y fácil de usar para ver, instalar y quitar certificados en el dispositivo. Con el nuevo administrador de certificados, los administradores y los usuarios han mejorado las herramientas de auditoría, diagnóstico y validación para asegurarse de que los dispositivos siguen siendo seguros y cumplen con las normas. 

-   **Auditoría:** Posibilidad de validar que un certificado se ha implementado correctamente o para confirmar que se ha eliminado correctamente. 
-   **Diagnóstico:** Cuando surjan problemas, validar que los certificados adecuados existen en el dispositivo ahorra tiempo y ayuda con la solución de problemas. 
-   **Validación:** Comprobar que un certificado tiene el propósito pretendido y es funcional, puede ahorrar mucho tiempo, especialmente en entornos comerciales antes de implementar certificados a mayor escala.

Para buscar rápidamente un certificado específico en la lista, hay opciones para ordenar por nombre, almacén o fecha de expiración. Los usuarios también pueden buscar un certificado directamente. Para ver las propiedades de certificado individuales, seleccione el certificado y haga clic en **información**. 

La instalación de certificados admite actualmente archivos. cer y. CRT. Los propietarios de dispositivos pueden instalar certificados en la máquina local y en el usuario actual;  el resto de los usuarios solo pueden instalarse en el usuario actual. Los usuarios solo pueden quitar certificados instalados directamente desde la interfaz de usuario de configuración. Si se ha instalado un certificado por otros medios, también debe ser eliminado por el mismo mecanismo.

#### Para instalar un certificado: 

1.  Conecta tu HoloLens 2 a un equipo PC.
1.  Coloca el archivo de certificado que deseas instalar en una ubicación de tu HoloLens 2.
1.  Vaya a **configuración de la aplicación > actualizar & certificados > de seguridad**y seleccione instalar un certificado.
1.  Haga clic en **Importar archivo** y vaya a la ubicación donde guardó el certificado.
1.  Seleccione **Ubicación**de la tienda.
1.  Seleccione **almacén de certificados**.
1.  Haz clic en **Instalar**.

El certificado debe instalarse ahora en el dispositivo.

#### Para quitar un certificado: 
1. Vaya a **configuración > la actualización y los certificados de > de seguridad**.
1. Busque el certificado por el nombre en el cuadro de búsqueda.
1. Seleccione el certificado.
1. Haga clic en **quitar**
1. Seleccione **sí** cuando se le solicite confirmación.

![Visor de certificados de la aplicación configuración](images/certificate-viewer-device.jpg)

![Imagen que muestra cómo usar la interfaz de usuario de certificados para instalar un certificado](images/certificate-device-install.jpg)

### Iniciar automáticamente el aprovisionamiento desde USB
Antes de que los usuarios de la compilación tuvieran que iniciar la pantalla de aprovisionamiento de forma manual durante OOBE para aprovisionar mediante una combinación de botones. Ahora los usuarios pueden omitir la combinación de botones con un paquete de aprovisionamiento en una unidad de almacenamiento USB. 

1. Conecta la unidad USB con el paquete de aprovisionamiento durante el primer momento de interactuación de OOBE
1. Cuando el dispositivo esté listo para su aprovisionamiento, se abrirá automáticamente el mensaje con la página de aprovisionamiento. 

Nota: si se deja de conectar una unidad USB mientras se está iniciando el dispositivo, OOBE enumerará el dispositivo de almacenamiento USB existente, así como la posibilidad de que se conecten otros adicionales.

Para obtener más información sobre cómo aplicar paquetes de aprovisionamiento durante OOBE, siga leyendo [aquí](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

### Confirmar automáticamente paquetes de aprovisionamiento en OOBE
Cuando se enciende la pantalla principal de aprovisionamiento, OOBE contará hasta 10 segundos antes de comenzar a aplicar automáticamente todos los paquetes de aprovisionamiento. Los usuarios pueden confirmar o cancelar dentro de estos 10 segundos después de verificar los paquetes que esperaban.

### Aprovisionamiento automático sin usar la interfaz de usuario
Al combinar el inicio automático de la provisión de dispositivos USB y la confirmación automática de paquetes de aprovisionamiento, un usuario puede aprovisionar dispositivos HoloLens 2 automáticamente sin usar la interfaz de usuario del dispositivo ni siquiera con el dispositivo. Puede seguir usando la misma unidad USB y el mismo paquete de aprovisionamiento para varios dispositivos. Esto es útil para implementar varios dispositivos a la vez en la misma área. 

1. [Crear un paquete de aprovisionamiento](hololens-provisioning.md) con el [Diseñador de configuración de Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Copie el paquete en una unidad de almacenamiento USB.
1. [Flashe tu HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) a [19041,1361 o una compilación más reciente](https://aka.ms/hololens2previewdownload). 
1. Cuando el [Asistente de recuperación avanzada](https://www.microsoft.com/store/productId/9P74Z35SFRS8) ha completado el parpadeo del dispositivo, desconecte el cable USB-C. 
1. Conecta tu unidad USB al dispositivo.
1. Cuando el dispositivo HoloLens 2 se inicie en OOBE, detectará automáticamente el paquete de aprovisionamiento en la unidad USB e iniciará la página de aprovisionamiento.
1. Después de 10 segundos, el dispositivo aplicará automáticamente el paquete de aprovisionamiento. 

El dispositivo ya está configurado y mostrará la pantalla de aprovisionamiento correcto.

### Usar el piloto automático con conexión Wi-Fi
Ahora, durante la OOBE, una vez que conecte HoloLens 2 con WiFi, OOBE buscará un perfil de AutoPilot para el dispositivo. Si se encuentra alguno, se usará para completar el resto de la Unión de AAD y el flujo de inscripción. En otras palabras, el uso de Ethernet a USB C o WiFi a USB C no es un requisito, aunque seguirá funcionando si se proporciona al principio de OOBE. Más información sobre el [autopiloto para dispositivos HoloLens 2](hololens2-autopilot.md).

### Tenantlockdown CSP y AutoPilot
Los dispositivos HoloLens 2 ahora son compatibles con TenantLockdown CSP a partir de la compilación de Windows Insider 19041.1366 +. 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP permite que HoloLens 2 se desvinculará a la inscripción de MDM solo con AutoPilot. Una vez que el nodo RequireNetworkInOOBE de TenantLockdown CSP se establece en verdadero o falso (establecido inicialmente) el valor en HoloLens 2, ese valor permanece en el dispositivo a pesar de que se vuelvan a parpadear, las actualizaciones del sistema operativo, etc. 

Una vez que el nodo RequireNetworkInOOBE TenantLockdown de CSP se establezca en verdadero en HoloLens 2, OOBE espera indefinidamente que el perfil de autopiloto se descargue y se aplique correctamente, después de la conectividad de red. 

Una vez que el nodo RequireNetworkInOOBE TenantLockdown de CSP se establece en true en HoloLens 2, no se permiten las siguientes operaciones en OOBE: 
- Crear usuarios locales mediante aprovisionamiento en tiempo de ejecución 
- Realizando operación de unión de AAD mediante aprovisionamiento en tiempo de ejecución 
- Selección de quién es el propietario del dispositivo en la experiencia de OOBE 

#### ¿Cómo se establece esta configuración con Intune? 
1. Cree un perfil de configuración de dispositivo URI OMA personalizado y especifique verdadero para el nodo RequireNetworkInOOBE como se muestra a continuación.
El valor OMA-URI debe ser. ![ configuración de/Vendor/msft/TenantLockdown/RequireNetworkInOOBE inquilinos bloqueo por OMA-URI](images/hololens-tenant-lockdown.png)
1. Crear un grupo y asignar el perfil de configuración del dispositivo a ese grupo de dispositivos. 
1. Haga que el miembro del dispositivo HoloLens 2 del grupo creado en el paso anterior y desencadene la sincronización.  

Compruebe en el portal de Intune que la configuración del dispositivo se aplicó correctamente. Una vez que la configuración del dispositivo se aplique correctamente en el dispositivo Hololens 2, los efectos de TenantLockdown estarán activos.

#### ¿Cómo anular la RequireNetworkInOOBE de TenantLockdown en HoloLens 2 con Intune? 
1. Quita la HoloLens 2 del grupo de dispositivos en el que se asignó previamente la configuración de dispositivo creada anteriormente. 
1. Cree un perfil de configuración de dispositivo basado en URI de OMA personalizado y especifique falso para RequireNetworkInOOBE como se muestra a continuación. El valor OMA-URI debe ser./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE ![ captura de pantalla de la configuración de RequireNetworkInOOBE a falso a través del URI de OMA en Intune](images/hololens-tenant-lockdown-false.png)
1. Crear un grupo y asignar el perfil de configuración del dispositivo a ese grupo de dispositivos. 
1. Haga que el miembro del dispositivo HoloLens 2 del grupo creado en el paso anterior y desencadene la sincronización.

Compruebe en el portal de Intune que la configuración del dispositivo se aplicó correctamente. Una vez que la configuración del dispositivo se aplique correctamente en el dispositivo Hololens 2, los efectos de TenantLockdown estarán inactivos. 

#### ¿Qué sucedería durante la OOBE? si el perfil de autopiloto no está asignado a HoloLens después de que TenantLockdown se hubiera establecido en true? 
OOBE esperará indefinidamente que se descargue el perfil de AutoPilot y el siguiente cuadro de diálogo. Para quitar los efectos de TenantLockdown, el dispositivo debe estar inscrito primero con su inquilino original solo con el piloto automático y RequireNetworkInOOBE debe ser no establecido como se describe en el paso anterior antes de que se quiten las restricciones introducidas por TenantLockdown CSP. 

![Vista en el dispositivo para cuando se aplica la Directiva en el dispositivo.](images/hololens-autopilot-lockdown.png)

### Acceso asignado global: modo de pantalla completa
Esta nueva característica permite que un administrador de ti configure un dispositivo HoloLens 2 para el modo de pantalla completa de varias aplicaciones, que es aplicable en el nivel del sistema, no tiene afinidad con ninguna identidad en el sistema y se aplica a todos los usuarios que inician sesión en el dispositivo. [Aquí encontrará](hololens-global-assigned-access-kiosk.md)información sobre esta nueva característica.

### Inicio automático de una aplicación en el modo de pantalla completa de varias aplicaciones 
Solo se aplica al modo de pantalla completa de varias aplicaciones y solo se puede designar una aplicación para iniciar automáticamente con el atributo resaltado a continuación en la configuración de acceso asignada. 

La aplicación se inicia automáticamente cuando el usuario inicia sesión. 

```xml
<AllowedApps>                     
    <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Inicio de sesión automático de los visitantes en quioscos
Esta nueva característica permite que el inicio de sesión automático en las cuentas de visitante se use para los modos de pantalla completa. 

Para una configuración no de AAD, para configurar un dispositivo para el inicio de sesión automático de los visitantes:
1.  Crear un paquete de aprovisionamiento que:
    1.  Configura la **configuración de tiempo de ejecución/AssignedAccess** para permitir cuentas de visitante.
    1.  De manera opcional, el dispositivo se puede inscribir en MDM **(configuración de tiempo de ejecución/área de trabajo/inscripciones)** para que pueda administrarse más adelante.
    1.  No crear una cuenta local
1.  [Aplicar el paquete de aprovisionamiento](hololens-provisioning.md).

En el caso de una configuración de AAD, los usuarios pueden lograr algo similar a este día sin realizar este cambio. Los dispositivos Unidos a AAD configurados para el modo de quiosco pueden iniciar sesión en una cuenta de visitante con un solo toque de botón en la pantalla de inicio de sesión. Una vez que haya iniciado sesión en la cuenta de visitante, el dispositivo no volverá a solicitar que se inicie sesión de nuevo hasta que el visitante se haya cerrado de forma explícita desde el menú Inicio o se reinicie el dispositivo.

### Cambios en el comportamiento del modo de pantalla completa para el tratamiento de errores

Antes de encontrar errores al aplicar el modo de pantalla completa, HoloLens se usó para mostrar todas las aplicaciones en el menú Inicio. A partir de esta compilación de Windows Insider, en caso de errores, no se mostrará ninguna aplicación en el menú Inicio como en el siguiente ejemplo: 

![Imagen del modo de quiosco que se muestra ahora cuando se produce un error.](images/hololens-kiosk-failure-behavior.png )

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

Name: AADGroupMembershipCacheValidityInDays URI Value:./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min-0 días  
Máximo: 60 días 

Pasos para usar esta directiva correctamente: 
1. Cree un perfil de configuración de dispositivo para quiosco dirigido a grupos de AAD y asígnelo a dispositivos HoloLens. 
1. Crear un URI de OMA personalizado configuración de dispositivo que establezca este valor de directiva en cantidad deseada de días (> 0) y asignarlo a dispositivos HoloLens. 
    1. El valor del URI debe especificarse en el cuadro de texto OMA-URI como./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. El valor puede estar entre Min/Max permitidos.
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
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

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

Para saber qué configuración de página puede personalizar en HoloLens 2, visite nuestra [Página de URI de configuración](settings-uri-list.md). 
 
![Captura de pantalla de horas activas que se están modificando en la aplicación configuración](images/hololens-page-visibility-list.jpg)

### Mejoras y correcciones de la actualización:
- Directiva actualizada para deshabilitar la enumeración de las funciones USB a través de MDM para NCM para AllowUsbConnection.
- Más pantallas de OOBE ahora están en modo oscuro.
- Más información debería apuntar a la última declaración de privacidad en línea.
- Se solucionó un problema en el que los usuarios no podían suministrar perfiles de VPN mediante paquetes de aprovisionamiento.
- Se ha corregido un problema que impedía que un dispositivo HoloLens se mostrara en el explorador de archivos sobre el protocolo de transferencia multimedia (MTP) cuando el dispositivo está configurado como una [pantalla completa de la aplicación](hololens-kiosk.md). Tenga en cuenta que se puede deshabilitar MTP (y conexión USB en general) usando la directiva [AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) .

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
