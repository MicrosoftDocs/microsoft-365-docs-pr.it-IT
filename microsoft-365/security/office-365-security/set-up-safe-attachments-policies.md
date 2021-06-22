---
title: Configurare i Cassaforte allegati in Microsoft Defender per Office 365
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
description: Informazioni su come definire i criteri Cassaforte allegati per proteggere l'organizzazione da file dannosi nella posta elettronica.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e7220140c25ecf457b42514356e41aabdf5481bb
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054329"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Configurare i Cassaforte allegati in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Questo articolo è rivolto ai clienti aziendali di [Microsoft Defender per Office 365](whats-new-in-defender-for-office-365.md). Se si è un utente principale che desidera informazioni sull'analisi degli allegati in Outlook, vedere [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Cassaforte Allegati è una funzionalità di [Microsoft Defender per Office 365 che](whats-new-in-defender-for-office-365.md) usa un ambiente virtuale per archiviare gli allegati nei messaggi di posta elettronica in ingresso dopo essere stati analizzati dalla protezione [antimalware in Exchange Online Protection (EOP),](anti-malware-protection.md)ma prima del recapito ai destinatari. Per ulteriori informazioni, vedere [Cassaforte allegati in Microsoft Defender per Office 365](safe-attachments.md).

Non esiste un criterio predefinito o predefinito Cassaforte allegati. Per ottenere Cassaforte allegati degli allegati dei messaggi di posta elettronica, è necessario creare uno o più criteri Cassaforte allegati come descritto in questo articolo.

È possibile configurare i criteri allegati Cassaforte nel portale di Microsoft 365 Defender o in PowerShell (Exchange Online PowerShell per le organizzazioni Microsoft 365 idonee con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online, ma con sottoscrizioni di componenti aggiuntivi defender per Office 365).

Gli elementi di base di un criterio Cassaforte allegati sono:

- Criterio allegati sicuri **:** Specifica le azioni per i rilevamenti di malware sconosciuti, se inviare messaggi con allegati di malware a un indirizzo di posta elettronica specificato e se recapitare i messaggi se l'analisi degli allegati Cassaforte non può essere completata.
- **La regola degli allegati sicuri**: Specifica la priorità e i filtri destinatari (a cui si applica il criterio).

La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri Cassaforte allegati nel portale Microsoft 365 Defender:

- Quando si crea un criterio Cassaforte allegati, si sta creando contemporaneamente una regola degli allegati sicuri e il criterio di allegato sicuro associato utilizzando lo stesso nome per entrambi.
- Quando si modifica un criterio Cassaforte allegati, le impostazioni relative al nome, alla priorità, abilitate o disabilitate e ai filtri destinatari modificano la regola degli allegati sicuri. Tutte le altre impostazioni modificano i criteri allegati sicuri associati.
- Quando si rimuove un criterio Cassaforte allegati sicuri, vengono rimossi la regola degli allegati sicuri e i criteri allegati sicuri associati.

In PowerShell di Exchange Online o in EOP PowerShell autonomo i criteri e la regola vengono gestiti separatamente. Per ulteriori informazioni, vedere la sezione Use [Exchange Online PowerShell or standalone EOP PowerShell to configure Cassaforte Attachments più](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) avanti in questo articolo.

