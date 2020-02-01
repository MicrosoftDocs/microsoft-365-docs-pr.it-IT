---
title: Verifica del reindirizzamento della posta indesiderata nella cartella Posta indesiderata degli utenti
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 7/16/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a instradare la posta indesiderata alle cartelle di posta indesiderata degli utenti in Exchange Online Protection.
ms.openlocfilehash: 6d1fd625669e8b638a408b2db1993f45fa653ffb
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599363"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Verifica del reindirizzamento della posta indesiderata nella cartella Posta indesiderata degli utenti

> [!IMPORTANT]
> Questo argomento si applica solo ai clienti di Exchange Online Protection (EOP) che ospitano le cassette postali in locale in una distribuzione ibrida. I clienti di Exchange Online le cui cassette postali sono completamente ospitate in Office 365 non devono eseguire questi comandi.

L'azione di protezione da posta indesiderata predefinita per i clienti EOP consiste nello spostamento dei messaggi di posta indesiderata nella cartella Posta indesiderata dei destinatari. Affinché questa azione funzioni con le cassette postali locali, è necessario configurare le regole del flusso di posta di Exchange (note anche come regole di trasporto) sui server perimetrali o hub locali per rilevare le intestazioni di posta indesiderata aggiunte da EOP. Queste regole del flusso di posta consentono di impostare il livello di probabilità di protezione da posta indesiderata utilizzato dalla proprietà SclJunkThreshold del cmdlet Set-OrganizationConfig per spostare lo spam nella cartella posta indesiderata di ogni cassetta postale.

### <a name="to-add-mail-flow-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a>Per aggiungere regole del flusso di posta per garantire che la posta indesiderata venga spostata nella cartella posta indesiderata utilizzando Windows PowerShell

1. Accedere a Exchange Management Shell per il server Exchange locale. Per sapere come aprire Exchange Management Shell nell'organizzazione Exchange locale, vedere **Open the Shell**.

2. Per instradare i messaggi di posta indesiderata filtrata in base al contenuto alla cartella Posta indesiderata, utilizzare il seguente comando:

   ```Powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
   ```

   Dove _NameForRule_ è il nome della nuova regola, ad esempio JunkContentFilteredMail.

3. Per instradare i messaggi di posta indesiderata in base al contenuto alla cartella Posta indesiderata, utilizzare il seguente comando:

   ```Powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
   ```

   Dove _NameForRule_ è il nome della nuova regola, ad esempio JunkMailBeforeReachingContentFilter.

4. Eseguire il seguente comando per verificare che i messaggi provenienti da mittenti contenuti in un elenco di blocco nel criterio di filtro della posta indesiderata, ad esempio l'elenco dei **Mittenti bloccati** , vengano instradati alla cartella posta indesiderata:

   ```Powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
   ```

   Dove _NameForRule_ è il nome della nuova regola, ad esempio JunkMailInSenderBlockList.

Se non si desidera utilizzare l'azione **Sposta messaggio all'interno della cartella posta indesiderata** , è possibile scegliere un'altra azione nei criteri di filtro del contenuto nell'interfaccia di amministrazione di Exchange. Per ulteriori informazioni, vedere [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md). Per ulteriori informazioni su questi campi nell'intestazione del messaggio, vedere intestazioni dei messaggi di protezione da [posta indesiderata](anti-spam-message-headers.md).

> [!TIP]
> Se non si desidera utilizzare l'azione **Sposta messaggio all'interno della cartella posta indesiderata** , è possibile scegliere un'altra azione nei criteri di filtro del contenuto nell'interfaccia di amministrazione di Exchange. Per ulteriori informazioni, vedere [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md). Per ulteriori informazioni su questi campi nell'intestazione del messaggio, vedere intestazioni dei messaggi di protezione da [posta indesiderata](anti-spam-message-headers.md).

## <a name="see-also"></a>Vedere anche

[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)
