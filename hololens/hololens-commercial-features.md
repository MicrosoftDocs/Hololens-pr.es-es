---
title: Características comerciales
description: Infórmese de las características de Microsoft HoloLens Commercial Suite que facilitan a las empresas la administración de dispositivos HoloLens.
author: scooley
ms.author: scooley
ms.date: 08/26/2019
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
audience: ITPro
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: HoloLens, comercial, características, MDM, administración de dispositivos móviles, pantalla completa
ms.openlocfilehash: 3682a2633477d68f61dba8a674846857947a3d15
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397866"
---
# <a name="commercial-features"></a>Características comerciales

HoloLens incluye características que facilitan a las empresas la administración de dispositivos HoloLens.

Cada dispositivo HoloLens 2 tiene características comerciales disponibles.

HoloLens (1.ª generación) se incluía con dos opciones de licencia, la licencia de desarrollador y una licencia comercial. Para potenciar las capacidades comerciales de HoloLens, puede actualizar la licencia de desarrollador a una licencia comercial. Para comprar Microsoft HoloLens Commercial Suite, póngase en contacto con el gestor de cuentas local de Microsoft.

>[!VIDEO https://www.youtube.com/embed/tNd0e2CiAkE]

## <a name="key-commercial-features"></a>Características comerciales clave

- **Pantalla completa**. Puede usar HoloLens en experiencias de demostración o presentación con la pantalla completa, para limitar qué aplicaciones se pueden ejecutar.

  ![De este modo, HoloLens se inicia directamente en la aplicación que se elija.](images/201608-kioskmode-400px.png)

- **Administración de dispositivos móviles (MDM) para HoloLens**. El departamento de TI puede administrar varios dispositivos HoloLens de forma simultánea mediante soluciones como Microsoft Intune. Puede administrar la configuración, seleccionar aplicaciones para instalar y establecer configuraciones de seguridad adaptadas a las necesidades de su organización.

  ![La administración de dispositivos móviles en HoloLens proporciona administración de dispositivos de nivel empresarial en varios dispositivos.](images/201608-enterprisemanagement-400px.png)

- **Windows Update para empresas**. Windows Update para empresas proporciona actualizaciones controladas del sistema operativo para dispositivos y soporte para el canal de mantenimiento a largo plazo.
- **Seguridad de los datos**. El cifrado de datos de BitLocker está habilitado en HoloLens para proporcionar el mismo nivel de protección de seguridad que cualquier otro dispositivo Windows.
- **Acceso al trabajo**. Cualquier persona de la organización puede conectarse de forma remota a la red corporativa mediante una red privada virtual (VPN) en un dispositivo HoloLens. HoloLens también puede acceder a redes Wi-Fi que requieren credenciales.
- **Microsoft Store para Empresas**. El departamento de TI también puede configurar una tienda privada de la empresa, que contenga solo las aplicaciones de la empresa para su uso específico en el dispositivo HoloLens. Distribuya de manera segura el software empresarial a un grupo seleccionado de usuarios empresariales.

## <a name="feature-comparison-between-editions"></a>Comparación de características entre ediciones

|Características |HoloLens (1.ª generación) Development Edition |HoloLens (1.ª generación) Commercial Suite |HoloLens 2 |
|---|:---:|:---:|:---:|
|Cifrado de dispositivo (BitLocker) | |✔️ |✔️ |
|Red privada virtual (VPN) | |✔️ |✔️ |
|[Pantalla completa](hololens-kiosk.md) | |✔️ |✔️ |
|**Administración e implementación** | | | |
|Administración de dispositivos móviles (MDM) | |✔️ |✔️ |
|Posibilidad de bloquear la anulación de la inscripción | |✔️ |✔️ |
|Acceso a red Wi-Fi corporativa basado en certificados | |✔️ |✔️ |
|Microsoft Store (consumidor) |Consumidor |Filtro mediante MDM |Filtro mediante MDM |
|[Portal de Store para empresas](https://docs.microsoft.com/microsoft-store/working-with-line-of-business-apps) | |✔️ |✔️ |
|**Seguridad e identidad** | | | |
|Inicio de sesión con la cuenta de Azure Active Directory (Azure AD) |✔️ |✔️ |✔️ |
|Inicio de sesión con una cuenta de Microsoft (MSA) |✔️ |✔️ |✔️ |
|Credenciales de próxima generación con desbloqueo de PIN |✔️ |✔️ |✔️ |
|[Arranque seguro](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot) |✔️ |✔️ |✔️ |
|**Mantenimiento y asistencia** | | | |
|Actualizaciones automáticas del sistema a medida que llegan |✔️ |✔️ |✔️ |
|[Windows Update para empresas](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) | |✔️ |✔️ |
|Canal de mantenimiento a largo plazo (LTSC) | |✔️ |✔️ |

## <a name="enabling-commercial-features"></a>Habilitación de características comerciales

El administrador de TI de la organización puede configurar características comerciales como Microsoft Store para Empresas, la pantalla completa y el acceso a la red Wi-Fi de la empresa. La documentación de [Microsoft HoloLens](index.yml) proporciona instrucciones paso a paso para inscribir dispositivos e instalar aplicaciones desde Microsoft Store para Empresas.

## <a name="see-also"></a>Vea también

- [Microsoft HoloLens](index.yml)
- [Pantalla completa](hololens-kiosk.md)
- [CSP admitidos en dispositivos HoloLens](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)
- [Microsoft Store para Empresas y aplicaciones de línea de negocio](https://blogs.technet.microsoft.com/sbucci/2016/04/13/windows-store-for-business-and-line-of-business-applications/)
- [Trabajar con aplicaciones de línea de negocio](/microsoft-store/working-with-line-of-business-apps)
