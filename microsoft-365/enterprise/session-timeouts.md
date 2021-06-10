---
title: Timeout di sessione per Microsoft 365
ms.author: tracyp
author: MSFTTracyP
manager: scotv
ms.date: 6/29/2018
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: 37a5c116-5b07-4f70-8333-5b86fd2c3c40
ms.collection:
- M365-security-compliance
description: Scopri come vengono usati i timeout di sessione per bilanciare la sicurezza e la facilità di accesso nelle Microsoft 365 client.
ms.openlocfilehash: b85ed8a45727e8a8eed2537fa2233125cd05ece7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924917"
---
# <a name="session-timeouts-for-microsoft-365"></a>Timeout di sessione per Microsoft 365

La durata delle sessioni è una parte importante dell'autenticazione Microsoft 365 e sono un componente importante per il bilanciamento della sicurezza e il numero di richieste di credenziali agli utenti.

## <a name="session-times-for-microsoft-365-services"></a>Tempi di sessione per Microsoft 365 servizi

Quando gli utenti eseguono l'autenticazione in Microsoft 365 app Web o per dispositivi mobili, viene stabilita una sessione. Per tutta la durata della sessione, gli utenti non dovranno eseguire nuovamente l'autenticazione. Le sessioni possono scadere quando gli utenti sono inattivi, quando chiudono il browser o la scheda o quando il token di autenticazione scade per altri motivi, ad esempio quando la password è stata reimpostata. I Microsoft 365 hanno timeout di sessione diversi per corrispondere all'utilizzo tipico di ogni servizio.

Nella tabella seguente sono elencate le durate di sessione per Microsoft 365 servizi:

| Servizio Microsoft 365 | Timeout sessione |
|:-----|:-----|
|Interfaccia di amministrazione di Microsoft 365  <br/> |Viene richiesto di fornire le credenziali per l'interfaccia di amministrazione ogni 8 ore.  <br/> |
|SharePoint Online  <br/> |5 giorni di inattività purché gli utenti scentino **Mantieni l'accesso**. Se l'utente accede SharePoint Online dopo 24 o più ore dall'accesso precedente, il valore di timeout viene reimpostato su 5 giorni.  <br/> |
|Outlook Web App  <br/> |6 ore.  <br/> È possibile modificare questo valore utilizzando il _parametro ActivityBasedAuthenticationTimeoutInterval_ nel cmdlet [Set-OrganizationConfig.](/powershell/module/exchange/set-organizationconfig)  <br/> |
|Azure Active Directory  <br/> (Utilizzato dalle applicazioni Office e Microsoft 365 nei client Windows con l'autenticazione moderna abilitata)  <br/> | L'autenticazione moderna usa i token di accesso e i token di aggiornamento per concedere all'utente l'accesso Microsoft 365 risorse Azure Active Directory. Un token di accesso è un token Web JSON fornito dopo un'autenticazione riuscita ed è valido per 1 ora. Viene fornito anche un token di aggiornamento con una durata più lunga. Quando i token di accesso scadono, Office client usano un token di aggiornamento valido per ottenere un nuovo token di accesso. Questo scambio ha esito positivo se l'autenticazione iniziale dell'utente è ancora valida.  <br/>  I token di aggiornamento sono validi per 90 giorni e, con l'uso continuo, possono essere validi fino alla revoca.  <br/>  I token di aggiornamento possono essere invalidati da diversi eventi, ad esempio:  <br/>  La password dell'utente è cambiata dopo l'emissione del token di aggiornamento.  <br/>  Un amministratore può applicare criteri di accesso condizionale che limitano l'accesso alla risorsa a cui l'utente sta tentando di accedere.  <br/> |
|SharePoint e OneDrive per dispositivi mobili per Android, iOS e Windows 10  <br/> |La durata predefinita per il token di accesso è 1 ora. Il tempo massimo di inattività predefinito del token di aggiornamento è 90 giorni.  <br/> [Altre informazioni sui token e su come configurare la durata dei token](/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> Per revocare il token di aggiornamento, è possibile reimpostare la password Microsoft 365'utente  <br/> |
|Yammer con Microsoft 365 Sign-In  <br/> |Durata del browser. Se gli utenti chiudono il browser e Yammer accesso in un nuovo browser, Yammer verranno autenticati di nuovo con Microsoft 365. Se gli utenti utilizzano browser di terze parti che memorizzano nella cache i cookie, potrebbe non essere necessario eseguire nuovamente l'autenticazione alla riapertura del browser.  <br/> > [!NOTE]> Questo valore è valido solo per le reti Microsoft 365 Sign-In per Yammer.           |