> [!NOTE]
> Nell'area impostazioni globali delle impostazioni Cassaforte allegati è possibile configurare funzionalità che non dipendono dai criteri Cassaforte allegati. Per istruzioni, vedere Attivare Cassaforte allegati per [SharePoint, OneDrive e](turn-on-mdo-for-spo-odb-and-teams.md) Microsoft Teams e [Cassaforte documenti in Microsoft 365 E5](safe-docs.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Per aprire il portale di Microsoft 365 Defender, andare alla pagina <https://security.microsoft.com>. Per passare direttamente alla pagina **Cassaforte allegati,** utilizzare <https://security.microsoft.com/safeattachmentv2> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni seguenti:
  - Per creare, modificare ed eliminare i criteri allegati Cassaforte, è  necessario  essere membri dei gruppi di  ruoli Gestione organizzazione  o Amministratore sicurezza nel portale di Microsoft 365 Defender e membri del gruppo di ruoli Gestione organizzazione in Exchange Online.
  - Per l'accesso in sola lettura ai criteri Cassaforte allegati,  è necessario  essere membri dei gruppi di ruoli Lettore globale o Lettore di sicurezza nel portale Microsoft 365 Defender sicurezza.

  Per ulteriori informazioni, vedere [Autorizzazioni nel portale Microsoft 365 Defender e](permissions-microsoft-365-security-center.md) Autorizzazioni in [Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Note**:

  - L'aggiunta di utenti al ruolo Azure Active Directory corrispondente nel interfaccia di amministrazione di Microsoft 365 offre agli utenti le  autorizzazioni necessarie nel portale di Microsoft 365 Defender e le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).
  - Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.

- Per le impostazioni consigliate per i criteri Cassaforte allegati, vedere impostazioni [Cassaforte allegati](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).

- Consentire fino a 30 minuti per l'applicazione di un criterio nuovo o aggiornato.

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies"></a>Usare il portale Microsoft 365 Defender per creare criteri Cassaforte allegati

La creazione di un criterio Cassaforte allegati personalizzati nel portale di Microsoft 365 Defender crea la regola degli allegati sicuri e i criteri allegati sicuri associati contemporaneamente utilizzando lo stesso nome per entrambi.

1. Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & posta elettronica & criteri di minaccia sezione Criteri \>  \>  \>  di \> **Cassaforte Allegati**.

2. Nella pagina **Cassaforte allegati** fare clic su Crea ![ icona ](../../media/m365-cc-sc-create-icon.png) **Crea**.

3. Viene aperta la creazione guidata criteri. Nella pagina **Assegnare un nome al** criterio configurare le impostazioni seguenti:
   - **Nome**: immettere un nome univoco descrittivo per il criterio.
   - **Descrizione**: immettere una descrizione opzionale per il criterio.

   Al termine dell'operazione, fare clic su **Avanti**.

4. Nella pagina **Utenti e domini** visualizzata identificare i destinatari interni a cui si applica il criterio (condizioni del destinatario):
   - **Utenti**: la cassette postali specificate, utenti di posta o contatti di posta specificati nell'organizzazione.
   - **Gruppi**: i gruppi di distribuzione specificati, gruppi di sicurezza abilitati alla posta elettronica o gruppi di Microsoft 365 nell'organizzazione.
   - **Domini**: tutti i destinatari nei domini specificati [accettati](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) nell'organizzazione.

   Fare clic nella casella appropriata, iniziare a digitare un valore e selezionare il valore desiderato nei risultati. Ripetere questa procedura tutte le volte necessarie. Per rimuovere un valore esistente, fare clic su Rimuovi ![Icona Rimuovi](../../media/m365-cc-sc-remove-selection-icon.png) accanto al valore.

   Per utenti o gruppi è possibile usare la maggior parte degli identificatori, ad esempio nome, nome visualizzato, alias, indirizzo di posta elettronica, nome dell'account e così via, ma il nome visualizzato corrispondente viene visualizzato nei risultati. Per gli utenti, immettere un asterisco (\*) da solo per visualizzare tutti i valori disponibili.

   Più valori della stessa condizione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_). Condizioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).

   - **Escludere questi utenti, gruppi e domini**: per aggiungere eccezioni per i destinatari interni a cui si applicano i criteri (eccezione destinatari), selezionare questa opzione e configurare le eccezioni. Impostazioni e comportamento sono equivalenti alle condizioni.

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nella pagina **Impostazioni** configurazione delle impostazioni seguenti:

   - **Cassaforte Allegati risposta malware sconosciuta**: selezionare uno dei seguenti valori:
     - **Disattivato:** in genere, non è consigliabile questo valore.
     - **Monitor**
     - **Block**: questo è il valore predefinito e il valore consigliato in Standard e Strict [preset security policies](preset-security-policies.md).
     - **Sostituisce**
     - **Recapito dinamico (funzionalità di anteprima)**

     Questi valori sono illustrati nelle impostazioni [Cassaforte dei criteri Allegati.](safe-attachments.md#safe-attachments-policy-settings)

   - Reindirizzare i messaggi con allegati rilevati **:** se si seleziona Abilita reindirizzamento **,** è possibile specificare un indirizzo di posta elettronica nella casella Invia messaggi che contengono allegati **bloccati,** monitorati o sostituiti all'indirizzo di posta elettronica specificato per inviare messaggi contenenti allegati di malware per l'analisi e l'analisi.

     Per le impostazioni dei criteri Standard e Strict è consigliabile abilitare il reindirizzamento. Per ulteriori informazioni, vedere [impostazioni Cassaforte allegati](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).

   - Applicare la risposta di rilevamento allegati Cassaforte se l'analisi non può essere completata (timeout o **errori): l'azione** specificata da **Cassaforte Allegati** risposta malware sconosciuta viene eseguita sui messaggi anche quando non è possibile completare l'analisi degli allegati di Cassaforte. Se è stata selezionata questa opzione, selezionare sempre **Abilita reindirizzamento** e specificare un indirizzo di posta elettronica per inviare messaggi contenenti allegati di malware. In caso contrario, i messaggi potrebbero essere persi.

   Al termine dell'operazione, fare clic su **Avanti**.

6. Nella pagina **Controllo** visualizzata controllare le impostazioni. È possibile selezionare **Modifica** in ogni sezione per modificare le impostazioni all'interno della sezione. Oppure è possibile fare clic su **Indietro** o selezionare la pagina specifica della procedura guidata.

   Al termine, fare clic su **Invia.**

7. Nel messaggio di conferma visualizzato fare clic su **Fatto**.

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-attachments-policies"></a>Utilizzare il portale Microsoft 365 Defender per visualizzare i criteri Cassaforte allegati

1. Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & posta elettronica & criteri di minaccia sezione Criteri \>  \>  \>  di \> **Cassaforte Allegati**.

2. Nella pagina **Cassaforte allegati** vengono visualizzate le proprietà seguenti nell'elenco dei criteri:
   - **Nome**
   - **Stato**
   - **Priorità**

3. Quando si seleziona un criterio facendo clic sul nome, le impostazioni dei criteri vengono visualizzate in un riquadro a comparsa.

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-attachments-policies"></a>Utilizzare il portale Microsoft 365 Defender per modificare i criteri Cassaforte allegati

1. Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & posta elettronica & criteri di minaccia sezione Criteri \>  \>  \>  di \> **Cassaforte Allegati**.

2. Nella pagina **Cassaforte allegati** selezionare un criterio dall'elenco facendo clic sul nome.

3. Nel riquadro a comparsa dei dettagli sui criteri visualizzato selezionare **Modifica** in ogni sezione per modificare le impostazioni all'interno della sezione. Per ulteriori informazioni sulle impostazioni, vedere la sezione Usare il portale di Microsoft 365 Defender per creare criteri Cassaforte [allegati](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) più indietro in questo articolo.  

Per abilitare o disabilitare un criterio o impostare l'ordine di priorità dei criteri, vedere le sezioni seguenti.

### <a name="enable-or-disable-safe-attachments-policies"></a>Abilitare o disabilitare i criteri Cassaforte allegati

1. Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & posta elettronica & criteri di minaccia sezione Criteri \>  \>  \>  di \> **Cassaforte Allegati**.

2. Nella pagina **Cassaforte allegati** selezionare un criterio dall'elenco facendo clic sul nome.

3. Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato è presente uno dei valori seguenti:
   - **Criterio disattivato**: per attivare il criterio, fare clic su ![Attiva icona](../../media/m365-cc-sc-turn-on-off-icon.png) **Attiva** .
   - **Criterio attivato**: per disattivare il criterio, fare clic su ![Disattiva icona](../../media/m365-cc-sc-turn-on-off-icon.png) **Disattiva**.

4. Nella finestra di dialogo di conferma visualizzata fare clic su **Attiva** o **Disattiva**.

5. Fare clic su **Chiudi** nel riquadro a comparsa dei dettagli del criterio.

Tornare alla pagina dei criteri principale, il valore **Stato** del criterio sarà **Attivato** o **Disattivato**.

### <a name="set-the-priority-of-safe-attachments-policies"></a>Impostare la priorità dei criteri Cassaforte allegati

Per impostazione predefinita, Cassaforte criteri allegati hanno una priorità basata sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità più bassa rispetto ai criteri precedenti). Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa). Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.

Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).

