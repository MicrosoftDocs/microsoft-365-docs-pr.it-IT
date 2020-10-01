---
title: Configurare i criteri anti-phishing ATP
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
description: Gli amministratori possono ottenere informazioni su come creare, modificare ed eliminare i criteri di anti-phishing avanzati disponibili nelle organizzazioni con Office 365 Advanced Threat Protection (Office 365 ATP).
ms.openlocfilehash: c08046bdc9e72bc824dc28acdf2443c9071236a0
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333547"
---
# <a name="configure-atp-anti-phishing-policies"></a>Configurare i criteri anti-phishing ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

I criteri di anti-phishing ATP fanno parte di [Office 365 Advanced Threat Protection](office-365-atp.md). I criteri di anti-phishing ATP consentono di proteggere l'organizzazione da attacchi di phishing basati sulla rappresentazione malevola e altri tipi di attacchi di phishing. Per ulteriori informazioni sulle differenze tra i criteri di anti-phishing in Exchange Online Protection (EOP) e i criteri di anti-phishing ATP, vedere [protezione anti-phishing](anti-phishing-protection.md).

Gli amministratori possono visualizzare, modificare e configurare (ma non eliminare) il criterio anti-phishing predefinito del trifosfato di adenosina. Per una maggiore granularità, è anche possibile creare criteri di anti-phishing ATP personalizzati che si applicano a utenti, gruppi o domini specifici nell'organizzazione. I criteri personalizzati hanno sempre la precedenza sul criterio predefinito, ma non è possibile modificarne la priorità (in funzione).

È possibile configurare i criteri di anti-phishing ATP nel centro sicurezza & Compliance o in PowerShell di Exchange Online.

Per informazioni sulla configurazione dei criteri di anti-phishing più limitati disponibili nelle organizzazioni di protezione di Exchange Online (ovvero le organizzazioni Microsoft 365 senza Office 365 ATP), vedere [Configure anti-phishing Policies in EOP](configure-anti-phishing-policies-eop.md).

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a>Criteri di anti-phishing ATP nel centro sicurezza & Compliance vs PowerShell

Gli elementi di base di un criterio anti-phishing ATP sono:

- **Il criterio anti-phishing**: specifica le protezioni di phishing da abilitare o disabilitare e le azioni da applicare.
- **La regola phishing**: specifica la priorità e i filtri destinatario (a chi si applica il criterio) per un criterio anti-phishing.

La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri di anti-phishing ATP nel centro sicurezza & Compliance:

- Quando si crea un criterio, si sta effettivamente creando una regola anti-phishing e il criterio anti-phishing associato contemporaneamente utilizzando lo stesso nome per entrambi.
- Quando si modifica un criterio, le impostazioni relative al nome, alla priorità, abilitate o disabilitate e ai filtri destinatario modificano la regola phishing. Tutte le altre impostazioni modificano i criteri anti-phishing associati.
- Quando si rimuove un criterio, la regola anti-phishing e i criteri anti-phishing associati vengono rimossi.

