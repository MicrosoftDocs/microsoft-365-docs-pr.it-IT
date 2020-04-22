---
title: Eseguire il backup dei dati prima di cambiare i piani di Microsoft 365 per le aziende
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: a1da52c9-2167-4973-9e6d-492314a79b87
description: Eseguire il backup di contenuto di Outlook, OneDrive, Yammer e SharePoint prima di cambiare le sottoscrizioni di Microsoft 365 o se un utente lascia l'organizzazione.
ms.openlocfilehash: fbebe72ec47fb6745cee6a12d81117ad08c50846
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636081"
---
# <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>Eseguire il backup dei dati prima di cambiare i piani di Microsoft 365 per le aziende

Se un utente viene spostato in un altro abbonamento con meno servizi correlati ai dati o se un utente lascia l'organizzazione, è possibile scaricare una copia dei dati archiviati in Microsoft 365 prima di passare alla nuova sottoscrizione.
  
## <a name="save-a-copy-of-outlook-information"></a>Salvataggio di una copia delle informazioni di Outlook

Se gli utenti dispongono di Outlook, possono [esportare o eseguire il backup di posta elettronica, contatti e calendario in un file PST di Outlook prima di](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91) commutare il piano.
  
Dopo aver completato il passaggio al nuovo piano, gli utenti possono [importare messaggi di posta elettronica, contatti e calendario da un file PST di Outlook](https://support.office.com/article/431a8e9a-f99f-4d5f-ae48-ded54b3440ac).
  
## <a name="save-files-stored-in-onedrive-for-business"></a>Salvare i file archiviati in OneDrive for business

Prima di passare a una sottoscrizione diversa, gli utenti possono [scaricare file e cartelle da OneDrive o SharePoint](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05) in un percorso diverso, ad esempio una cartella sul disco rigido del computer, o una condivisione file sulla rete dell'organizzazione.
  
## <a name="save-yammer-information"></a>Salvare le informazioni di Yammer

Gli amministratori possono esportare tutti i messaggi, le note, i file, gli argomenti, gli utenti e i gruppi in un file ZIP. Per ulteriori informazioni, vedere [esportare i dati da Yammer Enterprise](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data). Gli sviluppatori possono utilizzare l' [API Yammer](https://go.microsoft.com/fwlink/p/?linkid=842495) anche per eseguire questa operazione.
  
## <a name="how-to-save-sharepoint-information"></a>Come salvare le informazioni di SharePoint

Se un utente viene spostato da un abbonamento con SharePoint Online a uno che non lo contiene, il riquadro di **SharePoint** non verrà più visualizzato nel menu Microsoft 365.
  
Tuttavia, se il nuovo abbonamento è nella stessa organizzazione di quello precedente, l'utente potrà continuare ad accedere al sito del team di SharePoint e potrà visualizzare e aggiornare blocchi appunti, documenti, attività e calendari usando l'URL diretto del sito del team.
  
> [!TIP]
> è consigliabile che gli utenti accedano al sito del team prima del cambio di abbonamento e salvino l'URL come preferito o come segnalibro nel browser.
  
Per impostazione predefinita, il formato dell'URL del sito Web del team è:
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

dove _ \<orgDomain\> _ è l'URL dell'organizzazione.
  
Ad esempio, se il dominio dell'organizzazione è contoso.onmicrosoft.com, l'URL diretto del sito del team sarà https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx.
  
Naturalmente gli utenti possono anche scaricare i documenti di SharePoint Online dal sito del team di SharePoint nel loro computer locale o in un'altra posizione in qualsiasi momento.