---
title: Configurare i criteri anti-phishing in Exchange Online Protection
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a creare, modificare ed eliminare i criteri anti-phishing disponibili nelle organizzazioni di Exchange Online Protection (EOP) con o senza cassette postali di Exchange Online.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5bab5e791cb58c4e681a802179583471bb6ab165
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287914"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>Configurare i criteri anti-phishing in Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, esiste un criterio anti-phishing predefinito che contiene un numero limitato di funzionalità di anti-spoofing abilitate per impostazione predefinita. Per ulteriori informazioni, vedere [Impostazioni di spoofing nei criteri anti-phishing.](set-up-anti-phishing-policies.md#spoof-settings)

Gli amministratori possono visualizzare, modificare e configurare (ma non eliminare) il criterio anti-phishing predefinito. Per una maggiore granularità, è inoltre possibile creare criteri anti-phishing personalizzati che si applicano a utenti, gruppi o domini specifici nell'organizzazione. I criteri personalizzati hanno sempre la precedenza sul criterio predefinito, ma non è possibile modificarne la priorità (in funzione).

Le organizzazioni con cassette postali di Exchange Online possono configurare i criteri anti-phishing nel Centro sicurezza & conformità o in PowerShell di Exchange Online. Le organizzazioni EOP autonome possono utilizzare solo il Centro sicurezza & conformità.

Per informazioni sulla creazione e la modifica dei criteri anti-phishing più avanzati in Microsoft Defender per Office 365 disponibili in Defender per Office 365, vedere Configurare i criteri [anti-phishing in Microsoft Defender per Office 365.](configure-atp-anti-phishing-policies.md)

Gli elementi di base di un criterio anti-phishing sono:

- **Il criterio anti-phishing**: specifica le protezioni anti-phishing da abilitare o disabilitare e le azioni da applicare.
- **La regola anti-phish**: specifica la priorità e i filtri destinatario (a chi si applica il criterio) per un criterio anti-phish.

La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri anti-phishing nel Centro sicurezza & conformità:

- Quando si crea un criterio anti-phishing, si crea una regola anti-phishing e il criterio anti-phishing associato contemporaneamente usando lo stesso nome per entrambi.
- Quando si modifica un criterio anti-phishing, le impostazioni relative al nome, alla priorità, abilitata o disabilitata e i filtri destinatari modificano la regola anti-phishing. Tutte le altre impostazioni modificano il criterio anti-phish associato.
- Quando si rimuove un criterio anti-phishing, la regola anti-phishing e il criterio anti-phishing associato vengono rimossi.

In PowerShell di Exchange Online, il criterio e la regola vengono gestiti separatamente. Per ulteriori informazioni, vedere la sezione Utilizzare PowerShell di Exchange Online per configurare i criteri [anti-phishing](#use-exchange-online-powershell-to-configure-anti-phishing-policies) più avanti in questo articolo.

Ogni organizzazione dispone di un criterio anti-phishing predefinito denominato Office365 AntiPhish Default con queste proprietà:

- Il criterio viene applicato a tutti i destinatari nell'organizzazione, anche se al criterio non è associata alcuna regola anti-phish (filtri destinatari).
- Il valore personalizzato della priorità del criterio è **Minore** e non può essere modificato (il criterio viene sempre applicato per ultimo). Qualsiasi criterio personalizzato creato avrà sempre una priorità più alta.
- Il criterio è quello predefinito (la proprietà **IsDefault** contiene il valore `True`), e non è possibile eliminarlo.

Per aumentare l'efficacia della protezione anti-phishing, è possibile creare criteri anti-phishing personalizzati con impostazioni più rigide applicate a utenti o gruppi di utenti specifici.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla pagina **anti-phishing,** utilizzare <https://protection.office.com/antiphishing> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

  Non è possibile gestire i criteri anti-phishing in PowerShell EOP autonomo.

- Per poter eseguire le procedure contenute in questo articolo è necessario disporre delle autorizzazioni appropriate nel Centro sicurezza e conformità:
  - Per aggiungere, modificare ed eliminare criteri anti-phishing, è necessario essere membri dei gruppi di ruoli **Gestione** organizzazione o Amministratore **sicurezza.**
  - Per l'accesso in sola lettura ai criteri anti-phishing, è  necessario essere membri dei gruppi di ruoli **Lettore** globale o Lettore di <sup>\*</sup> sicurezza.

  Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

  **Note**:

  - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).
  - Il **gruppo di ruoli Gestione organizzazione** di sola visualizzazione in Exchange [Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) consente inoltre l'accesso in sola lettura alla <sup>\*</sup> funzionalità.
  - <sup>\*</sup> Nel Centro sicurezza & conformità, l'accesso di sola lettura consente agli utenti di visualizzare le impostazioni dei criteri anti-phishing personalizzati. Gli utenti di sola lettura non possono visualizzare le impostazioni nel criterio anti-phishing predefinito.

