---
title: Risoluzione dei problemi relativi all'analisi dell'utilizzo di Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Informazioni su come risolvere i problemi relativi all'app modello di analisi dei dati di utilizzo di Microsoft 365.
ms.openlocfilehash: bf8e4ece7b1e310d91f418f5388cae9aa27f2aa7
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841436"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Risoluzione dei problemi relativi all'analisi dell'utilizzo di Microsoft 365

Esaminare l'elenco dei messaggi di errore seguenti per ottenere assistenza con i problemi più comuni relativi all'analisi dell'utilizzo di Microsoft 365.
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>Non è possibile elaborare la richiesta. Per prima cosa, è necessario iscriversi a questi dati dall'interfaccia di amministrazione di Microsoft 365

 **Codice di errore:** 422 
  
 **Dove viene visualizzato questo messaggio:** In Power BI quando ci si connette all'app modello di analisi dei dati di utilizzo di Microsoft 365 o quando si chiama direttamente le API di report di Microsoft 365. 
  
 **Causa:** Prima di potersi connettere all'app, è necessario abbonarsi ai dati dell'interfaccia di amministrazione di Microsoft 365. Se questo passaggio non viene effettuato per primo, non sarà possibile connettersi all'app modello, anche se si fornisce l'ID tenant Microsoft 365. 
  
 **Per correggere l'errore:** Per sottoscrivere i dati, passare all'interfaccia di amministrazione \> **segnala** l' \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">utilizzo</a> e individuare il riquadro Analisi utilizzo Microsoft 365 nella pagina del dashboard principale. Selezionare il pulsante **inizia** e quindi nel riquadro **report** che si apre, trasformare i **dati disponibili in analisi di utilizzo di Microsoft 365 per** l'impostazione di Power bi su e **Save** .
  
## <a name="we-are-processing-your-data"></a>Stiamo elaborando i dati

 **Dove viene visualizzato questo messaggio:** Nel riquadro **Analisi utilizzo microsoft 365** sul dashboard di **utilizzo** nell'interfaccia di amministrazione di Microsoft 365. 
  
 **Causa:** Quando si [sceglie di visualizzare i dati nell'app modello](enable-usage-analytics.md) dall'interfaccia di amministrazione di Microsoft 365, il sistema Microsoft 365 inizia a generare dati di utilizzo cronologici per l'organizzazione. A seconda delle dimensioni del tenant, questa operazione potrebbe richiedere da 2 a 48 ore. 
  
 **Per risolvere il riguardo:** Basta essere pazienti, ma se il messaggio non cambia ai **dati è pronto** dopo 3 giorni, contattare il [supporto tecnico Microsoft 365 for business](../contact-support-for-business-products.md).
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>Non è possibile elaborare la richiesta in questo momento. La preparazione dei dati per l'organizzazione non è ancora terminata

 **Codice di errore:** 423 
  
 **Dove viene visualizzato questo messaggio:** In Power BI, quando ci si connette all'app modello di analisi di utilizzo di Microsoft 365 o quando si chiamano direttamente le API di report di Microsoft 365. 
  
 **Causa:** Quando si [sceglie di visualizzare i dati nell'app modello](enable-usage-analytics.md) dall'interfaccia di amministrazione, il sistema Microsoft 365 inizia a generare dati di utilizzo cronologici per l'organizzazione. A seconda delle dimensioni del tenant, questo passaggio può richiedere da due ore a 48 ore. 
  
 **Per risolvere il riguardo:** Basta essere pazienti, ma se il messaggio non cambia ai **dati è pronto** anche 3 giorni dopo l'inizio, contattare il [supporto tecnico Microsoft 365 for business](../contact-support-for-business-products.md).
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>L'ID tenant specificato non è nel formato corretto

 **Codice di errore:** 400 
  
 **Dove viene visualizzato questo messaggio:** In Power BI, quando ci si connette all'app modello di analisi di utilizzo di Microsoft 365 o quando si chiamano direttamente le API di report di Microsoft 365. 
  
 **Causa:** L'ID tenant è un GUID e deve essere nel formato xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. Se si immette qualsiasi altra stringa nella casella di input tenant, verrà visualizzato questo errore. 
  
 **Per correggere l'errore:** Passare all'interfaccia di amministrazione \> **segnala** l' \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">utilizzo</a> e individuare il riquadro Analisi utilizzo Microsoft 365 nella pagina del dashboard principale. L'ID tenant è elencato nel riquadro. È possibile copiarlo da qui e incollarlo nella finestra di dialogo per la connessione all'app modello. 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>L'ID tenant specificato non è stato riconosciuto dal sistema

 **Codice di errore:** 404 
  
 **Dove viene visualizzato questo messaggio:** In Power BI quando ci si connette all'app modello di analisi dei dati di utilizzo di Microsoft 365 o quando si chiama direttamente le API di report di Microsoft 365. 
  
 **Causa:** L'ID tenant specificato non è valido o non esiste. 
  
 **Per correggere l'errore:** Passare all'interfaccia di amministrazione \> **segnala** l' \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">utilizzo</a> e individuare il riquadro Analisi utilizzo Microsoft 365 nella pagina del dashboard principale. L'ID tenant è elencato nel riquadro. È possibile copiarlo da qui e incollarlo nella finestra di dialogo per la connessione all'app modello. 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>Immettere di nuovo le credenziali per accedere a Power BI

Codice di errore: 302
  
 **Dove viene visualizzato questo messaggio:** In Power BI quando ci si connette all'app modello di analisi dei dati di utilizzo di Microsoft 365 o quando si chiama direttamente le API di report di Microsoft 365. 
  
 **Causa:** il codice di autorizzazione ha avuto esito negativo e potrebbe essere necessario immettere nuovamente le credenziali. 
  
 **Per correggere l'errore:** disconnettersi da Power BI, quindi eseguire di nuovo l'accesso. 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>Non si ha l'autorizzazione giusta per accedere a questi dati. Per accedere ai dati da questo servizio, è necessario essere un amministratore globale o un amministratore prodotto

 **Codice di errore:** 403 
  
 **Dove viene visualizzato questo messaggio:** In Power BI quando ci si connette all'app modello di analisi dei dati di utilizzo di Microsoft 365 o quando si chiama direttamente le API di report di Microsoft 365. 
  
 **Causa:** Il codice di autorizzazione ha avuto esito negativo perché l'utente che ha tentato di connettersi all'app modello non ha il livello di autorizzazione appropriato per accedere a questi dati. 
  
 **Per correggere l'errore:** Specificare le credenziali di un utente che sia un amministratore **globale** , un amministratore di **Exchange** , un amministratore di **Skype for business** , un amministratore di **SharePoint** , un **lettore globale** o un **lettore di report** per connettersi all'app modello. Per ulteriori informazioni, vedere informazioni [sui ruoli di amministratore](../add-users/about-admin-roles.md) . 
  
## <a name="refresh-failed"></a>Aggiornamento non riuscito

 **Dove viene visualizzato questo messaggio:** messaggio di posta elettronica da Power BI o stato di errore nella cronologia degli aggiornamenti. 
  
 **Causa:** A volte le credenziali dell'utente che ha effettuato l'accesso all'app modello vengono reimpostate e non aggiornate nelle impostazioni di connessione dell'app modello causando la possibilità di visualizzare gli errori di aggiornamento. 
  
 **Per correggere l'errore:** In Power BI, individuare il set di dati corrispondente all'app modello di analisi di utilizzo di Microsoft 365, selezionare **Pianifica aggiornamento** e fornire le credenziali di amministratore. 
  
In caso contrario, cancellare la cache e creare di nuovo l'app modello.
  
  
