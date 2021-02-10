---
title: Configurare i criteri allegati sicuri in Microsoft Defender per Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Informazioni su come definire i criteri allegati sicuri per proteggere l'organizzazione da file dannosi nella posta elettronica.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 314f7fd882986c22adddd0c4570b4aa9f49a40f3
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166334"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Configurare i criteri allegati sicuri in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Questo articolo è rivolto ai clienti aziendali di [Microsoft Defender per Office 365](office-365-atp.md). Per informazioni sull'analisi degli allegati in Outlook, vedere [Advanced Outlook.com security.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Allegati sicuri è una funzionalità di Microsoft Defender per [Office 365](office-365-atp.md) che utilizza un ambiente virtuale per controllare gli allegati nei messaggi di posta elettronica in ingresso dopo che sono stati analizzati dalla protezione [antimalware in Exchange Online Protection (EOP),](anti-malware-protection.md)ma prima del recapito ai destinatari. Per altre informazioni, vedere [Allegati sicuri in Microsoft Defender per Office 365.](atp-safe-attachments.md)

Non esiste un criterio predefinito per gli allegati sicuri o predefinito. Per ottenere l'analisi degli allegati dei messaggi di posta elettronica con allegati sicuri, è necessario creare uno o più criteri allegati sicuri come descritto in questo articolo.

È possibile configurare i criteri allegati sicuri nel Centro sicurezza & conformità o in PowerShell (PowerShell di Exchange Online per le organizzazioni di Microsoft 365 idonee con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online, ma con sottoscrizioni di componenti aggiuntivi Defender per Office 365).

Gli elementi di base di un criterio Allegati sicuri sono:

- **Il** criterio allegati sicuri : specifica le azioni per i rilevamenti di malware sconosciuti, se inviare messaggi con allegati di malware a un indirizzo di posta elettronica specificato e se recapitare i messaggi se l'analisi degli allegati sicuri non può essere completata.
- **La regola degli allegati sicuri**: specifica la priorità e i filtri destinatario (a chi si applica il criterio).

La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri allegati sicuri nel Centro sicurezza & conformità:

- Quando si crea un criterio Allegati sicuri, si crea contemporaneamente una regola per gli allegati sicuri e il criterio allegati sicuri associato utilizzando lo stesso nome per entrambi.
- Quando si modifica un criterio Allegati sicuri, le impostazioni relative al nome, alla priorità, all'allegato abilitato o disabilitato e ai filtri destinatari modificano la regola degli allegati sicuri. Tutte le altre impostazioni modificano il criterio degli allegati sicuri associato.
- Quando si rimuove un criterio Allegati sicuri, vengono rimossi la regola degli allegati sicuri e i criteri allegati sicuri associati.

In PowerShell di Exchange Online o in EOP PowerShell autonomo i criteri e la regola vengono gestiti separatamente. Per ulteriori informazioni, vedere la sezione Utilizzare PowerShell di Exchange Online o [PowerShell EOP](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) autonomo per configurare i criteri allegati sicuri più avanti in questo articolo.

> [!NOTE]
> Nell'area delle impostazioni globali delle impostazioni allegati sicuri è possibile configurare caratteristiche che non dipendono dai criteri Allegati sicuri. Per istruzioni, vedere Attivare Allegati sicuri [per SharePoint, OneDrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) e Documenti sicuri in Microsoft [365 E5.](safe-docs.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Aprire il Centro sicurezza e conformità in<https://protection.office.com/>. Per passare direttamente alla **pagina Allegati sicuri,** utilizzare <https://protection.office.com/safeattachmentv2> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni seguenti:
  - Per creare, modificare ed eliminare i criteri allegati sicuri,  è necessario essere membri dei gruppi di ruoli Gestione organizzazione  o Amministratore sicurezza nel Centro sicurezza & conformità e membri del gruppo di ruoli Gestione organizzazione in Exchange Online.  
  - Per l'accesso in sola lettura ai criteri allegati  sicuri,  è necessario essere membri dei gruppi di ruoli Lettore globale o Lettore di sicurezza nel Centro sicurezza & conformità.

  Per ulteriori informazioni, vedere [Autorizzazioni nel Centro sicurezza & conformità](permissions-in-the-security-and-compliance-center.md) e Autorizzazioni in Exchange [Online.](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)

  **Note**:

  - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.

