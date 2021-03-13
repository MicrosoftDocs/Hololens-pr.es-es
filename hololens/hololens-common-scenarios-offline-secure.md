---
title: 'Escenarios comunes: HoloLens 2 seguro sin conexión'
description: Aprende a configurar un escenario de implementación segura sin conexión e implementación de aplicaciones con aprovisionamiento para dispositivos HoloLens.
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
ms.sourcegitcommit: 04b7e789fe69615a60571b769e13a01a9d7aee70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "11407602"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>Escenarios comunes: HoloLens 2 seguro sin conexión

## <a name="overview"></a>Información general

Esta guía proporciona instrucciones para aplicar un paquete de aprovisionamiento de ejemplo que bloqueará un HoloLens 2 para su uso en entornos seguros con las siguientes restricciones:

-   Deshabilite WiFi.
-   Deshabilitar BlueTooth.
-   Deshabilitar micrófonos.
-   Impide agregar o quitar paquetes de aprovisionamiento.
-   Ningún usuario puede habilitar ninguno de los componentes restringidos anteriores.

## <a name="prepare"></a>Preparar

Instalación del equipo con Windows 10
1. [Descargue el archivo del sistema operativo HoloLens 2 más](https://aka.ms/hololens2download) reciente directamente en un equipo. 
   1. La compatibilidad con esta configuración se incluye en la compilación 19041.1117 y posteriores.
1. Descargar e instalar la herramienta Advanced Recovery Companion(ARC) [de Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) en tu PC
1. Descargue o instale la herramienta más reciente del Diseñador de configuraciones [de Windows (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) de Microsoft Store en su PC.
1. [Descargue la OfflineSecureHL2_Sample con los archivos del proyecto](https://aka.ms/HoloLensDocs-SecureOfflineSample) para crear el PPKG.
1. Preparar la aplicación [línea de negocio sin conexión para la implementación de PPKG](app-deploy-provisioning-package.md). 


## <a name="configure"></a>Configurar

Crear un paquete de aprovisionamiento de configuración segura

1. Inicie la herramienta WCD en su PC.
1. Seleccione **Archivo -> Abrir proyecto**.
  1. Desplácese hasta la ubicación de la carpeta OfflineSecureHL2_Sample y seleccione: OfflineSecureHL2_Sample.icdproj.xml
1. El proyecto debe abrirse y ahora debería tener una lista de personalizaciones disponibles:

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla del paquete de configuración abierto en WCD](images/offline-secure-sample-wcd.png)

   Configuraciones establecidas en este paquete de aprovisionamiento:
   
   |     Elemento                                                |     Configuración                       |     Descripción                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Cuentas /Usuarios                                    |     Contraseña de nombre de & local    |     Para estos dispositivos sin conexión, todos los usuarios del dispositivo tendrán que establecer y compartir un solo nombre de usuario y contraseña.          |
   |     First Experience / HoloLens / SkipCalibration       |     Verdadero                          |     Omite la calibración solo durante la configuración inicial del dispositivo                                                                             |
   |     First Experience / HoloLens / SkipTraining          |     Verdadero                          |     Omite el aprendizaje del dispositivo durante la configuración inicial del dispositivo                                                                              |
   |     Primera experiencia / HoloLens / WiFi                  |     Verdadero                          |     Omite Wi-Fi configuración durante la configuración inicial del dispositivo                                                                                 |
   |     Directivas/Conectividad/AllowBluetooth                |     No                            |     Deshabilita Bluetooth                                                                                                             |
   |     Directivas/Experiencia/AllowCortana                    |     No                            |     Deshabilita Cortana (para eliminar posibles problemas ya que los micrófonos están deshabilitados)                                          |
   |     Directivas/Realidad mixta/MicrophoneDisabled            |     Sí                           |     Deshabilita micrófono                                                                                                            |
   |     Directivas/Privacidad/LetAppsAccessLocation              |     Forzar denegación                    |     Impide que las aplicaciones intenten acceder a los datos de ubicación (para eliminar posibles problemas ya que el seguimiento de ubicación está deshabilitado)    |
   |     Directivas/Privacidad/LetAppsAccessMicrophone            |     Forzar denegación                    |     Impide que las aplicaciones intenten acceder a micrófonos (para eliminar posibles problemas ya que los micrófonos están deshabilitados)           |
   |     Policies/Security/AllowAddProvisioningPackage       |     No                            |     Impide que cualquier usuario agregue paquetes de aprovisionamiento que puedan intentar invalidar directivas bloqueadas.                         |
   |     Policies/Security/AllowRemoveProvisioningPackage    |     No                            |     Impide que alguien quite este paquete de aprovisionamiento bloqueado.                                                           |
   |     Directivas/Sistema/AllowLocation                       |     No                            |     Impide que el dispositivo intente realizar un seguimiento de los datos de ubicación.                                                                        |
   |     Directivas/WiFi/AllowWiFi                             |     No                            |     Deshabilita Wi-Fi                                                                                                                 |

1. En Configuración del tiempo de ejecución, seleccione **Cuentas / Usuarios / UserName: Holo / Password**.

   Anote la contraseña y restablezca si lo desea.

1. Vaya a UniversalAppInstall / UserContextApp y configure la aplicación [lob](app-deploy-provisioning-package.md) que va a implementar en estos dispositivos.

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla de dónde agregar la aplicación en WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. Una vez completado, selecciona el botón "Exportar" y sigue todos los mensajes hasta que se cree el paquete de aprovisionamiento.

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla del botón Exportar para este paquete en WCD.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Implementar

1. Conecta el HL2 a tu PC con Windows 10 a través de un cable USB.
1. Iniciar la herramienta ARC y seleccionar **HoloLens 2**

   ![Pantalla inicial de la reprogramación de HoloLens 2](images/ARC2.png)

1. En la siguiente pantalla, seleccione **Selección manual del paquete**.

   ![Pantalla de información de HOLOLens 2 ARC](images/arc_device_info.png)

1. Vaya al archivo .ffu descargado anteriormente y seleccione **Abrir**.
1. En la página Advertencia, **seleccione Continuar**.

   ![Pantalla de advertencia de HOLOLens 2 ARC](images/arc_warning.png)

1. Espere a que la herramienta ARC complete la instalación del sistema operativo HoloLens 2.
1. Una vez que el dispositivo complete la instalación y se inicie la copia de seguridad, desde el equipo vaya al Explorador de archivos y copie el archivo PPKG guardado anteriormente en la carpeta del dispositivo.

   > [!div class="mx-imgBorder"]
   > ![Archivo PPKG en pc en la ventana Explorador de archivos.](images/offline-secure-file-explorer.png)

1. En HoloLens 2, presione el siguiente botón combinado para ejecutar el paquete de aprovisionamiento: **pulse** Bajar volumen y Botón de **encendido** al mismo tiempo.
1. Se le pedirá que aplique el paquete de aprovisionamiento, seleccione **Confirmar**
1. Una vez completado el paquete de aprovisionamiento, seleccione **Aceptar**.
1. A continuación, se te pedirá que inicies sesión en el dispositivo con la cuenta local compartida y la contraseña.

## <a name="maintain"></a>Mantener

Con esta configuración, se recomienda reiniciar el proceso anterior y reflash el dispositivo con la herramienta ARC y aplicar un nuevo PPKG para realizar cualquier actualización del sistema operativo y/o las aplicaciones.
