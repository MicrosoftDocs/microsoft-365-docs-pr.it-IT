---
title: Configurazione dei criteri di anti-phishing in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni su come creare, modificare ed eliminare i criteri di anti-phishing disponibili nelle organizzazioni di Exchange Online Protection (EOP) con o senza cassette postali di Exchange Online.
ms.openlocfilehash: 69ab17263ab8c0cc03d3bc4aed6bdf39b251b9fb
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572526"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>Configurazione dei criteri di anti-phishing in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365 organizzazioni con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, è presente un criterio anti-phishing predefinito che contiene un numero limitato di funzionalità di anti-spoofing che sono abilitate per impostazione predefinita. Per ulteriori informazioni, vedere [spoofing Settings in anti-phishing Policies](set-up-anti-phishing-policies.md#spoof-settings).

Gli amministratori possono visualizzare, modificare e configurare (ma non eliminare) il criterio anti-phishing predefinito. Per una maggiore granularità, è anche possibile creare criteri di anti-phishing personalizzati che si applicano a utenti, gruppi o domini specifici nell'organizzazione. I criteri personalizzati hanno sempre la precedenza sul criterio predefinito, ma non è possibile modificarne la priorità (in funzione).

Le organizzazioni con cassette postali di Exchange Online possono configurare criteri di anti-phishing nel centro sicurezza & conformità o in PowerShell di Exchange Online. Le organizzazioni di EOP autonome possono utilizzare solo il Centro sicurezza & Compliance.

Per informazioni sulla creazione e la modifica dei criteri di anti-phishing più avanzati in Microsoft Defender per Office 365 disponibili in Defender per Office 365, vedere [Configure anti-phishing Policies in Microsoft Defender for office 365](configure-atp-anti-phishing-policies.md).

Gli elementi di base di un criterio anti-phishing sono:

- **Il criterio anti-phishing**: specifica le protezioni di phishing da abilitare o disabilitare e le azioni da applicare.
- **La regola phishing**: specifica la priorità e i filtri destinatario (a chi si applica il criterio) per un criterio anti-phishing.

La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri di anti-phishing nel centro sicurezza & Compliance:

- Quando si crea un criterio di anti-phishing, si sta effettivamente creando una regola anti-phishing e il criterio anti-phishing associato contemporaneamente utilizzando lo stesso nome per entrambi.
- Quando si modifica un criterio di anti-phishing, le impostazioni relative ai filtri nome, priorità, abilitato o disabilitato e destinatario modificano la regola phishing. Tutte le altre impostazioni modificano i criteri anti-phishing associati.
- Quando si rimuove un criterio di anti-phishing, vengono rimosse la regola anti-phishing e i criteri anti-phishing associati.

