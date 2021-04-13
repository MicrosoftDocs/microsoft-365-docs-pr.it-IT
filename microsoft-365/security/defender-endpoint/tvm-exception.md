---
title: Creare e visualizzare le eccezioni per i suggerimenti per la sicurezza - gestione delle minacce e delle vulnerabilità
description: Creare e monitorare le eccezioni per i suggerimenti sulla sicurezza nella gestione delle minacce e delle vulnerabilità.
keywords: microsoft defender for endpoint tvm remediation, mdatp tvm, threat and vulnerability management, threat & vulnerability management, threat & vulnerability management remediation, tvm remediation intune, tvm remediation sccm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4f37300a742ab8cac32e95863cb706f1fd5f5d66
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689414"
---
# <a name="create-and-view-exceptions-for-security-recommendations---threat-and-vulnerability-management"></a>Creare e visualizzare le eccezioni per i suggerimenti per la sicurezza - gestione delle minacce e delle vulnerabilità

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Gestione di minacce e vulnerabilità](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

In alternativa a una richiesta di correzione quando al momento un suggerimento non è rilevante, è possibile creare eccezioni per i suggerimenti. Se l'organizzazione dispone di gruppi di dispositivi, sarà possibile impostare l'ambito dell'eccezione a gruppi di dispositivi specifici. Le eccezioni possono essere create per i gruppi di dispositivi selezionati o per tutti i gruppi di dispositivi passati e presenti.  

Quando viene creata un'eccezione per un suggerimento, il suggerimento sarà attivo solo alla fine della durata dell'eccezione. Lo stato del suggerimento verrà modificato in **Eccezione completa** o **Eccezione parziale** (per gruppo di dispositivi).

## <a name="permissions"></a>Autorizzazioni

Solo gli utenti con autorizzazioni di "gestione delle eccezioni" possono gestire le eccezioni (inclusa la creazione o l'annullamento). [Ulteriori informazioni sui ruoli RBAC.](user-roles.md)

![Visualizzazione dell'autorizzazione di gestione delle eccezioni.](images/tvm-exception-permissions.png)

## <a name="create-an-exception"></a>Creare un'eccezione

Selezionare un suggerimento per la sicurezza per cui si desidera creare un'eccezione, quindi selezionare **Opzioni eccezione** e compilare il modulo.  

![Visualizzazione del punto in cui si trova il pulsante per le "opzioni di eccezione" in un riquadro a comparsa dei suggerimenti per la sicurezza.](images/tvm-exception-options.png)

### <a name="exception-by-device-group"></a>Eccezione per gruppo di dispositivi

Applica l'eccezione a tutti i gruppi di dispositivi correnti o scegli gruppi di dispositivi specifici. I gruppi di dispositivi futuri non verranno inclusi nell'eccezione. I gruppi di dispositivi che hanno già un'eccezione non verranno visualizzati nell'elenco. Se si selezionano solo determinati gruppi di dispositivi, lo stato di raccomandazione cambierà da "attivo" a "eccezione parziale". Lo stato verrà modificato in "eccezione completa" se si selezionano tutti i gruppi di dispositivi.

![Elenco a discesa del gruppo di dispositivi.](images/tvm-exception-device-group-500.png)

#### <a name="filtered-views"></a>Visualizzazioni filtrate

Se hai filtrato per gruppo di dispositivi in una qualsiasi delle pagine di gestione delle minacce e delle vulnerabilità, solo i gruppi di dispositivi filtrati verranno visualizzati come opzioni.

Questo è il pulsante per filtrare in base al gruppo di dispositivi in una delle pagine di gestione delle minacce e delle vulnerabilità: 

![Visualizzazione del filtro dei gruppi di dispositivi selezionati.](images/tvm-selected-device-groups.png)

Visualizzazione eccezioni con gruppi di dispositivi filtrati:

![Elenco a discesa del gruppo di dispositivi filtrato.](images/tvm-exception-device-filter500.png)

#### <a name="large-number-of-device-groups"></a>Numero elevato di gruppi di dispositivi

Se l'organizzazione ha più di 20 gruppi di dispositivi, seleziona **Modifica** accanto all'opzione gruppo di dispositivi filtrato.

![Viene illustrato come modificare un numero elevato di gruppi.](images/tvm-exception-edit-groups.png)

Verrà visualizzato un riquadro a comparsa in cui è possibile cercare e scegliere i gruppi di dispositivi che si desidera includere. Seleziona l'icona del segno di spunta sotto Cerca per selezionare/deselezionare tutto.

![Visualizzazione del riquadro a comparsa gruppo di dispositivi di grandi dimensioni.](images/tvm-exception-device-group-flyout-400.png)

### <a name="global-exceptions"></a>Eccezioni globali

Se si dispone delle autorizzazioni di amministratore globale, sarà possibile creare e annullare un'eccezione globale. Influisce **su tutti** i gruppi di dispositivi correnti e futuri nell'organizzazione e solo un utente con autorizzazioni simili sarà in grado di modificarlo. Lo stato di raccomandazione cambierà da "attivo" a "eccezione completa".

![Opzione di eccezione globale visualizzata.](images/tvm-exception-global.png)

Alcuni aspetti da tenere presenti:

- Se un suggerimento è in un'eccezione globale, le nuove eccezioni create per i gruppi di dispositivi verranno sospese fino alla scadenza o all'annullamento dell'eccezione globale. Dopo questo punto, le nuove eccezioni del gruppo di dispositivi saranno effettive fino alla scadenza.
- Se un suggerimento contiene già eccezioni per gruppi di dispositivi specifici e viene creata un'eccezione globale, l'eccezione del gruppo di dispositivi verrà sospesa fino alla scadenza o all'annullamento dell'eccezione globale prima della scadenza.

### <a name="justification"></a>Giustificazione

Seleziona la giustificazione per l'eccezione che devi creare invece di correggere il suggerimento per la sicurezza in questione. Compila il contesto di giustificazione, quindi imposta la durata dell'eccezione.

L'elenco seguente elenca in dettaglio le giustificazioni alla base delle opzioni di eccezione:

- **Controllo di terze parti** - Un prodotto o un software di terze parti già si rivolge a questa raccomandazione- La scelta di questo tipo di giustificazione ridurrà il punteggio di esposizione e aumenterà il punteggio sicuro perché il rischio è ridotto
- **Mitigazione alternativa** - Uno strumento interno è già in grado di risolvere questo consiglio: la scelta di questo tipo di giustificazione ridurrà il punteggio di esposizione e aumenterà il punteggio sicuro perché il rischio è ridotto
- **Rischio accettato** - Pone un rischio basso e/o l'implementazione della raccomandazione è troppo costosa
- **Correzione pianificata (tolleranza):** già pianificata ma in attesa di esecuzione o autorizzazione

## <a name="view-all-exceptions"></a>Visualizzare tutte le eccezioni

Passare alla **scheda Eccezioni** nella **pagina Correzione.** È possibile filtrare in base a giustificazione, tipo e stato.

 Seleziona un'eccezione per aprire un riquadro a comparsa con altri dettagli. Le eccezioni per gruppo di dispositivi includeranno un elenco di tutti i gruppi di dispositivi trattati dall'eccezione, che puoi esportare. È inoltre possibile visualizzare il suggerimento correlato o annullare l'eccezione.

![Visualizzazione della scheda "Eccezioni" nella pagina Correzione.](images/tvm-exception-view.png)

## <a name="how-to-cancel-an-exception"></a>Come annullare un'eccezione

Per annullare un'eccezione, passare alla **scheda Eccezioni** nella **pagina Correzione.** Selezionare l'eccezione.

Per annullare l'eccezione per tutti i gruppi di dispositivi o per un'eccezione globale, seleziona il **pulsante Annulla eccezione per tutti i gruppi di** dispositivi. Potrai annullare solo le eccezioni per i gruppi di dispositivi per cui hai le autorizzazioni.

![Pulsante Annulla.](images/tvm-exception-cancel.png)

### <a name="cancel-the-exception-for-a-specific-device-group"></a>Annullare l'eccezione per un gruppo di dispositivi specifico

Seleziona il gruppo di dispositivi specifico per annullare l'eccezione. Verrà visualizzato un riquadro a comparsa per il gruppo di dispositivi ed è possibile selezionare **Annulla eccezione.**

![Mostra come selezionare un gruppo di dispositivi specifico.](images/tvm-exception-device-group-hover.png)

## <a name="view-impact-after-exceptions-are-applied"></a>Impatto della visualizzazione dopo l'applicazione delle eccezioni

Nella pagina Suggerimenti per la sicurezza seleziona **Personalizza** colonne e seleziona le caselle dispositivi esposti **(dopo** le eccezioni) e **Impatto (dopo le eccezioni).**

![Visualizzazione delle opzioni di personalizzazione delle colonne.](images/tvm-after-exceptions.png)

La colonna dispositivi esposti (dopo le eccezioni) mostra i dispositivi rimanenti che sono ancora esposti alle vulnerabilità dopo l'applicazione delle eccezioni. Le giustificazioni di eccezione che influiscono sull'esposizione includono "controllo di terze parti" e "mitigazione alternativa". Altre giustificazioni non riducono l'esposizione di un dispositivo e vengono comunque considerate esposte.

L'impatto (dopo le eccezioni) mostra l'impatto rimanente sul punteggio di esposizione o sul punteggio sicuro dopo l'applicazione delle eccezioni. Le giustificazioni delle eccezioni che influiscono sui punteggi includono "controllo di terze parti" e "mitigazione alternativa". Altre giustificazioni non riducono l'esposizione di un dispositivo e quindi il punteggio di esposizione e il punteggio sicuro non cambiano.

![Visualizzazione delle colonne nella tabella.](images/tvm-after-exceptions-table.png)

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica della gestione delle minacce e delle vulnerabilità](next-gen-threat-and-vuln-mgt.md)
- [Correggere le vulnerabilità](tvm-remediation.md)
- [Consigli sulla sicurezza](tvm-security-recommendation.md)
- [Punteggio di esposizione.](tvm-exposure-score.md)
- [Punteggio di sicurezza Microsoft per dispositivi](tvm-microsoft-secure-score-devices.md)
