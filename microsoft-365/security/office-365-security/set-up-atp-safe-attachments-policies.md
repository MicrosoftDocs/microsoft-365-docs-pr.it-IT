---
title: Configurare i criteri per gli allegati sicuri in Office 365 ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Informazioni su come definire i criteri per gli allegati sicuri per proteggere l'organizzazione da file dannosi tramite posta elettronica.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e50e5e961e1a45b0b6535995727029222539ff03
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326962"
---
# <a name="set-up-safe-attachments-policies-in-office-365-atp"></a>Configurare i criteri per gli allegati sicuri in Office 365 ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Questo articolo è destinato ai clienti aziendali che dispongono di [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md). Se si è un utente di casa che cerca informazioni sull'analisi degli allegati in Outlook, vedere [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Allegati sicuri è una funzionalità di [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) che utilizza un ambiente virtuale per controllare gli allegati nei messaggi di posta elettronica in ingresso dopo che sono stati analizzati dalla [protezione antimalware in Exchange Online Protection (EOP)](anti-malware-protection.md), ma prima del recapito ai destinatari. Per ulteriori informazioni, vedere [Safe Attachments in Office 365 ATP](atp-safe-attachments.md).

Non esiste alcun criterio di allegati sicuri incorporato o predefinito. Per ottenere l'analisi degli allegati sicuri degli allegati dei messaggi di posta elettronica, è necessario creare uno o più criteri per gli allegati sicuri come descritto in questo articolo.

È possibile configurare i criteri per gli allegati sicuri nel centro sicurezza & Compliance o in PowerShell (Exchange Online PowerShell per organizzazioni Microsoft 365 idonee con cassette postali in Exchange Online; standalone EOP PowerShell per le organizzazioni senza cassette postali di Exchange Online, ma con gli abbonamenti del componente aggiuntivo ATP di Office 365).

Gli elementi di base di un criterio di allegati sicuri sono i seguenti:

- **Criterio**degli allegati sicuri: consente di specificare le azioni per i rilevamenti di malware sconosciuti, se inviare messaggi con allegati malware a un indirizzo di posta elettronica specificato e se recapitare i messaggi se l'analisi degli allegati sicuri non può essere completata.
- **Regola per gli allegati sicuri**: consente di specificare i filtri priorità e destinatario (a chi si applica il criterio).

La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri degli allegati sicuri nel centro sicurezza & conformità:

- Quando si crea un criterio di allegati sicuri, si sta effettivamente creando una regola per gli allegati sicuri e il criterio degli allegati sicuri associato contemporaneamente utilizzando lo stesso nome per entrambi.
- Quando si modifica un criterio di allegati sicuri, le impostazioni relative ai filtri nome, priorità, abilitato o disabilitato e destinatario modificano la regola di allegato sicuro. Tutte le altre impostazioni modificano il criterio degli allegati sicuri associato.
- Quando si rimuove un criterio di allegati sicuri, la regola di allegato sicuro e i criteri degli allegati sicuri associati vengono rimossi.

In PowerShell di Exchange Online o in EOP PowerShell autonomo i criteri e la regola vengono gestiti separatamente. Per ulteriori informazioni, vedere la sezione [utilizzare Exchange Online PowerShell o standalone EOP PowerShell per configurare i criteri degli allegati sicuri](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) più avanti in questo articolo.

> [!NOTE]
> Nell'area impostazioni globali delle impostazioni degli allegati sicuri, è possibile configurare le funzionalità che non dipendono dai criteri degli allegati sicuri. Per le istruzioni [, vedere Abilitare ATP per SharePoint, OneDrive e Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md) e [documenti attendibili in Microsoft 365 E5](safe-docs.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per accedere direttamente alla pagina degli **allegati sicuri di ATP** , utilizzare <https://protection.office.com/safeattachmentv2> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Per visualizzare, creare, modificare ed eliminare i criteri per gli allegati sicuri, è necessario essere membri di uno dei gruppi di ruoli seguenti:

  - **Gestione organizzazione** o **Amministratore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).
  - **Gestione dell'organizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Per le impostazioni consigliate per i criteri per gli allegati sicuri, vedere [Safe Attachments Settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).

