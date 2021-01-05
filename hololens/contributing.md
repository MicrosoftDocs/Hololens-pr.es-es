---
title: Instrucciones para contribuir
description: Obtén información sobre cómo contribuir a los documentos de HoloLens en la plataforma de docs.microsoft.com usando Markdown con modo GitHub.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.openlocfilehash: d17d9e30ca3699a7bd6c69b75043c6974a2bde1f
ms.sourcegitcommit: 3827d244426ffecb517f6cfa714eeef9363c062d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "11253695"
---
# <span data-ttu-id="fa33d-103">Contribución a la documentación de HoloLens</span><span class="sxs-lookup"><span data-stu-id="fa33d-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="fa33d-104">Bienvenido a la [documentación de HoloLens](https://github.com/MicrosoftDocs/Hololens).</span><span class="sxs-lookup"><span data-stu-id="fa33d-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="fa33d-105">Todos los artículos que cree o edite en este repositorio serán **visibles para el público.**</span><span class="sxs-lookup"><span data-stu-id="fa33d-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="fa33d-106">Los documentos de HoloLens se muestran en la plataforma docs.microsoft.com, que usa Markdown con modo de GitHub con características de Markdig.</span><span class="sxs-lookup"><span data-stu-id="fa33d-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="fa33d-107">El contenido que edite en este repositorio se vuelve a dar formato a páginas estilizadas que se muestran en https://docs.microsoft.com/hololens .</span><span class="sxs-lookup"><span data-stu-id="fa33d-107">The content you edit in this repo gets formatted into stylized pages that show up at https://docs.microsoft.com/hololens.</span></span> 

<span data-ttu-id="fa33d-108">Esta página cubre los pasos básicos y las pautas para la contribución y los vínculos a los conceptos básicos de Markdown.</span><span class="sxs-lookup"><span data-stu-id="fa33d-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="fa33d-109">Gracias por su contribución.</span><span class="sxs-lookup"><span data-stu-id="fa33d-109">Thanks for your contribution!</span></span>

## <span data-ttu-id="fa33d-110">Repos disponibles</span><span class="sxs-lookup"><span data-stu-id="fa33d-110">Available repos</span></span>

