---
title: Reiniciar, restablecer o recuperar HoloLens
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
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
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5da7f954454b5713823c5aa94742f9c9c0033ca2
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828596"
---
# Reseteo y recuperación para el HoloLens 2

## Cargando el dispositivo

Antes de iniciar cualquier procedimiento de resolución de problemas, si es posible, asegúrese de que su dispositivo tiene una carga de por lo menos entre el 20% y el 40%.

Por favor, asegúrese de que está utilizando el cargador y los cables USB tipo C que vienen con el dispositivo HoloLens2. En caso de que no esté disponible, asegúrese de que el cargador disponible pueda soportar al menos 15W de potencia.

> [!NOTE]
> Si es posible, no utilice un PC para cargar el dispositivo a través de USB ya que esto proporcionará una carga muy lenta.

Si el dispositivo se enciende y funciona correctamente, hay tres formas diferentes de comprobar la carga de la batería.

1. Desde el menú principal de la interfaz del dispositivo HoloLens.
2. Usando el LED cerca del botón de encendido (para el 40% debería ver al menos dos LEDs sólidos).
3. En su equipo host abra la ventana del Explorador de archivos y busque su dispositivo HoloLens 2 en el lado izquierdo bajo "Esta PC".
    
      a. Haga clic con el botón derecho del ratón en el nombre del dispositivo y seleccione las propiedades. Aparecerá un diálogo que muestra el nivel de la batería de su dispositivo.

![Recuperación de restablecimiento de HoloLens 2](images/ResetRecovery2.png)

