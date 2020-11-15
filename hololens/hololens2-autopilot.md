---
title: Windows Autopilot para HoloLens 2 (vista previa)
description: Cómo configurar Autopilot en dispositivos HoloLens 2.
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
ms.openlocfilehash: be9da0ec2f301705a0691bcfc9dcf9d75eac8922
ms.sourcegitcommit: cfbcdf562f949eef9cd797bbb08dfdf9f29e8fcd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "11168555"
---
# Windows Autopilot para HoloLens 2

Cuando configures los dispositivos HoloLens 2 para el programa Windows Autopilot, los usuarios podrán seguir un proceso sencillo para aprovisionar los dispositivos desde la nube.

Este programa de Autopilot es compatible con el modo de implementación automática de Autopilot para aprovisionar dispositivos HoloLens 2 como dispositivos compartidos en su espacio empresarial. El modo de implementación automática aprovecha los controladores y la imagen del OEM preinstalado del dispositivo durante el proceso de aprovisionamiento. Un usuario puede aprovisionar el dispositivo sin tener el dispositivo activado, ni pasar por la experiencia de configuración rápida (OOBE). Para obtener más información sobre Windows Autopilot para Windows 10, haz clic [aquí](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).

Cuando un usuario inicia el proceso de implementación automática de Autopilot, el proceso completa estos pasos:

1. Unir el dispositivo a Azure Active Directory (Azure AD).

   > [!NOTE]  
   > Autopilot para HoloLens no es compatible con la combinación de Active Directory ni Azure AD híbrido.
   
1. Usar Azure AD para inscribir el dispositivo en Microsoft Intune (u otro servicio MDM).

1. Descargar las directivas de destino del dispositivo, las aplicaciones de destino del usuario, los certificados y los perfiles de red.

1. Aprovisionar el dispositivo.

1. Mostrar la pantalla de inicio de sesión al usuario.

## Windows Autopilot para HoloLens 2 (vista previa)

Sigue los pasos que se indican a continuación para configurar el entorno para la vista previa privada:

1. Asegúrate de que cumples con los requisitos para Windows Autopilot para HoloLens 2.

1. Inscríbete en el programa de vista previa privada de Windows Autopilot para HoloLens 2.

1. Comprueba que tu espacio empresarial forme parte del paquete piloto (inscrito para participar en el programa).

1. Registrar tus dispositivos en Windows Autopilot.

1. Crear un grupo de dispositivos.

1. Crear un perfil de implementación

1. Comprueba la configuración de ESP.

1. Configura un perfil de configuración personalizada para dispositivos HoloLens (problema conocido).

1. Comprueba el estado del perfil de los dispositivos HoloLens.


### Asegúrate de que cumples los requisitos para Windows Autopilot para HoloLens 2

**Consulta las secciones siguientes del artículo sobre los requisitos de Windows Autopilot:**