- Per le impostazioni consigliate per i criteri allegati sicuri, vedere [Impostazioni allegati sicuri.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)

- Consentire fino a 30 minuti per l'applicazione di un criterio nuovo o aggiornato.

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a>Usare il Centro sicurezza & conformità per creare criteri allegati sicuri

La creazione di un criterio allegati sicuri personalizzato nel Centro sicurezza & conformità crea la regola degli allegati sicuri e il criterio allegati sicuri associato contemporaneamente usando lo stesso nome per entrambi.

1. Nel Centro sicurezza & conformità passare a **Allegati** sicuri dei criteri di gestione delle \>  \> **minacce ATP.**

2. Nella pagina **Allegati sicuri** fare clic su **Crea.**

3. Verrà **visualizzata la procedura guidata nuovo criterio Allegati** sicuri. Nella pagina **Assegnare un nome al** criterio configurare le impostazioni seguenti:

   - **Nome**: immettere un nome univoco descrittivo per il criterio.

   - **Descrizione**: immettere una descrizione opzionale per il criterio.

   Al termine dell'operazione, fare clic su **Avanti**.

4. Nella pagina **Impostazioni** visualizzata configurare le impostazioni seguenti:

   - **Risposta malware sconosciuto allegati sicuri:** selezionare uno dei seguenti valori:

     - **Disattivato:** in genere, questo valore non è consigliato.
     - **Monitor**
     - **Blocco:** questo è il valore predefinito e il valore consigliato nei criteri di sicurezza standard [e rigidi.](preset-security-policies.md)
     - **Sostituisce**
     - **Recapito dinamico (funzionalità di anteprima)**

     Questi valori sono illustrati nelle [impostazioni del criterio Allegati sicuri.](atp-safe-attachments.md#safe-attachments-policy-settings)

   - Inviare l'allegato al seguente indirizzo di posta **elettronica:** per  i valori di azione **Blocca,** Monitora o **Sostituisci,** è possibile selezionare Abilita reindirizzamento per inviare messaggi contenenti allegati di malware all'indirizzo di posta elettronica interno o esterno specificato per l'analisi e l'analisi.

     Per le impostazioni dei criteri Standard e Strict è consigliabile abilitare il reindirizzamento. Per ulteriori informazioni, vedere [Impostazioni allegati sicuri.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)

   - **Applicare la selezione** precedente se si verifica il timeout o  l'errore dell'analisi antimalware per gli allegati: l'azione specificata dalla risposta malware sconosciuto allegati sicuri viene eseguita sui messaggi anche quando l'analisi degli allegati sicuri non può essere completata. Se è stata selezionata questa opzione, selezionare sempre **Reindirizzamento abilitato.** In caso contrario, i messaggi potrebbero essere persi.

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

6. Nella pagina **Controlla le impostazioni** visualizzata, rivedere le impostazioni. È possibile fare **clic su** Modifica per ogni impostazione per modificarla.

   Al termine dell'operazione, scegliere **Fine**.

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a>Usare il Centro sicurezza & conformità per visualizzare i criteri allegati sicuri

1. Nel Centro sicurezza & conformità passare a **Allegati** sicuri dei criteri di gestione delle \>  \> **minacce ATP.**

2. Nella pagina **Allegati sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).

   I dettagli dei criteri vengono visualizzati in un riquadro a comparsa

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a>Utilizzare il Centro sicurezza & conformità per modificare i criteri allegati sicuri

1. Nel Centro sicurezza & conformità passare a **Allegati** sicuri dei criteri di gestione delle \>  \> **minacce ATP.**

2. Nella pagina **Allegati sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).

3. Nel riquadro a comparsa dei dettagli del criterio visualizzato, fare clic **su Modifica criterio.**

