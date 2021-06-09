---
title: Definire i criteri delle barriere informative
description: Informazioni su come definire i criteri per le barriere in Microsoft Teams.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ce387799a2f9e6d6cdffe063d3adf7310d7e7757
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842723"
---
# <a name="define-information-barrier-policies"></a>Definire i criteri delle barriere informative

Con le barriere alle informazioni, puoi definire criteri progettati per impedire a determinati segmenti di utenti di comunicare tra loro o consentire a segmenti specifici di comunicare solo con determinati altri segmenti. I criteri di barriera delle informazioni possono aiutare l'organizzazione a mantenere la conformità agli standard e alle normative del settore pertinenti ed evitare potenziali conflitti di interesse. Per ulteriori informazioni, vedere [Ostacoli alle informazioni](information-barriers.md).

In questo articolo viene descritto come pianificare, definire, implementare e gestire i criteri di barriera delle informazioni. Sono coinvolti diversi passaggi e il flusso di lavoro è suddiviso in diverse parti. Leggere i prerequisiti [](#prerequisites) e l'intero processo prima di iniziare a definire (o modificare) i criteri di barriera delle informazioni.

> [!TIP]
> Questo articolo include uno [scenario di esempio](#example-contosos-departments-segments-and-policies) e una cartella Excel [cartella](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx) di lavoro scaricabile per facilitare la pianificazione e la definizione dei criteri di barriera delle informazioni.

## <a name="concepts-of-information-barrier-policies"></a>Concetti dei criteri di barriera informativa

Quando si definiscono i criteri per le barriere alle informazioni, si lavora con gli attributi degli account utente, i segmenti, i criteri di "blocco" e/o "consenti" e l'applicazione dei criteri.

- Gli attributi degli account utente sono definiti in Azure Active Directory (o Exchange Online). Questi attributi possono includere reparto, posizione, ubicazione, nome del team e altri dettagli del profilo professionale. 
- I segmenti sono insiemi di utenti definiti nel Centro sicurezza & conformità utilizzando un attributo **account utente selezionato.** Vedere l'[elenco degli attributi supportati](information-barriers-attributes.md).
- I criteri di barriera informativa determinano i limiti o le restrizioni applicate a livello comunicativo. Quando si definiscono i criteri di barriera informativa, è possibile scegliere tra due tipi di criteri:
    - I criteri "Blocca" impediscono a un segmento di comunicare con un altro segmento.
    - I criteri "Consenti" consentono a un segmento di comunicare solo con determinati altri segmenti.
- L'applicazione dei criteri nell'organizzazione viene eseguita dopo aver definito tutti i criteri di barriera informativa.

## <a name="the-work-flow-at-a-glance"></a>Flusso di lavoro in breve

| Fase | Cosa è coinvolto |
|:--------|:------------------|
| [Verificare che i prerequisiti siano soddisfatti](#prerequisites) | - Verificare di disporre delle [licenze e delle autorizzazioni necessarie](information-barriers.md#required-licenses-and-permissions)<br/>- Verificare che la directory includa dati per la segmentazione degli utenti<br/>- Abilitare la ricerca di directory con ambito per Microsoft Teams<br/>- Verificare che la registrazione di controllo sia attivata<br/>- Assicurarsi che non siano Exchange criteri della rubrica<br/>- Usare PowerShell (vengono forniti esempi)<br/>- Fornire il consenso dell'amministratore per Microsoft Teams (sono inclusi i passaggi) |
| [Parte 1: Segmentare gli utenti nell'organizzazione](#part-1-segment-users) | - Determinare quali criteri sono necessari<br/>- Creare un elenco di segmenti da definire<br/>- Identificare gli attributi da utilizzare<br/>- Definire i segmenti in termini di filtri dei criteri |
| [Parte 2: Definire i criteri di barriera delle informazioni](#part-2-define-information-barrier-policies) | - Definire i criteri (non ancora applicati)<br/>- Scegliere tra due tipi (blocca o consenti) |
| [Parte 3: Applicare i criteri di barriera delle informazioni](#part-3-apply-information-barrier-policies) | - Impostare i criteri sullo stato attivo<br/>- Eseguire l'applicazione dei criteri<br/>- Visualizzare lo stato dei criteri |
| (In base alle esigenze) [Modificare un segmento o un criterio](information-barriers-edit-segments-policies.md) | - Modificare un segmento<br/>- Modificare o rimuovere un criterio<br/>- Eseguire di nuovo l'applicazione dei criteri<br/>- Visualizzare lo stato dei criteri |
| (In base alle esigenze) [Risoluzione dei problemi](information-barriers-troubleshooting.md)| - Intervenire quando le cose non funzionano come previsto|

## <a name="prerequisites"></a>Prerequisiti

Oltre alle licenze [e alle](information-barriers.md#required-licenses-and-permissions)autorizzazioni necessarie, verificare che siano soddisfatti i requisiti seguenti:

- Dati della directory: assicurarsi che la struttura dell'organizzazione si rifletta nei dati della directory. Per eseguire questa operazione, assicurarsi che gli attributi dell'account utente, ad esempio l'appartenenza al gruppo, il nome del reparto e così via, siano popolati correttamente in Azure Active Directory (o Exchange Online). Per altre informazioni, vedere le risorse seguenti:
  - [Attributi per i criteri delle barriere informative](information-barriers-attributes.md)
  - [Aggiungere o aggiornare le informazioni del profilo di un utente Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [Configurare le proprietà degli account utente con Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)

- Ricerca directory con ambito: prima di definire i primi criteri di barriera delle informazioni dell'organizzazione, è necessario abilitare la ricerca di directory con ambito [in Microsoft Teams](/MicrosoftTeams/teams-scoped-directory-search). Attendere almeno 24 ore dopo aver abilitato la ricerca nella directory con ambito prima di configurare o definire i criteri di barriera delle informazioni.

- Licenza EXO: i criteri IB funzionano solo se agli utenti di destinazione è stata assegnata una licenza EXO.

- Registrazione di controllo: per cercare lo stato di un'applicazione di criteri, è necessario che la registrazione di controllo sia attivata. Ti consigliamo di abilitare il controllo prima di iniziare a definire segmenti o criteri. Per ulteriori informazioni, vedere [Attivare o disattivare la](turn-audit-log-search-on-or-off.md)ricerca nel log di controllo.

- Nessun criteri della rubrica: prima di definire e applicare i criteri di barriera delle informazioni, assicurarsi Exchange non siano presenti criteri della rubrica. Le barriere informative si basano sui criteri della rubrica, ma i due tipi di criteri non sono compatibili. Se si dispone di tali criteri, assicurarsi di [rimuovere prima i criteri della rubrica.](/exchange/address-books/address-book-policies/remove-an-address-book-policy) Dopo aver abilitato i criteri di barriera delle informazioni e aver abilitato la rubrica gerarchica, tutti gli utenti che non sono inclusi ***in*** un segmento di barriera delle informazioni potranno visualizzare la rubrica gerarchica [in](/exchange/address-books/hierarchical-address-books/hierarchical-address-books) Exchange online.

- PowerShell: attualmente, i criteri di barriera delle informazioni sono definiti e gestiti Office 365 nel Centro sicurezza & tramite i cmdlet di PowerShell. Anche se in questo articolo vengono forniti diversi esempi, è necessario avere familiarità con i cmdlet e i parametri di PowerShell. Sarà inoltre necessario il modulo Azure PowerShell.
    - [Connettersi a PowerShell in Centro sicurezza e conformità](/powershell/exchange/connect-to-scc-powershell)
    - [Installare il modulo Azure PowerShell](/powershell/azure/install-az-ps?view=azps-2.3.2)

- Consenso dell'amministratore per le barriere di informazioni in Microsoft Teams - Quando i criteri IB sono in atto, possono rimuovere gli utenti di conformità non IB dai gruppi (ad esempio, canali di Teams, che si basano su gruppi). Questa configurazione garantisce che l'organizzazione rimanga conforme ai criteri e alle normative. Utilizzare la procedura seguente per consentire ai criteri di barriera delle informazioni di funzionare come previsto in Microsoft Teams.

   1. Prerequisiti: installare Azure PowerShell da [Install Azure PowerShell](/powershell/azure/install-az-ps).

   1. Eseguire i cmdlet di PowerShell seguenti:

      ```powershell
      Connect-AzAccount -Tenant "<yourtenantdomain.com>"  //for example: Connect-AzAccount -Tenant "Contoso.onmicrosoft.com"
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzADServicePrincipal -ServicePrincipalName $appId
      if ($sp -eq $null) { New-AzADServicePrincipal -ApplicationId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   1. Quando richiesto, accedere usando l'account aziendale o dell'istituto di istruzione per Office 365.

   1. Nella finestra **di dialogo** Autorizzazioni richieste esaminare le informazioni e quindi scegliere **Accetta.** Le autorizzazioni richieste dall'app sono fornite di seguito.
      
      > [!div class="mx-imgBorder"]
      > ![image](https://user-images.githubusercontent.com/8932063/107690955-b1772300-6c5f-11eb-9527-4235de860b27.png)


Quando vengono soddisfatti tutti i prerequisiti, passare alla sezione successiva.

> [!TIP]
> Per preparare il piano, in questo articolo è incluso uno scenario di esempio. [Vedere Reparti, segmenti](#example-contosos-departments-segments-and-policies)e criteri di Contoso.<p>Inoltre, è disponibile una cartella Excel cartella di lavoro scaricabile che consente di pianificare e definire i segmenti e i criteri (e creare i cmdlet di PowerShell). [Ottenere la cartella di lavoro](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx).

## <a name="part-1-segment-users"></a>Parte 1: Segmentare gli utenti

Durante questa fase, è possibile determinare quali criteri di barriera delle informazioni sono necessari, creare un elenco di segmenti da definire e quindi definire i segmenti.

### <a name="determine-what-policies-are-needed"></a>Determinare quali criteri sono necessari

Considerando le normative legali e del settore, chi sono i gruppi all'interno dell'organizzazione che avranno bisogno di criteri di barriera delle informazioni? Creare un elenco. Vi sono gruppi a cui non è consentito comunicare con un altro gruppo? Esistono gruppi a cui dovrebbe essere consentito comunicare solo con uno o due altri gruppi? È necessario pensare ai criteri necessari come appartenenti a uno dei due gruppi seguenti:

- I criteri "Blocca" impediscono a un gruppo di comunicare con un altro gruppo.
- I criteri "Consenti" consentono a un gruppo di comunicare solo con determinati altri gruppi specifici.

Dopo aver creato l'elenco iniziale di gruppi e criteri, procedere con l'identificazione dei segmenti necessari.

### <a name="identify-segments"></a>Identificare i segmenti

Oltre all'elenco iniziale dei criteri, creare un elenco di segmenti per l'organizzazione. Gli utenti che verranno inclusi nei criteri di barriera delle informazioni devono appartenere a un segmento. Pianificare attentamente i segmenti in quanto un utente può essere in un solo segmento. A ogni segmento può essere applicato un solo criterio di barriera delle informazioni.

> [!IMPORTANT]
> Un utente può essere in un solo segmento.

Determinare gli attributi nei dati della directory dell'organizzazione che verranno utilizzati per definire i segmenti. È possibile utilizzare *Department*, *MemberOf* o uno degli attributi supportati. Assicurati di avere valori nell'attributo selezionato per gli utenti. [Per informazioni sulle barriere, vedere](information-barriers-attributes.md)l'elenco degli attributi supportati.

> [!IMPORTANT]
> **Prima di passare alla sezione successiva, verificare** che i dati della directory siano associati a valori per gli attributi che è possibile utilizzare per definire i segmenti. Se i dati della directory non dispongono di valori per gli attributi che si desidera utilizzare, gli account utente devono essere aggiornati per includere queste informazioni prima di procedere con le barriere di informazioni. Per ottenere assistenza, vedere le risorse seguenti:<br/>- [Configurare le proprietà dell'account utente con Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)<br/>- [Aggiungere o aggiornare le informazioni del profilo di un utente Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>Definire i segmenti tramite PowerShell

La definizione dei segmenti non influisce sugli utenti. imposta semplicemente la fase per definire e quindi applicare i criteri di barriera delle informazioni.

1. Utilizzare il cmdlet **New-OrganizationSegment** con il **parametro UserGroupFilter** corrispondente all'attributo [](information-barriers-attributes.md) che si desidera utilizzare.

    | Sintassi | Esempio |
    |:---------|:----------|
    | `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"` |`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>In questo esempio, un segmento denominato *HR* viene definito utilizzando *HR*, un valore nell'attributo *Department.* La **parte -eq** del cmdlet fa riferimento a "uguale a". In alternativa, è possibile utilizzare **-ne** per indicare "non uguale a". Vedere [Utilizzo di "uguale" e "non uguale a" nelle definizioni di segmento.](#using-equals-and-not-equals-in-segment-definitions) |

    Dopo aver eseguito ogni cmdlet, dovrebbe essere visualizzato un elenco di dettagli sul nuovo segmento. I dettagli includono il tipo del segmento, l'utente che lo ha creato o modificato per l'ultima volta e così via. 

2. Ripeti questo processo per ogni segmento che vuoi definire.

    > [!IMPORTANT]
    > **Assicurati che i segmenti non si sovrappongano.** Ogni utente che sarà interessato da barriere di informazione deve appartenere a un segmento (e a un solo segmento). Nessun utente deve appartenere a due o più segmenti. (Vedere [Esempio: Segmenti](#contosos-defined-segments) definiti da Contoso in questo articolo).

Dopo aver definito i segmenti, procedere con la definizione [dei criteri di barriera delle informazioni.](#part-2-define-information-barrier-policies)

### <a name="using-equals-and-not-equals-in-segment-definitions"></a>Utilizzo di "uguale" e "non uguale a" nelle definizioni di segmento

Nell'esempio seguente viene definito un segmento in modo che "Department equals HR". 

| Esempio | Nota |
|:----------|:-------|
|`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` | Si noti che in questo esempio la definizione del segmento include un parametro "uguale a" denotato **come -eq**. |

È inoltre possibile definire i segmenti utilizzando un parametro "diverso da uguale a", indicato come **-ne**, come illustrato nella tabella seguente:

| Sintassi | Esempio |
|:---------|:----------|
| `New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"` | In questo esempio è stato definito un segmento denominato *NotSales* che include tutti gli utenti non inclusi in *Sales.* La **parte -ne** del cmdlet fa riferimento a "diverso da". |

Oltre a definire i segmenti usando i parametri "uguale a" o "non uguale a", puoi definire un segmento utilizzando entrambi i parametri "uguale a" e "non uguale a". È inoltre possibile definire filtri di gruppo complessi utilizzando operatori *logici AND* *e OR.*

| Sintassi | Esempio |
|:---------|:----------|
| `New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" -and "Position -ne 'Temporary'"` | In questo esempio è stato definito un segmento denominato *LocalFTE* che include le persone che si trovano in locale e le cui posizioni non sono elencate come *Temporanee*. |
| `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "MemberOf -eq 'group1@contoso.com'' -and MemberOf -ne 'group3@contoso.com'"`| In questo esempio è stato definito un segmento denominato *Segment1* che include persone che sono membri di group1@contoso.com e non membri di group3@contoso.com. |
| `New-OrganizationSegment -Name "Segment2" -UserGroupFilter "MemberOf -eq 'group2@contoso.com' -or MemberOf -ne 'group3@contoso.com'"` | In questo esempio è stato definito un segmento denominato *Segment2* che include persone che sono membri di group2@contoso.com e non membri di group3@contoso.com. |
| `New-OrganizationSegment -Name "Segment1and2" -UserGroupFilter "(MemberOf -eq 'group1@contoso.com' -or MemberOf -eq 'group2@contoso.com') -and MemberOf -ne 'group3@contoso.com'"`| In questo esempio è stato definito un segmento denominato *Segment1and2* che include i membri di group1@contoso.com e group2@contoso.com e non i membri di group3@contoso.com. |

> [!TIP]
> Se possibile, usa le definizioni di segmento che includono "-eq" o "-ne". Cerca di non definire definizioni di segmento complesse.

## <a name="part-2-define-information-barrier-policies"></a>Parte 2: Definire i criteri di barriera delle informazioni

Determinare se è necessario impedire le comunicazioni tra determinati segmenti o limitare le comunicazioni a determinati segmenti. Idealmente, si utilizzerà il numero minimo di criteri per garantire che l'organizzazione sia conforme ai requisiti legali e del settore.

Con l'elenco dei segmenti di utenti e i criteri di barriera delle informazioni che vuoi definire, seleziona uno scenario e quindi segui i passaggi.

- [Scenario 1: bloccare le comunicazioni tra segmenti.](#scenario-1-block-communications-between-segments)
- [Scenario 2: consentire a un segmento di comunicare solo con un altro segmento.](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> **Durante la definizione dei criteri,** non assegnare più di un criterio a un segmento . Ad esempio, se si definisce un criterio per un segmento denominato *Sales*, non definire un criterio aggiuntivo per *Sales*.<p> Inoltre, quando si definiscono i criteri di barriera delle informazioni, assicurarsi di impostare tali criteri sullo stato inattivo fino a quando non si è pronti ad applicarli. La definizione (o la modifica) dei criteri non influisce sugli utenti finché tali criteri non vengono impostati sullo stato attivo e quindi applicati.

(Vedere [Esempio: Criteri di barriera](#contosos-information-barrier-policies) delle informazioni di Contoso in questo articolo).

### <a name="scenario-1-block-communications-between-segments"></a>Scenario 1: bloccare le comunicazioni tra segmenti.

Quando vuoi impedire ai segmenti di comunicare tra loro, definisci due criteri: uno per ogni direzione. Ogni criterio blocca le comunicazioni in modo unidirezionale.

Si supponga, ad esempio, di voler bloccare le comunicazioni tra il segmento A e il segmento B. In questo caso, definisci un criterio che impedisce al Segmento A di comunicare con il segmento B e quindi definisci un secondo criterio per impedire la comunicazione del segmento B con il segmento A.

1. Per definire il primo criterio di blocco, utilizzare il cmdlet **New-InformationBarrierPolicy** con il **parametro SegmentsBlocked.**

    | Sintassi | Esempio |
    |:--------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"` | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> In questo esempio è stato definito un criterio denominato *Sales-Research* per un segmento denominato *Sales*. Se attivo e applicato, questo criterio impedisce agli utenti di *Sales* di comunicare con persone in un segmento denominato *Ricerca*. |

2. Per definire il secondo segmento di blocco, utilizzare di nuovo il cmdlet **New-InformationBarrierPolicy** con il parametro **SegmentsBlocked,** questa volta con i segmenti invertito.

    | Esempio | Nota |
    |:----------|:-------|
    |`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` | In questo esempio è stato definito un criterio denominato *Research-Sales* per impedire a *Research* di comunicare con *Sales.* |

3. Procedere con una delle azioni seguenti:

   - (Se necessario) [Definire un criterio per consentire a un segmento di comunicare solo con un altro segmento](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) 
   - (Dopo aver definito tutti i criteri) [Applicare criteri di barriera delle informazioni](#part-3-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>Scenario 2: consentire a un segmento di comunicare solo con un altro segmento.

1. Per consentire a un segmento di comunicare con un solo altro segmento, utilizzare il cmdlet **New-InformationBarrierPolicy** con il **parametro SegmentsAllowed.**

    | Sintassi | Esempio |
    |:----------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name","segment1name"` | `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Manufacturing" -State Inactive` <p> In questo esempio è stato definito un criterio denominato *Manufacturing-HR* per un segmento denominato *Manufacturing*. Se attivo e applicato, questo criterio consente agli utenti di *Manufacturing* di comunicare solo con persone in un segmento denominato *HR.* In questo caso, *Manufacturing non* può comunicare con gli utenti che non fanno parte delle *risorse umane.* |

    **Se necessario, è possibile specificare più segmenti con questo cmdlet, come illustrato nell'esempio seguente.**

    | Sintassi | Esempio |
    |:---------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name","segment1name"` | `New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing","Research" -State Inactive` <p> In questo esempio è stato definito un criterio che consente al segmento *Research* di comunicare solo con *HR* e *Manufacturing.* |

    Ripetere questo passaggio per ogni criterio che si desidera definire per consentire a segmenti specifici di comunicare solo con determinati altri segmenti specifici.

2. Procedere con una delle azioni seguenti:

   - (Se necessario) [Definire un criterio per bloccare le comunicazioni tra segmenti](#scenario-1-block-communications-between-segments) 
   - (Dopo aver definito tutti i criteri) [Applicare criteri di barriera delle informazioni](#part-3-apply-information-barrier-policies)

## <a name="part-3-apply-information-barrier-policies"></a>Parte 3: Applicare i criteri di barriera delle informazioni

I criteri di barriera delle informazioni non sono attivi finché non li si imposta sullo stato attivo e quindi si applicano i criteri.

1. Utilizzare il cmdlet **Get-InformationBarrierPolicy** per visualizzare un elenco dei criteri definiti. Prendere nota dello stato e dell'identità (GUID) di ogni criterio.

    Sintassi: `Get-InformationBarrierPolicy`

2. Per impostare un criterio sullo stato attivo, utilizzare il cmdlet **Set-InformationBarrierPolicy** con un parametro **Identity** e il parametro **State** impostato su **Active.** 

    | Sintassi | Esempio |
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Active` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active` <p> In questo esempio viene impostato un criterio di barriera delle informazioni con GUID *43c37853-ea10-4b90-a23d-ab8c93772471* sullo stato attivo. |

    Ripetere questo passaggio come appropriato per ogni criterio.

3. Al termine dell'impostazione dei criteri di protezione delle informazioni sullo stato attivo, utilizzare il cmdlet **Start-InformationBarrierPoliciesApplication** nel Centro sicurezza & conformità.

    Sintassi: `Start-InformationBarrierPoliciesApplication`

    Dopo l'esecuzione, consentire al sistema di avviare l'applicazione dei criteri per `Start-InformationBarrierPoliciesApplication` 30 minuti. Il sistema applica criteri utente per utente. Il sistema elabora circa 5.000 account utente all'ora.

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>Visualizzare lo stato di account utente, segmenti, criteri o applicazione di criteri

Con PowerShell, è possibile visualizzare lo stato di account utente, segmenti, criteri e applicazione di criteri, come indicato nella tabella seguente.

| Per visualizzare queste informazioni | Eseguire questa azione |
|:---------------|:----------|
| Account utente | Utilizzare il cmdlet **Get-InformationBarrierRecipientStatus** con i parametri Identity. <p> Sintassi: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> È possibile utilizzare qualsiasi valore che identifichi ogni utente in modo univoco, ad esempio nome, alias, nome distinto, nome di dominio canonico, indirizzo di posta elettronica o GUID. <p> Esempio: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> In questo esempio si fa riferimento a due account utente in Office 365: *meganb* per *Megan* e *alexw* per *Alex*. <p> È inoltre possibile utilizzare questo cmdlet per un singolo `Get-InformationBarrierRecipientStatus -Identity <value>` utente: <p> Questo cmdlet restituisce informazioni sugli utenti, ad esempio i valori degli attributi e gli eventuali criteri di barriera delle informazioni applicati.|
| Segmenti | Utilizzare il cmdlet **Get-OrganizationSegment.**<p> Sintassi: `Get-OrganizationSegment` <p> Questo cmdlet visualizza un elenco di tutti i segmenti definiti per l'organizzazione. |
| Criteri di barriera informativa | Utilizzare il cmdlet **Get-InformationBarrierPolicy.** <p> Sintassi: `Get-InformationBarrierPolicy` <p> Questo cmdlet visualizza un elenco dei criteri di barriera delle informazioni definiti e il relativo stato. |
| L'applicazione più recente dei criteri di barriera delle informazioni | Utilizzare il cmdlet **Get-InformationBarrierPoliciesApplicationStatus.** <p> Sintassi: `Get-InformationBarrierPoliciesApplicationStatus`<p> Questo cmdlet visualizza informazioni sul completamento, l'esito negativo o l'esecuzione dell'applicazione dei criteri. |
| Tutte le applicazioni dei criteri di barriera delle informazioni|Usare `Get-InformationBarrierPoliciesApplicationStatus -All`<p> Questo cmdlet visualizza informazioni sul completamento, l'esito negativo o l'esecuzione dell'applicazione dei criteri.|

<!-- IN the " The most recent information barrier policy application, add link to troubleshooting topic -->

## <a name="what-if-i-need-to-remove-or-change-policies"></a>Cosa succede se è necessario rimuovere o modificare i criteri?

Sono disponibili risorse che consentono di gestire i criteri di barriera delle informazioni.

- Se si verifica un problema con le barriere alle informazioni, vedere [Risoluzione dei problemi relativi alle barriere delle informazioni.](information-barriers-troubleshooting.md)
- Per interrompere l'applicazione dei criteri, vedere [Stop a policy application](information-barriers-edit-segments-policies.md#stop-a-policy-application).
- Per rimuovere un criterio di barriera delle informazioni, [vedere Remove a policy](information-barriers-edit-segments-policies.md#remove-a-policy).
- Per apportare modifiche a segmenti o criteri, vedere [Modificare (o rimuovere) i criteri di barriera delle informazioni.](information-barriers-edit-segments-policies.md)

## <a name="example-contosos-departments-segments-and-policies"></a>Esempio: reparti, segmenti e criteri di Contoso

Per esempi sull'approccio di un'organizzazione alla definizione di segmenti e criteri, si prenda in considerazione l'esempio riportato di seguito.

### <a name="contosos-departments-and-plan"></a>Reparti e piano di Contoso

In Contoso sono presenti cinque reparti: Risorse umane, Vendite, Marketing, Ricerca e Produzione. Per rimanere conformi alle normative del settore, gli utenti di alcuni reparti non devono comunicare con altri reparti, come indicato nella tabella seguente:

| Segmento | Può comunicare con | Non può comunicare con |
|:----------|:--------------|:-----------------|
| Risorse umane | Tutti | (nessuna limitazione) |
| Vendite | HR, Marketing, Manufacturing | Ricerca |
| Marketing | Tutti | (nessuna limitazione) |
| Ricerca | HR, Marketing, Manufacturing | Vendite |
| Produzione | HR, Marketing | Chiunque diverso da HR o Marketing |

Per questa struttura, il piano di Contoso include tre criteri di barriera delle informazioni:

1. Un criterio progettato per impedire a Sales di comunicare con Research (e un altro criterio per impedire a Research di comunicare con Sales).

2. Criteri progettati per consentire a Manufacturing di comunicare solo con hr e marketing.

Per questo scenario, non è necessario definire criteri per HR o Marketing.

### <a name="contosos-defined-segments"></a>Segmenti definiti di Contoso

Contoso utilizzerà l'attributo Department in Azure Active Directory per definire i segmenti, come indicato di seguito:

| Reparto | Segment Definition |
|:-------------|:---------------------|
| Risorse umane | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` |
| Vendite | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"` |
| Marketing | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"` |
| Ricerca | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"` |
| Produzione | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"` |

Dopo avere definito i segmenti, Contoso procede con la definizione dei criteri.

### <a name="contosos-information-barrier-policies"></a>Criteri Barriere informative di Contoso

Contoso definisce tre criteri, come descritto nella tabella seguente:

| Criterio | Definizione criterio |
|:---------|:--------------------|
| **Il criterio 1 impedisce al segmento Vendite di comunicare con il segmento Ricerca** | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> Nell'esempio riportato il criterio Barriera informativa si chiama *Vendite-Ricerca*. Quando il criterio è attivo e applicato, impedisce agli utenti del segmento Vendite di comunicare con gli utenti del segmento Ricerca. Questo criterio è un criterio unidiredire due. non impedirà a Research di comunicare con Sales. A tale proposito è necessario il criterio 2. |
| **Il criterio 2 impedisce al segmento Ricerca di comunicare con il segmento Vendite** | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> Nell'esempio riportato il criterio Barriera informativa si chiama *Ricerca-Vendite*. Quando il criterio è attivo e applicato, impedisce agli utenti del segmento Ricerca di comunicare con gli utenti del segmento Vendite. |
| **Criterio 3: consentire alla produzione di comunicare solo con hr e marketing** | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing","Manufacturing" -State Inactive` <p> In questo caso, il criterio Barriera informativa si chiama *Produzione-Risorse umane-Marketing*. Quando il criterio è attivo e applicato, la Produzione può comunicare solo con i segmenti Risorse umane e Marketing. Le risorse umane e il marketing non sono limitati a comunicare con altri segmenti. |

Con i segmenti e i criteri definiti, Contoso applica i criteri eseguendo il cmdlet **Start-InformationBarrierPoliciesApplication.**

Al termine del cmdlet, Contoso è conforme ai requisiti legali e del settore.

## <a name="resources"></a>Risorse

- [Ottenere una panoramica delle barriere in fatto di informazioni](information-barriers.md)
- [Ulteriori informazioni sulle barriere di informazione in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Ulteriori informazioni sulle barriere di informazioni in SharePoint Online](/sharepoint/information-barriers)
- [Altre informazioni sulle barriere di informazione in OneDrive](/onedrive/information-barriers)