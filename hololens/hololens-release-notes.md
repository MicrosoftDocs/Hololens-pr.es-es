---
title: HoloLens 2 notas de la versión
description: Manténgase al día con todas las actualizaciones de cada versión HoloLens 2 lanzamiento.
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
ms.openlocfilehash: 18b0d6b304e8de8c85caeec9f3e8ba190647aaec
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310227"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 notas de la versión

Para asegurarse de que tiene una experiencia productiva con los dispositivos HoloLens, seguimos lanzando actualizaciones de características, errores y seguridad. En esta página, puede ver las novedades de HoloLens cada mes. Para obtener la actualización HoloLens 2 más reciente, puede buscar actualizaciones y actualizar manualmente u obtener la actualización flash completa (FFU) para flashear el dispositivo a través de Advanced [Recovery Companion](hololens-recovery.md#clean-reflash-the-device). [](hololens-update-hololens.md#check-for-updates-and-manually-update) La [descarga](https://aka.ms/hololens2download) se mantiene actualizada y proporciona la compilación más reciente disponible con carácter general.

>[!NOTE]
> Nos complace empezar a pasar nuevas características a Windows Insiders de nuevo. Se realizará un vuelo al canal de desarrollo para obtener las actualizaciones más recientes. Continuaremos con nuestras notas de [**HoloLens Insider**](hololens-insider.md) a medida que agreguemos más características y actualizaciones a nuestras Windows Insider compilaciones. Prepárese para mezclar estas actualizaciones en su realidad.

Consulte las notas de la versión relacionadas:

- [Visite el archivo del emulador de HoloLens.](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic, versión 20H2: actualización de abril de 2021
- Compilación 19041.1144

Mejoras y correcciones en la actualización:

- Corrige un problema en torno a los informes de estado de instalación de aplicaciones de línea de negocio.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic, versión 1903: actualización de abril de 2021
- Compilación 18362.1108

Mejoras y correcciones en la actualización:

- Soluciona un problema por el que la aplicación Configuración se bloquea al intentar cambiar una contraseña de una cuenta local.

## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, versión 20H2: actualización de marzo de 2021
- Compilación 19041.1140

Mejoras y correcciones en la actualización:

- Los clientes que usan AdvancedPhotoCapture o LowObjPhotoCapture para capturar fotos con HoloLens 2 ahora pueden recuperar la posición de la cámara hasta 3 segundos después de capturar la foto.
- Corrección de una pérdida de memoria en Portal de dispositivos Service, el problema provocó un aumento del uso de memoria por parte del servicio que provocó que otras aplicaciones no asignaran memoria.
- Se ha corregido un problema por el que los usuarios inscritos en el lanzamiento por fases no pueden iniciar sesión en el dispositivo.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, versión 1903: actualización de marzo de 2021
- Compilación 18362.1102

Mejoras y correcciones en la actualización:

- Corrección de una pérdida de memoria en Portal de dispositivos Service, el problema provocó un aumento del uso de memoria por parte del servicio que provocó que otras aplicaciones no asignaran memoria.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, versión 20H2: actualización de febrero de 2021
- Compilación 19041.1136

Mejoras y correcciones en la actualización:

- Corrige un problema en torno a la configuración inicial del dispositivo y las actualizaciones de la aplicación de almacenamiento.
- Soluciona un problema en torno a las actualizaciones y los vuelos de versiones posteriores de HoloLens.
- Se han quitado los certificados preinstalados no usados del almacén raíz de eSIM de los dispositivos HoloLens.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, versión 1903: actualización de febrero de 2021
- Compilación 18362.1098

Esta actualización de calidad mensual no contiene ningún cambio importante; le recomendamos que pruebe nuestras compilaciones más recientes para Windows Holographic, versión 2004.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, versión 20H2: actualización de enero de 2021
- Compilación 19041.1134

Mejoras y correcciones en la actualización:

- Rendimiento mejorado durante el inicio, la reanudación y el cambio de usuario cuando hay muchos usuarios en el dispositivo.
- Se ha agregado compatibilidad con arm32 para el [modo de investigación](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode).

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, versión 1903- Actualización de enero de 2021
- Compilación 18362.1091

Esta actualización de calidad mensual no contiene ningún cambio importante, le recomendamos que pruebe nuestras compilaciones más recientes para Windows Holographic, versión 2004.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, versión 20H2: actualización de diciembre de 2020
- Compilación 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalación de aplicaciones en HoloLens 2 a través de Instalador de aplicación

Vamos a **agregar una nueva funcionalidad (Instalador de aplicación)** para permitirle instalar aplicaciones más fácilmente en los dispositivos HoloLens 2 dispositivos. La característica estará en **modo predeterminado para dispositivos no administrados.** Para evitar interrupciones en las empresas, el instalador de la aplicación **no estará disponible para los dispositivos administrados** en este momento.  

Un dispositivo se considera "administrado" si **se** cumple alguna de las siguientes condiciones:
- MDM [inscrito](hololens-enroll-mdm.md)
- Configurado con el [paquete de aprovisionamiento](hololens-provisioning.md)
- Identidad [de usuario](hololens-identity.md) Azure AD

Ahora puede instalar aplicaciones sin necesidad de habilitar el modo de desarrollador ni usar Portal de dispositivos.  Simplemente descargue (a través de USB o a través de Edge) el paquete de Appx en el dispositivo y vaya al paquete de Appx en el Explorador de archivos para que se le pida que arranque la instalación.  Como alternativa, [inicie una instalación desde una página web](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  Al igual que las aplicaciones que instala desde Microsoft Store o la instalación local mediante la funcionalidad de [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) implementación de [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) aplicaciones LOB de MDM, las aplicaciones deben estar firmadas digitalmente con la herramienta de firma y el certificado que se usa para firmar debe ser de confianza para el dispositivo HoloLens antes de que se pueda implementar la aplicación.

**Instrucciones de instalación de la aplicación.**

1.  Asegúrese de que el dispositivo no se considera administrado.
1.  Asegúrese de que el HoloLens 2 está encendido y conectado al equipo.
1.  Asegúrese de que ha iniciado sesión en el HoloLens 2 dispositivo.
1.  En el equipo, vaya a la aplicación personalizada y copie yourapp.appxbundle en yourdevicename\Internal Storage\Downloads.   Una vez que haya terminado de copiar el archivo, puede desconectar el dispositivo.
1.  En el HoloLens 2, abra el menú Inicio, seleccione Todas las aplicaciones e inicie Explorador de archivos aplicación.
1.  Vaya a la carpeta Descargas. En el panel izquierdo de la aplicación, seleccione Este dispositivo en primer lugar y, a continuación, vaya a Descargas.
1.  Seleccione el archivo yourapp.appxbundle.
1.  La Instalador de aplicación se iniciará. Seleccione el botón Instalar para instalar la aplicación.
La aplicación instalada se iniciará automáticamente al finalizar la instalación.

Puede encontrar aplicaciones de ejemplo en GitHub de ejemplos [universales de Windows](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) para probar este flujo.

Obtenga información sobre el proceso completo de [instalación de aplicaciones en HoloLens 2 con el Instalador de aplicación](app-deploy-app-installer.md).  

![Instalación de ejemplos de MRTK mediante Instalador de aplicación](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Mejoras y correcciones en la actualización:

- El seguimiento de manos ahora mantiene el seguimiento en muchos casos nuevos en los que se habría perdido la mano anteriormente.  En algunos de estos nuevos casos, solo la posición de la mano sigue actualciendo en función de la mano real del usuario, mientras que las demás uniones se deducen en función de una posición anterior.  Este cambio ayuda a mejorar la coherencia del seguimiento en movimientos como las abofetas, el lanzamiento, la desenlazándose y el abarrote.  También ayuda en casos en los que la mano está cerca de una superficie o que contiene un objeto.  Cuando se inferan las [](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) uniones de mano, el valor de precisión por conjunta se establecerá en "Aproximado" en lugar de "Alto".
- Se ha corregido un problema por el que el restablecimiento del PIN Azure AD las cuentas mostraría el error "Se ha producido un error.
- Los usuarios deben ver mucho menos bloqueos de OOBE posteriores al arranque al iniciar ET, Iris desde la aplicación de configuración, nuevo usuario o notificación del sistema.
- Los usuarios deben tener una zona horaria correcta que salga de la configuración automática.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, versión 1903: actualización de diciembre de 2020
- Compilación 18362.1088

Esta actualización de calidad mensual no contiene ningún cambio importante; le recomendamos que pruebe la versión más reciente de Windows Holographic, la versión 20H2 - Actualización de diciembre de 2020 y la nueva característica Instalador de aplicación agregada en la compilación.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, versión 20H2
- Compilación 19041.1128

Windows Holographic, versión 20H2 ya está disponible y ofrece un gran conjunto de nuevas características para HoloLens 2 usuarios y profesionales de IT. Desde el posicionamiento automático de los ojos hasta el Administrador de certificados en Configuración, hasta la funcionalidad mejorada del modo quiosco y las nuevas funcionalidades de configuración de Autopilot. Esta nueva actualización permite a los equipos de IT tomar un control más granular de la configuración y administración de dispositivos HoloLens, y ofrece a los usuarios experiencias holográficas aún más fluidas. 

Esta versión más reciente es una actualización mensual a la versión 2004, pero esta vez se incluyen nuevas características. El número de compilación principal seguirá siendo el mismo y Windows Update indicará una versión mensual de la versión 2004 (compilación 19041). Puede ver el número de compilación en la pantalla Configuración > Acerca de para confirmar que se encuentra en la última compilación disponible 19041.1128+. Para actualizar a la versión más reciente, abra la aplicación Configuración, vaya a Actualizar & Seguridad y pulse Buscar actualizaciones. Para obtener más información sobre cómo administrar las actualizaciones de HoloLens, visite [esta página](https://docs.microsoft.com/hololens/hololens-updates).

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Novedades de Windows Holographic, versión 20H2  

| Característica                                              | Descripción                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Compatibilidad con la posición automática de los ojos](hololens-release-notes.md#auto-eye-position-support) | Calcula activamente las posiciones de los ojos sin que los usuarios pasen por la calibración de Eye Tracking.   |
| [Administrador de certificados](hololens-release-notes.md#certificate-manager)   | Permite que los nuevos métodos más sencillos instalen y quiten certificados de la aplicación Configuración.     |
| [Inicio automático del aprovisionamiento desde USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | El aprovisionamiento de paquetes en unidades USB solicita automáticamente la página de aprovisionamiento en OOBE.                                                         |
| [Confirmación automática de paquetes de aprovisionamiento en OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Los paquetes de aprovisionamiento se aplican automáticamente durante la OOBE desde la página de aprovisionamiento.                                                         |
| [Aprovisionamiento automático sin usar la interfaz de usuario](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Cómo combinar el inicio automático de aprovisionamiento y la confirmación automática juntos. |
| [Uso de Autopilot con Wi-Fi conexión](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Use Autopilot desde el dispositivo Wi-Fi sin necesidad de adaptador Ethernet. |
| [CSP de Tenantlockdown y Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Una vez aplicada la inscripción de inquilinos y la directiva, el dispositivo solo se puede inscribir en ese inquilino cada vez que se restablezca o se vuelva a parpadear el dispositivo. |
| [Acceso asignado global](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Nuevo método de configuración para el modo de pantalla completa de varias aplicaciones que aplica la pantalla completa en el nivel del sistema, lo que lo hace aplicable a todos.                  |
| [Inicio automático de una aplicación en quiosco de varias aplicaciones](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Establece una aplicación que se iniciará automáticamente al iniciar sesión en un modo de pantalla completa de varias aplicaciones.                                                        |
| [Cambios de comportamiento del modo de pantalla completa para el control de errores](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | El error del modo de pantalla completa ahora tiene una reserva restrictiva.                                                                                                |
| [Directivas de HoloLens](hololens-release-notes.md#hololens-policies)                                    | Nuevas directivas para HoloLens.     |
| [Pertenencia a Azure AD grupo de almacenamiento en caché para quiosco sin conexión](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | La nueva directiva permite a los usuarios usar la memoria caché de pertenencia a grupos para usar el modo quiosco sin conexión durante un número establecido de días.                                        |
| [Nuevas directivas de restricción de dispositivos para HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Directivas de administración de dispositivos habilitadas recientemente para HoloLens 2.                                                                                |
| [Nuevas directivas de energía para HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Directivas recién admitidas para la configuración de tiempo de espera de energía.  |
| [Actualizar directivas](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Directivas recién habilitadas que permiten el control de las actualizaciones.           |
| [Visibilidad de la página Configuración habilitada para HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Directiva para elegir qué páginas se ven en la aplicación Configuración.             |
| [Modo de investigación](hololens-release-notes.md#research-mode) | Uso del modo de investigación en HoloLens 2. |
| [Longitud de grabación aumentada](hololens-release-notes.md#recording-length-increased) | Las grabaciones de MRC ya no se han recortado a 5 minutos. |
| [Mejoras y correcciones en la actualización](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Correcciones adicionales en la actualización.   |

### <a name="auto-eye-position-support"></a>Compatibilidad con la posición del ojo automático

En HoloLens 2, las posiciones de los ojos permiten un posicionamiento preciso del holograma, una experiencia de visualización cómoda y una calidad de visualización mejorada. Las posiciones de los ojos se calculan internamente como parte del cálculo del seguimiento de los ojos. Sin embargo, esto requiere que cada usuario pase por la calibración del seguimiento de los ojos, incluso cuando la experiencia no requiera la entrada de mirada con los ojos.

**La posición automática de los ojos (AEP)** permite estos escenarios con una manera sin interacción de calcular las posiciones de los ojos para el usuario. La posición automática de los ojos comienza a funcionar en segundo plano automáticamente desde el momento en que el usuario coloca el dispositivo. Si el usuario no tiene una calibración de seguimiento de los ojos anterior, la posición del ojo automático comenzará a proporcionar las posiciones de los ojos del usuario al sistema de visualización después de un tiempo de procesamiento de 20 a 30 segundos. Los datos de usuario no se conservan en el dispositivo y, por lo tanto, este proceso se repite si el usuario despeda y vuelve a activar el dispositivo o si el dispositivo se reinicia o se reactiva de la suspensión.

Hay algunos cambios de comportamiento del sistema con la característica Posición automática de los ojos cuando un usuario sin problemas coloca en el dispositivo. En este contexto, un usuario sin problemas hace referencia a alguien que no ha pasado por el proceso de calibración del seguimiento de los ojos en el dispositivo anteriormente.

| Aplicación activa | Comportamiento anterior | Comportamiento de Windows Holographic, versión 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Aplicación habilitada para no mirada o Shell holográfico |Se muestra el cuadro de diálogo del símbolo del sistema de calibración de seguimiento de los ojos. | No se muestra ningún mensaje. |
| Aplicación habilitada para mirada | Se muestra el cuadro de diálogo del símbolo del sistema de calibración de seguimiento de los ojos. | El símbolo del sistema de calibración de seguimiento de los ojos solo se muestra cuando la aplicación accede a la secuencia de mirada con los ojos. |

Si el usuario pasa de una aplicación habilitada para no mirada a una que accede a los datos de mirada, se mostrará el símbolo del sistema de calibración. 

El resto del comportamiento del sistema será similar a cuando el usuario actual no tenga una calibración de seguimiento de los ojos activa. Por ejemplo, el gesto De inicio con una mano no se habilitará. No habrá ningún cambio en la experiencia de configuración rápida para la configuración inicial.

En el caso de las experiencias que requieren datos de mirada con los ojos o un posicionamiento de holograma muy preciso, se recomienda que los usuarios sin problemas ejecuten la calibración del seguimiento ocular. Es accesible desde el símbolo del sistema de calibración de seguimiento ocular o iniciando la aplicación Configuración desde el menú inicio y seleccionando System **> Calibration > Eye Calibration > Run eye calibration**.

Esta información se puede encontrar más adelante con [otra información de calibración](hololens-calibration.md#auto-eye-position-support). 

### <a name="certificate-manager"></a>Administrador de certificados

- Se han mejorado las herramientas de auditoría, diagnóstico y validación para la seguridad y el cumplimiento de dispositivos mediante el nuevo Administrador de certificados. Esta funcionalidad le permitirá implementar, solucionar problemas y validar los certificados a escala en entornos comerciales.

En Windows Holographic versión 20H2, vamos a agregar un administrador de certificados en la aplicación HoloLens 2 configuración. Vaya a **Configuración > actualizar & seguridad > certificados**. Esta característica proporciona una manera sencilla y fácil de ver, instalar y quitar certificados en el dispositivo. Con el nuevo Administrador de certificados, los administradores y los usuarios ahora tienen herramientas mejoradas de auditoría, diagnóstico y validación para garantizar que los dispositivos sigan siendo seguros y compatibles. 

-   **Auditoría:** Capacidad para validar que un certificado está implementado correctamente o para confirmar que se quitó correctamente. 
-   **Diagnóstico:** Cuando surgen problemas, validar que existen los certificados adecuados en el dispositivo ahorra tiempo y ayuda a solucionar problemas. 
-   **Validación:** Comprobar que un certificado sirve para el propósito previsto y es funcional, puede ahorrar mucho tiempo, especialmente en entornos comerciales antes de implementar certificados a mayor escala.

Para buscar rápidamente un certificado específico en la lista, hay opciones para ordenar por nombre, almacén o fecha de expiración. Los usuarios también pueden buscar directamente un certificado. Para ver las propiedades de certificado individuales, seleccione el certificado y haga clic en **Información**. 

La instalación de certificados admite actualmente archivos .cer y .crt. Los propietarios de dispositivos pueden instalar certificados en la máquina local y el usuario actual.  todos los demás usuarios solo pueden instalar en el usuario actual. Los usuarios solo pueden quitar los certificados instalados directamente desde la interfaz de usuario configuración. Si un certificado se ha instalado a través de otros medios, también debe quitarse mediante el mismo mecanismo.

#### <a name="to-install-a-certificate"></a>Para instalar un certificado: 

1.  Conecte el HoloLens 2 a un equipo.
1.  Coloque el archivo de certificado que desea instalar en una ubicación del HoloLens 2.
1.  Vaya a **Configuración App > Update & Security > Certificates** y seleccione Install a certificate (Instalar un certificado).
1.  Haga **clic en Importar** archivo y vaya a la ubicación en la que guardó el certificado.
1.  Seleccione **Store Location (Ubicación de la tienda).**
1.  Seleccione **Almacén de certificados.**
1.  Haga clic en **Instalar**.

El certificado debe estar ahora instalado en el dispositivo.

#### <a name="to-remove-a-certificate"></a>Para quitar un certificado: 
1. Vaya a **Configuración App > Update and Security > Certificates**(Actualización y seguridad de > certificados).
1. Busque el certificado por nombre en el cuadro de búsqueda.
1. Seleccione el certificado.
1. Haga clic **en Quitar.**
1. Seleccione **Sí** cuando se pida confirmación.

![Visor de certificados en la aplicación Configuración](images/certificate-viewer-device.jpg)

![Imagen que muestra cómo usar la interfaz de usuario de certificado para instalar un certificado](images/certificate-device-install.jpg)

Esta información se puede encontrar más adelante [en una nueva página del Administrador de certificados](certificate-manager.md).

### <a name="auto-launch-provisioning-from-usb"></a>Aprovisionamiento de inicio automático desde USB

- Procesos automatizados que permiten una menor interacción del usuario cuando se usan unidades USB con paquetes de aprovisionamiento durante la OOBE.

Antes de esta versión, los usuarios tenían que iniciar la pantalla de aprovisionamiento manualmente durante la OOBE para aprovisionar mediante una combinación de botones. Ahora los usuarios pueden omitir la combinación de botones mediante un paquete de aprovisionamiento en una unidad de almacenamiento USB. 

1. Conecte la unidad USB con el paquete de aprovisionamiento durante el primer momento interactuable de OOBE.
1. Cuando el dispositivo esté listo para aprovisionarse, se abrirá automáticamente el símbolo del sistema con la página de aprovisionamiento. 

Nota: Si una unidad USB se deja conectada mientras el dispositivo arranca, OOBE enumerará el dispositivo de almacenamiento USB existente, así como observará si hay otras adicionales conectadas.

Para obtener más información sobre cómo aplicar paquetes de aprovisionamiento durante la OOBE, visite la documentación de aprovisionamiento [de HoloLens.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Puede encontrar información adicional [sobre el aprovisionamiento de inicio](hololens-provisioning.md#auto-launch-provisioning-from-usb) automático desde un USB en la documentación de aprovisionamiento de HoloLens.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Confirmación automática de paquetes de aprovisionamiento en OOBE
- Proceso automatizado que permite una menor interacción del usuario; cuando se muestra la página Paquete de aprovisionamiento, se aplicarán automáticamente todos los paquetes enumerados.

Cuando aparece la pantalla principal de aprovisionamiento, la OOBE se cuenta 10 segundos antes de empezar automáticamente a aplicar todos los paquetes de aprovisionamiento. Los usuarios todavía [pueden confirmar o cancelar en](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) estos 10 segundos después de comprobar los paquetes que esperaban.

### <a name="automatic-provisioning-without-using-ui"></a>Aprovisionamiento automático sin usar la interfaz de usuario
- Procesos automáticos combinados para interacciones reducidas de dispositivos para el aprovisionamiento. 

Al combinar el inicio automático del aprovisionamiento desde dispositivos USB y la confirmación automática de los paquetes de aprovisionamiento, un usuario puede aprovisionar dispositivos HoloLens 2 automáticamente sin usar la interfaz de usuario del dispositivo ni siquiera llevar el dispositivo. Puede seguir usando la misma unidad USB y el mismo paquete de aprovisionamiento para varios dispositivos. Esto es útil para implementar varios dispositivos a la vez en la misma área. 

1. [Cree un paquete de aprovisionamiento](hololens-provisioning.md) mediante el [Diseñador de configuración de Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Copie el paquete en una unidad de almacenamiento USB.
1. [Flash your HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) to [19041.1361 or newer build](https://aka.ms/hololens2previewdownload). 
1. Cuando [Advanced Recovery Companion haya](https://www.microsoft.com/store/productId/9P74Z35SFRS8) terminado de parpadear el dispositivo, desconecte el cable USB-C. 
1. Conecte la unidad USB al dispositivo.
1. Cuando el HoloLens 2 arranque en OOBE, detectará automáticamente el paquete de aprovisionamiento en la unidad USB e iniciará la página de aprovisionamiento.
1. Después de 10 segundos, el dispositivo aplicará automáticamente el paquete de aprovisionamiento. 

El dispositivo ya está configurado y mostrará [la pantalla Aprovisionamiento correcto](hololens-provisioning.md#automatic-provisioning-without-using-ui).

### <a name="using-autopilot-with-wi-fi-connection"></a>Uso de Autopilot con Wi-Fi conexión
- Se ha quitado la necesidad de adaptadores USB-C para ethernet, lo que reduce las necesidades de hardware, ya que permite que Autopilot funcione en Wi-Fi dispositivos conectados.

Ahora, durante la configuración general, una vez que HoloLens 2 con Wi-Fi, OOBE buscará un perfil de Autopilot para el dispositivo. Si se encuentra uno, se usará para completar el resto del flujo de inscripción y unión de AAD. En otras palabras, el uso de Ethernet a USB-C o Wi-Fi adaptador de USB-C ya no es un requisito, pero siguen funcionando si se proporcionan al principio de la configuración general. Obtenga más información [sobre Autopilot para HoloLens 2 dispositivos](hololens2-autopilot.md).

### <a name="tenantlockdown-csp-and-autopilot"></a>CSP de Tenantlockdown y Autopilot
- Mantiene los dispositivos en el inquilino de la organización bloqueándolos en el inquilino incluso a través del restablecimiento o la reflash del dispositivo. Con mayor seguridad al no permitir la creación de cuentas a través del aprovisionamiento. 

HoloLens 2 dispositivos ahora admiten csp de TenantLockdown a partir de la versión [20H2 de Windows Holographic.](hololens-release-notes.md#windows-holographic-version-20h2) 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP permite HoloLens 2 a la inscripción de MDM solo mediante Autopilot. Una vez que el nodo RequireNetworkInOOBE del CSP de TenantLockdown se establece en un valor true o false (establecido inicialmente) en HoloLens 2, ese valor permanece en el dispositivo a pesar de volver a parpadear, actualizaciones del sistema operativo, etc. 

Una vez que el nodo RequireNetworkInOOBE de los CSP tenantLockdown está establecido en true en HoloLens 2, OOBE espera indefinidamente a que el perfil de Autopilot se descargue y aplique correctamente, después de la conectividad de red. 

Una vez que el nodo RequireNetworkInOOBE de los CSP tenantLockdown está establecido en true en HoloLens 2, las siguientes operaciones no se pueden realizar en OOBE: 
- Creación de un usuario local mediante el aprovisionamiento en tiempo de ejecución 
- Realización de Azure AD operación de combinación mediante el aprovisionamiento en tiempo de ejecución 
- Selección de quién posee el dispositivo en la experiencia de OOBE 

#### <a name="how-to-set-this-using-intune"></a>¿Cómo establecer esto mediante Intune? 
1. Cree un perfil de configuración de dispositivo OMA URI personalizado y especifique true para el nodo RequireNetworkInOOBE, como se muestra a continuación.
El valor de OMA-URI debe ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Establecimiento del bloqueo de tenso mediante OMA-URI](images/hololens-tenant-lockdown.png)

1. Cree un grupo y asigne el perfil de configuración del dispositivo a ese grupo de dispositivos. 

1. Haga que el HoloLens 2 miembro del dispositivo del grupo creado en el paso anterior y desencadene la sincronización.  

Compruebe en el portal de Intune que la configuración del dispositivo se ha aplicado correctamente. Una vez que esta configuración del dispositivo se aplique correctamente en HoloLens 2 dispositivo, los efectos de TenantLockdown estarán activos.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>¿Cómo se desenlace RequireNetworkInOOBE de TenantLockdown HoloLens 2 mediante Intune? 
1. Quite la HoloLens 2 del grupo de dispositivos al que se asignó previamente la configuración del dispositivo creada anteriormente. 

1. Cree un perfil de configuración de dispositivo personalizado basado en uri de OMA y especifique false para RequireNetworkInOOBE, como se muestra a continuación. El valor de OMA-URI debe ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla de la configuración de RequireNetworkInOOBE en false a través de OMA URI en Intune](images/hololens-tenant-lockdown-false.png)

1. Cree un grupo y asigne el perfil de configuración del dispositivo a ese grupo de dispositivos. 

1. Haga que el HoloLens 2 miembro del dispositivo del grupo creado en el paso anterior y desencadene la sincronización.

Compruebe en el portal de Intune que la configuración del dispositivo se ha aplicado correctamente. Una vez que esta configuración del dispositivo se aplique correctamente en HoloLens 2 dispositivo, los efectos de TenantLockdown estarán inactivos. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>¿Qué ocurriría durante la OOBE si el perfil de Autopilot no estásignado en holoLens después de que TenantLockdown se estableciese en true? 
OOBE esperará indefinidamente a que se descargue el perfil de Autopilot y se mostrará el siguiente cuadro de diálogo. Para quitar los efectos de TenantLockdown, el dispositivo debe inscribirse primero con su inquilino original solo mediante Autopilot y RequireNetworkInOOBE debe quitarse como se describe en el paso anterior antes de que se quiten las restricciones introducidas por el CSP de TenantLockdown. 

![Vista en el dispositivo para cuando se aplica la directiva en el dispositivo.](images/hololens-autopilot-lockdown.png)

Esta información se puede encontrar junto con el resto de Autopilot en [TENANTLOCKDOWN CSP y Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot).

### <a name="global-assigned-access--kiosk-mode"></a>Acceso asignado global: modo de pantalla completa
- Se ha reducido la administración de identidades para quiosco, al habilitar el nuevo método de quiosco que aplica el modo de pantalla completa en el nivel del sistema.

Esta nueva característica permite a un administrador de TI configurar un dispositivo HoloLens 2 para el modo de pantalla completa de varias aplicaciones, que es aplicable en el nivel del sistema, no tiene afinidad con ninguna identidad en el sistema y se aplica a todos los usuarios que inician sesión en el dispositivo. Obtenga información detallada sobre esta nueva característica en el quiosco de acceso [asignado global de HoloLens.](hololens-global-assigned-access-kiosk.md)

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Inicio automático de una aplicación en pantalla completa con varias aplicaciones 
- Experiencia centrada en el inicio automático de aplicaciones, lo que aumenta aún más la interfaz de usuario y las selecciones de aplicaciones elegidas para las experiencias de pantalla completa.

Solo se aplica al modo de pantalla completa de varias aplicaciones y solo se puede designar una aplicación para el inicio automático mediante el atributo resaltado a continuación en la configuración de acceso asignado. 

La aplicación se inicia automáticamente cuando el usuario inicia sesión. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Cambios de comportamiento del modo de pantalla completa para el control de errores
- Modo de quiosco más seguro mediante la eliminación de las aplicaciones disponibles en los errores de pantalla completa. 

Anteriormente, al encontrar errores en la aplicación del modo de pantalla completa, HoloLens solía mostrar todas las aplicaciones en el menú inicio. Ahora en Windows Holographic versión 20H2 en caso de errores, no se mostrará ninguna aplicación en el menú inicio como se indica a continuación: 

![Imagen del modo de pantalla completa ahora cuando se produce un error.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>Directivas de HoloLens
- Opciones de administración de dispositivos creadas específicamente para HoloLens para administrar el dispositivo. 

Se han creado nuevas directivas de realidad mixta para HoloLens 2 dispositivos en Windows Holographic versión 20H2. Entre las nuevas opciones controlables se incluyen: establecer el brillo, establecer el volumen, deshabilitar la grabación de audio en las capturas de realidad mixta, establecer cuándo se pueden recopilar diagnósticos y la caché de pertenencia a grupos de AAD.  

| Nueva directiva de HoloLens                                | Descripción                                                                               | Notas                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Permite deshabilitar los botones de brillo, por lo que presionarlo no cambia el brillo.       | 1 Sí, 0 No (valor predeterminado)                                                |
| MixedReality\VolumeButtonDisabled                  | Permite deshabilitar los botones de volumen para que al presionarlo no cambie el volumen.               | 1 Sí, 0 No (valor predeterminado)                                                |
| MixedReality\MicrophoneDisabled                    | Deshabilita el micrófono para que no sea posible grabar audio en HoloLens 2.                      | 1 Sí, 0 No (valor predeterminado)                                                |
| MixedReality\FallbackDiagnostics                   | Controla el comportamiento de cuando se pueden recopilar registros de diagnóstico.                               | 0 Deshabilitado, 1 Habilitado para propietarios de dispositivos, 2 Habilitado para todos (valor predeterminado) |
| MixedReality\HeadTrackingMode                      | Reservado para uso futuro.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Controla cuántos días se Azure AD caché de pertenencia a grupos para la pantalla completa que tiene como destino Azure AD grupos. | Vea a continuación.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Pertenencia a Azure AD grupo de almacenamiento en caché para quiosco sin conexión
- Quioscos sin conexión habilitados para usarse con grupos de AAD durante un máximo de 60 días.

Esta directiva controla durante cuántos días se puede usar Azure AD caché de pertenencia a grupos para las configuraciones de acceso asignado que tienen como destino Azure AD grupos de usuarios que han iniciado sesión. Una vez que este valor de directiva se establece en un valor mayor que 0, solo se usa la memoria caché; de lo contrario, no.  

Nombre: AADGroupMembershipCacheValidityInDays VALOR DE URI: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Mín. - 0 días  
Máximo: 60 días 

Pasos para usar esta directiva correctamente: 
1. Cree un perfil de configuración de dispositivo para pantalla completa Azure AD grupos y asígnelo a dispositivos HoloLens. 
1. Cree una configuración de dispositivo personalizada basada en uri de OMA que establece este valor de directiva en el número deseado de días (> 0) y asígnelo a dispositivos HoloLens. 
    1. El valor uri debe especificarse en el cuadro de texto OMA-URI como ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. El valor puede estar entre mínimo y máximo permitido.
1. Inscriba dispositivos HoloLens y compruebe que ambas configuraciones se aplican al dispositivo. 
1. Permita Azure AD inicio de sesión del usuario 1 cuando Internet esté disponible, una vez que el usuario inicie sesión y Azure AD la pertenencia Azure AD un grupo se confirme correctamente, se creará la memoria caché. 
1. Ahora Azure AD usuario 1 puede desconectar HoloLens y usarlo para el modo de pantalla completa siempre que el valor de la directiva permita X número de días. 
1. Los pasos 4 y 5 se pueden repetir para cualquier otro usuario de Azure AD N. La clave aquí es que cualquier usuario de Azure AD debe iniciar sesión en el dispositivo mediante Internet, por lo que al menos una vez podemos determinar Azure AD que son miembros de un grupo al que está destinada la configuración de quiosco. 
 
> [!NOTE]
> Hasta que se realice el paso 4 para un Azure AD usuario experimentará un comportamiento de error mencionado en entornos "desconectados". 

### <a name="new-device-restriction-policies-for-hololens-2"></a>Nuevas directivas de restricción de dispositivos para HoloLens 2
- Permite a los usuarios administrar directivas de administración de dispositivos específicas, como bloquear la adición o eliminación de paquetes de aprovisionamiento.

Directivas recién habilitadas que permiten más opciones de administración de HoloLens 2 dispositivos. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Estas dos nuevas políticas para AllowAddProvisioningPackage y AllowRemoveProvisioningPackage se agregan a nuestras [restricciones comunes de dispositivos](hololens-common-device-restrictions.md).

> [!NOTE]
> Con respecto a [RemoteLock,](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)HoloLens solo admitirá la configuración ./Vendor/MSFT/RemoteLock/Lock. No se admiten las configuraciones que se tratan con el PIN, como el restablecimiento y la recuperación.

### <a name="new-power-policies-for-hololens-2"></a>Nuevas directivas de energía para HoloLens 2
- Más opciones para cuando HoloLens se bloquea o se bloquea a través de directivas de energía. 

Estas directivas recién agregadas permiten a los administradores controlar los estados de energía, como el tiempo de espera de inactividad. Para más información sobre cada directiva individual, haga clic en el vínculo de esa directiva.

|     Vínculo a la documentación de la directiva                |     Notas                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Valor de ejemplo que se usará en el Diseñador de configuración de Windows, es decir,  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Valor de ejemplo que se usará en el Diseñador de configuración de Windows, es decir,  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Valor de ejemplo que se usará en el Diseñador de configuración de Windows, es decir, 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Valor de ejemplo que se usará en el Diseñador de configuración de Windows, es decir, 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Valor de ejemplo que se usará en el Diseñador de configuración de Windows, es decir,   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Valor de ejemplo que se usará en el Diseñador de configuración de Windows, es decir,  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Estas dos nuevas políticas para DisplayOffTimeoutOnBattery y DisplayOffTimeoutPluggedIn se agregan a nuestras [restricciones comunes de dispositivos](hololens-common-device-restrictions.md).

> [!NOTE]
> Para obtener una experiencia coherente HoloLens 2, asegúrese de que los valores de DisplayOffTimeoutOnBattery y StandbyTimeoutOnBattery se establecen como el mismo valor. Lo mismo se aplica a DisplayOffTimeoutPluggedIn y StandbyTimeoutPluggedIn. Consulte [Visualización, suspensión e hibernación de](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) temporizadores inactivos para obtener más detalles sobre el modo de espera moderno.

### <a name="newly-enabled-update-policies-for-hololens"></a>Directivas de actualización recién habilitadas para HoloLens
- Más opciones para cuando se instalan las actualizaciones o deshabilita el botón Pausar actualizaciones para garantizar las actualizaciones.

Estas directivas de actualización ahora están habilitadas en HoloLens 2 dispositivos:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Puede leer los detalles completos sobre estas directivas de actualización y cómo usarlas para dispositivos HoloLens aquí en Manage HoloLens updates (Administrar [actualizaciones de HoloLens).](hololens-updates.md)

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Visibilidad de la página Configuración habilitada para HoloLens 2
- Mayor control de la interfaz de usuario en la aplicación configuración, que puede confundirse para mostrar una selección limitada de páginas.

Ahora hemos habilitado una directiva que permite a los administradores de TI impedir que páginas específicas de la aplicación Configuración del sistema sean visibles o accesibles, o bien hacerlo para todas las páginas excepto las especificadas. Para obtener información sobre cómo personalizar completamente esta característica, haga clic en el vínculo siguiente.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Para saber qué configuración de página puede personalizar en HoloLens 2, visite nuestra página [de URI de configuración](settings-uri-list.md). 
 
![Captura de pantalla de las horas activas que se modifican en la aplicación Configuración](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Modo de investigación
Mientras está en modo de investigación, el HoloLens 2 se convierte en una herramienta para la investigación de computer vision. En comparación con las ediciones anteriores, el modo de investigación HoloLens 2 tiene las siguientes ventajas:
-   Además de los sensores expuestos en el modo de investigación de HoloLens (1.ª generación), ahora proporcionamos acceso al sensor IMU, incluido un acelerómetro, un giroscopio y un magnetómetro.
-   HoloLens 2 proporciona nuevas funcionalidades que se pueden usar junto con el modo de investigación. En concreto, el acceso a api de seguimiento de manos y seguimiento de los ojos articuladas que pueden ofrecer un conjunto más completo de experimentos.

Los investigadores ahora tienen la opción de habilitar el modo de investigación en sus dispositivos HoloLens para acceder a todos estos flujos de sensores de imagen sin procesar orientados externamente. El modo de investigación HoloLens 2 también proporciona acceso a las lecturas de acelerómetro, giroscopio y magnetómetro. Para proteger la privacidad de los usuarios, las imágenes de cámara de seguimiento de los ojos sin procesar no están disponibles a través del modo de investigación, pero la dirección de la mirada con los ojos está disponible a través de las API existentes.

Consulte la documentación [del modo de investigación](https://docs.microsoft.com/windows/mixed-reality/research-mode) para obtener más detalles técnicos.

### <a name="recording-length-increased"></a>Se ha aumentado la longitud de la grabación
Debido a los comentarios de los clientes, hemos aumentado la longitud de grabación de las capturas [de realidad mixta.](holographic-photos-and-videos.md) Las capturas de realidad mixta ya no se limitarán a 5 minutos de forma predeterminada, sino que calcularán la longitud máxima de grabación en función del espacio disponible en disco. El dispositivo calculará la duración máxima de la grabación de vídeo en función del espacio en disco disponible hasta el 80 % del espacio total en disco.

> [!NOTE]
> HoloLens usará una duración de grabación de vídeo predeterminada (5 minutos) si se produce una de las siguientes situaciones:
> - La duración máxima estimada de la grabación es menor que los 5 minutos predeterminados.
> - El espacio en disco disponible es inferior al 20 % del espacio total en disco.

Puede encontrar todos los requisitos en nuestra [documentación de fotos y vídeos holográficos.](holographic-photos-and-videos.md#maximum-recording-length) 

### <a name="improvements-and-fixes-in-the-update"></a>Mejoras y correcciones en la actualización:
- Ahora hay más pantallas en modo oscuro.
- Más información debe apuntar a la declaración de privacidad más reciente en línea.
- Se ha corregido un problema por el que los usuarios no podían aprovisionar perfiles de VPN a través de paquetes de aprovisionamiento.
- Se ha corregido un problema de configuración de proxy para la conexión VPN.
- Se ha actualizado la directiva para deshabilitar la enumeración de funciones USB a través de MDM para NCM para AllowUsbConnection.
- Se ha corregido un problema que impedía que un dispositivo HoloLens se mostrara en Explorador de archivos a través del Protocolo de transferencia de medios (MTP) cuando el dispositivo se configuraba como un quiosco de una sola [aplicación.](hololens-kiosk.md) Tenga en cuenta que MTP (y la conexión USB en general) todavía se pueden deshabilitar mediante la [directiva AllowUSBConnection.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
- Se ha corregido un problema por el que los iconos del menú Inicio se escalaban correctamente en modo de pantalla completa.
- Se ha corregido un problema debido a que el almacenamiento en caché HTTP interfiere con el modo de pantalla completa destinado a Azure AD grupos.
- Se ha corregido un problema por el que los usuarios no podían usar el botón Emparejar después de habilitar el modo de desarrollador con paquetes de aprovisionamiento a menos que se deshabilitara y se habilitara de nuevo el modo de desarrollador.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, versión 1903: actualización de noviembre de 2020
- Compilación 18362.1085

Esta actualización de calidad mensual no contiene ningún cambio importante; le recomendamos que pruebe la última compilación de la versión de características de Windows Holographic, versión 20H2.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic, versión 2004- Actualización de octubre de 2020
- Compilación 19041.1124
 
Mejoras y correcciones en la actualización:

- Se ha quitado una comprobación innecesaria que produjo un error del sistema en tiempo de ejecución.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic, versión 1903- Actualización de octubre de 2020
- Compilación 18362.1081

Esta actualización de calidad mensual no contiene ningún cambio importante; le recomendamos que pruebe nuestras compilaciones más recientes para Windows Holographic, versión 2004.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, versión 2004: actualización de septiembre de 2020
- Compilación 19041.1117

Mejoras y correcciones en la actualización:

- Soluciona un problema que impedía Visual Studio depurar una aplicación cuando SupportsMultipleInstances="true" está presente en appxmanifest.
- Esta versión incluye la corrección de detección de proxy NCSI para solucionar la detección de Internet con errores a través del proxy de red. NCSI puede usar el proxy de máquina y el proxy por perfil para la detección de conectividad a Internet. El proxy por usuario será compatible con NCSI en una versión futura.
- En la mayoría Windows Mixed Reality dispositivos, el vector de dirección hacia delante es paralelo al suelo cuando la cabeza del usuario está en una posición neutra mirando hacia delante. Sin embargo, las versiones anteriores de HoloLens 2 alineaban el vector para que fuera horizontal a los paneles de visualización, que se inclina hacia abajo unos grados en relación con la orientación ideal. Las versiones más recientes HoloLens 2 lo han corregido para garantizar la coherencia semántica entre los factores de forma.
- Se ha mejorado la solidez del seguimiento de las manos, lo que dará lugar a menos pérdidas de seguimiento en escenarios específicos.
- Esta versión contiene una corrección para mejorar la calidad de la marca de tiempo de audio que puede haber contribuido a problemas de captura de vídeo.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, versión 1903: actualización de septiembre de 2020
- Compilación 18362.1079

Mejoras y correcciones en la actualización:

- En la mayoría Windows Mixed Reality dispositivos, el vector de dirección hacia delante es paralelo al suelo cuando la cabeza del usuario está en una posición neutra mirando hacia delante. Sin embargo, las versiones anteriores de HoloLens 2 alineaban el vector para que fuera horizontal a los paneles de visualización, que se inclina hacia abajo unos grados en relación con la orientación ideal. Las versiones más recientes HoloLens 2 lo han corregido para garantizar la coherencia semántica entre los factores de forma.
- Se ha mejorado la solidez del seguimiento de las manos, lo que dará lugar a menos pérdidas de seguimiento en escenarios específicos.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, versión 2004- Actualización de agosto de 2020
- Compilación 19041.1113

Mejoras y correcciones en la actualización:

- La aplicación de configuración ya no seguirá al usuario en las experiencias de inscripción de Iris o calibración de seguimiento ocular.
- Se ha corregido un error por el que la aplicación de un paquete de aprovisionamiento durante la operación de OOBE que cambia el nombre del dispositivo y realiza otras acciones (como conectarse a una red) no podría realizar las demás acciones después del reinicio del dispositivo debido al cambio de nombre.
- Se ha modificado la combinación de colores de los flujos de configuración inicial del dispositivo para mejorar la calidad visual.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, versión 1903- Actualización de agosto de 2020
- Compilación 18362.1074

Esta actualización de calidad mensual no contiene ningún cambio importante, le recomendamos que pruebe nuestras compilaciones más recientes para Windows Holographic, versión 2004.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, versión 2004- Actualización de julio de 2020
- Compilación 19041.1109

Mejoras y correcciones en la actualización:

- Ahora, los desarrolladores pueden elegir entre habilitar o deshabilitar Portal de dispositivos requieren una conexión segura.
- Confiabilidad mejorada para los inicios de aplicaciones después de las actualizaciones del sistema operativo.
- Se ha cambiado el brillo predeterminado de la bandeja de entrada al 100 %.
- Se ha corregido un problema sobre el reenvío HTTPS para el Portal de dispositivos Windows en HoloLens 2.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, versión 1903: actualización de julio de 2020
- Compilación 18362.1071

Mejoras y correcciones en la actualización:

- Se ha corregido un problema que podía hacer que los hologramas desaparezcan en las aplicaciones de Unity al perder o recuperar el seguimiento.
- Se ha corregido un problema que provocaba que las aplicaciones exclusivas de HoloLens se bloqueara de nuevo en el shell mientras se usaba el emulador de HoloLens con aceleración de hardware en determinados dispositivos.
- Se ha corregido un problema relativo al reenvío HTTPS para el Portal de dispositivos Windows en HoloLens 2.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, versión 2004- Actualización de junio de 2020
- Compilación 19041.1106

Mejoras y correcciones en la actualización:

- Las grabadoras MRC personalizadas ahora tienen nuevos valores predeterminados para determinadas propiedades si no se especifican.
  - En el *efecto de vídeo de MRC:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (casco envolvente))
  - En el *efecto de audio de MRC:*
    - LoopbackGain (el valor actual de "Ganancia de audio de la aplicación" en la página Captura de realidad mixta en Portal de dispositivos Windows)
    - MicrophoneGain (el valor actual de "Ganancia de audio de micrófono" en la página Captura de realidad mixta en Portal de dispositivos Windows)
- Se ha corregido un error para mejorar la calidad del audio en escenarios de captura de realidad mixta. En concreto, esta corrección debe eliminar los problemas de audio en la grabación cuando se muestra **el** menú Inicio.
- Se ha mejorado la estabilidad del holograma en los vídeos grabados.
- Se ha resuelto un problema por el que la captura de realidad mixta no podía grabar vídeo después de que el dispositivo se dejara en estado de espera durante varios días.
- La API HolographicSpace.UserPresence está deshabilitada generalmente para las aplicaciones de Unity. Este comportamiento evita un problema que provocaba que algunas aplicaciones se pausase cuando se volteó el visor, incluso si la configuración "Ejecutar en segundo plano" estaba habilitada. La API ahora está habilitada para las versiones 2018.4.18 y posteriores de Unity y 2019.3.4 y versiones posteriores.
- Al acceder a Portal de dispositivos a través de una conexión Wi-Fi, un explorador web podría impedir el acceso a debido a un certificado no válido. El explorador podría notificar un error como "ERR_SSL_PROTOCOL_ERROR", incluso si el certificado de dispositivo era de confianza previamente. En este caso, no puede avanzar a Portal de dispositivos, ya que no hay ninguna opción para omitir las advertencias de seguridad. Esta actualización resolvió el problema. Si el certificado de dispositivo se descargó previamente y era de confianza en un equipo para quitar las advertencias de seguridad del explorador y se produce el error SSL, el nuevo certificado debe descargarse y ser de confianza para abordar las advertencias de seguridad del explorador.
- Se ha habilitado la capacidad de crear un paquete de aprovisionamiento en tiempo de ejecución que puede instalar una aplicación mediante paquetes MSIX.
- Se ha agregado una configuración en **Configuración**  >  **Hologramas** del sistema que permite a los usuarios quitar automáticamente todos los hologramas de Mixed Reality inicio cuando se  >   apaga el dispositivo.
- Se ha corregido un problema que provocaba que las aplicaciones de HoloLens que cambiaban su formato de píxel se representaran en negro en el emulador de HoloLens.
- Se ha corregido un error que provocaba un bloqueo durante el inicio de sesión de Iris.
- Se ha corregido un problema sobre las descargas repetidas de la tienda para las aplicaciones ya actuales.
- Se ha corregido un error para impedir que las aplicaciones inmersivas se Microsoft Edge varias veces.
- Se ha corregido un problema con los lanzamientos de la aplicación Fotos en los arranques iniciales después de actualizar desde la versión 1903.
- Rendimiento y confiabilidad mejorados.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, versión 1903- Actualización de junio de 2020
- Compilación 18362.1064

Mejoras y correcciones en la actualización:

- Las grabadoras MRC personalizadas tienen nuevos valores predeterminados para determinadas propiedades si no se especifican.
  - En el efecto *de vídeo de MRC:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (casco envolvente))
  - En el *efecto de audio de MRC*:
    - LoopbackGain (el valor actual de "Ganancia de audio de la aplicación" en la página Captura de realidad mixta en Portal de dispositivos Windows)
    - MicrophoneGain (el valor actual de "Ganancia de audio de micrófono" en la página Captura de realidad mixta en Portal de dispositivos Windows)
- La API HolographicSpace.UserPresence está deshabilitada generalmente para las aplicaciones de Unity. Este comportamiento evita un problema que hace que algunas aplicaciones se detengan cuando se voltear el visor, incluso si la configuración para ejecutarse en segundo plano está habilitada. La API ahora está habilitada para las versiones 2018.4.18 y posteriores de Unity, y 2019.3.4 y versiones posteriores.
- Se ha corregido un problema que provocaba que las aplicaciones de HoloLens que cambiaban su formato de píxel se representaran en negro en el emulador de HoloLens.
- Se ha corregido un problema sobre los inicios de la aplicación Photos en los arranques iniciales después de actualizar desde la versión 1903.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, versión 2004  
- Compilación: 19041.1103

La actualización de software principal de mayo de 2020 para HoloLens 2, *Windows Holographic, versión 2004* incluye una gran cantidad de nuevas funcionalidades interesantes, como la compatibilidad con Windows Autopilot, el modo oscuro de la aplicación, la compatibilidad con Usb Ethernet para zonas activas 5G/HOTSPOT DE 5G/HOTSPOT, etc. Para actualizar a la versión más reciente, abra la aplicación Configuración, vaya a Actualizar & Security y seleccione el   botón **Buscar** ****   actualizaciones. 

|             Característica                              |          Descripción                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Configuración previa y sin problemas de nuevos dispositivos para producción mediante Windows AutoPilot                 |
|       Compatibilidad con FIDO 2                             |          Compatibilidad con claves de seguridad FIDO2 para habilitar la autenticación rápida y segura para dispositivos compartidos            |
|       Aprovisionamiento mejorado                      |          Aplicar sin problemas un paquete de aprovisionamiento desde una unidad USB a HoloLens                              |
|       Estado de instalación de la aplicación                 |          Compruebe el estado de instalación en la aplicación Configuración para las aplicaciones que se han HoloLens 2 a través de MDM.               |
|       Proveedores de servicios de configuración (CSP)   |          Se han agregado nuevos proveedores de servicios de configuración para mejorar las funcionalidades de control de administración.                 |
|       Compatibilidad con USB 5G/USB/USB                       |          La funcionalidad Ethernet USB ampliada permite la compatibilidad con 5G/USB                                    |
|       Modo de aplicación oscura                              |          Modo de aplicación oscura disponible para aplicaciones que admiten los modos oscuro y claro, lo que mejora la experiencia de visualización        |
|       Comandos de voz                             |          Compatibilidad con comandos de voz del sistema adicionales para controlar holoLens con manos libres                           |
|       Mejoras en el seguimiento de manos                 |          Las mejoras en el seguimiento de las manos hacen que los botones y las interacciones de pizarra 2D sea más precisa                        |
|       Mejoras y correcciones de calidad                 |          Diversas mejoras de rendimiento y confiabilidad del sistema en toda la plataforma                            |

### <a name="support-for-windows-autopilot"></a>Compatibilidad con Windows Autopilot

Windows Autopilot para HoloLens 2 permite que el canal de ventas de dispositivos inscriba previamente HoloLens en el inquilino de Intune. Cuando llegan los dispositivos, están listos para implementarse automáticamente como dispositivos compartidos en el inquilino. Para aprovechar las ventajas de la implementación propia, el dispositivo debe conectarse a una red durante la primera pantalla de la configuración mediante un USB de C a Ethernet.

Una vez que un usuario inicia el proceso de implementación automática de Autopilot, el proceso completa los pasos siguientes:

1. Una el dispositivo para Azure Active Directory (Azure AD).
1. Use Azure AD para inscribir el dispositivo en Microsoft Intune (u otro servicio MDM).
1. Descargue las directivas, los certificados y los perfiles de red dirigidos al dispositivo.
1. Aprovisione el dispositivo.
1. Presente la pantalla de inicio de sesión al usuario.

Obtenga más información en la [guía Windows Autopilot para HoloLens 2 evaluación de datos](https://docs.microsoft.com/hololens/hololens2-autopilot).

*Póngase en contacto con el administrador de cuentas para unirse ahora a la versión preliminar de AutoPilot. Los dispositivos listos para Autopilot comenzarán a enviarse pronto.*

### <a name="fido2-security-key-support"></a>Compatibilidad con la clave de seguridad FIDO2

Algunos usuarios comparten un dispositivo HoloLens con otros en un entorno laboral o educativo. Por lo tanto, es importante que los usuarios puedan fácilmente sin escribir nombres de usuario y contraseñas largos. Fast Identity Online (FIDO) permite que cualquier persona de su organización (inquilino de Azure AD) inicie sesión sin problemas en HoloLens sin escribir un nombre de usuario ni una contraseña.

Las claves de seguridad FIDO2 son un método de autenticación sin contraseña basado en estándares que puede estar en cualquier factor de forma. FIDO es un estándar abierto para la autenticación sin contraseña. Permite a los usuarios y organizaciones iniciar sesión en sus recursos sin un nombre de usuario ni una contraseña. En su lugar, usan una clave de seguridad externa o una clave de plataforma integrada en un dispositivo.

Para empezar, consulte Habilitación del inicio de sesión con clave [de seguridad sin contraseña.](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Inscripción de MDM mejorada a través del paquete de aprovisionamiento

Los paquetes de aprovisionamiento permiten establecer la configuración de HoloLens a través de un archivo de configuración en lugar de a través de la experiencia personalizada de HoloLens. Anteriormente, los paquetes de aprovisionamiento tenían que copiarse en la memoria interna de HoloLens. Ahora pueden estar en una unidad USB, por lo que son más fáciles de reutilizar en varios dispositivos HoloLens y puede aprovisionar dispositivos en paralelo. Los paquetes de aprovisionamiento ahora también admiten un campo para inscribirse en la administración de dispositivos, por lo que no hay ninguna configuración manual después del aprovisionamiento.

Para probarlo:

1. Descargue la versión más reciente del Diseñador de configuración de Windows desde la Tienda Windows en el equipo.
1. Seleccione **Aprovisionar dispositivos HoloLens**  >  **Aprovisionar HoloLens 2 dispositivos**.
2. Compile el perfil de configuración. A continuación, copie todos los archivos que se crearon en un dispositivo de almacenamiento USB-C.
3. Conecte el dispositivo USB-C a cualquier holoLens recién parpadeado. A continuación, **presione los**  +  **botones de encendido del volumen** para aplicar el paquete de aprovisionamiento.

### <a name="line-of-business-application-install-status"></a>Estado de instalación de la aplicación de línea de negocio

La implementación y administración de aplicaciones MDM para aplicaciones de línea de negocio es fundamental para HoloLens. Los administradores y usuarios deben ver el estado de instalación de la aplicación para la auditoría y el diagnóstico. En esta versión, hemos agregado más detalles en Configuración Cuentas Acceso a trabajo o escuela Haga  >    >    >  **clic en la información de su**  >  **cuenta**.

### <a name="additional-csps-and-policies"></a>Directivas y CSP adicionales

Un [proveedor de servicios de configuración (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) es una interfaz para leer, establecer, modificar o eliminar valores de configuración en un dispositivo. En esta versión, se agrega compatibilidad con más directivas para aumentar el control que los administradores tienen sobre los dispositivos HoloLens implementados. Para obtener la lista de CSP compatibles con HoloLens, consulte [CSP de NetworkQoSPolicy.](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)

Novedades en esta versión:

**Policy CSP** 

El proveedor de servicios de configuración de directivas permite a la empresa configurar directivas en dispositivos Windows. En esta versión, hemos agregado nuevas directivas para HoloLens, que se enumeran aquí. Para más información, consulte [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

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

**NetworkQoSPolicy CSP**

El proveedor de servicios de configuración NetworkQoSPolicy crea directivas de calidad de servicio (QoS) de red. Una directiva de QoS realiza un conjunto de acciones en el tráfico de red en función de un conjunto de condiciones de coincidencia. Para más información, consulte [Csp de NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Compatibilidad con Ethernet USB ampliada para dispositivos tethered 5G/NFC

Se agregó compatibilidad para habilitar determinados dispositivos de banda ancha móvil, como teléfonos 5G/NFC y zonas activas de Wi-Fi, cuando están conectados a la red HoloLens 2 a través de USB. Estos dispositivos se muestran ahora en la **configuración de red** como otra conexión Ethernet. (No se admiten los dispositivos de banda ancha móvil que requieren un controlador externo). Esta funcionalidad permite conexiones de alto ancho de banda cuando Wi-Fi no está disponible y Wi-Fi tethering no tiene el rendimiento suficiente. Para más información sobre los dispositivos USB compatibles, consulte [Conexión a dispositivos Bluetooth y USB-C.](https://docs.microsoft.com/hololens/hololens-connect-devices)  

### <a name="hand-tracking-improvements"></a>Mejoras en el seguimiento de manos

Esta versión incluye varias mejoras de seguimiento de manos:

- **Apuntando la estabilidad de la posición:** El sistema ahora se resistirá a inclinar el dedo índice cuando la mano lo ocluse. Este cambio mejora la precisión al insertar botones, escribir, desplazar contenido, etc. 
- **Pulsaciones de aire accidentales reducidas:** Se ha mejorado la detección del gesto de pulsar en el aire. Ahora hay menos activaciones accidentales en varios escenarios comunes, como al colocar las manos en los lados.
- **Confiabilidad del conmutador de usuario:** El sistema ahora es más rápido y confiable a la hora de actualizar el tamaño de la mano al compartir un dispositivo.
- **Se ha reducido el robo con las manos:** Hemos mejorado el control de los casos en los que hay más de dos manos a la vista de los sensores. Si varias personas trabajan juntas, ahora hay una probabilidad mucho menor de que la mano con seguimiento "salte" del usuario a la mano de otra persona de la escena.
- **Confiabilidad del sistema:** Se ha corregido un problema que provocaba que el seguimiento manual dejara de funcionar cuando el dispositivo está bajo una carga elevada.

### <a name="dark-mode"></a>Modo oscuro

Muchas aplicaciones de Windows ahora admiten los modos oscuro y claro. HoloLens 2 usuarios pueden elegir el modo predeterminado para las aplicaciones que admiten ambos. Después de la actualización, el modo de aplicación predeterminado es "oscuro", pero puede cambiar fácilmente esta configuración: Vaya a Configuración Colores del sistema Elija el   >    >    >  **modo de aplicación predeterminado**. 

Estas aplicaciones "en cuadro" admiten el modo oscuro: 

- Configuración 
- Microsoft Store 
- Correo 
- Calendario 
- Explorador de archivos 
- Centro de opiniones 
- OneDrive 
- Fotos 
- Visor 3D 
- Películas y TV 

![Ventanas en mosaico en modo oscuro](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Comandos de voz del sistema

Ahora puede usar comandos de voz con cualquier aplicación del dispositivo. Para más información, consulte [Uso de la voz para usar HoloLens.](https://docs.microsoft.com/hololens/hololens-cortana) Consulte también [Idiomas admitidos para HoloLens 2](https://docs.microsoft.com/hololens/hololens2-language-support).  

### <a name="cortana-updates"></a>Actualizaciones de Cortana

La aplicación actualizada se integra con Microsoft 365 para ayudarle a realizar más cosas en los dispositivos (actualmente US-English solo). En HoloLens 2, Cortana ya no admite determinados comandos específicos del dispositivo, como ajustar el volumen o reiniciar. Estas opciones ahora son compatibles con los nuevos comandos de voz del sistema. Obtenga más información sobre la nueva aplicación Cortana en nuestro [blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### <a name="quality-improvements-and-fixes"></a>Mejoras y correcciones de calidad

Mejoras y correcciones también en la actualización:  
- Se ha introducido un sistema de calibración de pantalla activo. Esta característica mejora la estabilidad y alineación de los hologramas. Ahora permanecen en su lugar cuando mueve la cabeza de lado a lado.
- Se ha corregido un error Wi-Fi streaming a HoloLens se interrumpía periódicamente. Si una aplicación indica que necesita streaming de baja latencia, implemente la corrección llamando a la [función SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Se ha corregido un error de dispositivo que se produjo durante el streaming en modo de investigación.
- Se ha corregido un error por el que, en algunos casos, el usuario adecuado no se mostraría en la pantalla de inicio de sesión al reanudar una sesión.
- Se ha corregido un problema por el que los usuarios no podían exportar registros de MDM a través **de Configuración.**
- Se ha corregido un problema por el que la precisión del seguimiento de los ojos inmediatamente después de la configuración rápida podría ser inferior a la esperada.
- Se ha corregido un problema por el que el subsistema de seguimiento de los ojos no se inicializaba o realizaba la calibración en determinadas condiciones.
- Se ha corregido un problema por el que se solicitaba la calibración de los ojos para un usuario ya calibrado.
- Se ha corregido un problema por el que un controlador se bloqueaba durante la calibración de los ojos.
- Se ha corregido un problema por el que las pulsaciones repetidas del botón de encendido podían provocar un tiempo de espera del sistema de 60 segundos y un bloqueo del shell.
- Estabilidad mejorada para búferes de profundidad.
- Se ha agregado un **botón Compartir** en el Centro de opiniones para que los usuarios puedan compartir comentarios más fácilmente.
- Se ha corregido un error por el que RoboRaid wan no se instalaba correctamente.

### <a name="known-issues"></a>Problemas conocidos

- Un problema con el lenguaje del sistema zh-CN impide que los comandos de voz capturen la realidad mixta o muestren la dirección IP del dispositivo.
- Un problema requiere que inicie la aplicación Cortana después de iniciar el dispositivo para usar la activación de voz "Hey Cortana". Si ha actualizado desde una compilación 18362, es posible que también vea un segundo icono de aplicación para la versión anterior de la aplicación Cortana que ya no funciona en **Iniciar**.

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, versión 1903: actualización de mayo de 2020 
- Compilación 18362.1061

Esta actualización de calidad mensual no contiene ningún cambio importante porque el equipo estaba trabajando en la actualización de mayo de Windows Holographic versión 2004, como se describió anteriormente.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, versión 1903: actualización de abril de 2020
- Compilación 18362.1059

**Modo oscuro para aplicaciones admitidas** 

Muchas aplicaciones de Windows admiten el modo oscuro y claro. HoloLens 2 clientes pueden elegir el modo predeterminado para las aplicaciones que admiten ambos esquemas de color. En función de los comentarios de los clientes, establecemos el modo de aplicación predeterminado en "oscuro", pero puede cambiar fácilmente esta configuración en cualquier momento: Vaya a Configuración **> System > Colors** para buscar **"Choose your default app mode"** (Elegir el modo de aplicación predeterminado).

Estas aplicaciones "en cuadro" admiten el modo oscuro:
- Configuración
- Microsoft Store
- Correo
- Calendario
- Explorador de archivos
- Centro de opiniones
- OneDrive
- Fotos
- Visor 3D
- Películas y TV

**Mejoras y correcciones también en la actualización:** 
- Se ha asegurado de que las superposiciones de shell se incluyen en las capturas de realidad mixta.
- Los desarrolladores de Unreal ahora pueden usar la página Vista 3D Portal de dispositivos probar y depurar sus aplicaciones.
- Se ha mejorado la estabilidad del holograma en la captura de realidad mixta cuando se usa el algoritmo *DepthReprojection de HolographicDepthReprojectionMethod.*
- Se ha corregido el error "WinRT IStreamSocketListener API Class not registered" (Clase de API IStreamSocketListener de WinRT no registrada) en aplicaciones arm de 32 bits.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic, versión 1903: actualización de marzo de 2020 
- Compilación 18362.1056

Mejoras y correcciones en la actualización:

- Se ha mejorado la estabilidad del holograma en la captura de realidad mixta cuando se usa el algoritmo *AutoPlanar HolographicDepthReprojectionMethod.*
- Se ha asegurado de que el sistema de coordenadas asociado a un ejemplo de MF de profundidad es coherente con la documentación pública.
- Se ha mejorado la productividad del desarrollador al permitir que los clientes peguen grandes cantidades de texto a través del portal de dispositivos.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic, versión 1903: actualización de febrero de 2020 
- Compilación 18362.1053

Mejoras y correcciones en la actualización:

- Deshabilitó temporalmente la API HolographicSpace.UserPresence para aplicaciones de Unity. Este cambio evita un problema que provocaba que algunas aplicaciones se pausase cuando se volteó el visor, incluso si la configuración "Ejecutar en segundo plano" estaba habilitada.
- Se ha corregido un bloqueo de HUP aleatorio causado por el seguimiento de las manos, en el que el usuario observó una inmovilización de la interfaz de usuario y, después de varios segundos, vuelve al shell.
- Se ha mejorado el seguimiento de las manos para que, cuando se desenreda con el dedo índice, la parte superior de ese dedo tenga menos probabilidades de rizarse inesperadamente.
- Confiabilidad mejorada del seguimiento de la cabeza, la asignación espacial y otros tiempos de ejecución.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, versión 1903: actualización de enero de 2020 
- Compilación 18362.1043
 
Mejoras y correcciones en la actualización:

- Se ha mejorado la estabilidad de las aplicaciones exclusivas al trabajar con HoloLens 2 emulador.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, versión 1903: actualización de diciembre de 2019 
- Compilación 18362.1042

Mejoras y correcciones en la actualización:

- Se han introducido correcciones de reproducción de la última fase (LSR). Se ha mejorado la representación visual de los hologramas para que parezcan más estables y nítidos al tener en cuenta con más precisión su profundidad. Este síntoma será más evidente después de esta actualización si las aplicaciones no establecen correctamente la profundidad de los hologramas.
- Se ha corregido la estabilidad de las aplicaciones exclusivas y la navegación entre aplicaciones exclusivas.
- Se ha resuelto un problema por el que la captura de realidad mixta no podía grabar vídeo después de que el dispositivo estaba en estado de espera durante varios días.
- Estabilidad del holograma mejorada.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, versión 1903: actualización de noviembre de 2019 
- Compilación 18362.1039

Mejoras y correcciones en la actualización:

- Se ha corregido la **funcionalidad de Seleccionar** comandos de voz durante la configuración inicial para en-CA y en-AU.
- Calidad visual mejorada de los objetos colocados lejos en las versiones más recientes de Unity y Mixed Reality Toolkit (MRTK).
- Se han corregido problemas de direccionamiento con las aplicaciones holográficas que se atascaban en un estado de pausa durante el inicio hasta que menú Inicio se abre y, a continuación, se cierra.
- Correcciones y mejoras de conformidad del entorno de ejecución de OpenXR para HoloLens 2 y el emulador.
