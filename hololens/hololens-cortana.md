---
title: Usar tu voz para funcionar con HoloLens
description: Descubre cómo Cortana puede ayudarte a hacer todo tipo de cosas en los dispositivos de realidad mixta de HoloLens, como dar comandos con tu voz, dictar e interactuar con hologramas.
ms.assetid: fd96fb0e-6759-4dbe-be1f-58bedad66fed
ms.date: 03/10/2020
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
audience: ITPro
ms.author: v-tea
ms.topic: article
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f6e3dd8f7dc90cea158d000251973ec75dc76a90
ms.sourcegitcommit: 07ffe1bf2f45dcb2ba9d7fbe54b4773a0fb9d525
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393874"
---
# <a name="use-your-voice-to-operate-hololens"></a>Usar tu voz para funcionar con HoloLens

Puedes usar tu voz para hacer casi cualquier cosa en HoloLens, como hacer una foto rápida o abrir una aplicación. Muchos comandos de voz están integrados en HoloLens, mientras que otros están disponibles a través de Cortana.

Este artículo te enseña cómo controlar HoloLens y tu mundo holográfico con tu voz y con Cortana.

> [!NOTE]
> La voz solo se admite en [algunos idiomas](hololens2-language-support.md). El idioma de voz se basa en el idioma para mostrar de Windows, no en el idioma del teclado.  
>  
> Para verificar el idioma para mostrar de Windows, selecciona **Configuración** > **Hora e idioma** > **Idioma**.

## <a name="built-in-voice-commands"></a>Comandos de voz integrados

Desplázate más rápidamente por HoloLens con estos comandos básicos. Para poder utilizarlos, es necesario habilitar la voz durante la primera ejecución del dispositivo o en**Configuraciones** > **Privacidad** > **Voz**. Siempre puede comprobar si la voz está activada mirando el estado en la parte superior del menú Inicio. Para obtener los mejores resultados de reconocimiento de voz, HoloLens 2 utiliza los servicios basados en la nube de Microsoft. Sin embargo, puede utilizar configuración para desactivar esta función. Para hacer esto, en Configuraciones, desactive**Reconocimiento de voz en línea**. Después de cambiar esta configuración, el HoloLens 2 sólo procesará los datos de voz localmente para reconocer los comandos y el dictado, y Cortana no estará disponible.

### <a name="general-speech-commands"></a>Comandos de voz generales

Usa estos comandos en Windows Mixed Reality para moverte con mayor rapidez. Algunos comandos usan el cursor de mirada, que usted activa al decir "seleccionar".

> [!NOTE]
> No se admiten los rayos de mano en HoloLens (1.ª generación).

| Di esto | Para |
| - | - |
| "Seleccionar" | Di "seleccionar" para que aparezca el cursor de mirada. Luego, gire la cabeza para posicionar el cursor en la cosa que quiera seleccionar, y diga "seleccionar" nuevamente. |
| "Ir a Inicio" |  Abrir el menú Inicio |
| "Cerrar"  | Cerrar el menú Inicio |
| Diga "Ir a Inicio" para que aparezca el menú de acciones rápidas y luego diga "Ambiente principal".  | Salir de una aplicación inmersiva |
| "Ocultar haz de mano"/"Mostrar haz de mano" | Ocultar y mostrar haz de mano |
| "¿Qué puedo decir?"  | Ver los comandos de voz disponibles |

A partir de la versión 19041.x de HoloLens 2, también puede usar estos comandos:

| Di esto | Para |
| - | - |
| "Reiniciar dispositivo" | Ver un cuadro de diálogo para confirmar que quieres reiniciar el dispositivo; puedes decir "sí" para reiniciar |
| "Apagar dispositivo" | Ver un cuadro de diálogo para confirmar que quieres desconectar el dispositivo; puedes decir "sí" para confirmar |
| "Aumentar brillo/reducir brillo" | Aumentar o reducir el brillo de la pantalla un 10 % |
| "Subir/bajar volumen" | Aumentar o reducir el volumen un 10 % |
| "¿Cuál es mi IP?" | Ver un cuadro de diálogo en el que se muestra la dirección IP actual del dispositivo en la red local |
| "Haz una foto/Toma una foto" | Capturar una foto de realidad mixta de lo que estás viendo actualmente |
| "Graba un vídeo/Inicia la grabación/Inicia la grabación de vídeo" | Empezar a grabar un vídeo de realidad mixta | 
| "Detén el vídeo/Detén la grabación/Detén la grabación de vídeo" | Detener la grabación de vídeo de realidad mixta actual si hay alguna en curso |

