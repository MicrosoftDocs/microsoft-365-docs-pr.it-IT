---
title: ATP per SharePoint, OneDrive e Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Informazioni su Office 365 Advanced Threat Protection per i file in SharePoint Online, OneDrive for business e Microsoft teams.
ms.openlocfilehash: 95557e99817f7e7d3fe678c1966e4e04fd3753d7
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350890"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a>ATP per SharePoint, OneDrive e Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

ATP per SharePoint, OneDrive e Microsoft teams in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) fornisce un ulteriore livello di protezione per i file che sono già stati analizzati al momento del caricamento da parte del [motore di rilevamento virus comune in Microsoft 365](virus-detection-in-spo.md). ATP per SharePoint, OneDrive e Microsoft teams consente di rilevare e bloccare i file esistenti identificati come dannosi nei siti del team e nelle raccolte documenti.

ATP per SharePoint, OneDrive e Microsoft teams non è abilitato per impostazione predefinita. Per attivarlo, vedere [accendere ATP per SharePoint, OneDrive e Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md).

## <a name="how-atp-for-sharepoint-onedrive-and-microsoft-teams-works"></a>Funzionamento di ATP per SharePoint, OneDrive e Microsoft Teams

Quando ATP per SharePoint, OneDrive e Microsoft teams è abilitato e identifica un file come dannoso, il file viene bloccato utilizzando l'integrazione diretta con gli archivi di file. Nell'immagine seguente viene mostrato un esempio di un file dannoso rilevato in una raccolta.

![File in OneDrive for business con uno rilevato come dannoso](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Anche se il file bloccato è ancora elencato nella raccolta documenti e nelle applicazioni Web, per dispositivi mobili o desktop, gli utenti non possono aprire, copiare, spostare o condividere il file. Tuttavia, è possibile eliminare il file bloccato.

Di seguito è riportato un esempio di come si presenta un file bloccato su un dispositivo mobile:

![Eliminazione di un file bloccato da OneDrive for business dall'app per dispositivi mobili di OneDrive](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

Per impostazione predefinita, gli utenti possono scaricare un file bloccato. Di seguito è riportato l'aspetto del download di un file bloccato su un dispositivo mobile:

![Download di un file bloccato in OneDrive for business](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

Gli amministratori di SharePoint Online possono impedire agli utenti di scaricare file dannosi. Per istruzioni, vedere [utilizzare PowerShell di SharePoint Online per impedire agli utenti di scaricare file dannosi](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).

Per ulteriori informazioni sull'esperienza utente quando un file è stato rilevato come dannoso, vedere [cosa fare quando si trova un file dannoso in SharePoint Online, OneDrive o Microsoft teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).

## <a name="view-information-about-malicious-files-detected-by-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Visualizzare informazioni sui file dannosi rilevati da ATP per SharePoint, OneDrive e Microsoft Teams

I file identificati come dannosi da ATP verranno visualizzati nei [report di Office 365 Advanced Threat Protection](view-reports-for-atp.md) e in [Explorer (e in Real-Time detections)](threat-explorer.md).

A maggio 2018, quando un file viene identificato come dannoso da ATP, il file è disponibile anche in quarantena. Per ulteriori informazioni, vedere [use the Security & Compliance Center per gestire i file in quarantena](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).

## <a name="keep-these-points-in-mind"></a>Tenere presente questi punti

- ATP non analizzerà tutti i singoli file in SharePoint Online, OneDrive for business o Microsoft teams. Si tratta di un comportamento legato alla progettazione. I file vengono analizzati in modo asincrono. Il processo utilizza gli eventi di condivisione e attività Guest insieme a sistemi euristici intelligenti e segnalazioni di minacce per identificare i file dannosi.

- Verificare che i siti di SharePoint siano configurati per l'utilizzo dell' [esperienza moderna](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience). La protezione del trifosfato di adenosina applica se viene utilizzata l'esperienza moderna o la visualizzazione classica. Tuttavia, gli indicatori visivi che un file è bloccato sono disponibili solo nell'esperienza moderna.

- ATP per SharePoint, OneDrive e Microsoft teams è parte integrante della strategia globale di protezione dalle minacce dell'organizzazione, che include la protezione da posta indesiderata e antimalware in Exchange Online Protection (EOP), nonché collegamenti sicuri e allegati sicuri in Office 365 ATP. Per ulteriori informazioni, vedere [protezione dalle minacce in Office 365](protect-against-threats.md).
