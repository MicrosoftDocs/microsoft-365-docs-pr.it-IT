---
title: Eseguire il backup dei dati prima di modificare i piani
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: Eseguire il backup del contenuto di Outlook, OneDrive, Yammer e SharePoint prima di modificare i piani di Microsoft 365.
ms.date: 03/17/2021
ms.openlocfilehash: 86953f3235d8725ecdd6b5294611c0e5a378b17d
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333351"
---
# <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>Eseguire il backup dei dati prima di cambiare piano di Microsoft 365 per le aziende

Se un utente passa a un'altra sottoscrizione con meno servizi correlati ai dati o un utente lascia l'organizzazione, è possibile scaricare una copia dei dati archiviati in Microsoft 365 prima di passare alla nuova sottoscrizione.

Se si sta spostando un utente in una sottoscrizione con lo stesso o più servizi, non è necessario eseguire il backup dei dati utente. Vedere [Spostare gli utenti in un abbonamento diverso.](./move-users-different-subscription.md)
  
## <a name="save-a-copy-of-outlook-information"></a>Salvare una copia delle informazioni di Outlook

Se gli utenti hanno Outlook, possono esportare o eseguire il backup di posta [elettronica,](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) contatti e calendario in un file PST di Outlook prima di cambiare piano.
  
Al termine del passaggio al nuovo piano, gli utenti possono importare posta elettronica, contatti e [calendario da un file PST di Outlook.](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)
  
## <a name="save-files-stored-in-onedrive-for-business"></a>Salvare i file archiviati in OneDrive for Business

Prima di passare a un abbonamento diverso, gli utenti possono scaricare file e cartelle da OneDrive o [SharePoint](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) in un percorso diverso, ad esempio una cartella sul disco rigido del computer o una condivisione file nella rete dell'organizzazione.
  
## <a name="save-yammer-information"></a>Salvare le informazioni di Yammer

Gli amministratori possono esportare tutti i messaggi, le note, i file, gli argomenti, gli utenti e i gruppi in un file ZIP. Per ulteriori informazioni, vedere [Esportare i dati da Yammer Enterprise.](/yammer/manage-security-and-compliance/export-yammer-enterprise-data) A tale scopo, gli sviluppatori possono usare [l'API](https://go.microsoft.com/fwlink/p/?linkid=842495) di Yammer.
  
## <a name="how-to-save-sharepoint-information"></a>Come salvare le informazioni di SharePoint

Se un utente passa da una sottoscrizione con SharePoint Online a una che non lo contiene, il riquadro di **SharePoint** non verrà più visualizzato nel menu di Microsoft 365.
  
Tuttavia, se il nuovo abbonamento è nella stessa organizzazione di quello precedente, l'utente potrà continuare ad accedere al sito del team di SharePoint e potrà visualizzare e aggiornare blocchi appunti, documenti, attività e calendari usando l'URL diretto del sito del team.
  
> [!TIP]
> è consigliabile che gli utenti accedano al sito del team prima del cambio di abbonamento e salvino l'URL come preferito o come segnalibro nel browser.
  
Per impostazione predefinita, il formato dell'URL del sito Web del team è:
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

dove  _\<orgDomain\>_ è l'URL dell'organizzazione.
  
Ad esempio, se il dominio dell'organizzazione è contoso.onmicrosoft.com, l'URL diretto del sito del team sarà `https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx`.
  
Naturalmente gli utenti possono anche scaricare i documenti di SharePoint Online dal sito del team di SharePoint nel loro computer locale o in un'altra posizione in qualsiasi momento.