| <span data-ttu-id="fa33d-111">Nombre del repositorio</span><span class="sxs-lookup"><span data-stu-id="fa33d-111">Repository name</span></span> | <span data-ttu-id="fa33d-112">Dirección URL</span><span class="sxs-lookup"><span data-stu-id="fa33d-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="fa33d-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="fa33d-113">HoloLens</span></span> | [<span data-ttu-id="fa33d-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="fa33d-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="fa33d-115">Realidad mixta</span><span class="sxs-lookup"><span data-stu-id="fa33d-115">Mixed Reality</span></span> | [<span data-ttu-id="fa33d-116">MicrosoftDocs/Mixed-Reality</span><span class="sxs-lookup"><span data-stu-id="fa33d-116">MicrosoftDocs/mixed-reality</span></span>](https://docs.microsoft.com/windows/mixed-reality) |
| <span data-ttu-id="fa33d-117">Guía de entusiastas de VR</span><span class="sxs-lookup"><span data-stu-id="fa33d-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="fa33d-118">MicrosoftDocs/Mixed-Reality/entusiasta-guía</span><span class="sxs-lookup"><span data-stu-id="fa33d-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <span data-ttu-id="fa33d-119">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="fa33d-119">Before you start</span></span>

<span data-ttu-id="fa33d-120">Si aún no tiene una cuenta, tendrá que [crear una cuenta de github](https://github.com/join).</span><span class="sxs-lookup"><span data-stu-id="fa33d-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="fa33d-121">Si es un empleado de Microsoft, vincule su cuenta de GitHub al alias de Microsoft en el [portal de origen abierto de Microsoft](https://repos.opensource.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="fa33d-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="fa33d-122">Únase a las organizaciones **"Microsoft"** y **"MicrosoftDocs"** .</span><span class="sxs-lookup"><span data-stu-id="fa33d-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="fa33d-123">Al configurar su cuenta de GitHub, también recomendamos estas precauciones de seguridad:</span><span class="sxs-lookup"><span data-stu-id="fa33d-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="fa33d-124">Cree una [contraseña segura para su cuenta de github](https://github.com/settings/admin).</span><span class="sxs-lookup"><span data-stu-id="fa33d-124">Create a [strong password for your Github account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="fa33d-125">Habilitar [la autenticación en dos fases](https://github.com/settings/two_factor_authentication/configure).</span><span class="sxs-lookup"><span data-stu-id="fa33d-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="fa33d-126">Guarde los [códigos de recuperación](https://github.com/settings/auth/recovery-codes) en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="fa33d-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="fa33d-127">Actualiza la [configuración de tu perfil público](https://github.com/settings/profile).</span><span class="sxs-lookup"><span data-stu-id="fa33d-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="fa33d-128">Establezca su nombre y considere la posibilidad de configurar su *correo electrónico público* para *no mostrar mi dirección de correo electrónico*.</span><span class="sxs-lookup"><span data-stu-id="fa33d-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="fa33d-129">Le recomendamos que cargue una imagen de perfil porque se muestra una miniatura en las páginas de documentos en las que participa.</span><span class="sxs-lookup"><span data-stu-id="fa33d-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="fa33d-130">Si planea usar la línea de comandos, considere la posibilidad de configurar [git Credential Manager para Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span><span class="sxs-lookup"><span data-stu-id="fa33d-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="fa33d-131">De ese modo, no tendrá que escribir la contraseña cada vez que haga una contribución.</span><span class="sxs-lookup"><span data-stu-id="fa33d-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="fa33d-132">El sistema de publicación está vinculado a GitHub, por lo que estos pasos son importantes.</span><span class="sxs-lookup"><span data-stu-id="fa33d-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="fa33d-133">Aparecerá como autor o colaborador de cada artículo con su alias de GitHub.</span><span class="sxs-lookup"><span data-stu-id="fa33d-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <span data-ttu-id="fa33d-134">Editar un artículo existente</span><span class="sxs-lookup"><span data-stu-id="fa33d-134">Editing an existing article</span></span>

<span data-ttu-id="fa33d-135">Use el siguiente flujo de trabajo para hacer actualizaciones en un *artículo existente* a través de github en un explorador Web:</span><span class="sxs-lookup"><span data-stu-id="fa33d-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="fa33d-136">Vaya al artículo que desea editar en la carpeta "realidad mixta" docs ".</span><span class="sxs-lookup"><span data-stu-id="fa33d-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>
2. <span data-ttu-id="fa33d-137">En la parte superior derecha, haga clic en el botón Editar (icono de lápiz) para bifurcar automáticamente una rama descartable fuera de la rama "patrón".</span><span class="sxs-lookup"><span data-stu-id="fa33d-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![Editar un artículo.](images/editpage.png)
3. <span data-ttu-id="fa33d-139">Edite el contenido del artículo según las ["nociones básicas de Markdown"](#markdown-basics).</span><span class="sxs-lookup"><span data-stu-id="fa33d-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>
4. <span data-ttu-id="fa33d-140">Actualizar metadatos en la parte superior de cada artículo:</span><span class="sxs-lookup"><span data-stu-id="fa33d-140">Update metadata at the top of each article:</span></span>
   * <span data-ttu-id="fa33d-141">**título**: título de página que aparece en la pestaña del explorador cuando se está viendo el artículo.</span><span class="sxs-lookup"><span data-stu-id="fa33d-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="fa33d-142">Los títulos de página se usan para SEO e indización, así que no cambie el título a menos que sea necesario (aunque es menos importante antes de que la documentación sea pública).</span><span class="sxs-lookup"><span data-stu-id="fa33d-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="fa33d-143">**Descripción**: escriba una breve descripción del contenido del artículo, que mejora la SEO y la detección.</span><span class="sxs-lookup"><span data-stu-id="fa33d-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="fa33d-144">**autor**: si es el propietario principal de la página, agregue aquí su alias de github.</span><span class="sxs-lookup"><span data-stu-id="fa33d-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="fa33d-145">**MS. Author**: si es el propietario principal de la página, agregue su alias de Microsoft aquí (no necesita @microsoft. com, solo el alias).</span><span class="sxs-lookup"><span data-stu-id="fa33d-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="fa33d-146">**MS. fecha**: actualice la fecha Si va a agregar contenido principal a la página, pero no para soluciones como aclaración, formato, gramática o ortografía.</span><span class="sxs-lookup"><span data-stu-id="fa33d-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="fa33d-147">**palabras clave**: ayuda de palabras clave en SEO (optimización del motor de búsqueda).</span><span class="sxs-lookup"><span data-stu-id="fa33d-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="fa33d-148">Agregue palabras clave, separadas por una coma y un espacio, que sean específicas de su artículo, pero sin signos de puntuación después de la última palabra clave de la lista.</span><span class="sxs-lookup"><span data-stu-id="fa33d-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="fa33d-149">No es necesario agregar palabras clave globales que se apliquen a todos los artículos, puesto que se administran en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="fa33d-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
5. <span data-ttu-id="fa33d-150">Cuando haya completado las ediciones de los artículos, desplácese hacia abajo y seleccione **proponer cambio de archivo**.</span><span class="sxs-lookup"><span data-stu-id="fa33d-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>
6. <span data-ttu-id="fa33d-151">En la página siguiente, seleccione **crear solicitud de incorporación de inserción** para fusionar la rama creada automáticamente en ' maestra '.</span><span class="sxs-lookup"><span data-stu-id="fa33d-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>
7. <span data-ttu-id="fa33d-152">Repita los pasos anteriores para el siguiente artículo que desea editar.</span><span class="sxs-lookup"><span data-stu-id="fa33d-152">Repeat the steps above for the next article you want to edit.</span></span>

## <span data-ttu-id="fa33d-153">Cambiar el nombre o eliminar un artículo existente</span><span class="sxs-lookup"><span data-stu-id="fa33d-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="fa33d-154">Si su cambio cambiará de nombre o elimina un artículo existente, asegúrese de agregar un redireccionamiento.</span><span class="sxs-lookup"><span data-stu-id="fa33d-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="fa33d-155">De ese modo, cualquier persona que tenga un vínculo al artículo existente terminará en el lugar correcto.</span><span class="sxs-lookup"><span data-stu-id="fa33d-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="fa33d-156">Las redirecciones las administra el .openpublishing.redirection.jsen el archivo en la raíz del repositorio.</span><span class="sxs-lookup"><span data-stu-id="fa33d-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="fa33d-157">Para agregar un redireccionamiento a .openpublishing.redirection.js, agregue una entrada a la `redirections` matriz:</span><span class="sxs-lookup"><span data-stu-id="fa33d-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="fa33d-158">`source_path`Es la ruta de acceso relativa al repositorio del artículo antiguo que va a quitar.</span><span class="sxs-lookup"><span data-stu-id="fa33d-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="fa33d-159">Asegúrese de que la ruta comienza por `mixed-reality-docs` y termina en `.md` .</span><span class="sxs-lookup"><span data-stu-id="fa33d-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>
- <span data-ttu-id="fa33d-160">`redirect_url`Es la dirección URL relativa pública del artículo anterior al nuevo artículo.</span><span class="sxs-lookup"><span data-stu-id="fa33d-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="fa33d-161">Asegúrese de que esta dirección URL **no** contiene `mixed-reality-docs` o `.md` , como hace referencia a la dirección URL pública y no a la ruta del repositorio.</span><span class="sxs-lookup"><span data-stu-id="fa33d-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="fa33d-162">Se permite la vinculación a una sección en el nuevo artículo mediante `#section` .</span><span class="sxs-lookup"><span data-stu-id="fa33d-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="fa33d-163">También puede usar una ruta de acceso absoluta a otro sitio, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="fa33d-163">You can also use an absolute path to another site here, if necessary.</span></span>
- `redirect_document_id` <span data-ttu-id="fa33d-164">indica si desea mantener el identificador de documento del archivo anterior.</span><span class="sxs-lookup"><span data-stu-id="fa33d-164">indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="fa33d-165">El valor predeterminado es `false` .</span><span class="sxs-lookup"><span data-stu-id="fa33d-165">The default is `false`.</span></span> <span data-ttu-id="fa33d-166">Use `true` esta si desea conservar el `ms.documentid` valor de atributo del artículo redirigido.</span><span class="sxs-lookup"><span data-stu-id="fa33d-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="fa33d-167">Si conserva el identificador de documento, los datos, como las vistas de página y las clasificaciones, se transferirán al artículo de destino.</span><span class="sxs-lookup"><span data-stu-id="fa33d-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="fa33d-168">Haga esto si el redireccionamiento es principalmente un cambio de nombre y no un puntero a un artículo diferente que solo cubre parte del mismo contenido.</span><span class="sxs-lookup"><span data-stu-id="fa33d-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="fa33d-169">Si agrega un redireccionamiento, asegúrese de eliminar también el archivo antiguo.</span><span class="sxs-lookup"><span data-stu-id="fa33d-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <span data-ttu-id="fa33d-170">Crear un nuevo artículo</span><span class="sxs-lookup"><span data-stu-id="fa33d-170">Creating a new article</span></span>

<span data-ttu-id="fa33d-171">Use el siguiente flujo de trabajo para *crear artículos nuevos* en el repositorio de documentación a través de github en un explorador Web:</span><span class="sxs-lookup"><span data-stu-id="fa33d-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="fa33d-172">Crea una bifurcación fuera de la rama de MicrosoftDocs/"patrón" de realidad mixta (con el botón de la **horquilla** en la parte superior derecha).</span><span class="sxs-lookup"><span data-stu-id="fa33d-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![Bifurcar la rama principal.](images/forkbranch.png)
2. <span data-ttu-id="fa33d-174">En la carpeta "realidad mixta" docs ", seleccione **crear nuevo archivo** en la parte superior derecha.</span><span class="sxs-lookup"><span data-stu-id="fa33d-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>
3. <span data-ttu-id="fa33d-175">Crear un nombre de página para el artículo (use guiones en lugar de espacios y no use signos de puntuación o apóstrofos) y anexe ". MD"</span><span class="sxs-lookup"><span data-stu-id="fa33d-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![Asigne un nombre a la página nueva.](images/newpagetitle.PNG)
   
   >[!IMPORTANT]
   ><span data-ttu-id="fa33d-177">Asegúrese de crear el nuevo artículo desde la carpeta "realidad mixta-documentos".</span><span class="sxs-lookup"><span data-stu-id="fa33d-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="fa33d-178">Para confirmarlo, busque "/Mixed-Reality-docs/" en la nueva línea nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="fa33d-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="fa33d-179">En la parte superior de la página nueva, agregue el siguiente bloque de metadatos:</span><span class="sxs-lookup"><span data-stu-id="fa33d-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="fa33d-180">Rellene los campos de metadatos pertinentes según las instrucciones de la [sección anterior](#editing-an-existing-article).</span><span class="sxs-lookup"><span data-stu-id="fa33d-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>
6. <span data-ttu-id="fa33d-181">Escribir contenido de artículos con [conceptos básicos de Markdown](#markdown-basics).</span><span class="sxs-lookup"><span data-stu-id="fa33d-181">Write article content using [Markdown basics](#markdown-basics).</span></span>
7. <span data-ttu-id="fa33d-182">Agregue una `## See also` sección en la parte inferior del artículo con vínculos a otros artículos relevantes.</span><span class="sxs-lookup"><span data-stu-id="fa33d-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>
8. <span data-ttu-id="fa33d-183">Cuando haya terminado, seleccione **confirmar nuevo archivo**.</span><span class="sxs-lookup"><span data-stu-id="fa33d-183">When finished, select **Commit new file**.</span></span>
9. <span data-ttu-id="fa33d-184">Selecciona **New pull request** y combina la rama ' Master ' de la horquilla en MicrosoftDocs/mixed-reality ' Master ' (asegúrate de que la flecha apunte de la manera correcta).</span><span class="sxs-lookup"><span data-stu-id="fa33d-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Crear una solicitud de incorporación de extracción desde la horquilla en MicrosoftDocs/Mixed-Reality](images/pr_to_master.PNG)

## <span data-ttu-id="fa33d-186">Conceptos básicos de Markdown</span><span class="sxs-lookup"><span data-stu-id="fa33d-186">Markdown basics</span></span>

<span data-ttu-id="fa33d-187">Los recursos siguientes le ayudarán a obtener información sobre cómo editar la documentación con el idioma de Markdown:</span><span class="sxs-lookup"><span data-stu-id="fa33d-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="fa33d-188">Conceptos básicos de Markdown</span><span class="sxs-lookup"><span data-stu-id="fa33d-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="fa33d-189">Póster de referencia de Markdown a un vistazo</span><span class="sxs-lookup"><span data-stu-id="fa33d-189">Markdown-at-a-glance reference poster</span></span>](images/MarkdownPoster.pdf)
- [<span data-ttu-id="fa33d-190">Recursos adicionales para escribir Markdown para docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fa33d-190">Additional resources for writing Markdown for docs.microsoft.com</span></span>](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <span data-ttu-id="fa33d-191">Agregar tablas</span><span class="sxs-lookup"><span data-stu-id="fa33d-191">Adding tables</span></span>

<span data-ttu-id="fa33d-192">Debido a la forma en que las tablas de docs.microsoft.com Styles, no tendrán bordes ni estilos personalizados, aunque pruebe CSS en línea.</span><span class="sxs-lookup"><span data-stu-id="fa33d-192">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="fa33d-193">Parecerá que funciona durante un breve período de tiempo, pero la plataforma eliminará los estilos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="fa33d-193">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="fa33d-194">Así que es más sencillo mantener las tablas.</span><span class="sxs-lookup"><span data-stu-id="fa33d-194">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="fa33d-195">[Este es un sitio que simplifica las tablas de Markdown](https://www.tablesgenerator.com/markdown_tables).</span><span class="sxs-lookup"><span data-stu-id="fa33d-195">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="fa33d-196">La [extensión Markdown de docs para Visual Studio](https://docs.microsoft.com/teamblog/docs-extension) también hace que la generación de tablas sea fácil si usas [Visual Studio Code (ver a continuación)](#using-visual-studio-code) para editar la documentación.</span><span class="sxs-lookup"><span data-stu-id="fa33d-196">The [Docs Markdown Extension for Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <span data-ttu-id="fa33d-197">Agregar imágenes</span><span class="sxs-lookup"><span data-stu-id="fa33d-197">Adding images</span></span>

<span data-ttu-id="fa33d-198">Tendrá que cargar las imágenes en la carpeta "realidad mixta-documentos/imágenes" en el repositorio y, a continuación, hacer referencia a ellas correctamente en el artículo.</span><span class="sxs-lookup"><span data-stu-id="fa33d-198">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="fa33d-199">Las imágenes se mostrarán automáticamente a tamaño completo, lo que significa que las imágenes grandes rellenarán toda la anchura del artículo.</span><span class="sxs-lookup"><span data-stu-id="fa33d-199">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="fa33d-200">Le recomendamos que ajuste el tamaño de las imágenes antes de cargarlas.</span><span class="sxs-lookup"><span data-stu-id="fa33d-200">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="fa33d-201">El ancho recomendado es de entre 600 y 700 píxeles, aunque debe ajustar el tamaño si es una captura de pantalla densa o una fracción de una captura de pantalla, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="fa33d-201">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="fa33d-202">Solo puedes cargar imágenes en el repositorio bifurcado antes de fusionarlas.</span><span class="sxs-lookup"><span data-stu-id="fa33d-202">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="fa33d-203">Por lo tanto, si tiene previsto agregar imágenes a un artículo, tendrá que [usar el código de Visual Studio](#using-visual-studio-code) para agregar las imágenes a la carpeta "imágenes" de la horquilla en primer lugar, o asegurarse de que ha hecho lo siguiente en un explorador Web:</span><span class="sxs-lookup"><span data-stu-id="fa33d-203">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="fa33d-204">Se ha bifurcado el repositorio de MicrosoftDocs/realidad mixta.</span><span class="sxs-lookup"><span data-stu-id="fa33d-204">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="fa33d-205">Editó el artículo en la horquilla.</span><span class="sxs-lookup"><span data-stu-id="fa33d-205">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="fa33d-206">Ha cargado las imágenes a las que estás haciendo referencia en tu artículo a la carpeta "realidad mixta-documentos/imágenes" de tu horquilla.</span><span class="sxs-lookup"><span data-stu-id="fa33d-206">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="fa33d-207">Creó una **solicitud de incorporación de inserción** para fusionar tu bifurcación en la rama de MicrosoftDocs/"patrón" de realidad mixta.</span><span class="sxs-lookup"><span data-stu-id="fa33d-207">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="fa33d-208">Para obtener información sobre cómo configurar su propio repositorio bifurcado, siga las instrucciones para [crear un nuevo artículo](#creating-a-new-article).</span><span class="sxs-lookup"><span data-stu-id="fa33d-208">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <span data-ttu-id="fa33d-209">Obtener una vista previa del trabajo</span><span class="sxs-lookup"><span data-stu-id="fa33d-209">Previewing your work</span></span>

<span data-ttu-id="fa33d-210">Al editar en GitHub a través de un explorador Web, puede seleccionar la pestaña **vista previa** situada cerca de la parte superior de la página para obtener una vista previa de su trabajo antes de confirmarla.</span><span class="sxs-lookup"><span data-stu-id="fa33d-210">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="fa33d-211">La vista previa de los cambios en review.docs.microsoft.com solo está disponible para los empleados de Microsoft</span><span class="sxs-lookup"><span data-stu-id="fa33d-211">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="fa33d-212">Empleados de Microsoft: una vez que sus contribuciones se hayan fusionado en la rama "maestra", puede revisar el contenido antes de que se exponga públicamente https://review.docs.microsoft.com/hololens?branch=master .</span><span class="sxs-lookup"><span data-stu-id="fa33d-212">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at https://review.docs.microsoft.com/hololens?branch=master.</span></span> <span data-ttu-id="fa33d-213">Busque el artículo usando la tabla de contenido en la columna de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="fa33d-213">Find your article using the table of contents in the left column.</span></span>

## <span data-ttu-id="fa33d-214">Editar en el explorador y editar con un cliente de escritorio</span><span class="sxs-lookup"><span data-stu-id="fa33d-214">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="fa33d-215">Editar en el explorador es la manera más fácil de realizar cambios rápidos, pero hay algunas desventajas:</span><span class="sxs-lookup"><span data-stu-id="fa33d-215">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="fa33d-216">No puedes comprobar la ortografía.</span><span class="sxs-lookup"><span data-stu-id="fa33d-216">You don't get spell-check.</span></span>
- <span data-ttu-id="fa33d-217">No recibe ningún vínculo inteligente a otros artículos (tiene que escribir manualmente el nombre de archivo del artículo).</span><span class="sxs-lookup"><span data-stu-id="fa33d-217">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="fa33d-218">Puede ser un problema para cargar y hacer referencia a las imágenes.</span><span class="sxs-lookup"><span data-stu-id="fa33d-218">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="fa33d-219">Si prefieres no tratar estos problemas, usa un cliente de escritorio como [código Visual Studio](https://code.visualstudio.com/) con un par de [extensiones útiles](#useful-extensions) para la contribución.</span><span class="sxs-lookup"><span data-stu-id="fa33d-219">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <span data-ttu-id="fa33d-220">Uso de código de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fa33d-220">Using Visual Studio Code</span></span>

<span data-ttu-id="fa33d-221">Por los motivos mencionados [anteriormente](#editing-in-the-browser-vs-editing-with-a-desktop-client), puede que prefiera usar un cliente de escritorio para editar la documentación en lugar de un explorador Web.</span><span class="sxs-lookup"><span data-stu-id="fa33d-221">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="fa33d-222">Recomendamos usar [código de Visual Studio](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="fa33d-222">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <span data-ttu-id="fa33d-223">Programa de instalación</span><span class="sxs-lookup"><span data-stu-id="fa33d-223">Setup</span></span>

<span data-ttu-id="fa33d-224">Siga estos pasos para configurar el código de Visual Studio para que funcione con este repositorio:</span><span class="sxs-lookup"><span data-stu-id="fa33d-224">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="fa33d-225">En un explorador Web:</span><span class="sxs-lookup"><span data-stu-id="fa33d-225">In a web browser:</span></span>
    1. <span data-ttu-id="fa33d-226">Instala [git para tu equipo](https://git-scm.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="fa33d-226">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="fa33d-227">Instala el [código de Visual Studio](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="fa33d-227">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="fa33d-228">[Fork MicrosoftDocs/realidad mixta](#creating-a-new-article) si todavía no lo has hecho.</span><span class="sxs-lookup"><span data-stu-id="fa33d-228">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="fa33d-229">En la horquilla, seleccione **clonar o descargar** y copie la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="fa33d-229">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="fa33d-230">Cree un clon local de la bifurcación en Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="fa33d-230">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="fa33d-231">En el menú **vista** , seleccione **paleta de comandos**.</span><span class="sxs-lookup"><span data-stu-id="fa33d-231">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="fa33d-232">Escribe "git: clonar".</span><span class="sxs-lookup"><span data-stu-id="fa33d-232">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="fa33d-233">Pegue la dirección URL que ha copiado.</span><span class="sxs-lookup"><span data-stu-id="fa33d-233">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="fa33d-234">Elija dónde desea guardar el clon en el equipo.</span><span class="sxs-lookup"><span data-stu-id="fa33d-234">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="fa33d-235">Seleccione **abrir repositorio** en la ventana emergente.</span><span class="sxs-lookup"><span data-stu-id="fa33d-235">Select **Open repo** in the pop-up.</span></span>

### <span data-ttu-id="fa33d-236">Editar la documentación</span><span class="sxs-lookup"><span data-stu-id="fa33d-236">Editing documentation</span></span>

<span data-ttu-id="fa33d-237">Use el siguiente flujo de trabajo para realizar cambios en la documentación con código de Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="fa33d-237">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="fa33d-238">Todas las instrucciones para [Editar](#editing-an-existing-article) y [crear](#creating-a-new-article) artículos, y los [conceptos básicos de la edición de Markdown](#markdown-basics), de arriba, se aplican también al usar código de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fa33d-238">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="fa33d-239">Asegúrese de que la horquilla clonada está actualizada con el repositorio oficial.</span><span class="sxs-lookup"><span data-stu-id="fa33d-239">Make sure your cloned fork is up to date with the official repo.</span></span>
   1. <span data-ttu-id="fa33d-240">En un explorador Web, cree una solicitud de incorporación de cambios para sincronizar los cambios recientes de otros colaboradores en MicrosoftDocs/mixed-reality ' patrón ' a la horquilla (Asegúrese de que la flecha esté apuntando de la manera correcta).</span><span class="sxs-lookup"><span data-stu-id="fa33d-240">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![Sincronizar los cambios de MicrosoftDocs/Mixed-Reality con la horquilla](images/sync_repos.PNG)
   2. <span data-ttu-id="fa33d-242">En Visual Studio Code, seleccione el botón sincronizar para sincronizar la bifurcación recién actualizada con el clon local.</span><span class="sxs-lookup"><span data-stu-id="fa33d-242">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![Haga clic en la imagen del botón sincronizar](images/sync_clone.png)
2. <span data-ttu-id="fa33d-244">Cree o edite artículos en el repositorio clonado con código de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fa33d-244">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>
   1. <span data-ttu-id="fa33d-245">Editar uno o varios artículos (agregar imágenes a la carpeta "imágenes" si es necesario).</span><span class="sxs-lookup"><span data-stu-id="fa33d-245">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   2. <span data-ttu-id="fa33d-246">**Guarde** los cambios en el **Explorador**.</span><span class="sxs-lookup"><span data-stu-id="fa33d-246">**Save** changes in **Explorer**.</span></span>
      
      ![Elija "guardar todo" en el explorador](images/explorer_save.png)
   3. <span data-ttu-id="fa33d-248">**Confirmar todos** los cambios en el **control de código fuente** (escriba un mensaje de confirmación cuando se le solicite).</span><span class="sxs-lookup"><span data-stu-id="fa33d-248">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
      
      ![Elija "confirmar todo" en el control de código fuente](images/source_control_commit.png)
   4. <span data-ttu-id="fa33d-250">Seleccione el botón **sincronizar** para sincronizar los cambios de nuevo con el origen (su bifurcación en GitHub).</span><span class="sxs-lookup"><span data-stu-id="fa33d-250">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![Haga clic en el botón sincronizar](images/sync_back.png)
3. <span data-ttu-id="fa33d-252">En un explorador Web, cree una solicitud de incorporación de cambios para sincronizar nuevos cambios en la horquilla de nuevo a MicrosoftDocs/mixed-reality ' maestro ' (Asegúrese de que la flecha apunta correctamente).</span><span class="sxs-lookup"><span data-stu-id="fa33d-252">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Crear una solicitud de incorporación de extracción desde la horquilla en MicrosoftDocs/Mixed-Reality](images/pr_to_master.PNG)

### <span data-ttu-id="fa33d-254">Extensiones útiles</span><span class="sxs-lookup"><span data-stu-id="fa33d-254">Useful extensions</span></span>

<span data-ttu-id="fa33d-255">Las siguientes extensiones de código de Visual Studio son útiles al editar la documentación:</span><span class="sxs-lookup"><span data-stu-id="fa33d-255">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="fa33d-256">[Docs Markdown extensión para Visual Studio código](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) : use **Alt + M** para mostrar un menú de opciones de creación de documentos como:</span><span class="sxs-lookup"><span data-stu-id="fa33d-256">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="fa33d-257">Imágenes de búsqueda y de referencia que ha cargado.</span><span class="sxs-lookup"><span data-stu-id="fa33d-257">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="fa33d-258">Agregue formato como listas, tablas y llamadas específicas de documentos como `>[!NOTE]` .</span><span class="sxs-lookup"><span data-stu-id="fa33d-258">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="fa33d-259">Buscar y hacer referencia a vínculos internos y marcadores (vínculos a secciones específicas dentro de una página).</span><span class="sxs-lookup"><span data-stu-id="fa33d-259">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="fa33d-260">Se resaltan los errores de formato (mantenga el mouse sobre el error para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="fa33d-260">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="fa33d-261">[Corrector ortográfico de código](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) : las palabras con errores ortográficos se subrayan; Haga clic con el botón derecho en una palabra mal escrita para cambiarla o guardarla en el diccionario.</span><span class="sxs-lookup"><span data-stu-id="fa33d-261">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
