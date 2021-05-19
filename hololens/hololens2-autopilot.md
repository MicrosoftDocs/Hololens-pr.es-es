---
title: Windows Autopilot para HoloLens 2
description: Aprende a configurar y solucionar problemas de Autopilot en dispositivos HoloLens 2.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/13/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: jarrettr
ms.openlocfilehash: 23cb3612a633f6747c770d9fd52b137561492426
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284041"
---
# Windows Autopilot para HoloLens 2

A partir de la versión 2004 de Windows Holographic, HoloLens 2 es compatible con Windows Autopilot [Deployment](https://docs.microsoft.com/mem/autopilot/self-deploying). Los administradores pueden configurar la configuración rápida (OOBE) en Microsoft Endpoint Manager y permitir que los usuarios finales preparen dispositivos para su uso empresarial con una interacción escasa o nula. Esto reduce la sobrecarga de la administración de inventario, el costo de la preparación de dispositivos prácticos y las llamadas de soporte técnico de los empleados durante la experiencia de configuración. Obtén más información en la [documentación de Windows Autopilot.](https://docs.microsoft.com/mem/autopilot/windows-autopilot)

Al igual que en el caso de los dispositivos Surface, se recomienda que los clientes trabajen con su [proveedor de soluciones en la nube](https://partner.microsoft.com/cloud-solution-provider) de Microsoft (revendedor o distribuidor) para obtener dispositivos registrados con el servicio AutoPilot a través del Centro de partners. En la documentación de [Agregar dispositivo](https://docs.microsoft.com/mem/autopilot/add-devices) se describen otros métodos para el registro de dispositivos. Si embargo, la ruta de acceso de un extremo a otro más eficaz es usar los partners de canales de Microsoft.

> [!NOTE]
> Por lo que respecta a la configuración de Autopilot del 20 de noviembre de 2020 para HoloLens en Microsoft Endpoint Manager, está en transición a la **Versión preliminar pública**. Los clientes ya no necesitan inscribirse en la versión preliminar privada y todos los servicios empresariales podrán configurar Autopilot desde el centro de administración de MEM.

Cuando un usuario inicia el proceso de autoimplementado de Autopilot, AutoPilot realiza los pasos siguientes:

1. Unir el dispositivo a Azure Active Directory (Azure AD). Ten en cuenta que AutoPilot para HoloLens no admite una unión con Active Directory o Azure AD híbrido.

1. Usa Azure AD para inscribir el dispositivo en Microsoft Endpoint Manager (u otro servicio MDM).

1. Descargar y aplicar directivas, certificados, perfiles de red y aplicaciones enfocadas en dispositivos.

1. Aprovisionar el dispositivo.

1. Mostrar la pantalla de inicio de sesión al usuario.

## Configuración de Autopilot para HoloLens 2

Sigue los pasos que se indican a continuación para configurar el entorno:

1. [Revisar los requisitos de Windows AutoPilot para HoloLens 2.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Habilitar la inscripción automática de MDM](#2-enable-automatic-mdm-enrollment)

1. [Registrar dispositivos en Windows Autopilot.](#3-register-devices-in-windows-autopilot)

1. [Crear un grupo de dispositivos.](#4-create-a-device-group)

1. [Crear un perfil de implementación.](#5-create-a-deployment-profile)

1. [Comprueba la configuración de la página de estado de inscripción (ESP).](#6-verify-the-esp-configuration)

1. [Comprueba el estado del perfil de los dispositivos HoloLens.](#7-verify-the-profile-status-of-the-hololens-devices)

### 1. Revisar los requisitos de Windows AutoPilot para HoloLens 2

#### Consulta las secciones siguientes del artículo sobre los requisitos de Windows Autopilot:

- [Requisitos de red](https://docs.microsoft.com/mem/autopilot/networking-requirements)  
- [Requisitos de licencias](https://docs.microsoft.com/mem/autopilot/licensing-requirements)  
- [Requisitos de configuración](https://docs.microsoft.com/mem/autopilot/configuration-requirements)

**Consulta la sección "[Requisitos](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" del artículo Modo de implementación automática de Windows Autopilot.** El entorno tiene que cumplir estos requisitos, así como los requisitos estándar del Windows Autopilot. No es necesario revisar las secciones "Paso a paso" y "Validación" del artículo. Los procedimientos que se describen más adelante en este artículo proporcionan los pasos correspondientes específicos para HoloLens.

Para obtener más información sobre cómo registrar dispositivos y configurar perfiles, consulta [2. Registrar dispositivos en Windows AutoPilot](#3-register-devices-in-windows-autopilot) y [4. Crea un perfil de implementación](#5-create-a-deployment-profile) en este artículo. Para configurar y administrar los perfiles del modo de implementación automática de Autopilot, asegúrate de que tienes acceso al [Centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com).

#### Revisar los requisitos del sistema operativo HoloLens:

- Los dispositivos deben estar en [Windows Holographic, versión 2004](hololens-release-notes.md#windows-holographic-version-2004) (compilación 19041.1103) o posterior. Para confirmar la versión de compilación del dispositivo o volver a abrir el SO más reciente, usa el [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) y nuestras [instrucciones para devolver el flash del dispositivo](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device). Ten en cuenta que los dispositivos entregados hasta finales de septiembre de 2020 tienen la versión 1903 de Windows Holographic preinstalada. Comunícate con tu revendedor para asegurarte de que te envíen dispositivos preparados para Autopilot.

- Windows Holographic, versión 2004 solo admite Autopilot a través de conexión Ethernet. Asegúrate de que HoloLens esté conectado a Ethernet mediante un adaptador "USB-C a Ethernet" **antes de activarlo**. Al arrancar el dispositivo no es necesaria ninguna interacción con el usuario. Si estás planeando la implantación de un piloto automático en muchos dispositivos HoloLens, te recomendamos que planees la infraestructura del adaptador. No recomendamos concentradores USB, ya que, a menudo, es necesario instalar controladores de terceros adicionales que no son compatibles con HoloLens.

- [Windows Holographic, versión 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (compilación 19041.1128) o versiones posteriores, son compatibles con Autopilot a través de Wi-Fi, aunque también puede seguir usando adaptadores Ethernet. Para los dispositivos conectados a través de Wi-Fi, el usuario solo debes:

     - Ir a la escena del colibrí
     - Elegir el idioma y la configuración regional
     - Ejecutar calibración de ojos
     - Establecer conexión de red

- Windows Holographic, versión 20H2 es compatible con [Tenantlockdown CSP y Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot), el cual bloquea un dispositivo en un espacio empresarial y garantiza que el dispositivo permanezca enlazado a ese espacio empresarial en caso de restablecimientos o borrados accidentales o intencionados.  

- Asegúrate de que los dispositivos no sean ya miembros de Azure AD y de que no se hayan inscrito en Intune (u otro sistema MDM). El proceso de implementación automática de Autopilot completa estos pasos. Para asegurarte de que toda la información relacionada con los dispositivos se ha eliminado, activa la casilla de verificación **Dispositivos** en las páginas de los portales de Azure AD e Intune. Ten en cuenta que HoloLens no admite la característica "Convertir todos los dispositivos de destino en AutoPilot" en este momento.  

### 2. Habilitar la inscripción automática de MDM:

Para que Autopilot funcione correctamente, tendrás que habilitar la inscripción automática de MDM en Azure Portal. Esto permitirá que el dispositivo se inscriba sin necesidad de un usuario.

En [Azure Portal](https://portal.azure.com/#home), selecciona **Azure Active Directory**  ->  **Mobility (MDM y MAM)**  ->  **Microsoft Intune**. Después, configura el **ámbito de usuario de MDM**, donde tendrás que seleccionar **Todo**.

Consulta la siguiente guía breve sobre [Cómo habilitar la inscripción automática de MDM](https://docs.microsoft.com/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) o la [Guía de inicio rápido de inscripción automática](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment) para obtener más información sobre la configuración.

### 3. Registrar dispositivos en Windows AutoPilot

#### Obtener el hash de hardware

Los dispositivos deben estar registrados en Windows AutoPilot antes de la primera configuración. Para la documentación de MEM en el registro de dispositivos, consulta [Agregar dispositivos a AutoPilot](https://docs.microsoft.com/mem/autopilot/add-devices).  

Hay dos formas principales de registrar dispositivos HoloLens:

 - **El revendedor puede registrar dispositivos en el Centro de partners cuando realice un pedido.**

   > [!NOTE]  
   > Esta es la ruta recomendada para agregar dispositivos al servicio AutoPilot. [Más información](https://docs.microsoft.com/mem/autopilot/add-devices#reseller-distributor-or-partner-registration).  

 - **Recupera el hash de hardware (también conocido como el id. de hardware) y registra manualmente el dispositivo en el centro de administración de MEM**.

- **Recuperar el hash de hardware**

El dispositivo registra su hash de hardware en un archivo CSV durante el proceso OOBE o, posteriormente, cuando el propietario de un dispositivo inicia el proceso de recopilación del registro de diagnóstico (se describe en el siguiente procedimiento). Por lo general, el propietario del dispositivo es el primer usuario que inicia sesión en el mismo.

1. Iniciar el dispositivo HoloLens 2.

1. En el dispositivo, pulsa los botones de **Encendido** y **Apagado** al mismo tiempo y, después, suéltelos. El dispositivo recoge tanto los registros de diagnóstico como el hash del hardware y los almacena en un conjunto de archivos comprimidos .zip.

   1. Para obtener más detalles y un vídeo informativo sobre cómo hacerlo, lee acerca de los [diagnósticos sin conexión](hololens-diagnostic-logs.md#offline-diagnostics).

1. Usa un cable USB-C para conectar el dispositivo al equipo.

1. En el equipo, abre el explorador de archivos. Abra la carpeta **Esta PC\\ \<*HoloLens device name*>\\Almacenamiento interno\\Documentos**, y localice el archivo AutopilotDiagnostics.zip.  

   > [!NOTE]  
   > Puede que el archivo .zip no esté disponible inmediatamente. Si el archivo aún no está listo, es posible que veas el archivo HoloLensDiagnostics.temp en la carpeta Documentos. Para actualizar la lista de archivos, actualiza la ventana.

1. Extrae el contenido del archivo AutopilotDiagnostics.zip.

1. En los archivos extraídos, busca el archivo CSV con el prefijo de nombre de archivo "DeviceHash". Copia el archivo en una unidad del equipo en la que puedas obtener acceso a él más adelante.  

   > [!IMPORTANT]  
   > Los datos en el archivo CSV deben usar el siguiente formato de línea y encabezado:
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

#### Registrar dispositivo a través de MEM

1. En el [Centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com), selecciona **Dispositivos** > **Windows** > **Inscripción de Windows**y, a continuación, haz clic en **Dispositivos** > **Importar** bajo el **Programa de Windows Autopilot Deployment**.

1. En **Agregar dispositivos de Windows Autopilot**, selecciona el archivo CSV DeviceHash, selecciona **Abrir** y selecciona **Importación**.  

   > [!div class="mx-imgBorder"]
   > ![Usa el comando Importar para importar el hash de hardware.](./images/hololens-ap-hash-import.png)

1. Cuando finalice la importación, selecciona **Dispositivos** > **Windows** > **Inscripción de Windows** > **Dispositivos** > **Sincronizar**. Este proceso puede tardar unos minutos en completarse, en función del número de dispositivos que se sincronizan. Para ver el dispositivo registrado, selecciona **Actualizar**.  

   > [!div class="mx-imgBorder"]
   > ![Usa los comandos Sync y Refresh para ver la lista de dispositivos.](./images/hololens-ap-devices-sync.png)  

### 4. Crear un grupo de dispositivos

1. En el [Centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com), selecciona **Grupos** > **Nuevo grupo**.

1. Para **Tipo de grupo**, selecciona **Seguridad** y, a continuación, escribe un nombre de grupo y una descripción.

1. Para **Tipo de suscripción**, selecciona **Asignada** o **Dspositivo dinámico**.

1. Realiza una de las siguientes acciones:  

   - Si seleccionaste **Asignada** para **Tipo de suscripción** en el paso anterior, selecciona **Miembros** y agrega dispositivos Autopilot al grupo. Los dispositivos de Autopilot que no se han inscrito se muestran con el número de serie del dispositivo como el nombre del dispositivo.
   - Si seleccionaste **Dispositivos dinámicos** para **Tipo de suscripción** en el paso anterior, selecciona **Miembros de dispositivo dinámico** y escribe el código en **Regla avanzada** que se asemeje a lo siguiente:
     - Si quieres crear un grupo que incluya todos los dispositivos de Autopilot, escribe: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - El campo de la etiqueta de grupo de Intune se asigna al atributo **IdPedido** en los dispositivos de Azure AD. Si quieres crear un grupo que incluya todos los dispositivos de Autopilot que tienen una etiqueta de grupo específica (el IdPedido del dispositivo de Azure AD), debes escribir: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Si quieres crear un grupo que incluya todos los dispositivos Autopilot que tengan un ID. de pedido de compra específico, escribe lo siguiente: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Estas reglas buscan atributos que son exclusivos de dispositivos Autopilot.
1. Selecciona **Aceptar** y, a continuación, selecciona **Crear**.

### 5. Crear un perfil de implementación

1. In el [Centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com), selecciona **Dispositivos** > **Windows** > **Inscripción de Windows** > **Perfiles de implementación de Windows Autopilot** > **Crear perfil** > **HoloLens**.
   ![La lista desplegable Crear perfil incluye un elemento HoloLens.](./images/hololens-ap-enrollment-profiles.png)

1. Escribe un nombre y una descripción para el perfil y selecciona **Siguiente**.  
   Deberías ver una lista que incluya **HoloLens**. Si esta opción no está disponible, utiliza una de las opciones de [Comentarios](hololens2-autopilot.md#feedback-and-support-for-autopilot) para ponerte en contacto con nosotros.

   > [!div class="mx-imgBorder"]
   > ![Agrega un nombre y una descripción para el perfil](./images/hololens-ap-profile-name.png)

1. En la página de la **configuración rápida (OOBE)**, la mayoría de las opciones están preconfiguradas para simplificar la configuración rápida para esta evaluación. Opcionalmente, puedes configurar los valores siguientes:  

   - **Idioma (región)**: selecciona el idioma para OOBE. Recomendamos que selecciones un idioma de la lista de [idiomas compatibles con HoloLens 2](hololens2-language-support.md).
   - **Configura el teclado automáticamente**: para asegurarte de que el teclado coincide con el idioma seleccionado, selecciona **Sí**.
   - **Aplicar la plantilla nombre del dispositivo**: para establecer el nombre del dispositivo automáticamente durante la OOBE, selecciona **Sí** y escribe la frase y los marcadores de posición de la plantilla en **Escribe un nombre** Por ejemplo, especifica un prefijo y `%RAND:4%`&mdash;un marcador de posición para un número aleatorio de cuatro dígitos.
     > [!NOTE]  
     > Si usas una plantilla de nombre de dispositivo, el proceso OOBE reinicia el dispositivo una vez más después de aplicar el nombre del dispositivo y antes de que una el dispositivo a Azure AD. Este reinicio permite que el nuevo nombre surta efecto.  

   > [!div class="mx-imgBorder"]
   > ![Configura las opciones de OOBE](./images/hololens-ap-profile-oobe.png)

1. Después de configurar la configuración, selecciona **Siguiente**.
1. En la página **Etiquetas de ámbito**, puedes agregar las etiquetas de ámbito que quieras aplicar a este perfil. Para más información sobre las etiquetas de ámbito, consulta [Usar control de acceso basado en roles y etiquetas de ámbito para TI distribuida](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md). Cuando termines, haz clic en **Siguiente**.
1. En la página **Asignaciones**, selecciona **Grupos seleccionados** para **Asignar a**.
1. En **Grupos seleccionados**, selecciona **+ Seleccionar grupos para incluir**.
1. En la lista **Seleccionar grupos para incluir**, selecciona el grupo de dispositivos que creaste para los dispositivos de Hololens de Autopilot y selecciona **Siguiente**.  
  
   Si quieres excluir grupos, selecciona **Seleccionar grupos para excluir** y selecciona los grupos que quieres excluir.

   > [!div class="mx-imgBorder"]
   > ![Asignación de un grupo de dispositivos al perfil.](./images/hololens-ap-profile-assign-devicegroup.png)

1. En la página **Revisar y crear**, revisa la configuración y selecciona **Crear** para crear el perfil.  

   > [!div class="mx-imgBorder"]
   > ![Revisar y crear](./images/hololens-ap-profile-summ.png)

### 6. Comprobar la configuración de ESP

La página de estado de inscripción (ESP) muestra el estado de todo el proceso de configuración de dispositivos que se ejecuta cuando un usuario administrado por MDM inicia sesión en un dispositivo por primera vez. Asegúrate de que la configuración ESP es similar a la siguiente y comprueba que las tareas sean correctas.  

> [!div class="mx-imgBorder"]
> ![Configuración de ESP](./images/hololens-ap-profile-settings.png)

### 7. Comprobar el estado del perfil de los dispositivos HoloLens

1. En el Centro de administración de Microsoft Endpoint Manager, selecciona **Dispositivos** > **Windows** > **Inscripción de Windows** > **Dispositivos**.

1. Comprueba que los dispositivos HoloLens se muestran en la lista y que el estado del perfil es **Asignado**.  

   > [!NOTE]  
   > El perfil puede tardar unos minutos en asignarse al dispositivo.  

   > [!div class="mx-imgBorder"]
   > ![Asignaciones de dispositivo y perfil.](./images/hololens-ap-devices-assignments.png)

## Experiencia de usuario de Windows AutoPilot para HoloLens 2

Una vez que completes las instrucciones anteriores, tus usuarios de HoloLens 2 tendrán acceso a la siguiente experiencia para aprovisionar sus dispositivos HoloLens:  

1. La experiencia de Autopilot requiere acceso a Internet. Usa una de las siguientes opciones para proporcionar acceso a Internet:

    - Conecta el dispositivo a una red Wi-Fi en configuración rápida y, a continuación, deja que detecte la experiencia de Autopilot de manera automática. Este es el único momento en que tendrás que interactuar con la configuración rápida hasta que la experiencia de Autopilot se complete por sí sola. Ten en cuenta que, de forma predeterminada, HoloLens 2 espera 10 segundos para detectar el Autopilot después de detectar la conexión a Internet. Si después de 10 segundo no detecta ningún perfil de Autopilot, la configuración rápida presentará el CLUF. Si esto sucede, reinicia el dispositivo para intentar detectar de nuevo el Autopilot. Ten en cuenta también que la configuración rápida solo puede esperar de manera indefinidamente hasta detectar el Autopilot si la directiva TenantLockdown está configurada en el dispositivo.

    - Conecta el dispositivo con Ethernet con adaptadores "USB-C a Ethernet" para conectarte a Internet por cable y deja que HoloLens 2 complete de manera automática la experiencia de Autopilot.

    - Conecta el dispositivo con adaptadores de "USB-C a WiFi" para establecer una conexión inalámbrica a Internet y deja que HoloLens 2 complete de manera automática la experiencia de Autopilot.

        > [!IMPORTANT]  
       > Los dispositivos que intenten usar las redes Wi-Fi en la configuración rápida para el Autopilot deben disponer de la [versión 20H2 de Windows Holographic](hololens-release-notes.md#windows-holographic-version-20h2).
       >
       > Para los dispositivos que usan adaptadores Ethernet, debes conectar el dispositivo a la red antes de que se inicie la experiencia de configuración rápida. El dispositivo determina si se aprovisiona como dispositivo Autopilot mientras se encuentra en la primera pantalla de la configuración rápida. Si el dispositivo no se puede conectar a la red, o si eliges no aprovisionar el dispositivo como dispositivo Autopilot, no podrás cambiarlo posteriormente al aprovisionamiento de Autopilot. En su lugar, tendrías que iniciar este procedimiento para poder aprovisionar el dispositivo como dispositivo Autopilot.

1. El dispositivo debería iniciar automáticamente OOBE. No interactúes con OOBE. En su lugar, siéntate y relájate. Deje que HoloLens 2 detecte la conectividad de red y permite que complete la OOBE automáticamente. Es posible que el dispositivo se reinicie durante la OOBE. Las pantallas de OOBE deben tener un aspecto similar al siguiente.

   ![OOBE paso 1](./images/autopilot-welcome.jpg)
   ![OOBE paso 2](./images/autopilot-step-complete.jpg)
   ![OOBE paso 3](./images/autopilot-device-setup.jpg)

1. Al final de OOBE, puedes iniciar sesión en el dispositivo con tu nombre de usuario y contraseña.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## Tenantlockdown CSP y Autopilot

Los dispositivos HoloLens 2 son compatibles con TenantLockdown CSP en Windows Holographic, versión 20H2. Este CSP mantiene los dispositivos en el espacio empresarial de la organización al bloquearlos en ese espacio empresarial, incluso a través del restablecimiento del dispositivo o el formateo.

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP permite que HoloLens 2 se vincule a la inscripción de MDM únicamente con el Autopilot. Una vez que el nodo RequireNetworkInOOBE de TenantLockdown CSP se active o desactive (configurado inicialmente) en HoloLens 2, permanecerá así el dispositivo aunque se vuelva a formatear, a actualizar el sistema operativo, etc.

Una vez que el nodo RequireNetworkInOOBE de TenantLockdown CSP se active o desactive (configurado inicialmente) en HoloLens 2, la configuración rápida espera indefinidamente que el perfil de Autopilot se descargue y aplique correctamente, después de conectarse a la red.

Una vez que el nodo RequireNetworkInOOBE de TenantLockdown de CSP se active o desactive en HoloLens 2, no se permitirán las siguientes operaciones en la configuración rápida:

- Crear usuarios locales mediante aprovisionamiento en el tiempo de ejecución 
- Realizar una operación de replica de Azure AD mediante aprovisionamiento en el tiempo de ejecución 
- Seleccionar quién es el propietario del dispositivo en la experiencia de la configuración rápida 

#### ¿Cómo configurarlo con Intune? 
1. Crea un perfil de configuración de dispositivos OMA URI personalizado y activa el nodo RequireNetworkInOOBE como se hace a continuación.
El valor OMA-URI debe ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Configuración del bloqueo de inquilinos a través de OMA-URI](images/hololens-tenant-lockdown.png)

1. Crea un grupo y asigna el perfil de configuración del dispositivo a ese grupo de dispositivos.

1. Haz que el dispositivo HoloLens 2 sea un miembro del grupo creado en el paso anterior y desencadena la sincronización.  

Comprueba en el portal de Intune que la configuración del dispositivo se ha aplicado correctamente. Una vez que la configuración del dispositivo se aplique correctamente en el dispositivo HoloLens 2, los efectos de TenantLockdown estarán activos.

#### ¿Cómo se anula el nodo RequireNetworkInOOBE de TenantLockdown en HoloLens 2 con Intune?

1. Quita HoloLens 2 del grupo de dispositivos a los que asignó la configuración creada anteriormente.

1. Crea un perfil de configuración de dispositivos basado en OMA URI personalizado y desconecte RequireNetworkInOOBE como se hace a continuación.
El valor OMA-URI debe ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla de la configuración para desconectar RequireNetworkInOOBE a través de OMA URI en Intune](images/hololens-tenant-lockdown-false.png)

1. Crea un grupo y asigna el perfil de configuración del dispositivo a ese grupo de dispositivos. 

1. Haz que el dispositivo HoloLens 2 sea un miembro del grupo creado en el paso anterior y desencadena la sincronización.

Comprueba en el portal de Intune que la configuración del dispositivo se ha aplicado correctamente. Una vez que la configuración del dispositivo se aplique correctamente en el dispositivo HoloLens 2, los efectos de TenantLockdown estarán inactivos.

#### ¿Qué sucedería durante la configuración rápida si el perfil de Autopilot no está asignado a un HoloLens después de haber activado TenantLockdown? 
La configuración rápida esperará indefinidamente a que se descargue el perfil de Autopilot y a que aparezca el siguiente cuadro de diálogo. Para eliminar los efectos de TenantLockdown, el dispositivo debe estar antes inscrito en el espacio empresarial original únicamente con el Autopilot y RequireNetworkInOOBE configurarse como desconectado tal y como se describe en el paso anterior antes de que se quiten las restricciones introducidas por TenantLockdown CSP.

![Vista en el dispositivo cuando se aplica la directiva.](images/hololens-autopilot-lockdown.png)

## Problemas conocidos y limitaciones

- Estamos investigando un problema por el que la instalación de aplicaciones basadas en el contexto del dispositivo en MEM no se aplica a HoloLens. [Más información sobre el contexto del dispositivo y las instalaciones de contexto del usuario.](https://docs.microsoft.com/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Al configurar Autopilot a través de Wi-Fi, es posible que haya una instancia en la que no se descargue el perfil de Autopilot cuando se establezca primero la conexión a Internet. En este caso, se presenta el contrato de licencia de usuario final (CLUF) y el usuario tiene la opción de continuar con la experiencia de configuración que no es Autopilot. Para volver a intentar la configuración con Autopilot, pon el dispositivo en suspensión y después enciéndelo, o bien reinícialo y vuelve a intentarlo.
- La característica "convertir todos los dispositivos de destino en AutoPilot" no es compatible con HoloLens en este momento.  

### Solución de problemas

Los siguientes artículos pueden ser un recurso útil para obtener más información y solucionar problemas de Autopilot, pero ten en cuenta que estos artículos se basan en el escritorio de Windows 10 y no toda la información puede aplicarse a HoloLens:

- [Windows Autopilot: problemas conocidos](https://docs.microsoft.com/mem/autopilot/known-issues)
- [Solucionar problemas de inscripción de dispositivos de Windows en Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot: conflictos de directivas](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## Comentarios y soporte técnico para AutoPilot

Para proporcionar comentarios o informar de problemas, sigue uno de los métodos siguientes:

- Para obtener asistencia sobre el registro de dispositivos, comunícate con tu distribuidor o distribuidor.
- Para consultas generales de soporte técnico sobre Windows AutoPilot o para problemas como tareas de perfil, creación de grupos o controles de portal de MEM, [ponte en contacto con el soporte técnico de Microsoft Endpoint Manager](https://docs.microsoft.com/mem/get-support)  
- Si el dispositivo está registrado en el servicio de Autopilot y el perfil está asignado en el portal MEM, ponte en contacto con el [soporte técnico](https://docs.microsoft.com/hololens/) de HoloLens (ver la tarjeta « Soporte»). Abre una incidencia de soporte técnico y, si procede, incluye capturas de pantalla y registros capturando [registros de diagnóstico sin conexión](hololens-diagnostic-logs.md#offline-diagnostics) durante la integración rápida (OOBE).
- Para denunciar un problema desde el dispositivo, usa la aplicación Centro de opiniones en HoloLens. En el Centro de opiniones, selecciona la categoría **Administración empresarial** > **Dispositivo**.
- Para proporcionar comentarios generales sobre Autopilot para HoloLens, puedes enviar esta [encuesta](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)
