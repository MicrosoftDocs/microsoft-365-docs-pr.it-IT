---
title: Allegati sicuri per SharePoint, OneDrive e Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Informazioni su Microsoft Defender per Office 365 per i file in SharePoint Online, OneDrive for Business e Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 67bd2a0952ac630888b07eaf05d365736a0472ea
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028836"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Allegati sicuri per SharePoint, OneDrive e Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Safe Gli allegati per SharePoint, OneDrive e Microsoft Teams in [Microsoft Defender per Office 365](whats-new-in-defender-for-office-365.md) offre un ulteriore livello di protezione per i file che sono già stati analizzati in fase di caricamento dal motore di rilevamento dei virus comune in [Microsoft 365](virus-detection-in-spo.md). Safe Gli allegati per SharePoint, OneDrive e Microsoft Teams consentono di rilevare e bloccare i file esistenti identificati come dannosi nei siti del team e nelle raccolte documenti.

Safe Gli allegati SharePoint, OneDrive e Microsoft Teams non sono abilitati per impostazione predefinita. Per attivarlo, vedere [Attivare Safe allegati per SharePoint, OneDrive e Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>Funzionamento Safe allegati per SharePoint, OneDrive e Microsoft Teams

Quando Safe allegati per SharePoint, OneDrive e Microsoft Teams è abilitato e identifica un file come dannoso, il file viene bloccato utilizzando l'integrazione diretta con gli archivi file. L'immagine di seguito mostra un esempio di file dannoso rilevato in una raccolta.

![File in OneDrive for Business con uno rilevato come dannoso](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Anche se il file bloccato è ancora elencato nella raccolta documenti e nelle applicazioni Web, mobili o desktop, gli utenti non possono aprire, copiare, spostare o condividere il file. Ma possono eliminare il file bloccato.

Ecco un esempio dell'aspetto di un file bloccato in un dispositivo mobile:

![Eliminazione di un file bloccato OneDrive for Business dall'app OneDrive per dispositivi mobili](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

Per impostazione predefinita, gli utenti possono scaricare un file bloccato. Ecco l'aspetto del download di un file bloccato in un dispositivo mobile:

![Download di un file bloccato in OneDrive for Business](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

SharePoint Gli amministratori online possono impedire agli utenti di scaricare file dannosi. Per istruzioni, vedere [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).

Per ulteriori informazioni sull'esperienza utente quando un file è stato rilevato come dannoso, vedere Cosa fare quando viene trovato un file dannoso [in SharePoint Online, OneDrive](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)o Microsoft Teams .

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Visualizzare informazioni sui file dannosi rilevati Safe allegati per SharePoint, OneDrive e Microsoft Teams

I file identificati come dannosi dagli allegati di Safe per SharePoint, OneDrive e Microsoft Teams verranno visualizzati nei report per [Microsoft Defender](view-reports-for-mdo.md) per Office 365 e in Esplora risorse (e rilevamenti in tempo [reale).](threat-explorer.md)

A maggio 2018, quando un file viene identificato come dannoso da allegati Safe per SharePoint, OneDrive e Microsoft Teams, il file è disponibile anche in quarantena. Per altre informazioni, vedi [Gestire i file in quarantena in Defender per Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365).


## <a name="keep-these-points-in-mind"></a>Tenere presenti questi punti

- Defender per Office 365 non analizza ogni singolo file in SharePoint Online, OneDrive for Business o Microsoft Teams. Si tratta di un comportamento legato alla progettazione. I file vengono analizzati in modo asincrono. Il processo usa gli eventi di condivisione e attività guest insieme all'euristica intelligente e ai segnali di minaccia per identificare i file dannosi.

- Verificare che i siti SharePoint siano configurati per l'utilizzo [dell'esperienza moderna.](/sharepoint/guide-to-sharepoint-modern-experience) Defender per Office 365 protezione si applica se viene usata l'esperienza moderna o la visualizzazione classica; Tuttavia, gli indicatori visivi che un file è bloccato sono disponibili solo nell'esperienza moderna.

- Safe Gli allegati per SharePoint, OneDrive e Microsoft Teams fanno parte della strategia globale di protezione dalle minacce dell'organizzazione, che include la protezione da posta indesiderata e antimalware in Exchange Online Protection (EOP), nonché collegamenti Safe e allegati Safe in Microsoft Defender per Office 365. Per ulteriori informazioni, vedere [Protezione dalle minacce in Office 365](protect-against-threats.md).
