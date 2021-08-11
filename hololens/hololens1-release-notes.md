---
title: HoloLens notas de la primera versión (gen)
description: Obtenga información sobre las actualizaciones de cada versión HoloLens nueva.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 1
ms.openlocfilehash: e332794baf20fbab8278a138ceeafb651c6fa2a06f3f41a66038e544f7a6e46b
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661836"
---
# <a name="hololens-1st-gen-release-notes"></a>HoloLens notas de la primera versión (gen)

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens mantenimiento a largo plazo (1.ª generación)
HoloLens (1.ª generación) ha entrado en estado de mantenimiento a largo plazo (LTS). Las actualizaciones futuras se centrarán en las correcciones de problemas y seguridad, al tiempo que se mantiene la paridad de características con la versión 1809 de Windows 10 Holographic para HoloLens (1.ª generación).

Para los desarrolladores, esto significa HoloLens aplicaciones de (1.ª generación) no admitirán la API de OpenXR.  Estos cascos siguen siendo compatibles con Unity 2019 LTS con el back-end de la API de WinRT durante el ciclo de vida completo de Unity 2019 LTS hasta mediados de 2022.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic, versión 1809

> **Se aplica a:** HoloLens (1.ª generación)

| Característica | Detalles |
|---|---|
| **Menú Acciones rápidas** | Cuando esté en una aplicación, el gesto de Bloom abrirá ahora un menú Acciones rápidas para proporcionar acceso rápido a las características del sistema más usadas sin tener que salir de la aplicación. <br> Consulte [Configuración de HoloLens pantalla completa](hololens-kiosk.md) para obtener información sobre el menú Acciones rápidas en pantalla completa.<br><br> |
| **Detener la captura de vídeo desde el menú Inicio o acciones rápidas** | Si inicia la captura de vídeo desde el menú menú Inicio o acciones rápidas, podrá detener la grabación desde el mismo lugar. (No olvide que siempre puede hacerlo con comandos de voz). |
| **Project a un dispositivo Miracast habilitado para dispositivos** | Project el HoloLens contenido en un dispositivo Surface cercano o tv/monitor si se usa el adaptador de Microsoft Display.  En **Inicio,** **seleccione Conectar** y, a continuación, seleccione el dispositivo al que desea proyectar. **Nota:** Puede implementar HoloLens para usar la proyección Miracast sin habilitar el modo de desarrollador. |
| **Nuevas notificaciones** | Vea y responda a notificaciones del sistema en HoloLens, igual que en un equipo. Mire para responder a ellos o descartarlos (o si está en una experiencia inmersiva, use el gesto de Bloom). |
| **HoloLens superposiciones**<br>(selector de archivos, teclado, diálogos, etc.) | Ahora verá superposiciones como el teclado, los diálogos, el selector de archivos, etc. al usar aplicaciones envolventes. |
| **Interfaz de usuario de superposición de comentarios visuales para el cambio de volumen** | Al usar los botones de subir o bajar volumen en el HoloLens verá una presentación visual del nivel de volumen. |
| **Nueva interfaz de usuario para el arranque del dispositivo** | Se agregó un indicador de carga durante el proceso de arranque para proporcionar comentarios visuales sobre la carga del sistema. Reinicie el dispositivo para ver el nuevo indicador de carga, que se encuentra entre el mensaje "Hello" y el Windows de arranque. |
| **Uso compartido cercano** | Adición de la Windows uso compartido cercano, lo que le permite compartir una captura con un dispositivo Windows cercano. Al capturar una foto o vídeo en HoloLens (o usar el botón Compartir de una aplicación como Microsoft Edge), seleccione un dispositivo de Windows cercano con el que compartir. |
| **Compartir desde Microsoft Edge** | El botón Compartir ahora está disponible en Microsoft Edge windows en HoloLens. En Microsoft Edge, seleccione **Compartir**. Use el selector HoloLens recurso compartido para compartir contenido web. |

#### <a name="for-international-customers"></a>Para clientes internacionales

| Característica | Detalles |
| --- | --- |
| Compilaciones localizadas de chino y japonés | Use HoloLens interfaz de usuario localizada para chino simplificado o japonés, incluidos los comandos de teclado, dictado y voz de Pinyin localizados.<br>[Obtenga información sobre cómo instalar las versiones en chino y japonés de HoloLens.](hololens1-install-localized.md) |
| Síntesis de voz (TTS) | La característica de síntesis de voz ahora admite chino, japonés e inglés. |

#### <a name="for-administrators"></a>Para administradores

