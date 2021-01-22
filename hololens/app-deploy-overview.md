---
title: 'Información general: Administración de aplicaciones'
description: Introducción a la administración de aplicaciones de realidad mixta con la administración de dispositivos móviles, la Microsoft Store para Empresas y los paquetes de aprovisionamiento.
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
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283711"
---
# Administración de aplicaciones: información general

Puedes implementar aplicaciones en cuatro rutas diferentes: Administración de dispositivos móviles **(MDM),** **Microsoft Store**para Empresas, **Microsoft Store**o si las instalas a través del **aprovisionamiento.**

## Administración de dispositivos móviles (MDM)

Una solución MDM permite a los responsables de la toma de decisiones de TI y a los administradores instalar automáticamente (insertar) de forma privada sus aplicaciones de línea de negocio, o comprar aplicaciones a través de la tienda para un grupo de usuarios. Los dispositivos HoloLens funcionan mejor con Microsoft Endpoint Manager (Intune) para la [administración de aplicaciones.](app-deploy-intune.md) Intune también ofrece a los usuarios un control más preciso sobre las aplicaciones administradas por IT a través de la experiencia descargable del Portal de empresa.

> [!NOTE]
> Las siguientes instrucciones son para los usuarios que desean administrar sus aplicaciones con Intune. Microsoft recomienda usar Intune para la administración de aplicaciones y dispositivos.

La administración de dispositivos móviles (MDM) se aplica a:

* MDM implementado + Portal de empresa
* Aplicaciones de línea de negocio (no públicas)
* Instalación manual de aplicaciones disponibles a través del Portal de empresa
* Inserción de administrador a través de la directiva MDM
* Actualización automática a través de MDM

## Microsoft Store para Business

La [Microsoft Store para Empresas](app-deploy-store-business.md) proporciona a los responsables de la toma de decisiones de TI y a los administradores de las empresas la capacidad de buscar, adquirir, administrar y distribuir aplicaciones gratuitas y de pago. Los administradores de TI pueden administrar aplicaciones de Microsoft Store y aplicaciones de línea de negocio privadas en un inventario, además de asignar y reutilizar licencias según sea necesario. Para obtener más información, visita [Requisitos previos para usar la Microsoft Store para Empresas.](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)

La Microsoft Store para Empresas se aplica a:

* Aplicaciones públicas o de línea de negocio
* Instalación automática de aplicaciones necesarias a través de la asociación MDM
* El usuario descarga aplicaciones manualmente
* Actualización automática

## Aplicaciones de MicrosoftStore

Microsoft Store proporciona a los responsables de la toma de decisiones de TI y a los administradores de las empresas la capacidad de buscar, adquirir, administrar y distribuir aplicaciones públicas.

Esta Microsoft Store se aplica a:

* Solo aplicaciones públicas
* El usuario descarga aplicaciones manualmente
* Actualización automática si está conectado a Internet

Para obtener más información, visita [Aplicaciones de la Tienda Holográfica.](https://docs.microsoft.com/hololens/holographic-store-apps)

## Instalar a través de paquetes de aprovisionamiento

[Los paquetes](app-deploy-provisioning-package.md) de aprovisionamiento te permiten instalar aplicaciones personalizadas o de línea de negocio, lo que permite a los profesionales de TI y administradores instalar rápidamente aplicaciones en un dispositivo local a través de USB. Esta instalación se puede realizar sin una conexión a Internet y para cualquier tipo de identidad.

La instalación a través de paquetes de aprovisionamiento es aplicable para:

* Línea de negocio/ aplicaciones autodese desarrolladas (no públicas)
* Aplicaciones públicas (si el instalador sin conexión está disponible)
* Solo carga lateral USB
* Sin actualización automática (requiere actualizaciones manuales a través del paquete de aprovisionamiento)

## Instalar aplicaciones en HoloLens 2 mediante el Instalador de aplicación

El [](app-deploy-app-installer.md) uso del Instalador de aplicación puede tener una experiencia sencilla para instalar aplicaciones en dispositivos locales o compartir una aplicación con otra persona que no esté familiarizado con otros métodos de instalación de aplicaciones en HoloLens. Esto se puede hacer sin necesidad de habilitar el modo de desarrollador o usar Device Portal. Este es un método sencillo de distribuir una aplicación completamente integrada. Independientemente de si simplemente quieres realizar una demostración de la aplicación a otro usuario con un HoloLens, o quieres implementar tu aplicación, este método funciona fácilmente.

La instalación a través del Instalador de aplicación es aplicable para:

* Línea de negocio/ aplicaciones auto desarrolladas (no públicas)
* Solo carga lateral
* No requiere el modo de desarrollador ni Device Portal
* Fácil de instalar para el usuario final
