---
title: 'Zero-Hour Auto Purge: protezione contro la posta indesiderata e il malware'
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
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
ms.openlocfilehash: 9ffe169baaa522ca86f712bc0fde41d4985092cd
ms.sourcegitcommit: 39bd4be7e8846770f060b5dd7d895fc8040b18f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111900"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>Zero-Hour Auto Purge: protezione contro la posta indesiderata e il malware

## <a name="overview"></a>Panoramica

Zero-hour auto Purge (ZAP) è una funzionalità di protezione della posta elettronica che consente di rilevare messaggi con phishing, posta indesiderata o malware che sono già stati recapitati alle cassette postali degli utenti e quindi viene eseguito il rendering del contenuto dannoso innocuo. La modalità di utilizzo di ZAP dipende dal tipo di contenuto dannoso rilevato. La posta può essere zapped a causa di contenuto, URL o allegati di posta elettronica.

ZAP è disponibile con la protezione Exchange Online predefinita inclusa con qualsiasi sottoscrizione di Office 365 che contiene cassette postali di Exchange Online.

## <a name="how-zap-works"></a>Funzionamento di ZAP

Office 365 aggiorna le firme di malware e del motore di protezione da posta indesiderata in tempo reale su base giornaliera. Tuttavia, gli utenti possono comunque ottenere messaggi dannosi recapitati alle cassette postali per una serie di motivi, incluso se il contenuto è armato dopo essere stato recapitato agli utenti. ZAP risolve questo monitoraggio continuamente gli aggiornamenti alle firme di posta indesiderata e malware di Office 365. ZAP è in grado di trovare e rimuovere i messaggi precedentemente recapitati che sono già presenti nelle cassette postali degli utenti.

L'azione ZAP è senza problemi per l'utente della cassetta postale; non vengono notificati se viene spostato un messaggio di posta elettronica. Il messaggio non deve superare i 2 giorni.

Gli elenchi consentiti, [le regole del flusso di posta](use-transport-rules-to-configure-bulk-email-filtering.md) (note anche come regole di trasporto) e le regole degli utenti finali o i filtri aggiuntivi hanno la precedenza su Zap.

### <a name="malware-zap"></a>Malware ZAP

Per il malware appena rilevato, ZAP sposta l'intero messaggio, incluso il relativo allegato, per la quarantena di malware. I messaggi vengono spostati indipendentemente dallo stato di lettura della posta. Se si riceve un segnale di malware per un messaggio nel processo di analisi del recapito dinamico, ZAP prenderà una mossa per azione indesiderata sul messaggio. Successivamente, il recapito dinamico consente di terminare il periodo di analisi del recapito e di eseguire l'azione appropriata.

Il malware ZAP è abilitato per impostazione predefinita nel criterio di malware. È possibile disabilitare lo ZAP antimalware utilizzando il parametro *ZapEnabled* nel cmdlet [set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) in PowerShell di Exchange Online o Exchange Online Protection PowerShell. Malware ZAP può anche essere abilitato o disabilitato modificando il criterio di malware nel centro sicurezza e conformità.

### <a name="phish-zap"></a>Phishing ZAP

Per la posta identificata come phishing dopo il recapito, ZAP esegue un'azione in base al criterio di posta indesiderata che copre un utente specifico, indipendentemente dallo stato di lettura della posta. Se l'azione phishing del criterio è impostata su *non* eseguire l'azione (Aggiungi X-header, Modify Subject, No Action), zap non eseguirà alcuna azione per la posta. Se l'azione phishing è impostata su Sposta su posta indesiderata, ZAP sposterà il messaggio nella cartella posta indesiderata della posta in arrivo dell'utente. **Per qualsiasi altra azione phishing (redirect, DELETE, Quarantine) ZAP sposterà il messaggio in quarantena phishing**. Leggere le informazioni seguenti per i requisiti di configurazione e le esclusioni. Per ulteriori informazioni su come [configurare i criteri di filtro posta indesiderata](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) , vedere qui.

Phishing ZAP è abilitato per impostazione predefinita nei criteri di posta indesiderata. Phishing ZAP può essere disattivato utilizzando il parametro *PhishZapEnabled* di [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy), un cmdlet di EOP.

### <a name="spam-zap"></a>Spam ZAP

Per la posta elettronica identificata come posta indesiderata dopo il recapito, ZAP esegue un'azione in base ai criteri di posta indesiderata che riguardano l'utente specifico, solo se il messaggio non è stato letto.  Se l'azione dei criteri di posta indesiderata è impostata su non agire (aggiungere X-header, modificare l'oggetto, nessuna azione), ZAP non intraprendere alcuna azione per la posta. Se l'azione di posta indesiderata è impostata su Sposta su posta indesiderata, ZAP sposterà il messaggio nella cartella posta indesiderata della posta in arrivo dell'utente. **Per qualsiasi altra azione di posta indesiderata (redirect, DELETE, Quarantine), zap sposterà il messaggio in quarantena della posta indesiderata**. Leggere le informazioni seguenti per i requisiti di configurazione e le esclusioni. Per ulteriori informazioni su come [configurare i criteri di filtro posta indesiderata](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) , vedere qui.

Spam ZAP è abilitato per impostazione predefinita nei criteri di posta indesiderata. È possibile disabilitare la posta indesiderata utilizzando il parametro *SpamZapEnabled* del cmdlet [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy) in PowerShell di Exchange Online o Exchange Online Protection PowerShell.

