---
title: Configurare i criteri di filtro della posta indesiderata
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: Informazioni per amministratori su come visualizzare, creare, modificare ed eliminare criteri di protezione dalla posta indesiderata in Exchange Online Protection (EOP).
ms.openlocfilehash: 2bb6bff5fae661d755ea19dbb5af8ca62fbacbd8
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130864"
---
# <a name="configure-anti-spam-policies-in-eop"></a>Configurare criteri di protezione dalla posta indesiderata in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, i messaggi di posta elettronica in ingresso vengono protetti automaticamente dalla posta indesiderata da EOP. Come parte del sistema di difesa dell'organizzazione, EOP utilizza criteri di protezione dalla posta indesiderata, noti anche come criteri di filtro della posta indesiderata o criteri di filtro di contenuti. Per altre informazioni, vedere [Protezione dalla posta indesiderata](anti-spam-protection.md).

Gli amministratori possono visualizzare, modificare e configurare, ma non eliminare, il criterio di protezione dalla posta indesiderata predefinito. Per una maggiore granularità, è anche possibile creare criteri di protezione dalla posta indesiderata personalizzati applicabili a utenti, gruppi o domini specifici nell'organizzazione. I criteri personalizzati hanno sempre la precedenza sul criterio predefinito, ma non è possibile modificarne la priorità (in funzione).

È possibile configurare criteri di protezione dalla posta indesiderata nel Centro sicurezza e conformità o in PowerShell (PowerShell di Exchange Online per organizzazioni di Microsoft 365 con cassette postali in Exchange Online; PowerShell di EOP autonomo per organizzazioni prive di cassette postali di Exchange Online).

Gli elementi di base del criterio di protezione dalla posta indesiderata sono:

- **Criterio di filtro della posta indesiderata**: specifica le azioni per i verdetti filtro posta indesiderata e le opzioni di notifica.
- **Regola di filtro della posta indesiderata**: specifica la priorità e i filtri destinatario (a chi si applica il criterio) per un criterio di filtro della posta indesiderata.

La differenza tra questi due elementi non è ovvia quando si gestiscono criteri di protezione dalla posta indesiderata nel Centro sicurezza e conformità:

- Quando si crea un criterio di protezione dalla posta indesiderata, in contemporanea viene creata una regola di filtro della posta indesiderata e il criterio di filtro della posta indesiderata associato, utilizzando lo stesso nome per entrambi.
- Quando si modifica un criterio di protezione dalla posta indesiderata, le impostazioni relative a nome, priorità, attivazione o disattivazione e filtri destinatari modificano la regola di filtro della posta indesiderata. Tutte le altre impostazioni modificano il criterio di filtro della posta indesiderata associato.
- Quando si rimuovono il criterio di protezione dalla posta indesiderata, la regola di filtro della posta indesiderata e il criterio di filtro della posta indesiderata vengono rimossi.

In PowerShell di Exchange Online o in EOP PowerShell autonomo i criteri e la regola vengono gestiti separatamente. Per maggiori informazioni, vedere [Usare PowerShell di Exchange Online o EOP di PowerShell autonomo per configurare i criteri di posta indesiderata](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies) nella sezione successiva in questo argomento.

Ogni organizzazione ha un criterio incorporato per la posta indesiderata, denominato Predefinito, aventi le seguenti proprietà:

- Il criterio viene applicato a tutti i destinatari dell'organizzazione, anche se non esiste alcuna regola di filtro della posta indesiderata (filtri destinatari) associata al criterio.
- Il valore personalizzato della priorità del criterio è **Minore** e non può essere modificato (il criterio viene sempre applicato per ultimo). Qualsiasi criterio personalizzato creato avrà sempre una priorità più alta.
- Il criterio è quello predefinito (la proprietà **IsDefault** contiene il valore `True`), e non è possibile eliminarlo.

Per aumentare l'efficacia del filtro della posta indesiderata, è possibile creare criteri di protezione dalla posta indesiderata con impostazioni più restrittive da applicare a utenti o gruppi di utenti specifici.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla pagina **Impostazioni di filtro della posta indesiderata**, usare <https://protection.office.com/antispam>.

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- È necessario disporre delle autorizzazioni per eseguire le procedure di questo argomento:

  - Per aggiungere, modificare ed eliminare criteri di protezione dalla posta indesiderata, è necessario essere membri di uno dei seguenti gruppi di ruoli:

    - **Gestione organizzazione** o **Amministratore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).
    - **Gestione organizzazione** o **Gestione igiene** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Per l’accesso in sola lettura ai criteri di protezione della posta indesiderata, è necessario essere membri di uno dei seguenti gruppi di ruoli:

    - **Lettore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).
    - **Gestione organizzazione in sola lettura** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Per le impostazioni consigliate per i criteri contro la posta indesiderata, vedere [Impostazioni dei criteri di protezione dalla posta indesiderata di EOP](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).

## <a name="use-the-security--compliance-center-to-create-anti-spam-policies"></a>Utilizzare il Centro sicurezza e conformità per creare criteri di protezione dalla posta indesiderata

La creazione di un criterio di protezione dalla posta indesiderata nel Centro sicurezza e conformità permette di creare contemporaneamente una regola di filtro della posta indesiderata e il criterio di filtro della posta indesiderata associato, utilizzando lo stesso nome per entrambi.

1. Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.

2. Nella pagina **Impostazioni di filtro della posta indesiderata**, fare clic su **Crea un criterio**.

3. Nel riquadro a comparsa **Nuovo criterio di filtro della posta indesiderata** che si apre, configurare le seguenti impostazioni:

   - **Nome**: immettere un nome univoco descrittivo per il criterio. Non usare i caratteri seguenti: `\ % & * + / = ? { } | < > ( ) ; : , [ ] "`.

      Se nell'interfaccia di amministrazione di Exchange in precedenza sono stati creati criteri di protezione dalla posta indesiderata contenenti questi caratteri, è consigliabile rinominare tali criteri in PowerShell. Per le istruzioni, vedere la sezione [Utilizzo di PowerShell per modificare regole di filtro della posta indesiderata](#use-powershell-to-modify-spam-filter-rules) più avanti in questo argomento.

   - **Descrizione**: immettere una descrizione opzionale per il criterio.

