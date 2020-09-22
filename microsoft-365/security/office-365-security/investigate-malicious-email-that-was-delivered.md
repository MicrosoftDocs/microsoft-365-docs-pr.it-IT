---
title: Esaminare la posta elettronica dannosa che è stata recapitata in Office 365, trovare e analizzare messaggi di posta elettronica
keywords: TIMailData-inline, incidenti di sicurezza, incidenti, ATP PowerShell, malware per la posta elettronica, utenti compromessi, phishing di posta elettronica, malware per la posta elettronica, lettura intestazioni di posta, intestazioni di lettura, intestazioni di posta elettronica aperte, azioni speciali
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 07/09/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: Informazioni su come utilizzare le funzionalità di analisi e risposta alle minacce per individuare e studiare messaggi di posta elettronica dannosi.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 120cc32a2736858a0f0d99ab37f1d51c70a6071c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201914"
---
# <a name="investigate-malicious-email-that-was-delivered-in-office-365"></a>Esaminare la posta elettronica dannosa che è stata recapitata in Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Office 365 Advanced Threat Protection](office-365-atp.md) consente di analizzare le attività che inseriscono i rischi per l'organizzazione e di intervenire per proteggere l'organizzazione. Ad esempio, se si fa parte del team di sicurezza dell'organizzazione, è possibile trovare e analizzare i messaggi di posta elettronica sospetti che sono stati recapitati. A tale scopo, è possibile utilizzare [Esplora minacce (o rilevamenti in tempo reale)](threat-explorer.md).

