---
title: Instrucciones de colaboración
description: Aprende a contribuir a los documentos de HoloLens en la plataforma docs.microsoft.com usando Markdown con estilo GitHub.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: dd205ab1fe399d6612be982136c80733a5eb087e
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283670"
---
# Contribuir a la documentación de HoloLens

Bienvenido a la documentación [de HoloLens.](https://github.com/MicrosoftDocs/Hololens) Los artículos que cree o edite en este repositorio **serán visibles para el público.** 

Los documentos de HoloLens se muestran en la plataforma docs.microsoft.com, que usa Markdown con estilo GitHub con características de Markdig. El contenido que edite en este repositorio recibe formato de páginas stylized que se muestran en https://docs.microsoft.com/hololens . 

En esta página se tratan los pasos básicos y las directrices para contribuir y vínculos a los conceptos básicos de Markdown. Gracias por su contribución.

## Repositorios disponibles

| Nombre del repositorio | Dirección URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Realidad mixta | [MicrosoftDocs/realidad mixta](https://docs.microsoft.com/windows/mixed-reality) |
| Guía para entusiastas de VR | [MicrosoftDocs/mixed-reality/enthusiast-guide](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## Antes de empezar

Si aún no tienes una, tendrás que crear [una cuenta de GitHub.](https://github.com/join)

>[!NOTE]
>Si es un empleado de Microsoft, vincule su cuenta de GitHub a su alias de Microsoft en el [portal de código abierto de Microsoft.](https://repos.opensource.microsoft.com/) Únase a **las organizaciones "Microsoft"** **y "MicrosoftDocs".**

Al configurar tu cuenta de GitHub, también te recomendamos estas precauciones de seguridad:
- Cree una [contraseña segura para su cuenta de GitHub.](https://github.com/settings/admin)
- Habilite [la autenticación en dos fases.](https://github.com/settings/two_factor_authentication/configure)
- Guarde los [códigos de recuperación](https://github.com/settings/auth/recovery-codes) en un lugar seguro.
- Actualice la configuración [de perfil público.](https://github.com/settings/profile)
   - Establezca su nombre y considere la posibilidad de establecer su *correo electrónico* público en No mostrar mi dirección de *correo electrónico.*
   - Se recomienda cargar una imagen de perfil porque se muestra una miniatura en las páginas de documentos a las que contribuye.
- Si tienes previsto usar la línea de comandos, considera la posibilidad de configurar el Administrador de [credenciales de Git para Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest). De este modo, no tendrá que escribir su contraseña cada vez que realice una contribución.

El sistema de publicación está vinculado a GitHub, por lo que estos pasos son importantes. Aparecerá como autor o colaborador de cada artículo con el alias de GitHub.

## Edición de un artículo existente

Use el siguiente flujo de trabajo para realizar actualizaciones *de un artículo* existente a través de GitHub en un explorador web:

1. Vaya al artículo que desea editar en la carpeta "mixed-reality-docs".

2. Seleccione el botón de edición (icono de lápiz) en la parte superior derecha, que bifurcará automáticamente una rama desechable de la rama "maestra".

   ![Edite un artículo.](images/editpage.png)
   
3. Edite el contenido del artículo de acuerdo con [los "Conceptos básicos de Markdown".](#markdown-basics)

4. Actualice los metadatos en la parte superior de cada artículo:

   * **title:** título de página que aparece en la pestaña del explorador cuando se está visualizando el artículo. Los títulos de página se usan para SEO e indización, así que no cambies el título a menos que sea necesario (aunque esto es menos crítico antes de que la documentación se haga pública).
   * **description:** escriba una breve descripción del contenido del artículo, lo que aumenta el seo y la detección.
   * **autor:** si es el propietario principal de la página, agregue aquí el alias de GitHub.
   * **ms.author:** si es el propietario principal de la página, agregue el alias de Microsoft aquí (no necesita @microsoft.com, solo el alias).
   * **ms.date:** actualice la fecha si va a agregar contenido principal a la página, pero no para correcciones como la aclaración, el formato, la gramática o la ortografía.
   * **palabras clave:** ayuda con palabras clave en SEO (optimización del motor de búsqueda). Agregue palabras clave, separadas por una coma y un espacio, que sean específicas del artículo, pero sin puntuación después de la última palabra clave de la lista. No es necesario agregar palabras clave globales que se apliquen a todos los artículos, ya que se administran en otro lugar. 
   
5. Cuando haya completado las ediciones del artículo, desplácese hacia abajo y seleccione **Proponer cambio de archivo.**

6. En la página siguiente, seleccione **Crear solicitud de extracción** para combinar la rama creada automáticamente en "patrón".

7. Repita los pasos anteriores para el siguiente artículo que desee editar.

## Cambiar el nombre o eliminar un artículo existente

Si el cambio cambiará de nombre o eliminará un artículo existente, asegúrese de agregar un redireccionamiento. De este modo, cualquier persona con un vínculo al artículo existente seguirá en el lugar adecuado. Los redireccionamientos se administran mediante .openpublishing.redirection.jsen el archivo en la raíz del repositorio.

Para agregar un redireccionamiento .openpublishing.redirection.js, agregue una entrada a la `redirections` matriz:

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- Se trata de la ruta de acceso relativa del repositorio `source_path` al artículo antiguo que está quitando. Asegúrese de que la ruta comienza por `mixed-reality-docs` y termina por `.md` .

- Se `redirect_url` trata de la dirección URL pública relativa del artículo anterior al nuevo artículo. Asegúrese de que esta dirección URL **no** contiene o, como hace referencia a la dirección URL pública `mixed-reality-docs` y no a la ruta de acceso del `.md` repositorio. Se permite vincular a una sección dentro del nuevo artículo que `#section` se usa. También puede usar una ruta de acceso absoluta a otro sitio aquí, si es necesario.

- `redirect_document_id` indica si desea conservar el identificador del documento del archivo anterior. El valor predeterminado es `false` . Se `true` usa si desea conservar el valor de atributo del artículo `ms.documentid` redirigido. Si conserva el identificador del documento, los datos, como las vistas de página y las clasificaciones, se transferirán al artículo de destino. Haga esto si el redireccionamiento es principalmente un cambio de nombre y no un puntero a un artículo diferente que solo cubre parte del mismo contenido.

Si agrega un redireccionamiento, asegúrese de eliminar también el archivo antiguo.

## Creación de un nuevo artículo

Use el siguiente flujo de trabajo para *crear nuevos artículos en* el repositorio de documentación a través de GitHub en un explorador web:

1. Cree una bifurcación de la rama "patrón" de MicrosoftDocs/realidad mixta (con el botón Bifurcación situado en la parte superior derecha). ****

   ![Bifurca la rama maestra.](images/forkbranch.png)
   
2. En la carpeta "mixed-reality-docs", seleccione **Crear nuevo archivo** en la parte superior derecha.

3. Cree un nombre de página para el artículo (use guiones en lugar de espacios y no use signos de puntuación ni apóstrofes) y anexe ".md"

   ![Asigne un nombre a la nueva página.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >Asegúrese de crear el nuevo artículo desde la carpeta "documentos de realidad mixta". Para confirmar esto, compruebe "/mixed-reality-docs/" en la nueva línea de nombre de archivo.

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

5. Rellene los campos de metadatos relevantes según las instrucciones de la [sección anterior.](#editing-an-existing-article)

6. Escribir contenido de artículo con [los conceptos básicos de Markdown](#markdown-basics).

7. Agregue una `## See also` sección en la parte inferior del artículo con vínculos a otros artículos relevantes.

8. Cuando haya terminado, seleccione **Confirmar nuevo archivo.**

9. Seleccione Nueva solicitud **de** extracción y combine la rama 'master' de la bifurcación en MicrosoftDocs/'master' de realidad mixta (asegúrese de que la flecha apunta de la forma correcta).

   ![Crear una solicitud de extracción desde la bifurcación a MicrosoftDocs/realidad mixta](images/pr-to-master.png)

## Conceptos básicos de Markdown

Los siguientes recursos le ayudarán a aprender a editar la documentación con el lenguaje Markdown:

- [Conceptos básicos de Markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Recursos adicionales para escribir Markdown para docs.microsoft.com](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### Agregar tablas

Debido a la forma docs.microsoft.com tablas de estilos, no tendrán bordes ni estilos personalizados, incluso si intenta usar CSS en línea. Parecerá que funciona durante un breve período de tiempo, pero finalmente la plataforma quitará el estilo de la tabla. Por lo tanto, planee con antelación y mantenga las tablas sencillas. [Este es un sitio que facilita las tablas de Markdown.](https://www.tablesgenerator.com/markdown_tables)

La [extensión Docs Markdown](https://docs.microsoft.com/teamblog/docs-extension) para Visual Studio Code también facilita la generación de tablas si usa un código de Visual Studio [(vea](#using-visual-studio-code) a continuación) para editar la documentación.

### Agregar imágenes

Deberá cargar las imágenes en la carpeta "mixed-reality-docs/images" del repositorio y, a continuación, hacer referencia a ellas correctamente en el artículo. Las imágenes se mostrarán automáticamente a tamaño completo, lo que significa que las imágenes grandes rellenarán todo el ancho del artículo. Se recomienda dimensionar previamente las imágenes antes de cargarlas. El ancho recomendado es de entre 600 y 700 píxeles, aunque debes cambiar el tamaño hacia arriba o hacia abajo si es una captura de pantalla densa o una fracción de una captura de pantalla, respectivamente.

>[!IMPORTANT]
>Solo puedes cargar imágenes en el repositorio bifurcado antes de combinarlas. Por lo tanto, si planea agregar imágenes a un artículo, deberá usar un código de Visual Studio para agregar las imágenes [a](#using-visual-studio-code) la carpeta "imágenes" de la bifurcación en primer lugar o asegúrese de que ha hecho lo siguiente en un explorador web:
>
>1. Bifurcado el repositorio MicrosoftDocs/mixed-reality.
>2. Editó el artículo en la bifurcación.
>3. Ha cargado las imágenes a las que hace referencia en su artículo a la carpeta "mixed-reality-docs/images" en la bifurcación.
>4. Se ha **creado una solicitud de** extracción para combinar la bifurcación en la rama "maestra" de MicrosoftDocs/realidad mixta.
>
>Para obtener información sobre cómo configurar su propio repositorio bifurcado, siga las instrucciones para [crear un nuevo artículo.](#creating-a-new-article)

## Obtener una vista previa del trabajo

Durante la edición en GitHub a **** través de un explorador web, puede seleccionar la pestaña Vista previa cerca de la parte superior de la página para obtener una vista previa del trabajo antes de confirmarlo. 

>[!NOTE]
>La vista previa de los cambios review.docs.microsoft.com solo está disponible para los empleados de Microsoft

Empleados de Microsoft: una vez que sus contribuciones se han combinado en la rama "maestra", puede revisar el contenido antes de que se haga público en https://review.docs.microsoft.com/hololens?branch=master . Busque el artículo con la tabla de contenido de la columna izquierda.

## Edición en el explorador frente a edición con un cliente de escritorio

La edición en el explorador es la forma más sencilla de realizar cambios rápidos, pero hay algunas desventajas:

- You don't get spell-check.
- No obtiene ningún vínculo inteligente a otros artículos (tiene que escribir manualmente el nombre de archivo del artículo).
- Puede ser complicado cargar y hacer referencia a imágenes.

Si prefieres no abordar estos problemas, usa un cliente de escritorio como [Visual Studio Code](https://code.visualstudio.com/) con un par de extensiones útiles [al](#useful-extensions) contribuir.

## Uso Visual Studio código

Por los motivos [mencionados anteriormente,](#editing-in-the-browser-vs-editing-with-a-desktop-client)es posible que prefiera usar un cliente de escritorio para editar la documentación en lugar de un explorador web. Se recomienda usar [Visual Studio código de usuario.](https://code.visualstudio.com/)

### Programa de instalación

Siga estos pasos para configurar el código Visual Studio para que funcione con este repositorio:

1. En un explorador web:
    1. Instalar [Git para su PC.](https://git-scm.com/downloads)
    2. Instalar Visual Studio código de [instalación.](https://code.visualstudio.com/)
    3. [Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.
    4. En la bifurcación, seleccione **Clonar o descargar** y copiar la dirección URL.
2. Cree un clon local de la bifurcación en Visual Studio código:
    1. En el **menú** Ver, seleccione **Paleta de comandos.**
    2. Escriba "Git: Clone".
    3. Pegue la dirección URL que copió.
    4. Elige dónde guardar el clon en el equipo.
    5. Seleccione **Abrir repositorio** en la ventana emergente.

### Edición de documentación

Use el siguiente flujo de trabajo para realizar cambios en la documentación con Visual Studio código:

>[!NOTE]
>Todas las instrucciones para [editar](#editing-an-existing-article) [y](#creating-a-new-article) crear [artículos,](#markdown-basics)y los conceptos básicos de edición de Markdown , de arriba se aplican al usar Visual Studio código.

1. Asegúrese de que la bifurcación clonada esté actualizada con el repositorio oficial.

   1. En un explorador web, cree una solicitud de extracción para sincronizar los cambios recientes de otros colaboradores en MicrosoftDocs/"master" de realidad mixta con la bifurcación (asegúrese de que la flecha apunta hacia la derecha).
      
      ![Sincronizar los cambios de MicrosoftDocs/realidad mixta con la bifurcación](images/sync-repos.png)
      
   2. En Visual Studio código, seleccione el botón de sincronización para sincronizar la bifurcación actualizada con el clon local.
      
      ![Haga clic en la imagen del botón de sincronización](images/sync-clone.png)
      
2. Cree o edite artículos en el repositorio clonado con Visual Studio código.

   1. Edite uno o varios artículos (agregue imágenes a la carpeta "imágenes" si es necesario).
   
   2. **Guardar** los cambios en **el Explorador**.
      
      ![Elija "Guardar todo" en el Explorador](images/explorer-save.png)
      
   3. **Confirmar todos los** cambios en **el Control de código fuente** (escriba el mensaje de confirmación cuando se le pida).
   
      ![Elija "Confirmar todo" en el control de código fuente](images/source-control-commit.png)
      
   4. Seleccione el **botón de** sincronización para volver a sincronizar los cambios en el origen (la bifurcación en GitHub).
      
      ![Haga clic en el botón de sincronización](images/sync-back.png)
      
3. En un explorador web, cree una solicitud de extracción para sincronizar los nuevos cambios en la bifurcación de nuevo a MicrosoftDocs/'master' de realidad mixta (asegúrese de que la flecha apunta de la forma correcta).

   ![Crear una solicitud de extracción desde la bifurcación a MicrosoftDocs/realidad mixta](images/pr-to-master.png)

### Extensiones útiles

Las siguientes extensiones Visual Studio código son útiles al editar la documentación:

- [Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** para abrir un menú de opciones de creación de documentos como:
   - Buscar y hacer referencia a imágenes que ha cargado.
   - Agregue formato como listas, tablas y llamadas específicas de documentos como `>[!NOTE]` .
   - Buscar y hacer referencia a vínculos internos y marcadores (vínculos a secciones específicas dentro de una página).
   - Los errores de formato están resaltados (mantenga el mouse sobre el error para obtener más información).
- [Corrector ortográfico de código:](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) las palabras mal escritas estarán subrayadas; haga clic con el botón secundario en una palabra mal escrita para cambiarla o guardarla en el diccionario.
