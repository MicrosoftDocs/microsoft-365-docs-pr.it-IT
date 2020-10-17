---
title: Eseguire il progetto pilota di Microsoft Threat Protection
description: Eseguire il progetto pilota Microsoft Threat Protection in produzione per determinare in modo efficace i vantaggi e l'adozione di Microsoft Threat Protection (MTP).
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
ms.openlocfilehash: f49f1afe5461a4f2eff0a3049f1d14d1892f70ce
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477021"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a>Eseguire il progetto pilota di Microsoft Threat Protection 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft Threat Protection

Per determinare in modo efficace il vantaggio e l'adozione di Microsoft Threat Protection (MTP), è possibile eseguire un progetto pilota. Prima di abilitare Microsoft Threat Protection nell'ambiente di produzione e iniziare i casi di utilizzo, è preferibile pianificare la determinazione delle attività da eseguire per il progetto pilota e impostare i criteri di esito positivo. 


## <a name="how-to-use-this-pilot-playbook"></a>Come usare questo pilota PlayBook

In questa guida viene fornita una panoramica di Microsoft Threat Protection e istruzioni dettagliate su come configurare il progetto pilota. 

Microsoft Threat Protection è una famiglia di prodotti di difesa aziendale unificata che coordina in modo nativo la protezione, il rilevamento, la prevenzione, l'analisi e la risposta tra endpoint, identità, posta elettronica e applicazioni per garantire la protezione integrata da attacchi sofisticati. In questo modo, combinando e orchestrando le funzionalità seguenti in una singola soluzione di sicurezza:
  - Microsoft Defender per endpoint, il nuovo nome di Microsoft Defender Advanced Threat Protection (Endpoints)
  - Microsoft Defender per Office 365, il nuovo nome per Office 365 ATP (posta elettronica) 
  - Microsoft Defender per Identity, il nuovo nome per Azure ATP (Identity) 
  - Sicurezza delle app di Microsoft Cloud (app)

![Image of_Microsoft soluzione di protezione dalle minacce per gli utenti, la protezione avanzata dalle minacce di Azure, per gli endpoint Microsoft Defender Advanced Threat Protection, per le app Cloud, Microsoft cloud app Security e per i dati, Office 365 Advanced Threat Protection  ](../../media/mtp/m365pillars.png)

Con la soluzione integrata di Microsoft Threat Protection, i professionisti della sicurezza possono unire i segnali di minaccia che Microsoft Defender Advanced Threat Protection, Office 365 ATP, Azure ATP e Microsoft cloud app Security ricevono e determinare l'ambito e l'impatto completo della minaccia, come è entrata nell'ambiente, cosa ne è interessata e come sta influenzando l'organizzazione. Microsoft Threat Protection interviene automaticamente per impedire o arrestare l'attacco e la correzione automatica delle cassette postali, degli endpoint e delle identità degli utenti. Per informazioni dettagliate, vedere [Microsoft Threat Protection Overview](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) .

![Fasi di esecuzione di un pilota di Microsoft Threat Protection](../../media/pilotphases.png)

La sequenza temporale di esempio seguente varia a seconda dell'utilizzo delle risorse corrette nell'ambiente in uso. Alcuni rilevamenti e flussi di lavoro potrebbero richiedere più tempo di apprendimento rispetto agli altri.

![Sequenza temporale di esempio per l'esecuzione di un pilota di Microsoft Threat Protection](../../media/pilotimeline.png)

>[!IMPORTANT]
>Per ottenere risultati ottimali, seguire le istruzioni pilota il più fedelmente possibile.


### <a name="pilot-playbook-phases"></a>Fasi pilota del PlayBook 

Sono disponibili quattro fasi per l'esecuzione di un pilota di Microsoft Threat Protection:

|Fase | Descrizione | 
|:-------|:-----|
| ![Pianificazione](../../media/mtp/plan.png)<br>[Pianificazione](mtp-pilot-plan.md)| Informazioni su ciò che è necessario prendere in considerazione prima di eseguire il progetto pilota di Microsoft Threat Protection: <br><br>-Scope <br> -Use Cases <br>- Requisiti <br>-Piano di testing <br> -Criteri di esito positivo <br> -Scorecard 
| ![Preparazione](../../media/mtp/prep.png) <br>[Preparazione](mtp-evaluation.md)|  Accedere al centro sicurezza Microsoft 365 per configurare l'ambiente pilota di Microsoft Threat Protection. Verrà visualizzata la guida per:<br><br>-Identificare le parti interessate e cercare l'accesso per il pilota <br> -Considerazioni sull'ambiente <br>-Access <br>-Configurazione di Azure Active Directory <br> -Ordine di configurazione <br> -Iscriversi alla versione di valutazione di Microsoft 365 E5 <br> -Configurare il dominio <br>-Assegnare licenze Microsoft 365 E5 <br> -Completare l'installazione guidata nel portale|
| ![Simulazione di attacco](../../media/mtp/run-sim.png) <br>[Simulazione di attacco](mtp-pilot-simulate.md) | Per simulare un attacco, è possibile eseguire le operazioni seguenti:<br><br>-Verificare i requisiti dell'ambiente di testing <br>-Eseguire la simulazione <br>-Indagare su un evento imprevisto <br>-risolvere l'evento non consentita 
| ![Chiusura e riepilogo](../../media/mtp/close.png) <br>[Chiusura e riepilogo](mtp-pilot-close.md) | Dopo aver raggiunto la fine del processo, si verrà guidati a:<br><br>-Passare attraverso l'output finale<br>-Presentare l'output alle parti interessate <br>-Fornire commenti e suggerimenti <br>-Eseguire i passaggi successivi 

## <a name="next-step"></a>Passaggio successivo
|![Fase di pianificazione](../../media/mtp/plan.png) <br>[Fase di pianificazione](mtp-pilot-plan.md) | Pianificare il progetto pilota di Microsoft Threat Protection 
|:-------|:-----|
