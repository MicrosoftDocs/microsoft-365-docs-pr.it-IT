---
title: Introduzione ai criteri delle applicazioni
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Introduzione a Informazioni sui criteri delle app.
ms.openlocfilehash: 3f80048835388e740ba64ac36d1aa19594bf7a9d
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420409"
---
# <a name="get-started-with-app-policies"></a>Introduzione ai criteri delle applicazioni

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

I criteri delle app per la governance delle app di Microsoft consentono di implementare condizioni più proattive o reattive per creare avvisi o correzioni automatiche per le esigenze specifiche di conformità con le app dell'organizzazione.

Per visualizzare l'elenco dei criteri correnti delle app, vai a **Centro conformità Microsoft 365> Protezione e governance delle app > Criteri**.

![Pagina di riepilogo dei criteri MAPG nel Centro conformità Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-policies.png)

## <a name="whats-available-on-the-app-policies-dashboard"></a>Elementi disponibili nel dashboard dei criteri dell'app

È possibile visualizzare il numero di criteri attivi e inattivi, il numero di test e le informazioni seguenti per ogni criterio:

- **Nome criterio**
- **Stato**

  - **Active**: tutte le azioni e la valutazione dei criteri sono attive.
  - **Inattiva**: tutte le azioni e la valutazione dei criteri sono disabilitate.
  - **Modalità di controllo**: la valutazione dei criteri è in modalità di controllo. Il criterio è attivo, ma le azioni dei criteri sono disabilitate.

- **Gravità**: Livello di gravità impostato su tutti gli avvisi attivati a causa della valutazione di questo criterio come TRUE, che fa parte della configurazione del criterio.
- **Numero di avvisi attivi**: avvisi generati dai criteri con uno stato **In corso** o **Nuovo**.
- **Numero totale di avvisi**: sia gli avvisi attivi che gli avvisi risolti per questo criterio.
- **Data ultimo avviso**: data dell'ultimo avviso generato a causa di questo criterio.
- **Ultima modifica**: data dell'ultima modifica del criterio.

L'elenco dei criteri viene ordinato per **Ultima modifica** per impostazione predefinita. Per ordinare l'elenco in base a un altro attributo, selezionare il nome dell'attributo.

Quando selezioni un criterio, ottieni un riquadro dettagliato dei criteri con questi dettagli aggiuntivi:

- **Descrizione**: spiegazione più dettagliata dello scopo del criterio.
- **Creato da**: nome dell'entità utente (UPN) dell'account che ha creato il criterio.
- Elenco degli avvisi attivi generati da questo criterio.

È possibile modificare o eliminare un criterio di app selezionando **Modifica** o **Elimina** nel riquadro dettagliato dei criteri oppure selezionando i puntini di sospensione verticali del criterio nell'elenco dei criteri.

È inoltre possibile:

- Creare un nuovo criterio. È possibile iniziare con un criterio di utilizzo delle app o un criterio di autorizzazione.
- Esporta l'elenco dei criteri in un file con valori delimitati da virgole (CSV). Ad esempio, puoi aprire il file CVS in Microsoft Excel e ordinare i criteri in base alla **Gravità** e quindi **Numero di avvisi totali**.
- Cerca nell'elenco dei criteri.

## <a name="next-step"></a>Passaggio successivo

[Creare un criterio dell'app.](app-governance-app-policies-create.md)
