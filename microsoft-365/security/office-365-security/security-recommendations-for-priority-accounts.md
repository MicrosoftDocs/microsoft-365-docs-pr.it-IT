---
title: Suggerimenti per la sicurezza per gli account prioritari in Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni su come elevare le impostazioni di sicurezza e utilizzare i report, gli avvisi e le indagini per gli account prioritari nelle organizzazioni Microsoft 365.
ms.openlocfilehash: 9788131ea881a1cb3c36a60dfaac01ed5daf0901
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769246"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a>Suggerimenti per la sicurezza per gli account prioritari in Microsoft 365

Che cosa fare se si riceve un messaggio urgente da un dirigente dell'organizzazione che ha chiesto di fare qualcosa? Lo faresti? La maggior parte delle persone si conformerà alla richiesta.

Per gli aggressori, gli attacchi di phishing comuni che eseguono il cast di una rete casuale per ottenere le credenziali di utenti casuali o sconosciuti sono inefficienti. D'altra parte, attacchi di _phishing_ o _caccia alle balene_ che puntano gli utenti in posizioni di potere o autorità sono molto più gratificanti per gli aggressori. Se questi account di priorità sono compromessi, l'utente malintenzionato potrebbe accedere agli account con le funzionalità di amministratore, finanziarie, di prodotto o persino di accesso fisico all'interno dell'organizzazione.

Microsoft 365 e Microsoft Defender per Office 365 contengono diverse funzionalità che consentono di fornire ulteriori livelli di sicurezza per gli account prioritari. Le funzionalità disponibili e come utilizzarle sono descritte in questo articolo.

![Riepilogo dei suggerimenti per la sicurezza in formato icona](../../media/security-recommendations-for-priority-users.png)

## <a name="increase-sign-in-security-for-priority-accounts"></a>Aumentare la sicurezza dell'accesso per gli account prioritari

Gli account prioritari richiedono una maggiore sicurezza per l'accesso. È possibile aumentare la propria sicurezza di accesso richiedendo l'autenticazione a più fattori (AMF) e disabilitando i protocolli di autenticazione legacy.