Le impostazioni disponibili nel riquadro a comparsa visualizzate sono identiche a quelle descritte nella sezione Usare il Centro sicurezza [&](#use-the-security--compliance-center-to-create-safe-attachments-policies) conformità per creare criteri allegati sicuri.

Per abilitare o disabilitare un criterio o impostare l'ordine di priorità dei criteri, vedere le sezioni seguenti.

### <a name="enable-or-disable-safe-attachments-policies"></a>Abilitare o disabilitare i criteri allegati sicuri

1. Nel Centro sicurezza & conformità passare a **Allegati** sicuri dei criteri di gestione delle \>  \> **minacce ATP.**

2. Si noti il valore nella **colonna** Stato:

   - Spostare l'interruttore a sinistra ![Disattivare i criteri](../../media/scc-toggle-off.png) per disabilitare il criterio.

   - Spostare l'interruttore verso destra ![Attivare i criteri](../../media/scc-toggle-on.png) per abilitare il criterio.

### <a name="set-the-priority-of-safe-attachments-policies"></a>Impostare la priorità dei criteri allegati sicuri

Per impostazione predefinita, ai criteri Allegati sicuri viene data una priorità basata sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità inferiore rispetto ai criteri precedenti). Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa). Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.

Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).

I criteri allegati sicuri vengono visualizzati nell'ordine in cui vengono elaborati (il primo criterio ha il **valore Priority** 0).

**Nota:** nel Centro sicurezza & conformità, è possibile modificare la priorità del criterio Allegati sicuri solo dopo la creazione. In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola degli allegati sicuri (che può influire sulla priorità delle regole esistenti).

Per modificare la priorità di un criterio, spostare il criterio più in alto o più in basso nell'elenco (non è possibile modificare direttamente il numero **Priority** nel Centro sicurezza e conformità).

1. Nel Centro sicurezza & conformità passare a **Allegati** sicuri dei criteri di gestione delle \>  \> **minacce ATP.**

2. Nella pagina **Allegati sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).

3. Nel riquadro a comparsa dei dettagli del criterio visualizzato, fare clic sul pulsante di priorità disponibile.

   - Per il criterio Allegati sicuri con **valore Priorità** **0** è disponibile solo il **pulsante Diminuisci** priorità.

   - Per il criterio Allegati sicuri con il valore **di priorità** più basso (ad esempio, **3)** è disponibile solo il pulsante **Aumenta** priorità.

   - Se si dispone di tre o più criteri allegati sicuri,  i criteri tra i valori di priorità più alta e più bassa hanno entrambi i pulsanti Aumenta priorità e **Diminuisci** priorità disponibili.

4. Fare **clic su Aumenta priorità** o **Diminuisci priorità** per modificare il valore **di** Priorità.

5. Al termine, fare clic su **Chiudi**.

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a>Usare il Centro sicurezza & conformità per rimuovere i criteri allegati sicuri

1. Nel Centro sicurezza & conformità passare a **Allegati** sicuri dei criteri di gestione delle \>  \> **minacce ATP.**

2. Nella pagina **Allegati sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).

3. Nel riquadro a comparsa dei dettagli del criterio visualizzato, fare clic su **Elimina** criterio e quindi su **Sì** nella finestra di dialogo di avviso visualizzata.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>Utilizzare PowerShell di Exchange Online o PowerShell EOP autonomo per configurare i criteri allegati sicuri

Come descritto in precedenza, i criteri allegati sicuri sono costituiti da un criterio allegati sicuri e da una regola per gli allegati sicuri.

In PowerShell, la differenza tra i criteri allegati sicuri e le regole degli allegati sicuri è evidente. È possibile gestire i criteri allegati sicuri utilizzando i cmdlet **\* -SafeAttachmentPolicy** e gestire le regole degli allegati sicuri utilizzando i cmdlet **\* -SafeAttachmentRule.**

- In PowerShell, si crea prima il criterio degli allegati sicuri, quindi si crea la regola degli allegati sicuri che identifica il criterio a cui si applica la regola.
- In PowerShell, è possibile modificare le impostazioni nei criteri allegati sicuri e nella regola degli allegati sicuri separatamente.
- Quando si rimuove un criterio allegati sicuri da PowerShell, la regola degli allegati sicuri corrispondente non viene rimossa automaticamente e viceversa.

