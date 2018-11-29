---
title: Preparare la distribuzione client di Office per Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Informazioni su come installare le applicazioni di Office a 32 bit nei computer Windows 10 e mantenerle aggiornate automaticamente.
ms.openlocfilehash: 16a8230d60157f1c6731ac639d89533b05aa3afe
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868276"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a>Preparare la distribuzione client di Office per Microsoft 365 Business

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Preparare l'installazione automatica delle app di Office nei computer client

È possibile usare Microsoft 365 Business per installare automaticamente le app di Office a 32 bit in computer Windows 10 e mantenerle aggiornate.
  
Questa procedura funziona al meglio se nel computer dell'utente finale è installato Windows 10 Business e:
  
- Non sono installate app desktop di Office (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access e OneDrive).
    
    oppure
    
- È installata una versione A portata di clic di Office.
    
Per determinare se si ha la versione A portata di clic di Office, in un'app di Office qualsiasi scegliere **File** \> **Account** ( **Account di Office** in Outlook). Se la sezione Aggiornamenti di Office ha lo stesso aspetto della figura seguente, significa che l'installazione è stata eseguita tramite A portata di clic. 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Chi trarrà vantaggio da questa caratteristica**
  
L'utente finale il cui PC:
  
- **Ha** una licenza utente di Windows 10 Business, una licenza attiva di Microsoft 365 Business, Windows 10 Creators Update e fa parte di un dominio Azure Active Directory. 
    
- **Non ha** le app di Office a 64 bit (ad esempio Word, Excel, Powerpoint). Se le app di Office a 64 bit sono necessarie, questa caratteristica non è ideale perché non è offerto alcun supporto per l'attivazione di una versione A portata di clic di Office 2016 a 64 bit dalla console di amministrazione di Microsoft 365 Business. 
    
- **Non ha** app autonome della versione 2016 installate tramite Windows Installer (MSI), ad esempio Visio o Project. Microsoft 365 Business aggiorna Office alla versione A portata di clic di Office 2016, che non funziona con queste app autonome. 
    
La tabella seguente descrive nel dettaglio le azione che gli utenti finali/amministratori potrebbero dover eseguire, a seconda dello stato iniziale, per distribuire correttamente la versione A portata di clic di Office a 32 bit dalla console di amministrazione di Microsoft 365 Business.
  
|**Stato di installazione iniziale di Office**|**Azione da eseguire prima di installare Office di Microsoft 365 Business**|**Stato finale**|
|:-----|:-----|:-----|
|Nessuna famiglia di applicazioni Office installata  <br/> |Nessuno  <br/> |Office 2016 a 32 bit è installato con A portata di clic  <br/> |
|Versione A portata di clic a 32 bit di Office esistente (2016 o precedente) e nessuna app autonoma  <br/> |Nessuno  <br/> |Aggiornamento all'ultima versione A portata di clic a 32 bit di Office 2016, in base alle necessità **\*** <br/> |
|Versione A portata di clic a 32 bit di Office esistente e app di Office autonome A portata di clic a 32 o 64 bit (ad esempio Visio, Project)  <br/> |Nessuno  <br/> |Le app autonome non vengono interessate. La famiglia di applicazioni viene aggiornata alla versione A portata di clic a 32 bit di Office 2016  <br/> |
|Versione A portata di clic a 32 bit di Office esistente e qualsiasi app di Office autonoma a 32 o 64 bit (tranne la versione 2016) installata tramite MSI  <br/> |Nessuno  <br/> |Le app autonome non vengono interessate. La famiglia di applicazioni viene aggiornata alla versione A portata di clic a 32 bit di Office 2016  <br/> ||||
|Qualsiasi versione A portata di clic a 64 bit di Office esistente  <br/> |Disinstallare le app di Office a 64 bit, se è possibile sostituirle con le app di Office a 32 bit  <br/> |Se le app di Office a 64 bit vengono rimosse, viene installata la versione A portata di clic a 32 bit di Office 2016  <br/> |
|Un'installazione MSI esistente di Office 2016 con o senza app autonome  <br/> |Disinstallare Office 2016 MSI.  <br/> |Viene installata la versione A portata di clic a 32 bit di Office 2016. Nessuna modifica alle app autonome  <br/> |
|Installazione MSI esistente di Office 2013 (o versione precedente) e/o app autonome di Office  <br/> |Nessuno  <br/> |La versione A portata di clic a 32 bit di Office 2016 e l'installazione MSI di Office preesistente (e le app autonome) coesistono affiancate  <br/> |
||||
   
 **(\*) Nota:** l'aggiornamento alla versione A portata di clic a 32 bit di Office 2016 non viene eseguito a causa di un bug noto. Una correzione è in fase di sviluppo. 
  


