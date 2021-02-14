---
title: Gestire i blocchi in Advanced eDiscovery
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
description: Informazioni su come conservare i responsabile e le relative origini dati per conservare il contenuto pertinente per il caso di Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f56d12b6d69e56e85f0e7ad37fbf65746a1cff23
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024736"
---
# <a name="manage-holds-in-advanced-ediscovery"></a>Gestire i blocchi in Advanced eDiscovery

È possibile utilizzare un caso di Advanced eDiscovery per creare esenzioni per conservare il contenuto che potrebbe essere rilevante per il caso. Utilizzando le funzionalità di blocco di Advanced eDiscovery, è possibile inserire i blocchi sui responsabile e sulle relative origini dati. Inoltre, è possibile impostare un blocco non di tipo responsabile per le cassette postali e i siti di OneDrive for Business. È inoltre possibile impostare un blocco sulla cassetta postale del gruppo, sul sito di SharePoint e sul sito di OneDrive for Business per un gruppo di Microsoft 365. Analogamente, è possibile impostare un blocco sulla cassetta postale e sul sito associati a Microsoft Teams. Quando si posizionano i percorsi di contenuto in attesa, il contenuto viene mantenuto fino a quando non si rilascia il responsabile, si rimuove una posizione dati specifica o si elimina completamente il criterio di blocco.

## <a name="manage-custodian-based-holds"></a>Gestire le esenzioni basate sui responsabile

In alcuni casi, potresti avere un set di responsabile che hai identificato e che hai deciso di conservare i loro dati durante il caso. In Advanced eDiscovery, quando questi responsabile vengono messi in attesa, l'utente e le origini dati selezionate vengono aggiunti automaticamente a un criterio di blocco dei depositario.

Per visualizzare il criterio di blocco del responsabile:

1. Nel Centro conformità Microsoft 365 fare clic su **eDiscovery > Avanzate** per visualizzare l'elenco dei casi nell'organizzazione.

2. Vai alla scheda **Sources** per aggiungere i responsabile all'interno del tuo caso. Per informazioni su come aggiungere e mettere in attesa i responsabile all'interno di un caso di Advanced eDiscovery, vedere [Aggiungere i responsabile a un caso.](add-custodians-to-case.md) Se i responsabile sono già stati aggiunti e sono stati messi in attesa, andare al passaggio 3.

3. Passare alla scheda **Esenzioni** e fare **clic su \<HoldId> CustodianHold.**

4. Nella pagina del riquadro a comparsa è possibile visualizzare le statistiche di blocco per il criterio. È inoltre possibile eseguire azioni come applicare una query all'esenzione basata sul responsabile. Per ulteriori informazioni sulla creazione di una query di blocco e sull'utilizzo di condizioni, vedere Query con parole chiave [e condizioni di ricerca per Ricerca contenuto.](keyword-queries-and-search-conditions.md)

## <a name="manage-non-custodial-holds"></a>Gestire i blocchi non di tipo responsabile

Quando si crea un'esenzione, sono disponibili le opzioni seguenti per impostare l'ambito del contenuto nei percorsi di contenuto specificati:

- Si crea un'esenzione infinita in cui tutto il contenuto viene messo in attesa. In alternativa, è possibile creare un'esenzione basata su query in cui viene sospeso solo il contenuto che corrisponde a una query di ricerca.
  
- È possibile specificare un intervallo di date per contenere solo il contenuto inviato, ricevuto o creato entro tale intervallo di date. In alternativa, è possibile contenere tutto il contenuto indipendentemente da quando è stato inviato, ricevuto o creato.

Per creare un blocco non responsabile per un caso di Advanced eDiscovery:

1. Nel Centro conformità Microsoft 365 fare clic su **eDiscovery > Avanzate** per visualizzare l'elenco dei casi nell'organizzazione.
  
2. Fare **clic** su Apri accanto al caso in cui si desidera creare le esenzioni.
  
3. Nella home page del caso fare clic sulla **scheda Esenzioni.**
  
4. Nella scheda **Esenzioni** fare clic su **Crea.**
  
5. Nella pagina **Assegna un nome all'esenzione.** Il nome del blocco deve essere univoco nell'organizzazione.
 
6. (Facoltativo) Nella casella **Descrizione** aggiungere una descrizione dell'esenzione.
  
