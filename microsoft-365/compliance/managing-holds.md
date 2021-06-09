---
title: Gestire i blocchi in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Informazioni su come conservare i depositario e le relative origini dati per conservare il contenuto pertinente per il Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 70390a933de788a6b1190e42b5087b85a175b9a2
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570590"
---
# <a name="manage-holds-in-advanced-ediscovery"></a>Gestire i blocchi in Advanced eDiscovery

Puoi usare un caso Advanced eDiscovery per creare blocchi per conservare il contenuto che potrebbe essere rilevante per il tuo caso. Usando le funzionalità Advanced eDiscovery di conservazione, è possibile inserire i blocchi nei custodi e nelle relative origini dati. Inoltre, è possibile inserire un blocco non di archiviazione per le cassette postali e OneDrive for Business siti. È inoltre possibile impostare un blocco sulla cassetta postale del gruppo, SharePoint e sul sito OneDrive for Business per un Microsoft 365 gruppo. Analogamente, è possibile impostare un blocco sulla cassetta postale e sul sito associati a Microsoft Teams. Quando si posizionano le posizioni del contenuto in attesa, il contenuto viene mantenuto fino a quando non si rilascia il responsabile, si rimuove una posizione dati specifica o si elimina completamente il criterio di conservazione.

## <a name="manage-custodian-based-holds"></a>Gestire i blocchi basati sul responsabile

In alcuni casi, potresti avere un set di custodi che hai identificato e che hai deciso di conservare i loro dati durante il caso. In Advanced eDiscovery, quando questi custodi vengono messi in attesa, l'utente e le origini dati selezionate vengono aggiunti automaticamente a un criterio di conservazione dei depositario.

Per visualizzare il criterio di conservazione del responsabile:

1. Nel Centro Microsoft 365 conformità fare clic su **eDiscovery > avanzate** per visualizzare l'elenco dei casi nell'organizzazione.

2. Passare alla scheda **Origini** per aggiungere i custodi all'interno del caso. Per informazioni su come aggiungere e mettere i custodi in attesa all'interno di un caso Advanced eDiscovery, vedere [Add Custodians to a case](add-custodians-to-case.md). Se hai già aggiunto i custodi e li hai messi in attesa, vai al passaggio 3.

3. Passare alla scheda **Esenzioni** e fare clic **su \<HoldId> CustodianHold.**

4. Nella pagina a comparsa è possibile visualizzare le statistiche di blocco per il criterio. È inoltre possibile eseguire azioni come applicare una query all'esenzione basata sul responsabile. Per ulteriori informazioni sulla creazione di una query di blocco e sull'utilizzo di condizioni, vedere Query con parole chiave e condizioni [di ricerca per Ricerca contenuto.](keyword-queries-and-search-conditions.md)

## <a name="manage-non-custodial-holds"></a>Gestire i blocchi non depositario

Quando si crea un'esenzione, sono disponibili le opzioni seguenti per l'ambito del contenuto nei percorsi di contenuto specificati:

- Si crea un'esenzione infinita in cui tutto il contenuto viene messo in attesa. In alternativa, è possibile creare un'esenzione basata su query in cui viene messo in attesa solo il contenuto corrispondente a una query di ricerca.
  
- È possibile specificare un intervallo di date per contenere solo il contenuto inviato, ricevuto o creato all'interno di tale intervallo di date. In alternativa, è possibile mantenere tutto il contenuto indipendentemente dal momento in cui è stato inviato, ricevuto o creato.

Per creare un blocco non depositario per un caso Advanced eDiscovery caso:

1. Nel Centro Microsoft 365 conformità fare clic su **eDiscovery > avanzate** per visualizzare l'elenco dei casi nell'organizzazione.
  
2. Fare **clic** su Apri accanto al caso in cui si desidera creare le esenzioni.
  
3. Nella home page del caso fare clic sulla **scheda Esenzioni.**
  
4. Nella scheda **Esenzioni** fare clic su **Crea.**
  
5. Nella pagina **Assegna un nome all'esenzione.** Il nome del blocco deve essere univoco nell'organizzazione.
 