Cassaforte I criteri allegati vengono visualizzati nell'ordine in cui vengono elaborati (il primo criterio ha il **valore Priority** 0).

**Nota:** nel portale Microsoft 365 Defender, è possibile modificare la priorità del criterio allegati Cassaforte solo dopo aver creato il criterio. In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola degli allegati sicuri (che può influire sulla priorità delle regole esistenti).

Per modificare la priorità di un criterio, fare clic su **Aumenta priorità** o **Riduci priorità** nelle proprietà del criterio. Non è possibile modificare direttamente il valore **Priorità** nel portale di Microsoft 365 Defender. La modifica di priorità di un criterio è utile solo se si hanno più criteri.

1. Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & posta elettronica & criteri di minaccia sezione Criteri \>  \>  \>  di \> **Cassaforte Allegati**.

2. Nella pagina **Cassaforte allegati** selezionare un criterio dall'elenco facendo clic sul nome.

3. Nella parte superiore del riquadro a comparsa dei  dettagli del  criterio visualizzato, vedrai Aumentare la priorità o Diminuire la priorità in base al valore di priorità corrente e al numero di criteri:
   - Per il criterio con **valore Priority** **0 è** disponibile solo **l'opzione Riduci** priorità.
   - Il criterio con il valore **Di priorità** più basso (ad esempio, **3)** ha solo l'opzione **Aumenta** priorità disponibile.
   - Se si dispone di tre o più criteri, per i  criteri tra i valori di priorità più alta e più bassa sono disponibili le opzioni Aumenta priorità e **Riduci** priorità.

   Fare clic![ sull’icona Aumenta priorità](../../media/m365-cc-sc-increase-icon.png) **Aumenta priorità** o ![sull’icona Riduci priorità](../../media/m365-cc-sc-decrease-icon.png) **Riduci priorità** per modificare il valore **Priorità**.

