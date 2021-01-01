---
title: 'Información general: administración de aplicaciones'
description: App, administración, administración de aplicaciones
keywords: HoloLens, usuario, cuenta, aplicación, administración de aplicaciones
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
ms.openlocfilehash: 2ca0b05b6ed61ddce327a44fedbbcf280b33a106
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252671"
---
# Administración de aplicaciones: información general

Puede implementar aplicaciones en cuatro rutas diferentes: **Administración de dispositivos móviles (MDM)**, **Microsoft Store para empresas**, **Microsoft Store**o instalarlas a través del **aprovisionamiento**.

## Administración de dispositivos móviles (MDM)

Una solución MDM permite que los responsables de tomar decisiones de ti y los administradores se instalen automáticamente (push) sus aplicaciones internas, de línea de negocio o las aplicaciones de compra a través de la tienda para un grupo de usuarios. Los dispositivos HoloLens funcionan mejor con Microsoft Endpoint Manager (Intune) para la [Administración de aplicaciones](app-deploy-intune.md). Intune también ofrece a los usuarios un control más preciso sobre las aplicaciones administradas por ti a través de la experiencia descargable del portal de la empresa.

> [!NOTE]
> Las siguientes instrucciones son para los usuarios que desean administrar sus aplicaciones con Intune. Microsoft recomienda usar Intune para la administración de aplicaciones y dispositivos.

La administración de dispositivos móviles (MDM) es aplicable a:

* Implementación de MDM y portal de empresa
* Aplicaciones de línea de negocio (no públicas)
* Instalación manual de las aplicaciones disponibles a través del portal de la empresa
* Administrador Push a través de la Directiva MDM
* Actualización automática a través de MDM

## Microsoft Store para Business

[Microsoft Store para empresas](app-deploy-store-business.md) proporciona a los responsables de la toma de decisiones de ti y a los administradores de las empresas la búsqueda, la adquisición, la administración y la distribución de aplicaciones gratuitas y de dinero. Los administradores de TI pueden administrar las aplicaciones de Microsoft Store y las aplicaciones de línea de negocio privadas en un inventario, además de asignar y reutilizar licencias según sea necesario. Para obtener más información, visite [el apartado requisitos previos para usar Microsoft Store para empresas](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).

Microsoft Store para empresas es aplicable a:

* Aplicaciones públicas o de línea de negocio
* Instalación automática de las aplicaciones necesarias a través de la Asociación de MDM
* El usuario descarga las aplicaciones de forma manual
* Actualización automática

## Aplicaciones de MicrosoftStore

Microsoft Store proporciona a los responsables de las decisiones y administradores de TI de las empresas la búsqueda, la adquisición, la administración y la distribución de aplicaciones públicas.

Esta Microsoft Store es aplicable a:

* Solo aplicaciones públicas
* El usuario descarga las aplicaciones de forma manual
* Actualización automática si se conecta a Internet

Para obtener más información, visite aplicaciones de la [tienda holográfica](https://docs.microsoft.com/hololens/holographic-store-apps).

## Instalar a través de paquetes de aprovisionamiento

Los [paquetes de aprovisionamiento](app-deploy-provisioning-package.md) le permiten instalar aplicaciones personalizadas o de línea de negocios, lo que permite a los profesionales de ti y administradores instalar aplicaciones rápidamente en un dispositivo local a través de USB. Esta instalación puede realizarse sin conexión a Internet y para cualquier tipo de identidad.

La instalación de los paquetes de provisioning es aplicable a:

* Aplicaciones de línea de negocio/desarrolladas por sí mismos (no públicas)
* Aplicaciones públicas (si el instalador sin conexión está disponible)
* Solo carga del lado USB
* No hay ninguna actualización automática (requiere actualizaciones manuales mediante el paquete de aprovisionamiento)

## Instalar aplicaciones en HoloLens 2 a través del instalador de la aplicación

Con el [instalador de aplicaciones](app-deploy-app-installer.md) , los usuarios pueden tener una experiencia que es sencilla para instalar aplicaciones en dispositivos locales o para compartir una aplicación con otra persona que no está familiarizado con otros métodos de instalación de aplicaciones en HoloLens. Esto puede hacerse sin necesidad de habilitar el modo de desarrollador ni usar Device portal. Este es un método simple para distribuir una aplicación completamente integrada. Independientemente de si simplemente deseas demostrar la aplicación a otro usuario con HoloLens o deseas implementar tu aplicación, este método funciona fácilmente.

La instalación mediante el instalador de la aplicación es aplicable a:

* Aplicaciones de línea de negocio/desarrolladas (no públicas)
* Solo carga del lado
* No requiere el modo de desarrollador ni el portal de dispositivos
* Fácil de instalar para el usuario final
