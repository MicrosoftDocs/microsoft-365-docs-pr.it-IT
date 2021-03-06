---
title: Eliminazione automatica di zero ore in Microsoft Defender per Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 06/22/2021
audience: Admin
ms.topic: conceptual
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
description: Zero-hour auto purge (ZAP) sposta retroattivamente i messaggi recapitati in una cassetta postale di Exchange Online nella cartella Posta indesiderata o in quarantena che vengono trovati come posta indesiderata o phishing dopo il recapito.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fdfc39b8bd18d33f95b85028e3661008a17a1209
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083501"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Eliminazione automatica a zero ore (ZAP) in Exchange Online

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="zero-hour-auto-purge-zap-basics"></a>Nozioni di base su ZAP (Zero-Hour Auto Purge)

Nelle organizzazioni Microsoft 365 con cassette postali in Exchange Online, l'eliminazione automatica a zero ore (ZAP) è una funzionalità di protezione della posta elettronica che rileva e neutralizza retroattivamente i messaggi di phishing, posta indesiderata o malware dannosi già recapitati alle cassette postali di Exchange Online.

ZAP non funziona in ambienti di Exchange Online Protection (EOP) autonomi che proteggono le cassette postali Exchange locali.

## <a name="how-zap-works"></a>Funzionamento di ZAP

Le firme di posta indesiderata e malware vengono aggiornate quotidianamente nel servizio in tempo reale. Tuttavia, gli utenti possono comunque ricevere messaggi dannosi per diversi motivi, incluso se il contenuto viene utilizzato come arma dopo essere stati recapitati agli utenti. ZAP risolve questo problema monitorando continuamente gli aggiornamenti delle firme di posta indesiderata e malware nel servizio. ZAP può trovare e rimuovere i messaggi già presenti nella cassetta postale di un utente.

L'azione ZAP è facile per l'utente; non vengono avvisati se viene rilevato e spostato un messaggio.

[Cassaforte mittenti,](create-safe-sender-lists-in-office-365.md)regole del flusso di posta (note anche come regole di trasporto), regole di Posta in arrivo o filtri aggiuntivi hanno la precedenza su ZAP. Analogamente a quanto accade nel flusso di posta, questo significa che anche se il servizio determina che il messaggio recapitato necessita di ZAP, il messaggio non viene utilizzato a causa della configurazione dei mittenti attendibili. Questo è un altro motivo per cui prestare attenzione alla configurazione dei messaggi per ignorare il filtro.

### <a name="zero-hour-auto-purge-zap-for-malware"></a>Eliminazione automatica a zero ore (ZAP) per malware

Per **i messaggi letti o non** letti che contengono malware dopo il recapito, ZAP metta in quarantena il messaggio contenente l'allegato di malware. Solo gli amministratori possono visualizzare e gestire i messaggi di malware dalla quarantena.

ZAP per il malware è abilitato per impostazione predefinita nei criteri antimalware. Per ulteriori informazioni, vedere [Configure anti-malware policies in EOP.](configure-anti-malware-policies.md)

### <a name="zero-hour-auto-purge-zap-for-phishing"></a>Eliminazione automatica a zero ore (ZAP) per il phishing

Per **i** messaggi letti o non letti identificati come phishing dopo il recapito, il risultato zap dipende dall'azione configurata per un verdetto di filtro della posta elettronica di **phishing** nel criterio di protezione da posta indesiderata applicabile. Le azioni di filtro disponibili per il phishing e i possibili risultati zap sono descritte nell'elenco seguente:

- **Add X-Header**, **Prepend subject line with text**, Redirect message to email **address**, **Delete message**: ZAP takes no action on the message.

