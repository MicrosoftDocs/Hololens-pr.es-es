---
title: Problemas conocidos de HoloLens
description: Manténgase al día con nuestra lista de problemas conocidos y soluciones alternativas que pueden afectar a los clientes y desarrolladores de HoloLens que usan Unity y el Portal de dispositivos Windows.
keywords: solución de problemas, problema conocido, ayuda
author: mattzmsft
ms.author: mazeller
ms.date: 11/30/2020
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
- HoloLens 2
ms.openlocfilehash: 54bc090352983e814c64deea8f1f401c24e3261b
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310178"
---
# <a name="known-issues-for-hololens"></a>Problemas conocidos de HoloLens

Esta es la lista actual de problemas conocidos de los dispositivos HoloLens. Compruebe aquí primero si ve un comportamiento extraño. Esta lista se mantendrá actualizada a medida que se detectan o notifican nuevos problemas, o a medida que se solucionen problemas en futuras actualizaciones de software de HoloLens.

>[!NOTE]
> - Si detecta un problema que no está bloqueando, notimente en el dispositivo HoloLens a través [de Centro de opiniones](hololens-feedback.md).
> - Si el problema al que se enfrenta le está bloqueando, además de presentar comentarios, [envíe una solicitud de soporte técnico.](https://aka.ms/hlsupport)

- [Problemas conocidos de todas las generaciones de HoloLens](#known-issues-for-all-hololens-generations)
- [Problemas conocidos de HoloLens 2 dispositivos](#known-issues-for-hololens-2-devices)
- [Problemas conocidos de HoloLens (1.ª generación)](#known-issues-for-hololens-1st-gen)
- [Problemas conocidos del emulador de HoloLens](#known-issues-for-hololens-emulator)

## <a name="known-issues-for-all-hololens-generations"></a>Problemas conocidos de todas las generaciones de HoloLens

### <a name="unity"></a>Unity

- Consulte [Instalación de las herramientas](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) para obtener la versión más actualizada de Unity recomendada para el desarrollo de HoloLens.
- Los problemas conocidos de Unity HoloLens Technical Preview se documentan en los [foros de Unity de HoloLens.](https://forum.unity3d.com/threads/known-issues.394627/)

### <a name="windows-device-portal"></a>Portal de dispositivos Windows

- La característica Live Preview de Mixed Reality captura puede presentar varios segundos de latencia.

- En la página Entrada virtual, los controles Gesto y Desplazamiento de la sección Gestos virtuales no son funcionales. Su uso no tendrá ningún efecto. El teclado virtual de la misma página funciona correctamente.

- Después de habilitar el modo de desarrollador en Configuración, puede tardar unos segundos antes de que el conmutador active el Portal de dispositivos está habilitado.

### <a name="onedrive-camera-upload"></a>Carga de la cámara de OneDrive

La aplicación OneDrive para HoloLens no admite la carga automática de cámara para cuentas profesionales o educativas.

Soluciones alternativas:

- Si es viable para su empresa, la carga automática de la cámara se admite en las cuentas Microsoft del consumidor. Puede iniciar sesión en su cuenta Microsoft además de la cuenta profesional o educativa (la aplicación OneDrive admite el inicio de sesión dual). Desde el perfil de la cuenta De Microsoft en OneDrive, puede habilitar la carga automática de lanzamiento de cámara en segundo plano.

- Si no puede usar de forma segura una cuenta Microsoft de consumidor para cargar las fotos automáticamente, puede cargar manualmente las fotos en su cuenta de trabajo o educativa desde la aplicación OneDrive. Para ello, asegúrese de que ha iniciado sesión en su cuenta laboral o educativa en la aplicación OneDrive. Seleccione el **+** botón y elija **Cargar.** Para buscar las fotos o vídeos que desea cargar, vaya a **Imágenes > de cámara.** Seleccione las fotos o vídeos que desea cargar y, a continuación, seleccione el **botón** Abrir.

## <a name="known-issues-for-hololens-2-devices"></a>Problemas conocidos de HoloLens 2 dispositivos

### <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge no se puede iniciar

Algunos clientes han notificado un problema por el Microsoft Edge no se puede iniciar. Para estos clientes, el problema persiste durante el reinicio y no se resuelve con las actualizaciones de Windows o de la aplicación. Si experimenta este problema y ha confirmado que [Windows](hololens-updates.md#manually-check-for-updates)está actualizado, envíe un error desde la aplicación [de Centro de opiniones](hololens-feedback.md) con la siguiente categoría y subcategoría: Instalar y actualizar > Descarga, instalación y configuración de Windows Update.

No hay soluciones alternativas conocidas, ya que hasta ahora no hemos podido resolver la causa principal del problema. La presentación de un error mediante Centro de opiniones ayudará a nuestra investigación.

### <a name="keyboard-does-not-switch-to-special-characters"></a>El teclado no cambia a caracteres especiales

Hay un problema durante la OOBE, donde una vez que el usuario ha elegido una cuenta de trabajo o educativa y escribe su contraseña, intenta cambiar a los caracteres especiales del teclado pulsando el botón &123 no cambia a caracteres especiales. 

Entornos de trabajo:
-   Cierre el teclado y vuelva a abrirlo pulsando en el campo de texto.
-   Escriba incorrectamente la contraseña. Cuando el teclado se vuelva a iniciar la próxima vez, funcionará según lo previsto.
- Autenticación web, cierre el teclado y **seleccione Iniciar sesión desde otro dispositivo.** 
-   Si solo escribe números, un usuario puede presionar y mantener presionadas ciertas teclas para abrir un menú expandido.
-   Uso de un teclado USB.

Esto no afecta a:
- Usuarios que deciden usar una cuenta personal.

### <a name="blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build"></a>La pantalla azul se muestra después de la cancelación de la inscripción de las compilaciones de la versión preliminar de Insider en un dispositivo que se ha replanteado con una compilación de Insider.

Se trata de un problema que afecta a los usuarios que se encontraban en una compilación en versión preliminar de Insider, se ha reflashado su HoloLens 2 con una nueva compilación en versión preliminar de Insider y, a continuación, se ha des inscrito en el programa Insider. 

Esto no afecta a:
- Usuarios que no están inscritos en Windows Insider 
- Insiders:
    - Si un dispositivo se ha inscrito desde las compilaciones de Insider, era la versión 18362.x
    - Si se ha publicado una compilación 19041.x firmada por Insider y permanece inscrito en el programa Insider 

Trabajo: 
- Evitar el problema 
    - Flash en una compilación que no es de insider. Una de las actualizaciones mensuales normales. 
    - Permanecer en Insider Preview
- Reflash the device

    1. Coloque el [HoloLens 2 en modo de](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) parpadeo manualmente; para hacerlo, apague completamente sin conectarse. A continuación, mientras mantiene presionada la tecla Volumen, pulse el botón De encendido.
    
    1. Conéctese al equipo y abra Advanced Recovery Companion. 
    
    1. Flash el HoloLens 2 a la compilación predeterminada.   

## <a name="known-issues-for-hololens-1st-gen"></a>Problemas conocidos de HoloLens (1ª generación)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>No se puede conectar e implementar en HoloLens a través de Visual Studio

> [!NOTE]
> Última actualización: 8/8 @ 5:11 p. m.: Visual Studio ha publicado VS 2019 versión 16.2, que incluye una corrección para este problema. Se recomienda actualizar a esta versión más reciente para evitar experimentar este error.

Visual Studio versión 16.2 de VS 2019, que incluye una corrección para este problema. Se recomienda actualizar a esta versión más reciente para evitar experimentar este error.

Causa principal del problema: los usuarios que usaron Visual Studio 2015 o versiones anteriores de Visual Studio 2017 para implementar y depurar aplicaciones en sus HoloLens y, a continuación, usaron posteriormente las versiones más recientes de Visual Studio 2017 o Visual Studio 2019 con el mismo HoloLens, se verán afectados. Las versiones más recientes de Visual Studio implementan una nueva versión de un componente, pero los archivos de la versión anterior se quedan en el dispositivo, lo que provoca un error en la versión más reciente.  Esto produce el siguiente mensaje de error: DEP0100: Asegúrese de que el dispositivo de destino tiene habilitado el modo de desarrollador. No se pudo obtener una licencia de desarrollador \<ip\> en debido al error 80004005.

#### <a name="workaround"></a>Solución alternativa

Nuestro equipo está trabajando actualmente en una corrección. Mientras tanto, puede usar los pasos siguientes para evitar el problema y ayudar a desbloquear la implementación y depuración:  

1. Abra Visual Studio.

1. Seleccione **File (Archivo)**  > **New (Nuevo)**  > **Project (Proyecto)** .

1. Seleccione Aplicación de consola de escritorio de Windows de **Visual C#**  >    >  **(.NET Framework).**

1. Asigne un nombre al proyecto (por ejemplo, "HoloLensDeploymentFix") y asegúrese de que framework esté establecido en al menos .NET Framework 4.5 y, a continuación, seleccione **Aceptar.**

1. Haga clic con el botón **derecho** en el nodo Referencias  Explorador de soluciones agregue las siguientes referencias (seleccione la sección Examinar y **seleccione Examinar**):

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Si no tiene instalada la versión 10.0.18362.0, use la versión más reciente que tenga. 

1. Haga clic con el botón derecho en el proyecto Explorador de soluciones seleccione **Agregar**  >  **elemento existente.**

1. Vaya a C:\Archivos de programa (x86)\Windows Kits\10\bin\10.0.18362.0\x86 y cambie el filtro a Todos los archivos **( \* . \* )**.

1. Seleccione SirepClient.dll y SshClient.dll y Seleccione **Agregar**.

1. Busque y seleccione ambos archivos en Explorador de soluciones (deben estar en la parte inferior de la  lista de archivos) y cambie **Copiar** al directorio de salida en la ventana Propiedades a Copiar **siempre.**

1. En la parte superior del archivo, agregue lo siguiente a la lista existente `using` de instrucciones:

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. Dentro de `static void Main(...)` , agregue el código siguiente:

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. Seleccione **Compilar** > **Compilar solución**.

1. Abra una ventana del símbolo del sistema y cd en la carpeta que contiene el archivo .exe compilado (por ejemplo, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).

1. Ejecute el ejecutable y proporcione la dirección IP del dispositivo como argumento de línea de comandos. (Si está conectado mediante USB, puede usar 127.0.0.1; de lo contrario, use la dirección IP del Wi-Fi del dispositivo).  Por ejemplo, "HoloLensDeploymentFix 127.0.0.1".

1. Una vez que la herramienta ha salido sin ningún mensaje (esto solo debería tardar unos segundos), ahora podrá implementar y depurar desde Visual Studio 2017 o posterior.  No es necesario seguir utilizando la herramienta.

Se proporcionarán más actualizaciones a medida que estén disponibles.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>Problemas al iniciar Microsoft Store aplicaciones y en HoloLens

> [!NOTE]
> Última actualización: 4/2 @ 10 a. m.: problema resuelto. 

Puede experimentar problemas al intentar iniciar el Microsoft Store y las aplicaciones en HoloLens. Hemos determinado que el problema se produce cuando las actualizaciones de aplicaciones en segundo plano implementan una versión más reciente de los paquetes de marco en secuencias específicas mientras una o varias de sus aplicaciones dependientes todavía se están ejecutando. En este caso, una actualización automática de la aplicación entregó una nueva versión de .NET Native Framework (versión 10.0.25531 a 10.0.27413) hizo que las aplicaciones que se ejecutan no se actualizaran correctamente para todas las aplicaciones en ejecución que consuman la versión anterior del marco.  El flujo para la actualización del marco es el siguiente: 

1. El nuevo paquete de marco se descarga del almacén y se instala.

1. Todas las aplicaciones que usan el marco anterior se "actualizan" para usar la versión más reciente.

Si se interrumpe el paso 2 antes de la finalización, las aplicaciones para las que no se registró el marco más reciente no se iniciarán desde el menú Inicio.  Creemos que cualquier aplicación de HoloLens podría verse afectada por este problema.

Algunos usuarios han informado de que el cierre de aplicaciones que se han cerrado e iniciando otras aplicaciones como Centro de opiniones, Visor 3D o Fotos resuelve el problema, pero esto no funciona &mdash; el 100 % del tiempo.

La raíz ha provocado que este problema no se haya debido a la propia actualización, sino a un error en el sistema operativo que ha provocado que la actualización del marco de trabajo de .NET Native se controle incorrectamente. Nos complace anunciar que hemos identificado una corrección y que hemos publicado una actualización (versión del sistema operativo 17763.380) que contiene la corrección.  

Para ver si el dispositivo puede realizar la actualización, haga lo siguiente:

1. Vaya a la aplicación Configuración y abra **Actualizar & Seguridad.**

1. Seleccione **Buscar actualizaciones.**

1. Si la actualización a 17763.380 está disponible, actualice a esta compilación para recibir la corrección del error de app hang.

1. Tras actualizar a esta versión del sistema operativo, las aplicaciones deben funcionar según lo previsto.

Además, como hacemos con cada versión del sistema operativo HoloLens, hemos publicado la imagen de FFU en el Centro [de descarga de Microsoft.](https://aka.ms/hololensdownload/10.0.17763.380)

Si no desea realizar la actualización, hemos publicado una nueva versión de la aplicación Microsoft Store UWP a partir del 29/3. Una vez actualizada la versión de Store:

1. Abra store y confirme que se carga.
1. Use el gesto de Bloom para abrir el menú.
1. Intente abrir aplicaciones previamente rotas.
1. Si todavía no se puede iniciar, mantenga presionado el icono de la aplicación rota y seleccione Desinstalar.
1. Vuelva a instalar estas aplicaciones desde la tienda.

Si el dispositivo sigue sin poder cargar aplicaciones, puede realizar la instalación local de una versión de .NET Native Framework y Runtime a través del Centro de descarga siguiendo estos pasos:

1. Descargue este [archivo ZIP desde](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) el Centro de descarga de Microsoft. La descomprimir producirá dos archivos.  Microsoft .NET.Native.Runtime.1.7.appx y Microsoft .NET.Native.Framework.1.7.appx.

1. Compruebe que el dispositivo está desbloqueado.  Si no lo ha hecho antes, consulte Uso de [la Portal de dispositivos Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) para obtener instrucciones.

1. A continuación, quiere entrar en el Portal de dispositivos Windows. Nuestra recomendación es hacerlo a través de USB y lo haría escribiendo http://127.0.0.1:10080 en el explorador.

1. Una vez que haya Portal de dispositivos Windows, necesitamos que "cargue lateralmente" los dos archivos que descargó. Para ello, debe bajar la barra lateral izquierda hasta llegar a la sección **Aplicaciones** y seleccionar **Aplicaciones.**

1. A continuación, verá una pantalla similar a la siguiente.  Quiere ir a la sección que dice **Instalar** aplicación y ir a donde descomprimió esos dos archivos APPX. Solo puede hacer una a la vez, por lo que después de seleccionar la primera, haga clic en "Ir" en la sección Implementar. A continuación, haga esto para el segundo archivo APPX.

   ![Portal de dispositivos Windows instalar la Side-Loaded aplicación](images/20190322-DevicePortal.png)
   
1. En este momento creemos que las aplicaciones deben empezar a funcionar de nuevo y que también puede acceder a store.

1. En algunos casos, es necesario ejecutar el paso adicional de inicio de Visor 3D aplicación antes de que se inicien las aplicaciones afectadas. 

Agradecemos su paciencia a medida que hemos pasado por el proceso para resolver este problema y esperamos seguir trabajando con nuestra comunidad para crear experiencias de Mixed Reality correctas.

### <a name="device-update"></a>Actualización de dispositivos

- 30 segundos después de una nueva actualización, el shell puede desaparecer una vez. Realice el gesto **de Bloom** para reanudar la sesión.

### <a name="visual-studio"></a>Visual Studio

- Consulte [Instalación de las herramientas](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) para obtener la versión más actualizada de Visual Studio que se recomienda para el desarrollo de HoloLens.

- Al implementar una aplicación de Visual Studio en HoloLens, es posible que vea el error: La operación solicitada no se puede realizar en un archivo con una sección asignada por **el usuario abierta. (Excepción de HRESULT: 0x800704C8)**. Si esto sucede, inténtelo de nuevo y la implementación generalmente se realizará correctamente.

### <a name="api"></a>API

- Si la aplicación establece el [punto](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) de enfoque detrás del usuario o lo normal en camera.forward, los hologramas no aparecerán en Captura de realidad mixta fotos o vídeos. Hasta que este error se corrigió [](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) en Windows, si las aplicaciones establecen activamente el punto de enfoque, deben asegurarse de que el plano normal se establece en dirección opuesta a la cámara (por ejemplo, normal = -camera.forward).

### <a name="xbox-wireless-controller"></a>Controlador inalámbrico de Xbox

- El controlador inalámbrico S de Xbox debe actualizarse para poder usarse con HoloLens. Asegúrese de que [está actualizado antes](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) de intentar emparejar el controlador con un HoloLens.

- Si reinicias HoloLens mientras el controlador inalámbrico de Xbox está conectado, el controlador no se volverá a conectar automáticamente a HoloLens. La luz del botón Guía parpadeará lentamente hasta que el controlador se apague después de 3 minutos. Para volver a conectar el controlador inmediatamente, apague el controlador manteniendo presionado el botón Guía hasta que se apague la luz. Cuando vuelva a encender el controlador, se volverá a conectar a HoloLens.

- Si HoloLens entra en espera mientras el controlador inalámbrico de Xbox está conectado, cualquier entrada del controlador reactivará a HoloLens. Puede evitarlo apagando el controlador cuando haya terminado de usarlo.

## <a name="known-issues-for-hololens-emulator"></a>Problemas conocidos del emulador de HoloLens

- No todas las aplicaciones del Microsoft Store son compatibles con el emulador. Por ejemplo, Young Conker y Fragments no se pueden reproducir en el emulador.
- No puede usar la cámara web del equipo en el emulador.
- La característica Live Preview del Portal de dispositivos Windows no funciona con el emulador. Todavía puede capturar vídeos Mixed Reality imágenes.
