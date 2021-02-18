---
title: Analisi e risposta automatizzate in Microsoft Defender per Office 365
keywords: AIR, autoIR, ATP, automatizzato, indagine, risposta, correzione, minacce, avanzate, minaccia, protezione
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 01/29/2021
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Introduzione all'uso delle funzionalità di analisi e risposta automatizzate in Microsoft Defender per Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b2e359f193f3c8b0502a1995b8e9d515eb03a983
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287690"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Analisi e risposta automatizzate (AIR) in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[Microsoft Defender per Office 365](office-365-atp.md) include potenti funzionalità di analisi e risposta automatizzate (AIR) che consentono di risparmiare tempo e fatica nel team delle operazioni di sicurezza. Quando vengono attivati avvisi, il team delle operazioni di sicurezza deve esaminare, definire le priorità e rispondere a tali avvisi. Tenere il passo con il volume di avvisi in arrivo può essere eccessivo. L'automazione di alcune di queste attività può essere utile.

AIR consente al team delle operazioni di sicurezza di operare in modo più efficiente ed efficace. Le funzionalità AIR includono processi di indagine automatizzati in risposta alle minacce note che esistono oggi. Le azioni correttive appropriate attendono l'approvazione, consentendo al team delle operazioni di sicurezza di rispondere in modo efficace alle minacce rilevate. Con AIR, il team delle operazioni di sicurezza può concentrarsi sulle attività con priorità più alta senza perdere di vista gli avvisi importanti attivati.

In questo articolo viene descritto:

