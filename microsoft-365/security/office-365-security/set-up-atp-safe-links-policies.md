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
ms.openlocfilehash: 29d777a7f351b9ab33232cb0136703ce3fa29842
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290154"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>Configurare i criteri collegamenti sicuri in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> Questo articolo è rivolto ai clienti aziendali di [Microsoft Defender per Office 365](office-365-atp.md). Per informazioni sui collegamenti sicuri in Outlook, vedere [Advanced Outlook.com security.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Collegamenti sicuri è una funzionalità di [Microsoft Defender per Office 365](office-365-atp.md) che fornisce l'analisi degli URL dei messaggi di posta elettronica in ingresso nel flusso di posta e l'ora della verifica degli URL e dei collegamenti nei messaggi di posta elettronica e in altre posizioni. Per altre informazioni, vedere [Collegamenti sicuri in Microsoft Defender per Office 365.](atp-safe-links.md)

Non esiste un criterio collegamenti sicuri predefinito o predefinito. Per ottenere l'analisi dei collegamenti sicuri degli URL, è necessario creare uno o più criteri collegamenti sicuri come descritto in questo articolo.

> [!NOTE]
> Le impostazioni globali per la protezione dei collegamenti sicuri vengono configurate **al di fuori** dei criteri collegamenti sicuri. Per istruzioni, vedere [Configurare le impostazioni globali per i collegamenti sicuri in Microsoft Defender per Office 365.](configure-global-settings-for-safe-links.md)

È possibile configurare i criteri collegamenti sicuri nel Centro sicurezza & e conformità o in PowerShell (PowerShell di Exchange Online per le organizzazioni di Microsoft 365 idonee con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online, ma con sottoscrizioni ai componenti aggiuntivi di Microsoft Defender per Office 365).

Gli elementi di base di un criterio collegamenti sicuri sono:

- Il criterio collegamenti sicuri **:** attivare la protezione dei collegamenti sicuri, attivare l'analisi degli URL in tempo reale, specificare se attendere il completamento dell'analisi in tempo reale prima di recapitare il messaggio, attivare l'analisi dei messaggi interni, specificare se tenere traccia dei clic degli utenti sugli URL e specificare se consentire agli utenti di fare clic sull'URL originale.
- **La regola per i collegamenti sicuri**: specifica la priorità e i filtri destinatario (a chi si applica il criterio).

La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri collegamenti sicuri nel Centro sicurezza & conformità:

- Quando si crea un criterio collegamenti sicuri, si crea contemporaneamente una regola per i collegamenti sicuri e il criterio collegamenti sicuri associati utilizzando lo stesso nome per entrambi.
- Quando si modifica un criterio collegamenti sicuri, le impostazioni relative al nome, alla priorità, abilitata o disabilitata e ai filtri destinatari modificano la regola per i collegamenti sicuri. Tutte le altre impostazioni modificano il criterio collegamenti sicuri associato.
- Quando si rimuove un criterio collegamenti sicuri, vengono rimossi la regola dei collegamenti sicuri e il criterio collegamenti sicuri associato.

In PowerShell di Exchange Online o in EOP PowerShell autonomo i criteri e la regola vengono gestiti separatamente. Per ulteriori informazioni, vedere la sezione Utilizzare Exchange Online PowerShell o [PowerShell EOP](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) autonomo per configurare i criteri collegamenti sicuri più avanti in questo articolo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla **pagina Collegamenti sicuri,** utilizzare <https://protection.office.com/safelinksv2> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni seguenti:
  - Per creare, modificare ed eliminare i criteri collegamenti sicuri,  è necessario essere membri dei gruppi di ruoli Gestione organizzazione  o Amministratore sicurezza nel Centro sicurezza & **conformità** e membri del gruppo di ruoli Gestione organizzazione in Exchange Online. 
  - Per l'accesso in sola lettura ai criteri collegamenti  sicuri, è necessario essere membri dei gruppi di ruoli Lettore globale o Lettore **di** sicurezza.

  Per ulteriori informazioni, vedere [Autorizzazioni nel Centro sicurezza & conformità](permissions-in-the-security-and-compliance-center.md) e Autorizzazioni in Exchange [Online.](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)

  > [!NOTE]
  > 
  > - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).
  . - Il **gruppo di ruoli Gestione** organizzazione di sola visualizzazione in Exchange [Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) consente inoltre l'accesso in sola lettura alla funzionalità.