4. Al termine, fare clic su **Chiudi** nel riquadro a comparsa dei dettagli del criterio.

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-attachments-policies"></a>Utilizzare il portale Microsoft 365 Defender per rimuovere i criteri Cassaforte allegati

1. Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & posta elettronica & criteri di minaccia sezione Criteri \>  \>  \>  di \> **Cassaforte Allegati**.

2. Nella pagina **Cassaforte allegati** selezionare un criterio personalizzato nell'elenco facendo clic sul nome del criterio.

3. Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato fare clic![ sull'icona Altre azioni](../../media/m365-cc-sc-more-actions-icon.png) **Altre azioni** \> ![Icona Elimina criterio](../../media/m365-cc-sc-delete-icon.png) **Elimina criterio**.

4. Nella finestra di dialogo di conferma che viene visualizzata fare clic su **Sì**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>Utilizzare Exchange Online PowerShell o PowerShell EOP autonomo per configurare i criteri Cassaforte allegati

Come descritto in precedenza, un criterio Cassaforte allegati è costituito da un criterio di allegato sicuro e da una regola degli allegati sicuri.

In PowerShell, la differenza tra i criteri degli allegati sicuri e le regole degli allegati sicuri è evidente. È possibile gestire i criteri degli allegati sicuri utilizzando i cmdlet **\* -SafeAttachmentPolicy** e le regole degli allegati sicuri utilizzando i cmdlet **\* -SafeAttachmentRule.**

- In PowerShell, si crea prima il criterio degli allegati sicuri, quindi si crea la regola degli allegati sicuri che identifica il criterio a cui si applica la regola.
- In PowerShell, le impostazioni nel criterio degli allegati sicuri e nella regola degli allegati sicuri vengono modificate separatamente.
- Quando si rimuove un criterio di allegato sicuro da PowerShell, la regola degli allegati sicuri corrispondente non viene rimossa automaticamente e viceversa.

### <a name="use-powershell-to-create-safe-attachments-policies"></a>Utilizzare PowerShell per creare criteri Cassaforte allegati

La creazione Cassaforte criteri allegati in PowerShell è un processo in due passaggi:

1. Creare il criterio degli allegati sicuri.
2. Creare la regola degli allegati sicuri che specifica il criterio degli allegati sicuri a cui si applica la regola.

 **Note**:

- È possibile creare una nuova regola degli allegati sicuri e assegnarle un criterio di allegato sicuro non associato esistente. Una regola degli allegati sicuri non può essere associata a più criteri allegati sicuri.

- È possibile configurare le impostazioni seguenti nei nuovi criteri allegati sicuri in PowerShell che non sono disponibili nel portale di Microsoft 365 Defender fino a quando non si crea il criterio:
  - Creare il nuovo criterio come disabilitato (_Abilitato_ `$false` nel cmdlet **New-SafeAttachmentRule).**
  - Impostare la priorità del criterio durante la creazione (_Priority_ _\<Number\>_ ) nel cmdlet **New-SafeAttachmentRule.**

- Un nuovo criterio di allegato sicuro creato in PowerShell non è visibile nel portale di Microsoft 365 Defender finché non si assegna il criterio a una regola degli allegati sicuri.

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>Passaggio 1: Usare PowerShell per creare criteri allegati sicuri

Per creare criteri allegati sicuri, utilizzare la sintassi seguente:

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

In questo esempio viene creato un criterio di allegato sicuro denominato Contoso All con i valori seguenti:

- Blocca i messaggi che vengono trovati come contenenti malware Cassaforte'analisi dei documenti (non viene utilizzato il parametro _Action_ e il valore predefinito è `Block` ).
- Il reindirizzamento è abilitato e i messaggi che contengono malware vengono inviati a sec-ops@contoso.com per l'analisi e l'analisi.
- Se Cassaforte'analisi degli allegati non è disponibile o si verificano errori, non recapitare il messaggio (non viene utilizzato il parametro _ActionOnError_ e il valore predefinito è `$true` ).

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-SafeAttachmentPolicy.](/powershell/module/exchange/new-safeattachmentpolicy)

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>Passaggio 2: Usare PowerShell per creare una regola degli allegati sicuri

