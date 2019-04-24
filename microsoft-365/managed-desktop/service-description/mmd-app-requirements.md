---
title: Requisiti per le app di Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: de6cc7d77e023a9d41961e5fbcce060f1bb659ae
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278336"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Requisiti per le app di Microsoft Managed Desktop

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
Le applicazioni line-of-business che si desidera distribuire ai dispositivi Microsoft Managed Desktop devono soddisfare i requisiti di questo argomento. 

## <a name="application-condition"></a>Condizione dell'applicazione

È importante che le applicazioni non influiscano negativamente sull'ambiente Microsoft Managed Desktop. Di seguito sono indicati i requisiti che un'applicazione deve soddisfare affinché Microsoft la implementi. Per qualsiasi applicazione o driver specificata, Microsoft può rinunciare a qualsiasi requisito fornito nel presente documento. Microsoft può decidere di rimuovere qualsiasi applicazione o driver che influisce negativamente sulle prestazioni e l'affidabilità dei dispositivi Microsoft Managed Desktop.

## <a name="deployable-using-microsoft-technologies"></a>Deployable using Microsoft Technologies

Microsoft Managed Desktop utilizza Intune, Microsoft Store e Microsoft Store for business per la distribuzione di applicazioni. Di conseguenza, le applicazioni devono essere impacchettate in modo da poter essere distribuite dalla versione corrente di tali servizi.

## <a name="prohibited-app-classes"></a>Classi app non consentite

Alcuni tipi di applicazioni non sono consentiti sui dispositivi Microsoft Managed Desktop:
- software di terze parti antivirus, di sicurezza o di controllo
- Web browser di terze parti
- Versioni di Microsoft Office precedenti a Office 365 Pro Plus
- Applicazioni che installino o bundle altri software di terze parti

## <a name="restricted-app-behaviors"></a>Comportamenti delle app con limitazioni

Alcuni comportamenti dell'applicazione possono essere pregiudizievoli per l'esperienza degli utenti o per presentare un rischio per la sicurezza per i dispositivi desktop Microsoft gestiti. Le applicazioni non devono presentare i comportamenti o le caratteristiche seguenti: 

Esperienza utente:
- Installare servizi in background o generare processi in background di lunga durata
- Aggiungersi al percorso di avvio di Windows

Sicurezza:
- Chiamare le finestre non documentate o le API di Office o le dipendenze nelle strutture di dati interne di Windows o di Office
- Agire come App Store o avere un gestore di estensioni incorporato
- Elevare i privilegi dell'utente finale
- Sono note vulnerabilità relative alla sicurezza
- Firmato utilizzando un certificato che non viene eseguito su una radice attendibile
- Crittografare o limitare l'accesso ai dati degli utenti finali
- Modificare il codice del sistema operativo in fase di esecuzione

## <a name="driver-deployment"></a>Distribuzione del driver

Se un driver non è disponibile in Windows Update o è firmato separatamente da Windows Hardware Quality Lab (WHQL), Microsoft deve approvare un driver prima che Microsoft implementi il driver per i dispositivi Microsoft Managed Desktop.
