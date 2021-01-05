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
ms.openlocfilehash: 3e06540dd7dca8892cd69abaf9a318d46ca0f3f2
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253147"
---
# <span data-ttu-id="0e39b-103">Inscripción para la empresa de dispositivos HoloLens en un entorno Wi-Fi restringido de direcciones MAC</span><span class="sxs-lookup"><span data-stu-id="0e39b-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="0e39b-104">Este documento describirá un escenario común que hemos identificado dentro de los entornos de clientes en los que la Wi-Fi está restringida por direcciones MAC, o bien se requiere los certificados para unirse a las redes inalámbricas.</span><span class="sxs-lookup"><span data-stu-id="0e39b-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <span data-ttu-id="0e39b-105">Ejemplo de escenario</span><span class="sxs-lookup"><span data-stu-id="0e39b-105">Example Scenario</span></span>

<span data-ttu-id="0e39b-106">Un gran número de clientes en entornos seguros tienen restricciones en sus redes inalámbricas o alámbricas que solo permitirán que los dispositivos aprobados (basados en direcciones MAC) se conecten correctamente (ya sea con filtrado de direcciones MAC en un punto de acceso inalámbrico o en un servidor DHCP).</span><span class="sxs-lookup"><span data-stu-id="0e39b-106">Many customers in secure environments have restrictions on their Wireless or wired networks, which will only allow approved devices (based on MAC Addresses) to connect successfully (either with MAC Address filtering on a Wireless Access Point or on a DHCP server).</span></span> <span data-ttu-id="0e39b-107">Además, algunas redes inalámbricas se pueden proteger con PEAP, lo que requiere que se aplique un certificado al dispositivo antes de poder autenticar correctamente la red inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="0e39b-107">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate is applied to the device prior to being able to successfully authenticate the Wireless network.</span></span>

<span data-ttu-id="0e39b-108">Para los dispositivos HoloLens pueden surgir dos problemas clave, que pueden ocasionar retrasos y trabajo manual al unirse de los dispositivos HoloLens a la red.</span><span class="sxs-lookup"><span data-stu-id="0e39b-108">Two key issues can arise with HoloLens devices, which can cause delays and manual work in joining the HoloLens Devices to the network.</span></span>

- <span data-ttu-id="0e39b-109">El certificado inalámbrico PEAP debe aplicarse al dispositivo antes de que el dispositivo haya sido incorporado correctamente a la red inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="0e39b-109">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="0e39b-110">Debe registrarse la dirección MAC del adaptador Wi-Fi de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0e39b-110">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="0e39b-111">Los principales desafíos son:</span><span class="sxs-lookup"><span data-stu-id="0e39b-111">The key challenges to this are:</span></span>

1. <span data-ttu-id="0e39b-112">Actualmente, la dirección MAC solo puede ser identificada desde la aplicación Configuración del dispositivo, o bien desde Intune después de una inscripción completa de Intune.</span><span class="sxs-lookup"><span data-stu-id="0e39b-112">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful Intune enrollment.</span></span>
2. <span data-ttu-id="0e39b-113">Sin la dirección MAC, el dispositivo no puede unirse a la red Wi-Fi para comenzar la inscripción.</span><span class="sxs-lookup"><span data-stu-id="0e39b-113">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>
3. <span data-ttu-id="0e39b-114">Las soluciones manuales a estos desafíos necesitan de la participación de los técnicos en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0e39b-114">Manual Solutions to these challenges require technician involvement with the devices.</span></span>

## <span data-ttu-id="0e39b-115">Soluciones</span><span class="sxs-lookup"><span data-stu-id="0e39b-115">Solutions</span></span>