- Per le impostazioni consigliate per i criteri collegamenti sicuri, vedere [Impostazioni dei criteri collegamenti sicuri.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)

- Consentire fino a 30 minuti per l'applicazione di un criterio nuovo o aggiornato.

- [Nuove funzionalità vengono continuamente aggiunte a Microsoft Defender per Office 365.](office-365-atp.md#new-features-in-microsoft-defender-for-office-365) Quando vengono aggiunte nuove funzionalità, potrebbe essere necessario apportare modifiche ai criteri collegamenti sicuri esistenti.

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a>Usare il Centro sicurezza & conformità per creare criteri collegamenti sicuri

La creazione di un criterio collegamenti sicuri personalizzato nel Centro sicurezza & conformità crea la regola dei collegamenti sicuri e il criterio collegamenti sicuri associati contemporaneamente usando lo stesso nome per entrambi.

1. Nel Centro sicurezza & conformità passare a Collegamenti sicuri dei criteri di **gestione** delle \>  \> **minacce ATP.**

2. Nella pagina **Collegamenti sicuri** fare clic su **Crea.**

3. Verrà **visualizzata la procedura guidata Nuovo criterio collegamenti** sicuri. Nella pagina **Assegnare un nome al** criterio configurare le impostazioni seguenti:

   - **Nome**: immettere un nome univoco descrittivo per il criterio.

   - **Descrizione**: immettere una descrizione opzionale per il criterio.

   Al termine dell'operazione, fare clic su **Avanti**.

4. Nella pagina **Impostazioni** visualizzata configurare le impostazioni seguenti:

   - **Selezionare l'azione per URL sconosciuti** potenzialmente dannosi nei messaggi: selezionare **Attivato** per abilitare la protezione collegamenti sicuri per i collegamenti nei messaggi di posta elettronica.

   - **Selezionare l'azione per URL sconosciuti** o potenzialmente  dannosi in Microsoft Teams: selezionare Attiva per abilitare la protezione dei collegamenti sicuri per i collegamenti in Teams.

   - **Applicare l'analisi degli URL** in tempo reale per i collegamenti sospetti e i collegamenti che puntano ai file: selezionare questa impostazione per abilitare l'analisi in tempo reale dei collegamenti nei messaggi di posta elettronica.

   - **Attendere il completamento dell'analisi degli URL prima** di recapitare il messaggio: selezionare questa impostazione per attendere il completamento dell'analisi degli URL in tempo reale prima di recapitare il messaggio.

   - **Applica collegamenti sicuri ai messaggi di posta elettronica** inviati all'interno dell'organizzazione: selezionare questa impostazione per applicare il criterio Collegamenti sicuri ai messaggi tra mittenti interni e destinatari interni.

   - **Non tenere traccia dei clic degli utenti:** lasciare deselezionata questa impostazione per abilitare la verifica dei clic degli utenti sugli URL nei messaggi di posta elettronica.

   - **Non consentire agli utenti di passare all'URL** originale: selezionare questa impostazione per impedire agli utenti di fare clic sull'URL originale nelle pagine [di avviso.](atp-safe-links.md#warning-pages-from-safe-links)

   - **Non riscrivere gli URL** seguenti: consente l'accesso agli URL specificati che altrimenti verrebbero bloccati dai collegamenti sicuri.

     Nella casella digitare l'URL o il valore desiderato e quindi fare clic su ![Icona del pulsante Aggiungi](../../media/ITPro-EAC-AddIcon.png).

     Per rimuovere una voce esistente, selezionarla e quindi fare clic su ![Icona del pulsante Elimina](../../media/ITPro-EAC-DeleteIcon.png).

     Per la sintassi delle voci, vedere la sintassi delle voci per [l'elenco "Non riscrivere gli URL seguenti".](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)

   Per informazioni dettagliate su queste impostazioni, vedere [Safe Links settings for email messages](atp-safe-links.md#safe-links-settings-for-email-messages) and Safe Links settings for Microsoft [Teams.](atp-safe-links.md#safe-links-settings-for-microsoft-teams)

   Per ulteriori informazioni sui valori consigliati per le impostazioni dei criteri Standard e Strict, vedere Impostazioni dei criteri [collegamenti sicuri.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nella pagina **Applicato a** visualizzata, identificare i destinatari interni a cui si applica il criterio.

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

6. Nella pagina **Verifica le impostazioni** visualizzata, rivedere le impostazioni. È possibile fare **clic su** Modifica per ogni impostazione per modificarla.

   Al termine dell'operazione, scegliere **Fine**.

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a>Usare il Centro sicurezza & conformità per visualizzare i criteri collegamenti sicuri

1. Nel Centro sicurezza & conformità passare a Collegamenti sicuri dei criteri di **gestione** delle \>  \> **minacce ATP.**

2. Nella pagina **Collegamenti sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).

   I dettagli dei criteri vengono visualizzati in un riquadro a comparsa

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a>Utilizzare il Centro sicurezza & conformità per modificare i criteri collegamenti sicuri

1. Nel Centro sicurezza & conformità passare a Collegamenti sicuri dei criteri di **gestione** delle \>  \> **minacce ATP.**

2. Nella pagina **Collegamenti sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).

3. Nel riquadro a comparsa dei dettagli del criterio visualizzato, fare clic **su Modifica criterio.**

Le impostazioni disponibili nel riquadro a comparsa visualizzate sono identiche a quelle descritte nella sezione Usare il Centro sicurezza [& conformità](#use-the-security--compliance-center-to-create-safe-links-policies) per creare criteri collegamenti sicuri.

Per abilitare o disabilitare un criterio o impostare l'ordine di priorità dei criteri, vedere le sezioni seguenti.

### <a name="enable-or-disable-safe-links-policies"></a>Abilitare o disabilitare i criteri collegamenti sicuri

1. Nel Centro sicurezza & conformità passare a Collegamenti sicuri dei criteri di **gestione** delle \>  \> **minacce ATP.**

2. Si noti il valore nella **colonna** Stato:

   - Spostare l'interruttore a sinistra per disabilitare il criterio: ![Disattivare i criteri](../../media/scc-toggle-off.png).

   - Spostare l'interruttore a destra per abilitare il criterio: ![Attivare i criteri](../../media/scc-toggle-on.png).

### <a name="set-the-priority-of-safe-links-policies"></a>Impostare la priorità dei criteri collegamenti sicuri

Per impostazione predefinita, ai criteri collegamenti sicuri viene data una priorità basata sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità inferiore rispetto ai criteri precedenti). Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa). Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.

Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).

I criteri collegamenti sicuri vengono visualizzati nell'ordine in cui vengono elaborati (il primo criterio ha il **valore priority** 0).

> [!NOTE]
> Nel Centro sicurezza & conformità, è possibile modificare la priorità del criterio Collegamenti sicuri solo dopo aver creato il criterio. In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola dei collegamenti sicuri (che può influire sulla priorità delle regole esistenti).

Per modificare la priorità di un criterio, spostare il criterio più in alto o più in basso nell'elenco (non è possibile modificare direttamente il numero **Priority** nel Centro sicurezza e conformità).

1. Nel Centro sicurezza & conformità passare a Collegamenti sicuri dei criteri di **gestione** delle \>  \> **minacce ATP.**

2. Nella pagina **Collegamenti sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).

