---
title: Configurare i criteri Collegamenti sicuri in Office 365 ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni su come visualizzare, creare, modificare ed eliminare i criteri per i collegamenti sicuri e le impostazioni dei collegamenti sicuri globali in Office 365 Advanced Threat Protection (ATP).
ms.openlocfilehash: cf60820297401de92781a48f22f70d1f503e3097
ms.sourcegitcommit: 260c69fa31a898428d51cfdbd762c5f0213c403c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "48417257"
---
# <a name="set-up-safe-links-policies-in-office-365-atp"></a>Configurare i criteri Collegamenti sicuri in Office 365 ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Questo articolo è rivolto ai clienti aziendali di [Office 365 Advanced Threat Protection](office-365-atp.md). Se si è un utente di casa che cerca informazioni su Safelinks in Outlook, vedere [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Collegamenti attendibili è una funzionalità di [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) che fornisce l'analisi degli URL dei messaggi di posta elettronica in ingresso nel flusso di posta e l'ora in cui si fa clic su verifica degli URL e dei collegamenti nei messaggi di posta elettronica e in altre posizioni. Per ulteriori informazioni, vedere [collegamenti sicuri in Office 365 ATP](atp-safe-links.md).

Non esiste alcun criterio di collegamenti sicuri incorporato o predefinito. Per ottenere l'analisi dei collegamenti sicuri degli URL, è necessario creare uno o più criteri per i collegamenti sicuri, come descritto in questo articolo.

È possibile configurare i criteri per i collegamenti sicuri nel centro sicurezza & conformità o in PowerShell (Exchange Online PowerShell per organizzazioni Microsoft 365 idonee con cassette postali in Exchange Online; standalone EOP PowerShell per le organizzazioni senza cassette postali di Exchange Online, ma con le sottoscrizioni del componente aggiuntivo ATP di Office 365).

Gli elementi di base di un criterio collegamenti sicuri sono i seguenti:

- **Il criterio collegamenti sicuri**: attiva la protezione dei collegamenti sicuri, attiva l'analisi degli URL in tempo reale, specifica se attendere che l'analisi in tempo reale venga completata prima di recapitare il messaggio, attivare la ricerca per i messaggi interni, specificare se tenere presenti gli scatti degli utenti sugli URL e specificare se consentire agli utenti di fare clic su trogolo all'URL originale.
- **La regola per i collegamenti sicuri**: specifica i filtri priorità e destinatario (a chi si applica il criterio).

La differenza tra questi due elementi non è ovvia quando si gestiscono le politiche dei collegamenti sicuri nel centro sicurezza & conformità:

- Quando si crea un criterio per i collegamenti sicuri, si sta effettivamente creando una regola per i collegamenti sicuri e il criterio collegamenti sicuri associati contemporaneamente utilizzando lo stesso nome per entrambi.
- Quando si modifica un criterio per i collegamenti sicuri, le impostazioni relative ai filtri nome, priorità, abilitato o disabilitato e destinatario modificano la regola dei collegamenti sicuri. Tutte le altre impostazioni modificano il criterio collegamenti sicuri associato.
- Quando si rimuove un criterio per i collegamenti sicuri, la regola collegamenti sicuri e i criteri collegamenti sicuri associati vengono rimossi.

In PowerShell di Exchange Online o in EOP PowerShell autonomo i criteri e la regola vengono gestiti separatamente. Per ulteriori informazioni, vedere la sezione [use Exchange Online PowerShell or standalone EOP PowerShell per configurare i criteri dei collegamenti sicuri](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) più avanti in questo articolo.

> [!NOTE]
> È possibile configurare le impostazioni globali per la protezione di collegamenti sicuri **all'esterno** dei criteri collegamenti sicuri. Per istruzioni, vedere [Configure Global Settings for Safe Links in Office 365 ATP](configure-global-settings-for-safe-links.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per accedere direttamente alla pagina **collegamenti sicuri di ATP** , utilizzare <https://protection.office.com/safelinksv2> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Per visualizzare, creare, modificare ed eliminare i criteri per i collegamenti sicuri, è necessario essere membri di uno dei gruppi di ruoli seguenti:

  - **Gestione organizzazione** o **Amministratore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).
  - **Gestione dell'organizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Per le impostazioni consigliate per i criteri collegamenti sicuri, vedere [impostazioni dei criteri collegamenti sicuri](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).