<span data-ttu-id="0e39b-116">Existen muchas maneras de mejorar esta situación, en función de la infraestructura disponible en el entorno.</span><span class="sxs-lookup"><span data-stu-id="0e39b-116">There are many ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="0e39b-117">Solución</span><span class="sxs-lookup"><span data-stu-id="0e39b-117">Solution</span></span> | <span data-ttu-id="0e39b-118">Ventajas</span><span class="sxs-lookup"><span data-stu-id="0e39b-118">Benefits</span></span> | <span data-ttu-id="0e39b-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e39b-119">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="0e39b-120">Paquete de aprovisionamiento con adaptador Ethernet</span><span class="sxs-lookup"><span data-stu-id="0e39b-120">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="0e39b-121">Mejora la experiencia de OOBE y permite obtener una experiencia más rápida en lo técnico.</span><span class="sxs-lookup"><span data-stu-id="0e39b-121">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="0e39b-122">Las HubTechnician USB compatibles con HoloLens aún deberán interactuar con el dispositivo para la captura del MAC y la finalización del OOBE.</span><span class="sxs-lookup"><span data-stu-id="0e39b-122">HoloLens compatible USB C HubTechnician will still need to interact with the device for MAC Capture and OOBE finalization</span></span> |
| <span data-ttu-id="0e39b-123">Piloto automático con registro de Intune por Ethernet</span><span class="sxs-lookup"><span data-stu-id="0e39b-123">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="0e39b-124">La conexión y el registro del dispositivo en el entorno del cliente en un solo paso puede completarse sin interactuar con el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0e39b-124">Single Step connection and registration of the device to the customer environmentMAC capture can be completed without interacting with the device</span></span> | <span data-ttu-id="0e39b-125">Intune habilitado para el adaptador de red compatible con TenantHoloLens USB-C compatible con el cliente Azure AD</span><span class="sxs-lookup"><span data-stu-id="0e39b-125">Intune enabled for the customer Azure AD TenantHoloLens Compatible USB-C network adaptor</span></span> |
| <span data-ttu-id="0e39b-126">Información automatizada de las direcciones MAC</span><span class="sxs-lookup"><span data-stu-id="0e39b-126">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="0e39b-127">Una vez que los dispositivos hayan sido registrados en el espacio empresarial de Intune, escriba el reporte de la dirección MAC al técnico.</span><span class="sxs-lookup"><span data-stu-id="0e39b-127">When devices have been registered within the Intune Tenant, Script the reporting of the MAC address to the technician.</span></span> | <span data-ttu-id="0e39b-128">Commandlets de Intune PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e39b-128">Intune PowerShell Commandlets</span></span> |

## <span data-ttu-id="0e39b-129">Paquete de aprovisionamiento con adaptador Ethernet</span><span class="sxs-lookup"><span data-stu-id="0e39b-129">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="0e39b-130">Si la red cableada también está sujeta a restricciones de MAC, entonces la dirección MAC del adaptador Ethernet USB-C / Hub deberá ser aprobada previamente.</span><span class="sxs-lookup"><span data-stu-id="0e39b-130">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Ethernet adaptor / Hub will need to be pre-approved.</span></span> <span data-ttu-id="0e39b-131">Se debe tener cuidado con este concentrador ya que permitirá el acceso a la red desde otros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0e39b-131">Care should be taken with this hub as it will allow access to the network from other devices.</span></span>

### <span data-ttu-id="0e39b-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e39b-132">Requirements</span></span>

- <span data-ttu-id="0e39b-133">Puerto de red conectado con acceso a la red del cliente</span><span class="sxs-lookup"><span data-stu-id="0e39b-133">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="0e39b-134">Contenedor USB-C compatible con HoloLens que contiene un adaptador Ethernet: cualquier concentrador que no &#39; requiera que se instalen controladores adicionales o instalaciones de aplicaciones debe ser apropiado.</span><span class="sxs-lookup"><span data-stu-id="0e39b-134">HoloLens Compatible USB-C Hub containing an Ethernet adaptor – Any hub that doesn&#39;t require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="0e39b-135">Paquete de aprovisionamiento que contiene lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0e39b-135">Provisioning Package containing:</span></span>
  - <span data-ttu-id="0e39b-136">Contiene información de red inalámbrica y un certificado</span><span class="sxs-lookup"><span data-stu-id="0e39b-136">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="0e39b-137">Puede contener información de inscripción para Azure AD de la organización.</span><span class="sxs-lookup"><span data-stu-id="0e39b-137">Optionally containing enrollment information for the Organization&#39;s Azure AD</span></span>
  - <span data-ttu-id="0e39b-138">Contiene otras opciones de configuración de aprovisionamiento necesarias</span><span class="sxs-lookup"><span data-stu-id="0e39b-138">Containing any other required provisioning settings</span></span>

