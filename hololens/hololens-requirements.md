---
title: Configurar HoloLens en un entorno comercial
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
ms.openlocfilehash: 9458a6fd02cf96dd265580cb099e39fa221d4206
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284051"
---
# Implementación y administración empresarial de HoloLens 2

Esta introducción está pensada para ayudar a los profesionales de TI a comprender las consideraciones para implementar y administrar dispositivos De Microsoft HoloLens 2 en la empresa.

HoloLens 2 se ejecuta en Windows 10 Holographic, que proporciona a las organizaciones tecnologías sólidas, flexibles e integradas de administración de dispositivos móviles y aplicaciones. Windows 10 Holographic admite la administración del ciclo de vida de dispositivos de un extremo a otro para dar a las empresas el control sobre sus dispositivos, datos y aplicaciones. HoloLens 2 se puede incorporar fácilmente a los procedimientos de ciclo de vida estándar, desde la inscripción, la configuración y la administración de aplicaciones de dispositivos hasta el mantenimiento y la retirada mediante una solución completa de administración de dispositivos móviles.

## Preparar

A medida que se prepara para implementar HoloLens 2 en su entorno empresarial corporativo, hay varias consideraciones que deben revisarse y comprenderse a medida que comience a planear implementaciones de escala de HoloLens 2.

### Infrastructure Essentials

Para HoloLens 2 en un escenario de implementación empresarial corporativa, hay ciertos servicios de infraestructura esenciales necesarios para admitir todo el conjunto de funcionalidades. HoloLens 2 se creó pensando en la administración de [dispositivos](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) móviles modernos para la implementación y la administración. Con Azure AD Join + MDM como medio principal para lograrlo en un creciente personal móvil. Los siguientes temas proporcionan una breve introducción a cada componente de infraestructura que debe tenerse en cuenta en la planeación de implementación de HoloLens 2.

