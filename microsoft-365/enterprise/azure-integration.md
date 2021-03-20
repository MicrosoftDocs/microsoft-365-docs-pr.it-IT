---
title: Integrazione di Azure con Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: a5efce5d-9c9c-4190-b61b-fd273c1d425f
description: Integrare Microsoft 365 con Azure AD se si desidera la sincronizzazione delle password o single sign-on con l'ambiente locale.
ms.openlocfilehash: f977969634401d59d7598136f9323cb0e37f9ece
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905333"
---
# <a name="azure-integration-with-microsoft-365"></a>Integrazione di Azure con Microsoft 365

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Microsoft 365 usa Azure Active Directory (Azure AD) per gestire le identità degli utenti dietro le quinte. L'abbonamento a Microsoft 365 include un abbonamento gratuito ad Azure AD in modo da poter integrare i Servizi di dominio Active Directory locali per sincronizzare account utente e password o configurare l'accesso Single Sign-on. Puoi anche acquistare funzionalità avanzate per gestire meglio i tuoi account.
  
Azure AD offre anche altre funzionalità, come la gestione delle app integrate, che puoi usare per estendere e personalizzare le sottoscrizioni di Microsoft 365.
  
È possibile usare i consulenti per la distribuzione di Azure AD per un'esperienza di configurazione e configurazione guidata nell'interfaccia di amministrazione di Microsoft 365 (è necessario accedere a Microsoft 365):

 - [Advisor di Azure AD Connect](https://aka.ms/aadconnectpwsync)
 - [Assistente distribuzione di AD FS](https://aka.ms/adfsguidance)
 - [Guida alla configurazione di Azure AD](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Edizioni di Azure AD e gestione delle identità di Microsoft 365

Se si dispone di una sottoscrizione a pagamento a Microsoft 365, si dispone anche di un abbonamento gratuito ad Azure AD. È possibile usare Azure AD per creare e gestire account utente e di gruppo. Per attivare questa sottoscrizione, è necessario completare una registrazione una sola volta. Successivamente, è possibile accedere ad Azure AD dall'interfaccia di amministrazione di Microsoft 365. 

Per istruzioni su come registrare la sottoscrizione gratuita di Azure AD, vedi [usare la sottoscrizione gratuita di Azure AD.](../compliance/use-your-free-azure-ad-subscription-in-office-365.md) Non passare direttamente a azure.microsoft.com per iscriversi o si finirà con una sottoscrizione di valutazione o a pagamento a Microsoft Azure separata dall'abbonamento gratuito ad Azure AD con Microsoft 365. 
  
Con l'abbonamento gratuito è possibile eseguire la sincronizzazione con le directory locali, configurare l'accesso Single #A0 e sincronizzare con molti software come applicazioni di servizio, ad esempio Salesforce, DropBox e molti altri.
  
Se si desiderano funzionalità avanzate di Servizi di dominio Active Directory, sincronizzazione bidirezionale e altre funzionalità di gestione, è possibile aggiornare la sottoscrizione gratuita a una sottoscrizione premium a pagamento. Per informazioni dettagliate, vedere [Edizioni di Azure Active Directory.](https://azure.microsoft.com/pricing/details/active-directory/)
  
Per ulteriori informazioni su Microsoft 365 e Azure AD, vedere Modelli di [identità di Microsoft 365.](about-microsoft-365-identity.md)
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>Estendere le funzionalità del tenant di Microsoft 365

|**Caratteristica**|**Descrizione**|
|:-----|:-----|
|App integrate  <br/> |È possibile concedere alle singole app l'accesso ai dati di Microsoft 365, ad esempio posta, calendari, contatti, utenti, gruppi, file e cartelle. Puoi anche autorizzare queste app a livello di amministratore globale e renderle disponibili per l'intera azienda registrando le app in Azure AD. Per ulteriori informazioni, vedere [Integrated Apps e Azure AD per gli amministratori di Microsoft 365.](integrated-apps-and-azure-ads.md)  <br/> Vedere anche [Single #A0](/azure/active-directory/manage-apps/what-is-single-sign-on).  <br/> |
|PowerApps  <br/> | Le app di Power sono app incentrate su dispositivi mobili in grado di connettersi alle origini dati esistenti, ad esempio elenchi di SharePoint e altre app di dati. Per informazioni dettagliate, vedere Create [a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page.](https://powerapps.microsoft.com/)  <br/> |
   
## <a name="see-also"></a>Vedere anche

[Panoramica di Microsoft 365 Enterprise](microsoft-365-overview.md)