- Per creare e modificare i criteri anti-phishing in EOP autonomo, è necessario eseguire un'operazione che richiede l'idratazione _per_ il tenant. Ad esempio, nell'interfaccia di amministrazione di Exchange  (EAC), è possibile accedere  alla scheda Autorizzazioni, selezionare un gruppo di ruoli esistente, fare clic sull'icona Modifica modifica e rimuovere un ruolo (che verrà infine aggiunto ![ ](../../media/ITPro-EAC-EditIcon.png) di nuovo). Se il tenant non è mai stato idratato, viene visualizzata una finestra di dialogo denominata **Update Organization Settings** con una barra di stato che dovrebbe essere completata correttamente. Per ulteriori informazioni sull'idratazione, vedere il cmdlet [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) (che non è disponibile in PowerShell EOP autonomo o nel Centro sicurezza & conformità).

- Per le impostazioni consigliate per i criteri anti-phishing, vedere Impostazioni dei criteri [anti-phishing predefiniti di EOP.](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)

- Consentire fino a 30 minuti per l'applicazione del criterio aggiornato.

- Per informazioni su dove vengono applicati i criteri anti-phishing nella pipeline di filtro, vedere [Ordine e precedenza della protezione della posta elettronica.](how-policies-and-protections-are-combined.md)

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a>Usare il Centro sicurezza & conformità per creare criteri anti-phishing

La creazione di un criterio anti-phishing personalizzato nel Centro sicurezza & conformità crea contemporaneamente la regola anti-phishing e il criterio anti-phishing associato usando lo stesso nome per entrambi.

Quando si crea un criterio anti-phishing, è possibile specificare solo il nome, la descrizione e il filtro destinatario che identifica a chi si applica il criterio. Dopo aver creato il criterio, è possibile modificare il criterio per modificare o rivedere le impostazioni anti-phishing predefinite.

1. Nel Centro sicurezza & conformità passare a Criteri di **gestione** delle minacce \>  \> **Anti-phishing.**

2. Nella pagina **Anti-phishing** fare clic su **Crea.**

3. Verrà visualizzata la procedura guidata Crea un nuovo **criterio anti-phishing.** Nella pagina **Assegnare un nome al** criterio configurare le impostazioni seguenti:

   - **Nome**: immettere un nome univoco descrittivo per il criterio.

   - **Descrizione**: immettere una descrizione opzionale per il criterio.

   Al termine dell'operazione, fare clic su **Avanti**.

