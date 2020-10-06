---
title: Pianificazione del progetto pilota di Microsoft Threat Protection
description: Pianificare il progetto pilota Microsoft Threat Protection con le parti interessate per gestire le aspettative e garantire esito positivo.
keywords: Pilota di Microsoft Threat Protection, pianificare il progetto pilota di Microsoft Threat Protection, valutare Microsoft Threat Protection in produzione, Microsoft Threat Protection Project pilota, sicurezza cibernetica, Advanced Persistent Threat, sicurezza aziendale, dispositivi, dispositivo, identità, utenti, dati, applicazioni, incidenti, analisi automatizzata e correzione, ricerca avanzata
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
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: 7d1870d1b8972009bed657f476810ca011dc2621
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367978"
---
# <a name="planning-your-pilot-microsoft-threat-protection-project"></a>Pianificazione del progetto pilota di Microsoft Threat Protection 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft Threat Protection
<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft Threat Protection project" title="Pianificare il progetto pilota di Microsoft Threat Protection" />
      <br/>Piano</a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Preparare il laboratorio di valutazione di Microsoft Threat Protection o l'ambiente pilota" />
      <br/>Preparazione</a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft Threat Protection attack simulations" title="Eseguire le simulazioni di attacco di Microsoft Threat Protection" />
     <br/>Simula attacco</a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft Threat Protection pilot" title="Chiudere e riepilogare il pilota di Microsoft Threat Protection" />
     <br/>Chiudi e riepiloga</a><br>
    </td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
    <td valign="top" style="width:25%; border:0;">

</td>
  </tr>
</table>

Si è attualmente in fase di pianificazione.

Per assicurarsi che il progetto pilota sia un successo, è essenziale pianificare con attenzione e ottenere le approvazioni dalle parti interessate all'inizio. Gli elementi di pianificazione includono l'ambito di identificazione, i casi di utilizzo, i requisiti e i criteri di successo.

In questa guida viene illustrato come pianificare il progetto pilota. 

>[!IMPORTANT]
>Per ottenere risultati ottimali, seguire le istruzioni pilota il più fedelmente possibile.


## <a name="scope"></a>Scope

L'ambito del progetto pilota determinerà il livello di ampiezza del test, in base all'ambiente e ai metodi di testing accettabili. Di seguito sono riportate alcune considerazioni di esempio:
- Ambiente di sviluppo o di testing che include endpoint, server, controller di dominio.
- Ambiente di produzione con Microsoft 365, Azure, servizi, endpoint e server di Active Directory

