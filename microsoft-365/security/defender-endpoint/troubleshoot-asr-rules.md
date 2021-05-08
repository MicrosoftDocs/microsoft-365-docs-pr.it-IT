---
title: Segnalare e risolvere i problemi relativi alle regole di Risoluzione dei problemi di Microsoft Defender per Endpoint ASR
description: In questo argomento viene descritto come segnalare e risolvere i problemi di Microsoft Defender per le regole asR endpoint
keywords: Regole di riduzione della superficie di attacco, asr, fianchi, sistema di prevenzione delle intrusioni host, regole di protezione, anti-exploit, antiexploit, exploit, prevenzione delle infezioni, microsoft defender per endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c043e97d6c02e4f41d000e9ce8cfea4a0950252a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246145"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-atp-asr-rules"></a>Segnalare e risolvere i problemi relativi alle regole asR di Microsoft Defender for ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Il Microsoft 365 sicurezza è la nuova interfaccia per il monitoraggio e la gestione della sicurezza tra identità, dati, dispositivi, app e infrastruttura Microsoft. Qui è possibile visualizzare facilmente l'integrità della sicurezza dell'organizzazione, configurare dispositivi, utenti e app e ricevere avvisi per attività sospette. Il Centro sicurezza Microsoft 365 è progettato per gli amministratori e i team delle operazioni di sicurezza per gestire e proteggere in modo migliore le organizzazioni. Visitare il centro Microsoft 365 sicurezza all'indirizzo https://security.microsoft.com .
Nel Microsoft 365 sicurezza, ti offriamo un'occhiata completa alla configurazione e agli eventi correnti delle regole di ripristino automatico nel tuo immobile. Tieni presente che i dispositivi devono essere inseriti nel servizio Microsoft Defender for Endpoint per poter essere popolati.
Ecco uno screenshot dal Centro sicurezza Microsoft 365 sicurezza **(in** Segnala  >  **dispositivi** Riduzione superficie  >  **di attacco**). A livello di dispositivo, seleziona **Configurazione nel** riquadro Regole di riduzione della **superficie di** attacco. Viene visualizzata la schermata seguente, in cui è possibile selezionare un dispositivo specifico e controllare la configurazione delle singole regole asr.

:::image type="content" source="images/asrrulesnew.png" alt-text="Schermata regole di risoluzione dei dati":::

## <a name="microsoft-defender-for-endpoint--advanced-hunting"></a>Microsoft Defender for Endpoint - Ricerca avanzata

Una delle funzionalità più potenti di Microsoft Defender for Endpoint è la ricerca avanzata. Se non hai familiarità con la ricerca avanzata, fai riferimento alla ricerca proattiva per le [minacce con la ricerca avanzata.](advanced-hunting-overview.md)

Ricerca avanzata è uno strumento di ricerca delle minacce basato su query (Kusto Query Language) che consente di esplorare fino a 30 giorni dei dati acquisiti (non elaborati EDR), raccolti da tutti i computer. Tramite la ricerca avanzata, è possibile esaminare in modo proattivo gli eventi per individuare indicatori ed entità interessanti. L'accesso flessibile ai dati consente di cercare senza vincoli minacce note e potenziali.

Attraverso la ricerca avanzata, è possibile estrarre informazioni sulle regole asr, creare report e ottenere informazioni approfondite sul contesto di un determinato evento di controllo o blocco delle regole ASR.

Gli eventi delle regole di registrazione asr sono disponibili per essere interrogati dalla tabella DeviceEvents nella sezione ricerca avanzata del Microsoft Defender Security Center. Ad esempio, una query semplice come quella riportata di seguito può segnalare tutti gli eventi che dispongono di regole asr come origine dati per gli ultimi 30 giorni e li riepiloga in base al conteggio ActionType, che in questo caso sarà il nome in codice effettivo della regola asr.

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="Query di ricerca avanzata":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="schermata di ricerca avanzata":::

Con la ricerca avanzata è possibile modellare le query a proprio piacimento, in modo da poter vedere cosa accade, indipendentemente dal fatto che si desideri individuare un elemento in un singolo computer o estrarre informazioni dettagliate dall'intero ambiente.

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a>Sequenza temporale del computer Microsoft Defender for Endpoint

