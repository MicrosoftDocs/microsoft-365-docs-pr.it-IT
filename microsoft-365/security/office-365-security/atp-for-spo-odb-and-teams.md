---
title: Office 365 ATP per SharePoint, OneDrive e Microsoft Teams
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 03/19/2019
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
description: Estendere Office 365 Advanced Threat Protection ai file in SharePoint Online, OneDrive for business e Microsoft teams per consentire una collaborazione più sicura per l'organizzazione.
ms.openlocfilehash: ad2b5e06dab99bb2cdbe4b0e4c1785d716d865f7
ms.sourcegitcommit: 6e01543b3fff50a28719478b19b644991ba7505a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "38035716"
---
# <a name="office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Office 365 ATP per SharePoint, OneDrive e Microsoft Teams

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Panoramica di Office 365 ATP per SharePoint, OneDrive e Microsoft Teams

Gli utenti condividono periodicamente file e collaborano con SharePoint, OneDrive e Microsoft teams. Con [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), l'organizzazione può collaborare in maniera più sicura. ATP aiuta a rilevare e bloccare i file identificati come dannosi nei siti del team e nelle raccolte documenti.  
  
## <a name="how-it-works"></a>Funzionamento

Quando un file in SharePoint Online, OneDrive for business e Microsoft teams è stato identificato come dannoso, ATP si integra direttamente con gli archivi di file per bloccare il file. Nell'immagine seguente viene mostrato un esempio di un file dannoso rilevato in una raccolta.
  
[![File in OneDrive for business con uno rilevato come dannoso](../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
Anche se il file bloccato è ancora elencato nella raccolta documenti e nelle applicazioni Web, per dispositivi mobili o desktop, il file bloccato non può essere aperto, copiato, spostato o condiviso. Tuttavia, gli utenti possono eliminare un file bloccato. Di seguito è riportato un esempio di come si presenta sul dispositivo mobile di un utente:
  
[![Eliminazione di un file bloccato da OneDrive for business dall'app per dispositivi mobili di OneDrive](../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
A seconda del modo in cui Office 365 è configurato, la gente potrebbe o meno avere la possibilità di scaricare un file bloccato. Di seguito è riportato l'aspetto del download di un file bloccato nel dispositivo mobile di un utente:
  
[![Download di un file bloccato in OneDrive for business](../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
Per altre informazioni, vedere [Office 365 ATP per SharePoint, OneDrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).
  
## <a name="keep-these-points-in-mind"></a>Tenere presente questi punti

- ATP non analizzerà tutti i singoli file in SharePoint Online, OneDrive for business o Microsoft teams. Questo è il funzionamento predefinito. I file vengono analizzati in modo asincrono, tramite un processo che utilizza la condivisione e gli eventi di attività Guest insieme ai segnali euristici intelligenti e alle minacce per identificare i file dannosi.

- Verificare che i siti di SharePoint siano configurati per l'utilizzo dell' [esperienza moderna](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience). Quando un file viene identificato come dannoso e bloccato, gli utenti possono vedere che si è verificato l'esperienza moderna, ma non la visualizzazione classica. La protezione del trifosfato di adenosina applica se viene utilizzata l'esperienza moderna o la visualizzazione classica. Tuttavia, gli indicatori visivi che un file è bloccato sono presenti solo nell'esperienza moderna.
    
- I file identificati come dannosi in SharePoint Online, OneDrive for business o Microsoft teams verranno visualizzati nei [report di Office 365 Advanced Threat Protection](view-reports-for-atp.md) e in [Explorer (e in Real-Time detections)](threat-explorer.md).
    
- ATP fa parte della strategia globale di protezione dalle minacce dell'organizzazione, che include protezione da posta indesiderata e antimalware, oltre a collegamenti sicuri e allegati sicuri. Per ulteriori informazioni, vedere [protezione dalle minacce in Office 365](protect-against-threats.md).
    
- Un amministratore di SharePoint Online può decidere se consentire agli utenti di scaricare file che vengono rilevati come dannosi. A tale scopo, è possibile eseguire il cmdlet Set-SPOTenant di PowerShell utilizzando un parametro DisallowInfectedFileDownload (vedere [accendere Office 365 ATP per SharePoint, OneDrive e Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md)).
    
## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a>Quarantena in ATP per SharePoint Online, OneDrive for business e Microsoft Teams

 A partire dalla fine di maggio 2018, le funzionalità di [quarantena](quarantine-email-messages.md) nel centro sicurezza &amp; e conformità vengono estese a ATP per SharePoint Online, OneDrive for business e Microsoft teams.
  
Quando un file in SharePoint Online, OneDrive for business o Microsoft teams viene identificato come dannoso, oltre a ATP che blocca il file dall'apertura o dalla condivisione, tale file è incluso in un elenco di elementi in quarantena. (Nel centro sicurezza &amp; e conformità, passare alla **** \> **** \> **quarantena** e al filtro per la gestione delle minacce per il **contenuto**). 
  
Se si è parte del team di sicurezza di Office 365 dell'organizzazione e le autorizzazioni necessarie sono state [assegnate al centro sicurezza &amp; e conformità di Office 365](permissions-in-the-security-and-compliance-center.md), è possibile scaricare, rilasciare, segnalare ed eliminare file che vengono rilevati come dannosi da ATP dalla quarantena.
  
- Il **rilascio e la segnalazione** di un file rimuove il blocco ATP nel file nel sito del team o nella raccolta documenti di SharePoint, OneDrive o Microsoft teams. Gli utenti sono quindi in grado di aprire, condividere e scaricare il file. Quando l'opzione **Invia rapporto a Microsoft** è selezionata, il file viene segnalato come falso positivo a Microsoft. 
    
- L' **eliminazione di un file** consente di rimuovere il file dalla quarantena; Tuttavia, il file è ancora bloccato dall'apertura o dalla condivisione. Il file deve essere eliminato anche nella rispettiva raccolta documenti o sito del team (SharePoint Online, OneDrive for business o Microsoft Teams). 
    
- Il **download di un file** consente di scaricare e analizzare il file per eventuali falsi positivi. 
    
## <a name="next-steps"></a>Passaggi successivi

1. [Attivazione di Office 365 ATP per SharePoint, OneDrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)
    
2. [Visualizzare informazioni sui file dannosi rilevati in SharePoint, OneDrive o Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)
    