>[!NOTE]
>Se non si dispone ancora delle licenze complete, è possibile ottenere le licenze di valutazione per [valutare Microsoft Threat Protection](https://aka.ms/mtp-trial-lab) : pianificare, preparare, configurare ed eseguire il progetto pilota. Le parti interessate giocheranno un ruolo importante nell'agevolare il processo dall'inizio alla fine.

I tipi di sistemi operativi da valutare devono essere anche definiti in base al trucco dell'organizzazione. Questo può includere gli [endpoint Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), i [server Linux](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), gli [endpoint di windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).

## <a name="use-cases"></a>Casi di utilizzo

I casi di utilizzo rappresentano istruzioni sul modo in cui lo strumento da testare deve essere utilizzato dagli utenti previsti. Tali informazioni possono essere formulate come storie utente dal punto di vista di una persona specifica, ad esempio un analista SOC. Ad esempio:
- Come analista SOC, è necessario visualizzare, correlare, valutare e gestire avvisi ed eventi tra i dispositivi, gli utenti e le cassette postali della rete. [Gestione degli incidenti]
- Come analista SOC, è necessario disporre dello strumento e del processo per analizzare e rispondere automaticamente agli eventi dannosi nella rete. [IR automatico]
- Come analista SOC, è necessario eseguire la ricerca dei dati dal proprio ambiente per individuare minacce note e potenziali e attività sospette. [Caccia avanzata]

Tenere presente che questi casi di utilizzo devono essere creati all'interno dei parametri dell'ambito definito. Se, ad esempio, l'ambito del testing non include una valutazione di strumenti quali Microsoft cloud app Security, utilizzare i casi che si basano su questa operazione come origine dati non deve essere creato.

## <a name="requirements"></a>Requisiti

Nell'elenco dei casi di utilizzo è possibile iniziare a creare i requisiti. Requisiti: funzionalità è necessario uno strumento per soddisfare i casi di utilizzo. Questi requisiti possono essere suddivisi in categorie quali la configurazione e la manutenzione, il supporto per le integrazioni e i requisiti specifici per le funzionalità come la capacità di caccia e la possibilità di creare avvisi personalizzati.

## <a name="test-plan"></a>Piano di testing

A seconda dei requisiti, è possibile che i diversi metodi di test siano adatti. Ad esempio, se l'esigenza è quella di valutare l'efficacia della correzione automatica, il piano di test deve includere dei passaggi per generare i comportamenti che avrebbero attivato un'azione di correzione automatica all'interno di Microsoft Threat Protection. Se il requisito consiste nel rilevare un comportamento o un attacco specifico, il test può comportare più passaggi. Il punto è che è necessario disporre di un piano per testare accuratamente le proprie esigenze.

## <a name="success-criteria"></a>Criteri di esito positivo

I criteri di esito positivo sono infine il set di barre su misura rispetto a ciò che si sta testando. Se si sta testando Microsoft Threat Protection (o qualsiasi altra tecnologia per questo motivo) rispetto ad altri strumenti o da solo, devono essere disponibili alcuni criteri quantificabili per determinare il valore fornito dallo strumento. In base all'ambito, ai requisiti e al piano di testing, i criteri di esito positivo determineranno la modalità di valutazione del test. Questo valore deve essere inferiore a un passaggio o a un errore e più di un punteggio ponderato in base alle proprie esigenze. Ad esempio, per avere esito positivo, potrebbe essere necessario uno strumento per ottenere un punteggio maggiore di 80% in determinate aree critiche identificate.

## <a name="scorecard"></a>Scorecard

Un modo per portare insieme tutti gli elementi del piano può essere quello di creare una scorecard. Vedere una scorecard di esempio in basso:

|**Use case**|**Requisiti**|**Requisiti di configurazione**|**Piano di testing**|**Risultato previsto**|**Stato del test**|**Punteggio**|**Note**|
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|Gestione degli incidenti|-Protezione dalle minacce di Microsoft </br></br>-Azure ATP </br></br>-Microsoft Defender ATP </br></br>-Protezione delle app di Microsoft Cloud (facoltativa)|Per informazioni dettagliate, vedere i [prerequisiti](https://aka.ms/mtp-trial-lab) per la preparazione, l'installazione e la configurazione. |[Simula attacco](mtp-pilot-simulate.md) <br></br>[Esaminare l'evento Incident](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |Gli investigatori possono comprendere l'ambito e l'impatto dell'incidente e gestire l'evento imprevisto||||
|AutoIR|-Protezione dalle minacce di Microsoft </br></br>-Azure ATP </br></br>-Microsoft Defender ATP |Per informazioni dettagliate, vedere i [prerequisiti](https://aka.ms/mtp-trial-lab) per la preparazione, l'installazione e la configurazione. <br>Abilitare AutoIR  |[Simula attacco](mtp-pilot-simulate.md) <br></br>[Analisi automatizzata](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#automated-investigation-and-remediation) |Gli avvisi e gli eventi non consentiti vengono corretti automaticamente da Microsoft Threat Protection||||
|Ricerca avanzata|-Protezione dalle minacce di Microsoft </br></br>-Microsoft Defender ATP </br></br>-Office 365 ATP   |Per informazioni dettagliate, vedere i [prerequisiti](https://aka.ms/mtp-trial-lab) per la preparazione, l'installazione e la configurazione.|[Scenario di caccia avanzato](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#advanced-hunting-scenario) |Gli investigatori possono trovare dati tramite la ricerca avanzata, pivoting alle entità interessate e creando rilevamenti personalizzati||||



## <a name="next-step"></a>Passaggio successivo
|![Fase di preparazione](../../media/mtp/prep.png) <br>[Fase di preparazione](prepare-mtpeval.md) | Preparare l'ambiente pilota di Microsoft Threat Protection
|:-------|:-----|
