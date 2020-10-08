---
title: Definire i criteri delle barriere informative
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
description: Informazioni su come definire i criteri per le barriere informative in Microsoft teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f7e1fbb0f1d468f8e1b79f9cc414fdb87a224283
ms.sourcegitcommit: 5e40c760c1af2a4cc6d85cb782b17f5c979677c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2020
ms.locfileid: "48379183"
---
# <a name="define-information-barrier-policies"></a>Definire i criteri delle barriere informative

Con barriere informative, è possibile definire criteri che sono stati creati per impedire a determinati segmenti di utenti di comunicare tra loro oppure consentire a segmenti specifici di comunicare solo con determinati altri segmenti. I criteri barriera alle informazioni consentono all'organizzazione di mantenere la conformità agli standard e ai regolamenti del settore e di evitare potenziali conflitti di interesse. Per ulteriori informazioni, vedere [barriere informative](information-barriers.md). 

In questo articolo viene descritto come pianificare, definire, implementare e gestire i criteri di barriera delle informazioni. Sono coinvolti diversi passaggi e il flusso di lavoro è suddiviso in più parti. Assicurarsi di leggere i [prerequisiti](#prerequisites) e l'intero processo prima di iniziare a definire (o modificare) i criteri di barriera delle informazioni.

> [!TIP]
> In questo articolo è incluso uno [scenario di esempio](#example-contosos-departments-segments-and-policies) e una cartella di [lavoro di Excel scaricabile](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx) che consente di pianificare e definire i criteri di barriera delle informazioni.

## <a name="concepts-of-information-barrier-policies"></a>Concetti relativi ai criteri di barriera delle informazioni

Quando si definiscono i criteri per gli ostacoli alle informazioni, è possibile utilizzare gli attributi degli account utente, i segmenti, i criteri "blocca" e/o "Consenti" e l'applicazione di criteri.

- Gli attributi degli account utente sono definiti in Azure Active Directory (o Exchange Online). Questi attributi possono includere reparto, titolo del processo, posizione, nome del team e altre informazioni sul profilo dei processi. 

- I segmenti sono insiemi di utenti definiti nel centro sicurezza & conformità utilizzando un **attributo account utente**selezionato. (Vedere l' [elenco degli attributi supportati](information-barriers-attributes.md)). 

- I criteri barriera di informazioni determinano limiti di comunicazione o restrizioni. Quando si definiscono i criteri di barriera delle informazioni, è possibile scegliere tra due tipi di criteri:
    - I criteri "blocca" impediscono a un segmento di comunicare con un altro segmento.
    - I criteri "Consenti" consentono a un segmento di comunicare con solo alcuni segmenti.

- L'applicazione criterio viene completata dopo la definizione di tutti i criteri di barriera delle informazioni e si è pronti per applicarli all'interno dell'organizzazione.

## <a name="the-work-flow-at-a-glance"></a>Flusso di lavoro in breve

|Fase    |Cosa è coinvolto  |
|---------|---------|
|[Verificare che i prerequisiti siano soddisfatti](#prerequisites)     |-Verificare di disporre delle [licenze e delle autorizzazioni necessarie](information-barriers.md#required-licenses-and-permissions)<br/>-Verificare che la directory includa dati per segmentare gli utenti<br/>-Abilitare la ricerca di directory con ambito per Microsoft Teams<br/>-Verificare che la registrazione di controllo sia attivata<br/>-Verificare che non siano presenti criteri Rubrica di Exchange<br/>-Utilizzare PowerShell (vengono forniti esempi)<br/>-Fornire il consenso dell'amministratore per Microsoft Teams (sono inclusi i passaggi)          |
|[Parte 1: segmentare gli utenti nell'organizzazione](#part-1-segment-users)     |-Determinare quali criteri sono necessari<br/>-Creare un elenco di segmenti da definire<br/>-Identificare gli attributi da utilizzare<br/>-Definire i segmenti in termini di filtri per i criteri        |
|[Parte 2: definire i criteri di barriera delle informazioni](#part-2-define-information-barrier-policies)     |-Definire i criteri (non è ancora applicabile)<br/>-Scegliere tra due tipi (blocca o Consenti) |
|[Parte 3: applicare i criteri di barriera delle informazioni](#part-3-apply-information-barrier-policies)     |-Impostare i criteri per lo stato attivo<br/>-Eseguire l'applicazione per i criteri<br/>-Visualizzare lo stato dei criteri         |
|(Se necessario) [Modificare un segmento o un criterio](information-barriers-edit-segments-policies.md)    |-Modificare un segmento<br/>-Modificare o rimuovere un criterio<br/>-Rieseguire l'applicazione del criterio<br/>-Visualizzare lo stato dei criteri         |
|(Se necessario) [Risoluzione dei problemi](information-barriers-troubleshooting.md)|-Intervenire quando le cose non funzionano come previsto|

## <a name="prerequisites"></a>Prerequisiti

Oltre alle [licenze e le autorizzazioni necessarie](information-barriers.md#required-licenses-and-permissions), verificare che siano soddisfatti i requisiti seguenti: 
     
- Dati della directory: verificare che la struttura dell'organizzazione sia riflessa nei dati della directory. Per eseguire questa operazione, verificare che gli attributi degli account utente, ad esempio appartenenza a gruppo, nome reparto e così via, siano inseriti correttamente in Azure Active Directory (o Exchange Online). Per altre informazioni, vedere le risorse seguenti:
  - [Attributi per i criteri delle barriere informative](information-barriers-attributes.md)
  - [Aggiungere o aggiornare le informazioni del profilo di un utente tramite Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [Configurare le proprietà degli account utente con Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)

- Ricerca nell'ambito della directory-prima di definire il primo criterio barriera informativo dell'organizzazione, è necessario [abilitare la ricerca nell'ambito della directory in Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search). Attendere almeno 24 ore dopo aver abilitato la ricerca nell'ambito della directory prima di impostare o definire i criteri di barriera delle informazioni.

- Registrazione di controllo: per cercare lo stato di un'applicazione di criteri, è necessario che la registrazione di controllo sia attivata. Si consiglia di eseguire questa operazione prima di iniziare a definire segmenti o criteri. Per ulteriori informazioni, vedere [abilitare o disabilitare la ricerca del registro di controllo](turn-audit-log-search-on-or-off.md).

- Nessun criterio rubrica-prima di definire e applicare i criteri di barriera delle informazioni, assicurarsi che non siano presenti criteri Rubrica di Exchange. Le barriere informative si basano sui criteri della Rubrica, ma i due tipi di criteri non sono compatibili. Se si dispone di tali criteri, assicurarsi che [i criteri della Rubrica siano rimossi](https://docs.microsoft.com/exchange/address-books/address-book-policies/remove-an-address-book-policy) per primi. Dopo aver abilitato i criteri barriera informativi e aver abilitato la rubrica gerarchica, tutti gli utenti ***che non sono inclusi*** in un segmento barriera informazioni vedranno la [rubrica gerarchica](https://docs.microsoft.com/exchange/address-books/hierarchical-address-books/hierarchical-address-books) in Exchange Online.

- PowerShell-attualmente, i criteri di barriera delle informazioni vengono definiti e gestiti nel centro sicurezza & conformità di Office 365 tramite i cmdlet di PowerShell. Anche se alcuni esempi sono disponibili in questo articolo, è necessario avere familiarità con i cmdlet e i parametri di PowerShell. Sarà inoltre necessario il modulo di Azure PowerShell.
    - [Connettersi a PowerShell in Centro sicurezza e conformità](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)
    - [Installare il modulo di Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-2.3.2)

- Consenso dell'amministratore per le barriere informative in Microsoft teams-quando i criteri sono sul posto, gli ostacoli alle informazioni possono rimuovere persone dalle sessioni di chat di cui non si suppone che si trovino. Questo contribuisce a garantire che l'organizzazione rimanga conforme ai criteri e alle normative. Utilizzare la procedura seguente per consentire ai criteri di barriera delle informazioni di funzionare come previsto in Microsoft teams. 

   1. Eseguire i cmdlet di PowerShell seguenti:

      ```powershell
      Connect-AzureAD 
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzADServicePrincipal -ServicePrincipalName $appId
      if ($sp -eq $null) { New-AzADServicePrincipal -ApplicationId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   2. Quando richiesto, accedere con l'account aziendale o dell'Istituto di istruzione per Office 365.

   3. Nella finestra di dialogo **autorizzazioni richieste** esaminare le informazioni e quindi scegliere **accetta**.

Quando vengono soddisfatti tutti i prerequisiti, passare alla sezione successiva.

> [!TIP]
> Per preparare il piano, è incluso uno scenario di esempio in questo articolo. [Vedere Departments, Segments, and policies di Contoso](#example-contosos-departments-segments-and-policies).<p>Inoltre, è disponibile una cartella di lavoro di Excel scaricabile che consente di pianificare e definire i segmenti e i criteri (e creare i cmdlet di PowerShell). [Ottenere la cartella di lavoro](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx). 

## <a name="part-1-segment-users"></a>Parte 1: segmentare gli utenti

Durante questa fase, è possibile determinare quali criteri di barriera informativi sono necessari, creare un elenco di segmenti da definire e quindi definire i segmenti.

### <a name="determine-what-policies-are-needed"></a>Determinare quali criteri sono necessari

Considerando le normative legali e industriali, quali sono i gruppi all'interno dell'organizzazione che avranno bisogno di criteri barriera informativi? Creare un elenco. Esistono gruppi a cui è necessario impedire la comunicazione con un altro gruppo? Esistono gruppi che devono essere autorizzati a comunicare solo con uno o due altri gruppi? Si pensi ai criteri necessari come appartenenti a uno dei due gruppi:
- I criteri "blocca" impediscono a un gruppo di comunicare con un altro gruppo.
- I criteri "Consenti" consentono a un gruppo di comunicare con solo alcuni gruppi specifici.

Quando si ha un elenco iniziale di gruppi e criteri, procedere all'identificazione dei segmenti necessari. 

### <a name="identify-segments"></a>Identificare i segmenti

Oltre all'elenco iniziale dei criteri, creare un elenco di segmenti per l'organizzazione. Gli utenti che saranno inclusi nei criteri di barriera delle informazioni devono appartenere a un segmento. Pianificare attentamente i segmenti come un utente può essere in un solo segmento. Ogni segmento può disporre di un solo criterio barriera informativo applicato.

> [!IMPORTANT]
> Un utente può trovarsi in un solo segmento.

Determinare gli attributi dei dati di directory dell'organizzazione che verranno utilizzati per definire i segmenti. È possibile utilizzare *Department*, *member*o uno qualsiasi degli attributi supportati. Assicurarsi di avere valori nell'attributo selezionato per gli utenti. [Vedere l'elenco degli attributi supportati per le barriere informative](information-barriers-attributes.md).

> [!IMPORTANT]
> **Prima di procedere alla sezione successiva, verificare che i dati della directory dispongano di valori per gli attributi che è possibile utilizzare per definire i segmenti**. Se i dati della directory non contengono valori per gli attributi che si desidera utilizzare, gli account utente devono essere aggiornati per includere tali informazioni prima di procedere con le barriere informative. Per ottenere assistenza, vedere le risorse seguenti:<br/>- [Configurare le proprietà degli account utente con Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)<br/>- [Aggiungere o aggiornare le informazioni del profilo di un utente tramite Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>Definire segmenti tramite PowerShell

La definizione di segmenti non influisce sugli utenti. imposta solo la fase per i criteri di barriera delle informazioni da definire e quindi applicare.

1. Utilizzare il cmdlet **New-OrganizationSegment** con il parametro **UserGroupFilter** che corrisponde all' [attributo](information-barriers-attributes.md) che si desidera utilizzare.

    |Sintassi   |Esempio  |
    |---------|---------|
    |`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"`     |`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>In questo esempio, un segmento denominato *HR* è definito utilizzando *HR*, un valore nell'attributo *Department* . La parte **-EQ** del cmdlet si riferisce a "uguale a". (In alternativa, è possibile utilizzare **-ne** per indicare "non uguale a". Vedere [utilizzo di "Equals" e "not equals" nelle definizioni di segmento](#using-equals-and-not-equals-in-segment-definitions).        |

    Dopo aver eseguito ogni cmdlet, verrà visualizzato un elenco di dettagli sul nuovo segmento. I dettagli includono il tipo di segmento, che ha creato o modificato l'ultima volta e così via. 

2. Ripetere questa procedura per ogni segmento che si desidera definire.

    > [!IMPORTANT]
    > Verificare **che i segmenti non si sovrappongano**. Ogni utente che sarà influenzato dalle barriere informative dovrebbe appartenere a un solo segmento. Nessun utente deve appartenere a due o più segmenti. Vedere l' [esempio: segmenti definiti da Contoso](#contosos-defined-segments) in questo articolo.


Dopo aver definito i segmenti, procedere alla [definizione dei criteri barriera informativi](#part-2-define-information-barrier-policies).

### <a name="using-equals-and-not-equals-in-segment-definitions"></a>Utilizzo di "Equals" e "not equals" nelle definizioni di segmento

Nell'esempio seguente viene definito un segmento in modo che "Department sia uguale a HR". 

|Esempio  |
|---------|
|`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>Si noti che in questo esempio, la definizione del segmento include un parametro "Equals" indicato come **-EQ**. 
  |

È inoltre possibile definire segmenti utilizzando un parametro "not equals", indicato come **-ne**, come illustrato nella tabella seguente:

|Sintassi  |Esempio  |
|---------|---------|
|`New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"`   | <p>In questo esempio, è stato definito un segmento denominato *NotSales* che include tutti coloro che non sono nelle *vendite*. La parte **-ne** del cmdlet si riferisce a "non uguale a".  |

Oltre alla definizione di segmenti che utilizzano "Equals" o "not equals", è possibile definire un segmento utilizzando i parametri "Equals" e "not equals". È inoltre possibile definire filtri di gruppo complessi utilizzando operatori logici *e* and *or* .


|Sintassi    |Esempio  |
|---------|---------|
|`New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" -and "Position -ne 'Temporary'"` |<p>In questo esempio, è stato definito un segmento denominato *LocalFTE* che include persone situate localmente e le cui posizioni non sono elencate come *temporanee*.    |
 |`New-OrganizationSegment -Name "Segment1" -UserGroupFilter "MemberOf -eq 'group1@contoso.com'' -and MemberOf -ne 'group3@contoso.com'"`|  <p>In questo esempio, è stato definito un segmento denominato *segment1* che include persone che sono membri di group1@contoso.com e non membri di Group3@contoso.com.
|`New-OrganizationSegment -Name "Segment2" -UserGroupFilter "MemberOf -eq 'group2@contoso.com' -or MemberOf -ne 'group3@contoso.com'"` | In questo esempio, è stato definito un segmento denominato *segment2* che include persone che sono membri di group2@contoso.com e non membri di Group3@contoso.com.
|`New-OrganizationSegment -Name "Segment1and2" -UserGroupFilter "(MemberOf -eq 'group1@contoso.com' -or MemberOf -eq 'group2@contoso.com') -and MemberOf -ne 'group3@contoso.com'"`|  In questo esempio, è stato definito un segmento denominato *Segment1and2* che include membri di group1@contoso.com e group2@contoso.com e non membri di Group3@contoso.com.


> [!TIP]
> Se possibile, utilizzare definizioni di segmenti che includono "-EQ" o "-ne". Provare a non definire definizioni di segmenti complessi.

## <a name="part-2-define-information-barrier-policies"></a>Parte 2: definire i criteri di barriera delle informazioni

Determinare se è necessario impedire la comunicazione tra determinati segmenti o limitare le comunicazioni a determinati segmenti. In teoria, è possibile utilizzare il numero minimo di criteri per garantire che l'organizzazione sia conforme ai requisiti legali e di settore.

Con l'elenco dei segmenti di utenti e dei criteri barriera informativi che si desidera definire, selezionare uno scenario e quindi eseguire la procedura seguente. 

- [Scenario 1: bloccare le comunicazioni tra segmenti](#scenario-1-block-communications-between-segments)
- [Scenario 2: consentire a un segmento di comunicare solo con un altro segmento](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> Assicurarsi **che durante la definizione dei criteri non venga assegnato più di un criterio a un segmento**. Ad esempio, se si definisce un criterio per un segmento denominato *Sales*, non definire un criterio aggiuntivo per le *vendite*.<p>Inoltre, quando si definiscono i criteri di barriera delle informazioni, assicurarsi di impostare tali criteri sullo stato inattivo fino a quando non si è pronti per applicarli. La definizione o la modifica dei criteri non influiscono sugli utenti finché tali criteri non sono impostati sullo stato attivo e quindi applicati.

Vedere l' [esempio: criteri di protezione delle informazioni di Contoso](#contosos-information-barrier-policies) in questo articolo.

### <a name="scenario-1-block-communications-between-segments"></a>Scenario 1: bloccare le comunicazioni tra segmenti

Se si desidera bloccare i segmenti dalla comunicazione tra loro, è possibile definire due criteri: uno per ogni direzione. Ogni criterio blocca la comunicazione solo in un modo.

Ad esempio, si supponga di voler bloccare le comunicazioni tra il segmento A e il segmento B. In questo caso, è possibile definire un criterio che impedisca al segmento A di comunicare con il segmento B e quindi definire un secondo criterio per impedire che il segmento B comunichi con il segmento A.

1. Per definire il primo criterio di blocco, utilizzare il cmdlet **New-InformationBarrierPolicy** con il parametro **SegmentsBlocked** . 

    |Sintassi  |Esempio  |
    |---------|---------|
    |`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"`     |`New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p>    In questo esempio, è stato definito un criterio denominato *Sales-Research* per un segmento denominato *Sales*. Se attivo e applicato, questo criterio impedisce alle persone in *vendita* di comunicare con gli utenti di un segmento denominato *Research*.         |

2. Per definire il secondo segmento di blocco, utilizzare di nuovo il cmdlet **New-InformationBarrierPolicy** con il parametro **SegmentsBlocked** , stavolta con i segmenti invertiti.

    |Esempio  |
    |---------|
    |`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p>    In questo esempio, è stato definito un criterio denominato *Research-Sales* per impedire che la *ricerca* comunichi con le *vendite*.     |

2. Procedere con una delle operazioni seguenti:

   - (Se necessario) [Definire un criterio per consentire a un segmento di comunicare solo con un altro segmento](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) 
   - (Dopo che sono stati definiti tutti i criteri) [Applicare i criteri di barriera delle informazioni](#part-3-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>Scenario 2: consentire a un segmento di comunicare solo con un altro segmento

1. Per consentire a un segmento di comunicare solo con un altro segmento, utilizzare il cmdlet **New-InformationBarrierPolicy** con il parametro **SegmentsAllowed** . 

    |Sintassi  |Esempio  |
    |---------|---------|
    |`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name","segment1name"`     |`New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Manufacturing" -State Inactive` <p>    In questo esempio, è stato definito un criterio denominato *Manufacturing-HR* per un segmento denominato *Manufacturing*. Se attivo e applicato, questo criterio consente alle persone nella *produzione* di comunicare solo con le persone in un segmento denominato *HR*. In questo caso, la *produzione* non è in grado di comunicare con gli utenti che non fanno parte di *HR*.         |

    **Se necessario, è possibile specificare più segmenti con questo cmdlet, come illustrato nell'esempio seguente.**

    |Sintassi  |Esempio  |
    |---------|---------|
    |`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name","segment1name"`     |`New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing","Research" -State Inactive` <p>In questo esempio, è stato definito un criterio che consente al segmento di *ricerca* di comunicare solo con le *risorse umane* e la *produzione*.        |

    Ripetere questo passaggio per ogni criterio che si desidera definire per consentire a segmenti specifici di comunicare con solo alcuni segmenti specifici.

2. Procedere con una delle operazioni seguenti:

   - (Se necessario) [Definire un criterio per bloccare le comunicazioni tra i segmenti](#scenario-1-block-communications-between-segments) 
   - (Dopo che sono stati definiti tutti i criteri) [Applicare i criteri di barriera delle informazioni](#part-3-apply-information-barrier-policies)

## <a name="part-3-apply-information-barrier-policies"></a>Parte 3: applicare i criteri di barriera delle informazioni

I criteri di barriera delle informazioni non sono attivi finché non vengono impostati allo stato attivo e quindi vengono applicati i criteri.

1. Utilizzare il cmdlet **Get-InformationBarrierPolicy** per visualizzare un elenco di criteri definiti. Tenere presente lo stato e l'identità (GUID) di ogni criterio.

    Sintassi `Get-InformationBarrierPolicy`

2. Per impostare un criterio su stato attivo, utilizzare il cmdlet **set-InformationBarrierPolicy** con un parametro **Identity** e il parametro **state** impostato su **attivo**. 

    |Sintassi  |Esempio  |
    |---------|---------|
    |`Set-InformationBarrierPolicy -Identity GUID -State Active`     |`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active` <p>    In questo esempio, viene impostato un criterio barriera informativo che include il GUID *43c37853-EA10-4b90-a23d-ab8c93772471* per lo stato attivo.   |

    Ripetere questo passaggio come appropriato per ogni criterio.

3. Al termine dell'impostazione dei criteri di barriera delle informazioni sullo stato attivo, utilizzare il cmdlet **Start-InformationBarrierPoliciesApplication** nel centro sicurezza & Compliance.

    Sintassi `Start-InformationBarrierPoliciesApplication`

    Dopo aver eseguito `Start-InformationBarrierPoliciesApplication` Consenti 30 minuti affinché il sistema inizi a applicare i criteri. Il sistema applica i criteri utente all'utente. In generale, il sistema elabora circa 5.000 account utente all'ora.

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>Visualizzazione dello stato degli account utente, segmenti, criteri o applicazione di criteri

Con PowerShell, è possibile visualizzare lo stato degli account utente, i segmenti, i criteri e l'applicazione di criteri, come indicato nella tabella seguente.

|Per visualizzare questo  |Eseguire l'operazione seguente  |
|---------|---------|
|Account utente     |Utilizzare il cmdlet **Get-InformationBarrierRecipientStatus** con i parametri Identity. <p>Sintassi `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>È possibile utilizzare qualsiasi valore che identifichi in modo univoco ogni utente, ad esempio nome, alias, nome distinto, nome di dominio canonico, indirizzo di posta elettronica o GUID. <p>Esempio: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>In questo esempio, si fa riferimento a due account utente in Office 365: *meganb* per *Megan*e *alexw* per *Alex*. <p>È inoltre possibile utilizzare questo cmdlet per un singolo `Get-InformationBarrierRecipientStatus -Identity <value>` utente: <p>Questo cmdlet restituisce informazioni sugli utenti, ad esempio i valori degli attributi e tutti i criteri di barriera delle informazioni applicati.|
|Segmenti     |Utilizzare il cmdlet **Get-OrganizationSegment** .<p>Sintassi `Get-OrganizationSegment` <p>In questo modo verrà visualizzato un elenco di tutti i segmenti definiti per l'organizzazione.         |
|Criteri barriera di informazioni     |Utilizzare il cmdlet **Get-InformationBarrierPolicy** . <p> Sintassi `Get-InformationBarrierPolicy` <p>In questo modo verrà visualizzato un elenco di criteri barriera informativi definiti e il relativo stato.       |
|Applicazione dei criteri barriera informativa più recente     | Utilizzare il cmdlet **Get-InformationBarrierPoliciesApplicationStatus** . <p>Sintassi `Get-InformationBarrierPoliciesApplicationStatus`<p>    Verranno visualizzate informazioni sul modo in cui l'applicazione del criterio è stata completata, non è riuscita o è in corso.       |
|Tutte le applicazioni dei criteri barriera di informazioni|Usare `Get-InformationBarrierPoliciesApplicationStatus -All $true`<p>Verranno visualizzate informazioni sul modo in cui l'applicazione del criterio è stata completata, non è riuscita o è in corso.|

<!-- IN the " The most recent information barrier policy application, add link to troubleshooting topic -->

## <a name="what-if-i-need-to-remove-or-change-policies"></a>Cosa succede se è necessario rimuovere o modificare I criteri?

Sono disponibili risorse che consentono di gestire i criteri di barriera delle informazioni.

- Se si verifica un problema con gli ostacoli alle informazioni, vedere [Troubleshooting Information barriers](information-barriers-troubleshooting.md).

- Per arrestare l'applicazione dei criteri, vedere [arrestare un'istanza di criteri](information-barriers-edit-segments-policies.md#stop-a-policy-application).

- Per rimuovere un criterio di barriera delle informazioni, vedere [rimuovere un criterio](information-barriers-edit-segments-policies.md#remove-a-policy).

- Per apportare modifiche ai segmenti o ai criteri, vedere [modificare (o rimuovere) i criteri di barriera delle informazioni](information-barriers-edit-segments-policies.md).

## <a name="example-contosos-departments-segments-and-policies"></a>Esempio: reparti, segmenti e criteri di contoso

Per sapere in che modo un'organizzazione può approcciare la definizione di segmenti e criteri, prendere in considerazione l'esempio seguente.

### <a name="contosos-departments-and-plan"></a>Piani e reparti di contoso

Contoso dispone di cinque reparti: HR, Sales, marketing, Research e Manufacturing. Per rimanere conformi alle normative industriali, gli utenti di alcuni reparti non sono tenuti a comunicare con altri reparti, come indicato nella tabella seguente:

|Segmento  |Può parlare con  |Non è possibile parlare con  |
|---------|---------|---------|
|HR     |Tutti         |(nessuna restrizione)         |
|Sales     |HR, marketing, Manufacturing         |Ricerca         |
|Marketing     |Tutti         |(nessuna restrizione)         |
|Ricerca     |HR, marketing, Manufacturing        |Sales     |
|Produzione |HR, marketing |Altre persone che non siano HR o marketing |

In questo caso, il piano di Contoso include tre criteri di barriera delle informazioni:

1. Criteri che impediscono alla vendita di comunicare con la ricerca (e un altro criterio per impedire alla ricerca di comunicare con le vendite)
2. Un criterio destinato a consentire la produzione per la comunicazione solo con HR e marketing 

Non è necessario definire i criteri per HR o marketing.

### <a name="contosos-defined-segments"></a>Segmenti definiti di contoso

Contoso utilizzerà l'attributo Department in Azure Active Directory per definire i segmenti, come indicato di seguito:

|Reparto  |Definizione di segmento  |
|---------|---------|
|HR     | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`        |
|Sales     | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"`        |
|Marketing     | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"`        |
|Ricerca     | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"`        |
|Produzione     | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"`        |

Con i segmenti definiti, contoso procede alla definizione dei criteri. 

### <a name="contosos-information-barrier-policies"></a>Criteri di barriera delle informazioni di contoso

Contoso definisce tre criteri di polizia, come descritto nella tabella seguente:

|Criteri  |Definizione criterio  |
|---------|---------|
|Criterio 1: impedire la comunicazione delle vendite con la ricerca     | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> In questo esempio, il criterio barriera informativo è denominato *Sales-Research*. Quando questo criterio è attivo e applicato, consente di impedire agli utenti che si trovano nel segmento Sales di comunicare con gli utenti nel segmento di ricerca. Si tratta di un criterio unidirezionale. non impedirà alla ricerca di comunicare con le vendite. Per questo, è necessario il criterio 2.      |
|Criterio 2: impedire alla ricerca di comunicare con le vendite     | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> In questo esempio, il criterio barriera informativo è denominato *Research-Sales*. Quando questo criterio è attivo e applicato, consente di impedire agli utenti che si trovano nel segmento di ricerca di comunicare con gli utenti nel segmento Sales.       |
|Criterio 3: Consenti alla produzione di comunicare solo con HR e marketing     | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing","Manufacturing" -State Inactive` <p>In questo caso, il criterio barriera informativo è denominato *Manufacturing-HRMarketing*. Quando questo criterio è attivo e applicato, la produzione può comunicare solo con HR e marketing. Si noti che HR e marketing non sono limitati dalla comunicazione con altri segmenti. |

Con i segmenti e i criteri definiti, contoso applica i criteri eseguendo il cmdlet **Start-InformationBarrierPoliciesApplication** . 

Al termine, Contoso è conforme ai requisiti legali e di settore.

## <a name="related-articles"></a>Articoli correlati

- [Ottenere una panoramica delle barriere informative](information-barriers.md)

- [Barriere informative in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
