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
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: Informazioni per amministratori su come visualizzare, creare, modificare ed eliminare criteri di protezione dalla posta indesiderata in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 910923e693804c96c109c52606b62d92af51abeb
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228664"
---
# <a name="configure-anti-spam-policies-in-eop"></a>Configurare criteri di protezione dalla posta indesiderata in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, i messaggi di posta elettronica in ingresso vengono protetti automaticamente dalla posta indesiderata da EOP. Come parte del sistema di difesa dell'organizzazione, EOP utilizza criteri di protezione dalla posta indesiderata, noti anche come criteri di filtro della posta indesiderata o criteri di filtro di contenuti. Per altre informazioni, vedere [Protezione dalla posta indesiderata](anti-spam-protection.md).

Gli amministratori possono visualizzare, modificare e configurare, ma non eliminare, il criterio di protezione dalla posta indesiderata predefinito. Per una maggiore granularità, è anche possibile creare criteri di protezione dalla posta indesiderata personalizzati applicabili a utenti, gruppi o domini specifici nell'organizzazione. I criteri personalizzati hanno sempre la precedenza sul criterio predefinito, ma non è possibile modificarne la priorità (in funzione).

È possibile configurare criteri di protezione dalla posta indesiderata nel portale di Microsoft 365 Defender o in PowerShell (PowerShell di Exchange Online per organizzazioni di Microsoft 365 con cassette postali in Exchange Online; PowerShell di EOP autonomo per organizzazioni prive di cassette postali di Exchange Online).

Gli elementi di base del criterio di protezione dalla posta indesiderata sono:

- **Criterio di filtro della posta indesiderata**: specifica le azioni per i verdetti filtro posta indesiderata e le opzioni di notifica.
- **Regola di filtro della posta indesiderata**: specifica la priorità e i filtri destinatario (a chi si applica il criterio) per un criterio di filtro della posta indesiderata.

La differenza tra questi due elementi non è ovvia quando si gestiscono criteri di protezione dalla posta indesiderata nel portale di Microsoft 365 Defender:

- Quando si crea un criterio di protezione dalla posta indesiderata, in contemporanea viene creata una regola di filtro della posta indesiderata e il criterio di filtro della posta indesiderata associato, utilizzando lo stesso nome per entrambi.
- Quando si modifica un criterio di protezione dalla posta indesiderata, le impostazioni relative a nome, priorità, attivazione o disattivazione e filtri destinatari modificano la regola di filtro della posta indesiderata. Tutte le altre impostazioni modificano il criterio di filtro della posta indesiderata associato.
- Quando si rimuovono il criterio di protezione dalla posta indesiderata, la regola di filtro della posta indesiderata e il criterio di filtro della posta indesiderata vengono rimossi.

In PowerShell di Exchange Online o in EOP PowerShell autonomo i criteri e la regola vengono gestiti separatamente. Per altre informazioni, vedere [Usare PowerShell di Exchange Online o EOP di PowerShell autonomo per configurare i criteri di posta indesiderata](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies) nella sezione successiva in questo articolo.

Ogni organizzazione ha un criterio incorporato per la posta indesiderata, denominato Predefinito, aventi le seguenti proprietà:

- Il criterio viene applicato a tutti i destinatari dell'organizzazione, anche se non esiste alcuna regola di filtro della posta indesiderata (filtri destinatari) associata al criterio.
- Il valore personalizzato della priorità del criterio è **Minore** e non può essere modificato (il criterio viene sempre applicato per ultimo). Qualsiasi criterio personalizzato creato avrà sempre una priorità più alta.
- Il criterio è quello predefinito (la proprietà **IsDefault** contiene il valore `True`), e non è possibile eliminarlo.

Per aumentare l'efficacia del filtro della posta indesiderata, è possibile creare criteri di protezione dalla posta indesiderata con impostazioni più restrittive da applicare a utenti o gruppi di utenti specifici.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Per aprire il portale di Microsoft 365 Defender, andare alla pagina <https://security.microsoft.com>. Per passare direttamente alla pagina **Criteri di protezione dalla posta indesiderata**, usare <https://security.microsoft.com/antispam>.

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in **Exchange Online**:
  - Per aggiungere, modificare ed eliminare criteri di protezione dalla posta indesiderata, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **Amministratore della sicurezza**.
  - Per l'accesso in sola lettura ai criteri di protezione da posta indesiderata, è necessario avere il **ruolo con autorizzazioni di lettura globali** o il **ruolo con autorizzazioni di lettura per la sicurezza**.

  Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Note**:

  - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).
  - Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.

