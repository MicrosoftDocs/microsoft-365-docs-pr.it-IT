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
description: Informazioni sulle normative del Regolamento generale sulla protezione dei dati (GDPR) che regolano i dati personali dei minori.
ms.openlocfilehash: a738e22a0ac0b995c8e44fcf4cc5a2eb47375be5
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306552"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>Minorenni e acquisizione di componenti aggiuntivi dallo Store

Il Regolamento generale sulla protezione dei dati (GDPR) è un regolamento dell'Unione Europea che diventa effettivo il 25 maggio 2018. Concede agli utenti i diritti e la protezione dei propri dati. Uno degli aspetti del GDPR è che i minori non possono inviare i propri dati personali alle parti che il genitore o il tutore non ha approvato. L'età specifica definita come minore dipende dall'area geografica in cui si trova l'individuo.
  
Le aree geografiche che hanno normative legali sul consenso dei genitori includono Stati Uniti, Corea del Sud, Regno Unito e Unione Europea. Per queste aree geografiche, un componente aggiuntivo verrà bloccato (tramite Azure Active Directory) dal recupero di eventuali nuovi componenti aggiuntivi di Office dallo Store e dall'esecuzione di componenti aggiuntivi acquisiti in precedenza. Per i paesi senza normative normative, non ci saranno restrizioni per il download.
  
Un utente viene determinato come minore in base ai dati specificati in Azure Active Directory. L'amministratore dell'organizzazione è responsabile della dichiarazione della fascia d'età legale e del consenso dei genitori per tale utente.
  
Se il genitore/guardiano acconsente a un componente aggiuntivo specifico, l'amministratore dell'organizzazione può usare la distribuzione centralizzata per distribuire il componente aggiuntivo a tutti i minori che hanno il consenso.
  
Per essere conforme al GDPR per i minori, è necessario assicurarsi che una delle build seguenti di Office sia distribuita nell'istituto di istruzione/organizzazione.
 
 **Per Word, Excel, PowerPoint e Project:** 

|**Piattaforma** <br/> |**Numero di build** <br/> |
|:-----|:-----|
|Microsoft 365 Apps for enterprise (Current Channel)  <br/> |9001.2138   <br/> |
|Microsoft 365 Apps for enterprise (Canale Enterprise semestraale)  <br/> |8431.2159  <br/> |
|Office 2016 per Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 per Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 per Mac  <br/> |16.11.18020200  <br/> |
|Office per il web  <br/> |N/D  <br/> |
   
 **Per Outlook:** 
  
|**Piattaforma** <br/> |**Numero di build** <br/> |
|:-----|:-----|
|Outlook 2016 per Windows (MSI)  <br/> |Build No TBD  <br/> |
|Outlook 2016 per Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 per Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook Mobile per iOS  <br/> |2.75.0  <br/> |
|Outlook Mobile per Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |N/D  <br/> |

 **Requisiti di Office 2013**
  
Word, Excel e PowerPoint 2013 per Windows supporteranno gli stessi controlli secondari se Active Directory Authentication Library (ADAL) è abilitato. Esistono due opzioni per la conformità, come spiegato di seguito.
  
- **Abilitare ADAL**. Questo articolo spiega come abilitare ADAL per Office 2013: Uso dell'autenticazione moderna di [Microsoft 365 con i client di Office.](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)<br/>È inoltre necessario impostare le chiavi del Registro di sistema per abilitare ADAL come illustrato in Abilitare l'autenticazione moderna per [Office 2013 nei dispositivi Windows.](../security-and-compliance/enable-modern-authentication.md)<br/>Inoltre, è necessario installare i seguenti aggiornamenti di aprile per Office 2013:
    
  - [Descrizione dell'aggiornamento della sicurezza per Office 2013: 10 aprile 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [Aggiornamento del 3 aprile 2018 per Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **Non abilitare ADAL**. Se non è possibile abilitare ADAL in Office 2013, è consigliabile usare Criteri di gruppo per disattivare lo Store per i client di Office. Le informazioni su come disattivare le impostazioni dell'app per Office sono disponibili [qui.](https://technet.microsoft.com/library/cc178992.aspx)

## <a name="related-articles"></a>Articoli correlati

[Distribuire i componenti aggiuntivi nell'interfaccia di amministrazione](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[Gestire i componenti aggiuntivi nell'interfaccia di amministrazione](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