In Exchange Online PowerShell, è possibile gestire il criterio e la regola separatamente. Per ulteriori informazioni, vedere la sezione [utilizzare PowerShell di Exchange Online per configurare i criteri di anti-phishing](#use-exchange-online-powershell-to-configure-anti-phishing-policies) più avanti in questo articolo.

Ogni organizzazione dispone di un criterio di anti-phishing incorporato denominato Office365 antiphishing default con queste proprietà:

- Il criterio viene applicato a tutti i destinatari dell'organizzazione, anche se non è presente alcuna regola anti-phishing (filtri destinatario) associata al criterio.
- Il valore personalizzato della priorità del criterio è **Minore** e non può essere modificato (il criterio viene sempre applicato per ultimo). Qualsiasi criterio personalizzato creato avrà sempre una priorità più alta.
- Il criterio è quello predefinito (la proprietà **IsDefault** contiene il valore `True`), e non è possibile eliminarlo.

Per aumentare l'efficacia della protezione anti-phishing, è possibile creare criteri di anti-phishing personalizzati con impostazioni più rigorose applicate a utenti o gruppi di utenti specifici.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla pagina **anti-phishing** , utilizzare <https://protection.office.com/antiphishing> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

  Non è possibile gestire i criteri di anti-phishing in standalone EOP PowerShell.

- Prima di poter eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni per il Centro sicurezza & Compliance:
  - Per aggiungere, modificare ed eliminare i criteri di anti-phishing, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** .
  - Per l'accesso in sola lettura ai criteri di anti-phishing, è necessario essere membri dei gruppi di ruoli **lettore globale** o lettore di **sicurezza** <sup>\*</sup> .

  Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

  **Note**:

  - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie per il Centro sicurezza & Compliance _e_ le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - Il gruppo di ruoli di **gestione dell'organizzazione di sola visualizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) fornisce anche l'accesso in sola lettura alla funzionalità <sup>\*</sup> .
  - <sup>\*</sup> Nel centro sicurezza & conformità, l'accesso in sola lettura consente agli utenti di visualizzare le impostazioni dei criteri di protezione anti-phishing personalizzati. Gli utenti di sola lettura non sono in grado di visualizzare le impostazioni nei criteri di anti-phishing predefiniti.

- Per creare e modificare criteri di anti-phishing in EOP autonomo, è necessario eseguire un'operazione che richiede l' _idratazione_ per il tenant. Ad esempio, nell'interfaccia di amministrazione di Exchange (EAC), è possibile accedere alla scheda **autorizzazioni** , selezionare un gruppo di ruoli esistente, fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-EditIcon.png) e rimuovere un ruolo (che verrà infine aggiunto di nuovo). Se il tenant non è mai stato idratato, viene visualizzata una finestra di dialogo denominata **Impostazioni organizzazione di aggiornamento** con una barra di avanzamento che deve essere completata correttamente. Per ulteriori informazioni sull'idratazione, vedere il cmdlet [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) (che non è disponibile in standalone EOP PowerShell o nel Security & Compliance Center).

- Per le impostazioni consigliate per i criteri di anti-phishing, vedere [EOP default anti-phishing Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).

- Consentire l'applicazione dei criteri aggiornati fino a 30 minuti.

- Per informazioni su dove vengono applicati i criteri di anti-phishing nella pipeline dei filtri, vedere [ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a>Utilizzare il Centro sicurezza & conformità per creare criteri di anti-phishing

La creazione di un criterio anti-phishing personalizzato nel centro sicurezza & conformità crea la regola anti-phishing e i criteri anti-phishing associati contemporaneamente utilizzando lo stesso nome per entrambi.

Quando si crea un criterio anti-phishing, è possibile specificare solo il nome, la descrizione e il filtro destinatario che identifica gli utenti a cui si applica il criterio. Dopo aver creato il criterio, è possibile modificare il criterio per modificare o rivedere le impostazioni di anti-phishing predefinite.

1. Nel centro sicurezza & conformità, accedere a criterio di **gestione delle minacce** \> **Policy** \> **anti-phishing**.

2. Nella pagina **anti-phishing** fare clic su **Crea**.

3. Verrà visualizzata la procedura guidata **Crea un nuovo criterio anti-phishing** . Nella pagina **Name Your Policy** , configurare le seguenti impostazioni:

   - **Nome**: immettere un nome univoco descrittivo per il criterio.

   - **Descrizione**: immettere una descrizione opzionale per il criterio.

   Al termine dell'operazione, fare clic su **Avanti**.

4. Nella pagina **applicata alla** pagina che viene visualizzata, identificare i destinatari interni ai quali si applica il criterio.

   È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione. Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_). Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).

   Fare clic su **Aggiungi condizione**. Nell'elenco a discesa che viene visualizzato, selezionare una condizione in **applicato se**:

   - **Il destinatario è**: consente di specificare una o più cassette postali, utenti di posta elettronica o contatti di posta nell'organizzazione.
   - **Il destinatario è un membro di**: consente di specificare uno o più gruppi nell'organizzazione.
   - **Il dominio del destinatario è**: specifica i destinatari in uno o più dei domini configurati accettati nell'organizzazione.

   Dopo aver selezionato la condizione, viene visualizzato un elenco a discesa corrispondente con una **qualsiasi di queste** caselle.

   - Fare clic nella casella e scorrere l'elenco di valori da selezionare.
   - Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un valore.
   - Per aggiungere ulteriori valori, fare clic in un'area vuota nella casella.
   - Per rimuovere singole voci, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) sul valore.
   - Per rimuovere l'intera condizione, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) sulla condizione.

   Per aggiungere una condizione aggiuntiva, fare clic su **Aggiungi condizione** e selezionare un valore restante in **applicato se**.

   Per aggiungere eccezioni, fare clic su **Aggiungi condizione** e selezionare un'eccezione in **except if**. Impostazioni e comportamento sono equivalenti alle condizioni.

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nella pagina **Verifica le impostazioni** che viene visualizzata, esaminare le impostazioni. È possibile fare clic su **modifica** su ogni impostazione per modificarla.

   Al termine, fare clic su **crea questo criterio**.

