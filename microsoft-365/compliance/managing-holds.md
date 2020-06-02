---
title: Gestione delle esenzioni in Advanced eDiscovery
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
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Informazioni su come inserire le esenzioni sui depositari e sulle relative origini dati per conservare il contenuto pertinente per il caso di eDiscovery avanzato.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9f540877626d01652912038d69a83598af55ba1d
ms.sourcegitcommit: ff1af42b036bfdf75729db8c78f10cf4642616ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "44477162"
---
# <a name="manage-holds-in-advanced-ediscovery"></a>Gestione delle esenzioni in Advanced eDiscovery

È possibile utilizzare un caso avanzato di eDiscovery per creare le esenzioni per conservare il contenuto che potrebbe essere pertinente per il caso. Utilizzando le funzionalità avanzate di archiviazione di eDiscovery, è possibile applicare le esenzioni ai depositari e alle relative origini dati. Inoltre, è possibile applicare un blocco non detentivo alle cassette postali e ai siti di OneDrive for business. È inoltre possibile inserire un blocco nel sito di gruppo cassetta postale, sito di SharePoint e OneDrive for business per un gruppo di Microsoft 365. Analogamente, è possibile applicare un'esenzione alla cassetta postale e al sito associati a Microsoft teams. Quando si posizionano le posizioni di contenuto in attesa, il contenuto viene mantenuto finché non si rilascia il custode, si rimuove una specifica posizione dati o si elimina completamente il criterio di conservazione.

## <a name="manage-custodian-based-holds"></a>Gestione delle esenzioni basate su depositari

In alcuni casi, è possibile che si disponga di una serie di depositari che sono stati identificati e che si è deciso di conservare i dati durante il caso. In Advanced eDiscovery, quando questi depositari sono in attesa, l'utente e le relative origini dati selezionate vengono aggiunte automaticamente a un criterio di conservazione dei depositari.

Per visualizzare il criterio di conservazione dei depositari:

1. Nel centro conformità di Microsoft 365 fare clic su **eDiscovery > avanzate** per visualizzare l'elenco dei casi nell'organizzazione.
   
2. Passare alla scheda **depositari** per aggiungere depositari all'interno del caso. Per informazioni su come è possibile aggiungere e mettere in attesa i depositari all'interno di un caso di eDiscovery avanzato, vedere [aggiungere i depositari a un caso di eDiscovery avanzato](add-custodians-to-case.md). Se i depositari sono già stati aggiunti e li si tiene in attesa, andare al passaggio 3.
   
3. Passare alla scheda **esenzioni** e fare clic su **CustodianHold \<HoldId> **.
   
4. Nella pagina riquadro a comparsa, è possibile visualizzare le statistiche di blocco per il criterio. È inoltre possibile eseguire azioni come applicare una query al blocco basato su custode. Per ulteriori informazioni sulla creazione di una query di blocco e sull'utilizzo di condizioni, vedere [keyword queries and Search Conditions for content search](keyword-queries-and-search-conditions.md).
 
## <a name="manage-non-custodial-holds"></a>Gestione delle esenzioni non detentive

Quando si crea un'esenzione, sono disponibili le opzioni seguenti per l'ambito del contenuto conservato nei percorsi di contenuto specificati:

- È possibile creare un'esenzione infinita in cui tutto il contenuto viene messo in attesa. In alternativa, è possibile creare un blocco basato su query che contenga solo il contenuto che corrisponde a una query di ricerca.
  
- È possibile specificare un intervallo di date che contenga solo il contenuto che è stato inviato, ricevuto o creato all'interno di tale intervallo di date. In alternativa, è possibile conservare tutto il contenuto indipendentemente dal momento in cui è stato inviato, ricevuto o creato.

Per creare un blocco non affidatario per un caso avanzato di eDiscovery:

1. Nel centro conformità di Microsoft 365 fare clic su **eDiscovery > avanzate** per visualizzare l'elenco dei casi nell'organizzazione.
  
2. Fare clic su **Apri** accanto al caso in cui si desidera creare le esenzioni.
  
3. Nella Home page del caso, fare clic sulla scheda **esenzioni** .
  
4. Nella scheda **esenzioni** fare clic su **Crea**.
  