| Característica |  Detalles  |
|---|----|
| [Habilitación del aprovisionamiento posterior a la instalación](hololens-provisioning.md) | Ahora puede aplicar un paquete de aprovisionamiento en tiempo de ejecución en cualquier momento mediante **Configuración**. |
| Acceso asignado con Azure AD grupos | Ahora puede usar grupos de Azure AD configuración de Windows acceso asignado para configurar la pantalla completa de una o varias aplicaciones. |
| Cambio de perfil de inicio de sesión de PIN desde la pantalla de inicio de sesión | El inicio de sesión de PIN ya está disponible para **Otro usuario.** |
| Inicio de sesión con web Proveedor de credenciales con contraseña | Ahora puede seleccionar la opción De inicio de sesión de Globe para iniciar el inicio de sesión web con su contraseña. En la pantalla de inicio de sesión, seleccione **Opciones de inicio** de sesión y seleccione la opción Globo para iniciar el inicio de sesión web. Escriba el nombre de usuario si es necesario y, a continuación, la contraseña. <br>**Nota:** Puede optar por omitir cualquier opción de PIN o tarjeta inteligente cuando se le solicite durante el inicio de sesión web. |
| Leer la información de hardware del dispositivo a través de MDM para que se pueda realizar un seguimiento de los dispositivos por número de serie | Los administradores de TI pueden ver y realizar un seguimiento HoloLens número de serie del dispositivo en su consola MDM. Consulte la documentación de MDM para obtener instrucciones y disponibilidad de características. |
| Establecer HoloLens de dispositivo mediante MDM (cambiar nombre) | Los administradores de TI pueden ver y cambiar HoloLens dispositivos en su consola MDM. Consulte la documentación de MDM para obtener instrucciones y disponibilidad de características. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10, versión 1803 para Microsoft HoloLens

> **Se aplica a:** HoloLens (1.ª generación)

Windows 10, versión 1803, es la primera actualización de características de Windows Holographic for Business desde su lanzamiento en Windows 10, versión 1607. Esta actualización presenta los cambios siguientes:

- Anteriormente, solo podía comprobar que la licencia de actualización de Commercial Suite se había aplicado al dispositivo HoloLens comprobando si vpn era una opción disponible en el dispositivo. Ahora, **Configuración**  >  **system** mostrará  Windows Holographic for Business una vez aplicada la licencia de actualización. [Obtenga información sobre cómo desbloquear Windows Holographic for Business características](hololens1-upgrade-enterprise.md).

- Puede ver el número de compilación del sistema operativo en las propiedades del dispositivo en la aplicación Explorador de archivos y en Windows [Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)
- El aprovisionamiento de HoloLens dispositivo es ahora más fácil con el nuevo Asistente para **aprovisionar HoloLens dispositivos** en la Windows Diseñador de configuración. En el asistente, puede configurar la experiencia de configuración y las conexiones de red, establecer el modo de desarrollador y obtener tokens de Azure AD masivos. [Obtenga información sobre cómo usar el Asistente para aprovisionamiento simple para HoloLens](hololens-provisioning.md#provisioning-package-hololens-wizard).

- Cuando se crea una cuenta local en un paquete de aprovisionamiento, la contraseña ya no expira cada 42 días.

- Puede configurar HoloLens pantalla completa de una [sola aplicación o de varias aplicaciones.](hololens-kiosk.md) El modo de pantalla completa con varias aplicaciones le permite configurar un HoloLens ejecutar solo las aplicaciones que especifique e impide que los usuarios realicen cambios.

- El Protocolo de transferencia multimedia (MTP) está habilitado para que pueda conectar el dispositivo HoloLens a un equipo mediante USB y transferir archivos entre HoloLens y el equipo. También puede usar la aplicación Explorador de archivos para mover y eliminar archivos desde dentro HoloLens.

- Anteriormente, después de haber iniciado sesión en el dispositivo con una cuenta de  Azure Active Directory (Azure AD), tenía que agregar acceso al trabajo en **Configuración** para obtener acceso a los recursos corporativos. Ahora, inicie sesión con una cuenta Azure AD y la inscripción se realiza automáticamente.

- Antes de iniciar sesión, puede elegir el icono de red debajo del campo de contraseña para elegir una red Wi-Fi a la que conectarse. También puede conectarse a una red de invitados, como un hotel, un centro de conferencias o una empresa.

- Ahora puede compartir [fácilmente HoloLens con varias personas mediante](hololens-multiple-users.md) Azure AD cuentas.

- Cuando se produce un error en la instalación o el inicio de sesión, elija la **nueva opción Recopilar** información para obtener registros de diagnóstico para solucionar problemas.

- Los usuarios individuales pueden sincronizar su correo electrónico corporativo sin inscribir su dispositivo en la administración de dispositivos móviles (MDM). Puede usar el dispositivo con una cuenta Microsoft, descargar e instalar la aplicación Mail y agregar una cuenta de correo electrónico directamente.

- Puede comprobar el estado de sincronización de MDM de un dispositivo **en Configuración**  >  **Accounts** Access Work or  >  **School**  >  **Info**. En la **sección Estado de sincronización de** dispositivos, puede iniciar una sincronización, ver las áreas administradas por MDM y crear y exportar un informe de diagnóstico avanzado.
