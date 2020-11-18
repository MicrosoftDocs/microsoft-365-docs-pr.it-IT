---
title: Eseguire il progetto pilota Microsoft 365 Defender
description: Eseguire il progetto pilota Microsoft 365 Defender in produzione per determinare in modo efficace i vantaggi e l'adozione di Microsoft 365 Defender.
keywords: Pilota di Microsoft Threat Protection, eseguire il progetto pilota di Microsoft Threat Protection, valutare Microsoft Threat Protection in produzione, progetto pilota di Microsoft Threat Protection, sicurezza cibernetica, Advanced Persistent Threat, sicurezza dell'organizzazione, dispositivi, dispositivo, identità, utenti, dati, applicazioni, incidenti, analisi automatizzata e correzione, ricerca avanzata
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 50f334a055a5bd974f9ea1f39c8fa38d44be9c26
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131289"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>Eseguire il progetto pilota Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

Per determinare in modo efficace il vantaggio e l'adozione di Microsoft 365 Defender, è possibile eseguire un progetto pilota. Prima di abilitare Microsoft 365 Defender nell'ambiente di produzione e iniziare i casi di utilizzo, è preferibile pianificare la determinazione delle attività da eseguire per il progetto pilota e impostare i criteri di esito positivo. 


## <a name="how-to-use-this-pilot-playbook"></a>Come usare questo pilota PlayBook

In questa guida viene fornita una panoramica di Microsoft 365 Defender e istruzioni dettagliate su come configurare il progetto pilota. 

Microsoft 365 Defender è una famiglia di prodotti di difesa aziendale unificata che coordina in modo nativo la protezione, il rilevamento, la prevenzione, l'analisi e la risposta tra endpoint, identità, posta elettronica e applicazioni per garantire la protezione integrata da attacchi sofisticati. In questo modo, combinando e orchestrando le funzionalità seguenti in una singola soluzione di sicurezza:
  - Microsoft Defender per endpoint, il nuovo nome di Microsoft Defender Advanced Threat Protection (Endpoints)
  - Microsoft Defender per Office 365, il nuovo nome per Office 365 ATP (posta elettronica) 
  - Microsoft Defender per Identity, il nuovo nome per Azure ATP (Identity) 
  - Sicurezza delle app di Microsoft Cloud (app)

![Image of_Microsoft soluzione Defender di 365 per gli utenti, Microsoft Defender for Identity, per gli endpoint Microsoft Defender per endpoint, per le app Cloud, per la sicurezza di Microsoft cloud app e per i dati, Microsoft Defender per Office 365](../../media/mtp/m365pillars.png)

Con la soluzione Microsoft 365 Defender integrata, i professionisti della sicurezza possono unire i segnali di minaccia che Microsoft Defender per endpoint, Microsoft Defender per Office 365, Microsoft Defender per Identity e Microsoft cloud app Security ricevono e determinare l'ambito e l'impatto completo della minaccia, il modo in cui è entrata nell'ambiente, le conseguenze e la modalità di impatto dell'organizzazione. Microsoft 365 Defender esegue un'azione automatica per impedire o arrestare le cassette postali, gli endpoint e le identità degli utenti coinvolti. Per informazioni dettagliate, vedere [Microsoft 365 Defender Overview](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) .

![Fasi di esecuzione di un pilota Microsoft 365 Defender](../../media/pilotphases.png)

La sequenza temporale di esempio seguente varia a seconda dell'utilizzo delle risorse corrette nell'ambiente in uso. Alcuni rilevamenti e flussi di lavoro potrebbero richiedere più tempo di apprendimento rispetto agli altri.

![Sequenza temporale di esempio per l'esecuzione di un pilota Microsoft 365 Defender](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>Per ottenere risultati ottimali, seguire le istruzioni pilota il più fedelmente possibile.


### <a name="pilot-playbook-phases"></a>Fasi pilota del PlayBook 

Sono disponibili quattro fasi per l'esecuzione di un pilota Microsoft 365 Defender:

|Fase | Descrizione | 
|:-------|:-----|
| [Pianificazione](mtp-pilot-plan.md)<br> ~ 1 giorno| Informazioni su ciò che è necessario prendere in considerazione prima di eseguire il progetto pilota Microsoft 365 Defender: <br><br>-Scope <br> -Use Cases <br>- Requisiti <br>-Piano di testing <br> -Criteri di esito positivo <br> -Scorecard 
| [Preparazione](mtp-evaluation.md) <br>~ 2 giorni|  Accedere al centro sicurezza Microsoft 365 per configurare l'ambiente pilota Microsoft 365 Defender. Verrà visualizzata la guida per:<br><br>-Identificare le parti interessate e cercare l'accesso per il pilota <br> -Considerazioni sull'ambiente <br>-Access <br>-Configurazione di Azure Active Directory <br> -Ordine di configurazione <br> -Iscriversi alla versione di valutazione di Microsoft 365 E5 <br> -Configurare il dominio <br>-Assegnare licenze Microsoft 365 E5 <br> -Completare l'installazione guidata nel portale|
| [Simulazione di attacco](mtp-pilot-simulate.md) <br>~ 2 giorni| Per simulare un attacco, è possibile eseguire le operazioni seguenti:<br><br>-Verificare i requisiti dell'ambiente di testing <br>-Eseguire la simulazione <br>-Indagare su un evento imprevisto <br>-risolvere l'evento non consentita 
| [Chiusura e riepilogo](mtp-pilot-close.md) <br>~ 1 giorno| Dopo aver raggiunto la fine del processo, si verrà guidati a:<br><br>-Passare attraverso l'output finale<br>-Presentare l'output alle parti interessate <br>-Fornire commenti e suggerimenti <br>-Eseguire i passaggi successivi 

## <a name="next-step"></a>Passaggio successivo
|[Fase di pianificazione](mtp-pilot-plan.md) | Pianificare il progetto pilota Microsoft 365 Defender 
|:-------|:-----|