4. (Facoltativo) Espandere la sezione **Azioni per posta indesiderata e inviata in blocco** e verificare o configurare le impostazioni seguenti:

   - **Selezionare l'azione da eseguire per la posta indesiderata in ingresso e per la posta elettronica inviata in blocco**: selezionare o rivedere l'azione da eseguire per i messaggi in base ai verdetti filtro posta indesiderata seguenti:

     - **Posta indesiderata**
     - **Posta indesiderata con alta confidenza**
     - **Posta di phishing**
     - **Posta di phishing con alta confidenza**
     - **Posta elettronica inviata in massa**

     Le azioni disponibili per i verdetti filtro posta indesiderata sono descritte nella tabella seguente.

     - Un segno di spunta ( ![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)) indica che l'azione è disponibile (non tutte le azioni sono disponibili per tutti i verdetti filtro posta indesiderata).
     - Un asterisco (<sup>\*</sup>) dopo il segno di spunta indica l'azione predefinita per il verdetto filtro posta indesiderata.

     ****

     |<span>|Posta indesiderata|Fortemente<br/>confidenziale<br/>posta indesiderata|Phishing<br/>e-mail|Fortemente<br/>confidenziale<br/>phishing<br/>e-mail|Invio in blocco<br/>e-mail|
     |---|:---:|:---:|:---:|:---:|:---:|
     |**Spostare un messaggio nella cartella Posta indesiderata**: il messaggio viene recapitato nella cassetta postale e spostato nella cartella Posta indesiderata.<sup>1</sup>|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
     |**Aggiungi X-Header**: aggiunge un X-Header all'intestazione del messaggio e recapita il messaggio nella cassetta postale. <p> Immettere il nome del campo X-Header (non il valore) successivamente nella casella **Aggiungi testo X-Header**. <p> Per i verdetti **Posta indesiderata** e **Posta indesiderata con alta confidenza**, il messaggio viene spostato nella cartella Posta indesiderata.<sup>1,2</sup>|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
     |**Anteponi testo alla riga dell'oggetto**: aggiunge testo all'inizio della riga dell'oggetto del messaggio. Il messaggio viene recapitato nella cassetta postale e spostato nella cartella Posta indesiderata.<sup>1,2</sup> <p> Immettere il testo successivamente nella casella **Riga dell'oggetto del prefisso con il testo**.|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |**Reindirizza messaggio a indirizzo di posta elettronica:** invece di inviare il messaggio ai destinatari designati, lo invia ad altri destinatari. <p> Specificare i destinatari successivamente nella casella **Reindirizza a questo indirizzo di posta elettronica**.|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |**Elimina messaggio:** elimina automaticamente l'intero messaggio, inclusi gli allegati.|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |**Messaggio di quarantena:** il messaggio non viene inviato ai destinatari, ma viene messo in quarantena. <p> Specificare per quanto tempo mantenere il messaggio in quarantena più avanti nella casella **Quarantena**.|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |**Nessuna azione**|||||![Segno di spunta](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |

     <sup>1</sup> In Exchange Online, il messaggio viene spostato nella cartella Posta indesiderata se la regola per la posta indesiderata è abilitata per la cassetta postale (abilitata per impostazione predefinita). Per altre informazioni, vedere [Configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).

     Negli ambienti di EOP autonomi in cui EOP protegge le cassette postali di Exchange locali, è necessario configurare le regole del flusso di posta (anche note come regole di trasporto) in Exchange locale per tradurre il verdetto filtro posta indesiderata in modo che la regola della posta indesiderata possa spostare il messaggio nella cartella Posta indesiderata. Per dettagli, vedere [Configurare EOP autonomo per recapitare la posta indesiderata nella cartella Posta indesiderata negli ambienti ibridi](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

     <sup>2</sup> È possibile usare questo valore come condizione nelle regole del flusso di posta, anche note come regole di trasporto, per filtrare o instradare il messaggio.

   - **Selezionare la soglia**: specifica il livello di reclamo in blocco di un messaggio che attiva l'azione specificata per il verdetto filtro posta indesiderata **Posta elettronica inviata in massa** (maggiore del valore specificato, non maggiore di o uguale a). Un valore alto indica che il messaggio è meno opportuno (probabilmente un messaggio di posta indesiderata). Il valore predefinito è 7. Per altre informazioni, vedere [Livello di reclamo in blocco in EOP](bulk-complaint-level-values.md) e [Qual è la differenza tra posta indesiderata e posta inviata in massa?](what-s-the-difference-between-junk-email-and-bulk-email.md).

     Per impostazione predefinita, l'impostazione solo PowerShell _MarkAsSpamBulkMail_ è `On` nei criteri di protezione dalla posta indesiderata. Questa impostazione influisce molto sui risultati di un verdetto filtro **Posta elettronica inviata in massa**:

     - **_MarkAsSpamBulkMail_ è attivo**: un livello di reclamo di blocco maggiore della soglia viene convertito in un livello di probabilità di posta indesiderata 6 che corrisponde a un verdetto filtro **Posta indesiderata** e sul messaggio viene eseguita l'azione per il verdetto filtro **Posta elettronica inviata in massa**.

     - **_MarkAsSpamBulkMail_ è disattivato**: il messaggio viene contrassegnato con il livello di reclamo di blocco, ma _nessuna azione_ viene eseguita per un verdetto filtro **Posta elettronica inviata in massa**. In effetti, la soglia del livello di reclamo di blocco e l'azione verdetto filtro **Posta elettronica inviata in massa** sono irrilevanti.

   - **Quarantena**: specifica per quanto tempo mantenere il messaggio in quarantena se è stato selezionato **Messaggio di quarantena** come azione per il verdetto filtro posta indesiderata. Scaduto il periodo di tempo, il messaggio viene eliminato. Il valore predefinito è 30 giorni. Un valore valido è compreso tra 1 e 30 giorni. Per ulteriori informazioni sulla quarantena, vedere i seguenti argomenti:

     - [Messaggi in quarantena in EOP](quarantine-email-messages.md)
     - [Gestire i messaggi e i file messi in quarantena come amministratore in EOP](manage-quarantined-messages-and-files.md)
     - [Trovare e rilasciare i messaggi messi in quarantena come utente di EOP](find-and-release-quarantined-messages-as-a-user.md)

   - **Aggiungi testo X-Header**: questa casella è obbligatoria e disponibile solo se **Aggiungi X-Header** è stato selezionato come azione per il verdetto filtro posta indesiderata. Il valore specificato è il *nome* del campo di intestazione aggiunto all'intestazione del messaggio. Il *valore* del campo di intestazione è sempre `This message appears to be spam`.

     La lunghezza massima è 255 caratteri e il valore non può contenere spazi e due punti (:).

     Per esempio, se si immette il valore `X-This-is-my-custom-header`, l'opzione X-Header aggiunta al messaggio sarà `X-This-is-my-custom-header: This message appears to be spam.`

     Se si immette un valore che contiene spazi o due punti (:), il valore inserito viene ignorato e l'opzione X-Header viene aggiunta al messaggio (`X-This-Is-Spam: This message appears to be spam.`).

   - **Anteponi testo alla riga dell'oggetto**: questa casella è obbligatoria e disponibile solo se **Anteponi testo alla riga dell'oggetto** è stato selezionato come azione per il verdetto filtro posta indesiderata. Immettere il testo da aggiungere all'inizio della riga dell'oggetto del messaggio.

   - **Reindirizza a questo indirizzo di posta elettronica**: questa casella è obbligatoria e disponibile solo se **Reindirizza il messaggio all'indirizzo di posta elettronica** è stato selezionato come azione per il verdetto filtro posta indesiderata. Immettere l'indirizzo di posta elettronica cui recapitare il messaggio. È possibile immettere più valori separati da punto e virgola (;).

   - **Suggerimenti per la sicurezza**: per impostazione predefinita, i suggerimenti per la sicurezza sono abilitati, ma è possibile disabilitarli deselezionando la casella di controllo **Attivo**. Per altre informazioni sui suggerimenti per la sicurezza, leggere [Suggerimenti per la sicurezza nei messaggi di posta elettronica](safety-tips-in-office-365.md).

   Impostazioni **Zero-Hour Auto Purge**: ZAP rileva ed esegue operazioni sui messaggi già recapitati nelle cassette di posta di Exchange Online. Per altre informazioni su Zero-Hour Auto Purge vedere [Zero-Hour Auto Purge: protezione contro la posta indesiderata e il malware](zero-hour-auto-purge.md).

   - **ZAP della posta indesiderata**: per impostazione predefinita, la funzionalità ZAP è abilitata per il rilevamento della posta indesiderata, tuttavia è possibile disabilitarla deselezionando la casella di controllo **Attivo**.

   - **ZAP del phishing**: per impostazione predefinita, ZAP è abilitata per il rilevamento del phishing, tuttavia è possibile disabilitarla deselezionando la casella di controllo **Attivo**.

5. (Facoltativo) Espandere la sezione **Elenchi elementi consentiti** per configurare i mittenti dei messaggi in base all'indirizzo di posta elettronica o al dominio di posta elettronica a cui è consentito ignorare il filtro posta indesiderata:

   > [!CAUTION]
   >
   > - valutare con attenzione prima di aggiungere domini in questa sezione. Per altre informazioni, vedere [Creare elenchi di mittenti attendibili in EOP](create-safe-sender-lists-in-office-365.md)
   >
   > - Non aggiungere mai domini accettati, ovvero domini propri, o domini comuni, ad esempio microsoft.com o office.com, all'elenco di domini consentiti. Ciò consentirebbe agli utenti malintenzionati di inviare messaggi di posta elettronica in grado di ignorare il filtro posta indesiderata all'interno dell'organizzazione.

   - **Consenti mittente**: fare clic su **Modifica**. Nel riquadro a comparsa **Elenco di mittenti consentiti** che si apre:

      a. Immettere l'indirizzo di posta elettronica del mittente. È possibile indicare più indirizzi di posta elettronica separati da punto e virgola (;).

      b. Scegliere ![Icona Aggiungi](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) per aggiungere i mittenti.

      Ripetere questi passaggi tutte le volte necessarie.

      I mittenti aggiunti vengono visualizzati nella sezione **Mittente consentito** nel riquadro a comparsa. Per eliminare un mittente, fare clic su ![Icona Rimuovi](../../media/scc-remove-icon.png).

      Al termine, scegliere **Salva**.

   - **Consenti dominio**: fare clic su **Modifica**. Nel riquadro a comparsa **Elenco di domini consentiti** visualizzato procedere come segue:

      a. Immettere il dominio. È possibile specificare più domini separati da punto e virgola (;).

      b. Scegliere ![Icona Aggiungi](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) per aggiungere i domini.

      Ripetere questi passaggi tutte le volte necessarie.

      I domini aggiunti vengono visualizzati nella sezione **Dominio consentito** nel riquadro a comparsa. Per eliminare un dominio, fare clic su ![Icona Rimuovi](../../media/scc-remove-icon.png).

      Al termine, scegliere **Salva**.

6. (Facoltativo) Espandere la sezione **Elenchi elementi bloccati** per configurare i mittenti dei messaggi in base all'indirizzo di posta elettronica o al dominio di posta elettronica che sarà sempre contrassegnato come posta indesiderata con alta confidenza:

   > [!NOTE]
   > Il blocco manuale dei domini non è pericoloso, ma può aumentare il carico di lavoro amministrativo. Per altre informazioni, vedere [Creare elenchi di mittenti bloccati in EOP](create-block-sender-lists-in-office-365.md).

   - **Blocca mittente**: fare clic su **Modifica**. Nel riquadro a comparsa **Elenco di mittenti bloccati** che si apre procedere come segue:

      a. Immettere l'indirizzo di posta elettronica del mittente. È possibile indicare più indirizzi di posta elettronica separati da punto e virgola (;). Caratteri jolly (*) non consentiti.

      b. Scegliere ![Icona Aggiungi](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) per aggiungere i mittenti.

      Ripetere questi passaggi tutte le volte necessarie.

      I mittenti aggiunti vengono visualizzati nella sezione **Mittente bloccato** nel riquadro a comparsa. Per eliminare un mittente, fare clic su ![Pulsante Rimuovi](../../media/scc-remove-icon.png).

      Al termine, scegliere **Salva**.

   - **Blocca dominio**: fare clic su **Modifica**. Nel riquadro a comparsa **Elenco di domini bloccati** visualizzato:

      a. Immettere il dominio. È possibile specificare più domini separati da punto e virgola (;). Caratteri jolly (*) non consentiti.

      b. Scegliere ![Icona Aggiungi](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) per aggiungere i domini.

      Ripetere questi passaggi tutte le volte necessarie.

      I domini aggiunti vengono visualizzati nella sezione **Dominio bloccato** nel riquadro a comparsa. Per eliminare un dominio, fare clic su ![Pulsante Rimuovi](../../media/scc-remove-icon.png).

      Al termine, scegliere **Salva**.

7. (Facoltativo) Espandere la sezione **Posta indesiderata internazionale** per configurare la lingua per i messaggi di posta elettronica o i paesi di origine bloccati dal filtro posta indesiderata:

   - **Filtra i messaggi di posta elettronica scritti nelle lingue seguenti**: questa impostazione è disattivata per impostazione predefinita (**Stato: DISATTIVATO**). Fare clic su **Modifica**. Nel riquadro a comparsa **Impostazioni della posta indesiderata internazionale** visualizzato, configurare le impostazioni seguenti:

     - **Filtra i messaggi di posta elettronica scritti nelle lingue seguenti**: selezionare la casella di controllo per abilitare questa impostazione. Per disattivarla, deselezionare la casella di controllo.

     - Fare clic nella casella e iniziare a digitare il *nome* della lingua. Viene visualizzato un elenco filtrato di lingue supportate, insieme al codice della lingua ISO 639-2 corrispondente. Una volta trovata la lingua cercata, selezionarla. Ripetere questo passaggio tutte le volte necessarie.

       L'elenco delle lingue selezionate viene visualizzato nel riquadro a comparsa. Per eliminare una lingua, fare clic su ![Pulsante Rimuovi](../../media/scc-remove-icon.png).

     Al termine, scegliere **Salva**.

   - **Filtra i messaggi di posta elettronica inviati dai paesi o aree geografiche seguenti**: questa impostazione è disattivata per impostazione predefinita (**Stato: DISATTIVATO**). Per attivarla, fare clic su **Modifica**. Nel riquadro a comparsa **Impostazioni della posta indesiderata internazionale** visualizzato, configurare le impostazioni seguenti:

     - **Filtra i messaggi di posta elettronica inviati dai paesi o aree geografiche seguenti**: selezionare la casella di controllo per abilitare questa impostazione. Per disattivarla, deselezionare la casella di controllo.

     - Fare clic nella casella e iniziare a digitare il *nome* del paese o area geografica. Viene visualizzato un elenco filtrato di paesi supportati, insieme al codice del paese di due lettere in base a ISO 3166-1 corrispondente. Una volta trovato il paese o l'area geografica cercati, selezionarli. Ripetere questo passaggio tutte le volte necessarie.

       L'elenco dei paesi selezionati viene visualizzato nel riquadro a comparsa. Per eliminare un paese o un'area geografica, fare clic su ![Pulsante Rimuovi](../../media/scc-remove-icon.png).

     Al termine, scegliere **Salva**.

8. La sezione **Proprietà posta indesiderata** facoltativa contiene impostazioni per il filtro posta indesiderata avanzato disattivate per impostazione predefinita. Le impostazioni ASF per il filtro posta indesiderata avanzato sono in fase di deprecazione e le loro funzionalità vengono integrate in altre parti dello stack di filtro. È consigliabile chiudere tutte le impostazioni per il filtro posta indesiderata avanzato disattivate nei criteri di protezione dalla posta indesiderata.

   Per informazioni dettagliate su queste impostazioni, vedere [Impostazioni per il filtro posta indesiderata avanzato in EOP](advanced-spam-filtering-asf-options.md).

9. (Obbligatorio) Espandere la sezione **Si applica a** per identificare i destinatari interni cui si applica il criterio.

    È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione. Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_). Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).

    È più facile fare clic su **Aggiungi una condizione** tre volte per visualizzare tutte le condizioni disponibili. È possibile fare clic su ![Pulsante Rimuovi](../../media/scc-remove-icon.png) per rimuovere le condizioni che non si vogliono configurare.

    - **Il dominio del destinatario è**: specifica i destinatari in uno o più dei domini configurati accettati nell'organizzazione. Fare clic sulla casella **Aggiungi un tag** per visualizzare e selezionare un dominio. Fare nuovamente clic sulla casella **Aggiungi un tag** per selezionare altri domini se è disponibile più di un dominio.

    - **Il destinatario è**: specifica una o più cassette postali, utenti di posta o contatti di posta specificati nell'organizzazione. Fare clic su **Aggiungi un tag** e iniziare a digitare per filtrare l'elenco. Fare nuovamente clic sulla casella **Aggiungi un tag** per selezionare altri destinatari.

    - **Il destinatario è un membro di**: specifica uno o più gruppi nell'organizzazione. Fare clic su **Aggiungi un tag** e iniziare a digitare per filtrare l'elenco. Fare nuovamente clic sulla casella **Aggiungi un tag** per selezionare altri destinatari.

    - **Tranne quando**: per aggiungere eccezioni alla regola, fare clic su **Aggiungi una condizione** tre volte per visualizzare tutte le eccezioni disponibili. Impostazioni e comportamento sono equivalenti alle condizioni.

