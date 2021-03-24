---
title: Configurare i criteri collegamenti sicuri in Microsoft Defender per Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a visualizzare, creare, modificare ed eliminare i criteri collegamenti sicuri e le impostazioni globali dei collegamenti sicuri in Microsoft Defender per Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c8b2cb8b57dcf630b3e07ac387e96ab099ca7403
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064525"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>Configurare i criteri collegamenti sicuri in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Questo articolo è rivolto ai clienti aziendali di [Microsoft Defender per Office 365](defender-for-office-365.md). Se si è un utente principale che desidera informazioni sui collegamenti sicuri in Outlook, vedere [Advanced Outlook.com security.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Collegamenti sicuri è una funzionalità di [Microsoft Defender per Office 365](defender-for-office-365.md) che fornisce l'analisi DEGLI URL dei messaggi di posta elettronica in ingresso nel flusso di posta e l'ora della verifica degli URL e dei collegamenti nei messaggi di posta elettronica e in altre posizioni. Per ulteriori informazioni, vedere [Collegamenti sicuri in Microsoft Defender per Office 365.](safe-links.md)

Non esiste un criterio predefinito o predefinito per i collegamenti sicuri. Per ottenere l'analisi dei collegamenti sicuri degli URL, è necessario creare uno o più criteri collegamenti sicuri come descritto in questo articolo.

> [!NOTE]
> Le impostazioni globali per la protezione dei collegamenti sicuri vengono configurate **all'esterno** dei criteri collegamenti sicuri. Per istruzioni, vedere [Configurare le impostazioni globali per i collegamenti sicuri in Microsoft Defender per Office 365.](configure-global-settings-for-safe-links.md)

È possibile configurare i criteri collegamenti sicuri nel Centro sicurezza e conformità di & o in PowerShell (PowerShell di Exchange Online per le organizzazioni di Microsoft 365 idonee con cassette postali in Exchange Online, PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online, ma con sottoscrizioni di componenti aggiuntivi di Microsoft Defender per Office 365).

Gli elementi di base di un criterio Collegamenti sicuri sono:

- Il criterio collegamenti **sicuri:** attivare la protezione dei collegamenti sicuri, attivare l'analisi degli URL in tempo reale, specificare se attendere il completamento dell'analisi in tempo reale prima di recapitare il messaggio, attivare l'analisi dei messaggi interni, specificare se tenere traccia dei clic degli utenti sugli URL e specificare se consentire agli utenti di fare clic sull'URL originale.
- **La regola dei collegamenti sicuri**: Specifica la priorità e i filtri destinatari (a cui si applica il criterio).

La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri dei collegamenti sicuri nel Centro sicurezza & conformità:

- Quando si crea un criterio Collegamenti sicuri, si crea contemporaneamente una regola per i collegamenti sicuri e il criterio collegamenti sicuri associati utilizzando lo stesso nome per entrambi.
- Quando si modifica un criterio Collegamenti sicuri, le impostazioni relative al nome, alla priorità, abilitate o disabilitate e ai filtri destinatario modificano la regola dei collegamenti sicuri. Tutte le altre impostazioni modificano il criterio dei collegamenti sicuri associati.
- Quando si rimuove un criterio Collegamenti sicuri, la regola dei collegamenti sicuri e il criterio collegamenti sicuri associati vengono rimossi.

