---
title: Reinicie, restablezca o recupere el HoloLens 1
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
description: Cómo usar Windows Device Recovery Tool para flashear una imagen a HoloLens 1 era generación.
keywords: procedimientos para, reiniciar, resetear, recuperar, restablecimiento completo, restablecimiento parcial, ciclo de energía, HoloLens, apagar, wdrt, Windows Device Recovery Tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: de53f8f2cccfe3ece8900c88c5379adf2fb55a7b
ms.sourcegitcommit: 5d38af8d17dfcc028e7e0b2bb888c6c9d1e40524
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "10899183"
---
# Reiniciar, restablecer o recuperar HoloLens (1.ª generación)

Si tiene problemas con su HoloLens, puede probar reiniciar, restablecer o incluso volver a flashear con el modo recuperación del dispositivo.

Aquí tiene algunas cosas que puede probar si su HoloLens no está funcionando bien.  Este artículo le guiará a través de los pasos de recuperación recomendados en orden.

Si quiere recuperar un HoloLens 2, por favor visite la página para[Recuperación de un HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), ya que hay diferencias en los procesos.

Este artículo se centra en el dispositivo y el software HoloLens, si sus hologramas no se ven bien,[este artículo](hololens-environment-considerations.md) habla de los factores ambientales que mejoran la calidad de los hologramas.

## Reiniciar

### Realizar un reinicio seguro usando Cortana

La forma más segura de reiniciar el HoloLens es usando Cortana. Generalmente este es un primer paso fácil cuando se experimenta un problema con el HoloLens. 

> [!NOTE]
> Cortana no está disponible para todos los dispositivos. Cortana está disponible para todos los dispositivos HoloLens (1 era generación).
> Cortana está disponible en los dispositivos HoloLens 2 en una versión anterior a la actualización de Windows Holograpic, versión 2004.

1. Póngalo en su dispositivo
1. Asegúrese de que esté encendido, que un usuario haya iniciado sesión y que el dispositivo no esté esperando una contraseña para desbloquearlo.
1. Diga "Hey Cortana, reinicio" o "Hey Cortana, reiniciar".
1. Cuando lo reconozca, le pedirá una confirmación. Espere un segundo después de que termine su pregunta hasta escuchar un sonido, indicando que lo está escuchando y luego diga "Sí".
1. El dispositivo se reiniciará ahora.

### Realice un reinicio seguro usando el botón de encendido

Si aún así no puede reiniciar el dispositivo, puede intentarlo con el botón de encendido:

1. Mantenga pulsado el botón de encendido durante cinco segundos.
   1. Después de un segundo, verá que los cinco LEDs se iluminan, y luego se apagan lentamente de derecha a izquierda.
   1. Después de cinco segundos, todos los LEDs se apagarán, indicando que el comando de apagado fue emitido con éxito.
   1. Tenga en cuenta que es importante dejar de pulsar el botón inmediatamente después de que todos los LEDs se hayan apagado.
1. Espere un minuto para que el apagado tenga éxito. Tenga en cuenta que el apagado puede estar en curso incluso si las pantallas están apagadas.
1. Encienda el dispositivo de nuevo presionando y manteniendo el botón de encendido por un segundo.

### Realice un reinicio seguro usando el Portal de dispositivos Windows

> [!NOTE]
> Para ello, el HoloLens tiene que ser configurado como un dispositivo de desarrollo.  
> Obtenga más información acerca del [Portal de dispositivos Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).

Si el procedimiento anterior no funciona, puede intentar reiniciar el dispositivo mediante el[Portal de dispositivos Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal). En la esquina superior derecha, hay una opción para reiniciar o apagar el dispositivo.

### Realice un reinicio forzado inseguro

Si ninguno de los métodos anteriores es capaz de reiniciar con éxito su dispositivo, puede forzar un reinicio. Este método equivale a sacar la batería del HoloLens.  Es una operación peligrosa que puede dejar su dispositivo en un estado corrupto.  Si eso sucede, tendrá que flashear su HoloLens.  

> [!WARNING]
> Se trata de un método potencialmente nocivo y sólo debe utilizarse en caso de que ninguno de los métodos anteriores funcione.

