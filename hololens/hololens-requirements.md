---
title: Configuración de HoloLens en un entorno comercial
description: Obtenga más información sobre la implementación y administración de HoloLens en entornos empresariales, incluida la infraestructura, Azure Active Directory y la administración de dispositivos móviles.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
ms.reviewer: aboeger
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: e6aebfca076294de34068cd075d954220d7f4686
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397226"
---
# <a name="hololens-2-enterprise-deployment-and-management"></a>HoloLens 2 implementación y administración empresariales

Esta información general está pensada para ayudar a los profesionales de TI a comprender las consideraciones para implementar y administrar Microsoft HoloLens 2 dispositivos dentro de la empresa.

HoloLens 2 se ejecuta en Windows 10 Holographic que proporciona a las organizaciones tecnologías sólidas, flexibles y integradas de administración de aplicaciones y dispositivos móviles. Windows 10 Holographic admite la administración del ciclo de vida de los dispositivos de un extremo a otro para proporcionar a las empresas control sobre sus dispositivos, datos y aplicaciones. La HoloLens 2 se puede incorporar fácilmente a los procedimientos estándar del ciclo de vida, desde la inscripción de dispositivos, la configuración y la administración de aplicaciones hasta el mantenimiento y la retirada mediante una solución completa de administración de dispositivos móviles.

## <a name="prepare"></a>Preparación

A medida que se prepara para implementar HoloLens 2 en su entorno empresarial corporativo, hay varias consideraciones que deben revisarse y comprenderse a medida que empiece a planear implementaciones de escalado de HoloLens 2.

### <a name="infrastructure-essentials"></a>Aspectos básicos de la infraestructura

Por HoloLens 2 en un escenario de implementación empresarial corporativa, hay ciertos servicios de infraestructura esenciales necesarios para admitir el conjunto completo de funcionalidades. HoloLens 2 se creó con [Modern Mobile Administración de dispositivos](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) en mente para la implementación y administración. Con Azure AD y MDM como medio principal para lograrlo en un personal móvil cada vez mayor. Los temas siguientes proporcionan una breve introducción a cada componente de infraestructura que se debe tener en cuenta en el planeamiento de la implementación para HoloLens 2.

