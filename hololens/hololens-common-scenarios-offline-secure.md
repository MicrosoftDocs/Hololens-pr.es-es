---
title: 'Escenarios comunes: seguridad sin conexión HoloLens 2'
description: Aprenda a configurar un escenario de implementación segura sin conexión y de implementación de aplicaciones con aprovisionamiento para HoloLens dispositivos.
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
ms.openlocfilehash: 10d1955249630202a05fbf2057e1d175855ce0b5
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032985"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>Escenarios comunes: seguridad sin conexión HoloLens 2

## <a name="overview"></a>Información general

En esta guía se proporcionan instrucciones para aplicar un paquete de aprovisionamiento de ejemplo que bloqueará un HoloLens 2 para su uso en entornos seguros con las restricciones siguientes:

-   Deshabilite Wi-Fi.
-   Deshabilite BlueTooth.
-   Deshabilite micrófonos.
-   Impide agregar o quitar paquetes de aprovisionamiento.
-   Ningún usuario puede habilitar ninguno de los componentes restringidos anteriores.

[![Escenario seguro sin conexión. ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)

## <a name="prepare"></a>Preparación

Windows 10 Configuración del equipo
1. [Descargue el archivo HoloLens 2 sistema operativo más](https://aka.ms/hololens2download) reciente directamente en un equipo. 
   1. La compatibilidad con esta configuración se incluye en la compilación 19041.1117 y posteriores.
1. Descargar o instalar la herramienta Advanced Recovery Companion(ARC) [desde la Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) al equipo
1. Descargue o instale la herramienta [Windows configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) más reciente desde Microsoft Store al equipo.
1. [Descargue la OfflineSecureHL2_Sample con los archivos del proyecto para](https://aka.ms/HoloLensDocs-SecureOfflineSample) compilar el PPKG.
1. Prepare la aplicación [de línea de negocio sin conexión para la implementación de PPKG.](app-deploy-provisioning-package.md) 


## <a name="configure"></a>Configuración

Compilación de un paquete de aprovisionamiento de configuración segura

1. Inicie la herramienta WCD en el equipo.
1. Seleccione **Archivo -> Abrir proyecto**.
  1. Vaya a la ubicación de la carpeta OfflineSecureHL2_Sample guardada anteriormente y seleccione: OfflineSecureHL2_Sample.icdproj.xml
1. El proyecto debe abrirse y ahora debería tener una lista de personalizaciones disponibles:

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla del paquete de configuración abierto en WCD.](images/offline-secure-sample-wcd.png)

   Configuraciones establecidas en este paquete de aprovisionamiento:
   
   |     Elemento                                                |     Configuración                       |     Descripción                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Cuentas o usuarios                                    |     Nombre de usuario local & contraseña    |     Para estos dispositivos sin conexión, todos los usuarios del dispositivo tendrán que establecer y compartir un único nombre de usuario y contraseña.          |
   |     Primera experiencia/ HoloLens / Skip Yabration       |     Verdadero                          |     Omite la calibración solo durante la configuración inicial del dispositivo.                                                                             |
   |     Primera experiencia/HoloLens/SkipTraining          |     Verdadero                          |     Omite el entrenamiento del dispositivo durante la configuración inicial del dispositivo.                                                                              |
   |     Primera experiencia/HoloLens/Wi-Fi                  |     Verdadero                          |     Omite la Wi-Fi durante la configuración inicial del dispositivo.                                                                                 |
   |     Policies/Connectivity/AllowBluetooth                |     No                            |     Deshabilita Bluetooth                                                                                                             |
   |     Policies/Experience/AllowCortana                    |     No                            |     Deshabilita la Cortana (para eliminar posibles problemas, ya que los micrófonos están deshabilitados)                                          |
   |     Policies/MixedReality/MicrophoneDisabled            |     Sí                           |     Deshabilita micrófono                                                                                                            |
   |     Policies/Privacy/LetAppsAccessLocation              |     Forzar denegación                    |     Impide que las aplicaciones intenten acceder a los datos de ubicación (para eliminar posibles problemas, ya que el seguimiento de ubicación está deshabilitado)    |
   |     Directivas/Privacidad/LetAppsAccessMicrophone            |     Forzar denegación                    |     Impide que las aplicaciones intenten acceder a los micrófonos (para eliminar posibles problemas, ya que los micrófonos están deshabilitados)           |
   |     Policies/Security/AllowAddProvisioningPackage       |     No                            |     Impide que alguien agregue paquetes de aprovisionamiento que puedan intentar invalidar las directivas bloqueadas.                         |
   |     Policies/Security/AllowRemoveProvisioningPackage    |     No                            |     Impide que alguien quite este paquete de aprovisionamiento bloqueado.                                                           |
   |     Policies/System/AllowLocation                       |     No                            |     Impide que el dispositivo intente realizar un seguimiento de los datos de ubicación.                                                                        |
   |     Directivas/Wi-Fi/AllowWiFi                             |     No                            |     Deshabilita Wi-Fi                                                                                                                 |

1. En Runtime Configuración, seleccione **Accounts/Users/UserName: Holo /Password (Cuentas/Usuarios/NombreDeUsuario: Holo/Contraseña).**

   Anote la contraseña y restablezca si lo desea.

1. Vaya a UniversalAppInstall /UserContextApp y configure la aplicación [LOB](app-deploy-provisioning-package.md) que va a implementar en estos dispositivos.

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla de dónde agregar la aplicación en WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. Una vez completado, seleccione el botón "Exportar" y siga todas las indicaciones hasta que se cree el paquete de aprovisionamiento.

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla del botón Exportar para este paquete en WCD.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Implementar

1. Conectar hl2 al equipo Windows 10 a través de un cable USB.
1. Inicie la herramienta ARC y seleccione **HoloLens 2**

   ![Pantalla inicial de la nueva instalación de la imagen de HoloLens 2.](images/ARC2.png)

1. En la siguiente pantalla, seleccione **Selección manual de paquetes.**

   ![HoloLens 2 Pantalla de información de ARC.](images/arc_device_info.png)

1. Vaya al archivo .ffu descargado anteriormente y seleccione **Abrir.**
1. En la página Advertencia, seleccione **Continuar.**

   ![HoloLens 2 Pantalla de advertencia de ARC.](images/arc_warning.png)

1. Espere a que la herramienta ARC complete la instalación HoloLens 2 sistema operativo.
1. Una vez que el dispositivo complete la instalación y arranque la copia de seguridad, desde el equipo vaya a Explorador de archivos y copie el archivo PPKG guardado anteriormente en la carpeta del dispositivo.

   > [!div class="mx-imgBorder"]
   > ![Archivo PPKG en pc en Explorador de archivos ventana.](images/offline-secure-file-explorer.png)

1. En la HoloLens 2, presione el siguiente botón combinado para ejecutar el paquete de aprovisionamiento: **Pulse** Bajar volumen y **Botón** de encendido al mismo tiempo.
1. Se le pedirá que aplique el paquete de aprovisionamiento y seleccione **Confirmar.**
1. Una vez completado el paquete de aprovisionamiento, seleccione **Aceptar.**
1. A continuación, se le pedirá que inicie sesión en el dispositivo con la cuenta local compartida y la contraseña.

## <a name="maintain"></a>Mantenimiento

Con esta configuración, se recomienda reiniciar el proceso anterior y volver a actualizar el dispositivo con la herramienta ARC y aplicar un nuevo PPKG para realizar cualquier actualización del sistema operativo o las aplicaciones.