### <a name="phish-and-spam-zap-requirements-exclusions-and-notices"></a>Requisiti, esclusioni e notifiche di phishing e spam ZAP

> [!IMPORTANT]
> il parametro precedente del cmdlet *ZapEnabled* che ha controllato sia phishing che spam ZAP sarà **deprecato il 1 ° febbraio 2020**. Se sono stati scritti script che utilizzano il parametro ZapEnabled, è consigliabile aggiornarli per l'utilizzo di SpamZapEnabled e PhishZapEnabled. Nel periodo di transizione tutti e tre i parametri (ZapEnabled, PhishZapEnabled e SpamZapEnabled) saranno disponibili tramite il cmdlet. Fino a quando non viene impostato in modo esplicito tramite l'interfaccia utente o PowerShell, PhishZapEnabled e SpamZapEnabled visualizzeranno un valore ereditato dal parametro ZapEnabled. Dopo aver impostato i nuovi parametri, non erediterà più dal parametro ZapEnabled. Dopo che è stata deprecata l'impostazione ZapEnabled non avrà alcun effetto sulle proprietà PhishZapEnabled o SpamZapEnabled e ZapEnabled verrà rimosso dall'elenco dei parametri nei cmdlet.

ZAP non sposterà alcun messaggio in quarantena che è in fase di analisi del recapito dinamico o che ha già un verdetto di malware con un allegato sostituito. Se si riceve un segnale di phishing o di posta indesiderata per questi tipi di messaggi e l'azione di criteri di posta indesiderata/phishing è impostata su azione (sposta in posta indesiderata, reindirizzamento, Elimina, quarantena), per impostazione predefinita, ZAP verrà impostato su un'azione "sposta in spazzatura". Affinché ZAP esegua un'azione di "spostamento verso la posta indesiderata" in un messaggio, l'utente deve avere la protezione della posta indesiderata abilitata, con le impostazioni predefinite della posta indesiderata. Per informazioni dettagliate sulle opzioni utente in Outlook, vedere [modificare il livello di protezione del filtro della posta indesiderata](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b) .

## <a name="how-to-see-if-zap-moved-your-message"></a>Come vedere se ZAP ha spostato il messaggio

Per determinare se il messaggio è stato spostato da ZAP, è possibile utilizzare il [rapporto sullo stato di protezione di minacce](view-email-security-reports.md#threat-protection-status-report) o l' [esploratore di minacce (e i rilevamenti in tempo reale)](threat-explorer.md).

## <a name="disable-zap"></a>Disabilitare ZAP

Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Per connettersi a PowerShell di Exchange Online Protection, vedere [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

### <a name="disable-malware-zap"></a>Disabilitare il malware ZAP * *

Il malware ZAP può essere disabilitato tramite il parametro *ZapEnabled* sul cmdlet [set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) in PowerShell di Exchange Online o Exchange Online Protection PowerShell. Malware ZAP può anche essere abilitato o disabilitato modificando il criterio di malware nel centro sicurezza e conformità.

In questo esempio viene disabilitato ZAP nel criterio di filtro antimalware denominato "test".

```Powershell
Set-MalwareFilterPolicy -Identity Test -ZapEnabled $false
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy).

### <a name="disable-phish-zap-and-spam-zap"></a>Disabilitare phishing ZAP e spam ZAP

Per disabilitare phishing e spam ZAP per il tenant O365 o un gruppo di utenti, utilizzare i parametri *PhishZapEnabled* e *SpamZapEnabled* di [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy), un cmdlet EOP.

Nell'esempio seguente, phishing e spam ZAP sono disattivati per un criterio di filtro dei contenuti denominato "test".

```Powershell
Set-HostedContentFilterPolicy -Identity Test -PhishZapEnabled $false -SpamZapEnabled $false
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy).

## <a name="faq"></a>Domande frequenti

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a>Cosa succede se un messaggio legittimo viene spostato nella cartella posta indesiderata?

È consigliabile seguire la procedura di creazione di report normale per i [falsi positivi](../../compliance/prevent-email-from-being-marked-as-spam.md). L'unico motivo per il quale il messaggio verrebbe spostato dalla posta in arrivo alla cartella posta indesiderata sarebbe perché il servizio ha determinato che il messaggio era posta indesiderata o dannoso.

### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a>Che cosa fare se si utilizza la quarantena di Office 365 anziché la cartella posta indesiderata?

ZAP eseguirà un'azione in base alla configurazione delle impostazioni di azione di phishing e di posta indesiderata nel criterio di protezione da posta indesiderata. Per ulteriori informazioni, vedere la pagina relativa a malware, phishing e spam ZAP.

### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a>Cosa succede se si dispone di una regola del flusso di posta personalizzata (blocco/Consenti regola)?

Le regole create dagli amministratori (regole del flusso di posta) o blocca e Consenti hanno la precedenza. Tali messaggi sono esclusi dai criteri di funzionalità in modo che il flusso di posta seguirà l'azione della regola (blocco/Consenti regola).

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a>Cosa succede se un messaggio viene spostato in un'altra cartella (ad esempio, la regola di posta in arrivo)?

ZAP continua a funzionare in questo caso, a meno che il messaggio non sia stato eliminato o sia indesiderato.

## <a name="related-topics"></a>Argomenti correlati

[Protezione dalla posta indesiderata in Office 365](anti-spam-protection.md)

[Bloccare la posta indesiderata utilizzando il filtro di Office 365 al fine di evitare problemi di falsi negativi](reduce-spam-email.md)