- Consentire l'applicazione di un criterio nuovo o aggiornato fino a 30 minuti.

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a>Utilizzare il Centro sicurezza & conformità per creare criteri allegati sicuri

La creazione di un criterio di allegati sicuri personalizzato nel centro sicurezza & conformità crea la regola per gli allegati sicuri e il criterio degli allegati sicuri associato contemporaneamente utilizzando lo stesso nome per entrambi.

1. Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** per gli \> **Policy** \> **allegati sicuri ATP**.

2. Nella pagina **allegati sicuri** fare clic su **Crea**.

3. Verrà visualizzata la procedura guidata **nuovo criterio allegati sicuri** . Nella pagina **Name Your Policy** , configurare le seguenti impostazioni:

   - **Nome**: immettere un nome univoco descrittivo per il criterio.

   - **Descrizione**: immettere una descrizione opzionale per il criterio.

   Al termine dell'operazione, fare clic su **Avanti**.

4. Nella pagina **Impostazioni** che viene visualizzata, configurare le seguenti impostazioni:

   - **Risposta malware per gli allegati sicuri**: selezionare uno dei valori seguenti:

     - **Off**: in genere, non è consigliabile questo valore.
     - **Monitor**
     - **Block**: questo è il valore predefinito e il valore consigliato nei [criteri di sicurezza preimpostati](preset-security-policies.md)standard e rigorosi.
     - **Sostituisce**
     - **Recapito dinamico (funzionalità di anteprima)**

     Questi valori vengono illustrati nelle [impostazioni dei criteri allegati sicuri](atp-safe-attachments.md#safe-attachments-policy-settings).

   - **Inviare l'allegato all'indirizzo di posta elettronica seguente**: per il **blocco**, il **monitoraggio**o la **sostituzione**dei valori di azione, è possibile selezionare **Abilita reindirizzamento** per inviare messaggi che contengono allegati di malware all'indirizzo di posta elettronica interno o esterno specificato per l'analisi e l'indagine.

     La raccomandazione per le impostazioni dei criteri standard e rigorosa consiste nell'abilitare il reindirizzamento. Per ulteriori informazioni, vedere [impostazioni degli allegati sicuri](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).

   - **Applicare la selezione precedente se la ricerca di malware per gli allegati**non è stata eseguita o si verifica un errore: l'azione specificata dalla **risposta malware Unknown Attachments** è presa sui messaggi anche quando l'analisi degli allegati sicuri non può essere completata. Selezionare sempre questa opzione se si seleziona **reindirizza abilitato**. In caso contrario, è possibile che i messaggi vengano persi.

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

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a>Utilizzare il Centro sicurezza & conformità per visualizzare i criteri degli allegati sicuri

1. Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** per gli \> **Policy** \> **allegati sicuri ATP**.

2. Nella pagina **allegati sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).

   I dettagli del criterio vengono visualizzati in un volo

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a>Utilizzare il Centro sicurezza & conformità per modificare i criteri degli allegati sicuri

1. Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** per gli \> **Policy** \> **allegati sicuri ATP**.

2. Nella pagina **allegati sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).

3. Nei dettagli del criterio, fare clic su **modifica criterio**.

Le impostazioni disponibili nel volo visualizzato sono identiche a quelle descritte nella sezione [use the Security & Compliance Center to create Safe Attachments Policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) .

Per abilitare o disabilitare un criterio o impostare l'ordine di priorità dei criteri, vedere le sezioni seguenti.

### <a name="enable-or-disable-safe-attachments-policies"></a>Abilitare o disabilitare i criteri per gli allegati sicuri

1. Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** per gli \> **Policy** \> **allegati sicuri ATP**.

2. Si noti il valore nella colonna **stato** :

   - Sposta l'interruttore verso sinistra ![Disattiva criterio](../../media/scc-toggle-off.png) per disabilitare il criterio.

   - Spostare l'interruttore verso destra ![Attiva il criterio](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) per abilitare il criterio.

### <a name="set-the-priority-of-safe-attachments-policies"></a>Impostare la priorità dei criteri per gli allegati sicuri

Per impostazione predefinita, ai criteri allegati sicuri viene assegnata una priorità che si basa sull'ordine in cui sono stati creati (le nuove polizie sono più basse rispetto ai criteri precedenti). Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa). Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.

Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).

I criteri allegati sicuri vengono visualizzati nell'ordine in cui sono stati elaborati (il primo criterio ha il valore di **priorità** 0).

**Nota**: nel centro sicurezza & conformità è possibile modificare solo la priorità del criterio allegati sicuri dopo averlo creato. In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola degli allegati sicuri (che può influire sulla priorità delle regole esistenti).

Per modificare la priorità di un criterio, spostare il criterio più in alto o più in basso nell'elenco (non è possibile modificare direttamente il numero **Priority** nel Centro sicurezza e conformità).

1. Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** per gli \> **Policy** \> **allegati sicuri ATP**.

2. Nella pagina **allegati sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).

3. Nei dettagli dei criteri che vengono visualizzati, fare clic sul pulsante priorità disponibile.

   - Il criterio per gli allegati sicuri con il valore di **priorità** **0** ha solo il pulsante di **riduzione della priorità** disponibile.

   - Il criterio per gli allegati sicuri con il valore di **priorità** più basso (ad esempio, **3**) ha solo il pulsante **aumenta priorità** disponibile.

   - Se si dispone di tre o più criteri per gli allegati sicuri, i criteri tra i valori di priorità più alti e quelli più bassi hanno sia la **priorità di aumento** che i pulsanti di **priorità di riduzione** disponibili.

4. Fare clic su **aumenta priorità** o su **Diminuisci priorità** per modificare il valore di **priorità** .

5. Al termine, fare clic su **Chiudi**.

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a>Utilizzare il Centro sicurezza & conformità per rimuovere i criteri allegati sicuri

1. Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** per gli \> **Policy** \> **allegati sicuri ATP**.

2. Nella pagina **allegati sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).

3. Nei dettagli dei criteri che vengono visualizzati, fare clic su **Elimina criteri**, quindi fare clic su **Sì** nella finestra di dialogo di avviso visualizzata.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>Utilizzo di PowerShell di Exchange Online o standalone EOP PowerShell per configurare i criteri degli allegati sicuri

Come descritto in precedenza, un criterio di allegati sicuri è costituito da un criterio di allegato sicuro e da una regola di allegato sicura.

In PowerShell, la differenza tra i criteri degli allegati sicuri e le regole degli allegati sicuri è evidente. Per gestire i criteri degli allegati sicuri tramite i cmdlet ** \* -SafeAttachmentPolicy** , è possibile gestire le regole degli allegati sicuri utilizzando i cmdlet ** \* -SafeAttachmentRule** .

- In PowerShell, creare innanzitutto il criterio degli allegati sicuri, quindi creare la regola per gli allegati sicuri che identifica il criterio a cui si applica la regola.
- In PowerShell, è possibile modificare le impostazioni nel criterio degli allegati sicuri e la regola degli allegati sicuri separatamente.
- Quando si rimuove un criterio degli allegati sicuri da PowerShell, la regola di allegato sicura corrispondente non viene rimossa automaticamente e viceversa.

### <a name="use-powershell-to-create-safe-attachments-policies"></a>Utilizzo di PowerShell per creare criteri per gli allegati sicuri

La creazione di un criterio allegati sicuri in PowerShell è un processo in due passaggi:

