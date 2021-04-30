---
title: Instrucciones de contribución
description: Obtenga información sobre cómo contribuir a los documentos de HoloLens en docs.microsoft.com plataforma mediante Markdown con tipo GitHub.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: dd205ab1fe399d6612be982136c80733a5eb087e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310092"
---
# <a name="contributing-to-the-hololens-documentation"></a>Contribución a la documentación de HoloLens

Le damos la bienvenida a la documentación [de HoloLens.](https://github.com/MicrosoftDocs/Hololens) Los artículos que cree o edite en este repositorio **serán visibles para el público.** 

Los documentos de HoloLens se muestran en la plataforma docs.microsoft.com, que usa Markdown con estilo GitHub con características de Markdig. El contenido que edite en este repositorio se formatee en páginas con formato que se muestran en https://docs.microsoft.com/hololens . 

En esta página se tratan los pasos básicos y las directrices para contribuir y vínculos a los conceptos básicos de Markdown. Gracias por su contribución.

## <a name="available-repos"></a>Repositorios disponibles

| Nombre del repositorio | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Mixed Reality | [MicrosoftDocs/mixed-reality](https://docs.microsoft.com/windows/mixed-reality) |
| VR Enthusiasts Guide | [MicrosoftDocs/mixed-reality/enthusiast-guide](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>Antes de comenzar

Si aún no tiene una, deberá crear [una cuenta de GitHub.](https://github.com/join)

>[!NOTE]
>Si es un empleado de Microsoft, vincule su cuenta de GitHub a su alias de Microsoft en el [portal de código abierto de Microsoft](https://repos.opensource.microsoft.com/). Únase a **las organizaciones "Microsoft"** **y "MicrosoftDocs".**

Al configurar la cuenta de GitHub, también se recomiendan estas precauciones de seguridad:
- Cree una [contraseña segura para la cuenta de GitHub.](https://github.com/settings/admin)
- Habilite [la autenticación en dos fases.](https://github.com/settings/two_factor_authentication/configure)
- Guarde los [códigos de recuperación](https://github.com/settings/auth/recovery-codes) en un lugar seguro.
- Actualice la [configuración del perfil público.](https://github.com/settings/profile)
   - Establezca su nombre y considere la posibilidad de establecer *el correo electrónico público* en No mostrar mi dirección de correo *electrónico.*
   - Se recomienda cargar una imagen de perfil porque se muestra una miniatura en las páginas de documentos a las que contribuye.
- Si tiene previsto usar la línea de comandos, considere la posibilidad de configurar [Git Administrador de credenciales para Windows.](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest) De este modo, no tendrá que escribir la contraseña cada vez que realice una contribución.

El sistema de publicación está vinculado a GitHub, por lo que estos pasos son importantes. Aparecerá como autor o colaborador de cada artículo mediante el alias de GitHub.

## <a name="editing-an-existing-article"></a>Edición de un artículo existente

Use el siguiente flujo de trabajo para realizar actualizaciones en *un artículo existente* a través de GitHub en un explorador web:

1. Vaya al artículo que desea editar en la carpeta "mixed-reality-docs".

2. Seleccione el botón Editar (icono de lápiz) en la parte superior derecha, que bifurcará automáticamente una rama descartable de la rama "maestra".

   ![Edite un artículo.](images/editpage.png)
   
3. Edite el contenido del artículo según [los "Conceptos básicos de Markdown".](#markdown-basics)

4. Actualice los metadatos en la parte superior de cada artículo:

   * **title:** título de la página que aparece en la pestaña del explorador cuando se está visualizando el artículo. Los títulos de página se usan para SEO e indexación, por lo que no cambie el título a menos que sea necesario (aunque esto es menos crítico antes de que la documentación se haga pública).
   * **description:** escriba una breve descripción del contenido del artículo, lo que aumenta el SEO y la detección.
   * **author**: si es el propietario principal de la página, agregue aquí el alias de GitHub.
   * **ms.author:** si es el propietario principal de la página, agregue el alias de Microsoft aquí (no necesita , solo @microsoft.com el alias).
   * **ms.date:** actualice la fecha si va a agregar contenido principal a la página, pero no para correcciones como aclaración, formato, gramática o ortografía.
   * **keywords:** las palabras clave ayudan en SEO (optimización del motor de búsqueda). Agregue palabras clave, separadas por una coma y un espacio, que sean específicas del artículo, pero sin signos de puntuación después de la última palabra clave de la lista. No es necesario agregar palabras clave globales que se apliquen a todos los artículos, ya que se administran en otro lugar. 
   
5. Cuando haya completado las modificaciones del artículo, desplácese hacia abajo y seleccione **Propose file change (Proponer cambio de archivo).**

6. En la página siguiente, seleccione **Crear solicitud de extracción** para combinar la rama creada automáticamente en "master".

7. Repita los pasos anteriores para el siguiente artículo que desea editar.

## <a name="renaming-or-deleting-an-existing-article"></a>Cambio de nombre o eliminación de un artículo existente

Si el cambio cambiará el nombre o eliminará un artículo existente, asegúrese de agregar un redireccionamiento. De este modo, cualquier persona con un vínculo al artículo existente terminará en el lugar correcto. Los redireccionamientos se administran .openpublishing.redirection.jsen el archivo en la raíz del repositorio.

Para agregar una redirección a .openpublishing.redirection.js, agregue una entrada a la `redirections` matriz:

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- es la ruta de acceso relativa del repositorio `source_path` al artículo anterior que va a quitar. Asegúrese de que la ruta de acceso comienza `mixed-reality-docs` por y termina con `.md` .

- es `redirect_url` la dirección URL pública relativa del artículo anterior al nuevo. Asegúrese de que esta dirección URL **no contiene** o , ya que hace referencia a la dirección URL pública y no a la ruta de acceso `mixed-reality-docs` del `.md` repositorio. Se permite la vinculación a una sección dentro del `#section` nuevo artículo mediante . También puede usar una ruta de acceso absoluta a otro sitio aquí, si es necesario.

- `redirect_document_id` indica si desea conservar el identificador del documento del archivo anterior. De manera predeterminada, es `false`. Use `true` si desea conservar el valor del atributo del artículo `ms.documentid` redirigido. Si conserva el identificador del documento, los datos, como las vistas de página y las clasificaciones, se transferirán al artículo de destino. Haga esto si el redireccionamiento es principalmente un cambio de nombre y no un puntero a otro artículo que solo cubre parte del mismo contenido.

Si agrega un redireccionamiento, asegúrese de eliminar también el archivo antiguo.

## <a name="creating-a-new-article"></a>Creación de un nuevo artículo

Use el siguiente flujo de trabajo *para crear nuevos artículos en* el repositorio de documentación a través de GitHub en un explorador web:

1. Cree una bifurcación fuera de la rama "maestra" de MicrosoftDocs/mixed-reality (con el botón **Bifurcar** de la parte superior derecha).

   ![Bifurcar la rama maestra.](images/forkbranch.png)
   
2. En la carpeta "mixed-reality-docs", seleccione **Crear nuevo archivo** en la parte superior derecha.

3. Cree un nombre de página para el artículo (use guiones en lugar de espacios y no use signos de puntuación ni apóstrofos) y anexe ".md".

   ![Asigne un nombre a la nueva página.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >Asegúrese de crear el nuevo artículo desde la carpeta "mixed-reality-docs". Para confirmarlo, compruebe "/mixed-reality-docs/" en la nueva línea de nombre de archivo.

4. En la parte superior de la nueva página, agregue el siguiente bloque de metadatos:

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

5. Rellene los campos de metadatos pertinentes según las instrucciones de la [sección anterior.](#editing-an-existing-article)

6. Escribir contenido del artículo con [los conceptos básicos de Markdown.](#markdown-basics)

7. Agregue una `## See also` sección en la parte inferior del artículo con vínculos a otros artículos pertinentes.

8. Cuando termine, seleccione **Commit new file (Confirmar nuevo archivo).**

9. Seleccione **Nueva** solicitud de extracción y combine la rama "maestra" de la bifurcación en MicrosoftDocs/mixed-reality "master" (asegúrese de que la flecha apunta de la manera correcta).

   ![Creación de una solicitud de extracción desde la bifurcación en MicrosoftDocs/mixed-reality](images/pr-to-master.png)

## <a name="markdown-basics"></a>Aspectos básicos de Markdown

Los siguientes recursos le ayudarán a aprender a editar la documentación mediante el lenguaje Markdown:

- [Markdown basics](https://help.github.com/articles/basic-writing-and-formatting-syntax/) (Conceptos básicos de Markdown)
- [Recursos adicionales para escribir Markdown para docs.microsoft.com](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>Adición de tablas

Debido a la forma docs.microsoft.com tablas de estilos, no tendrán bordes ni estilos personalizados, aunque pruebe CSS en línea. Parecerá que funciona durante un breve período de tiempo, pero finalmente la plataforma quitará el estilo de la tabla. Por lo tanto, planee con antelación y mantenga las tablas sencillas. [Este es un sitio que facilita las tablas de Markdown.](https://www.tablesgenerator.com/markdown_tables)

La [extensión Docs Markdown](https://docs.microsoft.com/teamblog/docs-extension) para Visual Studio Code también facilita la generación de tablas si usa Visual Studio Code [(consulte](#using-visual-studio-code) a continuación) para editar la documentación.

### <a name="adding-images"></a>Incorporación de imágenes

Deberá cargar las imágenes en la carpeta "mixed-reality-docs/images" del repositorio y, a continuación, hacer referencia a ellas correctamente en el artículo. Las imágenes se mostrarán automáticamente a tamaño completo, lo que significa que las imágenes grandes rellenarán todo el ancho del artículo. Se recomienda dimensionar previamente las imágenes antes de cargarlas. El ancho recomendado es de entre 600 y 700 píxeles, aunque debe ajustar el tamaño hacia arriba o hacia abajo si es una captura de pantalla densa o una fracción de una captura de pantalla, respectivamente.

>[!IMPORTANT]
>Solo puede cargar imágenes en el repositorio bifurcado antes de la combinación. Por lo tanto, si planea agregar imágenes a un artículo, deberá usar Visual Studio Code para agregar primero las imágenes [a](#using-visual-studio-code) la carpeta "images" de la bifurcación o asegúrese de que ha hecho lo siguiente en un explorador web:
>
>1. Se ha bifurcado el repositorio MicrosoftDocs/mixed-reality.
>2. Editó el artículo en la bifurcación.
>3. Ha cargado las imágenes a las que hace referencia en el artículo en la carpeta "mixed-reality-docs/images" de la bifurcación.
>4. Ha creado **una solicitud de** extracción para combinar la bifurcación en la rama "maestra" de MicrosoftDocs/mixed-reality.
>
>Para obtener información sobre cómo configurar su propio repositorio bifurcado, siga las instrucciones para [crear un nuevo artículo](#creating-a-new-article).

## <a name="previewing-your-work"></a>Vista previa del trabajo

Durante la edición en GitHub a  través de un explorador web, puede seleccionar la pestaña Vista previa cerca de la parte superior de la página para obtener una vista previa del trabajo antes de confirmar. 

>[!NOTE]
>La vista previa de los cambios review.docs.microsoft.com solo está disponible para los empleados de Microsoft

Empleados de Microsoft: una vez que sus contribuciones se hayan combinado en la rama "maestra", puede revisar el contenido antes de que se haga público en https://review.docs.microsoft.com/hololens?branch=master . Busque el artículo con la tabla de contenido de la columna izquierda.

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>Edición en el explorador frente a edición con un cliente de escritorio

La edición en el explorador es la manera más fácil de realizar cambios rápidos; sin embargo, hay algunas desventajas:

- No se le hace una revisión ortótrea.
- No se obtiene ninguna vinculación inteligente a otros artículos (tiene que escribir manualmente el nombre de archivo del artículo).
- Puede ser complicado cargar y hacer referencia a imágenes.

Si prefiere no tratar estos problemas, use un cliente de escritorio [](#useful-extensions) como [Visual Studio Code](https://code.visualstudio.com/) con un par de extensiones útiles al contribuir.

## <a name="using-visual-studio-code"></a>Uso de Visual Studio Code

Por los motivos [mencionados anteriormente,](#editing-in-the-browser-vs-editing-with-a-desktop-client)puede que prefiera usar un cliente de escritorio para editar la documentación en lugar de un explorador web. Se recomienda usar [Visual Studio Code](https://code.visualstudio.com/).

### <a name="setup"></a>Instalación

Siga estos pasos para configurar Visual Studio Code para trabajar con este repositorio:

1. En un explorador web:
    1. Instale [Git para el equipo.](https://git-scm.com/downloads)
    2. Instale [Visual Studio Code](https://code.visualstudio.com/).
    3. Si aún no lo ha hecho, puede bifurcar [MicrosoftDocs/mixed-reality.](#creating-a-new-article)
    4. En la bifurcación, seleccione **Clonar o descargar y** copie la dirección URL.
2. Cree un clon local de la bifurcación en Visual Studio Code:
    1. En el **menú Ver,** seleccione **Paleta de comandos.**
    2. Escriba "Git: Clone".
    3. Pegue la dirección URL que copió.
    4. Elija dónde guardar el clon en el equipo.
    5. Seleccione **Abrir repositorio** en el menú emergente.

### <a name="editing-documentation"></a>Edición de documentación

Use el flujo de trabajo siguiente para realizar cambios en la documentación con Visual Studio Code:

>[!NOTE]
>Todas las instrucciones [](#creating-a-new-article) para [editar y](#editing-an-existing-article) crear [artículos,](#markdown-basics)y los aspectos básicos de la edición de Markdown , de arriba se aplican al Visual Studio Code también.

1. Asegúrese de que la bifurcación clonada está actualizada con el repositorio oficial.

   1. En un explorador web, cree una solicitud de extracción para sincronizar los cambios recientes de otros colaboradores de MicrosoftDocs/mixed-reality 'master' con la bifurcación (asegúrese de que la flecha apunta a la derecha).
      
      ![Sincronización de cambios de MicrosoftDocs/mixed-reality a la bifurcación](images/sync-repos.png)
      
   2. En Visual Studio Code, seleccione el botón sincronizar para sincronizar la bifurcación recién actualizada con el clon local.
      
      ![Haga clic en la imagen del botón de sincronización.](images/sync-clone.png)
      
2. Cree o edite artículos en el repositorio clonado mediante Visual Studio Code.

   1. Edite uno o varios artículos (agregue imágenes a la carpeta "images" si es necesario).
   
   2. **Guarde los** cambios en **el Explorador** de .
      
      ![Elija "Guardar todo" en el Explorador](images/explorer-save.png)
      
   3. **Confirme todos los** cambios en **el Control de código fuente** (escriba el mensaje de confirmación cuando se le solicite).
   
      ![Elija "Confirmar todo" en control de código fuente](images/source-control-commit.png)
      
   4. Seleccione el **botón** sincronizar para volver a sincronizar los cambios en el origen (la bifurcación en GitHub).
      
      ![Haga clic en el botón Sync (Sincronizar).](images/sync-back.png)
      
3. En un explorador web, cree una solicitud de extracción para sincronizar nuevos cambios en la bifurcación con MicrosoftDocs/mixed-reality 'master' (asegúrese de que la flecha apunta de la manera correcta).

   ![Creación de una solicitud de extracción desde la bifurcación en MicrosoftDocs/mixed-reality](images/pr-to-master.png)

### <a name="useful-extensions"></a>Extensiones útiles

Las siguientes extensiones Visual Studio Code son útiles al editar la documentación:

- [Extensión Markdown de Docs para Visual Studio Code:](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) use **Alt+M** para abrir un menú de opciones de creación de documentos como:
   - Busque y haga referencia a las imágenes que ha cargado.
   - Agregue formatos como listas, tablas y llamadas específicas de documentos, como `>[!NOTE]` .
   - Buscar y hacer referencia a vínculos internos y marcadores (vínculos a secciones específicas dentro de una página).
   - Los errores de formato están resaltados (mantenga el mouse sobre el error para obtener más información).
- [Corrector ortográfico de código:](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) las palabras mal escritas se subrayan; Haga clic con el botón derecho en una palabra mal escrita para cambiarla o guárdela en el diccionario.
