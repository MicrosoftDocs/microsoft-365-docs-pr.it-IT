---
title: 'Microsoft 365 Supporto app client: autenticazione basata su certificato'
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
description: In questo articolo, trovare informazioni dettagliate sull'Microsoft 365 dell'app client per l'autenticazione basata su certificato.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bef1a684ba1ebe2eaba90677cd726cc190e342db
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286574"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a>Microsoft 365 Supporto app client: autenticazione basata su certificato

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

L'autenticazione moderna è un termine generico per una combinazione di metodi di autenticazione e autorizzazione. Questi metodi comprendono:

- **Metodi di autenticazione**: Autenticazione a più fattori; Autenticazione basata su certificato client.
- **Metodi di autorizzazione**: Implementazione microsoft di Open Authorization (OAuth).

L'autenticazione moderna viene abilitata utilizzando una libreria di autenticazione, ad esempio Active Directory Authentication Library (ADAL) o Microsoft Authentication Library (MSAL). L'autenticazione moderna è ciò che i client usano per autenticare e autorizzare l'accesso Microsoft 365 risorse. L'autenticazione moderna utilizza OAuth e fornisce un meccanismo sicuro per l'accesso dei client Microsoft 365 servizi, senza richiedere l'accesso alle credenziali utente. All'accesso, l'utente esegue l'autenticazione direttamente con Azure Active Directory e riceve una coppia di token di accesso/aggiornamento in cambio. Il token di accesso concede al client l'accesso alle risorse appropriate nel tenant Microsoft 365 tenant. Un token di aggiornamento viene usato per ottenere una nuova coppia di token di accesso o aggiornamento alla scadenza del token di accesso corrente.

L'autenticazione moderna supporta meccanismi di autenticazione diversi, ad esempio l'autenticazione basata su certificati. I client Windows, Android o iOS possono usare l'autenticazione basata su certificato (CBA) per eseguire l'autenticazione Azure Active Directory utilizzando un certificato client nel dispositivo. Invece di un nome utente/password tipico, il certificato viene usato per ottenere una coppia di token di accesso/aggiornamento da Azure Active Directory.

Ulteriori informazioni [sull'autenticazione basata su certificato.](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)

## <a name="supported-clients--platforms"></a>Client supportati & piattaforme

Le versioni più recenti dei client e delle piattaforme seguenti supportano l'autenticazione basata su certificato durante l'accesso agli account Azure Active Directory all'interno del client (ad esempio, quando si aggiunge un account all'app). Per ulteriori informazioni sul supporto della piattaforma in Microsoft 365, vedere [Requisiti di sistema per Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).
<br>
<br>

[!INCLUDE [Certificate-based authentication services support table](../includes/microsoft-365-client-support-certificate-based-authentication-include.md)]

> [!NOTE]
> Edge per iOS e Android supporta l'autenticazione basata su certificati durante i flussi di aggiunta degli account. Edge per iOS e Android non supporta l'autenticazione basata su certificati quando si esegue l'autenticazione nei siti Web, che in genere sono siti Intranet. <br><br>  In questo scenario, un utente passa a un sito Web (in genere nella intranet) in cui il sito Web richiede all'utente di eseguire l'autenticazione tramite un certificato. Ciò non implica affatto l'autenticazione moderna e non sfrutta una libreria di autenticazione Microsoft. Ciò è dovuto a una limitazione di iOS: iOS impedisce alle app di terze parti di accedere al portachiavi di sistema in cui sono archiviati i certificati (solo le app Apple e il [controller Webview Safari](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) possono accedere al portachiavi di sistema). <br><br> Poiché Edge si basa sul framework [WebKit](https://developer.apple.com/documentation/webkit) per il rendering dei siti Web, Edge non è in grado di accedere al portachiavi di sistema e presentare all'utente una scelta di certificato. Questo, purtroppo, è dovuto all'architettura di Apple.

## <a name="supported-powershell-modules"></a>Moduli di PowerShell supportati

- [Azure Active Directory PowerShell](/powershell/azure/active-directory/overview)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)
- [PowerShell per SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
