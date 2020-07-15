---
title: Notas de la versión de HoloLens 2
description: Obtén más información sobre las actualizaciones en cada nueva versión de HoloLens.
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
ms.openlocfilehash: cb4296413fdf31376ff0d11f1fa807c190af81f4
ms.sourcegitcommit: 563797405f7470f979a27718c604df920efbb368
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881240"
---
# Notas de la versión de HoloLens 2

Para asegurarte de tener una experiencia productiva con tus dispositivos HoloLens, continuamos publicando características, errores y actualizaciones de seguridad. En esta página, puedes obtener información sobre las novedades de HoloLens cada mes. Si deseas descargar la última versión de HoloLens 2 FFU para Flash el dispositivo a través del [Asistente de recuperación avanzada](hololens-recovery.md#clean-reflash-the-device) , puedes descargarlo desde [aquí](https://aka.ms/hololens2download). Esto se mantiene actualizado y coincidirá con la última construcción generalmente disponible. 

Las notas de la versión del emulador de HoloLens se pueden encontrar [aquí](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive).

## Windows Holographic, versión 2004, actualización de julio de 2020
- Compilación 19041,1109

Mejoras y correcciones de la actualización:

- Los desarrolladores pueden elegir entre habilitar o deshabilitar Device portal que requiere una conexión segura.
- Mejoras de confiabilidad para los lanzamientos de aplicaciones después de las actualizaciones del sistema operativo.
- Cambie el brillo predeterminado de la bandeja de entrada a 100%.
- Se solucionó un problema relacionado con el reenvío de HTTPS para Windows Device portal en HoloLens 2.

## Windows Holographic, versión 1903, actualización de julio de 2020
- Compilación 18362,1071

Mejoras y correcciones de la actualización:

- Corrige un problema que podría provocar que los hologramas desaparezcan en las aplicaciones de Unity al perder o recuperar el seguimiento.
- Se ha corregido un problema que causaba que las aplicaciones de Hololens exclusivas se bloquearan en el shell al usar el emulador Hololens con aceleración de hardware en determinados dispositivos.
- Se solucionó un problema relacionado con el reenvío de HTTPS para Windows Device portal en HoloLens 2.

## Windows Holographic, versión 2004-actualización 2020 de junio
- Compilación 19041,1106

Mejoras y correcciones de la actualización:

- Los grabadores de MRC personalizados tienen nuevos valores predeterminados para determinadas propiedades si no se especifican.
  - En el efecto de vídeo MRC:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (auriculares con micrófono envolventes))
  - En el efecto de audio de MRC:
    - LoopbackGain (el valor actual "ganancia de audio de la aplicación" en la página de captura de realidad mixta en Windows Device portal)
    - MicrophoneGain (el valor actual de ganancia de audio de micrófono en la página de captura de realidad mixta en Windows Device portal)
- Esta actualización contiene una corrección de errores que mejora la calidad de audio en escenarios de captura de realidad mixta. En concreto, debe eliminar el problema de audio de la grabación cuando se muestra el menú Inicio.
- Mejor estabilidad de los hologramas en vídeos grabados.
- Resuelve un problema por el que la captura de realidad mixta no pudo grabar vídeo después de que el dispositivo quede en estado de modo de espera durante varios días.
- La API HolographicSpace. UserPresence generalmente está deshabilitada para las aplicaciones de Unity, lo que evita un problema que provoca la pausa de algunas aplicaciones cuando se voltea el parasol, incluso si la configuración que se ejecuta en segundo plano está habilitada. La API ahora está habilitada para las versiones de Unity 2018.4.18 y superior, y 2019.3.4 y versiones posteriores.
- Al acceder a Device portal a través de una conexión WiFi, un explorador Web puede impedir el acceso a un certificado no válido, lo que informa de un error como "ERR_SSL_PROTOCOL_ERROR", incluso si el certificado del dispositivo se ha confiado anteriormente.  En este caso, no podrás pasar a Device portal porque no hay disponibles opciones para ignorar las advertencias de seguridad.  Esta actualización resuelve el problema.  Si el certificado de dispositivo se ha descargado anteriormente y se confía en un equipo PC para quitar las advertencias de seguridad del explorador y se ha encontrado el error de SSL, el nuevo certificado tendrá que descargarse y ser de confianza para las advertencias de seguridad del explorador de direcciones.
- Ha habilitado la capacidad de crear un paquete de aprovisionamiento en tiempo de ejecución que puede instalar una aplicación con paquetes MSIX.
- Nueva configuración que los usuarios pueden encontrar en configuración > > hologramas de sistema, que permite a los usuarios quitar automáticamente todos los hologramas de la Página principal de realidad mixta cuando se cierra el dispositivo.
- Se ha corregido un problema que causaba que las aplicaciones de HoloLens cambiaran el formato de píxel para representar negro en el emulador de HoloLens.
- Se ha corregido un error que provocaba un bloqueo durante el inicio de sesión en iris.
- Corrige un problema con las descargas de tienda repetidas para las aplicaciones ya actuales.
- Se ha corregido un error que impide que las aplicaciones inmersivo inicien el borde varias veces.
- Corrige un problema sobre los lanzamientos de la aplicación fotos en arranque inicial después de la actualización de la versión 1903.
- Rendimiento y confiabilidad mejorados.

