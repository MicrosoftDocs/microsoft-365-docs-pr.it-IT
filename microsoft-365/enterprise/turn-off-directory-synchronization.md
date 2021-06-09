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
ms.openlocfilehash: 26f8729078ea06657ced565db780b57c7e537aa4
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445709"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a>Disattivare la sincronizzazione della directory per Microsoft 365
È possibile utilizzare PowerShell per disattivare la sincronizzazione della directory e convertire gli utenti sincronizzati in solo cloud. Tuttavia, non è consigliabile disattivare la sincronizzazione della directory come passaggio di risoluzione dei problemi. Se è necessaria assistenza per la risoluzione dei problemi di sincronizzazione della directory, vedere l'articolo Risolvere i [problemi di sincronizzazione della directory per Microsoft 365.](fix-problems-with-directory-synchronization.md) 
  
[Se necessario,](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) contattare il supporto per i prodotti aziendali.
  
## <a name="turn-off-directory-synchronization"></a>Disattivare la sincronizzazione della directory  
Per disattivare la sincronizzazione della directory:
  
1. Innanzitutto, installare il software necessario e connettersi all'Microsoft 365 abbonamento. Per istruzioni, vedere [Connessione con il modulo Microsoft Azure Active Directory per Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
    
2. Utilizzare [Set-MsolDirSyncEnabled](/previous-versions/azure/dn194097(v=azure.100)) per disabilitare la sincronizzazione della directory: 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
>Se si utilizza questo comando, è necessario attendere 72 ore prima di poter riattivare la sincronizzazione della directory.
>
