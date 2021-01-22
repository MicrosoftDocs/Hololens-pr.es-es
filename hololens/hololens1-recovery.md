---
title: Reinicie, restablezca o recupere el HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
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
ms.openlocfilehash: f0aa400be56d09a843a1b7c9bae78346551ad8af
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283921"
---
# Reiniciar, restablecer o recuperar HoloLens (1.ª generación)

Si tiene problemas con su HoloLens, puede probar a reiniciar, restablecer o incluso volver a flashearlo con el modo de recuperación del dispositivo. Este artículo le guiará por los pasos de recuperación recomendados.

Si desea recuperar un HoloLens 2, consulte [Recuperar un HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), ya que el proceso es distinto.

> [!NOTE]
> Este artículo se centra en el dispositivo y el software de HoloLens. Si el holograma no se muestra correctamente, vea **[Consideraciones de entorno de HoloLens](hololens-environment-considerations.md)** para obtener información sobre los factores que mejoran la calidad del holograma.

## Reiniciar

### Reinicie de manera segura con Cortana

El modo más seguro de reiniciar HoloLens es usando Cortana y, por lo general, es lo primero que puede probar a hacer cuando tenga un problema con HoloLens.

> [!NOTE] 
> Cortana no está disponible para todos los dispositivos.
> - Cortana está disponible para todos los dispositivos HoloLens (1 era generación). 
> - Cortana está disponible en los dispositivos HoloLens 2 en una versión anterior a la actualización de Windows Holograpic, versión 2004.

1. Active su HoloLens.
1. Asegúrese de que un usuario haya iniciado sesión y que el dispositivo no esté esperando una contraseña para desbloquearlo.
2. Diga "Hey Cortana, reinicio" o "Hey Cortana, reiniciar".
3. Cortana responderá y le pedirá confirmación. Espere a que se reproduzca un sonido después de la pregunta y, entonces, diga "sí". El dispositivo se reiniciará.

### Usar el botón de encendido para reiniciar de manera segura

Si aún así no puede reiniciar el dispositivo, inténtelo con el botón **de encendido**:

1. Mantenga pulsado el botón **de encendido** durante 5 segundos. Al cabo de 1 segundo se iluminarán los cinco LED y, a continuación, se apagarán lentamente de uno en uno y de derecha a izquierda. Al cabo de 5 segundos, todos los LED estarán apagados, lo que indica que el dispositivo se ha apagado correctamente.
      
   > [!IMPORTANT]
   > Deje de pulsar el botón inmediatamente después de que todos los LED se hayan apagado.
1. Espere 1 minuto hasta que se apague por completo. El apagado puede estar en curso incluso después de que se apaguen las pantallas.
2. Encienda el dispositivo de nuevo manteniendo pulsado el botón **de encendido** durante 1 segundo.

### Reinicie de manera segura con el Portal de dispositivos Windows

> [!NOTE]
> Para este proceso, se tiene que configurar el HoloLens como un dispositivo de desarrollo. Obtenga más información en el [Portal de dispositivos Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).

Si no funcionó el procedimiento anterior, puede intentar reiniciar el dispositivo mediante el[Portal de dispositivos Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal). En la esquina superior derecha, encontrará la opción para reiniciar o apagar el dispositivo.

### Reiniciar de manera forzosa y no segura

Si los métodos anteriores no reiniciaron su HoloLens, fuerce un reinicio. Este método equivale a quitar y volver a instalar la batería. Es peligroso porque podría dañar el dispositivo. Si eso sucede, tendrá que flashear su HoloLens.  

> [!WARNING]
> Se trata de un método potencialmente nocivo y únicamente se debe utilizar en el caso de que ninguno de los métodos anteriores funcione.

1. Mantenga presionado el botón **de encendido** por lo menos 10 segundos.
   - Está bien mantener el botón durante más de 10 segundos.
   - Es seguro ignorar cualquier actividad de los LED.
