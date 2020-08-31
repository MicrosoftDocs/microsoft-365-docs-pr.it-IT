---
title: Minorenni e acquisizione di componenti aggiuntivi dallo Store
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Informazioni sui regolamenti generali sulla protezione dei dati (GDPR) che regolano i dati personali dei minorenni.
ms.openlocfilehash: a738e22a0ac0b995c8e44fcf4cc5a2eb47375be5
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306552"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>Minorenni e acquisizione di componenti aggiuntivi dallo Store

Il regolamento generale sulla protezione dei dati (GDPR) è un regolamento dell'Unione europea che diventerà efficace il 25 maggio 2018. Attribuisce ai diritti degli utenti e alla protezione dei dati. Uno degli aspetti della GDPR è che i minorenni non possono avere i dati personali inviati alle terze parti che il loro genitore o tutore non ha approvato. L'età specifica definita come minorenne dipende dall'area geografica in cui si trova l'individuo.
  
Le regioni che dispongono di regole statutarie sul consenso dei genitori sono gli Stati Uniti, la Corea del sud, il Regno Unito e l'Unione europea. Per queste aree, un minorenne verrà bloccato (tramite Azure Active Directory) dall'acquisizione di nuovi componenti aggiuntivi di Office dall'archivio e dall'esecuzione di componenti aggiuntivi acquisiti in precedenza. Per i paesi senza regole statutarie non sono previste restrizioni per il download.
  
Un utente è determinato a essere un minorenne in base ai dati specificati in Azure Active Directory. L'amministratore dell'organizzazione è responsabile della dichiarazione del gruppo di validità legale e del consenso dei genitori per tale utente.
  
Se l'elemento padre/tutore acconsente a un minorenne utilizzando un componente aggiuntivo specifico, l'amministratore dell'organizzazione può utilizzare la distribuzione centralizzata per distribuire il componente aggiuntivo a tutti i minorenni che dispongono di un consenso.
  
Per essere conformi a GDPR per i minorenni, è necessario assicurarsi che una delle seguenti build di Office venga distribuita nella propria scuola/organizzazione.
 
 **Per Word, Excel, PowerPoint e Project**: 

|**Piattaforma** <br/> |**Numero di build** <br/> |
|:-----|:-----|
|Microsoft 365 Apps for Enterprise (canale corrente)  <br/> |9001,2138   <br/> |
|Microsoft 365 Apps for Enterprise (canale semestrale per l'organizzazione)  <br/> |8431,2159  <br/> |
|Office 2016 per Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 per Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 per Mac  <br/> |16.11.18020200  <br/> |
|Office per il Web  <br/> |N/D  <br/> |
   
 **Per Outlook**: 
  
|**Piattaforma** <br/> |**Numero di build** <br/> |
|:-----|:-----|
|Outlook 2016 per Windows (MSI)  <br/> |Build no TBD  <br/> |
|Outlook 2016 per Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 per Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook Mobile per iOS  <br/> |2.75.0  <br/> |
|Outlook Mobile per Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |N/D  <br/> |

 **Requisiti di Office 2013**
  
Word, Excel e PowerPoint 2013 per Windows supportano gli stessi controlli secondari se è abilitata la libreria di autenticazione di Active Directory (ADAL). Sono disponibili due opzioni per la conformità, come illustrato di seguito.
  
- **Abilitare adal**. In questo articolo viene illustrato come abilitare ADAL per Office 2013: [utilizzo dell'autenticazione moderna di Microsoft 365 con i client di Office](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).<br/>È inoltre necessario impostare le chiavi del registro di sistema per abilitare ADAL come spiegato in [Enable Modern Authentication for Office 2013 on Windows Devices](../security-and-compliance/enable-modern-authentication.md).<br/>Inoltre, è necessario installare gli aggiornamenti di aprile seguenti per Office 2013:
    
  - [Descrizione dell'aggiornamento della sicurezza per Office 2013:10 aprile 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [2018 aprile 3, aggiornamento per Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **Non abilitare adal**. Se non si è in grado di abilitare ADAL in Office 2013, è consigliabile utilizzare criteri di gruppo per disattivare l'archivio per i client di Office. Informazioni su come disattivare l'app per le impostazioni di Office si trova [qui](https://technet.microsoft.com/library/cc178992.aspx).

## <a name="related-articles"></a>Articoli correlati

[Distribuire i componenti aggiuntivi nell'interfaccia di amministrazione](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[Gestire i componenti aggiuntivi nell'interfaccia di amministrazione](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
