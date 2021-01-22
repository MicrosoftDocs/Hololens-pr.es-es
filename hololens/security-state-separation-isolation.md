---
title: Separación y aislamiento de estado
description: Obtén información sobre la separación de estado, el aislamiento, la firma de código y las aplicaciones de Defender en tu dispositivo mixto de HoloLens 2.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: seguridad, hololens, separación de estado, separación y aislamiento de estado, hololens 2, seguridad de hololens2, información general sobre seguridad, arquitectura de seguridad, arquitectura, arquitectura de hololens 2
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 60d6d7c0e281395957ce9158144a5f3d60927682
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11282811"
---
# Separación y aislamiento de estado

La separación y el aislamiento de estado protege partes críticas del sistema operativo de HoloLens 2 de los cambios (como aquellas necesarias para que el sistema operativo arranque en un estado de confianza). Con la tecnología de aislamiento, las aplicaciones que no son de confianza se mueven a un entorno aislado para asegurar que no afecten a la seguridad del sistema.

## Separación de estado

La separación de estado en HoloLens 2 mejora considerablemente la seguridad y la capacidad de servicio (actualización) y le ayuda a proteger los datos de su aplicación.  Así funciona la separación de estado:
  * Core Operating System se almacena en el volumen de Core Operating System (un sistema operativo de Microsoft de confianza o verificado que actualiza el sistema operativo).
  * Las partes del sistema operativo que pueden modificarse en tiempo de ejecución (como controladores y configuraciones descargables) usan una separación de estado adicional para hacer una partición de los datos y almacenarlos en ubicaciones de almacenamiento independientes y seguras.
  * Cada ubicación de almacenamiento segura tiene distintas directivas de seguridad asociadas, lo que ofrece diversas ventajas de seguridad, como se detalla en la siguiente sección.

## Ventajas de la separación de estado

  * Seguridad: la separación de estado incluida en HoloLens 2 mejora considerablemente la integridad de la plataforma, la resistencia al software malintencionado y la protección de datos del usuario. Al separar la parte que no se puede modificar del sistema operativo y hacer que sea de solo lectura o que se proteja su integridad, la separación de estado hace que sea muy difícil que el software malintencionado se mantenga en un reinicio en frío. 
  * Actualizaciones: con HoloLens 2, una vez que el Core Operating System no se pueda modificar y se haya separado limpiamente del resto de los datos del dispositivo, las actualizaciones se vuelven simples y confiables.  Además, la separación de estado presenta el trabajo preliminar fundamental para las actualizaciones mucho más rápidas, lo que permite que el sistema operativo se reemplace en un único paso (unidad atómica).
  * Restablecimiento del dispositivo: el restablecimiento de HoloLens 2 borra los datos generados por el usuario y los datos de la aplicación del usuario en el dispositivo, incluidas las ubicaciones de almacenamiento interno y externo. Conserva las aplicaciones del sistema operativo actuales, las aplicaciones críticas de seguridad y las aplicaciones personalizadas de Microsoft y del fabricante de equipo original actuales (preinstaladas). Es posible rehidratar estas aplicaciones preinstaladas en el dispositivo después de que se complete el restablecimiento

### Estados de la separación de estado

La separación de estado garantiza que el sistema operativo solo pueda modificarse por componentes de dispositivo de confianza de Microsoft y solo se permite que el estado de gran valor se conserve durante los reinicios. Otro estado del sistema existe solo durante la duración de la sesión de inicio y se descarta después de que se reinicia. La separación de estado devuelva rápidamente el dispositivo al estado de fábrica. Los estados de Windows Holographic para empresas pueden dividirse en las siguientes categorías:
  * Core Operating System: estado no modificable
  * Datos del sistema operativo: estado modificable 
  * Datos del usuario: estado modificable

Cada uno de estos estados operativos de HoloLens 2 se describe en la siguiente sección.

#### Core Operating System

Un estado inmutable está formado por archivos y datos ejecutables que no se pueden modificar y que solo Microsoft puede modificar durante la instalación de las actualizaciones. Durante dicha actualización del Core Operating System, se habilita una nueva imagen que contiene el último estado de funcionamiento deseado.
El estado no modificable está marcado como de solo lectura (en caso contrario, se protege su integridad), lo que impide la persistencia de cualquier software malintencionado con privilegios elevados. Los siguientes archivos y datos ejecutables están protegidos en el estado inmutable:
  * Controladores de bandeja de entrada de Windows Holographic
  * Archivos binarios del sistema operativo
  * Controladores de bandeja de entrada de Windows
  * Configuración estática de Windows Holographic almacenada en el subárbol del registro de Windows (HKLM)
    * Ejemplo: HKLM almacena la información de configuración de las aplicaciones instaladas en un equipo. También almacena información para detectar el hardware y los controladores correspondientes.
