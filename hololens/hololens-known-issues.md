---
title: Problemas conocidos de HoloLens
description: Manténgase al día con nuestra lista de problemas conocidos y soluciones alternativas que pueden afectar a los clientes y desarrolladores de HoloLens que usan Unity y Windows Device Portal.
keywords: solucionar problemas, problema conocido, ayuda
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284081"
---
# Problemas conocidos de HoloLens

Esta es la lista actual de problemas conocidos para dispositivos HoloLens. Compruebe aquí primero si ve un comportamiento extraño. Esta lista se mantendrá actualizada a medida que se descubran o se notifican nuevos problemas, o a medida que se aborden los problemas en futuras actualizaciones de software de HoloLens.

>[!NOTE]
> - Si detecta un problema que no está bloqueando, notimente en su dispositivo HoloLens a través del Centro [de opiniones.](hololens-feedback.md)
> - Si el problema al que te enfrentas te está bloqueando, además de enviar comentarios, presenta [una solicitud de soporte técnico.](https://aka.ms/hlsupport)

- [Problemas conocidos de todas las generaciones de HoloLens](#known-issues-for-all-hololens-generations)
- [Problemas conocidos para dispositivos HoloLens 2](#known-issues-for-hololens-2-devices)
- [Problemas conocidos de HoloLens (1.ª generación)](#known-issues-for-hololens-1st-gen)
- [Problemas conocidos para el emulador de HoloLens](#known-issues-for-hololens-emulator)

## Problemas conocidos de todas las generaciones de HoloLens

### Unity

- Consulta [Instalar las herramientas para](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) obtener la versión más actualizada de Unity recomendada para el desarrollo de HoloLens.
- Los problemas conocidos de Unity HoloLens Technical Preview se documentan en los [foros de Unity de HoloLens.](https://forum.unity3d.com/threads/known-issues.394627/)

### Windows Device Portal

- La característica Vista previa en vivo de la captura de realidad mixta puede mostrar varios segundos de latencia.

- En la página Entrada virtual, los controles Gestos y Desplazamiento de la sección Gestos virtuales no funcionan. Su uso no tendrá ningún efecto. El teclado virtual de la misma página funciona correctamente.

- Después de habilitar el modo de desarrollador en Configuración, el cambio puede tardar unos segundos en activar Device Portal.

### Carga de cámara de OneDrive

La aplicación de OneDrive para HoloLens no admite la carga automática de cámara para cuentas profesionales o educativas.

Soluciones alternativas:

- Si es viable para tu empresa, la carga automática de cámara se admite en las cuentas de Microsoft del consumidor. Puede iniciar sesión en su cuenta microsoft además de su cuenta profesional o educativa (la aplicación de OneDrive admite el inicio de sesión dual). Desde su perfil de cuenta de Microsoft en OneDrive, puede habilitar la carga automática de la cámara en segundo plano.

- Si no puede usar de forma segura una cuenta microsoft de consumidor para cargar las fotos automáticamente, puede cargar fotos manualmente en su cuenta de trabajo o escuela desde la aplicación de OneDrive. Para ello, asegúrese de que ha iniciado sesión en su cuenta de trabajo o escuela en la aplicación de OneDrive. Seleccione el **+** botón y elija **Cargar**. Busca las fotos o vídeos que quieras cargar navegando a **Imágenes > de cámara.** Seleccione las fotos o vídeos que desea cargar y, a continuación, seleccione el **botón** Abrir.

## Problemas conocidos para dispositivos HoloLens 2

### Microsoft Edge no se puede iniciar

Algunos clientes han notificado un problema en el que Microsoft Edge no se puede iniciar. Para estos clientes, el problema persiste durante el reinicio y no se resuelve con actualizaciones de Windows o de aplicaciones. Si estás experimentando este problema y has confirmado que [Windows](hololens-updates.md#manually-check-for-updates)está actualizado, presenta [](hololens-feedback.md) un error desde la aplicación Centro de opiniones con la siguiente categoría y subcategoría: Instalar y actualizar > Descargar, instalar y configurar Windows Update.

No hay soluciones alternativas conocidas, ya que hasta ahora no hemos podido resolver la causa del problema. Archivar un error a través del Centro de opiniones ayudará a nuestra investigación.

### El teclado no cambia a caracteres especiales

Hay un problema durante la configuración rápida, en el que, una vez que el usuario ha elegido una cuenta de trabajo o escuela y está especificando su contraseña, intentar cambiar a los caracteres especiales del teclado pulsando el botón &123 no cambia a caracteres especiales. 

Trabajo:
-   Cierre el teclado y vuelva a abrirlo pulsando en el campo de texto.
-   Escribe la contraseña incorrectamente. Cuando se vuelva a iniciar el teclado la próxima vez, funcionará como se espera.
- Autenticación web, cierre el teclado y seleccione **Iniciar sesión desde otro dispositivo.** 
-   Si escribe solo números, un usuario puede presionar y mantener presionadas ciertas teclas para abrir un menú expandido.
-   Con un teclado USB.

Esto no afecta a:
- Usuarios que eligen usar una cuenta personal.

### Se muestra la pantalla azul después de deshacer la inscripción de las compilaciones de Insider Preview en un dispositivo reflashado con una compilación de Insider

This is an issue affecting that affects users who are on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program. 

Esto no afecta a:
- Usuarios que no están inscritos en Windows Insider 
- Insider:
    - Si se ha inscrito un dispositivo desde que las compilaciones de Insider eran la versión 18362.x
    - Si flasheó una compilación de Insider 19041.x firmada y permanece inscrita en el programa Insider 

Trabajo: 
- Evitar el problema 
    - Destello de una compilación que no es de insider. Una de las actualizaciones mensuales habituales. 
    - Mantenerse en Insider Preview
- Reflash the device

    1. Ponga [HoloLens 2](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) en modo de parpadeo manualmente; para hacerlo, apague completamente y no se conecte. A continuación, mientras mantienes presionado el volumen, pulsa el botón de inicio/apagado.
    
    1. Conéctese al equipo y abra Advanced Recovery Companion. 
    
    1. Flash de HoloLens 2 a la compilación predeterminada.   

## Problemas conocidos de HoloLens (1.ª generación)

### No se puede conectar e implementar en HoloLens a través de Visual Studio

> [!NOTE]
> Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue. Se recomienda actualizar a esta versión más reciente para evitar experimentar este error.

Visual Studio ha publicado VS 2019 Versión 16.2, que incluye una corrección para este problema. Se recomienda actualizar a esta versión más reciente para evitar experimentar este error.

Causa raíz del problema: los usuarios que usaron Visual Studio 2015 o versiones anteriores de Visual Studio 2017 para implementar y depurar aplicaciones en su HoloLens y, posteriormente, usaron las versiones más recientes de Visual Studio 2017 o Visual Studio 2019 con el mismo HoloLens se verán afectados. Las versiones más recientes de Visual Studio implementan una nueva versión de un componente, pero los archivos de la versión anterior se quedan en el dispositivo, lo que provoca un error en la versión más reciente.  Esto provoca el siguiente mensaje de error: DEP0100: asegúrate de que el dispositivo de destino tenga habilitado el modo de desarrollador. No se pudo obtener una licencia de \<ip\> desarrollador debido al error 80004005.

#### Solución alternativa

Nuestro equipo está trabajando actualmente en una corrección. Mientras tanto, puedes usar los siguientes pasos para evitar el problema y ayudar a desbloquear la implementación y la depuración:  

1. Abra Visual Studio.

1. Seleccione **Archivo**  >  **nuevo**  >  **proyecto**.

1. Seleccione **Visual C#**  >  **Aplicación de consola de**escritorio de Windows  >  **(.NET Framework).**

1. Asigne un nombre al proyecto (como "HoloLensDeploymentFix") y asegúrese de que el marco esté establecido como mínimo en .NET Framework 4.5 y, a continuación, seleccione **Aceptar.**

1. Haga clic con el botón secundario en el **nodo** Referencias en el Explorador de soluciones y agregue las siguientes referencias (seleccione la sección **Examinar** y seleccione **Examinar**):

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Si no tiene instalada la versión 10.0.18362.0, use la versión más reciente que tenga. 

1. Haga clic con el botón secundario **** en el proyecto en el Explorador de soluciones y seleccione  >  **Agregar elemento existente.**

1. Vaya a C:\Archivos de programa (x86)\Windows Kits\10\bin\10.0.18362.0\x86 y cambie el filtro a Todos los archivos **(\*.\*)**.

1. Seleccione SirepClient.dll y SshClient.dll y Seleccione **Agregar**.

1. Busque y seleccione ambos archivos en el Explorador de soluciones (deben **** estar en la **** parte inferior de la lista de archivos) y cambie Copiar al directorio de salida en la ventana Propiedades a **Copiar siempre.**

1. En la parte superior del archivo, agregue lo siguiente a la lista existente `using` de instrucciones:

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. Dentro de `static void Main(...)` , agregue el siguiente código:

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. Seleccione **Generar**  >  **solución de compilación.**

1. Abra una ventana del símbolo del sistema y un cd en la carpeta que contiene el archivo .exe compilado (por ejemplo, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).

1. Ejecuta el archivo ejecutable y proporciona la dirección IP del dispositivo como argumento de línea de comandos. (Si estás conectado mediante USB, puedes usar 127.0.0.1; de lo contrario, usa la dirección IP Wi-Fi del dispositivo).  Por ejemplo, "HoloLensDeploymentFix 127.0.0.1".

1. Después de salir de la herramienta sin ningún mensaje (esto solo debería tardar unos segundos), ahora podrá implementar y depurar desde Visual Studio 2017 o posterior.  El uso continuo de la herramienta no es necesario.

Proporcionaremos actualizaciones adicionales a medida que estén disponibles.

### Problemas al iniciar la Microsoft Store y las aplicaciones en HoloLens

> [!NOTE]
> Last Update: 4/2 @ 10 AM - Issue resolved. 

Es posible que tenga problemas al intentar iniciar la Microsoft Store y las aplicaciones en HoloLens. Hemos determinado que el problema se produce cuando las actualizaciones de aplicaciones en segundo plano implementan una versión más reciente de los paquetes de marco en secuencias específicas mientras una o varias de sus aplicaciones dependientes aún se están ejecutando. En este caso, una actualización automática de aplicaciones entregó una nueva versión de .NET Native Framework (versión 10.0.25531 a 10.0.27413) provocó que las aplicaciones que se ejecutan no se actualicen correctamente para todas las aplicaciones en ejecución que consuman la versión anterior del marco.  El flujo para la actualización del marco es el siguiente: 

1. El nuevo paquete de marco se descarga de la tienda e instala.

1. Todas las aplicaciones que usan el marco anterior se "actualizan" para usar la versión más reciente.

Si se interrumpe el paso 2 antes de finalizar, las aplicaciones para las que no se registró el marco más reciente no se iniciarán desde el menú Inicio.  Creemos que cualquier aplicación en HoloLens podría verse afectada por este problema.

Algunos usuarios han notificado que el cierre de aplicaciones que están fuera de servicio y el inicio de otras aplicaciones, como el Centro de opiniones, el Visor 3D o Fotos resuelve el problema para ellos, pero esto no funciona &mdash; el 100 % del tiempo.

Hemos originado que este problema no fue la propia actualización, sino un error en el sistema operativo que provocó que la actualización de .NET Native Framework se tratara incorrectamente. Nos complace anunciar que hemos identificado una corrección y hemos publicado una actualización (versión del sistema operativo 17763.380) que contiene la corrección.  

Para ver si el dispositivo puede realizar la actualización, por favor:

1. Vaya a la aplicación Configuración y abra **Actualizar & seguridad.**

1. Seleccione **Buscar actualizaciones.**

1. Si la actualización a 17763.380 está disponible, actualice a esta compilación para recibir la corrección del error de app hang.

1. Al actualizar a esta versión del sistema operativo, las aplicaciones deben funcionar según lo esperado.

Además, como hacemos con cada versión del sistema operativo HoloLens, hemos publicado la imagen FFU en el Centro [de descarga de Microsoft.](https://aka.ms/hololensdownload/10.0.17763.380)

Si no quieres realizar la actualización, hemos lanzado una nueva versión de la aplicación para UWP de Microsoft Store a partir del 29/3. Después de tener la versión actualizada de la Tienda:

1. Abre la Tienda y confirma que se carga.
1. Usa el gesto de bloom para abrir el menú.
1. Intenta abrir aplicaciones que se han roto anteriormente.
1. Si aún no se puede iniciar, mantén pulsado el icono de la aplicación rota y selecciona desinstalar.
1. Vuelva a instalar estas aplicaciones desde la tienda.

Si el dispositivo sigue sin poder cargar aplicaciones, puedes realizar la instalación de prueba de una versión de .NET Native Framework y Runtime a través del centro de descarga siguiendo estos pasos:

1. Descargue este [archivo zip desde](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) el Centro de descarga de Microsoft. La descomprimir producirá dos archivos.  Microsoft.NET.Native.Runtime.1.7.appx y Microsoft.NET.Native.Framework.1.7.appx.

1. Comprueba que el dispositivo está desbloqueado.  Si no lo has hecho antes, consulta [Usar Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) para obtener instrucciones.

1. A continuación, quieres entrar en Windows Device Portal. Nuestra recomendación es hacerlo a través de USB y lo haría escribiendo http://127.0.0.1:10080 en el explorador.

1. Una vez que haya configurado Windows Device Portal, necesitamos que "cargue lateralmente" los dos archivos que descargó. Para ello, debes bajar la barra del lado **** izquierdo hasta llegar a la sección Aplicaciones y seleccionar **Aplicaciones.**

1. A continuación, verás una pantalla similar a la siguiente.  You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files. Solo puede hacer una por vez, por lo que después de seleccionar la primera, haga clic en "Ir" en la sección Implementar. A continuación, haga esto para el segundo archivo APPX.

   ![Windows Device Portal para instalar Side-Loaded aplicación](images/20190322-DevicePortal.png)
   
1. En este punto creemos que las aplicaciones deberían empezar a funcionar de nuevo y que también puedes acceder a la Tienda.

1. En algunos casos, es necesario ejecutar el paso adicional para iniciar la aplicación Visor 3D antes de que se inicien las aplicaciones afectadas. 

Le agradecemos su paciencia a medida que hemos pasado por el proceso para resolver este problema y esperamos seguir trabajando con nuestra comunidad para crear experiencias de realidad mixta correctas.

### Actualización de dispositivos

- 30 segundos después de una nueva actualización, el shell puede desaparecer una vez. Realice el gesto **de bloom** para reanudar la sesión.

### Visual Studio

- Consulta [Instalar las herramientas](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) para obtener la versión más actualizada de Visual Studio que se recomienda para el desarrollo de HoloLens.

- Al implementar una aplicación de Visual Studio a holoLens, es posible que vea el error: La operación solicitada no se puede realizar en un archivo con una sección asignada por el **usuario abierta. (Excepción de HRESULT: 0x800704C8)**. Si esto ocurre, inténtelo de nuevo y la implementación generalmente se realizará correctamente.

### API

- Si la aplicación [](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) establece el punto de enfoque detrás del usuario o lo normal en cámara.forward, los hologramas no aparecerán en fotos o vídeos de captura de realidad mixta. Hasta que se corrigió este error [](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) en Windows, si las aplicaciones establecen activamente el punto de enfoque, deben asegurarse de que el plano normal se establece en dirección opuesta a la cámara (por ejemplo, normal = -camera.forward).

### Mando Inalámbrico Xbox

- El mando inalámbrico Xbox S debe actualizarse para poder usarse con HoloLens. Asegúrate de estar [actualizado antes](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) de intentar emparejar el controlador con un HoloLens.

- Si reinicias HoloLens mientras el mando inalámbrico de Xbox está conectado, el controlador no se volverá a conectar automáticamente a HoloLens. La luz del botón Guía parpadeará lentamente hasta que el controlador se apague después de 3 minutos. Para volver a conectar el controlador inmediatamente, apaga el controlador manteniendo presionado el botón Guía hasta que se apague la luz. Cuando enciendas el controlador de nuevo, se volverá a conectar a HoloLens.

- Si holoLens entra en modo de espera mientras el mando inalámbrico de Xbox está conectado, cualquier entrada en el controlador activará HoloLens. Puedes evitar esto apagando el controlador cuando termines de usarlo.

## Problemas conocidos para el emulador de HoloLens

- No todas las aplicaciones de Microsoft Store son compatibles con el emulador. Por ejemplo, Young Conker y Fragments no se pueden reproducir en el emulador.
- No puedes usar la cámara web del equipo en el emulador.
- La característica Live Preview de Windows Device Portal no funciona con el emulador. Aún puedes capturar imágenes y vídeos de realidad mixta.