In Exchange Online PowerShell, è possibile gestire il criterio e la regola separatamente. Per ulteriori informazioni, vedere la sezione [utilizzare Exchange Online PowerShell per configurare i criteri di anti-phishing ATP](#use-exchange-online-powershell-to-configure-atp-anti-phishing-policies) più avanti in questo argomento.

Ogni organizzazione ATP di Office 365 ha un criterio anti-phishing incorporato denominato Office365 antiphishing default con queste proprietà:

- Il criterio viene applicato a tutti i destinatari dell'organizzazione, anche se non è presente alcuna regola anti-phishing (filtri destinatario) associata al criterio.
- Il valore personalizzato della priorità del criterio è **Minore** e non può essere modificato (il criterio viene sempre applicato per ultimo). Qualsiasi criterio personalizzato creato avrà sempre una priorità più alta.
- Il criterio è quello predefinito (la proprietà **IsDefault** contiene il valore `True`), e non è possibile eliminarlo.

Per aumentare l'efficacia della protezione anti-phishing, è possibile creare criteri di anti-phishing ATP personalizzati con impostazioni più rigorose applicate a utenti o gruppi di utenti specifici.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per accedere direttamente alla pagina **anti-phishing ATP** , utilizzare <https://protection.office.com/antiphishing> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Prima di poter eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni seguenti:

  - Per aggiungere, modificare ed eliminare i criteri di anti-phishing ATP, è necessario essere membri di uno dei gruppi di ruoli seguenti:

    - **Gestione organizzazione** o **Amministratore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).
    - **Gestione organizzazione** o **Gestione igiene** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Per l'accesso in sola lettura ai criteri di anti-phishing ATP, è necessario essere membri di uno dei gruppi di ruoli seguenti:

    - **Lettore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).
    - **Gestione organizzazione in sola lettura** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Per le impostazioni consigliate per i criteri di anti-phishing ATP, vedere [impostazioni dei criteri di anti-phishing ATP](recommended-settings-for-eop-and-office365-atp.md#atp-anti-phishing-policy-settings).

- Consentire l'applicazione di un criterio nuovo o aggiornato fino a 30 minuti.

- Per informazioni su dove vengono applicati i criteri di anti-phishing nella pipeline dei filtri, vedere [ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a>Utilizzare il Centro sicurezza & conformità per creare criteri di anti-phishing ATP

La creazione di un criterio di anti-phishing ATP personalizzato nel centro sicurezza & conformità crea la regola anti-phishing e i criteri anti-phishing associati contemporaneamente utilizzando lo stesso nome per entrambi.

Quando si crea un criterio di anti-phishing ATP, è possibile specificare solo il nome, la descrizione e il filtro destinatario che identifica gli utenti a cui si applica il criterio. Dopo aver creato il criterio, è possibile modificare il criterio per modificare o rivedere le impostazioni di anti-phishing predefinite.

1. Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.

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
   - **Il dominio del destinatario è**: consente di specificare i destinatari in uno o più dei domini accettati configurati nell'organizzazione.

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

Dopo aver creato il criterio anti-phishing ATP con queste impostazioni generali, utilizzare le istruzioni riportate nella sezione successiva per configurare le impostazioni di protezione nel criterio.

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a>Utilizzare il Centro sicurezza & conformità per modificare i criteri di anti-phishing ATP

Utilizzare le procedure seguenti per modificare i criteri di anti-phishing ATP: un nuovo criterio creato o criteri esistenti già personalizzati.

1. Se non si è ancora presenti, aprire il Centro sicurezza & compliance e passare al criterio di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.

2. Selezionare il criterio di anti-phishing ATP personalizzato che si desidera modificare. Se è già selezionata, deselezionarla e selezionarla di nuovo.

3. Verrà visualizzato il riquadro a comparsa **modifica il criterio \<name\> ** . Fare clic su **modifica** in qualsiasi sezione consente di accedere alle impostazioni di tale sezione.

   - I passaggi seguenti sono presentati nell'ordine in cui vengono visualizzate le sezioni, ma non sono sequenziali (è possibile selezionare e modificare le sezioni in qualsiasi ordine).

   - Dopo aver fatto clic su **modifica** in una sezione, le impostazioni disponibili vengono presentate in un formato di procedura guidata, ma è possibile passare all'interno delle pagine in qualsiasi ordine e fare clic su **Salva** in qualsiasi pagina oppure **annullare** o **chiudere** l' ![ icona Chiudi ](../../media/scc-remove-icon.png) per tornare alla pagina **modifica il criterio \<name\> ** (non è necessario visitare l'ultima pagina della procedura guidata per salvare o lasciare).

4. **Impostazione dei criteri**: fare clic su **modifica** per modificare le stesse impostazioni disponibili quando è stato [creato il criterio](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) nella sezione precedente:

   - **Nome**
   - **Descrizione**
   - **Applicato a**
   - **Esaminare le impostazioni**

   Al termine, fare clic su **Salva** su qualsiasi pagina.

5. **Rappresentazione**: fare clic su **modifica** per modificare i mittenti protetti e i domini protetti nel criterio. Queste impostazioni sono una condizione per i criteri che identificano i mittenti falsificati da cercare (singolarmente o in base al dominio) nell'indirizzo mittente dei messaggi in ingresso. Per ulteriori informazioni, vedere [impostazioni di rappresentazione nei criteri di anti-phishing ATP](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).

   - **Aggiungere gli utenti a Protect**: il valore predefinito è **disattivata**. Per attivarla, scorrere l' **interruttore su attivato**e quindi fare clic sul pulsante **Aggiungi utente** visualizzato.

     Nel riquadro a comparsa **utente aggiunto** che viene visualizzato, configurare i seguenti valori:

     - **Indirizzo di posta elettronica**:

        - Fare clic nella casella e scorrere l'elenco degli utenti da selezionare.
        - Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un utente.
        - Per rimuovere una voce, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) sull'utente.

     - **Nome**: questo valore viene popolato in base all'indirizzo di posta elettronica selezionato, ma è possibile modificarlo.

     Al termine, fare clic su **Salva** su qualsiasi pagina.

    Per modificare una voce esistente, selezionare l'utente protetto nell'elenco.

   - **Aggiungere i domini da proteggere**: configurare una o entrambe le impostazioni seguenti:

     - **Includere automaticamente i domini che possiedo**: il valore predefinito è **disattivata**. Per attivarla, fare scorrere l'interruttore **su**attivato.
     - **Includi domini personalizzati**: il valore predefinito è **disattivata**. Per attivarla, scorrere l'interruttore **su**attivato e nella casella **Aggiungi domini** immettere il nome di dominio (ad esempio, contoso.com), premere invio e ripetere il secondo caso.

       **Nota**: nel centro sicurezza & conformità, è possibile immettere un massimo di 20 domini. In Exchange Online PowerShell, è possibile immettere un massimo di 50 domini.

   - **Azioni**: fare clic su **modifica**

     - **Se il messaggio di posta elettronica viene inviato da un utente rappresentato**: configurare una delle seguenti azioni per i messaggi in cui il mittente falsificato è uno degli utenti protetti specificati in **Add Users to Protect**:

       - **Non applicare alcuna azione**
       - **Reindirizza il messaggio ad altri indirizzi di posta elettronica**
       - **Sposta messaggio nella cartella Posta indesiderata**
       - **Mettere in quarantena il messaggio**
       - **Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**
       - **Eliminare il messaggio prima di essere recapitato**

     - **Se il messaggio di posta elettronica viene inviato da un dominio rappresentato**: configurare una delle seguenti azioni per i messaggi in cui il mittente contraffatto si trova in uno dei domini protetti specificati in **Aggiungi domini da proteggere**:

     - **Non applicare alcuna azione**
     - **Reindirizza il messaggio ad altri indirizzi di posta elettronica**
     - **Sposta messaggio nella cartella Posta indesiderata**
     - **Mettere in quarantena il messaggio**
     - **Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**
     - **Eliminare il messaggio prima di essere recapitato**

   - Fare clic **su Attiva suggerimenti per la sicurezza della rappresentazione** e configurare una delle seguenti impostazioni:

     - **Mostra suggerimento per gli utenti rappresentati**: il valore predefinito è **disattivata**. Per attivarla, fare scorrere l'interruttore **su**attivato.
     - **Mostra suggerimento per i domini rappresentati**: il valore predefinito è **disattivata**. Per attivarla, fare scorrere l'interruttore **su**attivato.
     - **Mostra suggerimento per i caratteri insoliti**: il valore predefinito è **disattivata**. Per attivarla, fare scorrere l'interruttore **su**attivato.

     Al termine, scegliere **Salva**.

   - **Intelligence delle cassette postali**:

     - Abilitare la funzionalità di **Intelligence delle cassette postali?**: il valore predefinito è **on**. Per disattivarla, fare scorrere l'interruttore su **disattivata**.

     - **Abilitare la protezione della rappresentazione basata sull'Intelligence delle cassette postali?**: questa impostazione è disponibile solo se abilitare la funzionalità **di** **Intelligence delle cassette postali?** è attiva.

       **Se il messaggio di posta elettronica viene inviato da un utente rappresentato**, è possibile specificare una delle seguenti azioni da intraprendere per i messaggi che non riescono a utilizzare l'intelligence delle cassette postali (le stesse azioni disponibili per gli utenti protetti e i domini protetti):

       - **Non applicare alcuna azione**
       - **Reindirizza il messaggio ad altri indirizzi di posta elettronica**
       - **Sposta messaggio nella cartella Posta indesiderata**
       - **Mettere in quarantena il messaggio**
       - **Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**
       - **Eliminare il messaggio prima di essere recapitato**

   - **Aggiungere i domini e i mittenti attendibili**: specificare le eccezioni per il criterio:

     - **Mittenti attendibili**:

       - Fare clic nella casella e scorrere l'elenco degli utenti da selezionare.
       - Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un utente.
       - Per rimuovere una voce, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) sull'utente.

     - **Domini attendibili**: immettere il nome di dominio (ad esempio, contoso.com), premere invio e ripetere se necessario.

   - **Esaminare le impostazioni**: invece di fare clic su ogni singolo passaggio, le impostazioni vengono visualizzate in un riepilogo.

     - È possibile fare clic su **modifica** in ogni sezione per tornare alla pagina pertinente.
     - È possibile attivare o **disattivare** le seguenti impostazioni **direttamente in questa** pagina:

       - **Utenti protetti**
       - **Domini protetti** \> **Includere domini personali**
       - **Domini protetti** \> **Domini protetti** (domini personalizzati)
       - **Intelligence della cassetta postale**

   Al termine, fare clic su **Salva** su qualsiasi pagina.

6. **Spoof**: fare clic su **modifica** per abilitare o disabilitare l'intelligence di spoofing, abilitare l'identificazione dei mittenti non autenticati in Outlook attivato o disattivato e configurare l'azione da applicare ai messaggi provenienti da mittenti bloccati falsificati. Per ulteriori informazioni, vedere [spoofing Settings in anti-phishing Policies](set-up-anti-phishing-policies.md#spoof-settings).

   Si noti che le stesse impostazioni sono disponibili anche nei criteri di anti-phishing in EOP.

   - **Impostazioni del filtro di spoofing**: il valore predefinito **è attivato**e si consiglia di lasciarlo acceso. Per disattivarla, fare scorrere l'interruttore su **disattivata**. Per ulteriori informazioni, vedere [Configure Spoofing Intelligence in EOP](learn-about-spoof-intelligence.md).

     > [!NOTE]
     > Non è necessario disabilitare la protezione anti-spoofing se il record MX non punta a Microsoft 365; è invece possibile abilitare il filtro avanzato per i connettori. Per istruzioni, vedere [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   - **Abilita funzionalità mittente non autenticato** **: il valore predefinito è**attivato. Per disattivarla, fare scorrere l'interruttore su **disattivata**.

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

7. **Impostazioni avanzate**: fare clic su **modifica** per configurare le soglie di phishing avanzate. Per ulteriori informazioni, vedere [soglie di phishing avanzate nei criteri di anti-phishing ATP](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).

   - **Soglie di phishing avanzate**: selezionare uno dei seguenti valori:

   - **1-standard** (questo è il valore predefinito).
   - **2-aggressivo**
   - **3-maggiore aggressività**
   - **4-la più aggressiva**

   - **Esaminare le impostazioni**: fare clic su **modifica** per tornare alla pagina **soglie di phishing avanzate** .

   Al termine, fare clic su **Salva** in una delle pagine.

8. Tornare alla pagina **modifica il criterio \<Name\> ** , rivedere le impostazioni, quindi fare clic su **Chiudi**.

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a>Utilizzare il Centro sicurezza & conformità per modificare il criterio anti-phishing predefinito di ATP

Il criterio anti-phishing ATP predefinito è denominato Office365 antiphishing default e non viene visualizzato nell'elenco dei criteri. Per modificare i criteri di anti-phishing predefiniti, eseguire le operazioni seguenti:

1. Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.

2. Nella pagina **anti-phishing** fare clic su **criteri predefiniti**.

3. Viene visualizzata la pagina **modifica il criterio Office365 antiphishing predefinita** . Sono disponibili le sezioni seguenti, che contengono impostazioni identiche per quando si [modifica un criterio personalizzato](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):

   - **Rappresentazione**
   - **Spoof**
   - **Impostazioni avanzate**

   Le impostazioni seguenti non sono disponibili quando si modifica il criterio predefinito:

   - È possibile visualizzare la sezione e i valori dell' **impostazione dei criteri** , ma non esiste alcun collegamento di **modifica** , quindi non è possibile modificare le impostazioni (nome del criterio, descrizione e l'utente a cui si applica il criterio, applicabile a tutti i destinatari).
   - Non è possibile eliminare il criterio predefinito.
   - Non è possibile modificare la priorità del criterio predefinito (viene sempre applicato per ultimo).

4. Nella pagina **modifica il criterio Office365 antiphishing predefinita** , esaminare le impostazioni e quindi fare clic su **Chiudi**.

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a>Abilitare o disabilitare i criteri di anti-phishing ATP personalizzati

1. Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.

2. Si noti il valore nella colonna **stato** :

   - Fare scorrere l'interruttore su **disattivato** per disabilitare il criterio.

   - Scorrere l'interruttore **su** attivato per abilitare il criterio.

Non è possibile disabilitare il criterio anti-phishing predefinito.

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a>Impostare la priorità dei criteri personalizzati di anti-phishing ATP

Per impostazione predefinita, ai criteri di anti-phishing ATP viene assegnata una priorità che si basa sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità più bassa rispetto ai criteri precedenti). Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa). Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.

Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).