### <span data-ttu-id="0e39b-139">Proceso</span><span class="sxs-lookup"><span data-stu-id="0e39b-139">Process</span></span>

<span data-ttu-id="0e39b-140">El proceso puede variar según el nivel de software del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0e39b-140">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="0e39b-141">Si el dispositivo tiene la[actualización de mayo de 2004](hololens-release-notes.md#windows-holographic-version-2004), siga los pasos que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="0e39b-141">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="0e39b-142">Coloque el paquete de aprovisionamiento en la raíz de una memoria USB, y conéctelo al concentrador.</span><span class="sxs-lookup"><span data-stu-id="0e39b-142">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="0e39b-143">Conecte el cable de Ethernet al concentrador.</span><span class="sxs-lookup"><span data-stu-id="0e39b-143">Connect Ethernet cable to the hub.</span></span>
3. <span data-ttu-id="0e39b-144">Conecte el concentrador USB-C al dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0e39b-144">Connect USB-C hub to HoloLens device.</span></span>
4. <span data-ttu-id="0e39b-145">Active el dispositivo HoloLens y lleve el uso del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0e39b-145">Turn on HoloLens Device and wear the device.</span></span>
5. <span data-ttu-id="0e39b-146">Pulse el **botón de bajar volumen y encender** para aplicar el paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="0e39b-146">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="0e39b-147">El técnico ya puede seguir OOBE y, una vez completada, abra la aplicación configuración y recupere la dirección MAC del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0e39b-147">The technician can now follow OOBE, and when complete, open the Settings App, and retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="0e39b-148">Si el dispositivo tiene una compilación de sistema operativo antes de la [Actualización de mayo de 2004](hololens-release-notes.md#windows-holographic-version-2004), siga los siguientes pasos que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="0e39b-148">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="0e39b-149">Active el dispositivo HoloLens y conéctelo a un equipo.</span><span class="sxs-lookup"><span data-stu-id="0e39b-149">Turn on the HoloLens Device, and plug the device into a PC.</span></span>
2. <span data-ttu-id="0e39b-150">El dispositivo debe aparecer en el equipo como un dispositivo de almacenamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="0e39b-150">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="0e39b-151">Copie el paquete de aprovisionamiento al dispositivo</span><span class="sxs-lookup"><span data-stu-id="0e39b-151">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="0e39b-152">Conecte el cable de Ethernet al concentrador.</span><span class="sxs-lookup"><span data-stu-id="0e39b-152">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="0e39b-153">Conecte el concentrador USB-C al dispositivo HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0e39b-153">Connect USB-C hub to HoloLens device.</span></span>
6. <span data-ttu-id="0e39b-154">Use el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0e39b-154">Wear the device.</span></span>
7. <span data-ttu-id="0e39b-155">Pulse el botón de **Bajar volumen y encender** para aplicar el paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="0e39b-155">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="0e39b-156">El técnico ya puede seguir OOBE y, una vez completada, abra la aplicación configuración y recupere la dirección MAC del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0e39b-156">The technician can now follow OOBE, and when complete, open the Settings App, and retrieve the MAC Address of the device.</span></span>

### <span data-ttu-id="0e39b-157">Ventajas</span><span class="sxs-lookup"><span data-stu-id="0e39b-157">Benefits</span></span>

<span data-ttu-id="0e39b-158">De esta forma, con un &quot;simple toque &quot;del dispositivo, se puede aplicar el paquete de aprovisionamiento correcto y recoger la dirección MAC del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0e39b-158">This will allow a &quot;Single touch&quot; of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="0e39b-159">Los paquetes de aprovisionamiento se pueden ser creados siguiendo las instrucciones aquí.</span><span class="sxs-lookup"><span data-stu-id="0e39b-159">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <span data-ttu-id="0e39b-160">Autopiloto con inscripción de Intune</span><span class="sxs-lookup"><span data-stu-id="0e39b-160">Autopilot with Intune Enrollment</span></span>

