---
title: 'Zero-Hour Auto Purge: protezione contro la posta indesiderata e il malware'
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/11/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
description: Zero-hour auto Purge (ZAP) è una funzionalità di protezione della posta elettronica che consente di rilevare i messaggi con posta indesiderata o malware che sono già stati recapitati alle cassette postali degli utenti e quindi di eseguire il rendering del contenuto dannoso innocuo. La modalità di utilizzo di ZAP dipende dal tipo di contenuto dannoso rilevato.
ms.openlocfilehash: 725dc9da9119169937231372585489bdf192b11e
ms.sourcegitcommit: 0d423b50d2f1f4eccd64e35e00f67313244efba9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "37319269"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>Zero-Hour Auto Purge: protezione contro la posta indesiderata e il malware

## <a name="overview"></a>Panoramica

Zero-hour auto Purge (ZAP) è una funzionalità di protezione della posta elettronica che consente di rilevare messaggi con phishing, posta indesiderata o malware che sono già stati recapitati alle cassette postali degli utenti e quindi viene eseguito il rendering del contenuto dannoso innocuo. La modalità di utilizzo di ZAP dipende dal tipo di contenuto dannoso rilevato. la posta può essere zapped a causa di contenuto, URL o allegati di posta elettronica.
  
ZAP è disponibile con la protezione Exchange Online predefinita inclusa con qualsiasi sottoscrizione di Office 365 che contiene cassette postali di Exchange Online.

L'opzione ZAP è attivata per impostazione predefinita, ma devono essere soddisfatte le condizioni seguenti:
  
- **Azione di posta** indesiderata è impostata per **spostare il messaggio nella cartella posta indesiderata**. È inoltre possibile creare un nuovo criterio di filtro per la posta indesiderata che si applica solo a un gruppo di utenti se non si desidera che tutte le cassette postali vengano schermate da ZAP.

- Gli utenti hanno mantenuto le impostazioni predefinite della posta indesiderata e non sono state disattivate la protezione della posta indesiderata. Per informazioni dettagliate sulle opzioni utente in Outlook, vedere [modificare il livello di protezione del filtro della posta indesiderata](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b) .
  
## <a name="how-zap-works"></a>Funzionamento di ZAP

Office 365 aggiorna le firme di malware e del motore di protezione da posta indesiderata in tempo reale su base giornaliera. Tuttavia, gli utenti possono comunque ottenere messaggi dannosi recapitati alle cassette postali per una serie di motivi, incluso se il contenuto è armato dopo essere stato recapitato agli utenti. ZAP risolve questo monitoraggio continuamente gli aggiornamenti alle firme di posta indesiderata e malware di Office 365. ZAP è in grado di trovare e rimuovere i messaggi precedentemente recapitati che sono già presenti nelle cassette postali degli utenti.

L'azione ZAP è senza problemi per l'utente della cassetta postale; non vengono notificati se viene spostato un messaggio di posta elettronica. Il messaggio non deve superare i 2 giorni.
  
