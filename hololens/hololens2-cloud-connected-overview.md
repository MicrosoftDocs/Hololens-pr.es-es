---
title: Información general sobre las aplicaciones conectadas HoloLens 2 la nube con Remote Assist
description: Aprenda a inscribir dispositivos HoloLens 2 a través de una red conectada a la nube mediante Dynamics 365 Remote Assist.
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
ms.openlocfilehash: 69b31657a7efaebd5b25b742023dc8767f9c5038
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309109"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Guía de implementación: información general HoloLens 2 conexión a la nube con Remote Assist: información general

Esta guía ayuda a los profesionales de TI a planear e implementar Microsoft HoloLens 2 dispositivos en su organización con el objetivo general de que esos dispositivos estén conectados Microsoft HoloLens la nube a su organización con Dynamics 365 Remote Assist listo para su uso. Tenga en cuenta que esto servirá como modelo para las implementaciones de prueba de concepto en su organización en una variedad de HoloLens 2 casos de uso.

Durante la guía se explica cómo inscribir los dispositivos en la administración de dispositivos, aplicar licencias según sea necesario y validar que los usuarios finales pueden usar inmediatamente Remote Assist la configuración del dispositivo. Para ello, remos por los elementos importantes de infraestructura necesarios para configurarse y ejecutarse, lo que permite realizar la implementación a escala con HoloLens 2.

![Banner conectado a la nube](./images/cloud-connected-hololens-large.png)

## <a name="in-this-guide"></a>En esta guía

Esta guía tiene el objetivo específico de configurar Remote Assist dentro de la organización en los dispositivos HoloLens. Se cubrirán las necesidades necesarias para lograr ese objetivo. Para mantener el foco en este objetivo, se seleccionarán previamente ciertas configuraciones y preparación con el fin de optimizar esta implementación o reducir los elementos necesarios para configurar. Se le informará de estas opciones y podrá personalizar la implementación en función de sus necesidades empresariales.

Se trata de una configuración similar a Escenario [A:](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)Implementación en dispositivos de conexión a la nube, que es una buena opción para muchas implementaciones de prueba de concepto, que incluirá:

- Wi-Fi las redes están totalmente abiertas a Internet y a los servicios en la nube
- Azure AD unirse a la inscripción automática de MDM: MDM (Intune) administrado
- Los usuarios inician sesión con su propia cuenta corporativa (Azure AD)
  - Se admiten uno o varios usuarios por dispositivo.
- Los distintos niveles de configuraciones de bloqueo de dispositivos se aplican en función de casos de uso específicos, desde Totalmente abierto a Pantalla completa de aplicación única

![Escenario conectado a la nube](./images/cloud-connected-guide-diagram.png)

En esta guía no se aplicarán otras restricciones o configuraciones de dispositivos, pero le recomendamos que explore esas opciones después de finalizar.

## <a name="learn-about-remote-assist"></a>Más información sobre Remote Assist

Remote Assist permite el mantenimiento y la reparación colaborativos, la inspección remota, así como el uso compartido de conocimientos y el entrenamiento. Al conectar a personas en distintos roles y ubicaciones, un Remote Assist puede conectarse con un colaborador remoto en Microsoft Teams. Pueden combinar vídeo, capturas de pantalla y anotaciones para resolver problemas en tiempo real, incluso cuando&#39;están en la misma ubicación. Los colaboradores remotos pueden insertar imágenes de referencia, esquemas y otra información útil del espacio físico del técnico&#39;para que puedan hacer referencia al esquema mientras trabajan de forma rápida y sin manos en HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a>Esta guía le permitirá:

Preparación:

> [!div class="checklist"]
> - [Obtenga información sobre los aspectos básicos de la infraestructura HoloLens 2 dispositivos.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Obtenga más información Azure AD configurar una si&#39;no la tiene.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Obtenga información sobre la administración de identidades y cómo configurar mejor Azure AD cuentas.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Obtenga más información sobre MDM y configure con Intune si&#39;ya tiene uno listo.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Obtenga información sobre los requisitos de red de Remote Assist.](hololens2-cloud-connected-prepare.md#network)
> - [Opcionalmente: VPN para conectarse a recursos organizativos](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Configurar lo siguiente:

> [!div class="checklist"]
> - [Cómo crear usuarios y grupos.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Configuración de la inscripción automática en Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Asignación de licencias de aplicación.](hololens2-cloud-connected-configure.md#application-licenses)

Implementación:

> [!div class="checklist"]
> - [Configure la suscripción HoloLens 2 validar la inscripción.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Compruebe que puede realizar una Remote Assist llamada.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Mantener:

> [!div class="checklist"]
> - [Actualización de Remote Assist mediante la Microsoft Store aplicación.](hololens2-cloud-connected-maintain.md#updates)
> - [Realización de un plan de soporte técnico.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Plan de desarrollo.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Paso siguiente

> [!div class="nextstepaction"]
> [Implementación conectada a la nube: preparación](hololens2-cloud-connected-prepare.md)