### <span data-ttu-id="0e39b-161">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e39b-161">Requirements</span></span>

- <span data-ttu-id="0e39b-162">Puerto de red conectado con acceso a la red del cliente</span><span class="sxs-lookup"><span data-stu-id="0e39b-162">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="0e39b-163">Dispositivos HoloLens que ejecutan Windows Holographic 2004</span><span class="sxs-lookup"><span data-stu-id="0e39b-163">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="0e39b-164">Concentrador USB-C compatible con HoloLens</span><span class="sxs-lookup"><span data-stu-id="0e39b-164">HoloLens Compatible USB-C Hub</span></span>
- <span data-ttu-id="0e39b-165">Configuración y habilitación de Intune para el espacio empresarial de cliente</span><span class="sxs-lookup"><span data-stu-id="0e39b-165">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="0e39b-166">Dispositivo registrado para el piloto automático e importado en el espacio empresarial del cliente</span><span class="sxs-lookup"><span data-stu-id="0e39b-166">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="0e39b-167">Directivas de Intune definidas para el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="0e39b-167">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="0e39b-168">Contiene información de red inalámbrica y un certificado</span><span class="sxs-lookup"><span data-stu-id="0e39b-168">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="0e39b-169">Contiene otras opciones de configuración de aprovisionamiento necesarias</span><span class="sxs-lookup"><span data-stu-id="0e39b-169">Containing any other required provisioning settings</span></span>

