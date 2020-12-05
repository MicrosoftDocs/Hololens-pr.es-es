---
title: 'Guía de implementación: implementación de la nube conectada a HoloLens 2 a escala con asistencia remota-configurar'
description: Cómo configurar las configuraciones para inscribir dispositivos HoloLens en una red conectada en la nube
keywords: HoloLens, administración, nube conectada, asistencia remota, AAD, Azure AD, MDM, administración de dispositivos móviles
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
ms.openlocfilehash: 43b9db96a2c29d1e3a798d0c695ab6edaa8199ac
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196379"
---
# Configurar-guía conectada a la nube

En esta sección de la guía,&#39;emos cómo configurar la inscripción automática para su espacio empresarial y cómo aplicar licencias tanto para Intune como para asistencia remota.

## Usuarios y grupos de Azure

Azure e Intune con esa extensión, usa usuarios y grupos para ayudar a asignar configuraciones y licencias. Para validar este flujo de implementación y poder hacer una llamada de asistencia remota desde un usuario a otro&#39;necesita 2 cuentas de usuario.

Podemos crear un solo grupo de usuarios con el propósito de asignar licencias. Podemos unir ambos usuarios al mismo grupo y aplicar una licencia de Intune y asistencia remota a ese grupo.

Si no&#39;ya tiene acceso a dos cuentas de AAD en un grupo de usuarios que puede usar; Estas son las guías de inicio rápido para:

- [Cómo crear un usuario](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Cómo crear un grupo](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Agregar usuarios a un grupo](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) : agregar usuarios creados a crear grupo
- [Configurar AAD para permitir que un grupo de usuarios se una](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) a los dispositivos: Asegúrese de que el nuevo grupo de usuarios tiene permiso para inscribir dispositivos en AAD

## Inscripción automática en HoloLens 2

Para tener una experiencia fluida y fluida, la configuración de Azure Active Directory join (AADJ) y la inscripción automática en Intune para HoloLens 2 es la manera de ir. Esto permitirá a los usuarios simplemente introducir las credenciales de inicio de sesión de su organización durante OOBE y se registrarán automáticamente con AAD e inscribirán el dispositivo en MDM.

Al usar [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home) , podemos seleccionar servicios y navegar por unas pocas páginas hasta que podamos seleccionar obtener una prueba Premium. Muchas notificaciones: Azure Active Directory Premium 1 y 2, para la inscripción automática P1 es suficiente. Podemos seleccionar Intune y seleccionar el ámbito de usuario para la inscripción automática y seleccionar el grupo que se creó anteriormente.

Para obtener más detalles y pasos, lea la guía sobre [Cómo habilitar la inscripción automática para Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).

## Licencias de aplicación

Una licencia de aplicación permite a un usuario instalar aplicaciones compradas por la empresa o actualizar de una prueba gratuita a la versión completa de una aplicación. Las licencias de aplicación se pueden aplicar a usuarios, grupos de usuarios o grupos de dispositivos. &#39;s necesita que las licencias de asistencia remota para los usuarios de su organización utilicen asistencia remota. Para el propósito de esta guía, asignaremos licencias de asistencia remota al grupo de usuarios que hemos creado anteriormente en [usuarios y grupos de Azure](hololens2-cloud-connected-configure.md#azure-users-and-groups).

Los requisitos para las licencias pueden variar según si el usuario realizará la llamada de asistencia remota desde un dispositivo o será un colaborador remoto de Microsoft Teams. De forma predeterminada, están marcadas las casillas asistencia remota y equipos. Para los fines de esta guía, sugerimos que dejen las casillas predeterminadas seleccionadas.

1. Obtenga más información sobre los diferentes [requisitos de licencias y productos por rol](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role). Existen varios tipos diferentes de licencias de asistencia remota, así que asegúrese de tomar las correctas para satisfacer sus necesidades.
2. &#39;necesario [adquirir la licencia](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist).
3. [Aplicar las licencias](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) al grupo.

## Paso siguiente

> [!div class="nextstepaction"]
> [Implementación de nube conectada-implementar](hololens2-cloud-connected-deploy.md)