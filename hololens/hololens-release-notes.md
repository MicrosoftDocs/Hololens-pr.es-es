---
title: Notas de la versión de HoloLens 2
description: Manténgase al día con todas las actualizaciones de cada nueva versión de HoloLens 2.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 02/16/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 9ad1fd599605a82280fc3ce45a2b78fcd0be6f14
ms.sourcegitcommit: 1f3ad5b099e72491f436d851738d2b6f3d4dff31
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400720"
---
# <a name="hololens-2-release-notes"></a>Notas de la versión de HoloLens 2

Para asegurarte de que tienes una experiencia productiva con tus dispositivos HoloLens, seguimos lanzando actualizaciones de características, errores y seguridad. En esta página, puede ver las novedades de HoloLens cada mes. Para obtener la última actualización de HoloLens 2, puedes buscar actualizaciones y actualizar manualmente u obtener la actualización de Flash completo (FFU) para flashear el dispositivo a través de Advanced [Recovery Companion](hololens-recovery.md#clean-reflash-the-device). [](hololens-update-hololens.md#check-for-updates-and-manually-update) La [descarga](https://aka.ms/hololens2download) se mantiene actualizada y proporciona la compilación más reciente disponible en general.

>[!NOTE]
> Estamos encantados de empezar a volar nuevas características a Windows Insiders de nuevo. Vamos a volar al Canal de desarrollo para obtener las actualizaciones más recientes. Continuaremos con nuestras [**notas de HoloLens Insider**](hololens-insider.md) a medida que agreguemos más características y actualizaciones a nuestras compilaciones de Windows Insider. Prepárate para mezclar estas actualizaciones en tu realidad.

Consulte las notas de la versión relacionada:

- [Visitar el archivo del emulador de HoloLens](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, versión 20H2- Actualización de marzo de 2021
- Compilación 19041.1140

Mejoras y correcciones en la actualización:

- Los clientes que usan AdvancedPhotoCapture o LowLagPhotoCapture para capturar fotos con HoloLens 2 ahora pueden recuperar la posición de la cámara hasta 3 segundos después de capturar la foto.
- Se ha corregido una pérdida de memoria en el servicio device portal, el problema provocó un mayor uso de memoria por parte del servicio que provocó que otras aplicaciones no asignaran memoria.
- Se ha corregido un problema por el que los usuarios inscritos en la implementación por fases no pueden iniciar sesión en el dispositivo.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, versión 1903- Actualización de marzo de 2021
- Compilación 18362.1102

Mejoras y correcciones en la actualización:

- Se ha corregido una pérdida de memoria en el servicio device portal, el problema provocó un mayor uso de memoria por parte del servicio que provocó que otras aplicaciones no asignaran memoria.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, versión 20H2- Actualización de febrero de 2021
- Compilación 19041.1136

Mejoras y correcciones en la actualización:

- Se soluciona un problema en torno a la configuración inicial del dispositivo y las actualizaciones de la aplicación de almacenamiento.
- Se soluciona un problema en torno a las actualizaciones y los vuelos de versiones posteriores de HoloLens.
- Se quitaron los certificados preinstalados no usados del almacén raíz de eSIM de los dispositivos HoloLens.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, versión 1903- Actualización de febrero de 2021
- Compilación 18362.1098

Esta actualización de calidad mensual no contiene cambios notables, te animamos a probar nuestras compilaciones más recientes para Windows Holographic, versión 2004.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, versión 20H2: actualización de enero de 2021
- Compilación 19041.1134

Mejoras y correcciones en la actualización:

- Se ha mejorado el rendimiento durante el inicio, la reanudación y el cambio de usuario cuando hay muchos usuarios en el dispositivo.
- Se agregó compatibilidad con arm32 [para el modo de investigación](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode).

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, versión 1903: actualización de enero de 2021
- Compilación 18362.1091

Esta actualización de calidad mensual no contiene cambios notables, te animamos a probar nuestras compilaciones más recientes para Windows Holographic, versión 2004.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, versión 20H2 – Actualización de diciembre de 2020
- Compilación 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalar aplicaciones en HoloLens 2 a través del instalador de aplicaciones

Estamos **agregando una nueva funcionalidad (Instalador** de aplicaciones) para que pueda instalar aplicaciones de forma más sencilla en sus dispositivos HoloLens 2. La característica estará **en modo predeterminado para dispositivos no administrados.** Para evitar interrupciones en las empresas, el instalador de aplicaciones no **estará disponible para dispositivos administrados** en este momento.  

Un dispositivo se considera "administrado" si **se** cumple alguno de los siguientes valores:
- MDM [inscrito](hololens-enroll-mdm.md)
- Configurado con paquete [de aprovisionamiento](hololens-provisioning.md)
- Identidad [de usuario](hololens-identity.md) es Azure AD

Ahora puedes instalar aplicaciones sin necesidad de habilitar el Modo de desarrollador o usar Device Portal.  Solo tiene que descargar (a través de USB o a través de Edge) el paquete Appx en el dispositivo y navegar al paquete Appx en el Explorador de archivos para que se le pida que arranque la instalación.  Como alternativa, [inicie una instalación desde una página web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  Al igual que las aplicaciones que instalas desde Microsoft Store o la instalación local con la [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) funcionalidad de [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) implementación de la aplicación LOB de MDM, las aplicaciones deben estar firmadas digitalmente con la Herramienta de firma y el certificado usado para firmar debe ser de confianza para que el dispositivo HoloLens pueda implementar la aplicación.

**Instrucciones de instalación de la aplicación.**

1.  Asegúrese de que el dispositivo no se considera administrado
1.  Asegúrate de que el dispositivo HoloLens 2 esté encendido y conectado a tu PC
1.  Asegúrate de que has iniciado sesión en el dispositivo HoloLens 2
1.  En el equipo, vaya a la aplicación personalizada y copie yourapp.appxbundle en yourdevicename\Internal Storage\Downloads.   Una vez que hayas terminado de copiar el archivo, puedes desconectar el dispositivo
1.  Desde el dispositivo HoloLens 2 Abra el menú Inicio, seleccione Todas las aplicaciones e inicie la aplicación Explorador de archivos.
1.  Vaya a la carpeta Descargas. Es posible que debas seleccionar primero Este dispositivo en el panel izquierdo de la aplicación y, a continuación, ir a Descargas.
1.  Seleccione el archivo yourapp.appxbundle.
1.  Se iniciará el instalador de aplicaciones. Selecciona el botón Instalar para instalar la aplicación.
La aplicación instalada se iniciará automáticamente al finalizar la instalación.

Puedes encontrar aplicaciones de ejemplo en [Muestras universales de Windows GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) para probar este flujo.

Obtenga información sobre el proceso completo de [instalación de aplicaciones en HoloLens 2 con el instalador de aplicaciones.](app-deploy-app-installer.md)  

![Instalación de ejemplos de MRTK a través del instalador de aplicaciones](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Mejoras y correcciones en la actualización:

- Ahora, el seguimiento de manos mantiene el seguimiento en muchos casos nuevos en los que se habría perdido la mano anteriormente.  En algunos de estos nuevos casos, solo la posición de la palma continúa actualizando en función de la mano real del usuario, mientras que las demás uniones se deducen en función de una pose anterior.  Este cambio ayuda a mejorar la coherencia del seguimiento en movimientos como la bofetada, el lanzamiento, la primicia y el aplauso.  También ayuda en casos en los que la mano está cerca de una superficie o cuando se mantiene un objeto.  Cuando se inferirán las [](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) uniones de mano, el valor de precisión por junta se establecerá en "Aproximado" en lugar de "Alto".
- Se ha corregido un problema por el que el restablecimiento del PIN de las cuentas de Azure AD mostraría un error "Algo salió mal.
- Los usuarios deben ver mucho menos bloqueos de OOBE posteriores al arranque al iniciar ET, Iris desde la aplicación de configuración, nuevo usuario o notificación del sistema.
- Los usuarios deben tener la zona horaria correcta saliendo de OOBE.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, versión 1903 – Actualización de diciembre de 2020
- Compilación 18362.1088

Esta actualización de calidad mensual no contiene ningún cambio notable, te animamos a probar nuestra última actualización de Windows Holographic, versión 20H2 – Diciembre de 2020 y la nueva característica instalador de aplicaciones agregada en la compilación.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, versión 20H2
- Compilación 19041.1128

Windows Holographic, versión 20H2, ya está disponible y ofrece un gran conjunto de nuevas características a los usuarios de HoloLens 2 y a los profesionales de IT. Desde el Posicionamiento automático de ojos, hasta el Administrador de certificados en Configuración, hasta la funcionalidad mejorada del modo quiosco y las nuevas funcionalidades de configuración de Autopilot. Esta nueva actualización permite a los equipos de IT tomar un control más detallado para configurar y administrar dispositivos HoloLens, y ofrece a los usuarios experiencias holográficas aún más fluidas. 

Esta última versión es una actualización mensual a la versión 2004, pero esta vez se incluyen nuevas características. El número de compilación principal seguirá siendo el mismo y Windows Update indicará una versión mensual a la versión 2004 (compilación 19041). Puedes ver el número de compilación en la pantalla Configuración > Acerca de para confirmar que estás en la compilación más reciente disponible 19041.1128+. Para actualizar a la versión más reciente, abre la aplicación Configuración, ve a Actualizar & seguridad y pulsa Buscar actualizaciones. Para obtener más información sobre cómo administrar actualizaciones de HoloLens, visite [esta página](https://docs.microsoft.com/hololens/hololens-updates).

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Novedades de Windows Holographic, versión 20H2  

| Característica                                              | Descripción                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Compatibilidad con posición ocular automática](hololens-release-notes.md#auto-eye-position-support) | Calcula activamente las posiciones de los ojos sin que los usuarios pasen por la calibración de seguimiento de ojos.   |
| [Administrador de certificados](hololens-release-notes.md#certificate-manager)   | Permite que los nuevos métodos más sencillos instalen y quiten certificados de la aplicación Configuración.     |
| [Aprovisionamiento de inicio automático desde USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Los paquetes de aprovisionamiento en unidades USB solicitan automáticamente la página de aprovisionamiento en OOBE.                                                         |
| [Confirmar automáticamente paquetes de aprovisionamiento en OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Los paquetes de aprovisionamiento se aplican automáticamente durante OOBE desde la página de aprovisionamiento.                                                         |
| [Aprovisionamiento automático sin usar la interfaz de usuario](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Cómo combinar el inicio automático de aprovisionamiento y la confirmación automática juntos. |
| [Uso de Autopilot con Wi-Fi conexión](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Usa autopilot desde el dispositivo Wi-Fi sin necesidad de adaptador ethernet. |
| [Tenantlockdown CSP y Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Después de aplicar la inscripción de inquilinos y la directiva, el dispositivo solo puede inscribirse en ese espacio empresarial cada vez que el dispositivo se restablezca o vuelva a parpadear. |
| [Acceso asignado global](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Nuevo método de configuración para el modo de pantalla completa de varias aplicaciones que aplica el quiosco en el nivel del sistema, por lo que es aplicable a todos.                  |
| [Inicio automático de una aplicación en quiosco de varias aplicaciones](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Establece una aplicación para que se inicie automáticamente al iniciar sesión en un modo de pantalla completa de varias aplicaciones.                                                        |
| [Cambios en el comportamiento del modo quiosco para controlar errores](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | El error del modo de pantalla completa ahora tiene una reserva restrictiva.                                                                                                |
| [Directivas de HoloLens](hololens-release-notes.md#hololens-policies)                                    | Nuevas directivas para HoloLens.     |
| [Pertenencia al grupo de Azure AD en caché para quiosco sin conexión](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | La nueva directiva permite a los usuarios usar la memoria caché de pertenencia a grupos para usar el modo quiosco sin conexión durante un número establecido de días.                                        |
| [Nuevas directivas de restricción de dispositivos para HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Directivas de administración de dispositivos habilitadas recientemente para HoloLens 2.                                                                                |
| [Nuevas directivas de energía para HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Directivas admitidas recientemente para la configuración de tiempo de espera de energía.  |
| [Actualizar directivas](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Directivas recién habilitadas que permiten el control de actualizaciones.           |
| [Visibilidad de página Configuración habilitada para HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Directiva para elegir qué páginas se ven en la aplicación Configuración.             |
| [Modo de investigación](hololens-release-notes.md#research-mode) | Uso del modo de investigación en HoloLens 2. |
| [Longitud de grabación aumentada](hololens-release-notes.md#recording-length-increased) | Las grabaciones de MRC ya no se han límite a 5 minutos. |
| [Mejoras y correcciones en la actualización](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Correcciones adicionales en la actualización.   |

### <a name="auto-eye-position-support"></a>Compatibilidad con posición ocular automática

En HoloLens 2, las posiciones oculares permiten un posicionamiento preciso del holograma, una experiencia de visualización cómoda y una mejor calidad de visualización. Las posiciones oculares se calculan internamente como parte del análisis del seguimiento ocular. Sin embargo, esto requiere que cada usuario realice la calibración del seguimiento ocular, incluso cuando la experiencia no requiera una entrada ocular.

La **Posición ocular automática (AEP)** permite que estos escenarios tengan una forma sin interacción que calcule las posiciones de la vista para el usuario. La Posición ocular automática comienza a funcionar en segundo plano automáticamente desde el momento en el que el usuario se coloca el dispositivo. Si el usuario no ha calibrado su seguimiento ocular anteriormente, la Posición ocular automática comenzará a proporcionar las posiciones de ojo del usuario al sistema de visualización después de un tiempo de procesamiento de 20-30 segundos. Los datos de usuario no se conservan en el dispositivo y, por lo tanto, este proceso se repite si el usuario desconecta y vuelve a ponerse el dispositivo o si el dispositivo se reinicia o se reactiva tras haberse suspendido.

Cuando un usuario no calibrado se coloca el dispositivo, la opción Posición ocular automática provoca algunos cambios en la conducta del sistema. En este contexto, un usuario no calibrado es alguien que no ha pasado por el proceso de calibración de seguimiento ocular en el dispositivo anteriormente.

| Aplicación activa | Comportamiento anterior | Comportamiento de Windows Holographic, versión 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Aplicación no habilitada para la mirada o shell holográfica |Se muestra el cuadro de diálogo de solicitud de calibración de seguimiento ocular. | No se muestra ningún mensaje. |
| Aplicación habilitada para la mirada | Se muestra el cuadro de diálogo de solicitud de calibración de seguimiento ocular. | El aviso de calibración de seguimiento ocular se muestra solo cuando la aplicación accede a la secuencia de mirada. |

Si el usuario pasa de una aplicación con la opción de mirada no habilitada a otra que tiene acceso a los datos de mirada, se mostrará el aviso de calibración. 

El resto del comportamiento del sistema será similar a cuando el usuario actual no tiene una calibración de seguimiento ocular activa. Por ejemplo, el gesto Inicio de una sola mano no estará habilitado. No se cambiará la experiencia de configuración rápida para la configuración inicial.

Para las experiencias que requieran datos oculares o posicionamiento muy preciso de holograma, recomendamos a los usuarios no calibrados que realicen la calibración de seguimiento de ocular. Es accesible desde la solicitud de calibración de seguimiento ocular. También se puede iniciar la aplicación Configuración desde el menú Inicio y, a continuación, se selecciona **Sistema > Calibración > Calibración ocular > Ejecutar calibración ocular**.

Esta información se puede encontrar más adelante con [otra información de calibración](hololens-calibration.md#auto-eye-position-support). 

### <a name="certificate-manager"></a>Administrador de certificados

- Se han mejorado las herramientas de auditoría, diagnóstico y validación para la seguridad y el cumplimiento de dispositivos a través del nuevo Administrador de certificados. Esta funcionalidad le permitirá implementar, solucionar problemas y validar los certificados a escala en entornos comerciales.

En Windows Holographic versión 20H2, estamos agregando un Administrador de certificados en la aplicación Configuración de HoloLens 2. Vaya a **Configuración > actualizar & seguridad > certificados**. Esta característica proporciona una forma sencilla y fácil de usar para ver, instalar y quitar certificados en el dispositivo. Con el nuevo Administrador de certificados, los administradores y los usuarios ahora tienen herramientas mejoradas de auditoría, diagnóstico y validación para garantizar que los dispositivos sigan siendo seguros y compatibles. 

-   **Auditoría:** Capacidad para validar que un certificado se implementó correctamente o para confirmar que se quitó correctamente. 
-   **Diagnóstico:** Cuando surgen problemas, validar que los certificados adecuados existen en el dispositivo ahorra tiempo y ayuda a solucionar problemas. 
-   **Validación:** Comprobar que un certificado cumple el propósito previsto y es funcional, puede ahorrar mucho tiempo, especialmente en entornos comerciales antes de implementar certificados a mayor escala.

Para buscar rápidamente un certificado específico en la lista, hay opciones para ordenar por nombre, almacén o fecha de expiración. Los usuarios también pueden buscar directamente un certificado. Para ver las propiedades de certificado individuales, seleccione el certificado y haga clic en **Información**. 

Actualmente, la instalación de certificados admite archivos .cer y .crt. Los propietarios de dispositivos pueden instalar certificados en máquina local y usuario actual;  todos los demás usuarios solo pueden instalarse en el usuario actual. Los usuarios solo pueden quitar certificados instalados directamente desde la interfaz de usuario de configuración. Si un certificado se ha instalado a través de otros medios, también debe quitarse por el mismo mecanismo.

#### <a name="to-install-a-certificate"></a>Para instalar un certificado: 

1.  Conecta hololens 2 a un equipo.
1.  Coloque el archivo de certificado que desea instalar en una ubicación en holoLens 2.
1.  Vaya a **Configuración aplicación > actualizar & seguridad > certificados**y seleccione Instalar un certificado.
1.  Haga **clic en Importar** archivo y vaya a la ubicación en la que guardó el certificado.
1.  Seleccione **Ubicación de la tienda**.
1.  Seleccione **Almacén de certificados**.
1.  Haz clic en **Instalar**.

El certificado ahora debe instalarse en el dispositivo.

#### <a name="to-remove-a-certificate"></a>Para quitar un certificado: 
1. Vaya a **Configuración aplicación > actualización y seguridad > certificados**.
1. Busque el certificado por su nombre en el cuadro de búsqueda.
1. Seleccione el certificado.
1. Haga clic **en Quitar**
1. Seleccione **Sí** cuando se le pida confirmación.

![Visor de certificados en la aplicación Configuración](images/certificate-viewer-device.jpg)

![Imagen que muestra cómo usar la interfaz de usuario de certificado para instalar un certificado](images/certificate-device-install.jpg)

Esta información se puede encontrar más adelante [en una nueva página del Administrador de certificados.](certificate-manager.md)

### <a name="auto-launch-provisioning-from-usb"></a>Aprovisionamiento de inicio automático desde USB

- Procesos automatizados que permiten una menor interacción del usuario, cuando se usan unidades USB con paquetes de aprovisionamiento durante OOBE.

Antes de esta versión, los usuarios tenían que iniciar la pantalla de aprovisionamiento manualmente durante OOBE para aprovisionar mediante una combinación de botones. Ahora, los usuarios pueden omitir la combinación de botones mediante un paquete de aprovisionamiento en una unidad de almacenamiento USB. 

1. Conecte la unidad USB con el paquete de aprovisionamiento durante el primer momento interactuable de OOBE
1. Cuando el dispositivo esté listo para aprovisionarse, se abrirá automáticamente el mensaje con la página de aprovisionamiento. 

Nota: Si una unidad USB se deja conectada mientras el dispositivo se está iniciando, OOBE enumerará el dispositivo de almacenamiento USB existente, así como observará si se están conectando otras adicionales.

Para obtener más información acerca de cómo aplicar paquetes de aprovisionamiento durante OOBE, visite la documentación de [aprovisionamiento de HoloLens.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Encontrará información adicional [sobre el aprovisionamiento de inicio automático desde un USB](hololens-provisioning.md#auto-launch-provisioning-from-usb) en la documentación de aprovisionamiento de HoloLens.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Confirmar automáticamente paquetes de aprovisionamiento en OOBE
- Proceso automatizado que permite una menor interacción del usuario, cuando se muestre la página Paquete de aprovisionamiento aplicará automáticamente todos los paquetes enumerados.

Cuando aparece la pantalla principal de aprovisionamiento, OOBE contará 10 segundos antes de empezar a aplicar automáticamente todos los paquetes de aprovisionamiento. Los usuarios aún [pueden confirmar o cancelar](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) en estos 10 segundos después de comprobar los paquetes que esperaban.

### <a name="automatic-provisioning-without-using-ui"></a>Aprovisionamiento automático sin usar la interfaz de usuario
- Procesos automáticos combinados para interacciones reducidas de dispositivos para el aprovisionamiento. 

Al combinar el inicio automático del aprovisionamiento desde dispositivos USB y la confirmación automática de paquetes de aprovisionamiento, un usuario puede aprovisionar dispositivos HoloLens 2 automáticamente sin usar la interfaz de usuario del dispositivo ni siquiera usar el dispositivo. Puede seguir usando la misma unidad USB y el mismo paquete de aprovisionamiento para varios dispositivos. Esto es útil para implementar varios dispositivos a la vez en la misma área. 

1. [Crear un paquete de aprovisionamiento](hololens-provisioning.md) con [el Diseñador de configuraciones de Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Copie el paquete en una unidad de almacenamiento USB.
1. [Flash your HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) to [19041.1361 or newer build](https://aka.ms/hololens2previewdownload). 
1. Cuando [advanced recovery companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8) has completed flashing your device unplug your USB-C cable. 
1. Conecta la unidad USB al dispositivo.
1. Cuando el dispositivo HoloLens 2 se inicie en OOBE, detectará automáticamente el paquete de aprovisionamiento en la unidad USB e iniciará la página de aprovisionamiento.
1. Después de 10 segundos, el dispositivo aplicará automáticamente el paquete de aprovisionamiento. 

El dispositivo ya está configurado y mostrará [la pantalla Aprovisionamiento correcto.](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### <a name="using-autopilot-with-wi-fi-connection"></a>Uso de Autopilot con Wi-Fi conexión
- Se ha quitado la necesidad de adaptadores USB-C a ethernet para reducir las necesidades de hardware, ya que permite que Autopilot funcione en Wi-Fi dispositivos conectados.

Ahora, durante OOBE, una vez que conectes HoloLens 2 con Wi-Fi, OOBE buscará un perfil de Autopilot para el dispositivo. Si se encuentra, se usará para completar el resto del flujo de participación y inscripción de AAD. En otras palabras, el uso de ethernet a USB-C o adaptador Wi-Fi a USB-C ya no es un requisito, pero siguen funcionando si se proporcionan al principio de OOBE. Obtenga más información [sobre Autopilot para dispositivos HoloLens 2](hololens2-autopilot.md).

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP y Autopilot
- Mantiene los dispositivos en el espacio empresarial de la organización bloqueándolos, incluso al reestablecer el dispositivo o formatearlo. Es más seguro porque no permite crear cuentas mediante aprovisionamiento. 

Los dispositivos HoloLens 2 ahora admiten TenantLockdown CSP a partir de [Windows Holographic versión 20H2](hololens-release-notes.md#windows-holographic-version-20h2). 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP permite que HoloLens 2 se vincule a la inscripción de MDM únicamente con el Autopilot. Una vez que el nodo RequireNetworkInOOBE de TenantLockdown CSP se active o desactive (configurado inicialmente) en HoloLens 2, permanecerá así el dispositivo aunque se vuelva a formatear, a actualizar el sistema operativo, etc. 

Una vez que el nodo RequireNetworkInOOBE de TenantLockdown CSP se active o desactive (configurado inicialmente) en HoloLens 2, la configuración rápida espera indefinidamente que el perfil de Autopilot se descargue y aplique correctamente, después de conectarse a la red. 

Una vez que el nodo RequireNetworkInOOBE de TenantLockdown de CSP se active o desactive en HoloLens 2, no se permitirán las siguientes operaciones en la configuración rápida: 
- Crear usuarios locales mediante aprovisionamiento en el tiempo de ejecución 
- Realizar una operación de replica de Azure AD mediante aprovisionamiento en el tiempo de ejecución 
- Seleccionar quién es el propietario del dispositivo en la experiencia de la configuración rápida 

#### <a name="how-to-set-this-using-intune"></a>¿Cómo configurarlo con Intune? 
1. Crea un perfil de configuración de dispositivos OMA URI personalizado y activa el nodo RequireNetworkInOOBE como se hace a continuación.
El valor OMA-URI debe ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Configuración del bloqueo de inquilinos a través de OMA-URI](images/hololens-tenant-lockdown.png)

1. Crea un grupo y asigna el perfil de configuración del dispositivo a ese grupo de dispositivos. 

1. Haz que el dispositivo HoloLens 2 sea un miembro del grupo creado en el paso anterior y desencadena la sincronización.  

Comprueba en el portal de Intune que la configuración del dispositivo se ha aplicado correctamente. Una vez que la configuración del dispositivo se aplique correctamente en el dispositivo HoloLens 2, los efectos de TenantLockdown estarán activos.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>¿Cómo se anula el nodo RequireNetworkInOOBE de TenantLockdown en HoloLens 2 con Intune? 
1. Quita HoloLens 2 del grupo de dispositivos a los que asignó la configuración creada anteriormente. 

1. Crea un perfil de configuración de dispositivos basado en OMA URI personalizado y desconecte RequireNetworkInOOBE como se hace a continuación. El valor OMA-URI debe ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla de la configuración para desconectar RequireNetworkInOOBE a través de OMA URI en Intune](images/hololens-tenant-lockdown-false.png)

1. Crea un grupo y asigna el perfil de configuración del dispositivo a ese grupo de dispositivos. 

1. Haz que el dispositivo HoloLens 2 sea un miembro del grupo creado en el paso anterior y desencadena la sincronización.

Comprueba en el portal de Intune que la configuración del dispositivo se ha aplicado correctamente. Una vez que la configuración del dispositivo se aplique correctamente en el dispositivo HoloLens 2, los efectos de TenantLockdown estarán inactivos. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>¿Qué sucedería durante la configuración rápida si el perfil de Autopilot no está asignado a un HoloLens después de haber activado TenantLockdown? 
La configuración rápida esperará indefinidamente a que se descargue el perfil de Autopilot y a que aparezca el siguiente cuadro de diálogo. Para eliminar los efectos de TenantLockdown, el dispositivo debe estar antes inscrito en el espacio empresarial original únicamente con el Autopilot y RequireNetworkInOOBE configurarse como desconectado tal y como se describe en el paso anterior antes de que se quiten las restricciones introducidas por TenantLockdown CSP. 

![Vista en el dispositivo cuando se aplica la directiva.](images/hololens-autopilot-lockdown.png)

Esta información se puede encontrar junto con el resto de Autopilot en [Tenantlockdown CSP y Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot).

### <a name="global-assigned-access--kiosk-mode"></a>Acceso asignado global: modo de pantalla completa
- Se ha reducido la administración de identidades para kiosko, habilitando el nuevo método Kiosk que aplica el modo quiosco en el nivel del sistema.

Esta nueva característica permite a un administrador de TI configurar un dispositivo HoloLens 2 para el modo de pantalla completa de varias aplicaciones, que es aplicable a nivel del sistema, no tiene afinidad con ninguna identidad en el sistema y se aplica a todos los usuarios que inician sesión en el dispositivo. Lea esta nueva característica detalladamente en el quiosco de acceso [asignado global de HoloLens](hololens-global-assigned-access-kiosk.md).

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Inicio automático de una aplicación en modo de pantalla completa de varias aplicaciones 
- Experiencia centrada con el inicio automático de la aplicación, lo que aumenta aún más las selecciones de la interfaz de usuario y la aplicación elegidas para las experiencias del modo quiosco.

Solo se aplica al modo de pantalla completa de varias aplicaciones y solo se puede designar 1 aplicación para iniciarse automáticamente con el atributo resaltado a continuación en Configuración de acceso asignado. 

La aplicación se inicia automáticamente cuando el usuario inicia sesión. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Cambios en el comportamiento del modo quiosco para controlar errores
- Modo quiosco más seguro al eliminar las aplicaciones disponibles en los errores del modo quiosco. 

Anteriormente, al encontrar errores en la aplicación del modo de pantalla completa, HoloLens se usaba para mostrar todas las aplicaciones en el menú inicio. Ahora en Windows Holographic versión 20H2 en caso de errores, no se mostrará ninguna aplicación en el menú inicio como se muestra a continuación: 

![Imagen del modo quiosco de pantalla completa ahora cuando se produce un error.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>Directivas de HoloLens
- Opciones de administración de dispositivos específicamente para HoloLens creadas para administrar el dispositivo. 

Se han creado nuevas directivas de realidad mixta para dispositivos HoloLens 2 en Windows Holographic versión 20H2. Las nuevas configuraciones controlables incluyen: establecer el brillo, establecer el volumen, deshabilitar la grabación de audio en capturas de realidad mixta, establecer cuándo se pueden recopilar diagnósticos y la memoria caché de pertenencia a grupos de AAD.  

| Nueva directiva de HoloLens                                | Descripción                                                                               | Notas                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| Realidad mixta\BrightnessButtonDisabled              | Permite deshabilitar los botones de brillo para que al presionarlo no cambie el brillo.       | 1 Sí, 0 No (valor predeterminado)                                                |
| Realidad mixta\VolumeButtonDisabled                  | Permite deshabilitar los botones de volumen para que presionarlo no cambie el volumen.               | 1 Sí, 0 No (valor predeterminado)                                                |
| Realidad mixta\MicrophoneDisabled                    | Deshabilita el micrófono para que no se pueda grabar audio en HoloLens 2.                      | 1 Sí, 0 No (valor predeterminado)                                                |
| Realidad mixta\FallbackDiagnostics                   | Controla el comportamiento de cuándo se pueden recopilar los registros de diagnóstico.                               | 0 Deshabilitado, 1 Habilitado para propietarios de dispositivos, 2 Habilitado para todos (predeterminado) |
| Realidad mixta\HeadTrackingMode                      | Reservado para uso futuro.                                                                  |                                                                      |
| Realidad mixta\AADGroupMembershipCacheValidityInDays | Controla cuántos días se usa la memoria caché de pertenencia a grupos de Azure AD para los grupos de Quiosco de destino de Azure AD. | Vea a continuación.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Pertenencia al grupo de Azure AD en caché para quiosco sin conexión
- Habilitado quioscos sin conexión para usarse con grupos de AAD durante un máximo de 60 días.

Esta directiva controla durante cuántos días se puede usar la memoria caché de pertenencia a grupos de Azure AD para las configuraciones de acceso asignado destinadas a grupos de Azure AD para usuarios que han iniciado sesión. Una vez que este valor de directiva se establece en valor mayor que 0, solo se usa la memoria caché de lo contrario no.  

Nombre: valor uri de AADGroupMembershipCacheValidityInDays: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min : 0 días  
Max - 60 días 

Pasos para usar esta directiva correctamente: 
1. Crea un perfil de configuración de dispositivo para quiosco de pantalla completa destinado a grupos de Azure AD y asígnelo a dispositivos HoloLens. 
1. Cree una configuración de dispositivo basada en URI de OMA personalizada que establece este valor de directiva en el número de días deseado (> 0) y asígnelo a dispositivos HoloLens. 
    1. El valor uri debe especificarse en el cuadro de texto OMA-URI como ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. El valor puede estar entre min/max permitido.
1. Inscriba dispositivos HoloLens y compruebe que ambas configuraciones se apliquen al dispositivo. 
1. Permitir que el usuario de Azure AD inicie sesión 1 cuando Internet esté disponible, una vez que el inicio de sesión del usuario y la pertenencia al grupo de Azure AD se confirmen correctamente, se creará la memoria caché. 
1. Ahora, el usuario de Azure AD 1 puede desconectar HoloLens y usarlo para el modo de pantalla completa siempre que el valor de directiva permita X número de días. 
1. Los pasos 4 y 5 se pueden repetir para cualquier otro usuario de Azure AD N. Aquí la clave es que cualquier usuario de Azure AD debe iniciar sesión en el dispositivo con Internet, por lo que al menos una vez podemos determinar que son miembros del grupo de Azure AD al que está destinada la configuración de quiosco. 
 
> [!NOTE]
> Hasta que se realice el paso 4 para un usuario de Azure AD experimentará un comportamiento de error mencionado en entornos "desconectados". 

### <a name="new-device-restriction-policies-for-hololens-2"></a>Nuevas directivas de restricción de dispositivos para HoloLens 2
- Permite a los usuarios administrar directivas de administración de dispositivos específicas, como bloquear la adición o eliminación de paquetes de aprovisionamiento.

Directivas recién habilitadas que permiten más opciones de administración de dispositivos HoloLens 2. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Estas dos nuevas policías para AllowAddProvisioningPackage y AllowRemoveProvisioningPackage se agregan a nuestras [restricciones comunes de dispositivos](hololens-common-device-restrictions.md).

> [!NOTE]
> Con respecto a [RemoteLock,](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)HoloLens solo admitirá la configuración ./Vendor/MSFT/RemoteLock/Lock. No se admiten las configuraciones que tratan con PIN, como restablecer y recuperar.

### <a name="new-power-policies-for-hololens-2"></a>Nuevas directivas de energía para HoloLens 2
- Más opciones para cuando HoloLens se bloquea o se bloquea a través de directivas de energía. 

Estas directivas recién agregadas permiten a los administradores controlar los estados de energía, como el tiempo de espera de inactividad. Para obtener más información sobre cada directiva individual, haga clic en el vínculo de esa directiva.

|     Vínculo de documentación de directivas                |     Notas                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Valor de ejemplo que se usará en el Diseñador de configuraciones de Windows, es decir,  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Valor de ejemplo que se usará en el Diseñador de configuraciones de Windows, es decir,  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Valor de ejemplo para usar en el Diseñador de configuraciones de Windows, es decir, 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Valor de ejemplo para usar en el Diseñador de configuraciones de Windows, es decir, 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Valor de ejemplo que se usará en el Diseñador de configuraciones de Windows, es decir,   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Valor de ejemplo que se usará en el Diseñador de configuraciones de Windows, es decir,  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Estas dos nuevas policías para DisplayOffTimeoutOnBattery y DisplayOffTimeoutPluggedIn se agregan a nuestras [restricciones comunes de dispositivos](hololens-common-device-restrictions.md).

> [!NOTE]
> Para una experiencia coherente en HoloLens 2, asegúrese de que los valores de DisplayOffTimeoutOnBattery y StandbyTimeoutOnBattery se establecen como el mismo valor. Lo mismo se aplica a DisplayOffTimeoutPluggedIn y StandbyTimeoutPluggedIn. Consulte [Mostrar, suspender e hibernar](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) temporizadores inactivos para obtener más información sobre el modo de espera moderno.

### <a name="newly-enabled-update-policies-for-hololens"></a>Directivas de actualización recién habilitadas para HoloLens
- Más opciones para cuando se instalan las actualizaciones o deshabilita el botón Pausar actualizaciones para garantizar las actualizaciones.

Estas directivas de actualización ahora están habilitadas en dispositivos HoloLens 2:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Los detalles completos sobre estas directivas de actualización y cómo usarlas para dispositivos HoloLens se pueden leer aquí en [Administrar actualizaciones de HoloLens](hololens-updates.md).

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Visibilidad de página Configuración habilitada para HoloLens 2
- Mayor control de la interfaz de usuario en la aplicación Configuración, que puede confundirse para mostrar una selección limitada de páginas.

Ahora hemos habilitado una directiva que permite a los administradores de TI impedir que páginas específicas de la aplicación Configuración del sistema sean visibles o accesibles, o hacerlo para todas las páginas excepto las especificadas. Para obtener información sobre cómo personalizar completamente esta característica, haga clic en el vínculo siguiente.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Para obtener información sobre qué configuración de página puede personalizar en HoloLens 2, visite nuestra página [Configuración uri](settings-uri-list.md). 
 
![Captura de pantalla de la modificación de las horas activas en la aplicación de Configuración](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Modo de investigación
Mientras está en modo de investigación, HoloLens 2 se convierte en una herramienta potente para la investigación de la visión del equipo. En comparación con ediciones anteriores, el modo de investigación para HoloLens 2 tiene las siguientes ventajas:
-   Además de los sensores expuestos en el modo de investigación HoloLens (1ª generación), ahora proporcionamos acceso al sensor IMU, incluido un acelerómetro, un giroscopio y un magnetómetro.
-   HoloLens 2 proporciona nuevas funcionalidades que se pueden usar junto con el modo de investigación. Específicamente, el acceso a API de seguimiento de manos y seguimiento ocular articuladas que pueden ofrecer un conjunto más amplio de experimentos.

Los investigadores ahora tienen la opción de habilitar el modo de investigación en sus dispositivos HoloLens para tener acceso a todos estos flujos de sensores de imagen sin procesar orientados externos. El modo de investigación para HoloLens 2 también proporciona acceso a las lecturas de acelerómetro, giroscopio y magnetómetro. Para proteger la privacidad de los usuarios, las imágenes de cámara de seguimiento ocular sin procesar no están disponibles a través del modo de investigación, pero la dirección de la mirada visual está disponible a través de las API existentes.

Consulte la documentación [del modo de investigación](https://docs.microsoft.com/windows/mixed-reality/research-mode) para obtener más detalles técnicos.

### <a name="recording-length-increased"></a>Longitud de grabación aumentada
Debido a los comentarios de los clientes, hemos aumentado la longitud de grabación de las capturas [de realidad mixta.](holographic-photos-and-videos.md) Las capturas de realidad mixta ya no se limitarán a 5 minutos de forma predeterminada, sino que calcularán la longitud máxima de grabación en función del espacio en disco disponible. El dispositivo calculará la duración máxima de grabación de vídeo en función del espacio en disco disponible hasta el 80 % del espacio en disco total.

> [!NOTE]
> HoloLens usará la longitud de grabación de vídeo predeterminada (5 minutos) si se produce una de las siguientes situaciones:
> - La duración máxima de grabación estimada es menor que los 5 minutos predeterminados.
> - El espacio en disco disponible es inferior al 20 % del espacio en disco total.

Puede encontrar todos los requisitos en nuestra documentación [de fotos y vídeos holográficos.](holographic-photos-and-videos.md#maximum-recording-length) 

### <a name="improvements-and-fixes-in-the-update"></a>Mejoras y correcciones en la actualización:
- Ahora hay más pantallas en OOBE en modo oscuro.
- Obtenga más contenido que apunte a la declaración de privacidad más reciente en línea.
- Se ha corregido un problema por el que los usuarios no podían aprovisionar perfiles de VPN a través de paquetes de aprovisionamiento.
- Se ha corregido un problema de configuración de proxy para la conexión VPN.
- Directiva actualizada para deshabilitar la enumeración de funciones USB a través de MDM para NCM para AllowUsbConnection.
- Se ha corregido un problema que impedía que un dispositivo HoloLens se mostrara en el Explorador de archivos a través del Protocolo de transferencia de medios (MTP) cuando el dispositivo se configuraba como quiosco de una sola [aplicación.](hololens-kiosk.md) Tenga en cuenta que MTP (y conexión USB en general) todavía se pueden deshabilitar mediante la [directiva AllowUSBConnection.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
- Se ha corregido un problema por el que los iconos del menú Inicio se escalaban correctamente en modo quiosco.
- Se ha corregido un problema debido a que el almacenamiento en caché HTTP interfiera con el modo de quiosco de pantalla completa destinado a grupos de Azure AD.
- Se ha corregido un problema por el que los usuarios no podían usar el botón Par después de habilitar el modo de desarrollador con paquetes de aprovisionamiento a menos que deshabilitase y vuelva a habilitar el modo de desarrollador.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, versión 1903- Actualización de noviembre de 2020
- Compilación 18362.1085

Esta actualización de calidad mensual no contiene cambios notables, te animamos a probar nuestra última compilación de versión de características Windows Holographic, versión 20H2.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic, versión 2004- Actualización de octubre de 2020
- Compilación 19041.1124
 
Mejoras y correcciones en la actualización:

- Se quitó una comprobación innecesaria que causaba un error en el sistema en tiempo de ejecución.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic, versión 1903- Actualización de octubre de 2020
- Compilación 18362.1081

Esta actualización de calidad mensual no contiene cambios notables, te animamos a probar nuestras compilaciones más recientes para Windows Holographic, versión 2004.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, versión 2004- Actualización de septiembre de 2020
- Compilación 19041.1117

Mejoras y correcciones en la actualización:

- Se soluciona un problema que impedía Visual Studio depurar una aplicación cuando SupportsMultipleInstances="true" está presente en el appxmanifest.
- Esta versión incluye la corrección de detección de proxy NCSI para solucionar errores de detección de Internet a través del proxy de red. NCSI puede usar proxy de máquina y proxy por perfil para la detección de conectividad a Internet. El proxy por usuario será compatible con NCSI en la versión futura.
- En la mayoría de los dispositivos windows Mixed Reality, el vector de dirección hacia delante es paralelo al suelo cuando la cabeza del usuario está en una posición neutral mirando hacia delante. Sin embargo, las versiones anteriores de HoloLens 2 alineaban el vector para que fuera perpendicular a los paneles de visualización, que se inclina hacia abajo unos grados en relación con la orientación ideal. Las versiones más recientes de HoloLens 2 lo han corregido para garantizar la coherencia semántica en todos los factores de forma.
- Robustez mejorada del seguimiento de manos que dará como resultado menos pérdidas de seguimiento en escenarios específicos.
- Esta versión contiene una corrección para mejorar la calidad de la marca de tiempo de audio que puede haber contribuido a problemas de captura de vídeo.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, versión 1903- Actualización de septiembre de 2020
- Compilación 18362.1079

Mejoras y correcciones en la actualización:

- En la mayoría de los dispositivos windows Mixed Reality, el vector de dirección hacia delante es paralelo al suelo cuando la cabeza del usuario está en una posición neutral mirando hacia delante. Sin embargo, las versiones anteriores de HoloLens 2 alineaban el vector para que fuera perpendicular a los paneles de visualización, que se inclina hacia abajo unos grados en relación con la orientación ideal. Las versiones más recientes de HoloLens 2 lo han corregido para garantizar la coherencia semántica en todos los factores de forma.
- Robustez mejorada del seguimiento de manos que dará como resultado menos pérdidas de seguimiento en escenarios específicos.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, versión 2004- Actualización de agosto de 2020
- Compilación 19041.1113

Mejoras y correcciones en la actualización:

- La aplicación configuración ya no seguirá al usuario en las experiencias de inscripción de iris o calibración de seguimiento de ojos.
- Se ha corregido un error por el que la aplicación de un paquete de aprovisionamiento durante la OOBE que cambia el nombre del dispositivo y realiza otras acciones (como conectarse a una red) no podría realizar las otras acciones después del reinicio del dispositivo debido al cambio de nombre.
- Combinación de colores modificada de flujos de configuración inicial del dispositivo para mejorar la calidad visual.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, versión 1903- Actualización de agosto de 2020
- Compilación 18362.1074

Esta actualización de calidad mensual no contiene cambios notables, te animamos a probar nuestras compilaciones más recientes para Windows Holographic, versión 2004.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, versión 2004- Actualización de julio de 2020
- Compilación 19041.1109

Mejoras y correcciones en la actualización:

- Los desarrolladores ahora pueden elegir entre habilitar o deshabilitar que Device Portal requiera una conexión segura.
- Se mejoró la confiabilidad para los inicios de aplicaciones después de las actualizaciones del sistema operativo.
- Se ha cambiado el brillo predeterminado de la bandeja de entrada al 100 por ciento.
- Se ha corregido un problema sobre el reenvío HTTPS para el Portal de dispositivos de Windows en HoloLens 2.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, versión 1903- Actualización de julio de 2020
- Compilación 18362.1071

Mejoras y correcciones en la actualización:

- Se ha corregido un problema que podía hacer que los hologramas desapareciera en las aplicaciones de Unity al perder o recuperar el seguimiento.
- Se ha corregido un problema que provocaba que las aplicaciones exclusivas de HoloLens se bloqueasen en el shell mientras se usaba el emulador de HoloLens con aceleración de hardware en determinados dispositivos.
- Se ha corregido un problema relativo al reenvío HTTPS para el Portal de dispositivos de Windows en HoloLens 2.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, versión 2004- Actualización de junio de 2020
- Compilación 19041.1106

Mejoras y correcciones en la actualización:

- Las grabadoras mrc personalizadas ahora tienen nuevos valores predeterminados para determinadas propiedades si no se especifican.
  - En el *efecto de vídeo mrc*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1.0 (auriculares envolventes))
  - En el *efecto de audio mrc*:
    - LoopbackGain (el valor actual de "Ganancia de audio de la aplicación" en la página Captura de realidad mixta en Windows Device Portal)
    - MicrophoneGain (el valor actual de "Ganancia de audio de micrófono" en la página Captura de realidad mixta en Windows Device Portal)
- Se ha corregido un error para mejorar la calidad del audio en escenarios de captura de realidad mixta. En concreto, esta corrección debe eliminar las fallas de audio en la grabación cuando **se** muestra el menú Inicio.
- Estabilidad de holograma mejorada en vídeos grabados.
- Se ha resuelto un problema por el que la captura de realidad mixta no podía grabar vídeo después de que el dispositivo quedara en estado de espera durante varios días.
- La API HolographicSpace.UserPresence generalmente está deshabilitada para aplicaciones de Unity. Este comportamiento evita un problema que provocaba que algunas aplicaciones se pausase cuando se volteó el visor, incluso si la configuración "ejecutar en segundo plano" estaba habilitada. La API ahora está habilitada para las versiones de Unity 2018.4.18 y posteriores y 2019.3.4 y posteriores.
- Cuando accedes a Device Portal a través de una Wi-Fi, un explorador web puede impedir el acceso debido a un certificado no válido. El explorador puede notificar un error como "ERR_SSL_PROTOCOL_ERROR", incluso si el certificado del dispositivo era de confianza previa. En este caso, no puedes avanzar a Device Portal, ya que no hay ninguna opción para omitir las advertencias de seguridad. Esta actualización ha resuelto el problema. Si el certificado del dispositivo se descargó previamente y se confió en un equipo para quitar las advertencias de seguridad del explorador y se produce el error SSL, el nuevo certificado debe descargarse y ser de confianza para solucionar las advertencias de seguridad del explorador.
- Se ha habilitado la capacidad de crear un paquete de aprovisionamiento en tiempo de ejecución que puede instalar una aplicación mediante paquetes MSIX.
- Se agregó una configuración en **Configuración**  >  **Hologramas**del sistema que permite a los usuarios quitar automáticamente todos los hologramas de la casa de realidad mixta cuando el dispositivo se  >  **** apaga.
- Se ha corregido un problema que provocaba que las aplicaciones de HoloLens que cambiaban su formato de píxel se representaran en negro en el emulador de HoloLens.
- Se ha corregido un error que provocaba un bloqueo durante el inicio de sesión de Iris.
- Se ha corregido un problema sobre las descargas repetidas de la tienda para las aplicaciones ya actuales.
- Se ha corregido un error para evitar que las aplicaciones envolventes abran Microsoft Edge repetidamente.
- Se ha corregido un problema con los inicios de la Fotos inicios iniciales después de actualizar desde la versión de 1903.
- Rendimiento y confiabilidad mejorados.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, versión 1903- Actualización de junio de 2020
- Compilación 18362.1064

Mejoras y correcciones en la actualización:

- Las grabadoras de MRC personalizadas tienen nuevos valores predeterminados para determinadas propiedades si no se especifican.
  - En el *efecto de vídeo mrc*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1.0 (auriculares envolventes))
  - En el *efecto de audio mrc*:
    - LoopbackGain (el valor actual de "Ganancia de audio de la aplicación" en la página Captura de realidad mixta en Windows Device Portal)
    - MicrophoneGain (el valor actual de "Ganancia de audio de micrófono" en la página Captura de realidad mixta en Windows Device Portal)
- La API HolographicSpace.UserPresence generalmente está deshabilitada para aplicaciones de Unity. Este comportamiento evita un problema que hace que algunas aplicaciones se detengan cuando se voltear el visor, incluso si la configuración para ejecutarse en segundo plano está habilitada. La API ahora está habilitada para las versiones de Unity 2018.4.18 y posteriores, y 2019.3.4 y versiones posteriores.
- Se ha corregido un problema que provocaba que las aplicaciones de HoloLens que cambiaban su formato de píxel se representaran en negro en el emulador de HoloLens.
- Se ha corregido un problema acerca de los inicios de la Fotos inicios iniciales después de actualizar desde la versión de 1903.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, versión 2004  
- Compilación : 19041.1103

La actualización de software principal de mayo de 2020 para HoloLens 2, *Windows Holographic, versión 2004* incluye una gran cantidad de nuevas y emocionantes capacidades, como la compatibilidad con Windows Autopilot, el modo oscuro de la aplicación, la compatibilidad con Ethernet USB para puntos de acceso 5G/LTE y mucho más. Para actualizar a la versión **** más reciente, abre la aplicación Configuración, ve a Actualizar & Seguridad y selecciona el   botón **Buscar** ****   actualizaciones. 

|             Característica                              |          Descripción                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       WindowsAutopilot                          |          Configurar previamente y configurar sin problemas nuevos dispositivos para la producción mediante Windows AutoPilot                 |
|       Compatibilidad con FIDO 2                             |          Compatibilidad con las claves de seguridad fido2 para habilitar la autenticación rápida y segura para dispositivos compartidos            |
|       Aprovisionamiento mejorado                      |          Aplicar sin problemas un paquete de aprovisionamiento desde una unidad USB a hololens                              |
|       Estado de instalación de la aplicación                 |          Comprobar el estado de instalación en la aplicación Configuración para aplicaciones se ha pasado a HoloLens 2 a través de MDM               |
|       Proveedores de servicios de configuración (SPC)   |          Se agregaron nuevos proveedores de servicios de configuración para mejorar las capacidades de control de administración                 |
|       Compatibilidad con USB 5G/LTE                       |          La funcionalidad Ethernet USB expandida permite la compatibilidad con 5G/LTE                                    |
|       Modo de aplicación oscura                              |          Modo de aplicación oscuro disponible para aplicaciones que admiten modos oscuros y claros, lo que mejora la experiencia de visualización        |
|       Comandos de voz                             |          Compatibilidad con comandos de voz del sistema adicionales para controlar HoloLens manos libres                           |
|       Mejoras de seguimiento de manos                 |          Las mejoras de seguimiento de manos hacen que los botones y las interacciones de pizarra 2D sea más precisa                        |
|       Mejoras y correcciones de calidad                 |          Diversas mejoras en el rendimiento y la confiabilidad del sistema en toda la plataforma                            |

### <a name="support-for-windows-autopilot"></a>Compatibilidad con Windows Autopilot

Windows Autopilot para HoloLens 2 permite al canal de ventas del dispositivo inscribir previamente HoloLens en el inquilino de Intune. Cuando llegan los dispositivos, están listos para implementarse automáticamente como dispositivos compartidos en el espacio empresarial. Para aprovechar la implementación propia, el dispositivo debe conectarse a una red durante la primera pantalla de la configuración mediante un USB-C-to-Ethernet.

Después de que un usuario inicie el proceso de implementación automática de Autopilot, el proceso completa los pasos siguientes:

1. Unir el dispositivo a Azure Active Directory (Azure AD).
1. Usar Azure AD para inscribir el dispositivo en Microsoft Intune (u otro servicio MDM).
1. Descargar las directivas de destino del dispositivo, los certificados y los perfiles de red.
1. Aprovisionar el dispositivo.
1. Mostrar la pantalla de inicio de sesión al usuario.

Obtenga más información en la [guía de evaluación de Windows Autopilot para HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot).

*Póngase en contacto con el Administrador de cuentas para unirse a la vista previa de AutoPilot ahora. Los dispositivos listos para Autopilot empezarán a enviarse pronto.*

### <a name="fido2-security-key-support"></a>Soporte de clave de seguridad FIDO2

Algunos usuarios comparten un dispositivo HoloLens con otros en un entorno laboral o educativo. Por lo tanto, es importante que los usuarios puedan fácilmente sin escribir nombres de usuario largos y contraseñas. Fast Identity Online (FIDO) permite a cualquier persona de su organización (inquilino de Azure AD) iniciar sesión sin problemas en HoloLens sin especificar un nombre de usuario o contraseña.

Las claves de seguridad FIDO2 son un método de autenticación sin contraseña basado en estándares "nophishable" que puede venir en cualquier factor de forma. FIDO es un estándar abierto para la autenticación sin contraseña. Permite a los usuarios y organizaciones iniciar sesión en sus recursos sin un nombre de usuario o contraseña. En su lugar, usan una clave de seguridad externa o una clave de plataforma integrada en un dispositivo.

Para empezar, vea [Enable passwordless security key sign-in](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key).

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Inscripción de MDM mejorada a través del paquete de aprovisionamiento

Los paquetes de aprovisionamiento le permiten establecer la configuración de HoloLens a través de un archivo de configuración en lugar de a través de la experiencia lista para configurar HoloLens. Anteriormente, los paquetes de aprovisionamiento tenían que copiarse en la memoria interna de HoloLens. Ahora pueden estar en una unidad USB para que sean más fáciles de reutilizar en varios dispositivos HoloLens y puedes aprovisionar dispositivos en paralelo. Los paquetes de aprovisionamiento ahora también admiten un campo para inscribirse en la administración de dispositivos, por lo que no hay ninguna configuración manual después del aprovisionamiento.

Para probarlo:

1. Descarga la versión más reciente del Diseñador de configuraciones de Windows desde la Tienda Windows en tu PC.
1. Seleccione **Aprovisionar dispositivos HoloLens**  >  **Aprovisionar dispositivos HoloLens 2**.
2. Cree el perfil de configuración. A continuación, copie todos los archivos creados en un dispositivo de almacenamiento USB-C.
3. Conecta el dispositivo USB-C a cualquier HoloLens recién parpadeado. A continuación, **presione los botones de**  +  **encendido** del volumen hacia abajo para aplicar el paquete de aprovisionamiento.

### <a name="line-of-business-application-install-status"></a>Estado de instalación de la aplicación de línea de negocio

La implementación y administración de aplicaciones MDM para aplicaciones de línea de negocio es fundamental para HoloLens. Los administradores y los usuarios deben ver el estado de instalación de la aplicación para realizar auditorías y diagnósticos. En esta versión, agregamos más detalles en **Configuración**Cuentas acceso a  >  ****  >  **trabajo o escuela**Haga clic en la información de  >  **su**  >  **cuenta**.

### <a name="additional-csps-and-policies"></a>Directivas y CSP adicionales

Un [proveedor de servicios de configuración (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) es una interfaz para leer, establecer, modificar o eliminar opciones de configuración en un dispositivo. En esta versión, agregamos compatibilidad con más directivas para aumentar el control que los administradores tienen sobre los dispositivos HoloLens implementados. Para obtener la lista de CSP compatibles con HoloLens, vea [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

Novedades de esta versión:

**Policy CSP** 

El proveedor de servicios de configuración de directivas permite a la empresa configurar directivas en dispositivos Windows. En esta versión, agregamos nuevas directivas para HoloLens, que se enumeran aquí. Para obtener más información, vea [Policy CSP supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

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

El proveedor de servicios de configuración NetworkQoSPolicy crea directivas de calidad de servicio (QoS) de red. Una directiva de QoS realiza un conjunto de acciones en el tráfico de red en función de un conjunto de condiciones coincidentes. Para obtener más información, [vea NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Compatibilidad ethernet USB expandida para dispositivos con 5G/LTE tethered

Se agregó compatibilidad para habilitar determinados dispositivos de banda ancha móvil, como teléfonos 5G/LTE y puntos de acceso Wi-Fi, cuando están conectados a HoloLens 2 a través de USB. Estos dispositivos ahora se muestran en la configuración **de red** como otra conexión Ethernet. (No se admiten dispositivos de banda ancha móvil que requieren un controlador externo). Esta funcionalidad habilita las conexiones de ancho de banda alto Wi-Fi no está disponible y Wi-Fi el tethering no es lo suficientemente funcional. Para obtener más información sobre los dispositivos USB compatibles, [consulta Conectarse a Bluetooth dispositivos USB-C y USB-C](https://docs.microsoft.com/hololens/hololens-connect-devices).  

### <a name="hand-tracking-improvements"></a>Mejoras de seguimiento de manos

Esta versión incluye varias mejoras de seguimiento de manos:

- **Estabilidad de la pose de apuntar:** El sistema ahora se resiste a doblar el dedo índice cuando la palma lo oculta. Este cambio mejora la precisión al presionar botones, escribir, desplazar contenido y mucho más. 
- **Pulsaciones de aire accidentales reducidas:** Hemos mejorado la detección del gesto de pulsación de aire. Ahora hay menos activaciones accidentales en varios escenarios comunes, como cuando coloca las manos a los lados.
- **Confiabilidad del conmutador de usuario:** El sistema ahora es más rápido y confiable al actualizar el tamaño de la mano cuando compartes un dispositivo.
- **Reducción del robo de mano:** Hemos mejorado el tratamiento de los casos en los que hay más de dos manos a la vista de los sensores. Si varias personas trabajan juntas, ahora hay una probabilidad mucho menor de que la mano rastreada "saltará" del usuario a la mano de otra persona en la escena.
- **Confiabilidad del sistema:** Se ha corregido un problema que provocaba que el seguimiento de manos dejara de funcionar cuando el dispositivo estaba bajo carga alta.

### <a name="dark-mode"></a>Modo oscuro

Muchas aplicaciones de Windows ahora admiten modos oscuros y claros. Los usuarios de HoloLens 2 pueden elegir el modo predeterminado para las aplicaciones que admiten ambas. Después de la actualización, el modo de aplicación predeterminado es "oscuro", pero puedes cambiar fácilmente esta configuración: Navegue a Configuración Colores del sistema ****  >  ****  >  ****  >  **Elija el modo de aplicación predeterminado.** 

Estas aplicaciones "en cuadro" admiten el modo oscuro: 

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

![Ventanas en mosaico de modo oscuro](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Comandos de voz del sistema

Ahora puedes usar comandos de voz con cualquier aplicación en el dispositivo. Para obtener más información, [vea Use your voice to operate HoloLens](https://docs.microsoft.com/hololens/hololens-cortana). Vea también [Idiomas admitidos para HoloLens 2](https://docs.microsoft.com/hololens/hololens2-language-support).  

### <a name="cortana-updates"></a>Actualizaciones de Cortana

La aplicación actualizada se integra con Microsoft 365 para ayudarte a realizar más cosas en todos los dispositivos (actualmente solo US-English). En HoloLens 2, Cortana ya no admite determinados comandos específicos del dispositivo, como ajustar el volumen o reiniciar. Estas opciones ahora son compatibles con los nuevos comandos de voz del sistema. Obtenga más información sobre la nueva aplicación Cortana en nuestro [blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### <a name="quality-improvements-and-fixes"></a>Mejoras y correcciones de calidad

Mejoras y correcciones también en la actualización:  
- Se introdujo un sistema de calibración de pantalla activo. Esta característica mejora la estabilidad y alineación de los hologramas. Ahora permanecen en su lugar cuando mueves la cabeza de un lado a otro.
- Se ha corregido un error que Wi-Fi streaming a HoloLens se interrumpía periódicamente. Si una aplicación indica que necesita streaming de baja latencia, implemente la corrección llamando a la [función SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Se ha corregido un error que se produjo durante la transmisión en modo de investigación.
- Se ha corregido un error en el que, en algunos casos, el usuario correcto no se mostraría en la pantalla de inicio de sesión al reanudar una sesión.
- Se ha corregido un problema por el que los usuarios no podían exportar registros MDM a través **de Configuración.**
- Se ha corregido un problema por el que la precisión del seguimiento de ojos inmediatamente después de la configuración inmediata podría ser inferior a la esperada.
- Se ha corregido un problema por el que el subsistema de seguimiento ocular no se inicializaba ni realizaba la calibración en determinadas condiciones.
- Se ha corregido un problema por el que se solicitaba la calibración ocular para un usuario ya calibrado.
- Se ha corregido un problema por el que un controlador se bloqueaba durante la calibración ocular.
- Se ha corregido un problema por el que las pulsaciones repetidas del botón de encendido podían provocar un tiempo de espera del sistema de 60 segundos y un bloqueo del shell.
- Estabilidad mejorada para búferes de profundidad.
- Se agregó un **botón Compartir** en el Centro de opiniones para que los usuarios puedan compartir comentarios más fácilmente.
- Se ha corregido un error en el que RoboRaid wan no se instaló correctamente.

### <a name="known-issues"></a>Problemas conocidos

- Un problema con el lenguaje del sistema de zh-CN impide que los comandos de voz capturen una realidad mixta o muestren la dirección IP del dispositivo.
- Un problema requiere que inicies la aplicación Cortana después de iniciar el dispositivo para usar la activación de voz "Hola Cortana". Si actualizaste desde una compilación de 18362, es posible que también veas un segundo icono de aplicación para la versión anterior de la aplicación Cortana que ya no funciona en **Inicio**.

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, versión 1903- May 2020 Update 
- Compilación 18362.1061

Esta actualización de calidad mensual no contiene cambios notables porque el equipo estaba trabajando en windows Holographic versión 2004 May Update, como se describió anteriormente.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, versión 1903- Actualización de abril de 2020
- Compilación 18362.1059

**Modo oscuro para aplicaciones compatibles** 

Muchas aplicaciones de Windows admiten el modo oscuro y claro. Los clientes de HoloLens 2 ahora pueden elegir el modo predeterminado para las aplicaciones que admiten ambas esquemas de color. En función de los comentarios de los clientes, establecemos el modo de aplicación predeterminado en "oscuro", pero puede cambiar fácilmente esta configuración en cualquier momento: vaya a Configuración **> System > Colors** para buscar "Elegir el modo de aplicación **predeterminado".**

Estas aplicaciones "en cuadro" admiten el modo oscuro:
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
- Se garantiza que las superposiciones del shell se incluyen en capturas de realidad mixta.
- Los desarrolladores irreales ahora pueden usar la página Vista 3D en Device Portal para probar y depurar sus aplicaciones.
- Se ha mejorado la estabilidad del holograma en la captura de realidad mixta cuando se usa el algoritmo *HolographicDepthReprojectionMethod DepthReprojection.*
- Se ha corregido el error "WinRT IStreamSocketListener API Class not registered" en aplicaciones ARM de 32 bits.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic, versión 1903- Actualización de marzo de 2020 
- Compilación 18362.1056

Mejoras y correcciones en la actualización:

- Se ha mejorado la estabilidad del holograma en la captura de realidad mixta cuando se usa el algoritmo *HolographicDepthReprojectionMethod AutoPlanar.*
- Se aseguró de que el sistema de coordenadas adjunto a una muestra de MF de profundidad sea coherente con la documentación pública.
- Se ha mejorado la productividad de los desarrolladores al permitir a los clientes pegar grandes cantidades de texto a través del portal del dispositivo.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic, versión 1903- Actualización de febrero de 2020 
- Compilación 18362.1053

Mejoras y correcciones en la actualización:

- Deshabilitada temporalmente la API HolographicSpace.UserPresence para aplicaciones unity. Este cambio evita un problema que provocaba que algunas aplicaciones se pausase cuando se volteó el visor, incluso si la configuración "ejecutar en segundo plano" estaba habilitada.
- Se ha corregido un bloqueo de HUP aleatorio causado por el seguimiento de manos, en el que el usuario observó que una interfaz de usuario se congelaba y, a continuación, regresaba al shell después de varios segundos.
- Se ha mejorado el seguimiento de las manos para que, cuando se agarre con el dedo índice, la parte superior del dedo tenga menos probabilidades de rizarse inesperadamente.
- Se ha mejorado la confiabilidad del seguimiento de la cabeza, la asignación espacial y otros tiempos de ejecución.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, versión 1903: actualización de enero de 2020 
- Compilación 18362.1043
 
Mejoras y correcciones en la actualización:

- Estabilidad mejorada para aplicaciones exclusivas al trabajar con el emulador HoloLens 2.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, versión 1903- Actualización de diciembre de 2019 
- Compilación 18362.1042

Mejoras y correcciones en la actualización:

- Se han introducido correcciones de reproducción de última fase (LSR). Se ha mejorado la representación visual de hologramas para que parezcan más estables y nítidos al tener en cuenta con más precisión su profundidad. Este síntoma será más perceptible después de esta actualización si las aplicaciones no establecen la profundidad de los hologramas correctamente.
- Se ha corregido la estabilidad de las aplicaciones exclusivas y la navegación entre aplicaciones exclusivas.
- Se ha resuelto un problema por el que la captura de realidad mixta no podía grabar vídeo después de que el dispositivo estaba en estado de espera durante varios días.
- Estabilidad del holograma mejorada.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, versión 1903- Actualización de noviembre de 2019 
- Compilación 18362.1039

Mejoras y correcciones en la actualización:

- Se ha corregido la **funcionalidad de Seleccionar** comandos de voz durante la configuración inicial de en-CA y en-AU.
- Calidad visual mejorada de los objetos colocados lejos en las versiones más recientes de Unity y Mixed Reality Toolkit (MRTK).
- Se han corregido problemas de abordamiento con aplicaciones holográficas que se atascaban en un estado de pausa al iniciarse hasta que se abría el menú Inicio y, a continuación, se cerraba.
- Correcciones y mejoras de conformidad de tiempo de ejecución de OpenXR para HoloLens 2 y el emulador.
