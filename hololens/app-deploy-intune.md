---
title: Intune y portal de la empresa
description: Intune, administración de aplicaciones, aplicación, portal de la empresa, portal
keywords: Intune, administración de aplicaciones, aplicación, portal de la empresa, portal, hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 7871d5113b6803a3f702bf8d64f16fabc1c5a9bb
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252661"
---
# Portal de empresa e Intune

Con la administración de dispositivos móviles (MDM), puedes usar tus propias aplicaciones personalizadas a través de [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) para implementarlo directamente en tus dispositivos HoloLens. Microsoft Intune es un servicio basado en la nube que se centra en la administración de dispositivos móviles (MDM) y la administración de aplicaciones móviles (MAM). Intune está incluido en el [conjunto de programas de seguridad y movilidad empresarial](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)de Microsoft y permite que los usuarios sean productivos mientras mantienen protegidos los datos de su organización. Para obtener más información sobre Intune, lea [Qué es Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).

## Programa de instalación

1. Cargue una aplicación a una línea de negocio o cargue una aplicación personalizada a su inquilino de Intune. Vea también: [Administración de aplicaciones empresariales](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).

2. [Asignar la aplicación a un grupo](https://docs.microsoft.com/mem/intune/apps/apps-deploy). En función del tipo de asignación que elija, la aplicación se puede enviar de forma automática o disponible para extraerla inmediatamente si tiene una selección de aplicaciones.

> [!NOTE]
> Al crear tu paquete appx, asegúrate de incluir la arquitectura de los dispositivos en los que estás implementando. HoloLens 2 es ARM64, y HoloLens (1º gen) es x86. Si tienes pensados en un entorno de dispositivos mixtos, puedes incluir ambos en un solo paquete appx.

## Tipos de asignación

Para que la aplicación se instale automáticamente en el dispositivo después de la inscripción, debe seleccionar **obligatorio** para ese grupo (s).
Para que la aplicación esté disponible para su descarga en los dispositivos inscritos a través del portal de la empresa, seleccione **disponible para dispositivos inscritos**.

## Experiencia End-User

Una vez que haya configurado la configuración de Intune, estará listo para que los usuarios finales reciban las aplicaciones seleccionadas.

Siga estos pasos para obtener automáticamente las aplicaciones:

1. Inscriba el dispositivo en el inquilino.
2. Una vez que el dispositivo haya finalizado la inscripción, deberás recibir la aplicación en el dispositivo.
3. Si no ve la aplicación inmediatamente, vaya a **configuración**  >  **cuentas**  >  **trabajo o escuela**  >  *la información de su cuenta* y desplácese hacia abajo para ver información sobre el estado de la aplicación instalada.

Cómo acceder a las aplicaciones a través del portal de la empresa:

1. Abra el **menú Inicio** y seleccione **Microsoft Store**.
2. Busca el **portal** de la empresa y descarga la aplicación.
3. Inicia sesión en tu cuenta.
4. Seleccione la aplicación que desea recibir y descargarla.

> [!Tip]
> Obtenga más información acerca de [la instalación automática del portal de la empresa](https://docs.microsoft.com/mem/intune/apps/company-portal-app) y [de la implementación y administración de aplicaciones en Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).