6. (Facoltativo) Nella casella **Descrizione** aggiungere una descrizione dell'esenzione.
  
7. Fare clic su **Avanti**.
  
8. Scegliere i percorsi di contenuto che si desidera mettere in attesa. È possibile piazzare un blocco per cassette postali, siti e cartelle pubbliche.

   1. **Exchange posta elettronica-** Fare clic su Scegli utenti, gruppi o **team,** quindi fare di nuovo clic su Scegli **utenti,** gruppi o team per specificare le cassette postali da mettere in attesa. Utilizzare la casella di ricerca per trovare le cassette postali degli utenti e i gruppi di distribuzione da mettere in attesa (per mettere in attesa le cassette postali dei membri del gruppo). È inoltre possibile impostare un blocco sulla cassetta postale associata per un Microsoft 365 gruppo o un team Microsoft. Selezionare la casella di controllo utente, gruppo, team, fare clic **su Scegli** e quindi su **Fine.**
 
      > [!NOTE]
      > Quando si fa **clic su Scegli utenti,** gruppi o team per specificare le cassette postali da mettere in attesa, la selezione delle cassette postali visualizzata è vuota. Si tratta di un'impostazione predefinita per migliorare le prestazioni. Per aggiungere persone all'elenco, digitare un nome (un minimo di 3 caratteri) nella casella di ricerca.

   1. **SharePoint siti:** fare **clic** su  Scegli siti e quindi su Scegli siti di nuovo per specificare SharePoint e OneDrive for Business siti da mettere in attesa. Digitare l'URL per ogni sito che si desidera mettere in blocco. È inoltre possibile aggiungere l'URL per il sito SharePoint per un Microsoft 365 gruppo o un team Microsoft. Fare **clic su** Scegli e quindi su **Fine.**

      > [!NOTE]
      > L'URL dell'account OneDrive utente include il nome dell'entità utente (UPN, User Principal Name), ad esempio `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` . Nel raro caso in cui l'UPN di una persona viene modificato, anche l'URL OneDrive cambia per incorporare il nuovo UPN. Se l'account OneDrive di un utente fa parte di un'esenzione non depositale e il relativo UPN viene modificato, è necessario aggiornare il blocco e puntare al nuovo URL OneDrive. Per altre informazioni, vedere [Come le modifiche UPN influiscono sull'URL di OneDrive](/onedrive/upn-changes).

   1. **Exchange pubbliche-** Spostare l'interruttore interruttore nella posizione Tutti per mettere in attesa tutte le cartelle pubbliche Exchange Online'organizzazione. Si noti che non è possibile scegliere cartelle pubbliche specifiche da mettere in attesa. Lasciare l'interruttore **interruttore** impostato su Nessuno se non si desidera mettere un'esenzione sulle cartelle pubbliche.

9. Al termine dell'aggiunta di percorsi di contenuto all'esenzione, fare clic su **Avanti.**
  
10. Per creare un blocco basato su query con condizioni, completare le operazioni seguenti. In caso contrario, fare clic **su Avanti.**
    
    - Nella casella sotto Parole **chiave** digitare una query di ricerca nella casella in modo che solo il contenuto che soddisfa i criteri di ricerca sia messo in attesa. È possibile specificare parole chiave, proprietà del messaggio o proprietà del documento, ad esempio i nomi di file. È inoltre possibile utilizzare query più complesse che utilizzano un operatore booleano, ad esempio AND, OR o NOT. Se si lascia vuota la casella della parola chiave, tutto il contenuto che si trova nei percorsi di contenuto specificati verrà messo in attesa.

    - Fare  **clic su** Aggiungi condizioni per aggiungere una o più condizioni per limitare la query di ricerca per l'esenzione. Ogni condizione aggiunge una clausola alla query di ricerca KQL creata ed eseguita quando si crea il blocco. Ad esempio, è possibile specificare un intervallo di date in modo che i messaggi di posta elettronica o i documenti del sito creati nell'intervallo di date siano messi in attesa. Una condizione è collegata logicamente alla query con parola chiave (specificata nella relativa casella) dall'operatore AND. Ciò significa che gli elementi devono soddisfare sia la query con parole chiave che la condizione da mantenere.

     Per ulteriori informazioni sulla creazione di una query di ricerca e sull'utilizzo di condizioni, vedere Query con parole chiave e condizioni [di ricerca per Ricerca contenuto.](/office365/SecurityCompliance/keyword-queries-and-search-conditions)

