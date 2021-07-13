---
title: Instrucciones de contribución
description: Obtenga información sobre cómo contribuir a los documentos HoloLens en la plataforma docs.microsoft.com mediante GitHub markdown con GitHub de conexión.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: 73b6e8bcd634cb4d45171bda0a85f2e991a977c9
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635677"
---
# <a name="contributing-to-the-hololens-documentation"></a><span data-ttu-id="3a195-103">Contribución a la documentación HoloLens datos</span><span class="sxs-lookup"><span data-stu-id="3a195-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="3a195-104">Bienvenido a la [documentación de HoloLens .](https://github.com/MicrosoftDocs/Hololens)</span><span class="sxs-lookup"><span data-stu-id="3a195-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="3a195-105">Los artículos que cree o edite en este repositorio **serán visibles para el público.**</span><span class="sxs-lookup"><span data-stu-id="3a195-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="3a195-106">HoloLens documentos se muestran en la plataforma docs.microsoft.com, que usa markdown con GitHub con características markdig.</span><span class="sxs-lookup"><span data-stu-id="3a195-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="3a195-107">El contenido que edite en este repositorio se formatee en páginas con formato que se muestran en /hololens.</span><span class="sxs-lookup"><span data-stu-id="3a195-107">The content you edit in this repo gets formatted into stylized pages that show up at /hololens.</span></span>

<span data-ttu-id="3a195-108">En esta página se tratan los pasos básicos y las directrices para contribuir y vínculos a los conceptos básicos de Markdown.</span><span class="sxs-lookup"><span data-stu-id="3a195-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="3a195-109">Gracias por su contribución.</span><span class="sxs-lookup"><span data-stu-id="3a195-109">Thanks for your contribution!</span></span>

## <a name="available-repos"></a><span data-ttu-id="3a195-110">Repositorios disponibles</span><span class="sxs-lookup"><span data-stu-id="3a195-110">Available repos</span></span>

