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
description: Gli amministratori possono imparare a creare, modificare ed eliminare i criteri anti-phishing disponibili nelle organizzazioni di Exchange Online Protection (EOP) con o senza Exchange Online cassette postali.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2aaeb10eaa3c06e721df3cf7a00658482e6ffc0c
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029922"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>Configurare i criteri anti-phishing in Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)

Nelle organizzazioni Microsoft 365 con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, esiste un criterio anti-phishing predefinito che contiene un numero limitato di funzionalità anti-spoofing abilitate per impostazione predefinita. Per altre informazioni, vedere [Impostazioni di spoofing nei criteri anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).

Gli amministratori possono visualizzare, modificare e configurare (ma non eliminare) il criterio anti-phishing predefinito. Per una maggiore granularità, è inoltre possibile creare criteri anti-phishing personalizzati che si applicano a utenti, gruppi o domini specifici nell'organizzazione. I criteri personalizzati hanno sempre la precedenza sul criterio predefinito, ma non è possibile modificarne la priorità (in funzione).

Le organizzazioni con Exchange Online cassette postali possono configurare i criteri anti-phishing nel portale di Microsoft 365 Defender o in Exchange Online PowerShell. Le organizzazioni EOP autonome possono utilizzare solo il Microsoft 365 Defender portale.

Per informazioni sulla creazione e la modifica dei criteri anti-phishing più avanzati disponibili in Microsoft Defender per Office 365, vedere [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md).

Gli elementi di base di un criterio anti-phishing sono:

- **Il criterio anti-phishing**: Specifica le protezioni anti-phishing da abilitare o disabilitare e le azioni da applicare.
- **La regola anti-phish**: Specifica la priorità e i filtri destinatario (a chi si applica il criterio) per un criterio anti-phish.

La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri anti-phishing nel portale Microsoft 365 Defender:

- Quando crei un criterio anti-phishing, stai creando una regola anti-phishing e il criterio anti-phishing associato contemporaneamente usando lo stesso nome per entrambi.
- Quando si modifica un criterio anti-phishing, le impostazioni relative al nome, alla priorità, abilitate o disabilitate e ai filtri destinatari modificano la regola anti-phishing. Tutte le altre impostazioni modificano il criterio anti-phish associato.
- Quando si rimuove un criterio anti-phishing, la regola anti-phishing e il criterio anti-phishing associato vengono rimossi.

In Exchange Online PowerShell, il criterio e la regola vengono gestiti separatamente. Per ulteriori informazioni, vedere la sezione [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) più avanti in questo articolo.

Ogni organizzazione dispone di un criterio anti-phishing predefinito denominato Office365 AntiPhish Default con queste proprietà:

- Il criterio viene applicato a tutti i destinatari dell'organizzazione, anche se al criterio non è associata alcuna regola anti-phish (filtri destinatari).
- Il valore personalizzato della priorità del criterio è **Minore** e non può essere modificato (il criterio viene sempre applicato per ultimo). Qualsiasi criterio personalizzato creato avrà sempre una priorità più alta.
- Il criterio è quello predefinito (la proprietà **IsDefault** contiene il valore `True`), e non è possibile eliminarlo.

Per aumentare l'efficacia della protezione anti-phishing, è possibile creare criteri anti-phishing personalizzati con impostazioni più rigorose applicate a utenti o gruppi di utenti specifici.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Per aprire il portale di Microsoft 365 Defender, andare alla pagina <https://security.microsoft.com>. Per passare direttamente alla pagina **Anti-phishing,** utilizzare <https://security.microsoft.com/antiphishing> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

  Non è possibile gestire i criteri anti-phishing in PowerShell EOP autonomo.

- Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in **Exchange Online**:
  - Per aggiungere, modificare ed eliminare criteri anti-phishing, è necessario essere membri dei gruppi **di** ruoli Gestione organizzazione o Amministratore **sicurezza.**
  - Per l'accesso in sola lettura ai criteri anti-phishing, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.

  Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Note**:

  - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).
  - Il **gruppo di ruoli Gestione organizzazione** di sola visualizzazione in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) consente inoltre l'accesso in sola lettura alla funzionalità <sup>\*</sup> .

