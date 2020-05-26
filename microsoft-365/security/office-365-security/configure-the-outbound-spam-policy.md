---
title: Configurare il filtro posta indesiderata in uscita
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni su come visualizzare, creare, modificare ed eliminare i criteri di posta indesiderata in uscita in Exchange Online Protection (EOP).
ms.openlocfilehash: e035fe26cea0fcd1f3051f7464722ae1c7a3b56f
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352000"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>Configurare il filtro della posta indesiderata in uscita in EOP

In Microsoft 365 organizzazioni con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, i messaggi di posta elettronica in uscita inviati tramite EOP vengono controllati automaticamente per la posta indesiderata e l'attività di invio inusuale.

La posta indesiderata in uscita da un utente dell'organizzazione indica in genere un account compromesso. I messaggi in uscita sospetti sono contrassegnati come posta indesiderata (indipendentemente dal livello di probabilità di posta indesiderata o SCL) e vengono instradati attraverso il [pool di recapito ad alto rischio](high-risk-delivery-pool-for-outbound-messages.md) per proteggere la reputazione del servizio, ovvero mantenere i server di posta elettronica di origine di Microsoft 365 fuori dagli elenchi di indirizzi IP bloccati. Gli amministratori ricevono automaticamente una notifica delle attività di posta elettronica in uscita sospette e degli utenti bloccati tramite [criteri di avviso](../../compliance/alert-policies.md).

EOP utilizza i criteri di posta indesiderata in uscita come parte della difesa complessiva dell'organizzazione contro la posta indesiderata. Per altre informazioni, vedere [Protezione dalla posta indesiderata](anti-spam-protection.md).

Gli amministratori possono visualizzare, modificare e configurare (ma non eliminare) il criterio di posta indesiderata in uscita predefinito. Per una maggiore granularità, è anche possibile creare criteri di posta indesiderata in uscita personalizzati che si applicano a utenti, gruppi o domini specifici nell'organizzazione. I criteri personalizzati hanno sempre la precedenza sul criterio predefinito, ma non è possibile modificarne la priorità (in funzione).

È possibile configurare i criteri di posta indesiderata in uscita nel centro sicurezza & Compliance o in PowerShell (Exchange Online PowerShell per Microsoft 365 organizzazioni con cassette postali in Exchange Online; standalone EOP PowerShell per organizzazioni senza cassette postali di Exchange Online).

## <a name="outbound-spam-policies-in-the-security--compliance-center-vs-powershell"></a>Criteri di posta indesiderata in uscita nel centro sicurezza & Compliance vs PowerShell

Gli elementi di base di un criterio di posta indesiderata in uscita in EOP sono i seguenti:

- **Criterio di filtro per la posta indesiderata in uscita**: consente di specificare le azioni per i verdetti del filtro della posta indesiderata in uscita

- **Regola del filtro per la posta indesiderata in uscita**: consente di specificare i filtri priorità e destinatario (a chi si applica il criterio) per un criterio di filtro posta indesiderata in uscita.

La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri di posta indesiderata in uscita nel centro sicurezza & conformità:

- Quando si crea un criterio di posta indesiderata in uscita nel centro sicurezza & Compliance, si sta effettivamente creando una regola di filtro per la posta indesiderata in uscita e il criterio di filtro per la posta indesiderata in uscita associato contemporaneamente utilizzando lo stesso nome per entrambi.

- Quando si modifica un criterio di posta indesiderata in uscita nel centro sicurezza & conformità, le impostazioni relative ai filtri nome, priorità, abilitato o disabilitato e destinatario modificano la regola del filtro per la posta indesiderata in uscita. Tutte le altre impostazioni modificano i criteri di filtro della posta indesiderata in uscita associati.

- Quando si rimuove un criterio di posta indesiderata in uscita dal centro sicurezza & conformità, la regola di filtro posta indesiderata in uscita e i criteri di filtro della posta indesiderata in uscita associati vengono rimossi.

In Exchange Online PowerShell o standalone EOP PowerShell, la differenza tra i criteri di filtro della posta indesiderata in uscita e le regole del filtro per la posta indesiderata è evidente. È possibile gestire i criteri di filtro della posta indesiderata in uscita utilizzando i cmdlet ** \* -HostedOutboundSpamFilterPolicy** e gestire le regole del filtro per la posta indesiderata in uscita utilizzando i cmdlet ** \* -HostedOutboundSpamFilterRule** .

