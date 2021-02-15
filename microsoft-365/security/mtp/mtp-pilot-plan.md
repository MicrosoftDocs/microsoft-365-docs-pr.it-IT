---
title: Pianificazione del progetto pilota di Microsoft 365 Defender
description: Pianificare il progetto pilota di Microsoft 365 Defender con gli stakeholder per gestire le aspettative e garantire un esito positivo.
keywords: Progetto pilota di Microsoft Threat Protection, pianificare un progetto pilota di Microsoft Threat Protection, valutare Microsoft Threat Protection in produzione, progetto pilota di Microsoft Threat Protection, cyber security, minacce persistenti avanzate, sicurezza aziendale, dispositivi, dispositivo, identità, utenti, dati, applicazioni, eventi imprevisti, analisi e correzione automatizzate, ricerca avanzata
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
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 8037b71fc41fb7fb0bdbfc829bad2ece1de6849b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930175"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a>Pianificazione del progetto pilota di Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

|![Pianificazione](../../media/phase-diagrams/1-planning.png)<br/>Pianificazione|[![Preparazione](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)<br/>[Preparazione](prepare-mtpeval.md) | [![Simula attacco](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)<br/>[Simula attacco](mtp-pilot-simulate.md) | [![Chiudi e riepiloga](../../media/phase-diagrams/4-summary.png)](mtp-pilot-close.md)<br/>[Chiudi e riepiloga](mtp-pilot-close.md)|
|--|--|--|--|
|*Sei qui!*| | | |

Al momento è in corso la fase di pianificazione.

Per garantire che il progetto pilota sia un successo, è essenziale pianificare in modo accurato e ottenere le approvazioni dai cointeressati all'inizio. Gli elementi della pianificazione includono l'identificazione dell'ambito, dei casi di utilizzo, dei requisiti e dei criteri di riuscita.

Questa guida illustra come pianificare il progetto pilota. 

>[!IMPORTANT]
>Per ottenere risultati ottimali, seguire le istruzioni pilota il più attentamente possibile.


## <a name="scope"></a>Ambito

L'ambito del progetto pilota determinerà la portata del test, in base all'ambiente e ai metodi di test accettabili. Ecco alcuni ambiti di esempio da considerare:
- Ambiente di sviluppo o test che include endpoint, server, controller di dominio.
- Ambiente di produzione con Microsoft 365, Azure, servizi Active Directory, endpoint e server

>[!NOTE]
>Se non si hanno ancora le licenze complete, è possibile ottenere licenze di valutazione per [valutare Microsoft 365 Defender:](https://aka.ms/mtp-trial-lab) pianificare, preparare, configurare, configurare ed eseguire il progetto pilota. Le parti interessate avranno un ruolo importante nell'agevolare il processo dall'inizio alla fine.

Anche i tipi di sistemi operativi da valutare devono essere definiti in base alla struttura organizzativa. Ciò può includere: [endpoint Mac,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements) [server Linux,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements) [endpoint di Windows 10,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions) [Windows Server 2016.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)

## <a name="use-cases"></a>Casi d'uso

I casi d'uso rappresentano le istruzioni su come lo strumento da testare deve essere utilizzato dagli utenti che lo desiderano. Possono essere formulate come storie utente dal punto di vista di un particolare utente, ad esempio un analista SOC. Ad esempio:
- Come analista SOC, devo visualizzare, correlare, valutare e gestire avvisi ed eventi tra dispositivi, utenti e cassette postali nella rete. [Gestione degli eventi imprevisti]
- Come analista SOC, devo avere lo strumento e il processo per analizzare e rispondere automaticamente a eventi dannosi nella mia rete. [IR automatico]
- Come analista SOC, devo cercare i dati del mio ambiente per trovare minacce note e potenziali e attività sospette. [Ricerca avanzata]

Tenere presente che questi casi d'uso devono essere creati all'interno dei parametri dell'ambito definito. Se, ad esempio, l'ambito dei test non include una valutazione di strumenti come Microsoft Cloud App Security, non è consigliabile creare casi che si basano su questo come origine dati.

## <a name="requirements"></a>Requisiti

Dall'elenco dei casi d'uso puoi iniziare a creare i requisiti. I requisiti includono le funzionalità che uno strumento deve avere per soddisfare i casi d'uso. Questi requisiti possono essere suddivisi in categorie quali la configurazione e la manutenzione, il supporto per le integrazioni e i requisiti specifici delle funzionalità, ad esempio la possibilità di cercare e la possibilità di creare avvisi personalizzati.

## <a name="test-plan"></a>Piano di testing

A seconda dei requisiti, possono essere appropriati diversi metodi di test. Ad esempio, se il requisito è quello di valutare l'efficacia della correzione automatica, il piano di test deve includere passaggi per generare i comportamenti che attiverebbero un'azione di correzione automatica in Microsoft 365 Defender. Se il requisito è quello di rilevare un particolare comportamento o attacco, il test potrebbe richiedere più passaggi. Il punto è disporre di un piano da testare in modo accurato in base alle proprie esigenze.

## <a name="success-criteria"></a>Criteri di successo

I criteri di successo sono in definitiva l'insieme di barre da misurare rispetto a ciò che si sta testando. Se si sta testando Microsoft 365 Defender (o qualsiasi altra tecnologia del caso) rispetto ad altri strumenti o da solo, devono essere presenti alcuni criteri quantificabili per determinare il valore fornito dallo strumento. In base all'ambito, ai requisiti e al piano di testing, i criteri di esito positivo determineranno la modalità di valutazione del test. Questo valore deve essere inferiore a un passaggio o a un errore e più di un punteggio ponderato in base alle tue esigenze. Ad esempio, per avere esito positivo, uno strumento potrebbe dover segnare un punteggio superiore all'80% in alcune aree critiche identificate.

## <a name="scorecard"></a>Scorecard

Un modo per riunire tutti gli elementi del piano può essere la creazione di una scorecard. Di seguito è riportata una scorecard di esempio:

| Use case | Requisiti | Requisiti di configurazione | Piano di testing | Risultato previsto | Stato test | Punteggio | Note |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|Gestione degli incidenti|- Microsoft 365 Defender  </br></br>- Microsoft Defender for Identity </br></br>- Microsoft Defender per endpoint </br></br>- Microsoft Cloud App Security (facoltativo)|Per informazioni [dettagliate,](https://aka.ms/mtp-trial-lab) vedere i prerequisiti per la preparazione, la configurazione e la configurazione |[Simula attacco](mtp-pilot-simulate.md) <br></br>[Analizzare l'evento imprevisto](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |Gli investigatori possono comprendere l'ambito e l'impatto dell'incidente e gestire l'incidente||||
|AutoIR|- Microsoft 365 Defender </br></br>- Microsoft Defender for Identity </br></br>- Microsoft Defender per endpoint |Per informazioni [dettagliate,](https://aka.ms/mtp-trial-lab) vedere i prerequisiti per la preparazione, la configurazione e la configurazione <br>Abilitare AutoIR  |[Simula attacco](mtp-pilot-simulate.md) <br></br>[Indagine automatizzata](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#automated-investigation-and-remediation) |Gli avvisi e gli eventi imprevisti vengono corretti automaticamente da Microsoft 365 Defender||||
|Ricerca avanzata|- Microsoft 365 Defender </br></br>- Microsoft Defender per endpoint </br></br>-Microsoft Defender per Office 365 |Per informazioni [dettagliate,](https://aka.ms/mtp-trial-lab) vedere i prerequisiti per la preparazione, la configurazione e la configurazione|[Scenario di ricerca avanzata](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#advanced-hunting-scenario) |Gli investigatori possono trovare i dati tramite la ricerca avanzata, la ricerca pivot nelle entità influenzate e la creazione di rilevamenti personalizzati||||



## <a name="next-step"></a>Passaggio successivo
|![Fase di preparazione](../../media/mtp/prep.png) <br>[Fase di preparazione](prepare-mtpeval.md) | Preparare l'ambiente pilota di Microsoft 365 Defender
|:-------|:-----|
