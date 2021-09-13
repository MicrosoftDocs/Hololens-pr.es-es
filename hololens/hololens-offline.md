---
title: Administración de los puntos de conexión para HoloLens
description: Aprenda a configurar HoloLens a través de una red Wi-Fi mientras administra y configura puntos de conexión.
keywords: hololens, fuera de línea, OOBE
audience: ITPro
ms.date: 07/01/2019
ms.assetid: b86f603c-d25f-409b-b055-4bbc6edcd301
author: Teresa-Motiv
ms.author: v-tea
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: jarrettr
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f2d9faafac2f84b727b1e10be83d4d1b53a707b4
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034658"
---
# <a name="manage-connection-endpoints-for-hololens"></a>Administración de los puntos de conexión para HoloLens

Algunos componentes de HoloLens, aplicaciones y servicios relacionados transfieren datos a los puntos de conexión de red de Microsoft. En este artículo se enumeran diferentes puntos de conexión y direcciones URL que deben permitirse en la configuración de la red (por ejemplo, proxy o firewall) para que esos componentes sean funcionales.    

## <a name="near-offline-setup"></a>Configuración casi sin conexión

HoloLens admite un conjunto limitado de experiencias sin conexión para los clientes que tienen restricciones en el entorno de red. Sin embargo, HoloLens necesita la conexión de red para pasar por la configuración inicial del dispositivo y las siguientes URL tienen que estar habilitadas:

