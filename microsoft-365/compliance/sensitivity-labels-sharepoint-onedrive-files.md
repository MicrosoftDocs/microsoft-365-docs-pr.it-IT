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
description: Gli amministratori possono abilitare il supporto delle etichette di riservatezza per i file Word, Excel e PowerPoint in SharePoint e OneDrive.
ms.openlocfilehash: ee6f89db7758140ac8e4c2752d8a2883cc0990db
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780719"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>Abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

Prima di abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive, non è possibile applicare le [etichette di riservatezza](sensitivity-labels.md) in Office sul Web. Non viene visualizzato il pulsante **sensitivity** sulla barra multifunzione o il nome dell'etichetta applicata sulla barra di stato. Inoltre, se si utilizzano app desktop per assegnare etichette ai file e quindi salvarli in SharePoint o OneDrive, il servizio non è in grado di elaborare il contenuto di tali file se l'etichetta ha applicato la crittografia. La CoAuthoring, la eDiscovery, la prevenzione della perdita di dati, la ricerca e altre funzionalità di collaborazione non funzioneranno in queste circostanze.

Quando si abilitano le etichette di riservatezza per i file di Office in SharePoint e OneDrive, tutte queste funzionalità sono abilitate. Oltre a visualizzare le etichette di riservatezza per gli utenti, per i file nuovi e modificati che dispongono di un'etichetta di riservatezza applicata che include la crittografia con una chiave basata su cloud:

- Per i file Word, Excel e PowerPoint, SharePoint riconosce l'etichetta e ora è in grado di elaborare il contenuto del file crittografato.

- Quando si scaricano o si accede a questi file da SharePoint o OneDrive, l'etichetta di riservatezza e tutte le impostazioni di crittografia dell'etichetta vengono applicate e rimangono con il file, ovunque sia memorizzato. Assicurarsi di fornire istruzioni all'utente per l'utilizzo di etichette solo per la protezione dei documenti. Per ulteriori informazioni, vedere [Opzioni di Information Rights Management (IRM) e etichette di riservatezza](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels).

- Quando gli utenti caricano i file etichettati e crittografati in SharePoint, devono avere almeno i diritti di visualizzazione per tali file. Ad esempio, possono aprire i file all'esterno di SharePoint. Se non si dispone di questo diritto di utilizzo minimo, il caricamento ha esito positivo ma SharePoint non riconosce l'etichetta e non è in grado di elaborare il contenuto del file.

- Utilizzare Office sul Web (Word, Excel, PowerPoint) per aprire e modificare i file di Office che dispongono di etichette di riservatezza che applicano la crittografia. Le autorizzazioni assegnate alla crittografia vengono applicate. Con Word sul Web, è possibile utilizzare l'etichetta automatica anche quando si modificano questi documenti.

- Gli utenti esterni possono accedere ai documenti contrassegnati con la crittografia tramite gli account Guest. Per ulteriori informazioni, vedere [supporto per utenti esterni e contenuto con etichetta](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content). 

- Office 365 eDiscovery supporta la ricerca full-text per questi file. I criteri di prevenzione della perdita di dati (DLP) supportano i contenuti di questi file.

> [!NOTE]
> Se la crittografia non è stata applicata con una chiave basata sul cloud, ma con una chiave locale, una topologia di gestione delle chiavi spesso definita "tenere la propria chiave" (HYOK), il comportamento di SharePoint per l'elaborazione del contenuto del file non cambia.
>
> Il comportamento di SharePoint non cambia anche per i file etichettati e crittografati esistenti in SharePoint. Affinché questi file possano trarre vantaggio dalle nuove funzionalità, devono essere scaricati e caricati o modificati dopo aver eseguito il comando per abilitare le etichette di riservatezza per SharePoint e OneDrive. SharePoint può quindi elaborare questi file. Ad esempio, verranno restituiti nei risultati di ricerca e eDiscovery.

Dopo aver abilitato le etichette di riservatezza per i file di Office in SharePoint e OneDrive, sono disponibili tre nuovi [eventi di controllo](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) per il monitoraggio delle etichette di riservatezza applicate ai documenti in SharePoint e OneDrive:
- **Etichetta di riservatezza applicata al file**
- **Etichetta di riservatezza applicata a un file modificata**
- **Etichetta di riservatezza rimossa dal file**

