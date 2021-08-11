---
title: Búsqueda, instalación y desinstalación de aplicaciones
description: Microsoft Store es su fuente de aplicaciones y juegos que funcionan con HoloLens.  Obtenga más información sobre cómo buscar, instalar y desinstalar aplicaciones holográficas.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 10/27/2020
manager: jarrettr
keywords: hololens, store, tienda, uwp, aplicación, instalación
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: c26c3a236a1047e62d480c27ec1bbb09faa63630eb29e0e1103546842d6a76d3
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664798"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>Búsqueda, instalación y desinstalación de aplicaciones de Microsoft Store

Microsoft Store es su fuente de información para aplicaciones y juegos que funcionan con HoloLens. Cuando vaya a Store en su HoloLens, cualquier aplicación que vea allí funcionará en este.

Las aplicaciones de HoloLens usan la vista 2D o la vista holográfica. Las aplicaciones que usan la vista 2D parecen ventanas y pueden colocarse a su alrededor. Una aplicación que utiliza la vista holográfica lo rodea y se convierte en la única aplicación que ve.

HoloLens es compatible con muchas aplicaciones existentes de Microsoft Store, así como con nuevas aplicaciones compiladas específicamente para HoloLens.  Este artículo se centra en las aplicaciones holográficas de Microsoft Store.

Para más información sobre la instalación y ejecución de aplicaciones personalizadas, lea [Aplicaciones holográficas personalizadas](holographic-custom-apps.md).

## <a name="find-apps"></a>Buscar aplicaciones

Abra Microsoft Store desde el menú **Inicio**. A continuación, busque aplicaciones y juegos. Puede usar [comandos de voz](hololens-cortana.md) para realizar búsquedas. Para ello, diga "Buscar"; cuando se abra la ventana de búsqueda, diga "Iniciar dictado" y, a continuación, cuando se le solicite, empiece a pronunciar los términos de búsqueda.

> [!NOTE]
> Los requisitos del sistema para los dispositivos HoloLens se basan en la arquitectura de la compilación de la aplicación. Si una compilación de la aplicación para HoloLens (1.ª gen) no se ha actualizado con una UWP más reciente en Store para incluir el paquete de arquitectura ARM, no estará disponible para los dispositivos HoloLens 2. Del mismo modo, si una aplicación de HoloLens 2 no incluye el paquete de la arquitectura x86, no estará disponible para los dispositivos HoloLens (1.ª gen). Arquitecturas de dispositivos HoloLens:
> - x86 = HoloLens (1.ª generación)
> - ARM = HoloLens 2

> [!NOTE]
> El 12 de enero de 2021, las siguientes aplicaciones dejarán de recibir soporte técnico para los dispositivos HoloLens. Le recomendamos que use el vínculo siguiente en el dispositivo para utilizar la versión web de la aplicación.

| Aplicación        | Vínculo                                          |
|------------|-----------------------------------------------|
| Excel Mobile      | https://office.live.com/start/Excel.aspx      |
| Word Mobile       | https://office.live.com/start/Word.aspx       |
| PowerPoint Mobile | https://office.live.com/start/PowerPoint.aspx |

## <a name="install-apps"></a>Instalar aplicaciones

Para descargar aplicaciones, tendrá que iniciar sesión con una cuenta de Microsoft. Algunas aplicaciones son gratuitas y pueden descargarse de inmediato. Para las aplicaciones que requieren una compra, debe iniciar sesión en Store con su cuenta de Microsoft y tener un método de pago válido.

> [!NOTE]
> La cuenta que utilice en Microsoft Store no tiene que ser la misma que la cuenta con la que ha iniciado sesión. Si está usando una cuenta profesional o educativa en HoloLens, tal vez tendrá que iniciar sesión con su cuenta personal en la aplicación Store para hacer una compra.

