---
title: Usare il controllo di condivisione nel log di controllo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.collection:
- M365-security-compliance
- SPO_Content
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: "La condivisione è un'attività chiave in SharePoint Online e OneDrive for business. Gli amministratori possono ora utilizzare il controllo di condivisione nel log di controllo per identificare le risorse condivise con gli utenti all'esterno dell'organizzazione. "
ms.openlocfilehash: 63b56831dc5409cc92a0c4a2f4bf002cd268a878
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626382"
---
# <a name="use-sharing-auditing-in-the-audit-log"></a>Usare il controllo di condivisione nel log di controllo

La condivisione è un'attività chiave in SharePoint Online e OneDrive for business ed è ampiamente utilizzata nelle organizzazioni. Gli amministratori possono utilizzare il controllo di condivisione nel log di controllo per determinare in che modo viene utilizzata la condivisione nell'organizzazione. 
  
## <a name="the-sharepoint-sharing-schema"></a>Lo schema di condivisione di SharePoint

La condivisione di eventi (esclusi gli eventi relativi al criterio di condivisione e ai collegamenti di condivisione) è diversa dagli eventi relativi a file e cartelle in un unico modo principale: un utente sta eseguendo un'azione che ha effetto su un altro utente. Ad esempio, quando un utente di risorse A fornisce all'utente B l'accesso a un file. In questo esempio, l'utente A rappresenta l'utente che *agisce* e l'utente B è l' *utente di destinazione*. Nello schema dei file di SharePoint, l'azione dell'utente che agisce ha effetto solo sul file stesso. Quando un utente apre un file, le uniche informazioni necessarie per l'evento **Fileaccessed** sono gli utenti che agiscono. Per risolvere questa differenza, è disponibile uno schema distinto, denominato *schema di condivisione di SharePoint*, che acquisisce ulteriori informazioni sulla condivisione degli eventi. In questo modo gli amministratori avranno la visibilità su chi ha condiviso una risorsa e l'utente con cui è stata condivisa la risorsa. 
  
Nello schema di condivisione sono disponibili due campi aggiuntivi in un record di controllo relativo agli eventi di condivisione: 
  
- **TargetUserOrGroupType:** Identifica se l'utente o il gruppo di destinazione è membro, Guest, SharePointGroup, SecurityGroup o partner.

