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
description: Informazioni su come vengono usati i timeout di sessione per bilanciare la sicurezza e la facilità di accesso nelle app client di Microsoft 365.
ms.openlocfilehash: 2c0a7c2633715ac23942a22858b41e83a091c46a
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769293"
---
# <a name="session-timeouts-for-microsoft-365"></a>Timeout di sessione per Microsoft 365

La durata delle sessioni è una parte importante dell'autenticazione per Microsoft 365 e è un componente importante per il bilanciamento della sicurezza e il numero di volte in cui agli utenti vengono richieste le credenziali.

## <a name="session-times-for-microsoft-365-services"></a>Tempi di sessione per i servizi di Microsoft 365

Quando gli utenti eseguono l'autenticazione in una qualsiasi delle app Web o per dispositivi mobili di Microsoft 365, viene stabilita una sessione. Per tutta la durata della sessione, gli utenti non dovranno eseguire nuovamente l'autenticazione. Le sessioni possono scadere quando gli utenti sono inattivi, quando chiudono il browser o la scheda o quando il token di autenticazione scade per altri motivi, ad esempio quando la password è stata reimpostata. I servizi di Microsoft 365 hanno timeout di sessione diversi per corrispondere all'uso tipico di ogni servizio.

Nella tabella seguente sono elencate le durate delle sessioni per i servizi di Microsoft 365:

| Servizio Microsoft 365 | Timeout sessione |
|:-----|:-----|
|Interfaccia di amministrazione di Microsoft 365  <br/> |Viene richiesto di fornire le credenziali per l'interfaccia di amministrazione ogni 8 ore.  <br/> |
|SharePoint Online  <br/> |5 giorni di inattività, purché gli utenti scentino **Mantieni l'accesso.** Se l'utente accede di nuovo a SharePoint Online dopo 24 o più ore dall'accesso precedente, il valore di timeout viene reimpostato su 5 giorni.  <br/> |
|Outlook Web App  <br/> |6 ore.  <br/> È possibile modificare questo valore utilizzando il _parametro ActivityBasedAuthenticationTimeoutInterval_ nel cmdlet [Set-OrganizationConfig.](https://go.microsoft.com/fwlink/p/?LinkId=615378)  <br/> |
|Azure Active Directory  <br/> (Utilizzato dalle applicazioni di Office e Microsoft 365 nei client Windows con l'autenticazione moderna abilitata)  <br/> | L'autenticazione moderna usa i token di accesso e i token di aggiornamento per concedere agli utenti l'accesso alle risorse di Microsoft 365 tramite Azure Active Directory. Un token di accesso è un token Web JSON fornito dopo un'autenticazione riuscita ed è valido per 1 ora. Viene fornito anche un token di aggiornamento con una durata maggiore. Quando i token di accesso scadono, i client di Office utilizzano un token di aggiornamento valido per ottenere un nuovo token di accesso. Questo scambio ha esito positivo se l'autenticazione iniziale dell'utente è ancora valida.  <br/>  I token di aggiornamento sono validi per 90 giorni e, con l'uso continuo, possono essere validi fino a quando non vengono revocati.  <br/>  I token di aggiornamento possono essere invalidati da diversi eventi, ad esempio:  <br/>  La password dell'utente è cambiata dopo l'emissione del token di aggiornamento.  <br/>  Un amministratore può applicare criteri di accesso condizionale che limitano l'accesso alla risorsa a cui l'utente sta tentando di accedere.  <br/> |
|App per dispositivi mobili di SharePoint e OneDrive per Android, iOS e Windows 10  <br/> |La durata predefinita per il token di accesso è 1 ora. Il tempo massimo di inattività predefinito del token di aggiornamento è 90 giorni.  <br/> [Altre informazioni sui token e su come configurare la durata dei token](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> Per revocare il token di aggiornamento, è possibile reimpostare la password di Microsoft 365 dell'utente  <br/> |
|Yammer con Microsoft 365 Sign-In  <br/> |Durata del browser. Se gli utenti chiudono il browser e accedono a Yammer in un nuovo browser, Yammer li autentica nuovamente con Microsoft 365. Se gli utenti utilizzano browser di terze parti che memorizzano nella cache i cookie, potrebbe non essere necessario eseguire nuovamente l'autenticazione quando riapre il browser.  <br/> > [!NOTE]> è valido solo per le reti che usano Microsoft 365 Sign-In per Yammer.           |

