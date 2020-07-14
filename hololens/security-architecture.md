---
title: Arquitectura de seguridad de HoloLens
description: Arquitectura de seguridad
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: seguridad, hololens, hololens 2, hololens2 seguridad, introducción a la seguridad, arquitectura de seguridad, arquitectura, arquitectura de hololens 2
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 8045f534926e0719bd2f8e448809b5a2965346c4
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865800"
---
# <span data-ttu-id="d1489-104">Introducción y arquitectura de la seguridad</span><span class="sxs-lookup"><span data-stu-id="d1489-104">Security overview and architecture</span></span>

<span data-ttu-id="d1489-105">La arquitectura de seguridad de la HoloLens 2 se diseñó y fabricó desde la base para no tener problemas de seguridad heredados, creando al mismo tiempo una superficie de ataque minimizada.</span><span class="sxs-lookup"><span data-stu-id="d1489-105">The HoloLens 2 security architecture was designed and engineered from the ground up to be free from legacy security issues, while creating a minimized attack surface.</span></span> <span data-ttu-id="d1489-106">Esta nueva arquitectura innovadora ofrece ubicaciones de almacenamiento seguras y elementos de seguridad avanzada, con mecanismos capaces de blindar sistemas operativos frente a posibles amenazas y vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="d1489-106">This new, innovative architecture offers secure storage locations and advanced security elements, with mechanisms capable of shielding operating systems from potential threats and vulnerabilities.</span></span>

<span data-ttu-id="d1489-107">HoloLens 2 combina hardware, software, redes y servicios para brindar seguridad de un extremo a otro, al tiempo que proporciona al usuario una experiencia óptima.</span><span class="sxs-lookup"><span data-stu-id="d1489-107">HoloLens 2 combines hardware, software, networking, and services to deliver end-to-end security, while providing the user with an optimal experience.</span></span> <span data-ttu-id="d1489-108">Con el HoloLens 2, la gran mayoría de las funciones de seguridad se activan automáticamente, minimizando el esfuerzo requerido para configurar correctamente el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d1489-108">With HoloLens 2, a large majority of security features are now turned on automatically, minimizing the effort required to correctly set up and configure the operating system.</span></span>

<span data-ttu-id="d1489-109">El HoloLens 2 de Windows y la arquitectura del sistema operativo ofrecen estas innovadoras características de seguridad:</span><span class="sxs-lookup"><span data-stu-id="d1489-109">Windows HoloLens 2 and operating system architecture offers these innovative security features:</span></span>

  * <span data-ttu-id="d1489-110">**Separación y el aislamiento de estado**: Esta nueva arquitectura protege partes críticas del sistema operativo de HoloLens 2 de los cambios (como las necesarias para que el sistema operativo arranque en un estado de confianza).</span><span class="sxs-lookup"><span data-stu-id="d1489-110">**State separation and isolation**:  This new architecture protects critical portions of the HoloLens 2 operating system from change - such as those required for the core operating system to boot into a trusted state.</span></span> <span data-ttu-id="d1489-111">La tecnología de aislamiento se usa para limitar las aplicaciones que no sean de confianza en un área de espacio aislado, asegurándose de que no puedan influir en la seguridad del sistema.</span><span class="sxs-lookup"><span data-stu-id="d1489-111">Isolation technology is used to confine untrusted apps in a sandbox area, ensuring that they cannot impact the system security.</span></span> <span data-ttu-id="d1489-112">Todo el sistema operativo se segmenta en secciones seguras, donde cada sección se protege gracias a una combinación de otras tecnologías de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d1489-112">The entire operating system is segmented into secure sections, with each section shielded by a combination of different security technologies.</span></span>
  
  * <span data-ttu-id="d1489-113">**Protección de datos**: Si se pierde o se roba el dispositivo de un usuario, la HoloLens 2 previene que las aplicaciones no autorizadas lean información confidencial confiando en Bi</span><span class="sxs-lookup"><span data-stu-id="d1489-113">**Data Protection**: If a user’s device is lost or stolen, HoloLens 2 prevents unauthorized applications from reading sensitive information by relying on BitLocker encryption of data.</span></span> 
  
  * <span data-ttu-id="d1489-114">**Sistema operativo si contraseña**: un antiguo sistema operativo basado en contraseña podría exponer de forma inadvertida a los usuarios ante amenazas de phising y a menudo eran responsables de las cuentas comprometidas.</span><span class="sxs-lookup"><span data-stu-id="d1489-114">**Password-less operating system**:  Older, password-based operating systems could inadvertently expose users to phishing threats and were often responsible for compromised accounts.</span></span> <span data-ttu-id="d1489-115">Con Windows Holographic for Business se elimina el uso de contraseñas para el inicio de sesión de MSA y AAD y se refuerza la protección de la identidad del usuario con Windows Hello™ y el inicio de sesión de FIDO2.</span><span class="sxs-lookup"><span data-stu-id="d1489-115">Windows Holographic for Business eliminates the use of passwords for MSA and AAD sign-in and strengthens user-identity protection with Windows Hello™ and FIDO2 sign-in.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="d1489-116">Para que FIDO2 soporte técnico, el dispositivo debe estar en la versión 19041 o posterior.</span><span class="sxs-lookup"><span data-stu-id="d1489-116">To have FIDO2 support, the device must be on Build 19041 or higher.</span></span> 

  * <span data-ttu-id="d1489-117">**Seguridad de red**: HoloLens 2 brinda al usuario una mayor seguridad de red a través de protocolos mejorados y configuraciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="d1489-117">**Network security**: HoloLens 2 offers the user increased network security via improved protocols and default settings.</span></span>