| Propósito | URL |
|------|------|
| IDPS | https://sdx.microsoft.com/frx/idps |
| [NCSI](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services#bkmk-ncsi) |  http://www.msftconnecttest.com/connecttest.txt  |
| AADv9 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/9 |
| AADv10 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/10 |
| PIN de AAD | https://account.live.com/aadngc?uiflavor=win10&showSuccess=1 |
| MSA | https://login.live.com/ppsecure/inlineconnect.srf?id=80600 |
| PIN de MSA | https://account.live.com/msangc?fl=enroll |

## <a name="endpoint-configuration"></a>Configuración de punto de conexión

Además de la lista anterior, para aprovechar al máximo la funcionalidad de HoloLens, es necesario habilitar los siguientes puntos de conexión en la configuración de red.


| Propósito | URL |
|------|------|
| Azure                                               | wd-prod-fe.cloudapp.azure.com                                       |
|                                                     | ris-prod-atm.trafficmanager.net                                     |
|                                                     | validation-v2.sls.trafficmanager.net                                |
| Azure AD Multi-Factor Authentication                | https://secure.aadcdn.microsoftonline-p.com                         |
| Configuraciones de Intune y MDM                       | activation-v2.sls.microsoft.com/*                                   |
|                                                     | cdn.onenote.net                                                     |
|                                                     | client.wns.windows.com:443                                              |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ctldl.windowsupdate.com                                             |
|                                                     | displaycatalog.mp.microsoft.com                                    |
|                                                     | dm3p.wns.windows.com                                                |
|                                                     | *microsoft.com/pkiops/*                                             |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | r.manage.microsoft.com                                              |
|                                                     | tile-service.weather.microsoft.com                                  |
|                                                     | settings-win.data.microsoft.com                                     |
| Certificados                                        | activation-v2.sls.microsoft.com/*                                   |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | https://www.microsoft.com/pkiops/*                                          |
| Cortana y Búsqueda                                  | store-images.*microsoft.com                                         |
|                                                     | www.bing.com/client                                                 |
|                                                     | www.bing.com                                                        |
|                                                     | www.bing.com/proactive                                              |
|                                                     | www.bing.com/threshold/xls.aspx                                     |
|                                                     | exo-ring.msedge.net                                                 |
|                                                     | fp.msedge.net                                                       |
|                                                     | fp-vp.azureedge.net                                                 |
|                                                     | odinvzc.azureedge.net                                               |
|                                                     | spo-ring.msedge.net                                                 |
| Autenticación de dispositivos                               | login.live.com*                                                     |
| Metadatos del dispositivo                                     | dmd.metaservices.microsoft.com                                      |
| Ubicación                                            | inference.location.live.net                                         |
|                                                     | location-inference-westus.cloudapp.net                              |
| Datos de diagnóstico                                     | v10.events.data.microsoft.com                                       |
|                                                     | v10.vortex-win.data.microsoft.com/collect/v1                        |
|                                                     | https://www.microsoft.com                                                   |
|                                                     | co4.telecommand.telemetry.microsoft.com                             |
|                                                     | cs11.wpc.v0cdn.net                                                  |
|                                                     | cs1137.wpc.gammacdn.net                                             |
|                                                     | modern.watson.data.microsoft.com *                                   |
|                                                     | watson.telemetry.microsoft.com                                      |
| Licencias                                           | licensing.mp.microsoft.com                                          |
| Cuenta Microsoft                                   | login.msa.akadns6.net                                               |
|                                                     | us.configsvc1.live.com.akadns.net                                   |
| Microsoft Edge                                      | iecvlist.microsoft.com                                              |
| Servicio de redireccionamiento de vínculos hacia delante de Microsoft (FWLink) | go.microsoft.com                                                    |
| Microsoft Store                                     | *.wns.windows.com                                                   |
|                                                     | storecatalogrevocation.storequality.microsoft.com                   |
|                                                     | img-prod-cms-rt-microsoft-com*                                      |
|                                                     | store-images.microsoft.com                                          |
|                                                     | .md.mp.microsoft.com                                                |
|                                                     | displaycatalog.mp.microsoft.com                                    |
|                                                     | pti.store.microsoft.com                                             |
|                                                     | storeedgefd.dsx.mp.microsoft.com                                    |
|                                                     | markets.books.microsoft.com                                         |
|                                                     | share.microsoft.com                                                 |
| Indicador de estado de conexión de red (NCSI)          | www.msftconnecttest.com*                                            |
| Office                                              | *.c-msedge.net                                                      |
|                                                     | *.e-msedge.net                                                      |
|                                                     | *.s-msedge.net                                                      |
|                                                     | nexusrules.officeapps.live.com                                      |
|                                                     | ocos-office365-s2s.msedge.net                                       |
|                                                     | officeclient.microsoft.com                                          |
|                                                     | outlook.office365.com                                               |
|                                                     | client-office365-tas.msedge.net                                     |
|                                                     | https://www.office.com                                                      |
|                                                     | onecollector.cloudapp.aria                                          |
|                                                     | v10.events.data.microsoft.com/onecollector/1.0/                     |
|                                                     | self.events.data.microsoft.com                                      |
|                                                     | to-do.microsoft.com                                                 |
| OneDrive                                            | g.live.com/1rewlive5skydrive/*                                      |
|                                                     | msagfx.live.com                                                     |
|                                                     | oneclient.sfx.ms                                                    |
| Aplicación Fotos                                          | evoke-windowsservices-tas.msedge.net                                |
| Configuración                                            | cy2.settings.data.microsoft.com.akadns.net                          |
|                                                     | settings.data.microsoft.com                                         |
|                                                     | settings-win.data.microsoft.com                                     |
| Windows Defender                                    | wdcp.microsoft.com                                                  |
|                                                     | definitionupdates.microsoft.com                                     |
|                                                     | go.microsoft.com                                                    |
|                                                     | *smartscreen.microsoft.com                                          |
|                                                     | smartscreen-sn3p.smartscreen.microsoft.com                          |
|                                                     | unitedstates.smartscreen-prod.microsoft.com                         |
| Contenido destacado de Windows                                   | *. search.msn.com                                                    |
|                                                     | arc.msn.com                                                         |
|                                                     | g.msn.com*                                                          |
|                                                     | query.prod.cms.rt.microsoft.com                                     |
|                                                     | ris.api.iris.microsoft.com                                          |
| Windows Update                                      | *.prod.do.dsp.mp.microsoft.com                                      |
|                                                     | cs9.wac.phicdn.net                                                  |
|                                                     | emdl.ws.microsoft.com                                               |
|                                                     | *.dl.delivery.mp.microsoft.com                                      |
|                                                     | *.windowsupdate.com                                                 |
|                                                     | *.delivery.mp.microsoft.com                                         |
|                                                     | *.update.microsoft.com                                              |



## <a name="references"></a>Referencias

> [!NOTE]
> Si va a implementar D365 Remote Assist, tendrá que habilitar los puntos de conexión enumerados para SharePoint Online y OneDrive para la Empresa en [direcciones URL de Office 365 e intervalos de direcciones IP](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

- [Configurar los datos de diagnóstico de Windows en la organización](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)
- [Administrar puntos de conexión para Windows 10 Enterprise, versión 1903](/windows/privacy/manage-windows-1903-endpoints)
- [Administrar las conexiones de los componentes del sistema operativo Windows 10 a servicios Microsoft](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services)
- [Administrar las conexiones de los componentes del sistema operativo Windows 10 a los servicios Microsoft mediante el servidor MDM de Microsoft Intune](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services-using-mdm)
- [Ancho de banda y requisitos de configuración de red de Intune](/intune/fundamentals/network-bandwidth-use#network-communication-requirements)
- [Puntos de conexión de red de Microsoft Intune](/intune/fundamentals/intune-endpoints)
- [Intervalos de direcciones IP y URL de Office 365](/office365/enterprise/urls-and-ip-address-ranges)
- [Requisitos previos de Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)


## <a name="hololens-limitations"></a>Limitaciones de HoloLens

Una vez configurado el dispositivo HoloLens, puede usarlo sin una conexión Wi-Fi, pero las aplicaciones que usan conexiones a Internet tendrán capacidades limitadas cuando use HoloLens sin conexión.