- Per le impostazioni consigliate per i criteri contro la posta indesiderata, vedere [Impostazioni dei criteri di protezione dalla posta indesiderata di EOP](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-spam-policies"></a>Usare il portale di Microsoft 365 Defender per creare criteri di protezione dalla posta indesiderata

La creazione di un criterio di protezione dalla posta indesiderata nel portale di Microsoft 365 Defender permette di creare contemporaneamente una regola di filtro della posta indesiderata e il criterio di filtro della posta indesiderata associato, usando lo stesso nome per entrambi.

1. Nel portale di Microsoft 365 Defender passare a **Email e collaborazione** \> **Criteri e regole** \> pagina **Criteri delle minacce** \> **sezione** Criteri \> **Protezione posta indesiderata**.

2. Nella pagina **Criteri protezione posta indesiderata** fare clic su ![Crea icona](../../media/m365-cc-sc-create-icon.png) **Crea criteri** e quindi selezionare **In ingresso** nell'elenco a discesa.

3. Viene aperta la creazione guidata criteri. Nella pagina **Assegna un nome alla pagina criteri** configurare queste impostazioni:
   - **Nome**: immettere un nome univoco descrittivo per il criterio.
   - **Descrizione**: immettere una descrizione opzionale per il criterio.

   Al termine dell'operazione, fare clic su **Avanti**.

4. Nella pagina **Utenti, gruppi e domini** visualizzata identificare i destinatari interni a cui si applicano i criteri (condizioni del destinatario):
   - **Utenti**: la cassette postali specificate, utenti di posta o contatti di posta specificati nell'organizzazione.
   - **Gruppi**: i gruppi di distribuzione specificati, gruppi di sicurezza abilitati alla posta elettronica o gruppi di Microsoft 365 nell'organizzazione.
   - **Domini**: tutti i destinatari nei domini specificati [accettati](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) nell'organizzazione.

   Fare clic nella casella appropriata, iniziare a digitare un valore e selezionare il valore desiderato nei risultati. Ripetere questa procedura tutte le volte necessarie. Per rimuovere un valore esistente, fare clic su Rimuovi ![Icona Rimuovi](../../media/m365-cc-sc-remove-selection-icon.png) accanto al valore.

   Per utenti o gruppi è possibile usare la maggior parte degli identificatori, ad esempio nome, nome visualizzato, alias, indirizzo di posta elettronica, nome dell'account e così via, ma il nome visualizzato corrispondente viene visualizzato nei risultati. Per gli utenti, immettere un asterisco (\*) da solo per visualizzare tutti i valori disponibili.

   Più valori della stessa condizione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_). Condizioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).

   - **Escludere questi utenti, gruppi e domini**: per aggiungere eccezioni ai destinatari interni a cui si applicano i criteri (eccezione destinatari), selezionare questa opzione e configurare le eccezioni. Impostazioni e comportamento sono equivalenti alle condizioni.

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nella pagina visualizzata **Soglia di posta elettronica inviata in blocco e proprietà posta indesiderata** configurare le impostazioni seguenti:

   - **Soglia di posta elettronica inviata in blocco**: specificare il livello di reclamo in blocco di un messaggio che attiva l'azione specificata per il verdetto di filtro della posta indesiderata **In blocco** configurato nella pagina successiva (maggiore del valore specificato, non maggiore di o uguale a). Un valore alto indica che il messaggio è meno opportuno (probabilmente un messaggio di posta indesiderata). Il valore predefinito è 7. Per altre informazioni, vedere [Livello di reclamo in blocco in EOP](bulk-complaint-level-values.md) e [Qual è la differenza tra posta indesiderata e posta inviata in massa?](what-s-the-difference-between-junk-email-and-bulk-email.md).

     Per impostazione predefinita, l'impostazione solo PowerShell _MarkAsSpamBulkMail_ è `On` nei criteri di protezione dalla posta indesiderata. Questa impostazione influisce molto sui risultati di un verdetto filtro **In massa**:

     - **_MarkAsSpamBulkMail_ è attivo**: un livello di reclamo di blocco maggiore della soglia viene convertito in un livello di probabilità di posta indesiderata 6 che corrisponde a un verdetto filtro **Posta indesiderata** e sul messaggio viene eseguita l'azione per il verdetto filtro **In blocco**.
     - **_MarkAsSpamBulkMail_ è disattivato**: il messaggio viene contrassegnato con il livello di reclamo di blocco, ma _nessuna azione_ viene eseguita per un verdetto filtro **In blocco**. In effetti, la soglia del livello di reclamo di blocco e l'azione verdetto filtro **In blocco** sono irrilevanti.

   - **Aumenta il punteggio di posta indesiderata**, **Contrassegna come posta indesiderata**<sup>\*</sup> e **Modalità di test**: contiene le impostazioni del filtro avanzato della posta indesiderata (ASF) che sono disattivate per impostazione predefinita. Le impostazioni ASF per il filtro posta indesiderata avanzato sono in fase di deprecazione e le loro funzionalità vengono integrate in altre parti dello stack di filtro. È consigliabile chiudere tutte le impostazioni per il filtro posta indesiderata avanzato disattivate nei criteri di protezione dalla posta indesiderata.

     Per informazioni dettagliate su queste impostazioni, vedere [Impostazioni per il filtro posta indesiderata avanzato in EOP](advanced-spam-filtering-asf-options.md).

      <sup>\*</sup> **Contiene lingue specifiche** e **di Paesi che** non fanno parte delle impostazioni ASF.

   - **Contiene lingue specifiche**: fare clic sulla casella e selezionare **On** oppure **Off** nell'elenco a discesa. Se viene attivato, viene visualizzata una casella. Iniziare a digitare il nome di una lingua nella casella. Verrà visualizzato un elenco filtrato delle lingue supportate. Una volta trovata la lingua cercata, selezionarla. Ripetere questo passaggio tutte le volte necessarie. Per rimuovere un valore esistente, fare clic su ![Rimuovi icona](../../media/m365-cc-sc-remove-selection-icon.png) accanto al valore.

   - **Da questi paesi** _: fare clic sulla casella e selezionare _ *On** oppure **Off** nell'elenco a discesa. Se viene attivato, viene visualizzata una casella. Iniziare a digitare il nome di un Paese nella casella. Viene visualizzato un elenco filtrato dei Paesi supportati. Una volta trovato il Paese cercato, selezionarlo. Ripetere questo passaggio tutte le volte necessarie. Per rimuovere un valore esistente, fare clic su ![Rimuovi icona](../../media/m365-cc-sc-remove-selection-icon.png) accanto al valore.

   Al termine dell'operazione, fare clic su **Avanti**.

