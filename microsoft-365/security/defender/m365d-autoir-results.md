---
title: Dettagli e risultati di un'indagine automatizzata
description: Visualizzare i risultati e i risultati principali dell'indagine automatizzata in Microsoft 365 Defender
keywords: automatizzata, indagine, risultati, analizzare, dettagli, correzione, autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: ad774fc36f4f167cb7a4e695b9f572ceb55b968b
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274677"
---
# <a name="details-and-results-of-an-automated-investigation"></a>Dettagli e risultati di un'indagine automatizzata

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- Microsoft 365 Defender

Con Microsoft 365 Defender, quando [viene](m365d-autoir.md) eseguita un'indagine automatizzata, i dettagli su tale indagine sono disponibili sia durante che dopo il processo di indagine automatizzata. Se di dispone delle [autorizzazioni necessarie](m365d-action-center.md#required-permissions-for-action-center-tasks), è possibile visualizzare i dettagli in una visualizzazione dei dettagli dell'indagine. Questa visualizzazione offre lo stato aggiornato e la possibilità di approvare eventuali azioni in sospeso. 

![Dettagli indagine](../../media/mtp-air-investdetails.png)

## <a name="new-unified-investigation-page"></a>(NEW!) Pagina analisi unificata

La pagina di indagine è stata aggiornata di recente per includere informazioni su dispositivi, posta elettronica e contenuti di collaborazione. La nuova pagina di indagine unificata definisce un linguaggio comune e offre un'esperienza unificata per le indagini automatiche in [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) e Microsoft Defender per [Office 365](../office-365-security/defender-for-office-365.md). Per accedere alla pagina di indagine unificata, seleziona il collegamento nel banner giallo che vedrai in:

