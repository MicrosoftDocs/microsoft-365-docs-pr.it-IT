---
title: Deprecating Message Encryption Viewer App
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
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
description: L'app visualizzatore Office 365 Message Encryption (OME) è stata rimossa dagli store Android e Apple nel 2018.
ms.openlocfilehash: bb96601a8a542d53f6732ab9316051c1a820ba46
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741523"
---
# <a name="deprecating-message-encryption-viewer-app"></a>Deprecating Message Encryption Viewer App

Il 15 agosto 2018 abbiamo rimosso l'app per dispositivi mobili Office 365 Message Encryption (OME) Viewer dagli Store Android e Apple. L Visualizzatore Office 365 Message Encryption'app per dispositivi mobili era necessaria per leggere i messaggi di posta elettronica e gli allegati crittografati con la versione precedente di OME nei telefoni Apple e Android. Oltre a rimuovere l'app Visualizzatore OME, non vengono apportate altre modifiche alla versione precedente di OME.
  
## <a name="changes-from-august-2018"></a>Modifiche da agosto 2018

Come annunciato a settembre 2017, abbiamo rilasciato una nuova versione di [Office 365 Message Encryption in](https://aka.ms/ome2017) modo che gli utenti possano inviare messaggi crittografati e protetti a chiunque all'interno o all'esterno dell'organizzazione senza il requisito dell'app per dispositivi mobili. Da allora, sono state aggiunte funzionalità aggiuntive:
  
- [Modello di sola crittografia](https://aka.ms/encryptonly)

- [Controllo per decrittografare gli allegati](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)

Con questa modifica, gli utenti non potranno più scaricare l'app Visualizzatore Office 365 Message Encryption per dispositivi mobili a partire dal 1° agosto. Di conseguenza, i destinatari di posta elettronica potrebbero non essere in grado di leggere i messaggi crittografati con la versione precedente di OME su alcuni dispositivi mobili Android e Apple. Tuttavia, potranno comunque leggere questi messaggi nei personal computer (tramite browser desktop). Gli utenti che hanno già scaricato l'app continueranno a usarla.
  
## <a name="why-this-change-was-made"></a>Perché è stata apportata questa modifica

La nuova versione di OME non richiede più un'app per dispositivi mobili per leggere i messaggi di posta elettronica protetti e gli allegati. I clienti che usano le nuove funzionalità OME possono visualizzare il messaggio protetto in Outlook dispositivi mobili e i non clienti possono visualizzare i messaggi protetti in un browser.
  
Richiedere agli utenti di scaricare un'app per dispositivi mobili è un altro ostacolo per i clienti per visualizzare i messaggi protetti. Le nuove funzionalità Office 365 Message Encryption offrono un'esperienza mobile migliore.
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a>È comunque possibile usare la versione precedente di Office 365 Message Encryption

La versione precedente di Office 365 Message Encryption non verrà deprecata in questo momento, tuttavia, sono stati apportati miglioramenti significativi alla nuova versione di Office 365 Message Encryption, che rendono più semplice crittografare e proteggere i dati sensibili a chiunque e su qualsiasi dispositivo, inclusa la possibilità per gli utenti di leggere i messaggi protetti direttamente in Outlook (desktop, mobile e Web). 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Cosa devo fare per prepararmi a questa modifica

Se l'organizzazione attualmente invia allegati crittografati ai destinatari che richiedono l'app Visualizzatore OME, è consigliabile aggiornare la documentazione e le risorse di formazione.
  
È consigliabile aggiornare le regole Exchange del flusso di posta elettronica esistenti per utilizzare la versione corrente di OME in modo che l'organizzazione possa sfruttare le funzionalità nuove e migliorate. Dopo aver configurato le nuove funzionalità OME, i destinatari non dovranno utilizzare l'app Visualizzatore OME per leggere i messaggi crittografati nei dispositivi mobili.
  
Microsoft consiglia di pianificare il passaggio alle nuove funzionalità OME non appena è ragionevole per l'organizzazione. Per istruzioni, vedere [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md). Per ulteriori informazioni sul funzionamento delle nuove funzionalità, vedere Office 365 Message Encryption [.](ome.md)
  