10. Al termine, scegliere **Salva**.

## <a name="use-the-security--compliance-center-to-view-anti-spam-policies"></a>Utilizzare il Centro sicurezza e conformità per visualizzare criteri di protezione dalla posta indesiderata

1. Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.

2. Nella pagina **Impostazioni di filtro della posta indesiderata**, fare clic su ![Icona Espandi](../../media/scc-expand-icon.png) per espandere un criterio di protezione dalla posta indesiderata:

   - Il criterio predefinito denominato **Criteri predefiniti di filtro della posta indesiderata**.

   - Un criterio personalizzato creato dall'utente in cui il valore nella colonna **Tipo** è **Criterio di protezione dalla posta indesiderata personalizzato**.

3. Le importanti impostazioni dei criteri vengono visualizzate nei dettagli dei criteri espansi visualizzati. Per visualizzare altri dettagli, fare clic su **Modifica criterio**.

## <a name="use-the-security--compliance-center-to-modify-anti-spam-policies"></a>Utilizzare il Centro sicurezza e conformità per modificare criteri di protezione dalla posta indesiderata

1. Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.

2. Nella pagina **Impostazioni di filtro della posta indesiderata**, fare clic su ![Icona Espandi](../../media/scc-expand-icon.png) per espandere un criterio di protezione dalla posta indesiderata:

   - Il criterio predefinito denominato **Criteri predefiniti di filtro della posta indesiderata**.

   - Un criterio personalizzato creato dall'utente in cui il valore nella colonna **Tipo** è **Criterio di protezione dalla posta indesiderata personalizzato**.

