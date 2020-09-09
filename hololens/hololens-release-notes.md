---
title: Notas de la versión de HoloLens 2
description: Obtén más información sobre las actualizaciones en cada nueva versión de HoloLens 2.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 06/9/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 0fe78d4b668523de4faa66a64f54c14760a81b12
ms.sourcegitcommit: bddd470ac475dd8fc7b69e8904d18082a83f39e0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2020
ms.locfileid: "10997221"
---
# Notas de la versión de HoloLens 2

Para asegurarte de tener una experiencia productiva con tus dispositivos HoloLens, continuamos publicando características, errores y actualizaciones de seguridad. En esta página, puedes ver las novedades de HoloLens cada mes. Para obtener la última actualización de Flash (FFU) de HoloLens 2, [puedes descargarla aquí](https://aka.ms/hololens2download) [desde el Asistente de recuperación avanzada](hololens-recovery.md#clean-reflash-the-device). La descarga se mantiene actualizada y proporciona la última versión disponible general.

>[!NOTE]
> Para leer las notas de la versión del emulador de HoloLens, [visita el archivo](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive).

## Windows Holographic, versión 2004-actualización 2020 de septiembre
- Compilación 19041,1117

Mejoras y correcciones de la actualización:

- Corrige un problema que impedía que Visual Studio depure una aplicación cuando SupportsMultipleInstances = "true" está presente en el appxmanifest.
- Esta versión incluye la corrección de detección de proxy de NCSI para resolver errores de detección de Internet por proxy de red. NCSI puede usar un proxy de máquina y un proxy por perfil para la detección de conectividad a Internet. Un proxy por usuario será admitido por NCSI en una versión futura.
- En la mayoría de los dispositivos Windows Mixed Reality, el vector de dirección hacia adelante es paralelo al suelo cuando la cabeza del usuario se encuentra en una posición neutra mirando hacia adelante. Sin embargo, las versiones anteriores de HoloLens 2 alinearon el vector para que sea perpendicular a los paneles de visualización, que se inclina hacia abajo unos cuantos grados con relación a la orientación ideal. Las versiones más recientes de HoloLens 2 han corregido esto para garantizar la coherencia semántica en los factores de forma.
- Mejoras de la solidez del seguimiento de la mano que darán menos pérdidas de seguimiento en escenarios específicos.
- Esta versión contiene una corrección para mejorar la calidad de la marca de hora de audio que puede haber contribuido a problemas de captura de video.

## Windows Holographic, versión 1903-actualización 2020 de septiembre
- Compilación 18362,1079

Mejoras y correcciones de la actualización:

- En la mayoría de los dispositivos Windows Mixed Reality, el vector de dirección hacia adelante es paralelo al suelo cuando la cabeza del usuario se encuentra en una posición neutra mirando hacia adelante. Sin embargo, las versiones anteriores de HoloLens 2 alinearon el vector para que sea perpendicular a los paneles de visualización, que se inclina hacia abajo unos cuantos grados con relación a la orientación ideal. Las versiones más recientes de HoloLens 2 han corregido esto para garantizar la coherencia semántica en los factores de forma.
- Mejoras de la solidez del seguimiento de la mano que darán menos pérdidas de seguimiento en escenarios específicos.

## Windows Holographic, versión 2004, actualización de 2020 de agosto
- Compilación 19041,1113

Mejoras y correcciones de la actualización:

- La aplicación de configuración ya no seguirá al usuario en la inscripción de iris o en la calibración de seguimiento de ojos.
- Se ha corregido un error en el que se aplicaba un paquete de aprovisionamiento durante la ejecución de OOBE que cambia el nombre del dispositivo y realiza otras acciones (como conectarse a una red) no podía realizar otras acciones después de que se reinicie el dispositivo, debido a un cambio de nombre.
- Combinación de colores modificada de los flujos de configuración de dispositivos iniciales para mejorar la calidad visual.

## Windows Holographic, versión 1903, actualización de 2020 de agosto
- Compilación 18362,1074

Esta actualización mensual de calidad no contiene ningún cambio importante, le recomendamos que pruebe nuestras compilaciones más recientes para Windows Holographic, versión 2004.

## Windows Holographic, versión 2004, actualización de julio de 2020
- Compilación 19041,1109

Mejoras y correcciones de la actualización:

- Ahora, los desarrolladores pueden elegir entre habilitar o deshabilitar que el portal de dispositivos requiera una conexión segura.
- Confiabilidad mejorada para los lanzamientos de aplicaciones después de las actualizaciones del sistema operativo.
- Se ha cambiado el brillo de la bandeja de entrada a 100 por ciento.
- Se ha solucionado un problema relacionado con el reenvío de HTTPS para Windows Device portal en HoloLens 2.

## Windows Holographic, versión 1903, actualización de julio de 2020
- Compilación 18362,1071

Mejoras y correcciones de la actualización:

- Se ha corregido un problema que podría provocar que los hologramas desaparezcan en las aplicaciones de Unity al perder o recuperar un seguimiento.
- Se ha corregido un problema que causaba que las aplicaciones de HoloLens exclusivas se bloquearan en el shell al usar el emulador HoloLens con aceleración de hardware en determinados dispositivos.
- Se ha solucionado un problema relacionado con el reenvío de HTTPS para Windows Device portal en HoloLens 2.

## Windows Holographic, versión 2004-actualización 2020 de junio
- Compilación 19041,1106

Mejoras y correcciones de la actualización:

- Los grabadores de MRC personalizados ahora tienen nuevos valores predeterminados para determinadas propiedades si no se especifican.
  - En el *efecto de vídeo MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (auriculares con micrófono envolventes))
  - En el *efecto de audio de MRC*:
    - LoopbackGain (el valor actual "ganancia de audio de la aplicación" en la página de captura de realidad mixta en Windows Device portal)
    - MicrophoneGain (el valor actual de ganancia de audio de micrófono en la página de captura de realidad mixta en Windows Device portal)
