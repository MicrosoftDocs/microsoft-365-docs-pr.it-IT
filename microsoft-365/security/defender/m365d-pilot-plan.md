---
title: Pianificazione del progetto pilota Microsoft 365 Defender progetto
description: Pianificare il progetto pilota Microsoft 365 Defender con gli stakeholder per gestire le aspettative e garantire risultati positivi.
keywords: Microsoft 365 Defender progetto pilota, pianificare un progetto pilota Microsoft 365 Defender, valutare Microsoft 365 Defender in produzione, progetto pilota Microsoft 365 Defender, cyber security, minaccia persistente avanzata, sicurezza aziendale, dispositivi, dispositivo, identità, utenti, dati, applicazioni, incidenti, analisi e correzione automatizzate, ricerca avanzata
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
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6a52df8035ce6f84770a2d06c3b8c127e426622e
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53285998"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a>Pianificazione del progetto pilota Microsoft 365 Defender progetto 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

|![Pianificazione](../../media/phase-diagrams/1-planning.png)<br/>Pianificazione|[![Preparazione](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)<br/>[Preparazione](prepare-m365d-eval.md) | [![Simula attacco](../../media/phase-diagrams/3-simluate.png)](m365d-pilot-simulate.md)<br/>[Simula attacco](m365d-pilot-simulate.md) | [![Chiudi e riepiloga](../../media/phase-diagrams/4-summary.png)](m365d-pilot-close.md)<br/>[Chiudi e riepiloga](m365d-pilot-close.md)|
|--|--|--|--|
|*Sei qui!*| | | |

Al momento è in corso la fase di pianificazione.

Per garantire che il progetto pilota sia un successo, è essenziale pianificare a fondo e ottenere le approvazioni degli stakeholder all'inizio. Gli elementi della pianificazione includono l'identificazione dell'ambito, dei casi di utilizzo, dei requisiti e dei criteri di esito positivo.

Questa guida illustra come pianificare il progetto pilota. 

>[!IMPORTANT]
>Per ottenere risultati ottimali, seguire le istruzioni pilota il più possibile.


## <a name="scope"></a>Ambito

L'ambito del progetto pilota determinerà l'ampia portata del test, in base all'ambiente e ai metodi di test accettabili. Ecco alcuni ambiti di esempio da considerare:

- Ambiente di sviluppo o test che include endpoint, server, controller di dominio.
- Ambiente di produzione con Microsoft 365, Azure, servizi Active Directory, endpoint e server

>[!NOTE]
>Se non si dispone ancora delle licenze complete, [](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) è possibile ottenere licenze di valutazione per valutare Microsoft 365 Defender: pianificare, preparare, configurare, configurare ed eseguire il progetto pilota. I cointeressati avranno un ruolo importante nell'agevolare il processo dall'inizio alla fine.

Anche i tipi di sistemi operativi da valutare devono essere definiti in base alla struttura organizzativa. Ciò può includere: [endpoint Mac,](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements) [server Linux,](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements) [Windows 10 endpoint](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).

## <a name="use-cases"></a>Casi d'uso

I casi d'uso rappresentano le istruzioni relative al modo in cui lo strumento da testare deve essere utilizzato dagli utenti che lo desiderano. Queste possono essere formulate come storie utente dal punto di vista di una determinata persona, ad esempio un analista SOC. Ad esempio:

- Come analista SOC, devo visualizzare, correlare, valutare e gestire avvisi ed eventi tra dispositivi, utenti e cassette postali nella mia rete. [Gestione eventi imprevisti]
- Come analista SOC, devo avere lo strumento e il processo per analizzare e rispondere automaticamente a eventi dannosi nella mia rete. [Auto IR]
- Come analista SOC, devo cercare i dati dal mio ambiente per trovare minacce note e potenziali e attività sospette. [Ricerca avanzata]

Tenere presente che questi casi di utilizzo devono essere creati all'interno dei parametri dell'ambito definito. Se, ad esempio, l'ambito dei test non include una valutazione di strumenti come Microsoft Cloud App Security, non è consigliabile creare casi d'uso che si basano su questo come origine dati.

## <a name="requirements"></a>Requisiti

Dall'elenco dei casi di utilizzo, è possibile iniziare a creare i requisiti. I requisiti includono funzionalità che uno strumento deve avere per soddisfare i casi d'uso. Questi requisiti possono essere suddivisi in categorie quali la configurazione e la manutenzione, il supporto per le integrazioni e i requisiti specifici delle funzionalità, ad esempio la capacità di ricerca e la possibilità di creare avvisi personalizzati.

## <a name="test-plan"></a>Piano di testing

A seconda dei requisiti, possono essere appropriati diversi metodi di test. Ad esempio, se il requisito è valutare l'efficacia della correzione automatica, il piano di test deve includere passaggi per generare i comportamenti che attiverebbero un'azione di correzione automatica all'interno di Microsoft 365 Defender. Se il requisito è rilevare un comportamento o un attacco specifico, il test potrebbe richiedere più passaggi. Il punto è disporre di un piano per testare in modo accurato in base ai propri requisiti.

## <a name="success-criteria"></a>Criteri di esito positivo

I criteri di esito positivo sono in definitiva l'insieme di barre da misurare rispetto a ciò che si sta testando. Se si sta testando Microsoft 365 Defender (o qualsiasi altra tecnologia in questione) rispetto ad altri strumenti o da solo, devono essere disponibili alcuni criteri quantificabili per determinare il valore fornito dallo strumento. In base all'ambito, ai requisiti e al piano di testing, i criteri di esito positivo determineranno come segnare il test. Questo dovrebbe essere meno di un passaggio o di un errore e più di un punteggio ponderato in base alle tue esigenze. Ad esempio, per avere esito positivo, uno strumento potrebbe dover ottenere un punteggio superiore all'80% in determinate aree critiche identificate.

## <a name="scorecard"></a>Scorecard

Un modo per riunire tutti gli elementi del piano può essere quello di creare una scorecard. Di seguito è riportata una scorecard di esempio:

| Caso di utilizzo | Requisiti | Requisiti di configurazione | Piano di testing | Risultato previsto | Stato test | Punteggio | Note |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|Gestione degli incidenti|- Microsoft 365 Defender </br></br>- Microsoft Defender for Identity </br></br>- Microsoft Defender per Endpoint </br></br>- Microsoft Cloud App Security (facoltativo)|Per informazioni [dettagliate,](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) vedere i prerequisiti per la preparazione, la configurazione e la configurazione |[Simula attacco](m365d-pilot-simulate.md) <br></br>[Analizzare l'evento imprevisto](./m365d-pilot-simulate.md#investigate-an-incident) |Gli investigatori possono comprendere l'ambito e l'impatto dell'incidente e gestire l'incidente||||
|AutoIR|- Microsoft 365 Defender </br></br>- Microsoft Defender for Identity </br></br>- Microsoft Defender per Endpoint |Per informazioni [dettagliate,](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) vedere i prerequisiti per la preparazione, la configurazione e la configurazione <br>Abilita AutoIR  |[Simula attacco](m365d-pilot-simulate.md) <br></br>[Indagine automatizzata](m365d-pilot-simulate.md#automated-investigation-and-remediation) |Gli avvisi e gli eventi imprevisti vengono corretti automaticamente da Microsoft 365 Defender||||
|Rilevazione avanzata|- Microsoft 365 Defender </br></br>- Microsoft Defender per Endpoint </br></br>-Microsoft Defender per Office 365 |Per informazioni [dettagliate,](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) vedere i prerequisiti per la preparazione, la configurazione e la configurazione|[Scenario di ricerca avanzata](./m365d-pilot-simulate.md#advanced-hunting-scenario) |Gli investigatori possono trovare i dati tramite la ricerca avanzata, il pivot per le entità influenzate e creando rilevamenti personalizzati||||

## <a name="next-step"></a>Passaggio successivo

|![Fase di preparazione](../../media/mtp/prep.png) <br>[Fase di preparazione](prepare-m365d-eval.md) | Preparare l'Microsoft 365 Defender pilota
|:-------|:-----|