3. Nel riquadro a comparsa dei dettagli del criterio visualizzato, fai clic sul pulsante di priorità disponibile:

   - Il criterio Collegamenti sicuri con **valore Priorità** **0** ha solo il **pulsante Diminuisci** priorità disponibile.

   - Per il criterio Collegamenti sicuri con il valore **di priorità** più basso (ad esempio, **3)** è disponibile solo il pulsante **Aumenta** priorità.

   - Se si dispone di tre o più criteri collegamenti sicuri,  i criteri tra i valori di priorità più alta e più bassa hanno entrambi i pulsanti Aumenta priorità **e Diminuisci** priorità disponibili.

4. Fare **clic su Aumenta priorità** o **Diminuisci priorità** per modificare il valore **di** Priorità.

5. Al termine, fare clic su **Chiudi**.

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a>Usare il Centro sicurezza & conformità per rimuovere i criteri collegamenti sicuri

1. Nel Centro sicurezza & conformità passare a Collegamenti sicuri dei criteri di **gestione** delle \>  \> **minacce ATP.**

2. Nella pagina **Collegamenti sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).

3. Nel riquadro a comparsa dei dettagli del criterio visualizzato, fare clic su **Elimina** criterio e quindi su **Sì** nella finestra di dialogo di avviso visualizzata.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>Utilizzare PowerShell di Exchange Online o PowerShell di EOP autonomo per configurare i criteri collegamenti sicuri