Per istruzioni, vedere [passaggio 1. Aumentare la sicurezza dell'accesso per i dipendenti remoti con AMF](https://docs.microsoft.com/microsoft-365/solutions/empower-people-to-work-remotely-secure-sign-in). Anche se in questo articolo si parla di Worker remoti, gli stessi concetti si applicano agli utenti prioritari.

**Note**:

- L'autenticazione di base è in fase di divenire obsoleta in Exchange Online per i servizi Web Exchange (EWS), Exchange ActiveSync, POP3, IMAP4 e Remote PowerShell. Per informazioni dettagliate, vedere questo [post di Blog](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/).

- È possibile utilizzare i [criteri di autenticazione](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) e [le regole di accesso client](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) in Exchange Online per bloccare l'autenticazione di base e i protocolli di autenticazione legacy come POP3, IMAP4 e SMTP autenticato.

- È possibile disabilitare l'accesso POP3 e IMAP4 alle singole cassette postali. È possibile disabilitare l'autenticazione SMTP a livello di organizzazione e abilitarla su cassette postali specifiche che lo richiedono. Per istruzioni, vedere gli argomenti seguenti:
  - [Abilitazione o disabilitazione dell'accesso POP3 o IMAP4 per un utente](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [Abilitazione o disabilitazione dell'invio SMTP del client autenticato (AUTH SMTP)](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a>Utilizzo di criteri di sicurezza preimpostati rigorosi per gli account prioritari

Gli utenti prioritari richiedono azioni più rigorose per le diverse protezioni disponibili in Exchange Online Protection (EOP) e Defender per Office 365.

Ad esempio, invece di inviare messaggi che sono stati classificati come posta indesiderata nella cartella posta indesiderata, è consigliabile mettere in quarantena gli stessi messaggi se destinati agli account prioritari.

È possibile implementare questo approccio rigoroso per gli account di priorità utilizzando il profilo Strict nei criteri di sicurezza preimpostati.

I criteri di sicurezza preimpostati rappresentano una posizione comoda e centrale per applicare le impostazioni di criteri rigorose consigliate per tutte le protezioni in EOP e Defender per Office 365. Per ulteriori informazioni, vedere [criteri di sicurezza preimpostati in EOP e Microsoft Defender per Office 365](preset-security-policies.md).

Per informazioni dettagliate sul modo in cui le impostazioni dei criteri rigorose differiscono dalle impostazioni dei criteri predefiniti e standard, vedere [Recommended Settings for EOP e Microsoft Defender for Office 365 Security](recommended-settings-for-eop-and-office365-atp.md).

## <a name="apply-user-tags-to-priority-accounts"></a>Applicazione di tag utente agli account prioritari

I tag utente in Microsoft Defender per Office 365 piano 2 (come parte di Microsoft 365 E5 o un abbonamento a un componente aggiuntivo) sono un modo per identificare e classificare rapidamente utenti o gruppi di utenti specifici nei report e nelle indagini sugli incidenti.

Gli **account prioritari** sono un tipo di tag utente incorporato (noto come _Tag System_) che è possibile utilizzare per identificare gli incidenti e gli avvisi che coinvolgono gli account prioritari. Per ulteriori informazioni sugli **account di priorità**, vedere [Manage and monitor Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).

È inoltre possibile creare tag personalizzati per identificare e classificare ulteriormente gli account prioritari. Per ulteriori informazioni, vedere [tag utente](user-tags.md). Tenere presente che è possibile gestire gli **account prioritari** (tag di sistema) nella stessa interfaccia dei tag utente personalizzati.

## <a name="monitor-priority-accounts-in-alerts-reports-and-detections"></a>Monitorare gli account prioritari in avvisi, rapporti e rilevamenti

Dopo aver protetto e taggato gli utenti prioritari, è possibile utilizzare i report, gli avvisi e le indagini disponibili in EOP e Defender per Office 365 per identificare rapidamente gli incidenti o i rilevamenti che coinvolgono gli account prioritari. Le funzionalità che supportano i tag utente sono descritte nella tabella seguente.

<br>

****

|Funzionalità|Descrizione|
|---|---|
|Avvisi|I tag utente degli utenti coinvolti sono visibili e disponibili come filtri nella pagina **Visualizza avvisi** nel centro sicurezza & conformità. Per ulteriori informazioni, vedere [visualizzazione degli avvisi](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#viewing-alerts).|
|Esplora minacce <p> Rilevamenti in tempo reale|In **Threat Explorer** (Microsoft Defender per Office 365 piano 2) o **rilevamenti in tempo reale** (microsoft Defender per Office 365 piano 1), i tag utente sono visibili nella visualizzazione griglia di posta elettronica e nel riquadro a comparsa dettagli posta elettronica. I tag utente sono inoltre disponibili come proprietà filtrabile. Per ulteriori informazioni, vedere  [tag in Threat Explorer](threat-explorer.md#tags-in-threat-explorer).|
|Visualizzazioni campagna|I tag utente sono una delle numerose proprietà filtrabili nelle visualizzazioni della campagna in Microsoft Defender per Office 365 piano 2. Per ulteriori informazioni, vedere [Campaign views](campaigns.md).|
|Report dello stato di protezione dalle minacce|In quasi tutte le visualizzazioni e le tabelle dei dettagli nel **rapporto sullo stato di protezione di minacce** è possibile filtrare i risultati in base agli **account prioritari**. Per ulteriori informazioni, vedere [rapporto sullo stato della protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report).|
|Problemi di posta elettronica per il report account prioritari|I **problemi di posta elettronica per il rapporto account prioritari** nell'interfaccia di amministrazione di Exchange (EAC) contengono informazioni sui messaggi non recapitati e ritardati per gli **account prioritari**. Per ulteriori informazioni, vedere [problemi relativi alla posta elettronica per il rapporto account prioritari](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).|
|

## <a name="see-also"></a>Vedere anche

[Annuncio della protezione degli account prioritari in Microsoft Defender per Office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