Per creare una regola degli allegati sicuri, utilizzare la sintassi seguente:

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

In questo esempio viene creata una regola di allegato sicura denominata Contoso All con le condizioni seguenti:

- La regola è associata al criterio degli allegati sicuri denominato Contoso All.
- La regola si applica a tutti i destinatari del contoso.com dominio.
- Poiché non si utilizza il parametro _Priority,_ viene utilizzata la priorità predefinita.
- La regola è abilitata (non viene utilizzato il _parametro Enabled_ e il valore predefinito è `$true` ).

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).

### <a name="use-powershell-to-view-safe-attachment-policies"></a>Usare PowerShell per visualizzare i criteri allegati sicuri

Per visualizzare i criteri allegati sicuri esistenti, utilizzare la sintassi seguente:

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In questo esempio viene restituito un elenco riepilogativo di tutti i criteri allegati sicuri.

```PowerShell
Get-SafeAttachmentPolicy
```

In questo esempio vengono restituite informazioni dettagliate per il criterio degli allegati sicuri denominato Contoso Executives.

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).

### <a name="use-powershell-to-view-safe-attachment-rules"></a>Usare PowerShell per visualizzare le regole degli allegati sicuri

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

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>Utilizzare PowerShell per modificare i criteri allegati sicuri

Non è possibile rinominare un criterio degli allegati sicuri in PowerShell (il cmdlet **Set-SafeAttachmentPolicy** non dispone di _alcun parametro Name)._ Quando si rinomina un criterio Cassaforte allegati nel portale Microsoft 365 Defender, si rinomina solo la regola degli allegati _sicuri._

