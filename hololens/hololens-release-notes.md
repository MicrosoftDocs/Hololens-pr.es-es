---
title: Notas de la versión de HoloLens 2
description: Obtén información sobre las actualizaciones en cada nueva versión de HoloLens 2.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/12/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 7c93f567921a634e5a75c274304819ec9e81b933
ms.sourcegitcommit: e26aa9059a7d8e73914205e80a89ea9637926e74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "11269421"
---
# Notas de la versión de HoloLens 2

Para garantizar que tiene una experiencia productiva con sus dispositivos HoloLens, seguimos lanzando actualizaciones de características, errores y seguridad. En esta página, puede ver las novedades de HoloLens cada mes. Para obtener la última actualización de HoloLens 2, puede buscar actualizaciones y actualizar manualmente u obtener la actualización de Flash completo (FFU) para flashear el dispositivo a través de Advanced [Recovery Companion,](hololens-recovery.md#clean-reflash-the-device)descárquelo [aquí.](https://aka.ms/hololens2download) [](hololens-update-hololens.md#check-for-updates-and-manually-update) La descarga se mantiene actualizada y proporciona la compilación más reciente disponible en general.

Estamos encantados de empezar a usar nuevas características para los usuarios de Windows Insider de nuevo. We will be flighting to the Dev Channel for the latest updates. Seguiremos con nuestras notas [de HoloLens Insider](hololens-insider.md) a medida que agreguemos más características y actualizaciones a nuestras compilaciones de Windows Insider. Prepárate y listo para mezclar estas actualizaciones en tu realidad. 

>[!NOTE]
> Para leer las notas de la versión del emulador de HoloLens, [visite el archivo.](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)

## Windows Holographic, versión 20H2- Actualización de enero de 2021
- Compilación 19041.1134

Mejoras y correcciones en la actualización:

- Se mejoró el rendimiento durante el inicio, la reanudación y el cambio de usuario cuando hay muchos usuarios en el dispositivo.
- Se ha agregado compatibilidad con arm32 para [el modo de investigación.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)

## Windows Holographic, versión 1903- Actualización de enero de 2021
- Compilación 18362.1091

Esta actualización de calidad mensual no contiene ningún cambio notable, te animamos a probar nuestras compilaciones más recientes para Windows Holographic, versión 2004.

## Windows Holographic, versión 20H2– Actualización de diciembre de 2020
- Compilación 19041.1131

### Instalar aplicaciones en HoloLens 2 mediante el Instalador de aplicación

Estamos **agregando una nueva funcionalidad (Instalador** de aplicación) para permitirle instalar aplicaciones de forma más sencilla en sus dispositivos HoloLens 2. La característica estará en **modo predeterminado para dispositivos no administrados.** Para evitar interrupciones en las empresas, el instalador de aplicación no **estará disponible para dispositivos administrados** en este momento.  

Un dispositivo se considera "administrado" si **se** cumple alguna de las siguientes condiciones:
- MDM [inscrito](hololens-enroll-mdm.md)
- Configurado con el [paquete de aprovisionamiento](hololens-provisioning.md)
- Identidad [de usuario](hololens-identity.md) es Azure AD

Ahora puedes instalar aplicaciones sin tener que habilitar el modo de desarrollador o usar Device Portal.  Simplemente descarga (a través de USB o a través de Edge) la agrupación Appx en el dispositivo y navega a la agrupación Appx en el Explorador de archivos para que se te pida que arranques la instalación.  Como alternativa, [inicie una instalación desde una página web.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)  Al igual que las aplicaciones que instalas desde Microsoft Store o la instalación de instalación local [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) con la [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) funcionalidad de implementación de la aplicación LOB de MDM, las aplicaciones deben estar firmadas digitalmente con la Herramienta de firma y el certificado que se usa para firmar debe ser de confianza para el dispositivo HoloLens antes de que se pueda implementar la aplicación.

**Instrucciones de instalación de la aplicación.**

1.  Asegurarse de que el dispositivo no se considera administrado
1.  Asegúrate de que el dispositivo HoloLens 2 esté encendido y conectado a tu PC
1.  Asegúrese de que ha iniciado sesión en el dispositivo HoloLens 2
1.  En el equipo, ve a la aplicación personalizada y copia tuapp.appxbundle en tudevicename\Internal Storage\Downloads.   Cuando hayas terminado de copiar el archivo, puedes desconectar el dispositivo.
1.  En el dispositivo HoloLens 2, abre el menú Inicio, selecciona Todas las aplicaciones e inicia la aplicación Explorador de archivos.
1.  Vaya a la carpeta Descargas. Es posible que deba seleccionar primero este dispositivo en el panel izquierdo de la aplicación y, a continuación, ir a Descargas.
1.  Selecciona el archivo yourapp.appxbundle.
1.  Se iniciará el Instalador de aplicación. Selecciona el botón Instalar para instalar la aplicación.
La aplicación instalada se iniciará automáticamente al finalizar la instalación.

Puedes encontrar aplicaciones de ejemplo en [GitHub de muestras universales de Windows](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) para probar este flujo.

Lea sobre el proceso completo de [instalación de aplicaciones en HoloLens 2 con el Instalador de aplicación.](app-deploy-app-installer.md)  

![Instalación de ejemplos de MRTK a través del Instalador de aplicación](images/hololens-app-installer-picture.jpg)

### Mejoras y correcciones en la actualización:

- Ahora, el seguimiento de manos mantiene el seguimiento en muchos casos nuevos en los que se habría perdido la mano anteriormente.  En algunos de estos nuevos casos, solo la posición de la palma continúa actualizando en función de la mano real del usuario, mientras que el resto de las uniones se inferye en función de una posición anterior.  Este cambio ayuda a mejorar la coherencia del seguimiento en los movimientos, como las bofetadas, el lanzamiento, el lanzamiento y la cobertura.  También ayuda en los casos en los que la mano está cerca de una superficie o que mantienen un objeto.  Cuando se inferirán las [](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) uniones de mano, el valor de precisión por conjunto se establecerá en "Aproximado" en lugar de "Alto".
- Se ha corregido un problema por el que el restablecimiento del PIN para las cuentas de Azure AD mostraría un error "Se ha producido un error.
- Los usuarios deberían ver mucho menos bloqueos de OOBE posteriores al arranque al iniciar ET, Iris desde la aplicación de configuración, nuevo usuario o notificación del sistema.
- Los usuarios deben tener una zona horaria correcta que salga de la OOBE.

## Windows Holographic, versión 1903– Actualización de diciembre de 2020
- Compilación 18362.1088

Esta actualización de calidad mensual no contiene ningún cambio notable, te animamos a probar nuestra última actualización de Windows Holographic, versión 20H2 - Diciembre de 2020 y la nueva característica instalador de aplicación agregada en la compilación.


## Windows Holographic, versión 20H2
- Compilación 19041.1128

Windows Holographic, versión 20H2, ya está disponible y ofrece un excelente conjunto de nuevas características para los usuarios de HoloLens 2 y los profesionales de IT. Desde el posicionamiento automático del ojo, hasta el Administrador de certificados en Configuración, hasta la funcionalidad mejorada del modo de pantalla completa y las nuevas funcionalidades de configuración de Autopilot. Esta nueva actualización permite que los equipos de IT tomen un control más detallado de la configuración y administración de dispositivos HoloLens, y ofrece a los usuarios experiencias holográficas aún más fluidas. 

Esta versión más reciente es una actualización mensual a la versión 2004, pero esta vez se incluyen nuevas características. El número de compilación principal seguirá siendo el mismo y Windows Update indicará una versión mensual a la versión 2004 (compilación 19041). Puedes ver tu número de compilación en la pantalla Configuración > Acerca de para confirmar que estás en la última compilación disponible 19041.1128+. Para actualizar a la versión más reciente, abre la aplicación Configuración, ve a Actualizar & Seguridad y pulsa Buscar actualizaciones. Para obtener más información sobre cómo administrar las actualizaciones de HoloLens, visite [esta página.](https://docs.microsoft.com/hololens/hololens-updates)

### Novedades de Windows Holographic, versión 20H2  

| Característica                                              | Descripción                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Compatibilidad con posición ocular automática](hololens-release-notes.md#auto-eye-position-support) | Calcula activamente las posiciones oculares sin que los usuarios pasen por la calibración del seguimiento ocular.   |
| [Administrador de certificados](hololens-release-notes.md#certificate-manager)   | Permite que los nuevos métodos más sencillos instalen y quiten certificados de la aplicación Configuración.     |
| [Aprovisionamiento de inicio automático desde USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Los paquetes de aprovisionamiento en unidades USB solicitan automáticamente la página de aprovisionamiento en OOBE.                                                         |
| [Confirmar automáticamente los paquetes de aprovisionamiento en la OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Los paquetes de aprovisionamiento se aplican automáticamente durante la OOBE desde la página de aprovisionamiento.                                                         |
| [Aprovisionamiento automático sin usar la interfaz de usuario](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Cómo combinar el inicio automático de aprovisionamiento y la confirmación automática juntos. |
| [Uso de Autopilot con Wi-Fi conexión](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Usa Autopilot desde dispositivos Wi-Fi sin necesidad de adaptador Ethernet. |
| [Tenantlockdown CSP y Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Después de aplicar la inscripción de inquilinos y la directiva, el dispositivo solo se puede inscribir en ese inquilino cada vez que el dispositivo se restablezca o vuelva a parpadear. |
| [Acceso asignado global](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Nuevo método de configuración para el modo de pantalla completa de varias aplicaciones que aplica el quiosco en el nivel del sistema, lo que hace que sea aplicable a todos.                  |
| [Inicio automático de una aplicación en quiosco de varias aplicaciones](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Establece una aplicación para que se inicie automáticamente al iniciar sesión en un modo de pantalla completa de varias aplicaciones.                                                        |
| [Cambios en el comportamiento del modo de pantalla completa para controlar errores](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | El error en el modo de pantalla completa ahora tiene una reserva restrictiva.                                                                                                |
| [Directivas de HoloLens](hololens-release-notes.md#hololens-policies)                                    | Nuevas directivas para HoloLens.     |
| [Almacenar en caché la pertenencia a grupos de Azure AD para quiosco sin conexión](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | La nueva directiva permite a los usuarios usar la memoria caché de pertenencia a grupos para usar el modo de pantalla completa sin conexión durante un número establecido de días.                                        |
| [Nuevas directivas de restricción de dispositivos para HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Directivas de administración de dispositivos habilitadas recientemente para HoloLens 2.                                                                                |
| [Nuevas directivas de energía para HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Directivas recién admitidas para la configuración de tiempo de espera de energía.  |
| [Actualizar directivas](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Directivas recién habilitadas que permiten controlar las actualizaciones.           |
| [Visibilidad de página de configuración habilitada para HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Directiva para elegir qué páginas se ven en la aplicación Configuración.             |
| [Modo de investigación](hololens-release-notes.md#research-mode) | Usar el modo Investigación en HoloLens 2. |
| [Longitud de grabación aumentada](hololens-release-notes.md#recording-length-increased) | Las grabaciones de MRC ya no tienen límite de 5 minutos. |
| [Mejoras y correcciones en la actualización](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Correcciones adicionales en la actualización.   |

### Compatibilidad con posición ocular automática

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

Esta información se puede encontrar más adelante con [otra información de calibración.](hololens-calibration.md#auto-eye-position-support) 

### Administrador de certificados

- Herramientas mejoradas de auditoría, diagnóstico y validación para la seguridad y el cumplimiento de dispositivos a través del nuevo Administrador de certificados. Esta funcionalidad le permitirá implementar, solucionar problemas y validar los certificados a escala en entornos comerciales.

En Windows Holographic versión 20H2, estamos agregando un Administrador de certificados en la aplicación Configuración de HoloLens 2. Vaya a **Configuración > actualizar & seguridad > certificados.** Esta característica proporciona una forma sencilla y fácil de usar para ver, instalar y quitar certificados en el dispositivo. Con el nuevo Administrador de certificados, los administradores y usuarios ahora han mejorado las herramientas de auditoría, diagnóstico y validación para garantizar que los dispositivos sigan siendo seguros y compatibles. 

-   **Auditoría:** Capacidad para validar que un certificado se implementó correctamente o para confirmar que se quitó correctamente. 
-   **Diagnóstico:** Cuando surgen problemas, validar que existen los certificados adecuados en el dispositivo ahorra tiempo y ayuda a solucionar problemas. 
-   **Validación:** Comprobar que un certificado cumple el propósito previsto y es funcional, puede ahorrar mucho tiempo, especialmente en entornos comerciales antes de implementar certificados a mayor escala.

Para buscar rápidamente un certificado específico en la lista, hay opciones para ordenar por nombre, almacén o fecha de expiración. Los usuarios también pueden buscar directamente un certificado. Para ver propiedades de certificado individuales, seleccione el certificado y haga clic en **Información.** 

La instalación de certificados admite actualmente archivos .cer y .crt. Los propietarios de dispositivos pueden instalar certificados en el equipo local y en el usuario actual;  todos los demás usuarios solo pueden instalar en el usuario actual. Los usuarios solo pueden quitar certificados instalados directamente desde la interfaz de usuario de configuración. Si un certificado se ha instalado a través de otros medios, también debe quitarse mediante el mismo mecanismo.

#### Para instalar un certificado: 

1.  Conecta HoloLens 2 a un equipo.
1.  Coloque el archivo de certificado que desea instalar en una ubicación de HoloLens 2.
1.  Vaya a **Configuración de la aplicación > actualizar & seguridad > certificados**y seleccione Instalar un certificado.
1.  Haga **clic en Importar** archivo y vaya a la ubicación donde guardó el certificado.
1.  Seleccione **Ubicación de la tienda.**
1.  Seleccione **Almacén de certificados.**
1.  Haz clic en **Instalar**.

El certificado ahora debe instalarse en el dispositivo.

#### Para quitar un certificado: 
1. Vaya a **Configuración de la aplicación > actualización y seguridad > certificados.**
1. Busque el certificado por su nombre en el cuadro de búsqueda.
1. Seleccione el certificado.
1. Haga clic **en Quitar**
1. Seleccione **Sí** cuando se le pida confirmación.

![Visor de certificados en la aplicación Configuración](images/certificate-viewer-device.jpg)

![Imagen que muestra cómo usar la interfaz de usuario de certificado para instalar un certificado](images/certificate-device-install.jpg)

Esta información se puede encontrar más adelante [en una nueva página del Administrador de certificados.](certificate-manager.md)

### Aprovisionamiento de inicio automático desde USB

- Procesos automatizados que permiten una menor interacción del usuario, cuando se usan unidades USB con paquetes de aprovisionamiento durante la OOBE.

Antes de esta versión, los usuarios tenían que iniciar la pantalla de aprovisionamiento manualmente durante la OOBE para aprovisionar mediante una combinación de botones. Ahora los usuarios pueden omitir la combinación de botones mediante un paquete de aprovisionamiento en una unidad de almacenamiento USB. 

1. Conectar la unidad USB con el paquete de aprovisionamiento durante el primer momento interactuable de la OOBE
1. Cuando el dispositivo esté listo para aprovisionarse, abrirá automáticamente el mensaje con la página de aprovisionamiento. 

Nota: Si una unidad USB se deja enchufada mientras el dispositivo se está arrancando, la OOBE enumerará el dispositivo de almacenamiento USB existente, así como observará si se están conectando otras adicionales.

Para obtener más información acerca de cómo aplicar paquetes de aprovisionamiento durante la OOBE, siga leyendo [aquí.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Esta información se puede encontrar más [adelante aquí.](hololens-provisioning.md#auto-launch-provisioning-from-usb)

### Confirmar automáticamente los paquetes de aprovisionamiento en la OOBE
- Proceso automatizado que permite una menor interacción del usuario, cuando se muestra la página Paquete de aprovisionamiento, se aplicarán automáticamente todos los paquetes enumerados.

Cuando aparece la pantalla principal de aprovisionamiento, la OOBE contará 10 segundos antes de empezar automáticamente a aplicar todos los paquetes de aprovisionamiento. Los usuarios aún pueden confirmar o cancelar en estos 10 segundos después de comprobar los paquetes que esperaban.

Esta información se puede encontrar más [adelante aquí.](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)

### Aprovisionamiento automático sin usar la interfaz de usuario
- Procesos automáticos combinados para interacciones de dispositivo reducidas para el aprovisionamiento. 

Al combinar el inicio automático del aprovisionamiento desde dispositivos USB y la confirmación automática de paquetes de aprovisionamiento, un usuario puede aprovisionar dispositivos HoloLens 2 automáticamente sin usar la interfaz de usuario del dispositivo ni siquiera usar el dispositivo. Puedes seguir usando la misma unidad USB y el mismo paquete de aprovisionamiento para varios dispositivos. Esto es útil para implementar varios dispositivos a la vez en la misma área. 

1. [Crear un paquete de aprovisionamiento](hololens-provisioning.md) con el [Diseñador de configuraciones de Windows](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Copia el paquete en una unidad de almacenamiento USB.
1. [Flash your HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) to [19041.1361 or newer build](https://aka.ms/hololens2previewdownload). 
1. Cuando [Advanced Recovery Companion haya](https://www.microsoft.com/store/productId/9P74Z35SFRS8) completado el parpadeo del dispositivo, desconecte el cable USB-C. 
1. Conecta la unidad USB al dispositivo.
1. Cuando el dispositivo HoloLens 2 se inicia en la OOBE, detectará automáticamente el paquete de aprovisionamiento en la unidad USB e iniciará la página de aprovisionamiento.
1. Después de 10 segundos, el dispositivo aplicará automáticamente el paquete de aprovisionamiento. 

El dispositivo ya está configurado y mostrará la pantalla Aprovisionamiento correcto.

Esta información se puede encontrar más [adelante aquí.](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### Uso de Autopilot con Wi-Fi conexión
- Se ha quitado la necesidad de adaptadores USB-C a Ethernet para reducir las necesidades de hardware, ya que permite que Autopilot funcione en Wi-Fi dispositivos conectados.

Ahora, durante la OOBE, una vez que conectes HoloLens 2 con Wifi, OOBE buscará un perfil de Autopilot para el dispositivo. Si se encuentra una, se usará para completar el resto del flujo de unión e inscripción de AAD. En otras palabras, el uso de ethernet a USB-C o adaptador Wi-Fi a USB-C ya no es un requisito, pero siguen funcionando si se proporcionan al principio de la OOBE. Obtenga más información [sobre Autopilot para dispositivos HoloLens 2.](hololens2-autopilot.md)

### Tenantlockdown CSP y Autopilot
- Mantiene los dispositivos en el espacio empresarial de la organización bloqueándolos, incluso al reestablecer el dispositivo o formatearlo. Es más seguro porque no permite crear cuentas mediante aprovisionamiento. 

Los dispositivos HoloLens 2 ahora admiten tenantLockdown CSP a partir de [Windows Holographic versión 20H2](hololens-release-notes.md#windows-holographic-version-20h2). 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP permite que HoloLens 2 se vincule a la inscripción de MDM únicamente con el Autopilot. Una vez que el nodo RequireNetworkInOOBE de TenantLockdown CSP se active o desactive (configurado inicialmente) en HoloLens 2, permanecerá así el dispositivo aunque se vuelva a formatear, a actualizar el sistema operativo, etc. 

Una vez que el nodo RequireNetworkInOOBE de TenantLockdown CSP se active o desactive (configurado inicialmente) en HoloLens 2, la configuración rápida espera indefinidamente que el perfil de Autopilot se descargue y aplique correctamente, después de conectarse a la red. 

Una vez que el nodo RequireNetworkInOOBE de TenantLockdown de CSP se active o desactive en HoloLens 2, no se permitirán las siguientes operaciones en la configuración rápida: 
- Crear usuarios locales mediante aprovisionamiento en el tiempo de ejecución 
- Realizar una operación de replica de Azure AD mediante aprovisionamiento en el tiempo de ejecución 
- Seleccionar quién es el propietario del dispositivo en la experiencia de la configuración rápida 

#### ¿Cómo configurarlo con Intune? 
1. Crea un perfil de configuración de dispositivos OMA URI personalizado y activa el nodo RequireNetworkInOOBE como se hace a continuación.
El valor OMA-URI debe ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Configuración del bloqueo de inquilinos a través de OMA-URI](images/hololens-tenant-lockdown.png)

1. Crea un grupo y asigna el perfil de configuración del dispositivo a ese grupo de dispositivos. 

1. Haz que el dispositivo HoloLens 2 sea un miembro del grupo creado en el paso anterior y desencadena la sincronización.  

Comprueba en el portal de Intune que la configuración del dispositivo se ha aplicado correctamente. Una vez que la configuración del dispositivo se aplique correctamente en el dispositivo HoloLens 2, los efectos de TenantLockdown estarán activos.

#### ¿Cómo se anula el nodo RequireNetworkInOOBE de TenantLockdown en HoloLens 2 con Intune? 
1. Quita HoloLens 2 del grupo de dispositivos a los que asignó la configuración creada anteriormente. 

1. Crea un perfil de configuración de dispositivos basado en OMA URI personalizado y desconecte RequireNetworkInOOBE como se hace a continuación. El valor OMA-URI debe ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla de la configuración para desconectar RequireNetworkInOOBE a través de OMA URI en Intune](images/hololens-tenant-lockdown-false.png)

1. Crea un grupo y asigna el perfil de configuración del dispositivo a ese grupo de dispositivos. 

1. Haz que el dispositivo HoloLens 2 sea un miembro del grupo creado en el paso anterior y desencadena la sincronización.

Comprueba en el portal de Intune que la configuración del dispositivo se ha aplicado correctamente. Una vez que la configuración del dispositivo se aplique correctamente en el dispositivo HoloLens 2, los efectos de TenantLockdown estarán inactivos. 

#### ¿Qué sucedería durante la configuración rápida si el perfil de Autopilot no está asignado a un HoloLens después de haber activado TenantLockdown? 
La configuración rápida esperará indefinidamente a que se descargue el perfil de Autopilot y a que aparezca el siguiente cuadro de diálogo. Para eliminar los efectos de TenantLockdown, el dispositivo debe estar antes inscrito en el espacio empresarial original únicamente con el Autopilot y RequireNetworkInOOBE configurarse como desconectado tal y como se describe en el paso anterior antes de que se quiten las restricciones introducidas por TenantLockdown CSP. 

![Vista en el dispositivo cuando se aplica la directiva.](images/hololens-autopilot-lockdown.png)

Esta información se puede encontrar junto con el resto de Autopilot en [Tenantlockdown CSP y Autopilot.](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)

### Acceso asignado global: modo de pantalla completa
- Reducción de la administración de identidades para quiosco, habilitando un nuevo método de quiosco que aplica el modo de pantalla completa en el nivel del sistema.

Esta nueva característica permite a un administrador de TI configurar un dispositivo HoloLens 2 para el modo de pantalla completa de varias aplicaciones que se aplica a nivel del sistema, no tiene afinidad con ninguna identidad en el sistema y se aplica a todos los usuarios que inician sesión en el dispositivo. Lea esta nueva característica en detalle [aquí.](hololens-global-assigned-access-kiosk.md)

### Inicio automático de una aplicación en modo de pantalla completa de varias aplicaciones 
- Experiencia centrada con el inicio automático de la aplicación, aumentando aún más las selecciones de la interfaz de usuario y la aplicación elegidas para las experiencias del modo de pantalla completa.

Solo se aplica al modo de pantalla completa de varias aplicaciones y solo se puede designar una aplicación para el inicio automático mediante el atributo resaltado siguiente en la configuración de acceso asignado. 

La aplicación se inicia automáticamente cuando el usuario inicia sesión. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Cambios en el comportamiento del modo de pantalla completa para controlar errores
- Modo de pantalla completa más seguro al eliminar las aplicaciones disponibles en los errores del modo de pantalla completa. 

Anteriormente, al encontrar errores al aplicar el modo de pantalla completa, HoloLens se usaba para mostrar todas las aplicaciones en el menú Inicio. Ahora en Windows Holographic versión 20H2 en caso de errores, no se mostrará ninguna aplicación en el menú inicio como se muestra a continuación: 

![Imagen del aspecto que tiene ahora el modo de pantalla completa cuando se produce un error.](images/hololens-kiosk-failure-behavior.png )

### Directivas de HoloLens
- Opciones de administración de dispositivos específicamente para HoloLens creadas para administrar el dispositivo. 

Se han creado nuevas directivas de realidad mixta para dispositivos HoloLens 2 en Windows Holographic versión 20H2. Entre las nuevas opciones controlables se incluyen: configuración de brillo, configuración del volumen, deshabilitación de la grabación de audio en capturas de realidad mixta, configuración de cuándo se pueden recopilar diagnósticos y caché de pertenencia a grupos de AAD.  

| Nueva directiva de HoloLens                                | Descripción                                                                               | Notas                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Permite deshabilitar los botones de brillo para que presionarlo no cambie el brillo.       | 1 Sí, 0 No (valor predeterminado)                                                |
| MixedReality\VolumeButtonDisabled                  | Permite deshabilitar los botones de volumen para que presionarlo no cambie el volumen.               | 1 Sí, 0 No (valor predeterminado)                                                |
| Realidad mixta\MicrophoneDisabled                    | Deshabilita el micrófono para que no se pueda grabar audio en HoloLens 2.                      | 1 Sí, 0 No (valor predeterminado)                                                |
| Realidad mixta\FallbackDiagnostics                   | Controla el comportamiento de cuándo se pueden recopilar los registros de diagnóstico.                               | 0 Deshabilitado, 1 Habilitado para propietarios de dispositivos, 2 Habilitado para todos (predeterminado) |
| MixedReality\HeadTrackingMode                      | Reservado para uso futuro.                                                                  |                                                                      |
| Realidad mixta\AADGroupMembershipCacheValidityInDays | Controla cuántos días se usa la memoria caché de pertenencia a grupos de Azure AD para quiosco destinado a grupos de Azure AD. | Consulta a continuación.                                                           |

### Almacenar en caché la pertenencia a grupos de Azure AD para quiosco sin conexión
- Quioscos sin conexión habilitados para usarse con grupos de AAD durante un máximo de 60 días.

Esta directiva controla durante cuántos días se permite usar la memoria caché de pertenencia a grupos de Azure AD para las configuraciones de acceso asignado destinadas a grupos de Azure AD para usuarios que han iniciado sesión. Una vez que este valor de directiva se establece en un valor mayor que 0, solo se usa la memoria caché; de lo contrario, no se usa la memoria caché.  

Nombre: Valor uri AADGroupMembershipCacheValidityInDays: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Mínimo: 0 días  
Máximo: 60 días 

Pasos para usar esta directiva correctamente: 
1. Crea un perfil de configuración de dispositivo para quiosco de pantalla completa destinado a grupos de Azure AD y asígnelo a dispositivos HoloLens. 
1. Crea una configuración de dispositivo personalizada basada en OMA URI que establece este valor de directiva en el número de días deseado (> 0) y asígnelo a dispositivos HoloLens. 
    1. El valor uri debe especificarse en el cuadro de texto OMA-URI como ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. El valor puede estar entre mínimo/máximo permitido.
1. Inscribe dispositivos HoloLens y comprueba que ambas configuraciones se apliquen al dispositivo. 
1. Permitir que el usuario 1 de Azure AD inicie sesión cuando Internet esté disponible, una vez que el usuario inicie sesión y la pertenencia al grupo de Azure AD se confirme correctamente, se creará la memoria caché. 
1. Ahora, el usuario 1 de Azure AD puede desconectar HoloLens y usarlo para el modo de pantalla completa siempre que el valor de la directiva permita X número de días. 
1. Los pasos 4 y 5 se pueden repetir para cualquier otro usuario de Azure AD N. El punto clave aquí es que cualquier usuario de Azure AD debe iniciar sesión en el dispositivo con Internet, por lo que al menos una vez podemos determinar que son miembros del grupo de Azure AD al que está destinada la configuración de quiosco. 
 
> [!NOTE]
> Hasta que se realice el paso 4 para un usuario de Azure AD experimentará el comportamiento de error mencionado en entornos "desconectados". 

### Nuevas directivas de restricción de dispositivos para HoloLens 2
- Permite a los usuarios administrar directivas de administración de dispositivos específicas, como bloquear la adición o eliminación de paquetes de aprovisionamiento.

Directivas recién habilitadas que permiten más opciones de administración de dispositivos HoloLens 2. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Estas dos nuevas políticas para AllowAddProvisioningPackage y AllowRemoveProvisioningPackage se agregan a nuestras restricciones comunes [de dispositivos.](hololens-common-device-restrictions.md)

> [!NOTE]
> En lo que respecta [a RemoteLock,](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)HoloLens solo admitirá la configuración ./Vendor/MSFT/RemoteLock/Lock. No se admiten las configuraciones que se tratan con PIN, como restablecer y recuperar.

### Nuevas directivas de energía para HoloLens 2
- Más opciones para cuando HoloLens se bloquea o se bloquea a través de directivas de energía. 

Estas directivas recién agregadas permiten a los administradores controlar los estados de energía, como el tiempo de espera inactivo. Para obtener más información sobre cada directiva individual, haga clic en el vínculo de esa directiva.

|     Vínculo de documentación de directivas                |     Notas                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Valor de ejemplo para usar en el Diseñador de configuraciones de Windows, es decir,  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Valor de ejemplo para usar en el Diseñador de configuraciones de Windows, es decir,  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Valor de ejemplo para usar en el Diseñador de configuraciones de Windows, es decir, 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Valor de ejemplo para usar en el Diseñador de configuraciones de Windows, es decir, 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Valor de ejemplo para usar en el Diseñador de configuraciones de Windows, es decir,   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Valor de ejemplo para usar en el Diseñador de configuraciones de Windows, es decir,  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Estas dos nuevas políticas para DisplayOffTimeoutOnBattery y DisplayOffTimeoutPluggedIn se están agregando a nuestras restricciones de [dispositivo comunes.](hololens-common-device-restrictions.md)

> [!NOTE]
> Para una experiencia coherente en HoloLens 2, asegúrese de que los valores de DisplayOffTimeoutOnBattery y StandbyTimeoutOnBattery se establecen como el mismo valor. Lo mismo se aplica a DisplayOffTimeoutPluggedIn y StandbyTimeoutPluggedIn. Consulta [Mostrar, suspender e hibernar](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) temporizadores inactivos para obtener más información sobre el modo de espera moderno.

### Directivas de actualización recién habilitadas para HoloLens
- Más opciones para cuando se instalan actualizaciones o deshabilitar el botón Pausar actualizaciones para garantizar las actualizaciones.

Estas directivas de actualización ahora están habilitadas en dispositivos HoloLens 2:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Puedes leer los detalles completos sobre estas directivas de actualización y cómo usarlas para dispositivos HoloLens aquí en Administrar actualizaciones [de HoloLens.](hololens-updates.md)

### Visibilidad de página de configuración habilitada para HoloLens 2
- Mayor control de la interfaz de usuario en la aplicación Configuración, que puede confundirse para mostrar una selección limitada de páginas.

Ahora hemos habilitado una directiva que permite a los administradores de TI impedir que determinadas páginas de la aplicación Configuración del sistema sean visibles o accesibles, o bien hacerlo para todas las páginas excepto las especificadas. Para obtener información sobre cómo personalizar completamente esta característica, haga clic en el vínculo siguiente.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Para obtener información sobre la configuración de página que puede personalizar en HoloLens 2, visite nuestra página de [URI de configuración.](settings-uri-list.md) 
 
![Captura de pantalla de la modificación de las horas activas en la aplicación Configuración](images/hololens-page-visibility-list.jpg)

### Modo de investigación
Mientras se encuentra en modo de investigación, HoloLens 2 se convierte en una herramienta eficaz para la investigación de la visión del equipo. En comparación con las ediciones anteriores, el modo de investigación para HoloLens 2 tiene las siguientes ventajas:
-   Además de los sensores expuestos en el modo de investigación de HoloLens (1.ª generación), ahora proporcionamos acceso al sensor IMU, incluido un acelerómetro, un girómetro y un magnetómetro.
-   HoloLens 2 proporciona nuevas funcionalidades que se pueden usar junto con el modo de investigación. Específicamente, el acceso a API de seguimiento de manos y seguimiento ocular que pueden ofrecer un conjunto más completo de experimentos.

Ahora, los investigadores tienen la opción de habilitar el modo de investigación en sus dispositivos HoloLens para acceder a todas estas secuencias de sensores de imagen sin procesar orientados externamente. El modo de investigación para HoloLens 2 también proporciona acceso a las lecturas del acelerómetro, el girómetro y el magnetómetro. Para proteger la privacidad de los usuarios, las imágenes de cámara de seguimiento ocular sin procesar no están disponibles a través del modo de investigación, pero la dirección de la mirada está disponible a través de las API existentes.

Consulta la documentación [del modo de investigación](https://docs.microsoft.com/windows/mixed-reality/research-mode) para obtener más detalles técnicos.

### Longitud de grabación aumentada
Debido a los comentarios de los clientes, hemos aumentado la duración de grabación de las capturas [de realidad mixta.](holographic-photos-and-videos.md) Las capturas de realidad mixta ya no estarán limitadas a 5 minutos de forma predeterminada, sino que calcularán la longitud máxima de grabación en función del espacio disponible en disco. El dispositivo calculará la duración máxima de la grabación de vídeo en función del espacio disponible en disco hasta el 80 % del espacio total en disco.

> [!NOTE]
> HoloLens usará la duración de grabación de vídeo predeterminada (5 minutos) si se produce una de las siguientes situaciones:
> - La duración máxima estimada de grabación es menor que los 5 minutos predeterminados.
> - El espacio en disco disponible es inferior al 20 % del espacio total en disco.

Esta información se puede encontrar de nuevo [aquí.](holographic-photos-and-videos.md#maximum-recording-length) 

### Mejoras y correcciones en la actualización:
- Ahora hay más pantallas en OOBE en modo oscuro.
- Más información sobre el contenido debe apuntar a la declaración de privacidad más reciente en línea.
- Se ha corregido un problema por el que los usuarios no podían aprovisionar perfiles de VPN a través de paquetes de aprovisionamiento.
- Se ha corregido un problema de configuración de proxy para la conexión VPN.
- Directiva actualizada para deshabilitar la enumeración de funciones USB a través de MDM para NCM para AllowUsbConnection.
- Se ha corregido un problema que impedía que un dispositivo HoloLens se mostrara en el Explorador de archivos a través del Protocolo de transferencia de medios (MTP) cuando el dispositivo se configuraba como un quiosco de una sola [aplicación.](hololens-kiosk.md) Ten en cuenta que MTP (y la conexión USB en general) aún se pueden deshabilitar mediante la [directiva AllowUSBConnection.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
- Se ha corregido un problema por el que los iconos del menú Inicio se escalaban correctamente en el modo de pantalla completa.
- Se ha corregido un problema debido a que el almacenamiento en caché HTTP interfiera con el modo de pantalla completa destinado a grupos de Azure AD.
- Se ha corregido un problema por el que los usuarios no podían usar el botón Emparejar después de habilitar el modo de desarrollador con paquetes de aprovisionamiento a menos que deshabilitara y vuelva a habilitar el modo de desarrollador.

## Windows Holographic, versión 1903- Actualización de noviembre de 2020
- Compilación 18362.1085

Esta actualización de calidad mensual no contiene ningún cambio notable, te animamos a probar la última compilación de la versión de características de Windows Holographic, versión 20H2.

## Windows Holographic, versión 2004- Actualización de octubre de 2020
- Compilación 19041.1124
 
Mejoras y correcciones en la actualización:

- Se quitó una comprobación innecesaria que causó un error en el sistema en tiempo de ejecución.

## Windows Holographic, versión 1903- Actualización de octubre de 2020
- Compilación 18362.1081

Esta actualización de calidad mensual no contiene ningún cambio notable, te animamos a probar nuestras compilaciones más recientes para Windows Holographic, versión 2004.

## Windows Holographic, versión 2004- Actualización de septiembre de 2020
- Compilación 19041.1117

Mejoras y correcciones en la actualización:

- Se ha corregido un problema que impedía Visual Studio depurar una aplicación cuando SupportsMultipleInstances="true" está presente en el appxmanifest.
- Esta versión incluye la corrección de detección de proxy NCSI para solucionar errores de detección de Internet a través de proxy de red. NCSI puede usar proxy de máquina y proxy por perfil para la detección de conectividad a Internet. El proxy por usuario será compatible con NCSI en futuras versiones.
- En la mayoría de los dispositivos de Windows Mixed Reality, el vector de dirección hacia delante es paralelo al suelo cuando la cabeza del usuario está en una posición neutral mirando hacia delante. Sin embargo, las versiones anteriores de HoloLens 2 alineaban el vector para que fuera perpendicular a los paneles de pantalla, que se inclina hacia abajo unos grados con respecto a la orientación ideal. Las versiones más recientes de HoloLens 2 lo han corregido para garantizar la coherencia semántica en todos los factores de forma.
- Robustez mejorada del seguimiento de manos que dará como resultado menos pérdidas de seguimiento en escenarios específicos.
- Esta versión contiene una corrección para mejorar la calidad de la marca de tiempo de audio que puede haber contribuido a problemas de captura de vídeo.

## Windows Holographic, versión 1903- Actualización de septiembre de 2020
- Compilación 18362.1079

Mejoras y correcciones en la actualización:

- En la mayoría de los dispositivos de Windows Mixed Reality, el vector de dirección hacia delante es paralelo al suelo cuando la cabeza del usuario está en una posición neutral mirando hacia delante. Sin embargo, las versiones anteriores de HoloLens 2 alineaban el vector para que fuera perpendicular a los paneles de pantalla, que se inclina hacia abajo unos grados con respecto a la orientación ideal. Las versiones más recientes de HoloLens 2 lo han corregido para garantizar la coherencia semántica en todos los factores de forma.
- Robustez mejorada del seguimiento de manos que dará como resultado menos pérdidas de seguimiento en escenarios específicos.

## Windows Holographic, versión 2004- Actualización de agosto de 2020
- Compilación 19041.1113

Mejoras y correcciones en la actualización:

- La aplicación de configuración ya no seguirá al usuario en las experiencias de inscripción de iris o calibración de seguimiento de ojos.
- Se ha corregido un error por el que al aplicar un paquete de aprovisionamiento durante la OOBE que cambia el nombre del dispositivo y realiza otras acciones (como conectarse a una red) no se pueden realizar las demás acciones después del reinicio del dispositivo debido al cambio de nombre.
- Combinación de colores modificada de los flujos iniciales de configuración del dispositivo para mejorar la calidad visual.

## Windows Holographic, versión 1903- Actualización de agosto de 2020
- Compilación 18362.1074

Esta actualización de calidad mensual no contiene ningún cambio notable, te animamos a probar nuestras compilaciones más recientes para Windows Holographic, versión 2004.

## Windows Holographic, versión 2004- Actualización de julio de 2020
- Compilación 19041.1109

Mejoras y correcciones en la actualización:

- Los desarrolladores ahora pueden elegir entre habilitar o deshabilitar que Device Portal requiera una conexión segura.
- Confiabilidad mejorada para los inicios de aplicaciones después de actualizaciones del sistema operativo.
- Se cambió el brillo predeterminado de la bandeja de entrada al 100 por ciento.
- Se ha corregido un problema sobre el reenvío HTTPS para Windows Device Portal en HoloLens 2.

## Windows Holographic, versión 1903- Actualización de julio de 2020
- Compilación 18362.1071

Mejoras y correcciones en la actualización:

- Se ha corregido un problema que podía hacer que los hologramas desaparezcan en las aplicaciones de Unity al perder o recuperar el seguimiento.
- Se ha corregido un problema que provocaba que las aplicaciones exclusivas de HoloLens se bloqueara de nuevo en el shell mientras se usaba el emulador de HoloLens con aceleración de hardware en determinados dispositivos.
- Se ha corregido un problema relativo al reenvío HTTPS para Windows Device Portal en HoloLens 2.

## Windows Holographic, versión 2004- Actualización de junio de 2020
- Compilación 19041.1106

Mejoras y correcciones en la actualización:

- Las grabadoras de MRC personalizadas ahora tienen nuevos valores predeterminados para determinadas propiedades si no se especifican.
  - En el efecto *de vídeo de MRC:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (cascos envolventes))
  - En el *efecto de audio de MRC:*
    - LoopbackGain (el valor actual "Ganancia de audio de la aplicación" en la página Captura de realidad mixta en Windows Device Portal)
    - MicrophoneGain (el valor actual "Ganancia de audio de micrófono" en la página Captura de realidad mixta en Windows Device Portal)
- Se ha corregido un error para mejorar la calidad de audio en escenarios de captura de realidad mixta. En concreto, esta corrección debe eliminar los problemas de audio en la grabación cuando **se** muestra el menú Inicio.
- Se mejoró la estabilidad del holograma en los vídeos grabados.
- Se ha resuelto un problema por el que la captura de realidad mixta no podía grabar vídeo después de que el dispositivo se dejara en estado de espera durante varios días.
- Por lo general, la API HolographicSpace.UserPresence está deshabilitada para las aplicaciones de Unity. Este comportamiento evita un problema que provocaba que algunas aplicaciones se pausase cuando se volteó el visor, incluso si la configuración "ejecutar en segundo plano" estaba habilitada. La API ahora está habilitada para las versiones de Unity 2018.4.18 y posteriores y 2019.3.4 y posteriores.
- Cuando accedes a Device Portal a través de Wi-Fi conexión, es posible que un explorador web impida el acceso debido a un certificado no válido. El explorador puede notificar un error como "ERR_SSL_PROTOCOL_ERROR", incluso si el certificado del dispositivo era de confianza previa. En este caso, no puedes avanzar a Device Portal, ya que no hay ninguna opción para omitir las advertencias de seguridad. Esta actualización resolvió el problema. Si el certificado del dispositivo se descargó previamente y era de confianza en un equipo para quitar advertencias de seguridad del explorador, y se produce el error SSL, el nuevo certificado debe descargarse y ser de confianza para solucionar las advertencias de seguridad del explorador.
- Se habilitó la capacidad de crear un paquete de aprovisionamiento en tiempo de ejecución que puede instalar una aplicación mediante paquetes MSIX.
- Se agregó **** una configuración en hologramas del sistema de configuración que permite a los usuarios quitar automáticamente todos los hologramas de la casa de realidad mixta cuando el dispositivo  >  ****  >  **** se apaga.
- Se ha corregido un problema que provocaba que las aplicaciones de HoloLens que cambiaban su formato de píxel se representaran en negro en el emulador de HoloLens.
- Se ha corregido un error que causaba un bloqueo durante el inicio de sesión de Iris.
- Se ha corregido un problema sobre las descargas repetidas de la Tienda para las aplicaciones ya actuales.
- Se ha corregido un error para evitar que las aplicaciones inmersivas abran Microsoft Edge repetidamente.
- Se ha corregido un problema con los inicios de Fotos aplicación en los inicios iniciales después de actualizar desde la versión 1903.
- Rendimiento y confiabilidad mejorados.

## Windows Holographic, versión 1903- Actualización de junio de 2020
- Compilación 18362.1064

Mejoras y correcciones en la actualización:

- Las grabadoras de MRC personalizadas tienen nuevos valores predeterminados para determinadas propiedades si no se especifican.
  - En el efecto *de vídeo de MRC:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (cascos envolventes))
  - En el *efecto de audio de MRC:*
    - LoopbackGain (el valor actual "Ganancia de audio de la aplicación" en la página Captura de realidad mixta en Windows Device Portal)
    - MicrophoneGain (el valor actual "Ganancia de audio de micrófono" en la página Captura de realidad mixta en Windows Device Portal)
- Por lo general, la API HolographicSpace.UserPresence está deshabilitada para las aplicaciones de Unity. Este comportamiento evita un problema que hace que algunas aplicaciones se detengan cuando se volte el visor, incluso si la configuración para ejecutarse en segundo plano está habilitada. La API ahora está habilitada para las versiones 2018.4.18 y posteriores de Unity, y 2019.3.4 y versiones posteriores.
- Se ha corregido un problema que provocaba que las aplicaciones de HoloLens que cambiaban su formato de píxel se representaran en negro en el emulador de HoloLens.
- Se ha corregido un problema sobre los inicios de Fotos aplicación en los inicios iniciales después de actualizar desde la versión 1903.

## Windows Holographic, versión 2004  
- Compilación : 19041.1103

La actualización de software principal de mayo de 2020 para HoloLens 2, *Windows Holographic, versión 2004* incluye una gran cantidad de nuevas funcionalidades interesantes, como la compatibilidad con Windows Autopilot, el modo oscuro de la aplicación, la compatibilidad con Ethernet USB para zonas activas 5G/LTE y mucho más. Para actualizar a la versión **** más reciente, abre la aplicación Configuración, ve a Actualizar & Seguridad y selecciona el botón Buscar    **** ****   actualizaciones. 

|             Característica                              |          Descripción                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       WindowsAutopilot                          |          Configurar previamente y configurar sin problemas nuevos dispositivos para producción mediante Windows AutoPilot                 |
|       Compatibilidad con FIDO 2                             |          Compatibilidad con claves de seguridad FIDO2 para habilitar la autenticación rápida y segura para dispositivos compartidos            |
|       Aprovisionamiento mejorado                      |          Aplicar sin problemas un paquete de aprovisionamiento desde una unidad USB a holoLens                              |
|       Estado de instalación de la aplicación                 |          Comprobar el estado de instalación en la aplicación Configuración para que las aplicaciones se hayan instalado en HoloLens 2 a través de MDM               |
|       Proveedores de servicios de configuración (SSP)   |          Se agregaron nuevos proveedores de servicios de configuración para mejorar las capacidades de control de administración                 |
|       Compatibilidad con USB 5G/LTE                       |          La funcionalidad ethernet USB expandida permite la compatibilidad con 5G/LTE                                    |
|       Modo de aplicación oscuro                              |          Modo de aplicación oscuro disponible para aplicaciones que admiten los modos oscuro y claro, mejorando la experiencia de visualización        |
|       Comandos de voz                             |          Compatibilidad con comandos de voz del sistema adicionales para controlar holoLens sin manos                           |
|       Mejoras en el seguimiento de manos                 |          Las mejoras de seguimiento de manos hacen que los botones y las interacciones de la pizarra 2D sea más precisa                        |
|       Mejoras y correcciones de calidad                 |          Diversas mejoras de rendimiento y confiabilidad del sistema en toda la plataforma                            |

### Compatibilidad con Windows Autopilot

Windows Autopilot para HoloLens 2 permite que el canal de ventas del dispositivo inscriba previamente HoloLens en su espacio empresarial de Intune. Cuando los dispositivos llegan, están listos para implementarse automáticamente como dispositivos compartidos en el espacio empresarial. Para aprovechar la implementación propia, el dispositivo debe conectarse a una red durante la primera pantalla de la configuración mediante un USB-C-a-Ethernet.

Después de que un usuario inicia el proceso de implementación automática de Autopilot, el proceso completa los siguientes pasos:

1. Unir el dispositivo a Azure Active Directory (Azure AD).
1. Usar Azure AD para inscribir el dispositivo en Microsoft Intune (u otro servicio MDM).
1. Descargar las directivas de destino del dispositivo, los certificados y los perfiles de red.
1. Aprovisionar el dispositivo.
1. Mostrar la pantalla de inicio de sesión al usuario.

Obtenga más información en la [guía de evaluación de Windows Autopilot para HoloLens 2.](https://docs.microsoft.com/hololens/hololens2-autopilot)

*Ponte en contacto con el Administrador de cuentas para unirte a la vista previa de AutoPilot ahora. Los dispositivos listos para Autopilot empezarán a enviarse pronto.*

### Compatibilidad con la clave de seguridad FIDO2

Algunos usuarios comparten un dispositivo HoloLens con otros en un entorno de trabajo o escuela. Por lo tanto, es importante que los usuarios puedan fácilmente sin escribir nombres de usuario y contraseñas largos. Fast Identity Online (FIDO) permite a cualquier usuario de su organización (inquilino de Azure AD) iniciar sesión sin problemas en HoloLens sin escribir un nombre de usuario o contraseña.

Las claves de seguridad FIDO2 son un método de autenticación sin contraseñas basado en estándares "phishable" que puede encontrarse en cualquier factor de forma. FIDO es un estándar abierto para la autenticación sin contraseña. Permite a los usuarios y organizaciones iniciar sesión en sus recursos sin un nombre de usuario o contraseña. En su lugar, usan una clave de seguridad externa o una clave de plataforma integrada en un dispositivo.

Para empezar, consulte Habilitar el inicio de sesión [con clave de seguridad sin contraseña.](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### Inscripción de MDM mejorada a través del paquete de aprovisionamiento

Los paquetes de aprovisionamiento te permiten establecer la configuración de HoloLens a través de un archivo de configuración en lugar de a través de la experiencia de configuración predeterminada de HoloLens. Anteriormente, los paquetes de aprovisionamiento tenían que copiarse en la memoria interna de HoloLens. Ahora pueden estar en una unidad USB para que sean más fáciles de reutilizar en varios dispositivos HoloLens y puedes aprovisionar dispositivos en paralelo. Los paquetes de aprovisionamiento ahora también admiten un campo para inscribirse en la administración de dispositivos, por lo que no hay ninguna configuración manual después del aprovisionamiento.

Para probarlo:

1. Descarga la versión más reciente del Diseñador de configuraciones de Windows de la Tienda Windows en tu PC.
1. Seleccione **Aprovisionar dispositivos HoloLens**  >  **aprovisionar dispositivos HoloLens 2.**
2. Crear el perfil de configuración. A continuación, copia todos los archivos que se crearon en un dispositivo de almacenamiento USB-C.
3. Conecta el dispositivo USB-C a cualquier HoloLens parpadeado. A continuación, **presiona los botones de**encendido  +  **del** volumen para aplicar el paquete de aprovisionamiento.

### Estado de instalación de la aplicación de línea de negocio

La implementación y administración de aplicaciones MDM para aplicaciones de línea de negocio es fundamental para HoloLens. Los administradores y usuarios deben ver el estado de instalación de la aplicación para realizar auditorías y diagnósticos. En esta versión, hemos agregado **** más detalles en Configuración Cuentas de acceso a trabajo o  >  ****  >  **escuela**  >  **Haga clic en la información de su**  >  **cuenta.**

### Directivas y CSP adicionales

Un [proveedor de servicios de configuración (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) es una interfaz para leer, establecer, modificar o eliminar opciones de configuración en un dispositivo. En esta versión, agregamos compatibilidad para más directivas para aumentar el control que los administradores han implementado en los dispositivos HoloLens. Para obtener la lista de CSP compatibles con HoloLens, consulta [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

Novedad de esta versión:

**Policy CSP** 

El proveedor de servicios de configuración de directivas permite a la empresa configurar directivas en dispositivos Windows. En esta versión, hemos agregado nuevas directivas para HoloLens, que se enumeran aquí. Para obtener más información, vea [los CSP de directiva compatibles con HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

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

El proveedor de servicios de configuración NetworkQoSPolicy crea directivas de calidad de servicio (QoS) de red. Una directiva de QoS realiza un conjunto de acciones en el tráfico de red en función de un conjunto de condiciones coincidentes. Para obtener más información, consulta [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

### Compatibilidad con Ethernet USB expandida para dispositivos tethered 5G/LTE

Se agregó compatibilidad para habilitar determinados dispositivos de banda ancha móvil, como teléfonos 5G/LTE y Wi-Fi hotpots, cuando están conectados a HoloLens 2 a través de USB. Estos dispositivos ahora se muestran en la configuración **de red** como otra conexión Ethernet. (No se admiten los dispositivos de banda ancha móvil que requieren un controlador externo). Esta funcionalidad permite conexiones de ancho de banda alto Wi-Fi no está disponible y Wi-Fi el tethering no es lo suficientemente bueno. Para obtener más información sobre los dispositivos USB compatibles, consulta Conectarse a [dispositivos Bluetooth y USB-C.](https://docs.microsoft.com/hololens/hololens-connect-devices)  

### Mejoras en el seguimiento de manos

Esta versión incluye varias mejoras de seguimiento de manos:

- **Estabilidad de la posición señalada:** El sistema ahora se resiste a inclinar el dedo índice cuando la palma lo oculta. Este cambio mejora la precisión al presionar botones, escribir, desplazar contenido y mucho más. 
- **Pulsaciones de aire accidentales reducidas:** Hemos mejorado la detección del gesto de pulsar en el aire. Ahora hay menos activaciones accidentales en varios escenarios comunes, como cuando se sueltan las manos a los lados.
- **Confiabilidad del conmutador de usuario:** El sistema ahora es más rápido y confiable al actualizar el tamaño de la mano al compartir un dispositivo.
- **Robo de mano reducido:** Hemos mejorado el control de los casos en los que hay más de dos manos a la vista de los sensores. Si varias personas trabajan juntas, ahora hay muchas menos posibilidades de que la mano con seguimiento "salte" del usuario a la mano de otra persona en la escena.
- **Confiabilidad del sistema:** Se ha corregido un problema que provocaba que el seguimiento de manos dejara de funcionar cuando el dispositivo estaba bajo una carga alta.

### Modo oscuro

Muchas aplicaciones de Windows ahora admiten los modos oscuro y claro. Los usuarios de HoloLens 2 pueden elegir el modo predeterminado para las aplicaciones que admiten ambas. Después de la actualización, el modo de aplicación predeterminado es "oscuro", pero puede cambiar fácilmente esta configuración: Vaya a Configuración de colores del sistema ****  >  ****  >  ****  >  **Elija el modo de aplicación predeterminado.** 

Estas aplicaciones "en el cuadro" admiten el modo oscuro: 

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

Ahora puedes usar comandos de voz con cualquier aplicación del dispositivo. Para obtener más información, [consulta Usar tu voz para usar HoloLens.](https://docs.microsoft.com/hololens/hololens-cortana) Consulta también [idiomas admitidos para HoloLens 2.](https://docs.microsoft.com/hololens/hololens2-language-support)  

### Actualizaciones de Cortana

La aplicación actualizada se integra con Microsoft 365 para ayudarle a realizar más cosas en sus dispositivos (actualmente solo US-English). En HoloLens 2, Cortana ya no admite ciertos comandos específicos del dispositivo, como ajustar el volumen o reiniciar. Ahora, estas opciones son compatibles con los nuevos comandos de voz del sistema. Obtenga más información sobre la nueva aplicación de Cortana en nuestro [blog.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)

### Mejoras y correcciones de calidad

Mejoras y correcciones también en la actualización:  
- Se introdujo un sistema de calibración de pantalla activo. Esta característica mejora la estabilidad y la alineación de los hologramas. Ahora permanecen en su lugar cuando mueves la cabeza de un lado a otro.
- Se ha corregido un error Wi-Fi streaming a HoloLens se interrumpió periódicamente. Si una aplicación indica que necesita streaming de baja latencia, implementa la corrección llamando a la función [SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Se ha corregido un error de dispositivo que se produjo durante la transmisión por secuencias en modo de investigación.
- Se ha corregido un error en el que, en algunos casos, el usuario correcto no se mostraría en la pantalla de inicio de sesión al reanudar una sesión.
- Se ha corregido un problema por el que los usuarios no podían exportar registros MDM a través de **Configuración.**
- Se ha corregido un problema por el que la precisión del seguimiento de ojos inmediatamente después de la configuración rápida podía ser inferior a la esperada.
- Se ha corregido un problema por el que el subsistema de seguimiento ocular no se inicializaba o realizaba la calibración en determinadas condiciones.
- Se ha corregido un problema por el que se solicitaba la calibración ocular para un usuario ya calibrado.
- Se ha corregido un problema por el que un controlador se bloqueaba durante la calibración ocular.
- Se ha corregido un problema por el que las pulsaciones repetidas del botón de encendido podían provocar un tiempo de espera del sistema de 60 segundos y un bloqueo del shell.
- Estabilidad mejorada para búferes de profundidad.
- Se agregó un **botón** Compartir en el Centro de opiniones para que los usuarios puedan compartir comentarios con mayor facilidad.
- Se ha corregido un error por el que RoboRaid wan no estaba instalado correctamente.

### Problemas conocidos

- Un problema con el lenguaje del sistema zh-CN impide que los comandos de voz capturen o muestren la dirección IP del dispositivo.
- Un problema requiere que inicies la aplicación Cortana después de iniciar el dispositivo para usar la activación de voz "Hola Cortana". Si actualizaste desde una compilación 18362, es posible que también veas un segundo icono de la aplicación para la versión anterior de la aplicación Cortana que ya no funciona en **Inicio.**

## Windows Holographic, versión 1903: actualización de mayo de 2020 
- Compilación 18362.1061

Esta actualización de calidad mensual no contiene ningún cambio notable porque el equipo estaba trabajando en windows Holographic version 2004 May Update, como se describió anteriormente.

## Windows Holographic, versión 1903- Actualización de abril de 2020
- Compilación 18362.1059

**Modo oscuro para aplicaciones compatibles** 

Muchas aplicaciones de Windows admiten el modo oscuro y claro. Los clientes de HoloLens 2 ahora pueden elegir el modo predeterminado para las aplicaciones que admiten ambas esquemas de colores. En función de los comentarios de los clientes, establecemos el modo de aplicación predeterminado en "oscuro", pero puedes cambiar fácilmente esta configuración en cualquier momento: ve a Configuración **> Colores** del sistema > para encontrar "Elegir el modo de aplicación **predeterminado".**

Estas aplicaciones "en el cuadro" admiten el modo oscuro:
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
- Se garantiza que las superposiciones de shell se incluyan en las capturas de realidad mixta.
- Los desarrolladores de Unreal ahora pueden usar la página Vista 3D en Device Portal para probar y depurar sus aplicaciones.
- Se mejoró la estabilidad del holograma en la captura de realidad mixta cuando se usa el algoritmo *DepthReprojection HolographicDepthReprojectionMethod.*
- Se ha corregido el error "Clase DE API IStreamSocketListener de WinRT no registrada" en aplicaciones de ARM bits.

## Windows Holographic, versión 1903- Actualización de marzo de 2020 
- Compilación 18362.1056

Mejoras y correcciones en la actualización:

- Se ha mejorado la estabilidad del holograma en la captura de realidad mixta cuando se usa el algoritmo *AutoPlanar HolographicDepthReprojectionMethod.*
- Se aseguró de que el sistema de coordenadas adjunto a una muestra de MF de profundidad sea coherente con la documentación pública.
- Mejora de la productividad de los desarrolladores al permitir a los clientes pegar grandes cantidades de texto a través del portal del dispositivo.

## Windows Holographic, versión 1903- Actualización de febrero de 2020 
- Compilación 18362.1053

Mejoras y correcciones en la actualización:

- Deshabilitada temporalmente la API HolographicSpace.UserPresence para aplicaciones unity. Este cambio evita un problema que provocaba que algunas aplicaciones se pausase cuando se volteó el visor, incluso si la configuración "ejecutar en segundo plano" estaba habilitada.
- Se ha corregido un bloqueo de HUP aleatorio causado por el seguimiento de manos, en el que el usuario observó que una interfaz de usuario se bloqueaba y, a continuación, regresaba al shell después de varios segundos.
- Se ha mejorado el seguimiento de las manos para que, al asomar con el dedo índice, es menos probable que la parte superior del dedo se desenlace inesperadamente.
- Se mejoró la confiabilidad del seguimiento de la cabeza, la asignación espacial y otros tiempos de ejecución.

## Windows Holographic, versión 1903- Actualización de enero de 2020 
- Compilación 18362.1043
 
Mejoras y correcciones en la actualización:

- Estabilidad mejorada para aplicaciones exclusivas al trabajar con el emulador holoLens 2.

## Windows Holographic, versión 1903- Actualización de diciembre de 2019 
- Compilación 18362.1042

Mejoras y correcciones en la actualización:

- Se introdujeron correcciones de reproducción de última etapa (LSR). Representación visual mejorada de hologramas para que parezca más estable y nítido al tener en cuenta con mayor precisión su profundidad. Este síntoma será más perceptible después de esta actualización si las aplicaciones no establecen la profundidad de los hologramas correctamente.
- Estabilidad fija de aplicaciones exclusivas y navegación entre aplicaciones exclusivas.
- Se ha resuelto un problema por el que la captura de realidad mixta no podía grabar vídeo después de que el dispositivo estaba en estado de espera durante varios días.
- Estabilidad de hologramas mejorada.

## Windows Holographic, versión 1903- Actualización de noviembre de 2019 
- Compilación 18362.1039

Mejoras y correcciones en la actualización:

- Funcionalidad fija de **seleccionar comandos** de voz durante la configuración inicial para en-CA y en-AU.
- Calidad visual mejorada de objetos colocados lejos en las versiones más recientes de Unity y Mixed Reality Toolkit (MRTK).
- Se han corregido problemas de direccionamiento con las aplicaciones holográficas que se atascaban en un estado pausado en el inicio hasta que se abre y se cierra el menú Inicio.
- Correcciones y mejoras de conformidad en tiempo de ejecución de OpenXR para HoloLens 2 y el emulador.