4. Nella pagina **Applicato a** visualizzata, identificare i destinatari interni a cui si applica il criterio.

   È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione. Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_). Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).

   Fare **clic su Aggiungi condizione.** Nell'elenco a discesa visualizzato selezionare una condizione in **Applicato se:**

   - **Il destinatario è**: specifica una o più cassette postali, utenti di posta o contatti di posta nell'organizzazione.
   - **Il destinatario è membro di**: Specifica uno o più gruppi nell'organizzazione.
   - **Il dominio del destinatario è**: specifica i destinatari in uno o più dei domini configurati accettati nell'organizzazione.

   Dopo aver selezionato la condizione, viene visualizzato un elenco a discesa corrispondente con **una qualsiasi di queste** caselle.

   - Fare clic nella casella e scorrere l'elenco dei valori da selezionare.
   - Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un valore.
   - Per aggiungere ulteriori valori, fare clic in un'area vuota della casella.
   - Per rimuovere singole voci, fare **clic sull'icona** ![ Rimuovi sul ](../../media/scc-remove-icon.png) valore.
   - Per rimuovere l'intera condizione, fare **clic sull'icona** ![ Rimuovi nella ](../../media/scc-remove-icon.png) condizione.

   Per aggiungere una condizione aggiuntiva, fare clic **su Aggiungi una condizione** e selezionare un valore rimanente in Applicato **se.**

   Per aggiungere eccezioni, fare clic **su Aggiungi una condizione** e selezionare un'eccezione in Tranne **se**. Impostazioni e comportamento sono equivalenti alle condizioni.

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nella pagina **Verifica le impostazioni** visualizzata, rivedere le impostazioni. È possibile fare **clic su** Modifica per ogni impostazione per modificarla.

   Al termine, fare clic **su Crea questo criterio.**

6. Fare **clic su OK** nella finestra di dialogo di conferma visualizzata.

Dopo aver creato il criterio anti-phishing con queste impostazioni generali, seguire le istruzioni nella sezione successiva per configurare le impostazioni di protezione nel criterio.

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a>Utilizzare il Centro sicurezza & conformità per modificare i criteri anti-phishing

Utilizzare le procedure seguenti per modificare i criteri anti-phishing: un nuovo criterio creato dall'utente o criteri esistenti già personalizzati.

1. Se non si è già presenti, aprire il Centro sicurezza  & conformità e passare a Criteri di gestione delle minacce \>  \> **Anti-phishing.**

2. Selezionare il criterio anti-phishing personalizzato che si desidera modificare. Se è già selezionato, deselezionalo e selezionalo di nuovo.

3. Viene **visualizzato \<name\> il riquadro a comparsa** Modifica il criterio. Se **si fa** clic su Modifica in una sezione, è possibile accedere alle impostazioni in tale sezione.

   - I passaggi seguenti vengono presentati nell'ordine in cui vengono visualizzate le sezioni, ma non sono sequenziali (è possibile selezionare e modificare le sezioni in qualsiasi ordine).

   - Dopo aver fatto clic su Modifica **in** una sezione, le impostazioni disponibili vengono presentate in un  formato di procedura guidata,  ma è possibile passare alle pagine in qualsiasi ordine ed è possibile fare clic su Salva in qualsiasi pagina (o  ![ ](../../media/scc-remove-icon.png) **\<name\>** sull'icona Annulla o Chiudi chiudi per tornare alla pagina Modifica i criteri (non è necessario visitare l'ultima pagina della procedura guidata per salvare o uscire).

