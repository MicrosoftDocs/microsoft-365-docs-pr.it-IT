---
title: Disattivare la creazione di report per la posta indesiderata in Outlook sul web
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
ms.collection:
- M365-security-compliance
description: In qualità di amministratore di Office 365, è possibile disattivare la possibilità per gli utenti di segnalare la posta elettronica come indesiderata.
ms.openlocfilehash: de0e5d1aa51ececafc0d344b9907f6751a613370
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441173"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a>Disattivare la creazione di report per la posta indesiderata in Outlook sul web

È possibile inviare messaggi di posta indesiderata, di phishing e non a Microsoft per l'analisi utilizzando le opzioni di segnalazione della posta indesiderata di Outlook sul Web (in precedenza note come Outlook Web App), come descritto in [report posta indesiderata e truffe di phishing in Outlook sul Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). Se non si desidera utilizzare queste opzioni, gli amministratori possono disattivarli tramite il cmdlet [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) . 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare
<a name="sectionSection0"> </a>

- Tempo stimato per il completamento: 5 minuti
    
- Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere "criteri cassetta postale di Outlook sul Web" nell'argomento [autorizzazioni di Outlook sul Web](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp) . 

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a>Disattiva la segnalazione di posta indesiderata, phishing e non di posta indesiderata a Microsoft
<a name="sectionSection1"> </a>

Prima di tutto, eseguire il seguente comando per ottenere i nomi dei criteri cassetta postale di Outlook sul Web disponibili:
  
```
Get-OwaMailboxPolicy | Format-Table Name
```

Successivamente, utilizzare la seguente sintassi per abilitare o disabilitare la creazione di messaggi di posta indesiderata e non per la gestione delle cianfrusaglie a Microsoft in Outlook sul Web:
  
```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

In questo esempio viene disattivata la creazione di report nel criterio cassetta postale di Outlook Web App predefinito:
  
```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-OwaMailboxPolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx) e [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx).

## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo
<a name="sectionSection2"> </a>

Eseguire **Get-OwaMailboxPolicy** per controllare i valori dei parametri e quindi aprire Outlook sul Web per un utente in cui è stato applicato il criterio cassetta postale di Outlook sul Web e verificare che le opzioni per segnalare la posta indesiderata, il phishing e non la posta indesiderata non siano disponibili. È comunque possibile contrassegnare i messaggi come posta indesiderata, phishing e non indesiderata, ma non sarà possibile segnalarli. 