In PowerShell di Exchange Online o in EOP PowerShell autonomo i criteri e la regola vengono gestiti separatamente. Per ulteriori informazioni, vedere la sezione Utilizzare PowerShell di Exchange Online o [PowerShell EOP](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) autonomo per configurare i criteri collegamenti sicuri più avanti in questo articolo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Aprire il Centro sicurezza e conformità in<https://protection.office.com/>. Per passare direttamente alla **pagina Collegamenti sicuri,** utilizzare <https://protection.office.com/safelinksv2> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni seguenti:
  - Per creare, modificare ed eliminare i criteri collegamenti sicuri,  è  necessario essere membri dei gruppi di ruoli  Gestione organizzazione  o Amministratore sicurezza nel Centro sicurezza & conformità e membri del gruppo di ruoli Gestione organizzazione in Exchange Online.
  - Per l'accesso in sola lettura ai criteri collegamenti sicuri, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.

  Per ulteriori informazioni, vedere [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and Permissions in Exchange [Online.](/exchange/permissions-exo/permissions-exo)

  > [!NOTE]
  > 
  > - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).
  . - Il **gruppo di ruoli Gestione** organizzazione di sola visualizzazione in Exchange [Online](/Exchange/permissions-exo/permissions-exo#role-groups) consente inoltre l'accesso in sola lettura alla funzionalità.

- Per le impostazioni consigliate per i criteri collegamenti sicuri, vedere [Impostazioni dei criteri Collegamenti sicuri.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)

- Consentire fino a 30 minuti per l'applicazione di un criterio nuovo o aggiornato.

- [Nuove funzionalità vengono continuamente aggiunte a Microsoft Defender per Office 365.](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365) Quando vengono aggiunte nuove funzionalità, potrebbe essere necessario apportare modifiche ai criteri collegamenti sicuri esistenti.

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a>Usare il Centro sicurezza & conformità per creare criteri collegamenti sicuri

La creazione di un criterio collegamenti sicuri personalizzati nel Centro sicurezza & conformità crea contemporaneamente la regola dei collegamenti sicuri e il criterio collegamenti sicuri associati utilizzando lo stesso nome per entrambi.

1. Nel Centro sicurezza & conformità passare a **Criteri** di gestione delle minacce Collegamenti sicuri \>  \> **ATP**.

2. Nella pagina **Collegamenti sicuri** fare clic su **Crea.**

3. Verrà **visualizzata la procedura guidata Nuovo criterio Collegamenti** sicuri. Nella pagina **Assegnare un nome al** criterio configurare le impostazioni seguenti:

   - **Nome**: immettere un nome univoco descrittivo per il criterio.

   - **Descrizione**: immettere una descrizione opzionale per il criterio.

   Al termine dell'operazione, fare clic su **Avanti**.

4. Nella pagina **Impostazioni** visualizzata configurare le impostazioni seguenti:

   - **Selezionare l'azione per URL** sconosciuti potenzialmente dannosi nei messaggi: selezionare **Attivato** per abilitare la protezione collegamenti sicuri per i collegamenti nei messaggi di posta elettronica.

   - **Selezionare l'azione per URL sconosciuti** o potenzialmente dannosi in Microsoft Teams: selezionare **Attivato** per abilitare la protezione dei collegamenti sicuri per i collegamenti in Teams.

   - **Applica l'analisi degli URL** in tempo reale per i collegamenti sospetti e i collegamenti che puntano ai file: selezionare questa impostazione per abilitare l'analisi in tempo reale dei collegamenti nei messaggi di posta elettronica.

   - **Attendere il completamento dell'analisi dell'URL prima** di recapitare il messaggio: selezionare questa impostazione per attendere il completamento dell'analisi degli URL in tempo reale prima di recapitare il messaggio.

   - **Applica collegamenti sicuri ai messaggi di posta elettronica** inviati all'interno dell'organizzazione : selezionare questa impostazione per applicare il criterio Collegamenti sicuri ai messaggi tra mittenti interni e destinatari interni.

   - **Non tenere traccia dei clic degli utenti:** lasciare deselezionata questa impostazione per abilitare la verifica dei clic degli utenti sugli URL nei messaggi di posta elettronica.

   - **Non consentire agli utenti di passare all'URL** originale: selezionare questa impostazione per impedire agli utenti di passare all'URL originale nelle pagine [di avviso.](safe-links.md#warning-pages-from-safe-links)

   - **Non riscrivere gli URL** seguenti: consente l'accesso agli URL specificati che altrimenti verrebbero bloccati dai collegamenti sicuri.

     Nella casella digitare l'URL o il valore desiderato e quindi fare clic su ![Icona del pulsante Aggiungi](../../media/ITPro-EAC-AddIcon.png).

     Per rimuovere una voce esistente, selezionarla e quindi fare clic su ![Icona del pulsante Elimina](../../media/ITPro-EAC-DeleteIcon.png).

     Per la sintassi delle voci, vedere Sintassi delle voci per [l'elenco "Non riscrivere gli URL seguenti".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)

   Per informazioni dettagliate su queste impostazioni, vedere [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) e Safe Links settings for Microsoft [Teams.](safe-links.md#safe-links-settings-for-microsoft-teams)

   Per ulteriori informazioni sui valori consigliati per le impostazioni dei criteri Standard e Strict, vedere [Safe Links policy settings.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nella pagina **Applicato a** visualizzata identificare i destinatari interni a cui si applica il criterio.

   È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione. Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_). Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).

   Fare **clic su Aggiungi condizione.** Nell'elenco a discesa visualizzato selezionare una condizione in **Applicato se**:

   - **Il destinatario è**: Specifica una o più cassette postali, utenti di posta o contatti di posta nell'organizzazione.
   - **Il destinatario è un membro di**: Specifica uno o più gruppi nell'organizzazione.
   - **Il dominio del destinatario è**: specifica i destinatari in uno o più dei domini configurati accettati nell'organizzazione.

   Dopo aver selezionato la condizione, viene visualizzato un elenco a discesa corrispondente con **una casella** Qualsiasi di queste.

   - Fare clic nella casella e scorrere l'elenco di valori da selezionare.
   - Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un valore.
   - Per aggiungere altri valori, fare clic in un'area vuota della casella.
   - Per rimuovere singole voci, fare clic **su Rimuovi** ![ Icona Rimuovi sul ](../../media/scc-remove-icon.png) valore.
   - Per rimuovere l'intera condizione, fare **clic su Rimuovi** Icona Rimuovi nella ![ ](../../media/scc-remove-icon.png) condizione.

   Per aggiungere una condizione aggiuntiva, fare clic **su Aggiungi una condizione** e selezionare un valore rimanente in Applicato **se**.

   Per aggiungere eccezioni, fare clic **su Aggiungi una condizione** e selezionare un'eccezione in Tranne **se**. Impostazioni e comportamento sono equivalenti alle condizioni.

   Al termine dell'operazione, fare clic su **Avanti**.

6. Nella pagina **Rivedere le impostazioni** visualizzata esaminare le impostazioni. È possibile fare **clic su** Modifica per ogni impostazione per modificarla.

   Al termine dell'operazione, scegliere **Fine**.

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a>Usare il Centro sicurezza & conformità per visualizzare i criteri collegamenti sicuri

1. Nel Centro sicurezza & conformità passare a **Criteri** di gestione delle minacce Collegamenti sicuri \>  \> **ATP**.

2. Nella pagina **Collegamenti sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).

   I dettagli dei criteri vengono visualizzati in un riquadro a comparsa

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a>Utilizzare il Centro sicurezza & conformità per modificare i criteri collegamenti sicuri

1. Nel Centro sicurezza & conformità passare a **Criteri** di gestione delle minacce Collegamenti sicuri \>  \> **ATP**.

2. Nella pagina **Collegamenti sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).

3. Nel riquadro a comparsa dei dettagli del criterio visualizzato fare clic **su Modifica criterio.**

Le impostazioni disponibili nel riquadro a comparsa visualizzato sono identiche a quelle descritte nella sezione Utilizzare il Centro [sicurezza &](#use-the-security--compliance-center-to-create-safe-links-policies) conformità per creare criteri collegamenti sicuri.

Per abilitare o disabilitare un criterio o impostare l'ordine di priorità dei criteri, vedere le sezioni seguenti.

### <a name="enable-or-disable-safe-links-policies"></a>Abilitare o disabilitare i criteri collegamenti sicuri

1. Nel Centro sicurezza & conformità passare a **Criteri** di gestione delle minacce Collegamenti sicuri \>  \> **ATP**.

2. Notare il valore nella **colonna** Stato:

   - Spostare l'interruttore a sinistra per disabilitare il criterio: ![Disattivare i criteri](../../media/scc-toggle-off.png).

   - Spostare l'interruttore a destra per abilitare il criterio: ![Attivare i criteri](../../media/scc-toggle-on.png).

### <a name="set-the-priority-of-safe-links-policies"></a>Impostare la priorità dei criteri collegamenti sicuri

Per impostazione predefinita, ai criteri collegamenti sicuri viene data una priorità basata sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità più bassa rispetto ai criteri precedenti). Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa). Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.

Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).