6. Nella pagina **Azioni** visualizzata configurare le impostazioni seguenti:

   - **Azioni messaggio**: selezionare o esaminare l'azione da eseguire sui messaggi in base ai seguenti verdetti del filtro della posta indesiderata:
     - **Posta indesiderata**
     - **Posta indesiderata con alta confidenza**
     - **Phishing**
     - **Messaggio di phishing altamente riservato**
     - **Invio in blocco**

     Le azioni disponibili per i verdetti filtro posta indesiderata sono descritte nella tabella seguente.

     - Un segno di spunta ( ![Segno di spunta](../../media/checkmark.png) ) indica che l'azione è disponibile (non tutte le azioni sono disponibili per tutti i verdetti).
     - Un asterisco (<sup>\*</sup>) dopo il segno di spunta indica l'azione predefinita per il verdetto filtro posta indesiderata.

     <br>

     ****

     |Azione|Posta indesiderata|Fortemente<br>confidenziale<br>posta indesiderata|Phishing|Fortemente<br>confidenziale<br>phishing|Invio in blocco|
     |---|:---:|:---:|:---:|:---:|:---:|
     |**Spostare un messaggio nella cartella Posta indesiderata**: il messaggio viene recapitato nella cassetta postale e spostato nella cartella Posta indesiderata.<sup>1</sup>|![Segno di spunta](../../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../../media/checkmark.png)||![Segno di spunta](../../media/checkmark.png)<sup>\*</sup>|
     |**Aggiungi X-Header**: aggiunge un X-Header all'intestazione del messaggio e recapita il messaggio nella cassetta postale. <p> Immettere il nome del campo X-Header (non il valore) successivamente nella casella **Aggiungi testo X-Header**. <p> Per i verdetti **Posta indesiderata** e **Posta indesiderata con alta confidenza**, il messaggio viene spostato nella cartella Posta indesiderata.<sup>1,2</sup>|![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)||![Segno di spunta](../../media/checkmark.png)<sup>\*</sup>|
     |**Anteponi testo alla riga dell'oggetto**: aggiunge testo all'inizio della riga dell'oggetto del messaggio. Il messaggio viene recapitato nella cassetta postale e spostato nella cartella Posta indesiderata.<sup>1,2</sup> <p> Immettere il testo successivamente nella casella **Riga dell'oggetto del prefisso con il testo**.|![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)||![Segno di spunta](../../media/checkmark.png)|
     |**Reindirizza messaggio a indirizzo di posta elettronica:** invece di inviare il messaggio ai destinatari designati, lo invia ad altri destinatari. <p> Specificare i destinatari successivamente nella casella **Reindirizza a questo indirizzo di posta elettronica**.|![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|
     |**Elimina messaggio:** elimina automaticamente l'intero messaggio, inclusi gli allegati.|![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)||![Segno di spunta](../../media/checkmark.png)|
     |**Messaggio di quarantena:** il messaggio non viene inviato ai destinatari, ma viene messo in quarantena. <p> Specificare per quanto tempo mantenere il messaggio in quarantena più avanti nella casella **Quarantena**.|![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)<sup>\*</sup>|![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|
     |**Nessuna azione**|||||![Segno di spunta](../../media/checkmark.png)|
     |

     > <sup>1</sup> In Exchange Online, il messaggio viene spostato nella cartella Posta indesiderata se la regola per la posta indesiderata è abilitata per la cassetta postale (abilitata per impostazione predefinita). Per altre informazioni, vedere [Configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).
     >
     > Negli ambienti ibridi in cui EOP protegge le cassette postali di Exchange locali, è necessario configurare le regole del flusso di posta (anche note come regole di trasporto) in Exchange locale per tradurre il verdetto filtro posta indesiderata in modo che la regola della posta indesiderata possa spostare il messaggio nella cartella Posta indesiderata. Per dettagli, vedere [Configurare EOP per recapitare la posta indesiderata nella cartella Posta indesiderata negli ambienti ibridi](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).
     >
     > <sup>2</sup> È possibile usare questo valore come condizione nelle regole del flusso di posta per filtrare o instradare il messaggio.

   - **Conserva la posta indesiderata in quarantena per questo numero di giorni**: specifica per quanto tempo mantenere il messaggio in quarantena se è stato selezionato **Messaggio di quarantena** come azione per il verdetto filtro posta indesiderata. Scaduto il periodo di tempo, il messaggio viene eliminato. Il valore predefinito è 30 giorni. Un valore valido è compreso tra 1 e 30 giorni. Per ulteriori informazioni sulla quarantena, vedere i seguenti argomenti:

     - [Messaggi in quarantena in EOP](quarantine-email-messages.md)
     - [Gestire i messaggi e i file messi in quarantena come amministratore in EOP](manage-quarantined-messages-and-files.md)
     - [Trovare e rilasciare i messaggi messi in quarantena come utente di EOP](find-and-release-quarantined-messages-as-a-user.md)

   - **Aggiungi testo X-Header**: questa casella è obbligatoria e disponibile solo se **Aggiungi X-Header** è stato selezionato come azione per il verdetto filtro posta indesiderata. Il valore specificato è il *nome* del campo di intestazione aggiunto all'intestazione del messaggio. Il *valore* del campo di intestazione è sempre `This message appears to be spam`.

     La lunghezza massima è 255 caratteri e il valore non può contenere spazi e due punti (:).

     Per esempio, se si immette il valore `X-This-is-my-custom-header`, l'opzione X-Header aggiunta al messaggio sarà `X-This-is-my-custom-header: This message appears to be spam.`

     Se si immette un valore che contiene spazi o due punti (:), il valore inserito viene ignorato e l'opzione X-Header viene aggiunta al messaggio (`X-This-Is-Spam: This message appears to be spam.`).

   - **Anteponi testo alla riga dell'oggetto**: questa casella è obbligatoria e disponibile solo se **Anteponi testo alla riga dell'oggetto** è stato selezionato come azione per il verdetto filtro posta indesiderata. Immettere il testo da aggiungere all'inizio della riga dell'oggetto del messaggio.

   - **Reindirizza a questo indirizzo di posta elettronica**: questa casella è obbligatoria e disponibile solo se **Reindirizza il messaggio all'indirizzo di posta elettronica** è stato selezionato come azione per il verdetto filtro posta indesiderata. Immettere l'indirizzo di posta elettronica cui recapitare il messaggio. È possibile immettere più valori separati da punto e virgola (;).

   - **Abilitare suggerimenti per la sicurezza**: per impostazione predefinita, i suggerimenti per la sicurezza sono abilitati, ma è possibile disabilitarli deselezionando la casella di controllo.

   - **Abilitare Zero-Hour Auto Purge (ZAP)**: ZAP rileva ed esegue operazioni sui messaggi già recapitati nelle cassette di posta di Exchange Online. Per altre informazioni vedere [Zero-Hour Auto Purge: protezione contro la posta indesiderata e il malware](zero-hour-auto-purge.md).

     ZAP è attivata per impostazione predefinita. Quando ZAP è attivato, sono disponibili le impostazioni seguenti:

     - **Abilitare ZAP del phishing**: per impostazione predefinita, ZAP è abilitata per il rilevamento del phishing, tuttavia è possibile disabilitarla deselezionando la casella di controllo.
     - **ZAP della posta indesiderata**: per impostazione predefinita, la funzionalità ZAP è abilitata per il rilevamento della posta indesiderata, tuttavia è possibile disabilitarla deselezionando la casella di controllo.

   - **Abilitare le notifiche di posta indesiderata per l'utente finale**: per altre informazioni, vedere la sezione [Configurare le notifiche di posta indesiderata per l'utente finale](#configure-end-user-spam-notifications) più avanti in questo argomento.

   Al termine dell'operazione, fare clic su **Avanti**.

7. Nel riquadro a comparsa **Elenchi elementi consentiti e bloccati** è possibile configurare i mittenti dei messaggi in base all'indirizzo di posta elettronica o al dominio di posta elettronica a cui è consentito ignorare il filtro posta indesiderata.

   Nella sezione **Consentiti** è possibile configurare i mittenti e i domini consentiti. Nella sezione **Bloccati** è possibile aggiungere mittenti e domini bloccati.

   > [!IMPORTANT]
   >
   > Valutare con attenzione prima di aggiungere i domini all'elenco dei domini consentiti. Per altre informazioni, vedere [Creare elenchi di mittenti attendibili in EOP](create-safe-sender-lists-in-office-365.md)
   >
   > Non aggiungere mai [domini accettati](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)propri, o domini comuni, ad esempio microsoft.com o office.com, all'elenco di domini consentiti. Se a questi domini è consentito ignorare il filtro della posta indesiderata, gli utenti malintenzionati possono inviare facilmente messaggi che effettuano lo spoofing di questi domini attendibili nell'organizzazione.
   >
   > Il blocco manuale dei domini mediante l'aggiunta di domini all'elenco dei domini bloccati non è pericoloso, ma può aumentare il carico di lavoro amministrativo. Per altre informazioni, vedere [Creare elenchi di mittenti bloccati in EOP](create-block-sender-lists-in-office-365.md).
   >
   > A volte i filtri non riescono a bloccare un messaggio, non si è d'accordo con il verdetto di filtro o i filtri impiegano molto tempo a bloccare un messaggio. In questi casi, l'elenco di indirizzi consentiti e quello di quelli bloccati sono disponibili per ignorare i verdetti di filtro correnti. È tuttavia consigliabile usare questi elenchi con moderazione e temporaneamente, perché gli elenchi possono diventare ingestibili e temporaneamente perché il nostro stack di filtri deve svolgere il proprio lavoro. Se si mantiene un dominio consentito per un periodo di tempo prolungato, è necessario indicare al mittente di verificare che il dominio sia autenticato e impostato su DMARC, rifiutare se non lo è.

   La procedura per aggiungere voci a uno qualsiasi degli elenchi è la stessa:

   1. Fare clic sul collegamento relativo all’elenco che si vuole configurare:
      - **Mittenti** \> **consentiti**: fare clic su **Gestisci (nn) mittenti**.
      - **Domini** \> **consentiti**: fare clic su **Consenti domini**.
      - **Mittenti** \> **bloccati**: fare clic su **Gestisci mittenti (nn)**.
      - **Domini** \> **bloccati**: fare clic su **Blocca domini**.

   2. Nel riquadro a comparsa che viene visualizzato procedere come segue:
      1. Fare clic su ![Crea icona](../../media/m365-cc-sc-create-icon.png) **Aggiungi mittenti** o **Aggiungi domini**.
      2. Nel riquadro a comparsa **Aggiungi mittenti** o **Aggiungi domini** visualizzato immettere l'indirizzo di posta elettronica del mittente nella casella **Mittente** o il dominio nella casella **Dominio**. Mentre si digita, il valore viene visualizzato sotto la casella. Dopo aver digitato l'indirizzo di posta elettronica o il dominio, selezionare il valore sotto la casella.
      3. Ripetere il passaggio precedente tutte le volte necessarie. Per rimuovere un valore esistente, fare clic su Rimuovi ![Icona Rimuovi](../../media/m365-cc-sc-remove-selection-icon.png) accanto al valore.

      Al termine, fare clic su **Aggiungi mittenti** o **Aggiungi domini**.

      Tornando al riquadro a comparsa principale, i mittenti o i domini aggiunti vengono elencati nella pagina. Per rimuovere una voce da questa pagina, eseguire la procedura seguente:

      1. Selezionare una o più voci dall'elenco. Per trovare un componente aggiuntivo si può anche usare la casella **Cerca**.
      2. Dopo aver selezionato almeno una voce, l'icona Elimina ![Icona Elimina](../../media/m365-cc-sc-delete-icon.png) viene visualizzata.
      3. Fare clic sull’icona Elimina. ![Icona Elimina](../../media/m365-cc-sc-delete-icon.png) per rimuovere le voci selezionate.

      Al termine, fare clic su **Fine**.

      Tornare alla pagina **Elenchi consentiti e bloccati** fare clic su **Successivo** quando si è pronti a continuare per continuare.

8. Nella pagina **Controllo** visualizzata controllare le impostazioni. È possibile selezionare **Modifica** in ogni sezione per modificare le impostazioni all'interno della sezione. Oppure è possibile fare clic su **Indietro** o selezionare la pagina specifica della procedura guidata.

   Al termine, fare clic su **Crea**.

9. Nel messaggio di conferma visualizzato fare clic su **Fatto**.

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-spam-policies"></a>Usare il portale di Microsoft 365 Defender per visualizzare i criteri di protezione dalla posta indesiderata

1. Nel portale di Microsoft 365 Defender passare a **Email e collaborazione** \> **Criteri e regole** \> pagina **Criteri delle minacce** \> **sezione** Criteri \> **Protezione posta indesiderata**.

2. Nella pagina **Criteri filtro posta indesiderata** cercare uno dei valori seguenti:
   - Il valore **Tipo** personalizzato è il **Criterio personalizzato per la posta indesiderata**
   - Il valore **Nome** è **Criterio in ingresso per la posta indesiderata in ingresso (impostazione predefinita)**

   Nell'elenco dei criteri di protezione dalla posta indesiderata vengono visualizzate le proprietà seguenti:

   - **Nome**
   - **Stato**
   - **Priorità**
   - **Type**

3. Quando si seleziona un criterio di filtro della posta indesiderata facendo clic sul nome, le relative impostazioni vengono visualizzate in un riquadro a comparsa.

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-spam-policies"></a>Usare il portale di Microsoft 365 Defender per modificare i criteri di protezione dalla posta indesiderata

1. Nel portale di Microsoft 365 Defender passare a **Email e collaborazione** \> **Criteri e regole** \> pagina **Criteri delle minacce** \> **sezione** Criteri \> **Protezione posta indesiderata**.

2. Nella pagina **Criteri di filtro della posta indesiderata** selezionare un criterio di filtro della posta indesiderata nell'elenco facendo clic sul nome:
   - Un criterio personalizzato creato dall'utente in cui il valore nella colonna **Tipo** è **Criterio di protezione dalla posta indesiderata personalizzato**.
   - Il criterio predefinito denominato **Filtro della posta indesiderata in ingresso (Predefinito)**.

3. Nel riquadro a comparsa dei dettagli sui criteri visualizzato selezionare **Modifica** in ogni sezione per modificare le impostazioni all'interno della sezione. Per altre informazioni sulle impostazioni, vedere la sezione precedente [Usare il portale di Microsoft 365 Defender per creare criteri di protezione dalla posta indesiderata](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) in questo articolo.

   Per il criterio di protezione dalla posta indesiderata predefinito, la sezione **Applicato a**, non è disponibile (il criterio si applica a tutti gli utenti) e non è possibile rinominare il criterio.

Per abilitare o disabilitare un criterio, impostare l'ordine di priorità dei criteri o configurare le notifiche di quarantena per gli utenti finali. Vedere le sezioni seguenti.

### <a name="enable-or-disable-anti-spam-policies"></a>Abilitare o disabilitare criteri di protezione dalla posta indesiderata

Non è possibile disabilitare il criterio di protezione dalla posta indesiderata predefinito.

1. Nel portale di Microsoft 365 Defender passare a **Email e collaborazione** \> **Criteri e regole** \> pagina **Criteri delle minacce** \> **sezione** Criteri \> **Protezione posta indesiderata**.

2. Nella pagina **Criteri di filtro della posta indesiderata** selezionare un criterio con il **Valore tipo** dei **Criteri di protezione dalla posta indesiderata** dall'elenco facendo clic sul nome:.

3. Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato è presente uno dei valori seguenti:
   - **Criterio disattivato**: per attivare il criterio, fare clic su ![Attiva icona](../../media/m365-cc-sc-turn-on-off-icon.png) **Attiva** .
   - **Criterio attivato**: per disattivare il criterio, fare clic su ![Disattiva icona](../../media/m365-cc-sc-turn-on-off-icon.png) **Disattiva**.

4. Nella finestra di dialogo di conferma visualizzata fare clic su **Attiva** o **Disattiva**.

5. Fare clic su **Chiudi** nel riquadro a comparsa dei dettagli del criterio.

Tornare alla pagina dei criteri principale, il valore **Stato** del criterio sarà **Attivato** o **Disattivato**.

### <a name="set-the-priority-of-custom-anti-spam-policies"></a>Impostare la priorità dei criteri di protezione dalla posta indesiderata personalizzati

Per impostazione predefinita, ai criteri di protezione dalla posta indesiderata viene assegnata una priorità che si basa sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità più bassa rispetto a quelli precedenti). Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa). Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.