- Per le impostazioni consigliate per i criteri anti-phishing, vedere [Impostazioni dei criteri anti-phishing EOP.](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)

- Consentire fino a 30 minuti per l'applicazione del criterio aggiornato.

- Per informazioni su dove vengono applicati i criteri anti-phishing nella pipeline di filtro, vedere [Order and precedence of email protection.](how-policies-and-protections-are-combined.md)

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a>Utilizzare il portale Microsoft 365 Defender per creare criteri anti-phishing

La creazione di un criterio anti-phishing personalizzato nel portale di Microsoft 365 Defender crea la regola anti-phishing e il criterio anti-phishing associato contemporaneamente utilizzando lo stesso nome per entrambi.

1. Nel portale Microsoft 365 Defender, passare a Criteri di **collaborazione** & e-mail & regole Criteri di minaccia \>  \>  \>  sezione \> **Anti-phishing**.

2. Nella pagina **Anti-phishing** fare clic su ![ Crea icona ](../../media/m365-cc-sc-create-icon.png) **Crea**.

3. Viene aperta la creazione guidata criteri. Nella pagina **Nome criterio** configurare queste impostazioni:
   - **Nome**: immettere un nome univoco descrittivo per il criterio.
   - **Descrizione**: immettere una descrizione opzionale per il criterio.

   Al termine dell'operazione, fare clic su **Avanti**.