### <a name="azure-active-directory"></a>Azure Active Directory
Azure AD es un servicio de directorio en la nube que proporciona administración de identidades y acceso. Puedes integrarlo con directorios locales existentes para crear una solución de identidad híbrida. Las organizaciones que usan Microsoft Office 365 o Intune ya usan Azure AD, que tiene tres ediciones: Gratis, Premium P1 y Premium P2 (consulte [Azure Active Directory ediciones](https://azure.microsoft.com/documentation/articles/active-directory-editions/)). Todas las ediciones admiten Azure AD de dispositivos, pero se requiere Premium P1 para habilitar la inscripción automática de MDM. HoloLens 2 requiere Azure Active Directory join para habilitar la mayoría de las características y funcionalidades de nivel empresarial.

> [!NOTE]
> La combinación Active Directory local no se admite en HoloLens 2.

### <a name="mobile-device-management"></a>Administración de dispositivos móviles
HoloLens 2 está diseñado específicamente para administrarse mediante sistemas de Administración de dispositivos móviles (MDM) en un entorno empresarial. Microsoft [Intune,](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune)parte de la Enterprise Mobility + Security, es un sistema MDM basado en la nube que administra dispositivos en la empresa. Al igual que Office 365, Intune usa Azure AD para la administración de identidades, por lo que los empleados usan las mismas credenciales para inscribir dispositivos en Intune que usan para iniciar sesión en Office 365. Muchos sistemas MDM admiten Windows 10, y la mayoría también admiten los escenarios de implementación de dispositivos personales y corporativos. Los sistemas MDM también pueden administrar implementaciones y actualizaciones de aplicaciones para HoloLens 2 también. Otros proveedores de MDM que admiten HoloLens 2 actualmente incluyen: AirWatch, MobileIron y otros. Todos los proveedores de sistemas MDM tienen el mismo acceso a los proveedores de servicios de configuración de administración de dispositivos (CSP) de Windows 10, lo que ofrece a las organizaciones de TI la libertad de seleccionar el sistema que mejor se adapte a sus requisitos de administración, ya sea Microsoft Intune o un producto MDM de terceros.

> [!NOTE]
> Los sistemas de administración de equipos locales tradicionales como System Center Administrador de configuración no se admiten en HoloLens 2.

### <a name="windows-update-for-business"></a>Windows Update para empresas
Microsoft diseñó Windows Update para empresas con el fin de proporcionar a los administradores de TI capacidades adicionales de administración centradas en Windows Update, tal como la posibilidad de implementar actualizaciones en grupos de dispositivos y definir ventanas de mantenimiento para la instalación de actualizaciones. Consulte la documentación [de actualizaciones de HoloLens](https://docs.microsoft.com/hololens/hololens-updates) para obtener más información sobre cómo administrar HoloLens 2 actualizaciones.

### <a name="certificates"></a>Certificados
HoloLens 2 admite la implementación de certificados a través de MDM si su entorno requiere certificados para la autenticación de red Wi-Fi Corp o acceso a otros recursos. Es posible que se requieran algunas configuraciones de infraestructura de MDM para permitir que las implementaciones de certificados HoloLens 2. Obtenga información sobre cómo [preparar certificados y perfiles de red para HoloLens 2](https://docs.microsoft.com/hololens/hololens-certificates-network). Si usa Intune, consulte los detalles de configuración [de certificación.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)

## <a name="configure"></a>Configuración

Los administradores de MDM pueden definir e implementar la configuración de directivas en cualquier dispositivo corporativo inscrito en un sistema MDM. Las opciones de configuración que use variarán en función del escenario de implementación. En Windows 10, los proveedores de servicios de configuración (CSP) son una interfaz para leer, establecer, modificar o eliminar valores de configuración en el dispositivo. Estas opciones de configuración se asignan a claves del Registro o archivos. Para obtener más información sobre Windows 10 DESP de administración de dispositivos para HoloLens 2, consulte la lista completa de LOSPS admitidos en dispositivos [HoloLens.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)

HoloLens 2 también admite la configuración de un conjunto limitado de configuraciones de CSP a través de paquetes de aprovisionamiento personalizados. Normalmente, los paquetes de aprovisionamiento se aprovechan para dispositivos no administrados con MDM y requieren que se apliquen manualmente a cada dispositivo. Consulte la documentación [de aprovisionamiento de HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning) para obtener más información sobre la creación de paquetes de aprovisionamiento personalizados.

> [!NOTE]
> HoloLens 2 admite [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot), lo que proporciona un proceso sencillo y sencillo para administrar las configuraciones Windows 10 dispositivos corporativos.

### <a name="identity-management"></a>Administración de identidades

Los empleados solo pueden usar una cuenta para inicializar un dispositivo, por lo&#39;que la organización controle qué cuenta está habilitada en primer lugar. La cuenta elegida determinará quién controla el dispositivo e influirá en las funcionalidades de administración. HoloLens 2 admite 3 tipos de cuenta: cuenta de usuario local, cuenta microsoft personal y Azure Active Directory cuentas. Se recomienda encarecidamente aprovechar Azure Active Directory para la solución de administración de identidades empresarial, ya que habilitará todas las funcionalidades en los HoloLens 2 dispositivos. Consulte La [identidad de HoloLens](https://docs.microsoft.com/hololens/hololens-identity) para obtener más detalles sobre las identidades para HoloLens 2.

### <a name="network-and-connectivity"></a>Red y conectividad

Como HoloLens 2 es un primer dispositivo en la nube, se requiere acceso de red a los recursos en línea para que todas las funcionalidades y funcionalidades estén disponibles. Si va a implementar dispositivos HoloLens 2 con conectividad a la red de intranet corporativa, es posible que tenga que actualizar las reglas de proxy o firewall para permitir el acceso HoloLens 2 servicios en la nube. Para obtener más información, consulte la lista de puntos de conexión comunes [para el HoloLens 2 operativo](https://docs.microsoft.com/hololens/hololens-offline). Es posible que se requiera acceso a puntos de conexión adicionales para que las aplicaciones u otros servicios en la nube se ejecuten HoloLens 2 correctamente.

Algunos servicios HoloLens 2 que requieren acceso adicional al punto de conexión son los siguientes:

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [Guías D365](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365 Remote Assist (infraestructura de O365 Teams)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### <a name="certificate-deployment"></a>Implementación de certificados

Si se requieren certificados para el acceso a redes Wi-Fi corporativas u otros servicios dentro de la organización, HoloLens 2 la implementación de certificados de usuario y dispositivo a través de MDM. Nota: La solución MDM puede requerir una configuración de infraestructura adicional para implementar certificados en Windows 10 dispositivos.

### <a name="security-review"></a>Revisión de seguridad

La mayoría de los departamentos de TI empresariales requerirán la evaluación y revisión de los nuevos dispositivos que se implementan en una red empresarial corporativa. Si su organización necesita una revisión de seguridad de HoloLens 2, puede encontrar más detalles para ayudar a obtener las [aprobaciones de seguridad](https://docs.microsoft.com/hololens/security-overview).

### <a name="common-hololens-2-device-settings"></a>Configuración HoloLens 2 dispositivos comunes

Al implementar HoloLens 2 dispositivos en un entorno empresarial corporativo, hay una serie de configuraciones de dispositivo comunes que se pueden tener en cuenta al planear la implementación de HoloLens 2. En esta lista se resaltan las configuraciones y los valores que se encuentran bastante comunes y no constan de una lista completa de opciones disponibles:

| Configuración del dispositivo | Breve descripción.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [Restricciones de hardware](hololens-requirements.md#hardware-restrictions)               | Las restricciones de hardware reducen la conectividad y ayudan en la protección de datos.                        |
| [Perfiles de Wi-Fi](hololens-requirements.md#wi-fi-profiles)               | Configure Wi-Fi perfiles sin intervención del usuario ni interacción.                              |
| [Certificados](hololens-requirements.md#certificates-1)               | Proporcione la autenticación de cuenta Wi-Fi, el cifrado VPN y el cifrado SSL de contenido web. |
| [Proxy](hololens-requirements.md#proxy)              | Administrar el tráfico interno.                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | Controlar el acceso a aplicaciones y recursos en la intranet de su empresa.                               |
| [Pantalla completa](hololens-requirements.md#kiosk-mode) | Limita las aplicaciones que se presentan a los usuarios a través de la interfaz de usuario. |

#### <a name="hardware-restrictions"></a>Restricciones de hardware

HoloLens 2 tecnología de última generación que incluye características de hardware populares, como cámaras, micrófonos, altavoces, interfaces USB, interfaces Bluetooth y Wi-Fi. Puedes usar restricciones de hardware para controlar la disponibilidad de estas funciones.

A continuación se enumeran las opciones de MDM más usadas que HoloLens 2 admiten para configurar restricciones de hardware. Algunas de estas restricciones de hardware proporcionan conectividad y ayudan en la protección de datos.

- [**Permitir Wi-Fi:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Si los usuarios pueden habilitar y usar la radio Wi-Fi en sus dispositivos
- [**Permitir conexión USB:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Si la conexión USB está habilitada (no&#39;a la carga USB)
- [**Permitir Bluetooth:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Si los usuarios pueden habilitar y usar la radio Bluetooth en sus dispositivos

Obtenga más información sobre [otras restricciones comunes de dispositivos.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### <a name="wi-fi-profiles"></a>Perfiles de Wi-Fi

La mayoría de las redes Wi-Fi corporativas requiere certificados y otra información compleja para restringir y proteger el acceso de usuario. Esta información Wi-Fi avanzada es difícil de configurar para los usuarios típicos, pero los sistemas MDM pueden configurar completamente estos perfiles Wi-Fi sin intervención del usuario. Es posible crear varios perfiles Wi-Fi en el sistema MDM.

Para obtener más información sobre Wi-Fi configuración de Windows 10, consulte [Configuración de Wi-Fi de perfil de empresa.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)

#### <a name="certificates"></a>Certificados

Los certificados ayudan a mejorar la seguridad al proporcionar autenticación de cuenta, Wi-Fi, cifrado VPN y cifrado SSL de contenido web. Aunque los administradores pueden administrar certificados en dispositivos manualmente a través de paquetes de&#39;aprovisionamiento, es un procedimiento recomendado usar el sistema MDM para administrar esos certificados durante todo su ciclo de vida, desde la inscripción hasta la renovación y revocación. El sistema MDM puede implementar automáticamente estos certificados en los dispositivos&#39; almacenes de certificados después de inscribir el dispositivo (siempre que el sistema MDM admita el Protocolo de inscripción de certificados simple (SCEP) o public Key Cryptography Standards #12 (PKCS #12)). MDM también puede consultar y eliminar certificados de cliente inscritos o desencadenar una nueva solicitud de inscripción antes de que el certificado actual haya expirado.

Obtenga más información sobre cómo [preparar certificados y perfiles de red para HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### <a name="proxy"></a>Proxy

La mayoría de las redes de intranet corporativas aprovechan un proxy para administrar el tráfico interno. Con HoloLens 2 puede configurar un servidor proxy para conexiones Ethernet Wi-Fi conexión. Esta configuración no se aplica a las conexiones VPN.

Para obtener más información sobre la configuración de proxy Windows 10, consulte [CSP de NetworkProxy.](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)

#### <a name="vpn"></a>VPN

A menudo, las organizaciones usan una VPN para controlar el acceso a las aplicaciones y los recursos de su&#39;la intranet. HoloLens 2 admite conexiones VPN SSL, que requieren un complemento descargable del Microsoft Store y son específicos del proveedor de VPN de su elección.

Para obtener más información acerca de los perfiles de VPN, consulta [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx) (CSP de VPNv2).

#### <a name="kiosk-mode"></a>Pantalla completa

Puede configurar un dispositivo HoloLens 2 para que funcione como un dispositivo de propósito fijo, también denominado pantalla completa, configurando el dispositivo para que se ejecute en pantalla completa. El modo de pantalla completa limita las aplicaciones (o usuarios) que están disponibles en el dispositivo. El modo de pantalla completa es una característica práctica que puede usar para dedicar un dispositivo HoloLens 2 a aplicaciones empresariales o para usar el dispositivo HoloLens 2 en una demostración de aplicación.

Para obtener más información sobre cómo configurar un HoloLens 2 pantalla completa, consulte [Configuración de HoloLens como quiosco.](https://docs.microsoft.com/hololens/hololens-kiosk)

## <a name="deploy"></a>Implementar

### <a name="mdm-device-enrollment"></a>Inscripción de dispositivos MDM

En el caso de las [](https://docs.microsoft.com/hololens/hololens-enroll-mdm) implementaciones empresariales, se recomienda inscribir dispositivos en MDM como dispositivos corporativos solo con una Azure AD y la inscripción automática de MDM (Azure AD+MDM). Esto requiere Azure AD Premium y admite la inscripción automática a varios proveedores de MDM, incluido Intune.

Obtenga más información sobre el método de inscripción auto-implementando [Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot).

### <a name="application-deployment"></a>Implementación de aplicaciones

A menudo, la productividad del usuario en los dispositivos móviles está condicionada por las aplicaciones.

Windows 10 hace posible desarrollar aplicaciones que funcionen de manera óptima en varios dispositivos con la Plataforma universal de Windows (UWP) para aplicaciones de Windows.

Hay varias maneras de implementar aplicaciones para HoloLens 2 dispositivos. Las aplicaciones se pueden implementar directamente a través de MDM, el Microsoft Store para Empresas o se pueden descargar localmente a través de un paquete de aprovisionamiento. Consulte la documentación [de implementación de](https://docs.microsoft.com/hololens/app-deploy-overview) aplicaciones para obtener más detalles.

> [!NOTE]
> HoloLens 2 solo admite la ejecución de aplicaciones arm64 para UWP.

## <a name="maintain"></a>Mantenimiento

En los entornos de TI empresariales, la necesidad de administración y el control de costes se debe equilibrar con el deseo de ofrecer a los usuarios las tecnologías más recientes. Dado que los ciberataques se han convertido en una ocurrencia diaria, es importante mantener correctamente el estado de los dispositivos Windows 10 dispositivos. El departamento de TI debe controlar las opciones de configuración, impidiendo que incumplan los requisitos, así como hacer cumplir qué dispositivos pueden acceder a las aplicaciones internas. HoloLens 2 proporciona las funcionalidades de administración de operaciones móviles necesarias para garantizar que los dispositivos cumplen con la directiva corporativa.

### <a name="os-servicing-options"></a>Opciones de mantenimiento del sistema operativo

**Un proceso de actualización optimizado**

Microsoft ha optimizado el ciclo de ingeniería y lanzamiento de productos Windows para que las nuevas características, experiencias y funcionalidades que demanda el mercado se puedan ofrecer de forma más rápida que nunca. Microsoft tiene planeado entregar 2 actualizaciones de características al año (en un período de 12 meses). **Las actualizaciones de** características establecen Rama actual o CB y tienen una versión asociada.

Microsoft también entregará e instalará actualizaciones para la seguridad y la estabilidad directamente en HoloLens 2 dispositivos. Estas **actualizaciones de calidad,** publicadas bajo control de Microsoft Windows Update, están disponibles mensualmente. HoloLens 2 actualizaciones de características y actualizaciones de calidad como parte del mismo proceso de actualización estándar.

Los clientes empresariales pueden administrar la experiencia de actualización y el proceso en HoloLens 2s mediante un sistema MDM. En la mayoría de los casos, se aplicarán directivas para administrar el proceso de actualización tanto en el caso de actualizaciones de características como de calidad. Más información sobre [la configuración de MDM para las actualizaciones de HoloLens.](https://docs.microsoft.com/hololens/hololens-updates)

### <a name="managing-applications"></a>Administrar aplicaciones

Los administradores de TI pueden controlar qué aplicaciones se pueden instalar en el HoloLens 2 y cómo deben mantenerse actualizadas.

HoloLens 2 admite [Windows Defender Application Control (WDAC),](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)que permite a los administradores crear, permitir o no listas de aplicaciones de la Microsoft Store. Esta funcionalidad también se extiende a las aplicaciones integradas. La capacidad de permitir o denegar aplicaciones ayuda a garantizar que las personas usan sus dispositivos para sus fines previstos. Sin embargo, no siempre resulta sencillo encontrar un equilibrio entre lo que los empleados necesitan o solicitan y los problemas de seguridad. La creación de listas de permitidos o no permitidos también requiere mantenerse al día con el panorama cambiante de la aplicación en el Microsoft Store.

Para más información, consulte [CSP de Control de aplicaciones.](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)

### <a name="retire"></a>Retirar

La retirada de dispositivos es la última fase del ciclo de vida del dispositivo. Es&#39;que los dispositivos que se reemplazan por modelos más recientes se retiren de forma segura, ya que no&#39;desea que los datos de la empresa permanezcan en dispositivos descartados que podrían poner en peligro la confidencialidad de los datos. El departamento de TI también necesita una forma de dar soporte de forma adecuada a los usuarios que necesiten borrar los dispositivos perdidos o robados.

HoloLens 2 admite 3 métodos para borrar el dispositivo

**Borrado de fábrica de MDM:** Restablece el HoloLens 2 a la imagen de fábrica mediante el comando MDM iniciado por el administrador. Borra todos los datos almacenados en el dispositivo.

**Restablecimiento de dispositivos desde la configuración:** Los usuarios finales pueden restablecer manualmente la HoloLens 2 dentro de la aplicación Configuración del dispositivo. Borra todos los datos almacenados en el dispositivo.

**Advanced Recovery Companion (ARC):** Desde un equipo que ejecuta la herramienta ARC, un usuario o administrador puede flashear un HoloLens 2 conectado al equipo a través de un cable USB. Borra todos los datos almacenados en el dispositivo.

> [!div class="nextstepaction"]
> [Escenarios comunes de implementación](common-scenarios.md)
