---
title: 'Guía de implementación: implementación de HoloLens 2 conectada en la nube a escala con asistencia remota: configurar'
description: Aprende a configurar configuraciones para inscribir dispositivos HoloLens a través de una red conectada a la nube a escala con asistencia remota.
keywords: HoloLens, administración, conectado a la nube, Asistencia remota, AAD, Azure AD, MDM, Administración de dispositivos móviles
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283891"
---
# Configurar: Guía conectada a la nube

En esta sección de la guía,&#39;explicamos cómo configurar la inscripción automática para su espacio empresarial y cómo aplicar licencias para Intune y asistencia remota.

## Usuarios y grupos de Azure

Azure e Intune mediante esa extensión usan usuarios y grupos para ayudar a asignar configuraciones y licencias. Para validar este flujo de implementación y poder realizar una llamada de asistencia remota de un usuario a otro,&#39;necesitará dos cuentas de usuario.

Podemos crear un único grupo de usuarios con el fin de asignar licencias. Podemos unir a ambos usuarios al mismo grupo y aplicar una licencia para Intune y Asistencia remota a ese grupo.

Si aún no&#39;acceso a dos cuentas de Azure AD en un grupo de usuarios, puede usarlo; estas son las guías de inicio rápido para:

- [Cómo crear un usuario](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Cómo crear un grupo](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Agregar usuarios a un grupo:](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) agregar usuarios creados para crear grupos
- [Configurar Azure AD para permitir que un grupo de usuarios se una a](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) dispositivos: asegúrate de que el nuevo grupo de usuarios tenga permiso para inscribir dispositivos en Azure AD.

## Inscripción automática en HoloLens 2

Para que la experiencia sea fluida y sin problemas, la configuración de Azure Active Directory Join (AADJ) y la inscripción automática en Intune para dispositivos HoloLens 2 es el camino a seguir. Esto permitirá a los usuarios introducir sus credenciales de inicio de sesión de la organización durante la OOBE y registrarse automáticamente con Azure AD e inscribir el dispositivo en MDM.

Con [Microsoft Endpoint Manager,](https://endpoint.microsoft.com/#home)podemos seleccionar servicios y navegar por algunas páginas hasta que podamos seleccionar Obtener una versión de prueba premium. You may notice there is Azure Active Directory Premium 1 and 2, for Automatic Enrollment P1 is sufficient. Podemos seleccionar Intune, seleccionar el ámbito de usuario para la inscripción automática y seleccionar el grupo que se creó anteriormente.

Para obtener detalles completos y pasos, lee la guía [sobre cómo habilitar la inscripción automática para Intune.](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## Licencias de aplicación

Una licencia de aplicación permite a un usuario instalar aplicaciones adquiridas por la empresa o actualizar de una versión de prueba gratuita a la versión completa de una aplicación. Las licencias de aplicación se pueden aplicar a usuarios, grupos de usuarios o grupos de dispositivos. Necesitará&#39;licencias de asistencia remota para que los usuarios de su organización usen asistencia remota. Para el propósito de esta guía, asignaremos licencias de asistencia remota al grupo de usuarios que creamos anteriormente en [Usuarios y grupos de Azure.](hololens2-cloud-connected-configure.md#azure-users-and-groups)

Los requisitos para las licencias pueden ser diferentes en función de si el usuario realizará la llamada de asistencia remota desde un dispositivo o será un colaborador remoto de Microsoft Teams. De forma predeterminada, las casillas asistencia remota y Teams están marcadas. Para los fines de esta guía, se recomienda dejar activadas las casillas predeterminadas.

1. Obtenga más información sobre los distintos [requisitos de licencias y productos por rol.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role) Existen varios tipos diferentes de licencias de asistencia remota, así que asegúrese de obtener las correctas para sus necesidades.
2. Deberá&#39;adquirir la [licencia.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
3. [Aplicar las licencias al](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) grupo.

## Paso siguiente

> [!div class="nextstepaction"]
> [Implementación conectada a la nube: implementación](hololens2-cloud-connected-deploy.md)