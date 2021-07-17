---
title: Microsoft Managed Desktop e Windows 11
description: Come e quando Windows 11 è disponibile nel servizio
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1c5f2a7f60097bb02cb11eaabd66cad88657c505
ms.sourcegitcommit: 2abc6bf9939b14a427647e88f319dbb70de49ca6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2021
ms.locfileid: "53458482"
---
# <a name="microsoft-managed-desktop-and-windows-11"></a>Microsoft Managed Desktop e Windows 11

Dopo l'annuncio di Windows 11 Windows, è possibile che sia stata avviata la pianificazione di 11 migrazioni come parte degli sforzi per mantenere aggiornati Windows 10 dispositivi. In questo articolo vengono illustrate considerazioni importanti e Microsoft Managed Desktop supporteranno transizioni fluide negli ambienti. Per informazioni su Windows 11, vedere panoramica Windows [11.](/windows/whats-new/windows-11)

Per la procedura specifica da seguire per installare Windows 11 nei dispositivi Microsoft Managed Desktop, vedere Anteprima e [test Windows 11 con Microsoft Managed Desktop](../working-with-managed-desktop/test-win11-mmd.md).

## <a name="timeline-for-windows-11"></a>Sequenza temporale per Windows 11

Windows 11 build di anteprima sono disponibili a partire dal 28 giugno 2021 tramite [il Windows Insider Program.](/windows-insider/) Si prevede che le build di rilascio saranno generalmente disponibili entro la fine dell'anno di calendario 2021.

Puoi installare le build di anteprima nei dispositivi indipendentemente dal fatto che siano gestite da Microsoft Managed Desktop o meno. Continueremo a supportare Windows 10 in parallelo fino a quando non raggiungerà la fine del supporto.

Quando Windows 11 è in genere disponibile, verranno evasi altri test di convalida. Si prevede che gennaio 2022 sarà il più presto disponibile Windows 11 per Microsoft Managed Desktop dispositivi di produzione tramite i gruppi di distribuzione standard.

Verranno consultati e consigliati agli amministratori di sviluppare e implementare piani di migrazione per ogni tenant in base alla preparazione tecnica e alle considerazioni aziendali.

## <a name="assessing-pre-release-versions-of-windows-11"></a>Valutazione delle versioni non definitiva di Windows 11

Più del 95% dei dispositivi Microsoft Managed Desktop sono idonei per Windows 11, quindi potresti voler visualizzare in anteprima l'aggiornamento nei dispositivi di test prima della distribuzione di produzione. Per ulteriori informazioni Windows 11 requisiti di sistema, vedere [Windows 11 requirements](/windows/whats-new/windows-11-requirements). Puoi richiedere dettagli sullo stato di idoneità dei dispositivi da Microsoft Managed Desktop.

Per Microsoft Managed Desktop, puoi richiedere di aggiungere dispositivi di test al gruppo di dispositivi modern **\[ workplace Windows \] 11 dispositivi** di test non definitiva. Questo gruppo riceve Windows 11 build di anteprima insieme a una Microsoft Managed Desktop di base. Microsoft Managed Desktop non gestisce la frequenza di rilascio delle build di anteprima di Windows 11, pertanto i membri di questo gruppo di dispositivi potrebbero ricevere aggiornamenti più frequentemente rispetto Windows 10 gruppi di dispositivi.

Per i dispositivi non gestiti da Microsoft Managed Desktop, puoi partecipare al programma Insider di [Windows](/windows-insider/) per scaricare le build di anteprima e ottenere indicazioni sulla distribuzione di Windows 11. Se hai dispositivi che eseguono Windows 11 build non definitiva e successivamente li registrano in Microsoft Managed Desktop, non verranno ripristinati Windows 10.

## <a name="support-for-pre-release-windows-11-devices"></a>Supporto per 11 dispositivi Windows versione non definitiva

Le build non definitiva di qualsiasi piattaforma dovrebbero contenere difetti e problemi di compatibilità delle applicazioni che possono essere identificati e risolti prima della disponibilità generale. Di conseguenza, microsoft considera i dispositivi che eseguono build non definitiva di Windows 11 come dispositivi di test, ma li monitoriamo insieme al resto dell'ambiente per le minacce alla sicurezza e sono soggetti alla stessa risposta di avviso di sicurezza degli altri dispositivi Microsoft Managed Desktop.

Poiché ci impegniamo ad aiutarti a eseguire la migrazione a Windows 11 pur rimanendo produttivo, ti consigliamo di segnalare i difetti riscontrati con le build non definitiva. Diamo priorità ai difetti che bloccheranno la produttività degli utenti su un'ampia distribuzione di Windows 11 e ai difetti che bloccano la produttività degli utenti Windows 10 dispositivi.

## <a name="testing-application-compatibility"></a>Test della compatibilità delle applicazioni

La compatibilità delle applicazioni è uno dei problemi più comuni in qualsiasi migrazione della piattaforma a causa della potenziale interruzione della produttività. Stiamo usando diverse misure proattive e reattive per aiutarti a sentirti sicuro delle transizioni fluide delle app a Windows 11.

### <a name="proactive-measures"></a>Misure proattive

**App comuni:** Microsoft sta testando in modo approfondito le applicazioni e le suite aziendali più comuni distribuite nelle build di Windows 11. Microsoft lavora con editori di software esterni e team di prodotti interni per risolvere eventuali problemi rilevati durante il test. Per ulteriori informazioni sui test di compatibilità proattivi, vedere il [blog sulla compatibilità delle applicazioni.](https://blogs.windows.com/windowsexperience/2019/01/15/application-compatibility-in-the-windows-ecosystem/)

App **line-of-business:** [Test Base](https://www.microsoft.com/testbase) è una risorsa che gli editori di app e gli amministratori IT possono usare per inviare app e test case per Microsoft da eseguire in una macchina virtuale che esegue Windows 11 build in un ambiente Azure sicuro. I risultati, le informazioni dettagliate sui test e l'analisi di regressione per ogni esecuzione dei test sono disponibili in un portale privato di Azure. Microsoft Managed Desktop ti aiuterà a definire la priorità delle app line-of-business per la convalida in base all'utilizzo delle app e ai dati di affidabilità. Per ulteriori informazioni sulla base di test, vedere [Test Base for Microsoft 365](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/test-base-for-microsoft-365-microsoft-ignite-2021-updates/ba-p/2185566).

### <a name="reactive-measures"></a>Misure reattive

Se si verificano problemi di compatibilità delle app in ambienti di test o di produzione, è possibile ottenere supporto coinvolgendo [App Assure](/fasttrack/products-and-capabilities) o FastTrack, a livello appropriato. Per Windows 11, sono incluse tutte le funzionalità con le applicazioni Office, Microsoft Edge e Teams in esecuzione nelle build più recenti del sistema operativo. App Assure coinvolge direttamente gli editori di app per definire le priorità e risolvere i problemi di compatibilità delle app.