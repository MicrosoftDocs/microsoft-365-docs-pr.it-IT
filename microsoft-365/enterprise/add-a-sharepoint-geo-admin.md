---
title: Aggiungere o rimuovere un amministratore geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords:
- NOCSH
description: È necessario configurare amministratori separati per ogni posizione geografica? Informazioni su come aggiungere o rimuovere un amministratore di posizione geografica in Microsoft 365 Multi-Geo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 32fe5e934e6a3d6f18c802c3c427974e67c1b454
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905609"
---
# <a name="add-or-remove-a-geo-administrator-in-microsoft-365-multi-geo"></a>Aggiungere o rimuovere un amministratore di posizione geografica in Microsoft 365 Multi-Geo

È possibile configurare amministratori separati per ogni posizione geografica disponibili nel tenant. Questi amministratori avranno accesso alle impostazioni SharePoint Online e OneDrive specifiche per la posizione geografica.

Alcuni servizi, ad esempio l'archivio termini, sono gestiti dalla posizione centrale e replicati nelle posizioni satellitari. L’amministratore geografico della sede centrale può accedere a questi criteri, mentre gli amministratori geografici per località satellitari non possono.

Gli amministratori globali e di SharePoint Online continuano ad avere accesso alle impostazioni nella posizione centrale e in tutte le località satellitari.

## <a name="configuring-geo-administrators"></a>Configurazione gli amministratori geografici

Per configurare gli amministratori geografici è necessario il modulo di PowerShell per SharePoint Online.

Utilizzare [Connect-SPOService](/powershell/module/sharepoint-online/Connect-SPOService) per connettersi all'interfaccia di amministrazione della posizione geografica in cui si vuole aggiungere l'amministratore geografico. (Ad esempio Connect-SPOService  https://ContosoEUR-admin.sharepoint.com.)

Per visualizzare gli amministratori geografici esistenti in una posizione, eseguire `Get-SPOGeoAdministrator`

### <a name="adding-a-user-as-a-geo-admin"></a>Aggiunta di un utente come amministratore geografico

Per aggiungere un utente come amministratore geografico, eseguire `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`

Per rimuovere un utente da amministratore geografico di una posizione, eseguire  `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`

### <a name="adding-a-group-as-a-geo-admin"></a>Aggiunta di un gruppo come amministratore geografico

È possibile aggiungere un gruppo di sicurezza o un gruppo di sicurezza abilitato alla posta elettronica come amministratore di posizione geografica. I gruppi di distribuzione e i gruppi di Microsoft 365 non sono supportati.

Per aggiungere un gruppo come amministratore geografico, eseguire `Add-SPOGeoAdministrator -GroupAlias <alias>`

Per rimuovere un gruppo da amministratore geografico, eseguire `Remove-SPOGeoAdministrator -GroupAlias <alias>`

Si noti che non tutti i gruppi di sicurezza un alias di gruppo. Per aggiungere un gruppo di sicurezza che non dispone di un alias, eseguire [Get-MsolGroup](/powershell/module/msonline/get-msolgroup) per recuperare un elenco dei gruppi, trovare il valore del proprio gruppo di sicurezza e quindi eseguire:

`Add-SPOGeoAdministrator -ObjectID <ObjectID>`

Per rimuovere un gruppo usando il valore di ObjectID, eseguire `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`

## <a name="related-topics"></a>Argomenti correlati

[Add-SPOGeoAdministrator](/powershell/module/sharepoint-online/add-spogeoadministrator)

[Get-SPOGeoAdministrator](/powershell/module/sharepoint-online/get-spogeoadministrator)

[Remove-SPOGeoAdministrator](/powershell/module/sharepoint-online/remove-spogeoadministrator)

[Impostare un alias (MailNickName) per un gruppo di sicurezza](/powershell/module/azuread/set-azureadgroup)