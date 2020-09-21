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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: bf080fddd7545c4397483c0eba7a010952922e7e
ms.sourcegitcommit: a3c2c737995088c1bad3b12ab401a7ef242b0272
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47956404"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a>Eseguire il progetto pilota di Microsoft Threat Protection 

**Si applica a:**
- Microsoft Threat Protection

Per determinare in modo efficace il vantaggio e l'adozione di Microsoft Threat Protection (MTP), è possibile eseguire un progetto pilota. Prima di abilitare Microsoft Threat Protection nell'ambiente di produzione e iniziare con i casi di utilizzo definiti, è preferibile passare attraverso un processo di pianificazione per determinare le attività che devono essere eseguite in questo progetto pilota e i criteri di esito positivo. 


## <a name="how-to-use-this-pilot-playbook"></a>Come usare questo pilota PlayBook

In questa guida viene fornita una panoramica di Microsoft Threat Protection e istruzioni dettagliate su come configurare il progetto pilota. 

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
| ![Preparazione](../../media/prepare.png) <br>[Preparazione](mtp-evaluation.md)|  Accedere al centro sicurezza Microsoft 365 per configurare l'ambiente pilota Microsoft Threat Protection. Verrà guidato per:<br><br>-Identificare le parti interessate e cercare l'accesso per il pilota <br> -Considerazioni sull'ambiente <br>-Access <br>-Configurazione di Azure Active Directory <br> -Ordine di configurazione <br> -Iscriversi alla versione di valutazione di Microsoft 365 E5 <br> -Configurare il dominio <br>-Assegnare licenze Microsoft 365 E5 <br> -Completare l'installazione guidata nel portale|
| ![Simulazione di attacco](../../media/mtp/run-sim.png) <br>[Simulazione di attacco](mtp-pilot-simulate.md) | Per simulare un attacco, sarà possibile eseguire le operazioni seguenti:<br><br>-Verificare i requisiti dell'ambiente di testing <br>-Eseguire la simulazione <br>-Indagare su un evento imprevisto <br>-risolvere l'evento non consentita 
| ![Chiusura e riepilogo](../../media/mtp/close.png) <br>[Chiusura e riepilogo](mtp-pilot-close.md) | Dopo aver raggiunto la fine del processo, si verrà guidati a:<br><br>-Passare attraverso l'output finale<br>-Presentare l'output alle parti interessate <br>-Fornire commenti e suggerimenti <br>-Eseguire i passaggi successivi 

## <a name="next-step"></a>Passaggio successivo
|![Fase di pianificazione](../../media/mtp/plan.png) <br>[Fase di pianificazione](mtp-pilot-plan.md) | Pianificare il progetto pilota di Microsoft Threat Protection 
|:-------|:-----|