## Windows Holographic, versión 1903-actualización 2020 de junio
- Compilación 18362,1064

Mejoras y correcciones de la actualización:

- Los grabadores de MRC personalizados tienen nuevos valores predeterminados para determinadas propiedades si no se especifican.
  - En el efecto de vídeo MRC:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (auriculares con micrófono envolventes))
  - En el efecto de audio de MRC:
    - LoopbackGain (el valor actual "ganancia de audio de la aplicación" en la página de captura de realidad mixta en Windows Device portal)
    - MicrophoneGain (el valor actual de ganancia de audio de micrófono en la página de captura de realidad mixta en Windows Device portal)
- La API HolographicSpace. UserPresence generalmente está deshabilitada para las aplicaciones de Unity, lo que evita un problema que provoca la pausa de algunas aplicaciones cuando se voltea el parasol, incluso si la configuración que se ejecuta en segundo plano está habilitada. La API ahora está habilitada para las versiones de Unity 2018.4.18 y superior, y 2019.3.4 y versiones posteriores.
- Se ha corregido un problema que causaba que las aplicaciones de HoloLens cambiaran el formato de píxel para representar negro en el emulador de HoloLens.
- Corrige un problema sobre los lanzamientos de la aplicación fotos en arranque inicial después de la actualización de la versión 1903.

## Windows Holographic, versión 2004  
Compilación: 19041,1103

Nos complace anunciar nuestra actualización de software importante de mayo de 2020 para HoloLens 2, **Windows Holographic, versión 2004**. Esta versión incluye una gran cantidad de nuevas y emocionantes funciones, como la compatibilidad con Windows AutoPilot, el modo de aplicación oscuro, la compatibilidad con Ethernet USB para los puntos de acceso público con 5G/LTE y mucho más. Para actualizar a la última versión, abra la **aplicación configuración**, vaya a **Actualizar & seguridad**y, después, seleccione el botón **Buscar actualizaciones**   . 

|             Característica                              |          Descripción                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       WindowsAutopilot                          |          Configurar previamente y configurar sin problemas nuevos dispositivos para producción, con Windows AutoPilot                 |
|       Asistencia de FIDO 2                             |          Compatibilidad con las claves de seguridad de FIDO2 para habilitar una autenticación rápida y segura para dispositivos compartidos            |
|       Aprovisionamiento mejorado                      |          Aplicar sin problemas un paquete de aprovisionamiento de una unidad USB a tu HoloLens                              |
|       Estado de instalación de la aplicación                 |          Comprueba que el estado de la instalación de las aplicaciones se haya enviado a HoloLens 2 a través de MDM, en la aplicación configuración              |
|       Proveedores de servicios de configuración (CSP)   |          Nuevos proveedores de servicios de configuración (CSP) mejorados capacidades de control de administración.                 |
|       Compatibilidad con USB 5G/LTE                       |          La funcionalidad de Ethernet USB ampliada permite el soporte técnico para 5G/LTE                                    |
|       Modo de aplicación oscuro                              |          Modo de aplicación oscuro para las aplicaciones que admiten modos oscuros y claros, mejorando la experiencia de visualización        |
|       Comandos de voz                             |          Compatibilidad con comandos de voz de sistema adicionales para controlar HoloLens, manos libres                           |
|       Mejoras en el seguimiento de manos                 |          Mejoras en el seguimiento de la mano hacer más precisas los botones y las interacciones de tabletas 2D                        |
|       Mejoras y mejoras en la calidad                 |          Varias mejoras de rendimiento y confiabilidad del sistema en toda la plataforma                            |

