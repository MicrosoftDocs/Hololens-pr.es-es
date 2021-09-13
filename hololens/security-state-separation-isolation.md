---
title: Separación y aislamiento de estado
description: Obtenga información sobre la separación de estado, el aislamiento, la firma de código y las aplicaciones de Defender en su dispositivo de realidad mixta HoloLens 2.
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
ms.openlocfilehash: 0487ea49c706c753f4dfca7da7daa499d1715e9f
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034701"
---
# <a name="state-separation-and-isolation"></a>Separación y aislamiento de estado

La separación y el aislamiento de estado protegen partes críticas del sistema operativo de HoloLens 2 de cambios (como las necesarias para que el sistema operativo arranque en un estado de confianza). Con la tecnología de aislamiento, las aplicaciones que no son de confianza se mueven a un entorno de espacio aislado para garantizar que no afecten a la seguridad del sistema.

## <a name="state-separation"></a>Separación de estado

La separación de estado en HoloLens 2 mejora considerablemente la seguridad y la capacidad de servicio (actualización) y le ayuda a proteger los datos de la aplicación.  La separación de estado funciona de la siguiente manera:
  * El sistema operativo principal se almacena en el volumen Core Operating System (un sistema operativo de Microsoft de confianza o verificado que actualiza el sistema operativo).
  * Las partes del sistema operativo que pueden modificarse en tiempo de ejecución (como controladores y configuraciones descargables) usan una separación de estado adicional para realizar una partición de los datos y almacenarlos en ubicaciones de almacenamiento independientes y seguras.
  * Cada ubicación de almacenamiento segura tiene distintas directivas de seguridad asociadas, lo que ofrece diversas ventajas de seguridad, como se detalla en la siguiente sección.

## <a name="state-separation-benefits"></a>Ventajas de la separación de estado

  * Seguridad: la separación de estado incluida en HoloLens 2 mejora considerablemente la integridad de la plataforma, la resistencia al software malintencionado y la protección de datos del usuario. Al separar la parte que no se puede modificar del sistema operativo y hacer que sea de solo lectura o proteger su integridad, la separación de estado dificulta enormemente que el software malintencionado se mantenga en un reinicio en frío. 
  * Actualizaciones: con HoloLens 2, una vez que el sistema operativo principal no se puede modificar y se ha separado de forma limpia del resto de los datos del dispositivo, las actualizaciones se vuelven simples y confiables.  Además, la separación de estado presenta el trabajo preliminar fundamental para actualizaciones mucho más rápidas, lo que permite que el sistema operativo se reemplace en un único paso (unidad atómica).
  * Restablecimiento del dispositivo: el restablecimiento de HoloLens 2 borra los datos generados por el usuario y los datos de la aplicación del usuario en el dispositivo, incluidas las ubicaciones de almacenamiento interno y externo. Conserva las aplicaciones del sistema operativo actuales, las aplicaciones críticas de seguridad y las aplicaciones personalizadas de Microsoft y del OEM actuales (preinstaladas). Es posible rehidratar estas aplicaciones preinstaladas en el dispositivo después de que se complete el restablecimiento.

### <a name="state-separation-states"></a>Estados de la separación de estado

La separación de estado garantiza que el sistema operativo solo pueda modificarse a través de componentes de dispositivo de confianza de Microsoft y solo se permite que el estado de alto valor se conserve durante los reinicios. Existe otro estado del sistema solo durante la sesión de inicio, que se descarta después de un reinicio. La separación de estado devuelve rápidamente el dispositivo al estado de fábrica. Los estados de Windows Holographic for Business pueden dividirse en las siguientes categorías:
  * Sistema operativo principal: estado no modificable
  * Datos del sistema operativo: estado modificable 
  * Datos del usuario: estado modificable

Cada uno de estos estados operativos de HoloLens 2 se describe en la siguiente sección.

#### <a name="core-operating-system"></a>Sistema operativo principal

Un estado inmutable está formado por datos y archivos ejecutables que no se pueden modificar y que solo Microsoft puede alterar durante la instalación de las actualizaciones. Durante una de estas actualizaciones del sistema operativo principal, se habilita una nueva imagen que contiene el último estado de funcionamiento deseado.
El estado no modificable está marcado como de solo lectura (en caso contrario, se protege su integridad), lo que impide la persistencia de cualquier software malintencionado con privilegios elevados. Los siguientes datos y archivos ejecutables están protegidos en el estado inmutable:
  * Controladores de bandeja de entrada de Windows Holographic
  * Archivos binarios del sistema operativo
  * Controladores de bandeja de entrada de Windows
  * Configuración estática de Windows Holographic almacenada en el subárbol del registro de Windows (HKLM)
    * Ejemplo: HKLM almacena la información de configuración de las aplicaciones instaladas en una máquina. También almacena información para detectar el hardware y los controladores correspondientes.
