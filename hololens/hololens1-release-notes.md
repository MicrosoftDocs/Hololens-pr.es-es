---
title: Notas de la versión de HoloLens 1st (gen)
description: Obtenga información sobre las actualizaciones de cada nueva versión de HoloLens.
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
ms.openlocfilehash: 0fb6c9ed1cd8d3ecc23975052eed54512a465bfb
ms.sourcegitcommit: 35e180e09e3938c25e4cac8e99885d7e57fa4dad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "108310280"
---
# <a name="hololens-1st-gen-release-notes"></a>Notas de la versión de HoloLens 1st (gen)

## <a name="hololens-1st-gen-long-term-servicing"></a>Mantenimiento a largo plazo de HoloLens (1ª generación)
HoloLens (1.ª generación) ha entrado en el estado de mantenimiento a largo plazo (LTS). Las actualizaciones futuras se centrarán en las correcciones de problemas y seguridad, al tiempo que se mantiene la paridad de características con la versión 1809 de Windows 10 Holographic para HoloLens (1.ª generación).

Para los desarrolladores, esto significa que las aplicaciones de HoloLens (1ª generación) no admitirán la API de OpenXR.  Estos cascos siguen siendo compatibles con Unity 2019 LTS con el back-end de la API de WinRT durante el ciclo de vida completo de Unity 2019 LTS hasta mediados de 2022.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic, versión 1809

> **Se aplica a:** HoloLens (1ª generación)

| Característica | Detalles |
|---|---|
| **Menú Acciones rápidas** | Cuando esté en una aplicación, el gesto de Bloom abrirá ahora un menú Acciones rápidas para proporcionar acceso rápido a las características del sistema más usadas sin tener que salir de la aplicación. <br> Consulte [Configuración de HoloLens en pantalla completa](hololens-kiosk.md) para obtener información sobre el menú Acciones rápidas en pantalla completa.<br><br> |
| **Detener la captura de vídeo desde el menú Inicio o acciones rápidas** | Si inicia la captura de vídeo desde el menú menú Inicio o acciones rápidas, podrá detener la grabación desde el mismo lugar. (No olvide que siempre puede hacerlo con comandos de voz). |
| **Proyecto en un dispositivo habilitado para Miracast** | Proyecte el contenido de HoloLens en un dispositivo Surface o TV/Monitor cercanos si usa el adaptador de Microsoft Display.  En **Inicio,** seleccione **Conectar** y, a continuación, seleccione el dispositivo al que desea proyectar. **Nota:** Puede implementar HoloLens para usar la proyección miracast sin habilitar el modo de desarrollador. |
| **Nuevas notificaciones** | Vea y responda a notificaciones del sistema en HoloLens, igual que en un equipo. Mire para responder a ellos o descartarlos (o si está en una experiencia inmersiva, use el gesto de Bloom). |
| **Superposiciones de HoloLens**<br>(selector de archivos, teclado, diálogos, etc.) | Ahora verá superposiciones como el teclado, los diálogos, el selector de archivos, etc. al usar aplicaciones inmersivas. |
| **Interfaz de usuario de superposición de comentarios visuales para el cambio de volumen** | Al usar los botones de subir y bajar volumen en HoloLens, verá una presentación visual del nivel de volumen. |
| **Nueva interfaz de usuario para el arranque del dispositivo** | Se agregó un indicador de carga durante el proceso de arranque para proporcionar comentarios visuales sobre la carga del sistema. Reinicie el dispositivo para ver el nuevo indicador de carga, que se encuentra entre el mensaje "Hello" y el logotipo de arranque de Windows. |
| **Uso compartido cercano** | Adición de la experiencia de uso compartido cercano de Windows, lo que le permite compartir una captura con un dispositivo Windows cercano. Al capturar una foto o vídeo en HoloLens (o usar el botón Compartir de una aplicación como Microsoft Edge), seleccione un dispositivo Windows cercano con el que compartir. |
| **Compartir desde Microsoft Edge** | El botón Compartir ahora está disponible Microsoft Edge ventanas en HoloLens. En Microsoft Edge, seleccione **Compartir**. Use el selector de recursos compartidos de HoloLens para compartir contenido web. |

#### <a name="for-international-customers"></a>Para clientes internacionales

| Característica | Detalles |
| --- | --- |
| Compilaciones localizadas de chino y japonés | Use HoloLens con una interfaz de usuario localizada para chino simplificado o japonés, incluidos los comandos de teclado, dictado y voz de Pinyin localizados.<br>[Obtenga información sobre cómo instalar las versiones en chino y japonés de HoloLens.](hololens1-install-localized.md) |
| Síntesis de voz (TTS) | La característica de síntesis de voz ahora admite chino, japonés e inglés. |

#### <a name="for-administrators"></a>Para administradores

