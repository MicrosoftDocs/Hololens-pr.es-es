---
title: 'Escenarios comunes: seguridad sin conexión HoloLens 2'
description: Aprenda a configurar un escenario de implementación segura sin conexión y de implementación de aplicaciones con aprovisionamiento para dispositivos HoloLens.
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
ms.openlocfilehash: 7eb084d3de222581fd2b97eaa1c1e2812310810c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309128"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>Escenarios comunes: seguridad sin conexión HoloLens 2

## <a name="overview"></a>Introducción

En esta guía se proporcionan instrucciones para aplicar un paquete de aprovisionamiento de ejemplo que bloqueará un HoloLens 2 para su uso en entornos seguros con las restricciones siguientes:

-   Deshabilite wi-fi.
-   Deshabilite BlueTooth.
-   Deshabilite micrófonos.
-   Impide agregar o quitar paquetes de aprovisionamiento.
-   Ningún usuario puede habilitar ninguno de los componentes restringidos anteriores.

## <a name="prepare"></a>Preparación

Windows 10 configuración de PC
1. [Descargue el archivo HoloLens 2 sistema operativo más](https://aka.ms/hololens2download) reciente directamente en un equipo. 
   1. La compatibilidad con esta configuración se incluye en la compilación 19041.1117 y posteriores.
1. Descargar o instalar la herramienta Advanced Recovery Companion(ARC) [desde el Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) al equipo
1. Descargue o instale la herramienta [del Diseñador de configuración de Windows (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) más reciente Microsoft Store en el equipo.
1. [Descargue la OfflineSecureHL2_Sample con los archivos del proyecto para](https://aka.ms/HoloLensDocs-SecureOfflineSample) compilar el PPKG.
1. Prepare la aplicación [de línea de negocio sin conexión para la implementación de PPKG.](app-deploy-provisioning-package.md) 


## <a name="configure"></a>Configuración

Compilación de un paquete de aprovisionamiento de configuración segura

1. Inicie la herramienta WCD en el equipo.
1. Seleccione **Archivo -> Abrir proyecto**.
  1. Vaya a la ubicación de la carpeta guardada OfflineSecureHL2_Sample y seleccione: OfflineSecureHL2_Sample.icdproj.xml
1. El proyecto debe abrirse y ahora debería tener una lista de personalizaciones disponibles:

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla del paquete de configuración abierto en WCD](images/offline-secure-sample-wcd.png)

   Configuraciones establecidas en este paquete de aprovisionamiento:
   
   |     Elemento                                                |     Parámetro                       |     Descripción                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Cuentas y usuarios                                    |     Nombre de usuario local & contraseña    |     Para estos dispositivos sin conexión, todos los usuarios del dispositivo tendrán que establecer y compartir un único nombre de usuario y contraseña.          |
   |     Primera experiencia/HoloLens/Skip Holobration       |     Verdadero                          |     Omite la calibración solo durante la configuración inicial del dispositivo.                                                                             |
   |     Primera experiencia/HoloLens/SkipTraining          |     Verdadero                          |     Omite el entrenamiento del dispositivo durante la configuración inicial del dispositivo.                                                                              |
   |     Primera experiencia/HoloLens/Wi-Fi                  |     Verdadero                          |     Omite la Wi-Fi durante la configuración inicial del dispositivo.                                                                                 |
   |     Directivas/Conectividad/AllowBluetooth                |     No                            |     Deshabilita Bluetooth                                                                                                             |
   |     Directivas/Experiencia/AllowCortana                    |     No                            |     Deshabilita Cortana (para eliminar posibles problemas, ya que los micrófonos están deshabilitados)                                          |
   |     Policies/MixedReality/MicrophoneDisabled            |     Yes                           |     Deshabilita el micrófono                                                                                                            |
   |     Policies/Privacy/LetAppsAccessLocation              |     Forzar denegación                    |     Impide que las aplicaciones intenten acceder a los datos de ubicación (para eliminar posibles problemas, ya que el seguimiento de ubicación está deshabilitado)    |
   |     Directivas/Privacidad/LetAppsAccessMicrophone            |     Forzar denegación                    |     Impide que las aplicaciones intenten acceder a los micrófonos (para eliminar posibles problemas, ya que los micrófonos están deshabilitados)           |
   |     Policies/Security/AllowAddProvisioningPackage       |     No                            |     Impide que alguien agregue paquetes de aprovisionamiento que puedan intentar invalidar las directivas bloqueadas.                         |
   |     Policies/Security/AllowRemoveProvisioningPackage    |     No                            |     Impide que alguien quite este paquete de aprovisionamiento bloqueado.                                                           |
   |     Policies/System/AllowLocation                       |     No                            |     Impide que el dispositivo intente realizar un seguimiento de los datos de ubicación.                                                                        |
   |     Directivas/Wi-Fi/AllowWiFi                             |     No                            |     Deshabilita Wi-Fi                                                                                                                 |

1. En Configuración del entorno de ejecución, **seleccione Cuentas/Usuarios/NombreDeUsuario: Holo/Contraseña.**

   Anote la contraseña y restablezca si lo desea.

1. Vaya a UniversalAppInstall /UserContextApp y configure la aplicación [LOB](app-deploy-provisioning-package.md) que va a implementar en estos dispositivos.

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla de dónde agregar la aplicación en WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. Una vez completado, seleccione el botón "Exportar" y siga todas las indicaciones hasta que se cree el paquete de aprovisionamiento.

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla del botón Exportar para este paquete en WCD.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Implementar

1. Conecte hl2 al equipo Windows 10 a través de un cable USB.
1. Inicie la herramienta ARC y seleccione **HoloLens 2**

   ![HoloLens 2 pantalla inicial de reflash limpia](images/ARC2.png)

1. En la siguiente pantalla, seleccione **Selección manual del paquete.**

   ![HoloLens 2 de información de ARC](images/arc_device_info.png)

1. Vaya al archivo .ffu descargado anteriormente y seleccione **Abrir.**
1. En la página Advertencia, seleccione **Continuar.**

   ![HoloLens 2 de advertencia de ARC](images/arc_warning.png)

1. Espere a que la herramienta ARC complete la instalación HoloLens 2 sistema operativo.
1. Una vez que el dispositivo complete la instalación y arranque la copia de seguridad, desde el equipo vaya a Explorador de archivos y copie el archivo PPKG guardado anteriormente en la carpeta del dispositivo.

   > [!div class="mx-imgBorder"]
   > ![Archivo PPKG en pc en Explorador de archivos ventana.](images/offline-secure-file-explorer.png)

1. En la HoloLens 2, presione el siguiente botón combinado para ejecutar el paquete de aprovisionamiento: **Pulse** Bajar volumen y **Botón** de encendido al mismo tiempo.
1. Se le pedirá que aplique el paquete de aprovisionamiento y seleccione **Confirmar.**
1. Una vez completado el paquete de aprovisionamiento, seleccione **Aceptar.**
1. A continuación, se le pedirá que inicie sesión en el dispositivo con la cuenta local y la contraseña compartidas.

## <a name="maintain"></a>Mantenimiento

Con esta configuración, se recomienda reiniciar el proceso anterior y volver a actualizar el dispositivo con la herramienta ARC y aplicar un nuevo PPKG para realizar cualquier actualización del sistema operativo o las aplicaciones.
