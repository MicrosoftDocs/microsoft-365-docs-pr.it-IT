---
title: Gestire le caratteristiche di Office visualizzate in Novità
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
description: Decidere quali funzionalità di Office mostrare o nascondere quando un utente sceglie Guida > Novità nella propria app di Office in Windows usando la funzionalità "Novità di Office" nell'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: d0b5bc3e643b306d9a38a707fed50ab546249c2b
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122349"
---
# <a name="manage-which-office-features-appear-in-whats-new"></a>Gestire le caratteristiche di Office visualizzate in Novità

Quando viene rilasciata una funzionalità importante di Office, gli utenti riceveranno un messaggio in proposito quando scelgono ?? Novità nella  >   propria app di Office in Windows.

È possibile controllare quali di queste funzionalità vengono visualizzati dagli utenti usando la funzionalità Novità **di Office nell'interfaccia** di amministrazione di Microsoft 365. Se si decide di nascondere un messaggio di funzionalità agli utenti, è sempre possibile tornare in seguito e decidere di mostrarlo agli utenti.

> [!NOTE]
> - Nascondere un messaggio di funzionalità agli utenti non disabilita la funzionalità nell'app di Office.
> - Per usare la funzionalità Novità di Office, è necessario disporre del ruolo di amministratore globale o di amministratore delle app **di Office.**

## <a name="show-or-hide-new-features"></a>Mostrare o nascondere le nuove funzionalità 

1. Nell'interfaccia di amministrazione di Microsoft 365, in **Impostazioni,** scegliere **Impostazioni organizzazione.**
2. Nella scheda **Servizi** scegliere Novità **di Office.**
3. Quando fai clic sul nome della funzionalità, viene visualizzato un riquadro a comparsa con le informazioni seguenti:
     - Breve descrizione della funzionalità.
     - Collegamento a un articolo per ulteriori informazioni sulla funzionalità.
     - Le applicazioni di Office in cui viene visualizzata la caratteristica.
     - La prima versione (versione) in cui è disponibile la funzionalità per tale canale.
4. Scegliere **Nascondi dagli utenti.** In caso contrario, se in precedenza la funzionalità era stata celata, scegliere **Mostra agli utenti.**

È inoltre possibile selezionare più caratteristiche nella pagina Gestisci le caratteristiche di **Office** visualizzate nella pagina Novità e quindi scegliere Nascondi **o** **Mostra.**

> [!NOTE]
> - Se una caratteristica è disponibile in più  app di Office, se si imposta la caratteristica su Nascosta, il messaggio della funzionalità viene nascosto in tutte le app di Office.
> - Tutti i messaggi di funzionalità vengono visualizzati agli utenti per impostazione predefinita. Questo è lo stato predefinito per tutte le funzionalità e lo stato cambia solo se si è scelto di nascondere o visualizzare un messaggio di funzionalità.
> - È anche possibile accedere alla funzionalità **Novità di Office dall'interfaccia** di amministrazione di Microsoft 365 Apps ( [https://config.office.com](https://config.office.com) ). La caratteristica è disponibile in  >  **Personalizzazione - Nuova gestione.**

## <a name="list-of-features"></a>Elenco delle caratteristiche

È possibile filtrare le caratteristiche visualizzate nella pagina Gestisci **le caratteristiche di Office visualizzate nella pagina** Novità. È possibile filtrare in base al canale, all'applicazione o allo stato oppure in base a una combinazione di essi.

Le nuove funzionalità vengono visualizzate nella pagina in base alla pianificazione seguente:

||||
|:-----|:-----|:-----|
|**Canale** <br/> |**Data** <br/> |**Eseguire un'azione** <br/> |
|**Current** <br/> |15 del mese  <br/> |1 - 3 settimane prima del rilascio mensile <br/> |
|**Enterprise mensile** <br/> |Primo del mese  <br/> |Due settimane prima del rilascio principale che offre nuove funzionalità |
|**Enterprise semestra elettronica (anteprima)** <br/> |1 settembre e 1 marzo <br/> | 2 settimane prima del rilascio principale che offre nuove funzionalità|
|**Enterprise semestra elettronica** <br/> |1 gennaio e 1 luglio <br/> | 2 settimane prima del rilascio principale che offre nuove funzionalità<br/> |

Per altre informazioni sul momento in cui vengono rilasciate nuove versioni per ogni canale di aggiornamento, vedere Cronologia degli aggiornamenti per [Microsoft 365 Apps (elencate in base alla data).](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date)

## <a name="add-the-whats-new-in-office-card-to-the-admin-center-home-page"></a>Aggiungere la scheda "Novità di Office" alla home page dell'interfaccia di amministrazione

1. Nella pagina di amministrazione di Microsoft 365 scegliere **Aggiungi scheda** nella parte superiore della pagina
2. Individuare **Gestisci le caratteristiche di Office visualizzate nell'elenco** Novità e sceglierla.
3. Dopo aver visualizzato la scheda nella home page, è possibile scegliere Novità **di Office** per visualizzare o nascondere le [funzionalità](#show-or-hide-new-features) dell'organizzazione.


## <a name="related-articles"></a>Articoli correlati

[La gestione delle novità di Office è ora disponibile a livello generale](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-is-now-generally-available/ba-p/1179954)