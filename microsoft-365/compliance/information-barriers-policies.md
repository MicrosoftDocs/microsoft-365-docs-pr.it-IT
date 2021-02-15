---
title: Definire i criteri delle barriere informative
description: Informazioni su come definire i criteri per le barriere di informazioni in Microsoft Teams.
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
ms.openlocfilehash: 09e680d2bcf8f1e0fd5237adbf640349741c26fd
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126585"
---
# <a name="define-information-barrier-policies"></a>Definire i criteri delle barriere informative

Con le barriere in fatto di informazioni, è possibile definire criteri progettati per impedire a determinati segmenti di utenti di comunicare tra loro o consentire a segmenti specifici di comunicare solo con determinati altri segmenti. I criteri delle barriere di informazioni possono aiutare l'organizzazione a mantenere la conformità agli standard e alle normative del settore pertinenti ed evitare potenziali conflitti di interesse. Per ulteriori informazioni, vedere [Barriere di informazioni.](information-barriers.md)

Questo articolo descrive come pianificare, definire, implementare e gestire i criteri delle barriere di informazioni. Sono coinvolti diversi passaggi e il flusso di lavoro è suddiviso in diverse parti. Assicurarsi di leggere i prerequisiti [e](#prerequisites) l'intero processo prima di iniziare a definire (o modificare) i criteri delle barriere di informazioni.

> [!TIP]
> Questo articolo include uno [scenario di esempio e](#example-contosos-departments-segments-and-policies) una cartella di lavoro di Excel [scaricabile](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx) che consente di pianificare e definire i criteri delle barriere di informazioni.

## <a name="concepts-of-information-barrier-policies"></a>Concetti relativi ai criteri delle barriere in termini di informazioni

Quando si definiscono i criteri per le barriere in fatto di informazioni, si lavora con gli attributi degli account utente, i segmenti, i criteri "blocca" e/o "consenti" e l'applicazione dei criteri.

- Gli attributi dell'account utente sono definiti in Azure Active Directory (o Exchange Online). Questi attributi possono includere reparto, posizione, posizione, nome del team e altri dettagli del profilo di lavoro. 
- I segmenti sono insiemi di utenti definiti nel Centro sicurezza & conformità utilizzando un attributo **dell'account utente selezionato.** Vedi [l'elenco degli attributi supportati.](information-barriers-attributes.md)
- I criteri delle barriere di informazioni determinano limiti o restrizioni di comunicazione. Quando si definiscono i criteri delle barriere di informazioni, è possibile scegliere tra due tipi di criteri:
    - I criteri "Blocca" impediscono a un segmento di comunicare con un altro segmento.
    - I criteri "Consenti" consentono a un segmento di comunicare solo con determinati altri segmenti.
- L'applicazione dei criteri viene eseguita dopo aver definito tutti i criteri delle barriere di informazioni e sei pronto per applicarli nell'organizzazione.

## <a name="the-work-flow-at-a-glance"></a>Flusso di lavoro in breve

|**Fase**|**Cosa è coinvolto**|
|:--------|:------------------|
| [Verificare che i prerequisiti siano soddisfatti](#prerequisites) | - Verificare di disporre delle [licenze e delle autorizzazioni necessarie](information-barriers.md#required-licenses-and-permissions)<br/>- Verificare che la directory includa dati per la segmentazione degli utenti<br/>- Abilitare la ricerca nella directory con ambito per Microsoft Teams<br/>- Verificare che la registrazione di controllo sia attivata<br/>- Assicurarsi che non siano presenti criteri della rubrica di Exchange<br/>- Usare PowerShell (sono disponibili esempi)<br/>- Fornire il consenso dell'amministratore per Microsoft Teams (sono inclusi i passaggi) |
| [Parte 1: Segmentare gli utenti nell'organizzazione](#part-1-segment-users) | - Determinare i criteri necessari<br/>- Creare un elenco di segmenti da definire<br/>- Identificare gli attributi da utilizzare<br/>- Definire i segmenti in termini di filtri dei criteri |
| [Parte 2: Definire i criteri delle barriere di informazioni](#part-2-define-information-barrier-policies) | - Definire i criteri (non ancora applicabili)<br/>- Scegliere tra due tipi (blocca o consenti) |
| [Parte 3: Applicare i criteri delle barriere di informazioni](#part-3-apply-information-barrier-policies) | - Impostare i criteri sullo stato attivo<br/>- Eseguire l'applicazione dei criteri<br/>- Visualizzare lo stato dei criteri |
| (Se necessario) [Modificare un segmento o un criterio](information-barriers-edit-segments-policies.md) | - Modificare un segmento<br/>- Modificare o rimuovere un criterio<br/>- Eseguire di nuovo l'applicazione dei criteri<br/>- Visualizzare lo stato dei criteri |
| (Se necessario) [Risoluzione dei problemi](information-barriers-troubleshooting.md)| - Intervenire quando le cose non funzionano come previsto|

## <a name="prerequisites"></a>Prerequisiti

Oltre alle licenze e alle autorizzazioni [necessarie,](information-barriers.md#required-licenses-and-permissions)verificare che siano soddisfatti i requisiti seguenti:

- Dati della directory: verificare che la struttura dell'organizzazione sia riflessa nei dati della directory. Per eseguire questa operazione, assicurarsi che gli attributi dell'account utente, ad esempio l'appartenenza al gruppo, il nome del reparto e così via, siano popolati correttamente in Azure Active Directory (o Exchange Online). Per altre informazioni, vedere le risorse seguenti:
  - [Attributi per i criteri delle barriere informative](information-barriers-attributes.md)
  - [Aggiungere o aggiornare le informazioni del profilo di un utente con Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [Configurare le proprietà degli account utente con Office 365 PowerShell](/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)

- Ricerca nella directory con ambito: prima di definire i primi criteri delle barriere di informazioni dell'organizzazione, è necessario abilitare la ricerca di directory con ambito [in Microsoft Teams.](/MicrosoftTeams/teams-scoped-directory-search) Attendere almeno 24 ore dopo l'abilitazione della ricerca nella directory con ambito prima di configurare o definire i criteri delle barriere di informazioni.

- Licenza EXO: i criteri IB funzionano solo se agli utenti di destinazione è stata assegnata una licenza EXO.

- Registrazione di controllo: per cercare lo stato di un'applicazione dei criteri, è necessario che la registrazione di controllo sia attivata. È consigliabile abilitare il controllo prima di iniziare a definire segmenti o criteri. Per ulteriori informazioni, vedere [Attivare o disattivare la](turn-audit-log-search-on-or-off.md)ricerca nel log di controllo.

- Nessun criteri della rubrica: prima di definire e applicare i criteri delle barriere di informazioni, assicurarsi che non siano presenti criteri della rubrica di Exchange. Le barriere di informazioni si basano sui criteri della rubrica, ma i due tipi di criteri non sono compatibili. Se si dispone di tali criteri, assicurarsi di [rimuovere prima i criteri della rubrica.](/exchange/address-books/address-book-policies/remove-an-address-book-policy) Una volta abilitati i criteri delle barriere di informazioni e dopo aver abilitato la rubrica gerarchica, tutti gli utenti che non sono inclusi ***in*** un segmento di barriere di informazioni visualizzano la rubrica gerarchica [in](/exchange/address-books/hierarchical-address-books/hierarchical-address-books) Exchange Online.

- PowerShell: attualmente, i criteri delle barriere di informazioni sono definiti e gestiti nel Centro sicurezza & e conformità di Office 365 tramite i cmdlet di PowerShell. Anche se in questo articolo vengono forniti diversi esempi, è necessario avere familiarità con i cmdlet e i parametri di PowerShell. Sarà inoltre necessario il modulo Azure PowerShell.
    - [Connettersi a PowerShell in Centro sicurezza e conformità](/powershell/exchange/connect-to-scc-powershell)
    - [Installare il modulo di Azure PowerShell](/powershell/azure/install-az-ps?view=azps-2.3.2)

- Consenso dell'amministratore per le barriere in fatto di informazioni in Microsoft Teams: una volta applicati i criteri, le barriere delle informazioni possono rimuovere le persone dalle sessioni di chat in cui non dovrebbero essere presenti. Questa configurazione garantisce che l'organizzazione rimanga conforme ai criteri e alle normative. Utilizzare la procedura seguente per abilitare i criteri delle barriere di informazioni per funzionare come previsto in Microsoft Teams.

   1. Eseguire i cmdlet di PowerShell seguenti:

      ```powershell
      Connect-AzureAD 
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzADServicePrincipal -ServicePrincipalName $appId
      if ($sp -eq $null) { New-AzADServicePrincipal -ApplicationId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   2. Quando richiesto, accedere con l'account aziendale o dell'istituto di istruzione per Office 365.

   3. Nella finestra **di dialogo Autorizzazioni** richieste esaminare le informazioni e quindi scegliere **Accetta.**

Quando vengono soddisfatti tutti i prerequisiti, passare alla sezione successiva.

> [!TIP]
> Per facilitare la preparazione del piano, in questo articolo è incluso uno scenario di esempio. [Vedere i reparti, i segmenti e i criteri di Contoso.](#example-contosos-departments-segments-and-policies)<p>Inoltre, è disponibile una cartella di lavoro di Excel scaricabile che consente di pianificare e definire segmenti e criteri (e creare i cmdlet di PowerShell). [Recuperare la cartella di lavoro.](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx)

## <a name="part-1-segment-users"></a>Parte 1: Segmentare gli utenti

Durante questa fase, è possibile determinare quali criteri delle barriere di informazioni sono necessari, creare un elenco di segmenti da definire e quindi definire i segmenti.

### <a name="determine-what-policies-are-needed"></a>Determinare i criteri necessari

Considerando le normative legali e di settore, chi sono i gruppi all'interno dell'organizzazione che avranno bisogno di criteri di barriere di informazioni? Creare un elenco. Vi sono gruppi a cui non è consentito comunicare con un altro gruppo? Vi sono gruppi a cui dovrebbe essere consentito comunicare solo con uno o due altri gruppi? È necessario pensare ai criteri necessari come appartenenti a uno dei due gruppi seguenti:

- I criteri "Blocca" impediscono a un gruppo di comunicare con un altro gruppo.
- I criteri "Consenti" consentono a un gruppo di comunicare solo con determinati altri gruppi specifici.

Dopo aver creato l'elenco iniziale di gruppi e criteri, procedere con l'identificazione dei segmenti necessari.

### <a name="identify-segments"></a>Identificare i segmenti

Oltre all'elenco iniziale dei criteri, creare un elenco di segmenti per l'organizzazione. Gli utenti che verranno inclusi nei criteri delle barriere di informazioni devono appartenere a un segmento. Pianifica attentamente i segmenti in quanto un utente può essere solo in un segmento. A ogni segmento può essere applicato un solo criterio di barriere di informazioni.

> [!IMPORTANT]
> Un utente può essere in un solo segmento.

Determinare quali attributi nei dati della directory dell'organizzazione verranno utilizzati per definire i segmenti. È possibile utilizzare *Department,* *MemberOf* o uno qualsiasi degli attributi supportati. Assicurarsi di disporre di valori nell'attributo selezionato per gli utenti. [Per informazioni sulle barriere, vedere](information-barriers-attributes.md)l'elenco degli attributi supportati.

> [!IMPORTANT]
> **Prima di passare alla sezione successiva, verificare** che i dati della directory siano associati a valori per gli attributi che è possibile utilizzare per definire i segmenti. Se i dati della directory non dispongono di valori per gli attributi che si desidera utilizzare, gli account utente devono essere aggiornati per includere queste informazioni prima di procedere con le barriere di informazioni. Per ottenere assistenza in questo caso, vedere le risorse seguenti:<br/>- [Configurare le proprietà dell'account utente con PowerShell di Office 365](/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)<br/>- [Aggiungere o aggiornare le informazioni del profilo di un utente con Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>Definire segmenti tramite PowerShell

La definizione dei segmenti non influisce sugli utenti; imposta semplicemente la fase per la definizione e l'applicazione dei criteri delle barriere di informazioni.

1. Utilizzare il cmdlet **New-OrganizationSegment** con il **parametro UserGroupFilter** corrispondente all'attributo che si desidera utilizzare. [](information-barriers-attributes.md)

    |**Sintassi**|**Esempio**|
    |:---------|:----------|
    | `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"` |`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>In questo esempio, un segmento denominato *HR* viene definito utilizzando *HR*, un valore nell'attributo *Department.* La **parte -eq** del cmdlet fa riferimento a "uguale a". In alternativa, è possibile utilizzare **-ne** per indicare "diverso da". Vedi [Uso di "uguale" e "diverso da" nelle definizioni dei segmenti.](#using-equals-and-not-equals-in-segment-definitions) |

    Dopo aver eseguito ogni cmdlet, dovrebbe essere visualizzato un elenco di dettagli sul nuovo segmento. I dettagli includono il tipo del segmento, l'utente che lo ha creato o modificato per l'ultima volta e così via. 

2. Ripeti questo processo per ogni segmento che vuoi definire.

    > [!IMPORTANT]
    > **Assicurati che i segmenti non si sovrappongano.** Ogni utente a cui saranno interessate le barriere in fatto di informazioni deve appartenere a un segmento (e un solo). Nessun utente deve appartenere a due o più segmenti. (Vedere [l'esempio: segmenti](#contosos-defined-segments) definiti da Contoso in questo articolo).

Dopo aver definito i segmenti, procedere con la [definizione dei criteri delle barriere di informazioni.](#part-2-define-information-barrier-policies)

### <a name="using-equals-and-not-equals-in-segment-definitions"></a>Utilizzo di "uguale a" e "diverso da" nelle definizioni dei segmenti

Nell'esempio seguente viene definito un segmento in modo che "Department equals HR". 

|**Esempio**|**Nota**|
|:----------|:-------|
|`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` | Si noti che in questo esempio la definizione del segmento include un parametro "equals" denotato **come -eq**. |

È inoltre possibile definire segmenti utilizzando un parametro "diverso da", indicato come **-ne,** come illustrato nella tabella seguente:

|**Sintassi**|**Esempio**|
|:---------|:----------|
| `New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"` | In questo esempio è stato definito un segmento denominato *NotSales* che include tutti gli utenti non inclusi in *Sales.* La **parte -ne** del cmdlet fa riferimento a "diverso da". |

Oltre a definire i segmenti usando "equals" o "not equals", puoi definire un segmento usando entrambi i parametri "equals" e "not equals". È inoltre possibile definire filtri di gruppo complessi utilizzando operatori *logici AND* *e OR.*

|**Sintassi**|**Esempio**|
|:---------|:----------|
| `New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" -and "Position -ne 'Temporary'"` | In questo esempio è stato definito un segmento denominato *LocalFTE* che include le persone che si trovano in locale e le cui posizioni non sono elencate come *temporanee.* |
| `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "MemberOf -eq 'group1@contoso.com'' -and MemberOf -ne 'group3@contoso.com'"`| In questo esempio, abbiamo definito un segmento denominato *Segment1* che include persone che sono membri di group1@contoso.com e non membri di group3@contoso.com. |
| `New-OrganizationSegment -Name "Segment2" -UserGroupFilter "MemberOf -eq 'group2@contoso.com' -or MemberOf -ne 'group3@contoso.com'"` | In questo esempio, abbiamo definito un segmento denominato *Segment2* che include persone che sono membri di group2@contoso.com e non membri di group3@contoso.com. |
| `New-OrganizationSegment -Name "Segment1and2" -UserGroupFilter "(MemberOf -eq 'group1@contoso.com' -or MemberOf -eq 'group2@contoso.com') -and MemberOf -ne 'group3@contoso.com'"`| In questo esempio è stato definito un segmento denominato *Segment1and2* che include i membri delle persone di group1@contoso.com e group2@contoso.com e non i membri di group3@contoso.com. |

> [!TIP]
> Se possibile, usa definizioni di segmenti che includono "-eq" o "-ne". Cerca di non definire definizioni di segmenti complessi.

## <a name="part-2-define-information-barrier-policies"></a>Parte 2: Definire i criteri delle barriere di informazioni

Determinare se è necessario impedire le comunicazioni tra determinati segmenti o limitare le comunicazioni a determinati segmenti. Idealmente, si userà il numero minimo di criteri per garantire che l'organizzazione sia conforme ai requisiti legali e del settore.

Con l'elenco dei segmenti di utenti e i criteri delle barriere di informazioni che vuoi definire, seleziona uno scenario e quindi segui i passaggi.

- [Scenario 1: bloccare le comunicazioni tra segmenti](#scenario-1-block-communications-between-segments)
- [Scenario 2: consentire a un segmento di comunicare solo con un altro segmento](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> **Durante la definizione dei criteri,** non assegnare più di un criterio a un segmento. Se ad esempio si definisce un criterio per un segmento denominato *Vendite,* non definire un criterio aggiuntivo per *Sales.*<p> Inoltre, quando definisci i criteri delle barriere di informazioni, assicurati di impostare tali criteri sullo stato inattivo finché non sei pronto ad applicarli. La definizione (o modifica) dei criteri non influisce sugli utenti finché tali criteri non vengono impostati sullo stato attivo e quindi applicati.

(Vedere [l'esempio: i criteri delle barriere](#contosos-information-barrier-policies) di informazioni di Contoso in questo articolo).

### <a name="scenario-1-block-communications-between-segments"></a>Scenario 1: bloccare le comunicazioni tra segmenti

Quando vuoi impedire ai segmenti di comunicare tra loro, definisci due criteri: uno per ogni direzione. Ogni criterio blocca la comunicazione solo unidirezionale.

Si supponga, ad esempio, di voler bloccare le comunicazioni tra il segmento A e il segmento B. In questo caso, definisci un criterio che impedisce al segmento A di comunicare con il segmento B e quindi definisci un secondo criterio per impedire al segmento B di comunicare con il segmento A.

1. Per definire il primo criterio di blocco, utilizzare il cmdlet **New-InformationBarrierPolicy** con il **parametro SegmentsBlocked.**

    |**Sintassi** | **Esempio**| |**--------|:----------| |`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"` | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> In questo esempio è stato definito un criterio denominato *Sales-Research* per un segmento denominato *Sales.* Se attivo e applicato, questo criterio impedisce agli utenti di *Sales* di comunicare con persone in un segmento denominato *Ricerca.* |

2. Per definire il secondo segmento di blocco, utilizzare di nuovo il cmdlet **New-InformationBarrierPolicy** con il parametro **SegmentsBlocked,** questa volta con i segmenti invertito.

    |**Esempio**|**Nota**|
    |:----------|:-------|
    |`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` | In questo esempio, è stato definito un criterio denominato *Research-Sales* per impedire a *Research* di comunicare con *Sales.* |

3. Procedere con una delle azioni seguenti:

   - (Se necessario) [Definire un criterio per consentire a un segmento di comunicare solo con un altro segmento](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) 
   - (Dopo aver definito tutti i criteri) [Applicare i criteri delle barriere di informazioni](#part-3-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>Scenario 2: consentire a un segmento di comunicare solo con un altro segmento

1. Per consentire a un segmento di comunicare con un solo altro segmento, utilizzare il cmdlet **New-InformationBarrierPolicy** con il **parametro SegmentsAllowed.**

    |**Sintassi**|**Esempio**|
    |:----------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name","segment1name"` | `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Manufacturing" -State Inactive` <p> In questo esempio, è stato definito un criterio *denominato Manufacturing-HR* per un segmento denominato *Manufacturing.* Quando attivo e applicato, questo criterio consente agli utenti di *Produzione* di comunicare solo con persone in un segmento denominato *HR.* In questo caso, *Produzione non è* in grado di comunicare con utenti che non fanno parte delle risorse *umane.* |

    **Se necessario, è possibile specificare più segmenti con questo cmdlet, come illustrato nell'esempio seguente.**

    |**Sintassi**|**Esempio**|
    |:---------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name","segment1name"` | `New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing","Research" -State Inactive` <p> In questo esempio, è stato definito un criterio che consente al segmento *Research* di comunicare solo con *HR* e *Manufacturing.* |

    Ripeti questo passaggio per ogni criterio che vuoi definire per consentire a segmenti specifici di comunicare solo con determinati altri segmenti specifici.

2. Procedere con una delle azioni seguenti:

   - (Se necessario) [Definire un criterio per bloccare le comunicazioni tra segmenti](#scenario-1-block-communications-between-segments) 
   - (Dopo aver definito tutti i criteri) [Applicare i criteri delle barriere di informazioni](#part-3-apply-information-barrier-policies)

## <a name="part-3-apply-information-barrier-policies"></a>Parte 3: Applicare i criteri delle barriere di informazioni

I criteri delle barriere di informazioni non sono attivi finché non li si imposta sullo stato attivo e quindi si applicano i criteri.

1. Utilizzare il cmdlet **Get-InformationBarrierPolicy** per visualizzare un elenco dei criteri definiti. Prendere nota dello stato e dell'identità (GUID) di ogni criterio.

    Sintassi: `Get-InformationBarrierPolicy`

2. Per impostare un criterio sullo stato attivo, utilizzare il cmdlet **Set-InformationBarrierPolicy** con un parametro **Identity** e il parametro **State** impostato su **Active.** 

    |**Sintassi**|**Esempio**|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Active` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active` <p> In questo esempio viene impostato un criterio di barriere di informazioni con GUID *43c37853-ea10-4b90-a23d-ab8c93772471* sullo stato attivo. |

    Ripetere questo passaggio in base alle esigenze per ogni criterio.

3. Dopo aver impostato i criteri delle barriere di informazioni sullo stato attivo, utilizzare il cmdlet **Start-InformationBarrierPoliciesApplication** nel Centro sicurezza & conformità.

    Sintassi: `Start-InformationBarrierPoliciesApplication`

    Dopo l'esecuzione, lasciare al sistema 30 minuti per iniziare `Start-InformationBarrierPoliciesApplication` ad applicare i criteri. Il sistema applica i criteri utente per utente. Il sistema elabora circa 5.000 account utente all'ora.

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>Visualizzare lo stato di account utente, segmenti, criteri o applicazione di criteri

Con PowerShell, è possibile visualizzare lo stato di account utente, segmenti, criteri e applicazioni di criteri, come indicato nella tabella seguente.

|**Per visualizzare queste informazioni**|**Eseguire questa azione**|
|:---------------|:----------|
| Account utente | Utilizzare il cmdlet **Get-InformationBarrierRecipientStatus** con i parametri Identity. <p> Sintassi: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> È possibile utilizzare qualsiasi valore che identifichi ogni utente in modo univoco, ad esempio nome, alias, nome distinto, nome di dominio canonico, indirizzo di posta elettronica o GUID. <p> Esempio: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> In questo esempio si fa riferimento a due account utente in Office 365: *meganb* per *Megan* e *alexw* per *Alex.* <p> È inoltre possibile utilizzare questo cmdlet per un singolo `Get-InformationBarrierRecipientStatus -Identity <value>` utente: <p> Questo cmdlet restituisce informazioni sugli utenti, ad esempio i valori degli attributi e gli eventuali criteri delle barriere di informazioni applicati.|
| Segmenti | Utilizzare il cmdlet **Get-OrganizationSegment.**<p> Sintassi: `Get-OrganizationSegment` <p> Questo cmdlet visualizza un elenco di tutti i segmenti definiti per l'organizzazione. |
| Criteri delle barriere di informazioni | Utilizzare il cmdlet **Get-InformationBarrierPolicy.** <p> Sintassi: `Get-InformationBarrierPolicy` <p> Questo cmdlet visualizza un elenco dei criteri delle barriere di informazioni definiti e il relativo stato. |
| L'applicazione dei criteri delle barriere di informazioni più recenti | Utilizzare il cmdlet **Get-InformationBarrierPoliciesApplicationStatus.** <p> Sintassi: `Get-InformationBarrierPoliciesApplicationStatus`<p> Questo cmdlet visualizza informazioni sul completamento, l'esito negativo o l'esecuzione dell'applicazione dei criteri. |
| Tutte le applicazioni dei criteri delle barriere di informazioni|Usare `Get-InformationBarrierPoliciesApplicationStatus -All`<p> Questo cmdlet visualizza informazioni sul completamento, l'esito negativo o l'esecuzione dell'applicazione dei criteri.|

<!-- IN the " The most recent information barrier policy application, add link to troubleshooting topic -->

## <a name="what-if-i-need-to-remove-or-change-policies"></a>Cosa succede se è necessario rimuovere o modificare i criteri?

Sono disponibili risorse che consentono di gestire i criteri delle barriere di informazioni.

- Se si verifica un problema con le barriere delle informazioni, vedere [Risoluzione dei problemi relativi alle barriere in fatto di informazioni.](information-barriers-troubleshooting.md)
- Per interrompere l'applicazione dei criteri, vedere [Arrestare un'applicazione di criteri.](information-barriers-edit-segments-policies.md#stop-a-policy-application)
- Per rimuovere un criterio di barriere di informazioni, [vedere Rimuovere un criterio.](information-barriers-edit-segments-policies.md#remove-a-policy)
- Per apportare modifiche ai segmenti o ai criteri, vedi [Modificare (o rimuovere)](information-barriers-edit-segments-policies.md)i criteri delle barriere di informazioni.

## <a name="example-contosos-departments-segments-and-policies"></a>Esempio: reparti, segmenti e criteri di Contoso

Per vedere in che modo un'organizzazione potrebbe affrontare la definizione di segmenti e criteri, considera l'esempio seguente.

### <a name="contosos-departments-and-plan"></a>Piani e reparti di Contoso

Contoso ha cinque reparti: HR, Sales, Marketing, Research e Manufacturing. Per mantenere la conformità alle normative del settore, gli utenti di alcuni reparti non devono comunicare con altri reparti, come indicato nella tabella seguente:

|**Segmento**|**Può parlare con**|**Impossibile parlare con**|
|:----------|:--------------|:-----------------|
| HR | Tutti | (nessuna restrizione) |
| Sales | HR, Marketing, Manufacturing | Ricerca |
| Marketing | Tutti | (nessuna restrizione) |
| Ricerca | HR, Marketing, Manufacturing | Sales |
| Produzione | HR, Marketing | Chiunque diverso da HR o Marketing |

Per questa struttura, il piano di Contoso include tre criteri delle barriere di informazioni:

1. Un criterio progettato per impedire alle vendite di comunicare con la ricerca (e un altro criterio per impedire a Research di comunicare con Sales).
2. Un criterio progettato per consentire alla produzione di comunicare solo con le risorse umane e il marketing.

Per questo scenario, non è necessario definire criteri per hr o Marketing.

### <a name="contosos-defined-segments"></a>Segmenti definiti di Contoso

Contoso userà l'attributo Department in Azure Active Directory per definire i segmenti, come indicato di seguito:

|**Department**|**Segment Definition**|
|:-------------|:---------------------|
| HR | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` |
| Sales | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"` |
| Marketing | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"` |
| Ricerca | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"` |
| Produzione | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"` |

Dopo la definizione dei segmenti, Contoso procede con la definizione dei criteri.

### <a name="contosos-information-barrier-policies"></a>Criteri delle barriere di informazioni di Contoso

Contoso definisce tre criteri, come descritto nella tabella seguente:

|**Criterio**|**Definizione criterio**|
|:---------|:--------------------|
| **Criterio 1: Impedire alle vendite di comunicare con La ricerca** | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> In questo esempio il criterio delle barriere di informazioni è *denominato Sales-Research.* Quando questo criterio è attivo e applicato, impedisce agli utenti nel segmento Vendite di comunicare con gli utenti nel segmento Ricerche. Questo criterio è unidiresto; non impedirà a Research di comunicare con Sales. Per questo, è necessario il criterio 2. |
| **Criterio 2: impedire alle ricerche di comunicare con le vendite** | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> In questo esempio, il criterio delle barriere di informazioni è *denominato Research-Sales.* Quando questo criterio è attivo e applicato, impedisce agli utenti del segmento Ricerche di comunicare con gli utenti nel segmento Vendite. |
| **Criterio 3: consentire alla produzione di comunicare solo con le risorse umane e il marketing** | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing","Manufacturing" -State Inactive` <p> In questo caso, il criterio delle barriere di informazioni è *denominato Manufacturing-HRMarketing.* Quando questo criterio è attivo e applicato, Produzione può comunicare solo con HR e Marketing. Le risorse umane e marketing non sono limitate a comunicare con altri segmenti. |

Dopo aver definito segmenti e criteri, Contoso applica i criteri eseguendo il cmdlet **Start-InformationBarrierPoliciesApplication.**

Al termine del cmdlet, Contoso è conforme ai requisiti legali e del settore.

## <a name="resources"></a>Risorse

- [Panoramica delle barriere in fatto di informazioni](information-barriers.md)
- [Ulteriori informazioni sulle barriere di informazioni in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Ulteriori informazioni sulle barriere di informazioni in SharePoint Online](/sharepoint/information-barriers)
- [Ulteriori informazioni sulle barriere di informazioni in OneDrive](/onedrive/information-barriers)