3. Fare clic su **Modifica criterio**.

Per i criteri di protezione dalla posta indesiderata personalizzati, le impostazioni disponibili nel riquadro a comparsa sono identiche a quelle descritte nella sezione [Utilizzare il Centro sicurezza e conformità per creare criteri di protezione dalla posta indesiderata](#use-the-security--compliance-center-to-create-anti-spam-policies).

Per il criterio di protezione dalla posta indesiderata predefinito denominato **Criteri predefiniti di filtro della posta indesiderata**, la sezione **Si applica a** non è disponibile (il criterio si applica a tutti gli utenti) e non è possibile rinominare il criterio.

Per abilitare o disabilitare un criterio, impostare l'ordine di priorità dei criteri o configurare le notifiche di quarantena per gli utenti finali. Vedere le sezioni seguenti.

### <a name="enable-or-disable-anti-spam-policies"></a>Abilitare o disabilitare criteri di protezione dalla posta indesiderata

1. Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.

2. Nella pagina **Impostazioni di filtro della posta indesiderata**, fare clic su ![Icona Espandi](../../media/scc-expand-icon.png) per espandere un criterio personalizzato creato dall'utente (il valore nella colonna **Tipo** è **Criterio di protezione dalla posta indesiderata personalizzato**).

3. Nei dettagli dei criteri espansi visualizzati, notare il valore nella colonna **Attivo**.

   Spostare l'interruttore a sinistra per disabilitare il criterio: ![Disattiva](../../media/scc-toggle-off.png)

   Spostare l'interruttore a destra per abilitare il criterio: ![Attiva](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

Non è possibile disabilitare il criterio di protezione dalla posta indesiderata predefinito.

### <a name="set-the-priority-of-custom-anti-spam-policies"></a>Impostare la priorità dei criteri di protezione dalla posta indesiderata personalizzati

Per impostazione predefinita, ai criteri di protezione dalla posta indesiderata viene assegnata una priorità che si basa sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità più bassa rispetto a quelli precedenti). Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa). Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.

Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).

