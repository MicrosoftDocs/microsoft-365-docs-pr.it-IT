---
title: Cercare i dati delle chat di Teams degli utenti locali
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
description: Usare lo strumento Ricerca contenuto nel Centro sicurezza e conformità per cercare ed esportare i dati delle chat di Microsoft Teams degli utenti locali in una distribuzione ibrida di Exchange.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 39951ce125f86748beab12cf1998075e26ad734b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917188"
---
# <a name="search-for-teams-chat-data-for-on-premises-users"></a>Cercare i dati delle chat di Teams degli utenti locali

Se l'organizzazione ha una distribuzione ibrida di Exchange oppure sincronizza un'organizzazione di Exchange locale con Office 365 e ha abilitato Microsoft Teams, gli utenti locali possono usare l'applicazione di chat Teams per la messaggistica istantanea. Per un utente basato sul cloud, i dati delle chat di Teams, detti anche *chat 1x1 o 1xN*, vengono salvati nella cassetta postale principale basata sul cloud. Quando un utente locale usa l'applicazione di chat Teams, i messaggi della chat non possono essere archiviati nella sua cassetta postale principale, che è ubicata in locale. Per aggirare questa limitazione, Microsoft ha rilasciato una nuova funzionalità che consente di creare una risorsa di archiviazione basata sul cloud che consente di usare gli strumenti di eDiscovery per cercare ed esportare i dati delle chat di Teams degli utenti locali.
  
Di seguito sono elencati i requisiti e le limitazioni per l’abilitazione della risorsa di archiviazione basata sul cloud degli utenti locali:
  
- È necessario sincronizzare gli account utente del servizio directory locale, ad esempio Active Directory, con Azure Active Directory, il servizio directory di Microsoft 365. Questo vuol dire che in Microsoft 365 viene creato un account utente di posta elettronica, che viene associato a un utente la cui cassetta postale principale si trova nell'organizzazione locale.

- All'utente la cui cassetta postale principale si trova nell'organizzazione locale occorre assegnare una licenza di Microsoft Teams e almeno una licenza di Exchange Online Piano 1.

- Se l'organizzazione non dispone di una distribuzione ibrida di Exchange, è necessario sincronizzare lo schema di Exchange locale con Azure Active Directory. Se non lo fai, potresti rischiare di creare cassette postali basate su cloud duplicate in Exchange Online per gli utenti che dispongono di una cassetta postale nell'organizzazione di Exchange locale.

- Solo i dati delle chat di Teams associati all’utente locale sono archiviati nella risorsa di archiviazione basata sul cloud. L’utente locale non può accedere alla risorsa di archiviazione in alcun modo.