7. Fare clic su **Avanti**.
  
8. Scegliere i percorsi di contenuto che si desidera mettere in attesa. È possibile mantenere le cassette postali, i siti e le cartelle pubbliche.

   1. **Posta elettronica di Exchange:** fare clic su Scegli **utenti, gruppi** o team, quindi fare di nuovo clic su Scegli **utenti, gruppi o team** per specificare le cassette postali da mettere in attesa. Utilizzare la casella di ricerca per trovare le cassette postali degli utenti e i gruppi di distribuzione (per mettere un blocco sulle cassette postali dei membri del gruppo) da mettere in attesa. È inoltre possibile impostare un blocco sulla cassetta postale associata per un gruppo di Microsoft 365 o un team di Microsoft. Selezionare l'utente, il gruppo, la casella di controllo del team, **fare clic su Scegli** e quindi su **Fine.**
 
      > [!NOTE]
      > Quando si fa **clic su Choose users, groups, or teams** to specify mailboxes to place on hold, the mailbox picker that's displayed is empty. Si tratta di un'impostazione predefinita per migliorare le prestazioni. Per aggiungere persone all'elenco, digitare un nome (minimo 3 caratteri) nella casella di ricerca.

   1. **Siti di SharePoint:** fare  clic su Scegli siti e quindi fare di nuovo clic su Scegli siti per specificare i siti di SharePoint e OneDrive for Business da mettere in attesa.  Digitare l'URL per ogni sito che si desidera conservare. È inoltre possibile aggiungere l'URL per il sito di SharePoint per un gruppo di Microsoft 365 o un team di Microsoft. Fare **clic su** Scegli e quindi su **Fine.**
    
      Vedere la **sezione domande** frequenti per suggerimenti su come mettere in attesa i gruppi di Microsoft 365 e Microsoft Teams.

      > [!NOTE]
      > L'URL dell'account OneDrive di un utente include il nome dell'entità utente (UPN), ad esempio `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` . Nel raro caso in cui l'UPN di una persona viene modificato, anche l'URL di OneDrive cambierà per incorporare il nuovo UPN. Se l'account Di OneDrive di un utente fa parte di un blocco non responsabile e il relativo UPN viene modificato, è necessario aggiornare il blocco e puntare al nuovo URL di OneDrive. Per altre informazioni, vedere [Come le modifiche UPN influiscono sull'URL di OneDrive](https://docs.microsoft.com/onedrive/upn-changes).

   1. **Cartelle pubbliche di Exchange** - Spostare l'interruttore attiva/disattiva nella posizione Tutti per mettere in attesa tutte le cartelle pubbliche nell'organizzazione di Exchange Online. Si noti che non è possibile scegliere cartelle pubbliche specifiche da mettere in attesa. Lasciare l'interruttore Attiva/Disattiva impostato su **Nessuno** se non si desidera attivare un'esenzione per le cartelle pubbliche.

9. Dopo aver aggiunto i percorsi di contenuto all'esenzione, fare clic su **Avanti.**
  
10. Per creare un'esenzione basata su query con condizioni, completare le operazioni seguenti. In caso contrario, fare clic su **Avanti.**
    
    - Nella casella sotto **Parole** chiave digitare una query di ricerca nella casella in modo che solo il contenuto che soddisfa i criteri di ricerca sia messo in attesa. È possibile specificare parole chiave, proprietà dei messaggi o proprietà del documento, ad esempio nomi di file. È inoltre possibile utilizzare query più complesse che utilizzano un operatore booleano, ad esempio AND, OR o NOT. Se si lascia vuota la casella delle parole chiave, tutto il contenuto che si trova nei percorsi di contenuto specificati verrà messo in attesa.

    - Fare  **clic su** Aggiungi condizioni per aggiungere una o più condizioni per restringere la query di ricerca per l'esenzione. Ogni condizione aggiunge una clausola alla query di ricerca KQL creata ed eseguita quando si crea l'esenzione. Ad esempio, è possibile specificare un intervallo di date in modo che i messaggi di posta elettronica o i documenti del sito creati entro l'intervallo di date siano messi in attesa. Una condizione è collegata logicamente alla query con parola chiave (specificata nella relativa casella) dall'operatore AND. Ciò significa che gli elementi devono soddisfare sia la query con parole chiave che la condizione da mantenere.

     Per ulteriori informazioni sulla creazione di una query di ricerca e sull'utilizzo di condizioni, vedere Query con parole chiave [e condizioni di ricerca per Ricerca contenuto.](https://docs.microsoft.com/office365/SecurityCompliance/keyword-queries-and-search-conditions)

11. Dopo aver configurato un blocco basato su query, fare clic su **Avanti.**

12. Rivedere le impostazioni e quindi fare clic su **Crea blocco.**

## <a name="view-hold-statistics"></a>Visualizzare le statistiche relative all'esenzione

Dopo un certo periodo di tempo, le informazioni sulla  nuova esenzione vengono visualizzate nel riquadro dei dettagli nella scheda Esenzioni per l'esenzione selezionata. Queste informazioni includono il numero di cassette postali e siti in attesa e le statistiche sul contenuto che è stato messo in attesa, ad esempio il numero totale e le dimensioni degli elementi messi in attesa e l'ultima volta in cui sono state calcolate le statistiche di blocco. Queste statistiche di blocco consentono di identificare la quantità di contenuto correlato al caso di eDiscovery.

Tenere presente quanto segue sulle statistiche di blocco:

- Il numero totale di elementi in attesa indica il numero di elementi di tutte le origini di contenuto che vengono messi in attesa. Se è stata creata un'esenzione basata su query, questa statistica indica il numero di elementi che corrispondono alla query.
  
- Il numero di elementi in attesa include anche gli elementi non indicizzati trovati nei percorsi del contenuto. Si noti che se si crea un'archiviazione basata su query, tutti gli elementi non indicizzati nei percorsi del contenuto vengono messi in attesa. Sono inclusi gli elementi non indicizzati che non corrispondono ai criteri di ricerca di un'esenzione basata su query e gli elementi non indicizzati che potrebbero non rientrare in una condizione di intervallo di date. Ciò è diverso da quello che accade quando si esegue una ricerca di contenuto, in cui gli elementi non indicizzati che non corrispondono alla query di ricerca o sono esclusi da una condizione di intervallo di date non vengono inclusi nei risultati della ricerca. Per ulteriori informazioni sugli elementi non indicizzati, vedere Elementi parzialmente [indicizzati in Ricerca contenuto in Office 365.](partially-indexed-items-in-content-search.md) 

- È possibile ottenere le statistiche di blocco più recenti facendo clic su Aggiorna statistiche per eseguire di nuovo una stima della ricerca che calcola il numero corrente di elementi in attesa.

- Se necessario, fare clic su Aggiorna sulla barra degli strumenti per aggiornare le statistiche di blocco nel riquadro dei dettagli.

- È normale che il numero di elementi in attesa aumenti nel tempo perché gli utenti la cui cassetta postale o sito è in attesa in genere inviano o ricevono nuovi messaggi di posta elettronica e creano nuovi documenti di SharePoint e OneDrive for Business.

- Se un sito di SharePoint o un account di OneDrive viene spostato in un'area geografica diversa in un ambiente multi-geografico, le statistiche per tale sito non verranno incluse nelle statistiche di blocco. Tuttavia, il contenuto del sito continuerà a essere in attesa. Inoltre, se un sito viene spostato in un'area geografica diversa, l'URL visualizzato nell'esenzione non verrà aggiornato. You'll have to edit the hold and update the URL.

## <a name="place-a-hold-on-microsoft-teams-and-office-365-groups"></a>Blocco su Microsoft Teams e gruppi di Office 365

Microsoft Teams si basa sui gruppi di Office 365. Pertanto, la loro conservazione in Advanced eDiscovery è molto simile. 

- **Come si esegue il mapping di un altro sito gruppi di Microsoft 365 o Microsoft Teams a un responsabile? E per quanto riguarda l'applicazione di un blocco non responsabile ai gruppi di Microsoft 365 e a Microsoft Teams?** Microsoft Teams si basa sui gruppi di Microsoft 365. Pertanto, la loro conservazione in un caso di eDiscovery è molto simile. Tenere presente quanto segue quando si posizionano i gruppi di Microsoft 365 e Microsoft Teams in attesa.
  - Per mettere in attesa il contenuto nei gruppi di Microsoft 365 e Microsoft Teams, è necessario specificare la cassetta postale e il sito di SharePoint associati a un gruppo o team.
  
  - Eseguire il cmdlet **Get-UnifiedGroup** in Exchange Online per visualizzare le proprietà di un gruppo di Microsoft 365 o di Microsoft Team. Questo è un buon modo per ottenere l'URL del sito associato a un gruppo di Microsoft 365 o a un team di Microsoft. Ad esempio, il comando seguente consente di visualizzare le proprietà selezionate per un gruppo di Microsoft 365 denominato Senior Leadership Team:


    ```console
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Per eseguire il cmdlet Get-UnifiedGroup, è necessario avere il ruolo Destinatari di sola lettura in Exchange Online o essere membri di un gruppo di ruoli assegnato al ruolo Destinatari di sola lettura.

 - Quando si esegue la ricerca nella cassetta postale di un utente, non verrà cercata la cassetta postale di un gruppo di Microsoft 365 o di Microsoft Team di cui l'utente è membro. Analogamente, quando si applica un blocco a un gruppo di Microsoft 365 o a Microsoft Team, solo la cassetta postale del gruppo e il sito del gruppo vengono messi in attesa; le cassette postali e i siti di OneDrive for Business dei membri del gruppo non vengono messi in attesa, a meno che non vengano esplicitamente aggiunti come amministratori o non venga impostata la conservazione delle origini dati. Pertanto, se è necessario mettere in attesa un gruppo di Microsoft 365 o microsoft team per un responsabile specifico, è consigliabile mappare il sito del gruppo e la cassetta postale del gruppo al responsabile (vedere Gestione dei responsabile in Advanced eDiscovery). Se il gruppo di Microsoft 365 o il team di Microsoft non è attribuibile a un singolo responsabile, prendere in considerazione l'aggiunta dell'origine a un blocco non responsabile. 
 
 - Per ottenere un elenco dei membri di un gruppo di Microsoft 365 o microsoft team, è possibile visualizzare le proprietà nella pagina Home > Gruppi nell'interfaccia di amministrazione di Microsoft 365. In alternativa, è possibile eseguire il comando seguente in PowerShell di Exchange Online:

   ```powershell
   Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
   ```

    > [!NOTE]
    > Per eseguire il cmdlet **Get-UnifiedGroupLinks**, è necessario avere il ruolo Destinatari di sola lettura in Exchange Online o essere membri di un gruppo di ruoli assegnato al ruolo Destinatari di sola lettura.

- Le conversazioni di canale che fanno parte di un canale di Microsoft Teams vengono archiviate nella cassetta postale associata al team. Allo stesso modo, i file che i membri del team condividono in un canale vengono archiviati nel sito di SharePoint del team. Pertanto, è necessario conservare la cassetta postale di Microsoft Team e il sito di SharePoint per conservare conversazioni e file in un canale.
  
- In alternativa, le conversazioni che fanno parte dell'elenco chat in Microsoft Teams vengono archiviate nella cassetta postale degli utenti che partecipano alla chat.  I file condivisi da un utente nelle conversazioni di chat vengono archiviati nel sito di OneDrive for Business dell'utente che condivide il file. Pertanto, è necessario conservare le cassette postali dei singoli utenti e i siti di OneDrive for Business per conservare le conversazioni e i file nell'elenco chat. 
  
- Ogni canale del team o del team di Microsoft contiene un wiki per la raccolta di note e la collaborazione. Il contenuto Wiki viene salvato automaticamente in un file con formato MHT. Il file è archiviato nella raccolta documenti di dati Wiki di Teams nel sito di SharePoint del team. È possibile mettere in attesa il contenuto del wiki mettendo in attesa il sito di SharePoint del team.

  > [!NOTE]
  > La possibilità di conservare il contenuto wiki per un canale di Microsoft Team o del team (quando si mette in attesa il sito di SharePoint del team) è stata rilasciata il 22 giugno 2017. Se un sito del team è in attesa, il contenuto del wiki verrà conservato a partire da tale data. Tuttavia, se un sito del team è in attesa e il contenuto wiki è stato eliminato prima del 22 giugno 2017, il contenuto wiki non è stato conservato.
