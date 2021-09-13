---
title: Configuración HoloLens mediante un paquete de aprovisionamiento (HoloLens)
description: El aprovisionamiento de Windows permite a los administradores de TI configurar fácilmente los dispositivos para el usuario final sin necesidad de crear imágenes.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.custom:
- CI 115190
- CSSTroubleshooting
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9474774b47858003cc11363a5f325f589b0732ab
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033906"
---
# <a name="configure-hololens-by-using-a-provisioning-package"></a>Configuración HoloLens mediante un paquete de aprovisionamiento

[Windows aprovisionamiento facilita](/windows/configuration/provisioning-packages/provisioning-packages) a los administradores de TI la configuración de dispositivos de usuario final sin creación de imágenes. Windows El Diseñador de configuración es una herramienta para configurar imágenes y opciones en tiempo de ejecución que luego se integran en paquetes de aprovisionamiento.

Algunas de las HoloLens que se pueden aplicar en un paquete de aprovisionamiento son las siguientes:

- Actualización a [Windows Holographic for Business](hololens1-upgrade-enterprise.md)
- Configuración de una cuenta local
- Configuración de una conexión Wi-Fi
- Aplicación de certificados al dispositivo
- Habilitación del Modo de desarrollador
- Configure el modo de quiosco siguiendo [nuestras instrucciones detalladas.](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)

## <a name="provisioning-package-hololens-wizard"></a>Asistente para HoloLens paquetes de aprovisionamiento

El HoloLens ayuda a configurar los siguientes valores en un paquete de aprovisionamiento:

- Actualización a la edición Enterprise

    > [!NOTE]
    > Esto solo se debe usar para HoloLens de primera generación. Configuración en un paquete de aprovisionamiento solo se aplican si el paquete de aprovisionamiento incluye una licencia de actualización de edición a Windows Holographic for Business o si el dispositivo ya se ha actualizado [a Windows Holographic for Business](hololens1-upgrade-enterprise.md).

- Configuración de HoloLens primera experiencia (OOBE)
- Configuración de la Wi-Fi red
- Inscribir el dispositivo en Azure Active Directory o crear una cuenta local
- Adición de certificados
- Habilitación del Modo de desarrollador
- Configure el modo de quiosco siguiendo [las instrucciones detalladas](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens).

> [!WARNING]
> Debe ejecutar el Windows de configuración en Windows 10 para configurar Azure Active Directory inscripción mediante cualquiera de los asistentes.

Los paquetes de aprovisionamiento pueden incluir instrucciones y directivas de administración, directivas y conexiones de red personalizadas, etc.

> [!TIP]
> Use el Asistente para escritorio para crear un paquete con la configuración común y, a continuación, cambie al editor avanzado para agregar otras configuraciones, aplicaciones, directivas, etc.

## <a name="steps-for-creating-provisioning-packages"></a>Pasos para crear paquetes de aprovisionamiento

1. **Opción 1: desde** [Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22). Esto incluye HoloLens 2 funcionalidades.
2. **Opción 2:** [desde el kit Windows Assessment and Deployment Kit (ADK) para Windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit). Si instala Windows Configuration Designer desde Windows ADK, seleccione  Diseñador de configuración en el cuadro de diálogo Seleccionar las características que **desea** instalar. Esta opción no incluye HoloLens 2 funcionalidades.

