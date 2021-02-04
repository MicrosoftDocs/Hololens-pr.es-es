---
title: Información general sobre HoloLens 2 conectado en la nube con asistencia remota
description: Aprende a inscribir dispositivos HoloLens 2 a través de una red conectada a la nube con Dynamics 365 Remote Assist.
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
ms.openlocfilehash: 69b31657a7efaebd5b25b742023dc8767f9c5038
ms.sourcegitcommit: 39424078a75feaf6a1e9b0547cb7d5de9847faf3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312644"
---
# Guía de implementación de HoloLens 2 conectado a la nube con Remote Assist: Información general

Esta guía ayuda a los profesionales de TI a planear e implementar dispositivos De Microsoft HoloLens 2 en su organización con el objetivo general de que esos dispositivos estén conectados a la nube a su organización con el Asistente remoto de Dynamics 365 listo para usar. Tenga en cuenta que esto servirá como un modelo para implementaciones de prueba de concepto en su organización en una variedad de casos de uso de HoloLens 2.

Durante la guía, se explica cómo inscribir los dispositivos en la administración de dispositivos, aplicar licencias según sea necesario y validar que los usuarios finales puedan usar de inmediato asistencia remota tras la configuración del dispositivo. Para ello, nos dirigiremos a las partes importantes de la infraestructura necesarias para estar configurados y en funcionamiento, logrando la implementación a escala con HoloLens 2.

![Banner conectado a la nube](./images/cloud-connected-hololens-large.png)

## En esta guía

Esta guía tiene el objetivo específico de configurar asistencia remota dentro de su organización en sus dispositivos HoloLens. Cubriremos las necesidades necesarias para lograr ese objetivo. Para mantener el foco en este objetivo, se seleccionarán previamente determinadas configuraciones y preparación para optimizar esta implementación o para reducir los elementos necesarios para configurar. Se le informará de estas opciones y podrá personalizar la implementación en función de sus necesidades empresariales.

Se trata de una configuración similar al escenario [A:](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)Implementar en dispositivos de conexión en la nube, que es una buena opción para muchas implementaciones de prueba de concepto, que incluirán:

- Wi-Fi las redes están completamente abiertas a internet y a los servicios en la nube
- Unión a Azure AD con inscripción automática de MDM: mdm (Intune) administrado
- Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)
  - Se admiten uno o varios usuarios por dispositivo
- Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican en función de casos de uso específicos, desde Totalmente abierto a Quiosco de aplicación única

![Escenario conectado a la nube](./images/cloud-connected-guide-diagram.png)

No se aplicarán otras restricciones o configuraciones de dispositivos en esta guía, pero te animamos a explorar esas opciones después de finalizar.

## Más información sobre asistencia remota

Remote Assist permite el mantenimiento y reparación de colaboración, la inspección remota, así como el uso compartido y la formación de conocimientos. Al conectar a personas en diferentes roles y ubicaciones, un técnico con asistencia remota puede conectarse con un colaborador remoto en Microsoft Teams. Pueden combinar vídeo, capturas de pantalla y anotaciones para resolver problemas en tiempo real incluso cuando no&#39;en la misma ubicación. Los colaboradores remotos pueden insertar imágenes de referencia, esquemas y otra información útil en el espacio físico del técnico&#39;para que puedan hacer referencia al esquema mientras trabajan de forma rápida y sin manos en HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## En esta guía, hará lo siguiente:

Preparar:

> [!div class="checklist"]
> - [Obtenga información sobre los aspectos básicos de la infraestructura para dispositivos HoloLens 2.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Obtenga más información sobre Azure AD y configure una si no&#39;la tiene.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Obtenga información sobre la administración de identidades y cómo configurar mejor las cuentas de Azure AD.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Obtén más información sobre MDM y configura intune si&#39;ya tienes uno listo.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Obtenga información sobre los requisitos de red de Asistencia remota.](hololens2-cloud-connected-prepare.md#network)
> - [Opcionalmente: VPN para conectarse a recursos de la organización](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Configure:

> [!div class="checklist"]
> - [Cómo crear usuarios y grupos.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Cómo configurar la inscripción automática en Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Cómo asignar las licencias de aplicación.](hololens2-cloud-connected-configure.md#application-licenses)

Implemente:

> [!div class="checklist"]
> - [Configura HoloLens 2 y valida la inscripción.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Valide que puede realizar una llamada de asistencia remota.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Mantener:

> [!div class="checklist"]
> - [Cómo actualizar el asistente remoto con la aplicación de Microsoft Store.](hololens2-cloud-connected-maintain.md#updates)
> - [Realizar un plan de soporte técnico.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Plan de desarrollo.](hololens2-cloud-connected-maintain.md#development-plan)

## Paso siguiente

> [!div class="nextstepaction"]
> [Implementación conectada a la nube: preparar](hololens2-cloud-connected-prepare.md)

