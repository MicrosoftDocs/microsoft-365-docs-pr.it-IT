---
title: 'Supporto delle app client Microsoft 365: autenticazione basata su certificato'
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
description: In questo articolo sono disponibili informazioni dettagliate sul supporto delle app client di Microsoft 365 per l'autenticazione basata su certificati.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fde124fcefdf3b949ec35a3b2ed99b15ee36f85e
ms.sourcegitcommit: 2beefb695cead03cc21d6066f589572d3ae029aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2020
ms.locfileid: "49349681"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Supporto delle app client Microsoft 365: autenticazione basata su certificato

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

L'autenticazione moderna è un termine ombrello per una combinazione di metodi di autenticazione e autorizzazione. Ad esempio:

- **Metodi di autenticazione**: autenticazione a più fattori; Autenticazione basata su certificato client.
- **Metodi di autorizzazione**: implementazione di Microsoft di autorizzazione aperta (OAuth).

L'autenticazione moderna è abilitata mediante l'utilizzo di una raccolta di autenticazione, ad esempio la libreria di autenticazione di Active Directory (ADAL) o la libreria di autenticazione Microsoft (MSAL). L'autenticazione moderna è ciò che i client utilizzano per autenticare e autorizzare l'accesso alle risorse di Microsoft 365. L'autenticazione moderna utilizza OAuth e fornisce un meccanismo sicuro per i client di accedere ai servizi Microsoft 365, senza richiedere l'accesso alle credenziali dell'utente. All'accesso, l'utente autentica direttamente con Azure Active Directory e riceve una coppia di token di accesso/aggiornamento in ritorno. Il token di accesso concede all'utente l'accesso alle risorse appropriate nel tenant di Microsoft 365. Un token di aggiornamento viene utilizzato per ottenere una nuova coppia di token di accesso o di aggiornamento quando scade il token di accesso corrente.

L'autenticazione moderna supporta diversi meccanismi di autenticazione, ad esempio l'autenticazione basata su certificato. I client su dispositivi Windows, Android o iOS possono utilizzare l'autenticazione basata su certificato (CBA) per eseguire l'autenticità in Azure Active Directory utilizzando un certificato client nel dispositivo. Invece di un nome utente/password tipici, il certificato viene utilizzato per ottenere una coppia di token di accesso/aggiornamento da Azure Active Directory.

Per ulteriori informazioni, vedere [autenticazione basata su certificati](https://docs.microsoft.com/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started).

## <a name="supported-clients--platforms"></a>Client supportati & piattaforme

Le versioni più recenti dei client e delle piattaforme seguenti supportano l'autenticazione basata sui certificati per l'accesso agli account di Azure Active Directory all'interno del client (ad esempio, quando si aggiunge un account all'app). Per ulteriori informazioni sul supporto delle piattaforme in Microsoft 365, vedere [requisiti di sistema per microsoft 365](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources).
<br>
<br>

| Client | Android | iOS | Mac| Windows 10 <br> App moderne| Windows 10 <br> Desktop |
|:---|:---:|:---:|:---:|:---:|:---:|
| Amministratore di Azure Active Directory | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Access | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Amministratore di Azure | N/D | N/D | N/D | N/D | N/D |
| Portale aziendale | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D |
| Cortana | Pianificata | Pianificata | N/D | ![Supportato](../media/check-mark.png) | N/D |
| Delve | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Edge<sup>1</sup> | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Excel | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| Amministratore di Exchange Online | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Moduli | N/D | N/D | N/D | N/D | N/D |
| Amministratore di Office 365 | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |  |
| Kaizala | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Office Lens| ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) | N/D |
| Office Mobile | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Portale di Office | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) | N/D |
| OneDrive | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | Pianificata | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| OneNote | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| Outlook | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| Planner | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Power Apps | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) | N/D |
| Automatizzare la potenza | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Power BI | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| PowerPoint | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| Project | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Publisher | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Skype for Business | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | ![Supportato](../media/check-mark.png) |
| Amministratore di Skype for business | N/D | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) |
| SharePoint | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Amministratore di SharePoint Online | Pianificata | Pianificata | N/D | N/D | N/D |
| Sticky Notes | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) | N/D |
| Stream | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | N/D | N/D |
| Sway | N/D | N/D | N/D | ![Supportato](../media/check-mark.png) | N/D |
| Teams | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D | Pianificata |
| Da fare | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | N/D |
| Visio | N/D | ![Supportato](../media/check-mark.png) | N/D | N/D | ![Supportato](../media/check-mark.png) |
| Whiteboard | Pianificata | Pianificata | N/D | ![Supportato](../media/check-mark.png) | N/D |
| Word | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) |
| Analisi del luogo di lavoro | N/D | N/D | N/D | N/D | N/D |
| Yammer | ![Supportato](../media/check-mark.png) | ![Supportato](../media/check-mark.png) | Pianificata | N/D | Pianificata |

>[!NOTE]
><sup>1</sup> Edge per iOS e Android supporta l'autenticazione basata su certificato durante l'aggiunta dei flussi di account. Edge per iOS e Android non supporta l'autenticazione basata sui certificati quando eseguono l'autenticazione nei siti Web, che in genere sono siti Intranet. <br><br>  In questo scenario, un utente accede a un sito Web (in genere sulla rete Intranet) in cui il sito Web richiede all'utente di eseguire l'autenticazione tramite un certificato. Questo non comporta affatto l'autenticazione moderna e non utilizza una libreria di autenticazione di Microsoft. Ciò è dovuto a una limitazione con iOS: iOS impedisce alle app di terze parti di accedere al portachiavi del sistema in cui vengono archiviati i certificati (solo le app Apple e il [controller WebView di Safari](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) possono accedere al portachiavi del sistema). <br><br> Poiché Edge si basa sul Framework [WebKit](https://developer.apple.com/documentation/webkit) per il rendering dei siti Web, Edge non è in grado di accedere al portachiavi del sistema e di presentare l'utente con una scelta di certificato. Questo, purtroppo, è in base alla progettazione a causa dell'architettura di Apple.

## <a name="supported-powershell-modules"></a>Moduli di PowerShell supportati

- [PowerShell di Azure Active Directory](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)
- [PowerShell per SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