Come descritto in precedenza, un criterio collegamenti sicuri è costituito da un criterio collegamenti sicuri e da una regola per i collegamenti sicuri.

In PowerShell, la differenza tra i criteri dei collegamenti sicuri e le regole dei collegamenti sicuri è evidente. È possibile gestire i criteri collegamenti sicuri utilizzando i cmdlet **\* -SafeLinksPolicy** e gestire le regole dei collegamenti sicuri utilizzando i cmdlet **\* -SafeLinksRule.**

- In PowerShell, si crea prima il criterio collegamenti sicuri, quindi si crea la regola dei collegamenti sicuri che identifica il criterio a cui si applica la regola.
- In PowerShell, è possibile modificare le impostazioni nei criteri collegamenti sicuri e nella regola dei collegamenti sicuri separatamente.
- Quando si rimuove un criterio collegamenti sicuri da PowerShell, la regola dei collegamenti sicuri corrispondente non viene rimossa automaticamente e viceversa.

### <a name="use-powershell-to-create-safe-links-policies"></a>Utilizzare PowerShell per creare criteri collegamenti sicuri

La creazione di un criterio collegamenti sicuri in PowerShell è un processo in due passaggi:

1. Creare il criterio collegamenti sicuri.
2. Creare la regola per i collegamenti sicuri che specifica il criterio per i collegamenti sicuri a cui si applica la regola.

> [!NOTE]
> 
> - È possibile creare una nuova regola per i collegamenti sicuri e assegnare un criterio collegamenti sicuri esistente e non ad essa. Una regola per i collegamenti sicuri non può essere associata a più criteri collegamenti sicuri.
> 
> - È possibile configurare le impostazioni seguenti nei nuovi criteri per i collegamenti sicuri in PowerShell che non sono disponibili nel Centro sicurezza & conformità fino a quando non si crea il criterio:
> 
>   - Creare il nuovo criterio come disabilitato (_abilitato_ `$false` nel cmdlet **New-SafeLinksRule).**
>   - Impostare la priorità del criterio durante la creazione (_Priority_ ) nel _\<Number\>_ cmdlet **New-SafeLinksRule.**
> 
> - Un nuovo criterio collegamenti sicuri creato in PowerShell non è visibile nel Centro sicurezza & conformità finché non si assegna il criterio a una regola per i collegamenti sicuri.

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>Passaggio 1: Utilizzare PowerShell per creare un criterio collegamenti sicuri

