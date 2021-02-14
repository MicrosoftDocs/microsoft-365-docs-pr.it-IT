---
title: Disattivare la sincronizzazione della directory per Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: ee5f861e-bd48-4267-83d1-a4ead4b4a00d
description: In questo articolo, trovare informazioni sull'uso di PowerShell per disattivare la sincronizzazione della directory per Microsoft 365.
ms.openlocfilehash: 0bd8591f91dcf20cb1061b3cd93f69511027bab1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690924"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a>Disattivare la sincronizzazione della directory per Microsoft 365
È possibile utilizzare PowerShell per disattivare la sincronizzazione della directory. Non è tuttavia consigliabile disattivare la sincronizzazione della directory come passaggio di risoluzione dei problemi. Se è necessaria assistenza per la risoluzione dei problemi di sincronizzazione della directory, vedere l'articolo risolvere i problemi relativi alla sincronizzazione della [directory per Microsoft 365.](fix-problems-with-directory-synchronization.md) 
  
[Se necessario, contattare](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) il supporto tecnico per i prodotti aziendali.
  
## <a name="turn-off-directory-synchronization"></a>Disattivare la sincronizzazione della directory  
Per disattivare la sincronizzazione della directory:
  
1. Innanzitutto, installare il software necessario e connettersi all'abbonamento a Microsoft 365. Per istruzioni, vedere [Connettersi con il modulo di Microsoft Azure Active Directory per Windows PowerShell.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
    
2. Utilizzare [Set-MsolDirSyncEnabled per](https://go.microsoft.com/fwlink/p/?LinkId=821939) disabilitare la sincronizzazione della directory: 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
>Se si utilizza questo comando, è necessario attendere 72 ore prima di poter riattivare la sincronizzazione della directory.
>
 
