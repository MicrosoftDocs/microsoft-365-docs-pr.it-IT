---
title: Timeout della sessione per Microsoft 365
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
description: Informazioni su come vengono utilizzati i timeout della sessione per bilanciare la sicurezza e la facilità di accesso nelle app client Microsoft 365.
ms.openlocfilehash: 2c0a7c2633715ac23942a22858b41e83a091c46a
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769293"
---
# <a name="session-timeouts-for-microsoft-365"></a>Timeout della sessione per Microsoft 365

La durata della sessione è una parte importante dell'autenticazione per Microsoft 365 e costituisce un componente importante per l'equilibratura della sicurezza e il numero di volte in cui gli utenti vengono richieste per le proprie credenziali.

## <a name="session-times-for-microsoft-365-services"></a>Orari della sessione per i servizi Microsoft 365

Quando gli utenti eseguono l'autenticazione in una qualsiasi delle app Web o app per dispositivi mobili di Microsoft 365, viene stabilita una sessione. Per tutta la durata della sessione, gli utenti non dovranno rieseguire l'autenticazione. Le sessioni possono scadere quando gli utenti sono inattivi, quando chiudono il browser o la scheda oppure quando il token di autenticazione scade per altri motivi, ad esempio quando la password è stata reimpostata. I servizi Microsoft 365 dispongono di timeout di sessione diversi per corrispondere all'utilizzo tipico di ogni servizio.

Nella tabella seguente sono elencate le durata della sessione per i servizi Microsoft 365:

| Servizio Microsoft 365 | Timeout sessione |
|:-----|:-----|
|Interfaccia di amministrazione di Microsoft 365  <br/> |Viene richiesto di fornire le credenziali per l'interfaccia di amministrazione ogni 8 ore.  <br/> |
|SharePoint Online  <br/> |5 giorni di inattività finché gli utenti scelgono di **tenermi connesso** . Se l'utente accede nuovamente a SharePoint Online dopo che sono passate 24 o più ore dall'accesso precedente, il valore di timeout viene reimpostato su 5 giorni.  <br/> |
|Outlook Web App  <br/> |6 ore.  <br/> È possibile modificare questo valore utilizzando il parametro  _ActivityBasedAuthenticationTimeoutInterval_ nel cmdlet [Set-OrganizationConfig](https://go.microsoft.com/fwlink/p/?LinkId=615378) .  <br/> |
|Azure Active Directory  <br/> (Utilizzata dalle applicazioni di Office e Microsoft 365 nei client Windows con autenticazione moderna abilitata)  <br/> | L'autenticazione moderna utilizza i token di accesso e aggiorna i token per concedere agli utenti l'accesso alle risorse di Microsoft 365 utilizzando Azure Active Directory. Un token di accesso è un token Web JSON fornito dopo una corretta autenticazione ed è valido per 1 ora. Viene fornito anche un token di aggiornamento con una durata più lunga. Quando i token di accesso scadono, i client di Office utilizzano un token di aggiornamento valido per ottenere un nuovo token di accesso. Questo Exchange ha esito positivo se l'autenticazione iniziale dell'utente è ancora valida.  <br/>  I token di aggiornamento sono validi per 90 giorni e, con utilizzo continuativo, possono essere validi fino alla revoca.  <br/>  I token di aggiornamento possono essere invalidati da diversi eventi, ad esempio:  <br/>  La password dell'utente è cambiata dopo che è stato emesso il token di aggiornamento.  <br/>  Un amministratore può applicare criteri di accesso condizionale che limitano l'accesso alla risorsa che l'utente sta cercando di accedere.  <br/> |
|App per dispositivi mobili di SharePoint e OneDrive per Android, iOS e Windows 10  <br/> |La durata predefinita per il token di accesso è di 1 ora. La durata massima inattiva predefinita del token di aggiornamento è di 90 giorni.  <br/> [Ulteriori informazioni sui token e su come configurare le durata dei token](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> Per revocare il token di aggiornamento, è possibile reimpostare la password Microsoft 365 dell'utente  <br/> |
|Yammer con Microsoft 365 Sign-In  <br/> |Durata del browser. Se gli utenti chiudono il browser e accedono a Yammer in un nuovo browser, Yammer li riautentica con Microsoft 365. Se gli utenti utilizzano browser di terze parti che memorizzano nella cache i cookie, potrebbero non essere in grado di eseguire nuovamente l'autenticazione quando riaprono il browser.  <br/> > [!NOTE]> questo è valido solo per le reti che utilizzano Microsoft 365 Sign-In per Yammer.           |