Al protegerlos en el estado inmutable (de solo lectura y con la integridad protegida), garantizamos que el sistema operativo principal siempre arranque en un estado de confianza. Además, cuando se restablece un dispositivo, podemos asegurarnos de que este arranque solo en los componentes que se encuentran en esta sección inmutable. 

#### <a name="operating-system-data"></a>Datos del sistema operativo 

Es importante tener en cuenta que los archivos y los datos ejecutables que se pueden modificar en tiempo de ejecución (y no son fundamentales para la función del sistema operativo), se pueden descartar y volver a crear cuando los datos se dañan o están en peligro. Desde el punto de vista funcional, es necesario que el sistema operativo conserve un estado modificable de alto valor, o que dicho estado persista al apagar el sistema operativo o entre reinicios del sistema operativo Windows compatible o los escenarios de dispositivos. Los siguientes son ejemplos de estado mutable de alto valor:
  * Configuración de dispositivo global configurada por el administrador de TI, como deshabilitar la ubicación para todos los usuarios.
  * La conexión de red Wi-Fi accede a las redes recordadas por los datos del dispositivo y a las contraseñas de conexión asociadas.
  * Volcados de memoria que incluyen configuraciones y registros.
  * Controladores descargados a petición para dispositivos detectados recientemente.
Un estado modificable de alto valor en HoloLens 2 se encuentra en la ubicación de seguridad de datos del sistema operativo, ya sea como un archivo guardado en el disco o en un subárbol del registro persistente.

#### <a name="user-data"></a>Datos de usuario

La última categoría de estado representa los datos del usuario que producidos o conservados por las aplicaciones para UWP o el sistema operativo. Todas las carpetas de usuario conocidas como Descargas, Documentos, Vídeos, perfiles de usuario y el subárbol HKEY_CURRENT_USER también se almacenan en esta ubicación. Estos datos no se pueden extraer sin las credenciales adecuadas. Para obtener más información sobre cómo se protegen sus datos, vea [Cifrado y protección de datos](security-encryption-data-protection.md).

##  <a name="isolation"></a>Aislamiento

Para lograr este equilibrio, HoloLens 2 tiene el sistema operativo principal que se usa para las funciones principales, como el arranque, el control de hardware, el inicio de sesión, etc. Solo hay dos conjuntos de aplicaciones que se ejecutan en el sistema operativo principal: las aplicaciones preinstaladas y las aplicaciones para UWP.

## <a name="code-signing"></a>Firma de código

La firma digital de código permite verificar que los archivos ejecutables y los scripts no se modificaron desde que los firmó una fuente de confianza, lo que proporciona autenticidad e integridad. De manera predeterminada, las autoridades en las que confía HoloLens 2 son Microsoft y Microsoft Store. Los administradores de TI pueden agregar nuevos certificados al dispositivo a través de los CSP [ClientCertificateInstall](/windows/client-management/mdm/clientcertificateinstall-csp) y [RootCATrustedCertificates](/windows/client-management/mdm/rootcacertificates-csp). También pueden usar la [directiva AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) para confiar en [aplicaciones de línea de negocio](/intune/apps/lob-apps-windows) o con instalación de prueba adicionales. Los certificados se encuentran en el almacén de certificados de la máquina local en HKLM/root si usa "Dispositivo" o HKCU si utiliza "Usuario".

## <a name="defender-protections"></a>Protecciones de Defender
HoloLens 2 usa servicios de Microsoft para ofrecer a los usuarios un nivel avanzado de seguridad:

* [Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) se habilita automáticamente con el sistema operativo en Windows Holographic y protege frente a la suplantación de identidad (phishing) y el software malintencionado, así como frente a la descarga de archivos potencialmente malintencionados, en Edge. El usuario no puede desactivar esta opción, pero se puede deshabilitar a través de la directiva.

* [Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) impide que el tráfico de red no autorizado fluya hacia y desde el dispositivo. Está habilitado de manera predeterminada y el cliente no puede configurarlo a través de acciones locales ni de la directiva. 

* [Control de aplicaciones de Windows Defender](/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview): HoloLens 2 admite WDAC, que permite al administrador de TI insertar directivas de control de aplicaciones en el dispositivo. Puede encontrar más información en [Uso de WDAC en dispositivos HoloLens 2 con MSFT Intune](/mem/intune/configuration/custom-profile-hololens). 

Los administradores de TI pueden administrar el comportamiento de SmartScreen a través de [AllowSmartScreen](/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) y el comportamiento del explorador a través de [estas directivas](/windows/client-management/mdm/policy-csps-supported-by-hololens2). 