- **TargetUserOrGroupName:** Archivia l'UPN o il nome dell'utente o del gruppo di destinazione a cui è stata condivisa una risorsa (utente B nell'esempio precedente). 

Questi due campi, oltre ad altre proprietà dello schema del registro di controllo, ad esempio utente, operazione e data, possono raccontare la storia completa *dell'utente* che *ha condiviso la* risorsa con *cui* e *quando*. 
  
È presente un'altra proprietà dello schema che è importante per la storia della condivisione. Quando si esportano i risultati della ricerca dei log di controllo, la colonna **AuditData** nel file CSV esportato Archivia le informazioni sugli eventi di condivisione. Ad esempio, quando un utente condivide un sito con un altro utente, questo viene ottenuto aggiungendo l'utente di destinazione a un gruppo di SharePoint. La colonna **AuditData** acquisisce queste informazioni per fornire il contesto per gli amministratori. Per istruzioni su come analizzare le informazioni nella colonna **AuditData** , vedere il [passaggio 2](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) .

## <a name="sharepoint-sharing-events"></a>Eventi di condivisione di SharePoint

La condivisione è definita da quando un utente (l'utente che *agisce* ) desidera condividere una risorsa con un altro utente (l'utente di *destinazione* ). I record di controllo relativi alla condivisione di una risorsa con un utente esterno (un utente esterno all'organizzazione e che non dispongono di un account Guest nell'Azure Active Directory dell'organizzazione) sono identificati dagli eventi seguenti, che vengono registrati nel log di controllo:

- **SharingInvitationCreated:** Un utente dell'organizzazione ha provato a condividere una risorsa (probabilmente un sito) con un utente esterno. Questo comporta l'invio di un invito di condivisione esterna all'utente di destinazione. A questo punto non viene concesso l'accesso alla risorsa.

- **SharingInvitationAccepted:** L'utente esterno ha accettato l'invito di condivisione inviato dall'utente che agisce e ora ha accesso alla risorsa.

- **AnonymousLinkCreated:** Per una risorsa viene creato un collegamento Anonimo (denominato anche collegamento "chiunque"). Poiché è possibile creare un collegamento anonimo e quindi copiarlo, è ragionevole presumere che tutti i documenti che dispongono di un collegamento anonimo siano stati condivisi con un utente di destinazione.

- **AnonymousLinkUsed:** Come suggerisce il nome, questo evento viene registrato quando si utilizza un collegamento anonimo per accedere a una risorsa. 

- **SecureLinkCreated:** Un utente ha creato un "collegamento utenti specifici" per condividere una risorsa con una persona specifica. Questo utente di destinazione potrebbe essere una persona esterna all'organizzazione. La persona a cui è condivisa la risorsa viene identificata nel record di controllo per l'evento **AddedToSecureLink** . Gli indicatori di data e ora per questi due eventi sono quasi identici.

- **AddedToSecureLink:** Un utente è stato aggiunto a un collegamento di persone specifico. Utilizzare il campo **TargetUserOrGroupName** in questo evento per identificare l'utente aggiunto al collegamento specifico corrispondente. Questo utente di destinazione potrebbe essere una persona esterna all'organizzazione.

## <a name="sharing-auditing-work-flow"></a>Condivisione del flusso di lavoro di controllo
  
Quando un utente (l'utente che agisce) desidera condividere una risorsa con un altro utente (l'utente di destinazione), SharePoint (o OneDrive for business) prima verifica se l'indirizzo di posta elettronica dell'utente di destinazione è già associato a un account utente nella directory dell'organizzazione. Se l'utente di destinazione si trova nella directory e dispone di un account utente Guest corrispondente, SharePoint esegue le operazioni seguenti:
  
-  Assegna immediatamente le autorizzazioni utente di destinazione per accedere alla risorsa aggiungendo l'utente di destinazione al gruppo di SharePoint appropriato e registra un evento **AddedToGroup** . 
    
- Invia una notifica di condivisione all'indirizzo di posta elettronica dell'utente di destinazione.
    
- Registra un evento **SharingSet** . Questo evento ha un nome descrittivo di "file condiviso, cartella o sito" in **attività di condivisione e di richiesta di accesso** nella selezione attività dello strumento di ricerca del registro di controllo. Vedere la schermata nel [passaggio 1](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file). 
    
Se un account utente per l'utente di destinazione non è presente nella directory, SharePoint esegue le operazioni seguenti: 
    
   - Registra uno degli eventi seguenti, in base al modo in cui la risorsa è condivisa:
   
      - **AnonymousLinkCreated**
   
      - **SecureLinkCreated**
   
      - **AddedToSecureLink** 

      - **SharingInvitationCreated** (questo evento viene registrato solo quando la risorsa condivisa è un sito)
    
   - Quando l'utente di destinazione accetta l'invito di condivisione inviato a tali utenti (facendo clic sul collegamento nell'invito), SharePoint registra un evento **SharingInvitationAccepted** e assegna le autorizzazioni utente di destinazione per l'accesso alla risorsa. Se all'utente di destinazione viene inviato un collegamento anonimo, l'evento **AnonymousLinkUsed** viene registrato dopo che l'utente di destinazione ha utilizzato il collegamento per accedere alla risorsa. Per i collegamenti sicuri, viene registrato un evento **Fileaccessed** quando un utente esterno utilizza il collegamento per accedere alla risorsa.

Vengono inoltre registrate informazioni aggiuntive sull'utente di destinazione, ad esempio l'identità dell'utente a cui l'invito è associato e l'utente che accetta l'invito. In alcuni casi, questi utenti (o indirizzi di posta elettronica) possono essere diversi. 

## <a name="how-to-identify-resources-shared-with-external-users"></a>Come identificare le risorse condivise con gli utenti esterni

Un requisito comune per gli amministratori consiste nella creazione di un elenco di tutte le risorse condivise con utenti esterni all'organizzazione. Utilizzando la condivisione del controllo in Office 365, gli amministratori possono generare questo elenco. Ecco come fare.
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a>Passaggio 1: cercare gli eventi di condivisione ed esportare i risultati in un file CSV

Il primo passaggio consiste nell'eseguire una ricerca nel registro di controllo per la condivisione degli eventi. Per ulteriori informazioni (incluse le autorizzazioni necessarie) per la ricerca nel registro di controllo, vedere [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).
  
1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere con l'account aziendale o dell'Istituto di istruzione.
    
3. Nel riquadro sinistro del Centro sicurezza e conformità fare clic su **Cerca**  > **Ricerca log di controllo**.
    
    Viene visualizzata la pagina **Ricerca log di controllo**. 
    
4. In **attività**fare clic su **condivisione e accesso alle attività richieste** per cercare gli eventi relativi alla condivisione. 
    
    ![In attività selezionare condivisione e accesso alle attività richieste](../media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  Selezionare un intervallo di data e ora per individuare gli eventi di condivisione che si sono verificati entro quel periodo. 
    
6. Fare clic su **Cerca** per eseguire la ricerca. 
    
7. Al termine dell'esecuzione della ricerca e i risultati vengono visualizzati, fare clic su **Esporta risultati** \> **scaricare tutti i risultati**.
    
    Dopo aver selezionato l'opzione di esportazione, nella parte inferiore della finestra viene visualizzato un messaggio in cui viene richiesto di aprire o salvare il file CSV.
    
8. Fare clic su **Salva** \> con **nome** e salvare il file CSV in una cartella del computer locale. 

### <a name="step-2-use-the-powerquery-editor-to-format-the-exported-audit-log"></a>Passaggio 2: utilizzare l'editor di PowerQuery per formattare il registro di controllo esportato

Il passaggio successivo consiste nell'utilizzare la caratteristica di trasformazione JSON nell'editor di query di alimentazione in Excel per dividere ogni proprietà nella colonna **AuditData** (costituita da un oggetto JSON a più proprietà) nella relativa colonna. In questo modo è possibile filtrare le colonne per visualizzare i record relativi alla condivisione

Per istruzioni dettagliate, vedere "passaggio 2: formattare il log di controllo esportato utilizzando l'editor di query di alimentazione" in [esportare, configurare e visualizzare i record del registro di controllo](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).

### <a name="step-3-filter-the-csv-file-for-resources-shared-with-external-users"></a>Passaggio 3: filtrare il file CSV per le risorse condivise con gli utenti esterni

Il passaggio successivo consiste nel filtrare il CSV per i diversi eventi relativi alla condivisione descritti in precedenza nella sezione [eventi di condivisione di SharePoint](#sharepoint-sharing-events) . In alternativa, è possibile filtrare la colonna **TargetUserOrGroupType** per visualizzare tutti i record in cui il valore di questa proprietà è **Guest**. 

Dopo aver seguito le istruzioni riportate nel passaggio precedente per preparare il file CSV utilizzando l'editor di PowerQuery, eseguire le operazioni seguenti:
    
1. Aprire il file di Excel creato nel passaggio 2. 

2. Nella scheda **Home** fare clic su **Ordina & filtro**, quindi fare clic su **filtro**.
    
3. Nell'elenco a discesa **ordina & filtro** nella colonna **operazioni** deselezionare tutte le selezioni, quindi selezionare uno o più degli eventi correlati alla condivisione seguenti e quindi fare clic su **OK**.
 
   - **SharingInvitationCreated**
   
   - **AnonymousLinkCreated**
   
   - **SecureLinkCreated**
   
   - **AddedToSecureLink** 
    
    Excel Visualizza le righe per gli eventi selezionati.
    
4. Passare alla colonna denominata **TargetUserOrGroupType** e selezionarla. 
    
5. Nell'elenco a discesa **ordina & filtro** , deselezionare tutte le selezioni, quindi selezionare **TargetUserOrGroupType: Guest**e fare clic su **OK**.
    
    Ora Excel Visualizza le righe per gli eventi di condivisione e in cui l'utente di destinazione si trova all'esterno dell'organizzazione, perché gli utenti esterni sono identificati dal valore **TargetUserOrGroupType: Guest**. 
  
> [!TIP]
> Per i record di controllo visualizzati, la colonna **ObjectID** identifica la risorsa condivisa con l'utente di destinazione. ad esempio `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.