4. Nella pagina **Utenti, gruppi e domini** visualizzata identificare i destinatari interni a cui si applicano i criteri (condizioni del destinatario):
   - **Utenti**: la cassette postali specificate, utenti di posta o contatti di posta specificati nell'organizzazione.
   - **Gruppi**: i gruppi di distribuzione specificati, gruppi di sicurezza abilitati alla posta elettronica o gruppi di Microsoft 365 nell'organizzazione.
   - **Domini**: tutti i destinatari nei domini specificati [accettati](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) nell'organizzazione.

   Fare clic nella casella appropriata, iniziare a digitare un valore e selezionare il valore desiderato nei risultati. Ripetere questa procedura tutte le volte necessarie. Per rimuovere un valore esistente, fare clic su Rimuovi ![Icona Rimuovi](../../media/m365-cc-sc-remove-selection-icon.png) accanto al valore.

   Per utenti o gruppi è possibile usare la maggior parte degli identificatori, ad esempio nome, nome visualizzato, alias, indirizzo di posta elettronica, nome dell'account e così via, ma il nome visualizzato corrispondente viene visualizzato nei risultati. Per gli utenti, immettere un asterisco (\*) da solo per visualizzare tutti i valori disponibili.

   Più valori della stessa condizione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_). Condizioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).

   - **Escludere questi utenti, gruppi e domini**: per aggiungere eccezioni per i destinatari interni a cui si applicano i criteri (eccezione destinatari), selezionare questa opzione e configurare le eccezioni. Impostazioni e comportamento sono equivalenti alle condizioni.

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nella pagina **Soglia di &** phishing visualizzata, utilizzare la casella di controllo Abilita spoof **intelligence** per attivare o disattivare l'intelligence di spoofing. Il valore predefinito è on (selezionato) e ti consigliamo di lasciarlo. È possibile configurare l'azione da eseguire sui messaggi falsificati bloccati nella pagina successiva.

   Per disattivare lo spoof intelligence, deselezionare la casella di controllo.

   > [!NOTE]
   > Non è necessario disattivare la protezione anti-spoofing se il record MX non punta a Microsoft 365; si abilita invece il filtro avanzato per i connettori. Per istruzioni, vedere [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   Al termine dell'operazione, fare clic su **Avanti**.

6. Nella pagina **Azioni** visualizzata configurare le impostazioni seguenti:
   - **Se il messaggio viene rilevato come spoof:** questa impostazione è disponibile solo se è stato selezionato **Abilita spoof intelligence** nella pagina precedente. Selezionare una delle azioni seguenti nell'elenco a discesa per i messaggi provenienti da mittenti falsificati bloccati:
     - **Spostare il messaggio nelle cartelle posta indesiderata dei destinatari**
     - **Mettere in quarantena il messaggio**

   - **Suggerimenti per &** indicatori di sicurezza : questa impostazione è disponibile solo se è stata selezionata l'opzione **Abilita spoof intelligence** nella pagina precedente:
     - **Show (?) for unauthenticated senders for spoof**: Aggiunge un punto interrogativo alla foto del mittente nella casella Da  di Outlook se il messaggio non supera i controlli SPF o DKIM e il messaggio non supera DMARC o l'autenticazione [composita.](email-validation-and-authentication.md#composite-authentication)
     - **Mostra tag "via":** aggiunge un tag via (chris@contoso.com tramite fabrikam.com) all'indirizzo mittente se è diverso dal dominio nella firma DKIM o nell'indirizzo **MAIL FROM.**

     Per attivare un'impostazione, selezionare la casella di controllo. Per disattivarla, deselezionare la casella di controllo.

   Al termine dell'operazione, fare clic su **Avanti**.

7. Nella pagina **Controllo** visualizzata controllare le impostazioni. È possibile selezionare **Modifica** in ogni sezione per modificare le impostazioni all'interno della sezione. Oppure è possibile fare clic su **Indietro** o selezionare la pagina specifica della procedura guidata.

   Al termine, fare clic su **Invia.**

8. Nel messaggio di conferma visualizzato fare clic su **Fatto**.

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a>Utilizzare il portale Microsoft 365 Defender per visualizzare i criteri anti-phishing

1. Nel portale Microsoft 365 Defender, passare a Criteri di **collaborazione** & e-mail & regole Criteri di minaccia \>  \>  \>  sezione \> **Anti-phishing**.

2. Nella pagina **Anti-phishing** vengono visualizzate le proprietà seguenti nell'elenco dei criteri anti-phishing:

   - **Nome**
   - **Stato**
   - **Priorità**
   - **Data ultima modifica**

3. Quando si seleziona un criterio facendo clic sul nome, le impostazioni dei criteri vengono visualizzate in un riquadro a comparsa.

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a>Utilizzare il portale Microsoft 365 Defender per modificare i criteri anti-phishing

1. Nel portale Microsoft 365 Defender, passare a Criteri di **collaborazione** & e-mail & regole Criteri di minaccia \>  \>  \>  sezione \> **Anti-phishing**.

2. Nella pagina **Anti-phishing** selezionare un criterio dall'elenco facendo clic sul nome.

3. Nel riquadro a comparsa dei dettagli sui criteri visualizzato selezionare **Modifica** in ogni sezione per modificare le impostazioni all'interno della sezione. Per ulteriori informazioni sulle impostazioni, vedere la sezione Usare il portale di Microsoft 365 Defender per creare criteri [anti-phishing](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) più indietro in questo articolo.  

   Per il criterio anti-phishing predefinito, la sezione **Utenti,** gruppi e domini non è disponibile (il criterio si applica a tutti) e non è possibile rinominare il criterio.

Per abilitare o disabilitare un criterio o impostare l'ordine di priorità dei criteri, vedere le sezioni seguenti.

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>Abilitare o disabilitare i criteri anti-phishing personalizzati

Non è possibile disabilitare il criterio anti-phishing predefinito.

1. Nel portale Microsoft 365 Defender, passare a Criteri di **collaborazione** & e-mail & regole Criteri di minaccia \>  \>  \>  sezione \> **Anti-phishing**.

2. Nella pagina **Anti-phishing** selezionare un criterio personalizzato nell'elenco facendo clic sul nome.

3. Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato è presente uno dei valori seguenti:
   - **Criterio disattivato**: per attivare il criterio, fare clic su ![Attiva icona](../../media/m365-cc-sc-turn-on-off-icon.png) **Attiva** .
   - **Criterio attivato**: per disattivare il criterio, fare clic su ![Disattiva icona](../../media/m365-cc-sc-turn-on-off-icon.png) **Disattiva**.

4. Nella finestra di dialogo di conferma visualizzata fare clic su **Attiva** o **Disattiva**.

5. Fare clic su **Chiudi** nel riquadro a comparsa dei dettagli del criterio.

Tornare alla pagina dei criteri principale, il valore **Stato** del criterio sarà **Attivato** o **Disattivato**.

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>Impostare la priorità dei criteri anti-phishing personalizzati

Per impostazione predefinita, ai criteri anti-phishing viene data una priorità basata sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità più bassa rispetto ai criteri precedenti). Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa). Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.

