---
title: Riferimento alle impostazioni di condivisione guest di Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
f1.keywords: NOCSH
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
description: Informazioni sulle impostazioni di condivisione guest disponibili in Microsoft 365 che possono influire sulla condivisione con persone esterne all'organizzazione.
ms.openlocfilehash: 0c734d1046a1c2d180c8102187b8cf07de7dc4dc
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613045"
---
# <a name="microsoft-365-guest-sharing-settings-reference"></a>Riferimento alle impostazioni di condivisione guest di Microsoft 365

Questo articolo fornisce informazioni di riferimento per le varie impostazioni che possono interessare la condivisione con persone esterne all'organizzazione per i carichi di lavoro di Microsoft 365: Teams, Gruppi di Microsoft 365, SharePoint e OneDrive. Queste impostazioni si trovano nelle interfacce di amministrazione di Azure Active Directory, Microsoft 365, Teams e SharePoint admin centers.

## <a name="azure-active-directory"></a>Azure Active Directory

**Ruolo di amministratore:** Amministratore globale

Azure Active Directory è il servizio directory utilizzato da Microsoft 365. Le impostazioni delle relazioni aziendali di Azure Active Directory interessano direttamente la condivisione in Teams, Gruppi di Microsoft 365, SharePoint e OneDrive.

> [!NOTE]
> Queste impostazioni influiscono su SharePoint solo se è stata configurata [l'integrazione di SharePoint e OneDrive con Azure AD B2B (anteprima)](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview). Nella tabella seguente si presuppone che sia stata configurata.

### <a name="organizational-relationships-settings"></a>Impostazioni delle relazioni aziendali

**Navigazione:** [Interfaccia di amministrazione di Azure Active Directory](https://aad.portal.azure.com) > Azure Active Directory > Identità esterne > Impostazioni collaborazione esterna

![Screenshot della pagina delle impostazioni delle relazioni aziendali di Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

|**Impostazione**|**Predefinita**|**Descrizione**|
|:-----|:-----|:-----|
|Le autorizzazioni degli utenti guest sono limitate|Sì|Questa impostazione interessa le attività della directory che un utente guest può eseguire.|
|Gli amministratori e gli utenti nel ruolo Mittente dell'invito guest possono inviare inviti|Sì|Se l'impostazione è su **Sì**, gli amministratori possono invitare utenti guest tramite Azure AD e tramite le esperienze di condivisione di Microsoft 365, come Teams e SharePoint; se l'impostazione è su **No**, non possono farlo.|
|I membri possono invitare|Sì|Se l'impostazione è su **Sì**, i membri di Azure AD possono invitare utenti guest tramite Azure AD; se l'impostazione è su **No**, non possono farlo. Se l'impostazione è su **Sì**, i membri dei gruppi di Microsoft 365 possono invitare guest con l'approvazione dei proprietari; se l'impostazione è su **No**, i membri dei gruppi di Microsoft 365 possono invitare guest con l'approvazione dei proprietari ma i proprietari devono essere amministratori globali per concedere l'approvazione. <br><br>Tenere presente che **I membri possono invitare** si riferisce ai membri di Azure AD (anziché agli utenti guest) e non ai membri di siti o gruppi in Microsoft 365. <br><br>È identica all'impostazione **Consenti agli utenti di aggiungere nuovi utenti guest all'organizzazione** in Sicurezza e protezione di Microsoft 365.|
|Gli utenti guest possono invitare|Sì|Se l'impostazione è su **Sì**, gli utenti guest nella directory possono invitare altri utenti guest a collaborare su risorse di Azure AD e su file e cartelle in SharePoint e OneDrive; se l'impostazione è su **No**, non possono farlo. <br><br>Tenere presente che **Consentire agli utenti esterni di trovare gli account utente nella directory digitando le corrispondenze esatte degli indirizzi di posta elettronica** deve essere attivata nell'interfaccia di amministrazione di SharePoint affinché gli utenti guest possano condividere file e cartelle con altri utenti guest.|
|Abilita passcode monouso tramite posta elettronica per gli utenti guest (anteprima)|No|Se l'impostazione è su **Sì**, gli utenti guest senza un account del servizio gestito o un account aziendale o dell'istituto di istruzione possono [eseguire l'autenticazione con Azure AD utilizzando un passcode monouso](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode); se l'impostazione è su **No**, gli utenti dovranno creare un account Microsoft per eseguire l'autenticazione. Questa impostazione deve essere su **Sì** affinché [Integrazione di SharePoint e OneDrive con Azure AD B2B (anteprima)](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) funzioni.|
|Restrizioni di collaborazione|Consenti l'invio di inviti a qualsiasi dominio|Questa impostazione consente di specificare un elenco di domini autorizzati o bloccati per la condivisione. Se si specificano domini autorizzati, gli inviti di condivisione possono essere inviati solo a tali domini. Se si specificano domini non autorizzati, gli inviti di condivisione non possono essere inviati a tali domini.<br><br> Questa impostazione interessa le esperienze di condivisione di Microsoft 365 come Teams e SharePoint. È possibile autorizzare o bloccare i domini a un livello più granulare utilizzando i filtri per i domini in SharePoint o Teams.|

Questa impostazione influisce sul modo in cui gli utenti sono invitati nella directory. Non influisce sulla condivisione con gli utenti guest già presenti nella directory.

## <a name="microsoft-365"></a>Microsoft 365

**Ruolo di amministratore:** Amministratore globale

L'interfaccia di amministrazione di Microsoft 365 presenta delle impostazioni a livello di organizzazione per la condivisione e per Gruppi di Microsoft 365.

### <a name="sharing"></a>Condivisione

**Navigazione:** [Interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com) > Impostazioni > Impostazioni > Impostazioni organizzazione > Scheda sicurezza e privacy > Condivisione

![Screenshot dell'impostazione di condivisione guest in sicurezza e privacy nell'interfaccia di amministrazione di Microsoft 365](../media/sharepoint-security-privacy-sharing-setting.png)

|**Impostazione**|**Predefinita**|**Descrizione**|
|:-----|:-----|:-----|
|Consenti agli utenti di aggiungere nuovi utenti guest all'organizzazione|Attivato|Se l'impostazione è su **Sì**, i membri di Azure AD possono invitare utenti guest tramite Azure AD; se l'impostazione è su **No**, non possono farlo. Se l'impostazione è su **Sì**, i membri dei gruppi di Microsoft 365 possono invitare guest con l'approvazione dei proprietari; se l'impostazione è su **No**, i membri dei gruppi di Microsoft 365 possono invitare guest con l'approvazione dei proprietari ma i proprietari devono essere amministratori globali per concedere l'approvazione. <br><br>Tenere presente che **I membri possono invitare** si riferisce ai membri di Azure AD (anziché agli utenti guest) e non ai membri di siti o gruppi in Microsoft 365. <br><br>È identica all'impostazione **I membri possono invitare** nelle impostazioni delle relazioni aziendali di Azure Active Directory.|

### <a name="microsoft-365-groups"></a>Gruppi di Microsoft 365

**Spostamento:** [Interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com) > Impostazioni > Impostazioni > Gruppi di Microsoft 365

![Screenshot delle impostazioni guest di Gruppi di Microsoft 365 nell'interfaccia di amministrazione di Microsoft 365](../media/office-365-groups-guest-settings.png)

|**Impostazione**|**Predefinita**|**Descrizione**|
|:-----|:-----|:-----|
|Consenti ai membri del gruppo esterni all'organizzazione di accedere al contenuto del gruppo|Attivato|Se l'impostazione è su **Attivato**, gli utenti guest possono accedere al contenuto del gruppo; se l'impostazione è su **Disattivato**, non possono farlo. Questa impostazione deve essere su **Attivato** per qualsiasi scenario in cui gli utenti guest interagiscono con Teams o i Gruppi di Microsoft 365.|
|Consenti ai proprietari del gruppo di aggiungere persone esterne all'organizzazione ai gruppi|Attivato|Se è su **Attivato**, i proprietari di Teams o Gruppi di Microsoft 365 possono invitare nuovi guest al gruppo. Se è su **Disattivato**, i proprietari possono invitare solo utenti guest già presenti nella directory.|

Queste impostazioni sono a livello di organizzazione. Vedere [Creare impostazioni per un gruppo specifico](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#create-settings-for-a-specific-group) per informazioni sulle modifiche di queste impostazioni a livello di gruppo con PowerShell.

## <a name="teams"></a>Teams

L'opzione di accesso guest principale di Teams, **Consenti accesso ospite in Teams**, deve essere **attivata** affinché le altre impostazioni guest siano disponibili.

**Ruolo di amministratore:** Amministratore del servizio Teams

### <a name="guest-access"></a>Accesso guest

**Navigazione:** [Interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com) > Impostazioni organizzazione > Accesso guest

![Screenshot dell'opzione di accesso guest in Teams](../media/teams-guest-access-toggle.png)

|**Impostazione**|**Predefinita**|**Descrizione**|
|:-----|:-----|:-----|
|Consenti accesso ospite in Teams|Disattivato|Attiva o disattiva l'accesso guest per Teams. L'applicazione di questa impostazione può richiedere 24 ore una volta modificata.|

### <a name="guest-calling"></a>Chiamate guest

**Navigazione:** [Interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com) > Impostazioni organizzazione > Accesso guest

![Screenshot delle opzioni di chiamate guest di Teams](../media/teams-guest-calling-setting.png)

|**Impostazione**|**Predefinita**|**Descrizione**|
|:-----|:-----|:-----|
|Effettua chiamate private|Attivato|Se è su **Attivato**, gli utenti guest possono effettuare chiamate peer-to-peer in Teams; se è su **Disattivato**, non possono farlo.|

### <a name="guest-meeting"></a>Riunioni guest

**Navigazione:** [Interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com) > Impostazioni organizzazione > Accesso guest

![Screenshot delle impostazioni per le riunioni guest in Teams](../media/teams-guest-meeting-settings.png)

|**Impostazione**|**Predefinita**|**Descrizione**|
|:-----|:-----|:-----|
|Consenti video IP|Attivato|Se è su **Attivato**, gli utenti guest possono utilizzare i video nelle chiamate e nelle riunioni; se è su **Disattivato**, non possono farlo.|
|Modalità di condivisione dello schermo|Schermo intero|Se **disabilitato**, gli utenti guest non possono condividere gli schermi in Teams. Se impostato su **Applicazione singola**, gli utenti guest possono condividere solo una singola applicazione sullo schermo. Se impostato su **Schermo intero**, i guest possono scegliere di condividere un'applicazione o lo schermo interno.|
|Consenti Riunione immediata|Attivato|Se è su **Attivato**, gli utenti guest possono utilizzare la funzionalità Riunione immediata in Teams; se è su **Disattivato**, non possono farlo.|

### <a name="guest-messaging"></a>Messaggistica guest

**Navigazione:** [Interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com) > Impostazioni organizzazione > Accesso guest

![Screenshot delle impostazioni di messaggistica guest in Teams](../media/teams-guest-messaging-settings.png)

|**Impostazione**|**Predefinita**|**Descrizione**|
|:-----|:-----|:-----|
|Modifica i messaggi inviati|Attivato|Se è su **Attivato**, gli utenti guest possono modificare i messaggi inviati in precedenza; se è su **Disattivato**, non possono farlo.|
|Elimina i messaggi inviati|Attivato|Se è su **Attivato**, gli utenti guest possono eliminare i messaggi inviati in precedenza; se è su **Disattivato**, non possono farlo.|
|Chat|Attivato|Se è su **Attivato**, gli utenti guest possono utilizzare la chat in Teams; se è su **Disattivato**, non possono farlo.|
|Usa Giphy nelle conversazioni|Attivato|Se è su **Attivato**, gli utenti guest possono usare Giphy nelle conversazioni; se è su **Disattivato**, non possono farlo.|
|Classificazione contenuto Giphy|Moderato|Se impostato su **Consenti tutti i contenuti**, gli utenti guest possono inserire tutti i contenuti Giphy nelle chat, indipendentemente dalla loro classificazione. Se impostato su **Moderato**, i guest possono inserire contenuti Giphy nelle chat, ma i contenuti per adulti saranno moderatamente limitati. Se impostato su **Rigido**, gli utenti guest possono inserire contenuti Giphy nelle chat, ma i contenuti per adulti saranno vietati.|
|Usa meme nelle conversazioni|Attivato|Se è su **Attivato**, gli utenti guest possono usare meme nelle conversazioni; se è su **Disattivato**, non possono farlo.|
|Usa sticker nelle conversazioni|Attivato|Se è su **Attivato**, gli utenti guest possono usare sticker nelle conversazioni; se è su **Disattivato**, non possono farlo.|
|Consenti lo strumento di lettura immersiva per la visualizzazione dei messaggi|Attivato|Se è su **Attivato**, gli utenti guest possono visualizzare i messaggi con lo strumento di lettura immersiva; se è su **Disattivato**, non possono farlo.|

## <a name="sharepoint-and-onedrive-organization-level"></a>SharePoint e OneDrive (livello organizzazione)

**Ruolo di amministratore:** Amministratore di SharePoint

Queste impostazioni influiscono su tutti i siti dell'organizzazione. Non influiscono direttamente su Teams o Gruppi di Microsoft 365, ma è consigliabile allineare queste impostazioni a quelle di Teams e Gruppi di Microsoft 365 per evitare problemi con l'esperienza utente. Se, ad esempio, la condivisione guest è consentita in Teams ma non in SharePoint, gli utenti guest in Teams non avranno accesso alla scheda File perché i file di Teams sono archiviati in SharePoint.

### <a name="sharepoint-and-onedrive-sharing-settings"></a>Impostazioni di condivisione in SharePoint e OneDrive

Poiché OneDrive è una gerarchia di siti all'interno di SharePoint, le impostazioni di condivisione a livello di organizzazione influiscono direttamente su OneDrive come per altri siti di SharePoint.

**Navigazione:** Interfaccia di amministrazione di SharePoint > Condivisione

![Screenshot delle impostazioni di condivisione a livello di organizzazione in SharePoint](../media/sharepoint-organization-external-sharing-controls.png)

|**Impostazione**|**Predefinita**|**Descrizione**|
|:-----|:-----|:-----|
|SharePoint|Chiunque|Specifica le autorizzazioni di condivisione più permissive consentite per i siti di SharePoint.|
|OneDrive|Chiunque|Specifica le autorizzazioni di condivisione più permissive consentite per i siti di OneDrive. Questa impostazione non può essere più permissiva dell'impostazione di SharePoint.|

### <a name="sharepoint-and-onedrive-advanced-sharing-settings"></a>Impostazioni di condivisione avanzate in SharePoint e OneDrive

**Navigazione:** Interfaccia di amministrazione di SharePoint > Condivisione

![Screenshot delle impostazioni di condivisione a livello di organizzazione aggiuntive in SharePoint](../media/sharepoint-organization-advanced-sharing-settings.png)

|**Impostazione**|**Predefinita**|**Descrizione**|
|:-----|:-----|:-----|
|Limita condivisione esterna in base al dominio|Disattivato|Questa impostazione consente di specificare un elenco di domini autorizzati o bloccati per la condivisione. Se si specificano domini autorizzati, gli inviti di condivisione possono essere inviati solo a tali domini. Se si specificano domini non autorizzati, gli inviti di condivisione non possono essere inviati a tali domini.<br><br> Questa impostazione influisce su tutti i siti di SharePoint e OneDrive nell'organizzazione.|
|Gli utenti guest devono accedere con lo stesso account a cui vengono inviati gli inviti di condivisione|Disattivato|Impedisce agli utenti guest di utilizzare gli inviti di condivisione dei siti con un indirizzo di posta elettronica diverso da quello al quale è stato inviato l'invito.<br><br>[L'integrazione di SharePoint e OneDrive con Azure AD B2B (anteprima)](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) non usa questa impostazione perché tutti gli utenti guest vengono aggiunti alla directory in base all'indirizzo di posta elettronica al quale è stato inviato l'invito. Non è possibile utilizzare indirizzi di posta elettronica alternativi per accedere al sito.|
|Consenti agli utenti guest di condividere elementi che non possiedono|Attivato|Se è su **Attivato**, gli utenti guest possono condividere elementi che non possiedono con altri utenti o utenti guest; se è su **Disattivato**, non possono farlo. Gli utenti guest possono sempre condividere elementi di cui hanno il controllo completo.|

### <a name="sharepoint-and-onedrive-file-and-folder-link-settings"></a>Impostazioni dei collegamenti a file e cartelle di SharePoint e OneDrive

Quando si condividono file e cartelle in SharePoint e OneDrive, ai destinatari della condivisione viene inviato un collegamento con le autorizzazioni per il file o la cartella, anziché l'autorizzazione di accesso diretto al file o alla cartella. Sono disponibili diversi tipi di collegamenti ed è possibile scegliere quello predefinito presentato agli utenti quando condividono un file o una cartella. È inoltre possibile impostare autorizzazioni e opzioni di scadenza per i collegamenti *Chiunque*.

**Navigazione:** Interfaccia di amministrazione di SharePoint > Condivisione

![Screenshot delle impostazioni di condivisione di file e cartelle a livello di organizzazione in SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)

|**Impostazione**|**Predefinita**|**Descrizione**|
|:-----|:-----|:-----|
|Collegamenti di file e cartelle|Chiunque abbia il collegamento|Specifica quale collegamento di condivisione viene visualizzato per impostazione predefinita quando un utente condivide un file o una cartella. Se lo desiderano, gli utenti possono modificare l'opzione prima di condividere. Se l'impostazione predefinita è su **Chiunque abbia il collegamento** e *Chiunque*, la condivisione non è consentita per un determinato sito, **Solo persone nell'organizzazione** sarà visualizzata come impostazione predefinita per tale sito.|
|Questi collegamenti devono scadere entro questo numero di giorni|Disattivato (nessuna scadenza)|Specifica il numero di giorni dopo che un collegamento *Chiunque* creato scade. I collegamenti scaduti non possono essere rinnovati. Creare un nuovo collegamento se è necessario continuare a condividere dopo la scadenza.|
|Autorizzazioni per i file|Visualizzazione e modifica|Specifica i livelli di autorizzazione per i file disponibili per gli utenti quando si crea un collegamento *Chiunque*. Se si seleziona **Visualizzazione**, gli utenti possono creare collegamenti ai file *Chiunque* solo con autorizzazioni di visualizzazione. Se si seleziona **Visualizzazione e modifica**, gli utenti possono scegliere tra le autorizzazioni di visualizzazione e le autorizzazioni di visualizzazione e modifica quando creano il collegamento.|
|Autorizzazioni per le cartelle|Visualizzazione, modifica e caricamento|Specifica i livelli di autorizzazione per le cartelle disponibili per gli utenti quando si crea un collegamento *Chiunque*. Se si seleziona **Visualizzazione**, gli utenti possono creare collegamenti alle cartelle *Chiunque* solo con autorizzazioni di visualizzazione. Se si seleziona **Visualizzazione, modifica e caricamento**, gli utenti possono scegliere tra le autorizzazioni di visualizzazione e le autorizzazioni di visualizzazione, modifica e caricamento quando creano il collegamento.|

### <a name="sharepoint-and-onedrive-security-group-settings"></a>Impostazioni dei gruppi di sicurezza in SharePoint e OneDrive

Se si desidera limitare chi può condividere contenuti con utenti guest in SharePoint e OneDrive, è possibile farlo limitando la condivisione alle persone in gruppi di sicurezza specifici. Queste impostazioni non influiscono sulla condivisione tramite Teams o Gruppi di Microsoft 365. Gli utenti guest invitati tramite un gruppo o un team hanno accesso anche al sito associato, anche se la condivisione di documenti e cartelle può essere eseguita solo da persone nei gruppi di sicurezza specificati.

**Navigazione:** Interfaccia di amministrazione di SharePoint > Condivisione > Limitare la condivisione esterna ai gruppi di sicurezza

![Screenshot delle impostazioni dei gruppi di sicurezza per la condivisione a livello di organizzazione in SharePoint](../media/sharepoint-organization-external-sharing-security-groups.png)

|**Impostazione**|**Predefinita**|**Descrizione**|
|:-----|:-----|:-----|
|Consenti solo agli utenti dei gruppi di sicurezza selezionati di condividere con utenti esterni autenticati|Disattivato|Se è su **Attivato**, solo le persone nei gruppi di sicurezza specificati possono condividere con le persone esterne all’organizzazione. Sono disponibili solo i collegamenti *Persone specifiche*. La condivisione *Chiunque* è disabilitata a meno che anche **Consenti la condivisione con utenti esterni autenticati e usando collegamenti anonimi ai soli utenti dei gruppi di sicurezza selezionati** sia su **Attivato**|
|Consenti la condivisione con utenti esterni autenticati e usando collegamenti anonimi ai soli utenti dei gruppi di sicurezza selezionati|Disattivato|Se è su **Attivato**, solo le persone nei gruppi di sicurezza specificati possono condividere con utenti guest. Sono disponibili i collegamenti *Chiunque* e *Persone specifiche*.|

Queste due impostazioni possono essere usate contemporaneamente. Se un utente si trova nel gruppo di sicurezza specificato per entrambe le impostazioni, il livello di autorizzazione più elevato prevale (*Chiunque* più *Utente specifico*). I gruppi di sicurezza annidati sono supportati.

## <a name="sharepoint-site-level"></a>SharePoint (livello sito)

**Ruolo di amministratore:** Amministratore di SharePoint

Poiché queste impostazioni sono soggette alle impostazioni a livello di organizzazione per SharePoint, l'impostazione di condivisione effettiva per il sito potrebbe cambiare se l'impostazione a livello di organizzazione cambia. Se si sceglie un'impostazione qui e il livello di organizzazione viene impostato successivamente su un valore più restrittivo, a questo sito sarà applicato tale livello più restrittivo. Ad esempio, se si sceglie **Chiunque** e l'impostazione a livello di organizzazione viene in seguito impostata su **Utenti guest nuovi ed esistenti**, il sito consentirà solo utenti guest nuovi ed esistenti. Se l'impostazione a livello di organizzazione viene quindi reimpostata su **Chiunque**, il sito consentirà di nuovo i collegamenti *Chiunque*.

### <a name="site-sharing"></a>Condivisione di siti

È possibile impostare le autorizzazioni di condivisione guest per ogni sito di SharePoint. Questa impostazione è valida sia per la condivisione di siti che per la condivisione di file e cartelle. La condivisione *Chiunque* non è disponibile per la condivisione di siti. Se si sceglie **Chiunque**, gli utenti possono condividere file e cartelle utilizzando i collegamenti *Chiunque* e il sito stesso con utenti guest nuovi ed esistenti.

**Navigazione:** Interfaccia di amministrazione di SharePoint > Siti attivi > selezionare il sito > scheda Criteri > Modifica le impostazioni di condivisione esterna

![Screenshot delle impostazioni di condivisione esterna dei siti di SharePoint](../media/sharepoint-site-external-sharing-settings.png)

|**Impostazione**|**Predefinita**|**Descrizione**|
|:-----|:-----|:-----|
|Il contenuto del sito può essere condiviso con:|Varia in base al tipo di sito (vedere la tabella seguente)|Indica il tipo di condivisione esterna consentito per il sito. Le opzioni disponibili qui sono soggette alle impostazioni di condivisione a livello di organizzazione per SharePoint.|

### <a name="site-file-and-folder-link-settings"></a>Impostazioni dei collegamenti a file e cartelle dei siti

È possibile configurare impostazioni predefinite per il tipo di collegamento, le autorizzazioni e la scadenza dei collegamenti *Chiunque* per ogni sito. Se configurate al livello del sito, queste impostazioni sostituiscono le impostazioni a livello di organizzazione. Si noti che se i collegamenti *Chiunque* sono disabilitati a livello dell'organizzazione, *Chiunque* non sarà un tipo di collegamento disponibile a livello di sito.

**Navigazione:** Interfaccia di amministrazione di SharePoint > Siti attivi > selezionare il sito > scheda Criteri > Modifica le impostazioni di condivisione esterna

![Screenshot delle impostazioni di condivisione a livello di sito di SharePoint](../media/sharepoint-site-link-sharing-settings.png)

|**Impostazione**|**Predefinita**|**Descrizione**|
|:-----|:-----|:-----|
|Limita la condivisione esterna in base al dominio|Off|Questa impostazione consente di specificare un elenco di domini autorizzati o bloccati per la condivisione. Se si specificano domini autorizzati, gli inviti di condivisione possono essere inviati solo a tali domini. Se si specificano domini non autorizzati, gli inviti di condivisione non possono essere inviati a tali domini.<br><br> Questa impostazione non può essere usata per ignorare le restrizioni sul dominio impostate a livello di organizzazione o di Azure AD.|
|Tipo di collegamento di condivisione predefinito|Uguale all'impostazione a livello di organizzazione|Questa impostazione consente di specificare il collegamento di condivisione predefinito presentato agli utenti del sito. L'opzione *Uguale all'impostazione a livello di organizzazione* è definita da una combinazione di impostazioni di condivisione a livello di organizzazione e di sito.|
|Impostazioni avanzate per i collegamenti di tipo "Chiunque"|Uguale all'impostazione a livello di organizzazione|Specifica il numero di giorni dopo cui scade un collegamento *Chiunque* creato per un file di questo sito. I collegamenti scaduti non possono essere rinnovati. Creare un nuovo collegamento se è necessario continuare a condividere dopo la scadenza.|
|Autorizzazione collegamento predefinita|Uguale all'impostazione a livello di organizzazione|Questa impostazione consente di specificare l'autorizzazione predefinita (Visualizzazione o Modifica) per la i collegamenti di condivisione creati per i file nel sito.|

### <a name="default-site-sharing-settings"></a>Impostazioni di condivisione del sito predefinite

Nella tabella seguente viene mostrata l'impostazione di condivisione predefinita per ogni tipo di sito.

|**Tipo di sito**|**Impostazione di condivisione predefinita**|
|:-----|:-----|
|Classico|**Solo gli utenti dell'organizzazione**|
|OneDrive|**Chiunque**|
|Siti collegati ai gruppi (tra cui Teams)|**Guest nuovi ed esistenti** se l'impostazione di Gruppi di Microsoft 365 **Consenti ai proprietari di gruppi di aggiungere persone esterne all'organizzazione ai gruppi** è su **Attivato**; altrimenti, **Solo utenti guest esistenti**|
|Comunicazione|**Solo gli utenti dell'organizzazione**|
|Siti moderni senza gruppo (#STS3 TeamSite)|**Solo gli utenti dell'organizzazione**|

> [!NOTE]
> Il sito radice di comunicazione (tenant-name.sharepoint.com) include un'opzione di condivisione predefinita impostata su **Chiunque**.

## <a name="see-also"></a>Vedere anche

[Panoramica sulla condivisione esterna in SharePoint e OneDrive](https://docs.microsoft.com/sharepoint/external-sharing-overview)

[Accesso guest in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/guest-access)

[Aggiunta di guest a Gruppi di Microsoft 365](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)
