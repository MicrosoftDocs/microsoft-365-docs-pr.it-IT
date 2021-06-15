---
title: Preparare la Office client per Microsoft 365 per le aziende
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
description: Scopri come installare automaticamente le app Office a 32 bit Windows 10 e mantenerle aggiornate.
ms.openlocfilehash: 843be426d817da1173769b3b66dc4c054179f0fd
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924228"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a>Preparare la Office client per Microsoft 365 per le aziende

Questo articolo si applica a Microsoft 365 Business Premium.

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Preparare l'installazione automatica delle app di Office nei computer client

Puoi usare Microsoft 365 Business Premium per installare automaticamente le app Office a 32 bit nei computer Windows 10 e mantenerle aggiornati con gli aggiornamenti.
  
L'installazione automatica funziona meglio se il computer dell'utente finale è Windows 10 Business e:
  
- Non sono installate app desktop di Office (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access e OneDrive).
    
    oppure
    
- È installata una versione A portata di clic di Office.
    
Per determinare se si ha la versione A portata di clic di Office, in un'app di Office qualsiasi scegliere **File** \> **Account** ( **Account di Office** in Outlook). Se viene visualizzato **Office aggiornamenti,** come illustrato nella figura seguente, l'installazione è stata eseguita utilizzando A livello di clic. 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Who vantaggi dall'avere questa funzionalità**
  
L'utente finale il cui PC:
  
- **Ha** una Windows 10 Business utente, una licenza Microsoft 365 per le aziende attiva, Windows 10 Creators Update e fa parte di Azure Active Directory. 
    
- **Non dispone di app** Office a 64 bit (ad esempio: Word, Excel, PowerPoint). Se sono necessarie app Office a 64 bit, questa funzionalità non è adatta perché non è disponibile alcun supporto per l'attivazione di una versione a a scelta a 64 bit di Office a 64 bit dalla console di amministrazione di Microsoft 365 per le aziende. 
    
- **Non ha** app autonome della versione 2016 installate tramite Windows Installer (MSI), ad esempio Visio o Project. Microsoft 365 per le aziende Office alla versione A scelta di Office 2016 e questo non funziona con le app autonome MSI Office 2016. 
    
La tabella seguente mostra l'azione che gli utenti finali/amministratori potrebbero dover eseguire, a seconda dello stato iniziale, per avere una versione a 32 bit a 32 bit della distribuzione di Office dalla console di amministrazione di Microsoft 365 for business.<br/>


|Stato di installazione iniziale di Office|Azione da eseguire prima dell'Microsoft 365 per le Office aziendali|Stato finale|
|:-----|:-----|:-----|
|Nessuna famiglia di applicazioni Office installata  <br/> |Nessuno  <br/> |Office 2016 a 32 bit viene installato tramite A click-to-Run  <br/> |
|Versione A portata di clic a 32 bit di Office esistente (2016 o precedente) e nessuna app autonoma  <br/> |Nessuno  <br/> |Aggiornamento all'ultima versione A portata di clic a 32 bit di Office 2016, in base alle necessità **\*** <br/> |
|Versione a 32 bit a 32 bit esistente di Office app Office autonome a 32 o 64 bit (ad esempio, Visio, Project)  <br/> |Nessuno  <br/> |Le app autonome non sono interessate. La famiglia di applicazioni viene aggiornata alla versione A portata di clic a 32 bit di Office 2016  <br/> |
|Versione A portata di clic a 32 bit di Office esistente e qualsiasi app di Office autonoma a 32 o 64 bit (tranne la versione 2016) installata tramite MSI  <br/> |Nessuno  <br/> |Le app autonome non sono interessate. La famiglia di applicazioni viene aggiornata alla versione A portata di clic a 32 bit di Office 2016  <br/> |
|Qualsiasi versione A portata di clic a 64 bit di Office esistente  <br/> |Disinstallare le app Office a 64 bit, se è possibile sostituirle con app Office a 32 bit  <br/> |Se le app di Office a 64 bit vengono rimosse, viene installata la versione A portata di clic a 32 bit di Office 2016  <br/> |
|Un'installazione MSI esistente di Office 2016 con o senza app autonome  <br/> |Disinstallare Office 2016 MSI.  <br/> |Viene installata la versione A portata di clic a 32 bit di Office 2016. Nessuna modifica alle app autonome  <br/> |
|Installazione MSI esistente di Office 2013 (o versione precedente) e/o app autonome di Office  <br/> |Nessuno  <br/> |La versione A portata di clic a 32 bit di Office 2016 e l'installazione MSI di Office preesistente (e le app autonome) coesistono affiancate  <br/> |
||||
   
 **(\*) Nota:** l'aggiornamento alla versione A portata di clic a 32 bit di Office 2016 non viene eseguito a causa di un bug noto. È in corso una correzione. 
  
