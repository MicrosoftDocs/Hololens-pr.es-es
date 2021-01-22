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
# <span data-ttu-id="5b920-103">Contribuir a la documentación de HoloLens</span><span class="sxs-lookup"><span data-stu-id="5b920-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="5b920-104">Bienvenido a la documentación [de HoloLens.](https://github.com/MicrosoftDocs/Hololens)</span><span class="sxs-lookup"><span data-stu-id="5b920-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="5b920-105">Los artículos que cree o edite en este repositorio **serán visibles para el público.**</span><span class="sxs-lookup"><span data-stu-id="5b920-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="5b920-106">Los documentos de HoloLens se muestran en la plataforma docs.microsoft.com, que usa Markdown con estilo GitHub con características de Markdig.</span><span class="sxs-lookup"><span data-stu-id="5b920-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="5b920-107">El contenido que edite en este repositorio recibe formato de páginas stylized que se muestran en https://docs.microsoft.com/hololens .</span><span class="sxs-lookup"><span data-stu-id="5b920-107">The content you edit in this repo gets formatted into stylized pages that show up at https://docs.microsoft.com/hololens.</span></span> 

<span data-ttu-id="5b920-108">En esta página se tratan los pasos básicos y las directrices para contribuir y vínculos a los conceptos básicos de Markdown.</span><span class="sxs-lookup"><span data-stu-id="5b920-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="5b920-109">Gracias por su contribución.</span><span class="sxs-lookup"><span data-stu-id="5b920-109">Thanks for your contribution!</span></span>

## <span data-ttu-id="5b920-110">Repositorios disponibles</span><span class="sxs-lookup"><span data-stu-id="5b920-110">Available repos</span></span>