Per modificare la priorità di un criterio, fare clic su **Aumenta priorità** o **Riduci priorità** nelle proprietà del criterio. Non è possibile modificare direttamente il valore **Priorità** nel portale di Microsoft 365 Defender. La modifica di priorità di un criterio è utile solo se si hanno più criteri.

 **Note**:

- nel portale di Microsoft 365 Defender è possibile solo modificare la priorità del criterio di protezione dalla posta indesiderata dopo averlo creato. In PowerShell, è possibile sovrascrivere la priorità predefinita quando si crea la regola di filtro della posta indesiderata (che può incidere sulla priorità delle regole esistenti).
- I criteri di protezione dalla posta indesiderata vengono elaborati nell'ordine in cui sono visualizzati (il primo criterio contiene il valore **Priorità** 0). Il criterio di protezione dalla posta indesiderata predefinito contiene il valore di priorità **Minimo**, che non è possibile modificare.

1. Nel portale di Microsoft 365 Defender passare a **Email e collaborazione** \> **Criteri e regole** \> pagina **Criteri delle minacce** \> **sezione** Criteri \> **Protezione posta indesiderata**.

2. Nella pagina **Criteri di filtro della posta indesiderata**,selezionare un criterio con il **Valore tipo** dei **Criteri di protezione dalla posta indesiderata** dall'elenco facendo clic sul nome.

3. Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato viene visualizzato **Aumenta priorità** o **Riduci priorità** in base al valore di priorità corrente e al numero di criteri personalizzati:
   - Il criterio di filtro della posta indesiderata con **valore di** priorità **0** ha solo l'opzione **Riduci priorità** disponibile.
   - Il criterio di filtro della posta indesiderata con il **valore di** priorità più basso (per esempio, **3**) ha solo l'opzione **Aumenta priorità** disponibile.
   - Se si impostano tre o più criteri di filtro della posta indesiderata, i criteri tra i valori di priorità più alti e più bassi hanno sia le opzioni **Aumenta priorità** che **Riduci priorità** disponibili.

   Fare clic![ sull’icona Aumenta priorità](../../media/m365-cc-sc-increase-icon.png) **Aumenta priorità** o ![sull’icona Riduci priorità](../../media/m365-cc-sc-decrease-icon.png) **Riduci priorità** per modificare il valore **Priorità**.

4. Al termine, fare clic su **Chiudi** nel riquadro a comparsa dei dettagli del criterio.

### <a name="configure-end-user-spam-notifications"></a>Configurare le notifiche di posta indesiderata dell'utente finale

Quando un verdetto filtro posta indesiderata mette in quarantena un messaggio, è possibile configurare le notifiche di posta indesiderata per l'utente finale per informare i destinatari su quanto accaduto ai messaggi a loro destinati. Per altre informazioni sulle notifiche, vedere [Notifiche di posta indesiderata per l'utente finale in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).