- Se ha corregido un error para mejorar la calidad de audio en escenarios de captura de realidad mixta. En concreto, esta corrección debe eliminar el problema de audio en la grabación cuando se muestra el menú **Inicio** .
- Mejor estabilidad de los hologramas en vídeos grabados.
- Se ha resuelto un problema por el que la captura de realidad mixta no pudo grabar video después de que el dispositivo se quedó en estado de modo de espera durante varios días.
- La API HolographicSpace. UserPresence generalmente está deshabilitada para las aplicaciones de Unity. Este comportamiento evita un problema que provocaba que algunas aplicaciones se pausan cuando el parasol se ha volteado, incluso si estaba habilitada la opción "ejecutar en segundo plano". La API ahora está habilitada para las versiones de Unity 2018.4.18 y versiones posteriores, y 2019.3.4 y posteriores.
- Cuando accede al portal de dispositivos a través de una conexión WiFi, es posible que un explorador Web impida el acceso a un certificado no válido. El explorador puede notificar un error como "ERR_SSL_PROTOCOL_ERROR", incluso si el certificado de dispositivo era de confianza. En este caso, no puede progresar a Device portal, ya que no hay ninguna opción para ignorar las advertencias de seguridad. Esta actualización resolvió el problema. Si el certificado de dispositivo se ha descargado anteriormente y se confía en un equipo PC para quitar las advertencias de seguridad del explorador y se produce el error de SSL, el nuevo certificado debe descargarse y confiarse en las advertencias de seguridad del explorador de direcciones.
- Permitió la creación de un paquete de aprovisionamiento en tiempo de ejecución que pueda instalar una aplicación con paquetes MSIX.
- Se ha agregado una **Settings**configuración en los  >  hologramas**del sistema**de configuración  >  **Holograms** que permite a los usuarios quitar automáticamente todos los hologramas de la Página principal de la realidad mixta cuando se cierra el dispositivo.
- Se ha corregido un problema que causaba que las aplicaciones de HoloLens cambiaran el formato de píxel para representar negro en el emulador de HoloLens.
- Se ha corregido un error que provocaba un bloqueo durante el inicio de sesión de iris.
- Se ha corregido un problema sobre las descargas de tienda repetidas para las aplicaciones ya actuales.
- Se ha corregido un error para evitar que las aplicaciones inmersivo abran Microsoft Edge varias veces.
- Se ha corregido un problema con los lanzamientos de la aplicación fotos durante el arranque inicial después de la actualización de la versión 1903.
- Rendimiento y confiabilidad mejorados.

