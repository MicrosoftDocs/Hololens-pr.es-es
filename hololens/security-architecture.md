---
title: Arquitectura de seguridad de HoloLens
description: Arquitectura de seguridad
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: seguridad, hololens, hololens 2, hololens2 seguridad, introducción a la seguridad, arquitectura de seguridad, arquitectura, arquitectura de hololens 2
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8e68f73d05db397a7ee088382e82dfa762177b0
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253257"
---
# <span data-ttu-id="bb9ad-104">Introducción y arquitectura de la seguridad</span><span class="sxs-lookup"><span data-stu-id="bb9ad-104">Security overview and architecture</span></span>

<span data-ttu-id="bb9ad-105">La arquitectura de seguridad de la HoloLens 2 se diseñó y fabricó desde la base para no tener problemas de seguridad heredados, creando al mismo tiempo una superficie de ataque minimizada.</span><span class="sxs-lookup"><span data-stu-id="bb9ad-105">The HoloLens 2 security architecture was designed and engineered from the ground up to be free from legacy security issues, while creating a minimized attack surface.</span></span> <span data-ttu-id="bb9ad-106">Esta nueva arquitectura innovadora ofrece ubicaciones de almacenamiento seguras y elementos de seguridad avanzada, con mecanismos capaces de blindar sistemas operativos frente a posibles amenazas y vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="bb9ad-106">This new, innovative architecture offers secure storage locations and advanced security elements, with mechanisms capable of shielding operating systems from potential threats and vulnerabilities.</span></span>

<span data-ttu-id="bb9ad-107">HoloLens 2 combina hardware, software, redes y servicios para brindar seguridad de un extremo a otro, al tiempo que proporciona al usuario una experiencia óptima.</span><span class="sxs-lookup"><span data-stu-id="bb9ad-107">HoloLens 2 combines hardware, software, networking, and services to deliver end-to-end security, while providing the user with an optimal experience.</span></span> <span data-ttu-id="bb9ad-108">Con el HoloLens 2, la gran mayoría de las funciones de seguridad se activan automáticamente, minimizando el esfuerzo requerido para configurar correctamente el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="bb9ad-108">With HoloLens 2, a large majority of security features are now turned on automatically, minimizing the effort required to correctly set up and configure the operating system.</span></span>

<span data-ttu-id="bb9ad-109">El HoloLens 2 de Windows y la arquitectura del sistema operativo ofrecen estas innovadoras características de seguridad:</span><span class="sxs-lookup"><span data-stu-id="bb9ad-109">Windows HoloLens 2 and operating system architecture offers these innovative security features:</span></span>

  * <span data-ttu-id="bb9ad-110">**Separación y el aislamiento de estado**: Esta nueva arquitectura protege partes críticas del sistema operativo de HoloLens 2 de los cambios (como las necesarias para que el sistema operativo arranque en un estado de confianza).</span><span class="sxs-lookup"><span data-stu-id="bb9ad-110">**State separation and isolation**:  This new architecture protects critical portions of the HoloLens 2 operating system from change - such as those required for the core operating system to boot into a trusted state.</span></span> <span data-ttu-id="bb9ad-111">La tecnología de aislamiento se usa para limitar las aplicaciones que no sean de confianza en un área de espacio aislado, asegurándose de que no puedan influir en la seguridad del sistema.</span><span class="sxs-lookup"><span data-stu-id="bb9ad-111">Isolation technology is used to confine untrusted apps in a sandbox area, ensuring that they cannot impact the system security.</span></span> <span data-ttu-id="bb9ad-112">Todo el sistema operativo se segmenta en secciones seguras, donde cada sección se protege gracias a una combinación de otras tecnologías de seguridad.</span><span class="sxs-lookup"><span data-stu-id="bb9ad-112">The entire operating system is segmented into secure sections, with each section shielded by a combination of different security technologies.</span></span>
  
  * <span data-ttu-id="bb9ad-113">**Protección de datos**: Si se pierde o se roba el dispositivo de un usuario, la HoloLens 2 previene que las aplicaciones no autorizadas lean información confidencial confiando en Bi</span><span class="sxs-lookup"><span data-stu-id="bb9ad-113">**Data Protection**: If a user’s device is lost or stolen, HoloLens 2 prevents unauthorized applications from reading sensitive information by relying on BitLocker encryption of data.</span></span> 
  
  * <span data-ttu-id="bb9ad-114">**Sistema operativo si contraseña**: un antiguo sistema operativo basado en contraseña podría exponer de forma inadvertida a los usuarios ante amenazas de phising y a menudo eran responsables de las cuentas comprometidas.</span><span class="sxs-lookup"><span data-stu-id="bb9ad-114">**Password-less operating system**:  Older, password-based operating systems could inadvertently expose users to phishing threats and were often responsible for compromised accounts.</span></span> <span data-ttu-id="bb9ad-115">Con Windows Holographic for Business se elimina el uso de contraseñas para el inicio de sesión de MSA y Azure AD y se refuerza la protección de la identidad del usuario con Windows Hello™ y el inicio de sesión de FIDO2.</span><span class="sxs-lookup"><span data-stu-id="bb9ad-115">Windows Holographic for Business eliminates the use of passwords for MSA and Azure AD sign-in and strengthens user-identity protection with Windows Hello™ and FIDO2 sign-in.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="bb9ad-116">Para que FIDO2 soporte técnico, el dispositivo debe estar en la versión 19041 o posterior.</span><span class="sxs-lookup"><span data-stu-id="bb9ad-116">To have FIDO2 support, the device must be on Build 19041 or higher.</span></span> 

  * <span data-ttu-id="bb9ad-117">**Seguridad de red**: HoloLens 2 brinda al usuario una mayor seguridad de red a través de protocolos mejorados y configuraciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="bb9ad-117">**Network security**: HoloLens 2 offers the user increased network security via improved protocols and default settings.</span></span>