I criteri collegamenti sicuri vengono visualizzati nell'ordine in cui vengono elaborati (il primo criterio ha il **valore Priority** 0).

> [!NOTE]
> Nel Centro sicurezza & conformità, è possibile modificare la priorità del criterio Collegamenti sicuri solo dopo aver creato il criterio. In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola dei collegamenti sicuri (che può influire sulla priorità delle regole esistenti).

Per modificare la priorità di un criterio, spostare il criterio più in alto o più in basso nell'elenco (non è possibile modificare direttamente il numero **Priority** nel Centro sicurezza e conformità).

1. Nel Centro sicurezza & conformità passare a **Criteri** di gestione delle minacce Collegamenti sicuri \>  \> **ATP**.

2. Nella pagina **Collegamenti sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).

3. Nel riquadro a comparsa dei dettagli del criterio visualizzato fare clic sul pulsante priorità disponibile:

   - Il criterio Collegamenti sicuri con **valore Priorità** **0** ha solo il **pulsante Riduci** priorità disponibile.

   - Il criterio Collegamenti sicuri con il valore **Di** priorità più basso (ad esempio, **3)** ha solo il **pulsante Aumenta** priorità disponibile.

   - Se si dispone di tre o più criteri collegamenti sicuri,  i criteri  tra i valori di priorità più alta e più bassa hanno entrambi i pulsanti Aumenta priorità e Riduci priorità disponibili.