4. **Impostazione dei criteri:** **fare** clic su Modifica per modificare le stesse impostazioni disponibili quando [è](#use-the-security--compliance-center-to-create-anti-phishing-policies) stato creato il criterio nella sezione precedente:

   - **Nome**
   - **Descrizione**
   - **Applicato a**
   - **Rivedere le impostazioni**

   Al termine, fare clic su **Salva** in qualsiasi pagina.

5. **Spoof**:  fare clic su Modifica per attivare o disattivare spoof intelligence, attivare o disattivare l'identificazione del mittente non autenticato in Outlook e configurare l'azione da applicare ai messaggi provenienti da mittenti falsificati bloccati. Per ulteriori informazioni, vedere [Impostazioni di spoofing nei criteri anti-phishing.](set-up-anti-phishing-policies.md#spoof-settings)

   Si noti che queste stesse impostazioni sono disponibili anche nei criteri anti-phishing in Defender per Office 365.

   - **Impostazioni del filtro per lo spoofing**: il valore predefinito è **On** e si consiglia di lasciarlo. Per disattivarlo, far scorrere l'interruttore su **Disattivato.** Per ulteriori informazioni, vedere [Configurare spoof intelligence in EOP.](learn-about-spoof-intelligence.md)

     > [!NOTE]
     > Non è necessario disabilitare la protezione anti-spoofing se il record MX non punta a Microsoft 365; si abilita invece il filtro avanzato per i connettori. Per istruzioni, vedere [Enhanced Filtering for Connectors in Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

   - **Abilitare la funzionalità Mittente non autenticato**: il valore predefinito è **Attivato.** Per disattivarlo, far scorrere l'interruttore su **Disattivato.**

   - **Azioni**: specificare l'azione da eseguire sui messaggi che non riescono a spoof intelligence:

     Se la posta elettronica viene inviata da un utente a cui non è consentito **effettuare lo spoofing del dominio:**

     - **Spostare il messaggio nelle cartelle Posta indesiderata dei destinatari**
     - **Mettere in quarantena il messaggio**

   - **Rivedere le impostazioni:** invece di fare clic su ogni singolo passaggio, le impostazioni vengono visualizzate in un riepilogo.

     - È possibile fare **clic su Modifica** in ogni sezione per tornare alla pagina pertinente.
     - È possibile attivare o **disattivare** le **impostazioni** seguenti direttamente in questa pagina:

       - **Abilitare la protezione antispoofing**
       - **Abilitare la funzionalità Mittente non autenticato**

   Al termine, fare clic su **Salva** in qualsiasi pagina.

6. Tornare alla pagina **Modifica i \<Name\> criteri,** rivedere le impostazioni e quindi fare clic su **Chiudi.**

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>Utilizzare il Centro sicurezza & conformità per modificare il criterio anti-phishing predefinito

Il criterio anti-phishing predefinito è denominato Office365 AntiPhish Default e non viene visualizzato nell'elenco dei criteri. Per modificare il criterio anti-phishing predefinito, eseguire la procedura seguente:

1. Nel Centro sicurezza & conformità passare a Criteri di **gestione** delle minacce \>  \> **Anti-phishing.**

2. Nella pagina **Anti-phishing** fare clic su **Criterio predefinito.**

3. Verrà **visualizzata la pagina Modifica i criteri predefiniti di Office365 AntiPhish.** Sono disponibili le sezioni seguenti, che contengono le stesse impostazioni per la modifica [di un criterio personalizzato.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)

   - **Rappresentazione**
   - **Spoofing**
   - **Impostazioni avanzate**

   Le impostazioni seguenti non sono disponibili quando si modifica il criterio predefinito:

   - È possibile  visualizzare la sezione e i valori  dell'impostazione dei criteri, ma non è disponibile alcun collegamento Modifica, quindi non è possibile modificare le impostazioni (nome del criterio, descrizione e a chi si applica il criterio (si applica a tutti i destinatari)).
   - Non è possibile eliminare il criterio predefinito.
   - Non è possibile modificare la priorità del criterio predefinito (viene sempre applicato per ultimo).

4. Nella pagina **Modifica i criteri predefiniti di Office365,** rivedere le impostazioni e quindi fare clic su **Chiudi.**

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>Abilitare o disabilitare i criteri anti-phishing personalizzati

1. Nel Centro sicurezza & conformità passare a Criteri di **gestione** delle minacce \>  \> **Anti-phishing.**

2. Si noti il valore nella **colonna** Stato:

   - Fai scorrere **l'interruttore su Off** per disabilitare il criterio.

   - Far scorrere **l'interruttore su Attivato** per abilitare il criterio.

Non è possibile disabilitare il criterio anti-phishing predefinito.

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>Impostare la priorità dei criteri anti-phishing personalizzati

Per impostazione predefinita, ai criteri anti-phishing viene data una priorità che si basa sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità inferiore rispetto ai criteri precedenti). Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa). Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.

Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).

