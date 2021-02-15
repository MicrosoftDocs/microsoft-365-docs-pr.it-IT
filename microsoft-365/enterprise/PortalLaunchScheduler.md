---
title: Avviare il portale usando l'Utilità di pianificazione per l'avvio del portale
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
description: Questo articolo descrive come avviare il portale usando l'Utilità di pianificazione per l'avvio del portale
ms.openlocfilehash: 66912f5730c580bd75282a64124fefcdf262d738
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2021
ms.locfileid: "49864877"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>Avviare il portale usando l'Utilità di pianificazione per l'avvio del portale

Un portale è un sito di SharePoint nell’Intranet con un numero elevato di utenti che ne usano il contenuto. L'avvio del portale in modo ondoso è una parte importante per garantire agli utenti un'esperienza fluida ed performante per l'accesso a un nuovo portale di SharePoint Online. 

L'avvio in ondate è un modo chiave per implementare il portale, come descritto in Pianificazione del piano di implementazione dell'avvio del portale [in SharePoint Online.](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide) L'Utilità di pianificazione per l'avvio del portale è progettata per aiutarti a seguire un approccio di implementazione in fasi/wave gestendo i reindirizzamenti per il nuovo portale. Durante ognuna delle ondate, è possibile raccogliere il feedback dell'utente e monitorare le prestazioni durante ogni ondata di distribuzione. Ciò ha il vantaggio di introdurre lentamente il portale, offrendo la possibilità di sospendere e risolvere i problemi prima di procedere con l'ondata successiva e di garantire un'esperienza positiva per gli utenti. 

Esistono due tipi di reindirizzamento: 
- bidirezionale: avviare un nuovo portale di SharePoint Online moderno per sostituire un portale di SharePoint classico o moderno esistente 
- reindirizzamento temporaneo delle pagine: avviare un nuovo portale di SharePoint Online moderno senza un portale di SharePoint esistente

L'utilità di pianificazione per l'avvio del portale è disponibile solo per avviare i portali di SharePoint Online moderni (ad esempio i siti di comunicazione). Gli avvii devono essere pianificati con almeno 7 giorni di anticipo. Il numero di ondate richieste è determinato dal numero previsto di utenti. Prima di pianificare l'avvio di un portale, è necessario eseguire lo strumento Diagnostica pagine per [SharePoint](https://aka.ms/perftool) per verificare che la home page del portale sia integra. Al termine dell'avvio del portale, tutti gli utenti con autorizzazioni per il sito potranno accedere al nuovo sito. 

Per altre informazioni sull'avvio di un portale di successo, segui i principi di base, le procedure e i consigli dettagliati in Creazione, avvio e [gestione di un portale integro.](https://docs.microsoft.com/sharepoint/portal-health) 

> [!NOTE]
> Questa funzionalità non è disponibile per i piani di Office 365 Germany, Office 365 gestito da 21Vianet (Cina) o Microsoft 365 US Government.

## <a name="app-setup-and-connecting-to-sharepoint-online"></a>Configurazione dell'app e connessione a SharePoint Online
1. [Scaricare l'ultima versione di SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    > [!NOTE]
    > Se hai installato una versione precedente di SharePoint Online Management Shell, vai su Installazione applicazioni e disinstallare SharePoint Online Management Shell.<br>Nella pagina Download Center selezionare la lingua e fare clic sul pulsante Scarica. Ti verrà chiesto di scegliere tra il download di un file x64 e x86 con estensione msi. Scaricare il file x64 se stai eseguendo la versione a 64 bit di Windows e il file x86 se stai eseguendo quella a 32 bit. Se non conosci quale versione stai eseguendo, vedere[Quale versione del sistema operativo Windows sto eseguendo?](https://support.microsoft.com/help/13443/windows-which-operating-system). Dopo aver scaricato il file, eseguirlo e seguire i passaggi della configurazione guidata.

2. Connettiti a SharePoint come [amministratore globale o amministratore di SharePoint](/sharepoint/sharepoint-admin-role) in Microsoft 365. Per informazioni in merito, vedere [Guida introduttiva a SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).


## <a name="view-any-existing-portal-launch-setups"></a>Visualizzare eventuali configurazioni di avvio del portale esistenti

Per verificare se esistono configurazioni di avvio del portale esistenti:

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a>Pianificare l'avvio di un portale nel sito

Il numero di ondate necessarie dipende dalle dimensioni di avvio previste. 
- Meno di 10.000 utenti: 1 ondata
- Da 10.000 a 30.000 utenti: 3 ondate 
- Da 30.000 a 100.000 utenti: 5 ondate
- Più di 100.000 utenti: 5 ondate e contattare il team dell'account Microsoft

### <a name="steps-for-bidirectional-redirection"></a>Passaggi per il reindirizzamento bidirezionale

Il reindirizzamento bidirezionale prevede l'avvio di un nuovo portale di SharePoint Online moderno per sostituire un portale classico o moderno di SharePoint esistente. Gli utenti con ondate attive verranno reindirizzati al nuovo sito, indipendentemente dal fatto che si snavigare nel vecchio o nel nuovo sito. Gli utenti in un'ondata non avviata che tentano di accedere al nuovo sito verranno reindirizzati al sito precedente fino all'avvio dell'ondata. 

Il reindirizzamento tra la home page predefinita nel sito precedente e la home page predefinita nel nuovo sito è supportate solo. Se si dispone di amministratori o proprietari che devono accedere ai siti vecchi e nuovi senza essere reindirizzati, assicurarsi che siano elencati utilizzando il `WaveOverrideUsers` parametro.

Per eseguire la migrazione a fasi degli utenti da un sito di SharePoint esistente a un nuovo sito di SharePoint:

1. Eseguire il comando seguente per designare le ondate di avvio del portale.
   
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

2. Completare la convalida. Il reindirizzamento può richiedere da 5 a 10 minuti per completare la configurazione nel servizio. 

### <a name="steps-for-redirection-to-temporary-page"></a>Passaggi per il reindirizzamento alla pagina temporanea

Il reindirizzamento temporaneo delle pagine deve essere utilizzato quando non esiste un portale di SharePoint esistente. Gli utenti vengono indirizzati a un nuovo portale di SharePoint Online moderno in modo a fasi. Se un utente è in un'ondata che non è stata avviata, verrà reindirizzato a una pagina temporanea (qualsiasi URL). 

1. Eseguire il comando seguente per designare le ondate di avvio del portale.
   
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

2. Completare la convalida. Il reindirizzamento può richiedere da 5 a 10 minuti per completare la configurazione nel servizio. 

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a>Sospendere o riavviare l'avvio di un portale nel sito

1. Per sospendere l'avvio di un portale in corso e impedire temporaneamente che si verifichino imminenti progressioni delle onde, esegui il comando seguente:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. Verificare che tutti gli utenti siano reindirizzati al sito precedente. 

3. Per riavviare un avvio del portale sospeso, eseguire il comando seguente:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. Verificare che il reindirizzamento sia stato ripristinato. 

## <a name="delete-a-portal-launch-on-the-site"></a>Eliminare l'avvio di un portale nel sito

1. Eseguire il comando seguente per eliminare un avvio del portale pianificato o in corso per un sito.

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. Verificare che non si verifica alcun reindirizzamento per tutti gli utenti.

## <a name="learn-more"></a>Ulteriori informazioni
[Pianificazione del piano di implementazione dell'avvio del portale in SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
