---
title: Recopilar y usar información de diagnóstico de dispositivos HoloLens
description: ''
author: Teresa-Motiv
ms.author: v-tea
ms.date: 03/23/2020
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
ms.custom:
- CI 115131
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f11128c66845f0e062a006855fd75ca66ffc4e5e
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829603"
---
# Recopilar y usar información de diagnóstico de dispositivos HoloLens

Los usuarios y administradores de HoloLens pueden elegir entre cuatro métodos diferentes para recopilar información de diagnóstico de HoloLens:

- Aplicación del centro de opiniones
- DiagnosticLog CSP
- Aplicación Configuración

> [!IMPORTANT]  
> Los registros de diagnóstico de dispositivos contienen información de identificación personal (PII), como acerca de qué procesos o aplicaciones comienza el usuario durante las operaciones típicas. Cuando varios usuarios comparten un dispositivo HoloLens (por ejemplo, los usuarios inician sesión en el mismo dispositivo con diferentes cuentas de Microsoft Azure Active Directory (AAD)), los registros de diagnóstico pueden contener información PII que se aplica a varios usuarios. Para obtener más información, consulta la [declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement).

En la siguiente tabla se comparan los tres métodos de colección. Los nombres de métodos establecen un vínculo a información más detallada en las secciones siguientes de la tabla.

