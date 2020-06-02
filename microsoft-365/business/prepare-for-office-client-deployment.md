---
title: Preparare la distribuzione dei client di Office da Microsoft 365 for business
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Informazioni su come installare automaticamente le app di Office a 32 bit nei computer Windows 10 e mantenerle aggiornate.
ms.openlocfilehash: 2de492914edbde2afe593aac290c4a634b801443
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470948"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a>Preparare la distribuzione dei client di Office da Microsoft 365 for business

Questo articolo si applica a Microsoft 365 Business Premium.

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Preparare l'installazione automatica delle app di Office nei computer client

È possibile utilizzare Microsoft 365 Business Premium per installare automaticamente le app di Office a 32 bit nei computer Windows 10 e mantenerle aggiornate con gli aggiornamenti.
  
L'installazione automatica funziona meglio se il computer dell'utente finale è in Windows 10 business e:
  
- Non sono installate app desktop di Office (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access e OneDrive).
    
    oppure
    
- È installata una versione A portata di clic di Office.
    
Per determinare se si ha la versione A portata di clic di Office, in un'app di Office qualsiasi scegliere **File** \> **Account** ( **Account di Office** in Outlook). Se si visualizzano **gli aggiornamenti di Office** , come illustrato nella figura seguente, l'installazione è stata eseguita tramite la funzione a portata di clic. 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Vantaggi dell'utilizzo di questa funzionalità**
  
L'utente finale il cui PC:
  
- **Ha** una licenza per gli utenti di Windows 10 business, una licenza attiva di Microsoft 365 per le aziende, un aggiornamento di Windows 10 Creator ed è aggiunto ad Azure Active Directory. 
    
- **Non dispone** di app di Office a 64 bit (ad esempio: Word, Excel, PowerPoint). Se sono necessarie le app di Office a 64 bit, questa funzionalità non è adatta perché non è disponibile alcun supporto per l'attivazione di una versione di Office a portata di clic a 64 bit a 2016 dalla console di amministrazione di Microsoft 365 per le aziende. 
    
- **Non ha** app autonome della versione 2016 installate tramite Windows Installer (MSI), ad esempio Visio o Project. Microsoft 365 for business aggiorna Office alla versione a portata di clic di Office 2016 e non funziona con le app autonome MSI di Office 2016. 
    
Nella tabella seguente vengono illustrate le azioni che potrebbero essere necessarie per gli utenti finali e gli amministratori, a seconda dello stato iniziale, per avere una versione a portata di clic di 32 bit di distribuzione di Office dalla console di amministrazione di Microsoft 365 per le aziende.
  
|**Stato di installazione iniziale di Office**|**Azione da eseguire prima dell'installazione di Microsoft 365 per le aziende**|**Stato finale**|
|:-----|:-----|:-----|
|Nessuna famiglia di applicazioni Office installata  <br/> |Nessuno  <br/> |Office 2016 32 bit è installato tramite la funzione a portata di clic  <br/> |
|Versione A portata di clic a 32 bit di Office esistente (2016 o precedente) e nessuna app autonoma  <br/> |Nessuno  <br/> |Aggiornamento all'ultima versione A portata di clic a 32 bit di Office 2016, in base alle necessità **\*** <br/> |
|Versione a portata di clic a 32 bit di Office e a portata di clic su app di Office autonoma a 32 bit o a 64 bit (ad esempio, Visio, Project)  <br/> |Nessuno  <br/> |Le app autonome non sono intaccate. La famiglia di applicazioni viene aggiornata alla versione A portata di clic a 32 bit di Office 2016  <br/> |
|Versione A portata di clic a 32 bit di Office esistente e qualsiasi app di Office autonoma a 32 o 64 bit (tranne la versione 2016) installata tramite MSI  <br/> |Nessuno  <br/> |Le app autonome non sono intaccate. La famiglia di applicazioni viene aggiornata alla versione A portata di clic a 32 bit di Office 2016  <br/> ||||
|Qualsiasi versione A portata di clic a 64 bit di Office esistente  <br/> |Disinstallare le app di Office a 64 bit, se è possibile sostituirle con le app di Office a 32 bit  <br/> |Se le app di Office a 64 bit vengono rimosse, viene installata la versione A portata di clic a 32 bit di Office 2016  <br/> |
|Un'installazione MSI esistente di Office 2016 con o senza app autonome  <br/> |Disinstallare Office 2016 MSI.  <br/> |Viene installata la versione A portata di clic a 32 bit di Office 2016. Nessuna modifica alle app autonome  <br/> |
|Installazione MSI esistente di Office 2013 (o versione precedente) e/o app autonome di Office  <br/> |Nessuno  <br/> |La versione A portata di clic a 32 bit di Office 2016 e l'installazione MSI di Office preesistente (e le app autonome) coesistono affiancate  <br/> |
||||
   
 **(\*) Nota:** l'aggiornamento alla versione A portata di clic a 32 bit di Office 2016 non viene eseguito a causa di un bug noto. È in corso una correzione. 
  
