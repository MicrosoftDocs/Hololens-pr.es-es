---
title: 'Guía de implementación: HoloLens 2 conectado corporativamente con guías de Dynamics 365: configurar'
description: Obtenga información sobre cómo configurar configuraciones para implementar dispositivos HoloLens 2 en una red conectada corporativa con guías de Dynamics 365.
keywords: HoloLens, administración, con conexión corporativa, Guías de Dynamics 365, AAD, Azure AD, MDM, Administración de dispositivos móviles
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
ms.openlocfilehash: 939efc28a0c3255cc9a38af3cd8dd9aa8fc2ac98
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448628"
---
# <a name="configure---corporate-connected-guide"></a>Configurar: Guía conectada corporativa

## <a name="azure-users-and-groups"></a>Usuarios y grupos de Azure

Azure y Intune por esa extensión usan usuarios y grupos para ayudar a asignar configuraciones y licencias. Para validar este flujo de implementación y poder comprobar que puede crear y usar una guía, necesitará&#39;cuenta de usuario.

Podemos crear un único grupo de usuarios específicamente para asignar licencias.

Si aún no&#39;tener acceso a dos cuentas de Azure AD en un grupo de usuarios, puede usar; estas son las guías de inicio rápido para:

- [Cómo crear un usuario](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Cómo crear un grupo](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Agregar usuarios a un grupo:](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) agregar usuarios creados para crear un grupo
- [Configurar Azure AD para permitir que un grupo de usuarios se](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) una a dispositivos: asegúrese de que el nuevo grupo de usuarios tiene permiso para inscribir dispositivos en Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Inscripción automática en HoloLens 2

Para que la experiencia sea fluida y fluida, la configuración de Azure Active Directory Join (AADJ) y la inscripción automática en Intune para dispositivos HoloLens 2 es el camino a seguir. Esto permite a los usuarios introducir sus credenciales de inicio de sesión de la organización durante la OOBE y registrarse automáticamente con Azure AD e inscribir el dispositivo en MDM.

