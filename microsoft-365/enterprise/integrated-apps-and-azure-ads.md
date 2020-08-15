---
title: App integrate e Azure AD per gli amministratori di Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection: M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: cb2250e3-451e-416f-bf4e-363549652c2a
description: Informazioni su come registrare e amministrare le app integrate di Office 365 in Azure AD, consentendo le autorizzazioni per le applicazioni a livello di amministratore globale.
ms.openlocfilehash: 3d9ded2ba2819d0e957586b6c49811ec932dee31
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691483"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>App integrate e Azure AD per gli amministratori di Microsoft 365

La gestione delle app integrate non è sufficiente per [attivare o disattivare le app integrate](https://support.office.com/article/7e453a40-66df-44ab-92a1-96786cb7fb34#__toc379982114). Con l'avvento delle API REST di Microsoft 365, gli utenti possono concedere alle app l'accesso ai dati di Microsoft 365, come posta, calendari, contatti, utenti, gruppi, file e cartelle. Per impostazione predefinita, gli utenti devono concedere individualmente le autorizzazioni per ogni app, ma questo non viene ridimensionato correttamente se si desidera autorizzare un'app una volta a livello di amministratore globale e distribuirla all'intera organizzazione tramite l'icona di avvio delle app. A tale scopo, è necessario registrare l'app in Azure AD. Ci sono alcuni passaggi da eseguire prima di poter registrare un'app in Azure AD e alcune informazioni di base che è necessario conoscere per gestire le app nell'organizzazione Microsoft 365. In questo articolo vengono indicate le risorse.
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Risorse di Azure AD per gli amministratori di Microsoft 365

È necessario eseguire queste due procedure prima di poter gestire le app Microsoft 365 in Azure AD.
  
|**Prerequisiti**|**Comments**|
|:-----|:-----|
|[Usare la sottoscrizione gratuita ad Azure Active Directory](https://docs.microsoft.com/microsoft-365/compliance/use-your-free-azure-ad-subscription-in-office-365) <br/> |Ogni sottoscrizione a pagamento a Microsoft 365 viene fornita con una sottoscrizione gratuita ad Azure Active Directory (Azure AD). È possibile utilizzare Azure AD per gestire le app e per creare e gestire gli account utente e di gruppo. Per utilizzare Azure AD, basta andare al portale di Azure e accedere utilizzando l'account Microsoft 365.  <br/> |
|[Attivazione o disattivazione delle app integrate](https://support.office.com/article/7e453a40-66df-44ab-92a1-96786cb7fb34#__toc379982114) <br/> |Per consentire alle app di terze parti di accedere alle proprie informazioni di Microsoft 365, è necessario attivare le app integrate e registrare le app in Azure AD. Ad esempio, quando un utente utilizza un'app di terze parti, l'app potrebbe richiedere l'autorizzazione per accedere al calendario e modificare i file presenti in una cartella di OneDrive for business.  <br/> |
   
La gestione delle app Microsoft 365 richiede la conoscenza delle app in Azure AD. Questi articoli consentono di fornire lo sfondo necessario.
  
|**Articolo in background**|**Comments**|
|:-----|:-----|
|[Vedere l'icona di avvio delle app di Microsoft 365](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |Se si è nuovi per l'icona di avvio delle app, potrebbe essere utile sapere cosa è e come utilizzarlo. L'icona di avvio delle app è progettata per accedere alle app da qualsiasi posizione in Microsoft 365.  <br/> |
|[Panoramica delle API di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) <br/> |Le API di Microsoft 365 consentono di fornire l'accesso ai dati di Microsoft 365, compresi gli elementi più importanti, ovvero la posta elettronica, i calendari, i contatti, gli utenti e i gruppi, i file e le cartelle. In questo articolo è presente un buon diagramma che illustra la relazione tra le app di Microsoft 365, Azure AD e i dati di accesso delle app.  <br/> |
|[Integrazione di applicazioni in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | Informazioni sulle applicazioni che sono integrate con Azure AD e su come registrare l'applicazione, comprendere i concetti che stanno alla base di un'applicazione registrata e conoscere le linee guida per il branding per le applicazioni multi-tenant.  <br/> |
|[Aggiungere sezioni personalizzate all'icona di avvio delle app](https://docs.microsoft.com/office365/admin/manage/customize-the-app-launcher)  <br/> |L'icona di avvio delle app in Microsoft 365 rende più semplice per gli utenti trovare e accedere alle proprie app. In questo articolo vengono illustrati i modi in cui uno sviluppatore può visualizzare le app nei lanci delle app degli utenti e fornire loro un'esperienza Single Sign-on (SSO) utilizzando le credenziali di Microsoft 365.  <br/> |
|[Esercitazioni sull'integrazione di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list) <br/> |L'obiettivo di queste esercitazioni è mostrare come configurare Azure AD SSO per le applicazioni SaaS di terze parti.  <br/> |
|[Scenari di autenticazione per Azure AD](https://go.microsoft.com/fwlink/?LinkId=617145) <br/> |Azure AD semplifica l'autenticazione per gli sviluppatori fornendo l'identità come servizio, con supporto per i protocolli standard del settore, come OAuth 2,0 e OpenID Connect, nonché librerie open source per diverse piattaforme che consentono di avviare rapidamente la codifica. In questo documento vengono fornite informazioni utili per comprendere i vari scenari supportati da Azure AD e vengono illustrate le procedure per iniziare.  <br/> |
|[Accesso alle applicazioni](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-access-management) <br/> |Azure AD consente una facile integrazione con molte delle applicazioni di software popolare di oggi come servizio (SaaS). fornisce la gestione delle identità e degli accessi e offre un pannello di accesso per gli utenti in cui è possibile individuare l'accesso all'applicazione in uso e in cui è possibile utilizzare SSO per accedere alle proprie applicazioni. In questo articolo vengono forniti collegamenti alle risorse correlate che consentono di ottenere ulteriori informazioni sui miglioramenti relativi all'accesso alle applicazioni per Azure AD e su come è possibile contribuirvi.  <br/> |
|[Personalizzare l'esperienza di Office 365](https://support.office.com/article/eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |È possibile accedere rapidamente alle app che si usano ogni giorno aggiungendo o rimuovendo app dall'icona di avvio delle app di Microsoft 365.  <br/> |
   

