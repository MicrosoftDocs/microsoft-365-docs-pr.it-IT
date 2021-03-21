---
title: Avviare il portale usando l'Utilità di pianificazione di avvio portale
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
description: In questo articolo viene descritto come avviare il portale tramite l'Utilità di pianificazione di avvio portale
ms.openlocfilehash: e39f00dbc63ae7f1dcaf907d9c67df2c1683efc6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926143"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>Avviare il portale usando l'Utilità di pianificazione di avvio portale

Un portale è un sito di SharePoint nell’Intranet con un numero elevato di utenti che ne usano il contenuto. L'avvio del portale in modalità ondata è una parte importante per garantire agli utenti un'esperienza fluida ed performante per l'accesso a un nuovo portale di SharePoint Online. 

L'avvio in modalità ondata è un modo chiave per implementare il portale, come descritto in Pianificazione del piano di implementazione dell'avvio del portale [in SharePoint Online.](./planportallaunchroll-out.md?view=o365-worldwide) L'Utilità di pianificazione di avvio portale è progettata per consentire di seguire un approccio di implementazione graduale/ondata gestendo i reindirizzamenti per il nuovo portale. Durante ognuna delle ondate, è possibile raccogliere il feedback degli utenti e monitorare le prestazioni durante ogni ondata di distribuzione. Questo ha il vantaggio di introdurre lentamente il portale, offrendoti la possibilità di sospendere e risolvere i problemi prima di procedere con l'onda successiva e di garantire un'esperienza positiva per gli utenti. 

Esistono due tipi di reindirizzamento: 
- bidirezionale: avviare un nuovo portale moderno di SharePoint Online per sostituire un portale classico o moderno di SharePoint esistente 
- reindirizzamento temporaneo delle pagine: avviare un nuovo portale di SharePoint Online moderno senza portale di SharePoint esistente

L'utilità di pianificazione di avvio del portale è disponibile solo per avviare portali di SharePoint Online moderni (ad esempio, siti di comunicazione). Gli avvii devono essere pianificati con almeno 7 giorni di anticipo. Il numero di onde richieste è determinato dal numero previsto di utenti. Prima di pianificare l'avvio di un portale, è necessario eseguire lo strumento Diagnostica pagine per [SharePoint](./page-diagnostics-for-spo.md) per verificare che la home page del portale sia integra. Al termine dell'avvio del portale, tutti gli utenti con autorizzazioni per il sito potranno accedere al nuovo sito. 

Per ulteriori informazioni sull'avvio di un portale corretto, seguire i principi di base, le procedure e i suggerimenti dettagliati in Creazione, avvio e [manutenzione di un portale integro.](/sharepoint/portal-health) 

> [!NOTE]
> Questa funzionalità non è disponibile per i piani di Office 365 Germany, Office 365 gestito da 21Vianet (Cina) o Microsoft 365 US Government.

## <a name="app-setup-and-connecting-to-sharepoint-online"></a>Configurazione dell'app e connessione a SharePoint Online
1. [Scaricare l'ultima versione di SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    > [!NOTE]
    > Se hai installato una versione precedente di SharePoint Online Management Shell, vai su Installazione applicazioni e disinstallare SharePoint Online Management Shell.<br>Nella pagina Download Center selezionare la lingua e fare clic sul pulsante Scarica. Ti verrà chiesto di scegliere tra il download di un file x64 e x86 con estensione msi. Scaricare il file x64 se stai eseguendo la versione a 64 bit di Windows e il file x86 se stai eseguendo quella a 32 bit. Se non conosci quale versione stai eseguendo, vedere[Quale versione del sistema operativo Windows sto eseguendo?](https://support.microsoft.com/help/13443/windows-which-operating-system). Dopo aver scaricato il file, eseguirlo e seguire i passaggi della configurazione guidata.

2. Connettiti a SharePoint come [amministratore globale o amministratore di SharePoint](/sharepoint/sharepoint-admin-role) in Microsoft 365. Per informazioni in merito, vedere [Guida introduttiva a SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).


## <a name="view-any-existing-portal-launch-setups"></a>Visualizzare eventuali configurazioni di avvio del portale esistenti

Per verificare se sono presenti configurazioni di avvio del portale esistenti:

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a>Pianificare un avvio del portale nel sito

Il numero di onde necessarie dipende dalle dimensioni di avvio previste. 
- Meno di 10.000 utenti: 1 onda
- Da 10.000 a 30.000 utenti: 3 onde 
- Da 30.000 a 100.000 utenti: 5 onde
- Più di 100.000 utenti: 5 onde e contattare il team dell'account Microsoft

### <a name="steps-for-bidirectional-redirection"></a>Passaggi per il reindirizzamento bidirezionale

Il reindirizzamento bidirezionale prevede l'avvio di un nuovo portale di SharePoint Online moderno per sostituire un portale classico o moderno di SharePoint esistente. Gli utenti in ondate attive verranno reindirizzati al nuovo sito indipendentemente dal fatto che si snavigare verso il sito vecchio o nuovo. Gli utenti in un'ondata non avviata che tentano di accedere al nuovo sito verranno reindirizzati al sito precedente fino all'avvio dell'ondata. 

Supportiamo solo il reindirizzamento tra la home page predefinita nel vecchio sito e la home page predefinita nel nuovo sito. Se si dispone di amministratori o proprietari che devono accedere ai siti vecchi e nuovi senza essere reindirizzati, assicurarsi che siano elencati utilizzando il `WaveOverrideUsers` parametro .

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

1. Per sospendere l'avvio di un portale in corso e impedire temporaneamente che si verifichino imminenti progressioni delle onde, eseguire il comando seguente:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. Verificare che tutti gli utenti siano reindirizzati al sito precedente. 

3. Per riavviare un avvio del portale sospeso, eseguire il comando seguente:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. Verificare che il reindirizzamento sia stato ripristinato. 

## <a name="delete-a-portal-launch-on-the-site"></a>Eliminare un avvio del portale nel sito

1. Eseguire il comando seguente per eliminare un avvio del portale pianificato o in corso per un sito.

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. Verificare che non si verifica alcun reindirizzamento per tutti gli utenti.

## <a name="learn-more"></a>Ulteriori informazioni
[Pianificazione del piano di implementazione dell'avvio del portale in SharePoint Online](./planportallaunchroll-out.md)