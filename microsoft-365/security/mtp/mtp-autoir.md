---
title: Analisi e risposta automatizzate in Microsoft 365 Defender
description: Panoramica delle funzionalità di analisi e risposta automatizzate, denominate anche riparazione automatica, in Microsoft 365 Defender
keywords: automatizzato, indagine, avviso, trigger, azione, correzione, riparazione automatica
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 905455e4cd70485e099f8005b5f8876b1a5d9caf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930331"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Analisi e risposta automatizzate in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

> Si vuole provare Microsoft 365 Defender? È possibile [valutarlo in un ambiente lab o](https://aka.ms/mtp-trial-lab) eseguire il progetto pilota in [produzione.](https://aka.ms/m365d-pilotplaybook)
>

## <a name="how-automated-investigation-and-self-healing-works"></a>Come funzionano l'indagine automatizzata e la riparazione automatica

Quando vengono attivati avvisi di sicurezza, il team delle operazioni di sicurezza deve esaminare tali avvisi ed eseguire le operazioni necessarie per proteggere l'organizzazione. La classificazione in ordine di priorità e l'analisi degli avvisi può richiedere molto tempo, soprattutto quando continuano ad arrivare nuovi avvisi durante il corso di un'indagine. I team delle operazioni di sicurezza possono sentirsi sopraffatti dall'enorme volume di minacce che devono monitorare e da cui devono proteggersi. Le funzionalità di analisi e risposta automatizzate, con autori-riparazione, in Microsoft 365 Defender possono essere di aiuto.

Guardare il video seguente per vedere come funziona la riparazione automatica:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

In Microsoft 365 Defender, l'analisi e la risposta automatizzate con funzionalità di riparazione automatica funzionano su dispositivi, contenuti & posta elettronica e identità.
 
> [!TIP]
> Questo articolo descrive il funzionamento dell'indagine e della risposta automatizzate. Per configurare queste funzionalità, vedere Configurare le funzionalità di analisi e [risposta automatizzate in Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md)

## <a name="your-own-virtual-analyst"></a>Analista virtuale

È possibile immaginare un analista virtuale nel proprio team delle operazioni di sicurezza di livello 1 o di livello 2. L'analista virtuale simula i passaggi ideali che le operazioni di sicurezza seguirebbero per analizzare e correggere le minacce. L'assistente virtuale potrebbe lavorare 24 ore su 24, 7 giorni su 7 con capacità illimitata e intraprendere un carico significativo di indagini e correzione delle minacce. Un tale assistente virtuale potrebbe ridurre significativamente i tempi di risposta, togliendo l'incombenza al team delle operazioni di sicurezza per consentirgli di svolgere altri importanti progetti strategici. Se questo scenario sembra essere una fiction, non lo è! Tale analista virtuale fa parte della famiglia di prodotti Microsoft 365 Defender e il suo nome è analisi e risposta *automatizzate.*

L'analisi e la risposta automatizzate consentono al team delle operazioni di sicurezza di aumentare notevolmente la capacità dell'organizzazione di gestire gli avvisi e gli incidenti di sicurezza. Con l'analisi e la risposta automatizzate, è possibile ridurre i costi di gestione delle attività di analisi e correzione e ottenere il massimo dalla famiglia di prodotti di protezione dalle minacce. l'analisi e la risposta automatizzate consentono al team delle operazioni di sicurezza di:

1. stabilire se una minaccia richiede un'azione;
2. eseguire (o consigliare) tutte le azioni correttive necessarie;
3. stabilire quali ulteriori indagini dovrebbero essere intraprese;
4. ripetere il processo per altri avvisi, se necessario.

## <a name="the-automated-investigation-process"></a>Il processo di indagine automatizzata

**Avviso** > **incidente** > **indagine automatizzata** > **verdetto** > **azione correttiva**

Un avviso attivato crea un evento imprevisto, che può avviare un'indagine automatizzata. Tale indagine può comportare una o più azioni correttive. In Microsoft 365 Defender, ogni indagine automatizzata correla i segnali tra Microsoft Defender for Identity, Microsoft Defender for Endpoint e Defender per Office 365, come riepilogato nella tabella seguente: 

|Entità |Servizi di protezione dalle minacce  |
|---------|---------|
|Dispositivi (detti anche endpoint)     |[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Che cosa è Microsoft Defender per identità?](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|Contenuto della posta elettronica (file e messaggi nelle cassette postali)     |[Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

Ogni indagine genera verdetti (*Dannoso,* Sospetto o Nessuna minaccia *trovata)* per ogni prova esaminata. A seconda del tipo di minaccia e del verdetto risultante, le azioni di correzione vengono eseguite automaticamente o al momento dell'approvazione da parte del team delle operazioni di sicurezza dell'organizzazione. Le azioni in sospeso e quelle completate sono elencate nel [centro notifiche](mtp-action-center.md).

Durante l'esecuzione di un'indagine, tutti gli altri avvisi correlati che emergono vengono aggiunti all'indagine fino al suo completamento. Se un'entità incriminata viene visualizzata altrove, l'indagine automatizzata amplierà il suo ambito per includere tale entità e verrà eseguito un playbook della sicurezza generale. 

> [!NOTE]
> Non tutti gli avvisi attivano un'indagine automatizzata e non tutte le indagini generano azioni correttive automatizzate; Tutto questo dipende dalla configurazione dell'indagine e della risposta automatizzate per l'organizzazione. Vedere [Configurare le funzionalità di analisi e risposta automatizzate in Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md)


## <a name="next-steps"></a>Passaggi successivi

- [Vedere i prerequisiti per l'analisi e la risposta automatizzate in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [Configurare l'analisi e la risposta automatizzate per l'organizzazione](mtp-configure-auto-investigation-response.md)
- [Altre informazioni sul centro notifiche](mtp-action-center.md)
