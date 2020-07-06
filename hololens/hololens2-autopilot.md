---
title: Guía de evaluación de Windows Autopilot para HoloLens 2
description: ''
author: Teresa-Motiv
ms.author: v-tea
ms.date: 4/10/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: 3d98e67e79ae10b606c529adbda95dbb61b8fd15
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829642"
---
# Guía de evaluación de Windows Autopilot para HoloLens 2

Cuando configures los dispositivos HoloLens 2 para el programa Windows Autopilot, los usuarios podrán seguir un proceso sencillo para aprovisionar los dispositivos desde la nube.

Este programa de Autopilot es compatible con el modo de implementación automática de Autopilot para aprovisionar dispositivos HoloLens 2 como dispositivos compartidos en su espacio empresarial. El modo de implementación automática aprovecha los controladores y la imagen del OEM preinstalado del dispositivo durante el proceso de aprovisionamiento. Un usuario puede aprovisionar el dispositivo sin tener el dispositivo activado, ni pasar por la experiencia de configuración rápida (OOBE).  

![El proceso de implementación automática de Autopilot configura dispositivos compartidos en modo "sin periféricos" con una conexión de red.](./images/hololens-ap-intro.png)

Cuando un usuario inicia el proceso de implementación automática de Autopilot, el proceso completa estos pasos:

1. Unir el dispositivo a Azure Active Directory (Azure AD).
   > [!NOTE]  
   > Autopilot para HoloLens no es compatible con la combinación de Active Directory ni Azure AD híbrido.
1. Usar Azure AD para inscribir el dispositivo en Microsoft Intune (u otro servicio MDM).
1. Descargar las directivas de destino del dispositivo, las aplicaciones de destino del usuario, los certificados y los perfiles de red.
1. Aprovisionar el dispositivo.
1. Mostrar la pantalla de inicio de sesión al usuario.

## Windows Autopilot para HoloLens 2: Introducción

En los siguientes pasos se resume el proceso de configuración del entorno para Windows Autopilot para HoloLens 2. El resto de esta sección ofrece información detallada sobre estos pasos.

1. Asegúrate de que cumples los requisitos para Windows Autopilot para HoloLens.
1. Inscríbete en el programa de Windows Autopilot para HoloLens 2.
1. Comprueba que tu espacio empresarial forme parte del paquete piloto (inscrito para participar en el programa).
1. Registra dispositivos en Windows Autopilot.
1. Crear un grupo de dispositivos.
1. Crear un perfil de implementación
1. Comprueba la configuración de ESP.
1. Configura un perfil de configuración personalizada para dispositivos HoloLens (problema conocido).
1. Comprueba el estado del perfil de los dispositivos HoloLens.