I criteri anti-phishing personalizzati vengono visualizzati nell'ordine in cui vengono elaborati (il primo criterio ha il **valore Priority** 0). Il criterio anti-phishing predefinito denominato Office365 AntiPhish Default ha il valore di priorità personalizzato **Lowest** e non è possibile modificarlo.

 **Nota:** nel Centro sicurezza & conformità, è possibile modificare la priorità del criterio anti-phishing solo dopo aver creato il criterio. In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola anti-phish (che può influire sulla priorità delle regole esistenti).

Per modificare la priorità di  un criterio, fare clic su Aumenta priorità o Diminuisci  priorità nelle proprietà del criterio (non è possibile modificare direttamente il numero di priorità nel Centro sicurezza & conformità).  La modifica della priorità di un criterio è utile solo se si dispone di più criteri.

1. Nel Centro sicurezza & conformità passare **a** Anti-phishing dei criteri di gestione delle \>  \> **minacce ATP.**

2. Selezionare il criterio che si desidera modificare. Se è già selezionato, deselezionalo e selezionalo di nuovo.

3. Viene **visualizzato \<name\> il riquadro a comparsa** Modifica il criterio.

   - Il criterio anti-phishing personalizzato con **il valore Priority** **0** ha solo il **pulsante Diminuisci** priorità disponibile.

   - Il criterio anti-phishing personalizzato con il valore **Di** priorità più basso (ad esempio, **3)** ha solo il pulsante **Aumenta** priorità disponibile.

   - Se si dispone di tre o più criteri anti-phishing personalizzati,  i criteri tra i valori di priorità più alta e più bassa hanno entrambi i pulsanti Aumenta priorità e **Diminuisci** priorità disponibili.

4. Fare **clic su Aumenta priorità** o **Diminuisci priorità** per modificare il valore **di** Priorità.

5. Al termine, fare clic su **Chiudi**.

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a>Usare il Centro sicurezza & conformità per visualizzare i criteri anti-phishing

1. Nel Centro sicurezza & conformità e passare a Criteri di **gestione** delle minacce \>  \> **Anti-phishing.**

2. Eseguire una delle operazioni seguenti:

   - Selezionare un criterio anti-phishing personalizzato che si desidera visualizzare. Se è già selezionato, deselezionalo e selezionalo di nuovo.

   - Fare **clic su Criterio predefinito** per visualizzare il criterio anti-phishing predefinito.

3. Viene **visualizzato \<name\> il riquadro a comparsa** Modifica il criterio, in cui è possibile visualizzare le impostazioni e i valori.

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a>Utilizzare il Centro sicurezza & conformità per rimuovere i criteri anti-phishing

1. Nel Centro sicurezza & conformità passare a Criteri di **gestione** delle minacce \>  \> **Anti-phishing.**

2. Selezionare il criterio che si desidera rimuovere. Se è già selezionato, deselezionalo e selezionalo di nuovo.

3. Nel riquadro **a \<name\> comparsa Modifica** criterio visualizzato fare clic su Elimina criterio **e** quindi su **Sì** nella finestra di dialogo di avviso visualizzata.

Non è possibile rimuovere il criterio predefinito.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>Utilizzare PowerShell di Exchange Online per configurare i criteri anti-phishing

Come descritto in precedenza, un criterio anti-phishing è costituito da un criterio anti-phishing e da una regola anti-phishing.

In PowerShell di Exchange Online, la differenza tra i criteri anti-phish e le regole anti-phish è evidente. È possibile gestire i criteri anti-phish utilizzando i cmdlet **\* -AntiPhishPolicy** e gestire le regole anti-phish utilizzando i cmdlet **\* -AntiPhishRule.**