I criteri di protezione dalla posta indesiderata personalizzati vengono visualizzati nell'ordine in cui sono elaborati (il primo criterio contiene il valore **Priority** 0). Il criterio di protezione dalla posta indesiderata predefinito denominato **Criteri predefiniti di filtro della posta indesiderata** contiene il valore di priorità **Lowest** che non è possibile modificare.

 **Nota**: nel Centro sicurezza e conformità è possibile cambiare solo la priorità del criterio di protezione dalla posta indesiderata dopo averlo creato. In PowerShell, è possibile sovrascrivere la priorità predefinita quando si crea la regola di filtro della posta indesiderata (che può interessare la priorità delle regole esistenti).

Per modificare la priorità di un criterio, spostare il criterio più in alto o più in basso nell'elenco (non è possibile modificare direttamente il numero **Priority** nel Centro sicurezza e conformità).

1. Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.

2. Nella pagina **Impostazioni di filtro della posta indesiderata**, individuare i criteri in cui il valore nella colonna **Tipo** è **Criterio di protezione dalla posta indesiderata personalizzato**. Notare i valori nella colonna **Priorità**:

   - Il criterio di protezione dalla posta indesiderata personalizzato con la priorità più alta, ha il valore ![icona Freccia GIÙ](../../media/ITPro-EAC-DownArrowIcon.png) **0**.

   - Il criterio di protezione dalla posta indesiderata personalizzato con la priorità più bassa, ha il valore ![icona Freccia SU](../../media/ITPro-EAC-UpArrowIcon.png) **n**, ad esempio ![icona Freccia SU](../../media/ITPro-EAC-UpArrowIcon.png) **3**.

   - Se si hanno tre o più criteri di protezione dalla posta indesiderata personalizzati, i criteri tra la priorità più alta e quella più bassa hanno valori ![icona Freccia SU](../../media/ITPro-EAC-UpArrowIcon.png)![icona Freccia GIÙ](../../media/ITPro-EAC-DownArrowIcon.png) **n** (ad esempio, ![icona Freccia SU](../../media/ITPro-EAC-UpArrowIcon.png)![icona Freccia GIÙ](../../media/ITPro-EAC-DownArrowIcon.png) **2**).

3. Fare clic su ![Icona Freccia SU](../../media/ITPro-EAC-UpArrowIcon.png) oppure ![Icona Freccia GIÙ](../../media/ITPro-EAC-DownArrowIcon.png) per spostare i criteri di protezione dalla posta indesiderata personalizzati più in alto o più in basso nell'elenco delle priorità.

### <a name="configure-end-user-spam-notifications"></a>Configurare le notifiche di posta indesiderata dell'utente finale

Quando un verdetto filtro posta indesiderata mette in quarantena un messaggio, è possibile configurare le notifiche di posta indesiderata per l'utente finale per informare i destinatari su quanto accaduto ai messaggi a loro destinati. Per altre informazioni sulle notifiche, vedere [Notifiche di posta indesiderata per l'utente finale in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).

1. Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.

2. Nella pagina **Impostazioni di filtro della posta indesiderata**, fare clic su ![Icona Espandi](../../media/scc-expand-icon.png) per espandere un criterio di protezione dalla posta indesiderata:

   - Il criterio predefinito denominato **Criteri predefiniti di filtro della posta indesiderata**.

   - Un criterio personalizzato creato dall'utente in cui il valore nella colonna **Tipo** è **Criterio di protezione dalla posta indesiderata personalizzato**.

3. Nei dettagli dei criteri espansi visualizzati, fare clic su **Configurare le notifiche di posta indesiderata dell'utente finale**.

4. Nella finestra di dialogo **\<Policy Name\>** che si apre, configurare le seguenti impostazioni:

   - **Abilitare le notifiche di posta indesiderata per l'utente finale**: selezionare la casella di controllo per abilitare le notifiche. Per disattivare le notifiche, deselezionare la casella di controllo.

   - **Invia notifiche di posta indesiderata per l'utente finale ogni (giorni):**: selezionare la frequenza di invio delle notifiche. Il valore predefinito è 3 giorni. È possibile immettere da 1 a 15 giorni.

     Sono presenti 3 cicli di notifica della posta indesiderata dell'utente finale entro un periodo di 24 ore, che iniziano agli orari seguenti: 01:00 UTC, 08:00 UTC e 16:00 UTC.

     > [!NOTE]
     > Se una notifica durante risulta mancante durante un ciclo precedente, ne verrà eseguito il push in un ciclo successivo. Ciò può dare l'impressione di ricevere più notifiche nello stesso giorno.

   - **Lingua delle notifiche**: fare clic sul menu a discesa e selezionare una lingua disponibile dall'elenco. Il valore predefinito è **Predefinito**, ovvero l'inglese.

   Al termine, scegliere **Salva**.

## <a name="use-the-security--compliance-center-to-remove-anti-spam-policies"></a>Utilizzare il Centro sicurezza e conformità per rimuovere criteri di protezione dalla posta indesiderata

1. Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.

2. Nella pagina **Impostazioni di filtro della posta indesiderata**, fare clic su ![Icona Espandi](../../media/scc-expand-icon.png) per espandere il criterio personalizzato da eliminare (la colonna **Tipo** è **Criterio di protezione dalla posta indesiderata personalizzato**).

3. Nei dettagli sui criteri espansi visualizzati, fare clic su **Elimina criterio**.

4. Fare clic su **Sì** quando viene visualizzata la finestra di dialogo di avviso.

Non è possibile rimuovere il criterio predefinito.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a>Utilizzare PowerShell per Exchange Online o PowerShell di EOP autonomo per configurare criteri di protezione dalla posta indesiderata

Come descritto in precedenza, una criterio di posta indesiderata consiste in un criterio di filtro di posta indesiderata e una regola di filtro di posta indesiderata.

In PowerShell per Exchange Online o PowerShell di EOP autonomo è evidente la differenza tra i criteri di filtro della posta indesiderata e le regole di filtro della posta indesiderata. Gestire i criteri di filtro della posta indesiderata usando i cmdlet **\*-HostedContentFilterPolicy** e le regole di filtro della posta indesiderata usando i cmdlet **\*-HostedContentFilterRule**.

- In PowerShell, creare innanzitutto il criterio di filtro della posta indesiderata, quindi creare la regola di filtro della posta indesiderata che identifica il criterio cui viene applicata la regola.
- In PowerShell, modificare le impostazioni nel criterio di filtro della posta indesiderata e la regola di filtro della posta indesiderata separatamente.
- Quando si rimuove un criterio di filtro della posta indesiderata da PowerShell, la regola di filtro della posta indesiderata corrispondente non viene rimossa automaticamente, e viceversa.

Le impostazioni dei criteri contro la posta indesiderata seguenti sono disponibili solo in PowerShell:

- Il parametro _MarkAsSpamBulkMail_ è `On` per impostazione predefinita. Gli effetti di questa impostazione sono illustrati nella sezione precedente [Utilizzare il Centro sicurezza e conformità per creare criteri di protezione dalla posta indesiderata](#use-the-security--compliance-center-to-create-anti-spam-policies) in questo argomento.

- Le impostazioni seguenti per le notifiche di quarantena della posta indesiderata dell'utente finale:

  - Il parametro _DownloadLink_ che mostra o nasconde il collegamento allo strumento per la segnalazione delle e-mail indesiderate di Outlook.

  - Il parametro _EndUserSpamNotificationCustomSubject_ consente di personalizzare la riga dell'oggetto della notifica.

### <a name="use-powershell-to-create-anti-spam-policies"></a>Utilizzare PowerShell per creare criteri di protezione dalla posta indesiderata

La creazione di un criterio di protezione dalla posta indesiderata in PowerShell è un processo che prevede due passaggi:

1. Creare il criterio di filtro della posta indesiderata.
2. Creare la regola di filtro della posta indesiderata che specifica il criterio di filtro della posta indesiderata cui viene applicata la regola.

 **Note**:

- è possibile creare una nuova regola di filtro della posta indesiderata e assegnarvi un criterio di filtro della posta indesiderata esistente e non associato. Una regola di filtro della posta indesiderata non può essere associata a più di un criterio di filtro della posta indesiderata.

- È possibile configurare le impostazioni seguenti nei nuovi criteri di filtro della posta indesiderata in PowerShell che non sono disponibili nel Centro sicurezza e conformità finché non si crea il criterio:

  - Creare il nuovo criterio come disabilitato (_Abilitato_ `$false` nel cmdlet **New-HostedContentFilterRule**).
  - Impostare la priorità del criterio durante la creazione (_Priorità_ _\<Number\>_) nel cmdlet **New-HostedContentFilterRule**).

- Il nuovo criterio di filtro della posta indesiderata creato in PowerShell non sarà visibile nel Centro sicurezza e conformità finché non vi verrà assegnata una regola di filtro della posta indesiderata.

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a>Passaggio 1 - Utilizzo di PowerShell per creare criteri di filtro della posta indesiderata