Per modificare la priorità di un criterio, fare clic su **Aumenta priorità** o **Riduci priorità** nelle proprietà del criterio. Non è possibile modificare direttamente il valore **Priorità** nel portale di Microsoft 365 Defender. La modifica di priorità di un criterio è utile solo se si hanno più criteri.

 **Note**:

- Nel portale Microsoft 365 Defender, è possibile modificare la priorità del criterio anti-phishing solo dopo aver creato il criterio. In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola anti-phish (che può influire sulla priorità delle regole esistenti).
- I criteri anti-phishing vengono elaborati nell'ordine in cui vengono visualizzati (il primo criterio ha il **valore Priority** 0). Il criterio anti-phishing predefinito ha il valore di priorità **Lowest** e non è possibile modificarlo.

1. Nel portale Microsoft 365 Defender, passare a Criteri di **collaborazione** & e-mail & regole Criteri di minaccia \>  \>  \>  sezione \> **Anti-phishing**.

2. Nella pagina **Anti-phishing** selezionare un criterio personalizzato nell'elenco facendo clic sul nome.

3. Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato viene visualizzato **Aumenta priorità** o **Riduci priorità** in base al valore di priorità corrente e al numero di criteri personalizzati:
   - Per il criterio con **valore Priority** **0 è** disponibile solo **l'opzione Riduci** priorità.
   - Il criterio con il valore **Di priorità** più basso (ad esempio, **3)** ha solo l'opzione **Aumenta** priorità disponibile.
   - Se si dispone di tre o più criteri, per i  criteri tra i valori di priorità più alta e più bassa sono disponibili le opzioni Aumenta priorità e **Riduci** priorità.

   Fare clic![ sull’icona Aumenta priorità](../../media/m365-cc-sc-increase-icon.png) **Aumenta priorità** o ![sull’icona Riduci priorità](../../media/m365-cc-sc-decrease-icon.png) **Riduci priorità** per modificare il valore **Priorità**.

4. Al termine, fare clic su **Chiudi** nel riquadro a comparsa dei dettagli del criterio.

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a>Utilizzare il portale Microsoft 365 Defender per rimuovere criteri anti-phishing personalizzati

Quando si utilizza il portale Microsoft 365 Defender per rimuovere un criterio anti-phishing personalizzato, la regola anti-phishing e il criterio anti-phishing corrispondente vengono eliminati entrambi. Non è possibile rimuovere il criterio anti-phishing predefinito.

1. Nel portale Microsoft 365 Defender, passare a Criteri di **collaborazione** & e-mail & regole Criteri di minaccia \>  \>  \>  sezione \> **Anti-phishing**.

2. Selezionare un criterio personalizzato dall'elenco facendo clic sul nome del criterio. Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato fare clic![ sull'icona Altre azioni](../../media/m365-cc-sc-more-actions-icon.png) **Altre azioni** \> ![Icona Elimina criterio](../../media/m365-cc-sc-delete-icon.png) **Elimina criterio**.