- In PowerShell, si crea prima il criterio anti-phish, quindi si crea la regola anti-phish che identifica il criterio a cui si applica la regola.
- In PowerShell, le impostazioni dei criteri anti-phish e della regola anti-phish vengono modificate separatamente.
- Quando si rimuove un criterio anti-phish da PowerShell, la regola anti-phish corrispondente non viene rimossa automaticamente e viceversa.

> [!NOTE]
> Le procedure di PowerShell seguenti non sono disponibili nelle organizzazioni EOP autonome che utilizzano PowerShell di Exchange Online Protection.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>Utilizzare PowerShell per creare criteri anti-phishing

La creazione di un criterio anti-phishing in PowerShell è un processo in due passaggi:

1. Creare il criterio anti-phish.
2. Creare la regola anti-phish che specifica il criterio anti-phish a cui si applica la regola.

 **Note**:

- È possibile creare una nuova regola anti-phish e assegnarle un criterio anti-phish esistente e non associazione. Una regola anti-phish non può essere associata a più criteri anti-phish.

- È possibile configurare le impostazioni seguenti nei nuovi criteri anti-phish in PowerShell che non sono disponibili nel Centro sicurezza & conformità fino a quando non si crea il criterio:

  - Creare il nuovo criterio come disabilitato (_abilitato_ `$false` nel cmdlet **New-AntiPhishRule).**
  - Impostare la priorità del criterio durante la creazione (_Priority_ _\<Number\>_ ) nel cmdlet **New-AntiPhishRule.**

- Un nuovo criterio anti-phish creato in PowerShell non è visibile nel Centro sicurezza & conformità finché non si assegna il criterio a una regola anti-phish.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Passaggio 1: Utilizzare PowerShell per creare un criterio anti-phish

Per creare un criterio anti-phish, utilizzare la sintassi seguente:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

In questo esempio viene creato un criterio anti-phish denominato Research Quarantine con le impostazioni seguenti:

- La descrizione è: Criteri del reparto ricerche.
- Modifica l'azione predefinita per lo spoofing in Quarantena.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Passaggio 2: Utilizzare PowerShell per creare una regola anti-phish

Per creare una regola anti-phish, utilizzare la sintassi seguente:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In questo esempio viene creata una regola anti-phish denominata Research Department con le condizioni seguenti:

- La regola è associata al criterio anti-phish denominato Quarantena ricerche.
- La regola viene applicata ai membri del gruppo denominato Research Department.
- Poiché non viene utilizzato il parametro _Priority,_ viene utilizzata la priorità predefinita.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)

### <a name="use-powershell-to-view-anti-phish-policies"></a>Usare PowerShell per visualizzare i criteri anti-phish

Per visualizzare i criteri anti-phish esistenti, utilizzare la sintassi seguente:

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In questo esempio viene restituito un elenco riepilogativo di tutti i criteri anti-phish insieme alle proprietà specificate.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

In questo esempio vengono restituiti tutti i valori delle proprietà per il criterio anti-phish denominato Executives.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)

### <a name="use-powershell-to-view-anti-phish-rules"></a>Utilizzare PowerShell per visualizzare le regole anti-phish

Per visualizzare le regole anti-phish esistenti, utilizzare la sintassi seguente:

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In questo esempio viene restituito un elenco riepilogativo di tutte le regole anti-phish insieme alle proprietà specificate.

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

In questo esempio vengono restituiti tutti i valori delle proprietà per la regola anti-phish denominata Contoso Executives.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)

### <a name="use-powershell-to-modify-anti-phish-policies"></a>Utilizzare PowerShell per modificare i criteri anti-phish

Oltre agli elementi seguenti, le stesse impostazioni sono disponibili quando si modifica un criterio anti-phish in PowerShell come quando si crea un criterio come descritto nel passaggio [1: Utilizzare PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) per creare un criterio anti-phish più indietro in questo articolo.

