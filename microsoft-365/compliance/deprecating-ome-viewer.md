---
title: Deprecating Message Encryption Viewer App
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: L'app Visualizzatore office 365 Message Encryption (OME) è stata rimossa dagli archivi Android e Apple nel 2018.
ms.openlocfilehash: 9aca6fa2c0e9b276b666ffa187e3d18f061e7224
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817865"
---
# <a name="deprecating-message-encryption-viewer-app"></a>Deprecating Message Encryption Viewer App

Il 15 agosto 2018 è stata rimossa l'app per dispositivi mobili Office 365 Message Encryption (OME) Viewer dagli store Android e Apple. L'app office 365 Message Encryption Viewer per dispositivi mobili era necessaria per leggere i messaggi di posta elettronica e gli allegati crittografati con la versione precedente di OME nei telefoni Apple e Android. Oltre a rimuovere l'app Visualizzatore OME, non vengono apportate altre modifiche alla versione precedente di OME.
  
## <a name="changes-from-august-2018"></a>Modifiche da agosto 2018

Come annunciato a settembre 2017, è stata rilasciata una nuova versione della crittografia dei messaggi di [Office 365](https://aka.ms/ome2017) in modo che gli utenti possano inviare messaggi crittografati e protetti a chiunque all'interno o all'esterno dell'organizzazione senza la necessità dell'app per dispositivi mobili. Da allora, sono state aggiunte funzionalità aggiuntive:
  
- [Modello di sola crittografia](https://aka.ms/encryptonly)

- [Controllo per decrittografare gli allegati](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)
    
Con questa modifica, gli utenti non saranno più in grado di scaricare l'app per dispositivi mobili Visualizzatore crittografia messaggi di Office 365 a partire dal 1° agosto. Di conseguenza, i destinatari di posta elettronica potrebbero non essere in grado di leggere i messaggi crittografati con la versione precedente di OME su alcuni dispositivi mobili Android e Apple. Tuttavia, potranno comunque leggere questi messaggi nei personal computer (tramite browser desktop). Gli utenti che hanno già scaricato l'app continueranno a essere in grado di usarla.
  
## <a name="why-this-change-was-made"></a>Perché questa modifica è stata apportata

La nuova versione di OME non richiede più un'app per dispositivi mobili per leggere i messaggi di posta elettronica protetti e gli allegati. I clienti che utilizzano le nuove funzionalità di OME possono visualizzare il messaggio protetto in Outlook mobile e i non clienti possono visualizzare i messaggi protetti in un browser.
  
Richiedere agli utenti di scaricare un'app per dispositivi mobili è un altro ostacolo per consentire ai clienti di visualizzare i messaggi protetti. Le nuove funzionalità di crittografia dei messaggi di Office 365 offrono un'esperienza mobile migliore.
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a>Posso ancora usare la versione precedente della crittografia dei messaggi di Office 365

La versione precedente della crittografia dei messaggi di Office 365 non sarà deprecata in questo momento, tuttavia, sono stati apportati miglioramenti significativi alla nuova versione di Crittografia messaggi di Office 365, che rendono più semplice crittografare e proteggere i dati sensibili a chiunque e su qualsiasi dispositivo, inclusa la possibilità per gli utenti di leggere i messaggi protetti direttamente in Outlook (desktop, mobile e Web). 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Cosa devo fare per prepararmi a questa modifica

Se l'organizzazione attualmente invia allegati crittografati ai destinatari che richiedono l'app Visualizzatore OME, è necessario aggiornare la documentazione e le risorse di formazione.
  
È consigliabile aggiornare le regole esistenti del flusso di posta di Exchange per utilizzare la versione corrente di OME in modo che l'organizzazione possa sfruttare le funzionalità nuove e migliorate. Dopo aver configurato le nuove funzionalità di OME, i destinatari non dovranno utilizzare l'app Visualizzatore OME per leggere i messaggi crittografati nei dispositivi mobili.
  
Microsoft consiglia di pianificare il passaggio alle nuove funzionalità di OME non appena è ragionevole per l'organizzazione. Per istruzioni, vedere Configurare le nuove funzionalità di crittografia dei [messaggi di Office 365.](set-up-new-message-encryption-capabilities.md) Per ulteriori informazioni sul funzionamento delle nuove funzionalità, vedere Crittografia messaggi di [Office 365.](ome.md)
  

