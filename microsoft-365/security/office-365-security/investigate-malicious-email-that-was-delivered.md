---
title: Analizzare la posta elettronica dannosa recapitata in Microsoft 365, Individuare e analizzare la posta elettronica dannosa
keywords: TIMailData-Inline, Security Incident, incident, Microsoft Defender for Endpoint PowerShell, email malware, compromised users, email phish, email malware, read email headers, read headers, open email headers,special actions
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/16/2020
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: Informazioni su come usare le funzionalità di analisi e risposta alle minacce per trovare e analizzare la posta elettronica dannosa.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e49963d1ffaeb7bce20f21f82f37fd3675b9cdd3
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083357"
---
# <a name="investigate-malicious-email-that-was-delivered-in-microsoft-365"></a>Analizzare i messaggi di posta elettronica dannosi recapitati in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a:**

- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Microsoft Defender per Office 365](defender-for-office-365.md) consente di analizzare le attività che mettono a rischio le persone nell'organizzazione e di intraprendere azioni per proteggere l'organizzazione. Ad esempio, se si fa parte del team di sicurezza dell'organizzazione, è possibile individuare e analizzare i messaggi di posta elettronica sospetti recapitati. A tale scopo, puoi usare [Threat Explorer (o rilevamenti in tempo reale).](threat-explorer.md)

> [!NOTE]
> Passare all'articolo di correzione [qui](remediate-malicious-email-delivered-office-365.md).

## <a name="before-you-begin"></a>Prima di iniziare

Verificare che vengano soddisfatti i seguenti requisiti:

- L'organizzazione dispone [di Microsoft Defender per Office 365](defender-for-office-365.md) e le licenze vengono assegnate agli [utenti.](../../admin/manage/assign-licenses-to-users.md)

- [La registrazione di](../../compliance/turn-audit-log-search-on-or-off.md) controllo è attivata per l'organizzazione.

- L'organizzazione dispone di criteri definiti per la protezione da posta indesiderata, antimalware, anti-phishing e così via. Vedere [Protezione dalle minacce in Office 365](protect-against-threats.md).

- Si è un amministratore globale o si dispone del ruolo Amministratore sicurezza o Ricerca ed eliminazione assegnato nel Microsoft 365 Defender portale. Per altre informazioni, vedere [Autorizzazioni nel portale di Microsoft 365 Defender](permissions-microsoft-365-security-center.md). Per alcune azioni, è necessario assegnare anche il ruolo Anteprima.

### <a name="preview-role-permissions"></a>Autorizzazioni per il ruolo Anteprima

Per eseguire determinate azioni, ad esempio la visualizzazione delle intestazioni  dei messaggi o il download del contenuto dei messaggi di posta elettronica, è necessario aggiungere il ruolo Anteprima a un altro gruppo di ruoli appropriato. Nella tabella seguente vengono chiariti i ruoli e le autorizzazioni necessari.

<br>

****

