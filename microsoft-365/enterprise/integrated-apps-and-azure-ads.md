---
title: App integrate e Azure AD per amministratori di Microsoft 365
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
description: Informazioni su come registrare e amministrare le app integrate di Office 365 in Azure AD, consentendo autorizzazioni per le app a livello di amministratore globale.
ms.openlocfilehash: 0b7392984b77b01abb0992fea5db62b80ed9fb6c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909775"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>App integrate e Azure AD per amministratori di Microsoft 365

La gestione delle app integrate è molto più importante della semplice gestione del consenso [dell'utente alle app.](../admin/misc/user-consent.md) Con l'avvento delle API REST di Microsoft 365, gli utenti possono concedere alle app l'accesso ai dati di Microsoft 365, ad esempio posta, calendari, contatti, utenti, gruppi, file e cartelle. Per impostazione predefinita, gli utenti devono concedere singolarmente le autorizzazioni a ogni app. 

Tuttavia, questa operazione non è adatta se vuoi autorizzare un'app una sola volta a livello di amministratore globale e stentarla all'intera organizzazione tramite l'icona di avvio delle app. A tale scopo, è necessario registrare l'app in Azure Active Directory (Azure AD). Prima di registrare un'app in Azure AD, è necessario eseguire alcune operazioni e alcune informazioni di base utili per gestire le app nell'organizzazione di Microsoft 365.
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Risorse di Azure AD per gli amministratori di Microsoft 365

È necessario eseguire queste due attività prima di poter gestire le app di Microsoft 365 in Azure AD.
  
|Prerequisiti|Commenti|
|:-----|:-----|
|[Usare la sottoscrizione gratuita di Azure AD](../compliance/use-your-free-azure-ad-subscription-in-office-365.md) <br/> |Ogni abbonamento a pagamento a Microsoft 365 viene fornito con un abbonamento gratuito ad Azure AD. Puoi usare Azure AD per gestire le tue app e per creare e gestire account utente e di gruppo. Per usare Azure AD, è sufficiente accedere al portale di Azure all'indirizzo [https://portal.azure.com](https://portal.azure.com) e accedere con l'account Microsoft 365.  <br/> |
|[Gestire il consenso dell'utente alle app](../admin/misc/user-consent.md) <br/> |Devi gestire il consenso dell'utente alle app per consentire alle app di terze parti di accedere alle informazioni di Microsoft 365 dell'utente e registrare le app in Azure AD. Un'eventuale app di terze parti usata da qualcuno potrebbe ad esempio chiedere l'autorizzazione per accedere al calendario e per modificare i file contenuti in una cartella di OneDrive di questa persona.  <br/> |
   
La gestione delle app di Microsoft 365 richiede la conoscenza delle app in Azure AD. Usa questi articoli per fornire le informazioni di base necessarie.
  
|Articolo|Commenti|
|:-----|:-----|
|[Scopri l'icona di avvio delle app di Microsoft 365](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |Se non hai una nuova versione dell'icona di avvio delle app, potresti chiederti che cos'è e come usarla. L'icona di avvio delle app è progettata per aiutarti ad accedere alle tue app da qualsiasi posizione in Microsoft 365.  <br/> |
|[Panoramica delle API di gestione di Office 365](/office/office-365-management-api/office-365-management-apis-overview) <br/> |Le API di gestione di Microsoft 365 consentono di fornire l'accesso ai dati di Microsoft 365, inclusi gli aspetti più importanti, ovvero la posta, i calendari, i contatti, gli utenti e i gruppi, i file e le cartelle. <br/> |
|[Integrazione di applicazioni in Azure AD](/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | Informazioni sulle applicazioni integrate con Azure AD e su come registrare l'applicazione, sui concetti alla base di un'applicazione registrata e sulle linee guida per la personalizzazione per le applicazioni multi-tenant.  <br/> |
|[Aggiungere riquadri personalizzati all'icona di avvio delle app](/office365/admin/manage/customize-the-app-launcher)  <br/> |L'icona di avvio delle app in Microsoft 365 semplifica agli utenti la ricerca e l'accesso alle proprie app. In questo articolo vengono descritti i modi in cui gli sviluppatori possono visualizzare le app nelle applicazioni di avvio delle app degli utenti e offrire loro un'esperienza single sign-on (SSO) usando le credenziali di Microsoft 365.  <br/> |
|[Esercitazioni sull'integrazione di Azure AD](/azure/active-directory/saas-apps/tutorial-list) <br/> |L'obiettivo di queste esercitazioni è illustrare come configurare Azure AD SSO per le applicazioni SaaS di terze parti.  <br/> |
|[Scenari di autenticazione per Azure AD](/azure/active-directory/develop/authentication-vs-authorization) <br/> |Azure AD semplifica l'autenticazione per gli sviluppatori fornendo l'identità come servizio, con il supporto per protocolli standard del settore come OAuth 2.0 e OpenID Connect, nonché librerie open source per piattaforme diverse per aiutarti a iniziare rapidamente a scrivere codice. Questo documento consente di comprendere i vari scenari supportati da Azure AD e illustra come iniziare.  <br/> |
|[Accesso alle applicazioni](/azure/active-directory/manage-apps/what-is-access-management) <br/> |Azure AD consente una facile integrazione a molte delle applicazioni saaS (Software as a Service) odierne. Fornisce la gestione delle identità e degli accessi e fornisce un pannello di accesso per gli utenti in cui possono individuare l'accesso alle applicazioni e dove possono usare SSO per accedere alle proprie applicazioni. In questo articolo sono disponibili collegamenti alle risorse correlate che consentono di ottenere ulteriori informazioni sui miglioramenti dell'accesso alle applicazioni per Azure AD e su come è possibile contribuire a tali risorse.  <br/> |
|[Personalizzare l'esperienza di Office 365](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |Puoi accedere rapidamente alle app che usi ogni giorno aggiungendo o rimuovendo app nell'icona di avvio delle app di Microsoft 365.  <br/> |