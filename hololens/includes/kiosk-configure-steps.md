---
ms.openlocfilehash: 7a7122790d3e0257c07cdd8bc8c7f658b3a0e279
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859431"
---
# <a name="microsoft-intune-single-app-kiosk-template"></a>[Microsoft Intune de pantalla completa de aplicación única](#tab/uisak)

## <a name="microsoft-intune-single-app-kiosk-template"></a>Microsoft Intune de pantalla completa de aplicación única

1. Creación de un perfil de configuración <br> 
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Elección de la plantilla de quiosco <br> 
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Elija si una sola aplicación o varias pantallas de pantalla completa de aplicaciones y elija también el tipo de destino de usuario para el modo de pantalla completa. <br> 
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-sa-3.png"/>
</kbd>

<br>

4. Elección de la aplicación que se ejecutará en pantalla completa <br> 
<kbd>
    <img alt="Choose the app" src="../images/kiosk-steps/kiosk-template-sa-4.png"/>
</kbd>

<br>

5. Deje el resto de las opciones tal y como están <br> 
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Elija a qué grupos, dispositivos o usuarios debe asignarse este perfil de configuración. <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

7. Revisión y creación para guardar el perfil de configuración
8. Realice la sincronización de MDM a partir de un dispositivo o intune para aplicar la configuración al dispositivo. Sincronizar dispositivos desde [Intune](/mem/intune/remote-actions/device-sync#sync-a-device) o en el dispositivo mediante **Configuración -> Accounts -> Work o school ->** seleccione la cuenta conectada **-> Info -> Sync**
9. Inicie sesión como usuario de destino para experimentar el quiosco.

# <a name="microsoft-intune-multi-app-kiosk-template"></a>[Microsoft Intune de pantalla completa con varias aplicaciones](#tab/uimak)

## <a name="microsoft-intune-multi-app-kiosk-template"></a>Microsoft Intune de pantalla completa con varias aplicaciones

1. Creación de un perfil de configuración <br> 
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Elección de la plantilla de quiosco <br> 
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Elija si una sola aplicación o varias pantallas de pantalla completa de aplicaciones y elija también el tipo de destino de usuario para el modo de pantalla completa. <br> 
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-mak-3.png"/>
</kbd>

<br>

4. Elección de las aplicaciones que se ejecutarán en pantalla completa <br> 
<kbd>
    <img alt="Choose the app(s)" src="../images/kiosk-steps/kiosk-template-mak-4.png"/>
</kbd>

<br>

5. Deje el resto de las opciones tal y como están <br> 
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Elija a qué grupos, dispositivos o usuarios debe asignarse este perfil de configuración. <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

<br>

7. Revisión y creación para guardar el perfil de configuración
8. Realice la sincronización de MDM a partir de un dispositivo o intune para aplicar la configuración al dispositivo. Sincronizar dispositivos desde [Intune](/mem/intune/remote-actions/device-sync#sync-a-device) o en el dispositivo mediante **Configuración -> Accounts -> Work o school ->** seleccione la cuenta conectada **-> Info -> Sync**
9. Inicie sesión como usuario de destino para experimentar el quiosco.

# <a name="microsoft-intune-custom-template"></a>[Microsoft Intune personalizada](#tab/intunecustom)

## <a name="microsoft-intune-custom-template"></a>Microsoft Intune personalizada

1. Cree la configuración xml para la experiencia de quiosco deseada. Vea [los ejemplos](../hololens-kiosk-reference.md#kiosk-xml-code-samples) aquí para comenzar.

1. Creación de un perfil de configuración personalizado <br>
<kbd>
    <img alt="Create a custom configuration profile" src="../images/kiosk-steps/kiosk-custom-1.png"/>
</kbd>

<br>

3. Especifique el nombre del perfil de configuración personalizado y haga clic en "Agregar" en la sección "Configuración" para agregar la configuración de OMA-URI. <br>
<kbd>
    <img alt="Name and add" src="../images/kiosk-steps/kiosk-custom-2.png"/>
</kbd>

<br>

4. Especifique el nombre de la configuración de OMA-URI.

    1. En el cuadro de texto OMA-URI, escriba **./Device/Vendor/MSFT/AssignedAccess/Configuration.**
    1. Elija Tipo de datos como **Cadena.**
    1. En el cuadro de texto valor, copie y pegue el xml de configuración de acceso asignado (consulte los vínculos de referencia para obtener ejemplos basados en su escenario y actualice según sea necesario antes de copiar y pegar).
    1. Seleccione el botón Guardar para guardar la configuración y la configuración.

    <kbd>
        <img alt="Specify OMA-URI settings" src="../images/kiosk-steps/kiosk-custom-3.png"/>
    </kbd>

<br>

5. Elija a qué grupos, dispositivos o usuarios se debe asignar este perfil de configuración. <br>
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-custom-4.png"/>
</kbd>

<br>

6. Revise y cree para guardar el perfil de configuración.
1. Realice la sincronización de MDM a partir de un dispositivo o intune para aplicar la configuración al dispositivo. Sincronizar dispositivos desde [Intune](/mem/intune/remote-actions/device-sync#sync-a-device) o en el dispositivo mediante **Configuración -> Accounts -> Work o school ->** seleccione la cuenta conectada **-> Info -> Sync**
1. Inicie sesión como usuario de destino para experimentar el quiosco.

# <a name="runtime-provisioning---multi-app"></a>[Aprovisionamiento en tiempo de ejecución: varias aplicaciones](#tab/ppkgmak)

## <a name="runtime-provisioning---multi-app"></a>Aprovisionamiento en tiempo de ejecución: varias aplicaciones

1. Cree la configuración xml para la experiencia de quiosco deseada. Vea [los ejemplos](../hololens-kiosk-reference.md#kiosk-xml-code-samples) aquí para comenzar.

1. Abra [Windows Diseñador de configuración de](https://www.microsoft.com/store/apps/9nblggh4tx22).

1. En la página Inicio, seleccione **Aprovisionar HoloLens dispositivos.** <br>
<kbd>
    <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
</kbd>

<br>

4. Seleccione **Aprovisionar HoloLens 2 dispositivos y, a continuación,** seleccione Siguiente. <br>
<kbd>
    <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
</kbd>

<br>

5. Dé un nombre al proyecto. Opcionalmente, escriba una descripción. Seleccione **Finalizar** para continuar.

6. En la parte inferior izquierda de la pantalla, seleccione **Cambiar al editor avanzado.** Para confirmar el cambio al editor avanzado, seleccione **Sí.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

7. En el lado izquierdo, expanda Configuración del entorno de ejecución, AssignedAccess y **seleccione MultiAppAssignedAccess.** <br>

    <kbd>
        <img alt="select MultiAppAssignedAccess" src="../images/kiosk-steps/kiosk-provision-3.png"/>
    </kbd>

<br>

8. Seleccione el botón **Examinar...** para abrir el explorador de archivos. Y seleccione el archivo XML de quiosco configurado.

9. Seleccione **Exportar** y, a continuación, **Paquete de aprovisionamiento.**

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

10. Cambie el tipo de propietario a **Administrador de TI.** <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

11. Seleccione **Siguiente** tres veces. A continuación, **seleccione Compilar**.

12. Una vez que se compile el paquete de aprovisionamiento, abra la carpeta Ubicación de salida. El archivo .ppkg es el paquete de aprovisionamiento. Paso opcional: Guarde el proyecto.

13. Ahora puede aplicar el paquete de aprovisionamiento. Puede aplicar un [paquete de aprovisionamiento a HoloLens durante](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) la instalación o aplicar un paquete de [aprovisionamiento a HoloLens después de la instalación.](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)

14. Inicie sesión como usuario de destino para experimentar el quiosco.

# <a name="runtime-provisioning---single-app"></a>[Aprovisionamiento en tiempo de ejecución: aplicación única](#tab/ppkgsak)

## <a name="runtime-provisioning---single-app"></a>Aprovisionamiento en tiempo de ejecución: aplicación única

1. Abra [Windows Diseñador de configuración de](https://www.microsoft.com/store/apps/9nblggh4tx22).

1. En la página Inicio, seleccione **Aprovisionar HoloLens dispositivos.** <br>

    <kbd>
        <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
    </kbd>

<br>

3. Seleccione **Aprovisionar HoloLens 2 dispositivos y, a continuación,** seleccione Siguiente. <br>

    <kbd>
        <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

4. Dé un nombre al proyecto. Opcionalmente, escriba una descripción. Seleccione **Finalizar** para continuar.

5. En la parte inferior izquierda de la pantalla, seleccione **Cambiar al editor avanzado.** Para confirmar el cambio al editor avanzado, seleccione **Sí.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

6. En el lado izquierdo, expanda Configuración del entorno de ejecución, AssignedAccess y **seleccione AssignedAccessSettings.** <br>

    <kbd>
        <img alt="Navigate to assigned access settings" src="../images/kiosk-steps/kiosk-provision-sak-1.png"/>
    </kbd>

<br>

7. Defina la pantalla completa en el cuadro de texto. Por ejemplo, a continuación se crea una pantalla completa de aplicación única para una cuenta local denominada LocalAccount que es la aplicación de configuración.
```{"Account":"LocalAccount","AUMID":"BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App"}```

8. Seleccione **Exportar** y, a continuación, **Paquete de aprovisionamiento.** <br>

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

9. Cambie el tipo de propietario a **Administrador de TI.** <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

10. Seleccione **Siguiente** tres veces. A continuación, **seleccione Compilar**.

11. Una vez que se compile el paquete de aprovisionamiento, abra la carpeta Ubicación de salida. El archivo .ppkg es el paquete de aprovisionamiento. Paso opcional: Guarde el proyecto.

12. Ahora puede aplicar el paquete de aprovisionamiento. Puede aplicar un [paquete de aprovisionamiento a HoloLens durante](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) la instalación o aplicar un paquete de [aprovisionamiento a HoloLens después de la instalación.](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)