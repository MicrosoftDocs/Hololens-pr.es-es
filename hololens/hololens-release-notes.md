---
title: Notas de la versión de HoloLens 2
description: Obtén más información sobre las actualizaciones en cada nueva versión de HoloLens 2.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/10/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: df8d6e2c00bd8ff8507be4a2fd58c773d8833c11
ms.sourcegitcommit: 20ff249e3570c74f62cdf6339c8be76c401d9f4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2020
ms.locfileid: "11165968"
---
# Notas de la versión de HoloLens 2

Para asegurarte de tener una experiencia productiva con tus dispositivos HoloLens, continuamos publicando características, errores y actualizaciones de seguridad. En esta página, puedes ver las novedades de HoloLens cada mes. Para obtener la última actualización de HoloLens 2, puede [comprobar si hay actualizaciones y actualizar manualmente](hololens-update-hololens.md#check-for-updates-and-manually-update) o [Descargar](https://aka.ms/hololens2download)la actualización Flash completa (FFU) para que [parpadee el dispositivo a través del asistente de recuperación avanzada](hololens-recovery.md#clean-reflash-the-device). La descarga se mantiene actualizada y proporciona la última versión disponible general.

>[!NOTE]
> Para leer las notas de la versión del emulador de HoloLens, [visita el archivo](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive).

## Windows Holographic, versión 20H2
- Compilación 19041,1128

Windows Holographic, versión 20H2 ahora está disponible y ofrece un excelente conjunto de características nuevas para los usuarios de HoloLens 2 y los profesionales de ti. Desde la colocación de la vista automática, hasta el administrador de certificados de configuración, hasta la funcionalidad de modo de pantalla completa y nuevas capacidades de configuración de autopiloto. Esta nueva actualización permite que los equipos de ti tomen un control más granular sobre la configuración y la administración de dispositivos HoloLens, y ofrece a los usuarios una experiencia holográfica aún más sencilla. 

Esta última versión es una actualización mensual de la versión 2004, pero esta vez incluimos nuevas características. El número de compilación más importante permanecerá igual y Windows Update indicará una versión mensual de la versión 2004 (compilación 19041). Puede consultar el número de compilación en su configuración > acerca de la pantalla para confirmar que está en la última versión de compilación 19041.1128 +. Para actualizar a la última versión, abra la aplicación configuración, vaya a actualizar & seguridad y pulse buscar actualizaciones. Para obtener más información sobre cómo administrar las actualizaciones de HoloLens, visite [esta página](https://docs.microsoft.com/hololens/hololens-updates).

### Novedades de Windows Holographic, versión 20H2  

| Característica                                              | Descripción                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Soporte de posición de ojos automático](hololens-release-notes.md#auto-eye-position-support) | Calcula de forma activa las posiciones de la vista sin que los usuarios pasen por la calibración de seguimiento ocular.   |
| [Administrador de certificados](hololens-release-notes.md#certificate-manager)   | Permite nuevos métodos más sencillos para instalar y quitar certificados de la aplicación configuración.     |
| [Iniciar automáticamente el aprovisionamiento desde USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Los paquetes de aprovisionamiento de las unidades USB se solicitan automáticamente a la página de configuración de OOBE.                                                         |
| [Confirmar automáticamente paquetes de aprovisionamiento en OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Los paquetes de aprovisionamiento se aplican automáticamente durante OOBE desde la página de aprovisionamiento.                                                         |
| [Aprovisionamiento automático sin usar la interfaz de usuario](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Cómo combinar el inicio automático de aprovisionamiento y la confirmación automática juntos. |
| [Usar el piloto automático con conexión de Wi-Fi](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Usa AutoPilot desde Wi-Fi de dispositivos sin necesidad de un adaptador Ethernet. |
| [Tenantlockdown CSP y AutoPilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Después de que se aplique la inscripción a inquilinos y la Directiva, el dispositivo solo se puede inscribir en ese inquilino en cualquier momento en que el dispositivo se restablezca o vuelva a parpadear. |
| [Acceso asignado global](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Nuevo método de configuración para el modo de pantalla completa de varias aplicaciones que aplica el quiosco en el nivel del sistema, lo que hace que sea aplicable a todos.                  |
| [Iniciar automáticamente una aplicación en la pantalla completa de varias aplicaciones](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Configura una aplicación para que se inicie automáticamente al iniciar sesión en un modo quiosco de varias aplicaciones.                                                        |
| [Cambios en el comportamiento del modo de pantalla completa para el tratamiento de errores](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | El error en el modo de quiosco ahora tiene un retroceso restrictivo.                                                                                                |
| [Directivas de HoloLens](hololens-release-notes.md#hololens-policies)                                    | Nuevas directivas para HoloLens.     |
| [Caché de pertenencia a grupo AAD para el quiosco desconectado](hololens-release-notes.md#cache-aad-group-membership-for-offline-kiosk)         | La nueva directiva permite a los usuarios usar la caché de pertenencia a grupos para usar el modo de pantalla completa durante el número de días establecido.                                        |
| [Nuevas directivas de restricción de dispositivo para HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Directivas de administración de dispositivos habilitadas recientemente para HoloLens 2.                                                                                |
| [Nuevas directivas de energía para HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Directivas que se han admitido recientemente para la configuración del tiempo de espera.  |
| [Actualizar directivas](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Directivas habilitadas recientemente que permiten controlar las actualizaciones.           |
| [Visibilidad de la página de configuración habilitada para HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Directiva para elegir qué páginas se ven en la aplicación configuración.             |
| [Modo de investigación](hololens-release-notes.md#research-mode) | Usar el modo de referencia en HoloLens 2. |
| [Aumento de la longitud de grabación](hololens-release-notes.md#recording-length-increased) | Las grabaciones de MRC ya no se limitan a 5 minutos. |
| [Mejoras y correcciones de la actualización](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Correcciones adicionales de la actualización.   |

### Soporte de posición de ojos automático

En HoloLens 2, las posiciones de ojo permiten un posicionamiento preciso del holograma, una experiencia de visualización cómoda y una mejor calidad de visualización. Las posiciones de los ojos se calculan internamente como parte del cálculo del seguimiento ocular. Sin embargo, esto requiere que cada usuario Revise la calibración del seguimiento de los ojos, incluso cuando la experiencia podría no requerir una entrada de la vista.

La **posición de ojo automático (AEP)** permite que estos escenarios tengan una forma sin interacción que calcule las posiciones de la vista para el usuario. La posición del ojo automático comienza a funcionar en segundo plano automáticamente desde el momento en el que el usuario coloca el dispositivo. Si el usuario no tiene una calibración de seguimiento de ojos anteriores, la posición de la vista automática comenzará a proporcionar las posiciones de ojo del usuario en el sistema de visualización después de un tiempo de procesamiento de 20-30 segundos. Los datos de usuario no se conservan en el dispositivo y, por lo tanto, este proceso se repite si el usuario desconecta y vuelve a poner el dispositivo o si el dispositivo se reinicia o se reactiva desde la suspensión.

Hay algunos cambios en el comportamiento del sistema con la característica posición del ojo automático cuando un usuario no calibrado coloca el dispositivo. En este contexto, un usuario no calibrado se refiere a una persona que no ha realizado el proceso de calibración de seguimiento en el dispositivo anteriormente.

| Aplicación activa | Comportamiento anterior | Comportamiento de Windows Holographic, versión 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Aplicación no habilitada para la mirada o shell holográfica |Se muestra el cuadro de diálogo de solicitud de calibración de seguimiento ocular. | No se muestra ningún mensaje. |
| Aplicación de fijamente | Se muestra el cuadro de diálogo de solicitud de calibración de seguimiento ocular. | La pregunta de calibración de seguimiento ocular se muestra solo cuando la aplicación accede a la secuencia de ojo. |

Si el usuario realiza una transición de una aplicación con la opción de no estar habilitada a una persona que tiene acceso a los datos de fijamente, se mostrará la solicitud de calibración. 

El resto del comportamiento del sistema será similar cuando el usuario actual no tiene una calibración de seguimiento ocular activa. Por ejemplo, el gesto de inicio de una sola mano no estará habilitado. No se cambiará la experiencia de configuración rápida para la configuración inicial.

Para experiencias que requieren datos de ojo ocular o posicionamiento de hologramas muy precisos, recomendamos a los usuarios no calibrados que ejecuten la calibración de seguimiento de ojos. Es accesible desde la solicitud de calibración de seguimiento ocular o iniciando la aplicación configuración desde el menú Inicio y, a continuación, seleccionando **calibración de > del sistema > calibración de ojos > la calibración**de la vista.

Esta información puede encontrarse más adelante con [otra información de calibración](hololens-calibration.md#auto-eye-position-support). 

### Administrador de certificados

- Auditoría, diagnóstico y herramientas de validación mejoradas para la seguridad y el cumplimiento de los dispositivos a través del nuevo administrador de certificados. Esta capacidad le permitirá implementar, solucionar problemas y validar sus certificados a escala en entornos comerciales.

En Windows Holographic versión 20H2, agregamos un administrador de certificados en la aplicación de configuración de HoloLens 2. Vaya a **configuración > actualizar & certificados > de seguridad**. Esta característica proporciona una forma sencilla y fácil de usar para ver, instalar y quitar certificados en el dispositivo. Con el nuevo administrador de certificados, los administradores y los usuarios han mejorado las herramientas de auditoría, diagnóstico y validación para asegurarse de que los dispositivos siguen siendo seguros y cumplen con las normas. 

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

Esta información puede encontrarse más adelante [en una nueva página del administrador de certificados](certificate-manager.md).

### Iniciar automáticamente el aprovisionamiento desde USB

- Procesos automatizados que permiten una interacción mínima con el usuario, cuando se usan unidades USB con paquetes de aprovisionamiento durante OOBE.

Antes de esta versión, los usuarios tuvieron que iniciar la pantalla de aprovisionamiento manualmente durante el uso de OOBE para aprovisionar con una combinación de botones. Ahora los usuarios pueden omitir la combinación de botones con un paquete de aprovisionamiento en una unidad de almacenamiento USB. 

1. Conecta la unidad USB con el paquete de aprovisionamiento durante el primer momento de interactuación de OOBE
1. Cuando el dispositivo esté listo para su aprovisionamiento, se abrirá automáticamente el mensaje con la página de aprovisionamiento. 

Nota: si se deja de conectar una unidad USB mientras se está iniciando el dispositivo, OOBE enumerará el dispositivo de almacenamiento USB existente, así como la posibilidad de que se conecten otros adicionales.

Para obtener más información sobre cómo aplicar paquetes de aprovisionamiento durante OOBE, siga leyendo [aquí](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

Esta información puede encontrarse más adelante [.](hololens-provisioning.md#auto-launch-provisioning-from-usb)

### Confirmar automáticamente paquetes de aprovisionamiento en OOBE
- Proceso automatizado que permite menos interacción del usuario, cuando se muestra la página del paquete de aprovisionamiento, se aplicarán automáticamente todos los paquetes que aparecen en la lista.

Cuando se enciende la pantalla principal de aprovisionamiento, OOBE contará hasta 10 segundos antes de comenzar a aplicar automáticamente todos los paquetes de aprovisionamiento. Los usuarios pueden confirmar o cancelar dentro de estos 10 segundos después de verificar los paquetes que esperaban.

Esta información puede encontrarse más adelante [.](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)

### Aprovisionamiento automático sin usar la interfaz de usuario
- Procesos automáticos combinados para reducir las interacciones del dispositivo para el aprovisionamiento. 

Al combinar el inicio automático de la provisión de dispositivos USB y la confirmación automática de paquetes de aprovisionamiento, un usuario puede aprovisionar dispositivos HoloLens 2 automáticamente sin usar la interfaz de usuario del dispositivo ni siquiera con el dispositivo. Puede seguir usando la misma unidad USB y el mismo paquete de aprovisionamiento para varios dispositivos. Esto es útil para implementar varios dispositivos a la vez en la misma área. 

1. [Crear un paquete de aprovisionamiento](hololens-provisioning.md) con el [Diseñador de configuración de Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Copie el paquete en una unidad de almacenamiento USB.
1. [Flashe tu HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) a [19041,1361 o una compilación más reciente](https://aka.ms/hololens2previewdownload). 
1. Cuando el [Asistente de recuperación avanzada](https://www.microsoft.com/store/productId/9P74Z35SFRS8) ha completado el parpadeo del dispositivo, desconecte el cable USB-C. 
1. Conecta tu unidad USB al dispositivo.
1. Cuando el dispositivo HoloLens 2 se inicie en OOBE, detectará automáticamente el paquete de aprovisionamiento en la unidad USB e iniciará la página de aprovisionamiento.
1. Después de 10 segundos, el dispositivo aplicará automáticamente el paquete de aprovisionamiento. 

El dispositivo ya está configurado y mostrará la pantalla de aprovisionamiento correcto.

Esta información puede encontrarse más adelante [.](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### Usar el piloto automático con conexión de Wi-Fi
- Se ha eliminado la necesidad de adaptadores USB-C para reducir las necesidades de hardware, ya que permite que el piloto automático funcione en Wi-Fi dispositivos conectados.

Ahora, durante la OOBE, una vez que conecte HoloLens 2 con WiFi, OOBE buscará un perfil de AutoPilot para el dispositivo. Si se encuentra alguno, se usará para completar el resto de la Unión de AAD y el flujo de inscripción. En otras palabras, el uso de Ethernet a USB-C o Wi-Fi al adaptador USB-C no es necesario, aunque siga funcionando si se proporciona al principio de OOBE. Más información sobre el [autopiloto para dispositivos HoloLens 2](hololens2-autopilot.md).

### Tenantlockdown CSP y AutoPilot
- Mantiene los dispositivos en el espacio empresarial de la organización al bloquearlos en el inquilino, incluso a través del restablecimiento del dispositivo o el reflash. Con mayor seguridad, deshabilitando la creación de cuentas en el suministro. 

Los dispositivos HoloLens 2 ahora son compatibles con TenantLockdown CSP en la [versión de Windows Holographic 20H2](hololens-release-notes.md#windows-holographic-version-20h2). 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP permite que HoloLens 2 se desvinculará a la inscripción de MDM solo con AutoPilot. Una vez que el nodo RequireNetworkInOOBE de TenantLockdown CSP se establece en verdadero o falso (establecido inicialmente) el valor en HoloLens 2, ese valor permanece en el dispositivo a pesar de que se vuelvan a parpadear, las actualizaciones del sistema operativo, etc. 

Una vez que el nodo RequireNetworkInOOBE TenantLockdown de CSP se establezca en verdadero en HoloLens 2, OOBE espera indefinidamente que el perfil de autopiloto se descargue y se aplique correctamente, después de la conectividad de red. 

Una vez que el nodo RequireNetworkInOOBE TenantLockdown de CSP se establece en true en HoloLens 2, no se permiten las siguientes operaciones en OOBE: 
- Crear usuarios locales mediante aprovisionamiento en tiempo de ejecución 
- Realizando operación de unión de AAD mediante aprovisionamiento en tiempo de ejecución 
- Selección de quién es el propietario del dispositivo en la experiencia de OOBE 

#### ¿Cómo se establece esta configuración con Intune? 
1. Cree un perfil de configuración de dispositivo URI OMA personalizado y especifique verdadero para el nodo RequireNetworkInOOBE como se muestra a continuación.
El valor OMA-URI debe ser./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Configuración del bloqueo de inquilinos a través de OMA-URI](images/hololens-tenant-lockdown.png)

1. Crear un grupo y asignar el perfil de configuración del dispositivo a ese grupo de dispositivos. 

1. Haga que el miembro del dispositivo HoloLens 2 del grupo creado en el paso anterior y desencadene la sincronización.  

Compruebe en el portal de Intune que la configuración del dispositivo se aplicó correctamente. Una vez que la configuración del dispositivo se aplique correctamente en el dispositivo HoloLens 2, los efectos de TenantLockdown estarán activos.

#### ¿Cómo anular la RequireNetworkInOOBE de TenantLockdown en HoloLens 2 con Intune? 
1. Quita la HoloLens 2 del grupo de dispositivos en el que se asignó previamente la configuración de dispositivo creada anteriormente. 

1. Cree un perfil de configuración de dispositivo basado en URI de OMA personalizado y especifique falso para RequireNetworkInOOBE como se muestra a continuación. El valor OMA-URI debe ser./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla de la configuración de RequireNetworkInOOBE en falso a través del URI de OMA en Intune](images/hololens-tenant-lockdown-false.png)

1. Crear un grupo y asignar el perfil de configuración del dispositivo a ese grupo de dispositivos. 

1. Haga que el miembro del dispositivo HoloLens 2 del grupo creado en el paso anterior y desencadene la sincronización.

Compruebe en el portal de Intune que la configuración del dispositivo se aplicó correctamente. Una vez que la configuración del dispositivo se aplique correctamente en el dispositivo HoloLens 2, los efectos de TenantLockdown estarán inactivos. 

#### ¿Qué sucedería durante la OOBE? si el perfil de autopiloto no está asignado a HoloLens después de que TenantLockdown se hubiera establecido en true? 
OOBE esperará indefinidamente que se descargue el perfil de AutoPilot y el siguiente cuadro de diálogo. Para quitar los efectos de TenantLockdown, el dispositivo debe estar inscrito primero con su inquilino original solo con el piloto automático y RequireNetworkInOOBE debe ser no establecido como se describe en el paso anterior antes de que se quiten las restricciones introducidas por TenantLockdown CSP. 

![Vista en el dispositivo para cuando se aplica la Directiva en el dispositivo.](images/hololens-autopilot-lockdown.png)

Esta información puede encontrarse junto al resto del autopiloto en [TENANTLOCKDOWN CSP y AutoPilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot).

### Acceso asignado global: modo de pantalla completa
- Se redujo la administración de identidades de quiosco al habilitar el nuevo método quiosco que aplica el modo de pantalla completa en el nivel del sistema.

Esta nueva característica permite que un administrador de ti configure un dispositivo HoloLens 2 para el modo de pantalla completa de varias aplicaciones, que es aplicable en el nivel del sistema, no tiene afinidad con ninguna identidad en el sistema y se aplica a todos los usuarios que inician sesión en el dispositivo. [Aquí encontrará](hololens-global-assigned-access-kiosk.md)información sobre esta nueva característica.

### Inicio automático de una aplicación en el modo de pantalla completa de varias aplicaciones 
- Experiencia focalizada con el inicio automático de aplicaciones, el aumento de las selecciones de la interfaz de usuario y aplicaciones elegidas para las experiencias en modo de pantalla completa.

Solo se aplica al modo de pantalla completa de varias aplicaciones y solo se puede designar una aplicación para iniciar automáticamente con el atributo resaltado a continuación en la configuración de acceso asignada. 

La aplicación se inicia automáticamente cuando el usuario inicia sesión. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Cambios en el comportamiento del modo de pantalla completa para el tratamiento de errores
- Modo de pantalla completa más seguro eliminando las aplicaciones disponibles en errores de modo quiosco. 

Antes de encontrar errores al aplicar el modo de pantalla completa, HoloLens se usó para mostrar todas las aplicaciones en el menú Inicio. Ahora, en Windows Holographic versión 20H2, en caso de errores, no se mostrará ninguna aplicación en el menú Inicio como se indica a continuación: 

![Imagen del modo de quiosco que se muestra ahora cuando se produce un error.](images/hololens-kiosk-failure-behavior.png )

### Directivas de HoloLens
- Opciones de administración de dispositivos específicamente para HoloLens creadas para administrar el dispositivo. 

Se han creado nuevas directivas de realidad mixta para dispositivos HoloLens 2 en Windows Holographic versión 20H2. La nueva configuración controlable incluye: configuración del brillo, configuración del volumen, desactivación de la grabación de audio en capturas de realidad mixta, configuración de los diagnósticos y caché de pertenencia a grupos de AAD.  

| Nueva política de HoloLens                                | Descripción                                                                               | Notas                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Permite que los botones de brillo estén deshabilitados y, al presionarlos, no cambie el brillo.       | 1 sí, 0 no (valor predeterminado)                                                |
| MixedReality\VolumeButtonDisabled                  | Permite que los botones de volumen estén deshabilitados para que, al presionarlos, no cambie el volumen.               | 1 sí, 0 no (valor predeterminado)                                                |
| MixedReality\MicrophoneDisabled                    | Desactiva el micrófono para que no se pueda grabar audio en HoloLens 2.                      | 1 sí, 0 no (valor predeterminado)                                                |
| MixedReality\FallbackDiagnostics                   | Controla el comportamiento del momento en que se pueden recopilar los registros de diagnóstico.                               | 0 deshabilitado, 1 habilitado para propietarios de dispositivos, 2 habilitado para todos (predeterminado) |
| MixedReality\HeadTrackingMode                      | Reservado para uso futuro.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Controla la cantidad de días en que se usa la caché de pertenencia a grupos de AAD para quioscos segmentados. | Consulta a continuación.                                                           |

### Caché de pertenencia a grupo AAD para el quiosco desconectado
- Se habilitaron quioscos sin conexión para usarlos con grupos de AAD durante un máximo de 60 días.

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
> Hasta que se realice el paso 4 para un usuario de AAD experimentará un comportamiento de error mencionado en entornos "desconectados". 

### Nuevas directivas de restricción de dispositivo para HoloLens 2
- Permite a los usuarios administrar directivas específicas de administración de dispositivos, como bloquear la adición o eliminación de paquetes de aprovisionamiento.

Directivas habilitadas recientemente que permiten más opciones de administración de los dispositivos HoloLens 2. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Estas dos nuevas directivas para AllowAddProvisioningPackage y AllowRemoveProvisioningPackage se agregan a nuestras [restricciones de dispositivo comunes](hololens-common-device-restrictions.md).

### Nuevas directivas de energía para HoloLens 2
- Más opciones para cuando HoloLens se suspende o se bloquea mediante directivas de energía. 

Estas directivas recién agregadas permiten a los administradores controlar Estados de energía, como el tiempo de espera de inactividad. Para obtener más información sobre cada directiva individual, haga clic en el vínculo de esa Directiva.

|     Vínculo de documentación de Directiva                |     Notas                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Valor de ejemplo para usar en el diseñador de configuración de Windows, es decir,  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Valor de ejemplo para usar en el diseñador de configuración de Windows, es decir,  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Valor de ejemplo para usar en el diseñador de configuración de Windows, es decir, 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Valor de ejemplo para usar en el diseñador de configuración de Windows, es decir, 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Valor de ejemplo para usar en el diseñador de configuración de Windows, es decir,   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Valor de ejemplo para usar en el diseñador de configuración de Windows, es decir,  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Estas dos nuevas directivas para DisplayOffTimeoutOnBattery y DisplayOffTimeoutPluggedIn se agregan a nuestras [restricciones de dispositivo comunes](hololens-common-device-restrictions.md).

> [!NOTE]
> Para una experiencia coherente en HoloLens 2, asegúrate de que los valores tanto de DisplayOffTimeoutOnBattery como de StandbyTimeoutOnBattery estén establecidos con el mismo valor. Lo mismo se aplica a DisplayOffTimeoutPluggedIn y StandbyTimeoutPluggedIn. Para obtener más información sobre el modo de espera moderno, consulte [temporizadores de inactividad de mostrar, suspender y hibernar](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) .

### Nuevas directivas de actualización habilitadas para HoloLens
- Más opciones para las actualizaciones instaladas o deshabilitar el botón pausar actualizaciones para garantizar las actualizaciones.

Estas directivas de actualización ahora están habilitadas en los dispositivos HoloLens 2:
-   [Actualizar/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Actualizar/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Actualizar/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Actualizar/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Los detalles completos de estas directivas de actualización y cómo usarlas para dispositivos HoloLens pueden leerse aquí en [administrar las actualizaciones de hololens](hololens-updates.md).

### Visibilidad de la página de configuración habilitada para HoloLens 2
- Se ha aumentado el control de la interfaz de usuario en la aplicación configuración, lo cual puede confundirse para mostrar una selección limitada de páginas.

Hemos habilitado una directiva que permite a los administradores de ti evitar que determinadas páginas de la aplicación configuración del sistema sean visibles o accesibles, o para hacerlo en todas las páginas excepto en las especificadas. Para obtener información sobre cómo personalizar completamente esta característica, haz clic en el vínculo a continuación.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Para saber qué configuración de página puede personalizar en HoloLens 2, visite nuestra [Página de URI de configuración](settings-uri-list.md). 
 
![Captura de pantalla de la modificación de las horas activas en la aplicación Configuración](images/hololens-page-visibility-list.jpg)

### Modo de investigación
Mientras se encuentre en el modo de investigación, HoloLens 2 es una herramienta potente para la investigación de la visión del equipo. Comparado con las ediciones anteriores, el modo de estudio para HoloLens 2 tiene las siguientes ventajas:
-   Además de los sensores expuestos en el modo de investigación de HoloLens (1. ª gen), ahora ofrecemos el acceso a un sensor de IMU, entre ellos, el acelerómetro, el Gyroscope y el magnetómetro.
-   HoloLens 2 proporciona nuevas funciones que se pueden usar conjuntamente con el modo de investigación. En concreto, accede a las API de seguimiento manual y seguimiento de ojos articulados que pueden ofrecer un conjunto de experimentos más rico.

Ahora, los investigadores tienen la opción de habilitar el modo de referencia en sus dispositivos HoloLens para acceder a todas estas secuencias de sensores de imágenes RAW orientadas externamente. El modo de investigación para HoloLens 2 también proporciona acceso a las lecturas de acelerómetro, Gyroscope y magnetómetro. Para proteger la privacidad de los usuarios, las imágenes de cámara con seguimiento sin formato no están disponibles en el modo referencia, pero la dirección de ojo está disponible a través de API existentes.

Consulte la [documentación del modo de investigación](https://docs.microsoft.com/windows/mixed-reality/research-mode) para obtener más información técnica.

### Aumento de la longitud de grabación
Debido a los comentarios de los clientes, hemos aumentado la duración de la grabación de [capturas de realidad mixta](holographic-photos-and-videos.md). De forma predeterminada, las capturas de realidad mixta ya no se limitarán a 5 minutos, sino que calcularán la longitud máxima de grabación en función del espacio disponible en el disco. El dispositivo calculará la duración de la grabación de video máxima en función del espacio disponible en disco hasta el 80% del espacio total en el disco.

> [!NOTE]
> HoloLens usará la duración de grabación de video predeterminada (5 minutos) si se produce una de las siguientes situaciones:
> - La duración estimada de grabación máxima es inferior a los 5 minutos predeterminados.
> - El espacio en disco disponible es menor del 20% del espacio total en el disco.

Esta información se puede encontrar de nuevo [aquí](holographic-photos-and-videos.md#maximum-recording-length). 

### Mejoras y correcciones de la actualización:
- Más pantallas de OOBE ahora están en modo oscuro.
- Más información debería apuntar a la última declaración de privacidad en línea.
- Se solucionó un problema en el que los usuarios no podían suministrar perfiles de VPN mediante paquetes de aprovisionamiento.
- Problema de configuración de proxy fijo para la conexión VPN.
- Directiva actualizada para deshabilitar la enumeración de las funciones USB a través de MDM para NCM para AllowUsbConnection.
- Se ha corregido un problema que impedía que un dispositivo HoloLens se mostrara en el explorador de archivos sobre el protocolo de transferencia multimedia (MTP) cuando el dispositivo está configurado como una [pantalla completa de la aplicación](hololens-kiosk.md). Tenga en cuenta que se puede deshabilitar MTP (y conexión USB en general) usando la directiva [AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) .
- Se ha corregido un problema que causaba que los iconos del menú Inicio se ajustaran correctamente en el modo de pantalla completa.
- Se ha corregido un problema debido a que la memoria caché HTTP interfiere con el modo de pantalla destinada a grupos de AAD.
- Se ha corregido un problema por el que los usuarios no podían usar el botón emparejar después de habilitar el modo de desarrollador con paquetes de aprovisionamiento a menos que hayan deshabilitado y vuelto a habilitar el modo de desarrollador.

## Windows Holographic, versión 1903, actualización de noviembre de 2020
- Compilación 18362,1085

Esta actualización mensual de calidad no contiene ningún cambio importante, le recomendamos que pruebe la versión más reciente de la característica crear Windows Holographic, versión 20H2.

## Windows Holographic, versión 2004, actualización de octubre de 2020
- Compilación 19041,1124
 
Mejoras y correcciones de la actualización:

- Se ha quitado una comprobación innecesaria que causó un error de sistema en tiempo de ejecución.

## Windows Holographic, versión 1903, actualización de octubre de 2020
- Compilación 18362,1081

Esta actualización mensual de calidad no contiene ningún cambio importante, le recomendamos que pruebe nuestras compilaciones más recientes para Windows Holographic, versión 2004.

## Windows Holographic, versión 2004-actualización 2020 de septiembre
- Compilación 19041,1117

Mejoras y correcciones de la actualización:

- Corrige un problema que impedía que Visual Studio depure una aplicación cuando SupportsMultipleInstances = "true" está presente en el appxmanifest.
- Esta versión incluye la corrección de detección de proxy de NCSI para resolver errores de detección de Internet por proxy de red. NCSI puede usar un proxy de máquina y un proxy por perfil para la detección de conectividad a Internet. Un proxy por usuario será admitido por NCSI en una versión futura.
- En la mayoría de los dispositivos Windows Mixed Reality, el vector de dirección hacia adelante es paralelo al suelo cuando la cabeza del usuario se encuentra en una posición neutra mirando hacia adelante. Sin embargo, las versiones anteriores de HoloLens 2 alinearon el vector para que sea perpendicular a los paneles de visualización, que se inclina hacia abajo unos cuantos grados con relación a la orientación ideal. Las versiones más recientes de HoloLens 2 han corregido esto para garantizar la coherencia semántica en los factores de forma.
- Mejoras de la solidez del seguimiento de la mano que darán menos pérdidas de seguimiento en escenarios específicos.
- Esta versión contiene una corrección para mejorar la calidad de la marca de hora de audio que puede haber contribuido a problemas de captura de video.

## Windows Holographic, versión 1903-actualización 2020 de septiembre
- Compilación 18362,1079

Mejoras y correcciones de la actualización:

- En la mayoría de los dispositivos Windows Mixed Reality, el vector de dirección hacia adelante es paralelo al suelo cuando la cabeza del usuario se encuentra en una posición neutra mirando hacia adelante. Sin embargo, las versiones anteriores de HoloLens 2 alinearon el vector para que sea perpendicular a los paneles de visualización, que se inclina hacia abajo unos cuantos grados con relación a la orientación ideal. Las versiones más recientes de HoloLens 2 han corregido esto para garantizar la coherencia semántica en los factores de forma.
- Mejoras de la solidez del seguimiento de la mano que darán menos pérdidas de seguimiento en escenarios específicos.

## Windows Holographic, versión 2004, actualización de 2020 de agosto
- Compilación 19041,1113

Mejoras y correcciones de la actualización:

- La aplicación de configuración ya no seguirá al usuario en la inscripción de iris o en la calibración de seguimiento de ojos.
- Se ha corregido un error en el que se aplicaba un paquete de aprovisionamiento durante la ejecución de OOBE que cambia el nombre del dispositivo y realiza otras acciones (como conectarse a una red) no podía realizar otras acciones después de que se reinicie el dispositivo, debido a un cambio de nombre.
- Combinación de colores modificada de los flujos de configuración de dispositivos iniciales para mejorar la calidad visual.

## Windows Holographic, versión 1903, actualización de 2020 de agosto
- Compilación 18362,1074

Esta actualización mensual de calidad no contiene ningún cambio importante, le recomendamos que pruebe nuestras compilaciones más recientes para Windows Holographic, versión 2004.

## Windows Holographic, versión 2004, actualización de julio de 2020
- Compilación 19041,1109

Mejoras y correcciones de la actualización:

- Ahora, los desarrolladores pueden elegir entre habilitar o deshabilitar que el portal de dispositivos requiera una conexión segura.
- Confiabilidad mejorada para los lanzamientos de aplicaciones después de las actualizaciones del sistema operativo.
- Se ha cambiado el brillo de la bandeja de entrada a 100 por ciento.
- Se ha solucionado un problema relacionado con el reenvío de HTTPS para Windows Device portal en HoloLens 2.

## Windows Holographic, versión 1903, actualización de julio de 2020
- Compilación 18362,1071

Mejoras y correcciones de la actualización:

- Se ha corregido un problema que podría provocar que los hologramas desaparezcan en las aplicaciones de Unity al perder o recuperar un seguimiento.
- Se ha corregido un problema que causaba que las aplicaciones de HoloLens exclusivas se bloquearan en el shell al usar el emulador HoloLens con aceleración de hardware en determinados dispositivos.
- Se ha solucionado un problema relacionado con el reenvío de HTTPS para Windows Device portal en HoloLens 2.

## Windows Holographic, versión 2004-actualización 2020 de junio
- Compilación 19041,1106

Mejoras y correcciones de la actualización:

- Los grabadores de MRC personalizados ahora tienen nuevos valores predeterminados para determinadas propiedades si no se especifican.
  - En el *efecto de vídeo MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (auriculares con micrófono envolventes))
  - En el *efecto de audio de MRC*:
    - LoopbackGain (el valor actual "ganancia de audio de la aplicación" en la página de captura de realidad mixta en Windows Device portal)
    - MicrophoneGain (el valor actual de ganancia de audio de micrófono en la página de captura de realidad mixta en Windows Device portal)
- Se ha corregido un error para mejorar la calidad de audio en escenarios de captura de realidad mixta. En concreto, esta corrección debe eliminar el problema de audio en la grabación cuando se muestra el menú **Inicio** .
- Mejor estabilidad de los hologramas en vídeos grabados.
- Se ha resuelto un problema por el que la captura de realidad mixta no pudo grabar video después de que el dispositivo se quedó en estado de modo de espera durante varios días.
- La API HolographicSpace. UserPresence generalmente está deshabilitada para las aplicaciones de Unity. Este comportamiento evita un problema que provocaba que algunas aplicaciones se pausan cuando el parasol se ha volteado, incluso si estaba habilitada la opción "ejecutar en segundo plano". La API ahora está habilitada para las versiones de Unity 2018.4.18 y versiones posteriores, y 2019.3.4 y posteriores.
- Al acceder a Device portal a través de una conexión Wi-Fi, es posible que un explorador Web impida el acceso a un certificado no válido. El explorador puede notificar un error como "ERR_SSL_PROTOCOL_ERROR", incluso si el certificado de dispositivo era de confianza. En este caso, no puede progresar a Device portal, ya que no hay ninguna opción para ignorar las advertencias de seguridad. Esta actualización resolvió el problema. Si el certificado de dispositivo se ha descargado anteriormente y se confía en un equipo PC para quitar las advertencias de seguridad del explorador y se produce el error de SSL, el nuevo certificado debe descargarse y confiarse en las advertencias de seguridad del explorador de direcciones.
- Permitió la creación de un paquete de aprovisionamiento en tiempo de ejecución que pueda instalar una aplicación con paquetes MSIX.
- Se ha agregado una **Settings**configuración en los  >  hologramas**del sistema**de configuración  >  **Holograms** que permite a los usuarios quitar automáticamente todos los hologramas de la Página principal de la realidad mixta cuando se cierra el dispositivo.
- Se ha corregido un problema que causaba que las aplicaciones de HoloLens cambiaran el formato de píxel para representar negro en el emulador de HoloLens.
- Se ha corregido un error que provocaba un bloqueo durante el inicio de sesión de iris.
- Se ha corregido un problema sobre las descargas de tienda repetidas para las aplicaciones ya actuales.
- Se ha corregido un error para evitar que las aplicaciones inmersivo abran Microsoft Edge varias veces.
- Se ha corregido un problema con los lanzamientos de la aplicación fotos durante el arranque inicial después de la actualización de la versión 1903.
- Rendimiento y confiabilidad mejorados.

## Windows Holographic, versión 1903-actualización 2020 de junio
- Compilación 18362,1064

Mejoras y correcciones de la actualización:

- Los grabadores de MRC personalizados tienen nuevos valores predeterminados para determinadas propiedades si no se especifican.
  - En el *efecto de vídeo MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (auriculares con micrófono envolventes))
  - En el *efecto de audio de MRC*:
    - LoopbackGain (el valor actual "ganancia de audio de la aplicación" en la página de captura de realidad mixta en Windows Device portal)
    - MicrophoneGain (el valor actual de ganancia de audio de micrófono en la página de captura de realidad mixta en Windows Device portal)
- La API HolographicSpace. UserPresence generalmente está deshabilitada para las aplicaciones de Unity. Este comportamiento evita un problema que hace que algunas aplicaciones se detengan cuando se voltea el parasol, incluso si la configuración que se va a ejecutar en segundo plano está habilitada. La API ahora está habilitada para las versiones 2018.4.18 y posteriores de Unity, y 2019.3.4 y posteriores.
- Se ha corregido un problema que causaba que las aplicaciones de HoloLens cambiaran el formato de píxel para representar negro en el emulador de HoloLens.
- Se ha corregido un problema sobre los lanzamientos de la aplicación fotos durante el arranque inicial después de la actualización de la versión 1903.

## Windows Holographic, versión 2004  
- Compilación: 19041,1103

2020 la actualización de software más importante de HoloLens 2, *Windows Holographic, versión 2004* incluye una gran cantidad de nuevas y emocionantes funciones, como la compatibilidad con el piloto automático de Windows, el modo de aplicación oscuro, la compatibilidad con Ethernet USB para los puntos de acceso 5g/LTE y mucho más. Para actualizar a la última versión, abra la aplicación **configuración**   , vaya a **Actualizar & seguridad**y seleccione el botón **Buscar actualizaciones**   . 

|             Característica                              |          Descripción                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       WindowsAutopilot                          |          Configurar previamente y configurar sin problemas nuevos dispositivos para producción mediante el piloto automático de Windows                 |
|       Asistencia de FIDO 2                             |          Compatibilidad con las claves de seguridad de FIDO2 para habilitar una autenticación rápida y segura para dispositivos compartidos            |
|       Aprovisionamiento mejorado                      |          Aplicar sin problemas un paquete de aprovisionamiento de una unidad USB a tu HoloLens                              |
|       Estado de instalación de la aplicación                 |          Comprobar el estado de instalación en la aplicación configuración de las aplicaciones se ha insertado en HoloLens 2 a través de MDM               |
|       Proveedores de servicios de configuración (CSP)   |          Se agregaron nuevos proveedores de servicios de configuración para mejorar las capacidades de control de administración                 |
|       Compatibilidad con USB 5G/LTE                       |          La funcionalidad de Ethernet USB ampliada permite el soporte técnico para 5G/LTE                                    |
|       Modo de aplicación oscuro                              |          El modo de aplicación oscuro está disponible para las aplicaciones que admiten modos oscuros y claros, mejorando la experiencia de visualización        |
|       Comandos de voz                             |          Compatibilidad con comandos de voz de sistema adicionales para controlar HoloLens manos libres                           |
|       Mejoras en el seguimiento de manos                 |          Mejoras en el seguimiento de la mano hacer más precisas los botones y las interacciones de tabletas 2D                        |
|       Mejoras y mejoras en la calidad                 |          Varias mejoras de rendimiento y confiabilidad del sistema en toda la plataforma                            |

### Compatibilidad con Windows AutoPilot

El piloto automático de Windows para HoloLens 2 permite que el canal de ventas de dispositivos inscriba HoloLens en tu inquilino de Intune. Cuando los dispositivos llegan, están listos para su implementación automática como dispositivos compartidos en su espacio empresarial. Para aprovechar las ventajas de la implementación automática, el dispositivo debe conectarse a una red durante la primera pantalla de la instalación mediante USB-C-to-Ethernet.

Después de que un usuario inicia el proceso de Autoimplementación automática, el proceso completa los siguientes pasos:

1. Unir el dispositivo a Azure Active Directory (Azure AD).
1. Usar Azure AD para inscribir el dispositivo en Microsoft Intune (u otro servicio MDM).
1. Descargar las directivas de destino del dispositivo, los certificados y los perfiles de red.
1. Aprovisionar el dispositivo.
1. Mostrar la pantalla de inicio de sesión al usuario.

Para obtener más información, vea la [Guía de evaluación de Windows AutoPilot para HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot).

*Póngase en contacto con el administrador de su cuenta para unirse a la vista previa de AutoPilot ahora. Los dispositivos autoejecutables preparados comenzarán pronto.*

### Compatibilidad con clave de seguridad FIDO2

Algunos usuarios comparten un dispositivo HoloLens con otras personas en un entorno profesional o educativo. Por lo tanto, es importante que los usuarios puedan escribir fácilmente nombres de usuario y contraseñas largos. La identidad rápida en línea (FIDO) permite que cualquier persona de su organización (inquilino de Azure AD) inicie sesión en HoloLens sin tener que escribir un nombre de usuario o una contraseña.

Las claves de seguridad de FIDO2 son un método de autenticación no phish basado en estándares que puede venir en cualquier factor de forma. FIDO es un estándar abierto para autenticación con contraseña. Permite a los usuarios y las organizaciones iniciar sesión en sus recursos sin un nombre de usuario o contraseña. En su lugar, usan una clave de seguridad externa o una clave de plataforma integrada en un dispositivo.

Para empezar, consulte [Habilitar el inicio de sesión con clave de seguridad sin contraseñas](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key).

### Inscripción MDM mejorada mediante el paquete de aprovisionamiento

Los paquetes de aprovisionamiento te permiten establecer la configuración de HoloLens mediante un archivo de configuración en lugar de usar la configuración rápida de HoloLens. Anteriormente, los paquetes de aprovisionamiento se han copiado en la memoria interna de HoloLens. Ahora pueden estar en una unidad USB para que sea más fácil reutilizarlo en varios dispositivos HoloLens y puedes aprovisionar dispositivos en paralelo. Los paquetes de aprovisionamiento ahora también admiten un campo para inscribirse en la administración de dispositivos, por lo que no hay ninguna configuración manual después del aprovisionamiento.

Para probarlo:

1. Descargue la versión más reciente del diseñador de configuración de Windows de la tienda Windows en su PC.
1. Seleccione **aprovisionar dispositivos de hololens**  >  **aprovisionar dispositivos hololens 2**.
2. Cree el perfil de configuración. Después, copie todos los archivos que se crearon en un dispositivo de almacenamiento USB-C.
3. Conecta el dispositivo USB-C en cualquier HoloLens que haya parpadeado. Después, pulsa **volume down**los botones de  +  **encendido** por volumen para aplicar el paquete de aprovisionamiento.

### Estado de instalación de la aplicación de línea de negocio

La implementación y administración de la aplicación MDM de aplicaciones empresariales es crítica para HoloLens. Los administradores y los usuarios necesitan ver el estado de instalación de la aplicación para auditoría y diagnóstico. En esta versión, hemos agregado más detalles en **configuración**  >  **cuentas**de  >  **Access trabajo o escuela**  >  **haga clic en la información de su cuenta**  >  **Info**.

### CSP y directivas adicionales

Un [proveedor de servicios de configuración (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) es una interfaz para leer, establecer, modificar o eliminar la configuración de un dispositivo. En esta versión, agregamos compatibilidad con más directivas para aumentar los administradores de control en los dispositivos HoloLens implementados. Para obtener la lista de CSP compatibles con HoloLens, consulta [CSP NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

Novedades de esta versión:

**Policy CSP** 

El proveedor de servicios de configuración de directivas permite a la empresa configurar directivas en dispositivos de Windows. En esta versión, agregamos nuevas directivas para HoloLens, que se enumeran aquí. Para obtener más información, consulta la [política de CSP admitida por HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessGazeInput 
- LetAppsAccessGazeInput_ForceAllowTheseApps 
- LetAppsAccessGazeInput_ForceDenyTheseApps 
- LetAppsAccessGazeInput_UserInControlOfTheseApps 
- LetAppsAccessMicrophone_ForceAllowTheseApps 
- LetAppsAccessMicrophone_ForceDenyTheseApps 
- LetAppsAccessMicrophone_UserInControlOfTheseApps 
- AllowWiFi 

**CSP de NetworkQoSPolicy**

El proveedor de servicios de configuración de NetworkQoSPolicy crea directivas de calidad de servicio (QoS) de red. Una directiva de QoS realiza un conjunto de acciones en el tráfico de red en función de un conjunto de condiciones coincidentes. Para obtener más información, consulta [CSP NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

### Compatibilidad ampliada con Ethernet USB para dispositivos de tethering 5G/LTE

Se agregó compatibilidad para habilitar determinados dispositivos de banda ancha móvil, como teléfonos 5G/LTE y Wi-Fi hotpots, cuando están tethering a HoloLens 2 a través de USB. Estos dispositivos ahora se muestran en **configuración de red** como otra conexión Ethernet. (Los dispositivos de banda ancha móvil que requieren un controlador externo no son compatibles). Esta funcionalidad habilita conexiones de ancho de banda alto cuando Wi-Fi no está disponible y Wi-Fi el tethering no es lo suficientemente adecuado. Para obtener más información sobre los dispositivos USB compatibles, vea [conectarse a dispositivos Bluetooth y USB-C](https://docs.microsoft.com/hololens/hololens-connect-devices).  

### Mejoras en el seguimiento de manos

Esta versión incluye varias mejoras en el seguimiento de manos:

- **Estabilidad de la postura:** Ahora el sistema resistente curva el dedo del índice cuando obtiene occluded por la palma. Este cambio mejora la precisión cuando pulsas los botones, escribe, desplaza el contenido y mucho más. 
- **Reducción de las pulsaciones de aire accidentales:** Hemos mejorado la detección del gesto de pulsar el avión. Ahora hay menos activaciones accidentales en varios escenarios comunes, como cuando derribe las manos a sus lados.
- **Confiabilidad del cambio de usuario:** Ahora, el sistema es más rápido y más confiable al actualizar el tamaño de la mano al compartir un dispositivo.
- **Robo de manos reducido:** Hemos mejorado la gestión de casos en los que hay más de dos manos a la vista de los sensores. Si varias personas trabajan juntas, ahora hay muy pocas probabilidades de que la mano de la pista "salte" al usuario a la de otra persona en la escena.
- **Confiabilidad del sistema:** Se ha corregido un problema que provocaba que el seguimiento manual dejara de funcionar cuando el dispositivo está bajo mucha carga.

### Modo oscuro

Muchas aplicaciones de Windows ahora son compatibles con los modos oscuro y ligero. Los usuarios de HoloLens 2 pueden elegir el modo predeterminado para las aplicaciones que admiten ambos. Después de la actualización, el modo de aplicación predeterminado es "oscuro", pero puede cambiar esta configuración fácilmente: vaya a **configuración**  >  **colores del sistema**  >  **Colors**  >  **Elija el modo de aplicación predeterminado**. 

Estas aplicaciones "en el cuadro" son compatibles con el modo oscuro: 

- Configuración 
- Microsoft Store 
- Correo 
- Calendario 
- Explorador de archivos 
- Centro de opiniones 
- OneDrive 
- Fotos 
- Visor 3D 
- Películas y TV 

![Ventanas de modo oscuro en mosaico](images/DarkMode.jpg)

### Comandos de voz del sistema

Ahora puede usar los comandos de voz con cualquier aplicación del dispositivo. Para obtener más información, consulta [usar tu voz para trabajar con HoloLens](https://docs.microsoft.com/hololens/hololens-cortana). Consulta también los [idiomas admitidos para HoloLens 2](https://docs.microsoft.com/hololens/hololens2-language-support).  

### Actualizaciones de Cortana

La aplicación actualizada se integra con Microsoft 365 para ayudarte a sacar más partido de tus dispositivos (actualmente solo en US-English). En HoloLens 2, Cortana ya no es compatible con determinados comandos específicos del dispositivo, como, por ejemplo, ajustar el volumen o reiniciarlo. Estas opciones ahora son compatibles con los nuevos comandos de voz del sistema. Más información sobre la nueva aplicación de Cortana en nuestro [blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### Mejoras y mejoras en la calidad

Mejoras y correcciones también en la actualización:  
- Introdujo un sistema de calibración de pantalla activa. Esta característica mejora la estabilidad y la alineación de los hologramas. Ahora permanecen en su lugar cuando mueves tu cabeza de un lado a otro.
- Se ha corregido un error en el que Wi-Fi la transmisión a HoloLens se interrumpió periódicamente. Si una aplicación indica que necesita transmisión de baja latencia, implementa la corrección llamando a la [función SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Se ha corregido un bloqueo de dispositivo que se produjo durante la transmisión por secuencias en el modo de investigación.
- Se ha corregido un error en el que, en algunos casos, el usuario no se mostraba en la pantalla de inicio de sesión al reanudar una sesión.
- Se ha corregido un problema por el que los usuarios no pueden exportar registros de MDM mediante la **configuración**.
- Se ha corregido un problema por el que la precisión del seguimiento ocular inmediatamente después de la configuración no actualizada podría ser menor de lo esperado.
- Se ha corregido un problema por el que el subsistema de seguimiento ocular no se pudo inicializar o realizar una calibración en determinadas condiciones.
- Se ha corregido un problema que afectaba a la calibración de ojos para un usuario que ya está calibrado.
- Se ha corregido un problema por el que un controlador se bloqueaba durante la calibración ocular.
- Se ha corregido un problema que provocaba que el botón repetido de encendido del sistema y el bloqueo del shell 60.
- Estabilidad mejorada para los búferes de profundidad.
- Se ha agregado un botón **compartir** en el centro de opiniones para que los usuarios puedan compartir sus comentarios más fácilmente.
- Se ha corregido un error en el que RoboRaid wan't instalado correctamente.

### Problemas conocidos

- Un problema con el lenguaje de sistema zh-CN impide que los comandos de voz tomen una captura de realidad mixta o se muestre la dirección IP del dispositivo.
- Un problema requiere iniciar la aplicación de Cortana después de iniciar el dispositivo para usar la activación de voz "Hola Cortana". Si ha actualizado desde una compilación de 18362, también puede ver un segundo mosaico de la aplicación para la versión anterior de la aplicación de Cortana que ya no funciona en **Inicio**.

## Windows Holographic, versión 1903, actualización de mayo de 2020 
- Compilación 18362,1061

Esta actualización mensual de calidad no contiene ningún cambio importante porque el equipo estaba trabajando en Windows Holographic versión 2004 puede actualizarse como se ha descrito anteriormente.

## Windows Holographic, versión 1903, actualización de 2020 de abril
- Compilación 18362,1059

**Modo oscuro para aplicaciones compatibles** 

Muchas aplicaciones de Windows admiten el modo oscuro y el modo de luz. Los clientes de HoloLens 2 ahora pueden elegir el modo predeterminado para las aplicaciones que admiten ambas combinaciones de colores. En función de los comentarios de los clientes, establecemos el modo de aplicación predeterminado en "oscuro", pero puede cambiar fácilmente esta configuración en cualquier momento: vaya a **configuración > > colores del sistema** para buscar **"elegir el modo de aplicación predeterminado".**

Estas aplicaciones "en el cuadro" son compatibles con el modo oscuro:
- Configuración
- Microsoft Store
- Correo
- Calendario
- Explorador de archivos
- Centro de opiniones
- OneDrive
- Fotos
- Visor 3D
- Películas y TV

**Mejoras y correcciones también en la actualización:** 
- Se han asegurado de que las superposiciones de Shell se incluyen en las capturas de realidad mixta.
- Los programadores no reales ahora pueden usar la página de la vista 3D en Device portal para probar y depurar sus aplicaciones.
- Se ha mejorado la estabilidad de los hologramas en captura de realidad mixta cuando se usa el algoritmo de *DepthReprojection HolographicDepthReprojectionMethod* .
- Se ha corregido el error "no se ha registrado la clase API de IStreamSocketListener" en las aplicaciones ARM de 32-bit.

## Windows Holographic, versión 1903-actualización 2020 de marzo 
- Compilación 18362,1056

Mejoras y correcciones de la actualización:

- Se ha mejorado la estabilidad de los hologramas en captura de realidad mixta cuando se usa el algoritmo *Autobackplane HolographicDepthReprojectionMethod* .
- Se ha asegurado que el sistema de coordenadas conectado a una muestra de profundidad MF es coherente con la documentación pública.
- Se ha mejorado la productividad del desarrollador al permitir a los clientes pegar grandes cantidades de texto a través del portal de dispositivos.

## Windows Holographic, versión 1903, actualización de febrero de 2020 
- Compilación 18362,1053

Mejoras y correcciones de la actualización:

- Ha deshabilitado temporalmente la API HolographicSpace. UserPresence para aplicaciones de Unity. Este cambio evita un problema que provocaba que algunas aplicaciones se pausan cuando el parasol se ha volteado, incluso si estaba habilitada la opción "ejecutar en segundo plano".
- Se ha corregido un bloqueo HUP aleatorio causado por el seguimiento de manos, en el que el usuario observó una inmovilización de la interfaz de usuario y después volvió unos segundos.
- Se ha mejorado el seguimiento de las manos para que al escribir con el dedo del índice, la parte superior de ese dedo tenga menos probabilidades de que se produzcan de forma inesperada.
- Confiabilidad mejorada de la función de seguimiento de encabezado, asignación espacial y otros Runtime.

## Windows Holographic, versión 1903-actualización 2020 de enero 
- Compilación 18362,1043
 
Mejoras y correcciones de la actualización:

- Se ha mejorado la estabilidad de las aplicaciones exclusivas al trabajar con el emulador de HoloLens 2.

## Windows Holographic, versión 1903-diciembre 2019 Update 
- Compilación 18362,1042

Mejoras y correcciones de la actualización:

- Se introdujeron las correcciones de la última fase de reproducción (LSR). Representación visual mejorada de hologramas para que parezca más estable y nítida con el fin de lograr una mayor precisión de su profundidad. Este síntoma será más perceptible después de esta actualización si las aplicaciones no establecen la profundidad de hologramas correctamente.
- Estabilidad fija de aplicaciones exclusivas y navegación entre aplicaciones exclusivas.
- Se ha resuelto un problema por el que la captura de realidad mixta no pudo grabar video después de que el dispositivo estuviera en estado de espera durante varios días.
- Estabilidad mejorada de los hologramas.

## Windows Holographic, versión 1903, actualización de noviembre de 2019 
- Compilación 18362,1039

Mejoras y correcciones de la actualización:

- Funcionalidad fija de comandos de voz **Select** durante la configuración inicial para en-CA y en-au.
- Se ha mejorado la calidad visual de los objetos colocados en las últimas versiones de los toolkits de Unity y Mixed Reality (MRTK).
- Problemas de direccionamiento corregido con aplicaciones holográficas se atasca en un estado de pausa durante el inicio hasta que se abre y se cierra el menú Inicio.
- OpenXR correcciones y mejoras en el tiempo de ejecución para HoloLens 2 y el emulador.
