---
title: Windows Autopilot para HoloLens 2
description: Obtenga información sobre cómo instalar y configurar Autopilot en dispositivos HoloLens 2.
author: qianw211
ms.author: v-qianwen
ms.date: 9/8/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: sekerawa
ms.openlocfilehash: 28793b385bad58d44c6592a800c4f56b18d152ce
ms.sourcegitcommit: 20ea1ed37772655504ccb11a7e185ed19d85f336
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2021
ms.locfileid: "127833580"
---
# <a name="windows-autopilot-for-hololens-2"></a>Windows Autopilot para HoloLens 2

## <a name="overview"></a>Información general

Para realizar la implementación a escala, se recomienda empezar a usar Windows Autopilot. Se considera "casi automático", ya que simplifica considerablemente la configuración de HoloLens para el personal de TI y los usuarios finales. 

A un nivel alto, un administrador de TI normalmente creará configuraciones listas para empresas y registrará los dispositivos HoloLens 2 en los portales de MDM. Cuando los dispositivos HoloLens 2 se inician con la configuración rápida (OOBE) y se conectan con Internet, las configuraciones listas para empresas de dispositivos HoloLens 2 registrados se descargan y aplican automáticamente para que el dispositivo esté listo para la empresa sin la intervención del usuario.

Para obtener más información, consulte el artículo [Información general de Windows Autopilot | Microsoft Docs](/mem/autopilot/windows-autopilot).

## <a name="supported-autopilot-scenario-on-hololens-2"></a>Escenario de Autopilot admitido en HoloLens 2

> [!NOTE]
> La configuración de Autopilot para HoloLens en Microsoft Endpoint Manager dejará de encontrarse en **versión preliminar pública** y empezará a estar **disponible de forma general**. Todos los inquilinos podrán configurar Autopilot en el centro de administración de MEM.

A partir de la versión 2004 de Windows Holographic, HoloLens 2 admite el [modo autoimplementable](/mem/autopilot/self-deploying) de Windows Autopilot con Microsoft Intune (no se admiten MDM de terceros). Esta configuración reduce la sobrecarga de la administración de inventario, el coste de la preparación práctica de dispositivos y las llamadas de soporte de empleados durante la experiencia de configuración. Para obtener más información, consulte la documentación de [Windows Autopilot](/mem/autopilot/windows-autopilot).