- In PowerShell, creare innanzitutto il criterio di filtro per la posta indesiderata in uscita, quindi creare la regola di filtro posta indesiderata in uscita che identifica il criterio a cui si applica la regola.

- In PowerShell, è possibile modificare le impostazioni nel criterio di filtro della posta indesiderata in uscita e la regola di filtro posta indesiderata in uscita separatamente.

- Quando si rimuove un criterio di filtro per la posta indesiderata in uscita da PowerShell, la regola di filtro posta indesiderata in uscita corrispondente non viene rimossa automaticamente e viceversa.

### <a name="default-outbound-spam-policy"></a>Criterio di posta indesiderata in uscita predefinito

Ogni organizzazione dispone di un criterio di posta indesiderata in uscita incorporato denominato default con queste proprietà:

- Il criterio di filtro per la posta indesiderata in uscita denominato default viene applicato a tutti i destinatari dell'organizzazione, anche se non esiste una regola di filtro per la posta indesiderata in uscita (filtri destinatario) associata al criterio.

- Il valore personalizzato della priorità del criterio denominato Predefinito è **Lowest** e non può essere modificato (il criterio viene sempre applicato per ultimo). Qualsiasi criterio personalizzato creato avrà sempre una priorità più alta rispetto al criterio denominato Predefinito.

- Il criterio denominato Predefinito è il criterio predefinito (la proprietà **IsDefault** contiene il valore `True`), e non è possibile eliminare il criterio predefinito.

Per aumentare l'efficacia del filtro per la posta indesiderata in uscita, è possibile creare criteri di posta indesiderata in uscita personalizzati con impostazioni più rigorose applicate a utenti o gruppi di utenti specifici.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla pagina **Impostazioni di filtro della posta indesiderata**, usare <https://protection.office.com/antispam>.

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure. Per aggiungere, modificare ed eliminare i criteri di posta indesiderata in uscita, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** . Per l'accesso in sola lettura ai criteri di posta indesiderata in uscita, è necessario essere membri del gruppo di ruoli **lettore di sicurezza** . Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

- Per le impostazioni consigliate per i criteri di protezione da posta indesiderata in uscita, vedere [EOP in uscita Spam Policy Filter Settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).

- I [criteri di avviso](../../compliance/alert-policies.md) predefiniti denominati limite di invio di posta elettronica sono stati **superati**, sono stati **rilevati modelli di invio di messaggi**di posta elettronica sospetti e non è stato possibile inviare **messaggi** di posta elettronica ai membri del gruppo **TenantAdmins** (**Global Admins**) sull'attività di posta elettronica in uscita inusuale e sugli utenti bloccati. Per ulteriori informazioni, vedere [verificare le impostazioni degli avvisi per gli utenti con restrizioni](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). È consigliabile utilizzare questi criteri di avviso anziché le opzioni di notifica nei criteri di posta indesiderata in uscita.

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a>Utilizzare il Centro sicurezza & conformità per creare i criteri di posta indesiderata in uscita

La creazione di un criterio di posta indesiderata in uscita personalizzato nel centro sicurezza & conformità crea la regola del filtro posta indesiderata e i criteri di filtro della posta indesiderata associati allo stesso tempo utilizzando lo stesso nome per entrambi.

1. Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.

2. Nella pagina impostazioni di protezione da **posta indesiderata** fare clic su **Crea un criterio in uscita**.

3. Nel criterio di filtro per la **posta indesiderata in uscita** che si apre, configurare le seguenti impostazioni:

   - **Nome**: immettere un nome univoco descrittivo per il criterio.

   - **Descrizione**: immettere una descrizione opzionale per il criterio.