6. Fare clic su **OK** nella finestra di dialogo di conferma che viene visualizzata.

Dopo aver creato il criterio di anti-phishing con queste impostazioni di criteri generali, utilizzare le istruzioni nella sezione successiva per configurare le impostazioni di protezione nel criterio.

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a>Utilizzare il Centro sicurezza & conformità per modificare i criteri di anti-phishing

Per modificare i criteri di anti-phishing, utilizzare le procedure seguenti: un nuovo criterio creato o criteri esistenti già personalizzati.

1. Se non si è ancora presenti, aprire il Centro sicurezza & compliance e passare a criterio di **gestione delle minacce** \> **Policy** \> **anti-phishing**.

2. Selezionare il criterio di anti-phishing personalizzato che si desidera modificare. Se è già selezionata, deselezionarla e selezionarla di nuovo.

3. Verrà visualizzato il riquadro a comparsa **modifica il criterio \<name\>** . Fare clic su **modifica** in qualsiasi sezione consente di accedere alle impostazioni di tale sezione.

   - I passaggi seguenti sono presentati nell'ordine in cui vengono visualizzate le sezioni, ma non sono sequenziali (è possibile selezionare e modificare le sezioni in qualsiasi ordine).

   - Dopo aver fatto clic su **modifica** in una sezione, le impostazioni disponibili vengono presentate in un formato di procedura guidata, ma è possibile passare all'interno delle pagine in qualsiasi ordine e fare clic su **Salva** in qualsiasi pagina oppure **annullare** o **chiudere** l' ![ icona Chiudi ](../../media/scc-remove-icon.png) per tornare alla pagina **modifica il criterio \<name\>** (non è necessario visitare l'ultima pagina della procedura guidata per salvare o lasciare).

4. **Impostazione dei criteri**: fare clic su **modifica** per modificare le stesse impostazioni disponibili quando è stato [creato il criterio](#use-the-security--compliance-center-to-create-anti-phishing-policies) nella sezione precedente:

   - **Nome**
   - **Descrizione**
   - **Applicato a**
   - **Esaminare le impostazioni**

   Al termine, fare clic su **Salva** su qualsiasi pagina.

5. **Spoof**: fare clic su **modifica** per abilitare o disabilitare l'intelligence di spoofing, abilitare l'identificazione dei mittenti non autenticati in Outlook attivato o disattivato e configurare l'azione da applicare ai messaggi provenienti da mittenti bloccati falsificati. Per ulteriori informazioni, vedere [spoofing Settings in anti-phishing Policies](set-up-anti-phishing-policies.md#spoof-settings).

   Si noti che le stesse impostazioni sono disponibili anche nei criteri anti-phishing in Defender per Office 365.

   - **Impostazioni del filtro di spoofing**: il valore predefinito **è attivato** e si consiglia di lasciarlo acceso. Per disattivarla, fare scorrere l'interruttore su **disattivata**. Per ulteriori informazioni, vedere [Configure Spoofing Intelligence in EOP](learn-about-spoof-intelligence.md).

     > [!NOTE]
     > Non è necessario disabilitare la protezione anti-spoofing se il record MX non punta a Microsoft 365; è invece possibile abilitare il filtro avanzato per i connettori. Per istruzioni, vedere [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   - **Abilita funzionalità mittente non autenticato** **: il valore predefinito è** attivato. Per disattivarla, fare scorrere l'interruttore su **disattivata**.

   - **Azioni**: specificare l'azione da intraprendere per i messaggi che non superano l'intelligence spoof:

     **Se il messaggio di posta elettronica viene inviato da un utente che non ha il diritto di falsificare il dominio**:

     - **Spostare il messaggio nelle cartelle di posta indesiderata dei destinatari**
     - **Mettere in quarantena il messaggio**

   - **Esaminare le impostazioni**: invece di fare clic su ogni singolo passaggio, le impostazioni vengono visualizzate in un riepilogo.

     - È possibile fare clic su **modifica** in ogni sezione per tornare alla pagina pertinente.
     - È possibile attivare o **disattivare** le seguenti impostazioni **direttamente in questa** pagina:

       - **Abilitare la protezione antispoofing**
       - **Abilitare la funzionalità mittente non autenticato**

   Al termine, fare clic su **Salva** su qualsiasi pagina.

6. Tornare alla pagina **modifica il criterio \<Name\>** , rivedere le impostazioni, quindi fare clic su **Chiudi**.

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>Utilizzare il Centro sicurezza & conformità per modificare il criterio anti-phishing predefinito

Il criterio anti-phishing predefinito è denominato Office365 antiphishing default e non viene visualizzato nell'elenco dei criteri. Per modificare il criterio anti-phishing predefinito, eseguire le operazioni seguenti:

1. Nel centro sicurezza & conformità, accedere a criterio di **gestione delle minacce** \> **Policy** \> **anti-phishing**.

2. Nella pagina **anti-phishing** fare clic su **criteri predefiniti**.

3. Viene visualizzata la pagina **modifica il criterio Office365 antiphishing predefinita** . Sono disponibili le sezioni seguenti, che contengono impostazioni identiche per il momento in cui si [modifica un criterio personalizzato](#use-the-security--compliance-center-to-modify-anti-phishing-policies).

   - **Rappresentazione**
   - **Spoof**
   - **Impostazioni avanzate**

   Le impostazioni seguenti non sono disponibili quando si modifica il criterio predefinito:

   - È possibile visualizzare la sezione e i valori dell' **impostazione dei criteri** , ma non esiste alcun collegamento di **modifica** , quindi non è possibile modificare le impostazioni (nome del criterio, descrizione e l'utente a cui si applica il criterio, applicabile a tutti i destinatari).
   - Non è possibile eliminare il criterio predefinito.
   - Non è possibile modificare la priorità del criterio predefinito (viene sempre applicato per ultimo).

4. Nella pagina **modifica il criterio Office365 antiphishing predefinita** , esaminare le impostazioni e quindi fare clic su **Chiudi**.

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>Abilitazione o disabilitazione dei criteri di anti-phishing personalizzati

1. Nel centro sicurezza & conformità, accedere a criterio di **gestione delle minacce** \> **Policy** \> **anti-phishing**.

2. Si noti il valore nella colonna **stato** :

   - Fare scorrere l'interruttore su **disattivato** per disabilitare il criterio.

   - Scorrere l'interruttore **su** attivato per abilitare il criterio.

Non è possibile disabilitare il criterio anti-phishing predefinito.

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>Impostare la priorità dei criteri di anti-phishing personalizzati

Per impostazione predefinita, ai criteri di anti-phishing viene assegnata una priorità che si basa sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità più bassa rispetto ai criteri precedenti). Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa). Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.

Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).