## Windows Holographic, versión 1903-actualización 2020 de junio
- Compilación 18362,1064

Mejoras y correcciones de la actualización:

- Los grabadores de MRC personalizados tienen nuevos valores predeterminados para determinadas propiedades si no se especifican.
  - En el *efecto de vídeo MRC*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (auriculares con micrófono envolventes))
  - En el *efecto de audio de MRC*:
    - LoopbackGain (el valor actual "ganancia de audio de la aplicación" en la página de captura de realidad mixta en Windows Device portal)
    - MicrophoneGain (el valor actual de ganancia de audio de micrófono en la página de captura de realidad mixta en Windows Device portal)
- La API HolographicSpace. UserPresence generalmente está deshabilitada para las aplicaciones de Unity. Este comportamiento evita un problema que hace que algunas aplicaciones se detengan cuando se voltea el parasol, incluso si la configuración que se va a ejecutar en segundo plano está habilitada. La API ahora está habilitada para las versiones 2018.4.18 y posteriores de Unity, y 2019.3.4 y posteriores.
- Se ha corregido un problema que causaba que las aplicaciones de HoloLens cambiaran el formato de píxel para representar negro en el emulador de HoloLens.
- Se ha corregido un problema sobre los lanzamientos de la aplicación fotos durante el arranque inicial después de la actualización de la versión 1903.

## Windows Holographic, versión 2004  
- Compilación: 19041,1103

2020 la actualización de software más importante de HoloLens 2, *Windows Holographic, versión 2004* incluye una gran cantidad de nuevas y emocionantes funciones, como la compatibilidad con el piloto automático de Windows, el modo de aplicación oscuro, la compatibilidad con Ethernet USB para los puntos de acceso 5g/LTE y mucho más. Para actualizar a la última versión, abra la aplicación **configuración**   , vaya a **Actualizar & seguridad**y seleccione el botón **Buscar actualizaciones**   . 

|             Característica                              |          Descripción                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       WindowsAutopilot                          |          Configurar previamente y configurar sin problemas nuevos dispositivos para producción mediante el piloto automático de Windows                 |
|       Asistencia de FIDO 2                             |          Compatibilidad con las claves de seguridad de FIDO2 para habilitar una autenticación rápida y segura para dispositivos compartidos            |
|       Aprovisionamiento mejorado                      |          Aplicar sin problemas un paquete de aprovisionamiento de una unidad USB a tu HoloLens                              |
|       Estado de instalación de la aplicación                 |          Comprobar el estado de instalación en la aplicación configuración de las aplicaciones se ha insertado en HoloLens 2 a través de MDM               |
|       Proveedores de servicios de configuración (CSP)   |          Se agregaron nuevos proveedores de servicios de configuración para mejorar las capacidades de control de administración                 |
|       Compatibilidad con USB 5G/LTE                       |          La funcionalidad de Ethernet USB ampliada permite el soporte técnico para 5G/LTE                                    |
|       Modo de aplicación oscuro                              |          El modo de aplicación oscuro está disponible para las aplicaciones que admiten modos oscuros y claros, mejorando la experiencia de visualización        |
|       Comandos de voz                             |          Compatibilidad con comandos de voz de sistema adicionales para controlar HoloLens manos libres                           |
|       Mejoras en el seguimiento de manos                 |          Mejoras en el seguimiento de la mano hacer más precisas los botones y las interacciones de tabletas 2D                        |
|       Mejoras y mejoras en la calidad                 |          Varias mejoras de rendimiento y confiabilidad del sistema en toda la plataforma                            |

### Compatibilidad con Windows AutoPilot