4. Optional Espandere la sezione **notifiche** per configurare altri utenti che devono ricevere le copie e le notifiche dei messaggi di posta elettronica in uscita sospetti:

   - **Inviare una copia dei messaggi di posta elettronica in uscita sospetti a persone specifiche**: questa impostazione consente di aggiungere gli utenti specificati come destinatari Ccn ai messaggi in uscita sospetti.

     > [!NOTE]
     > Questa impostazione è compatibile solo con il criterio di posta indesiderata in uscita predefinito. Non è possibile utilizzare i criteri di posta indesiderata in uscita personalizzati creati.

     Per abilitare questa impostazione:

     a. Selezionare la casella di controllo per abilitare l'impostazione.

     b. Fare clic su **Aggiungi utenti**. Nel riquadro a comparsa **Aggiungi o Rimuovi destinatari** visualizzato:

     c. Immettere l'indirizzo di posta elettronica del mittente. È possibile specificare più indirizzi di posta elettronica separati da punti e virgola (;) o un destinatario per riga.

     d. Scegliere ![Icona Aggiungi](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) per aggiungere i destinatari.

        Ripetere questi passaggi tutte le volte necessarie.

        I destinatari aggiunti vengono visualizzati nella sezione **elenco dei destinatari** sul riquadro a comparsa. Per eliminare un destinatario, fare clic su ![ Rimuovi ](../../media/scc-remove-icon.png) .

     e. Al termine, scegliere **Salva**.

     Per disabilitare questa impostazione, deselezionare la casella di controllo.

   - **Notifica a determinate persone se un mittente è bloccato a causa dell'invio di posta indesiderata in uscita**:

     > [!NOTE]
     > Il [criterio di avviso](../../compliance/alert-policies.md) predefinito denominato utente con **restrizioni dall'invio di messaggi di posta** elettronica Invia già notifiche tramite posta elettronica ai membri del gruppo **TenantAdmins** (**Global Admins**) quando gli utenti vengono bloccati a causa del superamento dei limiti nella sezione **limiti dei destinatari** . È consigliabile utilizzare il criterio di avviso anziché questa impostazione nel criterio di posta indesiderata in uscita per inviare una notifica agli amministratori e ad altri utenti. Per istruzioni, vedere [verificare le impostazioni degli avvisi per gli utenti con restrizioni](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). <br/><br/> Questa impostazione è compatibile solo con il criterio di posta indesiderata in uscita predefinito. Non è possibile utilizzare i criteri di posta indesiderata in uscita personalizzati creati.

     Per abilitare questa impostazione:

     a. Selezionare la casella di controllo per abilitare l'impostazione.

     b. Fare clic su **Aggiungi utenti**. Nel riquadro a comparsa **Aggiungi o Rimuovi destinatari** visualizzato:

     c. Immettere l'indirizzo di posta elettronica del mittente. È possibile specificare più indirizzi di posta elettronica separati da punti e virgola (;) o un destinatario per riga.

     d. Scegliere ![Icona Aggiungi](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) per aggiungere i destinatari.

        Ripetere questi passaggi tutte le volte necessarie.

        I destinatari aggiunti vengono visualizzati nella sezione **elenco dei destinatari** sul riquadro a comparsa. Per eliminare un destinatario, fare clic su ![ Rimuovi ](../../media/scc-remove-icon.png) .

     e. Al termine, scegliere **Salva**.

     Per disabilitare questa impostazione, deselezionare la casella di controllo.

