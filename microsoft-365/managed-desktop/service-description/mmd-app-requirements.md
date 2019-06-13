---
title: Requisiti per le app di Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: ded8bcfd87a6b430dfc4be055a582b482872b104
ms.sourcegitcommit: 498340389e1c34f49f0b2da382c23c8d5334ae47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/12/2019
ms.locfileid: "34913017"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Requisiti per le app di Microsoft Managed Desktop

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
Per garantire le prestazioni, l'affidabilità e la funzionalità dei dispositivi Microsoft Managed Desktop, le app di una linea del cliente non devono influire sul serio sull'esperienza dell'utente finale o modificare la posizione di sicurezza. Di conseguenza, le applicazioni line-of-business che si desidera distribuire ai dispositivi Microsoft Managed Desktop devono soddisfare i requisiti di questo argomento.

## <a name="application-condition"></a>Condizione dell'applicazione

È importante che le applicazioni non influiscano negativamente sull'ambiente Microsoft Managed Desktop. Di seguito sono indicati i requisiti che un'applicazione deve soddisfare per la distribuzione di un'applicazione. Per qualsiasi applicazione o driver specificata, Microsoft può rinunciare a qualsiasi requisito fornito nel presente documento. Microsoft può decidere di rimuovere qualsiasi applicazione o driver che influisce negativamente sulle prestazioni e l'affidabilità dei dispositivi Microsoft Managed Desktop.

## <a name="centrally-managed-apps"></a>App gestite centralmente

Tutte le applicazioni e i driver installati nei dispositivi gestiti Microsoft devono essere distribuiti tramite Microsoft Intune, Microsoft Store o Microsoft Store for business. Se disponibile, i driver verranno distribuiti anche tramite il servizio Windows Update. 

## <a name="prohibited-app-classes"></a>Classi app non consentite

Alcuni tipi di applicazioni non sono consentiti sui dispositivi Microsoft Managed Desktop:
- software di terze parti antivirus, di sicurezza o di controllo
- Versioni di Microsoft Office precedenti a Office 365 Pro Plus
- Applicazioni che installino o bundle altri software di terze parti

## <a name="restricted-app-behaviors"></a>Comportamenti delle app con limitazioni

Alcuni comportamenti delle app possono influire negativamente sull'esperienza dell'utente o possono presentare un rischio per la sicurezza per i dispositivi desktop Microsoft gestiti. Le app con i comportamenti seguenti non sono autorizzate a essere eseguite nell'ambiente Microsoft Managed Desktop senza una specifica esenzione da parte di Microsoft.

Esperienza utente:
- Installare servizi in background
- Aggiungersi al percorso di avvio di Windows
- Le applicazioni dipendono dai driver
- Web browser di terze parti

Sicurezza:
- Elevare i privilegi dell'utente finale
- Agire come App Store o avere un gestore di estensioni incorporato
- Sono note vulnerabilità relative alla sicurezza
- Crittografare o limitare l'accesso ai dati degli utenti finali
- È senza segno o viene firmato utilizzando un certificato che non viene eseguito fino a una radice attendibile


## <a name="driver-deployment"></a>Distribuzione del driver

Microsoft Managed Desktop supporta solo i driver di dispositivo disponibili tramite Windows Update o la posta in arrivo installata con il dispositivo gestito Microsoft. 

Se un'applicazione richiede un driver specifico per l'esecuzione, è considerata un'applicazione limitata e richiede una deroga per la distribuzione in Microsoft Managed Desktop. 

