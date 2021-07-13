---
title: 'Información general: Administración de aplicaciones'
description: Introducción a la administración de aplicaciones de realidad mixta con administración de dispositivos móviles, Microsoft Store para empresas y paquetes de aprovisionamiento.
keywords: HoloLens, usuario, cuenta, aplicación, administración de aplicaciones,
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635558"
---
# <a name="app-management-overview"></a>Administración de aplicaciones: Información general

Puede implementar aplicaciones en cuatro rutas de acceso diferentes: **Mobile Administración de dispositivos (MDM)**, **Microsoft Store para Empresas**, **Microsoft Store** o instalando mediante el **aprovisionamiento** de .

## <a name="mobile-device-management-mdm"></a>Administración de dispositivos móviles (MDM)

Una solución MDM permite a los responsables de la toma de decisiones de TI y a los administradores instalar automáticamente (insertar) de forma privada sus aplicaciones de línea de negocio interna o comprar aplicaciones a través de la tienda para un grupo de usuarios. HoloLens dispositivos funcionan mejor con Microsoft Endpoint Manager (Intune) para la [administración de aplicaciones.](app-deploy-intune.md) Intune también ofrece a los usuarios un control más preciso sobre las aplicaciones administradas por IT a través Portal de empresa experiencia descargable.

> [!NOTE]
> Las instrucciones siguientes son para los usuarios que desean administrar sus aplicaciones con Intune. Microsoft recomienda usar Intune para la administración de aplicaciones y dispositivos.

La Administración de dispositivos móvil (MDM) es aplicable a:

* MDM implementado + Portal de empresa
* Aplicaciones de línea de negocio (no públicas)
* Instalación manual de aplicaciones disponibles mediante Portal de empresa
* Inserción de administración a través de la directiva MDM
* Actualización automática a través de MDM

## <a name="microsoft-store-for-business"></a>Microsoft Store para Empresas

El [Microsoft Store para Empresas](app-deploy-store-business.md) proporciona a los responsables de la toma de decisiones de TI y a los administradores de las empresas para buscar, adquirir, administrar y distribuir aplicaciones gratuitas y de pago. Los administradores de TI pueden administrar Microsoft Store aplicaciones y aplicaciones de línea de negocio privadas en un inventario, además de asignar y reutilizar licencias según sea necesario. Para obtener más información, visite [Requisitos previos para usar el Microsoft Store para Empresas](/microsoft-store/prerequisites-microsoft-store-for-business).

El Microsoft Store para Empresas es aplicable a:

* Aplicaciones públicas o de línea de negocio
* Instalación automática de aplicaciones necesarias a través de la asociación mdm
* El usuario descarga aplicaciones manualmente
* Actualización automática

## <a name="microsoft-store-apps"></a>Aplicaciones de Microsoft Store

El Microsoft Store proporciona a los responsables de la toma de decisiones de TI y a los administradores de las empresas para buscar, adquirir, administrar y distribuir aplicaciones públicas.

Esta Microsoft Store es aplicable a:

* Solo aplicaciones públicas
* El usuario descarga aplicaciones manualmente
* Actualización automática si está conectado a Internet

Para obtener más información, visite [Aplicaciones de la Tienda Holográfica](/hololens/holographic-store-apps).

## <a name="install-via-provisioning-packages"></a>Instalación a través de paquetes de aprovisionamiento

[Los paquetes](app-deploy-provisioning-package.md) de aprovisionamiento permiten instalar aplicaciones personalizadas o de línea de negocio, lo que permite a los profesionales de TI y administradores instalar rápidamente aplicaciones en un dispositivo local a través de USB. Esta instalación se puede realizar sin conexión a Internet y para cualquier tipo de identidad.

La instalación a través de paquetes de aprovisionamiento es aplicable a:

* Línea de negocio/ aplicaciones auto-desarrolladas (no públicas)
* Aplicaciones públicas (si el instalador sin conexión está disponible)
* Solo carga lateral USB
* Sin actualización automática (requiere actualizaciones manuales a través del paquete de aprovisionamiento)

## <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalación de aplicaciones en HoloLens 2 a través de Instalador de aplicación

Con el [Instalador de aplicación](app-deploy-app-installer.md) los usuarios pueden tener una experiencia sencilla para instalar aplicaciones en dispositivos locales o compartir una aplicación con otra persona que no esté familiarizado con otros métodos de instalación de aplicaciones en HoloLens. Esto se puede hacer sin necesidad de habilitar el modo de desarrollador o usar Portal de dispositivos. Se trata de un método sencillo de distribuir una aplicación completamente creada. Independientemente de si simplemente desea realizar una demostración de la aplicación a otro usuario con un HoloLens, o si desea implementar la aplicación, este método funciona fácilmente.

La instalación mediante Instalador de aplicación es aplicable a:

* Aplicaciones de línea de negocio/auto-desarrolladas (no públicas)
* Solo carga lateral
* No requiere el modo de desarrollador ni el portal de dispositivos
* Fácil de instalar para el usuario final