Per creare un criterio di filtro della posta indesiderata, utilizzare questa sintassi:

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

In questo esempio viene creato un criterio di filtro della posta indesiderata denominato Contoso Executives con le impostazioni seguenti:

- Mettere i messaggi in quarantena quando il verdetto filtro posta indesiderata indica posta indesiderata o alta probabilità di posta indesiderata.

- Il livello di reclamo di blocco 6 attiva l'azione per un verdetto filtro posta indesiderata della posta elettronica inviata in massa.

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

> [!NOTE]
> **New-HostedContentFilterPolicy** e **Set-HostedContentFilterPolicy** contengono un parametro precedente _ZapEnabled_, un parametro più recente _PhishZapEnabled_ e i parametri _SpamZapEnabled_. Il parametro _ZapEnabled_ è stato dichiarato obsoleto a febbraio 2020. I parametri _PhishZapEnabled_ e _SpamZapEnabled_ ereditavano i propri valori dal parametro _ZapEnabled_. Tuttavia, se si utilizzano i parametri _PhishZapEnabled_ e _SpamZapEnabled_ in un comando o si utilizzano le impostazioni **ZAP della posta indesiderata** o **ZAP del phishing** nei criteri di protezione dalla posta indesiderata nel Centro sicurezza e conformità, il valore del parametro _ZapEnabled_ viene ignorato. In altre parole, non utilizzare il parametro _ZapEnabled_. Utilizzare, invece, i parametri _PhishZapEnabled_ e _SpamZapEnabled_.

Per informazioni dettagliate su sintassi e parametri, vedere [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).

#### <a name="step-2-use-powershell-to-create-a-spam-filter-rule"></a>Passaggio 2 - Utilizzo di PowerShell per creare una regola di filtro della posta indesiderata

Per creare una regola di filtro della posta indesiderata, utilizzare questa sintassi:

```PowerShell
New-HostedContentFilterRule -Name "<RuleName>" -HostedContentFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In questo esempio viene creata una nuova regola di filtro della posta indesiderata denominata Contoso Executives con queste impostazioni:

- Il criterio di filtro della posta indesiderata denominato Contoso Executives è associato alla regola.

- La regola viene applicata ai membri del gruppo Contoso Executives Group.

```PowerShell
New-HostedContentFilterRule -Name "Contoso Executives" -HostedContentFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

Per informazioni dettagliate su sintassi e parametri, vedere [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterrule).

### <a name="use-powershell-to-view-spam-filter-policies"></a>Utilizzo di PowerShell per visualizzare criteri di filtro della posta indesiderata

Per visualizzare un elenco riepilogativo di tutti i criteri di filtro della posta indesiderata, eseguire questo comando:

```PowerShell
Get-HostedContentFilterPolicy
```

Per visualizzare informazioni dettagliate su un criterio di filtro della posta indesiderata specifico, utilizzare questa sintassi:

```PowerShell
Get-HostedContentFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

In questo esempio vengono visualizzati tutti i valori delle proprietà per il criterio di filtro della posta indesiderata denominato Executives.

```PowerShell
Get-HostedContentFilterPolicy -Identity "Executives" | Format-List
```

Per informazioni dettagliate su sintassi e parametri, vedere [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).

### <a name="use-powershell-to-view-spam-filter-rules"></a>Utilizzo di PowerShell per visualizzare regole di filtro della posta indesiderata

Per visualizzare le regole di filtro della posta indesiderata esistenti, usare la sintassi seguente:

```PowerShell
Get-HostedContentFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

Per visualizzare un elenco riepilogativo di tutte le regole di filtro della posta indesiderata, eseguire questo comando:

```PowerShell
Get-HostedContentFilterRule
```

Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:

```PowerShell
Get-HostedContentFilterRule -State Disabled
```

```PowerShell
Get-HostedContentFilterRule -State Enabled
```

Per visualizzare informazioni dettagliate su una regola di filtro della posta indesiderata specifica, utilizzare questa sintassi:

