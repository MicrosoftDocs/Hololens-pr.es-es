---
title: Configurar HoloLens en un entorno comercial
description: Más información sobre cómo implementar y administrar HoloLens en entornos empresariales.
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
ms.openlocfilehash: 5f24d62193f083f96144b7e8c3518dc97c14be68
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "11195593"
---
# Administración y implementación empresarial de HoloLens 2

Esta información general pretende ayudar a los profesionales de ti a comprender las consideraciones para implementar y administrar dispositivos de Microsoft HoloLens 2 dentro de la empresa.

HoloLens 2 se ejecuta en Windows 10 Holographic, que ofrece a las organizaciones aplicaciones de administración de aplicaciones y dispositivos móviles integradas y flexibles. Windows 10 Holographic admite la administración del ciclo de vida de un dispositivo completo para ofrecer a las empresas el control de sus dispositivos, datos y aplicaciones. HoloLens 2 se puede incorporar fácilmente a prácticas estándar del ciclo de vida, desde la inscripción de dispositivos, la configuración y la administración de aplicaciones hasta el mantenimiento y la jubilación con una solución completa de administración de dispositivos móviles.

## Preparar

Mientras preparas para implementar HoloLens 2 en tu entorno empresarial corporativo, hay varias consideraciones que debes revisar y comprender a medida que comienzas a planear implementaciones a escala de HoloLens 2.

### Conceptos básicos de la infraestructura

Para HoloLens 2 en un escenario de implementación empresarial corporativa, hay ciertos servicios de infraestructura esenciales necesarios para admitir el conjunto completo de capacidades. HoloLens 2 se creó teniendo en cuenta la [Administración moderna de los dispositivos móviles](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) para su implementación y administración. Con Azure AD join + MDM como el medio principal para lograr eso en un personal móvil en constante aumento. Los temas siguientes proporcionan una breve descripción general de cada componente de la infraestructura que debe considerarse en su plan de implementación para HoloLens 2.

