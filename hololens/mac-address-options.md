---
title: Inscripción para la empresa de dispositivos HoloLens en un entorno Wi-Fi restringido de direcciones MAC
description: Cómo obtener la dirección MAC para la red en los dispositivos HoloLens 2
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: fe365248332f8e78b15ab362f169b84e48dfe594
ms.sourcegitcommit: 07ffe1bf2f45dcb2ba9d7fbe54b4773a0fb9d525
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393844"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a><span data-ttu-id="4fbdc-103">Inscripción para la empresa de dispositivos HoloLens en un entorno Wi-Fi restringido de direcciones MAC</span><span class="sxs-lookup"><span data-stu-id="4fbdc-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="4fbdc-104">Este documento describirá un escenario común que hemos identificado dentro de los entornos de clientes en los que la Wi-Fi está restringida por direcciones MAC, o bien se requiere los certificados para unirse a las redes inalámbricas.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="4fbdc-105">Escenario de ejemplo</span><span class="sxs-lookup"><span data-stu-id="4fbdc-105">Example Scenario</span></span>

<span data-ttu-id="4fbdc-106">Un gran número de clientes en entornos seguros tienen restricciones en sus redes inalámbricas o alámbricas que solo permitirán que los dispositivos aprobados (basados en direcciones MAC) se conecten correctamente.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-106">Many customers in secure environments have restrictions on their Wireless or wired networks which will only allow approved devices (based on MAC Addresses) to connect successfully.</span></span> <span data-ttu-id="4fbdc-107">Esto puede aplicarse a través del filtrado de direcciones MAC en un punto de acceso inalámbrico o a través de un servidor DHCP.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-107">This may be enforced through MAC Address filtering on a Wireless Access Point or through a DHCP server.</span></span> <span data-ttu-id="4fbdc-108">Además, algunas redes inalámbricas se pueden proteger con PEAP, lo que requiere que se aplique un certificado al dispositivo antes de poder autenticar la red inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-108">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to authenticating on the Wireless network.</span></span>

<span data-ttu-id="4fbdc-109">En este escenario, dos requisitos clave pueden introducir retrasos o requerir una intervención manual al unir dispositivos HoloLens a la red:</span><span class="sxs-lookup"><span data-stu-id="4fbdc-109">In this scenario, two key requirements may introduce delays or require manual intervention when joining HoloLens devices to the network:</span></span>

- <span data-ttu-id="4fbdc-110">El certificado inalámbrico PEAP debe aplicarse al dispositivo antes de que el dispositivo haya sido incorporado correctamente a la red inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-110">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="4fbdc-111">Debe registrarse la dirección MAC del adaptador Wi-Fi de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-111">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="4fbdc-112">Los principales desafíos con los requisitos anteriores son:</span><span class="sxs-lookup"><span data-stu-id="4fbdc-112">The core challenges with the requirements above are:</span></span>

1. <span data-ttu-id="4fbdc-113">Actualmente, la dirección MAC solo puede ser identificada desde la aplicación Configuración del dispositivo, o bien desde Intune después de una inscripción completa.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-113">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful enrollment.</span></span>
2. <span data-ttu-id="4fbdc-114">Sin la dirección MAC, el dispositivo no puede unirse a la red Wi-Fi para comenzar la inscripción.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-114">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>
3. <span data-ttu-id="4fbdc-115">Las soluciones alternativas manuales a estos desafíos requieren que un técnico interactúe con el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-115">Manual workarounds to these challenges require a technician to interact with the device.</span></span>

## <a name="solutions"></a><span data-ttu-id="4fbdc-116">Soluciones</span><span class="sxs-lookup"><span data-stu-id="4fbdc-116">Solutions</span></span>

