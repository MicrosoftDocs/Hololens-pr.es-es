---
title: Desbloqueo de Windows Holographic for Business características
description: Al actualizar a Windows Holographic for Business, HoloLens proporciona características adicionales diseñadas para empresas.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310156"
---
# <a name="unlock-windows-holographic-for-business-features"></a>Desbloqueo de Windows Holographic for Business características

> [!IMPORTANT]
> Esta página solo se aplica a HoloLens 1st Gen.

Microsoft HoloLens está disponible en *development Edition,* que ejecuta Windows Holographic (una edición de Windows 10 diseñada para HoloLens) y en [Commercial Suite](hololens-commercial-features.md), que proporciona características adicionales diseñadas para empresas.

Al comprar Commercial Suite, recibirá una licencia que actualiza Windows Holographic a Windows Holographic for Business. Puede aplicar esta licencia al dispositivo mediante el proveedor de administración de dispositivos móviles [(MDM)](#edition-upgrade-by-using-mdm) de la organización o un paquete [de aprovisionamiento](#edition-upgrade-by-using-a-provisioning-package).

> [!TIP]
> En Windows 10, versión 1803, puede comprobar que HoloLens se ha actualizado a la edición business seleccionando Settings  >  System (Sistema de **configuración).**

## <a name="edition-upgrade-by-using-mdm"></a>Actualización de edición mediante MDM

La licencia de empresa se puede aplicar mediante cualquier proveedor de MDM que admita el [proveedor de servicios de configuración (CSP) WindowsLicensing](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) (en inglés). La versión más reciente de la API de MDM de Microsoft será compatible con el CSP WindowsLicensing.

Para obtener instrucciones paso a paso para actualizar HoloLens mediante Microsoft Intune, consulte Actualización de dispositivos que ejecutan [Windows Holographic a Windows Holographic for Business](https://docs.microsoft.com/intune/holographic-upgrade).

 En otros proveedores de MDM, los pasos específicos para configurar e implementar la directiva pueden variar.

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>Actualización de edición mediante un paquete de aprovisionamiento

Los paquetes de aprovisionamiento son archivos creados por la herramienta Diseñador de configuración de Windows que aplican una configuración especificada a un dispositivo.

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>Creación de un paquete de aprovisionamiento que actualice la edición de Windows Holographic

1. [Crea un paquete de aprovisionamiento para HoloLens.](hololens-provisioning.md)
1. Vaya a **Configuración del entorno de ejecución**  >  **EdiciónActulta** y seleccione **EdiciónUpgradeWithLicense.**

    ![Actualización de la edición con la configuración de la licencia seleccionada](images/icd1.png)

1. Busque el archivo de licencia XML que se proporcionó al adquirir el conjunto de aplicaciones comerciales.

    > [!NOTE]
    > Puedes configurar [valores de configuración adicionales en el paquete de aprovisionamiento](hololens-provisioning.md).

1. En el menú **Archivo**, seleccione **Guardar**. 

1. Lea la advertencia de que los archivos de proyecto pueden contener información confidencial y haga clic en **Aceptar.**

    > [!IMPORTANT]
    > Al compilar un paquete de aprovisionamiento, puede incluir información confidencial en los archivos de proyecto y el archivo de paquete de aprovisionamiento (.ppkg). Aunque tienes la posibilidad de cifrar el archivo .ppkg, los archivos de proyecto no se cifran. Debe almacenar los archivos del proyecto en una ubicación segura y eliminar los archivos del proyecto cuando ya no los necesite.

1. En el menú **Exportar**, selecciona **Paquete de aprovisionamiento**.

1. Cambie **Propietario a** **Administrador** de TI, que establece la prioridad de este paquete de aprovisionamiento para que sea mayor que otras aplicadas a este dispositivo desde orígenes diferentes y, a continuación, **seleccione Siguiente.**

1. Establece un valor para **Versión del paquete**.

    > [!TIP]
    > Puedes realizar cambios en los paquetes existentes y modificar el número de versión para actualizar los paquetes aplicados anteriormente.

1. En **Seleccionar detalles de seguridad para el paquete de aprovisionamiento,** seleccione **Siguiente.**

1. Seleccione **Siguiente** para especificar la ubicación de salida a la que desea que vaya el paquete de aprovisionamiento una vez que se haya creado. De forma predeterminada, Windows ICD usa la carpeta de proyecto como ubicación de salida.

    Opcionalmente, puede seleccionar Examinar **para** cambiar la ubicación de salida predeterminada.

1. Seleccione **Siguiente**.

1. Seleccione **Compilar** para empezar a compilar el paquete. La página de compilación muestra la información del proyecto y la barra de progreso indica el estado de compilación.

1. Cuando se complete la compilación, seleccione **Finalizar.**

### <a name="apply-the-provisioning-package-to-hololens"></a>Aplicación del paquete de aprovisionamiento a HoloLens

1. Con el cable USB, conecte el dispositivo a un equipo. Inicie el dispositivo, pero no continúe más allá de la **página** de ajuste de la experiencia de configuración inicial (la primera página con el cuadro azul). En el equipo, HoloLens se muestra como un dispositivo en Explorador de archivos.

    > [!NOTE]
    > Si el dispositivo HoloLens ejecuta Windows 10, versión 1607 o anterior, abra Explorador de archivos presionando brevemente  y  liberando los botones Bajar volumen y Encendido simultáneamente en el dispositivo.

1. En el Explorador de archivos, arrastra y coloca el paquete de aprovisionamiento (.ppkg) en el almacenamiento del dispositivo.

1. Mientras HoloLens sigue en la **página** de ajuste, presione  brevemente y suelte los botones **Bajar** volumen y Encendido simultáneamente de nuevo.

1. HoloLens le pregunta si confía en el paquete y le gustaría aplicarlo. Confirma que el paquete es de confianza.

1. Verás si el paquete se ha aplicado correctamente o no. Si no se aplicó correctamente, puede corregir el paquete e intentarlo de nuevo. Si se realiza correctamente, continúe con la configuración del dispositivo.