3. Nella finestra di dialogo di conferma che viene visualizzata fare clic su **Sì**.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>Utilizzare Exchange Online PowerShell per configurare i criteri anti-phishing

Come descritto in precedenza, un criterio anti-phishing è costituito da un criterio anti-phishing e da una regola anti-phishing.

In Exchange Online PowerShell, è evidente la differenza tra i criteri anti-phish e le regole anti-phish. È possibile gestire i criteri anti-phish utilizzando i cmdlet **\* -AntiPhishPolicy** e gestire le regole anti-phish utilizzando i cmdlet **\* -AntiPhishRule.**

- In PowerShell, si crea prima il criterio anti-phish, quindi si crea la regola anti-phish che identifica il criterio a cui si applica la regola.
- In PowerShell, le impostazioni dei criteri anti-phish e della regola anti-phish vengono modificate separatamente.
- Quando si rimuove un criterio anti-phish da PowerShell, la regola anti-phish corrispondente non viene rimossa automaticamente e viceversa.

> [!NOTE]
> Le procedure di PowerShell seguenti non sono disponibili nelle organizzazioni EOP autonome che usano Exchange Online Protection PowerShell.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>Utilizzare PowerShell per creare criteri anti-phishing

La creazione di un criterio anti-phishing in PowerShell è un processo in due passaggi:

1. Creare i criteri anti-phish.
2. Creare la regola anti-phish che specifica il criterio anti-phish a cui si applica la regola.

 **Note**:

- È possibile creare una nuova regola anti-phish e assegnarle un criterio anti-phish esistente e non associazione. Una regola anti-phish non può essere associata a più di un criterio anti-phish.

- È possibile configurare le impostazioni seguenti nei nuovi criteri anti-phish in PowerShell che non sono disponibili nel portale di Microsoft 365 Defender fino a quando non si crea il criterio:

  - Creare il nuovo criterio come disabilitato (_Abilitato_ `$false` nel cmdlet **New-AntiPhishRule).**
  - Impostare la priorità del criterio durante la creazione (_Priority_ _\<Number\>_ ) nel cmdlet **New-AntiPhishRule.**

- Un nuovo criterio anti-phish creato in PowerShell non è visibile nel portale di Microsoft 365 Defender finché non si assegna il criterio a una regola anti-phish.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Passaggio 1: Usare PowerShell per creare un criterio anti-phish