I criteri di anti-phishing personalizzati vengono visualizzati nell'ordine in cui sono stati elaborati (il primo criterio ha il valore di **priorità** 0). Il criterio anti-phishing predefinito denominato Office365 antiphishing default ha il valore di priorità personalizzato **più basso** e non è possibile modificarlo.

 **Nota**: nel centro sicurezza & conformità è possibile modificare solo la priorità dei criteri di anti-phishing dopo averlo creato. In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola anti-phishing (che può influire sulla priorità delle regole esistenti).

Per modificare la priorità di un criterio, fare clic su **aumenta priorità** o su **Diminuisci priorità** nelle proprietà del criterio (non è possibile modificare direttamente il numero di **priorità** nel centro sicurezza & conformità). La modifica della priorità di un criterio ha senso solo se si dispone di più criteri.

1. Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.

2. Selezionare il criterio che si desidera modificare. Se è già selezionata, deselezionarla e selezionarla di nuovo.

3. Verrà visualizzato il riquadro a comparsa **modifica il criterio \<name\>** .

   - Il criterio di anti-phishing personalizzato con il valore di **priorità** **0** ha solo il pulsante di **riduzione della priorità** disponibile.

   - Il criterio di anti-phishing personalizzato con il valore di **priorità** più basso (ad esempio, **3**) ha solo il pulsante **aumenta priorità** disponibile.

   - Se si dispone di tre o più criteri di anti-phishing personalizzati, i criteri tra i valori di priorità più alti e quelli più bassi sono disponibili per i pulsanti **aumenta priorità** e **Riduci priorità** .

