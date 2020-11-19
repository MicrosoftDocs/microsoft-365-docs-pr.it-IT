---
title: Analisi e risposta automatizzate in Microsoft 365 Defender
description: Ottenere una panoramica delle funzionalità di analisi e risposta automatizzate, denominate anche self-healing, in Microsoft 365 Defender
keywords: automatizzato, investigazione, allarme, trigger, azione, correzione, correzione automatica
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 2b8872288291adc0b9fc5e1c1541f885711df230
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356704"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Analisi e risposta automatizzate in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

> Vuoi provare Microsoft 365 Defender? È possibile [valutarla in un ambiente lab](https://aka.ms/mtp-trial-lab) o [eseguire il progetto pilota in produzione](https://aka.ms/m365d-pilotplaybook).
>

Quando vengono attivati gli avvisi di sicurezza, spetta al team delle operazioni di sicurezza esaminare gli avvisi e procedere per proteggere l'organizzazione. La classificazione in ordine di priorità e l'analisi degli avvisi può richiedere molto tempo, soprattutto quando continuano ad arrivare nuovi avvisi durante il corso di un'indagine. I team delle operazioni di sicurezza possono sentirsi sopraffatti dall'enorme volume di minacce che devono monitorare e da cui devono proteggersi. Le funzionalità di ricerca e risposta automatizzate, con la correzione automatica, possono essere utili in Microsoft 365 Defender.

Guardare il video seguente per vedere come funziona la guarigione automatica:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

In Microsoft 365 Defender, l'analisi automatizzata e la risposta con funzionalità di autoguarigione funzionano tra i dispositivi, la posta elettronica & il contenuto e le identità. Microsoft 365 Defender riunisce le funzionalità seguenti: 
- [Analisi e correzione automatizzate in Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Analisi e risposta automatizzate in Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [Rilevamento delle minacce avanzato di Azure](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
 
In questo articolo viene descritto come funziona l'analisi automatizzata e la risposta. Per configurare queste funzionalità, vedere [Configure Automatic Investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).

## <a name="your-virtual-analyst"></a>Analista virtuale

È possibile immaginare un analista virtuale nel proprio team delle operazioni di sicurezza di livello 1 o di livello 2. L'analista virtuale simula i passaggi ideali che le operazioni di sicurezza seguirebbero per analizzare e correggere le minacce. L'assistente virtuale potrebbe lavorare 24 ore su 24, 7 giorni su 7 con capacità illimitata e intraprendere un carico significativo di indagini e correzione delle minacce. Un tale assistente virtuale potrebbe ridurre significativamente i tempi di risposta, togliendo l'incombenza al team delle operazioni di sicurezza per consentirgli di svolgere altri importanti progetti strategici. Se questo scenario suona come fantascienza, non lo è. Tale analista virtuale fa parte della famiglia di prodotti Microsoft 365 Defender e il relativo nome è l' *analisi e la risposta automatizzate*.

L'analisi e la risposta automatizzate consentono al team di operazioni di sicurezza di aumentare drasticamente la capacità dell'organizzazione di gestire gli avvisi di sicurezza e gli incidenti. Con l'analisi e la risposta automatizzata, è possibile ridurre i costi di gestione delle attività di indagine e correzione e ottenere il massimo dalla propria famiglia di minacce per la protezione. l'analisi e la risposta automatizzate consentono al team di operazioni di sicurezza di:

1. stabilire se una minaccia richiede un'azione;
2. eseguire (o consigliare) tutte le azioni correttive necessarie;
3. stabilire quali ulteriori indagini dovrebbero essere intraprese;
4. ripetere il processo per altri avvisi, se necessario.

## <a name="the-automated-investigation-process"></a>Il processo di indagine automatizzata

**Avviso** > **incidente** > **indagine automatizzata** > **verdetto** > **azione correttiva**

Un avviso attivato crea un evento Incident che può avviare un'indagine automatizzata. Tale indagine può comportare una o più azioni correttive. In Microsoft 365 Defender, ogni indagine automatizzata correla i segnali tra Microsoft Defender per Identity, Microsoft Defender per endpoint e Defender per Office 365, come riepilogato nella tabella seguente: 

|Entità |Servizi di protezione dalle minacce  |
|---------|---------|
|Dispositivi (detti anche endpoint)     |[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Microsoft Defender per identità](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|Contenuto della posta elettronica (file e messaggi nelle cassette postali)     |[Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

Ogni indagine genera verdetti (*dannosi*, *sospetti* o *non sono state trovate minacce*) per ogni elemento di prova indagato. A seconda del tipo di minaccia e del verdetto risultante, le azioni di correzione si verificano automaticamente o dopo l'approvazione da parte del team di operazioni di sicurezza dell'organizzazione. Le azioni in sospeso e quelle completate sono elencate nel [centro notifiche](mtp-action-center.md).

Durante l'esecuzione di un'indagine, tutti gli altri avvisi correlati che emergono vengono aggiunti all'indagine fino al suo completamento. Se un'entità incriminata viene visualizzata altrove, l'indagine automatizzata amplierà il suo ambito per includere tale entità e verrà eseguito un playbook della sicurezza generale. 

> [!NOTE]
> Non tutti gli avvisi attivano un'analisi automatizzata e non tutti i risultati dell'indagine in azioni di correzione automatica; tutto dipende da come viene configurata l'analisi e la risposta automatizzata per la propria organizzazione. Vedere [Configure Automatic Investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).


## <a name="next-steps"></a>Passaggi successivi

- [Vedere i prerequisiti per l'analisi e la risposta automatizzati in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [Configurare l'analisi e la risposta automatizzate per l'organizzazione](mtp-configure-auto-investigation-response.md)
- [Altre informazioni sul centro notifiche](mtp-action-center.md)