5. Optional Espandere la sezione **limiti dei destinatari** per configurare i limiti e le azioni per i messaggi di posta elettronica in uscita sospetti:

   > [!NOTE]
   > Queste impostazioni sono valide solo per le cassette postali basate sul cloud.

   - **Numero massimo di destinatari per utente**

     Un valore valido è compreso tra 0 e 10000. Il valore predefinito è 0, il che significa che vengono utilizzati i valori predefiniti del servizio. Per ulteriori informazioni, vedere [invio di limiti tra le opzioni di Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).

     - **Limite orario esterno**: numero massimo di destinatari esterni all'ora.

     - **Limite orario interno**: numero massimo di destinatari interni all'ora.

     - **Limite giornaliero**: numero totale massimo di destinatari al giorno.

   - **Azione quando un utente supera i limiti sopra riportati**: configurare l'azione da eseguire quando si supera il **limite** di uno dei destinatari. Per tutte le azioni, i destinatari specificati nell' **utente hanno limitazioni dall'invio** dei criteri di avviso per la posta elettronica (e nell'ora ridondante **avvisano persone specifiche se un mittente è bloccato a causa** dell'impostazione della posta indesiderata in uscita nel criterio di posta indesiderata in uscita per ricevere notifiche tramite posta elettronica.

     - **Impedire all'utente di inviare messaggi di posta elettronica fino al giorno seguente**: questo è il valore predefinito. Le notifiche di posta elettronica vengono inviate e l'utente non sarà in grado di inviare altri messaggi fino al giorno seguente, in base all'ora UTC. Non è possibile che l'amministratore esegua l'override di questo blocco.

       - L'avviso attività denominato **utente con restrizioni dall'invio di messaggi di posta elettronica** informa gli amministratori (tramite posta elettronica e nella pagina **Visualizza avvisi** ).

       - Tutti i destinatari specificati nella **notifica di persone specifiche se un mittente è bloccato a causa dell'impostazione della posta indesiderata in uscita** nel criterio sono anche notificati.

       - L'utente non sarà in grado di inviare altri messaggi fino al giorno seguente, in base all'ora UTC. Non è possibile che l'amministratore esegua l'override di questo blocco.

     - **Impedire all'utente di inviare posta**elettronica: vengono inviate notifiche tramite posta elettronica, l'utente viene aggiunto al portale **[ <https://sip.protection.office.com/restrictedusers> utenti con restrizioni]** nel centro sicurezza & compliance e l'utente non può inviare messaggi di posta elettronica fino a quando non viene rimosso dal portale **degli utenti con restrizioni** da parte di un amministratore. Dopo che un amministratore ha rimosso l'utente dall'elenco, l'utente non sarà più limitato per quel giorno. Per istruzioni, vedere [rimozione di un utente dal portale degli utenti con restrizioni dopo l'invio di posta indesiderata](removing-user-from-restricted-users-portal-after-spam.md).

     - **Nessuna azione, solo avviso**: le notifiche di posta elettronica vengono inviate.

6. Necessari Espandere la sezione **applicato a** per identificare i mittenti interni ai quali si applica il criterio.

    È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione. Più valori della stessa condizione o utilizzo o logica dell'eccezione (ad esempio, _ \< sender1 \> _ o _ \< sender2 \> _). Utilizzo e logica di diverse condizioni o eccezioni (ad esempio, _ \< sender1 \> _ e _ \< membro del gruppo \> 1_).

    È più facile fare clic su **Aggiungi una condizione** tre volte per visualizzare tutte le condizioni disponibili. È possibile fare clic su ![Pulsante Rimuovi](../../media/scc-remove-icon.png) per rimuovere le condizioni che non si vogliono configurare.

    - **Il dominio del mittente è**: specifica i mittenti in uno o più dei domini accettati configurati nell'organizzazione. Fare clic sulla casella **Aggiungi un tag** per visualizzare e selezionare un dominio. Fare nuovamente clic sulla casella **Aggiungi un tag** per selezionare altri domini se è disponibile più di un dominio.

    - **Sender è**: consente di specificare uno o più utenti nell'organizzazione. Fare clic su **Aggiungi un tag** e iniziare a digitare per filtrare l'elenco. Fare di nuovo clic sulla casella **Aggiungi tag** per selezionare mittenti aggiuntivi.

    - **Sender è un membro di**: consente di specificare uno o più gruppi nell'organizzazione. Fare clic su **Aggiungi un tag** e iniziare a digitare per filtrare l'elenco. Fare di nuovo clic sulla casella **Aggiungi tag** per selezionare mittenti aggiuntivi.

    - **Tranne quando**: per aggiungere eccezioni alla regola, fare clic su **Aggiungi una condizione** tre volte per visualizzare tutte le eccezioni disponibili. Impostazioni e comportamento sono equivalenti alle condizioni.

7. Al termine, scegliere **Salva**.

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a>Utilizzare il Centro sicurezza & conformità per visualizzare i criteri di posta indesiderata in uscita

1. Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.

2. Nella pagina impostazioni di protezione da **posta indesiderata** , fare clic su ![ Espandi icona ](../../media/scc-expand-icon.png) per espandere un criterio di posta indesiderata in uscita:

   - Criterio predefinito denominato **criteri di filtro della posta indesiderata in uscita**.

   - Un criterio personalizzato creato in cui il valore nella colonna **tipo** è criterio di **posta indesiderata in uscita personalizzato**.

3. Le impostazioni dei criteri vengono visualizzate nei dettagli dei criteri espansi visualizzati oppure è possibile fare clic su **modifica criterio**.

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a>Utilizzare il Centro sicurezza & conformità per modificare i criteri di posta indesiderata in uscita

1. Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.

2. Nella pagina impostazioni di protezione da **posta indesiderata** , fare clic su ![ Espandi icona ](../../media/scc-expand-icon.png) per espandere un criterio di posta indesiderata in uscita:

   - Criterio predefinito denominato **criteri di filtro della posta indesiderata in uscita**.

   - Un criterio personalizzato creato in cui il valore nella colonna **tipo** è criterio di **posta indesiderata in uscita personalizzato**.

3. Fare clic su **Modifica criterio**.

Per i criteri di posta indesiderata personalizzati in uscita, le impostazioni disponibili nel riquadro a comparsa visualizzato sono identiche a quelle descritte in [use the Security & Compliance Center to create Outbound spam Policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.

Per il criterio di protezione da posta indesiderata in uscita predefinito denominato **criterio di filtro posta**indesiderata in uscita, la sezione **applicato a** non è disponibile (il criterio si applica a tutti) e non è possibile rinominare il criterio.

Per abilitare o disabilitare un criterio, impostare l'ordine di priorità dei criteri o configurare le notifiche di quarantena per gli utenti finali. Vedere le sezioni seguenti.

### <a name="enable-or-disable-outbound-spam-policies"></a>Abilitare o disabilitare i criteri di posta indesiderata in uscita

1. Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.

2. Nella pagina impostazioni di protezione da **posta indesiderata** , fare clic su ![ Espandi icona ](../../media/scc-expand-icon.png) per espandere un criterio personalizzato creato (il valore nella colonna **tipo** è **Custom criterio di posta indesiderata in uscita**).

3. Nei dettagli dei criteri espansi visualizzati, notare il valore nella colonna **Attivo**.

   Spostare l'interruttore a sinistra per disabilitare il criterio: ![Disattiva](../../media/scc-toggle-off.png)

   Spostare l'interruttore a destra per abilitare il criterio: ![Attiva](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

Non è possibile disabilitare il criterio di posta indesiderata in uscita predefinito.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>Impostare la priorità dei criteri di posta indesiderata in uscita personalizzati

Per impostazione predefinita, ai criteri di posta indesiderata in uscita viene assegnata una priorità che si basa sull'ordine in cui sono stati creati (le nuove politiche hanno priorità più basse rispetto ai criteri precedenti). Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa). Due criteri non possono avere priorità uguale.

I criteri di posta indesiderata in uscita personalizzati vengono visualizzati nell'ordine in cui sono stati elaborati (il primo criterio ha il valore di **priorità** 0). Il criterio di posta indesiderata in uscita predefinito denominato **criterio di filtro posta indesiderata in uscita** ha il valore di priorità **più basso**e non è possibile modificarlo.

Per modificare la priorità di un criterio, spostare il criterio più in alto o più in basso nell'elenco (non è possibile modificare direttamente il numero **Priority** nel Centro sicurezza e conformità).

1. Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.

2. Nella pagina impostazioni di protezione da **posta indesiderata** individuare i criteri in cui il valore nella colonna **tipo** è **criteri di posta indesiderata personalizzati in uscita**. Notare i valori nella colonna **Priorità**:

   - Il criterio di posta indesiderata in uscita personalizzato con la priorità più alta ha il valore ![ freccia giù (icona ](../../media/ITPro-EAC-DownArrowIcon.png) **0**).

   - Il criterio di posta indesiderata in uscita personalizzato con la priorità più bassa ha il valore ![ icona freccia su ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (ad esempio, ![ icona freccia su ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).

   - Se si dispone di tre o più criteri di posta indesiderata in uscita personalizzati, i criteri tra la priorità più alta e quella più bassa sono valori su icona freccia ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ giù icona ](../../media/ITPro-EAC-DownArrowIcon.png) **n** (ad esempio freccia ![ giù icona ](../../media/ITPro-EAC-UpArrowIcon.png)![ freccia giù ](../../media/ITPro-EAC-DownArrowIcon.png) **2**).

3. Fare clic su ![Icona Freccia SU](../../media/ITPro-EAC-UpArrowIcon.png) oppure ![Icona Freccia GIÙ](../../media/ITPro-EAC-DownArrowIcon.png) per spostare il criterio della posta indesiderata in uscita personalizzato verso l'alto o verso il basso nell'elenco priorità.

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a>Utilizzare il Centro sicurezza & conformità per rimuovere i criteri di posta indesiderata in uscita

1. Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.

2. Nella pagina impostazioni di protezione da **posta indesiderata** , fare clic su ![ Espandi icona ](../../media/scc-expand-icon.png) per espandere il criterio personalizzato che si desidera eliminare (la colonna **tipo** è un **criterio di posta indesiderata in uscita personalizzato**).

3. Nei dettagli sui criteri espansi visualizzati, fare clic su **Elimina criterio**.

4. Fare clic su **Sì** quando viene visualizzata la finestra di dialogo di avviso.

Non è possibile rimuovere il criterio predefinito.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>Utilizzo di PowerShell di Exchange Online o standalone EOP PowerShell per configurare i criteri di posta indesiderata in uscita

### <a name="use-powershell-to-create-outbound-spam-policies"></a>Utilizzo di PowerShell per creare i criteri di posta indesiderata in uscita

La creazione di un criterio di posta indesiderata in uscita in PowerShell è un processo in due fasi:

1. Creare il criterio di filtro per la posta indesiderata in uscita.

2. Creare la regola di filtro posta indesiderata in uscita che specifica il criterio di filtro della posta indesiderata in uscita a cui si applica la regola.

 **Note**:

- È possibile creare una nuova regola di filtro per la posta indesiderata in uscita e assegnare un criterio di filtro per la posta indesiderata in uscita non associato. Una regola di filtro per la posta indesiderata in uscita non può essere associata a più criteri di filtro posta indesiderata in uscita.

- È possibile configurare le seguenti impostazioni nei nuovi criteri di filtro per la posta indesiderata in uscita in PowerShell che non sono disponibili nel centro sicurezza & conformità fino a dopo la creazione del criterio:

  - Creare il nuovo criterio come disabilitato (_attivato_ `$false` nel cmdlet **New-HostedOutboundSpamFilterRule** ).

  - Impostare la priorità dei criteri durante la creazione (_Priority_ _ \< numero \> _di priorità) nel cmdlet **New-HostedOutboundSpamFilterRule** ).

- Un nuovo criterio di filtro per la posta indesiderata in uscita creato in PowerShell non è visibile nel centro sicurezza & conformità fino a quando non si assegna il criterio a una regola di filtro posta indesiderata.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>Passaggio 1: utilizzare PowerShell per creare un criterio di filtro per la posta indesiderata in uscita

Per creare un criterio di filtro per la posta indesiderata in uscita, utilizzare la sintassi seguente:

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

In questo esempio viene creato un nuovo criterio di filtro per la posta indesiderata in uscita denominato contoso Executives con le seguenti impostazioni:

- I limiti di frequenza dei destinatari sono limitati a valori inferiori a quelli predefiniti. Per ulteriori informazioni, vedere [invio di limiti tra le opzioni di Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).

- Dopo che è stato raggiunto uno dei limiti, all'utente viene impedito l'invio di messaggi.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>Passaggio 2: utilizzare PowerShell per creare una regola di filtro per la posta indesiderata in uscita

Per creare una regola di filtro per la posta indesiderata in uscita, utilizzare la sintassi seguente:

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In questo esempio viene creata una nuova regola di filtro per la posta indesiderata in uscita denominata Contoso Executives con queste impostazioni:

- Il criterio di filtro per la posta indesiderata in uscita denominato contoso Executives è associato alla regola.

- La regola viene applicata ai membri del gruppo Contoso Executives Group.

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>Utilizzo di PowerShell per visualizzare i criteri di filtro della posta indesiderata in uscita

Per restituire un elenco riepilogativo di tutti i criteri di filtro per la posta indesiderata in uscita, eseguire il comando seguente:

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

Per restituire informazioni dettagliate su uno specifico criterio di filtro della posta indesiderata in uscita, utilizzare la sintassi seguente:

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

In questo esempio vengono restituiti tutti i valori delle proprietà per il criterio di filtro della posta indesiderata in uscita denominato Executives.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>Utilizzare PowerShell per visualizzare le regole del filtro per la posta indesiderata in uscita

Per visualizzare le regole di filtro per la posta indesiderata in uscita esistenti, utilizzare la sintassi seguente:

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

Per restituire un elenco riepilogativo di tutte le regole del filtro per la posta indesiderata in uscita, eseguire il comando seguente:

```PowerShell
Get-HostedOutboundSpamFilterRule
```

Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

Per restituire informazioni dettagliate su una regola di filtro della posta indesiderata in uscita specifica, utilizzare la sintassi seguente:

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

In questo esempio vengono restituiti tutti i valori delle proprietà per la regola di filtro della posta indesiderata in uscita denominata Contoso Executives.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>Utilizzo di PowerShell per modificare i criteri di filtro della posta indesiderata in uscita

Le stesse impostazioni sono disponibili quando si modifica un criterio di filtro antimalware in PowerShell come quando si crea il criterio come descritto nel [passaggio 1: utilizzare PowerShell per creare una sezione dei criteri di filtro per la posta indesiderata in uscita](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) più indietro in questo argomento.

**Nota**: non è possibile rinominare un criterio di filtro per la posta indesiderata in uscita (il cmdlet **set-HostedOutboundSpamFilterPolicy** non ha un parametro _Name_ ). Quando si rinomina un criterio di posta indesiderata in uscita nel centro sicurezza & conformità, viene rinominata solo la _regola_del filtro per la posta indesiderata in uscita.

Per modificare un criterio di filtro per la posta indesiderata in uscita, utilizzare la sintassi seguente:

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>Utilizzare PowerShell per modificare le regole del filtro per la posta indesiderata in uscita

L'unica impostazione che non è disponibile quando si modifica una regola di filtro per la posta indesiderata in uscita in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata. Per abilitare o disabilitare le regole di filtro per la posta indesiderata in uscita esistenti, vedere la sezione successiva.

In caso contrario, non sono disponibili altre impostazioni quando si modifica una regola di filtro posta indesiderata in uscita in PowerShell. Le stesse impostazioni sono disponibili quando si crea una regola come descritto nel [passaggio 2: utilizzare PowerShell per creare una regola di filtro di protezione da posta indesiderata in uscita](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) più indietro in questo argomento.

Per modificare una regola di filtro posta indesiderata in uscita, utilizzare la sintassi seguente:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>Utilizzo di PowerShell per abilitare o disabilitare le regole di filtro della posta indesiderata in uscita

L'abilitazione o disabilitazione di una regola di filtro per la posta indesiderata in uscita in PowerShell consente di abilitare o disabilitare l'intero criterio di posta indesiderata in uscita (la regola del filtro posta indesiderata in uscita e il criterio filtro posta indesiderata Non è possibile abilitare o disabilitare il criterio di posta indesiderata in uscita predefinito (viene sempre applicato sempre a tutti i destinatari).

Per abilitare o disabilitare una regola di filtro per la posta indesiderata in uscita in PowerShell, utilizzare la sintassi seguente:

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

In questo esempio viene disabilitata la regola di filtro posta indesiderata in uscita denominata Marketing Department.

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

In questo esempio viene abilitata la stessa regola.

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) e [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>Utilizzo di PowerShell per impostare la priorità delle regole del filtro per la posta indesiderata in uscita

Il valore di priorità più alto che è possibile impostare in una regola è 0. Il valore più basso che è possibile impostare dipende dal numero di regole. Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4. Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole. Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola su 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.

Per impostare la priorità di una regola di filtro di protezione da posta indesiderata in uscita in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

**Note**:

- Per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-HostedOutboundSpamFilterRule** .

- I criteri di filtro della posta indesiderata in uscita non dispongono di una regola di filtro di posta indesiderata corrispondente e il valore di priorità immodificabile è sempre **inferiore**.

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>Utilizzo di PowerShell per rimuovere i criteri di filtro della posta indesiderata in uscita

Quando si utilizza PowerShell per rimuovere un criterio di filtro della posta indesiderata in uscita, la regola di filtro posta indesiderata in uscita corrispondente non viene rimossa

Per rimuovere un criterio di filtro per la posta indesiderata in uscita in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

In questo esempio viene rimosso il criterio di filtro per la posta indesiderata in uscita denominato Marketing Department.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>Utilizzo di PowerShell per rimuovere le regole di filtro della posta indesiderata in uscita

Quando si utilizza PowerShell per rimuovere una regola di filtro per la posta indesiderata in uscita, il criterio di filtro posta indesiderata in uscita corrispondente non viene rimosso

Per rimuovere una regola di filtro di protezione da posta indesiderata in uscita in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

In questo esempio viene rimossa la regola di filtro posta indesiderata in uscita denominata Marketing Department.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).

## <a name="for-more-information"></a>Ulteriori informazioni

[Rimuovere utenti bloccati dal portale Utenti con restrizioni](removing-user-from-restricted-users-portal-after-spam.md)

[Pool di recapito ad alto rischio per i messaggi in uscita](high-risk-delivery-pool-for-outbound-messages.md)

[Domande frequenti sulla protezione da posta indesiderata](anti-spam-protection-faq.md)
