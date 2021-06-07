---
title: Microsoft Defender for Endpoint Flow connector
ms.reviewer: ''
description: Usa Microsoft Defender for Endpoint Flow connector per automatizzare la sicurezza e creare un flusso che verrà attivato ogni volta che si verifica un nuovo avviso nel tenant.
keywords: flusso, api supportate, api, flusso Microsoft, query, automazione
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: dd0cc3c2da134750f905b1f80746d6ec65cc70b2
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769705"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a>Microsoft Power Automate (in precedenza Microsoft Flow) e Funzioni di Azure

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

L'automazione delle procedure di sicurezza è un requisito standard per ogni centro operativo di sicurezza moderno. La mancanza di cyber defender professionali obbliga SOC a lavorare nel modo più efficiente e l'automazione è un must. Microsoft Power Automate supporta connettori diversi che sono stati creati esattamente per questo. È possibile creare un'automazione di routine end-to-end entro pochi minuti.

Microsoft Defender API ha un connettore Flow con molte funzionalità.

![Immagine delle credenziali di modifica1](images/api-flow-0.png)

> [!NOTE]
> Per ulteriori informazioni sui prerequisiti di licenza per i connettori premium, vedere [Licensing for premium connectors.](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors)


## <a name="usage-example"></a>Esempio di utilizzo

L'esempio seguente illustra come creare un Flow che viene attivato ogni volta che si verifica un nuovo avviso nel tenant.

1. Accedere a [Microsoft Power Automate](https://flow.microsoft.com).

2. Vai a **Flussi my**  >  **New**  >  **Automated-from blank**.

    ![Immagine delle credenziali di modifica2](images/api-flow-1.png)

3. Scegli un nome per il Flow, cerca "Trigger Microsoft Defender ATP" come trigger e quindi seleziona il nuovo trigger Avvisi.

    ![Immagine delle credenziali di modifica3](images/api-flow-2.png)

Ora si dispone di Flow che viene attivato ogni volta che si verifica un nuovo avviso.

![Immagine delle credenziali di modifica4](images/api-flow-3.png)

Tutto quello che devi fare ora è scegliere i passaggi successivi.
Ad esempio, puoi isolare il dispositivo se la gravità dell'avviso è Alta e inviare un messaggio di posta elettronica al riguardo.
Il trigger Avviso fornisce solo l'ID avviso e l'ID computer. È possibile utilizzare il connettore per espandere queste entità.

### <a name="get-the-alert-entity-using-the-connector"></a>Ottenere l'entità Alert usando il connettore

1. Scegliere **Microsoft Defender ATP** per il nuovo passaggio.

2. Scegliere **Avvisi - Api per il singolo avviso.**

3. Imposta **l'ID avviso** dell'ultimo passaggio come **Input**.

    ![Immagine delle credenziali di modifica5](images/api-flow-4.png)

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a>Isolare il dispositivo se la gravità dell'avviso è Alta

1. Aggiungi **condizione** come nuovo passaggio.

2. Verificare se la gravità **dell'avviso è uguale a** Alta.

   Se sì, aggiungi **l'azione Microsoft Defender ATP - Isolare il** computer con l'ID computer e un commento.

    ![Immagine delle credenziali di modifica6](images/api-flow-5.png)

3. Aggiungi un nuovo passaggio per l'invio tramite posta elettronica dell'avviso e dell'isolamento. Esistono più connettori di posta elettronica molto facili da usare, ad esempio Outlook o Gmail.

4. Salvare il flusso.

È inoltre possibile creare un **flusso pianificato** che esegue query di ricerca avanzata e molto altro ancora.

## <a name="related-topic"></a>Argomento correlato
- [API di Microsoft Defender per endpoint](apis-intro.md)