- Qualsiasi pagina di indagine nel Centro Office 365 sicurezza & conformità ( [https://protection.office.com](https://protection.office.com) )
- Qualsiasi pagina di indagine nel Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) )
- Qualsiasi evento imprevisto o centro notifiche nel centro Microsoft 365 sicurezza ( [https://security.microsoft.com](https://security.microsoft.com) )

## <a name="open-the-investigation-details-view"></a>Aprire la visualizzazione dei dettagli dell'indagine

È possibile aprire la visualizzazione dei dettagli dell'indagine utilizzando uno dei metodi seguenti:

- [Selezionare un elemento nel centro notifiche](#select-an-item-in-the-action-center)
- [Selezionare un'indagine dalla pagina dei dettagli dell'incidente](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>Selezionare un elemento nel centro notifiche

Il centro [notifiche migliorato](m365d-action-center.md) ( ) riunisce le azioni di correzione nei dispositivi, nella posta elettronica & contenuti di [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) collaborazione e identità. [](m365d-remediation-actions.md) Le azioni elencate includono le azioni di correzione eseguite automaticamente o manualmente. Nel centro notifiche è possibile visualizzare le azioni in attesa di approvazione e le azioni già approvate o completate. Puoi anche passare a ulteriori dettagli, ad esempio una pagina di indagine.

> [!TIP]
> È necessario disporre [di determinate autorizzazioni](m365d-action-center.md#required-permissions-for-action-center-tasks) per approvare, rifiutare o annullare azioni.

1. Andare su [https://security.microsoft.com](https://security.microsoft.com) ed eseguire l'accesso. 

2. Nel riquadro di spostamento, scegliere **Centro notifiche**. 

3. Nella scheda **In sospeso** o **Cronologia**, selezionare un elemento. Verrà visualizzato il riquadro a comparsa.

4. Esaminare le informazioni nel riquadro a comparsa e quindi eseguire una delle operazioni seguenti:
   - Selezionare **Apri pagina di indagine** per visualizzare ulteriori dettagli sull'indagine.
   - Selezionare **Approva** per avviare un'azione in sospeso.
   - Selezionare **Rifiuta** per impedire l'esecuzione di un'azione in sospeso.
   - Seleziona **Vai a ricerca** per passare a Ricerca [avanzata.](advanced-hunting-overview.md)

### <a name="open-an-investigation-from-an-incident-details-page"></a>Aprire un'indagine dalla pagina dei dettagli dell'incidente

Utilizzare una pagina dei dettagli di un incidente per visualizzare informazioni dettagliate relative a un incidente, inclusi gli avvisi che sono stati attivati, le informazioni su eventuali dispositivi, gli account utente o le cassette postali interessati.

1. Andare su [https://security.microsoft.com](https://security.microsoft.com) ed eseguire l'accesso. 

2. Nel riquadro di spostamento scegliere **Eventi imprevisti & avvisi** Eventi  >  **imprevisti**. 

3. Selezionare un elemento nell'elenco e quindi scegliere **Apri pagina evento imprevisto.**

4. Selezionare la **scheda Indagini** e quindi selezionare un'indagine nell'elenco. Verrà visualizzato il riquadro a comparsa.

5. Selezionare **Apri pagina di analisi**. 

Di seguito viene riportato un esempio.

![Dettagli incidente](../../media/mtp-incidentdetails-tabs.png)

## <a name="investigation-details"></a>Dettagli indagine

Utilizzare la vista dei dettagli dell'indagine per visualizzare le attività passate, attuali e in sospeso relative a un'indagine. Di seguito viene riportato un esempio.

![Dettagli indagine](../../media/mtp-air-investdetails.png)

Nella visualizzazione dei dettagli dell'indagine, è possibile vedere le informazioni nelle schede **Grafico dell'indagine**, **Avvisi**, **Dispositivi**, **Identità**, **Risultati principali**, **Entità**, **Log**, e **Azioni in sospeso**, descritte nella tabella seguente.

> [!NOTE]
> Le schede specifiche visualizzate in una pagina dei dettagli dell'indagine dipendono da ciò che include l'abbonamento. Ad esempio, se l'abbonamento non include Microsoft Defender per Office 365 Piano 2, non verrà visualizzata una **scheda Cassette** postali.

| Scheda | Descrizione |
|:--------|:--------|
| **Grafico dell'indagine**   | Fornisce una rappresentazione visiva dell'indagine. Descrive le entità ed elenca le minacce rilevate, insieme agli avvisi e alle eventuali azioni ancora in fase di approvazione.<br/>È possibile selezionare un elemento nel grafico per visualizzare ulteriori dettagli. Ad esempio, selezionando **l'icona**  Prova si visualizza la scheda Prova, in cui è possibile visualizzare le entità rilevate e i relativi verdetti. |
| **Avvisi**    | Elenca gli avvisi associati all'indagine. Gli avvisi possono derivare dalle funzionalità di protezione dalle minacce nel dispositivo di un utente, in Office app, Microsoft Cloud App Security e altre funzionalità di Microsoft 365 Defender.|
| **Dispositivi** | Elenca i dispositivi inclusi nell'indagine insieme al relativo livello di correzione. I livelli di correzione corrispondono al [livello di automazione per i gruppi di dispositivi.](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) |
| **Cassette postali** |Elenca le cassette postali che sono influenzate dalle minacce rilevate.  |
| **Utenti**  | Elenca gli account utente che sono influenzati dalle minacce rilevate. |
| **Prova** | Elenca le prove generate da avvisi o indagini. Include i verdetti (*Dannoso,* *Sospetto,* *Sconosciuto* *o* Nessuna minaccia trovata) e lo stato di correzione. |
| **Entità**  | Fornisce informazioni dettagliate su ogni entità analizzata, incluso un verdetto per ogni tipo di entità (*Dannoso,* *Sospetto* o *Nessuna minaccia trovata).*|
|**Log**    | Fornisce una visualizzazione cronologica dettagliata di tutte le azioni di indagine eseguite dopo l'attivazione di un avviso.|
| **Cronologia azioni in sospeso** | Elenca gli elementi che richiedono l'approvazione per continuare. Passare al centro notifiche ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) per approvare le azioni in sospeso. |

## <a name="next-steps"></a>Passaggi successivi

- [Visualizzare e gestire le azioni correttive](m365d-autoir-actions.md)
- [Ulteriori informazioni sulle azioni di correzione](m365d-remediation-actions.md)