Un'alternativa alla ricerca avanzata, ma con un ambito più ristretto, è la sequenza temporale del computer microsoft Defender for Endpoint. Puoi visualizzare tutti gli eventi raccolti di un dispositivo, negli ultimi sei mesi, nel Microsoft Defender Security Center, andando all'elenco Machines, selezionare un determinato computer e quindi fare clic sulla scheda Timeline.

Nella figura seguente è riportata una schermata della visualizzazione Sequenza temporale di questi eventi in un determinato endpoint.  Da questa visualizzazione è possibile filtrare l'elenco degli eventi in base a uno qualsiasi dei gruppi di eventi nel riquadro a destra. Puoi anche abilitare o disabilitare gli eventi contrassegnati e dettagliati durante la visualizzazione degli avvisi e lo scorrimento nella sequenza temporale cronologica.

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="Sequenza temporale del Centro sicurezza Microsoft Defender":::

## <a name="how-to-troubleshoot-asr-rules"></a>Come risolvere i problemi relativi alle regole asr?

Il primo e più immediato modo è controllare localmente, in un dispositivo Windows, quali regole di registrazione automatico sono abilitate (e la relativa configurazione) utilizzando i cmdlet di PowerShell.

Ecco alcune altre fonti di informazioni che Windows, per risolvere i problemi relativi all'impatto e al funzionamento delle regole asr.

### <a name="querying-which-rules-are-active"></a>Esecuzione di query sulle regole attive
Uno dei modi più semplici per determinare se le regole asr sono già abilitate e, tramite un cmdlet di PowerShell, Get-MpPreference.
Di seguito viene riportato un esempio:

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="get mppreference script":::

Sono attive più regole asr, con diverse azioni configurate.

Per espandere le informazioni sopra riportate sulle regole asr, è possibile utilizzare le proprietà **AttackSurfaceReductionRules_Ids** e/o **AttackSurfaceReductionRules_Actions**.

Esempio:

*Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Ids*

:::image type="content" source="images/getmpref-examplenew.png" alt-text="esempio di ottenere mpreference":::

Quanto sopra mostra tutti gli ID per le regole asr con un'impostazione diversa da 0 (Non configurato).

Il passaggio successivo consiste nell'elencare le azioni effettive (Blocca o Controlla) con cui è configurata ogni regola. 

*Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Actions*

:::image type="content" source="images/getmpref-example2new.png" alt-text="get mppreference example2":::

### <a name="querying-blocking-and-auditing-events"></a>Esecuzione di query su eventi di blocco e controllo
Gli eventi delle regole asr possono essere visualizzati all'interno del Windows Defender registrazione.

Per accedervi, aprire Windows Visualizzatore eventi e passare **a** Registri applicazioni e servizi  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operativo**.

:::image type="content" source="images/eventviewerscrnew.png" alt-text="visualizzatore eventi scr":::

## <a name="microsoft-defender-malware-protection-logs"></a>Registri di Microsoft Defender Malware Protection
È inoltre possibile visualizzare gli eventi delle regole Antivirus Microsoft Defender tramite lo strumento da riga di comando dedicato, denominato , che può essere utilizzato per gestire e configurare e automatizzare le attività, `*mpcmdrun.exe*` se necessario.

Questa utilità è presente in *%ProgramFiles%\Windows Defender\MpCmdRun.exe*. È necessario eseguirlo da un prompt dei comandi con privilegi elevati, ovvero esegui come amministratore.

Per generare le informazioni di supporto, *digitareMpCmdRun.exe -getfiles*. Dopo un po', diversi log verranno archiviati in un archivio (MpSupportFiles.cab) e resi disponibili in *C:\ProgramData\Microsoft\Windows Defender\Support*.

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="registri di protezione antimalware":::

Estrai l'archivio e avrai molti file disponibili per la risoluzione dei problemi.

I file più rilevanti sono i seguenti:

- **MPOperationalEvents.txt-** Questo file contiene lo stesso livello di informazioni disponibili nel Visualizzatore eventi per Windows Defender del registro operativo di Windows Defender.
- **MPRegistry.txt:** in questo file è possibile analizzare tutte le configurazioni Windows Defender corrente, dal momento in cui i registri di supporto sono stati acquisiti.
- **MPLog.txt:** questo registro contiene informazioni più dettagliate su tutte le azioni/operazioni dell'Windows Defender.
