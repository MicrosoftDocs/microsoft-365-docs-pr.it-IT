---
title: Minori e acquisizione di componenti aggiuntivi dallo Store
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Informazioni sulle normative del Regolamento generale sulla protezione dei dati (GDPR) che regolano i dati personali dei minori.
ms.openlocfilehash: e7f53a5a6b64f29f5029f0080fef44439c926edb
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580919"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>Minori e acquisizione di componenti aggiuntivi dallo Store

Il Regolamento generale sulla protezione dei dati (GDPR) è un regolamento dell'Unione Europea che diventa effettivo il 25 maggio 2018. Concede agli utenti i diritti e la protezione dei propri dati. Uno degli aspetti del GDPR è che i minori non possono avere i propri dati personali inviati a parti che il genitore o il tutore non hanno approvato. L'età specifica definita come minore dipende dall'area geografica in cui si trova l'individuo.
  
Le regioni che dispongono di normative legali sul consenso dei genitori includono Stati Uniti, Corea del Sud, Regno Unito e Unione Europea. Per tali aree geografiche, un componente aggiuntivo secondario verrà bloccato (tramite Azure Active Directory) dal recupero di eventuali nuovi componenti aggiuntivi di Office dallo Store e dall'esecuzione di componenti aggiuntivi acquisiti in precedenza. Per i paesi senza normative di legge, non ci saranno restrizioni per il download.
  
Un utente viene determinato come secondario in base ai dati specificati in Azure Active Directory. L'amministratore dell'organizzazione è responsabile della dichiarazione del gruppo di età legale e del consenso dei genitori per tale utente.
  
Se il genitore/tutore acconsente a un minore usando un componente aggiuntivo specifico, l'amministratore dell'organizzazione può usare la distribuzione centralizzata per distribuire il componente aggiuntivo a tutti i minori che hanno il consenso.
  
Per essere conformi al GDPR per i minori, è necessario assicurarsi che una delle seguenti build di Office sia distribuita nell'istituto o nell'organizzazione.
 
 **Per Word, Excel, PowerPoint e Project**: 

|**Piattaforma** <br/> |**Numero di build** <br/> |
|:-----|:-----|
|Microsoft 365 Apps for enterprise (Canale corrente)  <br/> |9001.2138   <br/> |
|Microsoft 365 Apps for enterprise (Canale semestraale enterprise)  <br/> |8431.2159  <br/> |
|Office 2016 per Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 per Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 per Mac  <br/> |16.11.18020200  <br/> |
|Office per il web  <br/> |N/D  <br/> |
   
 **Per Outlook**: 
  
|**Piattaforma** <br/> |**Numero di build** <br/> |
|:-----|:-----|
|Outlook 2016 per Windows (MSI)  <br/> |Build No TBD  <br/> |
|Outlook 2016 per Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 per Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook mobile per iOS  <br/> |2.75.0  <br/> |
|Outlook mobile per Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |N/D  <br/> |

 **Requisiti di Office 2013**
  
Word, Excel e PowerPoint 2013 per Windows supportano gli stessi controlli secondari se è abilitata la libreria di autenticazione di Active Directory (ADAL). Esistono due opzioni per la conformità, come illustrato di seguito.
  
- **Abilita ADAL**. In questo articolo viene illustrato come abilitare ADAL per Office 2013: Utilizzo dell'autenticazione moderna di [Microsoft 365 con i client di Office.](../../enterprise/modern-auth-for-office-2013-and-2016.md)<br/>È inoltre necessario impostare le chiavi del Registro di sistema per abilitare ADAL come illustrato in [Enable Modern Authentication for Office 2013 on Windows devices.](../security-and-compliance/enable-modern-authentication.md)<br/>Inoltre, è necessario installare i seguenti aggiornamenti di aprile per Office 2013:
    
  - [Descrizione dell'aggiornamento della sicurezza per Office 2013: 10 aprile 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [Aggiornamento del 3 aprile 2018 per Office 2013 (KB40183333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **Non abilitare ADAL**. Se non è possibile abilitare ADAL in Office 2013, è consigliabile usare Criteri di gruppo per disattivare lo Store per i client di Office. Le informazioni su come disattivare le impostazioni dell'app per Office sono disponibili [qui.](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15))

## <a name="related-articles"></a>Articoli correlati

[Distribuire i componenti aggiuntivi nell'interfaccia di amministrazione](./manage-deployment-of-add-ins.md)

[Gestire i componenti aggiuntivi nell'interfaccia di amministrazione](./manage-addins-in-the-admin-center.md)