I criteri di anti-phishing ATP personalizzati vengono visualizzati nell'ordine in cui sono stati elaborati (il primo criterio ha il valore di **priorità** 0). Il criterio anti-phishing predefinito denominato Office365 antiphishing default ha il valore di priorità personalizzato **più basso**e non è possibile modificarlo.

 **Nota**: nel centro sicurezza & conformità è possibile modificare solo la priorità dei criteri di anti-phishing ATP dopo averlo creato. In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola anti-phishing (che può influire sulla priorità delle regole esistenti).

Per modificare la priorità di un criterio, fare clic su **aumenta priorità** o su **Diminuisci priorità** nelle proprietà del criterio (non è possibile modificare direttamente il numero di **priorità** nel centro sicurezza & conformità). La modifica della priorità di un criterio ha senso solo se si dispone di più criteri.

1. Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.

2. Selezionare il criterio che si desidera modificare. Se è già selezionata, deselezionarla e selezionarla di nuovo.

3. Verrà visualizzato il riquadro a comparsa **modifica il criterio \<name\> ** .

   - Il criterio di anti-phishing ATP personalizzato con il valore di **priorità** **0** ha solo il pulsante di **riduzione della priorità** disponibile.

   - Il criterio di antiphishing personalizzato ATP con il valore di **priorità** più basso (ad esempio, **3**) ha solo il pulsante **aumenta priorità** disponibile.

   - Se si dispone di tre o più criteri di anti-phishing personalizzati, i criteri tra i valori di priorità più alti e quelli più bassi sono disponibili per i pulsanti **aumenta priorità** e **Riduci priorità** .