<span data-ttu-id="4fbdc-117">Existen muchas maneras de mejorar esta situación, en función de la infraestructura disponible en el entorno.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-117">There are many ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="4fbdc-118">Solución</span><span class="sxs-lookup"><span data-stu-id="4fbdc-118">Solution</span></span> | <span data-ttu-id="4fbdc-119">Ventajas</span><span class="sxs-lookup"><span data-stu-id="4fbdc-119">Benefits</span></span> | <span data-ttu-id="4fbdc-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4fbdc-120">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="4fbdc-121">Paquete de aprovisionamiento con adaptador Ethernet</span><span class="sxs-lookup"><span data-stu-id="4fbdc-121">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="4fbdc-122">Mejora la experiencia de OOBE y permite obtener una experiencia técnica más rápida.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-122">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="4fbdc-123">Concentrador USB-C Hub + adaptador de Ethernet compatible con HoloLens, el técnico aún deberá interactuar con el dispositivo para la captura del MAC y la finalización del OOBE</span><span class="sxs-lookup"><span data-stu-id="4fbdc-123">HoloLens compatible USB-C Hub + Ethernet adaptor, and technician will still need to interact with the device for MAC capture and OOBE finalisation</span></span> |
| <span data-ttu-id="4fbdc-124">Piloto automático con registro de Intune por Ethernet</span><span class="sxs-lookup"><span data-stu-id="4fbdc-124">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="4fbdc-125">Se trata de una conexión y registro en un solo paso del dispositivo en el entorno del cliente.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-125">This is a single step connection and registration of the device to the customer environment.</span></span> <span data-ttu-id="4fbdc-126">La captura de MAC se puede completar sin necesidad de interactuar con el dispositivo</span><span class="sxs-lookup"><span data-stu-id="4fbdc-126">MAC capture can be completed without needing to interact with the device</span></span> | <span data-ttu-id="4fbdc-127">Intune habilitado para el espacio empresarial de AAD del cliente y un adaptador de Ethernet USB-C compatible con HoloLens</span><span class="sxs-lookup"><span data-stu-id="4fbdc-127">Intune enabled for the customer AAD tenant and a HoloLens compatible USB-C Ethernet adaptor</span></span> |
| <span data-ttu-id="4fbdc-128">Creación de informes automatizada de direcciones MAC</span><span class="sxs-lookup"><span data-stu-id="4fbdc-128">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="4fbdc-129">Cuando los dispositivos se registran con el espacio empresarial de Intune, un script puede notificar la dirección de MAC al técnico.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-129">When devices are registered with the Intune tenant, a script can report the MAC address to the technician.</span></span> | <span data-ttu-id="4fbdc-130">Commandlets de Intune PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fbdc-130">Intune Powershell Commandlets</span></span> |

## <a name="provisioning-package-with-ethernet-adaptor"></a><span data-ttu-id="4fbdc-131">Paquete de aprovisionamiento con adaptador Ethernet</span><span class="sxs-lookup"><span data-stu-id="4fbdc-131">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="4fbdc-132">Si la red cableada también está sujeta a restricciones de MAC, entonces la dirección MAC del concentrador USB-C Hub + adaptador de Ethernet también deberá ser aprobada previamente.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-132">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Hub + Ethernet adaptor will also need to be pre-approved.</span></span> <span data-ttu-id="4fbdc-133">Se debe tener cuidado con este adaptador ya que permitirá el acceso a la red desde otros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-133">Care should be taken with this adapter as it will allow access to the network from other devices.</span></span>

### <a name="requirements"></a><span data-ttu-id="4fbdc-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4fbdc-134">Requirements</span></span>

- <span data-ttu-id="4fbdc-135">Puerto de red conectado con acceso a la red del cliente</span><span class="sxs-lookup"><span data-stu-id="4fbdc-135">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="4fbdc-136">Concentrador USB-C compatible con HoloLens con adaptador Ethernet: cualquier adaptador que no requiera que se instalen controladores adicionales o instalaciones de aplicaciones debería servir.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-136">HoloLens Compatible USB-C Hub with Ethernet adaptor – Any adapter that doesn&#39;t require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="4fbdc-137">Paquete de aprovisionamiento que contiene lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4fbdc-137">Provisioning Package containing:</span></span>
  - <span data-ttu-id="4fbdc-138">Contiene información de red inalámbrica y un certificado</span><span class="sxs-lookup"><span data-stu-id="4fbdc-138">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="4fbdc-139">Puede contener información de inscripción para Azure AD de la organización.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-139">Optionally containing enrollment information for the Organization&#39;s Azure AD</span></span>
  - <span data-ttu-id="4fbdc-140">Contiene otras opciones de configuración de aprovisionamiento necesarias</span><span class="sxs-lookup"><span data-stu-id="4fbdc-140">Containing any other required provisioning settings</span></span>

