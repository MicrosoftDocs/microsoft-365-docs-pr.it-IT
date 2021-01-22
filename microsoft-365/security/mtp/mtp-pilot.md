---
title: Eseguire il progetto pilota di Microsoft 365 Defender
description: Eseguire il progetto pilota di Microsoft 365 Defender in produzione per determinare in modo efficace i vantaggi e l'adozione di Microsoft 365 Defender.
keywords: Progetto pilota di Microsoft Threat Protection, eseguire un progetto pilota di Microsoft Threat Protection, valutare Microsoft Threat Protection in produzione, progetto pilota di Microsoft Threat Protection, cyber security, minacce persistenti avanzate, sicurezza aziendale, dispositivi, dispositivo, identità, utenti, dati, applicazioni, eventi imprevisti, analisi e correzione automatizzate, ricerca avanzata
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 9c0635058539e464a76f1720f041c205a05fa9b2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933031"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>Eseguire il progetto pilota di Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender


Questa guida consente di eseguire un progetto pilota fornendo puntatori per garantire un piano ben strutturato, guidando l'utente attraverso l'uso della funzionalità di simulazione degli attacchi e infine concludendo il progetto pilota con le principali attività da eseguire per riflettere e documentare i risultati.

![Fasi dell'esecuzione di un progetto pilota di Microsoft 365 Defender](../../media/pilotphases.png)


L'esecuzione di un progetto pilota consente di determinare in modo efficace i vantaggi dell'adozione di Microsoft 365 Defender. Prima di abilitare Microsoft 365 Defender nell'ambiente di produzione e iniziare i casi d'uso, è meglio pianificare di determinare le attività da eseguire per il progetto pilota e impostare i criteri di successo. 


## <a name="how-to-use-this-pilot-playbook"></a>Come usare questo playbook pilota

Questa guida fornisce una panoramica di Microsoft 365 Defender e istruzioni dettagliate su come configurare il progetto pilota. 

Microsoft 365 Defender è una famiglia di prodotti di difesa aziendale pre e post-violazione unificata che coordina in modo nativo la protezione, il rilevamento, la prevenzione, l'indagine e la risposta tra endpoint, identità, posta elettronica e applicazioni per fornire protezione integrata da attacchi sofisticati. A tale scopo, combinando e orchestrando le funzionalità seguenti in un'unica soluzione di sicurezza:
  - Microsoft Defender for Endpoint, il nuovo nome per Microsoft Defender Advanced Threat Protection (endpoint)
  - Microsoft Defender per Office 365, il nuovo nome per Office 365 ATP (posta elettronica) 
  - Microsoft Defender for Identity, il nuovo nome per Azure ATP (identità) 
  - Microsoft Cloud App Security (app)

![Image of_Microsoft 365 Defender solution for users, Microsoft Defender for Identity, for endpoints Microsoft Defender for Endpoint, for cloud apps, Microsoft Cloud App Security, and for data, Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

Con la soluzione Microsoft 365 Defender integrata, i professionisti della sicurezza possono unire i segnali di minaccia ricevuti da Microsoft Defender for Endpoint, Microsoft Defender per Office 365, Microsoft Defender for Identity e Microsoft Cloud App Security e determinare l'ambito completo e l'impatto della minaccia, come è entrato nell'ambiente, cosa ne è interessato e in che modo influisce attualmente sull'organizzazione. Microsoft 365 Defender adotta un'azione automatica per impedire o arrestare l'attacco e auto-sanare le cassette postali, gli endpoint e le identità degli utenti interessati. Per informazioni dettagliate, vedere la panoramica [di Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)



La sequenza temporale di esempio seguente varia in base alla disponibilità delle risorse giuste nell'ambiente. Alcuni rilevamenti e flussi di lavoro potrebbero richiedere più tempo di apprendimento rispetto agli altri.

![Sequenza temporale di esempio nell'esecuzione di un progetto pilota di Microsoft 365 Defender](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>Per ottenere risultati ottimali, seguire le istruzioni pilota il più attentamente possibile.


### <a name="pilot-playbook-phases"></a>Fasi del playbook pilota 

Esistono quattro fasi nell'esecuzione di un progetto pilota di Microsoft 365 Defender:

|Fase | Descrizione | 
|:-------|:-----|
| [Pianificazione](mtp-pilot-plan.md)<br> ~ 1 giorno| Informazioni su cosa è necessario considerare prima di eseguire il progetto pilota di Microsoft 365 Defender: <br><br>- Ambito <br> - Casi d'uso <br>- Requisiti <br>- Piano di test <br> - Criteri di successo <br> - Scorecard 
| [Preparazione](mtp-evaluation.md) <br>~2 giorni|  Accedere al Centro sicurezza Microsoft 365 per configurare l'ambiente pilota di Microsoft 365 Defender. Verrà indicato come:<br><br>- Identificare le parti interessate e richiedere la disconnessione per il progetto pilota <br> - Considerazioni sull'ambiente <br>- Access <br>- Configurazione di Azure Active Directory <br> - Ordine di configurazione <br> - Iscriversi alla versione di valutazione di Microsoft 365 E5 <br> - Configurare il dominio <br>- Assegnare le licenze di Microsoft 365 E5 <br> - Completare la configurazione guidata nel portale|
| [Simulazione degli attacchi](mtp-pilot-simulate.md) <br>~2 giorni| Per simulare un attacco, verrà indicato come:<br><br>- Verificare i requisiti dell'ambiente di testing <br>- Eseguire la simulazione <br>- Analizzare un evento imprevisto <br>- Risolvere l'evento imprevisto 
| [Chiusura e riepilogo](mtp-pilot-close.md) <br>~ 1 giorno| Una volta raggiunta la fine del processo, si verrà guidati a:<br><br>- Passare attraverso l'output finale<br>- Presentare l'output alle parti interessate <br>- Inviare commenti e suggerimenti <br>- Eseguire i passaggi successivi 

## <a name="next-step"></a>Passaggio successivo
|[Fase di pianificazione](mtp-pilot-plan.md) | Pianificare il progetto pilota di Microsoft 365 Defender 
|:-------|:-----|