- Il [flusso complessivo di AIR;](#the-overall-flow-of-air)
- [Come ottenere AIR](#how-to-get-air); e
- Autorizzazioni [necessarie per](#required-permissions-to-use-air-capabilities) configurare o utilizzare le funzionalità AIR.
- Modifiche che saranno presto disponibili nel Centro sicurezza

Questo articolo include anche [i passaggi successivi](#next-steps)e risorse per saperne di più.

## <a name="the-overall-flow-of-air"></a>Il flusso complessivo di AIR

Viene attivato un avviso e un playbook sulla sicurezza avvia un'indagine automatizzata, che genera risultati e azioni consigliate. Ecco il flusso generale di AIR, passo dopo passo:

1. Un'indagine automatizzata viene avviata in uno dei modi seguenti:
   - Un [avviso viene attivato da qualcosa di](#which-alert-policies-trigger-automated-investigations) sospetto nella posta elettronica (ad esempio un messaggio, un allegato, un URL o un account utente compromesso). Viene creato un evento imprevisto e viene avviata un'indagine automatizzata; oppure
   - Un analista della [sicurezza avvia un'indagine automatizzata](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) durante l'uso [di Esplora minacce.](threat-explorer.md)
2. Durante l'esecuzione di un'indagine automatizzata, raccoglie i dati relativi al messaggio di posta elettronica in questione e le entità correlate a tale messaggio di posta elettronica. Tali entità possono includere file, URL e destinatari. L'ambito dell'indagine può aumentare quando vengono attivati avvisi nuovi e correlati.
3. Durante e dopo un'indagine automatizzata, i dettagli [e i](air-view-investigation-results.md) risultati sono disponibili per la visualizzazione. I risultati [includono le](air-remediation-actions.md) azioni consigliate che possono essere intraprese per rispondere e correggere eventuali minacce rilevate.
4. Il team delle operazioni di sicurezza esamina i risultati e gli elementi [consigliati](air-view-investigation-results.md)dell'indagine e approva o [rifiuta le azioni correttive.](air-review-approve-pending-completed-actions.md)
5. Quando le azioni di correzione in sospeso vengono approvate (o rifiutate), l'indagine automatizzata viene completata.

In Microsoft Defender per Office 365, nessuna azione di correzione viene eseguita automaticamente. Le azioni di correzione vengono eseguite solo dopo l'approvazione da parte del team di sicurezza dell'organizzazione. Le funzionalità AIR consentono al team delle operazioni di sicurezza di risparmiare tempo identificando le azioni correttive e fornendo i dettagli necessari per prendere una decisione informata.

Durante e dopo ogni indagine automatizzata, il team delle operazioni di sicurezza può:

- [Visualizzare i dettagli relativi a un avviso correlato a un'indagine](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [Visualizzare i dettagli dei risultati di un'indagine](air-view-investigation-results.md#view-details-of-an-investigation)
- [Rivedere e approvare le azioni a seguito di un'indagine](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Per una panoramica più dettagliata, vedere [Funzionamento di AIR.](automated-investigation-response-office.md)

## <a name="how-to-get-air"></a>Come ottenere AIR

Le funzionalità AIR sono incluse in [Microsoft Defender per Office 365,](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2)purché i criteri e gli avvisi siano configurati. Serve aiuto? Seguire le istruzioni in [Protezione dalle minacce](protect-against-threats.md) per configurare o configurare le impostazioni di protezione seguenti:

- [Registrazione di controllo](../../compliance/turn-audit-log-search-on-or-off.md) (deve essere attivata)
- [Criteri antimalware](protect-against-threats.md#part-1---anti-malware-protection)
- [Protezione antiphishing](protect-against-threats.md#part-2---anti-phishing-protection)
- [Protezione dalla posta indesiderata](protect-against-threats.md#part-3---anti-spam-protection)
- [Collegamenti sicuri e allegati sicuri](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)
- [Allegati sicuri per SharePoint, OneDrive e Microsoft Teams](protect-against-threats.md#part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)
- [Eliminazione automatica a zero ore per la posta elettronica.](protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop)

Inoltre, assicurarsi di esaminare i criteri di avviso [dell'organizzazione,](../../compliance/alert-policies.md)in particolare i criteri [predefiniti nella categoria gestione delle minacce.](../../compliance/alert-policies.md#default-alert-policies)

## <a name="which-alert-policies-trigger-automated-investigations"></a>Quali criteri di avviso attivano indagini automatizzate?

Microsoft 365 fornisce molti criteri di avviso incorporati che consentono di identificare l'abuso delle autorizzazioni di amministratore di Exchange, l'attività di malware, potenziali minacce esterne ed interne e i rischi di governance delle informazioni. Diversi dei criteri [di avviso predefiniti](../../compliance/alert-policies.md#default-alert-policies) possono attivare indagini automatizzate. La tabella seguente descrive gli avvisi che attivano le indagini automatizzate, la loro gravità nel Centro sicurezza Microsoft 365 e il modo in cui vengono generati:

|Avviso|Gravità|Modalità di generazione dell'avviso|
|:---|:---|:---|
|È stato rilevato un clic su UN URL potenzialmente dannoso|**High**|Questo avviso viene generato quando si verifica una delle condizioni seguenti: <ul><li>Un utente protetto da [collegamenti sicuri nell'organizzazione](atp-safe-links.md) fa clic su un collegamento dannoso</li><li>Le modifiche al verdetto per gli URL sono identificate da Microsoft Defender per Office 365</li><li>Gli utenti sostituiscono le pagine di avviso per i collegamenti sicuri (in base al criterio [Collegamenti sicuri dell'organizzazione).](set-up-atp-safe-links-policies.md)</li></ul> <p> Per ulteriori informazioni sugli eventi che attivano questo avviso, vedere [Set up Safe Links policies.](set-up-atp-safe-links-policies.md)|
|Un messaggio di posta elettronica viene segnalato da un utente come malware o malware|**Informativo**|Questo avviso viene generato quando gli utenti dell'organizzazione segnalano i messaggi come posta elettronica di phishing utilizzando il componente aggiuntivo Segnala messaggio o Segnala [phishing.](enable-the-report-phish-add-in.md) [](enable-the-report-message-add-in.md)|
|I messaggi di posta elettronica contenenti malware vengono rimossi dopo il recapito|**Informativo**|Questo avviso viene generato quando i messaggi di posta elettronica contenenti malware vengono recapitati alle cassette postali dell'organizzazione. Se si verifica questo evento, Microsoft rimuove i messaggi infetti dalle cassette postali di Exchange Online utilizzando [l'eliminazione automatica zero-hour.](zero-hour-auto-purge.md)|
|I messaggi di posta elettronica contenenti URL di phish vengono rimossi dopo il recapito|**Informativo**|Questo avviso viene generato quando i messaggi contenenti phish vengono recapitati alle cassette postali dell'organizzazione. Se si verifica questo evento, Microsoft rimuove i messaggi infetti dalle cassette postali di Exchange Online utilizzando [l'eliminazione automatica zero-hour.](zero-hour-auto-purge.md)|
|Vengono rilevati modelli di invio di posta elettronica sospetti|**Medium**|Questo avviso viene generato quando un utente dell'organizzazione ha inviato messaggi di posta elettronica sospetti ed è a rischio di essere limitato all'invio di posta elettronica. L'avviso è un avviso anticipato per il comportamento che potrebbe indicare che l'account è compromesso, ma non abbastanza grave da limitare l'utente. <p> Anche se è raro, un avviso generato da questo criterio potrebbe essere un'anomalia. Tuttavia, è una buona idea verificare [se l'account utente è compromesso.](responding-to-a-compromised-email-account.md)|
|A un utente viene limitato l'invio di posta elettronica|**High**|Questo avviso viene generato quando a un utente dell'organizzazione viene limitato l'invio di posta in uscita. Questo avviso in genere si verifica quando un [account di posta elettronica viene compromesso.](responding-to-a-compromised-email-account.md) <p> Per ulteriori informazioni sugli utenti con restrizioni, vedere Rimuovere gli utenti bloccati dal portale [Utenti con restrizioni in Microsoft 365.](removing-user-from-restricted-users-portal-after-spam.md)|
|

> [!TIP]
> Per ulteriori informazioni sui criteri di avviso o per modificare le impostazioni predefinite, vedere Criteri di avviso nel Centro conformità [Microsoft 365.](../../compliance/alert-policies.md)

## <a name="required-permissions-to-use-air-capabilities"></a>Autorizzazioni necessarie per l'utilizzo delle funzionalità AIR

Le autorizzazioni vengono concesse tramite determinati ruoli, ad esempio quelli descritti nella tabella seguente:

|Attività|Ruoli obbligatori|
|---|---|
|Configurare le funzionalità AIR|Uno dei ruoli seguenti: <ul><li>Amministratore globale</li><li>Amministratore della sicurezza</li></ul> <p> Questi ruoli possono essere assegnati in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) o nel Centro sicurezza & [conformità.](permissions-in-the-security-and-compliance-center.md)|
|Avviare un'indagine automatizzata <p> --- o --- <p> Approvare o rifiutare le azioni consigliate|Uno dei ruoli seguenti, assegnato in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) o nel Centro sicurezza & [conformità:](permissions-in-the-security-and-compliance-center.md) <ul><li>Amministratore globale</li><li>Amministratore della sicurezza</li><li>Operatore della sicurezza</li><li>Ruolo con autorizzazioni di lettura per la sicurezza <br> --- e --- </li><li>Ricerca ed eliminazione (questo ruolo viene assegnato solo nel [Centro sicurezza & conformità.](permissions-in-the-security-and-compliance-center.md) Potrebbe essere necessario creare un nuovo gruppo di ruoli e aggiungere il ruolo Di ricerca ed eliminazione a tale nuovo gruppo di ruoli.</li></ul>|

## <a name="required-licenses"></a>Licenze necessarie

[Le licenze di Microsoft Defender per Office 365 Piano 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) devono essere assegnate a:

- Amministratori della sicurezza (inclusi gli amministratori globali)
- Team delle operazioni di sicurezza dell'organizzazione (inclusi i lettori della sicurezza e quelli con il **ruolo Di ricerca ed** eliminazione)
- Utenti finali


## <a name="changes-are-coming-soon-in-your-security-center"></a>Le modifiche saranno presto disponibili nel Centro sicurezza

Se si usano già le funzionalità AIR in Microsoft Defender per Office 365, si stanno per vedere alcune modifiche nel Centro sicurezza [Microsoft 365 migliorato.](../mtp/overview-security-center.md)

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Centro notifiche unificato":::

Il centro sicurezza nuovo e migliorato riunisce le funzionalità AIR in [Microsoft Defender per Office 365](office-365-atp.md) e in Microsoft Defender for [Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) Con questi aggiornamenti e miglioramenti, il team delle operazioni di sicurezza sarà in grado di visualizzare i dettagli sulle indagini automatizzate e sulle azioni di correzione in tutta la posta elettronica, il contenuto di collaborazione, gli account utente e i dispositivi, il tutto in un'unica posizione.

> [!TIP]
> Il nuovo Centro sicurezza Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ) sostituisce i centri seguenti:
>
> - Centro sicurezza e conformità & di Office 365 ( [https://protection.office.com](https://protection.office.com) )
> - Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) )
>
> Oltre alla modifica dell'URL, è stato creato un nuovo aspetto, progettato per offrire al team di sicurezza un'esperienza più semplificata, con visibilità su più rilevamenti di minacce in un'unica posizione.

### <a name="what-to-expect"></a>Cosa aspettarsi

Nella tabella seguente sono elencati i miglioramenti e le modifiche in arrivo in AIR in Microsoft Defender per Office 365.

|Elemento|Cosa cambia?|
|---|---|
|**Pagina Indagini**|La pagina **Delle indagini aggiornata** è più coerente con quella visualizzata in Microsoft Defender per [Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) Vedrai alcune modifiche generali al formato e allo stile in linea con la nuova visualizzazione **Indagini unificate.** Ad esempio, il grafico delle indagini ha un formato più unificato.|
|**Scheda** Utenti|La **scheda Utenti** è ora la scheda **Cassette** postali. I dettagli sugli utenti sono elencati nella **scheda Cassetta** postale.|
|**Scheda Posta** elettronica|La **scheda Posta** elettronica è stata rimossa. visita la **scheda Entità per** visualizzare un elenco di elementi del cluster di posta elettronica e di posta elettronica.|
|**Scheda Entità**|La **scheda Entità** ha uno stile di tabulazione che include una visualizzazione di riepilogo e la possibilità di filtrare in base al tipo di entità. La **scheda Entità** ora include un'opzione **Vai** a ricerca oltre all'opzione Apri **in Esplora** risorse. Ora puoi usare [Esplora](threat-explorer.md) minacce o [la ricerca avanzata](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) per trovare entità e minacce e filtrare i risultati.|
|**Scheda Azioni**|La scheda **Azioni aggiornata** ora include una scheda **Azioni** in sospeso e una **scheda Cronologia** azioni. Le azioni possono essere approvate (o rifiutate) in un riquadro laterale che si apre quando si seleziona un'azione in sospeso.|
|**Scheda Prova**|Una nuova **scheda Evidenza** mostra i risultati chiave dell'entità correlati alle azioni. Le azioni correlate a ogni prova possono essere approvate (o rifiutate) in un riquadro laterale che si apre quando si seleziona un'azione in sospeso.|
|**Centro notifiche**|Il centro **notifiche aggiornato** ( ) riunisce le azioni in sospeso e completate tra posta <https://security.microsoft.com/action-center> elettronica, dispositivi e identità. Per altre informazioni, vedere Centro notifiche. Per altre informazioni, vedere [Il centro notifiche.](../mtp/mtp-action-center.md)|
|**Pagina Eventi imprevisti**|La **pagina Eventi** imprevisti ora correla più indagini per fornire una migliore visione consolidata delle indagini. ([Ulteriori informazioni sugli eventi imprevisti.](../mtp/incidents-overview.md))|
|

## <a name="next-steps"></a>Passaggi successivi

- [Visualizzare i dettagli e i risultati di un'indagine automatizzata](air-view-investigation-results.md#view-details-of-an-investigation)
- [Rivedere e approvare le azioni in sospeso](air-remediation-actions.md)
