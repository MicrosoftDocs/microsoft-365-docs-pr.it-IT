---
title: Visualizzare e gestire regole di rilevamento personalizzate in Microsoft Defender ATP
ms.reviewer: ''
description: Informazioni su come visualizzare e gestire regole di rilevamento personalizzate
keywords: rilevamenti personalizzati, visualizzare, gestire, avvisi, modificare, eseguire su richiesta, regole di rilevamento, ricerca avanzata, ricerca, query, azioni di risposta, mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b36521ada55fa3d60538beb981d487b153e7b1f9
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498750"
---
# <a name="view-and-manage-custom-detection-rules"></a>Visualizzare e gestire regole di rilevamento personalizzate

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Gestisci le regole [di rilevamento personalizzate esistenti](custom-detection-rules.md) per assicurarti che trovino in modo efficace minacce ed esercitino azioni. Scopri come visualizzare l'elenco delle regole, controllare le esecuzioni precedenti ed esaminare gli avvisi che hanno attivato. È inoltre possibile eseguire una regola su richiesta e modificarla.

## <a name="required-permissions"></a>Autorizzazioni necessarie

Per creare o gestire rilevamenti personalizzati, [il ruolo](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) deve disporre dell'autorizzazione gestisci **impostazioni di** sicurezza.

## <a name="view-existing-rules"></a>Visualizzare le regole esistenti

Per visualizzare tutte le regole di rilevamento personalizzate esistenti, passare a **Impostazioni**  >  **Rilevamenti personalizzati.** Nella pagina sono elencate tutte le regole con le seguenti informazioni di esecuzione:

- **Ultima esecuzione:** data dell'ultima esecuzione di una regola per verificare la presenza di corrispondenze di query e generare avvisi
- **Stato dell'ultima esecuzione:** indica se una regola è stata eseguita correttamente
- **Esecuzione successiva:** l'esecuzione pianificata successiva
- **Stato:** indica se una regola è stata attivata o disattivata

## <a name="view-rule-details-modify-rule-and-run-rule"></a>Visualizzare i dettagli della regola, modificare la regola ed eseguire la regola

Per visualizzare informazioni complete su una regola di rilevamento personalizzata, selezionare il nome della regola nell'elenco delle regole in **Impostazioni**  >  **Rilevamenti personalizzati**. In una pagina sulla regola selezionata vengono visualizzate le informazioni seguenti:

- Informazioni generali sulla regola, inclusi i dettagli dell'avviso, lo stato di esecuzione e l'ambito
- Elenco degli avvisi attivati
- Elenco delle azioni attivate

![Pagina regola di rilevamento personalizzata](images/atp-custom-detection-rule-details.png)<br>
*Pagina regola di rilevamento personalizzata*

È inoltre possibile eseguire le azioni seguenti nella regola da questa pagina:

- **Esegui:** eseguire immediatamente la regola. Questa azione reimposta anche l'intervallo per l'esecuzione successiva.
- **Modifica:** modificare la regola senza modificare la query
- **Modifica query**: modifica la query in ricerca avanzata
- **Attivare**  /  **Disattiva:** abilita la regola o arresta l'esecuzione
- **Delete:** disattivare la regola e rimuoverla

>[!TIP]
>Per visualizzare rapidamente le informazioni ed eseguire azioni su un elemento di una tabella, utilizzare la colonna di selezione [&#10003;] a sinistra della tabella.

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica dei rilevamenti personalizzati](overview-custom-detections.md)
- [Creare regole di rilevamento](custom-detection-rules.md)
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Visualizzare e organizzare gli avvisi](alerts-queue.md)