> [!NOTE]
> Passare [all'articolo relativo](remediate-malicious-email-delivered-office-365.md)alla correzione.

## <a name="before-you-begin"></a>Informazioni preliminari

Verificare che vengano soddisfatti i seguenti requisiti:

- L'organizzazione dispone di [Office 365 Advanced Threat Protection](office-365-atp.md) e le [licenze vengono assegnate agli utenti](../../admin/manage/assign-licenses-to-users.md).

- la [registrazione di controllo](../../compliance/turn-audit-log-search-on-or-off.md) è attivata per l'organizzazione.

- L'organizzazione dispone di criteri definiti per la protezione da posta indesiderata, anti-malware, anti-phishing e così via. Vedere [protezione dalle minacce in Office 365](protect-against-threats.md).

- Si è un amministratore globale oppure è stato assegnato il ruolo di amministratore della sicurezza o di ricerca ed eliminazione nel centro sicurezza e &amp; conformità. Vedere [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md). Per alcune azioni, è necessario disporre anche di un nuovo ruolo di anteprima assegnato.

### <a name="preview-role-permissions"></a>Autorizzazioni per il ruolo di anteprima

Per eseguire determinate azioni, ad esempio la visualizzazione delle intestazioni dei messaggi o il download del contenuto del messaggio di posta elettronica, è necessario un nuovo ruolo denominato *Anteprima* aggiunto a un altro gruppo di ruoli appropriato. La tabella seguente consente di chiarire i ruoli e le autorizzazioni necessari.

****

|Attività|Gruppo di ruolo|Ruolo di anteprima necessario?|
|---|---|---|
|Utilizzo di Esplora minacce (e rilevamenti in tempo reale) per l'analisi delle minacce |Amministratore globale <br> Amministratore della sicurezza <br> Ruolo con autorizzazioni di lettura per la sicurezza|No|
|Utilizzare Esplora minacce (e rilevamenti in tempo reale) per visualizzare le intestazioni dei messaggi di posta elettronica così come l'anteprima e il download dei messaggi di posta elettronica in quarantena|Amministratore globale <br> Amministratore della sicurezza <br>Ruolo con autorizzazioni di lettura per la sicurezza|No|
|Utilizzare Esplora minacce per visualizzare le intestazioni e scaricare i messaggi di posta elettronica recapitati alle cassette postali|Amministratore globale <br>Amministratore della sicurezza <br> Ruolo con autorizzazioni di lettura per la sicurezza <br> Anteprima|Sì|
|

> [!NOTE]
> L' *Anteprima* è un ruolo e non un gruppo di ruoli. il ruolo di anteprima deve essere aggiunto a un gruppo di ruoli esistente per Office 365. Al ruolo di amministratore globale viene assegnato l'interfaccia di amministrazione di Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ) e i ruoli amministratore sicurezza e lettore di sicurezza sono assegnati nel centro sicurezza & Compliance ( [https://protection.office.com](https://protection.office.com) ). Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="find-suspicious-email-that-was-delivered"></a>Trovare messaggi di posta elettronica sospetti recapitati

Threat Explorer è un potente report che può servire a molteplici scopi, ad esempio la ricerca e l'eliminazione dei messaggi, l'identificazione dell'indirizzo IP di un mittente di posta elettronica dannoso o l'avvio di un incidente per ulteriori indagini. La procedura seguente si concentra sull'utilizzo di Esplora risorse per individuare ed eliminare messaggi di posta elettronica dannosi dalle cassette postali del destinatario.

> [!NOTE]
> Le ricerche predefinite in Esplora risorse non includono attualmente gli elementi zapping.  Questo vale per tutte le visualizzazioni, ad esempio le visualizzazioni di malware o phishing. Per includere gli elementi zapped, è necessario aggiungere un'azione di recapito ' impostato su Includi ' rimosso da ZAP '. Se si includono tutte le opzioni, verranno visualizzati tutti i risultati dell'azione di recapito, compresi gli elementi zapped.

1. **Passare a Esplora minacce**: accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account aziendale o dell'Istituto di istruzione per Office 365. Questo porta al centro sicurezza e &amp; conformità.

2. Nella barra di avvio veloce di spostamento a sinistra, scegliere **gestione minacce** \> **Explorer**.

    ![Explorer con campi azione di recapito e posizione di recapito.](../../media/ThreatExFields.PNG)

    È possibile notare la nuova colonna **azioni speciali** . Questa funzionalità ha lo scopo di informare gli amministratori sull'esito dell'elaborazione di un messaggio di posta elettronica. È possibile accedere alla colonna **azioni speciali** nello stesso luogo in cui si trova l' **operazione di recapito** e il **percorso di recapito**. Le azioni speciali potrebbero essere aggiornate alla fine della sequenza temporale della posta elettronica di Threat Explorer, che è una nuova funzionalità che consente di migliorare l'esperienza di ricerca per gli amministratori.

3. **Visualizzazioni in Esplora minacce**: scegliere **tutti i messaggi di posta elettronica**dal menu **Visualizza** .

    ![Menu Visualizza Esplora minacce e posta elettronica-malware, phishing, invii e tutte le opzioni di posta elettronica, anche contenuto-malware.](../../media/tp-InvestigateMalEmail-viewmenu.png)

    La visualizzazione *malware* è attualmente l'impostazione predefinita e acquisisce i messaggi di posta elettronica in cui viene rilevata una minaccia di malware. La visualizzazione *phishing* funziona nello stesso modo, per phishing.

    Tuttavia, *tutti* i messaggi di posta elettronica visualizzano ogni messaggio ricevuto dall'organizzazione, se le minacce sono state rilevate o meno. Come si può immaginare, si tratta di un sacco di dati, che è il motivo per cui questa visualizzazione Mostra un segnaposto che richiede l'applicazione di un filtro. Questa visualizzazione è disponibile solo per i clienti ATP P2.

    Visualizzazione *invii* Visualizza tutti i messaggi inviati dall'amministratore o dall'utente che sono stati segnalati a Microsoft.

4. **Ricerca e filtro in Esplora minacce**: i filtri vengono visualizzati nella parte superiore della pagina nella barra di ricerca per consentire agli amministratori di eseguire le proprie indagini. Si noti che è possibile applicare più filtri contemporaneamente e che più valori separati da virgola sono stati aggiunti a un filtro per limitare la ricerca. Attenzione:

    - I filtri eseguono una corrispondenza esatta per la maggior parte delle condizioni del filtro.
    - Il filtro soggetto utilizza una query CONTAINs.
    - I filtri URL funzionano con o senza protocolli (es. https).
    - Il dominio URL, il percorso URL e i filtri per il dominio e il percorso URL non richiedono il filtro di un protocollo.
    - È necessario fare clic sull'icona di aggiornamento ogni volta che si modificano i valori del filtro per ottenere i risultati rilevanti.

5. **Filtri avanzati**: con questi filtri è possibile creare query complesse e filtrare il set di dati. Se si fa clic su *filtri avanzati* , verrà aperto un riquadro a comparsa con opzioni.

   Il filtro avanzato è una grande aggiunta alle funzionalità di ricerca. **Non** è stato introdotto un filtro booleano nel dominio del *destinatario*, del *mittente* e del *mittente* per consentire agli amministratori di eseguire indagini escludendo i valori. Questa opzione viene visualizzata sotto il parametro Selection *contiene None of*. **Non** consente agli amministratori di escludere le cassette postali di avviso, le cassette postali di risposta predefinite dalle proprie indagini ed è utile per i casi in cui gli amministratori cercano un oggetto specifico (Subject = "attention") in cui il destinatario può essere impostato su *none de defaultMail \@ contoso.com*. Si tratta di una ricerca di valore esatta.

   ![I destinatari-' contiene nessuno ' del filtro avanzato.](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   Il *filtraggio per ore* consentirà di eseguire il drill-down rapido del team di sicurezza dell'organizzazione. La durata di tempo consentita più breve è di 30 minuti. Se è possibile restringere l'azione sospetta tramite la tempistica (ad esempio, è successo 3 ore fa), questo limiterà il contesto e consentirà di individuare il problema.

   ![L'opzione filtro per ore per limitare la quantità di team di sicurezza dei dati deve essere elaborata e la cui durata più breve è di 30 minuti.](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. **Campi in Esplora minacce**: Esplora minacce espone molte più informazioni di posta elettronica correlate alla sicurezza, ad esempio l' *azione di recapito*, la *posizione di recapito*, l' *azione speciale*, la *direzionalità*, le *sostituzioni*e la *minaccia URL*. Consente inoltre al team di sicurezza dell'organizzazione di analizzare con maggiore certezza.

    *Azione di recapito* è l'azione intrapresa su un messaggio di posta elettronica a causa di criteri o rilevamenti esistenti. Ecco le possibili azioni che un messaggio di posta elettronica può eseguire:

    - **Recapitato** : la posta elettronica è stata recapitata alla posta in arrivo o alla cartella di un utente e l'utente può accedervi direttamente.
    - Posta **indesiderata (** recapitata a junk) – la e-mail è stata inviata alla cartella posta indesiderata o alla cartella eliminata dell'utente e l'utente ha accesso ai messaggi di posta elettronica nella cartella posta indesiderata o eliminato.
    - **Bloccato** : tutti i messaggi di posta elettronica in quarantena, che hanno avuto esito negativo o sono stati eliminati. (Questo è completamente inaccessibile dall'utente).
    - **Sostituito** : tutti i messaggi di posta elettronica in cui gli allegati dannosi sono stati sostituiti dai file. txt che lo stato

    **Percorso di recapito**: il filtro percorso di recapito è disponibile per aiutare gli amministratori a capire dove si è conclusa la posta dannosa sospetta e quali azioni sono state intraprese su di esso. I dati risultanti possono essere esportati in un foglio di calcolo. I possibili percorsi di recapito sono:

    - **Posta in arrivo o cartella** : l'indirizzo di posta elettronica si trova nella cartella posta in arrivo o in una specifica, in base alle regole di posta elettronica.
    - **On-Prem o External** -la cassetta postale non esiste nel cloud ma è in locale.
    - **Cartella posta indesiderata** : la posta elettronica si trova nella cartella della cassetta postale di un utente.
    - **Cartella Posta eliminata** – l'e-mail si trova nella cartella degli elementi eliminati di un utente.
    - **Quarantine** : la posta elettronica in quarantena e non nella cassetta postale di un utente.
    - **Failed** : la posta elettronica non è riuscita a raggiungere la cassetta postale.
    - **Eliminato** : il messaggio di posta elettronica è stato perso da qualche parte nel flusso di posta.

    **Direzionalità**: questa opzione consente al team di operazioni di sicurezza di filtrare in base alla ' direzione ' da cui proviene un messaggio o che è in corso. I valori di direzionalità sono in *ingresso* *, in uscita e* *intra-org* (corrispondente alla posta proveniente dall'esterno dell'organizzazione, che viene inviata dall'organizzazione o che viene inviata internamente all'org, rispettivamente). Queste informazioni consentono ai team di operazioni di sicurezza di spoofing e rappresentazione a campione, in quanto mancata corrispondenza tra il valore di direzionalità (es. In *ingresso*), e il dominio del mittente (che *sembra* essere un dominio interno) sarà evidente! Il valore di direzionalità è separato e può essere diverso da, la traccia dei messaggi. I risultati possono essere esportati in foglio di calcolo.

    **Sostituzioni**: questo filtro prende le informazioni visualizzate nella scheda Dettagli della posta e la utilizza per esporre i criteri dell'organizzazione, o degli utenti, per consentire e bloccare i messaggi di posta *elettronica.* La cosa più importante di questo filtro è che aiuta il team di sicurezza dell'organizzazione a vedere quanti messaggi di posta elettronica sospetti sono stati recapitati a causa della configurazione. In questo modo è possibile modificare le possibilità e i blocchi in base alle esigenze. Questo set di risultati di questo filtro può essere esportato in un foglio di calcolo.

    ****

    |Sostituzioni di Esplora minacce|Cosa significano|
    |---|---|
    |Consentito dai criteri org|La posta elettronica è stata consentita nella cassetta postale come indicato dal criterio dell'organizzazione.|
    |Bloccati dai criteri org|La posta elettronica è stata bloccata dal recapito alla cassetta postale, come indicato dal criterio dell'organizzazione.|
    |Estensione di file bloccata da criteri org|Il file è stato bloccato dal recapito alla cassetta postale, come indicato dal criterio dell'organizzazione.|
    |Consentito dai criteri utente|La posta elettronica è stata consentita nella cassetta postale come indicato dal criterio utente.|
    |Bloccati dai criteri utente|La posta elettronica è stata bloccata dal recapito alla cassetta postale, come indicato dal criterio utente.|
    |

    **Threat URL**: il campo di rischio URL è stato incluso nella scheda *Dettagli* di un messaggio di posta elettronica per indicare la minaccia presentata da un URL. Le minacce presentate da un URL possono includere *malware*, *phishing*o *posta indesiderata*e un URL *senza* minacce direbbe *nessuno* nella sezione minacce.

7. **Visualizzazione sequenza temporale della posta elettronica**: il team delle operazioni di sicurezza potrebbe essere necessario immergersi nei dettagli della posta elettronica per approfondire ulteriormente. La sequenza temporale della posta elettronica consente agli amministratori di visualizzare le azioni eseguite su un messaggio di posta elettronica dal recapito al post-recapito. Per visualizzare una cronologia della posta elettronica, fare clic sull'oggetto di un messaggio di posta elettronica, quindi fare clic su sequenza temporale della posta elettronica. (Viene visualizzato tra le altre intestazioni del pannello come riepilogo o dettagli). Questi risultati possono essere esportati in un foglio di calcolo.

    La sequenza temporale della posta elettronica verrà aperta a una tabella che Visualizza tutti gli eventi di recapito e post-recapito per la posta elettronica. Se non ci sono altre azioni sul messaggio di posta elettronica, dovrebbe essere visualizzato un singolo evento per il recapito originale che indica un risultato, ad esempio *bloccato*, con un verdetto come *phishing*. Gli amministratori possono esportare l'intera sequenza temporale della posta elettronica, inclusi tutti i dettagli sulla scheda e la posta elettronica (ad esempio, oggetto, mittente, destinatario, rete e ID messaggio). La sequenza temporale della posta elettronica riduce la randomizzazione perché è necessario meno tempo per controllare posizioni diverse per cercare di comprendere gli eventi accaduti dopo l'arrivo del messaggio di posta elettronica. Quando più eventi si verificano in un messaggio di posta elettronica o vicino allo stesso tempo, tali eventi vengono visualizzati in una visualizzazione sequenza temporale.

8. **Anteprima/download**: Threat Explorer fornisce al team di operazioni di sicurezza i dettagli necessari per esaminare la posta elettronica sospetta. Il team delle operazioni di sicurezza può:

    - [Controllare l'azione e il percorso di recapito](#check-the-delivery-action-and-location).

    - [Visualizzare la sequenza temporale del messaggio di posta elettronica](#view-the-timeline-of-your-email).

### <a name="check-the-delivery-action-and-location"></a>Controllare l'azione e il percorso di recapito

In [Esplora minacce (e rilevamenti in tempo reale)](threat-explorer.md), ora sono presenti le colonne dell' **azione** di recapito e del **percorso** di recapito anziché la precedente colonna **stato di recapito** . Questo comporta un'immagine più completa della posizione in cui i messaggi di posta elettronica atterrano. Parte dell'obiettivo di questa modifica consiste nell'agevolare le indagini per i team delle operazioni di sicurezza, ma il risultato finale è la conoscenza del percorso dei messaggi di posta elettronica problematici.

Lo stato di recapito è ora suddiviso in due colonne:

- **Azione di recapito** -qual è lo stato di questo messaggio di posta elettronica?

- **Percorso di recapito** -dove è stato instradato il messaggio di posta elettronica come risultato?

Azione di recapito è l'azione intrapresa su un messaggio di posta elettronica a causa di criteri o rilevamenti esistenti. Ecco le possibili azioni che un messaggio di posta elettronica può eseguire:

- **Recapitato** : la posta elettronica è stata recapitata alla posta in arrivo o alla cartella di un utente e l'utente può accedervi direttamente.

- **Junked** – la posta elettronica è stata inviata alla cartella posta indesiderata o alla cartella eliminata dell'utente e l'utente ha accesso ai messaggi di posta elettronica nella cartella posta indesiderata o eliminata.

- **Bloccato** : tutti i messaggi di posta elettronica in quarantena, che hanno avuto esito negativo o sono stati eliminati. (Questo è completamente inaccessibile dall'utente).

- **Sostituito** – qualsiasi messaggio di posta elettronica in cui gli allegati dannosi sono stati sostituiti dai file. txt che affermano che l'allegato è dannoso

Il percorso di recapito consente di visualizzare i risultati dei criteri e i rilevamenti eseguiti dopo il recapito. È collegato a un'azione di recapito. Questo campo è stato aggiunto per fornire informazioni dettagliate sull'azione intrapresa quando viene trovata una posta elettronica problematica. Di seguito sono riportati i possibili valori del percorso di recapito:

- **Posta in arrivo o cartella** – il messaggio di posta elettronica si trova nella cartella posta in arrivo o in una directory (secondo le regole di posta elettronica).

- **On-Prem o External** -la cassetta postale non esiste sul cloud ma è in locale.

- **Cartella posta indesiderata** : la posta elettronica si trova nella cartella posta indesiderata di un utente.

- **Cartella Posta eliminata** – l'e-mail si trova nella cartella degli elementi eliminati di un utente.

- **Quarantine** : la posta elettronica in quarantena e non nella cassetta postale di un utente.

- **Failed** : la posta elettronica non è riuscita a raggiungere la cassetta postale.

- **Eliminato** : il messaggio di posta elettronica viene perso da qualche parte nel flusso di posta.

### <a name="view-the-timeline-of-your-email"></a>Visualizzare la sequenza temporale del messaggio di posta elettronica

La **sequenza temporale della posta elettronica** è un campo in Esplora minacce che facilita la ricerca per il team delle operazioni di sicurezza. Quando più eventi si verificano alla stessa ora o in prossimità di un messaggio di posta elettronica, tali eventi vengono visualizzati in una visualizzazione sequenza temporale. Alcuni eventi che si verificano dopo il recapito al messaggio di posta elettronica vengono acquisiti nella colonna **azioni speciali** . La combinazione di informazioni dalla sequenza temporale di un messaggio di posta elettronica con le azioni speciali eseguite dopo il recapito consente agli amministratori di esaminare i criteri e la gestione delle minacce (ad esempio la posizione in cui è stata instradata la posta elettronica e, in alcuni casi, la valutazione finale).

> [!IMPORTANT]
> Passare a [un argomento di](remediate-malicious-email-delivered-office-365.md)correzione.

## <a name="related-topics"></a>Argomenti correlati

[Rimediare la posta elettronica dannosa recapitata in Office 365](remediate-malicious-email-delivered-office-365.md)

[Office 365 Advanced Threat Protection](office-365-ti.md)

[Protezione dalle minacce in Office 365](protect-against-threats.md)

[Visualizzare i report per Office 365 Advanced Threat Protection](view-reports-for-atp.md)
