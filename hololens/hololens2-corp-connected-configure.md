---
title: 'Guía de implementación: HoloLens 2 con conexión corporativa con Dynamics 365 Guides - Configurar'
description: Aprenda a configurar configuraciones para implementar dispositivos HoloLens 2 a través de una red conectada corporativa con Dynamics 365 Guides.
keywords: HoloLens, administración, con conexión corporativa, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Administración de dispositivos
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 9457acd2f53d0d3127d6c68d620b660f6e09866d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637088"
---
# <a name="configure---corporate-connected-guide"></a>Configuración: Guía de conexión corporativa

## <a name="azure-users-and-groups"></a>Usuarios y grupos de Azure

Azure e Intune con esa extensión usan usuarios y grupos para ayudar a asignar configuraciones y licencias. Para validar este flujo de implementación y poder comprobar que puede crear y usar una guía,&#39;necesitará una cuenta de usuario.

Podemos crear un único grupo de usuarios específicamente para asignar licencias.

Si no tiene&#39;acceso a dos cuentas de Azure AD en un grupo de usuarios que puede usar; Estas son las guías de inicio rápido para:

- [Creación de un usuario](/mem/intune/fundamentals/quickstart-create-user)
- [Creación de un grupo](/mem/intune/fundamentals/quickstart-create-group)
- [Agregar usuarios a un grupo:](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) agregar usuarios creados para crear un grupo
- [Configuración Azure AD permitir que un grupo de usuarios](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) se una a los dispositivos: asegúrese de que el nuevo grupo de usuarios tenga permiso para inscribir dispositivos en Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Inscripción automática en HoloLens 2

Para tener una experiencia fluida y sin problemas, la configuración de Azure Active Directory Join (AADJ) y la inscripción automática en Intune para dispositivos HoloLens 2 es el camino a seguir. Esto permite a los usuarios introducir sus credenciales de inicio de sesión de la organización durante la OOBE y registrarse automáticamente con Azure AD e inscribir el dispositivo en MDM.

Mediante el [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), podemos seleccionar servicios y navegar por algunas páginas hasta que podamos seleccionar Obtener una Premium prueba. Es posible que observe que hay Azure Active Directory Premium 1 y 2: para la inscripción automática P1 es suficiente. Podemos seleccionar Intune, seleccionar el ámbito de usuario para la inscripción automática y seleccionar el grupo que se creó anteriormente.