Con [Microsoft Endpoint Manager,](https://endpoint.microsoft.com/#home)podemos seleccionar servicios y navegar por algunas páginas hasta que podamos seleccionar Obtener una versión de prueba Premium. You may notice there is Azure Active Directory Premium 1 and 2 - for Automatic Enrollment P1 is sufficient. Podemos seleccionar Intune y seleccionar el ámbito de usuario para la inscripción automática y seleccionar el grupo que se creó anteriormente.

Para obtener información completa y los pasos, lea la guía sobre cómo habilitar [la inscripción automática para Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).

## <a name="corporate-wi-fi-connectivity"></a>Conectividad Wi-Fi corporativa

Las Wi-Fi corporativas normalmente requerirán autenticación basada en certificados para los clientes que usan HoloLens 2. Deberás implementar dichos certificados mediante una infraestructura de certificados del Protocolo simple de inscripción de certificados (SCEP) o una infraestructura de certificados estándar de criptografía de clave pública (PKCS) integrada con la solución MDM. El uso de Intune para implementar Wi-Fi, certificados y configuración de proxy crea una experiencia perfecta para los usuarios finales.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Implementar certificados y Wi-Fi perfiles

Para implementar certificados y perfiles a través de Microsoft Endpoint Manager, siga estos pasos:

1. Cree un perfil para cada uno de los certificados raíz e intermedio (vea [Crear perfiles de certificado de confianza).](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles) Cada uno de estos perfiles debe tener una descripción que incluya una fecha de expiración en formato DD/MM/AYYY. 

    > [!CAUTION]
    > **Los perfiles de certificado sin fecha de expiración no se implementarán.**

2.  Cree un perfil para cada uno de los certificados SCEP o PKCS (consulte [Crear perfiles de certificado SCEP o Crear perfiles de certificado PKCS](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)). Cada uno de estos perfiles debe tener una descripción que incluya una fecha de expiración en el formato DD/MM/AAAA. 

    > [!CAUTION]
    > **No se implementará ningún perfil de certificado digital sin una fecha de expiración.**

    > [!Note]
    > Como HoloLens 2 se considera para muchos un dispositivo compartido, es decir, varios usuarios por dispositivo, se recomienda implementar certificados de dispositivo en lugar de certificados de usuario para la autenticación de Wi-Fi siempre que sea posible.

3.  Crea un perfil para la red Wi-Fi corporativa (consulta Configuración de [Wi-Fi para Windows 10 y dispositivos posteriores).](https://docs.microsoft.com/intune/wi-fi-settings-windows) Dentro de Wi-Fi perfil, puede seleccionar usar la configuración de proxy dentro de la organización.
 
    Sus opciones:
    - **Ninguno:** no hay ninguna configuración de proxy configurada.
    - **Configurar manualmente:** escriba la **dirección IP del servidor proxy** y su número de **puerto**.
    - **Configuración automática:** escriba la dirección URL que apunta a un script de configuración automática de proxy (PAC). Por ejemplo, escriba *http://proxy.contoso.com/proxy.pac* .

    Para obtener más información sobre los archivos PAC, vea [Proxy Auto-Configuration (PAC) file (opens](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) a non-Microsoft site).
 
    > [!Note]
    > Se recomienda que el perfil de Wi-Fi se asigne a grupos de dispositivo, en lugar de a grupos de usuario, siempre que sea posible.
     
    > [!Tip]
    > También puede exportar un perfil Wi-Fi de trabajo desde un equipo con Windows 10 en su red corporativa. Esta exportación crea un archivo XML con toda la configuración. Luego, importe este archivo en Intune y úselo como perfil de Wi-Fi para sus dispositivos HoloLens 2. Consulta [Exportar e importar Wi-Fi configuración para dispositivos Windows](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

1.  [Asigna](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) los perfiles de dispositivo al grupo de dispositivos HoloLens.

2.  [Supervisar](https://docs.microsoft.com/mem/intune/configuration/device-profile-monitor) los perfiles de dispositivo en Intune.

Si hay problemas con los Wi-Fi, haga referencia a Solucionar problemas Wi-Fi perfiles de configuración [de dispositivos en Intune](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles).

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Solución de problemas de acceso a Internet externo cuando Corp está conectado
Cuando los servicios intentan no pasar por un proxy establecido, pueden intentar conectarse a través del firewall. Puede agregar una lista de detalles de extremo a las reglas de firewall para solucionar estos problemas.

Si está bloqueado en los puertos de firewall, habilite algunos puntos de [conexión comunes](https://docs.microsoft.com/hololens/hololens-offline) para HoloLens.

También puede habilitar los puertos específicos de guías: direcciones URL accesibles para Internet necesarias para [que la conectividad Microsoft Dynamics CRM Online](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami).

## <a name="app-deployment"></a>Implementación de aplicaciones

La implementación de una aplicación de LOB a través de MDM es un método que es fácilmente escalable y que se puede implementar automáticamente en los dispositivos al inscribirse en un grupo creado.

Si sigues desarrollando tus aplicaciones o aún no tienes ninguna, puedes usar una aplicación de ejemplo del centro de ejemplos de MRTK. Esta aplicación de ejemplo está lista para usarse y no requerirá el uso de Unity o Visual Studio. [Descargue la aplicación ejemplo de MRTK Examples](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App).

Si prefieres usar tu propia aplicación o estás interesado en el desarrollo de aplicaciones para realidad mixta, no dudes en revisar nuestra documentación para desarrolladores de realidad [mixta](https://docs.microsoft.com/windows/mixed-reality/design/design).

> [!NOTE]
> Los requisitos del sistema para los dispositivos HoloLens se basan en la arquitectura de la compilación de la aplicación. Los dispositivos HoloLens 2 usan ARM arquitectura. Al compilar las aplicaciones en Visual Studio, asegúrate de haber seleccionado la arquitectura correcta para el dispositivo e incluir las dependencias necesarias.

> [!IMPORTANT]
> Al implementar aplicaciones de LOB, es importante cargar también el certificado en Intune y asignarlo al mismo grupo que está pensado para usar la aplicación o no se instalará correctamente.

### <a name="upload-and-assign-the-app"></a>Cargar y asignar la aplicación

1. Vaya al Centro [de administración de MEM](https://endpoint.microsoft.com/#home).

2. Selecciona **Aplicaciones**  ->  **Todas las aplicaciones** y selecciona el botón **+** Agregar.

3. Debajo de Otro, Selecciona **Aplicación de línea de negocio**. Haga clic **en seleccionar**.

4. Seleccione el archivo de paquete de la aplicación, este es su archivo APPXBUNDLE, o en nuestro caso de este ejemplo, la aplicación es _MRTK Examples Hub\_2.4.2.0\_arm\_Master.appxbundle_.

5. Se le notificará si faltan dependencias. En este caso, debemos cargar _Microsoft.VCLibs.ARM.14.00.appx_. Busque en **Seleccionar un archivo**.

6. Selecciona Aceptar.

7. En la siguiente pantalla, los campos necesarios se rellenarán automáticamente. Selecciona **Siguiente**.

8. En Obligatorio, agrega nuestro grupo creado anteriormente para que esta aplicación sea necesaria para el grupo. Esto hará que la aplicación se descargue automáticamente en los dispositivos inscritos en el grupo. Selecciona **Siguiente**.

9. Selecciona **Crear**.

Leer más: [Asignar aplicaciones a grupos en Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Guías de instalación: licencias de aplicación, dataverse y creación

Para usar las Guías de Dynamics 365, deberá realizar una preparación. Hay tres áreas en las que tendremos que prepararnos; usuarios, dataverse y las propias guías.

### <a name="users-and-application-licenses"></a>Usuarios y licencias de aplicaciones

Para que alguien use guías, tendrá que usar una cuenta de Azure AD, que hemos configurado anteriormente en esta guía.

También tendrá que asignar la licencia de Guías de Dynamics 365 al usuario que haya creado. Lo hará desde el Centro de administración de [Microsoft 365](https://admin.microsoft.com/AdminPortal/Home). También asigne la licencia a su cuenta principal de Azure.

Siga [esta breve guía con](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) imágenes para obtener instrucciones paso a paso sobre cómo aplicar licencias de aplicación.

### <a name="set-up-the-dataverse"></a>Configurar dataverse

Para configurar [un entorno de producción,](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) deberá cumplir dos requisitos previos. Debe tener el rol [**administrador**](https://docs.microsoft.com/power-platform/admin/database-security) del sistema  **y**  debe tener una licencia de [**Power Apps**](https://docs.microsoft.com/power-platform/admin/signup-question-and-answer) (o una licencia de Guías de [**Dynamics 365**](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one) que incluya una licencia de Power Apps). Si siguiendo esta guía creó Azure AD, cumple los requisitos de roles para el administrador del sistema. También hemos asignado una licencia de guías en el paso anterior.

En esta guía para [crear un entorno de Microsoft Dataverse:](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two)

1. Empiece por usar el Centro [de administración de Power Platform](https://admin.powerplatform.microsoft.com/environments) y crear un nuevo entorno.
2. Al crear el **nuevo entorno**, para el **tipo** que&#39;seleccionará **Producción**.
3. ¿Es importante alternar crear una base de **datos para este entorno?**  opción a  **Sí**.
4. En el  **cuadro de diálogo**  Agregar base de datos, establezca la opción Habilitar aplicaciones de Dynamics  **365**  en  **Sí.**

Querrá aumentar el tamaño máximo de archivo de los elementos del dataverse. El aumento del tamaño máximo de archivo te permitirá cargar modelos 3D o archivos de vídeo más grandes que usarás más adelante en tus guías. Siga una breve guía [para cambiar el tamaño máximo del archivo de carga.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)

Por último, deberá instalar [y configurar la solución](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution). En el [Centro de administración de Power Platform,](https://admin.powerplatform.microsoft.com/environments)seleccione **Recursos**aplicaciones de Dynamics   \ &gt; **365**, seleccione Guías de **Dynamics 365** en la lista y, a continuación, **seleccione Instalar**.  

Debes agregar [un rol de seguridad Guías antes](https://docs.microsoft.com/dynamics365/mixed-reality/guides/assign-role) de poder usar las aplicaciones.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Crear una guía de prueba en el equipo a través de la creación

Al crear guías, siempre se iniciará en el equipo. Creación de los pasos, selección de modelos y cómo delimitar la guía. Esto se seguirá colocando contenido para la guía más adelante en modo de creación en el dispositivo HoloLens. Para los fines de esta guía, se recomienda crear una guía de prueba corta con pasos y modelos mínimos.

Si desea empezar a aprender sobre la creación de guías, empiece aquí con la [introducción a la creación.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/authoring-overview) O bien, para obtener información general sobre el seguimiento rápido, vea este breve vídeo.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>Opcional: modo quiosco

El modo quiosco es un modo que permite a un administrador de TI configurar la interfaz de usuario del menú inicio para mostrar solo una sola aplicación o una selección de aplicaciones. También se puede aplicar un quiosco de pantalla completa a usuarios, grupos o en el nivel de dispositivo específico; y, en algunos casos, excluir a determinados usuarios del quiosco que aún les permite tener acceso al menú de inicio normal.

El modo de pantalla completa tiene muchas variables diferentes, tanto en el ámbito como en las configuraciones que se pueden establecer, así como los métodos de implementación del quiosco en HoloLens. Debido a todas estas variables, el modo quiosco se deja como _opcional_ para esta guía y no se revisará. Si crees que tienes una necesidad empresarial de restringir las aplicaciones disponibles a los usuarios o quieres obtener más información, no dudes en aprender a configurar [HoloLens](https://docs.microsoft.com/hololens/hololens-kiosk)como quiosco.

## <a name="optional-wdac"></a>Opcional: WDAC

WDAC permite a un administrador de TI configurar sus dispositivos para bloquear el inicio de aplicaciones en dispositivos. Esto es diferente de los métodos de restricción de dispositivos, como el modo quiosco, donde el usuario se presenta con una interfaz de usuario que oculta las aplicaciones en el dispositivo, pero aún se pueden iniciar. Mientras se implementa WDAC, las aplicaciones siguen estando visibles en la lista Todas las aplicaciones, pero WDAC impide que el usuario del dispositivo pueda iniciar esas aplicaciones y procesos.

Para obtener más información, consulte Usar WDAC y Windows PowerShell para permitir o bloquear aplicaciones en [dispositivos HoloLens 2 con Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

[Control de aplicaciones de Windows Defender: WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Paso siguiente 
> [!div class="nextstepaction"]
> [Implementación conectada corporativa: implementar](hololens2-corp-connected-deploy.md)