11. Dopo aver configurato un blocco basato su query, fare clic su **Avanti.**

12. Rivedere le impostazioni e quindi fare clic su **Crea blocco.**

## <a name="view-hold-statistics"></a>Visualizzare le statistiche di blocco

Dopo un certo periodo di tempo, le informazioni sulla nuova esenzione vengono visualizzate nel riquadro dei dettagli **della** scheda Esenzioni per l'esenzione selezionata. Queste informazioni includono il numero di cassette postali e siti in attesa e le statistiche sul contenuto che è stato messo in attesa, ad esempio il numero totale e le dimensioni degli elementi messi in attesa e l'ultima volta in cui sono state calcolate le statistiche di blocco. Queste statistiche di blocco consentono di identificare la quantità di contenuto correlato al caso di eDiscovery.

Tenere presente quanto segue sulle statistiche di blocco:

- Il numero totale di elementi in attesa indica il numero di elementi di tutte le origini di contenuto che vengono messi in attesa. Se è stata creata un'esenzione basata su query, questa statistica indica il numero di elementi che corrispondono alla query.
  
- Il numero di elementi in attesa include anche gli elementi non indicizzati trovati nei percorsi del contenuto. Si noti che se si crea un'archiviazione basata su query, tutti gli elementi non indicizzati nelle posizioni del contenuto vengono messi in attesa. Sono inclusi gli elementi non indicizzati che non corrispondono ai criteri di ricerca di un'esenzione basata su query e gli elementi non indicizzati che potrebbero non rientrare in una condizione di intervallo di date. Ciò è diverso da quello che accade quando si esegue una ricerca di contenuto, in cui gli elementi non indicizzati che non corrispondono alla query di ricerca o sono esclusi da una condizione di intervallo di date non vengono inclusi nei risultati della ricerca. Per ulteriori informazioni sugli elementi non indicizzati, vedere [Elementi parzialmente indicizzati in Ricerca contenuto in Office 365](partially-indexed-items-in-content-search.md). 

- È possibile ottenere le statistiche di blocco più recenti facendo clic su Aggiorna statistiche per eseguire di nuovo una stima di ricerca che calcola il numero corrente di elementi in attesa.

- Se necessario, fare clic su Aggiorna sulla barra degli strumenti per aggiornare le statistiche di blocco nel riquadro dei dettagli.

- È normale che il numero di elementi in attesa aumenti nel tempo perché gli utenti la cui cassetta postale o sito è in attesa in genere inviano o ricevono nuovi messaggi di posta elettronica e creano nuovi documenti SharePoint e OneDrive for Business.

- Se un SharePoint o un account OneDrive viene spostato in un'area diversa in un ambiente multi-geografico, le statistiche per tale sito non verranno incluse nelle statistiche di blocco. Tuttavia, il contenuto del sito sarà ancora in attesa. Inoltre, se un sito viene spostato in un'area diversa, l'URL visualizzato nell'esenzione non verrà aggiornato. Dovrai modificare il blocco e aggiornare l'URL.

## <a name="place-a-hold-on-microsoft-teams-and-office-365-groups"></a>Blocco su Microsoft Teams e Office 365 gruppi

Microsoft Teams si basano su Office 365 gruppi. Pertanto, metterli in attesa in Advanced eDiscovery è molto simile.

