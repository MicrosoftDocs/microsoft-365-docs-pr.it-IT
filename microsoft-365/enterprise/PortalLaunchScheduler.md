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
ms.openlocfilehash: 929492742fd140654bd13be8165093ee10647c6d
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999580"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>Avviare il portale utilizzando l'utilità di pianificazione del lancio del portale

È possibile avviare il portale utilizzando l'utilità di avvio del portale, convalidando la capacità dell'amministratore del tenant di impostare un'ondata per un nuovo portale. L'amministratore può quindi convalidare il reindirizzamento delle richieste, in base all'esistenza di un utente nelle onde attive.

Per ulteriori informazioni sull'avvio di un portale con esito positivo, seguire i principi di base, le procedure e i suggerimenti illustrati nell'ambiente di [creazione, avvio e gestione di un portale integro](https://go.microsoft.com/fwlink/?linkid=2105838). 

## <a name="app-setup"></a>Configurazione delle app
1. Disinstalla se esiste una esistente `Microsoft.Online.SharePoint.PowerShell` dal computer tramite il pannello di controllo.
2. Sul passaggio di PowerShell `Install-Module -Name Microsoft.Online.SharePoint.PowerShell` .

## <a name="connect-to-sharepoint-online"></a>Connessione a SharePoint Online
1. Aprire [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) in Windows.
2. Connettersi al tenant come amministratore.
   - `Connect-SPOService -Url "https://*-admin.sharepoint.com" -Credential "username”`
3.  Fornire la password quando richiesto.

## <a name="command-to-get-an-existing-setup"></a>Comando per ottenere un'installazione esistente

Per visualizzare le configurazioni di avvio dei portale esistenti:

1. Passare `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite` .
2. Passare il parametro addition `-DisplayFormat Raw` se si desidera visualizzare l'insieme Wave formattato come formato di input non elaborato.

## <a name="commands-for-bi-directional-redirection"></a>Comandi per il reindirizzamento bi-direzionale

Per migrare gli utenti di siti precedenti al nuovo sito in modo a fasi:

1. Creare onde di avvio del portale.
   - Questa operazione è applicabile solo nella fase di test delle versioni precedenti.
   - Per testare immediatamente l'impatto della modifica, verificare che la prima ondata `LaunchDateUtc` sia impostata sulla data corrente. Se non si specifica questo flag, viene visualizzato un messaggio di errore. Questo errore si verifica perché i lanci in produzione devono essere pianificati con almeno 7 giorni di anticipo.

  `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. Completamento della convalida.
  - Il reindirizzamento può richiedere fino a 5 minuti per completare la configurazione del servizio, quindi attendere prima di continuare.
  - Se si effettua l'accesso con l'utente specificato come `WaveOverrideUsers` , quindi nulla cambia. Si consiglia di soggiornare nel sito a cui si accede.
  - Accedere con un utente che fa parte dei *visualizzatori SG1*.
    - Passare al sito precedente ed essere reindirizzato al nuovo sito.
    - Passare al nuovo sito ed è necessario rimanere nel nuovo sito.
    - Accedere con l'utente in *visualizzatori SG2* e passare al vecchio sito e rimanere nel sito precedente.
    - Passare al nuovo sito e procedere con il reindirizzamento al sito precedente.

3. Sospendere il lancio del portale.
  - Se è necessario sospendere le onde di lancio, è possibile sospenderle per il numero di giorni "x". L'impostazione del `Status` flag su pause impedisce tutte le progressioni dell'onda imminenti. 
  - `Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - Ciò consente di verificare che tutti gli utenti vengano reindirizzati al sito precedente.

4. Riavviare la progressione del lancio del portale. 
  - `Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - Verificare che il reindirizzamento venga ripristinato.

5. Eliminare una configurazione di avvio del portale.
  - `Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.
  - Verificare che non venga eseguito alcun reindirizzamento per tutti gli utenti.

## <a name="commands-for-redirection-to-temporary-page"></a>Comandi per il reindirizzamento alla pagina temporanea

Seguire questa procedura se non si dispone di un sito precedente e si desidera omettere gli utenti non presenti nell'ondata dall'atterraggio nella nuova pagina del portale.

Per creare una pagina temporanea in uno dei siti seguenti:

1. Creare un'onda di avvio portale.
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. Completamento della convalida.

  - Attendere cinque minuti prima di continuare, in quanto l'azione può richiedere fino a cinque minuti per il completamento.
  - Accedere con l'utente che fa parte dei *visualizzatori SG1* e:
     - Passare al nuovo sito ed è necessario rimanere nel nuovo sito.
     - Passare alla pagina Temp ed è necessario rimanere nella pagina Temp.
  - Accedere con l'utente che fa parte di *visualizzatori SG2* e:
     - Passare al nuovo sito ed essere reindirizzato alla pagina Temp.
     - Passare alla pagina Temp e mantenere la pagina temporanea.

3. Eliminare una configurazione di avvio del portale.
  - `Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - Verificare che non venga eseguito alcun reindirizzamento per tutti gli utenti.

## <a name="learn-more"></a>Ulteriori informazioni
[Pianificazione del piano di avvio del portale per il lancio in SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)