1. Suelte el botón y espere de 2 a 3 segundos.
1. Mantenga pulsado el botón **de encendido** durante 1 segundo.
1. Si sigue teniendo problemas, pulse el botón **de encendido** durante 4 segundos, hasta que todos los indicadores de la batería se atenúen y la pantalla deje de mostrar hologramas. Espere 1 minuto, luego presione de nuevo el botón **de encendido** para encender el dispositivo.

## Restaurar la configuración de fábrica

> [!NOTE]
> La batería necesita al menos un 40% de carga para reiniciarse.

Si HoloLens sigue teniendo algún problema, pruebe a restablecerlo en estado de fábrica. Este paso mantiene la versión del software holográfico de Windows que lleva instalado y reinicia todo lo demás a la configuración de fábrica.

>[!WARNING]
> Si restablece el dispositivo, se eliminarán todos los datos personales, las aplicaciones y la configuración, incluida la información para restablecer el TPM. Si restablece, se instalará únicamente la versión más reciente del software holográfico de Windows. Tendrá que rehacer todos los pasos de inicialización (calibrar, conectarse a una red Wi-Fi, crear una cuenta de usuario, descargar aplicaciones, etc.).

1. Abra la aplicación Ajustes y, a continuación, seleccione **Actualizar** > **Recuperación**.
1. Seleccione la opción**Reiniciar el dispositivo**y lea el mensaje de confirmación.
1. Confirme el restablecimiento. El dispositivo se reiniciará y mostrará un conjunto de engranajes giratorios y una barra de progreso.
1. Espere unos 30 minutos para que este proceso se complete. Cuando haya acabado, el dispositivo se reiniciará en la experiencia «listo para usar».

## Reinstalar el sistema operativo

Si el dispositivo sigue teniendo algún problema después de reiniciar y restaurar, puede utilizar una herramienta de recuperación en su ordenador para reinstalar el sistema operativo y el firmware del HoloLens.  

Los datos que HoloLens necesita para el restablecimiento se empaquetan en formato Full Flash Update (FFU), que es similar a un archivo ISO, WIM o VHD. [Aprenda sobre los formatos de archivos de imagen FFU.](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Puede instalar un sistema operativo nuevo en su HoloLens (1 era generación) con la herramienta de migración para recuperación de copias de seguridad (Windows Device Recovery Tool). Antes de usar esta herramienta, determine si reiniciando o restableciendo su HoloLens se soluciona el problema.

El proceso de recuperación puede tardar un poco. Cuando termine, se instalará la última versión del software holográfico de Windows.

Para usar la herramienta, necesita un ordenador con Windows 10, o posterior, con al menos 4 GB de espacio de almacenamiento libre. No puede ejecutar esta herramienta en una máquina virtual.

### Recuperar el HoloLens

1. Descargue e instale [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) en su ordenador.
1. Utilice el cable Micro USB que viene con HoloLens (1 era generación) para conectarlo a su ordenador.
1. Abra Windows Device Recovery Tool y siga las instrucciones.

Si no se detecta automáticamente el HoloLens (1 era generación), seleccione **Mi dispositivo no fue detectado**. Después, siga las instrucciones para poner el dispositivo en modo de recuperación.

### Modo flasheo manual

Si no se detecta el dispositivo, siga estos pasos para ponerlo manualmente en modo flasheo:

1. Desconecte el dispositivo de cualquier fuente de energía.
1. Si el dispositivo está encendido, mantenga pulsado el botón **de encendido** hasta que se apague por completo.
2. Mantenga presionado el botón de **subir volumen** y pulse el botón **de encendido**. El dispositivo debería iniciarse y mostrar solo la luz LED del medio.
3. Enchufe el dispositivo en su PC.
4. Abra Windows Device Recovery Tool.
5. Seleccione **Mi dispositivo no fue detectado** y, a continuación, **HoloLens**. 
6. Siga las instrucciones para recuperar su dispositivo.
