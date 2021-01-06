---
title: Instrucciones para contribuir
description: Obtén información sobre cómo contribuir a los documentos de HoloLens en la plataforma de docs.microsoft.com usando Markdown con modo GitHub.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: 311da6bc52098d5ba16e4684f68fec9a01e7c23b
ms.sourcegitcommit: 8cea4c04c6d2e22225f4de43e10c05dab840736a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "11253868"
---
# Contribución a la documentación de HoloLens

Bienvenido a la [documentación de HoloLens](https://github.com/MicrosoftDocs/Hololens). Todos los artículos que cree o edite en este repositorio serán **visibles para el público.** 

Los documentos de HoloLens se muestran en la plataforma docs.microsoft.com, que usa Markdown con modo de GitHub con características de Markdig. El contenido que edite en este repositorio se vuelve a dar formato a páginas estilizadas que se muestran en https://docs.microsoft.com/hololens . 

Esta página cubre los pasos básicos y las pautas para la contribución y los vínculos a los conceptos básicos de Markdown. Gracias por su contribución.

## Repos disponibles

| Nombre del repositorio | Dirección URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Realidad mixta | [MicrosoftDocs/Mixed-Reality](https://docs.microsoft.com/windows/mixed-reality) |
| Guía de entusiastas de VR | [MicrosoftDocs/Mixed-Reality/entusiasta-guía](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## Antes de empezar

Si aún no tiene una cuenta, tendrá que [crear una cuenta de github](https://github.com/join).

>[!NOTE]
>Si es un empleado de Microsoft, vincule su cuenta de GitHub al alias de Microsoft en el [portal de origen abierto de Microsoft](https://repos.opensource.microsoft.com/). Únase a las organizaciones **"Microsoft"** y **"MicrosoftDocs"** .

Al configurar su cuenta de GitHub, también recomendamos estas precauciones de seguridad:
- Cree una [contraseña segura para su cuenta de github](https://github.com/settings/admin).
- Habilitar [la autenticación en dos fases](https://github.com/settings/two_factor_authentication/configure).
- Guarde los [códigos de recuperación](https://github.com/settings/auth/recovery-codes) en un lugar seguro.
- Actualiza la [configuración de tu perfil público](https://github.com/settings/profile).
   - Establezca su nombre y considere la posibilidad de configurar su *correo electrónico público* para *no mostrar mi dirección de correo electrónico*.
   - Le recomendamos que cargue una imagen de perfil porque se muestra una miniatura en las páginas de documentos en las que participa.
- Si planea usar la línea de comandos, considere la posibilidad de configurar [git Credential Manager para Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest). De ese modo, no tendrá que escribir la contraseña cada vez que haga una contribución.

El sistema de publicación está vinculado a GitHub, por lo que estos pasos son importantes. Aparecerá como autor o colaborador de cada artículo con su alias de GitHub.

## Editar un artículo existente

Use el siguiente flujo de trabajo para hacer actualizaciones en un *artículo existente* a través de github en un explorador Web:

1. Vaya al artículo que desea editar en la carpeta "realidad mixta" docs ".

2. En la parte superior derecha, haga clic en el botón Editar (icono de lápiz) para bifurcar automáticamente una rama descartable fuera de la rama "patrón".

   ![Editar un artículo.](images/editpage.png)
   
3. Edite el contenido del artículo según las ["nociones básicas de Markdown"](#markdown-basics).

4. Actualizar metadatos en la parte superior de cada artículo:

   * **título**: título de página que aparece en la pestaña del explorador cuando se está viendo el artículo. Los títulos de página se usan para SEO e indización, así que no cambie el título a menos que sea necesario (aunque es menos importante antes de que la documentación sea pública).
   * **Descripción**: escriba una breve descripción del contenido del artículo, que mejora la SEO y la detección.
   * **autor**: si es el propietario principal de la página, agregue aquí su alias de github.
   * **MS. Author**: si es el propietario principal de la página, agregue su alias de Microsoft aquí (no necesita @microsoft. com, solo el alias).
   * **MS. fecha**: actualice la fecha Si va a agregar contenido principal a la página, pero no para soluciones como aclaración, formato, gramática o ortografía.
   * **palabras clave**: ayuda de palabras clave en SEO (optimización del motor de búsqueda). Agregue palabras clave, separadas por una coma y un espacio, que sean específicas de su artículo, pero sin signos de puntuación después de la última palabra clave de la lista. No es necesario agregar palabras clave globales que se apliquen a todos los artículos, puesto que se administran en otro lugar. 
   
5. Cuando haya completado las ediciones de los artículos, desplácese hacia abajo y seleccione **proponer cambio de archivo**.

6. En la página siguiente, seleccione **crear solicitud de incorporación de inserción** para fusionar la rama creada automáticamente en ' maestra '.

7. Repita los pasos anteriores para el siguiente artículo que desea editar.

## Cambiar el nombre o eliminar un artículo existente

Si su cambio cambiará de nombre o elimina un artículo existente, asegúrese de agregar un redireccionamiento. De ese modo, cualquier persona que tenga un vínculo al artículo existente terminará en el lugar correcto. Las redirecciones las administra el .openpublishing.redirection.jsen el archivo en la raíz del repositorio.

Para agregar un redireccionamiento a .openpublishing.redirection.js, agregue una entrada a la `redirections` matriz:

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- `source_path`Es la ruta de acceso relativa al repositorio del artículo antiguo que va a quitar. Asegúrese de que la ruta comienza por `mixed-reality-docs` y termina en `.md` .

- `redirect_url`Es la dirección URL relativa pública del artículo anterior al nuevo artículo. Asegúrese de que esta dirección URL **no** contiene `mixed-reality-docs` o `.md` , como hace referencia a la dirección URL pública y no a la ruta del repositorio. Se permite la vinculación a una sección en el nuevo artículo mediante `#section` . También puede usar una ruta de acceso absoluta a otro sitio, si es necesario.

- `redirect_document_id` indica si desea mantener el identificador de documento del archivo anterior. El valor predeterminado es `false` . Use `true` esta si desea conservar el `ms.documentid` valor de atributo del artículo redirigido. Si conserva el identificador de documento, los datos, como las vistas de página y las clasificaciones, se transferirán al artículo de destino. Haga esto si el redireccionamiento es principalmente un cambio de nombre y no un puntero a un artículo diferente que solo cubre parte del mismo contenido.

Si agrega un redireccionamiento, asegúrese de eliminar también el archivo antiguo.

## Crear un nuevo artículo

Use el siguiente flujo de trabajo para *crear artículos nuevos* en el repositorio de documentación a través de github en un explorador Web:

1. Crea una bifurcación fuera de la rama de MicrosoftDocs/"patrón" de realidad mixta (con el botón de la **horquilla** en la parte superior derecha).

   ![Bifurcar la rama principal.](images/forkbranch.png)
   
2. En la carpeta "realidad mixta" docs ", seleccione **crear nuevo archivo** en la parte superior derecha.

3. Crear un nombre de página para el artículo (use guiones en lugar de espacios y no use signos de puntuación o apóstrofos) y anexe ". MD"

   ![Asigne un nombre a la página nueva.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >Asegúrese de crear el nuevo artículo desde la carpeta "realidad mixta-documentos". Para confirmarlo, busque "/Mixed-Reality-docs/" en la nueva línea nombre de archivo.

4. En la parte superior de la página nueva, agregue el siguiente bloque de metadatos:

   ```md
   ---
   title:
   description:
   author:
   ms.author:
   ms.date:
   ms.topic: article
   keywords:
   ---
   ```

5. Rellene los campos de metadatos pertinentes según las instrucciones de la [sección anterior](#editing-an-existing-article).

6. Escribir contenido de artículos con [conceptos básicos de Markdown](#markdown-basics).

7. Agregue una `## See also` sección en la parte inferior del artículo con vínculos a otros artículos relevantes.

8. Cuando haya terminado, seleccione **confirmar nuevo archivo**.

9. Selecciona **New pull request** y combina la rama ' Master ' de la horquilla en MicrosoftDocs/mixed-reality ' Master ' (asegúrate de que la flecha apunte de la manera correcta).

   ![Crear una solicitud de incorporación de extracción desde la horquilla en MicrosoftDocs/Mixed-Reality](images/pr-to-master.png)

## Conceptos básicos de Markdown

Los recursos siguientes le ayudarán a obtener información sobre cómo editar la documentación con el idioma de Markdown:

- [Conceptos básicos de Markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Recursos adicionales para escribir Markdown para docs.microsoft.com](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### Agregar tablas

Debido a la forma en que las tablas de docs.microsoft.com Styles, no tendrán bordes ni estilos personalizados, aunque pruebe CSS en línea. Parecerá que funciona durante un breve período de tiempo, pero la plataforma eliminará los estilos de la tabla. Así que es más sencillo mantener las tablas. [Este es un sitio que simplifica las tablas de Markdown](https://www.tablesgenerator.com/markdown_tables).

La [extensión Markdown de docs para Visual Studio](https://docs.microsoft.com/teamblog/docs-extension) también hace que la generación de tablas sea fácil si usas [Visual Studio Code (ver a continuación)](#using-visual-studio-code) para editar la documentación.

### Agregar imágenes

Tendrá que cargar las imágenes en la carpeta "realidad mixta-documentos/imágenes" en el repositorio y, a continuación, hacer referencia a ellas correctamente en el artículo. Las imágenes se mostrarán automáticamente a tamaño completo, lo que significa que las imágenes grandes rellenarán toda la anchura del artículo. Le recomendamos que ajuste el tamaño de las imágenes antes de cargarlas. El ancho recomendado es de entre 600 y 700 píxeles, aunque debe ajustar el tamaño si es una captura de pantalla densa o una fracción de una captura de pantalla, respectivamente.

>[!IMPORTANT]
>Solo puedes cargar imágenes en el repositorio bifurcado antes de fusionarlas. Por lo tanto, si tiene previsto agregar imágenes a un artículo, tendrá que [usar el código de Visual Studio](#using-visual-studio-code) para agregar las imágenes a la carpeta "imágenes" de la horquilla en primer lugar, o asegurarse de que ha hecho lo siguiente en un explorador Web:
>
>1. Se ha bifurcado el repositorio de MicrosoftDocs/realidad mixta.
>2. Editó el artículo en la horquilla.
>3. Ha cargado las imágenes a las que estás haciendo referencia en tu artículo a la carpeta "realidad mixta-documentos/imágenes" de tu horquilla.
>4. Creó una **solicitud de incorporación de inserción** para fusionar tu bifurcación en la rama de MicrosoftDocs/"patrón" de realidad mixta.
>
>Para obtener información sobre cómo configurar su propio repositorio bifurcado, siga las instrucciones para [crear un nuevo artículo](#creating-a-new-article).

## Obtener una vista previa del trabajo

Al editar en GitHub a través de un explorador Web, puede seleccionar la pestaña **vista previa** situada cerca de la parte superior de la página para obtener una vista previa de su trabajo antes de confirmarla. 

>[!NOTE]
>La vista previa de los cambios en review.docs.microsoft.com solo está disponible para los empleados de Microsoft

Empleados de Microsoft: una vez que sus contribuciones se hayan fusionado en la rama "maestra", puede revisar el contenido antes de que se exponga públicamente https://review.docs.microsoft.com/hololens?branch=master . Busque el artículo usando la tabla de contenido en la columna de la izquierda.

## Editar en el explorador y editar con un cliente de escritorio

Editar en el explorador es la manera más fácil de realizar cambios rápidos, pero hay algunas desventajas:

- No puedes comprobar la ortografía.
- No recibe ningún vínculo inteligente a otros artículos (tiene que escribir manualmente el nombre de archivo del artículo).
- Puede ser un problema para cargar y hacer referencia a las imágenes.

Si prefieres no tratar estos problemas, usa un cliente de escritorio como [código Visual Studio](https://code.visualstudio.com/) con un par de [extensiones útiles](#useful-extensions) para la contribución.

## Uso de código de Visual Studio

Por los motivos mencionados [anteriormente](#editing-in-the-browser-vs-editing-with-a-desktop-client), puede que prefiera usar un cliente de escritorio para editar la documentación en lugar de un explorador Web. Recomendamos usar [código de Visual Studio](https://code.visualstudio.com/).

### Programa de instalación

Siga estos pasos para configurar el código de Visual Studio para que funcione con este repositorio:

1. En un explorador Web:
    1. Instala [git para tu equipo](https://git-scm.com/downloads).
    2. Instala el [código de Visual Studio](https://code.visualstudio.com/).
    3. [Fork MicrosoftDocs/realidad mixta](#creating-a-new-article) si todavía no lo has hecho.
    4. En la horquilla, seleccione **clonar o descargar** y copie la dirección URL.
2. Cree un clon local de la bifurcación en Visual Studio Code:
    1. En el menú **vista** , seleccione **paleta de comandos**.
    2. Escribe "git: clonar".
    3. Pegue la dirección URL que ha copiado.
    4. Elija dónde desea guardar el clon en el equipo.
    5. Seleccione **abrir repositorio** en la ventana emergente.

### Editar la documentación

Use el siguiente flujo de trabajo para realizar cambios en la documentación con código de Visual Studio:

>[!NOTE]
>Todas las instrucciones para [Editar](#editing-an-existing-article) y [crear](#creating-a-new-article) artículos, y los [conceptos básicos de la edición de Markdown](#markdown-basics), de arriba, se aplican también al usar código de Visual Studio.

1. Asegúrese de que la horquilla clonada está actualizada con el repositorio oficial.

   1. En un explorador Web, cree una solicitud de incorporación de cambios para sincronizar los cambios recientes de otros colaboradores en MicrosoftDocs/mixed-reality ' patrón ' a la horquilla (Asegúrese de que la flecha esté apuntando de la manera correcta).
      
      ![Sincronizar los cambios de MicrosoftDocs/Mixed-Reality con la horquilla](images/sync-repos.png)
      
   2. En Visual Studio Code, seleccione el botón sincronizar para sincronizar la bifurcación recién actualizada con el clon local.
      
      ![Haga clic en la imagen del botón sincronizar](images/sync-clone.png)
      
2. Cree o edite artículos en el repositorio clonado con código de Visual Studio.

   1. Editar uno o varios artículos (agregar imágenes a la carpeta "imágenes" si es necesario).
   
   2. **Guarde** los cambios en el **Explorador**.
      
      ![Elija "guardar todo" en el explorador](images/explorer-save.png)
      
   3. **Confirmar todos** los cambios en el **control de código fuente** (escriba un mensaje de confirmación cuando se le solicite).
      
   4. Seleccione el botón **sincronizar** para sincronizar los cambios de nuevo con el origen (su bifurcación en GitHub).
      
      ![Haga clic en el botón sincronizar](images/sync-back.png)
      
3. En un explorador Web, cree una solicitud de incorporación de cambios para sincronizar nuevos cambios en la horquilla de nuevo a MicrosoftDocs/mixed-reality ' maestro ' (Asegúrese de que la flecha apunta correctamente).

   ![Crear una solicitud de incorporación de extracción desde la horquilla en MicrosoftDocs/Mixed-Reality](images/pr-to-master.png)

### Extensiones útiles

Las siguientes extensiones de código de Visual Studio son útiles al editar la documentación:

- [Docs Markdown extensión para Visual Studio código](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) : use **Alt + M** para mostrar un menú de opciones de creación de documentos como:
   - Imágenes de búsqueda y de referencia que ha cargado.
   - Agregue formato como listas, tablas y llamadas específicas de documentos como `>[!NOTE]` .
   - Buscar y hacer referencia a vínculos internos y marcadores (vínculos a secciones específicas dentro de una página).
   - Se resaltan los errores de formato (mantenga el mouse sobre el error para obtener más información).
- [Corrector ortográfico de código](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) : las palabras con errores ortográficos se subrayan; Haga clic con el botón derecho en una palabra mal escrita para cambiarla o guardarla en el diccionario.
