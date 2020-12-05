---
title: 'Guía de implementación: HoloLens conectado a la nube con ayuda remota: información general'
description: Inscribir dispositivos HoloLens en una red conectada en la nube
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
ms.openlocfilehash: ba3f826360f999a72e671166af7a19d19ce9c567
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196384"
---
# Guía de implementación: HoloLens conectado a la nube con asistencia remota (información general)

Esta guía ayuda a los profesionales de ti a planear e implementar dispositivos Microsoft HoloLens 2 a su organización con el objetivo general de tener esos dispositivos conectados en la nube a la organización con el asistente remoto de Dynamics 365 listo para usar. Tenga en cuenta que este es un modelo para las implementaciones de prueba de concepto para su organización en una variedad de casos de uso de HoloLens 2.

Durante la guía, explicaremos cómo inscribir sus dispositivos en la administración de dispositivos, aplicar licencias según sea necesario y comprobar que los usuarios finales pueden usar inmediatamente asistencia remota al configurar el dispositivo. Para hacerlo, repasaremos las importantes partes de infraestructura necesarias para configurar y ejecutar: Cómo lograr la implementación a escala con HoloLens 2.

## En esta guía

Esta guía tiene el objetivo específico de configurar asistencia remota en tu organización en tus dispositivos HoloLens. Cubriremos las Necessities necesarias para alcanzar ese objetivo. Para mantener el foco en este objetivo, se preseleccionarán determinados preparativos y configuraciones a fin de optimizar esta implementación o reducir los elementos necesarios para configurar. Se le informará de estas elecciones y podrá personalizar su implementación según las necesidades de su empresa.

Se trata de una configuración similar a la del [escenario a: implementar en dispositivos de conexión en la nube](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), que es una buena opción para una prueba de implementaciones de concepto que incluirá:

- Las redes Wi-Fi suelen estar totalmente abiertas con los servicios de Internet y de la nube
- Unirse a Azure AD con inscripción automática de MDM: MDM (Intune) administrado
- Los usuarios inician sesión con su propia cuenta corporativa (AAD)
  - Compatible con uno o varios usuarios por dispositivo
- Se aplican diversos niveles de configuración de bloqueo de dispositivo en función de casos de uso específicos, desde el quiosco de la aplicación totalmente abierta a la única.

![Escenario de conexión a la nube](./images/cloud-connected-deployment-chart.png)

En esta guía no se aplicarán restricciones ni configuraciones de dispositivo adicionales, pero le recomendamos que explore dichas opciones después de finalizar.

## Obtener más información sobre asistencia remota

El asistente remoto permite el mantenimiento y la reparación de colaboración, la inspección remota, así como la formación y el uso compartido de la información. Al conectar personas en diferentes roles y ubicaciones, un técnico que use el asistente remoto puede conectarse con un colaborador remoto en Microsoft Teams. Pueden combinar vídeo, capturas de pantalla y anotaciones para resolver problemas en tiempo real, incluso cuando no&#39;en la misma ubicación. Los colaboradores remotos pueden insertar imágenes de referencia, esquemas y otra información útil el técnico&#39;s espacio físico para que puedan consultar el esquema mientras se trabaja con los cabezales y las manos libres en HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## En esta guía, usted podrá:

Preparar

> [!div class="checklist"]
> - [Más información sobre los conceptos básicos de infraestructura para dispositivos HoloLens 2.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Obtenga más información sobre AAD y configure uno si no&#39;lo tiene.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Obtenga información sobre la administración de identidades y sobre cómo configurar mejor las cuentas de AAD.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Obtenga más información sobre MDM y configúrelo con Intune si no&#39;ya hay una lista.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Obtenga más información sobre los requisitos de red de asistencia remota.](hololens2-cloud-connected-prepare.md#network)
> - [Opcionalmente: VPN para conectarse a los recursos de la organización](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Volver

> [!div class="checklist"]
> - [Cómo crear usuarios y grupos.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Cómo configurar la inscripción automática en AAD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Cómo asignar las licencias de la aplicación.](hololens2-cloud-connected-configure.md#application-licenses)

Implement

> [!div class="checklist"]
> - [Configura tu HoloLens 2 y valida la inscripción.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Validar: puede hacer una llamada de asistencia remota.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Mantener

> [!div class="checklist"]
> - [Cómo actualizar asistencia remota mediante la aplicación Microsoft Store.](hololens2-cloud-connected-maintain.md#updates)
> - [Realizar un plan de soporte técnico.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Plan de desarrollo.](hololens2-cloud-connected-maintain.md#development-plan)

## Paso siguiente

> [!div class="nextstepaction"]
> [Implementación con conexión en la nube-preparación](hololens2-cloud-connected-prepare.md)

