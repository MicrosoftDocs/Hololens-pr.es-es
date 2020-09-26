---
title: 'Escenarios comunes: HoloLens con conexión segura 2'
description: Implementación segura y de aplicaciones sin conexión a través del aprovisionamiento.
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
ms.openlocfilehash: d53f9ce19b020a866770b756dde6ab97b8331362
ms.sourcegitcommit: e6885d03c980b33dd0bab5c418cbd1892d5ff123
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "11080538"
---
# Escenarios comunes: HoloLens con conexión segura 2

## Introducción
Esta guía proporciona una guía para aplicar un paquete de aprovisionamiento de ejemplo que bloqueará una HoloLens 2 para su uso en entornos seguros con las siguientes restricciones:
-   Deshabilitar WiFi.
-   Deshabilitar BlueTooth.
-   Deshabilitar micrófonos.
-   Impide agregar o quitar paquetes de aprovisionamiento.
-   Ningún usuario puede habilitar ninguno de los componentes restringidos mencionados anteriormente.

## Preparar 
Configuración de Windows 10 PC
1. [Descarga el archivo de sistema operativo HoloLens 2 más reciente](https://aka.ms/hololens2download) directamente en tu PC. 
   1. La compatibilidad con esta configuración está incluida en la compilación 19041,1117 y versiones posteriores.
1. Descargar e instalar la herramienta de asistente de recuperación avanzada (ARC) [de Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) en su PC
1. Descargue e instale la herramienta [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) más reciente de Microsoft Store en su PC.
1. [Descargue la carpeta OfflineSecureHL2_Sample con los archivos de proyecto](https://aka.ms/HoloLensDocs-SecureOfflineSample) para generar el PPKG.
1. Prepare la [aplicación de línea de negocio sin conexión para la implementación de PPKG](app-deploy-provisioning-package.md). 


## Configurar
Crear un paquete de aprovisionamiento de configuración segura

1. Inicia la herramienta WCD en tu PC.
1. Seleccione **archivo-> abrir proyecto**.
  1. Vaya a la ubicación de la carpeta OfflineSecureHL2_Sample guardada anteriormente y seleccione: OfflineSecureHL2_Sample.icdproj.xml
1. El proyecto debe abrirse y ahora debe tener una lista de personalizaciones disponibles: 

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla del paquete de configuración abierto en WCD](images/offline-secure-sample-wcd.png)

Configuraciones definidas en este paquete de aprovisionamiento:

|     Elemento                                                |     Configuración                       |     Descripción                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     Cuentas/usuarios                                    |     Nombre de usuario local & contraseña    |     Para estos dispositivos sin conexión, todos los usuarios del dispositivo tendrán que establecer y compartir un solo nombre de usuario y contraseña.          |
|     Primera experiencia/HoloLens/SkipCalibration       |     Verdadero                          |     Omite la calibración durante la configuración del dispositivo inicial solamente                                                                             |
|     Primera experiencia/HoloLens/SkipTraining          |     Verdadero                          |     Omite la formación de dispositivos durante la configuración del dispositivo inicial                                                                              |
|     Primera experiencia/HoloLens/WiFi                  |     Verdadero                          |     Omite la configuración de Wi-Fi durante la configuración del dispositivo inicial                                                                                 |
|     Directivas/conectividad/AllowBluetooth                |     No                            |     Deshabilita Bluetooth                                                                                                             |
|     Directivas/experiencia/AllowCortana                    |     No                            |     Deshabilita Cortana (para eliminar posibles problemas, ya que los micrófonos están deshabilitados)                                          |
|     Directivas/MixedReality/MicrophoneDisabled            |     Sí                           |     Deshabilita el micrófono                                                                                                            |
|     Directivas/privacidad/LetAppsAccessLocation              |     Forzar denegación                    |     Impide que las aplicaciones intenten obtener acceso a los datos de la ubicación (para eliminar posibles problemas porque el seguimiento de ubicación está deshabilitado)    |
|     Directivas/privacidad/LetAppsAccessMicrophone            |     Forzar denegación                    |     Impide que las aplicaciones intenten acceder a micrófonos (para eliminar posibles problemas, ya que los micrófonos están deshabilitados)           |
|     Directivas/seguridad/AllowAddProvisioningPackage       |     No                            |     Impide que cualquier persona agregue paquetes de aprovisionamiento que puedan intentar suplantar las directivas de bloqueo.                         |
|     Directivas/seguridad/AllowRemoveProvisioningPackage    |     No                            |     Impide que cualquier persona quite este paquete de aprovisionamiento bloqueado.                                                           |
|     Directivas/sistema/AllowLocation                       |     No                            |     Impide que el dispositivo intente realizar un seguimiento de los datos de ubicación.                                                                        |
|     Directivas/WiFi/AllowWiFi                             |     No                            |     Deshabilita Wi-Fi                                                                                                                 |

4. En Runtime Settings, seleccione **accounts/Users/username: holo/password** 
    - Anote la contraseña y reinicie si lo desea.
5. Vaya a UniversalAppInstall/UserContextApp y [Configure la aplicación LOB](app-deploy-provisioning-package.md) que va a implementar en estos dispositivos.

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla de dónde agregar la aplicación en WCD.](images/offline-secure-sample-wcd-usercontextapp.png)

6. Una vez completado, seleccione el botón "exportar" y siga todas las indicaciones hasta que se cree el paquete de aprovisionamiento.

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla del botón exportar para este paquete en WCD.](images/offline-secure-sample-wcd-export.png)


## Implementar
1. Conecta el HL2 a tu PC con Windows 10 a través del cable USB.
1. Inicia la herramienta ARC y selecciona **HoloLens 2**

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. En la siguiente pantalla, seleccione **selección de paquetes manual**.
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. Vaya al archivo. FFU descargado anteriormente y seleccione **abrir**.
1. En la página de advertencia, seleccione **continuar**.

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. Espera a que la herramienta de arco complete la instalación del sistema operativo HoloLens 2.
1. Una vez que el dispositivo complete la instalación y arranque de nuevo, desde su PC, navegue hasta el explorador de archivos y copie el archivo PPKG guardado anteriormente en la carpeta del dispositivo.

   > [!div class="mx-imgBorder"]
   > ![PPKG archivo en equipo en la ventana del explorador de archivos.](images/offline-secure-file-explorer.png)

1. En la HoloLens 2, pulse el siguiente cuadro combinado de botones para ejecutar el paquete de aprovisionamiento: Pulse **volumen bajo** y **botón de encendido** al mismo tiempo.
1. Se le pedirá que aplique el paquete de aprovisionamiento, seleccione confirm ( **confirmar** ).
1. Una vez completado el paquete de aprovisionamiento, seleccione **Aceptar**.
1. Se le pedirá que inicie sesión en el dispositivo con la cuenta local y la contraseña compartidas.

## Mantener
Con esta configuración, se recomienda reiniciar el proceso anterior y volver a crear un flash del dispositivo con la herramienta ARC y aplicar una nueva PPKG para hacer actualizaciones en el sistema operativo o en las aplicaciones. 

