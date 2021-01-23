---
title: 'Escenarios comunes: HoloLens seguro sin conexión 2'
description: Aprende a configurar un escenario de implementación segura sin conexión y de implementación de aplicaciones con aprovisionamiento para dispositivos HoloLens.
keywords: HoloLens, administración, sin conexión, seguro sin conexión
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 03003995f1e63708652955e6217e506d53555c1b
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283421"
---
# Escenarios comunes: HoloLens seguro sin conexión 2

## Introducción

En esta guía se proporcionan instrucciones para aplicar un paquete de aprovisionamiento de muestra que bloqueará un HoloLens 2 para su uso en entornos seguros con las siguientes restricciones:
-   Deshabilita wi-fi.
-   Deshabilita BlueTooth.
-   Deshabilite los micrófonos.
-   Impide agregar o quitar paquetes de aprovisionamiento.
-   Ningún usuario puede habilitar ninguno de los componentes restringidos anteriores.

## Preparar

Configuración del equipo con Windows 10
1. [Descarga el archivo del sistema operativo HoloLens 2](https://aka.ms/hololens2download) más reciente directamente en un equipo. 
   1. La compatibilidad con esta configuración se incluye en la compilación 19041.1117 y posteriores.
1. Descargar e instalar la herramienta Advanced Recovery Companion(ARC) [de Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) en tu PC
1. Descarga e instala la herramienta más reciente del Diseñador de configuraciones [de Windows (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) de Microsoft Store en tu PC.
1. [Descarga la OfflineSecureHL2_Sample carpeta con los archivos del proyecto](https://aka.ms/HoloLensDocs-SecureOfflineSample) para compilar el PPKG.
1. Preparar la aplicación [de línea de negocio sin conexión para la implementación de PPKG.](app-deploy-provisioning-package.md) 


## Configurar

Crear un paquete de aprovisionamiento de configuración segura

1. Inicia la herramienta WCD en el equipo.
1. Seleccione **Archivo -> Abrir proyecto**.
  1. Vaya a la ubicación de la carpeta OfflineSecureHL2_Sample guardada anteriormente y seleccione: OfflineSecureHL2_Sample.icdproj.xml
1. El proyecto debe abrirse y ahora debería tener una lista de personalizaciones disponibles: 

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla del paquete de configuración abierto en WCD](images/offline-secure-sample-wcd.png)

Configuraciones establecidas en este paquete de aprovisionamiento:

|     Elemento                                                |     Configuración                       |     Descripción                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     Cuentas o usuarios                                    |     Nombre de usuario local & contraseña    |     Para estos dispositivos sin conexión, todos los usuarios del dispositivo tendrán que establecer y compartir un solo nombre de usuario y contraseña.          |
|     Primera experiencia / HoloLens / SkipCalibration       |     Verdadero                          |     Omite la calibración solo durante la configuración inicial del dispositivo                                                                             |
|     Primera experiencia / HoloLens / SkipTraining          |     Verdadero                          |     Omite el aprendizaje del dispositivo durante la configuración inicial del dispositivo                                                                              |
|     Primera experiencia / HoloLens / WiFi                  |     Verdadero                          |     Omite la configuración Wi-Fi durante la configuración inicial del dispositivo                                                                                 |
|     Directivas/Conectividad/AllowBluetooth                |     No                            |     Deshabilita Bluetooth                                                                                                             |
|     Directivas/Experiencia/AllowCortana                    |     No                            |     Deshabilita Cortana (para eliminar posibles problemas ya que los micrófonos están deshabilitados)                                          |
|     Directivas/Realidad mixta/MicrophoneDisabled            |     Sí                           |     Deshabilita el micrófono                                                                                                            |
|     Directivas/Privacidad/LetAppsAccessLocation              |     Forzar denegación                    |     Impide que las aplicaciones intenten acceder a los datos de ubicación (para eliminar posibles problemas ya que el seguimiento de ubicación está deshabilitado)    |
|     Directivas/Privacidad/LetAppsAccessMicrophone            |     Forzar denegación                    |     Impide que las aplicaciones intenten acceder a los micrófonos (para eliminar posibles problemas ya que los micrófonos están deshabilitados)           |
|     Directivas/Seguridad/AllowAddProvisioningPackage       |     No                            |     Impide que cualquier usuario agregue paquetes de aprovisionamiento que puedan intentar invalidar directivas bloqueadas.                         |
|     Directivas/Seguridad/AllowRemoveProvisioningPackage    |     No                            |     Impide que nadie quite este paquete de aprovisionamiento bloqueado.                                                           |
|     Directivas/Sistema/AllowLocation                       |     No                            |     Impide que el dispositivo intente realizar un seguimiento de los datos de ubicación.                                                                        |
|     Directivas/WiFi/AllowWiFi                             |     No                            |     Deshabilita Wi-Fi                                                                                                                 |

4. En Configuración de tiempo de ejecución, seleccione **Cuentas / Usuarios / Nombre de usuario: Holo / Contraseña** 
    - Anote la contraseña y restablezca si lo desea.
5. Ve a UniversalAppInstall /UserContextApp y configura la aplicación [lob](app-deploy-provisioning-package.md) que vas a implementar en estos dispositivos.

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla de dónde agregar la aplicación en WCD.](images/offline-secure-sample-wcd-usercontextapp.png)

6. Una vez completado, selecciona el botón "Exportar" y sigue todas las indicaciones hasta que se cree el paquete de aprovisionamiento.

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla del botón Exportar para este paquete en WCD.](images/offline-secure-sample-wcd-export.png)


## Implementar

1. Conecta HL2 a tu PC con Windows 10 a través de un cable USB.
1. Iniciar la herramienta ARC y seleccionar **HoloLens 2**

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. En la siguiente pantalla, seleccione **Selección de paquete manual.**
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. Vaya al archivo .ffu descargado anteriormente y seleccione **Abrir**.
1. En la página Advertencia, **seleccione Continuar**.

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. Espere a que la herramienta ARC complete la instalación del sistema operativo HoloLens 2.
1. Una vez que el dispositivo completa la instalación y arranca la copia de seguridad, desde el equipo ve al Explorador de archivos y copia el archivo PPKG guardado anteriormente en la carpeta del dispositivo.

   > [!div class="mx-imgBorder"]
   > ![Archivo PPKG en el equipo en la ventana del Explorador de archivos.](images/offline-secure-file-explorer.png)

1. En HoloLens 2, presione la combinación de botones **** siguiente para ejecutar el paquete de aprovisionamiento: pulse bajar volumen y botón de **encendido** al mismo tiempo.
1. Se te pedirá que apliques el paquete de aprovisionamiento, selecciona **Confirmar**
1. Una vez completado el paquete de aprovisionamiento, selecciona **Aceptar.**
1. A continuación, se te pedirá que inicies sesión en el dispositivo con la cuenta local compartida y la contraseña.

## Mantener

Con esta configuración, se recomienda reiniciar el proceso anterior y volver a actualizar el dispositivo con la herramienta ARC y aplicar un nuevo PPKG para realizar cualquier actualización al sistema operativo o a las aplicaciones. 

