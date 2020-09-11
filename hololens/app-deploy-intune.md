---
title: Intune y portal de la empresa
description: Intune, administración de aplicaciones, aplicación, portal de la empresa, portal
keywords: Intune, administración de aplicaciones, aplicación, portal de la empresa, portal, hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
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
ms.openlocfilehash: 5fc369caa2e5e26c91c07f9270c3984177507dbd
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009468"
---
# Portal de empresa e Intune

Con la administración de dispositivos móviles (MDM), puedes usar tus propias aplicaciones personalizadas a través de [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) para implementarlo directamente en tus dispositivos HoloLens. Microsoft Intune es un servicio basado en la nube que se centra en la administración de dispositivos móviles (MDM) y la administración de aplicaciones móviles (MAM). Intune está incluido en el[conjunto de programas de seguridad y movilidad empresarial](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)de Microsoft y permite que los usuarios sean productivos mientras mantienen protegidos los datos de su organización. Para obtener más información sobre Intune, lea [lo que es Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).

## Programa de instalación

1. Cargue una aplicación a una línea de negocio o cargue una aplicación personalizada a su inquilino de Intune. Vea también: [Administración de aplicaciones empresariales](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).

2. [Asignar la aplicación a un grupo](https://docs.microsoft.com/mem/intune/apps/apps-deploy). Según el tipo de asignación que elija, puede hacer que la aplicación se entregue de forma automática o disponible para que se extraiga fácilmente si tiene una selección de aplicaciones. 

> [!NOTE] 
> Al crear tu paquete appx, asegúrate de incluir la arquitectura de los dispositivos en los que estás implementando. HoloLens 2 es ARM64, y HoloLens (1º gen) es x86. Si tienes pensados en un entorno de dispositivos mixtos, puedes incluir ambos en un solo paquete appx.

## Tipos de asignación

Si prefiere que su aplicación se instale automáticamente en el dispositivo después de la inscripción, debe seleccionar **obligatorio** para ese grupo (s).
Si prefiere que la aplicación esté disponible para su descarga a las que se han inscrito a través del portal de la empresa, seleccione **disponible para dispositivos inscritos**.


## Experiencia de usuario final

Una vez que haya configurado la configuración de Intune, estará listo para que los usuarios finales reciban las aplicaciones seleccionadas.

Siga estos pasos para obtener automáticamente las aplicaciones:
1. Inscriba el dispositivo en el inquilino. 
2. Una vez que el dispositivo haya finalizado la inscripción, deberás recibir la aplicación en el dispositivo. 
3. Si no ve la aplicación inmediatamente, vaya a **configuración**  >  **cuentas**  >  **de trabajo o en la escuela**  >  **youraccount** información y desplácese hacia abajo para ver información sobre el estado de la aplicación instalada.

Cómo acceder a las aplicaciones a través del portal de la empresa:
1. Abra el **menú Inicio** y seleccione **Microsoft Store**. 
2. Busca el **portal** de la empresa y descarga la aplicación.
3. Inicia sesión en tu cuenta.
4. Seleccione la aplicación que desea recibir y descargarla.

> [!Tip]
> Obtenga más información acerca de [la instalación automática del portal de la empresa](https://docs.microsoft.com/mem/intune/apps/company-portal-app) y [de la implementación y administración de aplicaciones en Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).