4. Fare clic su **aumenta priorità** o su **Diminuisci priorità** per modificare il valore di **priorità** .

5. Al termine, fare clic su **Chiudi**.

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a>Utilizzare il Centro sicurezza & conformità per visualizzare i criteri di anti-phishing ATP

1. Nel centro sicurezza & conformità e passare a criteri di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.

2. Eseguire una delle operazioni seguenti:

   - Selezionare un criterio di anti-phishing ATP personalizzato che si desidera visualizzare. Se è già selezionata, deselezionarla e selezionarla di nuovo.

   - Fare clic su **criteri predefiniti** per visualizzare i criteri di anti-phishing predefiniti.

3. Verrà visualizzato il riquadro a comparsa **modifica il criterio \<name\> ** , in cui è possibile visualizzare le impostazioni e i valori.

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a>Utilizzare il Centro sicurezza & conformità per rimuovere i criteri di anti-phishing ATP

1. Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.

2. Selezionare il criterio che si desidera rimuovere. Se è già selezionata, deselezionarla e selezionarla di nuovo.

3. Nel riquadro a comparsa **modifica \<name\> il criterio** visualizzato, fare clic su **Elimina criteri**, quindi fare clic su **Sì** nella finestra di dialogo di avviso visualizzata.

Non è possibile rimuovere il criterio predefinito.

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a>Utilizzare PowerShell di Exchange Online per configurare i criteri di anti-phishing ATP