Si no se puede iniciar el dispositivo en el menú de inicio, tome nota de los LED y la enumeración en el equipo host y siga la guía de solución de problemas (https://docs.microsoft.com/hololens/hololens-troubleshooting). En caso de que el estado del dispositivo no se encuentre en ninguno de los estados enumerados en la guía de solución de problemas, ejecute el** procedimiento de restablecimiento completo** sin volver a conectar el dispositivo a su equipo host, sino que lo conecte a la fuente de alimentación Espere al menos una hora para que el dispositivo se cargue.

## Restablecer el dispositivo

En determinadas circunstancias, el cliente puede verse obligado a reiniciar manualmente el dispositivo sin utilizar el SW UI. 

### Procedimiento estándar
1. Desconecte el dispositivo de la fuente de alimentación o del equipo host desenchufando el cable de tipo C.

2. Mantenga pulsado el **botón de encendido** durante 15 segundos. Todos los LEDs deberían estar apagados.

3. Espere 2-3 segundos y presione brevemente el **botón de encendido**, los LEDs cercanos al botón de encendido se encenderán y el dispositivo comenzará a arrancar. 

4. Conecte el dispositivo al equipo host, abra el Administrador de dispositivos (para Windows 10 pulse la tecla **"Windows"** y luego la tecla **"x"** y haga clic en "Administrador de dispositivos") y asegúrese de que el dispositivo se enumera correctamente como HoloLente de Microsoft como se muestra en las siguientes imágenes:

![Recuperación de HoloLens de Windows para HoloLens 2 ](images/MicrosoftHoloLensRecovery.png)

### Procedimiento para hacer un restablecimiento completo

Si el procedimiento de reinicio estándar no funciona, puede utilizar el procedimiento de restablecimiento completo.

1. Desconecte el dispositivo de la fuente de alimentación o del equipo host desenchufando el cable de tipo C.

2. Mantenga presionado el botón de** volumen + el botón de encendido ** durante 15 segundos.

3. El dispositivo se reiniciará automáticamente. 

4. Conecte el dispositivo a el equipo host, abra el Administrador de dispositivos (para Windows 10 pulse la tecla **"Windows"** y luego la tecla **"x"** y haga clic en "Administrador de dispositivos") y asegúrese de que el dispositivo se enumera correctamente como HoloLens de Microsoft como se muestra en las siguientes imágenes.

![Recuperación de HoloLens de Windows para HoloLens 2 ](images/MicrosoftHoloLens_DeviceManager.png)

## Formatear el dispositivo

En situaciones extraordinarias se le puede pedir que formatee el dispositivo. Hay dos formas de formatear un dispositivo HoloLens2. Para todos los procedimientos de formateo se le pedirá que[instale la aplicación Advanced Recovery Companion de la Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8). Si restablece el dispositivo, se borrarán todos sus datos personales, aplicaciones y configuraciones, incluido el restablecimiento del TPM.

Advanced Recovery Companion está actualmente programado para descargar la versión de la función para[Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004), si desea descargar la última HoloLens 2 FFU para formatear su dispositivo a través de Advanced Recovery Companion, puede descargarla desde[aquí](https://aka.ms/hololens2download). Esto se mantiene actualizado y coincidirá con la última construcción generalmente disponible. 

Antes de iniciar el procedimiento de flasheo, asegúrese de que la aplicación esté instalada y funcionando en su PC con Windows 10 y que esté lista para detectar el dispositivo.

![Formateo de HoloLens 2](images/ARC1.png)

### Procedimiento normal

1. Mientras el dispositivo HoloLens está funcionando, conéctelo a su PC con Windows 10 donde previamente inició la aplicación Advanced Recovery Companion.

2. El dispositivo se detectará automáticamente y la interfaz de la aplicación Advanced Recovery Companion se actualizará de la siguiente manera:

![Formateo de HoloLens 2](images/ARC2.png)

3. Seleccione el dispositivo HoloLens2 en la interfaz de la aplicación Advanced Recovery Companion y siga las instrucciones para completar el flasheo.

### Procedimiento manual

Si el dispositivo no inicia correctamente, es posible que tenga que poner el dispositivo HoloLens 2 en modo de recuperación.

1. Desconecte el dispositivo de la fuente de alimentación o del equipo host desenchufando el cable de tipo C. 

2. Mantenga pulsado el **botón de encendido** durante 15 segundos. Todos los LEDs deberían apagarse. 

3. Mientras se pulsa el botón de**subir el volumen**, pulse y suelte el**botón de encendido** para encender el dispositivo. Espere 15 segundos antes de soltar el botón de subir el volumen. De los 5 LEDs del dispositivo, sólo se encenderá el LED del medio.

4. Conecte el dispositivo al equipo host, abra el Administrador de dispositivos (para Windows 10 pulse la tecla **"Windows"** y luego la tecla **"x"** y haga clic en "Administrador de dispositivos") y asegúrese de que el dispositivo se enumera correctamente como HoloLente de Microsoft como se muestra en la imagen de abajo.

![Recuperación de HoloLens de Windows para HoloLens 2 ](images/MicrosoftHoloLensRecovery.png)

5. El dispositivo se detectará automáticamente y la interfaz de la aplicación Advanced Recovery Companion se actualizará de la siguiente manera:

![Formateo de HoloLens 2](images/ARC2.png)

6. Seleccione el dispositivo HoloLens 2 en la interfaz de la aplicación Advanced Recovery Companion y siga las instrucciones para completar el flasheo.

## Descargar ARC sin usar la tienda de aplicaciones

Si un entorno de TI impide el uso de la aplicación Windows Store o limita el acceso a la tienda minorista, los administradores de TI pueden hacer que esta aplicación esté disponible a través de otras vías de despliegue "fuera de línea". 

- Este proceso también puede utilizarse para otras aplicaciones, como se ha visto en el paso 2. Esta guía se centrará en Advanced Recovery Companion, pero puede ser modificada para otras aplicaciones fuera de línea.  

Esta ruta de despliegue puede habilitarse con los siguientes pasos:
1.  Diríjase al [sitio web de la tienda para empresas](https://businessstore.microsoft.com)e inicie sesión con una identidad de Azure AD.
1.  Diríjase a **Administrar - Configuración**, y active **Mostrar aplicaciones fuera de línea** en**Experiencia de compra**como se describe enhttps://businessstore.microsoft.com/manage/settings/shop 
1.  Diríjase a la**tienda de mi grupo**y busque la aplicación[Advanced Recovery Companion](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).
1.  Cambie el cuadro de **Tipo de licencia**a fuera de línea y haga clic en **Administrar**.
1.  En Descargar el paquete para uso fuera de línea, haga clic en el segundo botón azul **"Descargar"**. Asegúrese de que la extensión del archivo sea .appxbundle.
1.  En esta etapa, si la PC de escritorio tiene acceso a Internet, simplemente haga doble clic e instale. 
1.  El administrador de TI también puede distribuir esta aplicación a través de System Center Configuration Manager (SCCM) o Intune.
1.  Si el ordenador objetivo no tiene conexión a Internet, se necesitan algunos pasos adicionales: 
    1.  Seleccione la licencia no codificada y haga clic en **"Generar licencia"** y en **"Marcos necesarios"** haga clic en **"Descargar."**  
    1.  Los ordenadores sin acceso a Internet tendrán que usar DISM para aplicar el paquete con la dependencia y la licencia. En un símbolo de comando de administrador, escriba:

      ```console
      C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
      ```
> [!NOTE]
> El número de versión en este ejemplo de código puede no coincidir con la versión disponible actualmente. También puede haber elegido una ubicación de descarga diferente a la del ejemplo dado. Asegúrese de hacer los cambios necesarios.

> [!TIP]
> Cuando se planea usar Advanced Recovery Companion para instalar un ffu fuera de línea puede ser útil descargar su imagen intermitente para estar disponible, aquí está la[imagen actual para HoloLens 2](https://aka.ms/hololens2download). 

Otros recursos:
- https://docs.microsoft.com/microsoft-store/distribute-offline-apps 
- https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options


