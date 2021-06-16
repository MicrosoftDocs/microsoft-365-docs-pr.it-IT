---
title: Eseguire il progetto pilota Microsoft 365 Defender
description: Esegui il progetto pilota Microsoft 365 Defender nell'ambiente di produzione per determinare in modo efficace i vantaggi e l'adozione di Microsoft 365 Defender.
keywords: Microsoft 365 Defender pilot, eseguire un progetto pilota Microsoft 365 Defender, valutare Microsoft 365 Defender in produzione, progetto pilota di Microsoft 365 Defender, cyber security, minaccia persistente avanzata, sicurezza aziendale, dispositivi, dispositivo, identità, utenti, dati, applicazioni, incidenti, indagine e correzione automatizzate, ricerca avanzata
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
ms.openlocfilehash: 3219b329c53c32e02cd29acdd41a48cd93b2e8bb
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930512"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>Eseguire il progetto pilota Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender


Questa guida consente di eseguire un progetto pilota fornendo puntatori per garantire un piano ben strutturato, guidando l'utente attraverso l'utilizzo della funzionalità di simulazione degli attacchi e infine concludendo il progetto pilota con le principali attività da eseguire per riflettere e documentare i risultati.

![Fasi dell'esecuzione di un Microsoft 365 defender pilota](../../media/pilotphases.png)


L'esecuzione di un progetto pilota consente di determinare in modo efficace i vantaggi dell'adozione di Microsoft 365 Defender. Prima di abilitare Microsoft 365 Defender nell'ambiente di produzione e avviare i casi d'uso, è meglio pianificare le attività da eseguire per il progetto pilota e impostare i criteri di esito positivo. 


## <a name="how-to-use-this-pilot-playbook"></a>Come usare questo playbook pilota

Questa guida fornisce una panoramica di Microsoft 365 Defender e istruzioni dettagliate su come configurare il progetto pilota. 

Microsoft 365 Defender è una suite di difesa aziendale unificata pre e post-violazione che coordina in modo nativo protezione, rilevamento, prevenzione, indagine e risposta tra endpoint, identità, posta elettronica e applicazioni per fornire protezione integrata da attacchi sofisticati. A tale scopo, combinando e orchestrando le funzionalità seguenti in un'unica soluzione di sicurezza:
  - Microsoft Defender per endpoint (endpoint)
  - Microsoft Defender per Office 365 (posta elettronica) 
  - Microsoft Defender for Identity (identità) 
  - Microsoft Cloud App Security (app)

![Immagine of_Microsoft 365 Defender per gli utenti, Microsoft Defender for Identity, per gli endpoint Microsoft Defender for Endpoint, per le app cloud, Microsoft Cloud App Security e per i dati, Microsoft Defender per Office 365](../../media/mtp/m365pillars.png)

Con la soluzione integrata Microsoft 365 Defender, i professionisti della sicurezza possono unire i segnali di minaccia ricevuti da Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity e Microsoft Cloud App Security e determinare l'ambito completo e l'impatto della minaccia, il modo in cui è entrata nell'ambiente, il suo impatto e il suo impatto sull'organizzazione. Microsoft 365 Defender adotta un'azione automatica per impedire o arrestare l'attacco e auto-sanare le cassette postali, gli endpoint e le identità degli utenti interessati. Vedi la [panoramica Microsoft 365 Defender per](microsoft-365-defender.md) i dettagli.



La sequenza temporale di esempio seguente varia a seconda della disponibilità delle risorse giuste nell'ambiente. Alcuni rilevamenti e flussi di lavoro potrebbero richiedere più tempo di apprendimento rispetto agli altri.

![Sequenza temporale di esempio nell'esecuzione di un Microsoft 365 Defender pilota](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>Per ottenere risultati ottimali, seguire le istruzioni pilota il più possibile.


### <a name="pilot-playbook-phases"></a>Fasi del playbook pilota 

L'esecuzione di un progetto pilota di Microsoft 365 Defender è Microsoft 365 quattro fasi:

|Fase | Descrizione | 
|:-------|:-----|
| [Pianificazione](m365d-pilot-plan.md)<br> ~ 1 giorno| Scopri cosa devi considerare prima di eseguire il progetto pilota Microsoft 365 Defender: <br><br>- Ambito <br> - Casi d'uso <br>- Requisiti <br>- Piano di test <br> - Criteri di esito positivo <br> - Scorecard 
| [Preparazione](m365d-evaluation.md) <br>~2 giorni|  Accedere Microsoft 365 Security Center per configurare l'ambiente pilota Microsoft 365 Defender. Sarai guidato a:<br><br>- Identificare le parti interessate e richiedere la disconnessione per il progetto pilota <br> - Considerazioni sull'ambiente <br>- Accesso <br>- Azure Active Directory configurazione <br> - Ordine di configurazione <br> - Iscriversi per la Microsoft 365 E5 prova <br> - Configurare il dominio <br>- Assegnare Microsoft 365 E5 licenze <br> - Completare la configurazione guidata nel portale|
| [Simulazione di attacco](m365d-pilot-simulate.md) <br>~2 giorni| Per simulare un attacco, verrà indicato come:<br><br>- Verificare i requisiti dell'ambiente di testing <br>- Eseguire la simulazione <br>- Analizzare un evento imprevisto <br>- Risolvere l'evento imprevisto 
| [Chiusura e riepilogo](m365d-pilot-close.md) <br>~ 1 giorno| Una volta raggiunta la fine del processo, si verrà guidati a:<br><br>- Passare all'output finale<br>- Presentare l'output ai cointeressati <br>- Fornire feedback <br>- Eseguire i passaggi successivi 

## <a name="next-step"></a>Passaggio successivo
|[Fase di pianificazione](m365d-pilot-plan.md) | Pianificare il progetto pilota Microsoft 365 Defender 
|:-------|:-----|