Per creare un criterio anti-phish, utilizzare la sintassi seguente:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>] [-EnableViaTag <$true | $false>]
```

In questo esempio viene creato un criterio anti-phish denominato Research Quarantine con le impostazioni seguenti:

- La descrizione è: Criteri del reparto di ricerca.
- Modifica l'azione predefinita per lo spoofing in Quarantena.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Passaggio 2: Usare PowerShell per creare una regola anti-phish

Per creare una regola anti-phish, utilizzare la sintassi seguente:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In questo esempio viene creata una regola anti-phish denominata Research Department con le condizioni seguenti:

- La regola è associata al criterio anti-phish denominato Quarantena ricerche.
- La regola viene applicata ai membri del gruppo denominato Research Department.
- Poiché non si utilizza il parametro _Priority,_ viene utilizzata la priorità predefinita.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).

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

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).

### <a name="use-powershell-to-view-anti-phish-rules"></a>Usare PowerShell per visualizzare le regole anti-phish

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

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).

### <a name="use-powershell-to-modify-anti-phish-policies"></a>Utilizzare PowerShell per modificare i criteri anti-phish

Oltre agli elementi seguenti, le stesse impostazioni sono disponibili quando si modifica un criterio anti-phish in PowerShell come quando si crea un criterio come descritto in [Passaggio 1: Utilizzare PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) per creare un criterio anti-phish più indietro in questo articolo.

- L'opzione _MakeDefault_ che trasforma il criterio specificato nel  criterio predefinito (applicato a tutti, sempre con priorità minima e non è possibile eliminarlo) è disponibile solo quando si modifica un criterio anti-phish in PowerShell.
- Non è possibile rinominare un criterio anti-phish (il cmdlet **Set-AntiPhishPolicy** non dispone di _alcun parametro Name)._ Quando si rinomina un criterio anti-phishing nel portale Microsoft 365 Defender, si rinomina solo la regola _anti-phishing._

Per modificare un criterio anti-phish, utilizzare la sintassi seguente:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AntiPhishPolicy.](/powershell/module/exchange/Set-AntiPhishPolicy)

### <a name="use-powershell-to-modify-anti-phish-rules"></a>Utilizzare PowerShell per modificare le regole anti-phish

L'unica impostazione non disponibile quando si modifica una regola anti-phish in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata. Per abilitare o disabilitare le regole anti-phish esistenti, vedi la sezione successiva.

In caso contrario, le stesse impostazioni sono disponibili quando si crea una regola come descritto nella sezione Passaggio 2: utilizzare PowerShell per creare una regola [anti-phish](#step-2-use-powershell-to-create-an-anti-phish-rule) in precedenza in questo articolo.

Per modificare una regola anti-phish, utilizzare la sintassi seguente:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AntiPhishRule.](/powershell/module/exchange/set-antiphishrule)

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>Usare PowerShell per abilitare o disabilitare le regole anti-phish

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

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) e [Disable-AntiPhishRule.](/powershell/module/exchange/disable-antiphishrule)

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>Usare PowerShell per impostare la priorità delle regole anti-phish

Il valore di priorità più alto che è possibile impostare in una regola è 0. Il valore più basso che è possibile impostare dipende dal numero di regole. Se si dispone di cinque regole predefinite, è possibile utilizzare i valori di priorità da 0 a 4. Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole. Ad esempio, se si dispone di cinque regole (priorità da 0 a 4) e si modifica la priorità di una regola a 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.

Per impostare la priorità di una regola anti-phish in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**Note**:

- Per impostare la priorità di una nuova regola al momento della creazione, utilizzare invece il parametro _Priority_ nel cmdlet **New-AntiPhishRule.**
- Il criterio anti-phish predefinito non dispone di una regola anti-phish corrispondente e ha sempre il valore di priorità non modificabile **Lowest**.

### <a name="use-powershell-to-remove-anti-phish-policies"></a>Usare PowerShell per rimuovere i criteri anti-phish

Quando si utilizza PowerShell per rimuovere un criterio anti-phish, la regola anti-phish corrispondente non viene rimossa.

Per rimuovere un criterio anti-phish in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

In questo esempio viene rimosso il criterio anti-phish denominato Marketing Department.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-AntiPhishPolicy.](/powershell/module/exchange/Remove-AntiPhishPolicy)

### <a name="use-powershell-to-remove-anti-phish-rules"></a>Usare PowerShell per rimuovere le regole anti-phish

Quando si utilizza PowerShell per rimuovere una regola anti-phish, il criterio anti-phish corrispondente non viene rimosso.

Per rimuovere una regola anti-phish in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

In questo esempio viene rimossa la regola anti-phish denominata Marketing Department.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-AntiPhishRule.](/powershell/module/exchange/Remove-AntiPhishRule)

## <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare la corretta configurazione dei criteri anti-phishing in EOP, eseguire una delle operazioni seguenti:

- Nel portale Microsoft 365 Defender, passare a Criteri di **collaborazione** & e-mail & regole Criteri di minaccia \>  \>  \>  sezione \> **Anti-phishing**. Verificare l'elenco dei criteri, i **relativi valori status** e i relativi valori **Priority.** Per visualizzare altri dettagli, selezionare il criterio dall'elenco facendo clic sul nome e visualizzando i dettagli nel riquadro a comparsa visualizzato.

- In Exchange Online PowerShell, sostituire con il nome del criterio o della regola, eseguire il \<Name\> comando seguente e verificare le impostazioni:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