### Compatibilidad con Windows AutoPilot 

El piloto automático de Windows para HoloLens 2 permite que el canal de ventas de dispositivos inscriba HoloLens en tu inquilino de Intune.  Cuando los dispositivos llegan, están listos para su implementación automática como dispositivos compartidos en su espacio empresarial. Para aprovechar la implementación automática, los dispositivos deberán conectarse a una red durante la primera pantalla de la instalación con un USB-C a Ethernet o USB-C a la llave de LTE. 

Cuando un usuario inicia el proceso de implementación automática de Autopilot, el proceso completa estos pasos: 

1. Unir el dispositivo a Azure Active Directory (Azure AD). 
1. Usar Azure AD para inscribir el dispositivo en Microsoft Intune (u otro servicio MDM). 
1. Descargar las directivas de destino del dispositivo, los certificados y los perfiles de red. 
1. Aprovisionar el dispositivo. 
1. Mostrar la pantalla de inicio de sesión al usuario. 

Para obtener más información, vea la [Guía de evaluación de Windows AutoPilot para HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot).

**Póngase en contacto con el administrador de su cuenta para unirse a la vista previa de AutoPilot ahora. Los dispositivos autoejecutables preparados comenzarán pronto.**

### Compatibilidad con clave de seguridad FIDO2 

Muchos de ellos comparten un dispositivo HoloLens con muchas personas en un entorno de trabajo o escuela. Si los dispositivos se comparten entre los alumnos en un aula o se desprotegen desde un dispositivo de bloqueo, es importante poder cambiar de forma rápida y sencilla sin escribir nombres de usuario y contraseñas largos. 

FIDO permite que cualquier persona de su organización (un inquilino de AAD) inicie sesión en HoloLens sin tener que escribir un nombre de usuario o una contraseña. 

Las claves de seguridad de FIDO2 son un método de autenticación con contraseñas basado en estándares que no se puede suplantar y que puede venir con cualquier factor de forma. Internet Identity online (FIDO) es un estándar abierto para autenticación con contraseña. FIDO permite que los usuarios y las organizaciones aprovechen el estándar para iniciar sesión en sus recursos sin un nombre de usuario o contraseña mediante una clave de seguridad externa o una clave de plataforma integrada en un dispositivo. 

Lea los [documentos de seguridad sin contraseñas](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key) para comenzar. 

### Inscripción MDM mejorada mediante el paquete de aprovisionamiento 

Los paquetes de aprovisionamiento te permiten establecer la configuración de HoloLens mediante un archivo de configuración en lugar de usar la configuración rápida de HoloLens. Anteriormente, los paquetes de aprovisionamiento se deben copiar en la memoria interna de HoloLens, ahora que pueden estar en una unidad USB para que sean más fáciles de volver a usar en varios HoloLens y para que más personas puedan aprovisionar HoloLens en paralelo.  Además, los paquetes de aprovisionamiento admiten un nuevo campo para inscribirse en la administración de dispositivos, por lo que no hay configuración manual. 

1. Para probarlo, descargue la versión más reciente del diseñador de configuración de Windows de la tienda Windows en su PC. 
1. Seleccione **aprovisionar dispositivos hololens** > seleccione **aprovisionar dispositivos hololens 2** 
1. Cree el perfil de configuración y, cuando haya terminado, copie todos los archivos creados en un dispositivo de almacenamiento USB-C. 
1. Conéctelo a HoloLens con flash y pulse **volumen + alimentación** para aplicar el paquete de aprovisionamiento. 

