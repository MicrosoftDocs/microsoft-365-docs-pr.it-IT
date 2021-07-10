---
title: Multi-Geo Capabilities in OneDrive e SharePoint Online
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
ms.assetid: 094e86f2-9ff0-40ac-af31-28fcaba00c1d
description: Con Multi-Geo Capabilities in OneDrive Online l'organizzazione può espandere la propria presenza Microsoft 365 a più paesi/aree geografiche.
ms.openlocfilehash: 405f876317a6cec6defdf3f1a49b0dc32ac0add2
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362283"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a>Multi-Geo Capabilities in OneDrive e SharePoint Online

Le funzionalità multi-geografiche in OneDrive e SharePoint Online consentono il controllo delle risorse condivise come i siti del team di SharePoint e le cassette postali di Microsoft 365 Group archiviate in una posizione geografica specificata.

Ogni utente, ogni cassetta postale di Gruppi e ogni sito SharePoint ha una posizione dei dati preferita che indica la posizione geografica in cui i dati associati vengono archiviati. I dati personali degli utenti (cassetta postale di Exchange e OneDrive) insieme ai siti SharePoint o ai gruppi di Microsoft 365 creati, possono essere archiviati nella posizione geografica specificata per soddisfare i requisiti di residenza dei dati. È possibile [specificare amministratori diversi per ogni posizione geografica](add-a-sharepoint-geo-admin.md).

In questo modo gli utenti avranno un’esperienza uniforme quando usano i servizi di Microsoft 365, incluse le applicazioni Office, OneDrive e Search. Per i dettagli vedere [Esperienza utente in un ambiente multi-geografico](multi-geo-user-experience.md).

## <a name="onedrive"></a>OneDrive

Ogni utente di OneDrive può essere gestito o [spostato da un amministratore](move-onedrive-between-geo-locations.md) in una posizione satellite in base alla propria posizione dei dati preferita. I file personali vengono quindi mantenuti in tale posizione geografica, ma possono essere condivisi con utenti di altre posizioni geografiche.

## <a name="sharepoint-sites-and-groups"></a>Gruppi e siti di SharePoint

La gestione della funzionalità Multi-Geo è disponibile tramite l'interfaccia di amministrazione di SharePoint. Per informazioni dettagliate, vedere il [post del blog corrispondente](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).

Quando un utente crea un sito connesso a un gruppo di SharePoint in un ambiente multi-geografico, la posizione preferita dei dati viene usata per determinare la posizione geografica in cui viene creato il sito e la relativa cassetta postale di Gruppi. Se la posizione dei dati preferita dell'utente non è stata impostata o è stata impostata una posizione geografica non configurata come satellite, il sito e la cassetta postale vengono creati nella posizione centrale.

Microsoft 365 servizi diversi da Exchange, OneDrive, SharePoint e Teams non sono Multi-Geo. Tuttavia, Microsoft 365 i gruppi creati da questi servizi verranno configurati con il file PDL del creatore e la relativa cassetta postale del gruppo Exchange, SharePoint viene eseguito il provisioning del sito nel sito geografico corrispondente. 

## <a name="managing-the-multi-geo-environment"></a>Gestione dell'ambiente multi-geografico

La configurazione e la gestione dell'ambiente multi-geo vengono eseguite tramite l'interfaccia di amministrazione di SharePoint. 

![Schermata della pagina con le località geografiche nell'interfaccia di amministrazione di SharePoint](../media/sharepoint-multi-geo-admin-center.png)

Per alcune azioni, come il trasferimento di un sito di SharePoint o OneDrive, è necessario Microsoft PowerShell.

## <a name="see-also"></a>Vedere anche

[Multi-Geo in gruppi di SharePoint e Microsoft 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[Amministrare un ambiente multi-geo](administering-a-multi-geo-environment.md)

[Quote di archiviazione di SharePoint in ambienti multi-geo ](sharepoint-multi-geo-storage-quota.md)

[Amministrazione delle cassette postali di Exchange Online in un ambiente multi-geo](administering-exchange-online-multi-geo.md)