### <a name="hologram-commands"></a>Comandos de holograma

Para usar estos comandos, mira fijamente a un objeto 3D, un holograma o una ventana de la aplicación.

| Di esto | Para |
| - | - |
| "Más grande" | Aumentar el tamaño |
| "Más pequeño" | Reducir el tamaño |
| "Orientar hacia mí" | Orientarlo hacia ti |
| "Mover esto" | Moverlo (seguir tu mirada) |
| "Cerrar" | Cerrarlo |
| "Sígueme" / "Deja de seguirme" | Hacer que te siga al moverte |

### <a name="see-it-say-it"></a>Ver, decir

Muchos botones y otros elementos de HoloLens también responden a tu voz, por ejemplo, **Seguirme** y **Cerrar** de la barra de aplicaciones o el botón **Atrás** de Edge. Para averiguar si un botón está habilitado para voz, coloque el **cursor de la mirada**, el **cursor táctil** o un **haz de mano** en él durante un momento. Si el botón está habilitado para voz, verá una sugerencia de voz.

### <a name="dictation-mode"></a>Modo de dictado

¿Estás cansado de escribir? Cambie al modo de dictado en cualquier momento en que el teclado holográfico esté activo. Para empezar, seleccione el botón del micrófono o diga "Iniciar dictado". Para dejar de dictar, selecciona el botón nuevamente o di "Termina dictado". Para eliminar lo que acabas de dictar, di "Eliminar eso". 

> [!NOTE]
> Para usar el modo dictado, debes tener una conexión a Internet.

El dictado de HoloLens usa la puntuación explícita, lo que significa que dices el nombre de la puntuación que quieres usar. Por ejemplo, puedes decir "Hola **coma** qué haces **signo de interrogación**."

Estas son las palabras clave de puntuación que puedes usar:

- Punto, coma, signo de interrogación, signo de exclamación/signo de exclamación
- Nueva línea/nuevo párrafo
- Punto y coma, dos puntos
- Abrir comillas, cerrar comillas
- Hashtag, sonrisa/cara sonriente, enfado, guiño
- Dólar, porcentaje

A veces es útil deletrear cosas como las direcciones de correo electrónico. Por ejemplo, para dictar ejemplo@outlook.com, deberás decir "E J E M P L O arroba outlook punto com".

## <a name="do-more-with-cortana"></a>Haz más con Cortana

Cortana puede ayudarte a hacer todo tipo de cosas en HoloLens, pero según la versión de Windows Holographic que estés usando, las capacidades pueden ser diferentes. Puedes obtener más información sobre las funcionalidades actualizadas de la última versión de Cortana aquí: [Cortana en la próxima versión de Windows 10: centrada en tu productividad con seguridad y privacidad mejoradas](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/). 

![Hola Cortana.](images/cortana-on-hololens.png)

Estas son algunas de las cosas que puedes intentar decir (recuerda decir "Hola Cortana" primero).

**Hola, Cortana**...

- ¿Qué puedo decir?
- Inicia <*nombre de aplicación*>.
- ¿Qué hora es?
- Muéstrame los últimos resultados de la NBA.
- Cuéntame un chiste.

Si usas la *versión 18362.x o una anterior*, también puedes usar estos comandos:

**Hola, Cortana**...

- Subir el volumen.
- Disminuir el brillo.
- Apagar.
- Reiniciar.
- Ir a suspensión.
- Silenciar.
- Mueve <*nombre de aplicación*> aquí (mira al lugar al que quieres mover la aplicación).
- Ir a Inicio.
- Tomar una imagen.
- Iniciar grabación. (Inicia la grabación de un vídeo).
- Detener grabación. (Detiene la grabación de un vídeo).
- ¿Cuánta batería me queda?

Algunas características de Cortana a las que estás acostumbrado desde Windows en tu PC o teléfono (por ejemplo, avisos y notificaciones) no están admitidas en Microsoft HoloLens y la experiencia de Cortana puede variar de una región a otra.

### <a name="turn-cortana-off"></a>Desactivar Cortana

Cortana está activada la primera vez que usas HoloLens al habilitar la voz. Puedes desactivarla en la configuración de Cortana. En la lista **Todas las aplicaciones**, Seleccionar **Cortana** > **Configuración**. A continuación, desactívala. Cortana puede ofrecerte sugerencias, ideas, avisos, alertas y mucho más.

Si Cortana no responde a "Hola Cortana", comprueba que la voz está habilitada en Inicio, ve a la configuración de Cortana y comprueba que está activada.
