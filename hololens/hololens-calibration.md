---
title: Mejorar la calidad visual y la comodidad
description: La calibración de tu IPD (distancia interpupilar) puede mejorar la calidad de tu elementos visuales. Tanto HoloLens como los cascos envolventes con micrófono de Windows Mixed Reality ofrecen formas de personalizar la IPD.
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
keywords: calibración, comodidad, elementos visuales, calidad, ipd
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 627631ee7070af6cb6c60e91890f05472ce0f6be
ms.sourcegitcommit: 8b56f4b9b5f9c928fc361f18efcbea729055a0b2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2020
ms.locfileid: "10919161"
---
# Mejorar la calidad visual y la comodidad

HoloLens 2 y HoloLens (1.ª generación) funcionan mejor cuando se han calibrado a tu ojos en concreto.

Aunque ambos dispositivos necesitan calibrarse para lograr la mejor experiencia de visualización de hologramas, usan tecnologías y técnicas de calibración diferentes.  Saltar a la [calibración de HoloLens 2](#calibrating-your-hololens-2) o a la [calibración de HoloLens (1.ª generación)](#calibrating-your-hololens-1st-gen).

## Calibrar HoloLens 2

HoloLens 2 usa la tecnología de seguimiento ocular para mejorar tu experiencia de visualización e interacción con el entorno virtual. La calibración de HoloLens 2 garantiza que pueda realizar un seguimiento exacto de tus ojos (y de los ojos de cualquier otra persona que use el dispositivo). También ayuda a la comodidad del usuario, a la alineación de los hologramas y al seguimiento con las manos. Tras la calibración, los hologramas aparecerán correctamente incluso a medida que el visor se desplace en tu cabeza.

HoloLens 2 pide a un usuario que calibre el dispositivo en las siguientes circunstancias:

- El usuario está usando el dispositivo por primera vez
- El usuario optó previamente por el proceso de calibración
- El proceso de calibración no se realizó correctamente la última vez que el usuario usó el dispositivo
- El usuario ha eliminado sus perfiles de calibración
- El dispositivo se quita y se vuelve a poner y cualquiera de las circunstancias anteriores se aplican 


![Aviso de calibración](./images/07-et-adjust-for-your-eyes.png)

Durante este proceso, veremos un conjunto de objetivos (gemas). Está bien si parpadea durante la calibración, pero trate de mantenerse enfocado en las gemas en lugar de otros objetos en la habitación.  Esto permite a HoloLens memorizar la posición de tu ojo para representar tu mundo holográfico.

![Aviso de calibración](./images/07-et-hold-head-still.png)

![Aviso de calibración](./images/08-et-gems.png)

![Aviso de calibración](./images/09-et-adjusting.png)

Si la calibración se realizó correctamente, verás una pantalla de operación correcta.  De lo contrario, lee más información sobre cómo diagnosticar errores de calibración [aquí](#troubleshooting-hololens-2-calibration).

![Aviso de calibración](./images/10-et-success.png)

### Calibración al compartir un dispositivo o una sesión

Varios usuarios pueden compartir un dispositivo HoloLens 2, sin necesidad de que cada persona pase por la configuración del dispositivo. Cuando un nuevo usuario se pone el dispositivo en la cabeza por primera vez, el HoloLens 2 le pide automáticamente que calibre las imágenes. Cuando un usuario que ha calibrado anteriormente elementos visuales se coloca el dispositivo en la cabeza, la pantalla se ajusta perfectamente para lograr una buena calidad y una experiencia de visualización cómoda.  

### Iniciar manualmente el proceso de calibración

1. Usa el gesto Inicio para abrir el [menú **Inicio**](hololens2-basic-usage.md#start-gesture).
1. Si la aplicación Configuración no está anclada a **Inicio**, selecciona **Todas las aplicaciones**.
1. Selecciona **Configuración**y, a continuación, **Sistema** > **Calibración** > **Calibración ocular** > **Ejecutar calibración ocular**.

   ![La aplicación Configuración, que muestra la opción Ejecutar calibración ocular](./images/C-Settings.Calibration.png)

### Solución de problemas de calibración de HoloLens 2

La calibración debería funcionar para la mayoría de los usuarios, pero hay casos en los que se produce un error en la calibración.
  
Entre los posibles motivos para un error de calibración se incluyen:

- El usuario se distrae y no sigue los objetivos de calibración
- El visor del dispositivo está sucio o arañado, o el visor del dispositivo no está colocado correctamente
- Gafas sucias o arañadas
- Determinados tipos de gafas y lentes de contacto (lentes de contacto coloreadas, algunos lentes de contacto tóricas, gafas de bloqueo de infrarrojos, algunos gafas de alta graduación, gafas de sol o similares)
- Maquillaje más pronunciado y algunas extensiones de pestañas
- Pelo o monturas gruesas si impiden que el dispositivo te vea los ojos
- Determinadas fisiologías oculares, afecciones de la vista o cirugías oculares, como ojos estrechos, pestañas largas, ambliopía, nistagmo, algunos casos de LASIK u otras cirugías oculares

Si la calibración no se ha realizado correctamente, prueba lo siguiente:

- Limpiar el visor del dispositivo
- Limpiar tus gafas
- Empujar el visor del dispositivo tan cerca de los ojos como sea posible.
- Quitar los objetos del visor (por ejemplo, el pelo)
- Encender una luz de la habitación o sacarlo de la luz solar directa

Si ha seguido todas las instrucciones y la calibración sigue fallando, puede desactivar el aviso de calibración en Ajustes. Por favor, también háganos saber enviando sus comentarios a el [Centro de comentarios](hololens-feedback.md).

Consulte también la información relacionada con [la resolución de problemas con el color o el brillo de imágenes.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Tenga en cuenta que la configuración de IPD no es válida para Hololens 2, ya que el sistema calcula las posiciones del ojo. 

### Seguridad y datos de calibración

La información de calibración se almacena localmente en el dispositivo y no está asociada a ningún tipo de información de la cuenta. No hay ningún registro de quién ha usado el dispositivo sin calibración. Esto significa que a los usuarios nuevos se les pedirá que calibren los elementos visuales cuando usen el dispositivo por primera vez, así como los usuarios que hayan optado por no realizar la calibración anteriormente o si la calibración no se realizó correctamente.

El dispositivo puede almacenar localmente hasta 50 perfiles de calibración. Cuando se alcanza este número, el dispositivo borra automáticamente el perfil más antiguo no utilizado.

La información de calibración siempre puede eliminarse del dispositivo en **Configuración** > **Privacidad** > **Seguimiento ocular**.  

### Deshabilitar calibración

También puedes deshabilitar el aviso de calibración siguiendo estos pasos:

1. Selecciona **Configuración** > **Sistema** > **Calibración**.
1. Desactive la opción **Cuando otra persona use este HoloLens, pedir automáticamente la ejecución de la calibración ocular**.

> [!IMPORTANT]
> Esta configuración puede afectar negativamente a la calidad y comodidad de la representación de los hologramas.  Cuando desactivas esta opción, las características que dependen del seguimiento ocular (como el desplazamiento de texto) ya no funcionan en las aplicaciones inmersivas.

### Tecnología de seguimiento ocular de HoloLens 2

El dispositivo usa su tecnología de seguimiento ocular para mejorar la calidad de la visualización y para garantizar que todos los hologramas están colocados de manera precisa y cómoda para verlos en 3D. Dado que usa los ojos como puntos de referencia, el dispositivo puede ajustarse para cada usuario y ajustar sus elementos visuales, ya que el casco cambia ligeramente durante el uso.  Todos los ajustes se producen sobre la marcha sin necesidad de ajustes manuales.
> [!NOTE]
> El establecimiento de IPD no es aplicable para Hololens 2, ya que el sistema calcula las posiciones del ojo.

Las aplicaciones de HoloLens usan seguimiento ocular para hacer un seguimiento de dónde miras en tiempo real. Esta es la capacidad principal que los desarrolladores pueden aprovechar para habilitar un nivel completamente nuevo de contexto, comprensión humana e interacciones dentro de la experiencia holográfica. Los desarrolladores no tienen que hacer nada para aprovechar esta funcionalidad.

## Calibración de tu HoloLens (1.ª generación)

HoloLens (1.ª generación) ajusta la visualización de hologramas según la [distancia interpupilar](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD). Si la IPD no es precisa, los hologramas pueden aparecer inestables o a una distancia incorrecta. Para mejorar la calidad de los elementos visuales, calibra el dispositivo para la distancia interpupilar (IPD).

Cuando configuras tu dispositivo Hololens (1.ª generación), te pide que calibres los elementos visuales después de que Cortana se presente. Se recomienda completar el paso de calibración durante esta fase de configuración. Sin embargo, puedes omitirlo esperando hasta que Cortana te pregunte y luego decir "Omitir".

Durante el proceso de calibración, HoloLens te pide que alinees el dedo con una serie de seis objetivos por ojo. HoloLens usa este proceso para establecer la IPD correctamente para los ojos.

![Pantalla de alineación de dedos de IPD en el segundo paso](./images/ipd-finger-alignment-300px.jpg)

### Iniciar manualmente el proceso de calibración

Si necesitas actualizar la calibración o si un nuevo usuario necesita ajustarla, puedes ejecutar manualmente la aplicación Calibración en cualquier momento. La aplicación Calibración se instala de forma predeterminada. Para obtener acceso a ella, usa el menú **Inicio** o la aplicación Configuración.

Para usar el menú **Inicio** para ejecutar la aplicación Calibración, sigue estos pasos:

1. Usa el gesto de la [eclosión](hololens1-basic-usage.md) para abrir el menú **Inicio**.
1. Para ver todas las aplicaciones, selecciona **+**.
1. Selecciona **Calibración**.

![Acceso a la aplicación de calibración desde el shell](./images/calibration-shell.png)

![La aplicación de calibración se muestra como un cubo en vivo después de iniciarse](./images/calibration-livecube-200px.png)

Para usar la aplicación Configuración para que ejecute la aplicación Calibración, sigue estos pasos:

1. Usa el gesto de [eclosión](hololens1-basic-usage.md) para abrir el menú **Inicio**.
1. Si **Configuración** no está anclada a **Inicio**, selecciona **+** para ver todas las aplicaciones.
1. Selecciona **Configuración**.
1. Selecciona **Sistema** > **Utilidades** > **Abrir calibración**.

![Iniciar la aplicación de calibración desde la aplicación de configuración](./images/calibration-settings-500px.jpg)

## Cascos envolventes

Algunos cascos envolventes ofrecen la posibilidad de personalizar la configuración de IPD. Para cambiar la IPD para tu casco, abre la aplicación Configuración y selecciona **Realidad mixta** > **Visualización de los auriculares** y, a continuación, mueve el control deslizante. Verás los cambios en tiempo real en tu casco. Si conoces tu IPD, quizás de una visita al optometrista, también puedes introducirlo directamente.

También puedes ajustar esta configuración en tu PC seleccionando **Configuración** > **Realidad mixta** > **Visualización de los auriculares**.

Si tu casco no admite la personalización de IPD, esta configuración se deshabilitará.
