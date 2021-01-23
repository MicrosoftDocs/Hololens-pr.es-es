---
title: Reiniciar, restablecer o recuperar HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Cómo usar el Advanced Recovery Companion para pasar una imagen a la HoloLens 2.
keywords: pasos para, reiniciar, resetear, recuperar, restablecimiento completo, restablecimiento parcial, ciclo de energía, HoloLens, apagado, arc, advanced recovery companion
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
ms.openlocfilehash: 025ba8508eb930cdad6d502c381e5a07d9efc6e0
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284091"
---
# Reiniciar, restablecer o recuperar HoloLens 2

## Cargar el dispositivo

Antes de iniciar un procedimiento de resolución de problemas, asegúrese de que la carga de la batería de su dispositivo se sitúe entre el 20 y 40% de capacidad, si es posible. Utilice el cargador y los cables USB tipo C que vienen con el dispositivo HoloLens 2. La fuente de alimentación y el cable USB C a C incluidos con el dispositivo son la mejor forma de cargar tu HoloLens 2. El cargador suministra 18W de potencia (9V a 2A). Con el cargador de pared suministrado, los dispositivos HoloLens 2 pueden realizar una carga completa de la batería en menos de 65 minutos cuando el dispositivo está en modo de espera. Si dichos accesorios no están disponibles, asegúrate de que el cargador disponible admita al menos 15 vatios de potencia.

> [!NOTE]
> Si es posible, evite usar un PC para cargar el dispositivo por USB, pues implica una carga lenta.

Si el dispositivo se enciende y funciona correctamente, hay tres formas de comprobar la carga de la batería:

- Desde el menú principal de la interfaz de usuario del dispositivo HoloLens.
- Observe el LED cerca del botón de encendido (si la carga de la batería está al 40%, debería ver al menos dos LED fijos).
    - Cuando se cargue el dispositivo, se iluminará el indicador de la batería para señalar el nivel de carga actual.  La última luz aparecerá y desaparecerá gradualmente para indicar la carga activa.
    - Cuando HoloLens está activado, el indicador de la batería muestra el nivel de la batería en cinco incrementos.
    - Cuando solo está encendida una de las cinco luces, significa que el nivel de batería se encuentra por debajo del 20 por ciento.
    - Si el nivel de la batería es críticamente bajo e intentas activar el dispositivo, una luz parpadeará brevemente y después se apagará.
- En su equipo host, abra el **Explorador de archivos** y busque su dispositivo HoloLens 2 en el lado izquierdo bajo **Este equipo**. Haga clic con el botón secundario en el dispositivo y seleccione **Propiedades**. Un cuadro de diálogo mostrará el nivel de carga de la batería.

   ![La pantalla de propiedades de HoloLens 2 muestra el nivel de cambio en la carga de batería](images/ResetRecovery2.png)

