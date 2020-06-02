---
title: Impostare i criteri di accesso condizionale per le campagne Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come configurare i criteri di accesso condizionale per le campagne Microsoft 365 per aggiungere una maggiore sicurezza aggiuntiva.
ms.openlocfilehash: 58ee760877ee2fd7e53ef9463242657ab66a2b6e
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470648"
---
# <a name="set-up-conditional-access-policies"></a>Configurare i criteri di accesso condizionale

Questo articolo si applica a Microsoft 365 Business Premium.

I criteri di [accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) aggiungono ulteriore sicurezza. Microsoft fornisce una serie di criteri di accesso condizionale previsti che sono consigliati per tutti i clienti. I criteri di base sono un insieme di criteri predefiniti che consentono di proteggere le organizzazioni da numerosi attacchi comuni. Questi attacchi comuni possono includere lo spray per la password, la riproduzione e il phishing.

Questi criteri richiedono agli amministratori e agli utenti di immettere una seconda forma di autenticazione (denominata autenticazione a più fattori o AMF) quando vengono soddisfatte determinate condizioni. Ad esempio, se un utente ha effettuato l'accesso da un paese diverso, l'accesso potrebbe essere considerato rischioso e l'utente deve fornire un'ulteriore forma di autenticazione. 

Attualmente, i criteri di base includono quanto segue:
- Richiedi l'autenticazione a più fattori **per gli amministratori** &ndash; Richiede l'autenticazione a più fattori per i ruoli di amministratore più privilegiati, tra cui l'amministratore globale.
- Protezione dell'utente **finale** &ndash; Richiede l'autenticazione a più fattori per gli utenti solo quando un accesso è rischioso. 
- **Blocca l'autenticazione legacy** &ndash; Le app client precedenti e alcune nuove app non utilizzano protocolli di autenticazione più recenti e sicuri. Queste app precedenti possono ignorare i criteri di accesso condizionale e ottenere un accesso non autorizzato all'ambiente. Questo criterio blocca l'accesso da client che non supportano l'accesso condizionale. 
- **Richiedere l'autenticazione dell'AMF per la gestione dei servizi** &ndash; Richiede l'autenticazione a più fattori per l'accesso agli strumenti di gestione, incluso il portale di Azure (in cui vengono configurati i criteri di base). 

Microsoft consiglia di abilitare tutti questi criteri di base. Dopo aver abilitato questi criteri, agli amministratori e agli utenti verrà richiesto di eseguire la registrazione per l'autenticazione a più fattori di Azure.

Per ulteriori informazioni su questi criteri, vedere [What are Baseline Policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?


## <a name="set-up-baseline-policies"></a>Impostare i criteri di base

1. Accedere a [portale di Azure](https://portal.azure.com)e quindi passare a **Azure Active Directory** \> **accesso condizionale**di Azure Active Directory.
    
    I criteri di base sono elencati nella pagina. <br/> <br/>
    ![Pagina in cui sono elencati i criteri di base per l'accesso condizionale.](../media/baslinepolicies.png)
1. Per ogni criterio, vedere le istruzioni specifiche seguenti:

  - [Richiedi l'autenticazione a più fattori per gli amministratori](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [Richiedi l'autenticazione per gli utenti](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [Bloccare l'autenticazione legacy](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [Richiedere l'autenticazione dell'AMF per la gestione dei servizi](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

È possibile configurare molti altri criteri, ad esempio la necessità di applicazioni client approvate. Per ulteriori informazioni, vedere la [documentazione relativa all'accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/).
