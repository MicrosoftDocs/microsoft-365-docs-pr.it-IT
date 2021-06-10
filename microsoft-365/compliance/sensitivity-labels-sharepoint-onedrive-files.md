---
title: Abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Gli amministratori possono abilitare il supporto delle etichette di riservatezza per i file di Word, Excel e PowerPoint in SharePoint e OneDrive.
ms.openlocfilehash: d4c0f9b4c280394dd63820320ba7ca30e349c361
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878041"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>Abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Abilitare l'etichettatura incorporata per i file Office supportati [in](sensitivity-labels-office-apps.md#office-file-types-supported) SharePoint e OneDrive [](sensitivity-labels.md) in modo che gli utenti possano applicare le etichette di riservatezza in Office per il Web. Quando questa funzionalità è abilitata, gli utenti visualizzano il pulsante Riservatezza sulla barra multifunzione in modo che possano applicare etichette e visualizzano qualsiasi nome di etichetta applicato sulla barra di stato. 

L'abilitazione di questa funzionalità consente inoltre SharePoint e OneDrive di elaborare il contenuto di Office file crittografati utilizzando un'etichetta di riservatezza. L'etichetta può essere applicata Office per il Web o nelle app desktop di Office e caricata o salvata in SharePoint e OneDrive. Fino a quando non si abilita questa funzionalità, questi servizi non possono elaborare file crittografati, il che significa che la creazione condivisa, eDiscovery, prevenzione della perdita dei dati, ricerca e altre funzionalità di collaborazione non funzioneranno per questi file.

Dopo aver abilitato le etichette di riservatezza per i file di Office in SharePoint e OneDrive, per i file nuovi e modificati con un'etichetta di riservatezza che applica la crittografia con una chiave basata su cloud (e non utilizza la crittografia a chiave doppia [):](double-key-encryption.md)

- Per word, Excel e PowerPoint file, SharePoint e OneDrive riconoscono l'etichetta e ora possono elaborare il contenuto del file crittografato.

- Quando gli utenti scaricano o accedono a questi file da SharePoint o OneDrive, l'etichetta di riservatezza e le eventuali impostazioni di crittografia dall'etichetta vengono applicate e rimangono nel file, ovunque sia archiviato. Assicurati di fornire indicazioni per l'uso solo delle etichette per proteggere i documenti. Per ulteriori informazioni, vedere [Opzioni di Information Rights Management (IRM) ed etichette di riservatezza.](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)

- Quando gli utenti caricano file con etichetta e crittografati SharePoint o OneDrive, devono disporre almeno dei diritti di visualizzazione per tali file. Ad esempio, possono aprire i file all'esterno SharePoint. Se non hanno questo diritto di utilizzo minimo, il caricamento ha esito positivo, ma il servizio non riconosce l'etichetta e non è in grado di elaborare il contenuto del file.

