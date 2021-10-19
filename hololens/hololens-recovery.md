---
title: Reinicio, restablecimiento o recuperación de HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Cómo usar Advanced Recovery Companion para instalar una imagen en HoloLens 2.
keywords: procedimientos, reiniciar, restablecer, recuperar, restablecimiento completo, restablecimiento parcial, reinicio, HoloLens, apagado, arc, advanced recovery companion
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 08/30/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: 0efcfd0adf9bd380007e5ed4f905cb130b76d4b8
ms.sourcegitcommit: 19d1abb7589cebf14ba45e830f49224f7b4fcfe9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2021
ms.locfileid: "130034253"
---
# <a name="restart-reset-or-recover-hololens-2"></a>Reinicio, restablecimiento o recuperación de HoloLens 2

>[!IMPORTANT]
> Antes de iniciar cualquier procedimiento de solución de problemas, asegúrese de que el dispositivo tenga entre un **20 y un 40 por ciento** de batería, si es posible. Las [luces indicadoras de batería](hololens2-setup.md#lights-that-indicate-the-battery-level) que se encuentran debajo del botón de encendido son una manera rápida de comprobar la capacidad de la batería sin iniciar sesión en el dispositivo.

Use el [cable y cargador USB-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) incluidos con HoloLens 2, ya que esa es la mejor manera de cargar el dispositivo. El cargador suministra 18 W de potencia (9 V a 2 A). Con el cargador de pared suministrado, los dispositivos HoloLens 2 pueden realizar una carga completa de la batería en menos de 65 minutos cuando el dispositivo está en modo de espera. Si esos accesorios no están disponibles, asegúrese de que el cargador disponible admita al menos 15 W de potencia.

> [!NOTE]
> Si es posible, evite usar un equipo para cargar el dispositivo por USB, ya que eso es lento.

Si el dispositivo se ha encendido correctamente y está en funcionamiento, hay tres formas de comprobar el nivel de carga de la batería:

- Desde el menú principal de la interfaz de usuario del dispositivo HoloLens.
- Los LED situados junto al botón de encendido (para una carga de un 40 %, debería ver al menos dos LED fijos).
    - Cuando el dispositivo se está cargando, se ilumina el indicador de la batería para señalar el nivel de carga actual.  La última luz parpadea para indicar que se está cargando.
    - Cuando HoloLens está encendido, el indicador de la batería muestra el nivel de esta en cinco incrementos.
    - Si solo hay encendida una de las cinco luces, el nivel de la batería está por debajo del 20 por ciento.
    - Si el nivel de la batería es demasiado bajo y se intenta encender el dispositivo, una luz parpadea brevemente y después se apaga.
- En el equipo host, abra **Explorador de archivos** y busque el dispositivo HoloLens 2 en el lado izquierdo, en **Este equipo**. Haga clic con el botón derecho en el dispositivo y seleccione **Propiedades**. Un cuadro de diálogo muestra el nivel de carga de la batería.

   ![Una pantalla de propiedades de HoloLens 2 muestra el nivel de carga de la batería.](images/ResetRecovery2.png)

Si el dispositivo no puede arrancar en el menú de inicio, observe la apariencia del LED y la enumeración de dispositivos en el equipo host. A continuación, siga la [guía de solución de problemas](hololens-troubleshooting.md). Si el estado del dispositivo no coincide con ninguno de los estados indicados en la guía de solución de problemas, realice el [procedimiento de restablecimiento completo](hololens-recovery.md#hard-restart-procedure) con el dispositivo conectado a la fuente de alimentación, en lugar de al equipo host. Espere al menos una hora para que el dispositivo se cargue.

> [!NOTE]
> Para empezar, definamos los términos.\
> "Reiniciar" simplemente significa apagar y encender el dispositivo.\
> "Restablecer" significa restaurar el dispositivo a los valores predeterminados a través de la interfaz de usuario de configuración para volver a instalar la imagen actual.\
> "Reprogramar" significa que el dispositivo está conectado a un equipo y que se va a instalar una nueva imagen (puede ser otra diferente).

## <a name="restart-the-device"></a>Reinicie el dispositivo.

En determinadas circunstancias, puede que tenga que reiniciar manualmente el dispositivo sin utilizar la interfaz de usuario del software. Esto puede ayudarlo a resolver un problema que se produce sin tener que restablecer ni reprogramar el dispositivo.

### <a name="standard-restart-procedure"></a>Procedimiento de reinicio estándar

1. Desenchufe el cable de tipo C para desconectar el dispositivo de la fuente de alimentación o del equipo host.

2. Mantenga presionado el botón de **encendido** durante 15 segundos. Deberían apagarse todas las luces LED.

3. Espere de 2 a 3 segundos y, a continuación, presione el botón de **encendido**. Se encenderán las luces LED cercanas al botón de encendido y el dispositivo se iniciará.

4. Conecte el dispositivo al equipo host y, después, abra el Administrador de dispositivos. (En Windows 10, presione la tecla **Windows**, luego la tecla **X** y, a continuación, seleccione **Administrador de dispositivos**). Asegúrese de que el dispositivo aparece correctamente en la lista como *Microsoft HoloLens*, tal y como se muestra en la imagen siguiente:

   ![Administrador de dispositivos para la recuperación de un dispositivo Microsoft HoloLens 2.](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-restart-procedure"></a>Procedimiento de reinicio completo

Si el procedimiento de reinicio estándar no ha funcionado, utilice el procedimiento de restablecimiento completo:

1. Desenchufe el cable de tipo C para desconectar el dispositivo de la fuente de alimentación o del equipo host.

1. Mantenga presionados los botones de **bajar volumen** + **encendido** durante 15 segundos. El dispositivo se reiniciará automáticamente.

1. Conecte el dispositivo al equipo host.

1. Abra Administrador de dispositivos (en Windows 10, presione la tecla **Windows**, luego la tecla **X** y, a continuación, seleccione **Administrador de dispositivos**). Asegúrese de que el dispositivo aparece correctamente en la lista como *Microsoft HoloLens*, tal y como se muestra en la imagen siguiente:

   ![Administrador de dispositivos 2 para la recuperación de un dispositivo Microsoft HoloLens 2.](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a>Nueva instalación de la imagen del dispositivo

En situaciones extraordinarias, puede que tenga que instalar de nuevo la imagen del dispositivo HoloLens 2. Tenga en cuenta que no se espera que esta opción solucione los siguientes problemas:

- [Uniformidad de color de la pantalla](hololens2-display.md)
- Arranque con sonido pero sin salida de pantalla
- [Patrón de LED 1-3-5](hololens2-setup.md#lights-to-indicate-problems)
- [Overheating](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- Bloqueos del sistema operativo (distintos de los bloqueos de la aplicación)

Hay dos formas de volver a instalar la imagen del dispositivo. En ambas, antes debe [instalar Advanced Recovery Companion desde Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).

>[!WARNING]
>Si vuelve a instalar la imagen del dispositivo, se eliminarán todos los datos personales, las aplicaciones y la configuración, incluida la información para restablecer el TPM.

De manera predeterminada, Advanced Recovery Companion está configurado para descargar la versión de actualización de características más reciente. Para obtener información sobre la versión de actualización de características, consulte las [notas de la versión de HoloLens 2](hololens-release-notes.md). Para obtener el paquete en formato Full Flash Update (FFU) de HoloLens 2 más reciente y volver a instalar la imagen del dispositivo por medio de Advanced Recovery Companion, descargue la imagen de actualización mensual de HoloLens 2 más reciente: [https://aka.ms/hololens2download](https://aka.ms/hololens2download). Esta versión es la compilación más reciente disponible con carácter general.

Antes de iniciar el procedimiento de instalación de la imagen, asegúrese de que la aplicación esté instalada y en ejecución en su PC con Windows 10 y de que esté lista para detectar el dispositivo. Asegúrese también de que el dispositivo HoloLens está cargado al 40 % como mínimo.

![Captura de pantalla de nueva instalación de la imagen de HoloLens 2.](images/ARC1.png)

### <a name="normal-flashing-procedure"></a>Procedimiento de instalación de imagen normal

1. Con el dispositivo HoloLens está en funcionamiento, conéctelo al PC con Windows 10 en el que ha abierto previamente la aplicación Advanced Recovery Companion.

   El dispositivo se detectará automáticamente y la interfaz de usuario de la aplicación Advanced Recovery Companion iniciará el proceso de actualización:

   ![Pantalla inicial de la nueva instalación de la imagen de HoloLens 2.](images/ARC2.png)

1. Seleccione el dispositivo HoloLens 2 en la interfaz de usuario de la aplicación Advanced Recovery Companion y siga las instrucciones para completar la instalación de la imagen.

### <a name="manual-flashing-mode-procedure"></a>Procedimiento del modo de instalación de imagen manual

Es posible que tenga que poner el dispositivo en modo de recuperación si:

- El dispositivo HoloLens 2 no se inicia correctamente.
- Advanced Recovery Companion no puede detectar el dispositivo.
- Ya no conoce la contraseña o el PIN de un dispositivo que solo tiene un usuario.

1. Desenchufe el cable de tipo C para desconectar el dispositivo de la fuente de alimentación o del equipo host.

2. Mantenga presionado el botón de **encendido** durante 15 segundos. Todos los LED deberían apagarse.

3. Mientras presiona el botón para **subir volumen**, presione y suelte el botón de **encendido** para iniciar el dispositivo. Espere 15 segundos y, a continuación, suelte el botón para **subir volumen**. De los cinco LED, se encenderá solo el LED del centro.

4. Conecte el dispositivo al equipo host y abra el Administrador de dispositivos. (En Windows 10, presione la tecla **Windows**, luego la tecla **X** y, a continuación, seleccione **Administrador de dispositivos**). Asegúrese de que el dispositivo aparece correctamente en la lista como Microsoft HoloLens, tal y como se muestra en la imagen siguiente:

   ![Recuperación de Microsoft HoloLens 2.](images/MicrosoftHoloLensRecovery.png)

   El dispositivo se detectará automáticamente y la interfaz de usuario de la aplicación Advanced Recovery Companion iniciará el proceso de actualización:

   ![Pantalla de nueva instalación de la imagen de HoloLens 2.](images/ARC2.png)

6. Seleccione el dispositivo HoloLens 2 en la interfaz de usuario de la aplicación Advanced Recovery Companion y, a continuación, siga las instrucciones para completar la nueva instalación de la imagen.

## <a name="troubleshoot-advanced-recovery-companion"></a>Solución de problemas de Advanced Recovery Companion

1. Asegúrese de que el dispositivo está cargado como mínimo al 40 % antes de intentar instalar la imagen.

1. Compruebe que el dispositivo está desbloqueado.

1. Compruebe que el dispositivo está conectado directamente al equipo host, no a un centro de conectividad.

1. Si el dispositivo no se muestra como un dispositivo HoloLens/HoloLens Recovery en Controladores de bus serie universal, compruebe lo siguiente:
    1. **Puertos**, como un dispositivo Qualcomm HS-USB.
    1. **Otros dispositivos**, como un dispositivo QUSB_BULK: en el equipo host faltan los controladores necesarios para detectar el dispositivo HoloLens. Haga clic con el botón derecho, seleccione Actualizar controlador y busque controladores en línea o [active Actualizaciones opcionales en la configuración de Windows Update](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674). Una vez descargado el controlador, ARC debería poder detectarlo.

1. Si ARC no detecta el dispositivo, asegúrese de que puede conectarse a él desde el Explorador de archivos en el equipo. Si no puede:

    1. Es posible que el dispositivo tenga directivas USB que deshabiliten esa conexión. Si es así, pruebe el [procedimiento manual](hololens-recovery.md#manual-flashing-mode-procedure) para instalar la imagen.
    2. Si no hay directivas, pruebe con otro cable USB.

1. Compruebe que el dispositivo no muestra un [patrón de LED 1-3-5](hololens2-setup.md#lights-to-indicate-problems).

## <a name="download-arc-without-using-the-app-store"></a>Descarga de ARC sin usar la tienda de aplicaciones

Si el entorno de TI impide el uso de la aplicación de Windows Store o limita el acceso a la tienda comercial, el administrador de TI puede hacer que esta aplicación esté disponible por medio de una ruta de acceso de implementación "sin conexión".

 >[!NOTE]
 > - Los administradores de TI también pueden distribuir esta aplicación por medio de System Center Configuration Manager (SCCM) o Intune.
 > - Esta guía se centra en Advanced Recovery Companion, pero el proceso se puede utilizar también con otras aplicaciones sin conexión.

Siga estos pasos para habilitar la ruta de acceso de implementación:

1. Vaya a [Microsoft Store para Empresas](https://businessstore.microsoft.com) e inicie sesión con una identidad de Azure Active Directory.

1. Vaya a **Administrar > Configuración**. Active **Show offline apps** (Mostrar aplicaciones sin conexión) en **Shopping experience** (Experiencia de compra).

1. Vaya a **Comprar para mi grupo** y busque [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).

1. Cambie **Tipo de licencia** a **_Sin conexión_ *_ y seleccione _* Administrar**.

1. En **Descargar el paquete para usar sin conexión**, seleccione el segundo botón azul **Descargar**. Asegúrese de que la extensión del archivo sea *.appxbundle*.

    - En esta etapa, si el equipo de escritorio tiene acceso a Internet, haga doble clic en el paquete para instalar la aplicación.

    - Si el equipo de destino no tiene conectividad a Internet, siga estos pasos:
       1. Seleccione la licencia no codificada y, a continuación, **Generar licencia**.
       2. En **Marcos necesarios**, seleccione **Descargar**.
       3. Use DISM para aplicar el paquete con la dependencia y la licencia. Desde un símbolo del sistema de administrador, ejecute el siguiente comando:

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > Puede que el número de versión de este ejemplo de código no coincida con la versión disponible actualmente. También puede que haya elegido una ubicación de descarga diferente a la del ejemplo. Realice los cambios necesarios en el comando.

> [!TIP]
> Cuando planee usar Advanced Recovery Companion para instalar una FFU sin conexión, puede que resulte útil descargar la imagen flash. [**Descargue la imagen actual para HoloLens 2**](https://aka.ms/hololens2download).

Otros recursos:

- [Distribuir aplicaciones sin conexión](/microsoft-store/distribute-offline-apps) 
- [Opciones de línea de comandos de mantenimiento del paquete de la aplicación DISM (.appx o .appxbundle)](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
