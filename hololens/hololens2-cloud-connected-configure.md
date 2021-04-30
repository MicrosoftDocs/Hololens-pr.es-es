---
title: 'Guía de implementación: implementación de HoloLens 2 conexión a la nube a escala con Remote Assist- Configurar'
description: Aprenda a configurar configuraciones para inscribir dispositivos HoloLens a través de una red conectada a la nube a escala con Remote Assist.
keywords: HoloLens, administración, conexión a la nube, Remote Assist, AAD, Azure AD, MDM, Mobile Administración de dispositivos
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 00cc3f9df1fefafc9c4c084ff642364ae3ccb85c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310128"
---
# <a name="configure---cloud-connected-guide"></a>Configuración: Guía conectada a la nube

En esta sección de la guía, veremos&#39;cómo configurar la inscripción automática para el inquilino y cómo aplicar licencias para Intune y Remote Assist.

## <a name="azure-users-and-groups"></a>Usuarios y grupos de Azure

Azure e Intune mediante esa extensión usan usuarios y grupos para ayudar a asignar configuraciones y licencias. Para validar este flujo de implementación y poder realizar una llamada Remote Assist de un usuario a otro,&#39;necesitará dos cuentas de usuario.

Podemos crear un único grupo de usuarios con el fin de asignar licencias. Podemos unir ambos usuarios al mismo grupo y aplicar una licencia para Intune Remote Assist a ese grupo.

Si aún no&#39;acceso a dos cuentas de Azure AD de un grupo de usuarios que puede usar; Estas son las guías de inicio rápido para:

- [Creación de un usuario](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Creación de un grupo](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Agregar usuarios a un grupo:](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) agregar usuarios creados para crear un grupo
- [Configurar Azure AD para permitir que un grupo de usuarios](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) se una a dispositivos: asegúrese de que el nuevo grupo de usuarios tenga permiso para inscribir dispositivos para Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Inscripción automática en HoloLens 2

Para tener una experiencia fluida y sin problemas, la configuración de Azure Active Directory Join (AADJ) y la inscripción automática en Intune para dispositivos HoloLens 2 es la mejor opción. Esto permitirá a los usuarios introducir sus credenciales de inicio de sesión de la organización durante la OOBE y registrarse automáticamente con Azure AD e inscribir el dispositivo en MDM.

Con [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), podemos seleccionar servicios y navegar por algunas páginas hasta que podamos seleccionar Obtener una evaluación Premium. Es posible que observe que hay Azure Active Directory Premium 1 y 2, para la inscripción automática P1 es suficiente. Podemos seleccionar Intune, seleccionar el ámbito de usuario para la inscripción automática y seleccionar el grupo que se creó anteriormente.

Para obtener detalles completos y pasos, lea la guía [sobre cómo habilitar la inscripción automática para Intune.](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="application-licenses"></a>Licencias de aplicación

Una licencia de aplicación permite a un usuario instalar aplicaciones adquiridas por la empresa o actualizar desde una evaluación gratuita a la versión completa de una aplicación. Las licencias de aplicación se pueden aplicar a usuarios, grupos de usuarios o grupos de dispositivos. Necesitará&#39;licencias de Remote Assist para que los usuarios de su organización usen Remote Assist. Para el propósito de esta guía, asignaremos licencias de Remote Assist al grupo de usuarios que creamos anteriormente en [Usuarios y grupos de Azure.](hololens2-cloud-connected-configure.md#azure-users-and-groups)

Los requisitos de las licencias pueden ser diferentes en función de si el usuario realizará la llamada Remote Assist desde un dispositivo o será un colaborador remoto de Microsoft Teams. De forma predeterminada, las casillas Remote Assist y Teams están marcadas. Para los fines de esta guía, se recomienda dejar activadas las casillas predeterminadas.

1. Obtenga más información sobre los [distintos requisitos de licencias y productos por rol.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role) Hay varios tipos diferentes de Remote Assist licencias, así que asegúrese de obtener las correctas para sus necesidades.
2. Debe&#39;adquirir la [licencia](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist).
3. [Aplique sus licencias al](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) grupo.

## <a name="next-step"></a>Paso siguiente

> [!div class="nextstepaction"]
> [Implementación conectada a la nube: implementación](hololens2-cloud-connected-deploy.md)