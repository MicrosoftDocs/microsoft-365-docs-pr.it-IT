---
title: Eseguire il progetto pilota Microsoft 365 Defender progetto
description: Eseguire il progetto Microsoft 365 Defender progetto pilota nell'ambiente di produzione per determinare in modo efficace i vantaggi e l'adozione di Microsoft 365 Defender.
keywords: Microsoft 365 Defender pilota, eseguire un progetto pilota Microsoft 365 Defender, valutare Microsoft 365 Defender in produzione, progetto pilota Microsoft 365 Defender, sicurezza informatica, minaccia persistente avanzata, sicurezza aziendale, dispositivi, dispositivo, identità, utenti, dati, applicazioni, incidenti, analisi e correzione automatizzate, ricerca avanzata
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: fd84ef93d679be6e1e42f823dcac1f2d5181f1e9
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2021
ms.locfileid: "53458418"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>Eseguire il progetto pilota Microsoft 365 Defender progetto 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender


Questa guida consente di eseguire un progetto pilota fornendo puntatori per garantire un piano ben strutturato, guidando l'utente attraverso l'utilizzo della funzionalità di simulazione degli attacchi e infine concludendo il progetto pilota con le principali attività da eseguire per riflettere e documentare i risultati.

![Fasi dell'esecuzione di un Microsoft 365 Defender pilota](../../media/pilotphases.png)


L'esecuzione di un progetto pilota consente di determinare in modo efficace i vantaggi dell'adozione di Microsoft 365 Defender. Prima di Microsoft 365 Defender nell'ambiente di produzione e avviare i casi di utilizzo, è meglio pianificare le attività da eseguire per il progetto pilota e impostare i criteri di esito positivo. 


## <a name="how-to-use-this-pilot-playbook"></a>Come usare questo playbook pilota

Questa guida fornisce una panoramica Microsoft 365 Defender istruzioni dettagliate su come configurare il progetto pilota. 

Microsoft 365 Defender è una suite di difesa aziendale unificata pre e post-violazione che coordina in modo nativo protezione, rilevamento, prevenzione, indagine e risposta tra endpoint, identità, posta elettronica e applicazioni per fornire una protezione integrata da attacchi sofisticati. A tale scopo, combinando e orchestrando le funzionalità seguenti in un'unica soluzione di sicurezza:

- Microsoft Defender per endpoint (endpoint)
- Microsoft Defender per Office 365 (posta elettronica)
- Microsoft Defender for Identity (identità)
- Microsoft Cloud App Security (app)

![Immagine of_Microsoft 365 Defender per gli utenti, Microsoft Defender for Identity, per gli endpoint Microsoft Defender for Endpoint, per le app cloud, Microsoft Cloud App Security e per i dati, Microsoft Defender per Office 365](../../media/mtp/m365pillars.png)

Con la soluzione Microsoft 365 Defender integrata, i professionisti della sicurezza possono unire i segnali di minaccia ricevuti da Microsoft Defender for Endpoint, Microsoft Defender per Office 365, Microsoft Defender for Identity e Microsoft Cloud App Security e determinare l'ambito completo e l'impatto della minaccia, il modo in cui è entrata nell'ambiente, le conseguenze e il suo impatto sull'organizzazione. Microsoft 365 Defender azioni automatiche per impedire o arrestare l'attacco e auto-sanare le cassette postali, gli endpoint e le identità degli utenti interessati. Per informazioni [dettagliate, Microsoft 365 Defender panoramica dei](microsoft-365-defender.md) dati.

La sequenza temporale di esempio seguente varia a seconda della disponibilità delle risorse giuste nell'ambiente. Alcuni rilevamenti e flussi di lavoro potrebbero richiedere più tempo di apprendimento rispetto agli altri.

![Sequenza temporale di esempio nell'esecuzione di Microsoft 365 Defender pilota](../../media/phase-diagrams/pilot-phases.png)

> [!IMPORTANT]
> Per ottenere risultati ottimali, seguire le istruzioni pilota il più possibile.

### <a name="pilot-playbook-phases"></a>Fasi del playbook pilota

L'esecuzione di un progetto pilota Microsoft 365 Defender quattro fasi:

|Fase | Descrizione |
|:-------|:-----|
| [Pianificazione](m365d-pilot-plan.md)<br> ~ 1 giorno| Informazioni su cosa è necessario prendere in considerazione prima di eseguire il Microsoft 365 Defender progetto pilota: <br><br>- Ambito <br> - Casi d'uso <br>- Requisiti <br>- Piano di test <br> - Criteri di esito positivo <br> - Scorecard 
| [Preparazione](m365d-evaluation.md) <br>~2 giorni|  Accedere Microsoft 365 Security Center per configurare l'Microsoft 365 Defender pilota. Sarai guidato a:<br><br>- Identificare le parti interessate e richiedere la disconnessione per il progetto pilota <br> - Considerazioni sull'ambiente <br>- Accesso <br>- Azure Active Directory configurazione <br> - Ordine di configurazione <br> - Iscriversi per la Microsoft 365 E5 prova <br> - Configurare il dominio <br>- Assegnare Microsoft 365 E5 licenze <br> - Completare la configurazione guidata nel portale|
| [Simulazione di attacco](m365d-pilot-simulate.md) <br>~2 giorni| Per simulare un attacco, verrà indicato come:<br><br>- Verificare i requisiti dell'ambiente di testing <br>- Eseguire la simulazione <br>- Analizzare un evento imprevisto <br>- Risolvere l'evento imprevisto 
| [Chiusura e riepilogo](m365d-pilot-close.md) <br>~ 1 giorno| Una volta raggiunta la fine del processo, si verrà guidati a:<br><br>- Passare all'output finale<br>- Presentare l'output ai cointeressati <br>- Fornire feedback <br>- Eseguire i passaggi successivi 

## <a name="next-step"></a>Passaggio successivo

|[Fase di pianificazione](m365d-pilot-plan.md) | Pianificare il Microsoft 365 Defender progetto pilota 
|:-------|:-----|
