---
title: Tecnologie Microsoft Desktop gestiti
description: In questo argomento sono elencate le applicazioni utilizzate in Microsoft Desktop gestiti e le tecnologie.
keywords: Servizio Microsoft Desktop gestiti, Microsoft 365, documentazione
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 4b26ec88e1f4ca95fee6f7c4c927fc06cab32135
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868484"
---
# <a name="microsoft-managed-desktop-technologies"></a>Tecnologie Microsoft Desktop gestiti

In questo argomento sono elencate le applicazioni utilizzate in Microsoft Desktop gestiti e le tecnologie.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

È necessario per il servizio Microsoft Desktop gestiti licenza E5 365 Microsoft (o equivalente). Di seguito sono tutti i componenti inclusi in tali licenze e come Desktop gestiti Microsoft utilizza ogni componente con i dispositivi Desktop gestiti Microsoft.  Ruoli specifici e le responsabilità per ogni area sono descritte in dettaglio nell'intera argomenti Microsoft Desktop gestiti. 

Microsoft 365 E5 è costituito da 3 componenti: Office 365 E5, Windows 10 Enterprise ed E5, mobilità aziendale + E5 sicurezza.  

## <a name="office-365-e5"></a>E5 Office 365
 |
 --- | ---
Famiglia di prodotti Standard di Office 365 (64 bit) * | La famiglia di prodotti Office standard delle applicazioni verranno inviato con il dispositivo: Word, Excel, PowerPoint, Outlook, Publisher, accesso e Skype per le aziende, OneNote.<br><br>Fare clic su Esegui a 64 bit (C2R) versioni complete di Microsoft Project e Microsoft Visio non sono inclusi in Office 365 Standard Suite.  Tuttavia, dopo l'installazione di tali applicazioni dipendono dall'installazione famiglia di prodotti Office standard, Desktop gestiti Microsoft ha creato distribuzioni Intune predefinito e gruppi di sicurezza utilizzato per distribuire le applicazioni per il cliente concesso in licenza agli utenti finali.  
Applicazioni di archiviazione |    Microsoft Sway, Teams Microsoft, Power BI Desktop (non professionisti) non forniti con dispositivi. Queste applicazioni sono disponibili per il download da Microsoft Store.
Applicazioni Win32 |    Power BI Pro, Client di protezione informazioni Azure e Microsoft Planner non vengono fornite con dispositivi e possono essere incluse in pacchetti di distribuzione dal cliente. 
Applicazioni Web |  Yammer, Office Online, Delve, flusso, StaffHub, PowerApps non vengono forniti con il dispositivo. Gli utenti possono accedere alla versione web di queste applicazioni con un browser.
Skype per il Cloud Online Business PBX | Questa funzionalità è disponibile tramite Office 365 E5. Microsoft Desktop gestiti non verrà configurato tutti gli aspetti di tale servizio

## <a name="windows-10-enterprise-e5"></a>Windows 10 Enterprise E5

 |
 --- | ---
Protezione delle credenziali |  Microsoft Desktop gestiti verrà vengono fornite informazioni e gestione di aspetti cloud di questa funzionalità
Protezione del dispositivo (controllo delle applicazioni di Windows Defender) | Microsoft Desktop gestiti verrà creato il criterio. Gestiranno delle firme dei clienti
Gestione AppLocker |  Microsoft Desktop gestiti verrà creato il criterio. Gestiranno delle firme dei clienti
Application Virtualization (App-V) |    Desktop gestiti Microsoft non supporta questo tipo di distribuzione come non è supportato in Intune.
Virtualizzazione di esperienza utente (UE-V) | Non viene utilizzato con i dispositivi Microsoft Managed Desktop gestiti
Esperienza utente gestito  | Non viene utilizzato con i dispositivi Microsoft Managed Desktop gestiti. MDM viene utilizzato come una soluzione di gestione dei dispositivi
Windows Defender Advanced Threat Protection |   Ciò è utilizzata dal Desktop gestiti Microsoft per gestire i criteri di protezione dispositivo. 

## <a name="enterprise-mobility--security"></a>Enterprise Mobility + Security 

 |
 --- | ---
Enterprise Mobility + Security E3<br>P2 Premium di Azure Active Directory |    Tutti gli aspetti della mobilità aziendale + E3 di sicurezza e AADP possono essere utilizzati per la gestione dei dispositivi MDM
Microsoft Cloud App Security |  Si tratta di una funzionalità facoltativa che i clienti possono utilizzare con il servizio Microsoft Desktop gestiti.
Informazioni Azure protezione P2  |Si tratta di una funzionalità facoltativa che i clienti possono utilizzare con il servizio Microsoft Desktop gestiti.
