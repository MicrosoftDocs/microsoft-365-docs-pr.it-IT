---
title: Informazioni sui criteri di conservazione per Teams
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Informazioni sui criteri di conservazione applicabili a Microsoft Teams.
ms.openlocfilehash: 709d4414ebb01081172aff932899146c06d05a19
ms.sourcegitcommit: 47c45bd81afdc4867ff2980ced3df31dbad92b84
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268277"
---
# <a name="learn-about-retention-policies-for-microsoft-teams"></a>Informazioni sui criteri di conservazione per Microsoft Teams

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

Questo articolo integra [Informazioni sui criteri di conservazione](retention-policies.md) con informazioni specifiche per Microsoft Teams.

## <a name="how-a-retention-policy-works-with-microsoft-teams"></a>Funzionamento dei criteri di conservazione con Microsoft Teams

È possibile usare i criteri di conservazione per conservare i messaggi di chat e canali in Teams. Le chat di Teams vengono archiviate in una cartella nascosta della cassetta postale di ogni utente incluso nella chat e i messaggi dei canali di Teams vengono archiviati in un'analoga cartella nascosta della cassetta postale del gruppo per il team. 

È importante sapere che Teams usa un servizio di chat con tecnologia Azure che archivia anche questi dati e che, per impostazione predefinita, questo servizio archivia i dati a tempo indeterminato. Per questo motivo, è consigliabile usare i percorsi di Teams per mantenere ed eliminare i dati di Teams. Con i percorsi di Teams, i dati verranno eliminati definitivamente dalle cassette postali di Exchange e dal servizio di chat con tecnologia Azure sottostante. Per altre informazioni, vedere [Sicurezza e conformità in Microsoft teams](https://go.microsoft.com/fwlink/?linkid=871258) e in particolare la sezione [Architettura di protezione delle informazioni](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture).

I messaggi di chat e canali di Teams non sono interessati dai criteri di conservazione configurati per le cassette postali di utenti o gruppi. Anche se i messaggi di chat e canali di Teams vengono archiviati in Exchange, questi dati vengono inclusi solo da un criterio di conservazione configurato per le posizioni **Messaggi del canale di Teams** e **Chat di Teams**.

> [!NOTE]
> Se un utente è incluso in un criterio di conservazione attivo che conserva i dati di Teams e si eliminata una cassetta postale di un utente incluso in tale criterio, per conservare i dati di Teams la cassetta postale viene convertita in una [cassetta postale inattiva](inactive-mailboxes-in-office-365.md). Se non è necessario conservare i dati di Teams per l'utente, escludere l'account utente dal criterio di conservazione prima di eliminare la relativa cassetta postale.

Dopo la configurazione di un criterio di conservazione per i messaggi di chat e canali, i percorsi del contenuto variano in base al fatto che il criterio di conservazione sia Conserva ed elimina, Conserva solo o Elimina solo.

Se il criterio di conservazione è Conserva ed elimina:

![Diagramma del flusso di conservazione per messaggi di chat e canali di Teams](../media/TeamsRetentionLifecycle.png)

1. **Se un messaggio di chat o canale viene modificato o eliminato** dall'utente durante il periodo di conservazione, viene spostato e archiviato, o copiato nel caso di modifica, nella cartella SubstrateHolds (una cartella nascosta nella cassetta postale di ogni utente o gruppo) fino alla scadenza del periodo di conservazione. I messaggi vengono eliminati definitivamente il giorno della scadenza del periodo di conservazione.

2. **Se un messaggio di chat o canale non viene eliminato** durante il periodo di conservazione, viene spostato nella cartella SubstrateHolds entro un giorno dalla scadenza del periodo di conservazione (l'operazione richiede da 0 a 24 ore). Il messaggio viene eliminato definitivamente un giorno dopo essere stato spostato nella cartella SubstrateHolds. 

> [!NOTE]
> I messaggi nella cartella SubstrateHolds sono disponibili per la ricerca tramite gli strumenti di eDiscovery. Dopo che un messaggio è stato eliminato definitivamente, non verrà restituito in una ricerca di eDiscovery.

Quando il criterio di conservazione è Conserva solo, o Elimina solo, i percorsi del contenuto sono varianti di Conserva ed elimina:

### <a name="content-paths-for-retain-only-retention-policy"></a>Percorsi di contenuto per il criterio di conservazione Conserva solo

1. **Se un messaggio di chat o di canale viene modificato o eliminato** durante il periodo di conservazione: una copia del messaggio originale viene creata nella cartella SubstrateHolds e conservata fino al termine del periodo di conservazione, quindi la copia nella cartella SubstrateHolds viene eliminata definitivamente un giorno dopo la scadenza dell'elemento. 

2. **Se l'elemento non viene modificato o eliminato** durante il periodo di conservazione: non succede niente prima o dopo il periodo di conservazione. L'elemento rimane nella posizione originale.

#### <a name="content-paths-for-delete-only-retention-policy"></a>Percorsi di contenuto per il criterio di conservazione Elimina solo

1. **Se il messaggio non viene eliminato** durante il periodo di conservazione: alla fine del periodo di conservazione il messaggio viene spostato nella cartella SubstrateHolds. 

2. **Se l'elemento viene eliminato dall'utente** durante il periodo, verrà immediatamente spostato nella cartella SubstrateHolds. Se un utente elimina il messaggio da questa posizione o svuota la cartella SubstrateHolds, l'elemento viene eliminato definitivamente. In caso contrario, il messaggio viene eliminato definitivamente un giorno dopo essere stato spostato nella cartella SubstrateHolds.


## <a name="skype-for-business-and-teams-interop-chats"></a>Chat di interoperabilità di Skype for Business e Teams.

La stessa procedura viene applicata alle chat di interoperabilità di Skype for Business e Teams. Quando una chat di Skype for Business viene spostata in Teams, diventa un messaggio in un thread di chat di Teams e viene inserita nella cassetta postale appropriata. I criteri di conservazione di Teams elimineranno questi messaggi dal thread di Teams. 

Tuttavia, se la cronologia delle conversazioni è abilitata per Skype for Business e dal lato client di Skype for Business questa cronologia viene salvata in una cassetta postale, i dati della chat non vengono gestiti dai criteri di conservazione di Teams.

## <a name="files-in-teams"></a>File in Teams

In Teams i file condivisi in chat vengono archiviati nell'account di OneDrive dell'utente che ha condiviso il file. I file caricati nei canali vengono archiviati nel sito di SharePoint del team. Questo significa che, per conservare o eliminare file in Teams, è necessario configurare uno o più criteri di conservazione applicati agli **account di OneDrive** e ai **siti di SharePoint** in aggiunta ai criteri di conservazione configurati per Teams. Per altre informazioni sul funzionamento dei criteri di conservazione per questi percorsi, vedere [Informazioni sui criteri di conservazione per SharePoint e OneDrive](retention-policies-sharepoint.md).

> [!NOTE]
> Un criterio di conservazione che include i messaggi dei canali di Teams o le chat di Teams può includere percorsi di Teams. Di conseguenza, per conservare o eliminare questi file in Teams è necessario creare un criterio di conservazione separato.
> 
> Per applicare un criterio di conservazione ai file di un solo team, è possibile scegliere il sito di SharePoint per il team e gli account di OneDrive per gli utenti del team.

È possibile che un criterio di conservazione applicato a SharePoint o OneDrive elimini un file a cui viene fatto riferimento nel messaggio di una chat o di un canale di Teams prima che tali messaggi vengano eliminati. In questo scenario, il file verrà comunque mostrato nel messaggio di Teams, ma se gli utenti fanno clic sul file visualizzeranno l'errore "File non trovato". Questo comportamento non è specifico dei criteri di conservazione e può verificarsi anche se un utente elimina manualmente un file da SharePoint o da OneDrive.

## <a name="meetings-and-external-users"></a>Riunioni e utenti esterni

I messaggi delle riunioni di canale vengono archiviati allo stesso modo dei messaggi di canale, quindi per questi dati selezionare il percorso **Messaggi del canale di Teams** quando si configura il criterio di conservazione.

I messaggi delle riunioni estemporanee vengono archiviati allo stesso modo dei messaggi delle chat di gruppo, quindi per questi dati selezionare il percorso **Chat di Teams** quando si configura il criterio di conservazione.

Quando in una riunione ospitata dall'organizzazione vengono inclusi utenti esterni:

- Se un utente esterno partecipa con un account guest nel tenant dell'organizzazione, l'utente ha una cassetta postale shadow che può essere soggetta ai criteri di conservazione dell'organizzazione per Teams. I messaggi della riunione vengono archiviati sia nella cassetta postale degli utenti che nella cassetta postale shadow. 

- Se un utente esterno partecipa usando un account di un'altra organizzazione di Microsoft 365, i criteri di conservazione non possono eliminare i messaggi per l'utente, perché sono archiviati nella sua cassetta postale in un altro tenant. Per la stessa riunione, tuttavia, i criteri di conservazione configurati possono eliminare i messaggi per gli utenti interni dell'organizzazione.


## <a name="limitations"></a>Limitazioni

Lavoriamo costantemente all'ottimizzazione della funzionalità di conservazione in Teams. Nel frattempo, ecco alcune limitazioni da tenere presenti:
  
- **Teams richiede criteri di conservazione specifici**. Quando si creano criteri di conservazione e si attivano i percorsi di Teams, tutti gli altri percorsi vengono disattivati. I criteri di conservazione che includono Teams possono includere solo Teams e non altri percorsi. 
    
- **Teams non è incluso in un criterio a livello di organizzazione**. Se si crea un criterio a livello di organizzazione, Teams non viene incluso perché richiede criteri di conservazione specifici. 
    
- **Teams non supporta la conservazione avanzata**. Quando si crea un criterio di conservazione, se si scelgono le [impostazioni avanzate per identificare il contenuto che soddisfa condizioni specifiche](create-retention-policies.md#advanced-settings-to-identify-content-that-meets-specific-conditions), i percorsi di Teams non sono disponibili. Attualmente, la conservazione in Teams si applica a tutto il contenuto di messaggi di chat e canali quando si selezionano tali posizioni. 

- **I messaggi di Teams nei canali privati non vengono inclusi quando si configurano criteri di conservazione per i messaggi dei canali di Teams**. I messaggi provenienti da canali privati sono invece inclusi per gli utenti come chat di gruppo scegliendo l'opzione **Chat di Teams**. 
    
- **In Teams potrebbero essere necessari fino a tre giorni per pulire i messaggi scaduti**. I criteri di conservazione applicati a Teams elimineranno i messaggi di chat e canali al termine del periodo di conservazione. Tuttavia, potrebbero essere necessari fino a tre giorni per pulire i messaggi ed eliminarli definitivamente. Inoltre, i messaggi di chat e canali saranno disponibili per la ricerca tramite strumenti di eDiscovery nel periodo successivo alla scadenza del periodo di conservazione e quando i messaggi vengono eliminati definitivamente.
    
   > [!NOTE]
   > È stata rimossa la limitazione secondo la quale un criterio di conservazione non poteva eliminare contenuti di Teams con meno di 30 giorni. Ora il periodo di conservazione per i contenuti di Teams può essere definito dall'utente a partire da 1 giorno. Se il periodo di conservazione è di 1 giorno, saranno necessari fino a tre giorni dopo la scadenza del periodo di conservazione, per l'eliminazione definitiva dei messaggi.

- **Problema di visualizzazione non corretta in Outlook**. Se si creano criteri di conservazione per i percorsi di Skype o Teams, uno di questi criteri viene visualizzato come criterio cartella predefinito quando un utente visualizza le proprietà di una cartella della cassetta postale nel client desktop di Outlook. Si tratta di un problema di visualizzazione non corretta in Outlook e di un [problema noto](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies). Quello che dovrebbe essere visualizzato come criterio cartella predefinito è il criterio di conservazione della cassetta postale applicato alla cartella. Il criterio di conservazione di Skype o Teams non viene applicato alla cassetta postale dell'utente.

- **Problemi di configurazione**: 
    - Quando si seleziona **Scegli i team** per il percorso **Messaggi del canale di Teams**, potrebbero essere visualizzati gruppi di Office 365 che non corrispondono anche a team. Non selezionare questi gruppi.
    
    - Quando si seleziona **Scegli utenti** per la posizione **Chat di Teams**, potrebbero essere visualizzati utenti non della cassetta postale e guest. I criteri di conservazione non sono pensati per questi utenti, quindi non selezionarli.


## <a name="how-to-configure-a-retention-policy-for-microsoft-teams"></a>Come configurare un criterio di conservazione per Microsoft Teams

Vedere [Creare e configurare criteri di conservazione](create-retention-policies.md).

Per la pagina **Seleziona posizioni** della procedura guidata, selezionare le opzioni seguenti:

- **Voglio scegliere posizioni specifiche** > **Messaggi del canale di Teams** e **Chat di Teams**

Un criterio di conservazione che si applica a Teams può usare la [protezione dell'archiviazione](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements), che potrebbe essere necessaria per motivi legali.

## <a name="related-information"></a>Informazioni correlate

[Criteri di conservazione in Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies)