El piloto automático de Windows para HoloLens 2 permite que el canal de ventas de dispositivos inscriba HoloLens en tu inquilino de Intune. Cuando los dispositivos llegan, están listos para su implementación automática como dispositivos compartidos en su espacio empresarial. Para aprovechar las ventajas de la implementación automática, el dispositivo debe conectarse a una red durante la primera pantalla de la instalación con un adaptador USB-C-to-Ethernet o USB-C-to-LTE.

Después de que un usuario inicia el proceso de Autoimplementación automática, el proceso completa los siguientes pasos:

1. Unir el dispositivo a Azure Active Directory (Azure AD).
1. Usar Azure AD para inscribir el dispositivo en Microsoft Intune (u otro servicio MDM).
1. Descargar las directivas de destino del dispositivo, los certificados y los perfiles de red.
1. Aprovisionar el dispositivo.
1. Mostrar la pantalla de inicio de sesión al usuario.

Para obtener más información, vea la [Guía de evaluación de Windows AutoPilot para HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot).

*Póngase en contacto con el administrador de su cuenta para unirse a la vista previa de AutoPilot ahora. Los dispositivos autoejecutables preparados comenzarán pronto.*

### Compatibilidad con clave de seguridad FIDO2

Algunos usuarios comparten un dispositivo HoloLens con otras personas en un entorno profesional o educativo. Por lo tanto, es importante que los usuarios puedan escribir fácilmente nombres de usuario y contraseñas largos. La identidad rápida en línea (FIDO) permite que cualquier persona de su organización (inquilino de Azure AD) inicie sesión en HoloLens sin tener que escribir un nombre de usuario o una contraseña.

Las claves de seguridad de FIDO2 son un método de autenticación no phish basado en estándares que puede venir en cualquier factor de forma. FIDO es un estándar abierto para autenticación con contraseña. Permite a los usuarios y las organizaciones iniciar sesión en sus recursos sin un nombre de usuario o contraseña. En su lugar, usan una clave de seguridad externa o una clave de plataforma integrada en un dispositivo.

Para empezar, consulte [Habilitar el inicio de sesión con clave de seguridad sin contraseñas](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key).

### Inscripción MDM mejorada mediante el paquete de aprovisionamiento

Los paquetes de aprovisionamiento te permiten establecer la configuración de HoloLens mediante un archivo de configuración en lugar de usar la configuración rápida de HoloLens. Anteriormente, los paquetes de aprovisionamiento se han copiado en la memoria interna de HoloLens. Ahora pueden estar en una unidad USB para que sea más fácil reutilizarlo en varios dispositivos HoloLens y puedes aprovisionar dispositivos en paralelo. Los paquetes de aprovisionamiento ahora también admiten un campo para inscribirse en la administración de dispositivos, por lo que no hay ninguna configuración manual después del aprovisionamiento.

Para probarlo:

1. Descargue la versión más reciente del diseñador de configuración de Windows de la tienda Windows en su PC.
1. Seleccione **aprovisionar dispositivos de hololens**  >  **aprovisionar dispositivos hololens 2**.
2. Cree el perfil de configuración. Después, copie todos los archivos que se crearon en un dispositivo de almacenamiento USB-C.
3. Conecta el dispositivo USB-C en cualquier HoloLens que haya parpadeado. Después, pulsa **volume down**los botones de  +  **encendido** por volumen para aplicar el paquete de aprovisionamiento.

### Estado de instalación de la aplicación de línea de negocio

La implementación y administración de la aplicación MDM de aplicaciones empresariales es crítica para HoloLens. Los administradores y los usuarios necesitan ver el estado de instalación de la aplicación para auditoría y diagnóstico. En esta versión, hemos agregado más detalles en **configuración**  >  **cuentas**de  >  **Access trabajo o escuela**  >  **haga clic en la información de su cuenta**  >  **Info**.

### CSP y directivas adicionales

