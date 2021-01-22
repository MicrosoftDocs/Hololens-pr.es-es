---
title: Intune y portal de empresa
description: Obtenga información sobre cómo configurar, asignar y crear una experiencia de usuario cómoda con Intune, la administración de dispositivos móviles y el portal de la empresa.
keywords: intune, administración de aplicaciones, aplicación, portal de empresa, portal, hololens
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
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283721"
---
# Portal de empresa e Intune

Con administración de dispositivos móviles (MDM), puedes usar tus propias aplicaciones personalizadas a través de [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) para implementarla directamente en los dispositivos HoloLens. Microsoft Intune es un servicio basado en la nube que se centra en la administración de dispositivos móviles (MDM) y la administración de aplicaciones móviles (MAM). Intune se incluye en el conjunto de aplicaciones [Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)de Microsoft y permite a los usuarios ser productivos mientras mantienen protegidos los datos de su organización. Para obtener más información sobre Intune, lea [¿Qué es Intune?](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

## Programa de instalación

1. Cargue una aplicación en una línea de negocio o cargue una aplicación personalizada en su inquilino de Intune. Consulta también: Administración [de aplicaciones empresariales.](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)

2. [Asignar la aplicación a un grupo.](https://docs.microsoft.com/mem/intune/apps/apps-deploy) En función del tipo de asignación que elijas, la aplicación se puede entregar automáticamente o disponible para que se pueda retirar fácilmente si tienes una selección de aplicaciones.

> [!NOTE]
> Al compilar el paquete appx, asegúrate de incluir la arquitectura de los dispositivos en los que estás implementando. HoloLens 2 es ARM64 y HoloLens (1.ª generación) es x86. Puedes incluir ambos en un único paquete appx si tienes previsto tener un entorno de dispositivos mixtos.

## Tipos de asignación

Para que la aplicación se instale automáticamente en el dispositivo después de la inscripción, debes seleccionar **Necesario** para ese grupo o grupos.
Para que la aplicación esté disponible para su descarga en dispositivos inscritos a través del portal de la empresa, selecciona **Disponible para dispositivos inscritos.**

## End-User experiencia

Después de configurar la configuración en Intune, estará listo para que los usuarios finales reciban las aplicaciones seleccionadas.

Sigue estos pasos para obtener automáticamente las aplicaciones:

1. Inscriba el dispositivo en el espacio empresarial.
2. Una vez que el dispositivo haya completado la inscripción, debes recibir la aplicación en el dispositivo.
3. Si no ves la aplicación **** inmediatamente, ve a Cuentas de configuración Trabajo o Escuela información de tu cuenta y desplázate hacia abajo para ver información sobre  >  ****  >  ****  >  ** el estado de la aplicación instalada.

Cómo obtener acceso a las aplicaciones a través del Portal de empresa:

1. Abre el **menú Inicio** y selecciona **Microsoft Store.**
2. Busque el **Portal de empresa** y descargue la aplicación.
3. Inicia sesión en tu cuenta.
4. Selecciona la aplicación que quieras recibir y descargarla.

> [!Tip]
> Obtenga más información [sobre la instalación automática del Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) de empresa y la implementación y administración de aplicaciones en [Intune.](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)