### Azure Active Directory
Azure AD es un servicio de directorio en la nube que proporciona administración de identidades y acceso. Puedes integrarlo con directorios locales existentes para crear una solución de identidad híbrida. Las organizaciones que usan Microsoft Office 365 o Intune ya usan Azure AD, que tiene tres ediciones: gratis, Premium P1 y Premium P2 (vea [Azure Active Directory Editions](https://azure.microsoft.com/documentation/articles/active-directory-editions/)). Todas las ediciones son compatibles con el registro de dispositivos de Azure AD, pero se necesita la Premium P1 para habilitar la inscripción automática de MDM. HoloLens 2 requiere la combinación de Azure Active Directory para habilitar la mayoría de las características y funcionalidades de nivel empresarial.

> [!NOTE]
> La Unión local de Active Directory no es compatible con HoloLens 2.

### Administración de dispositivos móviles
HoloLens 2 se ha diseñado específicamente para que lo administren los sistemas de administración de dispositivos móviles (MDM) en un entorno empresarial. Microsoft [Intune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune), parte de la seguridad y movilidad empresarial, es un sistema MDM basado en la nube que administra dispositivos de la empresa. Al igual que Office 365, Intune usa Azure AD para la administración de identidades, por lo que los empleados usan las mismas credenciales para inscribir dispositivos en Intune que usan para iniciar sesión en Office 365. Muchos sistemas MDM admiten Windows10, y la mayoría también admiten los escenarios de implementación de dispositivos personales y corporativos. Los sistemas MDM también pueden administrar implementaciones y actualizaciones de aplicaciones para HoloLens 2. Otros proveedores de MDM que son compatibles con HoloLens 2 son: electrowatch, MobileIron y otros. Todos los proveedores de sistemas de MDM tienen el mismo acceso a proveedores de servicios de configuración de administración de dispositivos (CSP) de Windows 10, lo que ofrece a las organizaciones la libertad de seleccionar cualquier sistema que se adapte mejor a sus requisitos de administración, ya sea Microsoft Intune o un producto MDM de terceros.

> [!NOTE]
> Los sistemas de administración de PC locales en local como System Center Configuration Manager no son compatibles con HoloLens 2.

### Windows Update para empresas
Microsoft diseñó Windows Update para empresas con el fin de proporcionar a los administradores de TI capacidades adicionales de administración centradas en Windows Update, tal como la posibilidad de implementar actualizaciones en grupos de dispositivos y definir ventanas de mantenimiento para la instalación de actualizaciones. Puedes encontrar más información sobre cómo administrar las actualizaciones de HoloLens 2 [aquí](https://docs.microsoft.com/hololens/hololens-updates).

### Certificados
HoloLens 2 admite la implementación de certificados a través de MDM si su entorno requiere certificados para Corp Wi-Fi la autenticación de red o el acceso a otros recursos. Es posible que se requieran algunas configuraciones de infraestructura de MDM para habilitar las implementaciones de certificados en HoloLens 2. Obtenga información sobre cómo [preparar certificados y perfiles de red para HoloLens 2](https://docs.microsoft.com/hololens/hololens-certificates-network). Puede encontrar los detalles de Intune [aquí](https://docs.microsoft.com/mem/intune/protect/certificates-configure).

## Configurar

Los administradores de MDM pueden definir e implementar la configuración de la Directiva en cualquier dispositivo corporativo inscrito en un sistema MDM. La configuración que use será diferente en función del escenario de implementación. En Windows 10, los proveedores de servicios de configuración (CSP) s son una interfaz para leer, establecer, modificar o eliminar la configuración en el dispositivo. Estas opciones de configuración se asignan a claves del Registro o archivos. Para obtener más información sobre los CSP de administración de dispositivos de Windows 10 para HoloLens 2, consulte la lista completa de [CSP admitidos en los dispositivos HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).

HoloLens 2 también admite la configuración de un conjunto limitado de configuraciones de CSP mediante paquetes de aprovisionamiento personalizados. Los paquetes de aprovisionamiento generalmente se aprovechan para dispositivos no administrados con MDM y requieren que se apliquen de forma manual a cada dispositivo. Puede encontrar más información sobre cómo crear paquetes de aprovisionamiento personalizados [aquí](https://docs.microsoft.com/hololens/hololens-provisioning).

> [!NOTE]
> HoloLens 2 es compatible con [Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot), lo que proporciona un proceso sencillo y simple para administrar las configuraciones de dispositivos empresariales de Windows 10.

### Administración de identidades

Los empleados solo pueden usar una cuenta para inicializar un dispositivo, por lo que&#39;s es imprescindible que la organización controle qué cuenta está habilitada en primer lugar. La cuenta elegida determinará quién controla el dispositivo e influirá en las funcionalidades de administración. HoloLens 2 admite tres tipos de cuenta: cuenta de usuario local, cuenta personal de Microsoft y cuentas de Azure Active Directory. Se recomienda enfáticamente aprovechar Azure Active Directory para su solución de administración de identidades empresarial, ya que permitirá las capacidades completas en sus dispositivos HoloLens 2. Puedes encontrar más información sobre las identidades en HoloLens 2 [aquí](https://docs.microsoft.com/hololens/hololens-identity).

### Red y conectividad

Como HoloLens 2 es un dispositivo en la nube, el acceso a los recursos en línea es necesario para que toda la funcionalidad y las funciones estén disponibles. Si implementas dispositivos HoloLens 2 con conectividad a tu red de intranet corporativa, es posible que tengas que actualizar las reglas de proxy o firewall para permitir el acceso a los servicios en la nube de HoloLens 2. [Aquí](https://docs.microsoft.com/hololens/hololens-offline)puedes encontrar una lista de puntos de conexión comunes necesarios para el sistema operativo HoloLens 2. Es posible que se requiera el acceso a puntos de conexión adicionales para que las aplicaciones u otros servicios en la nube se ejecuten correctamente en HoloLens 2.

Algunos de los servicios comunes de HoloLens 2 que requieren acceso de extremo adicionales son los siguientes:

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [Guías de D365](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [Asistencia remota de D365 (infraestructura de O365 Teams)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### Implementación de certificados

Si se necesitan certificados para acceder a redes Wi-Fi corporativas o a otros servicios de su organización, HoloLens 2 admite la implementación de certificados de usuario y dispositivo a través de MDM. Nota: la solución MDM puede requerir una configuración de infraestructura adicional para implementar certificados en dispositivos Windows 10.

### Revisión de seguridad

La mayoría de los departamentos de TI empresariales necesitarán la evaluación y revisión de nuevos dispositivos que se implementarán en una red empresarial corporativa. Si su organización necesita una revisión de seguridad de HoloLens 2, puede [encontrar más detalles aquí para ayudarle a obtener aprobaciones de seguridad](https://docs.microsoft.com/hololens/security-overview).

### Configuración de dispositivo común de HoloLens 2

Al implementar dispositivos HoloLens 2 en un entorno empresarial corporativo, hay varias configuraciones de dispositivos comunes que pueden considerarse al planear la implementación de HoloLens 2. En esta lista se resaltan las configuraciones y la configuración que se considera bastante común, y no se incluye una lista completa de las opciones disponibles:

| Configuración del dispositivo | Descripción breve.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [Restricciones de hardware](hololens-requirements.md#hardware-restrictions)               | Las restricciones de hardware reducen la conectividad y ayudan en la protección de datos.                        |
| [Perfiles Wi-Fi](hololens-requirements.md#wi-fi-profiles)               | Configure Wi-Fi perfiles sin intervención del usuario ni interacción.                              |
| [Certificados](hololens-requirements.md#certificates-1)               | Proporcionar autenticación de cuentas y/o Wi-Fi, cifrado de VPN y cifrado SSL de contenido Web. |
| [Proxy](hololens-requirements.md#proxy)              | Administrar el tráfico interno.                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | Controlar el acceso a las aplicaciones y recursos de la intranet de su empresa.                               |
| [Pantalla completa](hololens-requirements.md#kiosk-mode) | Limita las aplicaciones que se presentan a los usuarios a través de la interfaz de usuario. |

#### Restricciones de hardware

HoloLens 2 usa tecnología de vanguardia que incluye características de hardware populares, como cámaras, micrófonos, altavoces, interfaces USB, interfaces Bluetooth y Wi-Fi. Puedes usar restricciones de hardware para controlar la disponibilidad de estas funciones.

En la siguiente lista se enumeran las opciones de configuración de MDM que son compatibles con HoloLens 2 para configurar restricciones de hardware. Algunas de estas restricciones de hardware proporcionan conectividad y ayudan en la protección de datos.

- [**Permitir WiFi:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Si los usuarios pueden habilitar y usar la Wi-Fi radio en sus dispositivos
- [**Permitir conexión USB:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Si la conexión USB está habilitada (hace&#39;t afecta a la carga de USB)
- [**Permitir Bluetooth:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Si los usuarios pueden habilitar y usar la radio Bluetooth en sus dispositivos

Más información sobre otras [restricciones de dispositivos comunes.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### Perfiles Wi-Fi

La mayoría de las redes Wi-Fi corporativas requiere certificados y otra información compleja para restringir y proteger el acceso de usuario. Esta información de Wi-Fi avanzada es difícil para los usuarios típicos de configuración, pero MDM puede configurar por completo estos Wi-Fi perfiles sin la intervención del usuario. Es posible crear varios perfiles Wi-Fi en el sistema MDM.

Para obtener más información sobre la configuración de Wi-Fi para Windows 10, consulta [configuración del perfil de empresa WiFi](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile).

#### Certificados

Los certificados ayudan a mejorar la seguridad proporcionando autenticación de cuenta, autenticación de Wi-Fi, cifrado de VPN y cifrado SSL de contenido Web. A pesar de que los administradores pueden administrar certificados en dispositivos de forma manual mediante paquetes de aprovisionamiento,&#39;s es un procedimiento recomendado para usar su sistema MDM para administrar esos certificados durante todo su ciclo de vida, desde la inscripción a través de la renovación y la revocación. El sistema MDM puede implementar automáticamente estos certificados en los dispositivos&#39; los almacenes de certificados después de inscribir el dispositivo (siempre y cuando el sistema MDM admita el protocolo de inscripción de certificados simple (SCEP) o los estándares de criptografía de clave pública #12 (PKCS # 12)). MDM también puede consultar y eliminar certificados de cliente inscritos o desencadenar una nueva solicitud de inscripción antes de que venza el certificado actual.

Más información sobre cómo [preparar certificados y perfiles de red para HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### Proxy

La mayoría de las redes de intranet corporativas aprovechan un proxy para administrar el tráfico interno. Con HoloLens 2 puedes configurar un servidor proxy para conexiones Ethernet y Wi-Fi. Esta configuración no se aplica a las conexiones VPN.

Para obtener más información sobre la configuración de proxy para Windows 10, consulte [CSP NetworkProxy](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

#### VPN

Las organizaciones suelen usar una VPN para controlar el acceso a las aplicaciones y los recursos de la intranet de su empresa&#39;s. HoloLens 2 es compatible con las conexiones SSL VPN, que requieren un complemento que se pueda descargar de la tienda de Microsoft y que sean específicas del proveedor de VPN que elija.

Para obtener más información acerca de los perfiles de VPN, consulta [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx) (CSP de VPNv2).

#### Pantalla completa

Puede configurar un dispositivo HoloLens 2 para que funcione como un dispositivo de propósito fijo, también denominado quiosco, configurando el dispositivo para que se ejecute en el modo de pantalla completa. En el modo de pantalla completa, se limitan las aplicaciones (o usuarios) que están disponibles en el dispositivo. El modo de pantalla completa es una característica muy útil que puedes usar para dedicar un dispositivo HoloLens 2 a aplicaciones empresariales o para usar el dispositivo HoloLens 2 en una demostración de la aplicación.

Para obtener más información sobre cómo configurar HoloLens 2 en modo de pantalla completa, consulta [configurar hololens como exposición](https://docs.microsoft.com/hololens/hololens-kiosk)

## Implementar

### Inscripción de dispositivo MDM

Para las implementaciones empresariales, se recomienda [inscribir dispositivos](https://docs.microsoft.com/hololens/hololens-enroll-mdm) en MDM como dispositivos empresariales solo con la inscripción automática de Azure ad y la inscripción automática de MDM (AAD + MDM). Esto requiere Azure AD Premium y admite la inscripción automática a varios proveedores de MDM, incluido Intune.

Obtenga más información sobre el método de inscripción autoimplementado [AutoPilot](https://docs.microsoft.com/hololens/hololens2-autopilot).

### Implementación de aplicaciones

A menudo, la productividad del usuario en los dispositivos móviles está condicionada por las aplicaciones.

Windows10 hace posible desarrollar aplicaciones que funcionen de manera óptima en varios dispositivos con la Plataforma universal de Windows (UWP) para aplicaciones de Windows.

Hay varias maneras de implementar aplicaciones en dispositivos HoloLens 2. Las aplicaciones se pueden implementar directamente a través de MDM, Microsoft Store para empresas o transferidas a través de un paquete de aprovisionamiento. [Puede encontrar más información sobre la implementación de aplicaciones aquí](https://docs.microsoft.com/hololens/app-deploy-overview).

> [!NOTE]
> HoloLens 2 solo admite el funcionamiento de aplicaciones de ARM64 de UWP.

## Mantener

En los entornos de TI empresariales, la necesidad de administración y el control de costes se debe equilibrar con el deseo de ofrecer a los usuarios las tecnologías más recientes. Dado que cyberattacks se ha convertido en una incidencia diaria, es importante mantener correctamente el estado de los dispositivos con Windows 10. El departamento de TI debe controlar las opciones de configuración, impidiendo que incumplan los requisitos, así como hacer cumplir qué dispositivos pueden acceder a las aplicaciones internas. HoloLens 2 ofrece las funciones de administración de operaciones móviles necesarias para garantizar que los dispositivos cumplan con las directivas corporativas.

### Opciones de mantenimiento del sistema operativo

**Un proceso de actualización optimizado**

Microsoft ha optimizado el ciclo de ingeniería y lanzamiento de productos Windows para que las nuevas características, experiencias y funcionalidades que demanda el mercado se puedan ofrecer de forma más rápida que nunca. Microsoft tiene planeado entregar 2 actualizaciones de características al año (en un período de 12 meses). **Las actualizaciones de características** establecen una rama o CB actual, y tienen una versión asociada.

Microsoft también proporcionará e instalará actualizaciones de seguridad y estabilidad directamente en dispositivos HoloLens 2. Estas **actualizaciones de calidad** , publicadas bajo control de Microsoft a través de Windows Update, están disponibles mensualmente. HoloLens 2 consume actualizaciones de características y de calidad como parte del mismo proceso de actualización estándar.

Los clientes empresariales pueden administrar la experiencia de actualización y el proceso en HoloLens 2s con un sistema MDM. En la mayoría de los casos, se aplicarán directivas para administrar el proceso de actualización tanto en el caso de actualizaciones de características como de calidad. Más detalles en la [configuración de MDM para las actualizaciones de HoloLens](https://docs.microsoft.com/hololens/hololens-updates).

### Administración de aplicaciones

Los administradores de TI pueden controlar qué aplicaciones están autorizadas a instalarse en HoloLens 2 y cómo se deben mantener actualizadas.

HoloLens 2 es compatible con el [control de aplicaciones de Windows Defender (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac), que permite a los administradores crear, permitir o impedir listas de aplicaciones de Microsoft Store. Esta funcionalidad se extiende también a las aplicaciones integradas. La capacidad de permitir o denegar aplicaciones ayuda a garantizar que las personas usen sus dispositivos para sus fines previstos. Sin embargo, no siempre resulta sencillo encontrar un equilibrio entre lo que los empleados necesitan o solicitan y los problemas de seguridad. La creación de listas de aplicaciones permitidas y no permitidas también requiere mantenerse al día del cambiante mundo de las aplicaciones de Microsoft Store.

Para obtener más información, consulta [CSP de control de aplicaciones](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp).

### Retirar

La retirada del dispositivo es la última fase del ciclo de vida del dispositivo. &#39;s es importante que los dispositivos que se reemplazan con nuevos modelos estén retirados de forma segura, ya que no&#39;desea que los datos de la compañía permanezcan en dispositivos descartados que podrían poner en peligro la confidencialidad de los datos. El departamento de TI también necesita una forma de dar soporte de forma adecuada a los usuarios que necesiten borrar los dispositivos perdidos o robados.

HoloLens 2 es compatible con 3 métodos para borrar el dispositivo

**Borrado de fábrica de MDM:** Restablece HoloLens 2 a la imagen de fábrica a través de un comando MDM Iniciado por un administrador. Borra todos los datos almacenados en el dispositivo.

**Restablecimiento del dispositivo desde la configuración:** Los usuarios finales pueden restablecer de forma manual HoloLens 2 en la aplicación configuración del dispositivo. Borra todos los datos almacenados en el dispositivo.

**Asistente de recuperación avanzada (ARC):** Desde un equipo con la herramienta ARC, un usuario o administrador puede hacer parpadear a HoloLens 2 conectado al equipo a través del cable USB. Borra todos los datos almacenados en el dispositivo.

> [!div class="nextstepaction"]
> [Escenarios de implementación comunes](common-scenarios.md)