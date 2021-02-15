---
title: 'Supporto app client Microsoft 365: autenticazione basata su certificati'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: In questo articolo vengono fornite informazioni dettagliate sul supporto dell'app client di Microsoft 365 per l'autenticazione basata su certificati.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f7ab5e4a2575796e37a115b36a4f78add20414ef
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097259"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Supporto app client Microsoft 365: autenticazione basata su certificati

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

L'autenticazione moderna è un termine generico per una combinazione di metodi di autenticazione e autorizzazione. Ad esempio:

- **Metodi di autenticazione**: Autenticazione a più fattori; Autenticazione basata su certificati client.
- **Metodi di autorizzazione:** implementazione microsoft di Open Authorization (OAuth).

L'autenticazione moderna viene abilitata tramite una libreria di autenticazione, ad esempio Active Directory Authentication Library (ADAL) o Microsoft Authentication Library (MSAL). L'autenticazione moderna è ciò che i client usano per autenticare e autorizzare l'accesso alle risorse di Microsoft 365. L'autenticazione moderna sfrutta OAuth e fornisce un meccanismo sicuro per l'accesso dei client ai servizi di Microsoft 365, senza richiedere l'accesso alle credenziali utente. All'accesso, l'utente esegue l'autenticazione direttamente con Azure Active Directory e riceve una coppia di token di accesso/aggiornamento in cambio. Il token di accesso concede al client l'accesso alle risorse appropriate nel tenant di Microsoft 365. Un token di aggiornamento viene usato per ottenere una nuova coppia di token di accesso o aggiornamento alla scadenza del token di accesso corrente.

L'autenticazione moderna supporta meccanismi di autenticazione diversi, come l'autenticazione basata su certificati. I client su dispositivi Windows, Android o iOS possono usare l'autenticazione basata su certificato (CBA) per eseguire l'autenticazione in Azure Active Directory usando un certificato client nel dispositivo. Invece di un nome utente/password tipico, il certificato viene usato per ottenere una coppia di token di accesso/aggiornamento da Azure Active Directory.

Ulteriori informazioni [sull'autenticazione basata su certificati.](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)

## <a name="supported-clients--platforms"></a>Client supportati & piattaforme

Le versioni più recenti dei client e delle piattaforme seguenti supportano l'autenticazione basata su certificati quando si accede agli account Azure Active Directory all'interno del client (ad esempio, quando si aggiunge un account all'app). Per ulteriori informazioni sul supporto della piattaforma in Microsoft 365, vedere [Requisiti di sistema per Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)
<br>
<br>

| Client | Android | iOS | Mac| Windows 10 <br> App moderne| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Amministratore di Azure Active Directory | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Access | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Amministratore di Azure | N/D | N/D | N/D | N/D | N/D |
| Portale aziendale | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D |
| Cortana | Pianificato | Pianificato | N/D | ![Supportato](../media/check-mark.png) | N/D |
| Delve | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Edge<sup>1</sup> | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Excel | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| Amministratore di Exchange Online | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Forms | N/D | N/D | N/D | N/D | N/D |
| Amministratore di Office 365 | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |  |
| Kaizala | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Office Lens| ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) | N/D |
| Office Mobile | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Portale di Office | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) | N/D |
| OneDrive | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | Pianificato | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| OneNote | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| Outlook | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| Planner | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Power Apps | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) | N/D |
| Power Automate | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Power BI | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| PowerPoint | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| Project | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Publisher | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Skype for Business | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) |
| Amministratore di Skype for Business | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| SharePoint | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Amministratore di SharePoint Online | Pianificato | Pianificato | N/D | N/D | N/D |
| Sticky Notes | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) | N/D |
| Stream | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Sway | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) | N/D |
| Teams | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | Pianificato |
| To Do | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D |
| Visio | N/D | ![Supportato](../media/check-mark.png) | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Whiteboard | Pianificato | Pianificato | N/D | ![Supportato](../media/check-mark.png) | N/D |
| Word | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| Analisi dell'area di lavoro | N/D | N/D | N/D | N/D | N/D |
| Yammer | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | Pianificato | N/D | Pianificato |

>[!NOTE]
><sup>1</sup> Edge per iOS e Android supporta l'autenticazione basata su certificati durante i flussi di aggiunta dell'account. Edge per iOS e Android non supporta l'autenticazione basata su certificati quando si esegue l'autenticazione nei siti Web, che in genere sono siti Intranet. <br><br>  In questo scenario, un utente passa a un sito Web (in genere nella intranet) in cui il sito Web richiede all'utente di eseguire l'autenticazione tramite un certificato. Ciò non implica affatto l'autenticazione moderna e non sfrutta una libreria di autenticazione Microsoft. Ciò è dovuto a una limitazione di iOS: iOS impedisce alle app di terze parti di accedere al keychain di sistema in cui sono archiviati i certificati (solo le app Apple e il [controller Webview Safari](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) possono accedere al keychain di sistema). <br><br> Poiché Edge si basa sul framework [WebKit](https://developer.apple.com/documentation/webkit) per il rendering dei siti Web, Edge non è in grado di accedere al keychain di sistema e presentare all'utente una scelta di certificato. Questo, purtroppo, è da progettazione a causa dell'architettura di Apple.

## <a name="supported-powershell-modules"></a>Moduli di PowerShell supportati

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [PowerShell per SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

