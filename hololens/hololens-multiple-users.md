---
title: Uso compartido de HoloLens con varias personas
description: Puede configurar las HoloLens que compartan varias Azure Active Directory o por varios usuarios que usen una sola cuenta.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/23/2021
ms.reviewer: anisgup
manager: sean-kerawala
appliesto:
- HoloLens 2
ms.openlocfilehash: bbb955edaa500187ea921538291bb1c7bda05422
ms.sourcegitcommit: be1393d24a98381e37bd1f56183c1f381f87cbd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "129600736"
---
# <a name="share-your-hololens-with-multiple-people"></a>Uso compartido de HoloLens con varias personas

## <a name="overview"></a>Información general

A menudo, las empresas invierten en muchos dispositivos HoloLens compartidos. La forma de HoloLens es flexible en función de sus requisitos individuales. Este es un ejemplo de algunas experiencias de varios usuarios:

- Una flota de HoloLens 2 dispositivos se configura a través de Windows Autopilot para HoloLens 2, con una cartera coherente de aplicaciones de empresa en cada dispositivo. Ha configurado varios perfiles de quiosco, dirigidos a distintos grupos Azure AD pantalla completa. Cada usuario inicia sesión en HoloLens mediante claves FIDO2 e inicia sesión en su propia cuenta de Azure AD y se le presenta una experiencia personalizada.
- Un proveedor de software independiente (ISV) alquila HoloLens 2 Devices con D365 Remote Assist y su aplicación de línea de negocio (LOB) a la empresa de un cliente. Estos dispositivos están configurados para quioscos que incluyen solo su aplicación de LOB y Remote Assist, y se comparten entre varios usuarios finales. WDAC se usa para evitar que la aplicación Configuración y Microsoft Edge inicien. Se incluye con el alquiler una batería USB-C para mantener los dispositivos a carga completa en varios turnos.
- Un usuario final de una empresa intenta realizar ajustes en Bluetooth en el dispositivo para que pueda conectar un nuevo dispositivo, pero la directiva De visibilidad de página Configuración está habilitada para limitar la visualización de la página Dispositivos. Todavía se les permite el acceso a otras páginas según sea necesario, como Wi-Fi para que puedan usar Remote Assist en varias ubicaciones con ese mismo HoloLens.

## <a name="best-practices"></a>Procedimientos recomendados

Al planear compartir los dispositivos, hay varias consideraciones para optimizar el entorno del dispositivo en función de sus necesidades empresariales.