<span data-ttu-id="0e39b-170">Esto permitirá a un cliente con requisitos de red avanzados inscribir los dispositivos en un enfoque sin contacto y escalable</span><span class="sxs-lookup"><span data-stu-id="0e39b-170">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="0e39b-171">Los requisitos previos adicionales serán necesarios como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="0e39b-171">Additional pre-requisites will be needed as below:</span></span>
1. [<span data-ttu-id="0e39b-172">Habilitar el espacio empresarial en la versión preliminar del piloto automático</span><span class="sxs-lookup"><span data-stu-id="0e39b-172">Enable the Tenant for the Autopilot preview</span></span>](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. <span data-ttu-id="0e39b-173">Crear las directivas de HoloLens para reemplazar el paquete de aprovisionamiento en Intune.</span><span class="sxs-lookup"><span data-stu-id="0e39b-173">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="0e39b-174">Crear las directivas de HoloLens Intune.</span><span class="sxs-lookup"><span data-stu-id="0e39b-174">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="0e39b-175">Asignar los dispositivos al grupo correcto.</span><span class="sxs-lookup"><span data-stu-id="0e39b-175">Assign the devices to the correct group.</span></span>

### <span data-ttu-id="0e39b-176">Proceso</span><span class="sxs-lookup"><span data-stu-id="0e39b-176">Process</span></span>

1. <span data-ttu-id="0e39b-177">Conecte el concentrador USB-C y el cable Ethernet al dispositivo HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="0e39b-177">Plug the USB-C hub and ethernet cable into the HoloLens 2 device.</span></span>
2. <span data-ttu-id="0e39b-178">Active el HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="0e39b-178">Turn on the HoloLens 2.</span></span>
3. <span data-ttu-id="0e39b-179">El dispositivo debe conectarse automáticamente a Internet en OOBE mediante el adaptador Ethernet, detectar la configuración del piloto automático y registrarse automáticamente con Azure AD e Intune</span><span class="sxs-lookup"><span data-stu-id="0e39b-179">The device should automatically connect to the internet at OOBE via the Ethernet adaptor, detect the Autopilot configuration, and automatically register with Azure AD and Intune</span></span>
4. <span data-ttu-id="0e39b-180">El dispositivo aplicará los certificados Wi-Fi necesarios y otras opciones de configuración que sean necesarios mediante Intune.</span><span class="sxs-lookup"><span data-stu-id="0e39b-180">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune</span></span>
5. <span data-ttu-id="0e39b-181">Una vez finalizado, el técnico podrá cargar el portal de Intune (Endpoint Manager) y profundizar en la página de propiedades del dispositivo, en **> de dispositivos de Inicio-> el > de hardware**</span><span class="sxs-lookup"><span data-stu-id="0e39b-181">When complete, the technician will be able to load the Intune (Endpoint Manager) Portal, and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**</span></span>
6. <span data-ttu-id="0e39b-182">La dirección de MAC WiFi estará visible en el portal de Intune.</span><span class="sxs-lookup"><span data-stu-id="0e39b-182">The Wi-Fi MAC address will be visible within the Intune Portal</span></span>

![Dirección MAC a través de Intune](images/mac-address-intune.jpg)

7. <span data-ttu-id="0e39b-184">El técnico agregará esta dirección MAC como dispositivo permitido.</span><span class="sxs-lookup"><span data-stu-id="0e39b-184">The technician will add this MAC address as an allowed device.</span></span>

### <span data-ttu-id="0e39b-185">Ventajas</span><span class="sxs-lookup"><span data-stu-id="0e39b-185">Benefits</span></span>

<span data-ttu-id="0e39b-186">Esto permitirá una experiencia de implementación &quot;sin contacto&quot; para el técnico, en la que el dispositivo pueda inscribirse directamente en Azure AD e Intune sin que el técnico tenga que llevar el dispositivo o interactuar manualmente con el entorno del HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0e39b-186">This will allow a &quot;Heads off&quot; deployment experience for the Technician, with the device being able to go from the box to enrolled in Azure AD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <span data-ttu-id="0e39b-187">Informar de las direcciones MAC al técnico</span><span class="sxs-lookup"><span data-stu-id="0e39b-187">Reporting of MAC addresses to the Technician</span></span>

### <span data-ttu-id="0e39b-188">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e39b-188">Requirements</span></span>

- <span data-ttu-id="0e39b-189">Autorización de &quot;Intune Graph Powershell&quot; en el espacio empresarial del cliente</span><span class="sxs-lookup"><span data-stu-id="0e39b-189">Authorization of the &quot;Intune Graph PowerShell&quot; against the customer Tenant</span></span>
- <span data-ttu-id="0e39b-190">Instalación de Intune Graph Powershell en el equipo del técnico.</span><span class="sxs-lookup"><span data-stu-id="0e39b-190">Installation of the Intune Graph PowerShell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="0e39b-191">Acceso de lectura a los &quot;de dispositivos administrados&quot;de elementos de Intune.</span><span class="sxs-lookup"><span data-stu-id="0e39b-191">Read access to the &quot;Managed Devices&quot; elements of Intune.</span></span> <span data-ttu-id="0e39b-192">(Operador de asistencia o superior o un rol personalizado)</span><span class="sxs-lookup"><span data-stu-id="0e39b-192">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="0e39b-193">En la actualidad, no hay una manera&quot; sencilla &quot;de activar un comando de automatización basado en el registro de un nuevo dispositivo dentro de Intune.</span><span class="sxs-lookup"><span data-stu-id="0e39b-193">At present, there is no &quot;simple&quot; way to trigger an automation command based on the enrolment of a new device within Intune.</span></span> <span data-ttu-id="0e39b-194">Por lo tanto, este comando le proporcionará al técnico una forma sencilla de recuperar la dirección MAC sin tener que iniciar sesión en el portal y recuperarla de forma manual.</span><span class="sxs-lookup"><span data-stu-id="0e39b-194">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="0e39b-195">Se devolverá el nombre y la dirección MAC de cualquier dispositivo HoloLens que haya sido inscrito en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="0e39b-195">This will return the name and MAC address of any HoloLens devices which have been enrolled in the last 30 days.</span></span>

![Dirección MAC mediante PowerShell](images/mac-address-powershell.jpg)

### <span data-ttu-id="0e39b-197">Proceso</span><span class="sxs-lookup"><span data-stu-id="0e39b-197">Process</span></span>

<span data-ttu-id="0e39b-198">Una vez que haya completado la inscripción en Intune, el técnico ejecutaría el script anterior para recuperar la dirección MAC.</span><span class="sxs-lookup"><span data-stu-id="0e39b-198">After the Intune enrolment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