Al igual que en el caso de los dispositivos Surface, se recomienda que los clientes trabajen con su [proveedor de soluciones en la nube](https://partner.microsoft.com/cloud-solution-provider) de Microsoft (revendedor o distribuidor) para obtener dispositivos registrados con el servicio Autopilot a través del Centro de partners.

Cuando un usuario inicia el proceso autoimplementable de Autopilot, este realiza los siguientes pasos:

1. Unir el dispositivo a Azure Active Directory (Azure AD). Autopilot para HoloLens no admite la unión a Active Directory ni a Azure AD híbrido.

1. Usar Azure AD para inscribir el dispositivo en Microsoft Endpoint Manager (u otro servicio MDM).

1. Descargar y aplicar directivas, certificados, perfiles de red y aplicaciones dirigidos a dispositivos.

1. Mostrar la pantalla de inicio de sesión al usuario.

## <a name="configuring-autopilot-for-hololens-2"></a>Configuración de Autopilot para HoloLens 2

Siga los pasos a continuación para configurar el entorno:

1. [Revise los requisitos de Windows Autopilot para HoloLens 2.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Habilite la inscripción automática de MDM.](#2-enable-automatic-mdm-enrollment)

1. (Solo para Intune) [Asegúrese de que la inscripción de MDM no esté bloqueada para dispositivos Windows.](/mem/intune/enrollment/enrollment-restrictions-set)

1. [Registre dispositivos en Windows Autopilot.](#4-register-devices-in-windows-autopilot)

1. [Cree un grupo de dispositivos.](#5-create-a-device-group)

1. [Cree el perfil de Autopilot y asígnelo al grupo de dispositivos.](#6-create-autopilot-profile-and-assign-it-to-the-device-group)

1. [Cree la configuración de la página de estado de inscripción (ESP) y asígnela al grupo de dispositivos.](#7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group)

1. [Compruebe el estado del perfil de los dispositivos HoloLens.](#8-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. Revise los requisitos de Windows Autopilot para HoloLens 2

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Consulte las siguientes secciones del artículo sobre los requisitos de Windows Autopilot:

- [Requisitos de red](/mem/autopilot/networking-requirements)  
- [Requisitos de concesión de licencia](/mem/autopilot/licensing-requirements)  
- [Requisitos de configuración](/mem/autopilot/configuration-requirements)

**Consulte la sección ["Requisitos"](/windows/deployment/windows-autopilot/self-deploying#requirements) del artículo sobre el modo autoimplementable de Windows Autopilot.** Su entorno tiene que cumplir estos requisitos y los requisitos estándar de Windows Autopilot. No es necesario que revise las secciones "Paso a paso" y "Validación" del artículo. En los procedimientos que se describen más adelante en este artículo se proporcionan los pasos correspondientes específicos para HoloLens.

Asegúrese de que los dispositivos no sean ya miembros de Azure AD y de que no estén inscritos en Intune (u otro sistema MDM). El proceso autoimplementable de Autopilot completa estos pasos. Para asegurarse de que toda la información relacionada con los dispositivos se haya eliminado, active la casilla de verificación **Dispositivos** en las páginas de los portales de Azure AD e Intune. En estos momentos HoloLens no admite la característica "Convertir todos los dispositivos de destino a Autopilot". 

#### <a name="review-hololens-os-requirements"></a>Revise los requisitos de sistema operativo de HoloLens

Con el fin de confirmar la versión de la compilación en el dispositivo o reprogramarlo con el sistema operativo más reciente, use [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=2&activetab=pivot:overviewtab) y las [instrucciones para reprogramar dispositivos](hololens-recovery.md). Los dispositivos entregados hasta finales de septiembre de 2020 tienen preinstalada la versión 1903 de Windows Holographic. Póngase en contacto con su revendedor para asegurarse de que se le entreguen dispositivos preparados para Autopilot.

 Versión mínima del sistema operativo | Característica compatible | Comentarios 
 ------ | ------ | ------  
 [Windows Holographic, versión 2004](hololens-release-notes.md#windows-holographic-version-2004) (compilación 19041.1103) o posterior | 1. Escenario de implementación automática de Autopilot en HoloLens 2. | La descarga del perfil de Autopilot solo se admite a través de Ethernet. **Antes de activar HoloLens**, asegúrese de que esté conectado a Ethernet mediante un adaptador de USB-C a este estándar.  Si tiene pensado implantar Autopilot en muchos dispositivos HoloLens, le recomendamos planificar la infraestructura de adaptadores. No se recomienda usar centros de conectividad USB, ya que suelen requerir la instalación de controladores de terceros que no son compatibles con HoloLens.
 [Windows Holographic, versión 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (compilación 19041.1128) o posterior | 1. Descarga del perfil de Autopilot a través de Wi-Fi. <br> 2. [TenantLockdown CSP y Autopilot](#tenant-lockdown-csp-and-autopilot) para bloquear dispositivos con el inquilino especificado de Autopilot. | Puede seguir utilizando adaptadores Ethernet si lo desea. En el caso de dispositivos conectados a través de Wi-Fi, el usuario solo debe hacer lo siguiente: <ul> <li> Ir a la escena del colibrí. </li> <li> Elegir el idioma y la configuración regional. </li> <li> Ejecutar la calibración de los ojos. </li> <li> Conectarse correctamente con la red Wi-Fi deseada. </li> </ul>

### <a name="2-enable-automatic-mdm-enrollment"></a>2. Habilite la inscripción automática de MDM

Para que Autopilot funcione correctamente, tendrá que habilitar la inscripción automática de MDM en Azure Portal. De este modo, el dispositivo podrá inscribirse sin un usuario.

Revise la siguiente [guía breve sobre cómo habilitar la inscripción automática de MDM](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) o la [guía de inicio rápido de inscripción automática](/mem/intune/enrollment/quickstart-setup-auto-enrollment) para obtener aún más información sobre la configuración.

### <a name="3-ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>3. Asegúrese de que la inscripción de MDM no esté bloqueada para dispositivos Windows

Para que Autopilot funcione correctamente, deberá asegurarse de que los dispositivos HoloLens pueden inscribirse. Dado que HoloLens se considera un dispositivo Windows, no tendrá que haber ninguna restricción de inscripción que pueda bloquear la implementación. [Revise esta lista de restricciones](/mem/intune/enrollment/enrollment-restrictions-set) y asegúrese de que podrá inscribir los dispositivos.

### <a name="4-register-devices-in-windows-autopilot"></a>4. Registre dispositivos en Windows Autopilot

Sus dispositivos deben estar registrados en Windows Autopilot antes de la primera configuración. 

Hay tres formas principales de registrar dispositivos HoloLens:

 - **El revendedor puede registrar dispositivos en el Centro de partners cuando usted realice un pedido.**

   > [!NOTE]  
   > Esta es la ruta recomendada para agregar dispositivos al servicio Autopilot. [Más información](/mem/autopilot/partner-registration).  

 - **Puede [enviar una solicitud de soporte técnico](hololens2-autopilot-registration-support.md) directamente a Microsoft.**
 - **Recupere el hash de hardware (también conocido como "identificador de hardware") y registre el dispositivo manualmente en el centro de administración de MEM**.

#### <a name="obtain-hardware-hash"></a>Obtener el hash de hardware

Puede recuperar el hash de hardware del dispositivo. El dispositivo registra su hash de hardware en un archivo CSV durante el proceso OOBE, o bien posteriormente cuando el propietario de un dispositivo inicia el proceso de recopilación de registros de diagnósticos (descrito en el siguiente procedimiento). Por lo general, el propietario del dispositivo es el primer usuario que inicia sesión en este.

> [!WARNING]
> En las compilaciones anteriores a 20H2, si ha superado el proceso OOBE y la telemetría se ha establecido en "Requerido", no puede recopilar el hash de hardware para Autopilot usando este método. Para recopilar el hash de hardware usando este método, establezca la opción de telemetría en Completa mediante la aplicación Configuración y seleccione **Privacidad** > **Diagnóstico**.

1. Inicie el dispositivo HoloLens 2.

1. En el dispositivo, presione a la vez los botones **Encendido** y **Bajar volumen** y, a continuación, suéltelos. El dispositivo recopila registros de diagnósticos y el hash de hardware y los almacena en un conjunto de archivos .zip.

1. Para obtener más información y ver un vídeo explicativo, lea el artículo sobre el [Diagnóstico sin conexión](hololens-diagnostic-logs.md#offline-diagnostics).

1. Use un cable USB-C para conectar el dispositivo al equipo.

1. En el equipo, abra Explorador de archivos. Abra <b>Este equipo\\</b><*Nombre del dispositivo HoloLens*><b>\\Almacenamiento interno\\Documentos</b> y localice el archivo AutopilotDiagnostics.zip.  

   > [!NOTE]  
   > Puede que el archivo .zip no esté disponible inmediatamente. Si el archivo aún no está listo, es posible que aparezca el archivo "HoloLensDiagnostics.temp" en la carpeta "Documentos". Para actualizar la lista de archivos, actualice la ventana.
    
1. Extraiga el contenido del archivo "AutopilotDiagnostics.zip".

1. En los archivos extraídos, busque el archivo CSV con el prefijo de nombre "DeviceHash". Copie dicho archivo en una unidad del equipo donde pueda acceder a él más adelante.  

   > [!IMPORTANT]  
   > Los datos del archivo CSV deben usar el siguiente formato de línea y encabezado:
   >
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

#### <a name="register-device-through-mem"></a>Registrar un dispositivo a través de MEM

1. En el [centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com), seleccione **Dispositivos** > **Windows** > **Inscripción de Windows**; a continuación, seleccione **Dispositivos** > **Importar** en **Programa de implementación de Windows Autopilot**.

1. En **Agregar dispositivos de Windows Autopilot**, seleccione el archivo CSV "DeviceHash", **Abrir** y, a continuación, **Importar**.  

   > [!div class="mx-imgBorder"]
   > ![Use el comando "Importar" para importar el hash de hardware.](./images/hololens-ap-hash-import.png)

1. Una vez que finalice la importación, seleccione **Dispositivos** > **Windows** > **Inscripción de Windows** > **Dispositivos** > **Sincronizar**. El proceso puede tardar varios minutos en completarse, en función del número de dispositivos que se vayan a sincronizar. Para ver el dispositivo registrado, seleccione **Actualizar**.  

   > [!div class="mx-imgBorder"]
   > ![Use los comandos "Sincronizar" y "Actualizar" para ver la lista de dispositivos.](./images/hololens-ap-devices-sync.png)  

### <a name="5-create-a-device-group"></a>5. Cree un grupo de dispositivos

1. En el [centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com), elija **Grupos** > **Nuevo grupo**.

1. En **Tipo de grupo**, seleccione **Seguridad** y escriba un nombre de grupo y una descripción.

1. En **Tipo de pertenencia**, seleccione **Asignado** o **Dispositivo dinámico**.

1. Realice una de las siguientes acciones:  

   - Si ha seleccionado **Asignado** para **Tipo de pertenencia** en el paso anterior, seleccione **Miembros** y, a continuación, agregue dispositivos de Autopilot al grupo. Los dispositivos de Autopilot que no se han inscrito todavía se muestran usando su número de serie como nombre.
   - Si ha seleccionado **Dispositivos dinámicos** para **Tipo de pertenencia** en el paso anterior, seleccione **Miembros del dispositivo dinámico** y, a continuación, escriba en **Regla avanzada** código similar al siguiente:
     - Si quiere crear un grupo que incluya todos los dispositivos Autopilot, escriba `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`.
     - El campo de etiqueta de grupo de Intune se asigna al atributo **OrderID** en los dispositivos de Azure AD. Si quiere crear un grupo que incluya todos sus dispositivos de Autopilot que tienen una etiqueta de grupo específica (atributo "OrderID" del dispositivo de Azure AD), escriba lo siguiente: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Si quiere crear un grupo que incluya todos los dispositivos de Autopilot que tengan un identificador de pedido de compra específico, escriba lo siguiente: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Estas reglas buscan atributos que son exclusivos de dispositivos de Autopilot.
1. Seleccione **Guardar** y, a continuación, **Aceptar**.

### <a name="6-create-autopilot-profile-and-assign-it-to-the-device-group"></a>6. Cree un perfil de Autopilot y asígnelo al grupo de dispositivos

1. En el [centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com), seleccione **Dispositivos** > **Windows** > **Inscripción de Windows** > **Perfiles de implementación de Windows Autopilot** > **Crear perfil** > **HoloLens**.
   ![La lista desplegable "Crear perfil" incluye un elemento "HoloLens".](./images/hololens-ap-enrollment-profiles.png)

1. Escriba un nombre y una descripción para el perfil y seleccione **Siguiente**.  
   Deberías aparecer una lista que incluya **HoloLens**. Si esta opción no está disponible, utilice una de las opciones de [Comentarios](hololens2-autopilot.md#feedback-and-support-for-autopilot) para ponerse en contacto con nosotros.

   > [!div class="mx-imgBorder"]
   > ![Agregue un nombre y una descripción para el perfil.](./images/hololens-ap-profile-name.png)

1. En la página **Experiencia inmediata (OOBE)** , la mayoría de las opciones están configuradas previamente con el fin de simplificar la OOBE para esta evaluación. También puede configurar las siguientes opciones:  

   - **Idioma (región):** seleccione el idioma de la OOBE. Se recomienda seleccionar un idioma de la lista de [idiomas compatibles con HoloLens 2](hololens2-language-support.md).
   - **Configurar automáticamente el teclado:** para asegurarse de que el teclado coincida con el idioma seleccionado, seleccione **Sí**.
   - **Aplicar plantilla de nombre de dispositivo:** para establecer el nombre del dispositivo automáticamente durante la OOBE, seleccione **Sí** y escriba la frase y los marcadores de posición de la plantilla en **Escriba un nombre**. Por ejemplo, especifique un prefijo y `%RAND:4%`&mdash;un marcador de posición para un número aleatorio de cuatro dígitos.
     > [!NOTE]  
     > Si usa una plantilla de nombre de dispositivo, el proceso OOBE reinicia el dispositivo una vez después de aplicar el nombre del dispositivo y antes de unir el dispositivo a Azure AD. Este reinicio permite que el nuevo nombre surta efecto.  

   > [!div class="mx-imgBorder"]
   > ![Configurar las opciones de OOBE.](./images/hololens-ap-profile-oobe.png)

1. Una vez configuradas las opciones, seleccione **Siguiente**.
1. En la página **Etiquetas de ámbito**, también puede agregar las etiquetas de ámbito que quiera aplicar a este perfil. Para obtener más información sobre las etiquetas de ámbito, consulte [Use role-based access control and scope tags for distributed IT](/mem/intune/fundamentals/scope-tags.md) (Uso del control de acceso basado en roles y de las etiquetas de ámbito para la TI distribuida). Cuando termine, seleccione **Siguiente**.
1. En la página **Asignaciones**, seleccione **Grupos seleccionados** para **Asignar a**.
1. En **GRUPOS SELECCIONADOS**, elija **+ Seleccionar grupos para incluir**.
1. En la lista **Seleccionar grupos para incluir**, elija el grupo de dispositivos que ha creado para los dispositivos HoloLens de Autopilot y seleccione **Siguiente**.  
  
   Para excluir algún grupo, elija **Seleccionar grupos para excluir** y seleccione los grupos que quiera excluir.

   > [!div class="mx-imgBorder"]
   > ![Asignación de un grupo de dispositivos al perfil.](./images/hololens-ap-profile-assign-devicegroup.png)

1. En la página **Revisar y crear**, revise la configuración y seleccione **Crear** para crear el perfil.  

   > [!div class="mx-imgBorder"]
   > ![Revisar y crear.](./images/hololens-ap-profile-summ.png)

### <a name="7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group"></a>7. Cree la configuración de la página de estado de inscripción (ESP) y asígnela al grupo de dispositivos

En la página de estado de inscripción (ESP) se muestra el estado de todo el proceso de configuración de dispositivos que se ejecuta cuando un usuario administrado por MDM inicia sesión en un dispositivo por primera vez. Asegúrese de que la configuración de ESP sea similar a la siguiente y compruebe que las tareas sean correctas.  

> [!div class="mx-imgBorder"]
> ![Configuración de ESP.](./images/hololens-ap-profile-settings.png)

Para obtener más información sobre ESP, consulte [Configuración de la página de estado de la inscripción: Microsoft Intune | Microsoft Docs](/mem/intune/enrollment/windows-enrollment-status).

### <a name="8-verify-the-profile-status-of-the-hololens-devices"></a>8. Compruebe el estado del perfil de los dispositivos HoloLens

1. En el centro de administración de Microsoft Endpoint Manager, seleccione **Dispositivos** > **Windows** > **Inscripción de Windows** > **Dispositivos**.

1. Compruebe que los dispositivos HoloLens aparezcan en la lista y que el estado del perfil sea **Asignado**.  

   > [!NOTE]  
   > El perfil puede tardar unos minutos en asignarse al dispositivo.  

   > [!div class="mx-imgBorder"]
   > ![Asignaciones de dispositivo y perfil.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Experiencia de usuario de Windows Autopilot para HoloLens 2

Una vez que complete las instrucciones anteriores, sus usuarios de HoloLens 2 tendrán acceso a la siguiente experiencia para aprovisionar su dispositivo HoloLens:  

1. La experiencia de Autopilot requiere acceso a Internet. Use una de las siguientes opciones para proporcionar acceso a Internet:

    - Conecte el dispositivo a una red Wi-Fi en la OOBE y, a continuación, deje que detecte la experiencia de Autopilot automáticamente. Este es el único momento en que tendrá que interactuar con la OOBE hasta que la experiencia de Autopilot se complete por sí sola. De forma predeterminada, HoloLens 2 espera 10 segundos para detectar Autopilot después de detectar la conexión a Internet. Si transcurridos diez segundos no detecta ningún perfil de Autopilot, la OOBE mostrará el CLUF. Si se da este caso, reinicie el dispositivo para intentar detectar de nuevo Autopilot. Tenga también presente que la OOBE solo puede esperar indefinidamente para detectar Autopilot si se ha definido la directiva TenantLockdown en el dispositivo.

    - Conecte el dispositivo con Ethernet usando adaptadores de USB-C a Ethernet para disfrutar de conectividad a Internet por cable y deje que HoloLens 2 complete automáticamente la experiencia de Autopilot.

    - Conecte el dispositivo usando adaptadores de USB-C a Wi-Fi para disfrutar de conectividad a Internet sin cable y deje que HoloLens 2 complete automáticamente la experiencia de Autopilot.

        > [!IMPORTANT]  
       > Los dispositivos que intenten usar redes Wi-Fi en la OOBE para Autopilot deben estar en la [versión 20H2 de Windows Holographic](hololens-release-notes.md#windows-holographic-version-20h2).
       >
       > En el caso de dispositivos que usen adaptadores Ethernet, debe conectarlos a la red antes de que se inicie la experiencia inmediata (OOBE). El dispositivo determina si se aprovisiona como dispositivo de Autopilot mientras se encuentra en la primera pantalla de la OOBE. Si el dispositivo no se puede conectar a la red, o bien si usted opta por no aprovisionarlo como dispositivo de Autopilot, no podrá cambiarlo posteriormente al aprovisionamiento de Autopilot. En su lugar, tendría que iniciar este procedimiento para poder aprovisionarlo como dispositivo de Autopilot.

1. El dispositivo debería iniciar automáticamente la OOBE. No interactúe con la OOBE.

    > [!IMPORTANT]
    > No interactúe con la OOBE ni presione el botón de encendido para poner el sistema en espera ni apagarlo mientras Autopilot está en curso. Esto puede hacer que el flujo de Autopilot no se complete.

   Deje que HoloLens 2 detecte la conectividad de red y complete la OOBE automáticamente. Es posible que el dispositivo se reinicie durante la OOBE. Las pantallas de la OOBE deben tener un aspecto similar al siguiente.

   ![Paso 1 de OOBE.](./images/autopilot-welcome.jpg)
   ![Paso 2 de OOBE.](./images/autopilot-step-complete.jpg)
   ![Paso 3 de OOBE.](./images/autopilot-device-setup.jpg)

1. Al final de OOBE, puede iniciar sesión en el dispositivo con su nombre de usuario y contraseña.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenant-lockdown-csp-and-autopilot"></a>TenantLockdown CSP y Autopilot

Los dispositivos HoloLens 2 admiten TenantLockdown CSP en la versión 20H2 de Windows Holographic. Este CSP mantiene los dispositivos en el inquilino de la organización bloqueándolos en este, incluso en caso de restablecimiento o reprogramación del dispositivo.

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP permite que HoloLens 2 se vincule a la inscripción de MDM usando solo Autopilot. Una vez que el nodo RequireNetworkInOOBE de TenantLockdown CSP se establezca con un valor "true" o "false" (establecido inicialmente) en HoloLens 2, el valor permanecerá en el dispositivo incluso en caso de reprogramación, actualización del sistema operativo, etc.

Si el nodo RequireNetworkInOOBE de TenantLockdown CSP se establece con un valor "true" en HoloLens 2, la OOBE esperará indefinidamente a que el perfil de Autopilot se descargue y aplique correctamente, después de conectarse a la red.

Si el nodo RequireNetworkInOOBE de TenantLockdown CSP se establece con un valor "true" en HoloLens 2, no se permitirán las siguientes operaciones en la OOBE:

- Creación de usuarios locales mediante aprovisionamiento en el tiempo de ejecución 
- Realización de operaciones de unión de Azure AD mediante aprovisionamiento en el tiempo de ejecución 
- Selección del propietario del dispositivo en la experiencia OOBE 

#### <a name="how-to-set-this-using-intune"></a>¿Cómo se configura con Intune? 
1. Cree un perfil de configuración de dispositivos OMA-URI personalizado y especifique "true" para el nodo RequireNetworkInOOBE, tal y como se muestra a continuación.
El valor OMA-URI debe ser "./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE".

   > [!div class="mx-imgBorder"]
   > ![Configuración de un bloqueo de inquilinos mediante OMA-URI.](images/hololens-tenant-lockdown.png)

1. Cree un grupo de dispositivos y asígnele el perfil de configuración de dispositivos.

1. Haga que el dispositivo HoloLens 2 sea miembro del grupo creado en el paso anterior y desencadene la sincronización.  

Compruebe en el portal de Intune que la configuración de dispositivos se haya aplicado correctamente. Una vez que la configuración de dispositivos se aplique correctamente al dispositivo HoloLens 2, se activarán los efectos de TenantLockdown.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>¿Cómo se desactiva el nodo RequireNetworkInOOBE de TenantLockdown en HoloLens 2 usando Intune?

1. Quite HoloLens 2 del grupo de dispositivos al que ha asignado anteriormente la configuración creada.

1. Cree un perfil de configuración de dispositivos basado en OMA-URI personalizado y especifique false para RequireNetworkInOOBE, tal y como se muestra a continuación.
El valor OMA-URI debe ser "./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE".

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla en la que RequireNetworkInOOBE se establece en "false" mediante OMA-URI en Intune.](images/hololens-tenant-lockdown-false.png)

1. Cree un grupo de dispositivos y asígnele el perfil de configuración de dispositivos. 

1. Haga que el dispositivo HoloLens 2 sea miembro del grupo creado en el paso anterior y desencadene la sincronización.

Compruebe en el portal de Intune que la configuración de dispositivos se haya aplicado correctamente. Una vez que la configuración de dispositivos se aplique correctamente al dispositivo HoloLens 2, se desactivarán los efectos de TenantLockdown.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>¿Qué sucedería durante la OOBE si el perfil de Autopilot no está asignado a un HoloLens después de haber establecido en "true" TenantLockdown? 
La OOBE esperará indefinidamente a que se descargue el perfil de Autopilot y se mostrará el siguiente cuadro de diálogo. Para eliminar los efectos de TenantLockdown, el dispositivo debe haberse inscrito primero con su inquilino usando únicamente Autopilot, y RequireNetworkInOOBE debe haberse desactivado tal y como se describe en el paso anterior, antes de que se eliminen las restricciones introducidas por TenantLockdown CSP.

![Vista en el dispositivo cuando se aplica en este la directiva.](images/hololens-autopilot-lockdown.png)

## <a name="known-issues--limitations"></a>Limitaciones y problemas conocidos

- Estamos investigando un problema por el que la instalación de aplicaciones basadas en el contexto del dispositivo en MEM no se aplica a HoloLens. [Obtenga más información sobre el contexto del dispositivo y las instalaciones de contexto del usuario.](/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Al configurar Autopilot a través de Wi-Fi, es posible que haya una instancia en la que no se descargue el perfil de Autopilot cuando se establezca por primera vez la conexión a Internet. En este caso, se mostrará el Contrato de licencia de usuario final (CLUF), y el usuario tendrá la opción de continuar con la experiencia de configuración ajena a Autopilot. Para volver a intentar la configuración con Autopilot, suspenda el dispositivo y después enciéndalo, o bien reinícielo y vuelva a intentarlo.

### <a name="troubleshooting"></a>Solución de problemas

Los siguientes artículos pueden ser un recurso útil para obtener más información y solucionar problemas de Autopilot. No obstante, se basan en el escritorio de Windows 10 y es posible que no toda la información sea aplicable a HoloLens:

- [Windows Autopilot: problemas conocidos](/mem/autopilot/known-issues)
- [Solución de problemas con la inscripción de dispositivos Windows en Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot: conflictos de directivas](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Comentarios y soporte técnico para Autopilot

Para proporcionar comentarios o informar de problemas, aplique uno de los siguientes métodos:

- Para obtener asistencia con el registro de dispositivos, póngase en contacto con el revendedor o distribuidor.
- Si tiene consultas de soporte generales sobre Windows Autopilot o desea informar de problemas, por ejemplo, con asignaciones de perfiles, la creación de grupos o los controles del portal de MEM, [póngase en contacto con el soporte de Microsoft Endpoint Manager](/mem/get-support).  
- Si el dispositivo está registrado en el servicio Autopilot y el perfil está asignado en el portal de MEM, póngase en contacto con el [soporte](/hololens/) de HoloLens (véase la tarjeta "Soporte"). Abra un vale de soporte y, si procede, incluya capturas de pantalla y registros mediante la captura de [registros de diagnósticos sin conexión](hololens-diagnostic-logs.md#offline-diagnostics) durante la configuración rápida (OOBE).
- Para informar de un problema desde el dispositivo, use la aplicación Centro de opiniones en HoloLens. En Centro de opiniones, seleccione la categoría **Administración empresarial** > **Dispositivo**.
- Para proporcionar comentarios generales sobre Autopilot para HoloLens, puede enviar [esta encuesta](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993).

## <a name="delete-autopilot-devices"></a>Eliminación de dispositivos Autopilot

Es posible que ya no quiera usar un dispositivo para Autopilot ni registrar los dispositivos en otro inquilino. Si quiere hacerlo, lea el artículo sobre [cómo eliminar los dispositivos de Autopilot.](/mem/autopilot/add-devices#delete-autopilot-devices)