- Consentire l'applicazione di un criterio nuovo o aggiornato fino a 30 minuti.

- Le [nuove funzionalità vengono continuamente aggiunte al trifosfato di adenosina](office-365-atp.md#new-features-in-office-365-atp). Man mano che si aggiungono nuove funzionalità, potrebbe essere necessario apportare modifiche ai criteri dei collegamenti sicuri esistenti.

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a>Utilizzare il Centro sicurezza & conformità per creare i criteri collegamenti sicuri

La creazione di un criterio collegamenti sicuri personalizzato nel centro sicurezza & conformità crea la regola dei collegamenti sicuri e il criterio collegamenti sicuri associati contemporaneamente utilizzando lo stesso nome per entrambi.

1. Nel centro sicurezza & conformità, accedere a **Threat management** \> **Policy** \> **collegamenti sicuri ATP**per i criteri di gestione delle minacce.

2. Nella pagina **collegamenti sicuri** fare clic su **Crea**.

3. Verrà visualizzata la procedura guidata **nuovo criterio collegamenti sicuri** . Nella pagina **Name Your Policy** , configurare le seguenti impostazioni:

   - **Nome**: immettere un nome univoco descrittivo per il criterio.

   - **Descrizione**: immettere una descrizione opzionale per il criterio.

   Al termine dell'operazione, fare clic su **Avanti**.

4. Nella pagina **Impostazioni** che viene visualizzata, configurare le seguenti impostazioni:

   - **Selezionare l'azione per gli URL potenzialmente dannosi sconosciuti nei messaggi**: selezionare Attiva per abilitare la protezione dei collegamenti sicuri per i collegamenti nei **messaggi di posta** elettronica.

   - **Selezionare l'azione per gli URL sconosciuti o potenzialmente dannosi all'interno di Microsoft teams** **: selezionare Attiva** per abilitare la protezione dei collegamenti sicuri per i collegamenti nei team.

   - **Applicazione dell'analisi degli URL in tempo reale per collegamenti e collegamenti sospetti che puntano a file**: selezionare questa impostazione per abilitare l'analisi in tempo reale dei collegamenti nei messaggi di posta elettronica.

   - **Attendere il completamento dell'analisi degli URL prima di recapitare il messaggio**: selezionare questa impostazione per attendere il completamento dell'analisi degli URL in tempo reale prima di recapitare il messaggio.

   - **Applicazione di collegamenti sicuri ai messaggi di posta elettronica inviati all'interno dell'organizzazione**: selezionare questa impostazione per applicare il criterio collegamenti sicuri ai messaggi tra i mittenti interni e i destinatari interni.

   - **Non tenere traccia dei clic degli utenti**: lasciare questa impostazione deselezionata per abilitare l'utente di verifica facendo clic sugli URL nei messaggi di posta elettronica.

   - **Non consentire agli utenti di fare clic sull'URL originale**: selezionare questa impostazione per impedire agli utenti di fare clic sull'URL originale nelle [pagine di avviso](atp-safe-links.md#warning-pages-from-safe-links).

   - **Non riscrivere gli URL seguenti**: consente di accedere agli URL specificati che altrimenti verrebbero bloccati da collegamenti sicuri.

     Nella casella digitare l'URL o il valore desiderato e quindi fare clic su ![Icona Aggiungi pulsante](../../media/ITPro-EAC-AddIcon.png).

     Per rimuovere una voce esistente, selezionarla e fare clic su ![Icona pulsante Elimina](../../media/ITPro-EAC-DeleteIcon.png).

     Per la sintassi delle voci, vedere [la sintassi della voce per l'elenco "non riscrivere gli URL seguenti"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).

   Per informazioni dettagliate su queste impostazioni, vedere [impostazioni dei collegamenti sicuri per i messaggi di posta elettronica](atp-safe-links.md#safe-links-settings-for-email-messages) e [le impostazioni dei collegamenti sicuri per Microsoft teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).

   Per ulteriori informazioni sui valori consigliati per le impostazioni dei criteri standard e rigorosi, vedere [Safe Links Policy Settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nella pagina **applicata alla** pagina che viene visualizzata, identificare i destinatari interni ai quali si applica il criterio.

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

6. Nella pagina **Verifica le impostazioni** che viene visualizzata, esaminare le impostazioni. È possibile fare clic su **modifica** su ogni impostazione per modificarla.

   Al termine dell'operazione, scegliere **Fine**.

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a>Utilizzare il Centro sicurezza & conformità per visualizzare i criteri collegamenti sicuri

1. Nel centro sicurezza & conformità, accedere a **Threat management** \> **Policy** \> **collegamenti sicuri ATP**per i criteri di gestione delle minacce.

2. Nella pagina **collegamenti attendibili** , selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).

   I dettagli del criterio vengono visualizzati in un volo

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a>Utilizzare il Centro sicurezza & conformità per modificare i criteri per i collegamenti sicuri

1. Nel centro sicurezza & conformità, accedere a **Threat management** \> **Policy** \> **collegamenti sicuri ATP**per i criteri di gestione delle minacce.

2. Nella pagina **collegamenti attendibili** , selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).

3. Nei dettagli del criterio, fare clic su **modifica criterio**.

Le impostazioni disponibili nel volo visualizzato sono identiche a quelle descritte nella sezione [use the Security & Compliance Center to create Safe Links Policies](#use-the-security--compliance-center-to-create-safe-links-policies) .

Per abilitare o disabilitare un criterio o impostare l'ordine di priorità dei criteri, vedere le sezioni seguenti.

### <a name="enable-or-disable-safe-links-policies"></a>Abilitare o disabilitare i criteri per i collegamenti sicuri

1. Nel centro sicurezza & conformità, accedere a **Threat management** \> **Policy** \> **collegamenti sicuri ATP**per i criteri di gestione delle minacce.

2. Si noti il valore nella colonna **stato** :

   - Spostare l'interruttore a sinistra per disabilitare il criterio: ![Disattiva criterio](../../media/scc-toggle-off.png).

   - Spostare l'interruttore a destra per abilitare il criterio: ![Attiva il criterio](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

### <a name="set-the-priority-of-safe-links-policies"></a>Impostare la priorità dei criteri collegamenti sicuri

Per impostazione predefinita, ai criteri collegamenti sicuri viene assegnata una priorità che si basa sull'ordine in cui sono stati creati (le politiche più recenti hanno una priorità più bassa rispetto ai criteri precedenti). Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa). Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.

Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).

I criteri collegamenti sicuri vengono visualizzati nell'ordine in cui sono stati elaborati (il primo criterio ha il valore di **priorità** 0).

**Nota**: nel centro sicurezza & conformità è possibile modificare solo la priorità dei criteri collegamenti sicuri dopo averlo creato. In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola per i collegamenti sicuri (che può influire sulla priorità delle regole esistenti).

Per modificare la priorità di un criterio, spostare il criterio più in alto o più in basso nell'elenco (non è possibile modificare direttamente il numero **Priority** nel Centro sicurezza e conformità).

1. Nel centro sicurezza & conformità, accedere a **Threat management** \> **Policy** \> **collegamenti sicuri ATP**per i criteri di gestione delle minacce.

2. Nella pagina **collegamenti attendibili** , selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).

3. Nei dettagli dei criteri volare che viene visualizzato, fare clic sul pulsante priorità disponibile:

   - Il criterio collegamenti sicuri con il valore di **priorità** **0** ha solo il pulsante di **riduzione della priorità** disponibile.

   - Il criterio collegamenti sicuri con il valore di **priorità** più basso (ad esempio, **3**) ha solo il pulsante **aumenta priorità** disponibile.

   - Se si dispone di tre o più criteri per i collegamenti sicuri, i criteri tra i valori di priorità più alti e quelli più bassi sono disponibili per i pulsanti **aumenta priorità** e **Riduci priorità** .

4. Fare clic su **aumenta priorità** o su **Diminuisci priorità** per modificare il valore di **priorità** .

5. Al termine, fare clic su **Chiudi**.

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a>Utilizzare il Centro sicurezza & conformità per rimuovere i criteri per i collegamenti sicuri

1. Nel centro sicurezza & conformità, accedere a **Threat management** \> **Policy** \> **collegamenti sicuri ATP**per i criteri di gestione delle minacce.

2. Nella pagina **collegamenti attendibili** , selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).

3. Nei dettagli dei criteri che vengono visualizzati, fare clic su **Elimina criteri**, quindi fare clic su **Sì** nella finestra di dialogo di avviso visualizzata.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>Utilizzare PowerShell di Exchange Online o standalone EOP PowerShell per configurare i criteri per i collegamenti sicuri

Come descritto in precedenza, un criterio per i collegamenti sicuri è costituito da un criterio collegamenti sicuri e da una regola per i collegamenti sicuri.

In PowerShell, la differenza tra i criteri collegamenti sicuri e le regole per i collegamenti sicuri è evidente. Per gestire i criteri collegamenti sicuri è possibile utilizzare i cmdlet ** \* -SafeLinksPolicy** e gestire le regole per i collegamenti sicuri utilizzando i cmdlet ** \* -SafeLinksRule** .

- In PowerShell, creare innanzitutto il criterio collegamenti sicuri, quindi creare la regola collegamenti sicuri che identifica il criterio a cui si applica la regola.
- In PowerShell, è possibile modificare le impostazioni nel criterio collegamenti sicuri e la regola collegamenti sicuri separatamente.
- Quando si rimuove un criterio per i collegamenti sicuri da PowerShell, la regola relativa ai collegamenti sicuri corrispondente non viene rimossa automaticamente e viceversa.

### <a name="use-powershell-to-create-safe-links-policies"></a>Utilizzo di PowerShell per creare i criteri per i collegamenti sicuri

La creazione di un criterio collegamenti sicuri in PowerShell è un processo in due passaggi:

1. Creare il criterio collegamenti sicuri.
2. Creare la regola per i collegamenti sicuri che specifica il criterio collegamenti sicuri a cui si applica la regola.

 **Note**:

- È possibile creare una nuova regola per i collegamenti sicuri e assegnare un criterio di collegamenti sicuri esistente e non associato. Una regola per i collegamenti sicuri non può essere associata a più di un criterio collegamenti sicuri.

- È possibile configurare le impostazioni seguenti sui nuovi criteri collegamenti sicuri in PowerShell che non sono disponibili nel centro sicurezza & conformità fino a dopo la creazione del criterio:

  - Creare il nuovo criterio come disabilitato (_attivato_ `$false` nel cmdlet **New-SafeLinksRule** ).
  - Impostare la priorità del criterio durante la creazione (_priorità_ _\<Number\>_ ) del cmdlet **New-SafeLinksRule** .

- Un nuovo criterio collegamenti sicuri creato in PowerShell non è visibile nel centro sicurezza & conformità fino a quando non si assegna il criterio a una regola per i collegamenti sicuri.

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>Passaggio 1: utilizzare PowerShell per creare un criterio per i collegamenti sicuri

Per creare un criterio per i collegamenti sicuri, utilizzare la sintassi seguente:

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

**Note**:

- Per informazioni dettagliate sulla sintassi delle voci da utilizzare per il parametro _DoNotRewriteUrls_ , vedere la [sintassi relativa alla voce per l'elenco "non riscrivere gli URL seguenti"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).

- Per ulteriori informazioni sulla sintassi che è possibile utilizzare per il parametro _DoNotRewriteUrls_ quando si modificano i criteri collegamenti sicuri esistenti utilizzando il cmdlet **set-SafeLinksPolicy** , vedere la sezione [Use PowerShell to Modify Safe Links Policies](#use-powershell-to-modify-safe-links-policies) più avanti in questo articolo.

In questo esempio viene creato un criterio per i collegamenti sicuri denominato contoso all con i valori seguenti:

- Attiva l'analisi e la riscrittura degli URL nei messaggi di posta elettronica.
- Attiva l'analisi degli URL nei team (toccare solo anteprima).
- Attiva l'analisi in tempo reale degli URL cliccati, inclusi i collegamenti cliccati che puntano ai file.
- Attendere il completamento dell'analisi degli URL prima di recapitare il messaggio.
- Attiva l'analisi e la riscrittura degli URL per i messaggi interni.
- Monitorare gli utenti che si riferiscono alla protezione dei collegamenti sicuri (non si utilizza il parametro _DoNotTrackUserClicks_ e il valore predefinito è $false, il che significa che i clic dell'utente vengono registrati).
- Non consentire agli utenti di fare clic sull'URL originale.

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>Passaggio 2: utilizzare PowerShell per creare una regola per i collegamenti sicuri

Per creare una regola per i collegamenti sicuri, utilizzare la sintassi seguente:

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

In questo esempio viene creata una regola per i collegamenti sicuri denominata Contoso all con le condizioni seguenti:

- La regola è associata al criterio per i collegamenti sicuri denominato contoso all.
- La regola viene applicata a tutti i destinatari del dominio contoso.com.
- Poiché non si utilizza il parametro _Priority_ , viene utilizzata la priorità predefinita.
- La regola è abilitata (non viene utilizzato il parametro _Enabled_ e il valore predefinito è `$true` ).

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).

### <a name="use-powershell-to-view-safe-links-policies"></a>Utilizzo di PowerShell per visualizzare i criteri per i collegamenti sicuri

Per visualizzare i criteri collegamenti sicuri esistenti, utilizzare la sintassi seguente:

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In questo esempio viene restituito un elenco riepilogativo di tutti i criteri collegamenti sicuri.

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

In questo esempio vengono restituite informazioni dettagliate per il criterio collegamenti sicuri denominato contoso Executives.

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).

### <a name="use-powershell-to-view-safe-links-rules"></a>Utilizzo di PowerShell per visualizzare le regole per i collegamenti sicuri

Per visualizzare le regole per i collegamenti sicuri esistenti, utilizzare la sintassi seguente:

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In questo esempio viene restituito un elenco riepilogativo di tutte le regole relative ai collegamenti sicuri.

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

In questo esempio vengono restituite informazioni dettagliate per la regola per i collegamenti sicuri denominata Contoso Executives.

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).

### <a name="use-powershell-to-modify-safe-links-policies"></a>Utilizzo di PowerShell per modificare i criteri per i collegamenti sicuri

Non è possibile rinominare un criterio di collegamenti sicuri in PowerShell (il cmdlet **set-SafeLinksPolicy** non ha un parametro _Name_ ). Quando si rinomina un criterio per i collegamenti sicuri nel centro sicurezza & conformità, si sta solo rinominando la _regola_dei collegamenti sicuri.

L'unica ulteriore considerazione per la modifica dei criteri collegamenti sicuri in PowerShell è la sintassi disponibile per il parametro _DoNotRewriteUrls_ (l' [elenco "non riscrivere gli URL seguenti"](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):

- Per aggiungere valori che sostituiranno le voci esistenti, utilizzare la sintassi seguente: `"Entry1","Entry2,..."EntryN"` .
- Per aggiungere o rimuovere valori senza alterare altre voci esistenti, utilizzare la sintassi seguente: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

In caso contrario, le stesse impostazioni sono disponibili quando si crea un criterio per i collegamenti sicuri come descritto nel [passaggio 1: utilizzare PowerShell per creare una sezione dei criteri collegamenti sicuri](#step-1-use-powershell-to-create-a-safe-links-policy) più indietro in questo articolo.

Per modificare un criterio collegamenti sicuri, utilizzare la sintassi seguente:

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).

### <a name="use-powershell-to-modify-safe-links-rules"></a>Utilizzo di PowerShell per modificare le regole per i collegamenti sicuri

L'unica impostazione che non è disponibile quando si modifica una regola per i collegamenti sicuri in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata. Per abilitare o disabilitare le regole per i collegamenti sicuri esistenti, vedere la sezione successiva.

In caso contrario, le stesse impostazioni sono disponibili quando si crea una regola come descritto nel [passaggio 2: utilizzare PowerShell per creare una regola per i collegamenti sicuri](#step-2-use-powershell-to-create-a-safe-links-rule) descritta in precedenza in questo articolo.

Per modificare una regola per i collegamenti sicuri, utilizzare la sintassi seguente:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>Utilizzo di PowerShell per abilitare o disabilitare le regole per i collegamenti sicuri

L'abilitazione o disabilitazione di una regola per i collegamenti sicuri in PowerShell consente di abilitare o disabilitare l'intero criterio collegamenti sicuri (la regola collegamenti sicuri e il criterio collegamenti sicuri assegnati).

Per abilitare o disabilitare una regola per i collegamenti sicuri in PowerShell, utilizzare la sintassi seguente:

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

In questo esempio viene disabilitata la regola per i collegamenti sicuri denominata Marketing Department.

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

In questo esempio viene abilitata la stessa regola.

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) e [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>Utilizzo di PowerShell per impostare la priorità delle regole per i collegamenti sicuri

Il valore di priorità più alto che è possibile impostare in una regola è 0. Il valore più basso che è possibile impostare dipende dal numero di regole. Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4. Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole. Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola su 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.

Per impostare la priorità di una regola per i collegamenti sicuri in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

**Nota**: per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-SafeLinksRule** .

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).

### <a name="use-powershell-to-remove-safe-links-policies"></a>Utilizzo di PowerShell per rimuovere i criteri per i collegamenti sicuri

Quando si utilizza PowerShell per rimuovere un criterio per i collegamenti sicuri, la regola relativa ai collegamenti sicuri corrispondente non viene rimossa.

Per rimuovere un criterio collegamenti sicuri in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

In questo esempio viene rimosso il criterio collegamenti sicuri denominato Marketing Department.

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).