```PowerShell
Get-HostedContentFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

In questo esempio vengono visualizzati tutti i valori delle proprietà per la regola di filtro della posta indesiderata denominata Contoso Executives.

```PowerShell
Get-HostedContentFilterRule -Identity "Contoso Executives" | Format-List
```

Per informazioni dettagliate su sintassi e parametri, vedere [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterrule).

### <a name="use-powershell-to-modify-spam-filter-policies"></a>Utilizzo di PowerShell per modificare criteri di filtro della posta indesiderata

Oltre agli elementi seguenti, le stesse impostazioni sono disponibili quando si modificano i criteri di filtro della posta indesiderata in PowerShell e quando si creano i criteri come descritto nella sezione precedente [Passaggio 1 - Utilizzo di PowerShell per creare criteri di filtro della posta indesiderata](#step-1-use-powershell-to-create-a-spam-filter-policy) in questo argomento.

- Il parametro _MakeDefault_ che trasforma il criterio specificato nel criterio predefinito (si applica a tutti gli utenti, sempre priorità **Lowest** e non è possibile eliminarlo) è disponibile solo quando si modifica un criterio di filtro della posta indesiderata in PowerShell.

- Non è possibile rinominare un criterio di filtro della posta indesiderata (il cmdlet **Set-HostedContentFilterPolicy** non contiene il parametro _Name_). Quando si rinomina un criterio di protezione dalla posta indesiderata nel Centro sicurezza e conformità, si rinomina solamente la _regola_ di filtro della posta indesiderata.

Per modificare un criterio di filtro della posta indesiderata, utilizzare questa sintassi:

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

Per informazioni dettagliate su sintassi e parametri, vedere [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).

### <a name="use-powershell-to-modify-spam-filter-rules"></a>Utilizzo di PowerShell per modificare regole di filtro della posta indesiderata

L'unica impostazione non disponibile quando si modifica una regola di filtro della posta indesiderata in PowerShell è il parametro _Enabled_, che consente di creare una regola disabilitata. Per abilitare o disabilitare le regole di filtro della posta indesiderata esistenti, vedere la sezione successiva.

In caso contrario, non saranno disponibili altre impostazioni quando si modifica una regola di filtro della posta indesiderata in PowerShell. Le stesse impostazioni sono disponibili quando si crea una regola come descritto nella sezione precedente [Passaggio 2 - Utilizzo di PowerShell per creare una regola di filtro della posta indesiderata](#step-2-use-powershell-to-create-a-spam-filter-rule) in questo argomento.

Per modificare una regola di filtro della posta indesiderata, utilizzare questa sintassi:

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

In questo esempio viene rinominata la regola di filtro della posta indesiderata esistente denominata `{Fabrikam Spam Filter}` che potrebbe causare problemi nel Centro sicurezza e conformità.

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

Per informazioni dettagliate su sintassi e parametri, vedere [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterrule).

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a>Utilizzo di PowerShell per abilitare o disabilitare le regole di filtro della posta indesiderata

L'abilitazione o la disabilitazione di una regola di filtro della posta indesiderata in PowerShell, consente di abilitare o disabilitare l'intero criterio di protezione dalla posta indesiderata (la regola di filtro della posta indesiderata e il criterio di filtro dalla posta indesiderata assegnato). Non è possibile abilitare o disabilitare i criteri di protezione dalla posta indesiderata predefiniti, (sempre applicati a tutti i destinatari).

Per abilitare o disabilitare una regola di filtro della posta indesiderata in PowerShell, utilizzare questa sintassi:

```PowerShell
<Enable-HostedContentFilterRule | Disable-HostedContentFilterRule> -Identity "<RuleName>"
```

In questo esempio viene disabilitata la regola di filtro della posta indesiderata denominata Marketing Department.

```PowerShell
Disable-HostedContentFilterRule -Identity "Marketing Department"
```

In questo esempio viene abilitata la stessa regola.

```PowerShell
Enable-HostedContentFilterRule -Identity "Marketing Department"
```

Per informazioni dettagliate su sintassi e parametri, vedere [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedcontentfilterrule) e [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedcontentfilterrule).

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a>Utilizzare PowerShell per impostare una priorità sulle regole di filtro della posta indesiderata

Il valore di priorità più alto che è possibile impostare in una regola è 0. Il valore più basso che è possibile impostare dipende dal numero di regole. Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4. Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole. Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola su 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.

Per impostare la priorità di una regola di filtro della posta indesiderata in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).

```PowerShell
Set-HostedContentFilterRule -Identity "Marketing Department" -Priority 2
```

**Note**:

- per impostare la priorità di una nuova regola al momento della creazione, utilizzare invece il parametro _Priority_ nel cmdlet **New-HostedContentFilterRule**.

- Il criterio di filtro della posta indesiderata predefinito non contiene una regola di filtro della posta indesiderata corrispondente e contiene sempre il valore di priorità **Lowest** non modificabile.

### <a name="use-powershell-to-remove-spam-filter-policies"></a>Utilizzo di PowerShell per rimuovere criteri di filtro della posta indesiderata

Quando si rimuove un criterio di filtro della posta indesiderata tramite PowerShell, la regola di filtro della posta desiderata corrispondente non viene rimossa.

Per rimuovere un criterio di filtro della posta indesiderata in PowerShell, utilizzare questa sintassi:

```PowerShell
Remove-HostedContentFilterPolicy -Identity "<PolicyName>"
```

In questo esempio viene rimosso il criterio di filtro della posta indesiderata denominato Marketing Department.

```PowerShell
Remove-HostedContentFilterPolicy -Identity "Marketing Department"
```

Per informazioni dettagliate su sintassi e parametri, vedere [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterpolicy).

### <a name="use-powershell-to-remove-spam-filter-rules"></a>Utilizzo di PowerShell per rimuovere regole di filtro della posta indesiderata

Quando si rimuove una regola di filtro della posta indesiderata tramite PowerShell, il criterio di filtro della posta desiderata corrispondente non viene rimosso.

Per rimuovere una regola di filtro della posta indesiderata in PowerShell, utilizzare questa sintassi:

```PowerShell
Remove-HostedContentFilterRule -Identity "<PolicyName>"
```

In questo esempio viene rimossa la regola di filtro della posta indesiderata denominata Marketing Department.

```PowerShell
Remove-HostedContentFilterRule -Identity "Marketing Department"
```

Per informazioni dettagliate su sintassi e parametri, vedere [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterrule).

## <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a>Inviare un messaggio GTUBE per verificare le impostazioni dei criteri contro la posta indesiderata

> [!NOTE]
> Questi passaggi funzioneranno solo se l'organizzazione di posta elettronica da cui si sta inviando il messaggio GTUBE non ricerca posta indesiderata in uscita. In caso contrario, il messaggio di prova non potrà essere inviato.

Il test GTUBE (Generic Test for Unsolicited Bulk Email) è una stringa di testo da includere in un messaggio di prova per verificare le impostazioni di protezione dalla posta indesiderata dell'organizzazione. Un messaggio GTUBE è simile al file di testo EICAR (European Institute for Computer Antivirus Research) per la verifica delle impostazioni antimalware.

Includere il seguente testo GTUBE in un messaggio di posta elettronica o in una singola riga, senza spazi o interruzioni di riga:

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="allowblock-lists"></a>Elenchi di elementi consentiti/bloccati

A volte i filtri non riescono a bloccare i messaggi o impiegano molto tempo a farlo. In questi casi, i criteri di protezione dalla posta indesiderata presentano Elenchi di elementi consentiti/bloccati per ignorare il verdetto corrente. Questa opzione deve essere usata solo in modo parsimonioso, perché gli elenchi possono diventare ingestibili e temporaneamente perché il nostro stack di filtri deve svolgere il proprio lavoro.

> [!TIP]
> Ci potrebbero essere situazioni in cui l'organizzazione potrebbe non concordare con il verdetto fornito dal servizio. In questo caso, è consigliabile mantenere permanenti gli elenchi di elementi consentiti o bloccati. Tuttavia, se si vuole inserire un dominio nell'elenco di quelli consentiti per un periodo di tempo prolungato, è consigliabile indicare al mittente di verificare che il proprio dominio sia autenticato e impostato su DMARC, rifiutare se non lo è.
