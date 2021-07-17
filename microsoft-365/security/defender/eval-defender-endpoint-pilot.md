---
title: Pilotare Microsoft Defender for Endpoint, configurare un progetto pilota e testare le funzionalità di valutazione
description: Scopri come eseguire un progetto pilota per Microsoft Defender for Endpoint(MDE), inclusa la verifica del gruppo pilota e la prova delle funzionalità.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: d1efc37bd6412e441593dc9cf81296162f7fa754
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458007"
---
# <a name="pilot-microsoft-defender-for-endpoint"></a>Pilotare Microsoft Defender per Endpoint

Questo articolo ti guiderà nel processo di esecuzione di un progetto pilota per Microsoft Defender per Endpoint. 

Usa la procedura seguente per configurare il progetto pilota per Microsoft Defender per Endpoint. 

![Passaggi per l'aggiunta di Microsoft Defender per l'identità all'ambiente di valutazione di Defender](../../media/defender/m365-defender-endpoint-pilot-steps.png)

- Passaggio 1. Verificare il gruppo pilota
- Passaggio 2. Funzionalità di prova

Quando si esegue il test pilota di Microsoft Defender per Endpoint, è possibile scegliere di eseguire l'onboarding di alcuni dispositivi al servizio prima di eseguire l'onboarding dell'intera organizzazione.  

Puoi quindi provare le funzionalità disponibili, ad esempio l'esecuzione di simulazioni di attacco e vedere in che modo Defender for Endpoint eserciterà attività dannose e ti permetterà di eseguire una risposta efficiente. 

## <a name="step-1-verify-pilot-group"></a>Passaggio 1. Verificare il gruppo pilota
Dopo aver completato i passaggi di onboarding descritti nella sezione [Abilita](eval-defender-endpoint-enable-eval.md) valutazione, dovresti vedere i dispositivi nell'elenco Inventario dispositivi circa dopo un'ora. 

Quando vedi i dispositivi onboarded, puoi procedere con le funzionalità di prova. 

## <a name="step-2-try-out-capabilities"></a>Passaggio 2. Funzionalità di prova
Dopo aver completato l'onboarding di alcuni dispositivi e verificato che stiano segnalando al servizio, acquisire familiarità con il prodotto provando le potenti funzionalità disponibili direttamente.

Durante il progetto pilota, è possibile iniziare facilmente a provare alcune delle funzionalità per visualizzare il prodotto in azione senza eseguire passaggi di configurazione complessi.

Iniziamo con l'estrazione dei dashboard.

### <a name="view-the-device-inventory"></a>Visualizzare l'inventario dei dispositivi
L'inventario dei dispositivi è il punto in cui vedrai l'elenco di endpoint, dispositivi di rete e dispositivi IoT nella rete. Non solo fornisce una visualizzazione dei dispositivi nella rete, ma fornisce anche informazioni approfondite su di essi, ad esempio dominio, livello di rischio, piattaforma del sistema operativo e altri dettagli per una facile identificazione dei dispositivi più a rischio.

### <a name="view-the-threat-and-vulnerability-management-dashboard"></a>Visualizzare il dashboard delle minacce gestione delle vulnerabilità sicurezza 
Le minacce gestione delle vulnerabilità consentono di concentrarsi sui punti di debolezza che rappresentano il rischio più urgente e più alto per l'organizzazione. Dal dashboard, ottieni una visualizzazione di alto livello del punteggio di esposizione dell'organizzazione, microsoft secure score per i dispositivi, distribuzione dell'esposizione dei dispositivi, consigli di sicurezza principali, software più vulnerabile, attività di correzione principali e dati dei dispositivi più esposti. 

### <a name="run-a-simulation"></a>Eseguire una simulazione
Microsoft Defender for Endpoint include scenari di attacco "Fai da [te"](https://securitycenter.windows.com/tutorials) che puoi eseguire nei dispositivi pilota.  Ogni documento include i requisiti del sistema operativo e delle applicazioni, nonché istruzioni dettagliate specifiche per uno scenario di attacco. Questi script sono sicuri, documentati e facili da usare. Questi scenari rifletteranno le funzionalità di Defender for Endpoint e illustrano l'esperienza di analisi.

Per eseguire una delle simulazioni fornite, è necessario almeno [un dispositivo onboarded.](../defender-endpoint/onboard-configure.md)

1. In   >  **Simulazioni guida & esercitazioni** selezionare quali degli scenari di attacco disponibili si desidera simulare:

   - **Scenario 1: la backdoor** del documento viene simulare la consegna di un documento di esca socialmente progettato. Il documento avvia una backdoor appositamente predisposta che consente agli utenti malintenzionati di controllare.

   - **Scenario 2: script di PowerShell in** attacco senza file - Simula un attacco senza file che si basa su PowerShell, che mostra la riduzione della superficie di attacco e il rilevamento di dispositivi di apprendimento di attività di memoria dannose.

   - **Scenario 3: risposta** automatica agli eventi imprevisti : attiva un'indagine automatizzata, che cerca e correda automaticamente gli artefatti di violazione per ridimensionare la capacità di risposta agli incidenti.

2. Scaricare e leggere il documento della procedura dettagliata corrispondente fornito con lo scenario selezionato.

3. Scarica il file di simulazione o copia lo script di simulazione accedendo alla **Guida**  >  **Simulazioni & esercitazioni**. Puoi scegliere di scaricare il file o lo script nel dispositivo di test, ma non è obbligatorio.

4. Eseguire il file o lo script di simulazione nel dispositivo di test come indicato nel documento della procedura dettagliata.

> [!NOTE]
> I file o gli script di simulazione simulano l'attività di attacco, ma sono in realtà benigni e non danneggiano o comprometteranno il dispositivo di test.

## <a name="next-steps"></a>Passaggi successivi
[Valutare Microsoft Cloud App Security](eval-defender-mcas-overview.md)

Torna alla panoramica per [valutare Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)

Tornare alla panoramica per [valutare e valutare Microsoft 365 Defender](eval-overview.md)