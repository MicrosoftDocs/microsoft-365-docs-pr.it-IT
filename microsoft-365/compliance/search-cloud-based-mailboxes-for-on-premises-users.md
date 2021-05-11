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
description: Usare gli strumenti eDiscovery in Microsoft 365 per cercare ed esportare i dati delle chat di Teams per gli utenti locali in un'implementazione ibrida di Exchange.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ab59c179b62903dd5f1ddd9b718f81a1ac78923a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311802"
---
# <a name="search-for-teams-chat-data-for-on-premises-users"></a>Cercare i dati delle chat di Teams degli utenti locali

Se l'organizzazione ha una distribuzione ibrida di Exchange oppure sincronizza un'organizzazione di Exchange locale con Office 365 e ha abilitato Microsoft Teams, gli utenti locali possono usare l'applicazione di chat Teams per la messaggistica istantanea. Per un utente basato sul cloud, i dati delle chat di Teams, detti anche *chat 1x1 o 1xN*, vengono salvati nella cassetta postale principale basata sul cloud. Quando un utente locale usa l'applicazione di chat Teams, i messaggi della chat non possono essere archiviati nella sua cassetta postale principale, che è ubicata in locale. Per aggirare questa limitazione, Microsoft ha rilasciato una nuova funzionalità che consente di creare una risorsa di archiviazione basata sul cloud che consente di usare gli strumenti di eDiscovery per cercare ed esportare i dati delle chat di Teams degli utenti locali.
  
Di seguito sono elencati i requisiti e le limitazioni per l’abilitazione della risorsa di archiviazione basata sul cloud degli utenti locali:
  
- È necessario sincronizzare gli account utente del servizio directory locale, ad esempio Active Directory, con Azure Active Directory, il servizio directory di Microsoft 365. Questo vuol dire che in Microsoft 365 viene creato un account utente di posta elettronica, che viene associato a un utente la cui cassetta postale principale si trova nell'organizzazione locale.

- All'utente la cui cassetta postale principale si trova nell'organizzazione locale occorre assegnare una licenza di Microsoft Teams e almeno una licenza di Exchange Online Piano 1.

- Se l'organizzazione non dispone di una distribuzione ibrida di Exchange, è necessario sincronizzare lo schema di Exchange locale con Azure Active Directory. Se non lo fai, potresti rischiare di creare cassette postali basate su cloud duplicate in Exchange Online per gli utenti che dispongono di una cassetta postale nell'organizzazione di Exchange locale.

- Solo i dati delle chat di Teams associati all'utente locale vengono archiviati nella risorsa di archiviazione basata sul cloud. L’utente locale non può accedere alla risorsa di archiviazione in alcun modo.

