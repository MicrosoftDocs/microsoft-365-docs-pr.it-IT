---
title: Tecnologie Microsoft Managed Desktop
description: In questo argomento sono elencate le tecnologie e le app utilizzate in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 914a90b4267132c9cb942740ceb974b084bcdf82
ms.sourcegitcommit: 2f4a61f02ea90102ded8e5d71c9b78a1f7f6b789
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2019
ms.locfileid: "35778091"
---
# <a name="microsoft-managed-desktop-technologies"></a>Tecnologie Microsoft Managed Desktop

In questo argomento sono elencate le tecnologie e le app utilizzate in Microsoft Managed Desktop.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise Licensing è necessaria per tutti gli utenti di Microsoft Managed Desktop. Per ulteriori informazioni sui requisiti di licenza per il servizio, vedere [prerequisiti per Microsoft Managed Desktop](../get-ready/prerequisites.md).

Di seguito sono riportati tutti i componenti inclusi nelle licenze Enterprise necessarie e il modo in cui il servizio utilizza ogni componente con i dispositivi Microsoft Managed Desktop. I ruoli e le responsabilità specifici per ogni area sono descritti in tutto l'argomento Microsoft Managed Desktop. 

## <a name="office-365-e3"></a>Office 365 E3
 |
 --- | ---
Famiglia di prodotti Office 365 standard (64bit) * | La famiglia di applicazioni standard per Office verrà spedita con il dispositivo: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for business, OneNote.<br><br>Le versioni a 64 bit per l'esecuzione (C2R) complete di Microsoft Project e Microsoft Visio non sono incluse nella famiglia di prodotti standard di Office 365.  Tuttavia, dal momento che l'installazione di queste applicazioni dipendono dall'installazione standard della famiglia di prodotti Office, Microsoft Managed Desktop ha creato distribuzioni e gruppi di sicurezza predefiniti di Intune che il cliente utilizzerà per distribuire queste applicazioni in utenti finali con licenza.  
Archivia le app |    Microsoft Sway, Power BI desktop non viene fornito con il dispositivo. Queste app sono disponibili per il download da Microsoft Store.
Applicazioni Win32 |    Power BI Pro, Azure Information Protection client e Microsoft Planner non sono forniti con il dispositivo e possono essere inseriti in un pacchetto per la distribuzione da parte del cliente. 
Applicazioni Web |  Yammer, Office in un browser, approfondire, fluire, StaffHub, PowerApps non vengono forniti con il dispositivo. Gli utenti possono accedere alla versione Web di queste applicazioni con un browser.
Skype for business online cloud PBX | Questa funzionalità è disponibile tramite Office 365. Microsoft Managed Desktop non configurerà alcun aspetto del servizio

## <a name="windows-10-enterprise-e5"></a>Windows 10 Enterprise E5

 |
 --- | ---
Protezione delle credenziali |  Microsoft fornirà indicazioni e gestirà gli aspetti cloud di questa funzionalità.
Virtualizzazione di applicazioni (App-V) |    Microsoft Managed Desktop non supporta questo tipo di distribuzione poiché non è supportato in Intune.
Virtualizzazione dell'esperienza utente (UE-V) | Questo non viene utilizzato con i dispositivi gestiti di Microsoft Managed Desktop.
Esperienza utente gestita  | Questo non viene utilizzato con i dispositivi gestiti di Microsoft Managed Desktop. MDM viene utilizzato come soluzione per la gestione dei dispositivi.
Protezione avanzata dalle minacce di Microsoft Defender | Viene utilizzato da Microsoft Managed Desktop per gestire i criteri di sicurezza dei dispositivi. 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Tutti gli aspetti di Enterprise Mobility + Security E3 e AADP possono essere utilizzati per gestire i dispositivi MDM.
Microsoft Cloud App Security |  Caratteristica facoltativa che i clienti possono utilizzare con il servizio Microsoft Managed Desktop.
Azure Information Protection P2  |Caratteristica facoltativa che i clienti possono utilizzare con il servizio Microsoft Managed Desktop.
