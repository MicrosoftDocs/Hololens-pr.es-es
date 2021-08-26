---
ms.openlocfilehash: d96a769b40daba0948f8f3c71a88513576c531b5
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859411"
---
# <a name="non-aad-configuration"></a>[Configuración que no es de AAD](#tab/nonaadlogon)

#### <a name="non-aad-configuration"></a>Configuración que no es de AAD

1. Cree un paquete de aprovisionamiento que:
    1. Configura los valores de Runtime/AssignedAccess para permitir las cuentas de visitante.
    1. Opcionalmente, inscribe el dispositivo en MDM (Configuración del entorno de ejecución/Área de trabajo/Inscripciones) para que se pueda administrar más adelante.
    1. No crear una cuenta local
2. [Aplique el paquete de aprovisionamiento](../hololens-provisioning.md).

# <a name="aad-configuration"></a>[Configuración de AAD](#tab/aadlogon)

#### <a name="aad-configuration"></a>Configuración de AAD

Los dispositivos unidos a AAD configurados para el modo de pantalla completa pueden iniciar sesión en una cuenta de visitante con un solo botón pulsando en la pantalla de inicio de sesión. Una vez que haya iniciado sesión en la cuenta de visitante, el dispositivo no volverá a solicitar el inicio de sesión hasta que el visitante haya iniciado sesión explícitamente en el menú Inicio o se reinicie el dispositivo.

El inicio de sesión automático del visitante se puede administrar a través [de la directiva OMA-URI personalizada:](/mem/intune/configuration/custom-settings-windows-10)

- Valor de URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Directiva | Descripción | Configurations |
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | Permite que un visitante inicie sesión automáticamente en una pantalla completa. | 1 (Sí), 0 (No, valor predeterminado). |