| Característica |  Detalles  |
|---|----|
| [Habilitación del aprovisionamiento posterior a la instalación](hololens-provisioning.md) | Ahora puede aplicar un paquete de aprovisionamiento en tiempo de ejecución en cualquier momento mediante **Configuración**. |
| Acceso asignado con Azure AD grupos | Ahora puede usar grupos de Azure AD configuración del acceso asignado a Windows para configurar la pantalla completa de una o varias aplicaciones. |
| Cambio de perfil de inicio de sesión de PIN desde la pantalla de inicio de sesión | El inicio de sesión con PIN ahora está disponible para **Otro usuario.** |
| Inicio de sesión con web Proveedor de credenciales con contraseña | Ahora puede seleccionar la opción de inicio de sesión de Globe para iniciar el inicio de sesión web con su contraseña. En la pantalla de inicio de sesión, seleccione **Opciones de inicio de sesión y** seleccione la opción Globo para iniciar el inicio de sesión web. Escriba su nombre de usuario si es necesario y, a continuación, la contraseña. <br>**Nota:** Puede optar por omitir cualquier opción de PIN o tarjeta inteligente cuando se le solicite durante el inicio de sesión web. |
| Lee la información de hardware del dispositivo a través de MDM para que se pueda realizar el seguimiento de los dispositivos por número de serie. | Los administradores de TI pueden ver y realizar un seguimiento de HoloLens por número de serie del dispositivo en su consola MDM. Consulte la documentación de MDM para obtener instrucciones y disponibilidad de características. |
| Establecer el nombre del dispositivo HoloLens mediante MDM (cambiar el nombre) | Los administradores de TI pueden ver y cambiar el nombre de los dispositivos HoloLens en su consola MDM. Consulte la documentación de MDM para obtener instrucciones y disponibilidad de características. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10, versión 1803 para Microsoft HoloLens

> **Se aplica a:** HoloLens (1.ª generación)

Windows 10, versión 1803, es la primera actualización de características de Windows Holographic for Business desde su lanzamiento en Windows 10, versión 1607. Esta actualización presenta los siguientes cambios:

- Anteriormente, solo podía comprobar que la licencia de actualización de Commercial Suite se había aplicado al dispositivo HoloLens comprobando si vpn era una opción disponible en el dispositivo. Ahora, **el sistema**  >  **de** configuración mostrará **Windows Holographic for Business** después de aplicar la licencia de actualización. [Obtenga información sobre cómo desbloquear Windows Holographic for Business características](hololens1-upgrade-enterprise.md).

- Puede ver el número de compilación del sistema operativo en las propiedades del dispositivo en la aplicación Explorador de archivos y en la Herramienta de recuperación de dispositivos [de Windows (WDRT).](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)
- El aprovisionamiento de un dispositivo HoloLens ahora es más fácil con el nuevo Asistente **para aprovisionar dispositivos HoloLens** en la herramienta Diseñador de configuración de Windows. En el asistente, puede configurar la experiencia de configuración y las conexiones de red, establecer el modo de desarrollador y obtener tokens de Azure AD masivos. [Obtenga información sobre cómo usar el asistente de aprovisionamiento simple para HoloLens.](hololens-provisioning.md#provisioning-package-hololens-wizard)

- Cuando se crea una cuenta local en un paquete de aprovisionamiento, la contraseña ya no expira cada 42 días.

- Puede configurar [HoloLens como un quiosco](hololens-kiosk.md)de una sola aplicación o de varias aplicaciones. El modo de pantalla completa con varias aplicaciones permite configurar HoloLens para ejecutar solo las aplicaciones que especifique e impide que los usuarios realicen cambios.

- El Protocolo de transferencia multimedia (MTP) está habilitado para que pueda conectar el dispositivo HoloLens a un equipo mediante USB y transferir archivos entre HoloLens y el equipo. También puede usar la aplicación Explorador de archivos para mover y eliminar archivos desde HoloLens.

- Anteriormente, después de haber iniciado sesión en el dispositivo con una cuenta de Azure Active Directory  (Azure AD),  tenía que agregar acceso de trabajo en Configuración para obtener acceso a los recursos corporativos. Ahora, inicie sesión con una cuenta Azure AD y la inscripción se realiza automáticamente.

- Antes de iniciar sesión, puede elegir el icono de red debajo del campo de contraseña para elegir una red Wi-Fi a la que conectarse. También puede conectarse a una red de invitados, como en un hotel, un centro de conferencias o una empresa.

- Ahora puede compartir [fácilmente HoloLens con varias personas mediante](hololens-multiple-users.md) Azure AD cuentas.

- Cuando se produce un error en la instalación o el inicio de sesión, elija la **nueva opción Recopilar** información para obtener registros de diagnóstico para solucionar problemas.

- Los usuarios individuales pueden sincronizar su correo electrónico corporativo sin inscribir su dispositivo en la administración de dispositivos móviles (MDM). Puede usar el dispositivo con una cuenta Microsoft, descargar e instalar la aplicación correo electrónico y agregar una cuenta de correo electrónico directamente.

- Puede comprobar el estado de sincronización de MDM de un dispositivo en **Configuración**  >  **Cuentas**  >  **Access Work or School**  >  **Info**. En la **sección Estado de sincronización de** dispositivos, puede iniciar una sincronización, ver las áreas administradas por MDM y crear y exportar un informe de diagnóstico avanzado.
