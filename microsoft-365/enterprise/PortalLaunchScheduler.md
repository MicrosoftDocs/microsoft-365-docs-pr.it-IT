---
title: Avviare il portale utilizzando l'utilità di pianificazione del lancio del portale
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: In questo articolo viene descritto come avviare il portale utilizzando l'utilità di pianificazione di avvio del portale
ms.openlocfilehash: 6a191cf323e180fa77614eb09bae4185228a5029
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087668"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>Avviare il portale utilizzando l'utilità di pianificazione del lancio del portale

Un portale è un sito di SharePoint nell’Intranet con un numero elevato di utenti che ne usano il contenuto. L'avvio del portale in Waves è una parte importante per garantire agli utenti un'esperienza fluida ed eseguibile nell'accesso a un nuovo portale di SharePoint Online. 

L'avvio in onda è un modo essenziale per implementare il portale, come descritto in [Planning Your Portal Launch-out Plan in SharePoint Online](https://docs.microsoft.com/en-us/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide). L'utilità di pianificazione di avvio del portale è stata progettata per consentire l'esecuzione di un approccio di distribuzione Wave/phased tramite la gestione dei reindirizzamenti per il nuovo portale. Durante ciascuna delle onde, è possibile raccogliere commenti e suggerimenti per gli utenti e monitorare le prestazioni durante ogni ondata di distribuzione. Questo ha il vantaggio di introdurre lentamente il portale, offrendo la possibilità di sospendere e risolvere i problemi prima di procedere con l'ondata successiva e, infine, garantire un'esperienza positiva per gli utenti. 

Sono disponibili due tipi di reindirizzamento: 
- bidirezionale: avviare un nuovo portale di SharePoint Online moderno per sostituire un portale esistente di SharePoint classico o moderno 
- Reindirizzamento della pagina temporanea: avviare un nuovo portale di SharePoint Online moderno con nessun portale di SharePoint esistente

L'utilità di pianificazione di avvio portale è disponibile solo per il lancio dei portali di SharePoint Online moderni, come i siti di comunicazione e i siti del team moderno. I lanci devono essere pianificati con almeno 7 giorni di anticipo. Il numero di ondate richieste è determinato dal numero previsto di utenti. Prima di pianificare l'avvio di un portale, è necessario eseguire lo [strumento page Diagnostics for SharePoint](https://aka.ms/perftool) per verificare che la Home page del portale sia integra. Al termine del lancio del portale, tutti gli utenti con autorizzazioni per il sito potranno accedere al nuovo sito. 

Per ulteriori informazioni sull'avvio di un portale con esito positivo, seguire i principi di base, le procedure e le raccomandazioni dettagliate per la [creazione, l'avvio e la gestione di un portale integro](https://docs.microsoft.com/sharepoint/portal-health). 

> [!NOTE]
> Questa funzionalità non è disponibile per Office 365 Germany, Office 365 gestito da 21Vianet (Cina) o con i piani di Microsoft 365 US Government.

## <a name="app-setup-and-connecting-to-sharepoint-online"></a>Configurazione delle app e connessione a SharePoint Online
1. [Scaricare l'ultima versione di SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    > [!NOTE]
    > Se hai installato una versione precedente di SharePoint Online Management Shell, vai su Installazione applicazioni e disinstallare SharePoint Online Management Shell.<br>Nella pagina Download Center selezionare la lingua e fare clic sul pulsante Scarica. Ti verrà chiesto di scegliere tra il download di un file x64 e x86 con estensione msi. Scaricare il file x64 se stai eseguendo la versione a 64 bit di Windows e il file x86 se stai eseguendo quella a 32 bit. Se non conosci quale versione stai eseguendo, vedere[Quale versione del sistema operativo Windows sto eseguendo?](https://support.microsoft.com/help/13443/windows-which-operating-system). Dopo aver scaricato il file, eseguirlo e seguire i passaggi della configurazione guidata.

2. Connettiti a SharePoint come [amministratore globale o amministratore di SharePoint](/sharepoint/sharepoint-admin-role) in Microsoft 365. Per informazioni in merito, vedere [Guida introduttiva a SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).


## <a name="view-any-existing-portal-launch-setups"></a>Visualizzazione di tutte le configurazioni di avvio dei portale esistenti

Per verificare se sono presenti configurazioni di avvio dei portale esistenti:

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a>Pianificare un avvio del portale nel sito

Il numero di ondate richieste dipende dalle dimensioni previste per il lancio. 
- Utenti con meno di 10K: 1 onda
- 10K per gli utenti di 30K: 3 ondate 
- 30K + a 100K utenti: 5 ondate
- Più di 100K utenti: 5 ondate e contattare il team dell'account Microsoft

### <a name="steps-for-bi-directional-redirection"></a>Passaggi per il reindirizzamento bi-direzionale

Il reindirizzamento bidirezionale implica l'avvio di un nuovo portale di SharePoint Online moderno per la sostituzione di un portale SharePoint classico o moderno esistente. Gli utenti in ondate attive verranno reindirizzati al nuovo sito indipendentemente dal fatto che vengano spostati nel sito precedente o nuovo. Gli utenti in un'ondata non avviata che tentano di accedere al nuovo sito verranno reindirizzati al vecchio sito fino a quando non verrà avviata l'ondata. Se si dispone di amministratori o proprietari che devono accedere ai siti precedenti e nuovi senza essere reindirizzati, verificare che siano elencati utilizzando il `WaveOverrideUsers` parametro. 

Per eseguire la migrazione di utenti da un sito di SharePoint esistente a un nuovo sito di SharePoint in modo graduale:

1. Eseguire il seguente comando per designare le onde di avvio del portale.
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

Esempio:
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. Completamento della convalida. Per completare la configurazione del servizio, il reindirizzamento può richiedere 5-10 minuti. 

### <a name="steps-for-redirection-to-temporary-page"></a>Passaggi per il reindirizzamento alla pagina temporanea

Il reindirizzamento di pagine temporanee deve essere utilizzato quando non esiste alcun portale di SharePoint esistente. Gli utenti vengono indirizzati a un nuovo portale di SharePoint Online moderno in modalità a fasi. Se un utente si trova in un'ondata che non è stato avviato, verrà reindirizzato a una pagina temporanea (qualsiasi URL). 

1. Eseguire il seguente comando per designare le onde di avvio del portale.
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

Esempio:
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. Completamento della convalida. Per completare la configurazione del servizio, il reindirizzamento può richiedere 5-10 minuti. 
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a>Sospendere o riavviare un avvio portale nel sito

1. Per sospendere un avvio del portale in corso e impedire temporaneamente che si verifichino progressi dell'onda imminente, eseguire il seguente comando:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. Verificare che tutti gli utenti vengano reindirizzati al vecchio sito. 

3. Per riavviare un avvio del portale che è stato sospeso, eseguire il comando riportato di seguito:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. Verificare che il reindirizzamento venga ripristinato. 

## <a name="delete-a-portal-launch-on-the-site"></a>Eliminare un avvio portale nel sito
1. Creare un'onda di avvio portale.
  - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. Eseguire il seguente comando per eliminare un avvio del portale pianificato o in corso per un sito.

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

3. Verificare che non venga eseguito alcun reindirizzamento per tutti gli utenti.

## <a name="learn-more"></a>Ulteriori informazioni
[Pianificazione del piano di avvio del portale per il lancio in SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
