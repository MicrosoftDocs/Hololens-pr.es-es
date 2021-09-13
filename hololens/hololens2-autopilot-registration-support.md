---
title: Envío de registro en Windows Autopilot a Soporte técnico para HoloLens 2
description: Aprenda a obtener soporte técnico para el registro de dispositivos HoloLens 2 en Autopilot.
author: joyjaz
ms.author: v-jjaswinski
ms.date: 5/20/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: ylempidakis
ms.openlocfilehash: cdd2ab68905d5cc82b1c5ccc50640112e857f2f4
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034634"
---
# <a name="hololens-2-registration-support-for-autopilot"></a>Soporte técnico para el registro de HoloLens 2 en Autopilot

Ahora los clientes y proveedores de soluciones en la nube (CSP) de Microsoft pueden registrar dispositivos HoloLens 2 mediante el envío directo de solicitudes a Soporte técnico de Microsoft. En esta página se describen los requisitos para los siguientes escenarios de registro de Autopilot admitidos:

- **Registro en Autopilot de dispositivo HoloLens 2**. Envía una solicitud para registrar dispositivos HoloLens 2 en Windows Autopilot.
- **Solicitud hash de hardware de dispositivo HoloLens 2**. Envía una solicitud a Soporte técnico de Microsoft para proporcionar los hashes de hardware que los clientes o los CSP pueden usar para registrar dispositivos de forma independiente por medio de Microsoft Intune o el Centro de partners de Microsoft.
- **Anulación de registro en Autopilot de dispositivo HoloLens 2**. Envía una solicitud para eliminar dispositivos de Windows Autopilot; normalmente se usa en escenarios de fin de ciclo de vida del dispositivo.

En la tabla siguiente se detalla la información que necesitará reunir *antes* de enviar solicitudes de registro a Soporte técnico de Microsoft.

| Información necesaria | Descripción | Registro en Autopilot  | Solicitud de hash de hardware | Anulación de registro en Autopilot |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  Identificador de inquilino de Azure Active Directory    |    El identificador de inquilino de Azure Active Directory es un identificador único global (GUID) diferente del nombre o dominio de la organización.    Para buscar el identificador de inquilino, inicie sesión en [Azure Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).    |     ✔️                         |                              |                         ✔️                        |
|  Nombre de dominio de Azure Active Directory    |   El nombre de dominio de nivel superior; por ejemplo, contoso.com.    |     ✔️                         |                              |                         ✔️                        |
|  Prueba de propiedad    |   Verifique la prueba de propiedad mediante la carga de la factura original de venta o factura comercial en formato PDF. No se aceptan capturas de pantalla. Este documento debe incluir la siguiente información: números de serie del dispositivo. Nombre de la compañía.     |     ✔️                         |              ✔️                |                         ✔️                        |
|  Números de serie del dispositivo    |   Cargue un archivo Excel en formato CSV con el número de serie de cada dispositivo en una nueva línea.     |     ✔️                         |              ✔️                |                         ✔️                        |

## <a name="submit-support-requests"></a>Envío de solicitudes de soporte técnico

> [!div class="nextstepaction"]
> [Enviar registro en Autopilot a Soporte técnico para HoloLens 2](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
