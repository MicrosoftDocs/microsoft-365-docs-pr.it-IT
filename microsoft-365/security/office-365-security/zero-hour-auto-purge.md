---
title: Spurgo automatico zero-hour (ZAP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
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
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono sapere in che modo lo ZAP (zero-hour auto Purge) può spostare con effetto retroattivo i messaggi recapitati in una cassetta postale di Exchange Online nella cartella posta indesiderata o in quarantena che sono stati rilevati con effetto retroattivo come spam o phishing.
ms.openlocfilehash: e59d93285dd75a749739b8247c156c19533ce2b1
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845445"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Zero-hour auto Purge (ZAP) in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a>Funzionalità di base di ZAP

In Microsoft 365 organizzazioni con cassette postali in Exchange Online, zero-hour auto Purge (ZAP) è una funzionalità di protezione della posta elettronica che consente di rilevare e neutralizzare in modo retroattivo i messaggi di phishing, posta indesiderata o malware che sono già stati recapitati alle cassette postali di Exchange Online.

ZAP non funziona in ambienti autonomi di Exchange Online Protection (EOP) che proteggono le cassette postali di Exchange locali.

## <a name="how-zap-works"></a>Funzionamento di ZAP

Le firme di posta indesiderata e malware vengono aggiornate quotidianamente nel servizio in tempo reale. Tuttavia, gli utenti possono comunque ricevere messaggi dannosi per una serie di motivi, incluso se il contenuto è armato dopo essere stato recapitato agli utenti. ZAP risolve questo problema monitorando continuamente gli aggiornamenti alle firme di posta indesiderata e malware nel servizio. ZAP è in grado di trovare e rimuovere i messaggi che si trovano già nella cassetta postale di un utente.

L'azione ZAP è senza problemi per l'utente. non vengono informati se un messaggio viene rilevato e spostato.

[Elenchi di mittenti attendibili](create-safe-sender-lists-in-office-365.md), regole del flusso di posta (note anche come regole di trasporto), regole di posta in arrivo o filtri aggiuntivi hanno la precedenza su Zap. Analogamente a quanto avviene nel flusso di posta, ciò significa che anche se il servizio determina che il messaggio recapitato ha bisogno di ZAP, il messaggio non viene attivato a causa della configurazione dei mittenti attendibili. Questo è un altro motivo per cui fare attenzione alla configurazione dei messaggi per ignorare il filtro.

### <a name="malware-zap"></a>Malware ZAP

Per i **messaggi letti o non letti** che contengono malware dopo il recapito, zap mette in quarantena il messaggio che contiene l'allegato di malware. Solo gli amministratori possono visualizzare e gestire i messaggi di malware dalla quarantena.

Il malware ZAP è abilitato per impostazione predefinita nei criteri anti-malware. Per ulteriori informazioni, vedere [Configure anti-malware Policies in EOP](configure-anti-malware-policies.md).

### <a name="phish-zap"></a>Phishing ZAP

Per i **messaggi letti o non letti** identificati come phishing dopo il recapito, l'esito dello ZAP dipende dall'azione configurata per un verdetto di filtraggio della **posta elettronica di phishing** nei criteri di protezione da posta indesiderata applicabili. Le azioni del verdetto di filtraggio disponibili per phishing e i possibili risultati dello ZAP sono descritte nell'elenco seguente:

- **Aggiungi X-header** , **anteporre la riga dell'oggetto al testo** : zap non esegue alcuna azione sul messaggio.

- **Spostare il messaggio in posta indesiderata** : zap sposta il messaggio nella cartella posta indesiderata, purché la regola di posta indesiderata sia abilitata sulla cassetta postale (abilitata per impostazione predefinita). Per ulteriori informazioni, vedere [configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange online in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Reindirizza messaggio all'indirizzo di posta elettronica** , **eliminare** il messaggio, mettere in **quarantena** : zap mette in quarantena il messaggio.

Per impostazione predefinita, phishing ZAP è abilitato nei criteri di protezione dalla posta indesiderata e l'azione predefinita per il verdetto del filtro della **posta elettronica di phishing** è **messaggio in quarantena** , il che significa che phishing ZAP la quarantena del messaggio per impostazione predefinita.

Per ulteriori informazioni sulla configurazione dei verdetti del filtro della posta indesiderata, vedere [Configure anti-spam Policies in Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="spam-zap"></a>Spam ZAP

Per i **messaggi non letti** identificati come posta indesiderata dopo il recapito, l'esito zap dipende dall'azione configurata per il verdetto del filtro della **posta indesiderata** nel criterio di protezione da posta indesiderata applicabile. Le azioni del verdetto di filtraggio disponibili per la posta indesiderata e i possibili risultati dello ZAP sono descritte nell'elenco seguente:

- **Aggiungi X-header** , **anteporre la riga dell'oggetto al testo** : zap non esegue alcuna azione sul messaggio.

- **Spostare il messaggio in posta indesiderata** : zap sposta il messaggio nella cartella posta indesiderata, purché la regola di posta indesiderata sia abilitata sulla cassetta postale (abilitata per impostazione predefinita). Per ulteriori informazioni, vedere [configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange online in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Reindirizza messaggio all'indirizzo di posta elettronica** , **eliminare** il messaggio, mettere in **quarantena** : zap mette in quarantena il messaggio. Gli utenti finali possono visualizzare e gestire i propri messaggi di posta indesiderata in quarantena.

Per impostazione predefinita, lo strumento per la posta indesiderata è abilitato nei criteri di protezione dalla posta indesiderata e l'azione predefinita per il verdetto del filtro della **posta** indesiderata è **Sposta messaggio nella cartella posta indesiderata** , il che significa che la posta indesiderata sposta i messaggi non **letti**

Per ulteriori informazioni sulla configurazione dei verdetti del filtro della posta indesiderata, vedere [Configure anti-spam Policies in Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="zap-considerations-for-microsoft-defender-for-office-365"></a>Considerazioni su ZAP per Microsoft Defender per Office 365

ZAP non consentirà di mettere in quarantena nessun messaggio che sia nel processo di [recapito dinamico](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) nell'analisi degli allegati sicuri o in cui il filtro antimalware di EOP abbia già sostituito l'allegato con il file **Text.txtdi avviso antimalware** . Se si riceve un segnale di phishing o di posta indesiderata per questi tipi di messaggi e il verdetto di filtraggio nei criteri di protezione da posta indesiderata è impostato per eseguire alcune operazioni sul messaggio (spostamento in posta indesiderata, reindirizzamento, eliminazione o quarantena), per impostazione predefinita, il metodo ZAP passerà all'azione "sposta in spazzatura".

## <a name="how-to-see-if-zap-moved-your-message"></a>Come vedere se ZAP ha spostato il messaggio

Per determinare se il messaggio è stato spostato da ZAP, è possibile utilizzare il [rapporto sullo stato di protezione di minacce](view-email-security-reports.md#threat-protection-status-report) o l' [esploratore di minacce (e i rilevamenti in tempo reale)](threat-explorer.md). Si noti che, come azione di sistema, ZAP non è registrato nei registri di controllo delle cassette postali di Exchange.

## <a name="zap-faq"></a>DOMANDE FREQUENTI SU ZAP

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>Cosa succede se un messaggio legittimo viene spostato nella cartella posta indesiderata?

È consigliabile seguire la procedura di creazione di report normale per i [falsi positivi](report-junk-email-messages-to-microsoft.md). L'unico motivo per il quale il messaggio verrebbe spostato dalla posta in arrivo alla cartella posta indesiderata sarebbe perché il servizio ha determinato che il messaggio era posta indesiderata o dannoso.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>Che cosa fare se si utilizza la cartella Quarantine anziché la cartella posta indesiderata?

ZAP eseguirà un'azione su un messaggio in base alla configurazione dei criteri di protezione da posta indesiderata, come descritto in precedenza in questo argomento.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>Cosa succede se si utilizzano mittenti attendibili, regole del flusso di posta o elenchi di mittenti consentiti o bloccati?

I mittenti attendibili, le regole del flusso di posta o blocca e Consenti le impostazioni dell'organizzazione hanno la precedenza. Questi messaggi sono esclusi da ZAP poiché il servizio sta facendo ciò che è stato configurato per eseguire. Questo è un altro motivo per cui fare attenzione alla configurazione dei messaggi per ignorare il filtro.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>Cosa succede se un messaggio viene spostato in un'altra cartella (ad esempio, le regole di posta in arrivo)?

Lo ZAP continua a funzionare fino a quando il messaggio non è stato eliminato oppure finché non è stato ancora applicato lo stesso valore. Ad esempio, se il criterio phishing è impostato per la quarantena e l'utente o l'amministratore ha già scartato il messaggio di posta elettronica, la quarantena eseguirà un'azione per la quarantena del file.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>In che modo ZAP influenza le cassette postali in attesa?

ZAP non consentirà di mettere in quarantena i messaggi dalle cassette postali. ZAP è in grado di spostare i messaggi nella cartella posta indesiderata in base all'azione configurata per una posta indesiderata o di phishing nei criteri di protezione da posta indesiderata.

Per ulteriori informazioni sulle esenzioni in Exchange Online, vedere [blocco sul posto e conservazione per controversia legale in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).