1. Nel portale di Microsoft 365 Defender passare a **Email e collaborazione** \> **Criteri e regole** \> pagina **Criteri delle minacce** \> **sezione** Criteri \> **Protezione posta indesiderata**.

2. Nella pagina **Criteri di filtro della posta indesiderata** selezionare un criterio di filtro della posta indesiderata nell'elenco facendo clic sul nome:
   - Un criterio personalizzato creato dall'utente in cui il valore nella colonna **Tipo** è **Criterio di protezione dalla posta indesiderata personalizzato**.
   - Il criterio predefinito denominato **Filtro della posta indesiderata in ingresso (Predefinito)**.

3. Nel riquadro a comparsa dei dettagli del criterio che viene visualizzato fare clic su **Modifica** nella sezione **Azioni**. Nel riquadro a comparsa **Azioni** visualizzato, configurare le impostazioni seguenti:

   - **Abilita notifiche di posta indesiderata per l'utente**: selezionare la casella di controllo per abilitare le notifiche o deselezionarla per disabilitare le notifiche. Quando si seleziona la casella di controllo, vengono visualizzate le impostazioni aggiuntive seguenti:

     - **Invia notifiche di posta indesiderata per l'utente finale ogni (giorni):**: selezionare la frequenza di invio delle notifiche. Il valore predefinito è 3 giorni. È possibile immettere da 1 a 15 giorni.

       Sono presenti 3 cicli di notifica della posta indesiderata dell'utente finale entro un periodo di 24 ore, che iniziano agli orari seguenti: 01:00 UTC, 08:00 UTC e 16:00 UTC.

       > [!NOTE]
       > Se una notifica durante risulta mancante durante un ciclo precedente, ne verrà eseguito il push in un ciclo successivo. Ciò può dare l'impressione di ricevere più notifiche nello stesso giorno.

     - **Lingua**: fare clic sul menu a discesa e selezionare una lingua disponibile dall'elenco. Il valore predefinito è **Predefinito**, ovvero l'inglese.

   Al termine, scegliere **Salva**.