1. Creare il criterio degli allegati sicuri.
2. Creare la regola per gli allegati sicuri che specifichi il criterio degli allegati sicuri a cui si applica la regola.

 **Note**:

- È possibile creare una nuova regola per gli allegati sicuri e assegnare un criterio di allegato sicuro non associato esistente. Non è possibile associare una regola per gli allegati sicuri a più di un criterio di allegato sicuro.

- È possibile configurare le impostazioni seguenti sui nuovi criteri degli allegati sicuri in PowerShell che non sono disponibili nel centro sicurezza & conformità fino a dopo la creazione del criterio:
  - Creare il nuovo criterio come disabilitato (_attivato_ `$false` nel cmdlet **New-SafeAttachmentRule** ).
  - Impostare la priorità del criterio durante la creazione (_priorità_ _\<Number\>_ ) del cmdlet **New-SafeAttachmentRule** .

- Un nuovo criterio degli allegati sicuri creato in PowerShell non è visibile nel centro sicurezza & conformità fino a quando non si assegna il criterio a una regola di allegato sicura.

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>Passaggio 1: utilizzare PowerShell per creare un criterio degli allegati sicuri

Per creare un criterio degli allegati sicuri, utilizzare la sintassi seguente:

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

In questo esempio viene creato un criterio di allegato sicuro denominato contoso all con i valori seguenti:

- Bloccare i messaggi trovati per contenere malware tramite analisi dei documenti attendibili (non si utilizza il parametro _Action_ e il valore predefinito è `Block` ).
- Il reindirizzamento è abilitato e i messaggi che si trovano a contenere malware vengono inviati a sec-ops@contoso.com per l'analisi e l'indagine.
- Se l'analisi degli allegati sicuri non è disponibile o rileva errori, non recapitare il messaggio (non si utilizza il parametro _ActionOnError_ e il valore predefinito è `$true` ).

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>Passaggio 2: utilizzare PowerShell per creare una regola per gli allegati sicuri

Per creare una regola per gli allegati sicuri, utilizzare la sintassi seguente:

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

In questo esempio viene creata una regola di allegato sicura denominata Contoso all con le condizioni seguenti:

- La regola è associata al criterio degli allegati sicuri denominato contoso all.
- La regola viene applicata a tutti i destinatari del dominio contoso.com.
- Poiché non si utilizza il parametro _Priority_ , viene utilizzata la priorità predefinita.
- La regola è abilitata (non viene utilizzato il parametro _Enabled_ e il valore predefinito è `$true` ).

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).

### <a name="use-powershell-to-view-safe-attachment-policies"></a>Utilizzo di PowerShell per visualizzare i criteri degli allegati sicuri

Per visualizzare i criteri degli allegati sicuri esistenti, utilizzare la sintassi seguente:

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In questo esempio viene restituito un elenco riepilogativo di tutti i criteri degli allegati sicuri.

```PowerShell
Get-SafeAttachmentPolicy
```

In questo esempio vengono restituite informazioni dettagliate per il criterio degli allegati sicuri denominato contoso Executives.

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).

### <a name="use-powershell-to-view-safe-attachment-rules"></a>Utilizzo di PowerShell per visualizzare le regole relative agli allegati sicuri

Per visualizzare le regole degli allegati sicuri esistenti, utilizzare la sintassi seguente:

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In questo esempio viene restituito un elenco riepilogativo di tutte le regole relative agli allegati sicuri.

```PowerShell
Get-SafeAttachmentRule
```

Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

In questo esempio vengono restituite informazioni dettagliate per la regola degli allegati sicuri denominata Contoso Executives.

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>Utilizzo di PowerShell per modificare i criteri degli allegati sicuri

Non è possibile rinominare un criterio degli allegati sicuri in PowerShell (il cmdlet **set-SafeAttachmentPolicy** non ha un parametro _Name_ ). Quando si rinomina un criterio di allegati sicuri nel centro sicurezza & Compliance, si sta rinominando solo la _regola_degli allegati sicuri.