> [!TIP]
> Para configurar un método de pago, vaya a [account.microsoft.com](https://account.microsoft.com/) y seleccione **Pago y facturación** > **Opciones de pago** > **Agregar una opción de pago**.

1. Para abrir el [menú **Inicio**](holographic-home.md), realice un [gesto de inicio](/hololens/hololens2-basic-usage#start-gesture) o un gesto de [eclosión](hololens1-basic-usage.md) en HoloLens (1.ª generación).

1. Seleccione la aplicación Microsoft Store. Una vez que la aplicación Store se abra:
   1. Utilice la barra de búsqueda para buscar aplicaciones. 
   1. Seleccione aplicaciones esenciales o creadas específicamente para HoloLens de una de las categorías seleccionadas.
   1. En la parte superior derecha de la aplicación Store, seleccione el botón **"..."** y luego seleccione **Mi biblioteca** para ver las aplicaciones compradas anteriormente.

1. Seleccione **Obtener** o **Instalar** en la página de la aplicación (puede ser necesaria una compra).

## <a name="update-apps"></a>Actualizar aplicaciones

Puede utilizar la aplicación Microsoft Store para actualizar una aplicación que ha instalado desde Microsoft Store. En el caso de las aplicaciones instaladas para Microsoft Store para Empresas, también puede actualizar esas aplicaciones desde Microsoft Store para Empresas. 

1. Para abrir el [menú **Inicio**](holographic-home.md), realice un [gesto de inicio](/hololens/hololens2-basic-usage#start-gesture) o un gesto de [eclosión](hololens1-basic-usage.md) en HoloLens (1.ª generación).

1. Seleccione la aplicación Store.

1. Mire la parte superior derecha de la aplicación Store. 

1. Seleccione el botón **"..."** o "Ver más".

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla de la aplicación Microsoft Store.](images/store-update-1.png)

1. Seleccione **Descargas y actualizaciones**.
    1. Si el dispositivo ha identificado previamente actualizaciones, puede que vea una flecha hacia abajo y un número que representa las actualizaciones pendientes.

1. Seleccione **Obtener actualizaciones**. El dispositivo ahora buscará actualizaciones y las configurará para descargar e instalar. 
 
   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla de cómo obtener actualizaciones de la aplicación Microsoft Store.](images/store-update-2.png.jpg)

> [!NOTE]
> Si las aplicaciones del dispositivo las distribuyó su organización, podrán actualizarse a través de los mismos métodos de administración de aplicaciones comerciales. Si esto se aplica a su situación, obtenga más información a través de nuestra [introducción a la implementación de aplicaciones comerciales.](app-deploy-overview.md)
>
> Si desea actualizar una aplicación personalizada que se ha instalado de prueba o implementado, tendrá que usar el mismo método con la versión actualizada de la aplicación. Para más información sobre cómo instalar y ejecutar aplicaciones personalizadas, lea [Aplicaciones holográficas personalizadas](holographic-custom-apps.md).

## <a name="uninstall-apps"></a>Desinstalar aplicaciones

Hay tres formas de desinstalar aplicaciones. Puede desinstalar aplicaciones a través de Microsoft Store, del menú Inicio o de Configuración. 

> [!WARNING]
> No se puede desinstalar una aplicación del sistema ni Microsoft Store.

> [!IMPORTANT]
> Si el dispositivo HoloLens 2 tiene varios usuarios, debe iniciar sesión como el usuario que instaló la aplicación para desinstalarla. 

### <a name="uninstall-from-the-microsoft-store"></a>Desinstalar aplicaciones desde Microsoft Store

Abra Microsoft Store desde el menú **Inicio** y, a continuación, busque la aplicación que desea desinstalar.  En la página de Store, cada aplicación instalada tiene un botón **Desinstalar**.

### <a name="uninstall-from-the-start-menu"></a>Desinstalación desde el menú Inicio

En el menú **Inicio** o en la lista **Todas las aplicaciones**, vaya a la aplicación. Mantenga presionado hasta que aparezca el menú y, después, seleccione **Desinstalar**.

### <a name="uninstall-from-settings"></a>Desinstalación desde Configuración
En el menú **Inicio**, seleccione **Configuración -> Aplicaciones**. Busque la aplicación en la lista, selecciónela y, después, haga clic en **Desinstalar**.

Si no puede desinstalar una aplicación, envíe sus [comentarios](/hololens/hololens-feedback) mediante el Centro de opiniones.