- **Come si esegue il mapping di un sito Microsoft 365 o Microsoft Teams a un responsabile? E per quanto riguarda l'inserimento di un blocco non Microsoft 365 e Microsoft Teams?** Microsoft Teams si basano su Microsoft 365 gruppi. Di conseguenza, l'applicazione di un blocco in un caso di eDiscovery è molto simile. Tenere presente quanto segue quando si Microsoft 365 gruppi e Microsoft Teams blocco.
  - Per mettere in attesa il contenuto Microsoft 365 gruppi e Microsoft Teams, è necessario specificare la cassetta postale e il sito SharePoint associato a un gruppo o a un team.
  
  - Eseguire il cmdlet **Get-UnifiedGroup** in Exchange Online per visualizzare le proprietà di un gruppo Microsoft 365 o microsoft team. Questo è un buon modo per ottenere l'URL del sito associato a un Microsoft 365 gruppo o a un team Microsoft. Ad esempio, il comando seguente consente di visualizzare le proprietà selezionate per un gruppo di Microsoft 365 denominato Senior Leadership Team:


    ```console
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Per eseguire il cmdlet Get-UnifiedGroup, è necessario avere il ruolo Destinatari di sola lettura in Exchange Online o essere membri di un gruppo di ruoli assegnato al ruolo Destinatari di sola lettura.

 - Quando si esegue la ricerca nella cassetta postale di un utente, non verrà cercata alcuna Microsoft 365 gruppo o team Microsoft di cui l'utente è membro. Analogamente, quando si applica un blocco Microsoft 365 gruppo o microsoft team, solo la cassetta postale del gruppo e il sito del gruppo vengono messi in attesa; le cassette postali e i OneDrive for Business dei membri del gruppo non vengono messi in attesa a meno che non vengano esplicitamente aggiunti come custodi o non si mantino le origini dati. Pertanto, se è necessario mettere in attesa un gruppo di Microsoft 365 o un team Microsoft per un responsabile specifico, è consigliabile mappare il sito del gruppo e la cassetta postale del gruppo al responsabile (vedere Managing Custodians in Advanced eDiscovery). Se il Microsoft 365 o il Team Microsoft non è attribuibile a un singolo responsabile, valuta la possibilità di aggiungere l'origine a un blocco non depositario. 
 
 - Per ottenere un elenco dei membri di un gruppo di Microsoft 365 o microsoft team, è possibile visualizzare le proprietà nella pagina Home > Gruppi nell'interfaccia di amministrazione di Microsoft 365. In alternativa, è possibile eseguire il comando seguente in PowerShell di Exchange Online:

   ```powershell
   Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
   ```

    > [!NOTE]
    > Per eseguire il cmdlet **Get-UnifiedGroupLinks**, è necessario avere il ruolo Destinatari di sola lettura in Exchange Online o essere membri di un gruppo di ruoli assegnato al ruolo Destinatari di sola lettura.

- Le conversazioni di canale che fanno parte di Microsoft Teams canale vengono archiviate nella cassetta postale associata al team. Allo stesso modo, i file che i membri del team condividono in un canale vengono archiviati nel sito di SharePoint del team. Pertanto, è necessario mettere in attesa la cassetta postale e il sito SharePoint Microsoft Team per conservare le conversazioni e i file in un canale.
  
- In alternativa, le conversazioni che fanno parte dell'elenco Chat in Microsoft Teams vengono archiviate nella cassetta postale degli utenti che partecipano alla chat.  I file condivisi da un utente nelle conversazioni di Chat vengono archiviati nel OneDrive for Business dell'utente che condivide il file. Pertanto, è necessario mettere in attesa le singole cassette postali OneDrive for Business utenti e i siti per conservare le conversazioni e i file nell'elenco Chat. 
  
- Ogni team o canale del team Microsoft contiene un Wiki per prendere nota e collaborare. Il contenuto Wiki viene salvato automaticamente in un file con formato MHT. Il file è archiviato nella raccolta documenti di dati Wiki di Teams nel sito di SharePoint del team. È possibile bloccare il contenuto del Wiki bloccando il sito di SharePoint del team.

  > [!NOTE]
  > La possibilità di conservare il contenuto Wiki per un team Microsoft o un canale del team (quando si mette in attesa il sito di SharePoint del team) è stata rilasciata il 22 giugno 2017. Se un sito del team è in attesa, il contenuto wiki verrà conservato a partire da tale data. Tuttavia, se un sito del team è in attesa e il contenuto wiki è stato eliminato prima del 22 giugno 2017, il contenuto wiki non è stato conservato.
