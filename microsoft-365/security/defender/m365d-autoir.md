---
title: Analisi e risposta automatizzate in Microsoft 365 Defender
description: Ottenere una panoramica delle funzionalità di indagine e risposta automatizzate, denominate anche auto-riparazione, in Microsoft 365 Defender
keywords: automated, investigation, alert, trigger, action, remediation, self-healing
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 01/29/2021
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: c12937c016875c26a7212117e41aac4349cb540d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065901"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Analisi e risposta automatizzate in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- Microsoft 365 Defender

Se l'organizzazione usa [Microsoft 365 Defender,](microsoft-365-defender.md)il team delle operazioni di sicurezza riceve un avviso ogni volta che viene rilevato un artefatto dannoso o sospetto. Dato il flusso apparentemente senza fine di minacce che arrivano, i team di sicurezza spesso devono affrontare difficoltà nell'affrontare l'elevato volume di avvisi. Fortunatamente, Microsoft 365 Defender include funzionalità di analisi e correzione automatizzate (AIR) che consentono al team delle operazioni di sicurezza di affrontare le minacce in modo più efficiente ed efficiente.

In questo articolo viene fornita una panoramica di AIR e vengono forniti collegamenti ai passaggi successivi e a risorse aggiuntive.

> [!TIP]
> Vuoi provare Microsoft 365 Defender? È possibile [valutarlo in un ambiente lab o](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) eseguire il progetto pilota in [produzione.](m365d-pilot.md?ocid=cx-evalpilot)

## <a name="how-automated-investigation-and-self-healing-works"></a>Funzionamento dell'indagine automatizzata e dell'auto-riparazione

Quando vengono attivati avvisi di sicurezza, il team delle operazioni di sicurezza deve esaminare tali avvisi ed eseguire le operazioni necessarie per proteggere l'organizzazione. La classificazione in ordine di priorità e l'analisi degli avvisi può richiedere molto tempo, soprattutto quando continuano ad arrivare nuovi avvisi durante il corso di un'indagine. I team delle operazioni di sicurezza possono sentirsi sopraffatti dall'enorme volume di minacce che devono monitorare e da cui devono proteggersi. Le funzionalità di indagine e risposta automatizzate, con auto-riparazione, in Microsoft 365 Defender possono essere di aiuto.

Guarda il video seguente per vedere come funziona l'auto-riparazione: <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

In Microsoft 365 Defender, l'indagine e la risposta automatizzate con funzionalità di auto-riparazione funzionano su dispositivi, posta elettronica & contenuti e identità.
 
> [!TIP]
> In questo articolo viene descritto il funzionamento dell'indagine e della risposta automatizzate. Per configurare queste funzionalità, vedere [Configure automated investigation and response capabilities in Microsoft 365 Defender.](m365d-configure-auto-investigation-response.md)

## <a name="your-own-virtual-analyst"></a>Analista virtuale

Immagina di avere un analista virtuale nel tuo team di operazioni di sicurezza di livello 1 o di livello 2. L'analista virtuale simula i passaggi ideali che le operazioni di sicurezza seguirebbero per analizzare e correggere le minacce. L'assistente virtuale potrebbe lavorare 24 ore su 24, 7 giorni su 7 con capacità illimitata e intraprendere un carico significativo di indagini e correzione delle minacce. Un tale assistente virtuale potrebbe ridurre significativamente i tempi di risposta, togliendo l'incombenza al team delle operazioni di sicurezza per consentirgli di svolgere altri importanti progetti strategici. Se questo scenario sembra fantascienza, non lo è! Tale analista virtuale fa parte della famiglia di prodotti Microsoft 365 Defender e il suo nome è analisi e risposta *automatizzate.*

Le funzionalità di analisi e risposta automatizzate consentono al team delle operazioni di sicurezza di aumentare notevolmente la capacità dell'organizzazione di gestire gli avvisi e gli incidenti di sicurezza. Grazie all'indagine e alla risposta automatizzate, è possibile ridurre i costi di gestione delle attività di indagine e correzione e ottenere il massimo dalla famiglia di prodotti di protezione dalle minacce. Le funzionalità di analisi e risposta automatizzate consentono al team delle operazioni di sicurezza di:

1. stabilire se una minaccia richiede un'azione;
2. Eseguire (o consigliare) tutte le azioni di correzione necessarie;
3. Determinare se e quali altre indagini devono essere eseguite; e
4. ripetere il processo per altri avvisi, se necessario.

## <a name="the-automated-investigation-process"></a>Il processo di indagine automatizzata

Un avviso crea un evento imprevisto, che può avviare un'indagine automatizzata. L'indagine automatizzata determina un verdetto per ogni prova. I verdetti possono essere:
- *Dannoso*;
- *Sospetto;* o 
- *Nessuna minaccia trovata.* 

Vengono identificate le azioni di correzione per entità dannose o sospette. Di seguito sono riportati alcuni esempi di azioni correttive:
- Invio di un file in quarantena;
- Arresto di un processo;
- Isolamento di un dispositivo;
- Blocco di un URL. e 
- altre azioni. Vedere [Azioni di correzione in Microsoft 365 Defender.](m365d-remediation-actions.md)

A seconda [di come vengono configurate](m365d-configure-auto-investigation-response.md) le funzionalità di analisi e risposta automatizzate per l'organizzazione, le azioni di correzione vengono eseguite automaticamente o solo dopo l'approvazione da parte del team delle operazioni di sicurezza. Tutte le azioni, in sospeso o completate, sono elencate nel [Centro notifiche.](m365d-action-center.md)

Durante l'esecuzione di un'indagine, tutti gli altri avvisi correlati che emergono vengono aggiunti all'indagine fino al suo completamento. Se un'entità incriminata viene vista altrove, l'indagine automatizzata espande il suo ambito per includere tale entità e il processo di indagine si ripete. 

In Microsoft 365 Defender, ogni indagine automatizzata correla i segnali tra Microsoft Defender for Identity, Microsoft Defender for Endpoint e Defender per Office 365, come riepilogato nella tabella seguente: 

|Entità |Servizi di protezione dalle minacce  |
|:---------|:---------|
|Dispositivi (denominati anche endpoint e talvolta definiti computer)     |[Microsoft Defender ATP](../defender-endpoint/automated-investigations.md)<br/>[Microsoft Defender per identità](/azure-advanced-threat-protection/what-is-atp) |      
|Contenuto della posta elettronica (messaggi di posta elettronica che possono contenere file e URL)     |[Microsoft Defender per Office 365](../defender-365-security/defender-for-office-365.md)         |

> [!NOTE]
> Non tutti gli avvisi attivano un'indagine automatizzata e non tutte le indagini generano azioni di correzione automatizzate; dipende dal modo in cui l'indagine e la risposta automatizzate sono configurate per l'organizzazione. Vedere [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).

## <a name="next-steps"></a>Passaggi successivi

- [Vedere i prerequisiti per l'indagine e la risposta automatizzate in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [Configurare l'indagine e la risposta automatizzate per l'organizzazione](m365d-configure-auto-investigation-response.md)
- [Altre informazioni sul centro notifiche](m365d-action-center.md)
