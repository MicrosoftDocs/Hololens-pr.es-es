---
title: Desbloquear las funciones de Windows Holographic for Business
description: Al actualizar a Windows Holographic para la empresa, HoloLens ofrece características adicionales diseñadas para empresas.
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
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829621"
---
# Desbloquear las funciones de Windows Holographic for Business

> [!IMPORTANT]
> Esta página solo se aplica a HoloLens 1 ª gen.

Microsoft HoloLens está disponible en la *edición de desarrollo*, que ejecuta Windows Holographic (una edición de Windows 10 diseñada para HoloLens), y en el [conjunto comercial](hololens-commercial-features.md), que ofrece características adicionales diseñadas para empresas.

Si adquieres la Commercial Suite, recibirás una licencia que actualizará Windows Holographic a Windows Holographic for Business. Puede aplicar esta licencia al dispositivo con el [proveedor de administración de dispositivos móviles (MDM)](#edition-upgrade-by-using-mdm) o un [paquete de aprovisionamiento](#edition-upgrade-by-using-a-provisioning-package)de la organización.

> [!TIP]
> En Windows 10, versión 1803, puede comprobar que HoloLens se ha actualizado a la edición para empresas seleccionando sistema de **configuración**  >  **System**.

## Actualización de edición mediante MDM

La licencia de empresa se puede aplicar mediante cualquier proveedor de MDM que admita el [proveedor de servicios de configuración (CSP) WindowsLicensing](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) (en inglés). La versión más reciente de la API de MDM de Microsoft será compatible con el CSP WindowsLicensing.

Para obtener instrucciones paso a paso para actualizar HoloLens con Microsoft Intune, consulte [actualizar dispositivos que ejecutan Windows Holographic a Windows Holographic para empresas](https://docs.microsoft.com/intune/holographic-upgrade).

 En otros proveedores de MDM, los pasos específicos para configurar e implementar la directiva pueden variar.

## Actualización de edición mediante un paquete de aprovisionamiento

Los paquetes de aprovisionamiento son archivos creados por la herramienta Diseñador de configuraciones de Windows que aplican una configuración especificada a un dispositivo.

### Creación de un paquete de aprovisionamiento que actualice la edición de Windows Holographic

1. [Crea un paquete de aprovisionamiento para HoloLens.](hololens-provisioning.md)
1. Ve a **Configuración de tiempo de ejecución** > **EditionUpgrade**y selecciona **EditionUpgradeWithLicense**.

    ![Actualización de la edición con la configuración de la licencia seleccionada](images/icd1.png)

1. Busque el archivo de licencia XML que se proporcionó cuando compró el conjunto comercial.

    > [!NOTE]
    > Puedes configurar [valores de configuración adicionales en el paquete de aprovisionamiento](hololens-provisioning.md).

1. En el menú **archivo** , seleccione **Guardar**. 

1. Lea la advertencia de que los archivos de proyecto pueden contener información confidencial y haga clic en **Aceptar**.

    > [!IMPORTANT]
    > Al crear un paquete de aprovisionamiento, puede incluir información confidencial en el archivo de archivos de proyecto y en el archivo de paquete de aprovisionamiento (. ppkg). Aunque tienes la posibilidad de cifrar el archivo .ppkg, los archivos de proyecto no se cifran. Debe almacenar los archivos de proyecto en una ubicación segura y eliminar los archivos de proyecto cuando ya no los necesite.

1. En el menú **Exportar**, selecciona **Paquete de aprovisionamiento**.

1. Cambie el **propietario** a **Administrador de ti**, que establece la prioridad de este paquete de aprovisionamiento para que sea superior a la de otros usuarios que se aplican a este dispositivo desde diferentes orígenes y, después, seleccione **siguiente**.

1. Establece un valor para **Versión del paquete**.

    > [!TIP]
    > Puedes realizar cambios en los paquetes existentes y cambiar el número de versión para actualizar los paquetes aplicados anteriormente.

1. En **seleccionar detalles de seguridad para el paquete de aprovisionamiento**, seleccione **siguiente**.

1. Seleccione **siguiente** para especificar la ubicación de salida donde quiere que aparezca el paquete de aprovisionamiento una vez que se ha creado. De forma predeterminada, Windows ICD usa la carpeta de proyecto como la ubicación de salida.

    De manera opcional, puede seleccionar **examinar** para cambiar la ubicación de salida predeterminada.

1. Selecciona **Siguiente**.

1. Seleccione **compilación** para empezar a crear el paquete. En la página compilación se muestra la información del proyecto y la barra de progreso indica el estado de la compilación.

1. Una vez completada la compilación, seleccione **Finalizar**.

### Aplicación del paquete de aprovisionamiento a HoloLens

1. Con el cable USB, conecte el dispositivo a un PC. Inicie el dispositivo, pero no continúe después de la página **ajustar** de la experiencia de configuración inicial (la primera página con el cuadro azul). En el equipo, HoloLens se muestra como un dispositivo en el explorador de archivos.

    > [!NOTE]
    > Si el dispositivo HoloLens ejecuta Windows 10, versión 1607 o anterior, abre el explorador de archivos presionando y soltando el **volumen** y los botones de **encendido** y apagado de forma simultánea en el dispositivo.

1. En el Explorador de archivos, arrastra y coloca el paquete de aprovisionamiento (.ppkg) en el almacenamiento del dispositivo.

1. Mientras HoloLens esté en la página **ajustar** , pulse brevemente y suelte los botones de **encendido** y **apagado** de forma simultánea.

1. HoloLens te pregunta si confías en el paquete y deseas aplicarlo. Confirma que el paquete es de confianza.

1. Verás si el paquete se ha aplicado correctamente o no. Si no se aplicó correctamente, puedes corregir el paquete e intentarlo de nuevo. Si es correcto, continúe con la configuración del dispositivo.