> [!NOTE]
> Le conversazioni che si svolgono nei canali di Teams vengono sempre archiviate nella cassetta postale basata sul cloud associata al team, il che significa che è possibile cercare le conversazioni del canale. Per altre informazioni sulla ricerca di conversazioni dei canali di Teams, vedere [Eseguire una ricerca nei Gruppi di Microsoft 365 e Microsoft Teams](content-search.md#searching-microsoft-teams-and-microsoft-365-groups).
  
## <a name="how-it-works"></a>Funzionamento

Se un utente abilitato per Microsoft Teams dispone di una cassetta postale locale e la sua identità/account utente è stata sincronizzata con il cloud, Microsoft crea una risorsa di archiviazione basata sul cloud per associare i dati delle chat 1xN di Teams dell’utente locale. I dati delle chat di team degli utenti locali sono indicizzati per la ricerca. In questo modo è possibile usare Ricerca contenuto e le ricerche associate ai casi di eDiscovery Core and Adavanced per cercare, visualizzare in anteprima ed esportare i dati delle chat di Teams degli utenti locali. Per cercare dati delle chat di Teams per gli utenti locali è anche possibile usare i cmdlet **\*ComplianceSearch** in PowerShell per Centro sicurezza e conformità.
  
L'immagine seguente mostra il flusso di lavoro che consente di cercare, visualizzare in anteprima ed esportare i dati delle chat di Teams per gli utenti locali.
  
![Spazio di archiviazione basato sul cloud per gli utenti locali in Microsoft Teams](../media/EHAMShard1.png)
  
Oltre a questa nuova funzionalità, si può continuare a usare Ricerca contenuto per cercare, visualizzare in anteprima ed esportare il contenuto di Teams nel sito di SharePoint basato sul cloud e nella cassetta postale di Exchange associata a ogni team di Microsoft Teams e dati delle chat 1xN di Teams in una cassetta postale di Exchange Online per gli utenti basati sul cloud.


### <a name="what-happens-after-this-feature-is-enabled"></a>Cosa succede dopo l'abilitazione della funzionalità?

Dopo la distribuzione di questa funzionalità nell'organizzazione, vengono apportate le modifiche seguenti in Ricerca contenuto e nelle ricerche associate a un caso di eDiscovery nel Centro sicurezza e conformità:
  
- La casella di controllo **Aggiungi il contenuto delle app di Office per gli utenti locali** viene aggiunta sotto **Posizioni** in Ricerca contenuto.

    ![La casella di controllo Aggiungi il contenuto delle app di Office per gli utenti locali viene aggiunta all'interfaccia utente di Ricerca contenuto](../media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- Nel selettore delle posizioni dei contenuti usato per scegliere le cassette postali degli utenti in cui eseguire la ricerca vengono visualizzati gli utenti locali.

## <a name="searching-for-teams-chat-content-for-on-premises-users"></a>Cercare contenuto delle chat di Teams degli utenti locali

Una volta abilitata la funzionalità, è possibile usare Ricerca contenuto nel Centro sicurezza e conformità per cercare dati delle chat di Teams degli utenti locali.
  
1. Nel Centro sicurezza e conformità passare a **Ricerca** \> **Ricerca contenuto**.

2. Nella pagina **Ricerca** fare clic su ![Icona di aggiunta](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Nuova ricerca**.

    Come illustrato in precedenza, sotto **Posizioni** compare la casella di controllo **Aggiungi il contenuto delle app di Office per gli utenti locali**. Questa opzione è selezionata per impostazione predefinita.

3. Se necessario, creare la query con parole chiave e aggiungere condizioni alla query di ricerca. Per cercare solo dati di chat di Teams, è possibile aggiungere la query seguente nella casella **Parole chiave**:

    ```text
    kind:im
    ```

4. A questo punto, è possibile scegliere una delle opzioni seguenti in **Posizioni**:

    - **Tutte le posizioni:** selezionare questa opzione per cercare nelle cassette postali di tutti gli utenti dell'organizzazione. Quando la casella di controllo è selezionata, la ricerca verrà eseguita anche in tutte le risorse di archiviazione dei dati delle chat di Teams per gli utenti locali.

    - **Posizioni specifiche:** selezionare questa opzione e quindi fare clic su **Modifica** \> e scegliere l'utente, i gruppi o i team per cercare cassette postali specifiche. Come descritto in precedenza, il selettore delle posizioni consente di cercare i dati delle chat di Teams degli utenti locali.

5. Salvare ed eseguire la ricerca. È possibile visualizzare in anteprima i risultati della ricerca degli utenti locali come qualsiasi altro risultato della ricerca. È anche possibile esportare i risultati della ricerca, inclusi i dati delle chat di Teams, in un file PST. Per altre informazioni, vedere:

    - [Creare una ricerca](content-search.md#create-a-search)

    - [Visualizzare l'anteprima dei risultati della ricerca](content-search.md#preview-search-results)

    - [Esportare i risultati della Ricerca contenuto](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-for-on-premises-users"></a>Usare PowerShell per cercare i dati delle chat di Teams degli utenti locali

È possibile usare i cmdlet **New-ComplianceSearch** e **Set-ComplianceSearch** in PowerShell nel Centro sicurezza e conformità per cercare i dati delle chat di Teams degli utenti locali. Come già detto, non è necessario inviare una richiesta di supporto per usare PowerShell per cercare dati delle chat di Teams degli utenti locali.
  
1. [Connettersi a PowerShell in Centro sicurezza e conformità](/powershell/exchange/connect-to-scc-powershell).

2. Eseguire il comando di PowerShell seguente per creare una ricerca contenuto che cerchi i dati delle chat di Teams degli utenti locali.

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    Il parametro *IncludeUserAppContent* viene usato per specificare la risorsa di archiviazione basata sul cloud dell'utente o degli utenti specificati dal parametro *ExchangeLocation*. *AllowNotFoundExchangeLocationsEnabled* consente la ricerca della risorsa di archiviazione basata sul cloud degli utenti locali. Quando si usa il valore `$true` per questo parametro, la ricerca non tenta di verificare l'esistenza di una cassetta postale prima di procedere. Questo valore è obbligatorio per eseguire la ricerca della risorsa di archiviazione basata sul cloud per gli utenti locali, perché questa risorsa di archiviazione non viene risolta come una normale cassetta postale basata sul cloud.

    L'esempio seguente cerca chat di Teams, ossia messaggi istantanei, che contengono la parola chiave "redstone" nella risorsa di archiviazione basata sul cloud di Sara Davis, un utente locale nell'organizzazione Contoso.
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   Dopo aver creato una ricerca, assicurarsi di usare il cmdlet **Start-Get compliancesearch** per eseguirla. 
  
Per altre informazioni sull'uso di questi cmdlet, vedere:
  
- [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch)

- [Set-ComplianceSearch](/powershell/module/exchange/set-compliancesearch)

- [Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch)

## <a name="known-issues"></a>Problemi noti

- Attualmente è possibile cercare, visualizzare in anteprima ed esportare i dati delle chat di Teams degli utenti locali. È anche possibile applicare ai dati delle chat di Teams degli utenti locali un blocco associato a un caso di Core o Advanced eDiscovery, oltre che applicare criteri di conservazione per le chat di Teams o i messaggi degli utenti locali. Al momento, tuttavia, non è possibile applicare criteri di conservazione per altre posizioni dei contenuti (ad esempio cassette postali di Exchange e siti di SharePoint) degli utenti locali.

## <a name="frequently-asked-questions"></a>Domande frequenti

**Dove si trova la risorsa di archiviazione basata sul cloud per gli utenti locali?**
  
I dati delle chat di Teams vengono archiviati nel file PDL (Preferred Data Location) per un utente locale. Il file PDL viene rispettato negli ambienti a singola geo e multi geo. Per ulteriori informazioni, vedere [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).
  
 **Sono previsti altri requisiti oltre all'invio di una richiesta di supporto?**
  
Come descritto in precedenza, occorre sincronizzare le identità degli utenti con cassette postali locali con l'organizzazione basata sul cloud, in modo che venga creato un account di posta elettronica corrispondente per ogni account utente locale in Office 365. L'organizzazione deve avere anche un abbonamento a Office 365 Enterprise, ad esempio un abbonamento a Office 365 Enterprise E1, E3 o E5.
  
 **Esiste il rischio di perdere i dati di chat di Teams se si esegue la migrazione della cassetta postale locale dell'utente nel cloud?**
  
No. Quando si esegue la migrazione nel cloud della cassetta postale principale di un utente locale, i dati delle chat di Teams di quell'utente verranno spostati nella nuova cassetta postale principale basata sul cloud.
  
 **È possibile applicare un blocco di eDiscovery o criteri di conservazione agli utenti locali?**
  
Sì. È possibile applicare criteri di conservazione o blocchi di eDiscovery alle chat di Teams e ai messaggi del canale degli utenti locali.
  
 **Ricerca contenuto è in grado di trovare i dati delle chat di Teams meno recenti degli utenti locali, risalenti a prima che l'organizzazione inviasse la richiesta di abilitare questa funzionalità?**
  
Microsoft ha iniziato ad archiviare i dati delle chat di Teams degli utenti locali il 31 gennaio 2018. Quindi, se l'identità di un utente di Teams locale è stata sincronizzata tra Active Directory e Azure Active Directory fin dalla data specificata, i dati delle sue chat di Teams sono archiviati nel cloud e sono disponibili per la ricerca con Ricerca contenuto. Microsoft sta lavorando anche all'archiviazione dei dati delle chat di Teams precedenti al 31 gennaio 2018 nella risorsa di archiviazione basata sul cloud degli utenti locali. Altre informazioni su questo argomento saranno disponibili a breve.

 **Gli utenti locali hanno bisogno di una licenza per archiviare i loro dati delle chat di Teams nel cloud?**
  
Sì. Per archiviare i dati delle chat di Teams di un utente locale in una risorsa di archiviazione basata sul cloud, occorre assegnare all'utente una licenza di Microsoft Teams e una licenza di Exchange Online Piano in Office 365 (o Microsoft 365).