|Attività|Gruppo di ruolo|Ruolo anteprima necessario?|
|---|---|---|
|Usare Esplora minacce (e rilevamenti in tempo reale) per analizzare le minacce |Amministratore globale <p> Amministratore della sicurezza <p> Ruolo con autorizzazioni di lettura per la sicurezza|No|
|Usare Esplora minacce (e rilevamenti in tempo reale) per visualizzare le intestazioni dei messaggi di posta elettronica, nonché visualizzare in anteprima e scaricare i messaggi di posta elettronica in quarantena|Amministratore globale <p> Amministratore della sicurezza <p> Ruolo con autorizzazioni di lettura per la sicurezza|No|
|Usare Esplora minacce per visualizzare le intestazioni, visualizzare in anteprima la posta elettronica (solo nella pagina dell'entità di posta elettronica) e scaricare i messaggi di posta elettronica recapitati alle cassette postali|Amministratore globale <p> Amministratore della sicurezza <p> Ruolo con autorizzazioni di lettura per la sicurezza <p> Anteprima|Sì|
|

> [!NOTE]
> *L'anteprima* è un ruolo e non un gruppo di ruoli. Il ruolo Anteprima deve essere aggiunto a un gruppo di ruoli esistente nel portale di Microsoft 365 Defender ( <https://security.microsoft.com> ). Passare a **Autorizzazioni** e quindi modificare un gruppo di ruoli esistente o aggiungere un nuovo gruppo di ruoli con il **ruolo Anteprima** assegnato.
>
> Al ruolo Amministratore globale viene assegnato il interfaccia di amministrazione di Microsoft 365 ( ) e i ruoli Amministratore sicurezza e Lettore sicurezza vengono assegnati in Microsoft 365 Defender <https://admin.microsoft.com> ( <https://security.microsoft.com> ). Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere Autorizzazioni nel [portale Microsoft 365 Defender.](permissions-microsoft-365-security-center.md)

Sappiamo che l'anteprima e il download della posta elettronica sono attività sensibili e quindi il controllo è abilitato per queste attività. Una volta che un amministratore esegue queste attività sui messaggi di posta elettronica, i log di controllo vengono generati per lo stesso e possono essere visibili nel portale di Microsoft 365 Defender ( <https://security.microsoft.com> ). Vai alla **scheda** \> **Controlla** ricerca e filtra il nome dell'amministratore nella **casella** Utenti. I risultati filtrati mostreranno l'attività **AdminMailAccess.** Selezionare una riga per visualizzare i dettagli nella sezione **Ulteriori informazioni** sulla posta elettronica in anteprima o scaricata.

## <a name="find-suspicious-email-that-was-delivered"></a>Trovare messaggi di posta elettronica sospetti recapitati

Esplora minacce è un potente report che può servire a più scopi, come trovare ed eliminare messaggi, identificare l'indirizzo IP di un mittente di posta elettronica dannoso o avviare un evento imprevisto per ulteriori indagini. La procedura seguente è incentrata sull'utilizzo di Esplora risorse per trovare ed eliminare messaggi di posta elettronica dannosi dalle cassette postali del destinatario.

> [!NOTE]
> Le ricerche predefinite in Esplora risorse non includono attualmente gli elementi recapitati rimossi dalla cassetta postale cloud tramite protezione automatica a zero ore (ZAP). Questa limitazione si applica a tutte le visualizzazioni (ad esempio, le visualizzazioni **\> Malware** e-mail o **Email \> Phish).** Per includere gli elementi rimossi da ZAP, è necessario aggiungere un set **di** azioni di recapito per includere **Rimosso da ZAP.** Se includi tutte le opzioni, vedrai tutti i risultati dell'azione di recapito, inclusi gli elementi rimossi da ZAP.

1. Apri il portale Microsoft 365 Defender <https://security.microsoft.com> e accedi usando l'account aziendale o dell'istituto di istruzione per Office 365.

2. Vai a **Esplora minacce** scegliendo Posta elettronica **& collaborazione** \> **Explorer** nel riquadro di spostamento sinistro. Per passare direttamente a **Threat Explorer,** usa <https://security.microsoft.com/threatexplorer> .

   Nella colonna **Azioni**  aggiuntive della pagina Esplora risorse viene visualizzato il risultato dell'elaborazione di un messaggio di posta elettronica da parte degli amministratori. È **possibile accedere alla** colonna Azioni aggiuntive nella stessa posizione dell'azione di **recapito** e della posizione **di recapito.** Le azioni speciali potrebbero essere aggiornate alla fine della sequenza temporale della posta elettronica di Threat Explorer, una nuova funzionalità volta a migliorare l'esperienza di ricerca per gli amministratori.

3. Nel menu **Visualizza** scegliere **E-mail** \> **Tutti i messaggi di posta** elettronica dall'elenco a discesa.

    ![Menu Visualizza esplora minacce e Posta elettronica - Malware, Phish, Invii e Tutte le opzioni di posta elettronica, anche Contenuto - Malware.](../../media/tp-InvestigateMalEmail-viewmenu.png)

    La *visualizzazione Malware* è attualmente l'impostazione predefinita e acquisisce i messaggi di posta elettronica in cui viene rilevata una minaccia malware. La *visualizzazione Phish* funziona nello stesso modo, per Phish.

    Tuttavia, *nella visualizzazione Tutti i* messaggi di posta elettronica sono elencati tutti i messaggi ricevuti dall'organizzazione, indipendentemente dal fatto che siano state rilevate o meno minacce. Come puoi immaginare, si tratta di una grande quantità di dati, motivo per cui questa visualizzazione mostra un segnaposto che richiede l'applicazione di un filtro. Questa visualizzazione è disponibile solo per Defender per Office 365 clienti P2.

    *La visualizzazione* Invii mostra tutti i messaggi inviati dall'amministratore o dall'utente segnalati a Microsoft.

4. **Ricerca e filtro in Esplora** minacce : i filtri vengono visualizzati nella parte superiore della pagina nella barra di ricerca per aiutare gli amministratori nelle indagini. Si noti che è possibile applicare più filtri contemporaneamente e più valori delimitati da virgole aggiunti a un filtro per restringere la ricerca. Attenzione:

    - I filtri corrispondono esattamente alla maggior parte delle condizioni di filtro.
    - Il filtro dell'oggetto utilizza una query CONTAINS.
    - I filtri URL funzionano con o senza protocolli (ad esempio, https).
    - I filtri dominio URL, percorso URL e dominio URL e percorso non richiedono un protocollo per filtrare.
    - È necessario fare clic sull'icona Aggiorna ogni volta che si modificano i valori del filtro per ottenere risultati pertinenti.

5. **Filtri avanzati:** con questi filtri è possibile creare query complesse e filtrare il set di dati. Facendo clic *su Filtri avanzati* si apre un riquadro a comparsa con opzioni.

   Il filtro avanzato è un'ottima aggiunta alle funzionalità di ricerca. Un valore booleano  NOT nei filtri di dominio **Destinatario,** **Mittente** e Mittente consente agli amministratori di analizzare escludendo i valori. Questa opzione è **Uguale a nessuna selezione.** Questa opzione consente agli amministratori di escludere le cassette postali indesiderate dalle indagini (ad esempio, cassette postali di avviso e cassette postali di risposta predefinite) ed è utile nei casi in cui gli amministratori ricercano un oggetto specifico (ad esempio Attenzione) in cui il destinatario può essere impostato su Uguale a *nessuno di: defaultMail@contoso.com*. Si tratta di una ricerca con valore esatto.

   ![Destinatari - Filtro avanzato "Non contiene nessuno di".](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   L'aggiunta di un filtro ora alla data di inizio e alla data di fine consente al team di sicurezza di eseguire rapidamente il drill-down. La durata minima consentita è di 30 minuti. Se puoi restringere l'azione sospetta in base all'intervallo di tempo (ad esempio, si è verificato 3 ore fa), questo limiterà il contesto e aiuterà a individuare il problema.

   ![L'opzione filtro in base alle ore per limitare la quantità di team di sicurezza dei dati da elaborare e la cui durata più breve è di 30 minuti.](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. **Campi in Esplora** minacce : Threat Explorer espone molte più informazioni relative alla sicurezza della posta, ad esempio l'azione di *recapito,* la posizione di *recapito,* l'azione *speciale,* la direzionalità, le sostituzioni e la minaccia *url.* Consente inoltre al team di sicurezza dell'organizzazione di analizzare con maggiore certezza.

    *L'azione* di recapito è l'azione eseguita su un messaggio di posta elettronica a causa di criteri o rilevamenti esistenti. Ecco le possibili azioni che un messaggio di posta elettronica può eseguire:

    - **Recapitato:** la posta elettronica è stata recapitata nella posta in arrivo o nella cartella di un utente e l'utente può accedervi direttamente.
    - **Posta indesiderata** (recapitata nella posta indesiderata): la posta elettronica è stata inviata alla cartella posta indesiderata o eliminata dell'utente e l'utente ha accesso ai messaggi di posta elettronica nella cartella Posta indesiderata o Eliminata.
    - **Bloccato:** tutti i messaggi di posta elettronica messi in quarantena, non riusciti o eliminati. Questo è completamente inaccessibile dall'utente.
    - **Sostituito:** qualsiasi messaggio di posta elettronica in cui gli allegati dannosi vengono sostituiti da .txt che indica che l'allegato era dannoso

    **Posizione di recapito**: il filtro Percorso di recapito è disponibile per consentire agli amministratori di comprendere dove è stata terminata la posta indesiderata sospetta e quali azioni sono state intraprese su di esso. I dati risultanti possono essere esportati in un foglio di calcolo. I possibili percorsi di recapito sono:

    - **Posta in arrivo o cartella:** il messaggio di posta elettronica si trova nella cartella Posta in arrivo o in una cartella specifica, in base alle regole di posta elettronica.
    - **Locale o esterno:** la cassetta postale non esiste nel cloud ma è locale.
    - **Cartella Posta indesiderata:** il messaggio di posta elettronica si trova nella cartella Posta indesiderata di un utente.
    - **Cartella Posta eliminata:** il messaggio di posta elettronica si trova nella cartella Posta eliminata di un utente.
    - **Quarantena:** messaggio di posta elettronica in quarantena e non nella cassetta postale di un utente.
    - **Failed:** il messaggio di posta elettronica non è riuscito a raggiungere la cassetta postale.
    - **Eliminato:** il messaggio di posta elettronica è stato perso da qualche parte nel flusso di posta.

    **Direzionalità:** questa opzione consente al team delle operazioni di sicurezza di filtrare in base alla "direzione" da cui proviene o sta andando un messaggio di posta elettronica. I valori di direzionalità sono *Inbound,* *Outbound* e *Intra-org* (corrispondenti alla posta proveniente dall'esterno, inviata dall'esterno dell'organizzazione o inviata internamente all'organizzazione, rispettivamente). Queste informazioni possono aiutare i team delle operazioni di sicurezza a individuare lo spoofing e la rappresentazione, perché una mancata corrispondenza tra il valore Directionality (ad esempio. *In ingresso*) e il dominio del mittente *(che* sembra essere un dominio interno) saranno evidenti. Il valore Directionality è separato e può essere diverso da Message Trace. I risultati possono essere esportati in un foglio di calcolo.

    **Sostituzioni:** questo filtro accetta le informazioni visualizzate nella scheda dei dettagli della posta e le utilizza per esporre dove sono stati ignorati i criteri dell'organizzazione o degli utenti per consentire e bloccare i messaggi di *posta elettronica.* La cosa più importante di questo filtro è che consente al team di sicurezza dell'organizzazione di vedere quanti messaggi di posta elettronica sospetti sono stati recapitati a causa della configurazione. Ciò offre loro l'opportunità di modificare le autorizzazioni e i blocchi in base alle esigenze. Questo set di risultati di questo filtro può essere esportato in un foglio di calcolo.

    <br>

    ****

    |Sostituzioni di Esplora minacce|Significato|
    |---|---|
    |Consentito dai criteri dell'organizzazione|La posta è stata consentita nella cassetta postale come indicato dal criterio dell'organizzazione.|
    |Bloccato dai criteri dell'organizzazione|La posta è stata bloccata dal recapito alla cassetta postale come indicato dal criterio dell'organizzazione.|
    |Estensione di file bloccata dai criteri organizzazione|Il recapito del file alla cassetta postale è stato bloccato come indicato dal criterio dell'organizzazione.|
    |Consentito dai criteri utente|La posta è stata consentita nella cassetta postale come indicato dal criterio utente.|
    |Bloccato dai criteri utente|La posta è stata bloccata dal recapito alla cassetta postale come indicato dal criterio utente.|
    |

    **Minaccia URL**: il campo della  minaccia URL è stato incluso nella scheda dei dettagli di un messaggio di posta elettronica per indicare la minaccia presentata da un URL. Le minacce presentate da un URL possono includere *malware,*  *phish* o *posta* indesiderata e un URL senza minacce dirà *Nessuno* nella sezione minacce.

7. **Visualizzazione sequenza temporale della posta** elettronica: il team delle operazioni di sicurezza potrebbe dover approfondire i dettagli della posta elettronica per analizzare ulteriormente. La sequenza temporale della posta elettronica consente agli amministratori di visualizzare le azioni eseguite su un messaggio di posta elettronica dal recapito al post-recapito. Per visualizzare una sequenza temporale della posta elettronica, fare clic sull'oggetto di un messaggio di posta elettronica e quindi fare clic su Sequenza temporale della posta elettronica. Viene visualizzata tra le altre intestazioni del pannello, ad esempio Riepilogo o Dettagli. Questi risultati possono essere esportati in un foglio di calcolo.

    La sequenza temporale della posta elettronica verrà aperta in una tabella che mostra tutti gli eventi di recapito e post-recapito per il messaggio di posta elettronica. Se non sono presenti altre azioni nel messaggio di posta elettronica, dovrebbe essere visualizzato un singolo evento per il recapito originale che indica un risultato, ad esempio *Bloccato*, con un verdetto come *Phish.* Gli amministratori possono esportare l'intera sequenza temporale della posta elettronica, inclusi tutti i dettagli nella scheda e nella posta elettronica (ad esempio, Oggetto, Mittente, Destinatario, Rete e ID messaggio). La sequenza temporale della posta elettronica riduce la casualità perché c'è meno tempo impiegato per controllare posizioni diverse per cercare di comprendere gli eventi che si sono verificati dopo l'arrivo del messaggio di posta elettronica. Quando più eventi si verificano nello stesso momento o quasi in un messaggio di posta elettronica, tali eventi vengono visualizzati in una visualizzazione sequenza temporale.

8. **Anteprima/download:** Threat Explorer fornisce al team delle operazioni di sicurezza i dettagli necessari per analizzare la posta elettronica sospetta. Il team delle operazioni di sicurezza può:

    - [Controllare l'azione di recapito e la posizione](#check-the-delivery-action-and-location).

    - [Visualizzare la sequenza temporale del messaggio di posta elettronica.](#view-the-timeline-of-your-email)

### <a name="check-the-delivery-action-and-location"></a>Controllare l'azione di recapito e la posizione

In [Esplora minacce (e rilevamenti](threat-explorer.md)in tempo reale)  ora sono disponibili le colonne **Azione** di recapito e Posizione di recapito anziché la precedente **colonna Stato** recapito. Ciò consente di ottenere un quadro più completo della posizione dei messaggi di posta elettronica. Parte dell'obiettivo di questa modifica è semplificare le indagini per i team delle operazioni di sicurezza, ma il risultato è conoscere rapidamente la posizione dei messaggi di posta elettronica problematici.

Lo stato del recapito è ora suddiviso in due colonne:

- **Azione di recapito** - Qual è lo stato di questo messaggio di posta elettronica?
- **Posizione di recapito** - Dove è stato instradato il messaggio di posta elettronica?

L'azione di recapito è l'azione eseguita su un messaggio di posta elettronica a causa di criteri o rilevamenti esistenti. Ecco le possibili azioni che un messaggio di posta elettronica può eseguire:

- **Recapitato:** la posta elettronica è stata recapitata nella posta in arrivo o nella cartella di un utente e l'utente può accedervi direttamente.
- **Posta indesiderata:** la posta elettronica è stata inviata alla cartella posta indesiderata o eliminata dell'utente e l'utente ha accesso ai messaggi di posta elettronica nella cartella Posta indesiderata o Eliminata.
- **Bloccato:** tutti i messaggi di posta elettronica messi in quarantena, non riusciti o eliminati. Questo è completamente inaccessibile dall'utente.
- **Sostituito:** qualsiasi messaggio di posta elettronica in cui gli allegati dannosi vengono sostituiti da .txt che indica che l'allegato era dannoso.

Percorso di recapito mostra i risultati dei criteri e dei rilevamenti eseguiti dopo il recapito. È collegato a un'azione di recapito. Questo campo è stato aggiunto per fornire informazioni dettagliate sull'azione eseguita quando viene trovato un messaggio di posta elettronica problematico. Ecco i valori possibili della posizione di recapito:

- **Posta in arrivo o cartella:** il messaggio di posta elettronica si trova nella posta in arrivo o in una cartella (in base alle regole di posta elettronica).
- **Locale o esterno:** la cassetta postale non esiste nel cloud ma è locale.
- **Cartella Posta indesiderata:** il messaggio di posta elettronica si trova nella cartella Posta indesiderata di un utente.
- **Cartella Posta eliminata:** il messaggio di posta elettronica si trova nella cartella Posta eliminata di un utente.
- **Quarantena:** messaggio di posta elettronica in quarantena e non nella cassetta postale di un utente.
- **Failed:** il messaggio di posta elettronica non è riuscito a raggiungere la cassetta postale.
- **Eliminato:** il messaggio di posta elettronica si perde da qualche parte nel flusso di posta.

### <a name="view-the-timeline-of-your-email"></a>Visualizzare la sequenza temporale del messaggio di posta elettronica

**Sequenza temporale della** posta elettronica è un campo in Esplora minacce che semplifica la ricerca per il team delle operazioni di sicurezza. Quando in un messaggio di posta elettronica si verificano più eventi contemporaneamente o quasi, tali eventi vengono visualizzati in una visualizzazione sequenza temporale. Alcuni eventi che si verificano dopo il recapito alla posta elettronica vengono acquisiti nella **colonna Azioni** speciali. La combinazione delle informazioni della sequenza temporale di un messaggio di posta elettronica con eventuali azioni speciali intraprese dopo il recapito offre agli amministratori informazioni approfondite sui criteri e sulla gestione delle minacce (ad esempio, dove è stata instradata la posta e, in alcuni casi, qual è stata la valutazione finale).

> [!IMPORTANT]
> Passare a un argomento di correzione [qui](remediate-malicious-email-delivered-office-365.md).

## <a name="related-topics"></a>Argomenti correlati

[Correggere i messaggi di posta elettronica dannosi recapitati in Office 365](remediate-malicious-email-delivered-office-365.md)

[Microsoft Defender per Office 365](office-365-ti.md)

[Proteggere dalle minacce in Office 365](protect-against-threats.md)

[Visualizzare i report per Defender per Office 365](view-reports-for-mdo.md)