Guardare il video seguente (senza audio) per visualizzare le nuove funzionalità in azione:

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

Si ha sempre la possibilità di disabilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive ([opt-out](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out) in qualsiasi momento.

Se si sta attualmente proteggendo i documenti in SharePoint tramite SharePoint Information Rights Management (IRM), controllare la sezione [SharePoint Information Rights Management (IRM) e le etichette di riservatezza](#sharepoint-information-rights-management-irm-and-sensitivity-labels) in questa pagina. 

## <a name="requirements"></a>Requisiti

Queste nuove funzionalità funzionano solo con le [etichette di riservatezza](sensitivity-labels.md) . Se al momento sono presenti etichette di Azure Information Protection, prima eseguirne la migrazione in etichette di riservatezza, in modo da poter abilitare queste funzionalità per i nuovi file caricati. Per istruzioni, vedere [How to migrate Azure Information Protection labels to Unified Sensitivity labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

Usare l'app OneDrive Sync 19.002.0121.0008 o versione successiva su Windows e la versione 19.002.0107.0008 o successiva su Mac. Entrambe le versioni sono state rilasciate il 28 gennaio 2019 e sono attualmente rilasciate a tutti gli anelli. Per ulteriori informazioni, vedere le [Note sulla versione di OneDrive](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0). Dopo aver abilitato le etichette di riservatezza per i file di Office in SharePoint e OneDrive, viene richiesto di aggiornarlo agli utenti che eseguono una versione precedente dell'app Sync.

## <a name="limitations"></a>Limitazioni

- SharePoint non applica automaticamente le etichette di riservatezza ai file esistenti già crittografati utilizzando le etichette di Azure Information Protection. Al contrario, per far funzionare le caratteristiche dopo aver abilitato le etichette di riservatezza per i file di Office in SharePoint e OneDrive, eseguire le seguenti attività:
    
    1. Assicurarsi di aver eseguito [la migrazione delle etichette di Azure Information Protection](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels) in etichette di riservatezza e di [pubblicarle](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) dal centro conformità di Microsoft 365 o dall'interfaccia di amministrazione dell'etichettatura equivalente.
    
    2. Scaricare i file e quindi caricarli in SharePoint.

- SharePoint non è in grado di elaborare i file crittografati quando l'etichetta che applica la crittografia ha una delle seguenti [configurazioni per la crittografia](encryption-sensitivity-labels.md#configure-encryption-settings):
    - **Consenti agli utenti di assegnare le autorizzazioni quando applicano l'etichetta** e la casella di controllo per **in Word, PowerPoint ed Excel,** è selezionata l'opzione utenti per specificare le autorizzazioni. Questa impostazione viene a volte definita "autorizzazioni definite dall'utente".
    - **L'accesso degli utenti al contenuto scade** è impostato su un valore diverso da **Never**.
    
    Per le etichette con una di queste configurazioni di crittografia, le etichette non vengono visualizzate per gli utenti di Office sul Web. Inoltre, non è possibile utilizzare le nuove funzionalità con i documenti contrassegnati che dispongono già di queste impostazioni di crittografia. Ad esempio, questi documenti non verranno restituiti nei risultati della ricerca, anche se sono stati aggiornati.

- Per un documento crittografato che consenta di modificare le autorizzazioni per un utente, la copia non può essere bloccata nelle versioni Web delle app di Office.

- Il sito di verifica dei documenti di Azure Information Protection non è supportato.

- Le app desktop di Office e le app per dispositivi mobili non supportano la CoAuthoring per i file contrassegnati con la crittografia. Queste app continuano ad aprire i file contrassegnati e crittografati in modalità di modifica esclusiva.

- Se un amministratore modifica le impostazioni per un'etichetta pubblicata già applicata ai file scaricati nel client di sincronizzazione degli utenti, gli utenti potrebbero non essere in grado di salvare le modifiche apportate al file nella propria cartella di sincronizzazione di OneDrive. Questo scenario si applica ai file contrassegnati con la crittografia e anche quando la modifica dell'etichetta è da un'etichetta che non applica la crittografia a un'etichetta che applica la crittografia. Gli utenti visualizzano un [cerchio rosso con un errore di icona trasversale bianco](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)e sono invitati a salvare nuove modifiche come copia distinta. In alternativa, possono chiudere e riaprire il file oppure utilizzare Office sul Web.

- Se un documento etichettato viene caricato in SharePoint e l'etichetta ha applicato la crittografia utilizzando un account di un nome dell'entità servizio, il documento non può essere aperto in Office sul Web. Gli scenari di esempio includono la sicurezza delle app cloud di Microsoft e un file inviato ai team tramite posta elettronica.

- Gli utenti possono sperimentare il salvataggio dei problemi dopo l'esecuzione offline o in modalità Sleep quando invece di usare Office per il Web, utilizzano le app desktop e per dispositivi mobili per Word, Excel o PowerPoint. Per questi utenti, quando riprendono la sessione dell'app di Office e tentano di salvare le modifiche, visualizzano un messaggio di errore di caricamento con un'opzione per salvare una copia anziché salvare il file originale. 

- I documenti che sono stati crittografati nei modi seguenti non possono essere aperti in Office sul Web:
    - Crittografia che utilizza una chiave locale ("mantenere la propria chiave" o HYOK)
    - Crittografia applicata indipendentemente da un'etichetta, ad esempio applicando direttamente un modello di protezione di Rights Management.

- Se si elimina un'etichetta applicata a un documento in SharePoint, anziché rimuovere l'etichetta dal criterio di etichetta applicabile, il documento al momento del download non verrà etichettato o crittografato. Se il documento etichettato è archiviato all'esterno di SharePoint, il documento resta crittografato se l'etichetta è stata eliminata. Si noti che, sebbene sia possibile eliminare le etichette durante la fase di testing, è molto raro eliminare un'etichetta in un ambiente di produzione.

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>Come abilitare le etichette di riservatezza per SharePoint e OneDrive (opt-in)

È possibile abilitare le nuove funzionalità tramite il centro conformità di Microsoft 365 oppure tramite PowerShell.

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a>Utilizzare il centro conformità per abilitare il supporto per le etichette di riservatezza

Questa opzione è il modo più semplice per abilitare le etichette di riservatezza per SharePoint e OneDrive.

L'amministratore globale dell'organizzazione dispone delle autorizzazioni complete per creare e gestire tutti gli aspetti delle etichette di riservatezza. Se non si esegue l'accesso come amministratore globale, vedere le [autorizzazioni necessarie per creare e gestire etichette di riservatezza](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels).

1. Accedere al [centro conformità Microsoft 365](https://compliance.microsoft.com/)e passare a **soluzioni**  >  **Information Protection**
    
    Se questa opzione non è immediatamente visibile, selezionare prima **Mostra tutto**. 

2. Se viene visualizzato un messaggio per abilitare la funzionalità di elaborazione del contenuto nei file di Office Online, selezionare **attiva subito**:
    
    ![Pulsante Attiva ora per abilitare le etichette di riservatezza per Office Online](../media/sensitivity-labels-turn-on-banner.png)
    
    Il comando viene eseguito immediatamente e quando la pagina viene aggiornata successivamente, non viene più visualizzato il messaggio o il pulsante. 

> [!NOTE]
> Se si dispone di Microsoft 365 multi-Geo, è necessario utilizzare PowerShell per abilitare queste funzionalità per tutte le posizioni geografiche. Per informazioni dettagliate, vedere la sezione successiva.

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>Utilizzo di PowerShell per abilitare il supporto per le etichette di riservatezza

In alternativa all'utilizzo del centro conformità, è possibile abilitare il supporto per le etichette di riservatezza utilizzando il cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) di PowerShell di SharePoint Online. 

Se si dispone di Microsoft 365 multi-Geo, è necessario utilizzare PowerShell per abilitare il supporto per tutte le geoposizioni geografiche.

#### <a name="prepare-the-sharepoint-online-management-shell"></a>Preparare la shell di gestione di SharePoint Online

Prima di eseguire il comando di PowerShell per abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive, verificare che sia in esecuzione SharePoint Online Management Shell Version 16.0.19418.12000 o versione successiva. Se si ha già la versione più recente, è possibile passare alla [procedura successiva](#run-the-powershell-command-to-enable-support-for-sensitivity-labels) per eseguire il comando di PowerShell.

1. Se è stata installata una versione precedente di SharePoint Online Management Shell da PowerShell Gallery, è possibile aggiornare il modulo eseguendo il cmdlet seguente.

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. In alternativa, se è stata installata una versione precedente di SharePoint Online Management Shell dall'area download Microsoft, è anche possibile **aggiungere o rimuovere programmi** e disinstallare SharePoint Online Management Shell.

3. In un Web browser passare alla pagina Area download e [scaricare l'ultima versione di SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

4. Selezionare la lingua e fare clic su **Scarica**.

5. Scegliere tra il file MSI x64 o x86. Scaricare il file x64 se si esegue la versione di Windows a 64 bit o il file x86 se si esegue la versione a 32 bit. Se non si conosce, vedere [la versione del sistema operativo Windows in esecuzione?](https://support.microsoft.com/help/13443/windows-which-operating-system)

6. Dopo aver scaricato il file, eseguire il file e seguire i passaggi illustrati nell'installazione guidata.

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a>Eseguire il comando PowerShell per abilitare il supporto per le etichette di riservatezza

Per abilitare le nuove funzionalità, utilizzare il cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) con il parametro *EnableAIPIntegration* :

1. Utilizzo di un account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale o di amministrazione di SharePoint in Microsoft 365, connettersi a SharePoint. Per informazioni in merito, vedere [Guida introduttiva a SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
    
    Nota: se si dispone di Microsoft 365 multi-Geo, utilizzare il parametro-URL con [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps)e specificare l'URL del sito dell'interfaccia di amministrazione di SharePoint Online per una delle geoposizioni geografiche.

2. Eseguire il seguente comando e premere **Y** per confermare:

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```
3. Per Microsoft 365 multi-geo: ripetere i passaggi 1 e 2 per ogni posizione geografica rimanente.

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a>Pianificare l'implementazione dopo la creazione o la modifica di un'etichetta di riservatezza

Dopo aver creato o modificato un'etichetta di riservatezza nel centro conformità di Microsoft 365, pubblicarla in fasi. Se si pubblicano etichette che non sono state completamente sincronizzate, quando gli utenti applicano le etichette ai file e le caricano in SharePoint, i file non possono essere aperti nelle versioni Web delle app di Office. Anche le funzioni di ricerca e eDiscovery non funzionano per i file.

È consigliabile attenersi alla seguente procedura:

1. Pubblicare l'etichetta di riservatezza nuova o modificata solo su una o due persone.

2. Attendere almeno 24 ore dopo la pubblicazione iniziale. Verificare che l'etichetta sia stata completamente sincronizzata.

3. Pubblicare l'etichetta in senso più generale.

## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a>SharePoint Information Rights Management (IRM) e etichette di riservatezza

[SharePoint Information Rights Management (IRM)](set-up-irm-in-sp-admin-center.md) è una tecnologia meno recente che consente di proteggere i file a livello di elenco e raccolta applicando la crittografia e le restrizioni quando si scaricano i file. Questa tecnologia di protezione obsoleta è progettata per impedire agli utenti non autorizzati di aprire il file quando si trova all'esterno di SharePoint.

In confronto, le etichette di riservatezza forniscono le impostazioni di protezione delle marcature visive (intestazioni, piè di pagina, filigrane) oltre alla crittografia. Le impostazioni di crittografia supportano l'intera gamma di [diritti di utilizzo](https://docs.microsoft.com/azure/information-protection/configure-usage-rights) per limitare gli elementi che gli utenti possono eseguire con il contenuto e le stesse etichette di riservatezza sono supportate per [molti scenari](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels). L'utilizzo dello stesso metodo di protezione con impostazioni coerenti tra carichi di lavoro e app comporta una strategia di protezione coerente.

Tuttavia, è possibile utilizzare entrambe le soluzioni di protezione insieme e il comportamento è il seguente: 

- Se si carica un file con un'etichetta di riservatezza che applica la crittografia, SharePoint non è in grado di elaborare questo file in modo che la CoAuthoring, eDiscovery, DLP e Search non funzionino per questo file.

- Se si etichetta un file tramite Office sul Web, vengono applicate tutte le impostazioni di crittografia dell'etichetta. Per questi file sono supportati la CoAuthoring, eDiscovery, DLP e la ricerca.

- Se si scarica un file etichettato utilizzando Office sul Web, l'etichetta viene mantenuta e tutte le impostazioni di crittografia dall'etichetta vengono applicate anziché le impostazioni di restrizione di IRM.

- Se si scarica un file di Office o PDF che non è crittografato con un'etichetta di riservatezza, vengono applicate le impostazioni di IRM.

- Se sono state abilitate le impostazioni di una raccolta IRM aggiuntive, in cui è possibile impedire agli utenti di caricare documenti che non supportano IRM, queste impostazioni vengono applicate.

Con questo comportamento, è possibile garantire che tutti i file di Office e PDF siano protetti da accessi non autorizzati, se sono stati scaricati, anche se non sono etichettati. Tuttavia, i file etichettati caricati non trarranno vantaggio dalle nuove funzionalità.

## <a name="search-for-documents-by-sensitivity-label"></a>Ricerca di documenti in base all'etichetta di riservatezza

Utilizzare la proprietà gestita **InformationProtectionLabelId** per trovare tutti i documenti di SharePoint o OneDrive che dispongono di un'etichetta di riservatezza specifica. Utilizzare la sintassi seguente:`InformationProtectionLabelId:<GUID>`

Ad esempio, per cercare tutti i documenti che sono stati etichettati come "riservati" e tale etichetta ha un GUID di "8faca7b8-8d20-48A3-8ea2-0f96310a848e", nella casella di ricerca digitare quanto segue:

`InformationProtectionLabelId: 8faca7b8-8d20-48a3-8ea2-0f96310a848e`

Per ottenere i GUID per le etichette di riservatezza, utilizzare il cmdlet [get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps) :
    
1. Prima di tutto, [connettersi a PowerShell in Centro sicurezza e conformità di Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell). 
    
    Ad esempio, in una sessione di PowerShell eseguita come amministratore, accedere con un account di amministratore globale:
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. Eseguire quindi il comando riportato di seguito:
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

Per ulteriori informazioni sull'utilizzo delle proprietà gestite, vedere [gestire lo schema di ricerca in SharePoint](https://docs.microsoft.com/sharepoint/manage-search-schema).

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>Come disabilitare le etichette di riservatezza per SharePoint e OneDrive (opt-out)

Se si disabilitano queste nuove funzionalità, i file caricati dopo aver abilitato le etichette di riservatezza per SharePoint e OneDrive continuano a essere protetti dall'etichetta perché le impostazioni dell'etichetta continuano a essere applicate. Quando si applicano etichette di riservatezza ai nuovi file dopo aver disabilitato queste nuove funzionalità, la ricerca full-text, eDiscovery e la CoAuthoring non funzioneranno più.

Per disabilitare queste nuove funzionalità, è necessario utilizzare PowerShell. Se si utilizza SharePoint Online Management Shell e il cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) , specificare lo stesso parametro *EnableAIPIntegration* descritto nella sezione [Use PowerShell per abilitare il supporto per le etichette di riservatezza](#use-powershell-to-enable-support-for-sensitivity-labels) . Ma stavolta, impostare il valore del parametro su false e premere **Y** per confermare:

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

Se si dispone di Microsoft 365 multi-Geo, è necessario eseguire questo comando per ogni posizione geografica.

## <a name="next-steps"></a>Passaggi successivi

Dopo aver abilitato le etichette di riservatezza per i file di Office in SharePoint e OneDrive, considerare l'etichettatura automatica dei file utilizzando i criteri di etichettatura automatica. Per ulteriori informazioni, vedere [applicare automaticamente un'etichetta di riservatezza al contenuto](apply-sensitivity-label-automatically.md).