---
title: Eseguire ricerche nelle cassette postali basate sul cloud di utenti locali
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: Usare lo strumento Ricerca contenuto nel Centro sicurezza e conformità per cercare ed esportare i dati delle chat di Microsoft Teams (denominate chat 1xN) degli utenti locali in una distribuzione ibrida di Exchange.
ms.openlocfilehash: ab523c0d2d334d3d2366711e241b3bafa2e0002f
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352119"
---
# <a name="searching-cloud-based-mailboxes-for-on-premises-users"></a>Eseguire ricerche nelle cassette postali basate sul cloud di utenti locali

Se l'organizzazione ha una distribuzione ibrida di Exchange oppure sincronizza un'organizzazione di Exchange locale con Office 365 e ha abilitato Microsoft Teams, gli utenti possono usare l'applicazione di chat Teams per la messaggistica istantanea. Per un utente basato sul cloud, i dati delle chat di Teams, detti anche *chat 1xN*, vengono salvati nella cassetta postale principale basata sul cloud. Quando un utente locale usa l'applicazione di chat Teams, la sua cassetta postale principale è ubicata in locale. Per aggirare questa limitazione, Microsoft ha rilasciato una nuova funzionalità che consente di creare un'area di archiviazione basata sul cloud, denominata cassetta postale basata sul cloud per gli utenti locali, in cui archiviare i dati di chat di Teams per gli utenti locali. Questo consente di usare lo strumento Ricerca contenuto nel Centro sicurezza e conformità per cercare ed esportare i dati di chat di Teams per gli utenti locali. 
  
Di seguito sono elencati i requisiti e le limitazioni per la configurazione di cassette postali basate sul cloud per gli utenti locali:
  
- È necessario sincronizzare gli account utente del servizio directory locale, ad esempio Active Directory, con Azure Active Directory, il servizio directory di Microsoft 365. Questo vuol dire che in Microsoft 365 viene creato un account utente di posta elettronica, che viene associato a un utente la cui cassetta postale principale si trova nell'organizzazione locale.

- All'utente la cui cassetta postale principale si trova nell'organizzazione locale occorre assegnare una licenza di Microsoft Teams e almeno una licenza di Exchange Online Piano 1.

- La cassetta postale basata sul cloud per gli utenti locali viene usata solo per archiviare i dati di chat di Teams. Inoltre, un utente locale non può accedere alla cassetta postale basata sul cloud in alcun modo. Non è possibile usarla per inviare o ricevere messaggi di posta elettronica. 

- Per abilitare all'organizzazione per la ricerca di dati di chat di Teams nelle cassette postali basate sul cloud degli utenti locali, è necessario inviare una richiesta al Supporto tecnico Microsoft. Vedere [Presentare la richiesta di abilitare questa funzionalità al Supporto tecnico Microsoft](#filing-a-request-with-microsoft-support-to-enable-this-feature) in questo articolo. 

> [!NOTE]
> Le conversazioni che si svolgono nei canali di Teams vengono sempre archiviate nella cassetta postale basata sul cloud associata al team. Ciò significa che è possibile usare Ricerca contenuto per cercare conversazioni dei canali senza dover inviare una richiesta di supporto. Per altre informazioni sulla ricerca di conversazioni dei canali di Teams, vedere [Eseguire una ricerca nei Gruppi di Microsoft 365 e Microsoft Teams](content-search.md#searching-microsoft-teams-and-microsoft-365-groups).
  
## <a name="how-it-works"></a>Funzionamento

Se un utente abilitato per Microsoft Teams ha una cassetta postale locale e la sua identità/account utente è stato sincronizzato con il cloud, Microsoft crea una cassetta postale basata sul cloud per archiviare i dati delle 1xN di Teams. Dopo l'archiviazione nella cassetta postale basata sul cloud, i dati di chat di Teams vengono indicizzati per la ricerca. In questo modo è possibile usare Ricerca contenuto e le ricerche associate ai casi di eDiscovery per cercare, visualizzare in anteprima ed esportare i dati di chat di Teams per gli utenti locali. Per cercare dati delle chat di Teams per gli utenti locali è anche possibile usare i cmdlet **\*ComplianceSearch** in PowerShell per Centro sicurezza e conformità. 
  
L'immagine seguente mostra il flusso di lavoro che consente di cercare, visualizzare in anteprima ed esportare i dati delle chat di Teams per gli utenti locali.
  
![Spazio di archiviazione basato sul cloud per gli utenti locali in Microsoft Teams](../media/EHAMShard1.png)
  
Oltre a questa nuova funzionalità, si può continuare a usare Ricerca contenuto per cercare, visualizzare in anteprima ed esportare il contenuto di Teams nel sito di SharePoint basato sul cloud e nella cassetta postale di Exchange associata a ogni team di Microsoft Teams e dati delle chat 1xN di Teams in una cassetta postale di Exchange Online per gli utenti basati sul cloud.

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature"></a>Presentare la richiesta di abilitare questa funzionalità al Supporto tecnico Microsoft

Per cercare dati di chat di Teams nelle cassette postali basate sul cloud degli utenti locali, è necessario presentare al Supporto tecnico Microsoft la richiesta di abilitare l'organizzazione all'uso dell'interfaccia utente grafica nel Centro sicurezza e conformità. Questa funzionalità è disponibile in PowerShell per Centro sicurezza e conformità. Non è necessario inviare una richiesta di supporto per usare PowerShell per cercare dati delle chat di Teams degli utenti locali.
  
Includere le informazioni seguenti quando si invia la richiesta al Supporto tecnico Microsoft:
  
- Nome di dominio predefinito dell'organizzazione.

- Nome e ID del tenant dell'organizzazione. Queste informazioni sono disponibili nel portale di Azure Active Directory (in **Gestione** \> **Proprietà**). Vedere [Trovare l'ID tenant di Microsoft 365](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id).