- Utilizzare Office per il Web (Word, Excel, PowerPoint) per aprire e modificare Office file con etichette di riservatezza che applicano la crittografia. Vengono applicate le autorizzazioni assegnate con la crittografia. È inoltre possibile utilizzare [l'etichettatura automatica](apply-sensitivity-label-automatically.md) per questi documenti.

- Gli utenti esterni possono accedere ai documenti etichettati con crittografia utilizzando account guest. Per ulteriori informazioni, vedere [Support for external users and labeled content](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content). 

- Office 365 eDiscovery supporta la ricerca full-text per questi file e i criteri di prevenzione della perdita dei dati (DLP) supportano il contenuto in questi file.

> [!NOTE]
> Se la crittografia è stata applicata con una chiave locale (una topologia di gestione delle chiavi spesso definita "mantenere la propria chiave" o HYOK) o utilizzando la crittografia a chiave [doppia,](double-key-encryption.md)il comportamento del servizio per l'elaborazione del contenuto del file non cambia. Pertanto, per questi file, la creazione condivisa, eDiscovery, la prevenzione della perdita di dati, la ricerca e altre funzionalità di collaborazione non funzioneranno.
>
> Il SharePoint e OneDrive non cambia anche per i file esistenti in questi percorsi etichettati con la crittografia usando una singola chiave basata su Azure. Per consentire a questi file di trarre vantaggio dalle nuove funzionalità dopo aver abilitato le etichette di riservatezza per i file di Office in SharePoint e OneDrive, i file devono essere scaricati e caricati di nuovo o modificati.

Dopo aver abilitato le etichette di riservatezza per i file di Office in [](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) SharePoint e OneDrive, sono disponibili tre nuovi eventi di controllo per il monitoraggio delle etichette di riservatezza applicate ai documenti in SharePoint e OneDrive:
- **Etichetta di riservatezza applicata al file**
- **Etichetta di riservatezza applicata a un file modificata**
- **Etichetta di riservatezza rimossa dal file**

Guarda il video seguente (senza audio) per vedere le nuove funzionalità in azione:

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

È sempre possibile scegliere di disabilitare le etichette di riservatezza per Office file in SharePoint e OneDrive[(](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out)rifiuto esplicito ) in qualsiasi momento.

Se attualmente si proteggono i documenti in SharePoint utilizzando SharePoint Information Rights Management (IRM), verificare la sezione [SharePoint Information Rights Management (IRM)](#sharepoint-information-rights-management-irm-and-sensitivity-labels) e le etichette di riservatezza in questa pagina. 

## <a name="requirements"></a>Requisiti

Queste nuove funzionalità funzionano solo [con le etichette di](sensitivity-labels.md) riservatezza. Se attualmente si dispone di etichette di Azure Information Protection, eseguirne innanzitutto la migrazione alle etichette di riservatezza in modo da poter abilitare queste funzionalità per i nuovi file caricati. Per istruzioni, vedere [Come eseguire la migrazione di etichette di Azure Information Protection a etichette di riservatezza unificate](/azure/information-protection/configure-policy-migrate-labels).

Usa l'app di sincronizzazione OneDrive versione 19.002.0121.0008 o successiva su Windows e la versione 19.002.0107.0008 o successiva su Mac. Entrambe queste versioni sono state rilasciate il 28 gennaio 2019 e sono attualmente rilasciate per tutti gli anelli. Per ulteriori informazioni, vedere le OneDrive [sulla versione](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0). Dopo aver abilitato le etichette di riservatezza per i file Office in SharePoint e OneDrive, agli utenti che eseguono una versione precedente dell'app di sincronizzazione viene richiesto di aggiornarla.

## <a name="limitations"></a>Limitazioni

- SharePoint e OneDrive non possono elaborare alcuni file etichettati e crittografati da app desktop di Office quando questi file contengono dati PowerQuery, dati archiviati da componenti aggiuntivi personalizzati o parti XML personalizzate come le proprietà della pagina di presentazione, gli schemi dei tipi di contenuto, il riquadro informazioni documento personalizzato e il formato XSN personalizzato. Questa limitazione si applica anche ai file a cui è stato aggiunto un [ID](https://support.microsoft.com/office/enable-and-configure-unique-document-ids-ea7fee86-bd6f-4cc8-9365-8086e794c984) documento quando vengono caricati.
    
    Per questi file, applicare un'etichetta senza crittografia in modo che possano essere aperti in un secondo momento in Office sul web oppure indicare agli utenti di aprire i file nelle proprie app desktop. I file etichettati e crittografati solo in Office sul web non sono interessati.

- SharePoint e OneDrive non applicano automaticamente etichette di riservatezza ai file esistenti già crittografati con le etichette di Azure Information Protection. Al contrario, per il funzionamento delle funzionalità dopo aver abilitato le etichette di riservatezza per Office file in SharePoint e OneDrive, completare queste attività:
    
    1. Assicurarsi di aver eseguito la migrazione delle etichette [](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) di [Azure Information Protection](/azure/information-protection/configure-policy-migrate-labels) alle etichette di riservatezza e di averle pubblicate dal Centro Microsoft 365 conformità.
    2. Scarica i file etichettati e quindi caricali nella posizione originale in SharePoint o OneDrive.

- SharePoint e OneDrive non possono elaborare i file crittografati quando l'etichetta che ha applicato la crittografia ha una delle configurazioni [seguenti per la crittografia:](encryption-sensitivity-labels.md#configure-encryption-settings)
    - **Consentire agli utenti di assegnare le autorizzazioni quando applicano l'etichetta** e la casella di controllo **In Word, PowerPoint ed Excel, chiedere agli utenti di specificare le autorizzazioni** viene selezionata. Questa impostazione viene talvolta definita "autorizzazioni definite dall'utente".
    - **L'accesso utenti al contenuto scade** è impostato su un valore diverso da **Mai**.
    - Viene selezionata una **Crittografia a chiave doppia**.
    
    Per le etichette con una di queste configurazioni di crittografia, le etichette non vengono visualizzate agli utenti in Office per il Web. Inoltre, le nuove funzionalità non possono essere usate con documenti etichettati che già dispongono di queste impostazioni di crittografia. Ad esempio, questi documenti non verranno restituiti nei risultati della ricerca, anche se vengono aggiornati.

- Per motivi di prestazioni, quando si carica o si salva un documento in SharePoint  e l'etichetta del file non applica la crittografia, la colonna Riservatezza nella raccolta documenti può richiedere del tempo per visualizzare il nome dell'etichetta. Fattore in questo ritardo se si utilizzano script o automazione che dipendono dal nome dell'etichetta in questa colonna.

- Gli utenti potrebbero subire ritardi nell'apertura di documenti crittografati nel seguente scenario Salva con nome: utilizzando una versione desktop di Office, un utente sceglie Salva con nome per un documento con un'etichetta di riservatezza che applica la crittografia. L'utente seleziona SharePoint o OneDrive per il percorso e quindi tenta immediatamente di aprire il documento in Office per il Web. Se il servizio sta ancora elaborando la crittografia, l'utente visualizza un messaggio che indica che il documento deve essere aperto nell'app desktop. Se si riprova tra un paio di minuti, il documento verrà aperto Office per il Web. 

- Per i documenti crittografati, la stampa non è supportata.

- Per un documento crittografato che concede autorizzazioni di modifica a un utente, la copia non può essere bloccata nelle versioni Web delle Office app.

- Per impostazione predefinita, Office app desktop e per dispositivi mobili non supportano la creazione condivisa per i file etichettati con crittografia. Queste app continuano ad aprire file con etichetta e crittografati in modalità di modifica esclusiva.
    
    > [!NOTE]
    > La creazione condivisa è ora supportata in anteprima. Per ulteriori informazioni, vedere Abilitare la creazione condivisa per [i file crittografati con etichette di riservatezza.](sensitivity-labels-coauthoring.md)

- Se un amministratore modifica le impostazioni per un'etichetta pubblicata già applicata ai file scaricati nel client di sincronizzazione degli utenti, gli utenti potrebbero non essere in grado di salvare le modifiche apportate al file nella cartella OneDrive Sync. Questo scenario si applica ai file etichettati con crittografia e anche quando la modifica dell'etichetta deriva da un'etichetta che non applica la crittografia a un'etichetta che applica la crittografia. Gli utenti [visualizzano un cerchio rosso con un errore](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)con una croce bianca e gli viene chiesto di salvare le nuove modifiche come copia separata. Possono invece chiudere e riaprire il file o usare Office per il Web.

- Se un documento con etichetta viene caricato in SharePoint o OneDrive e l'etichetta ha applicato la crittografia utilizzando un account di un nome dell'entità servizio, il documento non può essere aperto in Office per il Web. Gli scenari di esempio includono Microsoft Cloud App Security e un file inviato a Teams tramite posta elettronica.

- Gli utenti possono provare problemi di salvataggio dopo essere stati offline o in modalità sospensione quando invece di usare Office per il Web, usano le app desktop e mobili per Word, Excel o PowerPoint. Per questi utenti, quando riprendono la sessione di app Office e provano a salvare le modifiche, viene visualizzato un messaggio di errore di caricamento con un'opzione per salvare una copia invece di salvare il file originale. 

- I documenti crittografati nei modi seguenti non possono essere aperti in Office per il Web:
    - Crittografia che usa una chiave locale ("mantieni la tua chiave" o HYOK)
    - Crittografia applicata tramite [la crittografia a chiave doppia](double-key-encryption.md)
    - Crittografia applicata in modo indipendente da un'etichetta, ad esempio applicando direttamente un modello di protezione Rights Management.

- Le etichette [configurate per altre lingue](create-sensitivity-labels.md#additional-label-settings-with-security--compliance-center-powershell) non sono supportate e visualizzano solo la lingua originale.

- Non è possibile impedire l'acquisizione dello schermo per i documenti crittografati. Per ulteriori informazioni, vedere [Can Rights Management prevent screen captures?](/azure/information-protection/faqs-rms#can-rights-management-prevent-screen-captures)

- Se si elimina un'etichetta applicata a un documento in SharePoint o OneDrive, anziché rimuovere l'etichetta dal criterio di etichetta applicabile, il documento scaricato non verrà etichettato o crittografato. Se invece il documento con etichetta è archiviato all'esterno di SharePoint o OneDrive, il documento rimane crittografato se l'etichetta viene eliminata. Si noti che, sebbene sia possibile eliminare le etichette durante una fase di testing, è molto raro eliminare un'etichetta in un ambiente di produzione.

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>Come abilitare le etichette di riservatezza per SharePoint e OneDrive (consenso esplicito)

È possibile abilitare le nuove funzionalità utilizzando il Centro Microsoft 365 conformità o PowerShell. Come per tutte le modifiche alla configurazione a livello di tenant per SharePoint e OneDrive, la modifica avrà effetto circa 15 minuti.

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a>Usare il Centro conformità per abilitare il supporto per le etichette di riservatezza

Questa opzione è il modo più semplice per abilitare le etichette di riservatezza per SharePoint e OneDrive, ma è necessario accedere come amministratore globale per il tenant.

1. Accedere al Centro [Microsoft 365 conformità](https://compliance.microsoft.com/) come amministratore globale e passare a **Soluzioni** Protezione  >  **delle informazioni**
    
    Se questa opzione non è immediatamente visibile, selezionare prima **Mostra tutto**. 

2. Se viene visualizzato un messaggio per attivare la possibilità di elaborare il contenuto Office file online, selezionare **Attiva ora**:
    
    ![Pulsante Attiva ora per abilitare le etichette di riservatezza per Office Online](../media/sensitivity-labels-turn-on-banner.png)
    
    Il comando viene eseguito immediatamente e al successivo aggiornamento della pagina non viene più visualizzato il messaggio o il pulsante.

> [!NOTE]
> Se hai Microsoft 365 Multi-Geo, devi usare PowerShell per abilitare queste funzionalità per tutte le posizioni geografiche. Per informazioni dettagliate, vedere la sezione successiva.

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>Abilitazione del supporto per le etichette di riservatezza tramite PowerShell

In alternativa all'utilizzo del Centro conformità, è possibile abilitare il supporto per le etichette di riservatezza utilizzando il cmdlet [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) di SharePoint PowerShell online. 

Se hai Microsoft 365 Multi-Geo, devi usare PowerShell per abilitare questo supporto per tutte le posizioni geografiche.

#### <a name="prepare-the-sharepoint-online-management-shell"></a>Preparare SharePoint Online Management Shell

Prima di eseguire il comando PowerShell per abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive, assicurarsi di eseguire SharePoint Online Management Shell versione 16.0.19418.12000 o successiva. Se si dispone già della versione più recente, è possibile passare alla [procedura successiva per](#run-the-powershell-command-to-enable-support-for-sensitivity-labels) eseguire il comando PowerShell.

1. Se è stata installata una versione precedente di SharePoint Online Management Shell da PowerShell Gallery, è possibile aggiornare il modulo eseguendo il cmdlet seguente.

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. In alternativa, se è stata installata una versione precedente di SharePoint Online Management Shell  dall'Area download Microsoft, è anche possibile accedere a Installazione applicazioni e disinstallare SharePoint Online Management Shell.

3. In un Web browser passare alla pagina Area download e [scaricare l'ultima versione di SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

4. Selezionare la lingua e fare clic su **Scarica**.

5. Scegliere tra il file MSI x64 o x86. Scaricare il file x64 se si esegue la versione a 64 bit di Windows o il file x86 se si esegue la versione a 32 bit. In caso contrario, vedere Quale versione del sistema operativo [Windows in esecuzione?](https://support.microsoft.com/help/13443/windows-which-operating-system)

6. Dopo aver scaricato il file, eseguire il file e seguire i passaggi dell'Installazione guidata.

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a>Eseguire il comando PowerShell per abilitare il supporto per le etichette di riservatezza

Per abilitare le nuove funzionalità, utilizzare il cmdlet [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) con *il parametro EnableAIPIntegration:*

1. Usando un account aziendale o dell'istituto di istruzione con privilegi di amministratore globale o SharePoint amministratore in Microsoft 365, connettersi a SharePoint. Per informazioni in merito, vedere [Guida introduttiva a SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
    
    > [!NOTE]
    > Se si dispone di Microsoft 365 Multi-Geo, utilizzare il parametro -Url con [Connessione-SPOService](/powershell/module/sharepoint-online/connect-sposervice)e specificare l'URL del sito Dell'interfaccia di amministrazione di SharePoint Online per una delle posizioni geografiche.

2. Eseguire il comando seguente e premere **Y** per confermare:

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true
    ```
3. Per Microsoft 365 multi-geo: ripetere i passaggi 1 e 2 per ognuna delle posizioni geografiche rimanenti.

## <a name="publishing-and-changing-sensitivity-labels"></a>Pubblicazione e modifica delle etichette di riservatezza

Quando si utilizzano etichette di riservatezza con SharePoint e OneDrive, tenere presente che è necessario consentire il tempo di replica quando si pubblicano nuove etichette di riservatezza o si aggiornano le etichette di riservatezza esistenti. Ciò è particolarmente importante per le nuove etichette che applicano la crittografia.

Ad esempio: puoi creare e pubblicare una nuova etichetta di riservatezza che applica la crittografia e viene visualizzata molto rapidamente nell'app desktop di un utente. L'utente applica l'etichetta a un documento e la carica SharePoint o OneDrive. Se la replica delle etichette non è stata completata per il servizio, le nuove funzionalità non verranno applicate al documento al caricamento. Di conseguenza, il documento non verrà restituito nella ricerca o per eDiscovery e il documento non può essere aperto in Office per il Web.  

Le modifiche seguenti vengono replicate entro un'ora: le etichette di riservatezza nuove ed eliminate e le impostazioni dei criteri delle etichette di riservatezza che includono le etichette incluse nel criterio.

Le modifiche seguenti vengono replicate entro 24 ore: modifiche alle impostazioni delle etichette di riservatezza per le etichette esistenti.

Poiché il ritardo di replica è di solo un'ora per le nuove etichette di riservatezza, è improbabile che si verifichi lo scenario nell'esempio. Tuttavia, come protezione, è consigliabile pubblicare prima nuove etichette per pochi utenti di test, attendere un'ora e quindi verificare il comportamento dell'etichetta SharePoint e OneDrive. Come passaggio finale, rendi l'etichetta disponibile per più utenti aggiungendo altri utenti al criterio di etichetta esistente o aggiungendo l'etichetta a un criterio di etichetta esistente per gli utenti standard. Al momento in cui gli utenti standard visualizzano l'etichetta, l'etichetta è già sincronizzata con SharePoint e OneDrive.

## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a>SharePoint Information Rights Management (IRM) e etichette di riservatezza

[SharePoint Information Rights Management (IRM)](set-up-irm-in-sp-admin-center.md) è una tecnologia precedente per proteggere i file a livello di elenco e raccolta applicando la crittografia e le restrizioni quando i file vengono scaricati. Questa tecnologia di protezione precedente è progettata per impedire agli utenti non autorizzati di aprire il file mentre si trova all'esterno SharePoint.

In confronto, le etichette di riservatezza forniscono le impostazioni di protezione dei contrassegni visivi (intestazioni, piè di pagina, filigrane) oltre alla crittografia. Le impostazioni di crittografia [](/azure/information-protection/configure-usage-rights) supportano l'intera gamma di diritti di utilizzo per limitare le operazioni che gli utenti possono eseguire con il contenuto e le stesse etichette di riservatezza sono supportate per [molti scenari.](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels) L'uso dello stesso metodo di protezione con impostazioni coerenti tra carichi di lavoro e app determina una strategia di protezione coerente.

Tuttavia, è possibile utilizzare entrambe le soluzioni di protezione insieme e il comportamento è il seguente: 

- Se si carica un file con un'etichetta di riservatezza che applica la crittografia, SharePoint non è in grado di elaborare il contenuto di questi file in modo che la creazione condivisa, eDiscovery, DLP e la ricerca non siano supportate per questi file.

- Se si applica un'etichetta a un file Office per il Web, vengono applicate le impostazioni di crittografia dell'etichetta. Per questi file, sono supportati la creazione condivisa, eDiscovery, DLP e la ricerca.

- Se si scarica un file etichettato utilizzando Office per il Web, l'etichetta viene mantenuta e vengono applicate le impostazioni di crittografia dell'etichetta anziché le impostazioni di restrizione IRM.

- Se si scarica un Office o un file PDF non crittografato con un'etichetta di riservatezza, vengono applicate le impostazioni IRM.

- Se è stata abilitata una qualsiasi delle impostazioni aggiuntive della raccolta IRM, che includono impedire agli utenti di caricare documenti che non supportano IRM, queste impostazioni vengono applicate.

Con questo comportamento, puoi essere certo che tutti i Office e i file PDF sono protetti da accessi non autorizzati se vengono scaricati, anche se non sono etichettati. Tuttavia, i file con etichetta che vengono caricati non trarranno vantaggio dalle nuove funzionalità.


## <a name="search-for-documents-by-sensitivity-label"></a>Cercare documenti in base all'etichetta di riservatezza

Utilizzare la proprietà gestita **InformationProtectionLabelId** per trovare tutti i documenti in SharePoint o OneDrive con un'etichetta di riservatezza specifica. Utilizzare la sintassi seguente: `InformationProtectionLabelId:<GUID>`

Ad esempio, per cercare tutti i documenti etichettati come "Riservato" e tale etichetta ha un GUID "8faca7b8-8d20-48a3-8ea2-0f96310a848e", nella casella di ricerca digitare:

```
InformationProtectionLabelId:8faca7b8-8d20-48a3-8ea2-0f96310a848e
```

La ricerca non troverà documenti etichettati in un file compresso, ad esempio un .zip file.

Per ottenere i GUID per le etichette di riservatezza, utilizzare il cmdlet [Get-Label:](/powershell/module/exchange/get-label)    

1. Prima di tutto, [connettersi a PowerShell in Centro sicurezza e conformità di Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell). 
   
    Ad esempio, in una sessione di PowerShell eseguita come amministratore, accedere con un account di amministratore globale.    

2. Eseguire quindi il comando seguente:  

    ```powershell   
    Get-Label |ft Name, Guid    
    ``` 

Per ulteriori informazioni sull'utilizzo delle proprietà gestite, vedere [Manage the search schema in SharePoint](/sharepoint/manage-search-schema).

## <a name="remove-encryption-for-a-labeled-document"></a>Rimuovere la crittografia per un documento con etichetta

In rari casi, un SharePoint deve rimuovere la crittografia da un documento archiviato in SharePoint. Qualsiasi utente a cui è assegnato il diritto di utilizzo [Rights Management](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) di Esportazione o Controllo completo per tale documento può rimuovere la crittografia applicata dal servizio Azure Rights Management da Azure Information Protection. Ad esempio, gli utenti con uno di questi diritti di utilizzo possono sostituire un'etichetta che applica la crittografia con un'etichetta senza crittografia. In alternativa, un [utente con privilegi di amministratore](/azure/information-protection/configure-super-users) potrebbe scaricare il file e salvare una copia locale senza la crittografia.

[In](/sharepoint/sharepoint-admin-role) alternativa, un amministratore globale o un amministratore di SharePoint può eseguire il cmdlet [Unlock-SPOSensitivityLabelEncryptedFile,](/powershell/module/sharepoint-online/unlock-sposensitivitylabelencryptedFile) che rimuove sia l'etichetta di riservatezza che la crittografia. Questo cmdlet viene eseguito anche se l'amministratore non dispone delle autorizzazioni di accesso al sito o al file o se il servizio Azure Rights Management non è disponibile. 

Ad esempio:

```powershell
Unlock-SPOSensitivityLabelEncryptedFile -FileUrl "https://contoso.com/sites/Marketing/Shared Documents/Doc1.docx" -JustificationText "Need to decrypt this file"
```

Requisiti:

- SharePoint Online Management Shell versione 16.0.20616.12000 o successiva.

- La crittografia è stata applicata da un'etichetta di riservatezza con le impostazioni di crittografia definite dall'amministratore (le [impostazioni dell'etichetta](encryption-sensitivity-labels.md#assign-permissions-now) Assegna ora le autorizzazioni). [La crittografia a chiave](encryption-sensitivity-labels.md#double-key-encryption) doppia non è supportata per questo cmdlet.

Il testo di giustificazione [](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) viene aggiunto all'evento di controllo dell'etichetta di riservatezza Rimossa dal **file** e l'azione di decrittografia viene registrata anche nella registrazione dell'utilizzo della protezione per [Azure Information Protection.](/azure/information-protection/log-analyze-usage)

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>Come disabilitare le etichette di riservatezza per SharePoint e OneDrive (rifiutare esplicitamente)

Se si disabilitano queste nuove funzionalità, i file caricati dopo aver abilitato le etichette di riservatezza per SharePoint e OneDrive continueranno a essere protetti dall'etichetta perché le impostazioni delle etichette continuano a essere applicate. Quando si applicano etichette di riservatezza ai nuovi file dopo aver disabilitato queste nuove funzionalità, la ricerca full-text, eDiscovery e la creazione condivisa non funzioneranno più.

Per disabilitare queste nuove funzionalità, è necessario utilizzare PowerShell. Utilizzando SharePoint Online Management Shell e il cmdlet [Set-SPOTenant,](/powershell/module/sharepoint-online/set-spotenant) specificare lo stesso parametro *EnableAIPIntegration* come descritto nella sezione [Use PowerShell to enable support for sensitivity labels.](#use-powershell-to-enable-support-for-sensitivity-labels) Ma questa volta, imposta il valore del parametro su false e premi **Y** per confermare:

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

Se hai Microsoft 365 Multi-Geo, devi eseguire questo comando per ognuna delle posizioni geografiche.

## <a name="next-steps"></a>Passaggi successivi

Dopo aver abilitato le etichette di riservatezza per Office file in SharePoint e OneDrive, è consigliabile etichettare automaticamente questi file utilizzando criteri di etichettatura automatica. Per ulteriori informazioni, vedere [Applicare automaticamente un'etichetta di riservatezza al contenuto.](apply-sensitivity-label-automatically.md)

È necessario condividere i propri documenti etichettati e crittografati con persone esterne all’organizzazione?  Vedere [Condivisione di documenti crittografati con utenti esterni](sensitivity-labels-office-apps.md#sharing-encrypted-documents-with-external-users).
