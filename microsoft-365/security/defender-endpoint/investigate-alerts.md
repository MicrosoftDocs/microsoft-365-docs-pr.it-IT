---
title: Analizzare gli avvisi di Microsoft Defender for Endpoint
description: Usa le opzioni di indagine per ottenere informazioni dettagliate sugli avvisi che influiscono sulla rete, sul loro significato e su come risolverli.
keywords: indagare, indagine, dispositivi, dispositivo, coda avvisi, dashboard, indirizzo IP, file, inviare, invii, analisi approfondita, sequenza temporale, ricerca, dominio, URL, IP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 8b3b864e716957c24893d2097249440b0a90f10a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186102"
---
# <a name="investigate-alerts-in-microsoft-defender-for-endpoint"></a>Analizzare gli avvisi in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatealerts-abovefoldlink) 

Analizzare gli avvisi che interessano la rete, comprenderne il significato e come risolverli.

Selezionare un avviso dalla coda degli avvisi per passare alla pagina di avviso. Questa visualizzazione contiene il titolo dell'avviso, gli asset interessati, il riquadro laterale dei dettagli e la storia dell'avviso.

Nella pagina di avviso iniziare l'indagine selezionando le risorse interessate o una delle entità nella visualizzazione albero della storia di avviso. Il riquadro dei dettagli viene popolato automaticamente con ulteriori informazioni sugli elementi selezionati. Per sapere quali tipi di informazioni è possibile visualizzare qui, vedere [Esaminare gli avvisi in Microsoft Defender per Endpoint.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/review-alerts)

## <a name="investigate-using-the-alert-story"></a>Analizzare usando la storia di avviso

La storia dell'avviso dettaglia il motivo per cui l'avviso è stato attivato, gli eventi correlati che si sono verificati prima e dopo, nonché altre entità correlate.

Le entità sono selezionabili e ogni entità che non è un avviso è espandibile usando l'icona di espansione sul lato destro della scheda dell'entità. L'entità con lo stato attivo verrà indicata da una striscia blu a sinistra della scheda dell'entità, con l'avviso nel titolo che è stato attivato in un primo momento.

Espandi entità per visualizzare i dettagli a colpo d'occhio. Se si seleziona un'entità, il contesto del riquadro dei dettagli verrà commutato in questa entità e sarà possibile esaminare ulteriori informazioni e gestire tale entità. Selezionando *...* a destra della scheda dell'entità verranno mostrate tutte le azioni disponibili per tale entità. Queste stesse azioni vengono visualizzate nel riquadro dei dettagli quando l'entità è attiva.

> [!NOTE]
> La sezione della storia dell'avviso può contenere più di un avviso, con altri avvisi correlati allo stesso albero di esecuzione visualizzati prima o dopo l'avviso selezionato.

![Esempio di una storia di avviso con un avviso attivo e alcune schede espanse](images/alert-story-tree.png)

## <a name="take-action-from-the-details-pane"></a>Eseguire un'azione dal riquadro dei dettagli

Dopo aver selezionato un'entità di interesse, il riquadro dei dettagli cambia per visualizzare le informazioni sul tipo  di entità selezionato, le informazioni storiche quando è disponibile e offrire controlli per eseguire azioni su questa entità direttamente dalla pagina di avviso.

Al termine dell'analisi, tornare all'avviso avviato, contrassegnare lo stato dell'avviso come **Risolto** e classificarlo come **Avviso** falso o **Avviso True.** La classificazione degli avvisi consente di ottimizzare questa funzionalità per fornire avvisi più veri e meno falsi.

Se lo classifichiamo come un avviso vero, puoi anche selezionare una determinazione, come mostrato nell'immagine seguente.

![Frammento del riquadro dei dettagli con un avviso risolto e l'elenco a discesa di determinazione espanso](images/alert-details-resolved-true.png)

Se si verifica un falso avviso con un'applicazione line-of-business, creare una regola di eliminazione per evitare questo tipo di avviso in futuro.

![azioni e classificazione nel riquadro dei dettagli con la regola di eliminazione evidenziata](images/alert-false-suppression-rule.png)

> [!TIP]
> Se riscontri problemi non descritti in precedenza, usa il pulsante per fornire feedback o 🙂 aprire un ticket di supporto.


## <a name="related-topics"></a>Argomenti correlati
- [Visualizzare e organizzare la coda di Microsoft Defender for Endpoint Alerts](alerts-queue.md)
- [Gestire gli avvisi di Microsoft Defender for Endpoint](manage-alerts.md)
- [Analizzare un file associato a un avviso di Defender for Endpoint](investigate-files.md)
- [Analizzare i dispositivi nell'elenco Defender for Endpoint Devices](investigate-machines.md)
- [Analizzare un indirizzo IP associato a un avviso Defender for Endpoint](investigate-ip.md)
- [Analizzare un dominio associato a un avviso Defender for Endpoint](investigate-domain.md)
- [Analizzare un account utente in Defender for Endpoint](investigate-user.md)


