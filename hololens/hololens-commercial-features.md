---
title: Características comerciales
description: Microsoft HoloLens Commercial Suite incluye características que facilitan a las empresas la administración de dispositivos HoloLens. Los dispositivos HoloLens 2 están equipados con características comerciales de forma predeterminada.
keywords: HoloLens, comercial, características, MDM, administración de dispositivos móviles, pantalla completa
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
ms.openlocfilehash: 28898c5c0cbc2a4f66cea13665e5ef63447db382
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828756"
---
# Características comerciales

HoloLens incluye características que facilitan a las empresas la administración de dispositivos HoloLens.

Cada dispositivo HoloLens 2 tiene características comerciales disponibles.

HoloLens (1.ª generación) se incluía con dos opciones de licencia, la licencia de desarrollador y una licencia comercial. Para potenciar las capacidades comerciales de HoloLens, actualiza la licencia de desarrollador a una licencia comercial. Para comprar Microsoft HoloLens Commercial Suite, ponte en contacto con el administrador de cuentas local de Microsoft.

>[!VIDEO https://www.youtube.com/embed/tNd0e2CiAkE]

## Características comerciales clave

- **Pantalla completa.** Puedes usar HoloLens en demostración o presentar experiencias con la pantalla completa, para limitar qué aplicaciones se pueden ejecutar.

  ![Con la pantalla completa, HoloLens se inicia directamente en la aplicación que elijas.](images/201608-kioskmode-400px.png)

- **Administración de dispositivos móviles (MDM) para HoloLens.** Tu departamento de TI puede administrar varios dispositivos HoloLens de forma simultánea mediante soluciones como Microsoft Intune. Puede administrar la configuración, seleccionar aplicaciones para instalar y establecer configuraciones de seguridad adaptadas a las necesidades de tu organización.

  ![La Administración de dispositivos móviles en HoloLens proporciona administración de dispositivos de nivel empresarial en varios dispositivos.](images/201608-enterprisemanagement-400px.png)

- **Windows Update para empresas.** Windows Update para empresas proporciona actualizaciones controladas del sistema operativo para dispositivos y soporte para el canal de mantenimiento a largo plazo.
- **Seguridad de los datos.** El cifrado de datos de BitLocker está habilitado en HoloLens para proporcionar el mismo nivel de protección de seguridad que cualquier otro dispositivo Windows.
- **Acceso al trabajo.** Cualquier persona de tu organización puede conectarse de forma remota a la red corporativa a través de una red privada virtual (VPN) en un HoloLens. HoloLens también puede obtener acceso a redes Wi-Fi que requieren credenciales.
- **Microsoft Store para Empresas.** Tu departamento de TI también puede configurar una tienda privada empresarial, que contenga solo las aplicaciones de tu empresa para su uso específico de HoloLens. Distribuye de manera segura el software empresarial al grupo seleccionado de usuarios empresariales.

## Comparación de características entre ediciones

|Características |HoloLens Development Edition |HoloLens Commercial Suite |HoloLens 2 |
|---|:---:|:---:|:---:|
|Cifrado de dispositivo (BitLocker) | |✔️ |✔️ |
|Red privada virtual (VPN) | |✔️ |✔️ |
|[Pantalla completa](hololens-kiosk.md) | |✔️ |✔️ |
|**Administración e implementación** | | | |
|Administración de dispositivos móviles (MDM) | |✔️ |✔️ |
|Posibilidad de bloquear la anulación de la inscripción | |✔️ |✔️ |
|Acceso de Wi-Fi corporativo basado en certificados | |✔️ |✔️ |
|Microsoft Store (consumidor) |Consumidor |Filtrar mediante MDM |Filtrar mediante MDM |
|[Portal de la Store para empresas](https://docs.microsoft.com/microsoft-store/working-with-line-of-business-apps) | |✔️ |✔️ |
|**Seguridad e identidad** | | | |
|Iniciar sesión con la cuenta de Azure Active Directory (AAD) |✔️ |✔️ |✔️ |
|Iniciar sesión con una cuenta de Microsoft (MSA) |✔️ |✔️ |✔️ |
|Credenciales de próxima generación con desbloqueo de PIN |✔️ |✔️ |✔️ |
|[Arranque seguro](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot) |✔️ |✔️ |✔️ |
|**Mantenimiento y asistencia** | | | |
|Actualizaciones automáticas del sistema a medida que llegan |✔️ |✔️ |✔️ |
|[Windows Update para empresas](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) | |✔️ |✔️ |
|Canal de mantenimiento a largo plazo (LTSC) | |✔️ |✔️ |

## Habilitar características comerciales

El administrador de TI de su organización puede configurar características comerciales como Microsoft Store para Empresas, la pantalla completa y el acceso de Wi-Fi empresarial. La documentación de [Microsoft HoloLens](index.md) proporciona instrucciones paso a paso para inscribir dispositivos e instalar aplicaciones desde Microsoft Store para Empresas.

## Puedes ver también

- [Microsoft HoloLens](index.md)
- [Pantalla completa](hololens-kiosk.md)
- [CSP admitidos en dispositivos HoloLens](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)
- [Microsoft Store para Empresas y aplicaciones de línea de negocio](https://blogs.technet.microsoft.com/sbucci/2016/04/13/windows-store-for-business-and-line-of-business-applications/)
- [Trabajar con aplicaciones de línea de negocio](/microsoft-store/working-with-line-of-business-apps)
