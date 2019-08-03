---
title: Tecnologie Microsoft Managed Desktop
description: In questo argomento sono elencate le tecnologie e le app utilizzate in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9f3094b1a1272b0c200271b8d5703fe7173683a6
ms.sourcegitcommit: 6b5370cded5d8259c9ed561eed324227f74c410b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/03/2019
ms.locfileid: "36171736"
---
# <a name="microsoft-managed-desktop-technologies"></a>Tecnologie Microsoft Managed Desktop

In questo argomento sono elencate le tecnologie e le app utilizzate in Microsoft Managed Desktop.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise Licensing è necessaria per tutti gli utenti di Microsoft Managed Desktop. Per ulteriori informazioni sui requisiti di licenza per il servizio, vedere [prerequisiti per Microsoft Managed Desktop](../get-ready/prerequisites.md).

In questo argomento vengono riepilogati i componenti inclusi nelle licenze Enterprise necessarie, con una descrizione del modo in cui il servizio utilizza ogni componente con i dispositivi Microsoft Managed Desktop. I ruoli e le responsabilità specifici per ogni area sono descritti in tutta la documentazione relativa a Microsoft Managed Desktop. 

## <a name="office-365-e3"></a>Office 365 E3
 |
 --- | ---
Famiglia di prodotti Office 365 standard (a 64 bit) | La famiglia di applicazioni standard per Office verrà spedita con il dispositivo: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for business, OneNote.<br><br>64 le versioni complete di Microsoft Project e Microsoft Visio non sono incluse in Office 365 (C2R). Tuttavia, poiché l'installazione di queste applicazioni dipende dall'installazione standard di Office Suite, Microsoft Managed Desktop ha creato distribuzioni e gruppi di sicurezza predefiniti di Microsoft Intune che è possibile utilizzare per distribuire queste applicazioni in utenti finali con licenza. Per ulteriori informazioni, vedere [Install Microsoft Project o Microsoft Visio su Microsoft Managed Desktop Devices](../get-started/project-visio.md)  
Archivia le app |    Microsoft Sway e Power BI non vengono forniti con il dispositivo. Queste app sono disponibili per il download da Microsoft Store.
Applicazioni Win32 |    I team non vengono forniti con il dispositivo, ma vengono inclusi nel pacchetto e forniti da Microsoft per i dispositivi desktop Microsoft gestiti. Il client Azure Information Protection non viene fornito con il dispositivo, ma è possibile ottenere questo pacchetto per la distribuzione. 
Applicazioni Web |  Yammer, Office in un browser, approfondendo, Flow, StaffHub, PowerApps e Planner non vengono forniti con il dispositivo. Gli utenti possono accedere alla versione Web di queste applicazioni con un browser.


## <a name="windows-10-enterprise-e5"></a>Windows 10 Enterprise E5

 |
 --- | ---
Virtualizzazione di applicazioni (App-V) |    Microsoft Managed Desktop non supporta questo tipo di distribuzione poiché non è supportato da Microsoft Intune.
Protezione avanzata dalle minacce di Microsoft Defender |  Microsoft Managed Desktop utilizza questo strumento per monitorare la sicurezza dei dispositivi. 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    È possibile utilizzare tutte le caratteristiche di Enterprise Mobility + Security E3 e Azure Active Directory Premium P2 per gestire i dispositivi MDM.
Microsoft Cloud App Security |  È possibile utilizzare questa funzionalità facoltativa con Microsoft Managed Desktop.
Azure Information Protection P2  | È possibile utilizzare questa funzionalità facoltativa con Microsoft Managed Desktop.