4. Fare clic su **aumenta priorità** o su **Diminuisci priorità** per modificare il valore di **priorità** .

5. Al termine, fare clic su **Chiudi**.

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a>Utilizzare il Centro sicurezza & conformità per visualizzare i criteri di anti-phishing

1. Nel centro sicurezza & compliance e passare al criterio di **gestione delle minacce** \> **Policy** \> **anti-phishing**.

2. Eseguire una delle operazioni seguenti:

   - Selezionare un criterio di anti-phishing personalizzato che si desidera visualizzare. Se è già selezionata, deselezionarla e selezionarla di nuovo.

   - Fare clic su **criteri predefiniti** per visualizzare i criteri di anti-phishing predefiniti.

3. Verrà visualizzato il riquadro a comparsa **modifica il criterio \<name\>** , in cui è possibile visualizzare le impostazioni e i valori.

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a>Utilizzare il Centro sicurezza & conformità per rimuovere i criteri di anti-phishing

1. Nel centro sicurezza & conformità, accedere a criterio di **gestione delle minacce** \> **Policy** \> **anti-phishing**.

2. Selezionare il criterio che si desidera rimuovere. Se è già selezionata, deselezionarla e selezionarla di nuovo.

3. Nel riquadro a comparsa **modifica \<name\> il criterio** visualizzato, fare clic su **Elimina criteri**, quindi fare clic su **Sì** nella finestra di dialogo di avviso visualizzata.

Non è possibile rimuovere il criterio predefinito.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>Utilizzare PowerShell di Exchange Online per configurare i criteri di anti-phishing

Come descritto in precedenza, un criterio anti-phishing è costituito da un criterio phishing e da una regola anti-phishing.

In Exchange Online PowerShell, la differenza tra i criteri anti-phishing e le regole anti-phishing è evidente. Per gestire i criteri anti-phishing è possibile utilizzare i cmdlet **\* -AntiPhishPolicy** e gestire le regole di anti-phishing utilizzando i cmdlet **\* -AntiPhishRule** .

- In PowerShell, è necessario creare innanzitutto il criterio phishing, quindi creare la regola anti-phishing che identifica il criterio a cui si applica la regola.
- In PowerShell, è possibile modificare le impostazioni nel criterio di phishing e la regola anti-phishing separatamente.
- Quando si rimuove un criterio di phishing da PowerShell, la regola anti-phishing corrispondente non viene rimossa automaticamente e viceversa.

