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
ms.openlocfilehash: 9b69d2b6f075539f411da971a314c127843b945a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917571"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Allegati sicuri per SharePoint, OneDrive e Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Allegati sicuri per SharePoint, OneDrive e Microsoft Teams in [Microsoft Defender per Office 365](office-365-atp.md) offre un ulteriore livello di protezione per i file che sono già stati analizzati in fase di caricamento dal motore di rilevamento virus comune in Microsoft [365.](virus-detection-in-spo.md) Allegati sicuri per SharePoint, OneDrive e Microsoft Teams consente di rilevare e bloccare i file esistenti identificati come dannosi nei siti del team e nelle raccolte documenti.

Allegati sicuri per SharePoint, OneDrive e Microsoft Teams non è abilitato per impostazione predefinita. Per attivarlo, vedere [Attivare allegati sicuri per SharePoint, OneDrive e Microsoft Teams.](turn-on-atp-for-spo-odb-and-teams.md)

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>Funzionamento degli allegati sicuri per SharePoint, OneDrive e Microsoft Teams

Quando allegati sicuri per SharePoint, OneDrive e Microsoft Teams è abilitato e identifica un file come dannoso, il file viene bloccato tramite l'integrazione diretta con gli archivi file. L'immagine seguente mostra un esempio di file dannoso rilevato in una raccolta.

![File in OneDrive for Business con uno rilevato come dannoso](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Anche se il file bloccato è ancora elencato nella raccolta documenti e nelle applicazioni Web, mobili o desktop, gli utenti non possono aprire, copiare, spostare o condividere il file. Ma possono eliminare il file bloccato.

Ecco un esempio dell'aspetto di un file bloccato in un dispositivo mobile:

![Eliminazione di un file bloccato da OneDrive for Business dall'app OneDrive per dispositivi mobili](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

Per impostazione predefinita, gli utenti possono scaricare un file bloccato. Ecco l'aspetto del download di un file bloccato in un dispositivo mobile:

![Download di un file bloccato in OneDrive for Business](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

Gli amministratori di SharePoint Online possono impedire agli utenti di scaricare file dannosi. Per istruzioni, vedere [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).

Per ulteriori informazioni sull'esperienza utente quando un file è stato rilevato come dannoso, vedere What [to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Visualizzare informazioni sui file dannosi rilevati dagli allegati sicuri per SharePoint, OneDrive e Microsoft Teams

I file identificati come dannosi da Microsoft Defender per Office 365 verranno visualizzati nei report per [Microsoft Defender per Office 365](view-reports-for-atp.md) e in Esplora risorse (e rilevamenti in tempo [reale).](threat-explorer.md)

A maggio 2018, quando un file viene identificato come dannoso da Microsoft Defender per Office 365, il file è disponibile anche in quarantena. Per ulteriori informazioni, vedere [Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files).

## <a name="keep-these-points-in-mind"></a>Tenere presenti questi punti

- Defender per Office 365 non analizza ogni singolo file in SharePoint Online, OneDrive for Business o Microsoft Teams. Si tratta di un comportamento legato alla progettazione. I file vengono analizzati in modo asincrono. Il processo usa gli eventi di condivisione e attività guest insieme all'euristica intelligente e ai segnali di minaccia per identificare i file dannosi.

- Verificare che i siti di SharePoint siano configurati per l'utilizzo [dell'esperienza moderna.](/sharepoint/guide-to-sharepoint-modern-experience) Defender per la protezione di Office 365 si applica se viene usata l'esperienza moderna o la visualizzazione classica. Tuttavia, gli indicatori visivi che un file è bloccato sono disponibili solo nell'esperienza moderna.

- Allegati sicuri per SharePoint, OneDrive e Microsoft Teams fa parte della strategia generale di protezione dalle minacce dell'organizzazione, che include la protezione da posta indesiderata e antimalware in Exchange Online Protection (EOP), nonché collegamenti sicuri e allegati sicuri in Microsoft Defender per Office 365. Per ulteriori informazioni, vedere [Protezione dalle minacce in Office 365.](protect-against-threats.md)