4. Tornare al riquadro a comparsa dei dettagli sui criteri, fare clic su **chiudi**.

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-spam-policies"></a>Usare il portale di Microsoft 365 Defender per rimuovere criteri di protezione dalla posta indesiderata

Quando si usa il portale di Microsoft 365 Defender per rimuovere un criterio di filtro della posta indesiderata personalizzato, vengono eliminati sia la regola di filtro della posta indesiderata che il criterio di filtro della posta indesiderata corrispondente. Non è possibile rimuovere il criterio di protezione dalla posta indesiderata predefinito.

1. Nel portale di Microsoft 365 Defender passare a **Email e collaborazione** \> **Criteri e regole** \> pagina **Criteri delle minacce** \> **sezione** Criteri \> **Protezione posta indesiderata**.

2. Nella pagina **Criteri di filtro della posta indesiderata** selezionare un criterio con il **Valore tipo** dei **Criteri di protezione dalla posta indesiderata** dall'elenco facendo clic sul nome:. Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato fare clic![ sull'icona Altre azioni](../../media/m365-cc-sc-more-actions-icon.png) **Altre azioni** \> ![Icona Elimina criterio](../../media/m365-cc-sc-delete-icon.png) **Elimina criterio**.

3. Nella finestra di dialogo di conferma che viene visualizzata fare clic su **Sì**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a>Utilizzare PowerShell per Exchange Online o PowerShell di EOP autonomo per configurare criteri di protezione dalla posta indesiderata

Come descritto in precedenza, una criterio di posta indesiderata consiste in un criterio di filtro di posta indesiderata e una regola di filtro di posta indesiderata.

In PowerShell per Exchange Online o PowerShell di EOP autonomo è evidente la differenza tra i criteri di filtro della posta indesiderata e le regole di filtro della posta indesiderata. Gestire i criteri di filtro della posta indesiderata usando i cmdlet **\*-HostedContentFilterPolicy** e le regole di filtro della posta indesiderata usando i cmdlet **\*-HostedContentFilterRule**.

- In PowerShell, creare innanzitutto il criterio di filtro della posta indesiderata, quindi creare la regola di filtro della posta indesiderata che identifica il criterio cui viene applicata la regola.
- In PowerShell, modificare le impostazioni nel criterio di filtro della posta indesiderata e la regola di filtro della posta indesiderata separatamente.
- Quando si rimuove un criterio di filtro della posta indesiderata da PowerShell, la regola di filtro della posta indesiderata corrispondente non viene rimossa automaticamente, e viceversa.

Le impostazioni dei criteri contro la posta indesiderata seguenti sono disponibili solo in PowerShell:

- Il parametro _MarkAsSpamBulkMail_ è `On` per impostazione predefinita. Gli effetti di questa impostazione sono stati illustrati nella sezione precedente [Usare il portale di Microsoft 365 Defender per creare criteri di protezione dalla posta indesiderata](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) in questo articolo.

- Le impostazioni seguenti per le notifiche di quarantena della posta indesiderata dell'utente finale:
  - Il parametro _DownloadLink_ che mostra o nasconde il collegamento allo strumento per la segnalazione delle e-mail indesiderate di Outlook.
  - Il parametro _EndUserSpamNotificationCustomSubject_ consente di personalizzare la riga dell'oggetto della notifica.

### <a name="use-powershell-to-create-anti-spam-policies"></a>Utilizzare PowerShell per creare criteri di protezione dalla posta indesiderata

La creazione di un criterio di protezione dalla posta indesiderata in PowerShell è un processo che prevede due passaggi:

1. Creare il criterio di filtro della posta indesiderata.
2. Creare la regola di filtro della posta indesiderata che specifica il criterio di filtro della posta indesiderata cui viene applicata la regola.

 **Note**:

- è possibile creare una nuova regola di filtro della posta indesiderata e assegnarvi un criterio di filtro della posta indesiderata esistente e non associato. Una regola di filtro della posta indesiderata non può essere associata a più di un criterio di filtro della posta indesiderata.
- È possibile configurare le impostazioni seguenti nei nuovi criteri di filtro della posta indesiderata in PowerShell che non sono disponibili nel portale di Microsoft 365 Defender finché non si crea il criterio:
  - Creare il nuovo criterio come disabilitato (_Abilitato_ `$false` nel cmdlet **New-HostedContentFilterRule**).
  - Impostare la priorità del criterio durante la creazione (_Priorità_ _\<Number\>_) nel cmdlet **New-HostedContentFilterRule**).

- Un nuovo criterio di filtro della posta indesiderata creato in PowerShell non sarà visibile nel portale di Microsoft 365 Defender finché non viene assegnato a una regola di filtro della posta indesiderata.

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a>Passaggio 1 - Utilizzo di PowerShell per creare criteri di filtro della posta indesiderata

Per creare un criterio di filtro della posta indesiderata, utilizzare questa sintassi:

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

