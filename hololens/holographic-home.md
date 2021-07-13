---
title: Uso del menú Inicio y el ambiente principal
description: Aprenda a usar el menú Inicio, a administrar y acceder a aplicaciones, y a navegar por el ambiente principal en dispositivos HoloLens.
ms.assetid: 742bc126-7996-4f3a-abb2-cf345dff730c
ms.date: 08/07/2019
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 66271911a4692dea89b6338cc8c77a05dfcaae1d
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397396"
---
# <a name="use-the-start-menu-and-mixed-reality-home"></a>Uso del menú Inicio y el ambiente principal

Al igual que la experiencia de un equipo Windows empieza con el escritorio, Windows Holographic comienza con un ambiente principal.  Con el menú Inicio puede abrir y colocar ventanas de aplicaciones, iniciadores de aplicaciones inmersivas y contenido 3D en el ambiente principal y s ubicación se recordará en el espacio físico.

## <a name="use-the-start-menu"></a>Uso del menú Inicio

En el menú Inicio de HoloLens es donde se abren las aplicaciones, se ve información de estado importante y se accede a herramientas como la cámara.

Dondequiera que esté en HoloLens, siempre podrá abrir el menú Inicio con el **gesto Inicio**.  En HoloLens (1.ª generación), el gesto Inicio es [eclosionar](https://support.microsoft.com/help/12644/hololens-use-gestures). En HoloLens 2, el [gesto Inicio](hololens2-basic-usage.md#start-gesture) es pulsar el icono de inicio que aparece en la muñeca.  También puede abrir el menú Inicio con su voz diciendo "Ir a Inicio".

> [!TIP]
> Cuando se abra el menú Inicio, use el gesto Inicio para cerrarlo o mire hacia el menú Inicio y diga "Cerrar".

En la parte superior del menú Inicio, verá indicadores de estado para Wi-Fi, batería, volumen y un reloj. En HoloLens 2, también hay un indicador de escucha que muestra si el dispositivo está habilitado para voz y está escuchando comandos de voz. En la parte inferior encontrará los botones **Foto** y **Vídeo** que le permiten realizar fotografías y grabaciones de vídeo.  También hay un botón **Conectar** que permite proyectar lo que se ve en otro dispositivo con Miracast.

### <a name="find-apps-on-start-menu"></a>Búsqueda de aplicaciones en el menú Inicio

El menú Inicio tiene una lista de **aplicaciones ancladas** y una lista de **todas las aplicaciones**.

- La lista de **aplicaciones ancladas** muestra las aplicaciones que se han anclado. Puede agregar y quitar aplicaciones de esta lista mediante el menú contextual que aparece al **seleccionar y mantener presionado** un icono de la aplicación.

- En la lista de **todas las aplicaciones** se muestran todas las aplicaciones instaladas en el dispositivo.  Seleccione el botón **Todas las aplicaciones** en el lado derecho del menú **Inicio** para llegar a la lista.

En ambas listas de aplicaciones, use los botones **Página anterior** y **Página siguiente** del lado derecho del menú Inicio para desplazarse por todas las aplicaciones de la lista.  Ambas listas de aplicaciones se abrirán automáticamente en la página que se usó por última vez durante una sesión de dispositivo.

> [!TIP]
> En HoloLens 2, puede desplazarse directamente por las listas de aplicaciones con el dedo índice. Solo tiene que tocar la lista con la punta del dedo y arrastrar hacia arriba o hacia abajo.

### <a name="open-apps-from-start-menu"></a>Apertura de aplicaciones desde el menú Inicio

Para abrir una aplicación desde el menú Inicio, simplemente **seleccione** un **icono de aplicación**. También puede decir el nombre de una aplicación para abrirla.

Al abrir una aplicación desde el menú Inicio, se producirá una de las siguientes situaciones, en función de cómo esté diseñada la aplicación:

- Se coloca una **ventana de aplicación**. A continuación, la aplicación se carga en la ventana y puede usarla como una pantalla táctil.
- Se coloca un **iniciador de aplicaciones 3D** para una aplicación inmersiva. A continuación, debe **seleccionar** el iniciador para abrir la aplicación inmersiva.
- Se coloca una ventana de aplicación que actúa como **iniciador** para una aplicación inmersiva. A continuación, la aplicación inmersiva se iniciará automáticamente.

Las ventanas de aplicaciones y los iniciadores de aplicaciones colocados en el ambiente principal permanecerán hasta que decida quitarlos.  Proporcionan un cómodo acceso directo para usar esas ventanas de aplicaciones o para iniciar aplicaciones inmersivas sin tener que abrirlas de nuevo en el menú Inicio. 

> [!NOTE]
>Como en un teléfono, los recursos del sistema se administran automáticamente en HoloLens.  Por ejemplo, al abrir una nueva aplicación inmersiva, todas las demás aplicaciones en ejecución pasar a estar inactivas de inmediato. No es necesario quitar ventanas de aplicaciones e iniciadores del ambiente principal para liberar recursos del sistema. 

## <a name="using-apps-on-hololens"></a>Uso de aplicaciones en el dispositivo HoloLens

Las aplicaciones en el dispositivo HoloLens pueden usar la vista de ventana de aplicación o la vista envolvente. Con la vista de ventana de aplicación, la aplicación simplemente muestra su contenido dentro de una ventana. Con la vista envolvente, la aplicación le saca del ambiente principal a donde pueda mostrar su contenido en el entorno físico que tiene a su alrededor. Las aplicaciones también pueden elegir usar ambas vistas.

### <a name="use-app-windows"></a>Uso de ventanas de aplicación

En HoloLens (1.ª generación), las ventanas de aplicación se colocan y usan en el ambiente principal, donde se pueden [mover, cambiar de tamaño y girar](hololens1-basic-usage.md#move-resize-and-rotate-apps) como se desee. Además de usar las ventanas de aplicación con miradas y gestos, también puedes usarlas con mouse y teclado conectados por Bluetooth.

En HoloLens 2, además de usar las ventanas de aplicación en el ambiente principal, también puede usar una ventana de aplicación a la vez dentro de una aplicación inmersiva. También puede poner una ventana de aplicación en el modo **Sígueme**, donde permanecerá delante de uno mientras se desplaza. Al abrir una ventana de aplicación desde dentro de una aplicación inmersiva, se abrirá automáticamente en modo **Sígueme**. Puede [mover, cambiar de tamaño y girar](hololens2-basic-usage.md#move-resize-and-rotate-holograms) las ventanas de aplicación directamente con las manos tanto en el ambiente principal como dentro de una aplicación inmersiva.

> [!NOTE]
>
> - Puede haber hasta tres ventanas de aplicación activas en el ambiente principal a la vez. Se pueden abrir más, pero solo tres permanecerán activas.
> - Cuando una ventana de aplicación no esté activa, mostrará su contenido con un aspecto oscurecido en comparación con una ventana activa.  Algunas simplemente mostrarán el icono de la aplicación en lugar de contenido.  Para activar una ventana inactiva, solo tiene que **seleccionarla**.
> - Cada aplicación abierta puede tener una ventana activa a la vez, excepto Microsoft Edge, que puede tener hasta tres.

### <a name="close-apps"></a>Cierre de aplicaciones

Para cerrar una aplicación que usa una ventana de aplicación, simplemente cierre esta ventana con el botón **Cerrar** de la barra de título.  También puede mirar la ventana y decir "Cerrar".

Para salir de una aplicación que usa la vista envolvente, use el gesto Inicio para mostrar el **menú Inicio** y, a continuación, seleccione el botón **Ambiente principal**.

Si una aplicación inmersiva se encuentra en un estado interrumpido y necesita reiniciarla, puede asegurarse de que la aplicación se apaga por completo cerrando su selector en el ambiente principal y, a continuación, iniciarla desde el menú Inicio.

### <a name="default-app-picker"></a>Selector de aplicaciones predeterminadas

Con [Windows Holographic, versión 21H1](hololens-release-notes.md#windows-holographic-version-21h1), al activar un hipervínculo o abrir un tipo de archivo con más de una aplicación instalada que lo admita, verá que se abre una nueva ventana en la que se le pedirá que seleccione qué aplicación instalada debe controlar el tipo de archivo o vínculo. En esta ventana, también puede elegir que la aplicación seleccionada controle el tipo de archivo o vínculo "Una vez" o "Siempre".

![Ventana del selector de aplicaciones](images/default-app-picker.png)

Si elige "Siempre" pero más adelante quiere cambiar la aplicación que controla un tipo de archivo o vínculo determinado, puede restablecer los valores predeterminados guardados en **Configuración > Aplicaciones**. Desplácese hasta la parte inferior de la página y seleccione el botón **Borrar** en "Default apps for file types" (Aplicaciones predeterminadas para tipos de archivos) o "Default apps for link types" (Aplicaciones predeterminadas para tipos de vínculos). A diferencia de la configuración similar en equipos de escritorio, no se pueden restablecer los valores predeterminados de un tipo de archivo individual.

### <a name="per-app-volume-control"></a>Control de volumen por aplicación

Con [Windows Holographic, versión 21H1](hololens-release-notes.md#windows-holographic-version-21h1), los usuarios pueden ajustar manualmente el nivel de volumen de cada aplicación. Esto permite a los usuarios centrarse mejor en las aplicaciones que lo necesitan o escuchar mejor cuando usan varias aplicaciones. Por ejemplo, cuando se tiene que bajar el volumen de una aplicación mientras se llama a alguien para conseguir asistencia remota en otra.

Para establecer el volumen de una aplicación individual, vaya a **Configuración** -> **Sistema** -> **Sonido** y en Advanced sound options (Opciones avanzadas de sonido), seleccione **App volume and device preferences** (Volumen de la aplicación y preferencias del dispositivo).

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

## <a name="related-info"></a>Información relacionada

[Encontrar, instalar y desinstalar aplicaciones de Microsoft Store](holographic-store-apps.md)