### <a name="use-powershell-to-create-safe-attachments-policies"></a>Utilizzare PowerShell per creare criteri allegati sicuri

La creazione di un criterio allegati sicuri in PowerShell è un processo in due passaggi:

1. Creare il criterio allegati sicuri.
2. Creare la regola degli allegati sicuri che specifica il criterio allegati sicuri a cui si applica la regola.

 **Note**:

- È possibile creare una nuova regola per gli allegati sicuri e assegnarle un criterio allegato sicuro non associato esistente. Una regola degli allegati sicuri non può essere associata a più criteri allegati sicuri.

- È possibile configurare le impostazioni seguenti nei nuovi criteri allegati sicuri in PowerShell che non sono disponibili nel Centro sicurezza & conformità fino a quando non si crea il criterio:
  - Creare il nuovo criterio come disabilitato (_abilitato_ `$false` nel cmdlet **New-SafeAttachmentRule).**
  - Impostare la priorità del criterio durante la creazione (_Priority_ ) nel _\<Number\>_ cmdlet **New-SafeAttachmentRule.**

- Un nuovo criterio allegati sicuri creato in PowerShell non è visibile nel Centro sicurezza & conformità finché non si assegna il criterio a una regola degli allegati sicuri.

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>Passaggio 1: Utilizzare PowerShell per creare un criterio allegati sicuri

Per creare un criterio allegati sicuri, utilizzare la sintassi seguente:

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

In questo esempio viene creato un criterio allegati sicuri denominato Contoso All con i seguenti valori:

- Bloccare i messaggi che vengono trovati come contenenti malware dall'analisi dei documenti sicuri (non viene utilizzato il parametro _Action_ e il valore predefinito è `Block` ).
- Il reindirizzamento è abilitato e i messaggi che contengono malware vengono inviati a sec-ops@contoso.com per l'analisi e l'analisi.
- Se l'analisi degli allegati sicuri non è disponibile o si verificano errori, non recapitare il messaggio (non viene utilizzato il parametro _ActionOnError_ e il valore predefinito è `$true` ).

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-SafeAttachmentPolicy.](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy)

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>Passaggio 2: Utilizzare PowerShell per creare una regola degli allegati sicuri

Per creare una regola per gli allegati sicuri, utilizzare la sintassi seguente:

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

In questo esempio viene creata una regola per gli allegati sicuri denominata Contoso All con le seguenti condizioni:

- La regola è associata al criterio allegati sicuri denominato Contoso All.
- La regola si applica a tutti i destinatari nel contoso.com dominio.
- Poiché non viene utilizzato il parametro _Priority,_ viene utilizzata la priorità predefinita.
- La regola è abilitata (non viene utilizzato il parametro _Enabled_ e il valore predefinito è `$true` ).

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-SafeAttachmentRule.](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule)

### <a name="use-powershell-to-view-safe-attachment-policies"></a>Utilizzare PowerShell per visualizzare i criteri allegati sicuri

Per visualizzare i criteri allegati sicuri esistenti, utilizzare la sintassi seguente:

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In questo esempio viene restituito un elenco riepilogativo di tutti i criteri allegati sicuri.

```PowerShell
Get-SafeAttachmentPolicy
```

In questo esempio vengono restituite informazioni dettagliate per il criterio allegati sicuri denominato Contoso Executives.

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SafeAttachmentPolicy.](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy)

### <a name="use-powershell-to-view-safe-attachment-rules"></a>Utilizzare PowerShell per visualizzare le regole degli allegati sicuri

Per visualizzare le regole degli allegati sicuri esistenti, utilizzare la sintassi seguente:

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In questo esempio viene restituito un elenco riepilogativo di tutte le regole degli allegati sicuri.

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

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SafeAttachmentRule.](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule)

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>Utilizzare PowerShell per modificare i criteri allegati sicuri

Non è possibile rinominare un criterio allegati sicuri in PowerShell (il cmdlet **Set-SafeAttachmentPolicy** non dispone di alcun _parametro_ Name). Quando si rinomina un criterio Allegati sicuri nel Centro sicurezza & conformità, si rinomina solo la regola degli allegati _sicuri._