Come descritto in precedenza, un criterio di protezione da posta indesiderata ATP è costituito da un criterio anti-phishing e da una regola anti-phishing.

In Exchange Online PowerShell, la differenza tra i criteri anti-phishing e le regole anti-phishing è evidente. Per gestire i criteri anti-phishing è possibile utilizzare i cmdlet ** \* -AntiPhishPolicy** e gestire le regole di anti-phishing utilizzando i cmdlet ** \* -AntiPhishRule** .

- In PowerShell, è necessario creare innanzitutto il criterio phishing, quindi creare la regola anti-phishing che identifica il criterio a cui si applica la regola.
- In PowerShell, è possibile modificare le impostazioni nel criterio di phishing e la regola anti-phishing separatamente.
- Quando si rimuove un criterio di phishing da PowerShell, la regola anti-phishing corrispondente non viene rimossa automaticamente e viceversa.

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
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

In questo esempio viene creato il criterio phishing denominato Research Quarantine con le seguenti impostazioni:

- Il criterio è abilitato (non viene utilizzato il parametro _Enabled_ e il valore predefinito è `$true` ).
- La descrizione è: criteri del reparto ricerche.
- Consente la protezione dei domini dell'organizzazione per tutti i domini accettati e la protezione dei domini mirati per fabrikam.com.
- Specifica Mai Fujito (mfujito@fabrikam.com) come l'utente da proteggere da imitazione.
- Abilita l'intelligence della cassetta postale.
- Consente di abilitare la protezione dall'intelligence della cassetta postale e di specificare l'azione di quarantena.
- Consente di abilitare i suggerimenti per la sicurezza.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
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

