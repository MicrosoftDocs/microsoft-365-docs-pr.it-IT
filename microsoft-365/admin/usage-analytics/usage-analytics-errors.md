---
title: Risoluzione dei problemi relativi all'analisi dell'utilizzo di Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Scopri come risolvere i problemi con l'app modello Analisi di utilizzo di Microsoft 365.
ms.openlocfilehash: bc7f1f7188a209188f1a67a20bf79477c6e1d4a0
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580739"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Risoluzione dei problemi relativi all'analisi dell'utilizzo di Microsoft 365

Esplorare il seguente elenco di messaggi di errore per ottenere assistenza sui problemi più comuni relativi all'analisi dell'utilizzo di Microsoft 365.
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>Non è possibile elaborare la richiesta. Devi prima sottoscrivere questi dati dall'interfaccia di amministrazione di Microsoft 365

 **Codice di errore:** 422 
  
 **Dove verrà visualizzato questo messaggio:** In Power BI quando ci si connette all'app modello Analisi di utilizzo di Microsoft 365 o quando si chiamano direttamente le API per la creazione di report di Microsoft 365. 
  
 **Causa:** Prima di connetterti all'app, devi sottoscrivere i dati dall'interfaccia di amministrazione di Microsoft 365. Se questo passaggio non viene eseguito per primo, non potrai connetterti all'app modello, anche se fornisci l'ID tenant di Microsoft 365. 
  
 **Per correggere l'errore:** Per sottoscrivere i dati, passare all'interfaccia di amministrazione Report Utilizzo e individuare il riquadro Analisi di utilizzo di \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 nella pagina del dashboard principale. Selezionare il **pulsante Introduzione** e  quindi, nel riquadro Report visualizzato, attivare l'impostazione Rendi disponibili i dati per l'analisi di utilizzo di **Microsoft 365** per Power BI e **Salva.**
  
## <a name="we-are-processing-your-data"></a>Stiamo elaborando i dati

 **Dove verrà visualizzato questo messaggio:** Nel riquadro Analisi di utilizzo di **Microsoft 365** nel dashboard **Utilizzo** nell'interfaccia di amministrazione di Microsoft 365. 
  
 **Causa:** Quando [acconsenti esplicitamente](enable-usage-analytics.md) alla visualizzazione dei dati nell'app modello dall'interfaccia di amministrazione di Microsoft 365, il sistema Microsoft 365 inizia a generare dati di utilizzo cronologici per la tua organizzazione. A seconda delle dimensioni del tenant, questa operazione potrebbe richiedere da 2 a 48 ore. 
  
 **Per risolvere il problema:** Sii paziente, ma se il messaggio non cambia in I tuoi dati sono pronti **dopo** 3 giorni, contatta il supporto di [Microsoft 365 per le aziende.](../contact-support-for-business-products.md)
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>Non è possibile elaborare la richiesta in questo momento. La preparazione dei dati per l'organizzazione non è ancora terminata

 **Codice di errore:** 423 
  
 **Dove verrà visualizzato questo messaggio:** In Power BI, quando ci si connette all'app modello Analisi di utilizzo di Microsoft 365 o quando si chiamano direttamente le API per la creazione di report di Microsoft 365. 
  
 **Causa:** Quando scegli [di visualizzare i](enable-usage-analytics.md) dati nell'app modello dall'interfaccia di amministrazione, il sistema Microsoft 365 inizia a generare dati di utilizzo cronologici per la tua organizzazione. A seconda delle dimensioni del tenant, questo passaggio può richiedere da due a 48 ore. 
  
 **Per risolvere il problema:** Basta essere pazienti, ma se il  messaggio non cambia in I dati sono pronti anche 3 giorni dopo l'avvio, contattare il supporto [di Microsoft 365 per le aziende](../contact-support-for-business-products.md).
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>L'ID tenant specificato non è nel formato corretto

 **Codice di errore:** 400 
  
 **Dove verrà visualizzato questo messaggio:** In Power BI, quando ci si connette all'app modello Analisi di utilizzo di Microsoft 365 o quando si chiamano direttamente le API per la creazione di report di Microsoft 365. 
  
 **Causa:** L'ID tenant è un GUID e deve essere nel formato xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. Se si immette un'altra stringa nella casella di input del tenant, verrà visualizzato questo errore. 
  
 **Per correggere l'errore:** Passare all'interfaccia di amministrazione Report Utilizzo e individuare il riquadro Analisi di utilizzo di \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 nella pagina del dashboard principale. L'ID tenant è elencato nel riquadro. Puoi copiarlo da qui e incollarlo nella finestra di dialogo per la connessione all'app modello. 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>L'ID tenant specificato non è stato riconosciuto dal sistema

 **Codice di errore:** 404 
  
 **Dove verrà visualizzato questo messaggio:** In Power BI quando ci si connette all'app modello Analisi di utilizzo di Microsoft 365 o quando si chiamano direttamente le API per la creazione di report di Microsoft 365. 
  
 **Causa:** L'ID tenant specificato non è valido o non esiste. 
  
 **Per correggere l'errore:** Passare all'interfaccia di amministrazione Report Utilizzo e individuare il riquadro Analisi di utilizzo di \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 nella pagina del dashboard principale. L'ID tenant è elencato nel riquadro. Puoi copiarlo da qui e incollarlo nella finestra di dialogo per la connessione all'app modello. 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>Immettere di nuovo le credenziali per accedere a Power BI