### 1. Asegúrate de que cumples los requisitos para Windows Autopilot para HoloLens
Para obtener la información más reciente sobre cómo participar en el programa, consulta [Notas de la versión de Windows Insider](hololens-insider.md#windows-insider-release-notes).

Consulta las secciones siguientes del artículo sobre los requisitos de Windows Autopilot:

- [Requisitos de red](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)  
- [Requisitos de licencias](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#licensing-requirements)  
- [Requisitos de configuración](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#configuration-requirements)
> [!IMPORTANT]  
> A diferencia de otros programas de Windows Autopilot, Windows Autopilot para HoloLens 2 tiene requisitos de sistema operativo específicos.

Consulta la sección "[Requisitos](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" del artículo Modo de implementación automática de Windows Autopilot. El entorno tiene que cumplir estos requisitos, así como los requisitos estándar del Windows Autopilot.

> [!NOTE]  
> No es necesario revisar las secciones "Paso a paso" y "Validación" del artículo. Los procedimientos que se describen más adelante en este artículo proporcionan los pasos correspondientes específicos para HoloLens.

> [!IMPORTANT]  
> Para obtener información sobre cómo registrar dispositivos y configurar perfiles, consulta [4. Registra dispositivos en Windows Autopilot](#4-register-devices-in-windows-autopilot) y [6. Crea un perfil de implementación](#6-create-a-deployment-profile) en este artículo. En estas secciones se proporcionan los pasos específicos para HoloLens.

Antes de iniciar el proceso de OOBE y aprovisionamiento, asegúrate de que los dispositivos HoloLens cumplan los requisitos siguientes:

- Los dispositivos aún no son miembros de Azure AD y no se han inscrito en Intune (u otro sistema MDM). El proceso de implementación automática de Autopilot completa estos pasos. Para asegurarte de que toda la información relacionada con los dispositivos se ha limpiado, activa la casilla de verificación **Dispositivos** en las páginas de Azure AD e Intune.
- Todos los dispositivos se pueden conectar a Internet. Puede usar adaptadores "USB C a Ethernet" para la conexión a Internet con cable o adaptadores "USB C a Wifi" para la conexión inalámbrica a Internet. 
- Cada dispositivo se puede conectar a un ordenador mediante un cable USB-C, y ese ordenador tiene instalado el [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab)
- Cada dispositivo tiene la última actualización de Windows: Windows 10, versión 19041.1002.200107-0909 o una versión posterior

Para configurar y administrar los perfiles del modo de implementación automática de Autopilot, asegúrate de que tienes acceso al [centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com).

### 2. Inscríbete en el programa Windows Autopilot para HoloLens 2

Para participar en el programa, tienes que usar un espacio empresarial que forme parte del paquete piloto para HoloLens. Para hacerlo, ve a [solicitud de vista previa de Windows AutoPilot para HoloLens](https://aka.ms/APHoloLensTAP) y usa el siguiente código QR para enviar una solicitud.  

![Código QR de Autopilot](./images/hololens-ap-qrcode.png)  

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
  Deberías ver una lista que incluya **HoloLens**. Si esta opción no está disponible, utiliza una de las opciones de [Comentarios](#feedback) para ponerte en contacto con nosotros.

### 4. Registra dispositivos en Windows Autopilot

Para registrar un dispositivo HoloLens en el programa Windows Autopilot, tienes que obtener el valor hash de hardware del dispositivo (también conocido como ID. de hardware). El dispositivo puede grabar su hash de hardware en un archivo CSV durante el proceso OOBE, o bien, cuando el propietario de un dispositivo inicia el proceso de recopilación de registros de diagnóstico (descrito en el procedimiento siguiente). Por lo general, el propietario del dispositivo es el primer usuario que inicia sesión en el dispositivo.

**Recuperar un algoritmo hash de hardware del dispositivo**

1. Inicia el dispositivo HoloLens 2.
1. En el dispositivo, presiona los botones apagar la energía y bajar el volumen al mismo tiempo y luego suéltalos. El dispositivo recoge los registros de diagnóstico y el hash de hardware, y los almacena en un conjunto de archivos .zip.
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

![Configuración deESP](./images/hololens-ap-profile-settings.png)

### 8. Verificar el estado del perfil de los dispositivos HoloLens

1. En el Centro de administración de Microsoft Endpoint Manager, selecciona **Dispositivos** > **Windows** > **Inscripción de Windows** > **Dispositivos**.
1. Comprueba que los dispositivos HoloLens se muestran en la lista y que el estado del perfil es **Asignado**.  
   > [!NOTE]  
   > El perfil puede tardar unos minutos en asignarse al dispositivo.  
   
   ![Asignaciones de dispositivo y perfil.](./images/hololens-ap-devices-assignments.png)

## Experiencia de usuario de Windows AutoPilot para HoloLens 2

Los usuarios de HoloLens pueden seguir estos pasos para aprovisionar dispositivos HoloLens.  

1. Usar el cable USB-C para conectar el dispositivo HoloLens a un equipo que tenga instalado Advanced Recovery Companion (ARC) y que tenga la actualización de Windows adecuada descargada.
1. Usar ARC para actualizar la versión adecuada de Windows en el dispositivo.
1. Conectar el dispositivo a la red y reiniciar el dispositivo.  
   > [!IMPORTANT]  
   > Debes conectar el dispositivo a la red antes de que se inicie la experiencia de configuración rápida (OOBE). El dispositivo determina si se aprovisiona como dispositivo Autopilot mientras se encuentra en la primera pantalla de OOBE. Si el dispositivo no se puede conectar a la red, o si eliges no aprovisionar el dispositivo como dispositivo Autopilot, no podrás cambiarlo posteriormente al aprovisionamiento de Autopilot. En su lugar, tendrías que iniciar este procedimiento para poder aprovisionar el dispositivo como dispositivo Autopilot.

   El dispositivo debería iniciar automáticamente OOBE. No interactúes con OOBE. En su lugar, siéntate y relájate. Deje que HoloLens 2 detecte la conectividad de red y permite que complete la OOBE automáticamente. Es posible que el dispositivo se reinicie durante la OOBE. Las pantallas de OOBE deben tener un aspecto similar al siguiente.
   
   ![OOBE paso 1](./images/hololens-ap-uex-1.png)
   ![OOBE paso 2](./images/hololens-ap-uex-2.png)
   ![OOBE paso 3](./images/hololens-ap-uex-3.png)
   ![OOBE paso 4](./images/hololens-ap-uex-4.png)

Al final de OOBE, puedes iniciar sesión en el dispositivo con tu nombre de usuario y contraseña.

  ![Paso 5 de OOBE](./images/hololens-ap-uex-5.png)

## Problemas conocidos

- No puede instalar aplicaciones que utilicen el contexto de seguridad del dispositivo.

## Comentarios

Para proporcionar comentarios o informar de problemas, sigue uno de los métodos siguientes:

- Usa la aplicación Centro de opiniones Puedes encontrar esta aplicación en un equipo conectado con HoloLens. En el Ccentro de opiniones, selecciona la categoría **Administración empresarial** > **Dispositivo**.  

  Cuando envíes comentarios o notifiques un problema, proporciona una descripción detallada. Si procede, incluye capturas de pantalla y registros.
- Envía un mensaje de correo electrónico a [hlappreview@microsoft.com](mailto:hlappreview@microsoft.com). En el asunto del correo electrónico, escriba**\<*Tenant*>Comentarios sobre la evaluación del Piloto Automático de HoloLens 2** (donde\<*Tenant*>sea el nombre de su inquilino de Intune).

  Proporciona una descripción detallada en el mensaje. Sin embargo, a menos que el personal de soporte técnico lo solicite específicamente, no incluyas datos como capturas de pantalla o registros. Estos datos podrían incluir información confidencial o de identificación personal (PII).
