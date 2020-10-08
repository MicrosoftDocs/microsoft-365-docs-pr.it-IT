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
description: Integrazione di Microsoft 365 con Azure AD se si desidera sincronizzare la password o l'accesso Single Sign-on con l'ambiente locale.
ms.openlocfilehash: b1f20ebc692421ed6df0d6f7c31a4d80347133e3
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384746"
---
# <a name="azure-integration-with-microsoft-365"></a>Integrazione di Azure con Microsoft 365

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Microsoft 365 utilizza Azure Active Directory (Azure AD) per gestire le identità degli utenti dietro le quinte. La sottoscrizione Microsoft 365 include una sottoscrizione gratuita AD Azure AD in modo che sia possibile integrare i servizi di dominio Active Directory (AD DS) locali per sincronizzare gli account utente e le password o configurare Single Sign-on. È inoltre possibile acquistare funzionalità avanzate per gestire al meglio gli account.
  
Azure AD offre anche altre funzionalità, come la gestione delle app integrate, che è possibile utilizzare per estendere e personalizzare le sottoscrizioni di Microsoft 365.
  
È possibile utilizzare i consulenti per la distribuzione di Azure AD per un'esperienza di installazione e configurazione guidata nell'interfaccia di amministrazione di Microsoft 365 (è necessario essere connessi a Microsoft 365):

 - [Advisor di Azure AD Connect](https://aka.ms/aadconnectpwsync)
 - [Assistente distribuzione di AD FS](https://aka.ms/adfsguidance)
 - [Guida alla configurazione di Azure AD](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Azure AD Editions e Microsoft 365 Identity Management

Se si dispone di un abbonamento a pagamento a Microsoft 365, si dispone anche di una sottoscrizione gratuita AD Azure AD. È possibile utilizzare Azure AD per creare e gestire gli account utente e di gruppo. Per attivare la sottoscrizione, è necessario completare una registrazione singola. Successivamente, è possibile accedere AD Azure AD dall'interfaccia di amministrazione di Microsoft 365. 

Per istruzioni su come registrare la sottoscrizione gratuita AD Azure AD, vedere [Use Your Free Azure ad Subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md). Non andare direttamente a azure.microsoft.com per iscriversi o finire con un abbonamento di valutazione o pagato a Microsoft Azure che è separato dalla sottoscrizione gratuita di Azure AD con Microsoft 365. 
  
Con l'abbonamento gratuito è possibile eseguire la sincronizzazione con le directory locali, configurare Single Sign-on e sincronizzarlo con molti software come applicazioni di servizio, ad esempio Salesforce, DropBox e molte altre.
  
Se si desidera migliorare la funzionalità di servizi di dominio Active Directory, la sincronizzazione bi-direzionale e altre funzionalità di gestione, è possibile aggiornare l'abbonamento gratuito a un abbonamento Premium a pagamento. Per i dettagli, vedere [edizioni di Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).
  
Per ulteriori informazioni su Microsoft 365 e Azure AD, vedere [modelli di identità di microsoft 365](about-microsoft-365-identity.md).
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>Estendere le funzionalità del tenant di Microsoft 365

|**Caratteristica**|**Descrizione**|
|:-----|:-----|
|App integrate  <br/> |È possibile concedere alle singole app l'accesso ai dati di Microsoft 365, ad esempio messaggi di posta elettronica, calendari, contatti, utenti, gruppi, file e cartelle. È inoltre possibile autorizzare tali applicazioni a livello di amministratore globale e renderle disponibili per l'intera società registrando le app in Azure AD. Formore informazioni, vedere [Integrated Apps and Azure ad per Microsoft 365 Administrators](integrated-apps-and-azure-ads.md).  <br/> Vedere anche [Single Sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).  <br/> |
|PowerApps  <br/> | Le app Power sono applicazioni mirate per i dispositivi mobili che possono connettersi alle origini dati esistenti come gli elenchi di SharePoint e altre app di dati. Per informazioni dettagliate, vedere [creare un PowerApp per un elenco in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) e la [pagina PowerApps](https://powerapps.microsoft.com/) .  <br/> |
   
## <a name="see-also"></a>Vedere anche

[Panoramica di Microsoft 365 Enterprise](microsoft-365-overview.md)
