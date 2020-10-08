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
ms.openlocfilehash: 1e84b5e6f82848bf1d100004bcd2711ad2e9ed39
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384904"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>App integrate e Azure AD per gli amministratori di Microsoft 365

La gestione delle app integrate non è solo la [gestione del consenso degli utenti alle app](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps). Con l'avvento delle API REST di Microsoft 365, gli utenti possono concedere alle app l'accesso ai dati di Microsoft 365, ad esempio posta elettronica, calendari, contatti, utenti, gruppi, file e cartelle. Per impostazione predefinita, gli utenti devono concedere individualmente le autorizzazioni per ogni app. 

Tuttavia, se si desidera autorizzare un'applicazione una volta a livello di amministratore globale e distribuirla all'intera organizzazione tramite l'icona di avvio delle app, questa operazione non viene ridimensionata correttamente. A tale scopo, è necessario registrare l'app in Azure Active Directory (Azure AD). Ci sono alcuni passaggi da eseguire prima di poter registrare un'app in Azure AD e alcune informazioni di base che è necessario conoscere per gestire le app nell'organizzazione Microsoft 365.
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Risorse di Azure AD per gli amministratori di Microsoft 365

È necessario eseguire queste due attività prima di poter gestire le app Microsoft 365 in Azure AD.
  
|Prerequisiti|Commenti|
|:-----|:-----|
|[Utilizzare la sottoscrizione gratuita AD Azure AD](https://docs.microsoft.com/microsoft-365/compliance/use-your-free-azure-ad-subscription-in-office-365) <br/> |Ogni sottoscrizione a pagamento a Microsoft 365 viene fornito con un abbonamento gratuito ad Azure AD. È possibile utilizzare Azure AD per gestire le app e per creare e gestire gli account utente e di gruppo. Per utilizzare Azure AD, è sufficiente accedere al portale di Azure [https://portal.azure.com](https://portal.azure.com) e accedere utilizzando l'account Microsoft 365.  <br/> |
|[Gestire il consenso degli utenti alle app](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps) <br/> |È necessario gestire il consenso degli utenti alle app per consentire alle app di terze parti di accedere alle informazioni di Microsoft 365 e di registrare le app in Azure AD. Un'eventuale app di terze parti usata da qualcuno potrebbe ad esempio chiedere l'autorizzazione per accedere al calendario e per modificare i file contenuti in una cartella di OneDrive di questa persona.  <br/> |
   
La gestione delle app Microsoft 365 richiede la conoscenza delle app in Azure AD. Utilizzare questi articoli per fornire lo sfondo necessario.
  
|Articolo|Commenti|
|:-----|:-----|
|[Vedere l'icona di avvio delle app di Microsoft 365](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |Se si è nuovi per l'icona di avvio delle app, potrebbe essere utile sapere cosa è e come utilizzarlo. L'icona di avvio delle app è progettata per accedere alle app da qualsiasi posizione in Microsoft 365.  <br/> |
|[Panoramica delle API di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) <br/> |Le API di Microsoft 365 Management consentono di fornire l'accesso ai dati di Microsoft 365, compresi gli elementi più importanti, ovvero la posta elettronica, i calendari, i contatti, gli utenti e i gruppi, i file e le cartelle. <br/> |
|[Integrazione di applicazioni in Azure AD](https://docs.microsoft.com/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | Informazioni sulle applicazioni che sono integrate con Azure AD e su come registrare l'applicazione, comprendere i concetti che stanno alla base di un'applicazione registrata e conoscere le linee guida per la personalizzazione delle applicazioni multi-tenant.  <br/> |
|[Aggiungere sezioni personalizzate all'icona di avvio delle app](https://docs.microsoft.com/office365/admin/manage/customize-the-app-launcher)  <br/> |L'icona di avvio delle app in Microsoft 365 rende più semplice per gli utenti trovare e accedere alle proprie app. In questo articolo vengono illustrati i modi in cui uno sviluppatore può visualizzare le app nei lanci delle app degli utenti e fornire loro un'esperienza Single Sign-on (SSO) utilizzando le credenziali di Microsoft 365.  <br/> |
|[Tutorial di integrazione con Azure AD](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list) <br/> |L'obiettivo di queste esercitazioni è mostrare come configurare Azure AD SSO per le applicazioni SaaS di terze parti.  <br/> |
|[Scenari di autenticazione di Azure AD](https://go.microsoft.com/fwlink/?LinkId=617145) <br/> |Azure AD semplifica l'autenticazione per gli sviluppatori fornendo l'identità come servizio, con supporto per i protocolli standard del settore, come OAuth 2,0 e OpenID Connect, nonché librerie open source per diverse piattaforme che consentono di avviare rapidamente la codifica. In questo documento vengono fornite informazioni utili per comprendere i vari scenari supportati da Azure AD e vengono illustrate le procedure per iniziare.  <br/> |
|[Accesso alle applicazioni](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-access-management) <br/> |Azure AD consente una facile integrazione con molte delle applicazioni di software popolari di oggi come servizio (SaaS). Fornisce la gestione delle identità e degli accessi e offre un pannello di accesso per gli utenti in cui è possibile individuare l'accesso all'applicazione in uso e in cui è possibile utilizzare SSO per accedere alle proprie applicazioni. In questo articolo vengono forniti collegamenti alle risorse correlate che consentono di ottenere ulteriori informazioni sui miglioramenti relativi all'accesso alle applicazioni per Azure AD e su come è possibile contribuirvi.  <br/> |
|[Personalizzare l'esperienza di Office 365](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |È possibile accedere rapidamente alle app che si usano ogni giorno aggiungendo o rimuovendo app dall'icona di avvio delle app di Microsoft 365.  <br/> |

