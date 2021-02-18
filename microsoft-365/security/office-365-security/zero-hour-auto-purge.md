---
title: Zero-hour auto purge (ZAP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
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
description: Gli amministratori possono scoprire in che modo zap (zero-hour auto purge) può spostare retroattivamente i messaggi recapitati in una cassetta postale di Exchange Online nella cartella Posta indesiderata o in quarantena che sono retroattivamente trovati come posta indesiderata o phishing.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5fd41cf45ad2a49d74684ae3e20dded5c1b8f034
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287306"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Zero-hour auto purge (ZAP) in Exchange Online

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a>Funzionalità di base di ZAP

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online, ZAP (Zero-Hour Auto Purge) è una funzionalità di protezione della posta elettronica che consente di rilevare e neutralizzare in modo retroattivo i messaggi di phishing, posta indesiderata o malware dannosi già recapitati alle cassette postali di Exchange Online.

ZAP non funziona in ambienti Exchange Online Protection (EOP) autonomi che proteggono le cassette postali di Exchange locali.

## <a name="how-zap-works"></a>Funzionamento di ZAP

Le firme di posta indesiderata e malware vengono aggiornate nel servizio in tempo reale su base giornaliera. Tuttavia, gli utenti possono comunque ricevere messaggi dannosi per una serie di motivi, tra cui se il contenuto viene evaso dopo essere stato recapitato agli utenti. ZAP risolve questo problema monitorando continuamente gli aggiornamenti delle firme di posta indesiderata e malware nel servizio. ZAP può trovare e rimuovere i messaggi già presenti nella cassetta postale di un utente.

L'azione ZAP è facile per l'utente; non vengono avvisati se viene rilevato e spostato un messaggio.

[Gli elenchi di mittenti attendibili,](create-safe-sender-lists-in-office-365.md)le regole del flusso di posta (note anche come regole di trasporto), le regole di Posta in arrivo o filtri aggiuntivi hanno la precedenza su ZAP. Analogamente a quanto accade nel flusso di posta, questo significa che anche se il servizio determina che il messaggio recapitato necessita di ZAP, il messaggio non viene utilizzato a causa della configurazione dei mittenti attendibili. Questo è un altro motivo per cui prestare attenzione alla configurazione dei messaggi per ignorare il filtro.

### <a name="malware-zap"></a>Malware ZAP

Per **i messaggi letti o non** letti che contengono malware dopo il recapito, ZAP messo in quarantena il messaggio che contiene l'allegato malware. Solo gli amministratori possono visualizzare e gestire i messaggi di malware dalla quarantena.

ZaP antimalware è abilitato per impostazione predefinita nei criteri antimalware. Per ulteriori informazioni, vedere [Configurare i criteri antimalware in EOP.](configure-anti-malware-policies.md)

### <a name="phish-zap"></a>Phish ZAP

Per **i** messaggi letti o non letti identificati come phishing dopo il recapito, il risultato zap dipende dall'azione configurata per un verdetto di filtro della posta elettronica di **phishing** nel criterio di protezione da posta indesiderata applicabile. Le azioni del verdetto filtro disponibili per il phishing e i possibili risultati ZAP sono descritte nell'elenco seguente:

- **Aggiungi X-Header**, **antepone l'oggetto al** testo: ZAP non fa alcuna azione sul messaggio.

- **Spostamento del messaggio** nella posta indesiderata : ZAP sposta il messaggio nella cartella Posta indesiderata, purché la regola di posta indesiderata sia abilitata nella cassetta postale (è abilitata per impostazione predefinita). Per ulteriori informazioni, vedere Configurare le impostazioni di posta indesiderata nelle [cassette postali di Exchange Online in Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

- **Reindirizzare il messaggio all'indirizzo di posta** elettronica, **eliminare il messaggio,** **mettere in quarantena** il messaggio.

Per impostazione predefinita, zap phishing è abilitato nei criteri di protezione dalla posta indesiderata e l'azione predefinita per il verdetto del filtro della posta elettronica di **phishing** è **Il** messaggio in quarantena, il che significa che ZAP phishing messo in quarantena il messaggio per impostazione predefinita.

Per ulteriori informazioni sulla configurazione dei verdetti del filtro posta indesiderata, vedere Configurare i criteri di protezione da [posta indesiderata in Microsoft 365.](configure-your-spam-filter-policies.md)

### <a name="spam-zap"></a>ZaP della posta indesiderata

Per **i messaggi** non letti identificati come posta indesiderata dopo il recapito, il  risultato zap dipende dall'azione configurata per il verdetto filtro posta indesiderata nel criterio di protezione da posta indesiderata applicabile. Le azioni del verdetto filtro disponibili per la posta indesiderata e i possibili risultati ZAP sono descritte nell'elenco seguente:

- **Aggiungi X-Header**, **antepone l'oggetto al** testo: ZAP non fa alcuna azione sul messaggio.

- **Spostamento del messaggio** nella posta indesiderata : ZAP sposta il messaggio nella cartella Posta indesiderata, purché la regola di posta indesiderata sia abilitata nella cassetta postale (è abilitata per impostazione predefinita). Per ulteriori informazioni, vedere Configurare le impostazioni di posta indesiderata nelle [cassette postali di Exchange Online in Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

- **Reindirizzare il messaggio all'indirizzo di posta** elettronica, **eliminare il messaggio,** **mettere in quarantena** il messaggio. Gli utenti finali possono visualizzare e gestire i propri messaggi di posta indesiderata in quarantena.

Per impostazione predefinita, zap della posta indesiderata è abilitato  nei criteri di protezione da posta indesiderata e l'azione predefinita per il verdetto del filtro della posta indesiderata è Sposta messaggio nella cartella Posta **indesiderata,** il che significa che zaP della posta indesiderata sposta i messaggi non letti nella cartella Posta indesiderata per impostazione predefinita. 

Per ulteriori informazioni sulla configurazione dei verdetti del filtro posta indesiderata, vedere Configurare i criteri di protezione da [posta indesiderata in Microsoft 365.](configure-your-spam-filter-policies.md)

### <a name="zap-considerations-for-microsoft-defender-for-office-365"></a>Considerazioni zap per Microsoft Defender per Office 365

ZAP non metta in quarantena i [](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) messaggi in corso di recapito dinamico nell'analisi degli allegati sicuri o in cui il filtro antimalware EOP ha già sostituito l'allegato con il **file** di Text.txtmalware. Se viene ricevuto un segnale di phishing o di posta indesiderata per questi tipi di messaggi e il verdetto di filtro nel criterio di protezione da posta indesiderata è impostato per eseguire un'azione sul messaggio (Sposta nella posta indesiderata, Reindirizza, Elimina o Quarantena), ZAP per impostazione predefinita verrà impostata su "Sposta nella posta indesiderata".

## <a name="how-to-see-if-zap-moved-your-message"></a>Come verificare se ZAP ha spostato il messaggio

Per determinare se ZAP ha spostato il messaggio, è possibile utilizzare il rapporto sullo stato di [Threat Protection](view-email-security-reports.md#threat-protection-status-report) o Esplora minacce (e rilevamenti in tempo [reale).](threat-explorer.md) Si noti che, come azione di sistema, ZAP non viene registrato nei registri di controllo delle cassette postali di Exchange.

## <a name="zap-faq"></a>Domande frequenti su ZAP

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>Cosa succede se un messaggio legittimo viene spostato nella cartella Posta indesiderata?

È consigliabile seguire il normale processo di segnalazione [dei falsi positivi.](report-junk-email-messages-to-microsoft.md) L'unico motivo per cui il messaggio verrebbe spostato dalla cartella Posta in arrivo alla cartella Posta indesiderata sarebbe perché il servizio ha determinato che il messaggio era posta indesiderata o dannoso.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>Cosa succede se si utilizza la cartella Quarantena anziché la cartella Posta indesiderata?

ZAP prenderà un'azione su un messaggio in base alla configurazione dei criteri di protezione da posta indesiderata come descritto in precedenza in questo articolo.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>Cosa succede se si utilizzano mittenti attendibili, regole del flusso di posta o elenchi di mittenti consentiti/bloccati?

I mittenti attendibili, le regole del flusso di posta o bloccano e consentono le impostazioni dell'organizzazione hanno la precedenza. Questi messaggi sono esclusi da ZAP perché il servizio sta eseguendo le operazioni configurate per l'operazione. Questo è un altro motivo per cui prestare attenzione alla configurazione dei messaggi per ignorare il filtro.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>Cosa succede se un messaggio viene spostato in un'altra cartella (ad esempio, regole posta in arrivo)?

ZAP funziona comunque finché il messaggio non è stato eliminato o finché l'azione stessa o più forte non è già stata applicata. Ad esempio, se il criterio anti-phishing è impostato in quarantena e il messaggio è già nella posta indesiderata, ZAP farà un'azione per mettere in quarantena il messaggio.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>In che modo ZAP influisce sulle cassette postali in attesa?

ZAP non mettere in quarantena i messaggi dalle cassette postali in attesa. ZAP può spostare i messaggi nella cartella Posta indesiderata in base all'azione configurata per un verdetto di posta indesiderata o phishing nei criteri di protezione da posta indesiderata.

Per ulteriori informazioni sui blocchi in Exchange Online, vedere [In-Place Hold and Litigation Hold in Exchange Online.](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)