> [!NOTE]
> Le seguenti procedure di PowerShell non sono disponibili nelle organizzazioni di EOP autonome che utilizzano Exchange Online Protection PowerShell.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>Utilizzo di PowerShell per creare criteri di anti-phishing

La creazione di un criterio anti-phishing in PowerShell è un processo in due passaggi:

1. Creare il criterio anti-phishing.
2. Creare la regola anti-phishing che specifica i criteri anti-phishing a cui si applica la regola.

 **Note**:

- È possibile creare una nuova regola anti-phishing e assegnargli un criterio anti-phishing esistente e non associato. Non è possibile associare una regola anti-phishing a più di un criterio anti-phishing.

- È possibile configurare le impostazioni seguenti sui nuovi criteri di phishing in PowerShell che non sono disponibili nel centro sicurezza & conformità fino a dopo la creazione del criterio:

  - Creare il nuovo criterio come disabilitato (_attivato_ `$false` nel cmdlet **New-AntiPhishRule** ).
  - Impostare la priorità del criterio durante la creazione (_priorità_ _\<Number\>_ ) del cmdlet **New-AntiPhishRule** .

- Un nuovo criterio di phishing creato in PowerShell non è visibile nel centro sicurezza & conformità fino a quando non si assegna il criterio a una regola anti-phishing.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Passaggio 1: utilizzare PowerShell per creare un criterio anti-phishing

Per creare un criterio di phishing, utilizzare la sintassi seguente:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

In questo esempio viene creato un criterio anti-phishing denominato Research Quarantine con le seguenti impostazioni:

- La descrizione è: criteri del reparto ricerche.
- Consente di modificare l'azione predefinita per lo spoofing in quarantena.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Passaggio 2: utilizzare PowerShell per creare una regola anti-phishing

Per creare una regola anti-phishing, utilizzare la sintassi seguente:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In questo esempio viene creata una regola di phishing denominata Research Department con le condizioni seguenti:

- La regola è associata ai criteri anti-phishing denominati Research Quarantine.
- La regola viene applicata ai membri del gruppo denominato Research Department.
- Poiché non si utilizza il parametro _Priority_ , viene utilizzata la priorità predefinita.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).

### <a name="use-powershell-to-view-anti-phish-policies"></a>Utilizzo di PowerShell per visualizzare i criteri anti-phishing

Per visualizzare i criteri anti-phishing esistenti, utilizzare la sintassi seguente:

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In questo esempio viene restituito un elenco riepilogativo di tutti i criteri anti-phishing insieme alle proprietà specificate.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

In questo esempio vengono restituiti tutti i valori della proprietà per il criterio phishing denominato Executives.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).

### <a name="use-powershell-to-view-anti-phish-rules"></a>Utilizzo di PowerShell per visualizzare le regole anti-phishing

Per visualizzare le regole anti-phishing esistenti, utilizzare la sintassi seguente:

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In questo esempio viene restituito un elenco riepilogativo di tutte le regole anti-phishing insieme alle proprietà specificate.

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

In questo esempio vengono restituiti tutti i valori della proprietà per la regola phishing denominata Contoso Executives.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).

### <a name="use-powershell-to-modify-anti-phish-policies"></a>Utilizzo di PowerShell per la modifica dei criteri anti-phishing

A parte gli elementi seguenti, le stesse impostazioni sono disponibili quando si modifica un criterio di phishing in PowerShell come quando si crea un criterio come descritto nel [passaggio 1: utilizzare PowerShell per creare un criterio di phishing](#step-1-use-powershell-to-create-an-anti-phish-policy) più indietro in questo articolo.

- L'opzione _MakeDefault_ che consente di trasformare il criterio specificato nel criterio predefinito (applicato a tutti, priorità sempre **più bassa** e non è possibile eliminarla) è disponibile solo quando si modifica un criterio di protezione da phishing in PowerShell.

- Non è possibile rinominare un criterio anti-phishing (il cmdlet **set-AntiPhishPolicy** non ha un parametro _Name_ ). Quando si rinomina un criterio anti-phishing nel centro sicurezza & Compliance, viene rinominata solo la _regola_ anti-phishing.

Per modificare un criterio di phishing, utilizzare la sintassi seguente:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).

