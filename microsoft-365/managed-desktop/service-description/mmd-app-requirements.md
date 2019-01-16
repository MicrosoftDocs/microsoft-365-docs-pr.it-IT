---
title: Requisiti di app Desktop gestiti Microsoft
description: ''
keywords: Servizio Microsoft Desktop gestiti, Microsoft 365, documentazione
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.openlocfilehash: 6b6c6f6a2e719496578ac1d15c9b94a92a2ab492
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868263"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Requisiti di app Desktop gestiti Microsoft

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
Le applicazioni line-of-business che si desidera distribuire ai dispositivi Desktop gestiti Microsoft devono soddisfare i requisiti in questo argomento. 

## <a name="application-condition"></a>Condizione di applicazione

È importante che le applicazioni non negativamente dell'ambiente Desktop gestito Microsoft. Di seguito sono i requisiti di un'applicazione deve essere soddisfatti per Microsoft per la distribuzione. Per un'applicazione specificata o driver, Microsoft può rinunciare qualsiasi requisito contenuta nel presente documento. Microsoft può decidere di rimuovere un'applicazione o driver che impatta negativamente sulle prestazioni e affidabilità dei dispositivi Desktop gestiti Microsoft.

## <a name="deployable-using-microsoft-technologies"></a>Deployable utilizzando le tecnologie Microsoft

Desktop gestiti Microsoft utilizza Intune, Microsoft Store e Microsoft Store for Business per distribuire le applicazioni. Di conseguenza, è necessario essere un pacchetto applicazioni in modo possono essere distribuiti con la versione vigore di tali servizi.

## <a name="prohibited-app-classes"></a>Classi proibito app

Alcuni tipi di applicazioni non sono consentite per i dispositivi Desktop gestiti Microsoft:
- antivirus parti 3, sicurezza o software di controllo
- 3 web browser di terze parti
- Versioni di Microsoft Office prima di Office 365 Professional Plus
- Applicazioni di installare o aggregano altri software di terze parti 3

## <a name="restricted-app-behaviors"></a>Comportamenti di app con restrizioni

Alcuni comportamenti applicazione possono essere genere pregiudizievole per l'esperienza utente o costituire un rischio di protezione per i dispositivi Desktop gestiti Microsoft. Le applicazioni non devono presentare comportamenti o le caratteristiche seguenti: 

Esperienza utente:
- Installare i servizi in background o generano processi in background di lunga durata
- Aggiungersi al percorso di avvio di Windows

Sicurezza:
- Chiamata non documentate Windows o le API di Office o prendere dipendenze sulle strutture di dati interne Windows o di Office
- Agire come archivio dell'app o hanno estensione incorporata manager
- Aumentare i privilegi dell'utente finale
- Sono noti vulnerabilità di protezione
- Effettuato l'accesso utilizzando un certificato di riporto non viene applicato a un'autorità attendibile
- Crittografare o limitare l'accesso ai dati dell'utente finale
- Modificare il codice del sistema operativo in fase di esecuzione

## <a name="driver-deployment"></a>Distribuzione di driver

A meno che un driver è disponibile in Windows Update o separatamente è firmato da Windows Hardware Quality Lab (WHQL), Microsoft è necessario approvare un driver prima che Microsoft verrà distribuito il driver di dispositivi Desktop gestiti Microsoft.