Si el dispositivo no puede arrancar en el menú de inicio, observe la apariencia del LED y la enumeración de dispositivos en el equipo host. A continuación, siga la [guía de solución de problemas](https://docs.microsoft.com/hololens/hololens-troubleshooting). Si el estado del dispositivo no coincide con ninguno de los estados enumerados en la guía de solución de problemas, realice el [procedimiento de restablecimiento completo](hololens-recovery.md#hard-reset-procedure) con el dispositivo conectado a la fuente de alimentación, en lugar de al equipo host. Espere al menos una hora para que el dispositivo se cargue.

## Restablecer el dispositivo

En determinadas circunstancias, puede que tenga que reiniciar manualmente el dispositivo sin utilizar la UI del software.

### Procedimiento estándar

1. Desenchufe el cable de tipo C para desconectar el dispositivo de la fuente de alimentación o del equipo host.

2. Mantenga pulsado el botón **de encendido** durante 15 segundos. Todos los LEDs deberían estar apagados.

3. Espere de 2 a 3 segundos y, a continuación, pulse el botón de **Inicio/Apagado**. Se encenderán los LEDs cercanos al botón de Inicio/Apagado y el dispositivo se iniciará.

4. Conecte el dispositivo al equipo host y, después, abra el Administrador de dispositivos. (Para Windows 10, pulse la tecla **Windows**, luego la tecla**X** y, a continuación, seleccione **Administrador de dispositivos**.) Asegúrese de que el dispositivo se enumera correctamente como *Microsoft HoloLens*, tal y como se muestra en la imagen siguiente:

   ![Administrador de dispositivos HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### Procedimiento para hacer un restablecimiento completo

Si el procedimiento de reinicio estándar no ha funcionado, utilice el procedimiento de restablecimiento completo:

1. Desenchufe el cable de tipo C para desconectar el dispositivo de la fuente de alimentación o del equipo host.

2. Mantenga presionados los botones de **Bajar volumen** + **Inicio/Apagado** durante 15 segundos. El dispositivo se reiniciará automáticamente.

4. Conecte el dispositivo al equipo host.
5. Abra el Administrador de dispositivos (para Windows 10, presione la tecla de **Windows** y, a continuación, la clave **X** y después seleccione **Administrador de dispositivos**). Asegúrese de que el dispositivo se muestre correctamente como *Microsoft HoloLens*, tal y como se muestra en la imagen siguiente:

   ![Administrador de dispositivos 2 HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## Reprogramar el dispositivo

En situaciones extraordinarias, puede que tenga que reprogramar el dispositivo HoloLens 2. Tenga en cuenta que no se espera que restablecer el dispositivo afecte a los siguientes problemas:
- [Mostrar uniformidad de color](hololens2-display.md)
- Arranque con sonido pero sin salida de pantalla
- [Patrón LED 1-3-5](hololens2-setup.md#lights-to-indicate-problems)
- [Sobrecalentamiento](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- Bloqueos del sistema operativo (que son distintos de los bloqueos de la aplicación)

Hay dos formas de reprogramar el dispositivo. En ambos casos, primero debe [instalar el complemento de recuperación avanzada desde la Tienda Windows](https://www.microsoft.com/store/productId/9P74Z35SFRS8).

>[!WARNING]
>Si reprograma el dispositivo, se eliminarán todos los datos personales, las aplicaciones y la configuración, incluida la información para restablecer el TPM.

De forma predeterminada, el Asistente de recuperación avanzada está configurado para descargar la compilación de la versión de características más reciente, consulte aquí para leer nuestras [Notas de la versión](hololens-release-notes.md#) y obtener información sobre la última versión de características. Para obtener el paquete de actualización completa de Flash (FFU) más reciente de HoloLens 2 para formatear el dispositivo a través del Asistente de recuperación avanzada, [haga clic aquí para descargar la última imagen mensual de HoloLens 2](https://aka.ms/hololens2download). Esta versión es la compilación más reciente de la que se dispone de manera general.

Antes de iniciar el procedimiento de reprogramación, asegúrese de que la aplicación esté instalada y en ejecución en su PC con Windows 10 y de que esté lista para detectar el dispositivo. Asegúrate también de que tu HoloLens se cargue al 40 % como mínimo.

![Captura de pantalla de la reprogramación de HoloLens 2](images/ARC1.png)

### Procedimiento normal

1. Mientras el dispositivo HoloLens está en funcionamiento, conéctelo al PC con Windows 10 en el que ha abierto previamente la aplicación Advanced Recovery Companion.
 
   El dispositivo se detectará automáticamente y la interfaz de usuario de la aplicación Advanced Recovery Companion iniciará el proceso de actualización:

   ![Pantalla inicial de la reprogramación de HoloLens 2](images/ARC2.png)

3. Seleccione el dispositivo HoloLens 2 en la interfaz de usuario de la aplicación Advanced Recovery Companion y siga las instrucciones para completar la reprogramación.

### Procedimiento manual

Si el dispositivo HoloLens 2 no se inicia correctamente, puede que tenga que poner el dispositivo en modo de recuperación:

1. Desenchufe el cable de tipo C para desconectar el dispositivo de la fuente de alimentación o del equipo host.

2. Mantenga pulsado el botón **de encendido** durante 15 segundos. Todos los LEDs deberían apagarse.

3. Mientras mantiene pulsado el botón de **Subir volumen**, pulse y suelte el botón **de Inicio/Apagado** para encender el dispositivo. Espere 15 segundos y suelte el botón de **Subir volumen**. De los cinco LED, se encenderá solo el LED del centro.

4. Conecte el dispositivo al equipo host y abra el Administrador de dispositivos. (Para Windows 10, pulse la tecla **Windows**, luego la tecla**X** y, a continuación, seleccione **Administrador de dispositivos**.) Asegúrese de que el dispositivo se enumera correctamente como Microsoft HoloLens, tal y como se muestra en la imagen siguiente:

   ![Recuperación de HoloLens de Windows para HoloLens 2 ](images/MicrosoftHoloLensRecovery.png)

   El dispositivo se detectará automáticamente y la interfaz de usuario de la aplicación Advanced Recovery Companion iniciará el proceso de actualización:

   ![Pantalla de la reprogramación de HoloLens 2](images/ARC2.png)

6. Seleccione el dispositivo HoloLens 2 en la interfaz de usuario de la aplicación Advanced Recovery Companion y, a continuación, siga las instrucciones para completar la reprogramación.

## Descargar ARC sin usar la App Store

Si el entorno de TI impide el uso de la aplicación de la Tienda Windows o limita el acceso a la tienda comercial, el administrador de TI puede hacer que esta aplicación esté disponible a través de una ruta de acceso de implementación "sin conexión".

 >[!NOTE]
 > - Los administradores de TI también pueden distribuir esta aplicación a través de System Center Configuration Manager (SCCM) o Intune.
 > - Esta guía se centra en Advanced Recovery Companion, pero el proceso se puede utilizar también para otras aplicaciones sin conexión.

Siga estos pasos para habilitar la ruta de acceso de implementación:
1. Vaya a la [Microsoft Store para Empresas](https://businessstore.microsoft.com) e inicie sesión con una identidad de Azure Active Directory.

1. Vaya a **Administrar – Configuración**. Active **Mostrar las aplicaciones sin conexión** en la **Experiencia de compra**.
1. Vaya a **tienda para mi grupo** y busque el [**_Asistente de recuperación avanzada_*_](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).
1. Cambie el _*Tipo de licencia** a **_sin conexión_*_ y seleccione _*Administrar**.
1. En **Descargar el paquete para uso sin conexión**, seleccione el segundo botón azul de **Descargar**. Asegúrese de que la extensión del archivo sea *.appxbundle*.

    - En esta etapa, si el PC de escritorio tiene acceso a Internet, haz doble clic en el paquete para instalar la aplicación.

    - Si el PC de destino no tiene conectividad a Internet, sigue estos pasos:
       1. Selecciona la licencia sin codificar y, a continuación, selecciona **Generar licencia**.
       2. En **Marcos necesarios**, seleccione **Descargar**.
       3. Use DISM para aplicar el paquete con la dependencia y la licencia. Desde un símbolo del sistema de administrador, ejecute el siguiente comando:

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > El número de versión en este ejemplo de código puede no coincidir con la versión disponible actualmente. También puede que haya elegido una ubicación de descarga diferente a la del ejemplo. Realice los cambios necesarios en el comando.

> [!TIP]
> Cuando planee usar Advanced Recovery Companion para instalar una FFU sin conexión, puede que resulte útil descargar la imagen flash. [**Descargar la imagen actual para HoloLens 2**](https://aka.ms/hololens2download).

Otros recursos:
- [Distribuir aplicaciones sin conexión](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [Opciones de línea de comandos de servicio de paquete de aplicación DISM (.appx or .appxbundle)](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
