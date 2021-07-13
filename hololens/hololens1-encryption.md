---
title: HoloLens Cifrado de BitLocker
description: Obtenga información sobre cómo habilitar el cifrado de dispositivos BitLocker para proteger los archivos almacenados en HoloLens de realidad mixta.
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
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 37efab3ef3d68a9641320e144619008612f6efa2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635252"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a>Cifrado de BitLocker para HoloLens (1.ª generación)

HoloLens (1.ª generación) y HoloLens 2 admiten el cifrado de dispositivos mediante BitLocker; sin embargo, BitLocker siempre está habilitado en HoloLens 2.

Este artículo le ayudará a habilitar y administrar BitLocker en HoloLens (1.ª generación).

En HoloLens (1.ª generación) puede habilitar el cifrado de dispositivos BitLocker manualmente o mediante la administración de dispositivos móviles (MDM). Siga estas instrucciones para habilitar el cifrado [de dispositivos BitLocker](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) para proteger los archivos y la información almacenada en el HoloLens. El cifrado de dispositivos ayuda a proteger los datos mediante el método de cifrado AES-CBC 128, que es equivalente al método [EncryptionMethodByDriveType 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) en el proveedor de servicios de configuración (CSP) de BitLocker. El personal que tiene la clave de cifrado correcta (por ejemplo, una contraseña) puede descifrarla o realizar una recuperación de datos.

## <a name="enable-device-encryption-using-mdm"></a>Habilitación del cifrado de dispositivos mediante MDM

Puede usar el proveedor de Administración de dispositivos móviles (MDM) para aplicar una directiva que requiera cifrado de dispositivos. La directiva que se va a usar [es la configuración Security/RequireDeviceEncryption](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) en el CSP de directiva.

[Consulte las instrucciones para habilitar el cifrado de dispositivos mediante Microsoft Intune.](/intune/compliance-policy-create-windows#windows-holographic-for-business)

Para otras herramientas de MDM, consulte la documentación del proveedor de MDM para obtener instrucciones. Si el proveedor de MDM requiere un URI personalizado para el cifrado de dispositivos, use la siguiente configuración:

- **Nombre:** nombre de su elección
- **Descripción:** opcional
- **OMA-URI:**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **Tipo de datos**: entero
- **Valor**: `1`

## <a name="enable-device-encryption-using-a-provisioning-package"></a>Habilitación del cifrado de dispositivos mediante un paquete de aprovisionamiento

Los paquetes de aprovisionamiento son archivos creados por la Windows diseñador de configuración que aplican una configuración especificada a un dispositivo. 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a>Creación de un paquete de aprovisionamiento que actualice la Windows holographic edition y habilita el cifrado

1. [Crea un paquete de aprovisionamiento para HoloLens.](hololens-provisioning.md)
1. Vaya a **Configuración del entorno de ejecución**  >  **Directivas**  >  **seguridad** y **seleccione RequerirDispositivoEncryption.**

    ![Requerir configuración de cifrado de dispositivo configurada en Sí](images/device-encryption.png)

1. Busque el archivo de licencia XML que se proporcionó al adquirir el conjunto de aplicaciones comerciales.

1. Busca y selecciona el archivo de licencia XML que se te proporcionara al adquirir la Commercial Suite.
    > [!NOTE]
    > Puedes configurar [valores de configuración adicionales en el paquete de aprovisionamiento](hololens-provisioning.md).

1. En el menú **Archivo**, haga clic en **Guardar**. 

1. Lea la advertencia que explica que los archivos de proyecto pueden contener información confidencial y haga clic **en Aceptar.**

    > [!IMPORTANT]
    > Al compilar un paquete de aprovisionamiento, puede incluir información confidencial en los archivos de proyecto y el archivo de paquete de aprovisionamiento (.ppkg). Aunque tienes la posibilidad de cifrar el archivo .ppkg, los archivos de proyecto no se cifran. Debe almacenar los archivos del proyecto en una ubicación segura y eliminar los archivos del proyecto cuando ya no los necesite.

1. En el menú **Exportar**, haz clic en **Paquete de aprovisionamiento**.
1. Cambie **Propietario a** **Administrador** de TI, que establecerá la prioridad de este paquete de aprovisionamiento mayor que los paquetes de aprovisionamiento aplicados a este dispositivo desde otros orígenes y, a continuación, **seleccione Siguiente.**
1. Establece un valor para **Versión del paquete**.

    > [!TIP]
    > Puedes realizar cambios en los paquetes existentes y modificar el número de versión para actualizar los paquetes aplicados anteriormente.

1. En **Selecciona los detalles de seguridad del paquete de aprovisionamiento**, haz clic en **Siguiente**.
1. Haz clic en **Siguiente** para especificar la ubicación de salida donde quieras ubicar el paquete de aprovisionamiento una vez compilado. De forma predeterminada, Windows ICD usa la carpeta de proyecto como ubicación de salida.

    También puedes hacer clic en Examinar para cambiar la ubicación de salida predeterminada.

1. Haga clic en **Next**.
1. Haz clic en **Compilar** para comenzar a compilar el paquete. La información del proyecto se muestra en la página de compilación y la barra de progreso indica el estado de la compilación.
1. Cuando la compilación se haya completado, haz clic en **Finalizar**.

### <a name="apply-the-provisioning-package-to-hololens"></a>Aplicación del paquete de aprovisionamiento a HoloLens

1. Conectar el dispositivo a través de USB a un equipo e  inicie el dispositivo, pero no continúe más allá de la página de ajuste de la experiencia de configuración inicial (la primera página con el cuadro azul).
1. Presiona brevemente los botones **Bajar el volumen** e **Inicio/Apagado** a la vez y suéltalos.
1. HoloLens aparecerá como un dispositivo en el Explorador de archivos del equipo.
1. En el Explorador de archivos, arrastra y coloca el paquete de aprovisionamiento (.ppkg) en el almacenamiento del dispositivo.
1. En la página de **ajuste**, presiona otra vez brevemente los botones **Bajar el volumen** e **Inicio/Apagado** a la vez y suéltalos.
1. El dispositivo te preguntará si el paquete es de confianza y si quieres aplicarlo. Confirma que el paquete es de confianza.
1. Verás si el paquete se ha aplicado correctamente o no. Si se ha producido un error, puedes arreglar el paquete y volver a intentarlo. Si se ha hecho correctamente, continúe con la configuración del dispositivo.

> [!NOTE]
> Si el dispositivo se compró antes de agosto de 2016, deberá iniciar sesión en el dispositivo con una cuenta Microsoft, obtener la actualización más reciente del sistema operativo y, a continuación, restablecer el sistema operativo para aplicar el paquete de aprovisionamiento.

## <a name="verify-device-encryption"></a>Comprobación del cifrado del dispositivo

El cifrado es silencioso en HoloLens. Para comprobar el estado de cifrado del dispositivo:

- En HoloLens, vaya **a** Configuración  >  **Sistema**  >  **acerca de**. **BitLocker** está **habilitado si** el dispositivo está cifrado. 

    ![Acerca de la pantalla que muestra BitLocker habilitado](images/about-encryption.png)