In caso contrario, le stesse impostazioni sono disponibili quando si crea un criterio allegati sicuri come descritto nel passaggio [1:](#step-1-use-powershell-to-create-a-safe-attachment-policy) Utilizzare PowerShell per creare una sezione dei criteri allegati sicuri più indietro in questo articolo.

Per modificare un criterio allegati sicuri, utilizzare la sintassi seguente:

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeAttachmentPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy)

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>Utilizzare PowerShell per modificare le regole degli allegati sicuri

L'unica impostazione non disponibile quando si modifica una regola degli allegati sicuri in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata. Per abilitare o disabilitare le regole degli allegati sicuri esistenti, vedere la sezione successiva.

In caso contrario, le stesse impostazioni sono disponibili quando si crea una regola come descritto nel passaggio [2:](#step-2-use-powershell-to-create-a-safe-attachment-rule) Utilizzare PowerShell per creare una regola degli allegati sicuri più indietro in questo articolo.

Per modificare una regola degli allegati sicuri, utilizzare la sintassi seguente:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeAttachmentRule.](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>Abilitazione o disabilitazione delle regole degli allegati sicuri tramite PowerShell

L'abilitazione o la disabilitazione di una regola degli allegati sicuri in PowerShell abilita o disabilita l'intero criterio Allegati sicuri (la regola degli allegati sicuri e il criterio degli allegati sicuri assegnato).

Per abilitare o disabilitare una regola degli allegati sicuri in PowerShell, utilizzare la sintassi seguente:

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

In questo esempio viene disabilitata la regola degli allegati sicuri denominata Marketing Department.

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

In questo esempio viene abilitata la stessa regola.

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) [e Disable-SafeAttachmentRule.](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule)

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a>Utilizzare PowerShell per impostare la priorità delle regole degli allegati sicuri

Il valore di priorità più alto che è possibile impostare in una regola è 0. Il valore più basso che è possibile impostare dipende dal numero di regole. Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4. Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole. Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola su 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.

Per impostare la priorità di una regola degli allegati sicuri in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

**Nota:** per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-SafeAttachmentRule.**

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeAttachmentRule.](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>Utilizzare PowerShell per rimuovere i criteri allegati sicuri

Quando si utilizza PowerShell per rimuovere un criterio allegati sicuri, la regola degli allegati sicuri corrispondente non viene rimossa.

Per rimuovere un criterio allegati sicuri in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

In questo esempio viene rimosso il criterio allegati sicuri denominato Marketing Department.

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-SafeAttachmentPolicy.](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy)

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>Utilizzare PowerShell per rimuovere le regole degli allegati sicuri

Quando si utilizza PowerShell per rimuovere una regola degli allegati sicuri, il criterio degli allegati sicuri corrispondente non viene rimosso.

Per rimuovere una regola degli allegati sicuri in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

In questo esempio viene rimossa la regola degli allegati sicuri denominata Marketing Department.

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-SafeAttachmentRule.](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule)

## <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare la corretta creazione, modifica o rimozione dei criteri allegati sicuri, eseguire una delle operazioni seguenti:

- Nel Centro sicurezza & conformità passare a **Allegati** sicuri dei criteri di gestione delle \>  \> **minacce ATP.** Verificare l'elenco dei criteri, i relativi **valori di** stato e i relativi **valori di** priorità. Per visualizzare altri dettagli, selezionare il criterio nell'elenco e visualizzare i dettagli nel riquadro a comparsa.

- In PowerShell di Exchange Online o PowerShell di Exchange Online Protection, sostituire con il nome del criterio o della regola, eseguire il comando seguente \<Name\> e verificare le impostazioni:

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

Per verificare che allegati sicuri eseere in corso l'analisi dei messaggi, controllare i report di Defender per Office 365 disponibili. Per altre informazioni, vedere [Visualizzare i report per Defender per Office 365](view-reports-for-atp.md) e Usare Esplora risorse nel Centro sicurezza & [conformità.](threat-explorer.md)