| <span data-ttu-id="3a195-111">Nombre del repositorio</span><span class="sxs-lookup"><span data-stu-id="3a195-111">Repository name</span></span> | <span data-ttu-id="3a195-112">URL</span><span class="sxs-lookup"><span data-stu-id="3a195-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="3a195-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="3a195-113">HoloLens</span></span> | [<span data-ttu-id="3a195-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="3a195-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="3a195-115">Mixed Reality</span><span class="sxs-lookup"><span data-stu-id="3a195-115">Mixed Reality</span></span> | [<span data-ttu-id="3a195-116">MicrosoftDocs/mixed-reality</span><span class="sxs-lookup"><span data-stu-id="3a195-116">MicrosoftDocs/mixed-reality</span></span>](/windows/mixed-reality) |
| <span data-ttu-id="3a195-117">VR Enthusiasts Guide</span><span class="sxs-lookup"><span data-stu-id="3a195-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="3a195-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span><span class="sxs-lookup"><span data-stu-id="3a195-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a><span data-ttu-id="3a195-119">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="3a195-119">Before you start</span></span>

<span data-ttu-id="3a195-120">Si aún no tiene una, deberá crear una cuenta [de GitHub .](https://github.com/join)</span><span class="sxs-lookup"><span data-stu-id="3a195-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="3a195-121">Si es empleado de Microsoft, vincule su cuenta de GitHub a su alias de Microsoft en el [portal de código abierto de Microsoft](https://repos.opensource.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="3a195-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="3a195-122">Únase a **las organizaciones "Microsoft"** **y "MicrosoftDocs".**</span><span class="sxs-lookup"><span data-stu-id="3a195-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="3a195-123">Al configurar la cuenta GitHub, también se recomiendan estas precauciones de seguridad:</span><span class="sxs-lookup"><span data-stu-id="3a195-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="3a195-124">Cree una [contraseña segura para la cuenta GitHub .](https://github.com/settings/admin)</span><span class="sxs-lookup"><span data-stu-id="3a195-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="3a195-125">Habilite [la autenticación en dos fases.](https://github.com/settings/two_factor_authentication/configure)</span><span class="sxs-lookup"><span data-stu-id="3a195-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="3a195-126">Guarde los [códigos de recuperación](https://github.com/settings/auth/recovery-codes) en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="3a195-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="3a195-127">Actualice la configuración [del perfil público.](https://github.com/settings/profile)</span><span class="sxs-lookup"><span data-stu-id="3a195-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="3a195-128">Establezca su nombre y considere la posibilidad de establecer *el correo electrónico público* en No mostrar mi dirección de correo *electrónico.*</span><span class="sxs-lookup"><span data-stu-id="3a195-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="3a195-129">Se recomienda cargar una imagen de perfil porque se muestra una miniatura en las páginas de documentos a las que contribuye.</span><span class="sxs-lookup"><span data-stu-id="3a195-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="3a195-130">Si tiene previsto usar la línea de comandos, considere la posibilidad de configurar [Git Administrador de credenciales para Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span><span class="sxs-lookup"><span data-stu-id="3a195-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="3a195-131">De este modo, no tendrá que escribir la contraseña cada vez que realice una contribución.</span><span class="sxs-lookup"><span data-stu-id="3a195-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="3a195-132">El sistema de publicación está asociado a GitHub, por lo que estos pasos son importantes.</span><span class="sxs-lookup"><span data-stu-id="3a195-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="3a195-133">Aparecerá como autor o colaborador de cada artículo mediante el alias GitHub usuario.</span><span class="sxs-lookup"><span data-stu-id="3a195-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <a name="editing-an-existing-article"></a><span data-ttu-id="3a195-134">Edición de un artículo existente</span><span class="sxs-lookup"><span data-stu-id="3a195-134">Editing an existing article</span></span>

<span data-ttu-id="3a195-135">Use el flujo de trabajo siguiente para realizar actualizaciones en *un artículo existente* a través GitHub en un explorador web:</span><span class="sxs-lookup"><span data-stu-id="3a195-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="3a195-136">Vaya al artículo que desea editar en la carpeta "mixed-reality-docs".</span><span class="sxs-lookup"><span data-stu-id="3a195-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="3a195-137">Seleccione el botón Editar (icono de lápiz) de la parte superior derecha, que bifurcará automáticamente una rama descartable de la rama "maestra".</span><span class="sxs-lookup"><span data-stu-id="3a195-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![Edite un artículo.](images/editpage.png)
   
3. <span data-ttu-id="3a195-139">Edite el contenido del artículo según [los "Conceptos básicos de Markdown".](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="3a195-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="3a195-140">Actualice los metadatos de la parte superior de cada artículo:</span><span class="sxs-lookup"><span data-stu-id="3a195-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="3a195-141">**title:** título de página que aparece en la pestaña del explorador cuando se está visualizando el artículo.</span><span class="sxs-lookup"><span data-stu-id="3a195-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="3a195-142">Los títulos de página se usan para seO e indexación, por lo que no cambie el título a menos que sea necesario (aunque esto es menos crítico antes de que la documentación se haga pública).</span><span class="sxs-lookup"><span data-stu-id="3a195-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="3a195-143">**description:** escriba una breve descripción del contenido del artículo, lo que aumenta el SEO y la detección.</span><span class="sxs-lookup"><span data-stu-id="3a195-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="3a195-144">**author:** si es el propietario principal de la página, agregue el alias GitHub aquí.</span><span class="sxs-lookup"><span data-stu-id="3a195-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="3a195-145">**ms.author:** si es el propietario principal de la página, agregue el alias de Microsoft aquí (no necesita , solo @microsoft.com el alias).</span><span class="sxs-lookup"><span data-stu-id="3a195-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="3a195-146">**ms.date:** actualice la fecha si va a agregar contenido principal a la página, pero no para correcciones como aclaración, formato, gramática o ortografía.</span><span class="sxs-lookup"><span data-stu-id="3a195-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="3a195-147">**keywords:** las palabras clave ayudan en SEO (optimización del motor de búsqueda).</span><span class="sxs-lookup"><span data-stu-id="3a195-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="3a195-148">Agregue palabras clave, separadas por una coma y un espacio, que sean específicas del artículo, pero sin signos de puntuación después de la última palabra clave de la lista.</span><span class="sxs-lookup"><span data-stu-id="3a195-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="3a195-149">No es necesario agregar palabras clave globales que se apliquen a todos los artículos, ya que se administran en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="3a195-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="3a195-150">Cuando haya completado las modificaciones del artículo, desplácese hacia abajo y seleccione **Propose file change (Proponer cambio de archivo).**</span><span class="sxs-lookup"><span data-stu-id="3a195-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="3a195-151">En la página siguiente, seleccione **Crear solicitud de extracción** para combinar la rama creada automáticamente en "master".</span><span class="sxs-lookup"><span data-stu-id="3a195-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="3a195-152">Repita los pasos anteriores para el siguiente artículo que desea editar.</span><span class="sxs-lookup"><span data-stu-id="3a195-152">Repeat the steps above for the next article you want to edit.</span></span>

## <a name="renaming-or-deleting-an-existing-article"></a><span data-ttu-id="3a195-153">Cambio de nombre o eliminación de un artículo existente</span><span class="sxs-lookup"><span data-stu-id="3a195-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="3a195-154">Si el cambio cambiará el nombre o eliminará un artículo existente, asegúrese de agregar un redireccionamiento.</span><span class="sxs-lookup"><span data-stu-id="3a195-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="3a195-155">De este modo, cualquier persona con un vínculo al artículo existente terminará en el lugar correcto.</span><span class="sxs-lookup"><span data-stu-id="3a195-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="3a195-156">Los redireccionamientos se administran .openpublishing.redirection.jsen el archivo en la raíz del repositorio.</span><span class="sxs-lookup"><span data-stu-id="3a195-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="3a195-157">Para agregar una redirección a .openpublishing.redirection.js, agregue una entrada a la `redirections` matriz:</span><span class="sxs-lookup"><span data-stu-id="3a195-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="3a195-158">es la ruta de acceso relativa del repositorio `source_path` al artículo anterior que va a quitar.</span><span class="sxs-lookup"><span data-stu-id="3a195-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="3a195-159">Asegúrese de que la ruta de acceso comienza `mixed-reality-docs` por y termina con `.md` .</span><span class="sxs-lookup"><span data-stu-id="3a195-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="3a195-160">es `redirect_url` la dirección URL pública relativa del artículo anterior al nuevo.</span><span class="sxs-lookup"><span data-stu-id="3a195-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="3a195-161">Asegúrese de que esta dirección URL **no contiene** o , ya que hace referencia a la dirección URL pública y no a la ruta de acceso `mixed-reality-docs` del `.md` repositorio.</span><span class="sxs-lookup"><span data-stu-id="3a195-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="3a195-162">Se permite la vinculación a una sección dentro del `#section` nuevo artículo mediante .</span><span class="sxs-lookup"><span data-stu-id="3a195-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="3a195-163">También puede usar una ruta de acceso absoluta a otro sitio aquí, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="3a195-163">You can also use an absolute path to another site here, if necessary.</span></span>

- <span data-ttu-id="3a195-164">`redirect_document_id` indica si desea conservar el identificador del documento del archivo anterior.</span><span class="sxs-lookup"><span data-stu-id="3a195-164">`redirect_document_id` indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="3a195-165">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="3a195-165">The default is `false`.</span></span> <span data-ttu-id="3a195-166">Use `true` si desea conservar el valor del atributo del artículo `ms.documentid` redirigido.</span><span class="sxs-lookup"><span data-stu-id="3a195-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="3a195-167">Si conserva el identificador del documento, los datos, como las vistas de página y las clasificaciones, se transferirán al artículo de destino.</span><span class="sxs-lookup"><span data-stu-id="3a195-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="3a195-168">Haga esto si el redireccionamiento es principalmente un cambio de nombre y no un puntero a un artículo diferente que solo cubre parte del mismo contenido.</span><span class="sxs-lookup"><span data-stu-id="3a195-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="3a195-169">Si agrega un redireccionamiento, asegúrese de eliminar también el archivo antiguo.</span><span class="sxs-lookup"><span data-stu-id="3a195-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <a name="creating-a-new-article"></a><span data-ttu-id="3a195-170">Creación de un nuevo artículo</span><span class="sxs-lookup"><span data-stu-id="3a195-170">Creating a new article</span></span>

<span data-ttu-id="3a195-171">Use el flujo de trabajo siguiente *para crear nuevos artículos en* el repositorio de documentación a través GitHub en un explorador web:</span><span class="sxs-lookup"><span data-stu-id="3a195-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="3a195-172">Cree una bifurcación de la rama "maestra" de MicrosoftDocs/mixed-reality (con el botón **Bifurcar** de la parte superior derecha).</span><span class="sxs-lookup"><span data-stu-id="3a195-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![Bifurcar la rama maestra.](images/forkbranch.png)
   
2. <span data-ttu-id="3a195-174">En la carpeta "mixed-reality-docs", seleccione **Crear nuevo archivo** en la parte superior derecha.</span><span class="sxs-lookup"><span data-stu-id="3a195-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="3a195-175">Cree un nombre de página para el artículo (use guiones en lugar de espacios y no use signos de puntuación ni apóstrofes) y anexe ".md".</span><span class="sxs-lookup"><span data-stu-id="3a195-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![Asigne un nombre a la nueva página.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="3a195-177">Asegúrese de crear el nuevo artículo desde la carpeta "mixed-reality-docs".</span><span class="sxs-lookup"><span data-stu-id="3a195-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="3a195-178">Para confirmarlo, compruebe "/mixed-reality-docs/" en la nueva línea de nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="3a195-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="3a195-179">En la parte superior de la nueva página, agregue el siguiente bloque de metadatos:</span><span class="sxs-lookup"><span data-stu-id="3a195-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="3a195-180">Rellene los campos de metadatos pertinentes según las instrucciones de la [sección anterior.](#editing-an-existing-article)</span><span class="sxs-lookup"><span data-stu-id="3a195-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="3a195-181">Escribir contenido del artículo con [los conceptos básicos de Markdown.](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="3a195-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="3a195-182">Agregue una `## See also` sección en la parte inferior del artículo con vínculos a otros artículos pertinentes.</span><span class="sxs-lookup"><span data-stu-id="3a195-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="3a195-183">Cuando termine, seleccione **Commit new file (Confirmar nuevo archivo).**</span><span class="sxs-lookup"><span data-stu-id="3a195-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="3a195-184">Seleccione **Nueva** solicitud de extracción y combine la rama "maestra" de la bifurcación en MicrosoftDocs/mixed-reality "master" (asegúrese de que la flecha apunta de la manera correcta).</span><span class="sxs-lookup"><span data-stu-id="3a195-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Creación de una solicitud de extracción desde la bifurcación en MicrosoftDocs/mixed-reality](images/pr-to-master.png)

## <a name="markdown-basics"></a><span data-ttu-id="3a195-186">Aspectos básicos de Markdown</span><span class="sxs-lookup"><span data-stu-id="3a195-186">Markdown basics</span></span>

<span data-ttu-id="3a195-187">Los siguientes recursos le ayudarán a aprender a editar la documentación mediante el lenguaje Markdown:</span><span class="sxs-lookup"><span data-stu-id="3a195-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- <span data-ttu-id="3a195-188">[Markdown basics](https://help.github.com/articles/basic-writing-and-formatting-syntax/) (Conceptos básicos de Markdown)</span><span class="sxs-lookup"><span data-stu-id="3a195-188">[Markdown basics](https://help.github.com/articles/basic-writing-and-formatting-syntax/)</span></span>
- [<span data-ttu-id="3a195-189">Recursos adicionales para escribir Markdown para docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3a195-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a><span data-ttu-id="3a195-190">Adición de tablas</span><span class="sxs-lookup"><span data-stu-id="3a195-190">Adding tables</span></span>

<span data-ttu-id="3a195-191">Debido a la forma docs.microsoft.com tablas de estilos, no tendrán bordes ni estilos personalizados, aunque pruebe CSS en línea.</span><span class="sxs-lookup"><span data-stu-id="3a195-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="3a195-192">Parecerá que funciona durante un breve período de tiempo, pero finalmente la plataforma quitará el estilo de la tabla.</span><span class="sxs-lookup"><span data-stu-id="3a195-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="3a195-193">Por lo tanto, planee con antelación y mantenga las tablas sencillas.</span><span class="sxs-lookup"><span data-stu-id="3a195-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="3a195-194">[Este es un sitio que facilita las tablas de Markdown.](https://www.tablesgenerator.com/markdown_tables)</span><span class="sxs-lookup"><span data-stu-id="3a195-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="3a195-195">La [extensión Docs Markdown](/teamblog/docs-extension) para Visual Studio Code también facilita la generación de tablas si usa Visual Studio Code [(consulte a continuación)](#using-visual-studio-code) para editar la documentación.</span><span class="sxs-lookup"><span data-stu-id="3a195-195">The [Docs Markdown Extension for Visual Studio Code](/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <a name="adding-images"></a><span data-ttu-id="3a195-196">Incorporación de imágenes</span><span class="sxs-lookup"><span data-stu-id="3a195-196">Adding images</span></span>

<span data-ttu-id="3a195-197">Deberá cargar las imágenes en la carpeta "mixed-reality-docs/images" del repositorio y, a continuación, hacer referencia a ellas correctamente en el artículo.</span><span class="sxs-lookup"><span data-stu-id="3a195-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="3a195-198">Las imágenes se mostrarán automáticamente a tamaño completo, lo que significa que las imágenes grandes rellenarán todo el ancho del artículo.</span><span class="sxs-lookup"><span data-stu-id="3a195-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="3a195-199">Se recomienda dimensionar previamente las imágenes antes de cargarlas.</span><span class="sxs-lookup"><span data-stu-id="3a195-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="3a195-200">El ancho recomendado es de entre 600 y 700 píxeles, aunque debe ajustar el tamaño hacia arriba o hacia abajo si es una captura de pantalla densa o una fracción de una captura de pantalla, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="3a195-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="3a195-201">Solo puede cargar imágenes en el repositorio bifurcado antes de la combinación.</span><span class="sxs-lookup"><span data-stu-id="3a195-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="3a195-202">Por lo tanto, si planea agregar imágenes a un artículo, deberá usar Visual Studio Code para agregar primero las imágenes [a](#using-visual-studio-code) la carpeta "images" de la bifurcación o asegúrese de que ha hecho lo siguiente en un explorador web:</span><span class="sxs-lookup"><span data-stu-id="3a195-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="3a195-203">Se ha bifurcado el repositorio MicrosoftDocs/mixed-reality.</span><span class="sxs-lookup"><span data-stu-id="3a195-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="3a195-204">Editó el artículo en la bifurcación.</span><span class="sxs-lookup"><span data-stu-id="3a195-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="3a195-205">Ha cargado las imágenes a las que hace referencia en el artículo en la carpeta "mixed-reality-docs/images" de la bifurcación.</span><span class="sxs-lookup"><span data-stu-id="3a195-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="3a195-206">Ha creado **una solicitud de** extracción para combinar la bifurcación en la rama "maestra" de MicrosoftDocs/mixed-reality.</span><span class="sxs-lookup"><span data-stu-id="3a195-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="3a195-207">Para obtener información sobre cómo configurar su propio repositorio bifurcado, siga las instrucciones para [crear un nuevo artículo](#creating-a-new-article).</span><span class="sxs-lookup"><span data-stu-id="3a195-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <a name="previewing-your-work"></a><span data-ttu-id="3a195-208">Vista previa del trabajo</span><span class="sxs-lookup"><span data-stu-id="3a195-208">Previewing your work</span></span>

<span data-ttu-id="3a195-209">Al editar en GitHub a través de un  explorador web, puede seleccionar la pestaña Vista previa cerca de la parte superior de la página para obtener una vista previa del trabajo antes de confirmar.</span><span class="sxs-lookup"><span data-stu-id="3a195-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="3a195-210">La vista previa de los cambios review.docs.microsoft.com solo está disponible para los empleados de Microsoft</span><span class="sxs-lookup"><span data-stu-id="3a195-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="3a195-211">Empleados de Microsoft: una vez que sus contribuciones se hayan combinado en la rama "maestra", puede revisar el contenido antes de que se haga público en </hololens?branch=master>.</span><span class="sxs-lookup"><span data-stu-id="3a195-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at </hololens?branch=master>.</span></span> <span data-ttu-id="3a195-212">Busque el artículo con la tabla de contenido de la columna izquierda.</span><span class="sxs-lookup"><span data-stu-id="3a195-212">Find your article using the table of contents in the left column.</span></span>

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a><span data-ttu-id="3a195-213">Edición en el explorador frente a edición con un cliente de escritorio</span><span class="sxs-lookup"><span data-stu-id="3a195-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="3a195-214">La edición en el explorador es la manera más fácil de realizar cambios rápidos; sin embargo, hay algunas desventajas:</span><span class="sxs-lookup"><span data-stu-id="3a195-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="3a195-215">No se obtiene la revisión ortótórquea.</span><span class="sxs-lookup"><span data-stu-id="3a195-215">You don't get spell-check.</span></span>
- <span data-ttu-id="3a195-216">No se obtiene ninguna vinculación inteligente a otros artículos (tiene que escribir manualmente el nombre de archivo del artículo).</span><span class="sxs-lookup"><span data-stu-id="3a195-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="3a195-217">Puede ser complicado cargar y hacer referencia a imágenes.</span><span class="sxs-lookup"><span data-stu-id="3a195-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="3a195-218">Si prefiere no tratar estos problemas, use un cliente de escritorio como [Visual Studio Code](https://code.visualstudio.com/) con un par de extensiones [útiles](#useful-extensions) al contribuir.</span><span class="sxs-lookup"><span data-stu-id="3a195-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <a name="using-visual-studio-code"></a><span data-ttu-id="3a195-219">Uso de Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="3a195-219">Using Visual Studio Code</span></span>

<span data-ttu-id="3a195-220">Por los motivos [mencionados anteriormente,](#editing-in-the-browser-vs-editing-with-a-desktop-client)puede que prefiera usar un cliente de escritorio para editar la documentación en lugar de un explorador web.</span><span class="sxs-lookup"><span data-stu-id="3a195-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="3a195-221">Se recomienda usar [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="3a195-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <a name="setup"></a><span data-ttu-id="3a195-222">Configurar</span><span class="sxs-lookup"><span data-stu-id="3a195-222">Setup</span></span>

<span data-ttu-id="3a195-223">Siga estos pasos para configurar Visual Studio Code para trabajar con este repositorio:</span><span class="sxs-lookup"><span data-stu-id="3a195-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="3a195-224">En un explorador web:</span><span class="sxs-lookup"><span data-stu-id="3a195-224">In a web browser:</span></span>
    1. <span data-ttu-id="3a195-225">Instale [Git para el equipo.](https://git-scm.com/downloads)</span><span class="sxs-lookup"><span data-stu-id="3a195-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="3a195-226">Instale [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="3a195-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="3a195-227">Si aún no lo ha hecho, puede bifurcar [MicrosoftDocs/mixed-reality.](#creating-a-new-article)</span><span class="sxs-lookup"><span data-stu-id="3a195-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="3a195-228">En la bifurcación, seleccione **Clonar o descargar y** copie la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="3a195-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="3a195-229">Cree un clon local de la bifurcación en Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="3a195-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="3a195-230">En el **menú Ver,** seleccione **Paleta de comandos.**</span><span class="sxs-lookup"><span data-stu-id="3a195-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="3a195-231">Escriba "Git: Clone".</span><span class="sxs-lookup"><span data-stu-id="3a195-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="3a195-232">Pegue la dirección URL que copió.</span><span class="sxs-lookup"><span data-stu-id="3a195-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="3a195-233">Elija dónde guardar el clon en el equipo.</span><span class="sxs-lookup"><span data-stu-id="3a195-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="3a195-234">Seleccione **Abrir repositorio** en el menú emergente.</span><span class="sxs-lookup"><span data-stu-id="3a195-234">Select **Open repo** in the pop-up.</span></span>

### <a name="editing-documentation"></a><span data-ttu-id="3a195-235">Edición de documentación</span><span class="sxs-lookup"><span data-stu-id="3a195-235">Editing documentation</span></span>

<span data-ttu-id="3a195-236">Use el siguiente flujo de trabajo para realizar cambios en la documentación con Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="3a195-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="3a195-237">Todas las instrucciones para [editar](#editing-an-existing-article) [y](#creating-a-new-article) crear [artículos,](#markdown-basics)y los conceptos básicos de la edición de Markdown , de arriba, también se aplican al Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="3a195-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="3a195-238">Asegúrese de que la bifurcación clonada está actualizada con el repositorio oficial.</span><span class="sxs-lookup"><span data-stu-id="3a195-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="3a195-239">En un explorador web, cree una solicitud de extracción para sincronizar los cambios recientes de otros colaboradores de MicrosoftDocs/mixed-reality 'master' con la bifurcación (asegúrese de que la flecha apunta a la derecha).</span><span class="sxs-lookup"><span data-stu-id="3a195-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![Sincronización de cambios de MicrosoftDocs/mixed-reality a la bifurcación](images/sync-repos.png)
      
   2. <span data-ttu-id="3a195-241">En Visual Studio Code, seleccione el botón sincronizar para sincronizar la bifurcación recién actualizada con el clon local.</span><span class="sxs-lookup"><span data-stu-id="3a195-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![Haga clic en la imagen del botón sincronizar.](images/sync-clone.png)
      
2. <span data-ttu-id="3a195-243">Cree o edite artículos en el repositorio clonado mediante Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="3a195-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="3a195-244">Edite uno o varios artículos (agregue imágenes a la carpeta "images" si es necesario).</span><span class="sxs-lookup"><span data-stu-id="3a195-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="3a195-245">**Guarde** los cambios en el **Explorador** de .</span><span class="sxs-lookup"><span data-stu-id="3a195-245">**Save** changes in **Explorer**.</span></span>
      
      ![Elija "Guardar todo" en el Explorador](images/explorer-save.png)
      
   3. <span data-ttu-id="3a195-247">**Confirme todos los** cambios en **control de código fuente** (escriba el mensaje de confirmación cuando se le solicite).</span><span class="sxs-lookup"><span data-stu-id="3a195-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
   
      ![Elija "Confirmar todo" en control de código fuente](images/source-control-commit.png)
      
   4. <span data-ttu-id="3a195-249">Seleccione el **botón** Sincronizar para volver a sincronizar los cambios en el origen (la bifurcación en GitHub).</span><span class="sxs-lookup"><span data-stu-id="3a195-249">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![Haga clic en el botón sync (Sincronizar).](images/sync-back.png)
      
3. <span data-ttu-id="3a195-251">En un explorador web, cree una solicitud de extracción para sincronizar nuevos cambios en la bifurcación con MicrosoftDocs/mixed-reality 'master' (asegúrese de que la flecha apunta de la manera correcta).</span><span class="sxs-lookup"><span data-stu-id="3a195-251">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Creación de una solicitud de extracción desde la bifurcación en MicrosoftDocs/mixed-reality](images/pr-to-master.png)

### <a name="useful-extensions"></a><span data-ttu-id="3a195-253">Extensiones útiles</span><span class="sxs-lookup"><span data-stu-id="3a195-253">Useful extensions</span></span>

<span data-ttu-id="3a195-254">Las siguientes extensiones Visual Studio Code son útiles al editar la documentación:</span><span class="sxs-lookup"><span data-stu-id="3a195-254">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="3a195-255">[Extensión Markdown de Docs para Visual Studio Code:](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) use **Alt+M** para abrir un menú de opciones de creación de documentos como:</span><span class="sxs-lookup"><span data-stu-id="3a195-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="3a195-256">Busque y haga referencia a las imágenes que ha cargado.</span><span class="sxs-lookup"><span data-stu-id="3a195-256">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="3a195-257">Agregue formatos como listas, tablas y llamadas específicas de documentos, como `>[!NOTE]` .</span><span class="sxs-lookup"><span data-stu-id="3a195-257">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="3a195-258">Buscar y hacer referencia a vínculos internos y marcadores (vínculos a secciones específicas dentro de una página).</span><span class="sxs-lookup"><span data-stu-id="3a195-258">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="3a195-259">Los errores de formato están resaltados (mantenga el mouse sobre el error para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="3a195-259">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="3a195-260">[Corrector ortográfico de código:](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) las palabras mal escritas se subrayan; Haga clic con el botón derecho en una palabra mal escrita para cambiarla o guárdela en el diccionario.</span><span class="sxs-lookup"><span data-stu-id="3a195-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
