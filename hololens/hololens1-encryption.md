---
title: Cifrado de BitLocker de HoloLens
description: Aprende a habilitar el cifrado de dispositivos bitlocker para proteger los archivos almacenados en los dispositivos de realidad mixta de HoloLens.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: 268c3650b85e7e7f102618ccc5a94c25de54dcfe
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284031"
---
# Cifrado de BitLocker (1º exgen) para HoloLens

HoloLens (1.ª generación) y HoloLens 2 admiten el cifrado de dispositivos con BitLocker; sin embargo, BitLocker siempre está habilitado en HoloLens 2.

Este artículo te ayudará a habilitar y administrar BitLocker en HoloLens (1.ª generación).

En HoloLens (1.ª generación) puedes habilitar el cifrado de dispositivos BitLocker manualmente o mediante la administración de dispositivos móviles (MDM). Sigue estas instrucciones para habilitar el cifrado [de dispositivos BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) para proteger los archivos y la información almacenada en HoloLens. El cifrado de dispositivos ayuda a proteger los datos mediante el método de cifrado AES-CBC 128, que es equivalente al método [EncryptionMethodByDriveType 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) en el proveedor de servicios de configuración (CSP) de BitLocker. El personal que tiene la clave de cifrado correcta (como una contraseña) puede descifrarla o realizar una recuperación de datos.

## Habilitar el cifrado de dispositivos con MDM

Puedes usar el proveedor de administración de dispositivos móviles (MDM) para aplicar una directiva que requiera cifrado de dispositivos. La directiva que se va a usar [es la configuración Seguridad/RequireDeviceEncryption](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) en el CSP de directivas.

[Consulta las instrucciones para habilitar el cifrado de dispositivos con Microsoft Intune.](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

Para otras herramientas MDM, consulta la documentación de tu proveedor MDM para obtener instrucciones. Si el proveedor de MDM requiere un URI personalizado para el cifrado de dispositivos, usa la siguiente configuración:

- **Nombre**: el nombre que elijas
- **Descripción**: opcional
- **OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **Tipo de datos**: enteros
- **Valor**: `1`

## Habilitar el cifrado de dispositivo mediante un paquete de aprovisionamiento

Los paquetes de aprovisionamiento son archivos creados por la herramienta Diseñador de configuraciones de Windows que aplican una configuración especificada a un dispositivo. 

### Crear un paquete de aprovisionamiento que actualice la edición Holográfica de Windows y permita el cifrado

1. [Crea un paquete de aprovisionamiento para HoloLens.](hololens-provisioning.md)
1. Ve a **Configuración de tiempo de ejecución** > **Directivas** > **Seguridad** y selecciona **RequireDeviceEncryption**.

    ![Requerir el establecimiento de la configuración de cifrado de dispositivo en sí](images/device-encryption.png)

1. Busque el archivo de licencia XML que se proporcionó al adquirir commercial suite.

1. Busca y selecciona el archivo de licencia XML que se te proporcionara al adquirir la Commercial Suite.
    > [!NOTE]
    > Puedes configurar [valores de configuración adicionales en el paquete de aprovisionamiento](hololens-provisioning.md).

1. En el menú **Archivo**, haz clic en **Guardar**. 

1. Lea la advertencia que explica que los archivos del proyecto pueden contener información confidencial y haga clic en **Aceptar.**

    > [!IMPORTANT]
    > Al compilar un paquete de aprovisionamiento, puedes incluir información confidencial en los archivos del proyecto y el archivo de paquete de aprovisionamiento (.ppkg). Aunque tienes la posibilidad de cifrar el archivo .ppkg, los archivos de proyecto no se cifran. Debe almacenar los archivos del proyecto en una ubicación segura y eliminar los archivos del proyecto cuando ya no sea necesario.

1. En el menú **Exportar**, haz clic en **Paquete de aprovisionamiento**.
1. Cambia el **Propietario** a **Administrador de TI** para establecer una prioridad para este paquete de aprovisionamiento superior a la de los paquetes de aprovisionamiento aplicados a este dispositivo desde otros orígenes y, a continuación, selecciona **Siguiente**.
1. Establece un valor para **Versión del paquete**.

    > [!TIP]
    > Puedes realizar cambios en los paquetes existentes y modificar el número de versión para actualizar los paquetes aplicados anteriormente.

1. En **Selecciona los detalles de seguridad del paquete de aprovisionamiento**, haz clic en **Siguiente**.
1. Haz clic en **Siguiente** para especificar la ubicación de salida donde quieras ubicar el paquete de aprovisionamiento una vez compilado. De forma predeterminada, Windows ICD usa la carpeta de proyecto como la ubicación de salida.

    También puedes hacer clic en Examinar para cambiar la ubicación de salida predeterminada.

1. Haz clic en **Siguiente**.
1. Haz clic en **Compilar** para comenzar a compilar el paquete. La información del proyecto se muestra en la página de compilación y la barra de progreso indica el estado de la compilación.
1. Cuando la compilación se haya completado, haz clic en **Finalizar**.

### Aplicación del paquete de aprovisionamiento a HoloLens

1. Conecta el dispositivo mediante USB a un equipo e inícialo, pero no pases de la página de **ajuste** de la experiencia de configuración inicial (la primera página con el cuadro azul).
1. Presiona brevemente los botones **Bajar el volumen** e **Inicio/Apagado** a la vez y suéltalos.
1. HoloLens aparecerá como un dispositivo en el Explorador de archivos del equipo.
1. En el Explorador de archivos, arrastra y coloca el paquete de aprovisionamiento (.ppkg) en el almacenamiento del dispositivo.
1. En la página de **ajuste**, presiona otra vez brevemente los botones **Bajar el volumen** e **Inicio/Apagado** a la vez y suéltalos.
1. El dispositivo te preguntará si el paquete es de confianza y si quieres aplicarlo. Confirma que el paquete es de confianza.
1. Verás si el paquete se ha aplicado correctamente o no. Si se ha producido un error, puedes arreglar el paquete y volver a intentarlo. Si se ha aplicado correctamente, continúa con la configuración del dispositivo.

> [!NOTE]
> Si el dispositivo se ha adquirido antes de agosto de 2016, deberás iniciar sesión en el dispositivo con una cuenta de Microsoft, obtener la última actualización del sistema operativo y luego restablecer dicho sistema operativo para aplicar el paquete de aprovisionamiento.

## Verificar el cifrado de dispositivo

El cifrado es silencioso en HoloLens. Para verificar el estado de cifrado del dispositivo:

- En HoloLens, ve a **Configuración** > **Sistema** > **Acerca de**. **BitLocker** está **habilitado si** el dispositivo está cifrado. 

    ![Acerca de la pantalla que muestra BitLocker habilitado](images/about-encryption.png)