Gli elenchi consentiti, [le regole del flusso di posta](https://go.microsoft.com/fwlink/p/?LinkId=722755) (note anche come regole di trasporto) e le regole degli utenti finali o i filtri aggiuntivi hanno la precedenza su Zap.

### <a name="malware-zap"></a>Malware ZAP

Per il malware appena rilevato, ZAP rimuove gli allegati dai messaggi di posta elettronica, lasciando il corpo del messaggio nella cassetta postale dell'utente. Gli allegati vengono rimossi indipendentemente dallo stato di lettura della posta.

Il malware ZAP è abilitato per impostazione predefinita nel criterio di malware. È possibile disabilitare lo ZAP antimalware utilizzando il parametro *ZapEnabled* nel cmdlet [set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) in PowerShell di Exchange Online o Exchange Online Protection PowerShell.

### <a name="phish-zap"></a>Phishing ZAP

Per la posta identificata come phishing dopo il recapito, ZAP esegue un'azione in base ai criteri di posta indesiderata che l'utente deve coprire. Se l'azione phishing del criterio è impostata per eseguire un'azione su un messaggio di posta elettronica (redirect, DELETE, Quarantine, Move to Junk), ZAP sposterà il messaggio nella cartella posta indesiderata della posta in arrivo dell'utente, indipendentemente dallo stato di lettura della posta. Se l'azione phishing del criterio non è impostata su azione (aggiungere X-header, Modify Subject, No Action), ZAP non eseguirà alcuna azione per la posta. Per ulteriori informazioni su come [configurare i criteri di filtro posta indesiderata](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) , vedere qui.

Phishing ZAP è abilitato per impostazione predefinita nei criteri di posta indesiderata. Phishing ZAP può essere disattivato utilizzando il parametro *PhishZapEnabled* di [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), un cmdlet di EOP.

> **[Nota]** il parametro precedente cmdlet *ZapEnabled* che controllava sia phishing che spam ZAP sarà **deprecato il 1 ° febbraio 2020**. Se sono stati scritti script che utilizzano il parametro ZapEnabled, è consigliabile aggiornarli per l'utilizzo di SpamZapEnabled e PhishZapEnabled. Nel periodo di transizione tutti e tre i parametri (ZapEnabled, PhishZapEnabled e SpamZapEnabled) saranno disponibili tramite il cmdlet. Fino a quando non viene impostato in modo esplicito tramite l'interfaccia utente o PowerShell, PhishZapEnabled e SpamZapEnabled visualizzeranno un valore ereditato dal parametro ZapEnabled. Dopo aver impostato i nuovi parametri, non erediterà più dal parametro ZapEnabled. Dopo che è stato deprecato, l'impostazione di ZapEnabled non avrà alcun effetto sulle proprietà PhishZapEnabled o SpamZapEnabled e ZapEnabled verrà rimosso dall'elenco dei parametri nei cmdlet.

### <a name="spam-zap"></a>Spam ZAP

Per la posta elettronica identificata come posta indesiderata dopo il recapito, ZAP esegue un'azione in base ai criteri di posta indesiderata che l'utente deve coprire. Se l'azione dei criteri di posta indesiderata è impostata per eseguire un'azione su una posta (redirect, DELETE, Quarantine, Move to Junk), ZAP sposterà il messaggio nella cartella posta indesiderata della posta in arrivo dell'utente, se il messaggio non è stato letto. Se l'azione dei criteri di posta indesiderata non è impostata su azione (Aggiungi X-header, modifica oggetto, nessuna azione), ZAP non interverrà sulla posta. Per ulteriori informazioni su come [configurare i criteri di filtro posta indesiderata](configure-your-spam-filter-policies.md) , vedere qui.

Spam ZAP è abilitato per impostazione predefinita nei criteri di posta indesiderata. È possibile disabilitare la posta indesiderata utilizzando il parametro *SpamZapEnabled* del cmdlet [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) in PowerShell di Exchange Online o Exchange Online Protection PowerShell.

> **[Nota]** il parametro precedente cmdlet *ZapEnabled* che controllava sia phishing che spam ZAP sarà **deprecato il 1 ° febbraio 2020**. Se sono stati scritti script che utilizzano il parametro ZapEnabled, è consigliabile aggiornarli per l'utilizzo di SpamZapEnabled e PhishZapEnabled. Nel periodo di transizione tutti e tre i parametri (ZapEnabled, PhishZapEnabled e SpamZapEnabled) saranno disponibili tramite il cmdlet. Fino a quando non viene impostato in modo esplicito tramite l'interfaccia utente o PowerShell, PhishZapEnabled e SpamZapEnabled visualizzeranno un valore ereditato dal parametro ZapEnabled. Dopo aver impostato i nuovi parametri, non erediterà più dal parametro ZapEnabled. Dopo che è stato deprecato, l'impostazione di ZapEnabled non avrà alcun effetto sulle proprietà PhishZapEnabled o SpamZapEnabled e ZapEnabled verrà rimosso dall'elenco dei parametri nei cmdlet.

## <a name="how-to-see-if-zap-moved-your-message"></a>Come vedere se ZAP ha spostato il messaggio

Per determinare se il messaggio è stato spostato da ZAP, è possibile utilizzare il [rapporto sullo stato di protezione di minacce](../../compliance/view-email-security-reports.md#threat-protection-status-report) o l' [esploratore di minacce (e i rilevamenti in tempo reale)](threat-explorer.md).

## <a name="disable-zap"></a>Disabilitare ZAP

Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554). Per connettersi a PowerShell di Exchange Online Protection, vedere [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).

### <a name="disable-malware-zap"></a>Disabilitare il malware ZAP * *

In questo esempio viene disabilitato ZAP nel criterio di filtro antimalware denominato "test".

```Powershell
Set-MalwareFilterPolicy -Identity Test -ZapEnabled $false
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy).

### <a name="disable-phish-zap-and-spam-zap"></a>Disabilitare phishing ZAP e spam ZAP

Per disabilitare phishing e spam ZAP per il tenant O365 o un gruppo di utenti, utilizzare i parametri *PhishZapEnabled* e *SpamZapEnabled* di [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), un cmdlet EOP.

Nell'esempio seguente, phishing e spam ZAP sono disattivati per un criterio di filtro dei contenuti denominato "test".

```Powershell
Set-HostedContentFilterPolicy -Identity Test -PhishZapEnabled $false -SpamZapEnabled $false
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758).

## <a name="faq"></a>Domande frequenti

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a>Cosa succede se un messaggio legittimo viene spostato nella cartella posta indesiderata?
  
È consigliabile seguire la procedura di creazione di report normale per i [falsi positivi](../../compliance/prevent-email-from-being-marked-as-spam.md). L'unico motivo per il quale il messaggio verrebbe spostato dalla posta in arrivo alla cartella posta indesiderata sarebbe perché il servizio ha determinato che il messaggio era posta indesiderata o dannoso.
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a>Che cosa fare se si utilizza la quarantena di Office 365 anziché la cartella posta indesiderata?
  
ZAP non sposta i messaggi in quarantena dalla posta in arrivo in questo momento.
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a>Cosa succede se si dispone di una regola del flusso di posta personalizzata (blocco/Consenti regola)?
  
Le regole create dagli amministratori (regole del flusso di posta) o blocca e Consenti hanno la precedenza. Tali messaggi sono esclusi dai criteri di funzionalità in modo che il flusso di posta seguirà l'azione della regola (blocco/Consenti regola).

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a>Cosa succede se un messaggio viene spostato in un'altra cartella (ad esempio, la regola di posta in arrivo)?

ZAP continua a funzionare in questo caso, a meno che il messaggio non sia stato eliminato o sia indesiderato.

## <a name="related-topics"></a>Argomenti correlati

[Protezione dalla posta indesiderata in Office 365](anti-spam-protection.md)
  
[Bloccare la posta indesiderata utilizzando il filtro di Office 365 al fine di evitare problemi di falsi negativi](reduce-spam-email.md)
