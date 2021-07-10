---
title: Funzionalità multi-geografiche in Microsoft Teams
ms.reviewer: daro
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
description: Informazioni su come Teams con Microsoft 365 Multi-Geo.
ms.openlocfilehash: 9fe9b289b0ffbef12327c4232b9deb6727b6d718
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362667"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a>Funzionalità multi-geografiche in Microsoft Teams

Le funzionalità Multi-Geo in Teams consentono Teams i dati della chat da archiviare in una posizione geografica specificata. I dati di chat sono costituiti da messaggi di chat, inclusi messaggi privati, messaggi di canale e immagini utilizzati nelle chat.

Teams utilizza il file PDL (Preferred Data Location) per utenti e gruppi per determinare dove archiviare i dati. Se la PDL non è impostata o non è valida, i dati vengono archiviati nella posizione centrale del tenant.

## <a name="user-chat"></a>Chat utente

La chat utente include messaggi di riunione uno-a-uno, uno-a-molti e privati.

Quando viene creato un nuovo utente, Teams legge il file PDL dell'utente e archivia tutti i dati della chat in tale posizione geografica.

Per gli utenti esistenti, se un amministratore aggiunge o modifica il file PDL per un utente, i dati della chat dell'utente vengono aggiunti a una coda di migrazione per essere spostati nella posizione geografica specificata.

La posizione di archiviazione per una chat uno-a-uno o uno-a-molti si basa sul file PDL della persona che ha creato la chat. Se il PDL dell'utente viene modificato, la chat verrà migrata nella nuova posizione geografica. La posizione di archiviazione per una chat di riunione si basa sul PDL dell'organizzatore della riunione.

Per trovare la posizione corrente dei dati Teams utente, connettersi a [Teams PowerShell](/powershell/module/teams/connect-microsoftteams) ed eseguire il comando seguente:

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a>Messaggi di canale

Ogni Microsoft 365 ha una posizione dati preferita (PDL, Preferred Data Location) che indica la posizione geografica in cui devono essere archiviati i dati correlati. Teams il file PDL per il gruppo associato a ogni team per determinare dove archiviare i dati di messaggistica del canale per tale team. Sono incluse le chat che si verificano all'interno di una riunione di canale.

Quando un utente crea un nuovo team, il PDL dell'utente determina quale file PDL viene assegnato al Microsoft 365 gruppo. Il file PDL del gruppo determina dove vengono archiviati i dati del team. Se il PDL dell'utente in un secondo momento cambia, il PDL del gruppo non viene modificato.

Per i team esistenti, se un amministratore aggiunge o modifica il file PDL per il gruppo di Microsoft 365 che contiene un team, i dati di messaggistica del canale del team vengono aggiunti a una coda di migrazione per essere spostati nella posizione geografica specificata.

La modifica del file PDL del gruppo Microsoft 365 coda dei dati Teams eseguire la migrazione nel percorso scelto. Tuttavia, non viene eseguita automaticamente la migrazione del SharePoint o dei file associati al gruppo. È necessario spostare il sito separatamente seguendo le procedure descritte in [Move a SharePoint site to a different geo location.](/microsoft-365/enterprise/move-sharepoint-between-geo-locations) Assicurati di eseguire entrambi i passaggi per evitare Teams dati e SharePoint per un gruppo in posizioni diverse.

Per trovare la posizione corrente dei dati di un team, connettersi a [Teams PowerShell](/powershell/module/teams/connect-microsoftteams) ed eseguire il comando seguente:

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

## <a name="user-experience"></a>Esperienza utente

Teams Multi-Geo è facile per l'utente finale. Dopo aver modificato il file PDL di un utente o di un gruppo, i rispettivi dati verranno accodato per la migrazione e la migrazione verrà eseguita automaticamente senza alcun impatto sull'utente o sul client Teams anche se sono attivi durante la migrazione.

## <a name="see-also"></a>Vedere anche

[Configurazione del tenant di Microsoft 365 Multi-Geo](/microsoft-365/enterprise/multi-geo-tenant-configuration)

[Amministrare un ambiente multi-geo](administering-a-multi-geo-environment.md)

[Amministrazione delle cassette postali di Exchange Online in un ambiente multi-geo](administering-exchange-online-multi-geo.md)
