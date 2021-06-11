---
title: Pianificare analisi regolari rapide e complete con Antivirus Microsoft Defender
description: Configurare analisi ricorrenti (pianificate), inclusa la data e l'ora in cui devono essere eseguite e se vengono eseguite come analisi complete o rapide
keywords: analisi rapida, analisi completa, rapida e completa, pianificazione dell'analisi, giornaliera, settimanale, ora, pianificata, ricorrente, regolare
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 5566050e4a64713f6f8b4ac2cb4a7188d3a241c8
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879726"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>Configurare analisi pianificate rapide o complete di Microsoft Defender Antivirus

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Oltre alle analisi antivirus su richiesta [](run-scan-microsoft-defender-antivirus.md) e di protezione sempre in tempo reale, è possibile configurare analisi antivirus regolari e pianificate. È possibile configurare il tipo di analisi, quando deve verificarsi [](manage-protection-updates-microsoft-defender-antivirus.md) l'analisi e se l'analisi deve essere eseguita dopo un aggiornamento della protezione o quando non viene utilizzato un endpoint. È inoltre possibile configurare analisi speciali per completare le azioni di correzione, se necessario.

## <a name="what-do-you-want-to-do"></a>Operazione desiderata

- [Informazioni su analisi rapide, analisi complete e analisi personalizzate](#quick-scan-full-scan-and-custom-scan)
- [Utilizzare Criteri di gruppo per pianificare le analisi antivirus](schedule-antivirus-scans-group-policy.md)
- [Utilizzare Windows PowerShell per pianificare le analisi antivirus](schedule-antivirus-scans-powershell.md)
- [Utilizzare Windows Management Instrumentation per pianificare le analisi antivirus](schedule-antivirus-scans-wmi.md)

## <a name="keep-the-following-points-in-mind"></a>Tenere presenti i punti seguenti

- Per impostazione predefinita, Antivirus Microsoft Defender un aggiornamento 15 minuti prima dell'ora di qualsiasi analisi pianificata. È possibile gestire la pianificazione per il momento in cui gli aggiornamenti di protezione [devono essere scaricati e applicati per](manage-protection-update-schedule-microsoft-defender-antivirus.md) ignorare questa impostazione predefinita. 

- Se un dispositivo viene scollegato e in esecuzione a batteria durante un'analisi completa pianificata, l'analisi pianificata verrà interrotta con l'evento 1002, che indica che l'analisi è stata interrotta prima del completamento. Antivirus Microsoft Defender verrà eseguita un'analisi completa alla successiva ora pianificata.

## <a name="quick-scan-full-scan-and-custom-scan"></a>Analisi rapida, analisi completa e analisi personalizzata

Quando si configurano analisi pianificate, è possibile specificare se l'analisi deve essere completa o rapida. Nella maggior parte dei casi, è consigliabile eseguire un'analisi rapida. 

| Analisi rapida  | Analisi completa  | Analisi personalizzata |
|---------|---------|---------|
| (Scelta consigliata) Un'analisi rapida esamina tutti i percorsi in cui potrebbe essere registrato malware per iniziare con il sistema, ad esempio le chiavi del Registro di sistema e le cartelle di avvio Windows note. <p>In combinazione con la protezione sempre in tempo reale, che rivede i file quando vengono aperti e chiusi e ogni volta che un utente passa a una cartella, un'analisi rapida consente di fornire una protezione avanzata dal malware che inizia con il malware a livello di sistema e kernel. <p>Nella maggior parte dei casi, un'analisi rapida è sufficiente ed è l'opzione consigliata per le analisi pianificate. | Un'analisi completa inizia eseguendo un'analisi rapida e quindi continua con un'analisi sequenziale dei file di tutti i dischi fissi montati e delle unità rimovibili/di rete (se l'analisi completa è configurata per farlo). <p>Il completamento di un'analisi completa può richiedere alcune ore o giorni, a seconda della quantità e del tipo di dati da analizzare.<p>Una volta completata l'analisi completa, è disponibile una nuova intelligence per la sicurezza ed è quindi necessaria una nuova analisi per assicurarsi che non siano rilevate altre minacce con la nuova intelligence per la sicurezza. <p>A causa del tempo e delle risorse coinvolte in un'analisi completa, in generale, Microsoft non consiglia di pianificare analisi complete.  | Un'analisi personalizzata è un'analisi rapida eseguita sui file e sulle cartelle specificati. Ad esempio, puoi scegliere di analizzare un'unità USB o una cartella specifica nell'unità locale del dispositivo. <p> | 

> [!NOTE]
> Per impostazione predefinita, le analisi rapide vengono eseguite su dispositivi rimovibili montati, ad esempio unità USB.

## <a name="how-do-i-know-which-scan-type-to-choose"></a>Come è possibile sapere quale tipo di analisi scegliere?

Utilizzare la tabella seguente per scegliere un tipo di analisi.

| Scenario  | Tipo di analisi consigliato  |
|---------|---------|
| Si desidera configurare analisi regolari e pianificate     | Analisi rapida <p>Un'analisi rapida controlla i processi, la memoria, i profili e alcune posizioni nel dispositivo. In combinazione con la protezione [in tempo](configure-real-time-protection-microsoft-defender-antivirus.md)reale sempre on, un'analisi rapida consente di fornire una copertura avanzata sia per il malware che inizia con il sistema che con il malware a livello di kernel. La protezione in tempo reale esamina i file quando vengono aperti e chiusi e ogni volta che un utente passa a una cartella.         |
| Minacce, ad esempio malware, vengono rilevate in un singolo dispositivo     | Analisi rapida <p>Nella maggior parte dei casi, un'analisi rapida rileva e pulisce il malware rilevato.   |
| Si desidera eseguire [un'analisi su richiesta](run-scan-microsoft-defender-antivirus.md)     | Analisi rapida       |
| Si desidera verificare che un dispositivo portatile, ad esempio un'unità USB, non contenga malware | Analisi personalizzata <p>Un'analisi personalizzata consente di selezionare percorsi, cartelle o file specifici ed esegue un'analisi rapida. |

## <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a>Altre informazioni sulle analisi rapide e complete

- I file dannosi possono essere archiviati in posizioni non incluse in un'analisi rapida. Tuttavia, la protezione sempre in tempo reale esamina tutti i file aperti e chiusi e tutti i file presenti in cartelle a cui un utente accede. La combinazione di protezione in tempo reale e analisi rapida consente di garantire una protezione avanzata dal malware.

- La protezione all'accesso con protezione garantita dal [cloud](cloud-protection-microsoft-defender-antivirus.md) garantisce che tutti i file a cui si accede nel sistema vengano analizzati con i modelli più recenti di security intelligence e machine learning cloud.

- Quando la protezione in tempo reale rileva malware e l'estensione dei file interessati non viene determinata inizialmente, Antivirus Microsoft Defender avvia un'analisi completa come parte del processo di correzione.

- Un'analisi completa può rilevare file dannosi non rilevati da altre analisi, ad esempio un'analisi rapida. Tuttavia, un'analisi completa può richiedere un po' di tempo e utilizzare risorse di sistema preziose per il completamento.

- Se un dispositivo è offline per un lungo periodo di tempo, il completamento di un'analisi completa può richiedere più tempo. 