Per creare un criterio collegamenti sicuri, utilizzare la sintassi seguente:

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - Per informazioni dettagliate sulla sintassi delle voci da utilizzare per il parametro _DoNotRewriteUrls,_ vedere La sintassi delle voci per l'elenco ["Non riscrivere gli URL seguenti".](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)
> 
> - Per ulteriori informazioni sulla sintassi che è possibile utilizzare per il parametro _DoNotRewriteUrls_ quando si modificano i criteri dei collegamenti sicuri esistenti utilizzando il cmdlet **Set-SafeLinksPolicy,** vedere la sezione Utilizzare [PowerShell](#use-powershell-to-modify-safe-links-policies) per modificare i criteri dei collegamenti sicuri più avanti in questo articolo.

In questo esempio viene creato un criterio collegamenti sicuri denominato Contoso All con i seguenti valori:

- Attivare l'analisi e la riscrittura degli URL nei messaggi di posta elettronica.
- Attivare l'analisi degli URL in Teams (solo anteprima TAP).
- Attivare l'analisi in tempo reale degli URL selezionati, inclusi i collegamenti selezionati che puntano ai file.
- Attendere il completamento dell'analisi degli URL prima di recapitare il messaggio.
- Attivare l'analisi e la riscrittura degli URL per i messaggi interni.
- Tenere traccia dei clic degli utenti correlati alla protezione dei collegamenti sicuri (non viene utilizzato il parametro _DoNotTrackUserClicks_ e il valore predefinito è $false, ovvero i clic degli utenti vengono monitorati).
- Non consentire agli utenti di passare all'URL originale.

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-SafeLinksPolicy.](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy)

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>Passaggio 2: Utilizzare PowerShell per creare una regola per i collegamenti sicuri

Per creare una regola per i collegamenti sicuri, utilizzare la sintassi seguente:

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

In questo esempio viene creata una regola per i collegamenti sicuri denominata Contoso All con le seguenti condizioni:

- La regola è associata al criterio collegamenti sicuri denominato Contoso All.
- La regola si applica a tutti i destinatari nel contoso.com dominio.
- Poiché non viene utilizzato il parametro _Priority,_ viene utilizzata la priorità predefinita.
- La regola è abilitata (non viene utilizzato il parametro _Enabled_ e il valore predefinito è `$true` ).

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule)

### <a name="use-powershell-to-view-safe-links-policies"></a>Usare PowerShell per visualizzare i criteri per i collegamenti sicuri

Per visualizzare i criteri collegamenti sicuri esistenti, utilizzare la sintassi seguente:

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In questo esempio viene restituito un elenco riepilogativo di tutti i criteri collegamenti sicuri.

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

In questo esempio vengono restituite informazioni dettagliate per il criterio collegamenti sicuri denominato Contoso Executives.

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SafeLinksPolicy.](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy)

### <a name="use-powershell-to-view-safe-links-rules"></a>Utilizzare PowerShell per visualizzare le regole per i collegamenti sicuri

Per visualizzare le regole dei collegamenti sicuri esistenti, utilizzare la sintassi seguente:

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In questo esempio viene restituito un elenco riepilogativo di tutte le regole per i collegamenti sicuri.

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

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule)

### <a name="use-powershell-to-modify-safe-links-policies"></a>Utilizzare PowerShell per modificare i criteri per i collegamenti sicuri

Non è possibile rinominare un criterio collegamenti sicuri in PowerShell (il cmdlet **Set-SafeLinksPolicy** non dispone di alcun _parametro_ Name). Quando si rinomina un criterio collegamenti sicuri nel Centro sicurezza & conformità, si rinomina solo la regola dei collegamenti _sicuri._

L'unica considerazione aggiuntiva per la modifica dei criteri per i collegamenti sicuri in PowerShell è la sintassi disponibile per il parametro _DoNotRewriteUrls_ (l'elenco "Non riscrivere gli [URL seguenti"](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):

- Per aggiungere valori che sostituiranno eventuali voci esistenti, utilizzare la sintassi seguente: `"Entry1","Entry2,..."EntryN"` .
- Per aggiungere o rimuovere valori senza influire sulle altre voci esistenti, utilizzare la sintassi seguente: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