- [Requisitos de red](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)  
- [Requisitos de licencias](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#licensing-requirements)  
- [Requisitos de configuración](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#configuration-requirements)

**Consulta la sección "[Requisitos](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" del artículo Modo de implementación automática de Windows Autopilot.** El entorno tiene que cumplir estos requisitos, así como los requisitos estándar del Windows Autopilot. No es necesario revisar las secciones "Paso a paso" y "Validación" del artículo. Los procedimientos que se describen más adelante en este artículo proporcionan los pasos correspondientes específicos para HoloLens. Para obtener información sobre cómo registrar dispositivos y configurar perfiles, consulta [4. Registra dispositivos en Windows Autopilot](#4-register-devices-in-windows-autopilot) y [6. Crea un perfil de implementación](#6-create-a-deployment-profile) en este artículo. En estas secciones se proporcionan los pasos específicos para HoloLens.

> [!IMPORTANT]  
> Windows Autopilot para HoloLens 2 tiene requisitos de sistema operativo específicos. Autopilot usa la versión 2004 de Windows Holographic (compilación 19041.1103 o posteriores) preinstalada en los dispositivos HoloLens. Los dispositivos entregados hasta finales de septiembre de 2020 vienen con la versión de Windows Holographic 1903 preinstalada. Ponte en contacto con tu distribuidor para saber cuándo te puede enviar dispositivos con Autopilot listo para su uso. Si quieres participar en la previsualización privada, consulta las instrucciones y los requisitos siguientes.

Información específica de Autopilot para las distintas versiones del sistema operativo de HoloLens.
- Para poder usar Autopilot, el dispositivo debe tener [Windows Holographic en la versión 2004](hololens-release-notes.md#windows-holographic-version-2004) o posterior.

- Para poder usar Autopilot por Wi-Fi, el dispositivo debe tener [Windows Holographic en la versión 20H2](hololens-release-notes.md#windows-holographic-version-20h2) o posterior. No obstante, estas compilaciones pueden seguir usando adaptadores Ethernet. 

- En compilaciones de [Windows Holographic, versión 20H2](hololens-release-notes.md#windows-holographic-version-20h2), se ha habilitado [Tenantlockdown CSP y Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot), una nueva opción de administración de dispositivos.  

Ya sea para confirmar la versión de compilación del dispositivo o para actualizarla, conecta tu PC con Windows 10 e inicia el [Asistente de recuperación avanzada](https://www.microsoft.com/store/productId/9P74Z35SFRS8). 

**Si quieres participar en la vista previa de Autopilot, antes de iniciar el proceso de configuración rápida y aprovisionamiento, asegúrate de que los dispositivos HoloLens cumplan los requisitos siguientes:**

- Asegúrate de que tu dispositivo se encuentra en Windows Holographic, versión 2004 (compilación 19041.1103 o posteriores). Si el sistema operativo más reciente no está preinstalado, debes actualizarlo manualmente con el [Asistente de recuperación avanzada (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab). Puedes encontrar instrucciones [aquí](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device). 

- Tus dispositivos deben estar registrados en Windows Autopilot Para obtener información sobre cómo registrar dispositivos, consulta [4. Registrar dispositivos en Windows Autopilot](#4-register-devices-in-windows-autopilot). La ruta de acceso recomendable es que tu revendedor o distribuidor registre estos dispositivos por ti.  

- En la [versión 2004 de Windows Holographic](hololens-release-notes.md#windows-holographic-version-2004), los dispositivos deben estar conectados a Internet antes de activar HoloLens e iniciar el proceso de aprovisionamiento de Autopilot. Conecta el dispositivo a Ethernet con un adaptador "USB-C a Ethernet" para conectarte a Internet por cable.

- En la [versión 20H2 de Windows Holographic](hololens-release-notes.md#windows-holographic-version-20h2), es posible que los dispositivos se conecten al Wi-Fi mediante la configuración rápida para detectar el Autopilot. 

- Los dispositivos aún no son miembros de Azure AD y no se han inscrito en Intune (u otro sistema MDM). El proceso de implementación automática de Autopilot completa estos pasos. Para asegurarte de que toda la información relacionada con los dispositivos se ha eliminado, activa la casilla de verificación **Dispositivos** en las páginas de los portales de Azure AD e Intune.

- Para configurar y administrar los perfiles del modo de implementación automática de Autopilot, asegúrate de que tienes acceso al [centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com).


### 2. Inscríbete en el programa Windows Autopilot para HoloLens 2

**Para participar en el programa, debes tener tu espacio empresarial inscrito en el programa de vista previa privado. Esto activa los controles de IU específicos de HoloLens de Intune (o MEM) para Autopilot.** Para hacerlo, ve a [solicitud de vista previa de Windows AutoPilot para HoloLens](https://aka.ms/APHoloLensTAP) y usa el siguiente código QR para enviar una solicitud.  

![Código QR de Autopilot](./images/hololens-ap-qrcode.png)  

Microsoft lanza espacios empresariales como paquetes piloto una vez a la semana. Recibirás una notificación por correo electrónico cuando tu espacio empresarial forme parte del paquete piloto. 

En esta solicitud, proporciona la siguiente información:

- Dominio del espacio empresarial
- ID. del espacio empresarial
- Número de dispositivos HoloLens 2 que participan en esta evaluación
- Número de dispositivos HoloLens 2 que tienes previsto implementar con el modo de implementación automática de Autopilot

### 3. Comprueba que tu espacio empresarial forma parte del paquete piloto

Para comprobar que su espacio empresarial forma parte del paquete piloto para el programa Autopilot una vez que haya enviado la solicitud, siga estos pasos:

1. Inicia sesión en el [Centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com).

1. Selecciona **Dispositivos** > **Windows** > **Inscripción de Windows** > **Perfiles de implementación de Windows Autopilot** > **Crear perfil**.  
   
   ![La lista desplegable Crear perfil incluye un elemento HoloLens.](./images/hololens-ap-enrollment-profiles.png)
   
   Deberías ver una lista que incluya **HoloLens**. Si esta opción no está disponible, utiliza una de las opciones de [Comentarios](hololens2-autopilot.md#feedback-for-autopilot) para ponerte en contacto con nosotros.

### 4. Registra dispositivos en Windows Autopilot

En la fase de preparación, hay dos formas principales de registrar dispositivos en Windows Autopilot: 

1. **Ponte en contacto con el distribuidor o revendedor cuando hagas tu pedido para que registren tus dispositivos**.

   o
   
2. **Recupera el hash de hardware (también conocido como el identificador de hardware) y registralo manualmente**. 

Para obtener más información sobre el registro de dispositivos, consulta la documentación [Agregar dispositivos a Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices).  

**Recuperar un algoritmo hash de hardware del dispositivo**

El dispositivo puede grabar su hash de hardware en un archivo CSV durante el proceso OOBE, o bien, cuando el propietario de un dispositivo inicia el proceso de recopilación de registros de diagnóstico (descrito en el procedimiento siguiente). Por lo general, el propietario del dispositivo es el primer usuario que inicia sesión en el dispositivo.

1. Inicia el dispositivo HoloLens 2.

1. En el dispositivo, presiona los botones apagar la energía y bajar el volumen al mismo tiempo y luego suéltalos. El dispositivo recoge tanto los registros de diagnóstico como el hash del hardware y los almacena en un archivo comprimido .zip. 

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

**Registra el dispositivo en Windows Autopilot**

1. En el Centro de administración de Microsoft Endpoint Manager, selecciona **Dispositivos** > **Windows** > **Inscripción de Windows** y selecciona **Dispositivos** > ** Importación** en **Programa de implementación de Windows Autopilot**.

1. En **Agregar dispositivos de Windows Autopilot**, selecciona el archivo CSV DeviceHash, selecciona **Abrir** y selecciona **Importación**.  
   
   ![Usa el comando Importar para importar el hash de hardware.](./images/hololens-ap-hash-import.png)
   
1. Cuando finalice la importación, selecciona **Dispositivos** > **Windows** > **Inscripción de Windows** > **Dispositivos** > **Sincronizar**. Este proceso puede tardar unos minutos en completarse, en función del número de dispositivos que se sincronizan. Para ver el dispositivo registrado, selecciona **Actualizar**.  
   
   ![Use los comandos Sync y Refresh para ver la lista de dispositivos.](./images/hololens-ap-devices-sync.png)  

### 5. Crea un grupo de dispositivos

1. En el Centro de administración de Microsoft Endpoint Manager, selecciona **Grupos** > **Nuevo grupo**.

1. Para **Tipo de grupo**, selecciona **Seguridad** y escribe un nombre de grupo y una descripción.

1. Para **Tipo de suscripción**, selecciona **Asignada** o **Dspositivo dinámico**.

1. Realiza una de las siguientes acciones:  
   
   - Si seleccionaste **Asignada** para **Tipo de suscripción** en el paso anterior, selecciona **Miembros** y agrega dispositivos Autopilot al grupo. Los dispositivos de Autopilot que no se han inscrito se muestran con el número de serie del dispositivo como el nombre del dispositivo.
   - Si seleccionaste **Dispositivos dinámicos** para **Tipo de suscripción** en el paso anterior, selecciona **Miembros de dispositivo dinámico** y escribe el código en **Regla avanzada** que se asemeje a lo siguiente:
     - Si quieres crear un grupo que incluya todos los dispositivos de Autopilot, escribe: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - El campo de la etiqueta de grupo de Intune se asigna al atributo **IdPedido** en los dispositivos de Azure AD. Si quieres crear un grupo que incluya todos los dispositivos de Autopilot que tienen una etiqueta de grupo específica (el IdPedido del dispositivo de Azure AD), debes escribir: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Si quieres crear un grupo que incluya todos los dispositivos Autopilot que tengan un ID. de pedido de compra específico, escribe lo siguiente: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Estas reglas buscan atributos que son exclusivos de dispositivos Autopilot.
1. Selecciona **Aceptar** y selecciona **Crear**.

### 6. Crea un recurso compartido de implementación

1. En el Centro de administración de Microsoft Endpoint Manager, selecciona **Dispositivos** > **Windows** > **Inscripción de Windows** > **Perfiles de implementación de Windows Autopilot** > **Crear perfil** > **HoloLens**.
1. Escribe un nombre y una descripción para el perfil y selecciona **Siguiente**.  
   
   ![Agrega un nombre y una descripción para el perfil](./images/hololens-ap-profile-name.png)
1. En la página de la **configuración rápida (OOBE)**, la mayoría de las opciones están preconfiguradas para simplificar la configuración rápida para esta evaluación. Opcionalmente, puedes configurar los valores siguientes:  

   - **Idioma (región)**: selecciona el idioma para OOBE. Recomendamos que selecciones un idioma de la lista de [idiomas compatibles con HoloLens 2](hololens2-language-support.md).
   - **Configura el teclado automáticamente**: para asegurarte de que el teclado coincide con el idioma seleccionado, selecciona **Sí**.
   - **Aplicar la plantilla nombre del dispositivo**: para establecer el nombre del dispositivo automáticamente durante la OOBE, selecciona **Sí** y escribe la frase y los marcadores de posición de la plantilla en **Escribe un nombre** Por ejemplo, especifica un prefijo y `%RAND:4%`&mdash;un marcador de posición para un número aleatorio de cuatro dígitos.
     > [!NOTE]  
     > Si usas una plantilla de nombre de dispositivo, el proceso OOBE reinicia el dispositivo una vez más después de aplicar el nombre del dispositivo y antes de que una el dispositivo a Azure AD. Este reinicio permite que el nuevo nombre surta efecto.  

   ![Configura las opciones de OOBE](./images/hololens-ap-profile-oobe.png)
1. Después de configurar la configuración, selecciona **Siguiente**.
1. En la página **Etiquetas de ámbito**, puedes agregar las etiquetas de ámbito que quieras aplicar a este perfil. Para más información sobre las etiquetas de ámbito, consulta [Usar control de acceso basado en roles y etiquetas de ámbito para TI distribuida](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md). Cuando termines, haz clic en **Siguiente**.
1. En la página **Asignaciones**, selecciona **Grupos seleccionados** para **Asignar a**.
1. En **Grupos seleccionados**, selecciona **+ Seleccionar grupos para incluir**.
1. En la lista **Seleccionar grupos para incluir**, selecciona el grupo de dispositivos que creaste para los dispositivos de Hololens de Autopilot y selecciona **Siguiente**.  
  
   Si quieres excluir grupos, selecciona **Seleccionar grupos para excluir** y selecciona los grupos que quieres excluir.

   ![Asignación de un grupo de dispositivos al perfil.](./images/hololens-ap-profile-assign-devicegroup.png)
   
1. En la página **Revisar y crear**, revisa la configuración y selecciona **Crear** para crear el perfil.  
   
   ![Revisar y crear](./images/hololens-ap-profile-summ.png)

### 7. Comprueba la configuración de ESP

La página de estado de inscripción (ESP) muestra el estado de todo el proceso de configuración de dispositivos que se ejecuta cuando un usuario administrado por MDM inicia sesión en un dispositivo por primera vez. Asegúrate de que la configuración ESP es similar a la siguiente y comprueba que las tareas sean correctas.  

> [!div class="mx-imgBorder"]
> ![Configuración deESP](./images/hololens-ap-profile-settings.png)

### 8. Verificar el estado del perfil de los dispositivos HoloLens

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

       > [!NOTE]
       > El uso de Autopilot afectará al [propietario del dispositivo](security-adminless-os.md#device-owner).
   
       > [!IMPORTANT]  
       > Los dispositivos que intenten usar las redes Wi-Fi en la configuración rápida para el Autopilot deben disponer de [la versión 20H2 de Windows Holographic](hololens-release-notes.md#windows-holographic-version-20h2).
       >
       > Para los dispositivos que usan adaptadores Ethernet, debes conectar el dispositivo a la red antes de que se inicie la experiencia de configuración rápida. El dispositivo determina si se aprovisiona como dispositivo Autopilot mientras se encuentra en la primera pantalla de la configuración rápida. Si el dispositivo no se puede conectar a la red, o si eliges no aprovisionar el dispositivo como dispositivo Autopilot, no podrás cambiarlo posteriormente al aprovisionamiento de Autopilot. En su lugar, tendrías que iniciar este procedimiento para poder aprovisionar el dispositivo como dispositivo Autopilot.

1. El dispositivo debería iniciar automáticamente OOBE. No interactúes con OOBE. En su lugar, siéntate y relájate. Deje que HoloLens 2 detecte la conectividad de red y permite que complete la OOBE automáticamente. Es posible que el dispositivo se reinicie durante la OOBE. Las pantallas de OOBE deben tener un aspecto similar al siguiente.
   
   ![OOBE paso 1](./images/autopilot-welcome.jpg)
   ![OOBE paso 2](./images/autopilot-step-complete.jpg)
   ![OOBE paso 3](./images/autopilot-device-setup.jpg)

1. Al final de OOBE, puedes iniciar sesión en el dispositivo con tu nombre de usuario y contraseña.

   <br/><img src="./images/other-user.jpg" width="450" height="700" />

## Tenantlockdown CSP y Autopilot
- Mantiene los dispositivos en el espacio empresarial de la organización bloqueándolos, incluso al reestablecer el dispositivo o formatearlo. Es más seguro porque no permite crear cuentas mediante aprovisionamiento. 

Los dispositivos HoloLens 2 ahora son compatibles con TenantLockdown CSP en la versión de Windows Holographic 20H2. 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP permite que HoloLens 2 se vincule a la inscripción de MDM únicamente con el Autopilot. Una vez que el nodo RequireNetworkInOOBE de TenantLockdown CSP se active o desactive (configurado inicialmente) en HoloLens 2, permanecerá así el dispositivo aunque se vuelva a formatear, a actualizar el sistema operativo, etc. 

Una vez que el nodo RequireNetworkInOOBE de TenantLockdown CSP se active o desactive (configurado inicialmente) en HoloLens 2, la configuración rápida espera indefinidamente que el perfil de Autopilot se descargue y aplique correctamente, después de conectarse a la red. 

Una vez que el nodo RequireNetworkInOOBE de TenantLockdown de CSP se active o desactive en HoloLens 2, no se permitirán las siguientes operaciones en la configuración rápida: 
- Crear usuarios locales mediante aprovisionamiento en el tiempo de ejecución 
- Realizar una operación de replica de AAD mediante aprovisionamiento en el tiempo de ejecución 
- Seleccionar quién es el propietario del dispositivo en la experiencia de la configuración rápida 

### ¿Cómo configurarlo con Intune? 
1. Crea un perfil de configuración de dispositivos OMA URI personalizado y activa el nodo RequireNetworkInOOBE como se hace a continuación.
El valor OMA-URI debe ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Configuración del bloqueo de inquilinos a través de OMA-URI](images/hololens-tenant-lockdown.png)

1. Crea un grupo y asigna el perfil de configuración del dispositivo a ese grupo de dispositivos. 

1. Haz que el dispositivo HoloLens 2 sea un miembro del grupo creado en el paso anterior y desencadena la sincronización.  

Comprueba en el portal de Intune que la configuración del dispositivo se ha aplicado correctamente. Una vez que la configuración del dispositivo se aplique correctamente en el dispositivo HoloLens 2, los efectos de TenantLockdown estarán activos.

### ¿Cómo se anula el nodo RequireNetworkInOOBE de TenantLockdown en HoloLens 2 con Intune? 
1. Quita HoloLens 2 del grupo de dispositivos a los que asignó la configuración creada anteriormente. 

1. Crea un perfil de configuración de dispositivos basado en OMA URI personalizado y desconecte RequireNetworkInOOBE como se hace a continuación. El valor OMA-URI debe ser ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla de la configuración para desconectar RequireNetworkInOOBE a través de OMA URI en Intune](images/hololens-tenant-lockdown-false.png)

1. Crea un grupo y asigna el perfil de configuración del dispositivo a ese grupo de dispositivos. 

1. Haz que el dispositivo HoloLens 2 sea un miembro del grupo creado en el paso anterior y desencadena la sincronización.

Comprueba en el portal de Intune que la configuración del dispositivo se ha aplicado correctamente. Una vez que la configuración del dispositivo se aplique correctamente en el dispositivo HoloLens 2, los efectos de TenantLockdown estarán inactivos. 

### ¿Qué sucedería durante la configuración rápida si el perfil de Autopilot no está asignado a un HoloLens después de haber activado TenantLockdown? 
La configuración rápida esperará indefinidamente a que se descargue el perfil de Autopilot y a que aparezca el siguiente cuadro de diálogo. Para eliminar los efectos de TenantLockdown, el dispositivo debe estar antes inscrito en el espacio empresarial original únicamente con el Autopilot y RequireNetworkInOOBE configurarse como desconectado tal y como se describe en el paso anterior antes de que se quiten las restricciones introducidas por TenantLockdown CSP. 

![Vista en el dispositivo cuando se aplica la directiva.](images/hololens-autopilot-lockdown.png)

## Problemas conocidos

- La instalación de aplicaciones basadas en el contexto del dispositivo configurada en Intune aún no funciona.
- Al configurar Autopilot a través de Wi-Fi, es posible que haya una instancia en la que no se descargue el perfil de Autopilot cuando se establezca primero la conexión a Internet y se presente el contrato de licencia para el usuario final (CLUF) y éste tenga la opción de continuar con las experiencias de configuración sin Autopilot. Para volver a intentar la configuración con Autopilot, pon el dispositivo en suspensión y después enciéndelo, o bien reinícialo y vuelve a intentarlo.

### Solución de problemas

Los siguientes artículos pueden ser un recurso útil para obtener más información y solucionar problemas de Autopilot, pero ten en cuenta que estos artículos se basan en el escritorio de Windows 10 y no toda la información puede aplicarse a HoloLens:
- [Windows Autopilot: problemas conocidos](https://docs.microsoft.com/mem/autopilot/known-issues)
- [Solucionar problemas de inscripción de dispositivos de Windows en Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot: conflictos de directivas](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## Comentarios sobre Autopilot

Para proporcionar comentarios o informar de problemas, sigue uno de los métodos siguientes:

- Usa la aplicación Centro de opiniones Puedes encontrar esta aplicación en un equipo conectado con HoloLens. En el Ccentro de opiniones, selecciona la categoría **Administración empresarial** > **Dispositivo**. Cuando envíes comentarios o notifiques un problema, proporciona una descripción detallada. Si procede, incluye capturas de pantalla y registros.
- Si experimentas problemas en Intune durante el registro del dispositivo o no se asigna un perfil de Autopilot, abre un vale de soporte técnico en [https://aka.ms/apsupport](https://aka.ms/apsupport) .
- Si tienes problemas con el dispositivo HoloLens durante la experiencia de Autopilot, abre un vale de soporte técnico en [https://aka.ms/hlsupport](https://aka.ms/hlsupport) con los [registros de diagnóstico sin conexión](hololens-diagnostic-logs.md#offline-diagnostics).

  Proporciona una descripción detallada en el mensaje. Sin embargo, a menos que el personal de soporte técnico lo solicite específicamente, no incluyas datos como capturas de pantalla o registros. Estos datos podrían incluir información confidencial o de identificación personal (PII).