- Il titolo seguente o la descrizione dello scopo della richiesta di supporto: "Abilitare la ricerca di contenuto dell'applicazione per gli utenti locali". Questo consentirà di instradare la richiesta al team di progettazione di eDiscovery che implementerà la richiesta.

Una volta apportata la modifica, il Supporto tecnico Microsoft invierà una data di distribuzione stimata. Il processo di distribuzione in genere richiede 2-3 settimane dopo l'invio della richiesta di supporto.
  
### <a name="what-happens-after-this-feature-is-enabled"></a>Cosa succede dopo l'abilitazione della funzionalità?

Dopo la distribuzione di questa funzionalità nell'organizzazione, vengono apportate le modifiche seguenti in Ricerca contenuto e nelle ricerche associate a un caso di eDiscovery nel Centro sicurezza e conformità:
  
- La casella di controllo **Aggiungi il contenuto delle app di Office per gli utenti locali** viene aggiunta sotto **Posizioni** in Ricerca contenuto.

    ![La casella di controllo Aggiungi il contenuto delle app di Office per gli utenti locali viene aggiunta all'interfaccia utente di Ricerca contenuto](../media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- Nel selettore delle posizioni dei contenuti usato per scegliere le cassette postali degli utenti in cui eseguire la ricerca vengono visualizzati gli utenti locali.

## <a name="searching-for-teams-chat-content-in-cloud-based-mailboxes-for-on-premises-users"></a>Cercare contenuto delle chat di Teams nelle cassette postali basate sul cloud di utenti locali

Una volta abilitata la funzionalità, è possibile usare Ricerca contenuto nel Centro sicurezza e conformità per cercare dati di chat di Teams nelle cassette postali basate sul cloud degli utenti locali.
  
1. Nel Centro sicurezza e conformità passare a **Ricerca** \> **Ricerca contenuto**.

2. Nella pagina **Ricerca** fare clic su ![Icona di aggiunta](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Nuova ricerca**.

    Come illustrato in precedenza, sotto **Posizioni** compare la casella di controllo **Aggiungi il contenuto delle app di Office per gli utenti locali**. Questa opzione è selezionata per impostazione predefinita.

3. Se necessario, creare la query con parole chiave e aggiungere condizioni alla query di ricerca. Per cercare solo dati di chat di Teams, è possibile aggiungere la query seguente nella casella **Parole chiave**:

    ```text
    kind:im
    ```

4. A questo punto, è possibile scegliere una delle opzioni seguenti in **Posizioni**:

    - **Tutte le posizioni:** selezionare questa opzione per cercare nelle cassette postali di tutti gli utenti dell'organizzazione. Quando la casella di controllo è selezionata, la ricerca verrà eseguita anche in tutte le cassette postali basate sul cloud degli utenti locali.

    - **Posizioni specifiche:** selezionare questa opzione e quindi fare clic su **Modifica** \> e scegliere l'utente, i gruppi o i team per cercare in cassette postali specifiche. Come descritto in precedenza, il selettore delle posizioni consente di cercare utenti locali.

5. Salvare ed eseguire la ricerca. I risultati della ricerca nelle cassette postali basate sul cloud degli utenti locali possono essere visualizzati in anteprima come qualsiasi altro risultato della ricerca. È anche possibile esportare i risultati della ricerca, inclusi i dati delle chat di Teams, in un file PST. Per altre informazioni, vedere: 

    - [Creare una ricerca](content-search.md#create-a-search)

    - [Visualizzare l'anteprima dei risultati della ricerca](content-search.md#preview-search-results)

    - [Esportare i risultati della Ricerca contenuto](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-in-cloud-based-mailboxes-for-on-premises-users"></a>Uso di PowerShell per cercare dati delle chat di Teams nelle cassette postali basate sul cloud di utenti locali

È possibile usare i cmdlet **New-ComplianceSearch** e **Set-ComplianceSearch** in PowerShell nel Centro sicurezza e conformità per eseguire ricerche nelle cassette postali basate sul cloud degli utenti locali. Come già detto, non è necessario inviare una richiesta di supporto per usare PowerShell per cercare dati delle chat di Teams degli utenti locali. 
  
1. [Connettersi a PowerShell in Centro sicurezza e conformità](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

2. Eseguire il comando di PowerShell seguente per creare una ricerca contenuto che cerchi nelle cassette postali basate sul cloud degli utenti locali.

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    Il parametro *IncludeUserAppContent* viene usato per specificare la cassetta postale basata sul cloud dell'utente o degli utenti specificati dal parametro *ExchangeLocation*. *AllowNotFoundExchangeLocationsEnabled* consente le cassette postali basate sul cloud degli utenti locali. Quando si usa il valore `$true` per questo parametro, la ricerca non tenta di verificare l'esistenza di una cassetta postale prima di procedere. Questo valore è obbligatorio per eseguire ricerche nelle cassette postali basate sul cloud degli utenti locali, perché le cassette postali di questo tipo non vengono risolte come quelle regolari.

    L'esempio seguente cerca chat di Teams, ossia messaggi istantanei, che contengono la parola chiave "redstone" nella cassetta postale basata sul cloud di Sara Davis, un utente locale nell'organizzazione Contoso.
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   Dopo aver creato una ricerca, assicurarsi di usare il cmdlet **Start-Get compliancesearch** per eseguirla. 
  
Per altre informazioni sull'uso di questi cmdlet, vedere:
  
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)

- [Set-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/set-compliancesearch)

- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/start-compliancesearch)

## <a name="known-issues"></a>Problemi noti

- Attualmente è possibile cercare, visualizzare in anteprima ed esportare il contenuto delle cassette postali basate sul cloud per gli utenti locali. È anche possibile applicare alla cassetta postale basata sul cloud di un utente locale un blocco associato a un caso di eDiscovery, oltre che applicare criteri di conservazione per le chat di Teams o i messaggi dei canali alle cassette postali basate sul cloud degli utenti locali. Al momento, tuttavia, non è possibile applicare criteri di conservazione per altre posizioni dei contenuti (ad esempio cassette postali di Exchange e siti di SharePoint), alle cassette postali basate sul cloud degli utenti locali.

## <a name="frequently-asked-questions"></a>Domande frequenti

 **Dove si trovano le cassette postali basate sul cloud degli utenti locali?**
  
Le cassette postali basate sul cloud vengono create e archiviate nello stesso data center dell'organizzazione.
  
 **Sono previsti altri requisiti oltre all'invio di una richiesta di supporto?**
  
 Come descritto in precedenza, occorre sincronizzare le identità degli utenti con cassette postali locali con l'organizzazione basata sul cloud, in modo che venga creato un account di posta elettronica corrispondente per ogni account utente locale in Office 365. L'organizzazione deve avere anche un abbonamento a Office 365 Enterprise, ad esempio un abbonamento a Office 365 Enterprise E1, E3 o E5.
  
 **Esiste il rischio di perdere i dati di chat di Teams se si esegue la migrazione della cassetta postale locale dell'utente nel cloud?**
  
No. Quando si esegue la migrazione nel cloud della cassetta postale principale di un utente locale, i dati delle chat di Teams di quell'utente verranno spostati nella nuova cassetta postale principale basata sul cloud.
  
 **È possibile applicare un blocco di eDiscovery o criteri di conservazione agli utenti locali?**
  
Sì. È possibile applicare criteri di conservazione o blocchi di eDiscovery per le chat di Teams e i messaggi dei canali alle cassette postali basate sul cloud degli utenti locali.
  
 **Ricerca contenuto è in grado di trovare chat di Teams meno recenti degli utenti locali, risalenti a prima che l'organizzazione inviasse la richiesta di abilitare questa funzionalità?**
  
Microsoft ha iniziato ad archiviare i dati delle chat di Teams per gli utenti locali il 31 gennaio 2018. Quindi, se l'identità di un utente di Teams locale è stata sincronizzata tra Active Directory e Azure Active Directory fin dalla data specificata, i dati delle sue chat di Teams sono archiviati in una cassetta postale basata sul cloud e sono disponibili per la ricerca con Ricerca contenuto. Microsoft sta lavorando anche all'archiviazione dei dati delle chat di Teams precedenti al 31 gennaio 2018 nelle cassette postali basate sul cloud degli utenti locali. Altre informazioni su questo argomento saranno disponibili a breve.

 **Gli utenti locali hanno bisogno di una licenza per archiviare i dati di chat di Teams in una cassetta postale basata sul cloud?**
  
Sì. Per archiviare i dati di chat di Teams per un utente locale in una cassetta postale basata sul cloud, occorre assegnare all'utente una licenza di Microsoft Teams e una licenza di Exchange Online Piano 1 in Office 365 (o Microsoft 365).