> [!NOTE]
> Si sabe que va a usar un equipo sin conexión que necesita acceso al Diseñador de configuración de Windows, siga las instrucciones de [instalación de la aplicación sin conexión (hololens-recovery.md#downloading-arc-without-using-the-app-store) para Advanced Recovery Companion. Haga Windows Diseñador de configuración de la selección. 

### <a name="2-create-the-provisioning-package"></a>2. Creación del paquete de aprovisionamiento

Use la herramienta Windows Diseñador de configuración para crear un paquete de aprovisionamiento.

1. Abra Windows Configuration Designer (de forma predeterminada, %windir%\Archivos de programa (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe).

2. Seleccione **Aprovisionar HoloLens dispositivos**.

   ![Opciones de inicio de ICD.](images/icd-create-options-1703.png)

3. Asigne un nombre al proyecto y seleccione **Finalizar.**

4. Lea las instrucciones de la **página Introducción** y seleccione **Siguiente.** Las páginas para el aprovisionamiento de escritorio le indican los pasos siguientes.
  
> [!IMPORTANT]
> Cuando compilas un paquete de aprovisionamiento, puedes incluir información confidencial en los archivos de proyecto y en el archivo del paquete de aprovisionamiento (.ppkg). Aunque tienes la posibilidad de cifrar el archivo .ppkg, los archivos de proyecto no se cifran. Deberías almacenar los archivos del proyecto en una ubicación segura y eliminarlos cuando ya no sean necesarios.

### <a name="configure-settings"></a>Definición de configuración

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>Vaya a y seleccione el archivo de licencia empresarial para actualizar la HoloLens edición.</br></br>También puede alternar Sí <strong>o</strong> <strong>No</strong> para ocultar partes de la primera experiencia.</br></br>Para configurar el dispositivo sin necesidad de conectarse a una red Wi-Fi, cambie Skip Wi-Fi setup (Omitir Wi-Fi <strong>configuración)</strong> a <strong>On (Activar).</strong></br></br>Seleccione una región y zona horaria en la que se usará el dispositivo. </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>En esta sección, puede especificar los detalles de la Wi-Fi inalámbrica a la que el dispositivo debe conectarse automáticamente. Para ello, seleccione En <strong>,</strong>escriba el SSID, el tipo de red<strong>(Open</strong> o <strong>WPA2-Personal)</strong>y (si <strong>WPA2-Personal)</strong>la contraseña de la red inalámbrica.</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>Puede inscribir el dispositivo en Azure Active Directory o crear una cuenta local en el dispositivo.</br></br>Antes de usar un asistente Windows Configuration Designer para configurar la inscripción Azure AD masiva, configure Azure AD <a href="/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](/azure/active-directory/active-directory-azureadjoin-setup)">unirse a su organización.</a> El <strong>número máximo de dispositivos</strong> por configuración de usuario en el inquilino de Azure AD determina cuántas veces se puede usar el token masivo que se obtiene en el asistente. Para inscribir el dispositivo en Azure AD, seleccione esa opción y escriba un nombre descriptivo para el token masivo que recibirá con el asistente. Establezca una fecha de expiración para el token (el máximo es 30 días a partir de la fecha en que obtiene el token). Seleccione <strong>Obtener token masivo.</strong> En la <strong>ventana Let&#39;s get you signed in</strong> (Permitir que&#39;sesión, escriba una cuenta que tenga permisos para unir un dispositivo a Azure AD y, a continuación, la contraseña. Seleccione <strong>Aceptar</strong> para conceder a Windows Diseñador de configuración los permisos necesarios. </br></br>Para crear una cuenta local, seleccione esa opción y escriba un nombre de usuario y una contraseña. </br></br><strong>Importante:</strong> <br />(Solo Windows 10 versión 1607) Si crea una cuenta local en el paquete de aprovisionamiento, debe cambiar la contraseña mediante Configuración <strong>aplicación</strong> cada 42 días. Si la contraseña no se cambia en ese período, es posible que la cuenta se bloquee y no se pueda iniciar sesión.  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>Para aprovisionar el dispositivo con un certificado, haga clic <strong>en Agregar un certificado.</strong> Escriba un nombre para el certificado y, a continuación, vaya a y seleccione el certificado que se va a usar.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>Alterne <strong>Sí</strong> o <strong>No para</strong> habilitar el modo de desarrollador en el HoloLens. <a href="/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">Obtén más información sobre el modo de desarrollador.</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>No establezca una contraseña para proteger el paquete de aprovisionamiento. Si el paquete de aprovisionamiento está protegido con una contraseña, se producirá un error al aprovisionar HoloLens dispositivo.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

Seleccione **Crear** cuando haya terminado. Solo tarda unos segundos. Cuando se ha creado el paquete, la ubicación donde se almacena el paquete se muestra como un hipervínculo en la parte inferior de la página.

### <a name="3-create-a-provisioning-package-for-hololens-by-using-advanced-provisioning"></a>3. Creación de un paquete de aprovisionamiento para HoloLens mediante el aprovisionamiento avanzado

> [!NOTE]
> Un paquete de aprovisionamiento que cree en El aprovisionamiento avanzado no necesita incluir una licencia de actualización de edición para Windows Holographic for Business para aplicar correctamente a un HoloLens (1.ª generación).  [Consulte más información Windows Holographic for Business para HoloLens (1.ª generación).](hololens1-upgrade-enterprise.md)

1. En la página Windows inicio del Diseñador de configuración avanzada, seleccione **Aprovisionamiento avanzado.**
2. En la ventana **Escribir los detalles del proyecto**, especifica un nombre y una ubicación para el proyecto. También tienes la opción de especificar una breve descripción del proyecto.

3. Seleccione **Siguiente**.

4. En la **ventana Elegir qué opciones desea ver** y configurar, seleccione **Windows 10 Holographic** y, a continuación, **seleccione Siguiente.**

5. Seleccione **Finalizar**.

6. Expanda **Configuración del entorno** de ejecución y personalice el paquete mediante cualquiera de las opciones que se [describen más adelante en este artículo.](#what-you-can-configure)

    > [!IMPORTANT]
    > (Solo Windows 10 versión 1607) Si crea una cuenta local en el paquete de aprovisionamiento, debe cambiar la contraseña mediante Configuración **aplicación** cada 42 días. Si la contraseña no se cambia en ese período, es posible que la cuenta se bloquee y no se pueda iniciar sesión. Si la cuenta de usuario se bloquea, deberás [realizar una recuperación completa del dispositivo](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery) (vínculo en inglés).

7. Seleccione **Archivo** > **Guardar**.

8. Lea la advertencia de que los archivos de proyecto pueden contener información confidencial y seleccione **Aceptar.**

    > [!IMPORTANT]
    > Cuando compilas un paquete de aprovisionamiento, puedes incluir información confidencial en los archivos de proyecto y en el archivo del paquete de aprovisionamiento (.ppkg). Aunque tienes la posibilidad de cifrar el archivo .ppkg, los archivos de proyecto no se cifran. Deberías almacenar los archivos del proyecto en una ubicación segura y eliminarlos cuando ya no sean necesarios.

9. Seleccione **Exportar paquete** de  >  **aprovisionamiento.**

10. Cambie **Propietario a** Administrador de **TI.** Esto establece la prioridad de este paquete de aprovisionamiento mayor que los paquetes de aprovisionamiento aplicados a este dispositivo desde otros orígenes. Seleccione **Siguiente**.

11. Establece un valor para **Versión del paquete**.

    > [!TIP]
    > Puedes realizar cambios en los paquetes existentes y modificar el número de versión para actualizar los paquetes aplicados anteriormente.

12. En Select security details for the provisioning package (Seleccionar **detalles de seguridad para el paquete de aprovisionamiento),** seleccione **Siguiente.**

    > [!WARNING]
    > Si cifra el paquete de aprovisionamiento, se producirá un error al aprovisionar HoloLens dispositivo.  

13. Seleccione **Siguiente** para especificar la ubicación de salida a la que desea que vaya el paquete de aprovisionamiento una vez que se haya creado. De forma predeterminada, Windows Configuration Designer usa la carpeta del proyecto como ubicación de salida.

    Opcionalmente, puede seleccionar Examinar **para** cambiar la ubicación de salida predeterminada.

14. Seleccione **Siguiente**.

15. Seleccione **Compilar** para empezar a compilar el paquete. La información del proyecto se muestra en la página de compilación y la barra de progreso indica el estado de la compilación.

16. Cuando se complete la compilación, seleccione **Finalizar.**

<span id="apply" />

## <a name="apply-a-provisioning-package-to-hololens-during-setup"></a>Aplicación de un paquete de aprovisionamiento a HoloLens durante la instalación

HoloLens 2 dispositivos en Windows Holographic, versión 2004 o [compilación 19041.1103](hololens-release-notes.md#windows-holographic-version-2004) o posterior, pueden usar una unidad USB para aplicar un paquete de aprovisionamiento. Basta con copiar el archivo .ppkg en la raíz de la unidad USB. Los paquetes de aprovisionamiento solo se aplicarán si están en la raíz de la unidad USB. Varios paquetes de aprovisionamiento presentes se aplicarán secuencialmente.

HoloLens 2 dispositivos [de Windows Holographic versión 20H2](hololens-release-notes.md#windows-holographic-version-20h2) o posterior tienen características más recientes que ayudan a simplificar y simplificar este proceso, lo que lo hace automático. Revise las secciones siguientes:

- [Aprovisionamiento de inicio automático desde USB](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [Confirmación automática del aprovisionamiento de paquetes en OOBE](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [Aprovisionamiento automático sin usar la interfaz de usuario](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. Use el cable USB para conectar el dispositivo a un equipo (o unidad USB para HoloLens 2 como se mencionó anteriormente) y, a continuación, inicie el dispositivo. No continúe más allá de la página Primer momento **interactuable** de OOBE.
    - En HoloLens (1ª generación), esta página contiene un cuadro azul.
    - En HoloLens 2, esta página contiene el colibrí.

2. Presiona brevemente los botones **Bajar el volumen** e **Inicio/Apagado** a la vez y suéltalos.

3. HoloLens se muestra como un dispositivo en Explorador de archivos en el equipo.

4. En el Explorador de archivos, arrastra y coloca el paquete de aprovisionamiento (.ppkg) en el almacenamiento del dispositivo.

5. Presione brevemente y suelte los  botones **Bajar** volumen y Encendido simultáneamente mientras se encuentra en la página Primer momento **interactuable** de OOBE.

6. El dispositivo le pregunta si confía en el paquete y le gustaría aplicarlo. Confirma que el paquete es de confianza.

7. Verás si el paquete se ha aplicado correctamente o no. Si se ha producido un error, puedes arreglar el paquete y volver a intentarlo. Si se ha aplicado correctamente, continúa con la configuración rápida.

> [!NOTE]
> Si el dispositivo se compró antes de agosto de 2016, deberá iniciar sesión en el dispositivo con una cuenta Microsoft, obtener la actualización más reciente del sistema operativo y, a continuación, restablecer el sistema operativo para aplicar el paquete de aprovisionamiento.

### <a name="auto-launch-provisioning-from-usb"></a>Aprovisionamiento de inicio automático desde USB

- Procesos automatizados que permiten una menor interacción del usuario, cuando se usan unidades USB con paquetes de aprovisionamiento durante la configuración automática.

Antes de esta versión, los usuarios tenían que iniciar la pantalla de aprovisionamiento manualmente durante la operación de aprovisionamiento mediante una combinación de botones. Ahora los usuarios pueden omitir la combinación de botones mediante un paquete de aprovisionamiento en una unidad de almacenamiento USB.

1. Conecte la unidad USB con el paquete de aprovisionamiento durante el primer momento interactuable de OOBE.
1. Cuando el dispositivo esté listo para aprovisionarse, se abrirá automáticamente el símbolo del sistema con la página de aprovisionamiento.

Nota: Si una unidad USB se deja conectada mientras el dispositivo arranca, OOBE enumerará el dispositivo de almacenamiento USB existente, así como observará si hay otras adicionales conectadas.

Obtenga información sobre la [aplicación de paquetes de aprovisionamiento durante la configuración general.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Confirmación automática del aprovisionamiento de paquetes en OOBE
- Proceso automatizado que permite una menor interacción del usuario, cuando se muestra la página Paquete de aprovisionamiento, se aplicarán automáticamente todos los paquetes enumerados.

Cuando se muestra la pantalla principal de aprovisionamiento, la OOBE se cuenta como una cantidad de 10 segundos antes de empezar a aplicar automáticamente todos los paquetes de aprovisionamiento. Los usuarios todavía pueden confirmar o cancelar en estos 10 segundos después de comprobar los paquetes que esperaban.

### <a name="automatic-provisioning-without-using-ui"></a>Aprovisionamiento automático sin usar la interfaz de usuario
- Procesos automáticos combinados para interacciones reducidas de dispositivos para el aprovisionamiento. 

Mediante la combinación del inicio automático del aprovisionamiento desde dispositivos USB y la confirmación automática de los paquetes de aprovisionamiento, un usuario puede aprovisionar dispositivos HoloLens 2 automáticamente sin usar la interfaz de usuario del dispositivo ni siquiera llevar el dispositivo. Puede seguir usando la misma unidad USB y el mismo paquete de aprovisionamiento para varios dispositivos. Esto es útil para implementar varios dispositivos a la vez en la misma área. 

1. [Cree un paquete de aprovisionamiento](hololens-provisioning.md) [mediante Windows Diseñador de configuración de](https://www.microsoft.com/store/productId/9NBLGGH4TX22). 
1. Copie el paquete en una unidad de almacenamiento USB.
1. [Se ha HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) a [19041.1361 o una compilación más reciente.](https://aka.ms/hololens2previewdownload) 
1. Cuando [Advanced Recovery Companion haya](https://www.microsoft.com/store/productId/9P74Z35SFRS8) terminado de parpadear el dispositivo, desconecte el cable USB-C. 
1. Conecte la unidad USB al dispositivo.
1. Cuando el HoloLens 2 arranque en OOBE, detectará automáticamente el paquete de aprovisionamiento en la unidad USB e iniciará la página de aprovisionamiento.
1. Después de 10 segundos, el dispositivo aplicará automáticamente el paquete de aprovisionamiento. 

El dispositivo ya está configurado y mostrará la pantalla Aprovisionamiento correcto.

## <a name="applyremove-a-provisioning-package-to-hololens-after-setup"></a>Aplicación o eliminación de un paquete de aprovisionamiento HoloLens después de la instalación

> [!NOTE]
> Estos pasos se aplican a todos los dispositivos HoloLens 2 y HoloLens (1ª generación) en Windows Holographic, versión 1809 y posteriores.

En el equipo, siga estos pasos:
1. Cree un paquete de aprovisionamiento como se describe en Creación de un paquete de [aprovisionamiento para HoloLens mediante el HoloLens de aprovisionamiento.](hololens-provisioning.md)
2. Conectar el HoloLens dispositivo a un equipo mediante un cable USB. HoloLens se muestra como un dispositivo en Explorador de archivos en el equipo.
3. Arrastre y coloque el paquete de aprovisionamiento en la carpeta Documentos del HoloLens.

En el HoloLens, siga estos pasos:
1. Vaya a **Configuración** > **Cuentas** > **Obtener acceso a trabajo o escuela**. 
2. En **Relacionado Configuración**, seleccione Agregar o quitar un paquete de **aprovisionamiento.**
3. En la página siguiente, seleccione **Agregar un paquete para** iniciar el selector de archivos y seleccione el paquete de aprovisionamiento. Si la carpeta está vacía, asegúrese de seleccionar **Este dispositivo** y **documentos.**

Una vez aplicado el paquete, se muestra en la lista **de paquetes instalados.** Para ver los detalles del paquete o quitar el paquete del dispositivo, seleccione el paquete enumerado.

## <a name="what-you-can-configure"></a>Lo que puede configurar

Los paquetes de aprovisionamiento utilizan proveedores de servicios de configuración (CSP). Si no estás familiarizado con los CSP, consulta [Introducción a los proveedores de servicios de configuración (CSP) para lo profesionales de las TI](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers).

En Windows Diseñador de configuración de Windows, al crear un paquete de  aprovisionamiento para Windows Holographic, la configuración de Personalizaciones disponibles se basa en los [CSP](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)que se admiten en Windows Holographic . La siguiente tabla describe los valores que puedes configurar para HoloLens.

![Configuración de tiempo de ejecución común para HoloLens.](images/icd-settings.png)

| Configuración | Descripción |
| --- | --- |
| **Certificados** | Implementa un certificado en HoloLens.  |
| **ConnectivityProfiles** | Implementa un perfil de Wi-Fi en HoloLens.   |
| **EditionUpgrade** | [Actualice a Windows Holographic for Business.](hololens1-upgrade-enterprise.md)  |
| **Directivas** | Permite o impide el Modo de desarrollador en HoloLens. [Directivas compatibles con Windows Holographic for Business](/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## <a name="app-install-via-provisioning-package"></a>Instalación de aplicaciones mediante el paquete de aprovisionamiento

Las aplicaciones se pueden instalar a través de paquetes de aprovisionamiento en HoloLens 2 dispositivos. Esto permite un paquete fácilmente utilizable que puede usar para ayudarle a distribuir las aplicaciones. Lea las instrucciones completas para implementar [aplicaciones a través de Paquetes de aprovisionamiento.](app-deploy-provisioning-package.md)  

> [!NOTE]
> HoloLens (1.ª generación) tiene compatibilidad limitada con la instalación de aplicaciones **(UniversalAppInstall)** mediante un paquete de aprovisionamiento. HoloLens dispositivos (1.ª generación) solo admiten la instalación de una aplicación a través de PPKG solo durante la OOBE y solo con las instalaciones de contexto de usuario.