- **Move message to Junk Email**: ZAP sposta il messaggio nella cartella Posta indesiderata, purché la regola di posta indesiderata sia abilitata nella cassetta postale (è abilitata per impostazione predefinita). Per ulteriori informazioni, vedere [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Messaggio in quarantena**: ZAP messo in quarantena il messaggio.

Per impostazione predefinita, ZAP per il phishing è abilitato nei  criteri di protezione da posta indesiderata e l'azione predefinita per il verdetto Filtro posta elettronica di phishing è **Messaggio** di quarantena, il che significa che ZAP per il phishing quarantena il messaggio per impostazione predefinita.

Per ulteriori informazioni sulla configurazione dei verdetti di filtro della posta indesiderata, vedere [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="zero-hour-auto-purge-zap-for-high-confidence-phishing"></a>Eliminazione automatica a zero ore (ZAP) per phishing ad alta probabilità

Per **i messaggi letti o non** letti identificati come phishing ad alta probabilità dopo il recapito, ZAP metta in quarantena il messaggio. Solo gli amministratori possono visualizzare e gestire i messaggi di phish ad alta probabilità dalla quarantena.

ZAP per il phish ad alta probabilità è abilitato per impostazione predefinita. Per ulteriori informazioni, vedere [Secure by Default in Office 365](secure-by-default.md).

### <a name="zero-hour-auto-purge-zap-for-spam"></a>Eliminazione automatica a zero ore (ZAP) per la posta indesiderata

Per **i messaggi** non letti identificati come posta indesiderata dopo il recapito, il  risultato zap dipende dall'azione configurata per il verdetto filtro posta indesiderata nel criterio di protezione da posta indesiderata applicabile. Le azioni di filtro disponibili per la posta indesiderata e i possibili risultati zap sono descritte nell'elenco seguente:

- **Add X-Header**, **Prepend subject line with text**, Redirect message to email **address**, **Delete message**: ZAP takes no action on the message.

- **Move message to Junk Email**: ZAP sposta il messaggio nella cartella Posta indesiderata, purché la regola di posta indesiderata sia abilitata nella cassetta postale (è abilitata per impostazione predefinita). Per ulteriori informazioni, vedere [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Messaggio in quarantena**: ZAP messo in quarantena il messaggio. Gli utenti finali possono visualizzare e gestire i propri messaggi di posta indesiderata in quarantena.

Per impostazione predefinita, zap di posta indesiderata è abilitato  nei criteri di protezione da posta indesiderata e l'azione predefinita per il verdetto filtro posta indesiderata è Sposta il messaggio nella cartella Posta indesiderata **,** il che significa che zaP di posta indesiderata sposta i messaggi non letti nella cartella Posta indesiderata per impostazione predefinita. 

Per ulteriori informazioni sulla configurazione dei verdetti di filtro della posta indesiderata, vedere [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="zero-hour-auto-purge-zap-considerations-for-microsoft-defender-for-office-365"></a>Considerazioni sull'eliminazione automatica di zero ore (ZAP) per Microsoft Defender per Office 365

ZAP non metta in quarantena i [](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) messaggi in corso di recapito dinamico nell'analisi degli allegati di Cassaforte o in cui il filtro antimalware EOP ha già sostituito l'allegato con il **file** di Text.txtavviso di malware. Se viene ricevuto un segnale di phishing o di posta indesiderata per questi tipi di messaggi e il verdetto di filtro nel criterio di protezione da posta indesiderata è impostato per eseguire un'azione sul messaggio (Sposta nella posta indesiderata, Reindirizza, Elimina o Quarantena), ZAP avrà per impostazione predefinita un'azione "Sposta nella posta indesiderata".

## <a name="how-to-see-if-zap-moved-your-message"></a>Come verificare se ZAP ha spostato il messaggio

Per determinare se ZAP ha spostato il messaggio, puoi usare il rapporto Stato di [Threat Protection](view-email-security-reports.md#threat-protection-status-report) o Threat Explorer (e i rilevamenti in tempo [reale).](threat-explorer.md) Si noti che, come azione di sistema, ZAP non viene registrato nei registri di controllo Exchange cassetta postale.

## <a name="zero-hour-auto-purge-zap-faq"></a>Domande frequenti sull'eliminazione automatica a zero ore (ZAP)

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>Cosa succede se un messaggio legittimo viene spostato nella cartella Posta indesiderata?

È consigliabile seguire il normale processo di segnalazione [per i falsi positivi.](report-junk-email-messages-to-microsoft.md) L'unico motivo per cui il messaggio verrebbe spostato dalla posta in arrivo alla cartella Posta indesiderata sarebbe perché il servizio ha determinato che il messaggio era posta indesiderata o dannoso.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>Cosa succede se si utilizza la cartella Quarantena anziché la cartella Posta indesiderata?

ZAP verrà eseguita su un messaggio in base alla configurazione dei criteri di protezione da posta indesiderata, come descritto in precedenza in questo articolo.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>Cosa succede se si utilizzano mittenti attendibili, regole del flusso di posta o elenchi di mittenti consentiti/bloccati?

Cassaforte mittenti, regole del flusso di posta o bloccare e consentire le impostazioni dell'organizzazione hanno la precedenza. Questi messaggi sono esclusi da ZAP poiché il servizio sta eseguendo le operazioni che è stato configurato per l'operazione. Questo è un altro motivo per cui prestare attenzione alla configurazione dei messaggi per ignorare il filtro.

### <a name="what-are-the-licensing-requirements-for-zero-hour-auto-purge-zap-to-work"></a>Quali sono i requisiti di licenza per l'eliminazione automatica a zero ore (ZAP) per funzionare?

Non esistono limitazioni per le licenze. ZAP funziona su tutte le cassette postali ospitate Exchange online. ZAP non funziona in ambienti di Exchange Online Protection (EOP) autonomi che proteggono le cassette postali Exchange locali.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>Cosa succede se un messaggio viene spostato in un'altra cartella (ad esempio, regole posta in arrivo)?

L'eliminazione automatica a zero ore continua a funzionare finché il messaggio non è stato eliminato o finché l'azione stessa o più forte non è già stata applicata. Ad esempio, se il criterio anti-phishing è impostato sulla quarantena e il messaggio è già nella posta indesiderata, ZAP farà un'azione per mettere in quarantena il messaggio.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>In che modo ZAP influisce sulle cassette postali in attesa?

L'eliminazione automatica di zero ore mettere in quarantena i messaggi dalle cassette postali in attesa. ZAP può spostare i messaggi nella cartella Posta indesiderata in base all'azione configurata per un verdetto di posta indesiderata o phishing nei criteri di protezione da posta indesiderata.

Per ulteriori informazioni sui blocchi in Exchange Online, vedere Blocco sul posto e [conservazione per controversia legale in Exchange Online](/Exchange/security-and-compliance/in-place-and-litigation-holds).