### Estado de instalación de la aplicación de línea de negocio 

La implementación y administración de la aplicación MDM de las aplicaciones de línea de negocio (LOB) es crítica para nuestros clientes. Los administradores y los usuarios deben poder ver el estado de instalación de la aplicación, con fines de auditoría y diagnóstico. En esta versión, agregamos más detalles en **configuración > cuentas > Access o school > haga clic en su cuenta > información.**

### CSP y directivas adicionales 

Un [proveedor de servicios de configuración (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) es una interfaz para leer, establecer, modificar o eliminar la configuración de un dispositivo. En esta versión, agregamos soporte técnico para más directivas, lo que aumenta el número de administradores de control en los dispositivos HoloLens de implementación. Para obtener la lista de CSP admitidos por HoloLens, visite este [vínculo](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp). Novedades de esta versión:

**Policy CSP** 

El proveedor de servicios de configuración de directivas permite a la empresa configurar directivas en dispositivos de Windows. En esta versión, agregamos nuevas directivas para HoloLens, que se enumeran a continuación. Puede obtener más información sobre las directivas admitidas [aquí](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

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

**CSP NetworkQoSPolicy** El proveedor de servicios de configuración de NetworkQoSPolicy crea directivas de calidad de servicio (QoS) de red. Una directiva de QoS realiza un conjunto de acciones en el tráfico de red en función de un conjunto de condiciones coincidentes. Puede obtener más información sobre esta directiva [aquí](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp). 

### Compatibilidad ampliada con Ethernet USB para dispositivos de tethering 5G/LTE

Se ha agregado soporte técnico para habilitar determinados dispositivos de banda ancha móvil, como teléfonos 5G/LTE y hotpots de WiFi cuando están tethering a HoloLens 2 a través de USB. Estos dispositivos se mostrarán en configuración de red como otra conexión Ethernet. No se admiten los dispositivos de banda ancha móvil que requieren un controlador externo. Esto habilita las conexiones de ancho de banda alto en escenarios en los que WiFi no está disponible, y el tethering WiFi no es lo suficientemente adecuado. Puede obtener más información sobre los dispositivos USB admitidos [aquí](https://docs.microsoft.com/hololens/hololens-connect-devices).  

### Mejoras en el seguimiento de manos

El seguimiento manual ha recibido varias mejoras en esta versión. 

- **Estabilidad de la postura:** Ahora, el sistema resistente curvará el dedo del índice cuando se convierta en occluded por la palma de la mano.  Esto mejora la precisión al insertar botones, escribir, desplazar contenido y mucho más. 
- **Reducción de las pulsaciones accidentales por accidente:** Hemos mejorado la detección del gesto de AirTap.  Ahora hay menos activaciones accidentales en varios casos comunes, como colocar las manos a tu lado. 
- **Confiabilidad del cambio de usuario:** Ahora, el sistema es más rápido y más fiable en la actualización del tamaño de la mano cuando se comparte un dispositivo. 
- **Robo de manos reducido:** Hemos mejorado la gestión de casos en los que hay más de 2 manos a la vista de los sensores.  Si varias personas trabajan juntas, ahora hay muy pocas probabilidades de que la mano con la que se hace un seguimiento pase del usuario a la de otra persona en la escena. 
- **Confiabilidad del sistema:** Se ha corregido un problema que provocaba que el seguimiento manual dejara de funcionar durante un período de tiempo si el dispositivo tiene mucha carga. 

### Modo oscuro

Muchas aplicaciones de Windows ahora son compatibles con los modos oscuro y ligero, y los clientes de HoloLens 2 pueden elegir el modo predeterminado para las aplicaciones que admitan ambos. Una vez actualizada, el modo de aplicación predeterminado será "oscuro", pero puede cambiarse fácilmente. Vaya a configuración > > colores del sistema para buscar "elegir el modo de aplicación predeterminado". Estas son algunas de las aplicaciones en el cuadro que admiten el modo oscuro: 

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

Ahora puedes acceder a los comandos y usarlos rápidamente con tu voz mientras usas cualquier aplicación en el dispositivo. Si está ejecutando el sistema con un idioma diferente, pruebe los comandos apropiados en ese idioma. Para obtener más información sobre los comandos y sobre cómo usarlos, consulta nuestra documentación [aquí](https://docs.microsoft.com/hololens/hololens-cortana).  

### Actualizaciones de Cortana 

La aplicación actualizada se integra con Microsoft 365, que actualmente se encuentra en inglés (Estados Unidos), para ayudarte a sacar más partido de tus dispositivos. En HoloLens 2, Cortana ya no admite determinados comandos específicos del dispositivo, como ajustar el volumen o reiniciar el dispositivo, que ahora son compatibles con los nuevos comandos de voz del sistema mencionados anteriormente. Más información sobre la nueva aplicación de Cortana y su dirección en nuestro blog [aquí](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/). 

### Mejoras y mejoras en la calidad 

Mejoras y correcciones también en la actualización:  
- La actualización introduce un sistema de calibración de pantalla activa. Esto mejora la estabilidad y la alineación de los hologramas, lo que les ayuda a mantenerte al mover la cabeza de cara a cara. 
- Se ha corregido un error que provoca que la transmisión por secuencias de Wi-Fi a HoloLens se interrumpa periódicamente. Si una aplicación indica que necesita transmisión de baja latencia, esta corrección se puede llevar a cabo llamando a [esta función](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode). 
- Se ha corregido un problema por el que el dispositivo podría bloquearse durante la transmisión por secuencias en el modo de investigación. 
- Se ha corregido un error en el que, en algunos casos, el usuario adecuado no aparecía en la pantalla de inicio de sesión al reanudar la sesión. 
- Se ha corregido un problema por el que los usuarios no podían exportar registros de MDM mediante la configuración. 
- Se ha corregido un problema por el que la precisión del seguimiento ocular inmediatamente después de la configuración desplegable podría ser inferior a la especificación. 
- Se ha corregido un problema que provocaba que el subsistema de seguimiento ocular no pudiera inicializarse y/o realizar una calibración en determinadas condiciones. 
- Se ha corregido un problema por el que la calibración ocular se preguntaba para un usuario que ya está calibrado. 
- Se ha corregido un problema por el que un controlador se bloqueaba durante la calibración ocular. 
- Se ha corregido un problema en el que las prensas repetidas del botón de encendido pueden provocar un tiempo de espera y un bloqueo de Shell de 60 segundos. 
- Estabilidad mejorada para los búferes de profundidad. 
- Se ha agregado el botón ' compartir ' en el centro de opiniones para que los usuarios puedan compartir tus comentarios más fácilmente. 
- Se ha corregido un error en el que RoboRaid no se instaló correctamente. 

### Problemas conocidos

- Estamos investigando un problema que rodea el uso del lenguaje del sistema zh-CN que impide que los comandos de voz tomen una captura de realidad mixta o que la dirección IP del dispositivo no funcione.
- Estamos investigando un problema que requiere que inicie la aplicación de Cortana después de arrancar el dispositivo para usar la activación de voz "Hola Cortana", y si ha actualizado desde una compilación de 18362, es posible que vea un segundo icono de aplicación para la versión anterior de la aplicación de Cortana en Inicio que ya no funciona. 

## Windows Holographic, versión 1903, actualización de mayo de 2020 
- Compilación 18362,1061

Esta actualización mensual de calidad no contiene ningún cambio de nota porque el equipo se ha centrado en proporcionarle la actualización de características de la más alta calidad ahora disponible en Windows Holographic, la versión 2004 puede actualizarse detalladamente más arriba. Aproveche esta oportunidad para ir a la última actualización de características y disfrutar de una tonelada de nuevos e increíbles cambios.

## Windows Holographic, versión 1903, actualización de 2020 de abril
- Compilación 18362,1059

**Modo oscuro para aplicaciones compatibles** 

Muchas aplicaciones de Windows admiten modos oscuros y claros, y pronto los clientes de HoloLens 2 pueden elegir el modo predeterminado para las aplicaciones que admiten ambas combinaciones de colores. Basado en comentarios muy positivos sobre clientes, con esta actualización configuramos el modo de aplicación predeterminado en "oscuro", pero puede cambiar esta configuración fácilmente en cualquier momento.
Vaya a **configuración > > colores del sistema** para buscar **"elegir el modo de aplicación predeterminado".**

Estas son algunas de las aplicaciones en el cuadro que admiten el modo oscuro:
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
- Asegúrate de que las superposiciones de Shell se incluyan en capturas de realidad mixta.
- Los programadores no reales ahora pueden usar la página de la vista 3D en Device portal para probar y depurar sus aplicaciones.
- Mejorar la estabilidad del holograma en captura de realidad mixta cuando se usa el algoritmo de DepthReprojection HolographicDepthReprojectionMethod.
- Error de clase de API de WinRT IStreamSocketListener no registrado en la aplicación ARM de 32 bits.

## Windows Holographic, versión 1903-actualización 2020 de marzo 
- Compilación 18362,1056

Mejoras y correcciones de la actualización:

- Mejora la estabilidad de los hologramas en captura de realidad mixta cuando se usa el algoritmo autobackplane HolographicDepthReprojectionMethod.
- Garantiza que el sistema de coordenadas conectado a una muestra de profundidad MF es coherente con la documentación pública.
- Mejora la productividad de los programadores al permitir a los clientes pegar una gran cantidad de texto a través de Device portal.

## Windows Holographic, versión 1903, actualización de febrero de 2020 
- Compilación 18362,1053

Mejoras y correcciones de la actualización:

- Ha deshabilitado temporalmente la API HolographicSpace. UserPresence para las aplicaciones de Unity con el fin de evitar un problema que hace que algunas aplicaciones se detengan cuando se voltea el parasol, incluso si la configuración que se ejecuta en segundo plano está habilitada.
- Se ha corregido un bloqueo de HUP aleatorio con seguimiento manual, en el que el usuario verá una inmovilización de la interfaz de usuario y después volverá a iniciar la sesión después de varios segundos.
- Hemos realizado una mejora en el seguimiento manual, de modo que aunque Poking con el dedo de índice, la parte superior de ese dedo tendrá menos probabilidades de tener un doblez inesperado.
- Confiabilidad mejorada de la función de seguimiento de encabezado, asignación espacial y otros Runtime.

## Windows Holographic, versión 1903-actualización 2020 de enero 
- Compilación 18362,1043

Mejora en la actualización:

- Mejoras de estabilidad para aplicaciones exclusivas al trabajar con el emulador de HoloLens 2.

## Windows Holographic, versión 1903-diciembre 2019 Update 
- Compilación 18362,1042

Mejoras y correcciones de la actualización:

- Presenta correcciones de LSR (reproducción de la última etapa). Mejora la representación visual de los hologramas para que parezcan más estables y nítidas con mayor precisión. Esto será más apreciable si las aplicaciones no establecen la profundidad de hologramas correctamente, después de esta actualización.
- Soluciona la estabilidad de las aplicaciones exclusivas y la navegación entre aplicaciones exclusivas.
- Resuelve un problema por el que la captura de realidad mixta no pudo grabar vídeo después de que el dispositivo quede en estado de modo de espera durante varios días.
- Mejora la estabilidad del holograma.

## Windows Holographic, versión 1903, actualización de noviembre de 2019 
- Compilación 18362,1039

Mejoras y correcciones de la actualización:

- Correcciones de comandos de voz **"Select"** durante la configuración inicial para en-CA y en-au.
- Mejoras en la calidad visual de objetos en las últimas versiones de Unity y MRTK.
- Correcciones de problemas de aplicaciones holográficas que se bloquean en un estado de pausa durante el lanzamiento hasta que el panel pines se vuelve a poner y se descarta nuevamente.
- OpenXR correcciones y mejoras en el tiempo de ejecución para HoloLens 2 y el emulador.