4. Fare **clic su Aumenta priorità** o **Diminuisci priorità** per modificare il valore **Priorità.**

5. Al termine, fare clic su **Chiudi**.

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a>Usare il Centro sicurezza & conformità per rimuovere i criteri collegamenti sicuri

1. Nel Centro sicurezza & conformità passare a **Criteri** di gestione delle minacce Collegamenti sicuri \>  \> **ATP**.

2. Nella pagina **Collegamenti sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).

3. Nel riquadro a comparsa dei dettagli del criterio visualizzato fare clic su **Elimina** criterio e quindi su **Sì** nella finestra di dialogo di avviso visualizzata.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>Utilizzare PowerShell di Exchange Online o PowerShell EOP autonomo per configurare i criteri collegamenti sicuri

Come descritto in precedenza, un criterio Collegamenti sicuri è costituito da un criterio collegamenti sicuri e da una regola per i collegamenti sicuri.

In PowerShell, la differenza tra i criteri dei collegamenti sicuri e le regole dei collegamenti sicuri è evidente. È possibile gestire i criteri dei collegamenti sicuri utilizzando i cmdlet **\* -SafeLinksPolicy** e gestire le regole dei collegamenti sicuri utilizzando i cmdlet **\* -SafeLinksRule.**

- In PowerShell, si crea prima il criterio collegamenti sicuri, quindi si crea la regola dei collegamenti sicuri che identifica il criterio a cui si applica la regola.
- In PowerShell, le impostazioni nel criterio collegamenti sicuri e nella regola dei collegamenti sicuri vengono modificate separatamente.
- Quando si rimuove un criterio collegamenti sicuri da PowerShell, la regola dei collegamenti sicuri corrispondente non viene rimossa automaticamente e viceversa.

### <a name="use-powershell-to-create-safe-links-policies"></a>Usare PowerShell per creare criteri collegamenti sicuri

La creazione di un criterio collegamenti sicuri in PowerShell è un processo in due passaggi:

1. Creare il criterio collegamenti sicuri.
2. Creare la regola dei collegamenti sicuri che specifica il criterio dei collegamenti sicuri a cui si applica la regola.

> [!NOTE]
> 
> - È possibile creare una nuova regola per i collegamenti sicuri e assegnarle un criterio di collegamenti sicuri non associazione esistente. Una regola dei collegamenti sicuri non può essere associata a più di un criterio collegamenti sicuri.
> 
> - È possibile configurare le impostazioni seguenti nei nuovi criteri dei collegamenti sicuri in PowerShell che non sono disponibili nel Centro sicurezza & conformità fino a quando non si crea il criterio:
> 
>   - Creare il nuovo criterio come disabilitato (_Abilitato_ `$false` nel cmdlet **New-SafeLinksRule).**
>   - Impostare la priorità del criterio durante la creazione (_Priority_ _\<Number\>_ ) nel cmdlet **New-SafeLinksRule.**
> 
> - Un nuovo criterio di collegamenti sicuri creato in PowerShell non è visibile nel Centro sicurezza & conformità finché non si assegna il criterio a una regola dei collegamenti sicuri.

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>Passaggio 1: Usare PowerShell per creare un criterio collegamenti sicuri