Para obtener detalles y pasos completos, lea la guía sobre cómo habilitar [la inscripción automática para Intune.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="corporate-wi-fi-connectivity"></a>Conectividad Wi-Fi corporativa

Las Wi-Fi corporativas normalmente requerirán autenticación basada en certificados para los clientes que usan HoloLens 2. Tendrá que implementar dichos certificados mediante una infraestructura de certificados Protocolo de inscripción de certificados simple (SCEP) o Public Key Cryptography Standard (PKCS) integrada con la solución MDM. El uso de Intune para implementar Wi-Fi, certificados y configuración de proxy crea una experiencia sin problemas para los usuarios finales.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Implementación de certificados y Wi-Fi perfiles

Para implementar certificados y perfiles mediante Microsoft Endpoint Manager, siga estos pasos:

1. Cree un perfil para cada uno de los certificados raíz e intermedio (consulte [Creación de perfiles de certificado de confianza).](/intune/protect/certificates-configure#create-trusted-certificate-profiles) Cada uno de estos perfiles debe tener una descripción que incluya una fecha de expiración en formato DD/MM/AÑO.

    > [!CAUTION]
    > **Los perfiles de certificado sin una fecha de expiración no se implementarán.**

2. Cree un perfil para cada certificado SCEP o PKCS (vea Crear un perfil de certificado SCEP o Crear un perfil de certificado [PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)). Cada uno de estos perfiles debe tener una descripción que incluya una fecha de expiración en formato DD/MM/YYYY.

    > [!CAUTION]
    > **Los perfiles de certificado sin una fecha de expiración no se implementarán.**

    > [!Note]
    > Como el HoloLens 2 se considera para muchos un dispositivo compartido, es decir, varios usuarios por dispositivo, se recomienda implementar certificados de dispositivo en lugar de certificados de usuario para la autenticación de Wi-Fi siempre que sea posible.

3. Cree un perfil para la red de Wi-Fi corporativa (consulte Configuración de [Wi-Fi para Windows 10 dispositivos posteriores).](/intune/wi-fi-settings-windows) Dentro de Wi-Fi perfil, puede seleccionar usar la configuración de proxy dentro de la organización.

    Las opciones son:
    - **Ninguna**: no se ha configurado ningún valor de proxy.
    - **Configurar manualmente**: escriba la **Dirección IP del servidor proxy** y su **Número de puerto**.
    - **Configurar automáticamente**: escriba la dirección URL que apunta a un script de configuración automática de proxy (PAC). Por ejemplo, escriba: *http://proxy.contoso.com/proxy.pac* .

    Para obtener más información sobre los archivos PAC, vea [Archivo de configuración automática de proxy (PAC)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file), aunque tenga en cuenta que este sitio no pertenece a Microsoft.
 
    > [!Note]
    > Se recomienda asignar el perfil de Wi-Fi a grupos de dispositivos en lugar de a grupos de usuarios siempre que sea posible.
     
    > [!Tip]
    > También puede exportar un perfil de Wi-Fi trabajo desde un equipo Windows 10 en la red corporativa. Esta exportación crea un archivo XML con toda la configuración actual. A continuación, importe este archivo en Intune y úselo como perfil de Wi-Fi para los HoloLens 2 dispositivos. Vea [Exportación e importación de la configuración de Wi-Fi para dispositivos Windows](/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

1.  [Asigne](/mem/intune/configuration/device-profile-assign) los perfiles de dispositivo al HoloLens de dispositivos.

2.  [Supervise](/mem/intune/configuration/device-profile-monitor) los perfiles de dispositivo en Intune.

Si hay problemas con los perfiles de Wi-Fi, consulte Solución Wi-Fi perfiles de configuración [de dispositivos en Intune.](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Solución de problemas de acceso externo a Internet cuando corp está conectado
Cuando los servicios intentan no pasar por un proxy establecido, pueden intentar conectarse a través del firewall. Puede agregar una lista de los detalles del punto de conexión a las reglas de firewall para solucionar estos problemas.

Si está bloqueado en los puertos de firewall, habilite algunos puntos de [conexión comunes](/hololens/hololens-offline) para HoloLens.

También puede habilitar los puertos específicos de las guías: direcciones [URL accesibles desde Internet necesarias](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)para la conectividad a Microsoft Dynamics CRM Online .

## <a name="app-deployment"></a>Implementación de aplicaciones

La implementación de una aplicación lob a través de MDM es un método que es fácil de escalable y se puede implementar automáticamente en los dispositivos tras la inscripción en un grupo creado.

Si sigue desarrollando sus aplicaciones o aún no tiene ninguna, puede usar una aplicación de ejemplo del centro de ejemplos de MRTK. Esta aplicación de ejemplo está lista para usarse y no requerirá el uso de Unity ni Visual Studio. [Descargue la aplicación de ejemplo de ejemplos de MRTK](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App).

Si prefiere usar su propia aplicación o está interesado en el desarrollo de aplicaciones para Mixed Reality, no dude en revisar nuestra documentación de Mixed Reality [desarrollador.](/windows/mixed-reality/design/design)

> [!NOTE]
> Los requisitos del sistema HoloLens dispositivos se basan en la arquitectura de la compilación de la aplicación. HoloLens 2 dispositivos usan la arquitectura arm. Al compilar las aplicaciones en Visual Studio, asegúrese de que ha seleccionado la arquitectura correcta para el dispositivo e incluya las dependencias necesarias.

> [!IMPORTANT]
> Al implementar aplicaciones lob, es importante cargar también el certificado en Intune y asignarlo al mismo grupo que está pensado para usar la aplicación o no se instalará correctamente.

### <a name="upload-and-assign-the-app"></a>Upload y asignar la aplicación

1. Vaya al Centro [de administración de MEM.](https://endpoint.microsoft.com/#home)

2. Seleccione **Aplicaciones**  ->  **Todas las aplicaciones** y seleccione el botón **+** Agregar.

3. Debajo de Otros, seleccione **Aplicación de línea de negocio.** Haga clic **en seleccionar**.

4. Seleccione el archivo de paquete de aplicación, este es el archivo APPXBUNDLE o, en nuestro caso, la aplicación es el Centro de ejemplos de _MRTK \_ 2.4.2.0 \_ \_ arm Master.appxbundle_.

5. Se le notificará si faltan dependencias. En este caso, es necesario cargar _Microsoft.VCLibs.ARM.14.00.appx_. Bájelo en **Seleccionar un archivo.**

6. Seleccione Aceptar.

7. En la siguiente pantalla, los campos obligatorios se rellenarán automáticamente. Seleccione **Siguiente**.

8. En Requerido, agregue el grupo creado anteriormente para que esta aplicación sea necesaria para el grupo. Esto hará que la aplicación se descargue automáticamente en los dispositivos inscritos en el grupo. Seleccione **Siguiente**.

9. Seleccione **Crear**.

Más información: [Asignación de aplicaciones a grupos en Microsoft Intune](/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Guías de instalación: licencias de aplicación, dataverse y creación

Para poder usar Dynamics 365 Guides, deberá realizar cierta preparación. Hay tres áreas en las que debemos prepararnos. los usuarios, el inverso de datos y las propias guías.

### <a name="users-and-application-licenses"></a>Usuarios y licencias de aplicación

Para que alguien use guías, deberá usar una cuenta de Azure AD, que hemos configurado anteriormente en esta guía.

También deberá asignar una licencia Dynamics 365 Guides al usuario que ha creado. Lo hará desde el [Centro de administración de Microsoft 365](https://admin.microsoft.com/AdminPortal/Home). Asigne también la licencia a la cuenta principal de Azure.

Siga [esta breve guía con](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) imágenes para obtener instrucciones paso a paso sobre cómo aplicar licencias de aplicación.

### <a name="set-up-the-dataverse"></a>Configuración del dataverse

Para configurar [un entorno de producción,](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) debe cumplir dos requisitos previos. Debe tener el rol [**administrador del**](/power-platform/admin/database-security) sistema **y** debe tener [](/dynamics365/mixed-reality/guides/setup-step-one) una licencia de Power Apps [**(o**](/power-platform/admin/signup-question-and-answer) una licencia Dynamics 365 Guides que incluya una Power Apps licencia). Si sigue esta guía ha creado el Azure AD, cumple los requisitos de rol para el administrador del sistema. También hemos asignado una licencia de guías en el paso anterior.

En esta guía para [crear un entorno de Microsoft Dataverse:](/dynamics365/mixed-reality/guides/setup-step-two)

1. Empiece por usar el [Centro de administración de Power Platform](https://admin.powerplatform.microsoft.com/environments) y crear un nuevo entorno.
2. Al crear el **nuevo entorno**, para **el** tipo que&#39;seleccionará **Producción**.
3. ¿Es importante activar o desactivar **La creación de una base de datos para este entorno?**  opción a **Sí.**
4. En el  **cuadro de diálogo**  Agregar base de datos, establezca la opción Habilitar aplicaciones de Dynamics  **365**  en  **Sí.**

Querrá aumentar el tamaño máximo de archivo de los elementos del inverso de datos. Aumentar el tamaño máximo de archivo le permitirá cargar modelos 3D o archivos de vídeo más grandes que usará más adelante en las guías. Siga una breve guía [para cambiar el tamaño máximo del archivo de carga.](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)

Por último, deberá instalar y configurar [la solución](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution). En la [Centro de administración de Power Platform](https://admin.powerplatform.microsoft.com/environments), seleccione **Recursos** \& gt;  **Aplicaciones de Dynamics 365,** **seleccione Dynamics 365 Guides** en la lista y, a continuación, **seleccione Instalar**.  

Debe agregar [un rol de seguridad Guides](/dynamics365/mixed-reality/guides/assign-role) antes de poder usar las aplicaciones.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Crear una guía de prueba en el equipo a través de la creación

Al crear guías, siempre se iniciará en el equipo. Crear los pasos, seleccionar modelos y cómo delimitar la guía. A continuación, se colocará el contenido de la guía más adelante en el modo de creación en HoloLens dispositivo. Para los fines de esta guía, se recomienda crear una guía de prueba corta con pasos y modelos mínimos.

Si desea empezar a aprender sobre la creación de guías, comience aquí con la introducción [a la creación.](/dynamics365/mixed-reality/guides/authoring-overview) O bien, para obtener información general de un seguimiento rápido, vea este breve vídeo.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>Opcional: modo de pantalla completa

El modo de pantalla completa es un modo que permite a un administrador de TI configurar la interfaz de usuario del menú inicio para mostrar solo una aplicación o una selección de aplicaciones. También se puede aplicar un quiosco a usuarios, grupos o usuarios específicos en el nivel de dispositivo. y, en algunos casos, excluir a determinados usuarios de la pantalla completa, lo que les permite tener acceso al menú inicio normal.

El modo de pantalla completa tiene muchas variables diferentes, tanto en el ámbito como en las configuraciones que se pueden establecer, así como los métodos para implementar la pantalla completa en el HoloLens. Debido a todas estas variables, el modo quiosco se deja como _opcional_ para esta guía y no se vuelve a visitar. Si cree que tiene una necesidad empresarial de restringir las aplicaciones disponibles [a](/hololens/hololens-kiosk)los usuarios o desea obtener más información, no dude en aprender a configurar HoloLens como un quiosco.

## <a name="optional-wdac"></a>Opcional: WDAC

WDAC permite a un administrador de TI configurar sus dispositivos para bloquear el inicio de aplicaciones en los dispositivos. Esto es diferente de los métodos de restricción de dispositivos, como el modo de pantalla completa, donde se presenta al usuario una interfaz de usuario que oculta las aplicaciones en el dispositivo, pero todavía se pueden iniciar. Mientras se implementa WDAC, las aplicaciones siguen estando visibles en la lista Todas las aplicaciones, pero WDAC impide que el usuario del dispositivo pueda iniciar esas aplicaciones y procesos.

Para obtener más información, consulte Uso de WDAC Windows PowerShell para permitir o bloquear aplicaciones en HoloLens 2 [dispositivos con Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).

[Control de aplicaciones de Microsoft Defender: WDAC](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Paso siguiente 
> [!div class="nextstepaction"]
> [Implementación conectada corporativa: implementación](hololens2-corp-connected-deploy.md)