- L'opzione _MakeDefault_ che trasforma il criterio specificato nel  criterio predefinito (applicato a tutti, sempre con priorità bassa e non è possibile eliminarlo) è disponibile solo quando si modifica un criterio anti-phish in PowerShell.

- Non è possibile rinominare un criterio anti-phish (il cmdlet **Set-AntiPhishPolicy** non dispone di alcun _parametro_ Name). Quando si rinomina un criterio anti-phishing nel Centro sicurezza & conformità, si rinomina solo la regola anti-phishing.

Per modificare un criterio anti-phish, utilizzare la sintassi seguente:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)

### <a name="use-powershell-to-modify-anti-phish-rules"></a>Utilizzare PowerShell per modificare le regole anti-phish

L'unica impostazione non disponibile quando si modifica una regola anti-phish in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata. Per abilitare o disabilitare le regole anti-phish esistenti, vedere la sezione successiva.

In caso contrario, le stesse impostazioni sono disponibili quando si crea una regola come descritto nel passaggio 2: Utilizzare PowerShell per creare una sezione della regola [anti-phish](#step-2-use-powershell-to-create-an-anti-phish-rule) descritta in precedenza in questo articolo.

Per modificare una regola anti-phish, utilizzare la sintassi seguente:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>Utilizzare PowerShell per abilitare o disabilitare le regole anti-phish

L'abilitazione o la disabilitazione di una regola anti-phishing in PowerShell abilita o disabilita l'intero criterio anti-phishing (la regola anti-phishing e il criterio anti-phishing assegnato). Non è possibile abilitare o disabilitare il criterio anti-phishing predefinito (viene sempre applicato a tutti i destinatari).

Per abilitare o disabilitare una regola anti-phish in PowerShell, utilizzare la sintassi seguente:

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

In questo esempio viene disabilitata la regola anti-phish denominata Marketing Department.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

In questo esempio viene abilitata la stessa regola.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) e [Disable-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>Usare PowerShell per impostare la priorità delle regole anti-phish

Il valore di priorità più alto che è possibile impostare in una regola è 0. Il valore più basso che è possibile impostare dipende dal numero di regole. Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4. Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole. Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola su 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.

Per impostare la priorità di una regola anti-phish in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**Note**:

- Per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-AntiPhishRule.**

- Il criterio anti-phish predefinito non dispone di una regola anti-phish corrispondente e ha sempre il valore di priorità non modificabile **Lowest.**

### <a name="use-powershell-to-remove-anti-phish-policies"></a>Utilizzare PowerShell per rimuovere i criteri anti-phish

Quando si utilizza PowerShell per rimuovere un criterio anti-phish, la regola anti-phish corrispondente non viene rimossa.

Per rimuovere un criterio anti-phish in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

In questo esempio viene rimosso il criterio anti-phish denominato Marketing Department.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)

### <a name="use-powershell-to-remove-anti-phish-rules"></a>Utilizzare PowerShell per rimuovere le regole anti-phish

Quando si utilizza PowerShell per rimuovere una regola anti-phish, il criterio anti-phish corrispondente non viene rimosso.

Per rimuovere una regola anti-phish in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

In questo esempio viene rimossa la regola anti-phish denominata Marketing Department.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)

## <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare la corretta configurazione dei criteri anti-phishing in Microsoft Defender per Office 365, eseguire una delle operazioni seguenti:

- Nel Centro sicurezza & conformità passare a Criteri di **gestione** delle minacce \>  \> **Anti-phishing.** Verificare l'elenco dei criteri, i relativi **valori di** stato e i relativi **valori di** priorità. Per visualizzare ulteriori dettagli, eseguire una delle operazioni seguenti:

  - Selezionare il criterio nell'elenco e visualizzare i dettagli nel riquadro a comparsa.
  - Fare **clic su Criterio** predefinito e visualizzare i dettagli nel riquadro a comparsa.

- In PowerShell di Exchange Online, sostituire con il nome del criterio o della regola, eseguire \<Name\> il comando seguente e verificare le impostazioni:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