### <a name="process"></a><span data-ttu-id="4fbdc-141">Proceso</span><span class="sxs-lookup"><span data-stu-id="4fbdc-141">Process</span></span>

<span data-ttu-id="4fbdc-142">El proceso puede variar según el nivel de software del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-142">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="4fbdc-143">Si el dispositivo tiene la[actualización de mayo de 2004](hololens-release-notes.md#windows-holographic-version-2004), siga los pasos que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-143">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="4fbdc-144">Coloque el paquete de aprovisionamiento en la raíz de una memoria USB, y conéctelo al concentrador.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-144">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="4fbdc-145">Conecte el cable de Ethernet al adaptador Concentrador + adaptador de Ethernet.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-145">Connect Ethernet cable to the Hub + Ethernet adapter.</span></span>
3. <span data-ttu-id="4fbdc-146">Conecte el concentrador USB-C al dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-146">Connect USB-C Hub to HoloLens device.</span></span>
4. <span data-ttu-id="4fbdc-147">Active HoloLens y póngase el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-147">Turn on the HoloLens and put on the device.</span></span>
5. <span data-ttu-id="4fbdc-148">Pulse el botón de **Bajar volumen y Encendido** para aplicar el paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-148">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="4fbdc-149">El técnico ya puede seguir OOBE y, una vez completada, abrir la aplicación Configuración y recuperar la dirección MAC del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-149">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="4fbdc-150">Si el dispositivo tiene una compilación de sistema operativo antes de la [Actualización de mayo de 2004](hololens-release-notes.md#windows-holographic-version-2004), siga los siguientes pasos que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-150">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="4fbdc-151">Active HoloLens y conéctelo a un equipo.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-151">Turn on the HoloLens and plug the device into a PC.</span></span>
2. <span data-ttu-id="4fbdc-152">El dispositivo debería aparecer en el equipo como un dispositivo de almacenamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-152">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="4fbdc-153">Copie el paquete de aprovisionamiento al dispositivo</span><span class="sxs-lookup"><span data-stu-id="4fbdc-153">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="4fbdc-154">Conecte el cable de Ethernet al concentrador.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-154">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="4fbdc-155">Conecte el concentrador USB-C al dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-155">Connect USB-C Hub to HoloLens device.</span></span>
6. <span data-ttu-id="4fbdc-156">Póngase HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="4fbdc-156">Put on the HoloLens</span></span>
7. <span data-ttu-id="4fbdc-157">Pulse el botón de **Bajar volumen y encender** para aplicar el paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-157">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="4fbdc-158">El técnico ya puede seguir OOBE y, una vez completada, abrir la aplicación Configuración y recuperar la dirección MAC del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-158">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

### <a name="benefits"></a><span data-ttu-id="4fbdc-159">Ventajas</span><span class="sxs-lookup"><span data-stu-id="4fbdc-159">Benefits</span></span>

<span data-ttu-id="4fbdc-160">De esta forma, con un &quot;simple toque &quot;del dispositivo, se puede aplicar el paquete de aprovisionamiento correcto y recoger la dirección MAC del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-160">This will allow a &quot;Single touch&quot; of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="4fbdc-161">Los paquetes de aprovisionamiento se pueden ser creados siguiendo las instrucciones aquí.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-161">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="autopilot-with-intune-enrollment"></a><span data-ttu-id="4fbdc-162">Autopiloto con inscripción de Intune</span><span class="sxs-lookup"><span data-stu-id="4fbdc-162">Autopilot with Intune Enrollment</span></span>

### <a name="requirements"></a><span data-ttu-id="4fbdc-163">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4fbdc-163">Requirements</span></span>

- <span data-ttu-id="4fbdc-164">Puerto de red conectado con acceso a la red del cliente</span><span class="sxs-lookup"><span data-stu-id="4fbdc-164">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="4fbdc-165">Dispositivos HoloLens que ejecutan Windows Holographic 2004</span><span class="sxs-lookup"><span data-stu-id="4fbdc-165">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="4fbdc-166">Adaptador de Ethernet USB-C compatible con HoloLens</span><span class="sxs-lookup"><span data-stu-id="4fbdc-166">HoloLens Compatible USB-C Ethernet adapter</span></span>
- <span data-ttu-id="4fbdc-167">Configuración y habilitación de Intune para el espacio empresarial de cliente</span><span class="sxs-lookup"><span data-stu-id="4fbdc-167">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="4fbdc-168">Dispositivo registrado para el piloto automático e importado en el espacio empresarial del cliente</span><span class="sxs-lookup"><span data-stu-id="4fbdc-168">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="4fbdc-169">Directivas de Intune definidas para el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="4fbdc-169">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="4fbdc-170">Contiene información de red inalámbrica y un certificado</span><span class="sxs-lookup"><span data-stu-id="4fbdc-170">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="4fbdc-171">Contiene otras opciones de configuración de aprovisionamiento necesarias</span><span class="sxs-lookup"><span data-stu-id="4fbdc-171">Containing any other required provisioning settings</span></span>

<span data-ttu-id="4fbdc-172">Esto permitirá a un cliente con requisitos de red avanzados inscribir los dispositivos en un enfoque sin contacto y escalable</span><span class="sxs-lookup"><span data-stu-id="4fbdc-172">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="4fbdc-173">Los requisitos previos adicionales serán necesarios como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="4fbdc-173">Additional pre-requisites will be needed as below:</span></span>
1. [<span data-ttu-id="4fbdc-174">Habilitar el espacio empresarial en la versión preliminar del piloto automático</span><span class="sxs-lookup"><span data-stu-id="4fbdc-174">Enable the Tenant for the Autopilot preview</span></span>](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. <span data-ttu-id="4fbdc-175">Crear las directivas de HoloLens para reemplazar el paquete de aprovisionamiento en Intune.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-175">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="4fbdc-176">Crear las directivas de HoloLens Intune.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-176">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="4fbdc-177">Asignar los dispositivos al grupo correcto.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-177">Assign the devices to the correct group.</span></span>

### <a name="process"></a><span data-ttu-id="4fbdc-178">Proceso</span><span class="sxs-lookup"><span data-stu-id="4fbdc-178">Process</span></span>

1. <span data-ttu-id="4fbdc-179">Conecte el cable de ethernet al adaptador y conecte el adaptador al puerto USB-C en el dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-179">Connect the ethernet cable to the adapter and plug the adapter into the USB-C port on the HoloLens 2 device.</span></span>
2. <span data-ttu-id="4fbdc-180">Active el HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="4fbdc-180">Turn on the HoloLens.</span></span>
3. <span data-ttu-id="4fbdc-181">El dispositivo debería conectarse automáticamente a Internet durante OOBE a través del adaptador Ethernet.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-181">The device should automatically connect to the internet during OOBE via the Ethernet adaptor.</span></span> <span data-ttu-id="4fbdc-182">Debería detectar la configuración de Autopilot y registrarse automáticamente con Azure AD e Intune.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-182">It should detect the Autopilot configuration and automatically register with Azure AD and Intune</span></span>
4. <span data-ttu-id="4fbdc-183">El dispositivo aplicará los certificados Wi-Fi necesarios y otras opciones de configuración que sean necesarios mediante Intune.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-183">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune</span></span>
5. <span data-ttu-id="4fbdc-184">Una vez finalizado, el técnico podrá cargar el portal de Intune (Endpoint Manager) y profundizar en la página de propiedades del dispositivo, en **Inicio -> Dispositivos -> NombreDispositivo -> Hardware**</span><span class="sxs-lookup"><span data-stu-id="4fbdc-184">When complete, the technician can load the Intune (Endpoint Manager) Portal and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**</span></span>
6. <span data-ttu-id="4fbdc-185">La dirección de MAC WiFi estará visible en el portal de Intune.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-185">The Wifi MAC address will be visible within the Intune Portal</span></span>

![Dirección MAC a través de Intune](images/mac-address-intune.jpg)

7. <span data-ttu-id="4fbdc-187">El técnico agregará esta dirección MAC como dispositivo permitido.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-187">The technician will add this MAC address as an allowed device.</span></span>

### <a name="benefits"></a><span data-ttu-id="4fbdc-188">Ventajas</span><span class="sxs-lookup"><span data-stu-id="4fbdc-188">Benefits</span></span>

<span data-ttu-id="4fbdc-189">Esto permitirá una experiencia de implementación &quot;sin contacto&quot; para el técnico, en la que el dispositivo pueda inscribirse directamente en Azure AD e Intune sin que el técnico tenga que llevar el dispositivo o interactuar manualmente con el entorno del HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-189">This will allow a &quot;Heads off&quot; deployment experience for the Technician, with the device being able to go from the box to enrolled in Azure AD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <a name="reporting-of-mac-addresses-to-the-technician"></a><span data-ttu-id="4fbdc-190">Informar de las direcciones MAC al técnico</span><span class="sxs-lookup"><span data-stu-id="4fbdc-190">Reporting of MAC addresses to the Technician</span></span>

### <a name="requirements"></a><span data-ttu-id="4fbdc-191">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4fbdc-191">Requirements</span></span>

- <span data-ttu-id="4fbdc-192">Autorización de &quot;Intune Graph Powershell&quot; en el espacio empresarial del cliente</span><span class="sxs-lookup"><span data-stu-id="4fbdc-192">Authorization of the &quot;Intune Graph PowerShell&quot; against the customer Tenant</span></span>
- <span data-ttu-id="4fbdc-193">Instalación de Intune Graph Powershell en el equipo del técnico.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-193">Installation of the Intune Graph PowerShell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="4fbdc-194">Acceso de lectura a los &quot;de dispositivos administrados&quot;de elementos de Intune.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-194">Read access to the &quot;Managed Devices&quot; elements of Intune.</span></span> <span data-ttu-id="4fbdc-195">(Operador de asistencia o superior o un rol personalizado)</span><span class="sxs-lookup"><span data-stu-id="4fbdc-195">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="4fbdc-196">En la actualidad, no hay una manera&quot; sencilla &quot;de activar un comando de automatización basado en el registro de un nuevo dispositivo dentro de Intune.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-196">At present, there is no &quot;simple&quot; way to trigger an automation command based on the enrolment of a new device within Intune.</span></span> <span data-ttu-id="4fbdc-197">Por lo tanto, este comando le proporcionará al técnico una forma sencilla de recuperar la dirección MAC sin tener que iniciar sesión en el portal y recuperarla de forma manual.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-197">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="4fbdc-198">Se devolverá el nombre y la dirección MAC de cualquier dispositivo HoloLens que haya sido inscrito en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-198">This will return the name and MAC address of any HoloLens devices which have been enrolled in the last 30 days.</span></span>

![Dirección MAC mediante PowerShell](images/mac-address-powershell.jpg)

### <a name="process"></a><span data-ttu-id="4fbdc-200">Proceso</span><span class="sxs-lookup"><span data-stu-id="4fbdc-200">Process</span></span>

<span data-ttu-id="4fbdc-201">Una vez que haya completado la inscripción en Intune, el técnico ejecutaría el script anterior para recuperar la dirección MAC.</span><span class="sxs-lookup"><span data-stu-id="4fbdc-201">After the Intune enrolment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
