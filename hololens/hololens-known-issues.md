---
title: Problemas conocidos de HoloLens
description: Esta es la lista de problemas conocidos que pueden afectar a los desarrolladores de HoloLens.
keywords: solución de problemas, problema conocido, ayuda
author: mattzmsft
ms.author: mazeller
ms.date: 4/20/2020
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
ms.openlocfilehash: db95edfbadb271b7fc47cf5798e80d9b2cad3c90
ms.sourcegitcommit: 708da7b390fed1fd3aea1a2b2e50461851052683
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881333"
---
# Problemas conocidos de HoloLens

Esta es la lista actual de problemas conocidos para dispositivos HoloLens. Marca aquí primero si ves un comportamiento extraño. Esta lista se mantendrá actualizada a medida que se descubran problemas nuevos o se informe de ellos, o cuando se resuelvan problemas en futuras actualizaciones de software de HoloLens.

>[!NOTE]
> - Si descubres un problema que no te bloquea, puedes notificarlo en tu dispositivo HoloLens a través del [centro de comentarios](hololens-feedback.md).
> - Si el problema que estás enfrentando te está bloqueando, en addtion para enviar comentarios, haz [una solicitud de asistencia](https://aka.ms/hlsupport).

- [Problemas conocidos para todas las generaciones de HoloLens](#known-issues-for-all-hololens-generations)
- [Problemas conocidos para dispositivos HoloLens 2](#known-issues-for-hololens-2-devices)
- [Problemas conocidos de HoloLens (1ª generación)](#known-issues-for-hololens-1st-gen)
- [Problemas conocidos con el emulador HoloLens](#known-issues-for-hololens-emulator)

## Problemas conocidos para todas las generaciones de HoloLens

### Unity

- Consulta [instalar las herramientas](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) de la versión más actualizada de Unity recomendada para el desarrollo de HoloLens.
- Los problemas conocidos con la versión preliminar de Unity HoloLens están documentados en los [foros de Unity de hololens](https://forum.unity3d.com/threads/known-issues.394627/).

### Windows Device Portal

- La característica de vista previa dinámica de la captura de realidad mixta puede mostrar varios segundos de latencia.
- En la página de entrada virtual, los controles gestos y de desplazamiento de la sección gestos virtuales no funcionan. Su uso no tendrá ningún efecto. El teclado virtual de la misma página funciona correctamente.
- Después de habilitar el modo de Desarrollador en la configuración, puede demorar unos segundos antes de que se habilite el cambio para activar el portal del dispositivo.

### Carga de la cámara de OneDrive

La aplicación de OneDrive para HoloLens no admite la carga automática de la cámara para las cuentas profesionales o educativas.

Correccion
- Si es viable para su empresa, la carga de cámara automática es compatible con las cuentas de Microsoft. Puede iniciar sesión en su cuenta de Microsoft además de en su cuenta profesional o educativa (la aplicación de OneDrive admite el inicio de sesión dual). Desde el perfil de la cuenta de Microsoft dentro de OneDrive puede habilitar la carga automática de la cámara en segundo plano.
- Si no puede usar de forma segura una cuenta de Microsoft para cargar las fotos automáticamente, puede cargar manualmente las fotos en su cuenta profesional o educativa desde la aplicación de OneDrive. Para ello, asegúrese de que ha iniciado sesión en su cuenta profesional o educativa en la aplicación de OneDrive. Seleccione el **+** botón y elija **cargar**. Busca las fotos o vídeos que deseas cargar desplazándose a las **imágenes > álbum de cámara**. Seleccione las fotos o los vídeos que desee cargar y, a continuación, seleccione el botón **abrir** .

## Problemas conocidos para dispositivos HoloLens 2

### Se muestra una pantalla azul después de cancelar la inscripción de las compilaciones de Insider Preview en un dispositivo que se retrasó con una compilación de Insider

Esto es un problema que afecta a los usuarios que se encuentran en una compilación de Insider Preview, reproducían HoloLens 2 con una nueva compilación de Insider Preview y luego se anula la inscripción del programa Insider. 

Esto no afecta a:
- Usuarios que no están inscritos en Windows Insider 
- Insider
    - Si se ha inscrito un dispositivo desde que las compilaciones de Insider eran la versión 18362. x
    - Si han parpadeado una versión de 19041. x firmada por el Insider, y permanece inscrito en el programa Insider 

Solución alternativa: 
- Evitar el problema 
    - Crear una compilación que no sea de Insider. Una de las actualizaciones mensuales normales. 
    - Mantente en la versión preliminar de Insider
- Reparpadee el dispositivo
    1. Coloca la [HoloLens 2 en el modo parpadeando](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) de forma manual; Después, manteniendo el volumen al día, pulse el botón de encendido.
    1. Conéctese al equipo y abra el Asistente de recuperación avanzada. 
    1. Llama a HoloLens 2 a la compilación predeterminada.   

## Problemas conocidos de HoloLens (1ª generación)

### No se puede conectar e implementar en HoloLens a través de Visual Studio

> [!NOTE]
> Última actualización: 8/8 @ 5:11PM-Visual Studio ha lanzado VS 2019 versión 16,2, que incluye una corrección para este problema. Recomendamos actualizar la versión más reciente para evitar que se produzca este error.

Visual Studio ha publicado la versión 16,2 de VS 2019, que incluye una corrección para este problema. Recomendamos actualizar la versión más reciente para evitar que se produzca este error.

Problema de raíz del problema: los usuarios que usaron Visual Studio 2015 o versiones anteriores de Visual Studio 2017 para implementar y depurar aplicaciones en su HoloLens y después usar posteriormente las versiones más recientes de Visual Studio 2017 o Visual Studio 2019 con el mismo HoloLens se verán afectadas. Las versiones más recientes de Visual Studio implementan una nueva versión de un componente, pero los archivos de la versión anterior permanecen en el dispositivo, lo que provoca errores en la versión más reciente.  Esto provoca el siguiente mensaje de error: DEP0100: Asegúrese de que el dispositivo de destino tiene habilitado el modo de desarrollador. No se pudo obtener una licencia de desarrollador \<ip\> para el error 80004005.

#### Solución alternativa

Nuestro equipo está trabajando actualmente en una solución. Mientras tanto, puede usar los pasos siguientes para solucionar el problema y ayudar a desbloquear la implementación y la depuración:  

1. Abrir Visual Studio
1. Seleccione **archivo**  >  **nuevo**  >  **proyecto**.
1. Seleccione aplicación de consola de escritorio de **Visual C#**  >  **Windows Desktop**  >  **(.NET Framework)**.
1. Asigne un nombre al proyecto (como "HoloLensDeploymentFix") y asegúrese de que el marco está configurado como mínimo en .NET Framework 4,5 y, a continuación, seleccione **Aceptar**.
1. Haga clic con el botón derecho en el nodo **referencias** en el explorador de soluciones y agregue las siguientes referencias (seleccione la sección **examinar** y seleccione **examinar**):

    ```CMD
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Si no tiene 10.0.18362.0 instalado, use la versión más reciente que tenga. 

1. Haga clic con el botón derecho en el proyecto en el explorador de soluciones y seleccione **Agregar**  >  **elemento existente**.
1. Vaya a C:\Archivos de programa (x86) \Windows Kits\10\bin\10.0.18362.0\x86 y cambie el filtro a **todos los archivos (\ *. \ *)**.
1. Seleccione SirepClient.dll y SshClient.dll y haga clic en **Agregar**.
1. Busque y seleccione ambos archivos en el explorador de soluciones (deberían estar en la parte inferior de la lista de archivos) y cambie la **copia a directorio de salida** en la ventana **propiedades** para **copiar siempre**.
1. En la parte superior del archivo, agregue lo siguiente a la lista de `using` instrucciones existente:

    ```CMD
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. En el interior de `static void Main(...)` , agregue el siguiente código:

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. Seleccione **generar**  >  **solución de compilación**.
1. Abra una ventana del símbolo del sistema y un CD en la carpeta que contiene el archivo. exe compilado (por ejemplo, C:\MyProjects\HoloLensDeploymentFix\bin\Debug)
1. Ejecuta el archivo ejecutable y proporciona la dirección IP del dispositivo como un argumento de la línea de comandos. (Si se conecta mediante USB, puede usar 127.0.0.1; de lo contrario, usar la dirección IP de Wi-Fi del dispositivo).  Por ejemplo, "HoloLensDeploymentFix 127.0.0.1"

1. Una vez que la herramienta haya salido sin ningún mensaje (esto debería tardar solo unos segundos), ahora podrá implementar y depurar desde Visual Studio 2017 o posterior.  El uso continuado de la herramienta no es necesario.

Proporcionaremos actualizaciones adicionales a medida que estén disponibles.

### Problemas al iniciar Microsoft Store y las aplicaciones en HoloLens

> [!NOTE]
> Última actualización: 4/2 @ 10% AM-problema solucionado. 

Es posible que se produzcan problemas al intentar iniciar Microsoft Store y las aplicaciones en HoloLens. Hemos determinado que el problema se produce cuando las actualizaciones de las aplicaciones en segundo plano implementan una versión más reciente de los paquetes de Framework en secuencias específicas, mientras una o más de sus aplicaciones dependientes siguen ejecutándose. En este caso, una actualización automática de la aplicación ha entregado una nueva versión de .NET Native Framework (versión 10.0.25531 a 10.0.27413) porque las aplicaciones que se ejecutan no se actualizan correctamente para todas las aplicaciones en ejecución que consumen la versión anterior de Framework.  El flujo para la actualización del marco es el siguiente: 

1. El nuevo paquete de .NET Framework se descarga de la tienda y se instala
1. Todas las aplicaciones que usan el marco anterior se ' actualizan ' para usar la versión más reciente

Si el paso 2 se interrumpe antes de su finalización, las aplicaciones para las que no se registró el marco más reciente no se podrán iniciar desde el menú Inicio.  Creemos que cualquier aplicación en HoloLens podría verse afectada por este problema.

Algunos usuarios han informado que el cierre de aplicaciones bloqueadas y el inicio de otras aplicaciones como el centro de opiniones, el visor 3D o las fotos resuelve el problema &mdash; sin embargo, esto no funciona en el 100% del tiempo.

Tenemos raíz debido a que este problema no causó la causa de la actualización, pero un error en el sistema operativo que provocaba que la actualización de .NET Native Framework no se controlara correctamente. Nos complace anunciar que hemos identificado una corrección y que hemos publicado una actualización (versión de SO 17763,380) que contiene la corrección.  

Para ver si su dispositivo puede llevar a cabo la actualización, haga lo siguiente:

1. Vaya a la aplicación configuración y Abra **actualización & seguridad**.
1. Seleccione **Buscar actualizaciones**.
1. Si la actualización a 17763,380 está disponible, actualice a esta compilación para recibir la corrección del error de bloqueo de la aplicación.
1. Al actualizar a esta versión del sistema operativo, las aplicaciones deberían funcionar según lo esperado.

Además, como hacemos con cada versión del sistema operativo HoloLens, hemos publicado la imagen de FFU en el [centro de descarga de Microsoft](https://aka.ms/hololensdownload/10.0.17763.380).

Si no deseas realizar la actualización, hemos publicado una nueva versión de la aplicación para UWP de Microsoft Store a partir de 3/29. Una vez que tenga la versión actualizada de la tienda:

1. Abra la tienda y confirme que se carga.
1. Use el gesto de la floración para abrir el menú.
1. Intente abrir aplicaciones que hayan sido eliminadas anteriormente.
1. Si sigue sin poder iniciarse, pulse y mantenga pulsado el icono de la aplicación dañada y seleccione Desinstalar.
1. Resinstall estas aplicaciones de la tienda.

Si el dispositivo aún no puede cargar aplicaciones, puede transferir una versión de .NET Native Framework y en tiempo de ejecución a través del centro de descargas siguiendo estos pasos:

1. Descarga [este archivo zip](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) desde el centro de descarga de Microsoft. Descomprimir genera dos archivos.  Microsoft. NET. Native. Runtime. 1.7. appx y Microsoft. NET. Native. Framework. 1.7. appx
1. Verifica que tu dispositivo esté desbloqueado.  Si no lo ha hecho antes de que las instrucciones para ello estén [aquí](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).
1. A continuación, deseas entrar en Windows Device portal. Nuestra recomendación es hacerlo a través de USB y lo harías escribiendo http://127.0.0.1:10080 en tu explorador.
1. Una vez que tengas Windows Device portal, necesitamos que "cargues" los dos archivos que has descargado. Para ello, debe ir hacia abajo en la barra lateral izquierda hasta llegar a la sección **aplicaciones** y seleccionar **aplicaciones**.
1. Verá una pantalla similar a la siguiente.  Quiere ir a la sección que indica **instalar aplicación** y examinar dónde descomprimió esos dos archivos appx. Solo puede realizar una por una, así que después de seleccionar la primera, haga clic en "ir" en la sección implementar. A continuación, haz esto para el segundo archivo APPX.

   ![Windows Device portal para instalar la aplicación de prueba](images/20190322-DevicePortal.png)
1. En este punto, creemos que las aplicaciones deberían comenzar a funcionar de nuevo y que también puedes acceder a la tienda.
1. En algunos casos, es necesario realizar el paso adicional de iniciar la aplicación de visor 3D antes de que se inicien las aplicaciones afectadas. 

Agradecemos tu paciencia porque hemos pasado por el proceso para resolver este problema, y esperamos continuar trabajando con nuestra comunidad para crear experiencias de realidad mixta con éxito.

### Actualización de dispositivo

- 30 segundos después de una nueva actualización, el shell puede desaparecer una vez. Realiza el gesto de la **floración** para reanudar la sesión.

### Visual Studio

- Consulta [instalar las herramientas](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) de la versión más actualizada de Visual Studio que se recomienda para el desarrollo de HoloLens.
- Al implementar una aplicación de Visual Studio en HoloLens, es posible que vea el error: **la operación solicitada no se puede realizar en un archivo con una sección asignada por el usuario abierta. (Excepción de HRESULT: 0x800704C8)**. Si esto sucede, inténtelo de nuevo y generalmente la implementación se realizará correctamente.

### API

- Si la aplicación establece el [punto de foco](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) detrás del usuario o el normal a la cámara. reenviar, los hologramas no aparecerán en la realidad mixta captura fotos o vídeos. Hasta que este error se solucione en Windows, si las aplicaciones establecen activamente el [punto de foco](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) , deben asegurarse de que el plano normal se establezca en sentido opuesto: reenvío de cámara (por ejemplo, normal =-Camera. forward).

### Controlador de telefonía móvil Xbox

- Es necesario actualizar el controlador inalámbrico de Xbox para poder usarlo con HoloLens. Asegúrate de estar [al día](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) antes de intentar emparejar tu controlador con HoloLens.
- Si reinicia tu HoloLens mientras el mando de Xbox Wireless está conectado, el controlador no volverá a conectarte automáticamente a HoloLens. La luz del botón de la guía parpadeará lentamente hasta que el controlador se apague después de 3 minutos. Para volver a conectar tu controlador inmediatamente, apaga el controlador manteniendo pulsado el botón guía hasta que se apague la luz. Cuando vuelvas a encender el controlador, se volverá a conectar a HoloLens.
- Si HoloLens entra en modo de espera mientras la controladora Xbox Wireless está conectada, cualquier entrada en el controlador reactivará HoloLens. Para evitar que esto ocurra, apague el dispositivo cuando haya terminado de usarlo.

## Problemas conocidos con el emulador HoloLens

- No todas las aplicaciones de Microsoft Store son compatibles con el emulador. Por ejemplo, los conkers y los fragmentos jóvenes no se pueden reproducir en el emulador.
- No puedes usar la cámara web para PC en el emulador.
- La característica de vista previa dinámica de Windows Device Portal no funciona con el emulador. Aún puedes capturar imágenes y videos de realidad mixta.