In caso contrario, le stesse impostazioni sono disponibili quando si crea un criterio degli allegati sicuri come descritto nella sezione Passaggio [1:](#step-1-use-powershell-to-create-a-safe-attachment-policy) utilizzare PowerShell per creare un criterio di allegati sicuri più indietro in questo articolo.

Per modificare un criterio degli allegati sicuri, utilizzare la sintassi seguente:

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>Utilizzare PowerShell per modificare le regole degli allegati sicuri

L'unica impostazione non disponibile quando si modifica una regola degli allegati sicuri in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata. Per abilitare o disabilitare le regole degli allegati sicuri esistenti, vedere la sezione successiva.

In caso contrario, le stesse impostazioni sono disponibili quando si crea una regola come descritto nella sezione Passaggio [2:](#step-2-use-powershell-to-create-a-safe-attachment-rule) Utilizzare PowerShell per creare una regola degli allegati sicuri in precedenza in questo articolo.

Per modificare una regola degli allegati sicuri, utilizzare la sintassi seguente:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>Abilitazione o disabilitazione delle regole degli allegati sicuri tramite PowerShell

L'abilitazione o la disabilitazione di una regola degli allegati sicuri in PowerShell abilita o disabilita l'intero criterio allegati Cassaforte (la regola degli allegati sicuri e il criterio degli allegati sicuri assegnati).

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

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) [e Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a>Utilizzare PowerShell per impostare la priorità delle regole degli allegati sicuri

Il valore di priorità più alto che è possibile impostare in una regola è 0. Il valore più basso che è possibile impostare dipende dal numero di regole. Se si dispone di cinque regole predefinite, è possibile utilizzare i valori di priorità da 0 a 4. Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole. Ad esempio, se si dispone di cinque regole (priorità da 0 a 4) e si modifica la priorità di una regola a 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.

Per impostare la priorità di una regola degli allegati sicuri in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

**Nota:** per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-SafeAttachmentRule.**

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>Usare PowerShell per rimuovere i criteri allegati sicuri

Quando si utilizza PowerShell per rimuovere un criterio di allegato sicuro, la regola degli allegati sicuri corrispondente non viene rimossa.

Per rimuovere un criterio di allegato sicuro in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

In questo esempio viene rimosso il criterio degli allegati sicuri denominato Marketing Department.

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-SafeAttachmentPolicy.](/powershell/module/exchange/remove-safeattachmentpolicy)

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>Usare PowerShell per rimuovere le regole degli allegati sicuri

Quando si utilizza PowerShell per rimuovere una regola degli allegati sicuri, il criterio di allegato sicuro corrispondente non viene rimosso.

Per rimuovere una regola degli allegati sicuri in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

In questo esempio viene rimossa la regola degli allegati sicuri denominata Marketing Department.

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).

## <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare che i criteri allegati siano stati creati, modificati o rimossi correttamente, Cassaforte eseguire una delle operazioni seguenti:

- Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & posta elettronica & criteri di minaccia sezione Criteri \>  \>  \>  di \> **Cassaforte Allegati**. Verificare l'elenco dei criteri, i **relativi valori status** e i relativi valori **Priority.** Per visualizzare altri dettagli, selezionare il criterio dall'elenco facendo clic sul nome e visualizzare i dettagli nel riquadro a comparsa.

- In Exchange Online PowerShell o Exchange Online Protection PowerShell, sostituire con il nome del criterio o della regola, eseguire il comando seguente e \<Name\> verificare le impostazioni:

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

Per verificare che Cassaforte allegati esempa l'analisi dei messaggi, controlla il Defender disponibile per Office 365 report. Per altre informazioni, vedi [Visualizzare i report per Defender per Office 365](view-reports-for-mdo.md) e Usare Esplora risorse nel portale [Microsoft 365 Defender.](threat-explorer.md)