### <a name="use-powershell-to-modify-anti-phish-rules"></a>Utilizzo di PowerShell per modificare le regole anti-phishing

L'unica impostazione che non è disponibile quando si modifica una regola anti-phishing in PowerShell è il parametro _Enabled_ che consente di creare una regola disattivata. Per abilitare o disabilitare le regole anti-phishing esistenti, vedere la sezione successiva.

In caso contrario, le stesse impostazioni sono disponibili quando si crea una regola come descritto nel [passaggio 2: utilizzare PowerShell per creare una sezione di regola phishing](#step-2-use-powershell-to-create-an-anti-phish-rule) più indietro in questo articolo.

Per modificare una regola anti-phishing, utilizzare la sintassi seguente:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>Utilizzo di PowerShell per abilitare o disabilitare le regole anti-phishing

L'abilitazione o disabilitazione di una regola anti-phishing in PowerShell consente di abilitare o disabilitare l'intero criterio anti-phishing (la regola anti-phishing e i criteri di anti-phishing assegnati). Non è possibile abilitare o disabilitare il criterio anti-phishing predefinito (viene sempre applicato a tutti i destinatari).

Per abilitare o disabilitare una regola anti-phishing in PowerShell, utilizzare la sintassi seguente:

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

In questo esempio viene disabilitata la regola anti-phishing denominata Marketing Department.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

In questo esempio viene abilitata la stessa regola.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) e [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>Utilizzo di PowerShell per impostare la priorità delle regole anti-phishing

Il valore di priorità più alto che è possibile impostare in una regola è 0. Il valore più basso che è possibile impostare dipende dal numero di regole. Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4. Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole. Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola su 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.

Per impostare la priorità di una regola anti-phishing in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**Note**:

- Per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-AntiPhishRule** .

- I criteri predefiniti di phishing non dispongono di una regola anti-phishing corrispondente e hanno sempre il valore di priorità immodificabile **più basso**.

### <a name="use-powershell-to-remove-anti-phish-policies"></a>Utilizzo di PowerShell per rimuovere i criteri anti-phishing

Quando si utilizza PowerShell per rimuovere un criterio phishing, la regola anti-phishing corrispondente non viene rimossa.

Per rimuovere un criterio di phishing in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

In questo esempio viene rimosso il criterio anti-phishing denominato Marketing Department.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).

### <a name="use-powershell-to-remove-anti-phish-rules"></a>Utilizzo di PowerShell per rimuovere le regole anti-phishing

Quando si utilizza PowerShell per rimuovere una regola anti-phishing, i criteri di anti-phishing corrispondenti non vengono rimossi.

Per rimuovere una regola anti-phishing in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

In questo esempio viene rimossa la regola anti-phishing denominata Marketing Department.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).

## <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare che i criteri di anti-phishing siano stati configurati correttamente in Microsoft Defender per Office 365, eseguire una delle operazioni seguenti:

- Nel centro sicurezza & conformità, accedere a criterio di **gestione delle minacce** \> **Policy** \> **anti-phishing**. Verificare l'elenco dei criteri, i relativi valori di **stato** e i relativi valori di **priorità** . Per visualizzare ulteriori dettagli, eseguire una delle operazioni seguenti:

  - Selezionare il criterio dall'elenco e visualizzare i dettagli nel riquadro a comparsa.
  - Fare clic su **criteri predefiniti** e visualizzare i dettagli nel riquadro a comparsa.

- In Exchange Online PowerShell, sostituire \<Name\> con il nome del criterio o della regola, eseguire il comando riportato di seguito e verificare le impostazioni:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