### Azure Active Directory
Azure AD es un servicio de directorio en la nube que proporciona administración de identidades y acceso. Puedes integrarlo con directorios locales existentes para crear una solución de identidad híbrida. Las organizaciones que usan Microsoft Office 365 o Intune ya usan Azure AD, que tiene tres ediciones: gratuita, Premium P1 y Premium P2 (vea las ediciones de [Azure Active Directory).](https://azure.microsoft.com/documentation/articles/active-directory-editions/) Todas las ediciones admiten el registro de dispositivos de Azure AD, pero se requiere Premium P1 para habilitar la inscripción automática de MDM. HoloLens 2 requiere la unión a Azure Active Directory para habilitar la mayoría de las características y funcionalidades de nivel empresarial.

> [!NOTE]
> La unión local a Active Directory no se admite en HoloLens 2.

### Administración de dispositivos móviles
HoloLens 2 está diseñado específicamente para ser administrado por sistemas de administración de dispositivos móviles (MDM) en un entorno empresarial. Microsoft [Intune,](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune)parte de Enterprise Mobility + Security, es un sistema MDM basado en la nube que administra dispositivos en la empresa. Al igual que Office 365, Intune usa Azure AD para la administración de identidades, por lo que los empleados usan las mismas credenciales para inscribir dispositivos en Intune que usan para iniciar sesión en Office 365. Muchos sistemas MDM admiten Windows10, y la mayoría también admiten los escenarios de implementación de dispositivos personales y corporativos. Los sistemas MDM también pueden administrar las implementaciones de aplicaciones y las actualizaciones de HoloLens 2. Actualmente, otros proveedores de MDM compatibles con HoloLens 2 incluyen: AirWatch, MobileIron y otros. Todos los proveedores de sistemas MDM tienen el mismo acceso a los proveedores de servicios de configuración de administración de dispositivos (CSP) de Windows 10, lo que da a las organizaciones de TI la libertad de seleccionar el sistema que mejor se adapte a sus requisitos de administración, ya sea Microsoft Intune o un producto MDM de terceros.

> [!NOTE]
> Los sistemas de administración de EQUIPOS locales tradicionales, como System Center Configuration Manager, no se admiten en HoloLens 2.

### Windows Update para empresas
Microsoft diseñó Windows Update para empresas con el fin de proporcionar a los administradores de TI capacidades adicionales de administración centradas en Windows Update, tal como la posibilidad de implementar actualizaciones en grupos de dispositivos y definir ventanas de mantenimiento para la instalación de actualizaciones. Consulta la documentación [de actualizaciones de HoloLens](https://docs.microsoft.com/hololens/hololens-updates) para obtener más información sobre cómo administrar las actualizaciones de HoloLens 2.

### Certificados
HoloLens 2 admite la implementación de certificados a través de MDM si su entorno requiere certificados para la autenticación de red corp Wi-Fi o el acceso a otros recursos. Algunas configuraciones de infraestructura MDM pueden ser necesarias para habilitar implementaciones de certificados en HoloLens 2. Obtenga información sobre cómo [preparar certificados y perfiles de red para HoloLens 2](https://docs.microsoft.com/hololens/hololens-certificates-network). Si usa Intune, consulte los detalles de configuración [de](https://docs.microsoft.com/mem/intune/protect/certificates-configure) certificación.

## Configurar

Los administradores de MDM pueden definir e implementar la configuración de directiva en cualquier dispositivo corporativo inscrito en un sistema MDM. Las opciones de configuración que use variarán en función del escenario de implementación. En Windows 10, los proveedores de servicios de configuración (CSP) son una interfaz para leer, establecer, modificar o eliminar opciones de configuración en el dispositivo. Estas opciones de configuración se asignan a claves del Registro o archivos. Para obtener más información acerca de los CSP de administración de dispositivos Windows 10 para HoloLens 2, consulta la lista completa de LOSP compatibles con [dispositivos HoloLens.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)

HoloLens 2 también admite la configuración de un conjunto limitado de configuraciones de CSP a través de paquetes de aprovisionamiento personalizados. Normalmente, los paquetes de aprovisionamiento se aprovechan para dispositivos que no son administrados por MDM y requieren que se apliquen manualmente a cada dispositivo. Consulta la documentación [de aprovisionamiento de HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning) para obtener más información sobre la creación de paquetes de aprovisionamiento personalizados.

> [!NOTE]
> HoloLens 2 admite [Windows Autopilot,](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)lo que proporciona un proceso sencillo y sencillo para administrar las configuraciones corporativas de dispositivos Windows 10.

### Administración de identidades

Los empleados solo pueden usar una cuenta para inicializar un dispositivo, por lo que es&#39;imperativo que la organización controle qué cuenta está habilitada en primer lugar. La cuenta elegida determinará quién controla el dispositivo e influirá en las funcionalidades de administración. HoloLens 2 admite 3 tipos de cuenta: cuenta de usuario local, cuenta personal de Microsoft y cuentas de Azure Active Directory. Es muy recomendable aprovechar Azure Active Directory para su solución de administración de identidades empresarial, ya que habilitará todas las funcionalidades en sus dispositivos HoloLens 2. Echa un vistazo [a la identidad de HoloLens](https://docs.microsoft.com/hololens/hololens-identity) para obtener más información sobre las identidades de HoloLens 2.

### Red y conectividad

Como HoloLens 2 es un primer dispositivo en la nube, el acceso de red a los recursos en línea es necesario para que todas las funcionalidades y funcionalidades estén disponibles. Si implementa dispositivos HoloLens 2 con conectividad a la red de intranet corporativa, es posible que deba actualizar las reglas de proxy o firewall para permitir el acceso a los servicios en la nube de HoloLens 2. Para obtener más información, echa un vistazo a la lista de puntos de conexión comunes para el sistema operativo [HoloLens 2](https://docs.microsoft.com/hololens/hololens-offline). Es posible que se requiera acceso a puntos de conexión adicionales para que las aplicaciones u otros servicios en la nube se ejecuten correctamente en HoloLens 2.

Algunos servicios comunes de HoloLens 2 que requieren acceso a puntos de conexión adicionales son los siguientes:

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [Guías D365](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [Asistencia remota D365 (infraestructura de Teams de O365)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### Implementación de certificados

Si se requieren certificados para obtener acceso a redes Wi-Fi corporativas u otros servicios de la organización, HoloLens 2 admite la implementación de certificados de usuario y dispositivo a través de MDM. Nota: Es posible que la solución MDM requiera una configuración de infraestructura adicional para implementar certificados en dispositivos Windows 10.

### Revisión de seguridad

La mayoría de los departamentos de TI empresariales requerirán la evaluación y revisión de los nuevos dispositivos que se implementan en una red empresarial corporativa. Si su organización necesita una revisión de seguridad de HoloLens 2, puede encontrar más detalles para ayudar a obtener [aprobaciones de seguridad.](https://docs.microsoft.com/hololens/security-overview)

### Configuración común de dispositivos HoloLens 2

Al implementar dispositivos HoloLens 2 en un entorno empresarial corporativo, hay una serie de configuraciones de dispositivo comunes que se pueden tener en cuenta al planear la implementación de HoloLens 2. En esta lista se resaltan las configuraciones y las opciones que se encuentran bastante comunes y no se compone de una lista completa de opciones disponibles:

| Configuración del dispositivo | Breve descripción.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [Restricciones de hardware](hololens-requirements.md#hardware-restrictions)               | Las restricciones de hardware reducen la conectividad y ayudan a la protección de datos.                        |
| [Perfiles Wi-Fi](hololens-requirements.md#wi-fi-profiles)               | Configurar Wi-Fi perfiles sin intervención ni interacción del usuario.                              |
| [Certificados](hololens-requirements.md#certificates-1)               | Proporcionar autenticación de cuenta o Wi-Fi, cifrado VPN y cifrado SSL de contenido web. |
| [Proxy](hololens-requirements.md#proxy)              | Administrar el tráfico interno.                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | Controlar el acceso a aplicaciones y recursos en la intranet de su empresa.                               |
| [Pantalla completa](hololens-requirements.md#kiosk-mode) | Limita las aplicaciones que se presentan a los usuarios a través de la interfaz de usuario. |

#### Restricciones de hardware

HoloLens 2 usa tecnología de última generación que incluye características de hardware populares como cámaras, micrófonos, altavoces, interfaces USB, interfaces Bluetooth y Wi-Fi. Puedes usar restricciones de hardware para controlar la disponibilidad de estas funciones.

A continuación se enumeran las opciones de configuración de MDM más usadas que HoloLens 2 admite para configurar restricciones de hardware. Algunas de estas restricciones de hardware proporcionan conectividad y ayudan en la protección de datos.

- [**Permitir WiFi:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Indica si los usuarios pueden habilitar y usar la Wi-Fi en sus dispositivos
- [**Permitir conexión USB:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Si la conexión USB está habilitada (no&#39;a la carga USB)
- [**Permitir Bluetooth:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Indica si los usuarios pueden habilitar y usar la Bluetooth en sus dispositivos

Obtenga más información sobre [otras restricciones de dispositivo comunes.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### Perfiles Wi-Fi

La mayoría de las redes Wi-Fi corporativas requiere certificados y otra información compleja para restringir y proteger el acceso de usuario. Esta información Wi-Fi avanzada es difícil de configurar para los usuarios habituales, pero los sistemas MDM pueden configurar completamente estos Wi-Fi perfiles sin la intervención del usuario. Es posible crear varios perfiles Wi-Fi en el sistema MDM.

Para obtener más información sobre Wi-Fi configuración de Windows 10, consulta Configuración [de WiFi de](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)perfil de empresa.

#### Certificados

Los certificados ayudan a mejorar la seguridad proporcionando autenticación de cuenta, Wi-Fi autenticación, cifrado VPN y cifrado SSL de contenido web. Aunque los administradores pueden administrar certificados en dispositivos manualmente a través de paquetes de aprovisionamiento,&#39;es un procedimiento recomendado usar el sistema MDM para administrar esos certificados durante todo su ciclo de vida, desde la inscripción hasta la renovación y la revocación. El sistema MDM puede implementar automáticamente estos certificados en los dispositivos&#39; almacenes de certificados después de inscribir el dispositivo (siempre que el sistema MDM admita el Protocolo simple de inscripción de certificados (SCEP) o los estándares de criptografía de clave pública #12 (PKCS#12)). MDM también puede consultar y eliminar certificados de cliente inscritos o desencadenar una nueva solicitud de inscripción antes de que el certificado actual haya expirado.

Obtenga más información sobre cómo [preparar certificados y perfiles de red para HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### Proxy

La mayoría de las redes de intranet corporativas aprovechan un proxy para administrar el tráfico interno. Con HoloLens 2 puede configurar un servidor proxy para conexiones ethernet y Wi-Fi web. Esta configuración no se aplica a las conexiones VPN.

Para obtener más información sobre la configuración de proxy para Windows 10, consulta [NetworkProxy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

#### VPN

A menudo, las organizaciones usan una VPN para controlar el acceso a las aplicaciones y los recursos de su&#39;intranet. HoloLens 2 admite conexiones VPN SSL, que requieren un complemento descargable de Microsoft Store y son específicas del proveedor de VPN que elijas.

Para obtener más información acerca de los perfiles de VPN, consulta [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx) (CSP de VPNv2).

#### Pantalla completa

Puedes configurar un dispositivo HoloLens 2 para que funcione como un dispositivo de propósito fijo, también denominado quiosco, configurando el dispositivo para que se ejecute en modo de pantalla completa. El modo de pantalla completa limita las aplicaciones (o los usuarios) que están disponibles en el dispositivo. El modo de pantalla completa es una característica práctica que puedes usar para dedicar un dispositivo HoloLens 2 a aplicaciones empresariales, o para usar el dispositivo HoloLens 2 en una demostración de la aplicación.

Para obtener más información sobre cómo configurar HoloLens 2 en modo de pantalla completa, consulta [Configurar HoloLens como quiosco](https://docs.microsoft.com/hololens/hololens-kiosk)

## Implementar

### Inscripción de dispositivos MDM

Para las implementaciones empresariales, se recomienda inscribir dispositivos en MDM como dispositivos corporativos solo con unión a Azure AD e inscripción automática de MDM (Azure AD+MDM). [](https://docs.microsoft.com/hololens/hololens-enroll-mdm) Esto requiere Azure AD Premium y admite la inscripción automática en varios proveedores de MDM, incluido Intune.

Obtén más información sobre el método de inscripción [Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot)que se implementa automáticamente.

### Implementación de aplicaciones

A menudo, la productividad del usuario en los dispositivos móviles está condicionada por las aplicaciones.

Windows10 hace posible desarrollar aplicaciones que funcionen de manera óptima en varios dispositivos con la Plataforma universal de Windows (UWP) para aplicaciones de Windows.

Hay varias formas de implementar aplicaciones en dispositivos HoloLens 2. Las aplicaciones se pueden implementar directamente a través de MDM, la Microsoft Store para Empresas o se pueden realizar de forma local a través de un paquete de aprovisionamiento. Consulta la documentación [de implementación de](https://docs.microsoft.com/hololens/app-deploy-overview) aplicaciones para obtener más información.

> [!NOTE]
> HoloLens 2 solo admite la ejecución de aplicaciones ARM64 para UWP.

## Mantener

En los entornos de TI empresariales, la necesidad de administración y el control de costes se debe equilibrar con el deseo de ofrecer a los usuarios las tecnologías más recientes. Dado que los ciberataques se han convertido en una ocurrencia cotidiana, es importante mantener correctamente el estado de los dispositivos Windows 10. El departamento de TI debe controlar las opciones de configuración, impidiendo que incumplan los requisitos, así como hacer cumplir qué dispositivos pueden acceder a las aplicaciones internas. HoloLens 2 ofrece las capacidades de administración de operaciones móviles necesarias para garantizar que los dispositivos cumplen con la directiva corporativa.

### Opciones de mantenimiento del sistema operativo

**Un proceso de actualización optimizado**

Microsoft ha optimizado el ciclo de ingeniería y lanzamiento de productos Windows para que las nuevas características, experiencias y funcionalidades que demanda el mercado se puedan ofrecer de forma más rápida que nunca. Microsoft tiene planeado entregar 2 actualizaciones de características al año (en un período de 12 meses). **Las actualizaciones de** características establecen una rama actual o CB y tienen una versión asociada.

Microsoft también entregará e instalará actualizaciones de seguridad y estabilidad directamente en dispositivos HoloLens 2. Estas **actualizaciones de calidad,** publicadas bajo control de Microsoft a través de Windows Update, están disponibles mensualmente. HoloLens 2 consume actualizaciones de características y actualizaciones de calidad como parte del mismo proceso de actualización estándar.

Los clientes empresariales pueden administrar la experiencia de actualización y el proceso en HoloLens 2s con un sistema MDM. En la mayoría de los casos, se aplicarán directivas para administrar el proceso de actualización tanto en el caso de actualizaciones de características como de calidad. Más detalles sobre [cómo configurar MDM para las actualizaciones de HoloLens.](https://docs.microsoft.com/hololens/hololens-updates)

### Administración de aplicaciones

Los administradores de TI pueden controlar qué aplicaciones pueden instalarse en HoloLens 2 y cómo deben mantenerse actualizadas.

HoloLens 2 admite Windows Defender Control de aplicaciones [(WDAC),](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)que permite a los administradores crear, permitir o no permitir listas de aplicaciones de Microsoft Store. Esta funcionalidad también se extiende a las aplicaciones integradas. La capacidad de permitir o denegar aplicaciones ayuda a garantizar que los usuarios usen sus dispositivos para sus fines previstos. Sin embargo, no siempre resulta sencillo encontrar un equilibrio entre lo que los empleados necesitan o solicitan y los problemas de seguridad. La creación de listas de aplicaciones permitidas y no permitidas también requiere mantenerse al día del cambiante mundo de las aplicaciones de Microsoft Store.

Para obtener más información, consulta [CSP de control de aplicaciones.](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)

### Retirar

La retirada de dispositivos es la última fase del ciclo de vida del dispositivo. Es&#39;&#39;que los dispositivos que se reemplazan por modelos más recientes se retiren de forma segura, ya que no quieres que los datos de la empresa permanezcan en dispositivos descartados que puedan poner en peligro la confidencialidad de los datos. El departamento de TI también necesita una forma de dar soporte de forma adecuada a los usuarios que necesiten borrar los dispositivos perdidos o robados.

HoloLens 2 admite 3 métodos para borrar el dispositivo

**Eliminación de fábrica de MDM:** Restablece HoloLens 2 a la imagen de fábrica a través del comando MDM iniciado por el administrador. Borra todos los datos almacenados en el dispositivo.

**Restablecimiento de dispositivo desde la configuración:** Los usuarios finales pueden restablecer manualmente HoloLens 2 en la aplicación Configuración del dispositivo. Borra todos los datos almacenados en el dispositivo.

**Advanced Recovery Companion (ARC):** Desde un equipo que ejecuta la herramienta ARC, un usuario o administrador puede flashear un HoloLens 2 conectado al equipo a través de un cable USB. Borra todos los datos almacenados en el dispositivo.

> [!div class="nextstepaction"]
> [Escenarios de implementación comunes](common-scenarios.md)