| <span data-ttu-id="5b920-111">Nombre del repositorio</span><span class="sxs-lookup"><span data-stu-id="5b920-111">Repository name</span></span> | <span data-ttu-id="5b920-112">Dirección URL</span><span class="sxs-lookup"><span data-stu-id="5b920-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="5b920-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="5b920-113">HoloLens</span></span> | [<span data-ttu-id="5b920-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="5b920-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="5b920-115">Realidad mixta</span><span class="sxs-lookup"><span data-stu-id="5b920-115">Mixed Reality</span></span> | [<span data-ttu-id="5b920-116">MicrosoftDocs/realidad mixta</span><span class="sxs-lookup"><span data-stu-id="5b920-116">MicrosoftDocs/mixed-reality</span></span>](https://docs.microsoft.com/windows/mixed-reality) |
| <span data-ttu-id="5b920-117">Guía para entusiastas de VR</span><span class="sxs-lookup"><span data-stu-id="5b920-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="5b920-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span><span class="sxs-lookup"><span data-stu-id="5b920-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <span data-ttu-id="5b920-119">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="5b920-119">Before you start</span></span>

<span data-ttu-id="5b920-120">Si aún no tienes una, tendrás que crear [una cuenta de GitHub.](https://github.com/join)</span><span class="sxs-lookup"><span data-stu-id="5b920-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="5b920-121">Si es un empleado de Microsoft, vincule su cuenta de GitHub a su alias de Microsoft en el [portal de código abierto de Microsoft.](https://repos.opensource.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="5b920-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="5b920-122">Únase a **las organizaciones "Microsoft"** **y "MicrosoftDocs".**</span><span class="sxs-lookup"><span data-stu-id="5b920-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="5b920-123">Al configurar tu cuenta de GitHub, también te recomendamos estas precauciones de seguridad:</span><span class="sxs-lookup"><span data-stu-id="5b920-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="5b920-124">Cree una [contraseña segura para su cuenta de GitHub.](https://github.com/settings/admin)</span><span class="sxs-lookup"><span data-stu-id="5b920-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="5b920-125">Habilite [la autenticación en dos fases.](https://github.com/settings/two_factor_authentication/configure)</span><span class="sxs-lookup"><span data-stu-id="5b920-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="5b920-126">Guarde los [códigos de recuperación](https://github.com/settings/auth/recovery-codes) en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="5b920-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="5b920-127">Actualice la configuración [de perfil público.](https://github.com/settings/profile)</span><span class="sxs-lookup"><span data-stu-id="5b920-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="5b920-128">Establezca su nombre y considere la posibilidad de establecer su *correo electrónico* público en No mostrar mi dirección de *correo electrónico.*</span><span class="sxs-lookup"><span data-stu-id="5b920-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="5b920-129">Se recomienda cargar una imagen de perfil porque se muestra una miniatura en las páginas de documentos a las que contribuye.</span><span class="sxs-lookup"><span data-stu-id="5b920-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="5b920-130">Si tienes previsto usar la línea de comandos, considera la posibilidad de configurar el Administrador de [credenciales de Git para Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span><span class="sxs-lookup"><span data-stu-id="5b920-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="5b920-131">De este modo, no tendrá que escribir su contraseña cada vez que realice una contribución.</span><span class="sxs-lookup"><span data-stu-id="5b920-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="5b920-132">El sistema de publicación está vinculado a GitHub, por lo que estos pasos son importantes.</span><span class="sxs-lookup"><span data-stu-id="5b920-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="5b920-133">Aparecerá como autor o colaborador de cada artículo con el alias de GitHub.</span><span class="sxs-lookup"><span data-stu-id="5b920-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <span data-ttu-id="5b920-134">Edición de un artículo existente</span><span class="sxs-lookup"><span data-stu-id="5b920-134">Editing an existing article</span></span>

<span data-ttu-id="5b920-135">Use el siguiente flujo de trabajo para realizar actualizaciones *de un artículo* existente a través de GitHub en un explorador web:</span><span class="sxs-lookup"><span data-stu-id="5b920-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="5b920-136">Vaya al artículo que desea editar en la carpeta "mixed-reality-docs".</span><span class="sxs-lookup"><span data-stu-id="5b920-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="5b920-137">Seleccione el botón de edición (icono de lápiz) en la parte superior derecha, que bifurcará automáticamente una rama desechable de la rama "maestra".</span><span class="sxs-lookup"><span data-stu-id="5b920-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![Edite un artículo.](images/editpage.png)
   
3. <span data-ttu-id="5b920-139">Edite el contenido del artículo de acuerdo con [los "Conceptos básicos de Markdown".](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="5b920-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="5b920-140">Actualice los metadatos en la parte superior de cada artículo:</span><span class="sxs-lookup"><span data-stu-id="5b920-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="5b920-141">**title:** título de página que aparece en la pestaña del explorador cuando se está visualizando el artículo.</span><span class="sxs-lookup"><span data-stu-id="5b920-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="5b920-142">Los títulos de página se usan para SEO e indización, así que no cambies el título a menos que sea necesario (aunque esto es menos crítico antes de que la documentación se haga pública).</span><span class="sxs-lookup"><span data-stu-id="5b920-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="5b920-143">**description:** escriba una breve descripción del contenido del artículo, lo que aumenta el seo y la detección.</span><span class="sxs-lookup"><span data-stu-id="5b920-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="5b920-144">**autor:** si es el propietario principal de la página, agregue aquí el alias de GitHub.</span><span class="sxs-lookup"><span data-stu-id="5b920-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="5b920-145">**ms.author:** si es el propietario principal de la página, agregue el alias de Microsoft aquí (no necesita @microsoft.com, solo el alias).</span><span class="sxs-lookup"><span data-stu-id="5b920-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="5b920-146">**ms.date:** actualice la fecha si va a agregar contenido principal a la página, pero no para correcciones como la aclaración, el formato, la gramática o la ortografía.</span><span class="sxs-lookup"><span data-stu-id="5b920-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="5b920-147">**palabras clave:** ayuda con palabras clave en SEO (optimización del motor de búsqueda).</span><span class="sxs-lookup"><span data-stu-id="5b920-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="5b920-148">Agregue palabras clave, separadas por una coma y un espacio, que sean específicas del artículo, pero sin puntuación después de la última palabra clave de la lista.</span><span class="sxs-lookup"><span data-stu-id="5b920-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="5b920-149">No es necesario agregar palabras clave globales que se apliquen a todos los artículos, ya que se administran en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="5b920-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="5b920-150">Cuando haya completado las ediciones del artículo, desplácese hacia abajo y seleccione **Proponer cambio de archivo.**</span><span class="sxs-lookup"><span data-stu-id="5b920-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="5b920-151">En la página siguiente, seleccione **Crear solicitud de extracción** para combinar la rama creada automáticamente en "patrón".</span><span class="sxs-lookup"><span data-stu-id="5b920-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="5b920-152">Repita los pasos anteriores para el siguiente artículo que desee editar.</span><span class="sxs-lookup"><span data-stu-id="5b920-152">Repeat the steps above for the next article you want to edit.</span></span>

## <span data-ttu-id="5b920-153">Cambiar el nombre o eliminar un artículo existente</span><span class="sxs-lookup"><span data-stu-id="5b920-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="5b920-154">Si el cambio cambiará de nombre o eliminará un artículo existente, asegúrese de agregar un redireccionamiento.</span><span class="sxs-lookup"><span data-stu-id="5b920-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="5b920-155">De este modo, cualquier persona con un vínculo al artículo existente seguirá en el lugar adecuado.</span><span class="sxs-lookup"><span data-stu-id="5b920-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="5b920-156">Los redireccionamientos se administran mediante .openpublishing.redirection.jsen el archivo en la raíz del repositorio.</span><span class="sxs-lookup"><span data-stu-id="5b920-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="5b920-157">Para agregar un redireccionamiento .openpublishing.redirection.js, agregue una entrada a la `redirections` matriz:</span><span class="sxs-lookup"><span data-stu-id="5b920-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="5b920-158">Se trata de la ruta de acceso relativa del repositorio `source_path` al artículo antiguo que está quitando.</span><span class="sxs-lookup"><span data-stu-id="5b920-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="5b920-159">Asegúrese de que la ruta comienza por `mixed-reality-docs` y termina por `.md` .</span><span class="sxs-lookup"><span data-stu-id="5b920-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="5b920-160">Se `redirect_url` trata de la dirección URL pública relativa del artículo anterior al nuevo artículo.</span><span class="sxs-lookup"><span data-stu-id="5b920-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="5b920-161">Asegúrese de que esta dirección URL **no** contiene o, como hace referencia a la dirección URL pública `mixed-reality-docs` y no a la ruta de acceso del `.md` repositorio.</span><span class="sxs-lookup"><span data-stu-id="5b920-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="5b920-162">Se permite vincular a una sección dentro del nuevo artículo que `#section` se usa.</span><span class="sxs-lookup"><span data-stu-id="5b920-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="5b920-163">También puede usar una ruta de acceso absoluta a otro sitio aquí, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="5b920-163">You can also use an absolute path to another site here, if necessary.</span></span>

- `redirect_document_id` <span data-ttu-id="5b920-164">indica si desea conservar el identificador del documento del archivo anterior.</span><span class="sxs-lookup"><span data-stu-id="5b920-164">indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="5b920-165">El valor predeterminado es `false` .</span><span class="sxs-lookup"><span data-stu-id="5b920-165">The default is `false`.</span></span> <span data-ttu-id="5b920-166">Se `true` usa si desea conservar el valor de atributo del artículo `ms.documentid` redirigido.</span><span class="sxs-lookup"><span data-stu-id="5b920-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="5b920-167">Si conserva el identificador del documento, los datos, como las vistas de página y las clasificaciones, se transferirán al artículo de destino.</span><span class="sxs-lookup"><span data-stu-id="5b920-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="5b920-168">Haga esto si el redireccionamiento es principalmente un cambio de nombre y no un puntero a un artículo diferente que solo cubre parte del mismo contenido.</span><span class="sxs-lookup"><span data-stu-id="5b920-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="5b920-169">Si agrega un redireccionamiento, asegúrese de eliminar también el archivo antiguo.</span><span class="sxs-lookup"><span data-stu-id="5b920-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <span data-ttu-id="5b920-170">Creación de un nuevo artículo</span><span class="sxs-lookup"><span data-stu-id="5b920-170">Creating a new article</span></span>

<span data-ttu-id="5b920-171">Use el siguiente flujo de trabajo para *crear nuevos artículos en* el repositorio de documentación a través de GitHub en un explorador web:</span><span class="sxs-lookup"><span data-stu-id="5b920-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="5b920-172">Cree una bifurcación de la rama "patrón" de MicrosoftDocs/realidad mixta (con el botón Bifurcación situado en la parte superior derecha). \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5b920-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![Bifurca la rama maestra.](images/forkbranch.png)
   
2. <span data-ttu-id="5b920-174">En la carpeta "mixed-reality-docs", seleccione **Crear nuevo archivo** en la parte superior derecha.</span><span class="sxs-lookup"><span data-stu-id="5b920-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="5b920-175">Cree un nombre de página para el artículo (use guiones en lugar de espacios y no use signos de puntuación ni apóstrofes) y anexe ".md"</span><span class="sxs-lookup"><span data-stu-id="5b920-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![Asigne un nombre a la nueva página.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="5b920-177">Asegúrese de crear el nuevo artículo desde la carpeta "documentos de realidad mixta".</span><span class="sxs-lookup"><span data-stu-id="5b920-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="5b920-178">Para confirmar esto, compruebe "/mixed-reality-docs/" en la nueva línea de nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="5b920-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="5b920-179">En la parte superior de la nueva página, agregue el siguiente bloque de metadatos:</span><span class="sxs-lookup"><span data-stu-id="5b920-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="5b920-180">Rellene los campos de metadatos relevantes según las instrucciones de la [sección anterior.](#editing-an-existing-article)</span><span class="sxs-lookup"><span data-stu-id="5b920-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="5b920-181">Escribir contenido de artículo con [los conceptos básicos de Markdown](#markdown-basics).</span><span class="sxs-lookup"><span data-stu-id="5b920-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="5b920-182">Agregue una `## See also` sección en la parte inferior del artículo con vínculos a otros artículos relevantes.</span><span class="sxs-lookup"><span data-stu-id="5b920-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="5b920-183">Cuando haya terminado, seleccione **Confirmar nuevo archivo.**</span><span class="sxs-lookup"><span data-stu-id="5b920-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="5b920-184">Seleccione Nueva solicitud **de** extracción y combine la rama 'master' de la bifurcación en MicrosoftDocs/'master' de realidad mixta (asegúrese de que la flecha apunta de la forma correcta).</span><span class="sxs-lookup"><span data-stu-id="5b920-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Crear una solicitud de extracción desde la bifurcación a MicrosoftDocs/realidad mixta](images/pr-to-master.png)

## <span data-ttu-id="5b920-186">Conceptos básicos de Markdown</span><span class="sxs-lookup"><span data-stu-id="5b920-186">Markdown basics</span></span>

<span data-ttu-id="5b920-187">Los siguientes recursos le ayudarán a aprender a editar la documentación con el lenguaje Markdown:</span><span class="sxs-lookup"><span data-stu-id="5b920-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="5b920-188">Conceptos básicos de Markdown</span><span class="sxs-lookup"><span data-stu-id="5b920-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="5b920-189">Recursos adicionales para escribir Markdown para docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5b920-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <span data-ttu-id="5b920-190">Agregar tablas</span><span class="sxs-lookup"><span data-stu-id="5b920-190">Adding tables</span></span>

<span data-ttu-id="5b920-191">Debido a la forma docs.microsoft.com tablas de estilos, no tendrán bordes ni estilos personalizados, incluso si intenta usar CSS en línea.</span><span class="sxs-lookup"><span data-stu-id="5b920-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="5b920-192">Parecerá que funciona durante un breve período de tiempo, pero finalmente la plataforma quitará el estilo de la tabla.</span><span class="sxs-lookup"><span data-stu-id="5b920-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="5b920-193">Por lo tanto, planee con antelación y mantenga las tablas sencillas.</span><span class="sxs-lookup"><span data-stu-id="5b920-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="5b920-194">[Este es un sitio que facilita las tablas de Markdown.](https://www.tablesgenerator.com/markdown_tables)</span><span class="sxs-lookup"><span data-stu-id="5b920-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="5b920-195">La [extensión Docs Markdown](https://docs.microsoft.com/teamblog/docs-extension) para Visual Studio Code también facilita la generación de tablas si usa un código de Visual Studio [(vea](#using-visual-studio-code) a continuación) para editar la documentación.</span><span class="sxs-lookup"><span data-stu-id="5b920-195">The [Docs Markdown Extension for Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <span data-ttu-id="5b920-196">Agregar imágenes</span><span class="sxs-lookup"><span data-stu-id="5b920-196">Adding images</span></span>

<span data-ttu-id="5b920-197">Deberá cargar las imágenes en la carpeta "mixed-reality-docs/images" del repositorio y, a continuación, hacer referencia a ellas correctamente en el artículo.</span><span class="sxs-lookup"><span data-stu-id="5b920-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="5b920-198">Las imágenes se mostrarán automáticamente a tamaño completo, lo que significa que las imágenes grandes rellenarán todo el ancho del artículo.</span><span class="sxs-lookup"><span data-stu-id="5b920-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="5b920-199">Se recomienda dimensionar previamente las imágenes antes de cargarlas.</span><span class="sxs-lookup"><span data-stu-id="5b920-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="5b920-200">El ancho recomendado es de entre 600 y 700 píxeles, aunque debes cambiar el tamaño hacia arriba o hacia abajo si es una captura de pantalla densa o una fracción de una captura de pantalla, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="5b920-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="5b920-201">Solo puedes cargar imágenes en el repositorio bifurcado antes de combinarlas.</span><span class="sxs-lookup"><span data-stu-id="5b920-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="5b920-202">Por lo tanto, si planea agregar imágenes a un artículo, deberá usar un código de Visual Studio para agregar las imágenes [a](#using-visual-studio-code) la carpeta "imágenes" de la bifurcación en primer lugar o asegúrese de que ha hecho lo siguiente en un explorador web:</span><span class="sxs-lookup"><span data-stu-id="5b920-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="5b920-203">Bifurcado el repositorio MicrosoftDocs/mixed-reality.</span><span class="sxs-lookup"><span data-stu-id="5b920-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="5b920-204">Editó el artículo en la bifurcación.</span><span class="sxs-lookup"><span data-stu-id="5b920-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="5b920-205">Ha cargado las imágenes a las que hace referencia en su artículo a la carpeta "mixed-reality-docs/images" en la bifurcación.</span><span class="sxs-lookup"><span data-stu-id="5b920-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="5b920-206">Se ha **creado una solicitud de** extracción para combinar la bifurcación en la rama "maestra" de MicrosoftDocs/realidad mixta.</span><span class="sxs-lookup"><span data-stu-id="5b920-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="5b920-207">Para obtener información sobre cómo configurar su propio repositorio bifurcado, siga las instrucciones para [crear un nuevo artículo.](#creating-a-new-article)</span><span class="sxs-lookup"><span data-stu-id="5b920-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <span data-ttu-id="5b920-208">Obtener una vista previa del trabajo</span><span class="sxs-lookup"><span data-stu-id="5b920-208">Previewing your work</span></span>

<span data-ttu-id="5b920-209">Durante la edición en GitHub a \*\*\*\* través de un explorador web, puede seleccionar la pestaña Vista previa cerca de la parte superior de la página para obtener una vista previa del trabajo antes de confirmarlo.</span><span class="sxs-lookup"><span data-stu-id="5b920-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="5b920-210">La vista previa de los cambios review.docs.microsoft.com solo está disponible para los empleados de Microsoft</span><span class="sxs-lookup"><span data-stu-id="5b920-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="5b920-211">Empleados de Microsoft: una vez que sus contribuciones se han combinado en la rama "maestra", puede revisar el contenido antes de que se haga público en https://review.docs.microsoft.com/hololens?branch=master .</span><span class="sxs-lookup"><span data-stu-id="5b920-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at https://review.docs.microsoft.com/hololens?branch=master.</span></span> <span data-ttu-id="5b920-212">Busque el artículo con la tabla de contenido de la columna izquierda.</span><span class="sxs-lookup"><span data-stu-id="5b920-212">Find your article using the table of contents in the left column.</span></span>

## <span data-ttu-id="5b920-213">Edición en el explorador frente a edición con un cliente de escritorio</span><span class="sxs-lookup"><span data-stu-id="5b920-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="5b920-214">La edición en el explorador es la forma más sencilla de realizar cambios rápidos, pero hay algunas desventajas:</span><span class="sxs-lookup"><span data-stu-id="5b920-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="5b920-215">You don't get spell-check.</span><span class="sxs-lookup"><span data-stu-id="5b920-215">You don't get spell-check.</span></span>
- <span data-ttu-id="5b920-216">No obtiene ningún vínculo inteligente a otros artículos (tiene que escribir manualmente el nombre de archivo del artículo).</span><span class="sxs-lookup"><span data-stu-id="5b920-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="5b920-217">Puede ser complicado cargar y hacer referencia a imágenes.</span><span class="sxs-lookup"><span data-stu-id="5b920-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="5b920-218">Si prefieres no abordar estos problemas, usa un cliente de escritorio como [Visual Studio Code](https://code.visualstudio.com/) con un par de extensiones útiles [al](#useful-extensions) contribuir.</span><span class="sxs-lookup"><span data-stu-id="5b920-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <span data-ttu-id="5b920-219">Uso Visual Studio código</span><span class="sxs-lookup"><span data-stu-id="5b920-219">Using Visual Studio Code</span></span>

<span data-ttu-id="5b920-220">Por los motivos [mencionados anteriormente,](#editing-in-the-browser-vs-editing-with-a-desktop-client)es posible que prefiera usar un cliente de escritorio para editar la documentación en lugar de un explorador web.</span><span class="sxs-lookup"><span data-stu-id="5b920-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="5b920-221">Se recomienda usar [Visual Studio código de usuario.](https://code.visualstudio.com/)</span><span class="sxs-lookup"><span data-stu-id="5b920-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <span data-ttu-id="5b920-222">Programa de instalación</span><span class="sxs-lookup"><span data-stu-id="5b920-222">Setup</span></span>

<span data-ttu-id="5b920-223">Siga estos pasos para configurar el código Visual Studio para que funcione con este repositorio:</span><span class="sxs-lookup"><span data-stu-id="5b920-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="5b920-224">En un explorador web:</span><span class="sxs-lookup"><span data-stu-id="5b920-224">In a web browser:</span></span>
    1. <span data-ttu-id="5b920-225">Instalar [Git para su PC.](https://git-scm.com/downloads)</span><span class="sxs-lookup"><span data-stu-id="5b920-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="5b920-226">Instalar Visual Studio código de [instalación.](https://code.visualstudio.com/)</span><span class="sxs-lookup"><span data-stu-id="5b920-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="5b920-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span><span class="sxs-lookup"><span data-stu-id="5b920-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="5b920-228">En la bifurcación, seleccione **Clonar o descargar** y copiar la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="5b920-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="5b920-229">Cree un clon local de la bifurcación en Visual Studio código:</span><span class="sxs-lookup"><span data-stu-id="5b920-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="5b920-230">En el **menú** Ver, seleccione **Paleta de comandos.**</span><span class="sxs-lookup"><span data-stu-id="5b920-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="5b920-231">Escriba "Git: Clone".</span><span class="sxs-lookup"><span data-stu-id="5b920-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="5b920-232">Pegue la dirección URL que copió.</span><span class="sxs-lookup"><span data-stu-id="5b920-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="5b920-233">Elige dónde guardar el clon en el equipo.</span><span class="sxs-lookup"><span data-stu-id="5b920-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="5b920-234">Seleccione **Abrir repositorio** en la ventana emergente.</span><span class="sxs-lookup"><span data-stu-id="5b920-234">Select **Open repo** in the pop-up.</span></span>

### <span data-ttu-id="5b920-235">Edición de documentación</span><span class="sxs-lookup"><span data-stu-id="5b920-235">Editing documentation</span></span>

<span data-ttu-id="5b920-236">Use el siguiente flujo de trabajo para realizar cambios en la documentación con Visual Studio código:</span><span class="sxs-lookup"><span data-stu-id="5b920-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="5b920-237">Todas las instrucciones para [editar](#editing-an-existing-article) [y](#creating-a-new-article) crear [artículos,](#markdown-basics)y los conceptos básicos de edición de Markdown , de arriba se aplican al usar Visual Studio código.</span><span class="sxs-lookup"><span data-stu-id="5b920-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="5b920-238">Asegúrese de que la bifurcación clonada esté actualizada con el repositorio oficial.</span><span class="sxs-lookup"><span data-stu-id="5b920-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="5b920-239">En un explorador web, cree una solicitud de extracción para sincronizar los cambios recientes de otros colaboradores en MicrosoftDocs/"master" de realidad mixta con la bifurcación (asegúrese de que la flecha apunta hacia la derecha).</span><span class="sxs-lookup"><span data-stu-id="5b920-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![Sincronizar los cambios de MicrosoftDocs/realidad mixta con la bifurcación](images/sync-repos.png)
      
   2. <span data-ttu-id="5b920-241">En Visual Studio código, seleccione el botón de sincronización para sincronizar la bifurcación actualizada con el clon local.</span><span class="sxs-lookup"><span data-stu-id="5b920-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![Haga clic en la imagen del botón de sincronización](images/sync-clone.png)
      
2. <span data-ttu-id="5b920-243">Cree o edite artículos en el repositorio clonado con Visual Studio código.</span><span class="sxs-lookup"><span data-stu-id="5b920-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="5b920-244">Edite uno o varios artículos (agregue imágenes a la carpeta "imágenes" si es necesario).</span><span class="sxs-lookup"><span data-stu-id="5b920-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="5b920-245">**Guardar** los cambios en **el Explorador**.</span><span class="sxs-lookup"><span data-stu-id="5b920-245">**Save** changes in **Explorer**.</span></span>
      
      ![Elija "Guardar todo" en el Explorador](images/explorer-save.png)
      
   3. <span data-ttu-id="5b920-247">**Confirmar todos los** cambios en **el Control de código fuente** (escriba el mensaje de confirmación cuando se le pida).</span><span class="sxs-lookup"><span data-stu-id="5b920-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
   
      ![Elija "Confirmar todo" en el control de código fuente](images/source-control-commit.png)
      
   4. <span data-ttu-id="5b920-249">Seleccione el **botón de** sincronización para volver a sincronizar los cambios en el origen (la bifurcación en GitHub).</span><span class="sxs-lookup"><span data-stu-id="5b920-249">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![Haga clic en el botón de sincronización](images/sync-back.png)
      
3. <span data-ttu-id="5b920-251">En un explorador web, cree una solicitud de extracción para sincronizar los nuevos cambios en la bifurcación de nuevo a MicrosoftDocs/'master' de realidad mixta (asegúrese de que la flecha apunta de la forma correcta).</span><span class="sxs-lookup"><span data-stu-id="5b920-251">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Crear una solicitud de extracción desde la bifurcación a MicrosoftDocs/realidad mixta](images/pr-to-master.png)

### <span data-ttu-id="5b920-253">Extensiones útiles</span><span class="sxs-lookup"><span data-stu-id="5b920-253">Useful extensions</span></span>

<span data-ttu-id="5b920-254">Las siguientes extensiones Visual Studio código son útiles al editar la documentación:</span><span class="sxs-lookup"><span data-stu-id="5b920-254">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="5b920-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** para abrir un menú de opciones de creación de documentos como:</span><span class="sxs-lookup"><span data-stu-id="5b920-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="5b920-256">Buscar y hacer referencia a imágenes que ha cargado.</span><span class="sxs-lookup"><span data-stu-id="5b920-256">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="5b920-257">Agregue formato como listas, tablas y llamadas específicas de documentos como `>[!NOTE]` .</span><span class="sxs-lookup"><span data-stu-id="5b920-257">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="5b920-258">Buscar y hacer referencia a vínculos internos y marcadores (vínculos a secciones específicas dentro de una página).</span><span class="sxs-lookup"><span data-stu-id="5b920-258">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="5b920-259">Los errores de formato están resaltados (mantenga el mouse sobre el error para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="5b920-259">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="5b920-260">[Corrector ortográfico de código:](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) las palabras mal escritas estarán subrayadas; haga clic con el botón secundario en una palabra mal escrita para cambiarla o guardarla en el diccionario.</span><span class="sxs-lookup"><span data-stu-id="5b920-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