Codice di errore: 302
  
 **Dove verrà visualizzato questo messaggio:** In Power BI quando ci si connette all'app modello Analisi di utilizzo di Microsoft 365 o quando si chiamano direttamente le API per la creazione di report di Microsoft 365. 
  
 **Causa:** il codice di autorizzazione ha avuto esito negativo e potrebbe essere necessario immettere nuovamente le credenziali. 
  
 **Per correggere l'errore:** disconnettersi da Power BI, quindi eseguire di nuovo l'accesso. 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>Non si ha l'autorizzazione giusta per accedere a questi dati. Per accedere ai dati da questo servizio, è necessario essere un amministratore globale o un amministratore prodotto

 **Codice di errore:** 403 
  
 **Dove verrà visualizzato questo messaggio:** In Power BI quando ci si connette all'app modello Analisi di utilizzo di Microsoft 365 o quando si chiamano direttamente le API per la creazione di report di Microsoft 365. 
  
 **Causa:** Il codice di autorizzazione non è riuscito perché l'utente che ha tentato di connettersi all'app modello non dispone del livello di autorizzazione giusto per accedere a questi dati. 
  
 **Per correggere l'errore:** Fornire le credenziali di un utente che è un amministratore globale, un amministratore  di  **Exchange,** un amministratore di **Skype for Business,** un amministratore di **SharePoint,** un lettore globale o un lettore di report per connettersi all'app modello.  Per [ulteriori informazioni, vedere Informazioni sui](../add-users/about-admin-roles.md) ruoli di amministratore. 
  
## <a name="refresh-failed"></a>Aggiornamento non riuscito

 **Dove viene visualizzato questo messaggio:** messaggio di posta elettronica da Power BI o stato di errore nella cronologia degli aggiornamenti. 
  
 **Causa:** A volte le credenziali dell'utente connesso all'app modello vengono reimpostate e non aggiornate nelle impostazioni di connessione dell'app modello causando la visualizzazione di errori di aggiornamento. 
  
 **Per correggere l'errore:** In Power BI individuare il set di dati corrispondente all'app  modello Analisi di utilizzo di Microsoft 365, selezionare pianifica l'aggiornamento e fornire le credenziali di amministratore. 
  
Se non funziona, cancella la cache e crea di nuovo l'app modello.
  
  
