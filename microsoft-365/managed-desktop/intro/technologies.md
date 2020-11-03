---
title: Tecnologie Microsoft Managed Desktop
description: In questo argomento sono elencate le tecnologie e le app utilizzate in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b98cec62a018556bfbd31df0aa824acbd00b37b6
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846241"
---
# <a name="microsoft-managed-desktop-technologies"></a>Tecnologie Microsoft Managed Desktop

In questo argomento sono elencate le tecnologie e le app utilizzate in Microsoft Managed Desktop.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise Licensing è necessaria per tutti gli utenti di Microsoft Managed Desktop. Per ulteriori informazioni sui requisiti di licenza per il servizio, vedere [prerequisiti per Microsoft Managed Desktop](../get-ready/prerequisites.md).

In questo argomento vengono riepilogati i componenti inclusi nelle licenze Enterprise necessarie, con una descrizione del modo in cui il servizio utilizza ogni componente con i dispositivi Microsoft Managed Desktop. I ruoli e le responsabilità specifici per ogni area sono descritti in tutta la documentazione relativa a Microsoft Managed Desktop. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 o E5
 |
 --- | ---
Microsoft 365 Apps for Enterprise (64 bit) | Queste applicazioni di Office verranno fornite con il dispositivo: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for business, OneNote.<br><br>Le versioni complete di 64 bit di Microsoft Project e Microsoft Visio non sono incluse. Tuttavia, poiché l'installazione di queste applicazioni dipende dall'installazione di Microsoft 365 Apps for Enterprise, Microsoft Managed Desktop ha creato distribuzioni e gruppi di sicurezza predefiniti di Microsoft Intune che è possibile utilizzare per distribuire queste applicazioni agli utenti con licenza. Per ulteriori informazioni, vedere [Install Microsoft Project o Microsoft Visio su Microsoft Managed Desktop Devices](../get-started/project-visio.md).
OneDrive for Business |Azure Active Directory Single Sign-on è abilitato per gli utenti al primo accesso a OneDrive for business.<br><br>È incluso il reindirizzamento delle cartelle note per le cartelle "desktop", "documento" e "immagini"; abilitata e configurata da Microsoft Managed Desktop. 
Archivia le app |    Microsoft Sway e Power BI non vengono forniti con il dispositivo. Queste app sono disponibili per il download da Microsoft Store.
Applicazioni Win32 |    I team non vengono forniti con il dispositivo, ma vengono inclusi nel pacchetto e forniti da Microsoft per i dispositivi desktop Microsoft gestiti. Il client Azure Information Protection non viene fornito con il dispositivo, ma è possibile ottenere questo pacchetto per la distribuzione. 
Applicazioni Web |  Yammer, Office in un browser, approfondendo, Flow, StaffHub, PowerApps e Planner non vengono forniti con il dispositivo. Gli utenti possono accedere alla versione Web di queste applicazioni con un browser.


## <a name="windows-10-enterprise-e3-or-e5"></a>Windows 10 Enterprise E3 o E5

 |
 --- | ---
Virtualizzazione di applicazioni (App-V) |    I clienti possono distribuire pacchetti App-V utilizzando il client di gestione delle app Win32 di Intune.
Microsoft Defender ATP |    Microsoft Managed Desktop utilizza questo strumento per monitorare la sicurezza dei dispositivi. 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    È possibile utilizzare tutte le caratteristiche di Enterprise Mobility + Security E3 e Azure Active Directory Premium P2 per gestire i dispositivi MDM.
Microsoft Cloud App Security |  È possibile utilizzare questa funzionalità facoltativa con Microsoft Managed Desktop.
Azure Information Protection P2  | È possibile utilizzare questa funzionalità facoltativa con Microsoft Managed Desktop.