> [!NOTE]
> Le conversazioni che si svolgono nei canali di Teams vengono sempre archiviate nella cassetta postale basata sul cloud associata al team, il che significa che è possibile cercare le conversazioni del canale. Per altre informazioni sulla ricerca di conversazioni dei canali di Teams, vedere [Eseguire una ricerca nei Gruppi di Microsoft 365 e Microsoft Teams](content-search-reference.md#searching-microsoft-teams-and-microsoft-365-groups).
  
## <a name="how-it-works"></a>Funzionamento

Se un utente abilitato per Microsoft Teams dispone di una cassetta postale locale e la sua identità/account utente è stata sincronizzata con il cloud, Microsoft crea una risorsa di archiviazione basata sul cloud per associare i dati delle chat 1xN di Teams dell’utente locale. I dati delle chat di team degli utenti locali sono indicizzati per la ricerca. In questo modo, è possibile usare Ricerca contenuto (e le ricerche associate ai casi di Core eDiscovery e Adavanced eDiscovery) per cercare, visualizzare in anteprima ed esportare i dati delle chat di Teams degli utenti locali. Per cercare dati delle chat di Teams per gli utenti locali è anche possibile usare i cmdlet **\*ComplianceSearch** in PowerShell per Centro sicurezza e conformità.
  
L'immagine seguente mostra il flusso di lavoro che consente di cercare, visualizzare in anteprima ed esportare i dati delle chat di Teams per gli utenti locali.
  
![Spazio di archiviazione basato sul cloud per gli utenti locali in Microsoft Teams](../media/EHAMShard1.png)
  
Oltre a questa funzionalità, è possibile usare gli strumenti eDiscovery per cercare, visualizzare in anteprima ed esportare i contenuti di Teams nel sito di SharePoint basato sul cloud e nella cassetta postale di Exchange associata ai dati delle chat di Microsoft Teams e delle chat 1xN di Teams in una cassetta postale di Exchange Online per gli utenti basati sul cloud.

### <a name="how-this-feature-is-supported-in-content-search-and-core-ediscovery-search-tools"></a>In che modo questa funzionalità è supportata in Ricerca contenuto e negli strumenti di ricerca Core eDiscovery

I seguenti elementi di interfaccia utente in Ricerca contenuto e nello strumento di ricerca associato ai casi Core eDiscovery nel Centro conformità Microsoft 365:
  
- La casella di controllo **Aggiungi il contenuto dell'app per gli utenti locali** viene visualizzata nella pagina della procedura guidata di **Posizioni** nello strumento Ricerca contenuto ed è selezionata per impostazione predefinita. Mantenere selezionata questa casella di controllo per includere lo spazio di archiviazione basato sul cloud per gli utenti locali in una ricerca di contenuto.

    ![La casella di controllo "Aggiungi il contenuto delle app Office per gli utenti locali" viene aggiunta all'interfaccia utente di Ricerca contenuto](../media/EHAMShardCheckBox.png)
  
- È possibile cercare utenti locali quando si scelgono utenti specifici da cercare.

## <a name="searching-for-teams-chat-content-for-on-premises-users"></a>Cercare contenuto delle chat di Teams degli utenti locali

Ecco come usare Ricerca contenuto nel Centro conformità Microsoft 365 per cercare i dati delle chat di Teams per gli utenti locali.
  
1. Nel Centro conformità Microsoft 365, passare a **Ricerca contenuto**.

2. Nella scheda **Ricerche** fare clic su **Nuova ricerca** e assegnare un nome alla nuova ricerca.

3. Nella pagina **Posizioni** impostare l'interruttore su **attivato per** cassette postali di Exchange. Si noti che la casella di controllo **Aggiungi il contenuto dell'app per gli utenti locali** è visualizzata e selezionata per impostazione predefinita.

4. Per cercare contenuti di Teams per utenti specifici, selezionare **Scegli utenti, gruppi o team** e scegliere utenti specifici da includere nella ricerca. In caso contrario, fare click su **Successivo** per cercare il contenuto di Teams per tutti gli utenti, inclusi gli utenti locali.

5. Nella pagina **Definisci le tue condizioni di ricerca** digitare una query con parole chiave e, se necessario, aggiungere condizioni alla query di ricerca. Per cercare solo dati di chat di Teams, è possibile aggiungere la query seguente nella casella **Parole chiave**:

    ```text
    kind:im AND kind:microsoftteams
    ```

6. Salvare ed eseguire la ricerca. È possibile visualizzare in anteprima i risultati della ricerca degli utenti locali come qualsiasi altro risultato della ricerca. È anche possibile esportare i risultati della ricerca, inclusi i dati delle chat di Teams, in un file PST. Per altre informazioni, vedere:

    - [Creare una ricerca](content-search.md)

    - [Visualizzare l'anteprima dei risultati della ricerca](preview-ediscovery-search-results.md)

    - [Esportare i risultati della ricerca](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-for-on-premises-users"></a>Usare PowerShell per cercare i dati delle chat di Teams degli utenti locali

È possibile usare i cmdlet **New-ComplianceSearch** e **Set-ComplianceSearch** in PowerShell nel Centro sicurezza e conformità per cercare i dati delle chat di Teams degli utenti locali. Come già detto, non è necessario inviare una richiesta di supporto per usare PowerShell per cercare dati delle chat di Teams degli utenti locali.
  
1. [Connettersi a PowerShell in Centro sicurezza e conformità](/powershell/exchange/connect-to-scc-powershell).

2. Eseguire il comando di PowerShell seguente per creare una ricerca contenuto che cerchi i dati delle chat di Teams degli utenti locali.

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    Il parametro *IncludeUserAppContent* viene usato per specificare la risorsa di archiviazione basata sul cloud dell'utente o degli utenti specificati dal parametro *ExchangeLocation*. *AllowNotFoundExchangeLocationsEnabled* consente la ricerca della risorsa di archiviazione basata sul cloud degli utenti locali. Quando si usa il valore `$true` per questo parametro, la ricerca non tenta di verificare l'esistenza di una cassetta postale prima di procedere. Questo valore è obbligatorio per eseguire la ricerca della risorsa di archiviazione basata sul cloud per gli utenti locali, perché questa risorsa di archiviazione non viene risolta come una normale cassetta postale basata sul cloud.

    L'esempio seguente cerca chat di Teams che contengono la parola chiave "redstone" nella risorsa di archiviazione basata sul cloud di Sara Davis, un utente locale nell'organizzazione Contoso.
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND (kind:im AND kind:microsoftteams)" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   Dopo aver creato una ricerca, assicurarsi di usare il cmdlet **Start-Get compliancesearch** per eseguirla.
  
Per altre informazioni sull'uso di questi cmdlet, vedere:
  
- [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch)

- [Set-ComplianceSearch](/powershell/module/exchange/set-compliancesearch)

- [Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch)

## <a name="known-issues"></a>Problemi noti

- Attualmente è possibile cercare, visualizzare in anteprima ed esportare i dati delle chat di Teams degli utenti locali. È anche possibile applicare ai dati delle chat di Teams degli utenti locali un blocco associato a un caso di Core o Advanced eDiscovery, oltre che applicare criteri di conservazione per le chat di Teams o i messaggi degli utenti locali. Al momento, tuttavia, non è possibile applicare criteri di conservazione per altre posizioni dei contenuti (ad esempio cassette postali di Exchange e siti di SharePoint) degli utenti locali.

## <a name="frequently-asked-questions"></a>Domande frequenti

**Devo inviare una richiesta di supporto per cercare i messaggi di chat per gli utenti locali?**

No. Questa funzionalità viene abilitata per impostazione predefinita per tutte le organizzazioni. A un certo punto, sarà necessario contattare il Supporto tecnico Microsoft, ma non è ancora il momento.
  
 **Gli strumenti eDiscovery possono trovare i dati delle chat di Teams più vecchi per gli utenti locali prima che questa funzionalità venisse abilitata per impostazione predefinita per tutte le organizzazioni?**
  
Microsoft ha iniziato ad archiviare i dati della chat di Teams per gli utenti locali il 31 gennaio 2018. Quindi, se l'identità di un utente di Teams locale è stata sincronizzata tra Windows Server Active Directory e Azure Active Directory locali fin dalla data specificata in Microsoft 365, i dati delle chat di Teams sono archiviati nel cloud e sono disponibili per la ricerca tramite gli strumenti eDiscovery.

 **Gli utenti locali hanno bisogno di una licenza per archiviare i loro dati delle chat di Teams nel cloud?**
  
Si. Per archiviare i dati delle chat di Teams di un utente locale in una risorsa di archiviazione basata sul cloud, occorre assegnare all'utente una licenza di Microsoft Teams e una licenza di un’offerta Exchange Online in Office 365 (o Microsoft 365).

**Dove si trova la risorsa di archiviazione basata sul cloud per gli utenti locali?**
  
I dati delle chat di Teams vengono archiviati nel file PDL (Preferred Data Location) per un utente locale. Il file PDL viene rispettato negli ambienti a singola geo e multi geo. Per ulteriori informazioni, vedere [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).

**Esiste il rischio di perdere i dati di chat di Teams se si esegue la migrazione della cassetta postale locale dell'utente nel cloud?**
  
No. Quando si esegue la migrazione nel cloud della cassetta postale principale di un utente locale, i dati delle chat di Teams di quell'utente verranno spostati nella nuova cassetta postale principale basata sul cloud.
  
 **È possibile applicare un blocco di eDiscovery o criteri di conservazione agli utenti locali?**
  
Sì. È possibile applicare criteri di conservazione o blocchi di eDiscovery alle chat di Teams e ai messaggi del canale degli utenti locali. Tuttavia, per preservare o conservare i contenuti di Teams per gli utenti locali, un utente locale deve disporre di una licenza Exchange Online Plan 2.