A parte gli elementi seguenti, le stesse impostazioni sono disponibili quando si modifica un criterio di phishing in PowerShell come quando si crea il criterio come descritto nel [passaggio 1: utilizzare PowerShell per creare una sezione dei criteri anti-phishing](#step-1-use-powershell-to-create-an-anti-phish-policy) più indietro in questo argomento.

- L'opzione _MakeDefault_ che consente di trasformare il criterio specificato nel criterio predefinito (applicato a tutti, priorità sempre **più bassa** e non è possibile eliminarla) è disponibile solo quando si modifica un criterio di protezione da phishing in PowerShell.

- Non è possibile rinominare un criterio anti-phishing (il cmdlet **set-AntiPhishPolicy** non ha un parametro _Name_ ). Quando si rinomina un criterio anti-phishing nel centro sicurezza & Compliance, viene rinominata solo la _regola_anti-phishing.

Per modificare un criterio di phishing, utilizzare la sintassi seguente:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).

### <a name="use-powershell-to-modify-anti-phish-rules"></a>Utilizzo di PowerShell per modificare le regole anti-phishing

L'unica impostazione che non è disponibile quando si modifica una regola anti-phishing in PowerShell è il parametro _Enabled_ che consente di creare una regola disattivata. Per abilitare o disabilitare le regole anti-phishing esistenti, vedere la sezione successiva.

In caso contrario, non sono disponibili ulteriori impostazioni quando si modifica una regola anti-phishing in PowerShell. Le stesse impostazioni sono disponibili quando si crea una regola come descritto nel [passaggio 2: utilizzo di PowerShell per creare una sezione di regola anti-phishing](#step-2-use-powershell-to-create-an-anti-phish-rule) più indietro in questo argomento.

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

Per verificare la corretta configurazione dei criteri di anti-phishing ATP, eseguire una delle operazioni seguenti:

- Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**. Verificare l'elenco dei criteri, i relativi valori di **stato** e i relativi valori di **priorità** . Per visualizzare ulteriori dettagli, eseguire una delle operazioni seguenti:

  - Selezionare il criterio dall'elenco e visualizzare i dettagli nel riquadro a comparsa.
  - Fare clic su **criteri predefiniti** e visualizzare i dettagli nel riquadro a comparsa.

- In Exchange Online PowerShell, sostituire \<Name\> con il nome del criterio o della regola ed eseguire il comando riportato di seguito e verificare le impostazioni:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
