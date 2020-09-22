---
title: Configurar HoloLens con un paquete de aprovisionamiento (HoloLens)
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
ms.date: 03/10/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: c10f07a6caeae6f2e8ace41d345c3ad11901621a
ms.sourcegitcommit: 89ce6cdc0fc6d70a88217791c5f6d613778af614
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "11052649"
---
# Configurar HoloLens con un paquete de aprovisionamiento

El [aprovisionamiento de Windows](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) facilita que los administradores de ti configuren dispositivos de usuario final sin imágenes. El diseñador de configuración de Windows es una herramienta para configurar las imágenes y la configuración del tiempo de ejecución, que se integran en paquetes de aprovisionamiento.

Algunas de las configuraciones de HoloLens que puede aplicar en un paquete de aprovisionamiento son las siguientes:

- Actualizar a Windows Holographic para empresas [aquí](hololens1-upgrade-enterprise.md)
- Configuración de una cuenta local
- Configuración de una conexión Wi-Fi
- Aplicar certificados al dispositivo
- Habilitar el modo de desarrollador
- Configurar el modo de pantalla completa ( [aquí](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)encontrará instrucciones detalladas para configurar el modo de pantalla completa.

## Asistente para el paquete de aprovisionamiento de HoloLens

El Asistente de HoloLens te ayuda a configurar las siguientes opciones en un paquete de aprovisionamiento:

- Actualizar a la edición Enterprise

    > [!NOTE]
    > Esto solo debe usarse para los dispositivos de la primera generación de HoloLens. La configuración de un paquete de aprovisionamiento solo se aplica si el paquete de aprovisionamiento incluye una licencia de actualización de edición a Windows Holographic para empresas o si [el dispositivo ya se ha actualizado a Windows Holographic para empresas](hololens1-upgrade-enterprise.md).

- Configurar la primera experiencia (OOBE) de HoloLens
- Configurar la red Wi-Fi
- Inscribir el dispositivo en Azure Active Directory o crear una cuenta local
- Agregar certificados
- Habilitar el modo de desarrollador
- Configurar el modo de pantalla completa. Puede [encontrar instrucciones](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)detalladas para configurar el modo de pantalla completa.

> [!WARNING]
> Debes ejecutar el Diseñador de configuraciones de Windows en Windows 10 para configurar la inscripción en Azure Active Directory a través de cualquiera de los asistentes.

Los paquetes de aprovisionamiento pueden incluir instrucciones de administración y directivas, conexiones de red personalizadas y directivas, entre otras.

> [!TIP]
> Usa el asistente para escritorio para crear un paquete con la configuración común y después usa el editor avanzado para agregar otras configuraciones, aplicaciones, directivas, etc.

## Pasos para crear paquetes de aprovisionamiento

1. **Opción 1:** [desde Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22). Esto incluye las capacidades de HoloLens 2.
2. **Opción 2:** [de Windows Assessment and Deployment Kit (ADK) para Windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit). Si instala el diseñador de configuración de Windows desde Windows ADK, seleccione **Diseñador de configuración** en el cuadro de diálogo **Seleccione las características que desea instalar** . Esta opción no incluye las funcionalidades de HoloLens 2.

> [!NOTE]
> Si sabe que va a usar un equipo sin conexión que necesita acceso al diseñador de configuración de Windows, siga la instalación sin conexión de la aplicación aquí para el Asistente de recuperación avanzada, pero haciendo que Windows [le](https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) Confiugration en su lugar la selección. 

### 2. crear el paquete de aprovisionamiento

Usa la herramienta Diseñador de configuraciones de Windows para crear un paquete de aprovisionamiento.

1. Abre el Diseñador de configuraciones de Windows (que se encuentra de forma predeterminada en %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Diseñador de imágenes y configuraciones\x86\ICD.exe).

2. Seleccione **aprovisionar dispositivos HoloLens**.

   ![Opciones de inicio de ICD](images/icd-create-options-1703.png)

3. Asigne un nombre al proyecto y seleccione **Finalizar**.

4. Lea las instrucciones de la página **Introducción** y seleccione **siguiente**. Las páginas de aprovisionamiento de escritorio le guiarán a través de los pasos siguientes.
  
> [!IMPORTANT]
> Cuando compilas un paquete de aprovisionamiento, puedes incluir información confidencial en los archivos de proyecto y en el archivo del paquete de aprovisionamiento (.ppkg). Aunque tienes la posibilidad de cifrar el archivo .ppkg, los archivos de proyecto no se cifran. Debes almacenar los archivos de proyecto en una ubicación segura y eliminarlos cuando ya no sean necesarios.

### Configurar opciones

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>Busque y seleccione el archivo de licencia empresarial para actualizar la edición de HoloLens.</br></br>También puede activar o desactivar <strong> sí </strong> o <strong> no </strong> para ocultar partes de la primera experiencia.</br></br>Para configurar el dispositivo sin necesidad de conectarse a una red Wi-Fi, conmute por <strong> omisión la configuración de Wi-Fi </strong> a <strong> activado </strong> .</br></br>Seleccione una región y una zona horaria en la que se usará el dispositivo. </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>En esta sección, puede introducir los detalles de la red inalámbrica Wi-Fi a la que el dispositivo debe conectarse automáticamente. Para ello, seleccione <strong> activado </strong> , escriba el SSID, el tipo de red ( <strong> abierto </strong> o <strong> WPA2-Personal </strong> ) y (si <strong> WPA2-Personal </strong> ) la contraseña de la red inalámbrica.</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>Puede inscribir el dispositivo en Azure Active Directory o crear una cuenta local en el dispositivo</br></br>Antes de usar un asistente del Diseñador de configuraciones de Windows para configurar la inscripción masiva en AzureAD, <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">configura la unión a Azure AD en la organización</a>. La opción <strong>Número máximo de dispositivos por usuario</strong> del inquilino de Azure AD determina cuántas veces se puede usar el token masivo que se obtiene en el asistente. Para inscribir el dispositivo en Azure AD, selecciona esa opción y escribe un nombre descriptivo para el token masivo que obtendrás mediante el asistente. Establece una fecha de expiración del token (el máximo es de 30 días a partir de la fecha de obtención del token). Seleccione <strong> obtener token en masa </strong> . En la <strong> ventana ¿permitir que&#39;s inicie sesión? </strong> , escriba una cuenta que tenga permisos para unirse a un dispositivo a Azure ad y, a continuación, la contraseña. Seleccione <strong> Aceptar </strong> para dar al diseñador de configuración de Windows los permisos necesarios. </br></br>Para crear una cuenta local, seleccione esa opción y escriba un nombre de usuario y una contraseña. </br></br><strong>Importante:</strong> <br />(Solo para Windows 10, versión 1607) Si crea una cuenta local en el paquete de aprovisionamiento, debe cambiar la contraseña con la <strong> </strong> aplicación configuración cada 42 días. Si la contraseña no se cambia en ese período, es posible que se bloquee y no se pueda iniciar sesión.  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>Para aprovisionar el dispositivo con un certificado, haz clic en <strong>Agregar un certificado</strong>. Escribe un nombre de certificado y luego busca y selecciona el certificado que quieres usar.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br><strong> </strong> <strong> </strong> Para habilitar el modo de Desarrollador en HoloLens, activa sí o no. <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">Obtén más información acerca del modo de desarrollador.</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finish"/></br></br>No establezca una contraseña para proteger el paquete de aprovisionamiento. Si el paquete de aprovisionamiento está protegido por contraseña, el aprovisionamiento del dispositivo HoloLens fallará.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

Cuando haya terminado, seleccione **crear**. El proceso solo tarda unos pocos segundos. Cuando se genera el paquete, la ubicación donde se almacena el paquete se muestra como un hipervínculo en la parte inferior de la página.

### 3. crear un paquete de aprovisionamiento para HoloLens con el aprovisionamiento avanzado

> [!NOTE]
> Un paquete de aprovisionamiento creado en el **aprovisionamiento avanzado** no necesita incluir una licencia de actualización de la edición para que Windows Holographic para empresas pueda aplicarse correctamente a HoloLens (1 ª generación). [Más información en Windows Holographic para la empresa para HoloLens (1ª generación)](hololens1-upgrade-enterprise.md).

1. En la página de inicio del Diseñador de configuraciones de Windows, selecciona **Aprovisionamiento avanzado**.
2. En la ventana **Escribir los detalles del proyecto**, especifica un nombre y una ubicación para el proyecto. También tienes la opción de especificar una breve descripción del proyecto.

3. Selecciona **Siguiente**.

4. En la ventana **Elija los ajustes que desea ver y configurar** , seleccione **Windows 10 Holographic**y, a continuación, seleccione **siguiente**.

5. Seleccione **Finalizar**.

6. Expanda la **configuración de tiempo de ejecución** y personalice el paquete con cualquiera de las opciones que [se describen más adelante en este artículo](#what-you-can-configure).

    > [!IMPORTANT]
    > (Solo para Windows 10, versión 1607) Si crea una cuenta local en el paquete de aprovisionamiento, debe cambiar la contraseña con la aplicación **configuración** cada 42 días. Si la contraseña no se cambia en ese período, es posible que la cuenta se bloquee y no se pueda iniciar sesión. Si la cuenta de usuario se bloquea, deberás [realizar una recuperación completa del dispositivo](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery) (vínculo en inglés).

7. Seleccione **File**  >  **Guardar**archivo.

8. Lea la advertencia de que los archivos de proyecto pueden contener información confidencial y seleccione **Aceptar**.

    > [!IMPORTANT]
    > Cuando compilas un paquete de aprovisionamiento, puedes incluir información confidencial en los archivos de proyecto y en el archivo del paquete de aprovisionamiento (.ppkg). Aunque tienes la posibilidad de cifrar el archivo .ppkg, los archivos de proyecto no se cifran. Debes almacenar los archivos del proyecto en una ubicación segura y eliminarlos cuando ya no sean necesarios.
    
9. Seleccione **exportar**  >  **paquete de aprovisionamiento**.

10. Cambie el **propietario** a **Administrador de ti**. Esto establece la prioridad de este paquete de aprovisionamiento más alta que los paquetes de aprovisionamiento que se aplican a este dispositivo desde otros orígenes. Selecciona **Siguiente**.

11. Establece un valor para **Versión del paquete**.

    > [!TIP]
    > Puedes realizar cambios en los paquetes existentes y cambiar el número de versión para actualizar los paquetes aplicados anteriormente.

12. En **seleccionar detalles de seguridad para el paquete de aprovisionamiento**, seleccione **siguiente**.

    > [!WARNING]
    > Si cifras el paquete de aprovisionamiento, se producirá un error al aprovisionar el dispositivo Hololens.  

13. Seleccione **siguiente** para especificar la ubicación de salida donde quiere que aparezca el paquete de aprovisionamiento una vez que se ha creado. De forma predeterminada, el Diseñador de configuraciones de Windows usa la carpeta de proyecto como la ubicación de salida.

    De manera opcional, puede seleccionar **examinar** para cambiar la ubicación de salida predeterminada.

14. Selecciona **Siguiente**.

15. Seleccione **compilación** para empezar a crear el paquete. La información del proyecto se muestra en la página de compilación y la barra de progreso indica el estado de compilación.

16. Una vez completada la compilación, seleccione **Finalizar**.

<span id="apply" />

## Aplicar un paquete de aprovisionamiento a HoloLens durante la instalación

Los dispositivos HoloLens 2 en la compilación [19041,1103](hololens-release-notes.md#windows-holographic-version-2004) o posteriores pueden usar una unidad USB para aplicar un paquete de aprovisionamiento. Simplemente copia el archivo. ppkg en la raíz de la unidad USB. Los paquetes de aprovisionamiento solo se aplicarán si se encuentran en la raíz de la unidad USB. Se aplicará un paquete de aprovisionamiento múltiple secuencialmente.

1. Use el cable USB para conectar el dispositivo a un PC (o unidad USB para HoloLens 2 como se mencionó anteriormente) y, a continuación, inicie el dispositivo. No continúe más allá de la primera página de un momento que se pueda **interactuar** de Oobe.   
    - En HoloLens (1ª generación), esta página contiene un cuadro azul. 
    - En HoloLens 2, esta página contiene el complemento Hummingbird.

2. Presiona brevemente los botones **Bajar el volumen** e **Inicio/Apagado** a la vez y suéltalos. 

3. HoloLens se muestra como un dispositivo en el explorador de archivos de su PC.

4. En el Explorador de archivos, arrastra y coloca el paquete de aprovisionamiento (.ppkg) en el almacenamiento del dispositivo.

5. Pulsa y suelta **brevemente los botones** de **encendido** y de apagado de forma simultánea mientras se encontraba en la primera página de un momento que se pueda **interactuar** de Oobe.

6. El dispositivo te pregunta si confías en el paquete y deseas aplicarlo. Confirma que el paquete es de confianza.

7. Verás si el paquete se ha aplicado correctamente o no. Si se ha producido un error, puedes arreglar el paquete y volver a intentarlo. Si se ha aplicado correctamente, continúa con la configuración rápida.

> [!NOTE]
> Si el dispositivo se compró antes del 2016 de agosto, tendrá que iniciar sesión en el dispositivo con una cuenta de Microsoft, obtener la actualización más reciente del sistema operativo y, a continuación, restablecer el sistema operativo para aplicar el paquete de aprovisionamiento.

## Aplicar un paquete de aprovisionamiento a HoloLens después de la instalación

> [!NOTE]
> Estos pasos solo se aplican a Windows 10, versión 1809.

En su equipo, siga estos pasos:
1. Cree un paquete de aprovisionamiento como se describe en [crear un paquete de aprovisionamiento para HoloLens con el Asistente de hololens](hololens-provisioning.md).
2. Conecta el dispositivo HoloLens a un equipo de PC con un cable USB. HoloLens se muestra como un dispositivo en el explorador de archivos de su PC.
3. Arrastre y coloque el paquete de aprovisionamiento en la carpeta documentos de HoloLens.

En HoloLens, siga estos pasos:
1. Vaya a **configuración**  >  **cuentas**de  >  **acceso profesional o educativa**. 
2. En **configuración relacionada**, seleccione **Agregar o quitar un paquete de aprovisionamiento**.
3. En la página siguiente, seleccione **Agregar un paquete** para iniciar el selector de archivos y seleccione el paquete de aprovisionamiento. Si la carpeta está vacía, asegúrese de seleccionar **este dispositivo** y de seleccionar **documentos**.

Después de que se haya aplicado el paquete, aparecerá en la lista de **paquetes instalados**. Para ver los detalles del paquete o para quitar el paquete del dispositivo, seleccione el paquete que aparece en la lista.

## Elementos que puedes configurar

Los paquetes de aprovisionamiento utilizan proveedores de servicios de configuración (CSP). Si no estás familiarizado con los CSP, consulta [Introducción a los proveedores de servicios de configuración (CSP) para lo profesionales de las TI](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers).

En Diseñador de configuraciones de Windows, cuando se crea un paquete de aprovisionamiento para Windows Holographic, los valores de configuración que aparecen en **Personalizaciones disponibles** se basan en los [CSP que se admiten en Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices). La siguiente tabla describe los valores que puedes configurar para HoloLens.

![Valores de configuración comunes de tiempo de ejecución para HoloLens](images/icd-settings.png)

| Valor | Descripción |
| --- | --- |
| **Certificados** | Implementa un certificado en HoloLens.  |
| **ConnectivityProfiles** | Implementa un perfil de Wi-Fi en HoloLens.   |
| **EditionUpgrade** | [Actualiza a Windows Holographic for Business.](hololens1-upgrade-enterprise.md)  |
| **Directivas** | Permite o impide el Modo de desarrollador en HoloLens. [Directivas compatibles con Windows Holographic for Business](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## Instalación de aplicaciones mediante el paquete de aprovisionamiento

Las aplicaciones se pueden instalar mediante paquetes de aprovisionamiento en dispositivos HoloLens 2. Esto permite un paquete fácilmente reutilizable que puede usar para ayudarle a distribuir las aplicaciones. Lea las instrucciones completas para [implementar aplicaciones a través de paquetes de aprovisionamiento](app-deploy-provisioning-package.md).  

> [!NOTE]
> HoloLens (1º gen) tiene un soporte limitado para instalar aplicaciones (**UniversalAppInstall**) mediante un paquete de aprovisionamiento. Los dispositivos HoloLens (1. ª gen) solo admiten la instalación de una aplicación a través de PPKG solo durante OOBE y solo con instalaciones de contexto de usuario.