1. Mantenga presionado el botón de encendido por lo menos 10 segundos.
   - Está bien mantener el botón durante más de 10 segundos.
   - Es seguro ignorar cualquier actividad de los LED.
1. Suelte el botón y espere dos o tres segundos.
1. Encienda el dispositivo de nuevo presionando y manteniendo el botón de encendido por un segundo.
Si sigue teniendo problemas, pulse el botón de encendido durante 4 segundos, hasta que todos los indicadores de la batería se apaguen y la pantalla deje de mostrar hologramas. Espere 1 minuto, luego presione el botón de encendido de nuevo para encender el dispositivo.

## Restaurar la configuración de fábrica

> [!NOTE]
> La batería necesita al menos un 40 por ciento de carga para reiniciarse.

Si su HoloLens sigue experimentando problemas después de reiniciar, intente restablecerlo al estado de fábrica.  Al reiniciar su HoloLens se mantiene la versión del software holográfico de Windows que está instalado en él y se reinicia todo lo demás a la configuración de fábrica.

Si restablece el dispositivo, se eliminarán todos los datos personales, las aplicaciones y la configuración, incluido el restablecimiento del TPM. Al reiniciar sólo se instalará la última versión instalada de Windows Holographic y tendrá que rehacer todos los pasos de inicialización (calibrar, conectar a Wi-Fi, crear una cuenta de usuario, descargar aplicaciones, etc.).

1. Inicie la aplicación Ajustes y, a continuación, seleccione **Actualizar** > **Recuperación**.
1. Seleccione la opción**Reiniciar el dispositivo**y lea el mensaje de confirmación.
1. Si acepta reiniciar el dispositivo, éste se reiniciará y mostrará un conjunto de engranajes giratorios con una barra de progreso.
1. Espere unos 30 minutos para que este proceso se complete.
1. El reinicio se completará y el dispositivo se reiniciará en la experiencia listo para usar.

## Reinstale el sistema operativo

Si el dispositivo sigue teniendo un problema después de reiniciar y restaurar, puede utilizar una herramienta de recuperación en su ordenador para reinstalar el sistema operativo y el firmware del HoloLens.  

Todos los datos que el HoloLens necesita para reiniciar están empaquetados en una actualización de Full Flash (ffu).  Esto es similar a un iso, wim o vhd.  [Aprenda sobre los formatos de archivos de imagen FFU.](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Si es necesario, puede instalar un sistema operativo completamente nuevo en su HoloLens (1 era generación) con Windows Device Recovery Tool.

Antes de usar esta herramienta, determine si reiniciando o restableciendo su HoloLens se soluciona el problema. El proceso de recuperación puede llevar algún tiempo.  Cuando termine, se instalará la última versión del software holográfico de Windows aprobado para su HoloLens.

Para usar la herramienta, necesitará un ordenador con Windows 10 o posterior, con al menos 4 GB de espacio de almacenamiento libre.  Tenga en cuenta que no puede ejecutar esta herramienta en una máquina virtual.

### Recupere su HoloLens:

1. Descargue e instale [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) en su ordenador.
1. Conecte HoloLens (1 era generación) a su ordenador con el cable Micro USB que viene con HoloLens.
1. Ejecute Windows Device Recovery Tool y siga las instrucciones.

Si el HoloLens (1 era generación) no se detecta automáticamente, seleccione **Mi dispositivo no fue detectado **y siga las instrucciones para poner su dispositivo en modo de recuperación.

### Manual del modo flasheo:

En el caso de que su dispositivo no sea detectado, por favor utilice el siguiente método para colocarlo manualmente en modo intermitente.

1. Desconecte el dispositivo de todas las fuentes de energía.
1. Si el dispositivo está encendido, por favor mantenga pulsado el botón de encendido hasta que esté completamente apagado.
1. Mantenga presionado el botón de **Subir volumen** y pulse el **botón de Inicio/Apagado**. 
1. El dispositivo debería iniciar y luego mostrar sólo la luz LED del medio.
1. Enchufe el dispositivo en su PC.
1. Ejecute Windows Device Recovery Tool.
1. Tendrá que seleccionar *Mi dispositivo no fue detectado**, y luego seleccione**HoloLens**. 
1. Siga las instrucciones para recuperar su dispositivo.
