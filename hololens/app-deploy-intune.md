---
title: Intune y Portal de empresa
description: Aprenda a configurar, asignar y crear una experiencia de usuario cómoda con Intune, la administración de dispositivos móviles y el portal de empresa.
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
ms.openlocfilehash: f1c178c940224ed3cd07c58b886b176108614caf7a8463af089e2f2357f45553
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665257"
---
# <a name="intune--company-portal"></a>Intune y Portal de empresa

Con Mobile Administración de dispositivos (MDM), puede usar sus propias aplicaciones personalizadas a través de [Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) para implementarla directamente en los dispositivos HoloLens dispositivos. Microsoft Intune es un servicio basado en la nube que se centra en la administración de dispositivos móviles (MDM) y la administración de aplicaciones móviles (MAM). Intune se incluye en el conjunto de programas de [Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) de Microsoft y permite a los usuarios ser productivos manteniendo protegidos los datos de la organización. Para más información sobre Intune, lea [¿Qué es Intune?](/mem/intune/fundamentals/what-is-intune)

## <a name="setup"></a>Configurar

1. Upload una aplicación a una línea de negocio o cargue una aplicación personalizada en el inquilino de Intune. Consulte también: Administración [Enterprise aplicaciones.](/windows/client-management/mdm/enterprise-app-management)

2. [Asigne la aplicación a un grupo](/mem/intune/apps/apps-deploy). En función del tipo de asignación que elija, la aplicación se puede entregar automáticamente o disponible para que se pueda retirar fácilmente si tiene una selección de aplicaciones.

> [!NOTE]
> Al compilar el paquete appx, asegúrese de incluir la arquitectura de los dispositivos en los que va a realizar la implementación. HoloLens 2 arm64 y HoloLens (1ª generación) es x86. Puede incluir ambos en un único paquete appx si planea tener un entorno de dispositivos mixtos.

## <a name="assignment-types"></a>Tipos de asignación

Para que la aplicación se instale automáticamente en el dispositivo después de la inscripción, debe seleccionar **Requerido** para ese grupo.
Para que la aplicación esté disponible para su descarga en los dispositivos inscritos a través del portal de empresa, **seleccione Disponible para dispositivos inscritos.**

## <a name="end-user-experience"></a>Experiencia del usuario final

Después de configurar la configuración en Intune, está listo para que los usuarios finales reciban las aplicaciones seleccionadas.

Siga estos pasos para obtener automáticamente las aplicaciones:

1. Inscriba el dispositivo con el inquilino.
2. Una vez que el dispositivo haya completado la inscripción, debe recibir la aplicación en el dispositivo.
3. Si no ve la aplicación inmediatamente, vaya **a Configuración** Accounts Work or School your account Info (Cuentas de trabajo o escuela) y desplácese hacia abajo para ver información sobre el estado de  >    >    >   la aplicación instalada.

Cómo llegar a las aplicaciones a través de la Portal de empresa:

1. Abra el **menú Inicio** y seleccione **Microsoft Store**.
2. Busque **Portal de empresa** y descargue la aplicación.
3. Inicie sesión en su cuenta.
4. Seleccione la aplicación que desea recibir y descárárelo.

> [!Tip]
> Obtenga más información [sobre la instalación automática de Portal de empresa](/mem/intune/apps/company-portal-app) y la implementación y administración de aplicaciones en [Intune.](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)
