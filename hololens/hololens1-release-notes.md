---
title: Notas de la versión de HoloLens 1 (gen)
description: Obtén más información sobre las actualizaciones en cada nueva versión de HoloLens.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/12/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 1
ms.openlocfilehash: a3761fc383b991743c20c09ce430e8988af789fb
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828565"
---
# Notas de la versión de HoloLens 1 (gen)

### Windows 10 Holographic, versión 1809

> **Se aplica a:** Hololens (1ª generación)

| Característica | Detalles |
|---|---|
| **Menú acciones rápidas** | Cuando estés en una aplicación, el gesto de la floración abrirá un menú de acciones rápidas para proporcionarte acceso rápido a las características del sistema más usadas sin tener que salir de la aplicación. <br> Para obtener más información sobre el menú de acciones rápidas en el modo de pantalla completa, consulta [configurar HoloLens en el modo de pantalla](hololens-kiosk.md) completa.<br><br> |
| **Detener captura de vídeo desde el menú Inicio o acciones rápidas** | Si inicia la captura de vídeo desde el menú Inicio o el menú acciones rápidas, podrá detener la grabación desde el mismo lugar. (No olvides que siempre puedes hacerlo con los comandos de voz). |
| **Proyecto a un dispositivo habilitado para Miracast** | Proyecta tu contenido de HoloLens en un dispositivo Surface cercano o TV/monitor si usas el adaptador de pantalla de Microsoft.  En **Inicio**, seleccione **conectar**y, a continuación, seleccione el dispositivo al que desea proyectar. **Nota:** Puedes implementar HoloLens para usar la proyección Miracast sin habilitar el modo de desarrollador. |
| **Notificaciones nuevas** | Visualiza y responde a notificaciones de notificaciones en HoloLens, tal como lo haces en un equipo de PC. Mira fijamente para responder o descartar (o si estás en una experiencia envolvente, usa el gesto de flores). |
| **Superposiciones de HoloLens**<br>(selector de archivos, teclado, diálogos, etc.) | Ahora verás las superposiciones como el teclado, los diálogos, el selector de archivos, etc. cuando usas aplicaciones inmersivo. |
| **Interfaz de usuario de superposición de comentarios visuales para cambio de volumen** | Cuando usas los botones subir o bajar el volumen de tu HoloLens, verás una pantalla del nivel de volumen. |
| **Nueva interfaz de usuario para inicio de dispositivo** | Durante el proceso de inicio se agregó un indicador de carga para proporcionar comentarios visuales que el sistema está cargando. Reinicie el dispositivo para ver el nuevo indicador de carga, que se encuentra entre el mensaje "Hola" y el logotipo de inicio de Windows. |
| **Uso compartido en proximidad** | Incorporación de la experiencia de uso compartido cercano de Windows, que le permite compartir una captura con un dispositivo Windows cercano. Cuando Capture una foto o un vídeo en HoloLens (o use el botón compartir desde una aplicación como Microsoft Edge), seleccione un dispositivo de Windows cercano con el que compartir. |
| **Compartir desde Microsoft Edge** | El botón compartir ahora está disponible en Microsoft Edge Windows en HoloLens. En Microsoft Edge, seleccione **compartir**. Usa el selector de recursos compartidos de HoloLens para compartir contenido Web. |

#### Para clientes internacionales

| Característica | Detalles |
| --- | --- |
| Versiones localizadas de chino y japonés | Usa HoloLens con una interfaz de usuario localizada para chino simplificado o japonés, incluidos los comandos de teclado, dictado y voz localizados de pinyin.<br>[Más información sobre cómo instalar las versiones en chino y japonés de HoloLens.](hololens1-install-localized.md) |
| Síntesis de voz (TTS) | La característica de síntesis de voz ahora es compatible con chino, Japonés e inglés. |

#### Para administradores