Un [proveedor de servicios de configuración (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) es una interfaz para leer, establecer, modificar o eliminar la configuración de un dispositivo. En esta versión, agregamos compatibilidad con más directivas para aumentar los administradores de control en los dispositivos HoloLens implementados. Para obtener la lista de CSP compatibles con HoloLens, consulta [CSP NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

Novedades de esta versión:

**Policy CSP** 

El proveedor de servicios de configuración de directivas permite a la empresa configurar directivas en dispositivos de Windows. En esta versión, agregamos nuevas directivas para HoloLens, que se enumeran aquí. Para obtener más información, consulta la [política de CSP admitida por HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessGazeInput 
- LetAppsAccessGazeInput_ForceAllowTheseApps 
- LetAppsAccessGazeInput_ForceDenyTheseApps 
- LetAppsAccessGazeInput_UserInControlOfTheseApps 
- LetAppsAccessMicrophone_ForceAllowTheseApps 
- LetAppsAccessMicrophone_ForceDenyTheseApps 
- LetAppsAccessMicrophone_UserInControlOfTheseApps 
- AllowWiFi 

**CSP de NetworkQoSPolicy**

El proveedor de servicios de configuración de NetworkQoSPolicy crea directivas de calidad de servicio (QoS) de red. Una directiva de QoS realiza un conjunto de acciones en el tráfico de red en función de un conjunto de condiciones coincidentes. Para obtener más información, consulta [CSP NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

### Compatibilidad ampliada con Ethernet USB para dispositivos de tethering 5G/LTE

Se agregó compatibilidad para habilitar determinados dispositivos de banda ancha móvil, como teléfonos 5G/LTE y Wi-Fi hotpots, cuando están tethering a HoloLens 2 a través de USB. Estos dispositivos ahora se muestran en **configuración de red** como otra conexión Ethernet. (Los dispositivos de banda ancha móvil que requieren un controlador externo no son compatibles). Esta funcionalidad habilita las conexiones de ancho de banda alto cuando la Wi-Fi no está disponible y el tethering Wi-Fi no es lo suficientemente adecuado. Para obtener más información sobre los dispositivos USB compatibles, vea [conectarse a dispositivos Bluetooth y USB-C](https://docs.microsoft.com/hololens/hololens-connect-devices).  

### Mejoras en el seguimiento de manos

Esta versión incluye varias mejoras en el seguimiento de manos:

- **Estabilidad de la postura:** Ahora el sistema resistente curva el dedo del índice cuando obtiene occluded por la palma. Este cambio mejora la precisión cuando pulsas los botones, escribe, desplaza el contenido y mucho más. 
- **Reducción de las pulsaciones de aire accidentales:** Hemos mejorado la detección del gesto de pulsar el avión. Ahora hay menos activaciones accidentales en varios escenarios comunes, como cuando derribe las manos a sus lados.
- **Confiabilidad del cambio de usuario:** Ahora, el sistema es más rápido y más confiable al actualizar el tamaño de la mano al compartir un dispositivo.
- **Robo de manos reducido:** Hemos mejorado la gestión de casos en los que hay más de dos manos a la vista de los sensores. Si varias personas trabajan juntas, ahora hay muy pocas probabilidades de que la mano de la pista "salte" al usuario a la de otra persona en la escena.
- **Confiabilidad del sistema:** Se ha corregido un problema que provocaba que el seguimiento manual dejara de funcionar cuando el dispositivo está bajo mucha carga.

### Modo oscuro

Muchas aplicaciones de Windows ahora son compatibles con los modos oscuro y ligero. Los usuarios de HoloLens 2 pueden elegir el modo predeterminado para las aplicaciones que admiten ambos. Después de la actualización, el modo de aplicación predeterminado es "oscuro", pero puede cambiar esta configuración fácilmente: vaya a **configuración**  >  **colores del sistema**  >  **Colors**  >  **Elija el modo de aplicación predeterminado**. 

Estas aplicaciones "en el cuadro" son compatibles con el modo oscuro: 

- Configuración 
- Microsoft Store 
- Correo 
- Calendario 
- Explorador de archivos 
- Centro de opiniones 
- OneDrive 
- Fotos 
- Visor 3D 
- Películas y TV 

![Ventanas de modo oscuro en mosaico](images/DarkMode.jpg)

### Comandos de voz del sistema

Ahora puede usar los comandos de voz con cualquier aplicación del dispositivo. Para obtener más información, consulta [usar tu voz para trabajar con HoloLens](https://docs.microsoft.com/hololens/hololens-cortana). Consulta también los [idiomas admitidos para HoloLens 2](https://docs.microsoft.com/hololens/hololens2-language-support).  

### Actualizaciones de Cortana

La aplicación actualizada se integra con Microsoft 365 para ayudarte a sacar más partido de tus dispositivos (actualmente solo en Inglés de Estados Unidos). En HoloLens 2, Cortana ya no es compatible con determinados comandos específicos del dispositivo, como, por ejemplo, ajustar el volumen o reiniciarlo. Estas opciones ahora son compatibles con los nuevos comandos de voz del sistema. Más información sobre la nueva aplicación de Cortana en nuestro [blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### Mejoras y mejoras en la calidad

Mejoras y correcciones también en la actualización:  
- Introdujo un sistema de calibración de pantalla activa. Esta característica mejora la estabilidad y la alineación de los hologramas. Ahora permanecen en su lugar cuando mueves tu cabeza de un lado a otro.
- Se ha corregido un error que provocaba que la transmisión por secuencias de Wi-Fi a HoloLens se interrumpa periódicamente. Si una aplicación indica que necesita transmisión de baja latencia, implementa la corrección llamando a la [función SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Se ha corregido un bloqueo de dispositivo que se produjo durante la transmisión por secuencias en el modo de investigación.
- Se ha corregido un error en el que, en algunos casos, el usuario no se mostraba en la pantalla de inicio de sesión al reanudar una sesión.
- Se ha corregido un problema por el que los usuarios no pueden exportar registros de MDM mediante la **configuración**.
- Se ha corregido un problema por el que la precisión del seguimiento ocular inmediatamente después de la configuración no actualizada podría ser menor de lo esperado.
- Se ha corregido un problema por el que el subsistema de seguimiento ocular no se pudo inicializar o realizar una calibración en determinadas condiciones.
- Se ha corregido un problema que afectaba a la calibración de ojos para un usuario que ya está calibrado.
- Se ha corregido un problema por el que un controlador se bloqueaba durante la calibración ocular.
- Se ha corregido un problema que provocaba que el botón repetido de encendido del sistema y el bloqueo del shell 60.
- Estabilidad mejorada para los búferes de profundidad.
- Se ha agregado un botón **compartir** en el centro de opiniones para que los usuarios puedan compartir sus comentarios más fácilmente.
- Se ha corregido un error en el que RoboRaid wan't instalado correctamente.

### Problemas conocidos

- Un problema con el lenguaje de sistema zh-CN impide que los comandos de voz tomen una captura de realidad mixta o se muestre la dirección IP del dispositivo.
- Un problema requiere iniciar la aplicación de Cortana después de iniciar el dispositivo para usar la activación de voz "Hola Cortana". Si ha actualizado desde una compilación de 18362, también puede ver un segundo mosaico de la aplicación para la versión anterior de la aplicación de Cortana que ya no funciona en **Inicio**.

## Windows Holographic, versión 1903, actualización de mayo de 2020 
- Compilación 18362,1061

Esta actualización mensual de calidad no contiene ningún cambio importante porque el equipo estaba trabajando en Windows Holographic versión 2004 puede actualizarse como se ha descrito anteriormente.

## Windows Holographic, versión 1903, actualización de 2020 de abril
- Compilación 18362,1059

**Modo oscuro para aplicaciones compatibles** 

Muchas aplicaciones de Windows admiten el modo oscuro y el modo de luz. Los clientes de HoloLens 2 ahora pueden elegir el modo predeterminado para las aplicaciones que admiten ambas combinaciones de colores. En función de los comentarios de los clientes, establecemos el modo de aplicación predeterminado en "oscuro", pero puede cambiar fácilmente esta configuración en cualquier momento: vaya a **configuración > > colores del sistema** para buscar **"elegir el modo de aplicación predeterminado".**

Estas aplicaciones "en el cuadro" son compatibles con el modo oscuro:
- Configuración
- Microsoft Store
- Correo
- Calendario
- Explorador de archivos
- Centro de opiniones
- OneDrive
- Fotos
- Visor 3D
- Películas y TV

**Mejoras y correcciones también en la actualización:** 
- Se han asegurado de que las superposiciones de Shell se incluyen en las capturas de realidad mixta.
- Los programadores no reales ahora pueden usar la página de la vista 3D en Device portal para probar y depurar sus aplicaciones.
- Se ha mejorado la estabilidad de los hologramas en captura de realidad mixta cuando se usa el algoritmo de *DepthReprojection HolographicDepthReprojectionMethod* .
- Se ha corregido el error "no se ha registrado la clase API de IStreamSocketListener" en las aplicaciones ARM de 32-bit.

## Windows Holographic, versión 1903-actualización 2020 de marzo 
- Compilación 18362,1056

Mejoras y correcciones de la actualización:

- Se ha mejorado la estabilidad de los hologramas en captura de realidad mixta cuando se usa el algoritmo *Autobackplane HolographicDepthReprojectionMethod* .
- Se ha asegurado que el sistema de coordenadas conectado a una muestra de profundidad MF es coherente con la documentación pública.
- Se ha mejorado la productividad del desarrollador al permitir a los clientes pegar grandes cantidades de texto a través del portal de dispositivos.

## Windows Holographic, versión 1903, actualización de febrero de 2020 
- Compilación 18362,1053

Mejoras y correcciones de la actualización:

- Ha deshabilitado temporalmente la API HolographicSpace. UserPresence para aplicaciones de Unity. Este cambio evita un problema que provocaba que algunas aplicaciones se pausan cuando el parasol se ha volteado, incluso si estaba habilitada la opción "ejecutar en segundo plano".
- Se ha corregido un bloqueo HUP aleatorio causado por el seguimiento de manos, en el que el usuario observó una inmovilización de la interfaz de usuario y después volvió unos segundos.
- Se ha mejorado el seguimiento de las manos para que al escribir con el dedo del índice, la parte superior de ese dedo tenga menos probabilidades de que se produzcan de forma inesperada.
- Confiabilidad mejorada de la función de seguimiento de encabezado, asignación espacial y otros Runtime.

## Windows Holographic, versión 1903-actualización 2020 de enero 
- Compilación 18362,1043
 
Mejoras y correcciones de la actualización:

- Se ha mejorado la estabilidad de las aplicaciones exclusivas al trabajar con el emulador de HoloLens 2.

## Windows Holographic, versión 1903-diciembre 2019 Update 
- Compilación 18362,1042

Mejoras y correcciones de la actualización:

- Se introdujeron las correcciones de la última fase de reproducción (LSR). Representación visual mejorada de hologramas para que parezca más estable y nítida con el fin de lograr una mayor precisión de su profundidad. Este síntoma será más perceptible después de esta actualización si las aplicaciones no establecen la profundidad de hologramas correctamente.
- Estabilidad fija de aplicaciones exclusivas y navegación entre aplicaciones exclusivas.
- Se ha resuelto un problema por el que la captura de realidad mixta no pudo grabar video después de que el dispositivo estuviera en estado de espera durante varios días.
- Estabilidad mejorada de los hologramas.

## Windows Holographic, versión 1903, actualización de noviembre de 2019 
- Compilación 18362,1039

Mejoras y correcciones de la actualización:

- Funcionalidad fija de comandos de voz **Select** durante la configuración inicial para en-CA y en-au.
- Se ha mejorado la calidad visual de los objetos colocados en las últimas versiones de los toolkits de Unity y Mixed Reality (MRTK).
- Problemas de direccionamiento corregido con aplicaciones holográficas se atasca en un estado de pausa durante el inicio hasta que se abre y se cierra el menú Inicio.
- OpenXR correcciones y mejoras en el tiempo de ejecución para HoloLens 2 y el emulador.