- [Identidad y autenticación](#identity-and-authentication)
- [Administración de dispositivos](#device-management)
- [Administración avanzada de dispositivos: pantalla completa y WDAC](#advanced-device-management---kiosk-and-wdac)
- [Administración física](#physical-management)

### <a name="identity-and-authentication"></a>[Identidad y autenticación](hololens-identity.md)

Si planea tener varias cuentas en un dispositivo, tendrá cuentas de Azure AD con todos los modos de autenticación. Estos métodos de autenticación se basarán [en Windows Hello](/windows-hardware/design/device-experiences/windows-hello), incluidas las claves Iris y FIDO2.

- Las claves de seguridad de FIDO 2 son excelentes si tiene varios dispositivos, muchos usuarios o usa constantemente nuevos dispositivos.
- Si tiene 10 o menos usuarios, Iris es una solución rápida para iniciar sesión a los usuarios que han iniciado sesión previamente en el mismo dispositivo.

### <a name="device-management"></a>[Administración de dispositivos](hololens-csp-policy-overview.md)

Si los dispositivos se comparten entre los usuarios, es probable que quiera usar restricciones de dispositivos. Mediante el uso de la administración de dispositivos, puede establecer algunas directivas para permitir mejor que los usuarios usen el dispositivo, administren actualizaciones o limiten lo que el dispositivo puede hacer. Se recomienda revisar las restricciones comunes [de los dispositivos](hololens-common-device-restrictions.md)y ver si estas recomendaciones parecen ajustarse a su organización. Una vez que sepa qué directivas desea usar, puede aplicarlas a través de los paquetes de aprovisionamiento [Endpoint Manager (MDM)](hololens-mdm-configure.md) de Microsoft.

### <a name="advanced-device-management---kiosk-and-wdac"></a>Administración avanzada de [dispositivos: pantalla completa](hololens-kiosk.md) y [WDAC](windows-defender-application-control-wdac.md)

En algunos casos, es posible que quiera limitar a qué aplicaciones pueden acceder los usuarios finales. Podría limitar las aplicaciones que presentan los usuarios en el menú inicio mediante el [modo de pantalla completa.](hololens-kiosk.md) La pantalla completa se puede configurar para presentar diferentes menús de inicio basados en usuarios, grupos de Azure o tipos de usuario especiales. como visitante o excepto los propietarios de dispositivos. Puede elegir varias aplicaciones o solo una sola aplicación. Un quiosco con varias aplicaciones no detiene que una aplicación inicie otra, por lo que si la tienda u otra aplicación está disponible, los usuarios todavía pueden iniciar otra aplicación.

También puede detener completamente el inicio de aplicaciones o servicios mediante [Windows Defender Application Control (WDAC) para](windows-defender-application-control-wdac.md) restringir las aplicaciones. WDAC es diferente al quiosco, ya que no cambia la interfaz de usuario de HoloLens sino que no permite que se inicie una aplicación bloqueada.

[La visibilidad Configuración página](settings-uri-list.md) es otra manera de agregar restricciones a un dispositivo. En caso de que necesite conceder a los usuarios acceso a algunas páginas de la aplicación Configuración, pero no todos pueden usar Page Configuración Visibility para limitar el acceso. Esto resulta útil, por ejemplo, si los usuarios necesitan cambiar la red Wi-Fi, pero no quiere que accedan a la página Cuentas.

### <a name="physical-management"></a>Administración física

Al compartir el dispositivo entre varios usuarios, hay algunas consideraciones físicas.

- Asegúrese de que los dispositivos se cargan entre turnos.
- Si un dispositivo es necesario para un turno y necesita durar varios turnos, considere la posibilidad de usar una batería externa al principio de un turno, mientras que el dispositivo todavía tiene una carga significativa según las direcciones de administración del [calor.](hololens2-charging.md#managing-heat)
- Al almacenar dispositivos, mantenga conectados y conectados a una red. Esta es la mejor manera de garantizar las actualizaciones del sistema operativo y la aplicación.
- Tenga en cuenta cómo planea [limpiar el dispositivo entre](hololens2-maintenance.md) los usuarios.
- En el caso de un dispositivo con un único usuario compartido si usa un PIN o contraseña compartidos para un solo usuario, no coloque el PIN o la contraseña en el lado del dispositivo.
- Para varios dispositivos con un solo usuario compartido, use varios PIN o contraseñas.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Compartir con varias personas, cada una con su propia cuenta

Las Azure Active Directory individuales (Azure AD) son el caso de uso de identidad preferido y más seguro para HoloLens 2 usuarios. Al usar sus propias Azure AD, varios usuarios pueden mantener su propia configuración de usuario y sus propios datos de usuario en el dispositivo. Solo un usuario puede haber iniciado sesión a la vez. Cuando un usuario inicia sesión, HoloLens cierra la sesión del usuario anterior.

Para asegurarse de que varias personas pueden usar sus propias cuentas en HoloLens, siga estos pasos para configurarlo:

1. Al configurar [el dispositivo, seleccione](hololens2-start.md) **Mi** trabajo o escuela es propietario de él e inicie sesión con una cuenta Azure AD usuario.
1. Una vez que termine la instalación, asegúrese de que la configuración de la cuenta (Configuración > cuentas) **incluya Otros usuarios.**

> [!NOTE]
> Si el dispositivo no se ha configurado con una cuenta Azure AD, debe restablecerse o [volver](hololens-recovery.md) a actualizarse y configurarse correctamente.

Para usar HoloLens, cada usuario sigue estos pasos:

1. Si otro usuario ha estado usando el dispositivo, elija una de las siguientes opciones:
   - Presione el botón de encendido una vez para pasar al modo de espera y, a continuación, vuelva a presionar el botón de encendido para volver a la pantalla de bloqueo.
   - Seleccione el icono de usuario de **la menú Inicio** o elija Cerrar sesión en el **menú Energía** para cerrar la sesión del usuario actual.

1. Use las credenciales Azure AD cuenta de usuario para iniciar sesión en el dispositivo.  
    - Si es la primera vez que usa el dispositivo, [](hololens-calibration.md) le pedirá que calibrará el HoloLens a sus propios ojos.
    - Si anteriormente usó el dispositivo:
        - [Windows Holographic, versión 20H2, compilación 19041.1128](hololens-release-notes.md#windows-holographic-version-20h2) o posterior, la pantalla se ajusta perfectamente para mejorar la calidad y una experiencia de visualización cómoda.
        - Las compilaciones anteriores necesitarán calibración manual para ajustarse a los ojos.

> [!TIP]
> Si un usuario aún no ha iniciado sesión en un dispositivo, pruebe uno de estos dos métodos para un inicio de sesión más rápido:
>
> - **Clave de seguridad FIDO 2:** la clave de seguridad FIDO2 se reconocerá automáticamente y el usuario no tendrá que escribir sus credenciales de usuario ni usar MFA. Este es el método más rápido para iniciar sesión en un dispositivo nuevo.
> - **Autenticación web:** al iniciar sesión en un  nuevo dispositivo, puede seleccionar el vínculo Iniciar sesión desde otro dispositivo que generará un código de 9 caracteres que puede usar en [aka.ms/devicelogin](https://login.microsoftonline.com/common/oauth2/deviceauth) para iniciar sesión como usuario en el dispositivo o escribir su nombre de usuario y contraseña con un teclado para su comodidad.

Para ver una lista de los usuarios del dispositivo o quitar un usuario del dispositivo, vaya a Configuración  >  **Cuentas de** otros  >  **usuarios.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Compartir con varias personas, todas con la misma cuenta

Varios usuarios también pueden compartir un dispositivo HoloLens mientras se usa una única cuenta de usuario. Aunque es preferible que HoloLens usuarios inicien sesión en el dispositivo con sus identidades individuales (Azure AD cuentas), esta no es una opción en algunas organizaciones.

Hay dos métodos de dispositivo compartido disponibles:

- **Varios usuarios finales que comparten un** dispositivo: HoloLens dispositivo se asigna a un espacio designado donde cualquier empleado puede usar el dispositivo. Algunos ejemplos serían una sala limpia o un conjunto de procedimientos.

- **Varios usuarios finales que comparten** varios dispositivos: HoloLens dispositivos están en un espacio de almacenamiento compartido donde los empleados pueden usar cualquier dispositivo. Algunos ejemplos serían un distribuidor de petróleo o un distribuidor automático o un aparcamiento.

Cuando un nuevo usuario coloca el dispositivo por primera vez mientras mantiene la misma cuenta de inicio de sesión, el dispositivo le pide que calibra y personalice rápidamente la experiencia de visualización. El dispositivo almacenará la información de calibración para optimizar automáticamente la calidad y la comodidad de la experiencia de visualización de cada usuario. Los usuarios no necesitarán calibrar el dispositivo de nuevo.