| Característica |  Detalles  |
|---|----|
| [Habilitar aprovisionamiento posterior a la instalación](hololens-provisioning.md) | Ahora puede aplicar un paquete de aprovisionamiento en tiempo de ejecución en cualquier momento con la **configuración**. |
| Acceso asignado con grupos de Azure AD | Ahora puede usar grupos de Azure AD para la configuración de acceso asignado de Windows para configurar la configuración de quiosco de una sola o de varias aplicaciones. |
| Cambiar el inicio de sesión con PIN en la pantalla de inicio de sesión | El inicio de sesión con PIN ahora está disponible para **otros usuarios**. |
| Iniciar sesión con el proveedor de credenciales Web mediante contraseña | Ahora puede seleccionar la opción de inicio de sesión del globo para iniciar el inicio de sesión Web con la contraseña. En la pantalla de inicio de sesión, seleccione **Opciones de inicio de sesión** y seleccione la opción globo para iniciar el inicio de sesión en la Web. Escriba su nombre de usuario, si es necesario, y su contraseña. <br>**Nota:** Puede omitir cualquier opción de PIN o SmartCard cuando se le solicite durante el inicio de sesión Web. |
| Leer la información de hardware del dispositivo a través de MDM para que se pueda realizar un seguimiento de los dispositivos por número de serie | Los administradores de TI pueden ver y realizar un seguimiento de HoloLens por número de serie de dispositivo en su consola de MDM. Para obtener más información, consulte la documentación de MDM. |
| Establecer nombre de dispositivo HoloLens a través de MDM (cambiar el nombre) | Los administradores de TI pueden ver y cambiar el nombre de los dispositivos de HoloLens en la consola de MDM. Para obtener más información, consulte la documentación de MDM. |

### Windows 10, versión 1803 para HoloLens

> **Se aplica a:** Hololens (1ª generación)

Windows 10, versión 1803, es la primera actualización de características de Windows Holographic para empresas desde su lanzamiento en Windows 10, versión 1607. Esta actualización introduce los cambios siguientes:

- Anteriormente, solo puedes verificar que la licencia de actualización de la Suite comercial se haya aplicado a tu dispositivo HoloLens comprobando si VPN era una opción disponible en el dispositivo. Ahora, **Settings**  >  el**sistema** de configuración mostrará **Windows Holographic para empresas** después de que se aplique la licencia de actualización. [Obtenga información sobre cómo desbloquear características de Windows Holographic para empresas](hololens1-upgrade-enterprise.md).

- Puede ver el número de compilación del sistema operativo en las propiedades del dispositivo en la aplicación explorador de archivos y en la [herramienta de recuperación de dispositivos de Windows (WDRT)](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq).
- Aprovisionar un dispositivo HoloLens ahora es más fácil con el nuevo Asistente para **aprovisionar dispositivos hololens** en la herramienta diseñador de configuración de Windows. En el asistente, puede configurar la experiencia de instalación y las conexiones de red, establecer el modo de desarrollador y obtener tokens de Azure AD en masa. [Más información sobre cómo usar el Asistente de aprovisionamiento simple para HoloLens](hololens-provisioning.md#provisioning-package-hololens-wizard).

- Al crear una cuenta local en un paquete de aprovisionamiento, la contraseña ya no vence cada 42 días.

- Puede [configurar HoloLens como una quiosco de aplicación única o de varias aplicaciones](hololens-kiosk.md). El modo quiosco de varias aplicaciones te permite configurar HoloLens para que solo ejecute las aplicaciones que especifiques e impide que los usuarios realicen cambios.

- El protocolo de transferencia multimedia (MTP) está habilitado para que puedas conectar el dispositivo HoloLens a un equipo de USB y transferir archivos entre HoloLens y el equipo. También puede usar la aplicación explorador de archivos para mover y eliminar archivos en HoloLens.

- Anteriormente, una vez que haya iniciado sesión en el dispositivo con una cuenta de Azure Active Directory (Azure AD), tendrá que **Agregar el acceso de trabajo** en **configuración** para obtener acceso a los recursos de la empresa. Ahora, inicia sesión con una cuenta de Azure AD y la inscripción se realiza automáticamente.

- Antes de iniciar sesión, puede elegir el icono de red debajo del campo de contraseña para elegir una red Wi-Fi diferente a la que conectarse. También puede conectarse a una red de invitado, como un hotel, un centro de conferencias o una empresa.

- Ahora puedes compartir fácilmente [HoloLens con varias personas](hololens-multiple-users.md) que usen cuentas de Azure ad.

- Cuando se produce un error en la configuración o el inicio de sesión, elija la nueva opción **recopilar información** para obtener registros de diagnóstico para la solución de problemas.

- Los usuarios individuales pueden sincronizar su correo electrónico corporativo sin inscribir su dispositivo en la administración de dispositivos móviles (MDM). Puede usar el dispositivo con una cuenta de Microsoft, descargar e instalar la aplicación correo, y agregar una cuenta de correo directamente.

- Puede comprobar el estado de sincronización de MDM de un dispositivo en **configuración**  >  **cuentas**de la información del  >  **trabajo o de la escuela**  >  **Info**. En la sección **Estado de sincronización de dispositivos** , puede iniciar una sincronización, ver áreas administradas por MDM y crear y exportar un informe de diagnóstico avanzado.