5. Nella pagina **denominare il blocco** , assegnare un nome al blocco. Il nome del blocco deve essere univoco nell'organizzazione.
 
6. Optional Nella casella **Descrizione** aggiungere una descrizione dell'esenzione.
  
7. Fare clic su **Avanti**.
  
8. Scegliere i percorsi di contenuto che si desidera inserire in attesa. È possibile inserire le cassette postali, i siti e le cartelle pubbliche in attesa.

   a. **Posta elettronica di Exchange** -fare clic su **Scegli utenti, gruppi o team** e quindi fare di nuovo clic su **Scegli utenti, gruppi o team** per specificare le cassette postali da inserire in attesa. Utilizzare la casella di ricerca per trovare le cassette postali degli utenti e i gruppi di distribuzione (per inserire un'esenzione nelle cassette postali dei membri del gruppo) per effettuare il blocco. È inoltre possibile inserire un blocco sulla cassetta postale associata per un gruppo di Microsoft 365 o un team di Microsoft. Selezionare la casella di controllo utente, gruppo, team, fare clic su **Scegli**e quindi su **fine**.
 
    > [!NOTE]
    > Quando si fa clic su **Scegli utenti, gruppi o team** per specificare le cassette postali da inserire in attesa, lo strumento di selezione delle cassette postali visualizzato è vuoto. Si tratta di un'impostazione predefinita per migliorare le prestazioni. Per aggiungere persone a questo elenco, digitare un nome, almeno 3 caratteri, nella casella di ricerca.

    b. **Siti di SharePoint** -fare clic su **Scegli siti** , quindi fare di nuovo clic su **Choose sites** per specificare i siti di SharePoint e OneDrive for business in attesa. Digitare l'URL per ogni sito che si desidera conservare. È inoltre possibile aggiungere l'URL per il sito di SharePoint per un gruppo di Microsoft 365 o un team di Microsoft. Fare clic su **Scegli**e quindi su **fine**.
    
     Vedere la sezione **FAQ** per suggerimenti su come mettere in attesa i gruppi di Microsoft 365 e Microsoft teams.

    > [!NOTE]
    > L'URL dell'account OneDrive di un utente include il relativo nome dell'entità utente (UPN) (ad esempio, `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` ). Nel caso raro che l'UPN di una persona sia cambiato, anche il relativo URL di OneDrive verrà modificato per incorporare il nuovo UPN. Se l'account OneDrive di un utente fa parte di un blocco non affidatario e il relativo UPN è cambiato, è necessario aggiornare il blocco e puntare al nuovo URL di OneDrive. Per altre informazioni, vedere [Come le modifiche UPN influiscono sull'URL di OneDrive](https://docs.microsoft.com/onedrive/upn-changes).

     c. **Cartelle pubbliche di Exchange** -spostare l'interruttore Toggle nella posizione all per inserire in attesa tutte le cartelle pubbliche nell'organizzazione di Exchange Online. Si noti che non è possibile scegliere le cartelle pubbliche specifiche da mettere in attesa. Lasciare l'opzione toggle impostata su **None** se non si desidera inserire un blocco nelle cartelle pubbliche.

9. Dopo aver aggiunto i percorsi di contenuto all'esenzione, fare clic su **Avanti**.
  
10. Per creare un blocco basato su query con condizioni, completare quanto segue. In caso contrario, fare clic su **Avanti**.
    
    - Nella casella sotto **parole chiave**Digitare una query di ricerca nella casella in modo che solo il contenuto che soddisfa i criteri di ricerca venga messo in attesa. È possibile specificare le parole chiave, le proprietà del messaggio o le proprietà del documento, ad esempio i nomi di file. È inoltre possibile utilizzare query più complesse che utilizzano un operatore booleano, ad esempio e, o o meno. Se si lascia vuota la casella parola chiave, tutto il contenuto che si trova nei percorsi di contenuto specificato verrà messo in attesa.

    - Fare clic su **Aggiungi** condizioni per aggiungere una o più condizioni per limitare la query di ricerca per il blocco. Ogni condizione aggiunge una clausola alla query di ricerca di KQL che viene creata e eseguita quando si crea il blocco. Ad esempio, è possibile specificare un intervallo di date in modo che i documenti di posta elettronica o di sito creati entro la data di intervallo siano stati inseriti in attesa. Una condizione è collegata logicamente alla query con parola chiave (specificata nella relativa casella) dall'operatore AND. Questo significa che gli elementi devono soddisfare sia la query di parole chiave che la condizione da inserire in attesa.

     Per ulteriori informazioni sulla creazione di una query di ricerca e sull'utilizzo di condizioni, vedere [keyword queries and Search Conditions for content search](https://docs.microsoft.com/office365/SecurityCompliance/keyword-queries-and-search-conditions).

11. Dopo aver configurato un blocco basato su query, fare clic su **Avanti**.

12. Rivedere le impostazioni e quindi fare clic su **Crea blocco**.

## <a name="view-hold-statistics"></a>Visualizzazione delle statistiche di blocco

Dopo un po' di tempo, le informazioni relative al nuovo blocco vengono visualizzate nel riquadro dei dettagli della scheda **esenzioni** per il blocco selezionato. Queste informazioni includono il numero di cassette postali e i siti in attesa e le statistiche sul contenuto che è stato messo in attesa, ad esempio il numero totale e le dimensioni degli elementi che sono stati messi in attesa e l'ultima volta che sono state calcolate le statistiche di blocco. Queste statistiche di blocco consentono di identificare la quantità di contenuto correlata al caso di eDiscovery.

Tenere presenti le considerazioni seguenti sulle statistiche di archiviazione:

- Il numero totale di elementi in attesa indica il numero di elementi provenienti da tutte le origini di contenuto che vengono bloccate. Se è stata creata una conservazione basata su query, questa statistica indica il numero di elementi che corrispondono alla query.
  
- Il numero di elementi in attesa include anche gli elementi non indicizzati trovati nei percorsi di contenuto. Si noti che se si crea un blocco basato su query, tutti gli elementi non indicizzati nei percorsi di contenuto vengono inseriti in attesa. Sono inclusi gli elementi non indicizzati che non corrispondono ai criteri di ricerca di un blocco basato su query e di elementi non indicizzati che potrebbero non essere compresi in una condizione dell'intervallo di date. Questo è diverso da quello che succede quando si esegue una ricerca di contenuto, in cui gli elementi non indicizzati che non corrispondono alla query di ricerca o sono esclusi da una condizione dell'intervallo di date non sono inclusi nei risultati della ricerca. Per ulteriori informazioni sugli elementi non indicizzati, vedere [gli elementi parzialmente indicizzati in ricerca contenuto in Office 365](partially-indexed-items-in-content-search.md). 

- È possibile ottenere le statistiche di blocco più recenti facendo clic su Aggiorna statistiche per rieseguire una stima di ricerca che calcola il numero corrente di elementi in attesa.

- Se necessario, fare clic su Aggiorna sulla barra degli strumenti per aggiornare le statistiche di blocco nel riquadro dei dettagli.

- È normale che il numero di elementi in attesa aumenti nel tempo, in quanto gli utenti la cui cassetta postale o sito è in attesa vengono in genere inviati o ricevuti da un nuovo messaggio di posta elettronica e dalla creazione di nuovi documenti di SharePoint e OneDrive for business.

- Se un sito di SharePoint o un account OneDrive viene spostato in un'area geografica diversa in un ambiente multi-geografico, le statistiche per il sito non verranno incluse nelle statistiche di esenzione. Tuttavia, il contenuto del sito rimarrà ancora in attesa. Inoltre, se un sito viene spostato in un'altra area, l'URL visualizzato nell'esenzione non verrà aggiornato. È necessario modificare il blocco e aggiornare l'URL.

## <a name="place-a-hold-on-microsoft-teams-and-office-365-groups"></a>Inserire un blocco nei gruppi di Microsoft teams e Office 365

Microsoft teams è basato sui gruppi di Office 365. Pertanto, la loro conservazione in Advanced eDiscovery è molto simile. 

- **In che modo è possibile eseguire il mapping di un sito Microsoft di Microsoft 365 o di altri gruppi a un custode? E che dire di disporre di un blocco non affidatario sui gruppi Microsoft 365 e Microsoft Teams?** Microsoft teams è basato sui gruppi di Microsoft 365. Pertanto, la loro conservazione in un caso di eDiscovery è molto simile. Tenere in considerazione gli aspetti seguenti quando si immettono in attesa gruppi Microsoft 365 e Microsoft teams.
  - Per inserire il contenuto in gruppi Microsoft 365 e Microsoft teams in attesa, è necessario specificare la cassetta postale e il sito di SharePoint associato a un gruppo o a un team.
  
  - Eseguire il cmdlet **Get-UnifiedGroup** in Exchange Online per visualizzare le proprietà di un gruppo di Microsoft 365 o di un team Microsoft. Si tratta di un modo efficace per ottenere l'URL del sito associato a un gruppo di Microsoft 365 o a un team di Microsoft. Ad esempio, il comando seguente consente di visualizzare le proprietà selezionate per un gruppo di Microsoft 365 denominato Senior Leadership Team:


    ```text
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Per eseguire il cmdlet Get-UnifiedGroup, è necessario avere il ruolo Destinatari di sola lettura in Exchange Online o essere membri di un gruppo di ruoli assegnato al ruolo Destinatari di sola lettura.

 - Quando viene eseguita la ricerca della cassetta postale di un utente, qualsiasi gruppo di Microsoft 365 o Microsoft Team che l'utente è membro di non verrà cercato. Analogamente, quando si inserisce un gruppo di Microsoft 365 o un blocco di Microsoft Team, solo la cassetta postale di gruppo e il sito del gruppo vengono conservati in blocco; le cassette postali e i siti di OneDrive for business dei membri del gruppo non vengono conservati a meno che non vengano aggiunti in modo esplicito come depositari o che dispongano delle origini dati. Pertanto, se si ha la necessità di disporre di un gruppo di Microsoft 365 o di un team Microsoft per uno specifico custode, valutare la possibilità di mappare la cassetta postale del sito e del gruppo del gruppo al custode (vedere Managing Depositaries in Advanced eDiscovery). Se il gruppo Microsoft 365 o il team Microsoft non è attribuibile a un singolo custode, è consigliabile aggiungere l'origine a un blocco non detentivo. 
 
 - Per ottenere un elenco dei membri di un gruppo di Microsoft 365 o di un team Microsoft, è possibile visualizzare le proprietà nella pagina Home > gruppi nell'interfaccia di amministrazione di Microsoft 365. In alternativa, è possibile eseguire il comando seguente in PowerShell di Exchange Online:

   ```powershell
   Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
   ```

    > [!NOTE]
    > Per eseguire il cmdlet **Get-UnifiedGroupLinks**, è necessario avere il ruolo Destinatari di sola lettura in Exchange Online o essere membri di un gruppo di ruoli assegnato al ruolo Destinatari di sola lettura.

- Le conversazioni di canale che fanno parte di un canale Microsoft teams vengono memorizzate nella cassetta postale associata al team. Allo stesso modo, i file che i membri del team condividono in un canale vengono archiviati nel sito di SharePoint del team. Pertanto, è necessario inserire la cassetta postale di Microsoft Team e il sito di SharePoint in attesa per conservare le conversazioni e i file in un canale.
  
- In alternativa, le conversazioni che fanno parte dell'elenco chat in Microsoft teams vengono memorizzate nella cassetta postale dell'utente che partecipa alla chat.  I file che un utente condivide nelle conversazioni chat sono archiviati nel sito di OneDrive for business dell'utente che condivide il file. Pertanto, è necessario posizionare i singoli utenti e le cassette postali di OneDrive for business in attesa per conservare le conversazioni e i file nell'elenco chat. 
  
- Ogni canale di Microsoft Team o team contiene un wiki per la partecipazione alle note e la collaborazione. Il contenuto Wiki viene salvato automaticamente in un file con formato MHT. Il file è archiviato nella raccolta documenti di dati Wiki di Teams nel sito di SharePoint del team. È possibile inserire il contenuto nel wiki in attesa inserendo il sito di SharePoint del team in attesa.

  > [!NOTE]
  > La possibilità di conservare il contenuto wiki per un canale Microsoft Team o team (quando si posiziona il sito di SharePoint del team in attesa) è stata rilasciata il 22 giugno 2017. Se un sito del team è in attesa, il contenuto del wiki verrà mantenuto a partire da tale data. Tuttavia, se un sito del team è in attesa e il contenuto del wiki è stato eliminato entro il 22 giugno 2017, il contenuto del wiki non è stato mantenuto.