In questo esempio viene creato un criterio di filtro della posta indesiderata denominato Contoso Executives con le impostazioni seguenti:

- Mettere i messaggi in quarantena quando il verdetto filtro posta indesiderata indica posta indesiderata o alta probabilità di posta indesiderata.
- Il BCL 7, 8, o 9 attiva l'azione per un verdetto filtro posta indesiderata della posta elettronica inviata in blocco.

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

Per informazioni dettagliate su sintassi e parametri, vedere [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).

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

Per informazioni dettagliate su sintassi e parametri, vedere [New-HostedContentFilterRule](/powershell/module/exchange/new-hostedcontentfilterrule).

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

Per informazioni dettagliate su sintassi e parametri, vedere [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).

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

Per informazioni dettagliate su sintassi e parametri, vedere [Get-HostedContentFilterRule](/powershell/module/exchange/get-hostedcontentfilterrule).

### <a name="use-powershell-to-modify-spam-filter-policies"></a>Utilizzo di PowerShell per modificare criteri di filtro della posta indesiderata

Oltre agli elementi seguenti, le stesse impostazioni sono disponibili quando si modificano i criteri di filtro della posta indesiderata in PowerShell e quando si creano i criteri come descritto nella sezione precedente [Passaggio 1 - Utilizzo di PowerShell per creare criteri di filtro della posta indesiderata](#step-1-use-powershell-to-create-a-spam-filter-policy) in questo articolo.

- Il parametro _MakeDefault_ che trasforma il criterio specificato nel criterio predefinito (si applica a tutti gli utenti, sempre priorità **Lowest** e non è possibile eliminarlo) è disponibile solo quando si modifica un criterio di filtro della posta indesiderata in PowerShell.
- Non è possibile rinominare un criterio di filtro della posta indesiderata (il cmdlet **Set-HostedContentFilterPolicy** non contiene il parametro _Name_). Quando si rinomina un criterio di protezione dalla posta indesiderata nel portale di Microsoft 365 Defender, si rinomina solamente la _regola_ di filtro della posta indesiderata.

Per modificare un criterio di filtro della posta indesiderata, utilizzare questa sintassi:

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

Per informazioni dettagliate su sintassi e parametri, vedere [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).

### <a name="use-powershell-to-modify-spam-filter-rules"></a>Utilizzo di PowerShell per modificare regole di filtro della posta indesiderata

L'unica impostazione non disponibile quando si modifica una regola di filtro della posta indesiderata in PowerShell è il parametro _Enabled_, che consente di creare una regola disabilitata. Per abilitare o disabilitare le regole di filtro della posta indesiderata esistenti, vedere la sezione successiva.

In caso contrario, non saranno disponibili altre impostazioni quando si modifica una regola di filtro della posta indesiderata in PowerShell. Le stesse impostazioni sono disponibili quando si crea una regola come descritto nella sezione precedente [Passaggio 2 - Utilizzo di PowerShell per creare una regola di filtro della posta indesiderata](#step-2-use-powershell-to-create-a-spam-filter-rule) in questo articolo.

Per modificare una regola di filtro della posta indesiderata, utilizzare questa sintassi:

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

Questo esempio rinomina la regola di filtro della posta indesiderata esistente denominata `{Fabrikam Spam Filter}`.

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

Per informazioni dettagliate su sintassi e parametri, vedere [Set-HostedContentFilterRule](/powershell/module/exchange/set-hostedcontentfilterrule).

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

Per informazioni dettagliate su sintassi e parametri, vedere [Enable-HostedContentFilterRule](/powershell/module/exchange/enable-hostedcontentfilterrule) e [Disable-HostedContentFilterRule](/powershell/module/exchange/disable-hostedcontentfilterrule).

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a>Utilizzare PowerShell per impostare una priorità sulle regole di filtro della posta indesiderata

Il valore di priorità più alto che è possibile impostare in una regola è 0. Il valore più basso che è possibile impostare dipende dal numero di regole. Se si dispone di cinque regole predefinite, è possibile utilizzare i valori di priorità da 0 a 4. Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole. Ad esempio, se si dispone di cinque regole (priorità da 0 a 4) e si modifica la priorità di una regola a 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.

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

Per informazioni dettagliate su sintassi e parametri, vedere [Remove-HostedContentFilterPolicy](/powershell/module/exchange/remove-hostedcontentfilterpolicy).

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

Per informazioni dettagliate su sintassi e parametri, vedere [Remove-HostedContentFilterRule](/powershell/module/exchange/remove-hostedcontentfilterrule).

## <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a>Inviare un messaggio GTUBE per verificare le impostazioni dei criteri contro la posta indesiderata

> [!NOTE]
> Questi passaggi funzioneranno solo se l'organizzazione di posta elettronica da cui si sta inviando il messaggio GTUBE non ricerca posta indesiderata in uscita. In caso contrario, non è possibile inviare il messaggio di prova.

Il test GTUBE (Generic Test for Unsolicited Bulk Email) è una stringa di testo da includere in un messaggio di prova per verificare le impostazioni di protezione dalla posta indesiderata dell'organizzazione. Un messaggio GTUBE è simile al file di testo EICAR (European Institute for Computer Antivirus Research) per la verifica delle impostazioni antimalware.

Includere il seguente testo GTUBE in un messaggio di posta elettronica o in una singola riga, senza spazi o interruzioni di riga:

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```