### <a name="use-powershell-to-remove-safe-links-rules"></a>Utilizzo di PowerShell per rimuovere le regole per i collegamenti sicuri

Quando si utilizza PowerShell per rimuovere una regola per i collegamenti sicuri, il criterio collegamenti sicuri corrispondente non viene rimosso.

Per rimuovere una regola per i collegamenti sicuri in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

In questo esempio viene rimossa la regola per i collegamenti sicuri denominata Marketing Department.

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).

Per verificare che i collegamenti sicuri eseguano l'analisi dei messaggi, controllare i report di protezione avanzata delle minacce disponibili. Per ulteriori informazioni, vedere [View Reports for Office 365 ATP](view-reports-for-atp.md) e [use Explorer in the Security & Compliance Center](threat-explorer.md).

## <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare che i criteri collegamenti sicuri siano stati creati, modificati o rimossi correttamente, eseguire una delle operazioni seguenti:

- Nel centro sicurezza & conformità, accedere a **Threat management** \> **Policy** \> **collegamenti sicuri ATP**per i criteri di gestione delle minacce. Verificare l'elenco dei criteri, i relativi valori di **stato** e i relativi valori di **priorità** . Per visualizzare ulteriori dettagli, selezionare il criterio dall'elenco e visualizzare i dettagli all'interno del volo.

- In Exchange Online PowerShell o Exchange Online Protection PowerShell, sostituire \<Name\> con il nome del criterio o della regola, eseguire il comando riportato di seguito e verificare le impostazioni:

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
