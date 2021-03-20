---
title: Manage which ‎Office‎ features appear in What's New
f1.keywords:
- NOCSH
ms.author: danbrown
author: DHB-MSFT
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
description: Decidere quali caratteristiche di Office mostrare o nascondere quando un utente sceglie Guida > Novità nella propria app di Office in Windows usando la funzionalità "Novità di Office" nell'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: b9d20e3df4a2de540316dce0e6a6905c07e65176
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915028"
---
# <a name="manage-which-office-features-appear-in-whats-new"></a>Manage which Office‎ features appear in What's New

When an important ‎Office‎ feature is released, users will get a message about it when they choose **Help**  >  **What's New** in their ‎‎Office‎‎ app on ‎Windows‎.

È possibile controllare quali di questi messaggi di funzionalità vengono visualizzati dagli utenti usando la funzionalità Novità **di Office nell'interfaccia** di amministrazione di Microsoft 365. Se si decide di nascondere un messaggio di funzionalità agli utenti, è sempre possibile tornare in un secondo momento e decidere di mostrarlo agli utenti.

> [!NOTE]
> - Nascondere un messaggio di funzionalità agli utenti non disabilita la funzionalità nell'app di Office.
> - Per usare la funzionalità Novità di Office, è necessario disporre del ruolo amministratore globale o di amministratore delle app **di Office.**

## <a name="show-or-hide-new-features"></a>Mostrare o nascondere le nuove funzionalità 

1. Nell'interfaccia di amministrazione di Microsoft 365, in **Impostazioni** scegliere **Impostazioni organizzazione.**
2. Nella scheda **Servizi** scegliere **Novità di Office**.
3. Quando fai clic sul nome della funzionalità, viene visualizzato un riquadro a comparsa con le informazioni seguenti:
     - Breve descrizione della funzionalità.
     - Collegamento a un articolo per ulteriori informazioni sulla funzionalità.
     - Le applicazioni di Office in cui viene visualizzata la caratteristica.
     - Prima versione (versione) in cui è disponibile la funzionalità per tale canale.
4. Scegliere **Nascondi dagli utenti**. In caso contrario, se la funzionalità è stata precedentemente nascosto, scegliere **Mostra agli utenti.**

You can also select multiple features on the **Manage which ‎Office‎ features appear in What's New** page, and then choose either **Hide** or **Show**.

> [!NOTE]
> - Se una funzionalità è disponibile in più  app di Office, l'impostazione della caratteristica su Nascosto nasconde il messaggio della funzionalità in tutte le app di Office.
> - Per impostazione predefinita, tutti i messaggi di funzionalità vengono visualizzati agli utenti. Questo è lo stato predefinito per tutte le funzionalità e lo stato cambia solo se si è scelto di nascondere o visualizzare un messaggio di funzionalità.
> - È anche possibile accedere alla funzionalità **Novità di Office dall'interfaccia** di amministrazione di Microsoft 365 Apps ( [https://config.office.com](https://config.office.com) ). La funzionalità è disponibile in  >  **Personalizzazione What's New Management.**

## <a name="list-of-features"></a>Elenco delle caratteristiche

You can filter which features appear on the **Manage which ‎Office‎ features appear in What's New** page. È possibile filtrare in base al canale, all'applicazione o allo stato oppure in base a una combinazione di essi.

Le nuove funzionalità vengono visualizzate nella pagina in base alla pianificazione seguente:

||||
|:-----|:-----|:-----|
|**Canale** <br/> |**Data** <br/> |**Eseguire un'azione** <br/> |
|**Current** <br/> |15 del mese  <br/> |1 - 3 settimane prima del rilascio mensile <br/> |
|**Enterprise mensile** <br/> |Primo del mese  <br/> |Due settimane prima del rilascio principale che introduce nuove funzionalità |
|**Organizzazione semestrare (anteprima)** <br/> |1 settembre e 1 marzo <br/> | 2 settimane prima della versione principale che offre nuove funzionalità|
|**Enterprise semestrare** <br/> |1 gennaio e 1 luglio <br/> | 2 settimane prima della versione principale che offre nuove funzionalità<br/> |

Per ulteriori informazioni sul rilascio di nuove versioni a ogni canale di aggiornamento, vedere Cronologia degli aggiornamenti per [Microsoft 365 Apps (elencate per data).](/officeupdates/update-history-microsoft365-apps-by-date)

## <a name="add-the-whats-new-in-office-card-to-the-admin-center-home-page"></a>Aggiungere la scheda "Novità di Office" alla home page dell'interfaccia di amministrazione

1. Nella pagina di amministrazione di Microsoft 365 scegliere **Aggiungi scheda** nella parte superiore della pagina
2. Individuare **Gestire le caratteristiche di Office visualizzate nell'elenco** Novità e sceglierla.
3. Dopo aver visualizzato la scheda nella home page, è possibile scegliere Novità **di Office** per visualizzare o nascondere le [caratteristiche](#show-or-hide-new-features) dell'organizzazione.


## <a name="related-articles"></a>Articoli correlati

[La gestione delle novità di Office è ora disponibile in generale](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-is-now-generally-available/ba-p/1179954)