In caso contrario, le stesse impostazioni sono disponibili quando si crea un criterio collegamenti sicuri come descritto nel passaggio [1:](#step-1-use-powershell-to-create-a-safe-links-policy) Utilizzare PowerShell per creare una sezione dei criteri collegamenti sicuri più indietro in questo articolo.

Per modificare un criterio collegamenti sicuri, utilizzare la sintassi seguente:

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeLinksPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy)

### <a name="use-powershell-to-modify-safe-links-rules"></a>Utilizzare PowerShell per modificare le regole per i collegamenti sicuri

L'unica impostazione non disponibile quando si modifica una regola per i collegamenti sicuri in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata. Per abilitare o disabilitare le regole dei collegamenti sicuri esistenti, vedere la sezione successiva.

In caso contrario, le stesse impostazioni sono disponibili quando si crea una regola come descritto nel passaggio [2:](#step-2-use-powershell-to-create-a-safe-links-rule) Utilizzare PowerShell per creare una regola per i collegamenti sicuri più indietro in questo articolo.

Per modificare una regola per i collegamenti sicuri, utilizzare la sintassi seguente:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>Abilitazione o disabilitazione delle regole per i collegamenti sicuri tramite PowerShell

L'abilitazione o la disabilitazione di una regola per i collegamenti sicuri in PowerShell abilita o disabilita l'intero criterio Collegamenti sicuri (la regola per i collegamenti sicuri e il criterio collegamenti sicuri assegnati).

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

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) [e Disable-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule)

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>Utilizzare PowerShell per impostare la priorità delle regole per i collegamenti sicuri

Il valore di priorità più alto che è possibile impostare in una regola è 0. Il valore più basso che è possibile impostare dipende dal numero di regole. Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4. Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole. Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola su 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.

Per impostare la priorità di una regola per i collegamenti sicuri in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> Per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-SafeLinksRule.**

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)

### <a name="use-powershell-to-remove-safe-links-policies"></a>Utilizzare PowerShell per rimuovere i criteri per i collegamenti sicuri

Quando si utilizza PowerShell per rimuovere un criterio collegamenti sicuri, la regola dei collegamenti sicuri corrispondente non viene rimossa.

Per rimuovere un criterio collegamenti sicuri in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

In questo esempio viene rimosso il criterio collegamenti sicuri denominato Marketing Department.

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-SafeLinksPolicy.](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy)

### <a name="use-powershell-to-remove-safe-links-rules"></a>Utilizzare PowerShell per rimuovere le regole per i collegamenti sicuri

Quando si utilizza PowerShell per rimuovere una regola per i collegamenti sicuri, il criterio collegamenti sicuri corrispondente non viene rimosso.

Per rimuovere una regola per i collegamenti sicuri in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

In questo esempio viene rimossa la regola per i collegamenti sicuri denominata Marketing Department.

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule)

Per verificare che Collegamenti sicuri eseere in corso l'analisi dei messaggi, controllare i report di Microsoft Defender per Office 365 disponibili. Per altre informazioni, vedere [Visualizzare i report per Defender per Office 365](view-reports-for-atp.md) e Usare Esplora risorse nel Centro sicurezza & [conformità.](threat-explorer.md)

## <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare la corretta creazione, modifica o rimozione dei criteri collegamenti sicuri, eseguire una delle operazioni seguenti:

- Nel Centro sicurezza & conformità passare a Collegamenti sicuri dei criteri di **gestione** delle \>  \> **minacce ATP.** Verificare l'elenco dei criteri, i relativi **valori di** stato e i relativi **valori di** priorità. Per visualizzare altri dettagli, selezionare il criterio nell'elenco e visualizzare i dettagli nel riquadro a comparsa.

- In PowerShell di Exchange Online o PowerShell di Exchange Online Protection, sostituire con il nome del criterio o della regola, eseguire il comando seguente \<Name\> e verificare le impostazioni:

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