Per creare un criterio collegamenti sicuri, utilizzare la sintassi seguente:

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - Per informazioni dettagliate sulla sintassi delle voci da utilizzare per il parametro _DoNotRewriteUrls,_ vedere [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).
> 
> - Per ulteriori sintassi che è possibile utilizzare per il parametro _DoNotRewriteUrls_ quando si modificano i criteri dei collegamenti sicuri esistenti utilizzando il cmdlet **Set-SafeLinksPolicy,** vedere la sezione Utilizzare [PowerShell](#use-powershell-to-modify-safe-links-policies) per modificare i criteri dei collegamenti sicuri più avanti in questo articolo.

In questo esempio viene creato un criterio collegamenti sicuri denominato Contoso All con i valori seguenti:

- Attivare l'analisi e la riscrittura degli URL nei messaggi di posta elettronica.
- Attivare l'analisi degli URL in Teams (solo anteprima TAP).
- Attiva l'analisi in tempo reale degli URL selezionati, inclusi i collegamenti selezionati che puntano ai file.
- Attendere il completamento dell'analisi degli URL prima di recapitare il messaggio.
- Attivare l'analisi e la riscrittura degli URL per i messaggi interni.
- Tenere traccia dei clic degli utenti correlati alla protezione dei collegamenti sicuri (non viene utilizzato il parametro _DoNotTrackUserClicks_ e il valore predefinito è $false, ovvero vengono monitorati i clic degli utenti).
- Non consentire agli utenti di passare all'URL originale.

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-SafeLinksPolicy.](/powershell/module/exchange/new-safelinkspolicy)

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>Passaggio 2: Utilizzare PowerShell per creare una regola di collegamenti sicuri

Per creare una regola di collegamenti sicuri, utilizzare la sintassi seguente:

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

In questo esempio viene creata una regola di collegamenti sicuri denominata Contoso All con le condizioni seguenti:

- La regola è associata al criterio collegamenti sicuri denominato Contoso All.
- La regola si applica a tutti i destinatari del contoso.com dominio.
- Poiché non si utilizza il parametro _Priority,_ viene utilizzata la priorità predefinita.
- La regola è abilitata (non viene utilizzato il _parametro Enabled_ e il valore predefinito è `$true` ).

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).

### <a name="use-powershell-to-view-safe-links-policies"></a>Usare PowerShell per visualizzare i criteri dei collegamenti sicuri

Per visualizzare i criteri dei collegamenti sicuri esistenti, utilizzare la sintassi seguente:

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In questo esempio viene restituito un elenco riepilogativo di tutti i criteri dei collegamenti sicuri.

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

In questo esempio vengono restituite informazioni dettagliate per il criterio collegamenti sicuri denominato Contoso Executives.

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SafeLinksPolicy.](/powershell/module/exchange/get-safelinkspolicy)

### <a name="use-powershell-to-view-safe-links-rules"></a>Usare PowerShell per visualizzare le regole dei collegamenti sicuri

Per visualizzare le regole dei collegamenti sicuri esistenti, utilizzare la sintassi seguente:

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In questo esempio viene restituito un elenco riepilogativo di tutte le regole dei collegamenti sicuri.

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

In questo esempio vengono restituite informazioni dettagliate per la regola dei collegamenti sicuri denominata Contoso Executives.

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).

### <a name="use-powershell-to-modify-safe-links-policies"></a>Utilizzare PowerShell per modificare i criteri dei collegamenti sicuri

Non è possibile rinominare un criterio collegamenti sicuri in PowerShell (il cmdlet **Set-SafeLinksPolicy** non dispone di _alcun parametro Name)._ Quando si rinomina un criterio Collegamenti sicuri nel Centro sicurezza & conformità, si rinomina solo la regola dei collegamenti _sicuri._