|Método |Requisitos previos |Ubicaciones de datos |Acceso y uso de datos |Retención de datos |
| --- | --- | --- | --- | --- |
|[Centro de opiniones](#feedback-hub) |Conexión a Internet y a la red<br /><br />Aplicación del centro de opiniones<br /><br />Permiso para cargar archivos en la nube de Microsoft |Microsoft Cloud<br /><br />Dispositivo HoloLens (opcional) |El usuario solicita asistencia, acepta las condiciones de uso y carga los datos<br /><br />Los empleados de Microsoft ven los datos de acuerdo con las condiciones de uso |Los datos de la nube se conservan para el período definido por la siguiente generación de privacidad (NGP). A continuación, los datos se eliminan automáticamente.<br /><br />Los datos en el dispositivo se pueden eliminar en cualquier momento por un usuario que tenga permisos de **Administrador** o **propietario del dispositivo** . |
|[Solucionador de problemas de configuración](#settings-troubleshooter) |Aplicación Configuración |Dispositivo HoloLens<br /><br />Equipo conectado (opcional) |El usuario almacena los datos y solo el usuario tiene acceso a los datos (a menos que el usuario comparta específicamente los datos con otro usuario). |Los datos se conservan hasta que el usuario lo elimina. * |
|[DiagnosticLog CSP](#diagnosticlog-csp) |Conexión de red<br /><br />Entorno MDM que admite el CSP DiagnosticLog |El administrador configura las ubicaciones de almacenamiento |En el entorno administrado, el usuario reenvía implícitamente a los datos el acceso de administrador.<br /><br />El administrador configura los roles y permisos de Access. | El administrador configura la Directiva de retención. |


-   El usuario final es responsable de compartir los registros de forma responsable con otra persona. Estos archivos son útiles principalmente para ponerse en contacto con el servicio de asistencia al cliente.  

## Centro de opiniones

Un usuario de HoloLens puede usar la aplicación de escritorio del Hub de comentarios de Microsoft para enviar información de diagnóstico al soporte técnico de Microsoft. Para obtener más información y obtener instrucciones completas, vea enviar [comentarios](hololens-feedback.md).  

> [!NOTE]  
> **Usuarios de empresas o comerciales:** Si usa la aplicación centro de opiniones para notificar un problema relacionado con MDM, aprovisionamiento o cualquier otro aspecto de administración de dispositivos, cambie la categoría aplicación a categoría dispositivo de **Administración empresarial**  >  **Device category**.

### Requisitos previos

- El dispositivo está conectado a una red.
- La aplicación centro de opiniones está disponible en el equipo de escritorio del usuario y el usuario puede cargar archivos en la nube de Microsoft.

### Ubicaciones de datos, acceso y retención

Si aceptas las condiciones de uso del centro de opiniones, el usuario confirmará explícitamente el almacenamiento y el uso de los datos (según lo definido en dicho contrato).

El centro de opiniones proporciona dos lugares para que el usuario almacene la información de diagnóstico:

- **La nube de Microsoft**. Los datos que el usuario carga mediante la aplicación centro de opiniones se almacenan para el número de días que son coherentes con los requisitos de privacidad de próxima generación (NGP). Los empleados de Microsoft pueden usar un visor compatible con NGP para acceder a la información durante este período.
   > [!NOTE]  
   > Estos requisitos se aplican a los datos de todas las categorías de los concentradores de comentarios.

- **El dispositivo HoloLens**. Al archivar un informe en el centro de opiniones, el usuario puede seleccionar **guardar una copia local de los diagnósticos y datos adjuntos creados al proporcionar comentarios**. Si el usuario selecciona esta opción, el centro de opiniones almacena una copia de la información de diagnóstico en el dispositivo HoloLens. Esta información sigue siendo accesible para el usuario (o cualquier persona que use esa cuenta para iniciar sesión en HoloLens). Para eliminar esta información, un usuario debe tener permisos de **Administrador** o de **propietario del dispositivo** en el dispositivo. Un usuario con los permisos adecuados puede iniciar sesión en el centro de comentarios, seleccionar la **opción**  >  **Ver registros de diagnósticos**y eliminar la información.

## Solucionador de problemas de configuración

Un usuario de HoloLens puede usar la aplicación configuración en el dispositivo para solucionar problemas y recopilar información de diagnóstico. Para ello, sigue estos pasos:

1. Abra la aplicación configuración y seleccione **Actualizar &** la página de  >  **solución de problemas** de seguridad.
1. Seleccione el área correspondiente y haga clic en **iniciar**.
1. Reproducir el problema.
1. Después de reproducir el problema, vuelva a configuración y, a continuación, seleccione **detener**.

### Requisitos previos

- La aplicación configuración está instalada en el dispositivo y está disponible para el usuario.

### Ubicaciones de datos, acceso y retención

Dado que el usuario inicia la recolección de datos, el usuario se reenvía implícitamente al almacenamiento de la información de diagnóstico. Solo el usuario, o cualquier persona con quien comparta los datos, puede obtener acceso a los datos.

La información de diagnóstico se almacena en el dispositivo. Si el dispositivo está conectado al equipo del usuario, la información también reside en el equipo en el siguiente archivo:

> Este PC\\ \<*HoloLens device name*> \\Internal Storage\\Documents\\Trace \<*ddmmyyhhmmss*> . ETL

> [!NOTE]  
> En esta ruta de acceso y nombre \<*HoloLens device name*> de archivo, representa el nombre del dispositivo HoloLens y \<*ddmmyyhhmmss*> representa la fecha y la hora en que se creó el archivo.

La información de diagnóstico permanece en estas ubicaciones hasta que el usuario la elimina.

## DiagnosticLog CSP

En un entorno de administración de dispositivos móviles (MDM), el administrador de ti puede usar el [proveedor de servicios de configuración de DiagnosticLog (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) para establecer la configuración de diagnóstico en dispositivos HoloLens inscritos. El administrador de ti puede configurar esta configuración para recopilar registros de dispositivos inscritos.

### Requisitos previos

- El dispositivo está conectado a una red.
- El dispositivo se ha inscrito en un entorno MDM que admite el CSP DiagnosticLog.

### Ubicaciones de datos, acceso y retención

Dado que el dispositivo es parte del entorno administrado, el usuario reenvía implícitamente a la información de diagnóstico el acceso de administrador.

El administrador de ti usa el CSP DiagnosticLog para configurar el almacenamiento de datos, la retención y las directivas de acceso, incluidas las directivas que rigen lo siguiente:

- La infraestructura de la nube que almacena la información de diagnóstico.
- El período de retención de la información de diagnóstico.
- Permisos que controlan el acceso a la información de diagnóstico.