Al protegerlos en el estado inmutable (con su integridad protegida y al ser de solo lectura), aseguramos que el Core Operating System siempre arranque en un estado de confianza. Además, cuando se restablece un dispositivo, podemos asegurarnos de que el dispositivo arranque solo en los componentes que se encuentran en esta sección inmutable. 

#### Datos del sistema operativo 

Es importante tener en cuenta que los archivos y los datos ejecutables que se pueden modificar en tiempo de ejecución (y no son fundamentales para la función del sistema operativo), se pueden descartar y volver a crear cuando los datos se dañan o están en peligro. El sistema operativo requiere funcionalmente que un estado modificable de alto valor persista, o se espera que este valor persista durante el apagado del sistema operativo y/o mientras un sistema operativo Windows compatible o escenarios de dispositivos lo reinician. Estos son ejemplos de estado mutable de alto valor:
  * Configuración de dispositivo global configurada por el administrador de tecnologías de la información (TI), tal como deshabilitar la ubicación para todos los usuarios.
  * La conexión de red Wi-Fi accede a las redes recordadas por los datos del dispositivo y a las contraseñas de conexión asociadas.
  * Volcados de memoria que incluyen configuraciones y registros.  
  * Controladores descargados a petición para dispositivos recientemente detectados.
Un estado modificable de alto valor en HoloLens 2 se encuentra en la ubicación de seguridad de los datos del sistema operativo, ya sea como un archivo guardado en disco o en un subárbol del registro persistente.

#### Datos del usuario

La última categoría de estado representa los datos del usuario producidos o guardados por las aplicaciones de la plataforma universal de Windows (UWP) o por el sistema operativo. Todas las carpetas de usuario conocidas (como descargas, documentos, vídeos, perfiles de usuario y HKEY_CURRENT_USER subárbol) también se almacenan en esta ubicación. Estos datos no se pueden extraer sin las credenciales adecuadas. Para obtener más información sobre cómo se protegen sus datos, vea [Cifrado y protección de datos](security-encryption-data-protection.md).

##  Aislamiento

Para lograr este equilibrio, HoloLens 2 tiene el Core Operating System que se usa para las funciones principales como el arranque, el control de hardware, el inicio de sesión, etc. Solo hay dos conjuntos de aplicaciones que se ejecutan en el Core Operating System: las aplicaciones preinstaladas y las aplicaciones de la UWP.

## Firma de código

El código de firma digital permite verificar que los archivos ejecutables y los scripts no se modificaron ya que fueron firmados por una fuente de confianza, lo que proporciona autenticidad e integridad. De manera predeterminada, las autoridades en las que confía HoloLens 2 son Microsoft y Microsoft Store. Los administradores de TI pueden agregar nuevos certificados al dispositivo a través de los CSP de [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) y [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp). También pueden usar la [directiva de AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) para confiar en aplicaciones transferidas localmente o en [aplicaciones de línea de negocio](https://docs.microsoft.com/intune/apps/lob-apps-windows) adicionales. Los certificados se encuentran en el almacén de certificados de la máquina local que se almacena en HKLM/root si usa "Dispositivo" o en HKCU si usa "Usuario".

## Protecciones de Defender
HoloLens 2 usa servicios de Microsoft para ofrecer a los usuarios un nivel avanzado de seguridad:

* El sistema operativo habilita automáticamente [SmartScreen Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) en Windows Holographic y protege frente a la suplantación de identidad (phishing) y el software malintencionado, así como frente a la descarga de archivos potencialmente malintencionados, en Microsoft Edge. El usuario no puede desactivar esta opción, pero se puede deshabilitar a través de la directiva.

* [El Firewall de Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) impide que el tráfico de red no autorizado fluya hasta el dispositivo y desde él. Está habilitado de manera predeterminada y el cliente no puede configurarla a través de las acciones locales o la directiva. 

* [El control de aplicaciones de Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview)(WDAC): HoloLens 2 es compatible con el WDAC que permite a los administradores de TI insertar las directivas de control de aplicaciones en el dispositivo. Puede encontrar más información en [Use WDAC en dispositivos HoloLens 2 con Intune MSFT](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens). 

Los administradores de TI pueden administrar el comportamiento de SmartScreen mediante [AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) y el comportamiento del explorador a través de [estas directivas](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2). 