L'unica considerazione aggiuntiva per la modifica dei criteri dei collegamenti sicuri in PowerShell è la sintassi disponibile per il parametro _DoNotRewriteUrls_ (l'elenco "Non riscrivere gli [URL seguenti"):](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- Per aggiungere valori che sostituiranno le voci esistenti, utilizzare la sintassi seguente: `"Entry1","Entry2,..."EntryN"` .
- Per aggiungere o rimuovere valori senza influire sulle altre voci esistenti, utilizzare la sintassi seguente: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

In caso contrario, le stesse impostazioni sono disponibili quando si crea un criterio collegamenti sicuri come descritto nella sezione Passaggio [1:](#step-1-use-powershell-to-create-a-safe-links-policy) Utilizzare PowerShell per creare un criterio collegamenti sicuri più indietro in questo articolo.

Per modificare un criterio collegamenti sicuri, utilizzare la sintassi seguente:

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeLinksPolicy.](/powershell/module/exchange/set-safelinkspolicy)

### <a name="use-powershell-to-modify-safe-links-rules"></a>Utilizzare PowerShell per modificare le regole dei collegamenti sicuri

L'unica impostazione non disponibile quando si modifica una regola di collegamenti sicuri in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata. Per abilitare o disabilitare le regole dei collegamenti sicuri esistenti, vedere la sezione successiva.

In caso contrario, le stesse impostazioni sono disponibili quando si crea una regola come descritto nella sezione Passaggio [2:](#step-2-use-powershell-to-create-a-safe-links-rule) Utilizzare PowerShell per creare una regola di collegamenti sicuri più indietro in questo articolo.

Per modificare una regola dei collegamenti sicuri, utilizzare la sintassi seguente:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeLinksRule.](/powershell/module/exchange/set-safelinksrule)

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>Abilitazione o disabilitazione delle regole dei collegamenti sicuri tramite PowerShell

L'abilitazione o la disabilitazione di una regola di collegamenti sicuri in PowerShell abilita o disabilita l'intero criterio Collegamenti sicuri (la regola dei collegamenti sicuri e il criterio collegamenti sicuri assegnati).

Per abilitare o disabilitare una regola di collegamenti sicuri in PowerShell, utilizzare la sintassi seguente:

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

In questo esempio viene disabilitata la regola dei collegamenti sicuri denominata Marketing Department.

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

In questo esempio viene abilitata la stessa regola.

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) [e Disable-SafeLinksRule.](/powershell/module/exchange/disable-safelinksrule)

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>Utilizzare PowerShell per impostare la priorità delle regole dei collegamenti sicuri

Il valore di priorità più alto che è possibile impostare in una regola è 0. Il valore più basso che è possibile impostare dipende dal numero di regole. Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4. Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole. Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola su 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.

Per impostare la priorità di una regola di collegamenti sicuri in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> Per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-SafeLinksRule.**

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeLinksRule.](/powershell/module/exchange/set-safelinksrule)

### <a name="use-powershell-to-remove-safe-links-policies"></a>Usare PowerShell per rimuovere i criteri dei collegamenti sicuri

Quando si utilizza PowerShell per rimuovere un criterio collegamenti sicuri, la regola dei collegamenti sicuri corrispondente non viene rimossa.

Per rimuovere un criterio collegamenti sicuri in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

In questo esempio viene rimosso il criterio collegamenti sicuri denominato Marketing Department.

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).

### <a name="use-powershell-to-remove-safe-links-rules"></a>Usare PowerShell per rimuovere le regole dei collegamenti sicuri

Quando si utilizza PowerShell per rimuovere una regola dei collegamenti sicuri, il criterio collegamenti sicuri corrispondente non viene rimosso.

Per rimuovere una regola di collegamenti sicuri in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

In questo esempio viene rimossa la regola dei collegamenti sicuri denominata Marketing Department.

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).

Per verificare che collegamenti sicuri eseere in corso l'analisi dei messaggi, controllare i report di Microsoft Defender per Office 365 disponibili. Per ulteriori informazioni, vedere [View reports for Defender for Office 365](view-reports-for-mdo.md) e Use Explorer in the Security & Compliance [Center.](threat-explorer.md)

## <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare di aver creato, modificato o rimosso correttamente i criteri collegamenti sicuri, eseguire una delle operazioni seguenti:

- Nel Centro sicurezza & conformità passare a **Criteri** di gestione delle minacce Collegamenti sicuri \>  \> **ATP**. Verificare l'elenco dei criteri, i **relativi valori status** e i relativi valori **Priority.** Per visualizzare altri dettagli, selezionare il criterio nell'elenco e visualizzare i dettagli nel riquadro a comparsa.

- In PowerShell di Exchange Online o PowerShell di Exchange Online Protection, sostituire con il nome del criterio o della regola, eseguire il \<Name\> comando seguente e verificare le impostazioni:

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```