In caso contrario, le stesse impostazioni sono disponibili quando si crea un criterio degli allegati sicuri come descritto nel [passaggio 1: utilizzare PowerShell per creare una sezione dei criteri per gli allegati sicuri](#step-1-use-powershell-to-create-a-safe-attachment-policy) più indietro in questo articolo.

Per modificare un criterio degli allegati sicuri, utilizzare la sintassi seguente:

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>Utilizzo di PowerShell per modificare le regole relative agli allegati sicuri

L'unica impostazione che non è disponibile quando si modifica una regola per gli allegati sicuri in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata. Per abilitare o disabilitare le regole per gli allegati sicuri esistenti, vedere la sezione successiva.

In caso contrario, le stesse impostazioni sono disponibili quando si crea una regola come descritto nel [passaggio 2: utilizzare PowerShell per creare una regola per gli allegati sicuri](#step-2-use-powershell-to-create-a-safe-attachment-rule) descritta in precedenza in questo articolo.

Per modificare una regola per gli allegati sicuri, utilizzare la sintassi seguente:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>Utilizzo di PowerShell per abilitare o disabilitare le regole relative agli allegati sicuri

L'abilitazione o disabilitazione di una regola per gli allegati sicuri in PowerShell consente di abilitare o disabilitare l'intero criterio per i collegamenti sicuri (la regola di allegati sicuri e il criterio degli allegati sicuri assegnato).

Per abilitare o disabilitare una regola per gli allegati sicuri in PowerShell, utilizzare la sintassi seguente:

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

In questo esempio viene disabilitata la regola per gli allegati sicuri denominata Marketing Department.

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

In questo esempio viene abilitata la stessa regola.

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) e [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a>Utilizzo di PowerShell per impostare la priorità delle regole per gli allegati sicuri

Il valore di priorità più alto che è possibile impostare in una regola è 0. Il valore più basso che è possibile impostare dipende dal numero di regole. Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4. Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole. Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola su 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.

Per impostare la priorità di una regola per gli allegati sicuri in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

**Nota**: per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-SafeAttachmentRule** .

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>Utilizzo di PowerShell per rimuovere i criteri degli allegati sicuri

Quando si utilizza PowerShell per rimuovere un criterio di allegato sicuro, la regola di allegato sicura corrispondente non viene rimossa.

Per rimuovere un criterio degli allegati sicuri in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

In questo esempio viene rimosso il criterio degli allegati sicuri denominato Marketing Department.

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>Utilizzo di PowerShell per rimuovere le regole relative agli allegati sicuri

Quando si utilizza PowerShell per rimuovere una regola per gli allegati sicuri, il criterio degli allegati sicuri corrispondente non viene rimosso.

Per rimuovere una regola per gli allegati sicuri in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

In questo esempio viene rimossa la regola per gli allegati sicuri denominata Marketing Department.

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).

## <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare che i criteri allegati sicuri siano stati creati, modificati o rimossi correttamente, eseguire una delle operazioni seguenti:

- Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** per gli \> **Policy** \> **allegati sicuri ATP**. Verificare l'elenco dei criteri, i relativi valori di **stato** e i relativi valori di **priorità** . Per visualizzare ulteriori dettagli, selezionare il criterio dall'elenco e visualizzare i dettagli all'interno del volo.

- In Exchange Online PowerShell o Exchange Online Protection PowerShell, sostituire \<Name\> con il nome del criterio o della regola, eseguire il comando riportato di seguito e verificare le impostazioni:

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

Per verificare che gli allegati sicuri eseguano l'analisi dei messaggi, controllare i report di protezione avanzata delle minacce disponibili. Per ulteriori informazioni, vedere [View Reports for Office 365 ATP](view-reports-for-atp.md) e [use Explorer in the Security & Compliance Center](threat-explorer.md).
