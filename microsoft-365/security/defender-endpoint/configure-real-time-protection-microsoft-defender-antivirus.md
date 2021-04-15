---
title: Abilitare e configurare le funzionalità di protezione di Microsoft Defender Antivirus
description: Abilitare e configurare le funzionalità di protezione in tempo reale di Microsoft Defender Antivirus, ad esempio il monitoraggio del comportamento, l'euristica e l'apprendimento automatico
keywords: antivirus, protezione in tempo reale, rtp, machine learning, monitoraggio del comportamento, euristica
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.date: 12/16/2019
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 807348fcbf3ad4ef9698b11b194d752d8038b4c9
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765108"
---
# <a name="enable-and-configure-microsoft-defender-antivirus-always-on-protection-in-group-policy"></a>Abilitare e configurare la protezione always-on di Microsoft Defender Antivirus in Criteri di gruppo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

La protezione always-on è costituita da protezione in tempo reale, monitoraggio del comportamento ed euristica per identificare il malware in base ad attività sospette e dannose note.

Queste attività includono eventi, ad esempio processi che apportano modifiche insolite ai file esistenti, modifica o creazione di chiavi del Registro di sistema di avvio automatico e percorsi di avvio (noti anche come punti di estendibilità di avvio automatico o ASEP) e altre modifiche al file system o alla struttura di file.

## <a name="enable-and-configure-always-on-protection-in-group-policy"></a>Abilitare e configurare la protezione always-on in Criteri di gruppo

Puoi usare Editor **Criteri di gruppo locali per** abilitare e configurare le impostazioni di protezione always-on di Microsoft Defender Antivirus.

Per abilitare e configurare la protezione always-on:

1. Aprire **Editor Criteri di gruppo locali.** Per eseguire l'operazione:  

    1. Nella casella di ricerca della barra delle applicazioni di Windows 10 digita **gpedit.**
    
    1. In **Corrispondenza ottimale** fare clic su Modifica Criteri di **gruppo** per avviare Editor Criteri di **gruppo locali.**
    
       ![GpEdit taskbar search result](images/gpedit-search.png)

2. Nel riquadro sinistro **dell'Editor Criteri** di gruppo locali espandere l'albero fino a Configurazione **computer** Modelli amministrativi  >    >  **Componenti di Windows** Microsoft Defender  >  **Antivirus.** 

3. Configurare le impostazioni dei criteri del servizio antimalware di Microsoft Defender Antivirus. Per eseguire l'operazione:  

    1. Nel riquadro **dei dettagli di Microsoft Defender Antivirus** a destra fare doppio clic sull'impostazione dei criteri come specificato nella tabella seguente:

       | Impostazione | Descrizione | Impostazione predefinita |
       |-----------------------------|------------------------|-------------------------------|
       | Consenti avvio del servizio antimalware con priorità normale | Puoi ridurre la priorità del motore di Microsoft Defender Antivirus, che può essere utile nelle distribuzioni leggere in cui vuoi avere il più possibile un processo di avvio snello. Ciò può influire sulla protezione dell'endpoint. | Abilitato
       | Consenti al servizio antimalware di rimanere sempre in esecuzione | Se gli aggiornamenti della protezione sono stati disabilitati, puoi impostare Microsoft Defender Antivirus per l'esecuzione. In questo modo si riduce la protezione nell'endpoint. | Disabilitato |
    
    1. Configurare l'impostazione in base alle esigenze e fare clic su **OK.**
    
    1. Ripetere i passaggi precedenti per ogni impostazione nella tabella.

4. Configurare le impostazioni dei criteri di protezione in tempo reale di Microsoft Defender Antivirus. Per eseguire l'operazione:

    1. Nel riquadro **dei dettagli di Microsoft Defender Antivirus** fare doppio clic su Protezione in tempo **reale.** In caso contrario, dal **riquadro sinistro dell'albero di Microsoft Defender Antivirus** fai clic su Protezione in tempo **reale.**
    
    1. Nel riquadro **dei dettagli protezione** in tempo reale a destra fare doppio clic sull'impostazione del criterio come specificato nella tabella seguente:  

       | Impostazione | Descrizione | Impostazione predefinita |
       |-----------------------------|------------------------|-------------------------------|
       | Attivare il monitoraggio del comportamento | Il motore AV monitorerà i processi di file, le modifiche ai file e al Registro di sistema e altri eventi sugli endpoint per attività dannose sospette e note. | Abilitato |
       | Analizzare tutti i file e gli allegati scaricati | I file e gli allegati scaricati vengono analizzati automaticamente. Questo funziona in aggiunta al filtro SmartScreen Windows Defender, che analizza i file prima e durante il download. | Abilitato |
       | Monitorare le attività di file e programmi nel computer | Il motore di Microsoft Defender Antivirus prende nota di eventuali modifiche ai file (scritture di file, ad esempio spostamenti, copie o modifiche) e attività generali del programma (programmi aperti o in esecuzione e che causano l'esecuzione di altri programmi). | Abilitato |
       | Attivare le notifiche di scrittura del volume non elaborato | Le informazioni sulle scritture di volumi non elaborati verranno analizzate dal monitoraggio del comportamento. | Abilitato |
       | Attivare l'analisi dei processi ogni volta che è abilitata la protezione in tempo reale | Puoi abilitare in modo indipendente il motore di Microsoft Defender Antivirus per analizzare i processi in esecuzione alla ricerca di modifiche o comportamenti sospetti. Ciò è utile se la protezione in tempo reale è stata temporaneamente disabilitata e si desidera analizzare automaticamente i processi avviati mentre era disabilitata. | Abilitato |
       | Definire le dimensioni massime dei file e degli allegati scaricati da analizzare | È possibile definire le dimensioni in kilobyte. | Abilitato |
       | Configurare l'override delle impostazioni locali per attivare il monitoraggio del comportamento | Configurare una sostituzione locale per la configurazione del monitoraggio del comportamento. Questa impostazione può essere impostata solo da Criteri di gruppo. Se abiliti questa impostazione, l'impostazione della preferenza locale avrà la priorità su Criteri di gruppo. Se si disabilita o non si configura questa impostazione, Criteri di gruppo avrà la priorità sull'impostazione di preferenza locale.| Abilitato |
       | Configurare l'override delle impostazioni locali per l'analisi di tutti i file e gli allegati scaricati | Configurare una sostituzione locale per la configurazione dell'analisi di tutti i file e gli allegati scaricati. Questa impostazione può essere impostata solo da Criteri di gruppo. Se abiliti questa impostazione, l'impostazione della preferenza locale avrà la priorità su Criteri di gruppo. Se si disabilita o non si configura questa impostazione, Criteri di gruppo avrà la priorità sull'impostazione di preferenza locale.| Abilitato |
       | Configurare l'override delle impostazioni locali per il monitoraggio dell'attività di file e programmi nel computer | Configurare una sostituzione locale per la configurazione del monitoraggio dell'attività di file e programmi nel computer. Questa impostazione può essere impostata solo da Criteri di gruppo. Se abiliti questa impostazione, l'impostazione della preferenza locale avrà la priorità su Criteri di gruppo. Se si disabilita o non si configura questa impostazione, Criteri di gruppo avrà la priorità sull'impostazione di preferenza locale.| Abilitato |
       | Configurare l'override delle impostazioni locali per attivare la protezione in tempo reale | Configurare una sostituzione locale per la configurazione per attivare la protezione in tempo reale. Questa impostazione può essere impostata solo da Criteri di gruppo. Se abiliti questa impostazione, l'impostazione della preferenza locale avrà la priorità su Criteri di gruppo. Se si disabilita o non si configura questa impostazione, Criteri di gruppo avrà la priorità sull'impostazione di preferenza locale.| Abilitato |
       | Configurare l'override delle impostazioni locali per il monitoraggio dell'attività dei file in ingresso e in uscita | Configurare una sostituzione locale per la configurazione del monitoraggio per l'attività dei file in ingresso e in uscita. Questa impostazione può essere impostata solo da Criteri di gruppo. Se abiliti questa impostazione, l'impostazione della preferenza locale avrà la priorità su Criteri di gruppo. Se si disabilita o non si configura questa impostazione, Criteri di gruppo avrà la priorità sull'impostazione di preferenza locale. | Abilitato |
       | Configurare il monitoraggio per l'attività di file e programmi in ingresso e in uscita | Specificare se il monitoraggio deve essere eseguito in ingresso, in uscita, in entrambe le direzioni o in nessuna delle due direzioni. Ciò è rilevante per le installazioni di Windows Server in cui sono stati definiti server specifici o ruoli del server che visualizzano grandi quantità di modifiche ai file in una sola direzione e si desidera migliorare le prestazioni di rete. Gli endpoint (e i server) completamente aggiornati in una rete avranno un impatto minimo sulle prestazioni indipendentemente dal numero o dalla direzione delle modifiche ai file. | Abilitato (entrambe le direzioni) |

    1. Configurare l'impostazione in base alle esigenze e fare clic su **OK.**
    
    1. Ripetere i passaggi precedenti per ogni impostazione nella tabella.

5. Configurare l'impostazione dei criteri di analisi di Microsoft Defender Antivirus. Per eseguire l'operazione:  

    1. Nel riquadro **sinistro dell'albero di Microsoft Defender Antivirus** fai clic su **Analizza.**
    
       ![Opzioni di analisi di Microsoft Defender Antivirus](images/gpedit-windows-defender-antivirus-scan.png)

    1. Nel riquadro **Dei** dettagli analisi a destra fare doppio clic sull'impostazione del criterio come specificato nella tabella seguente:

       | Impostazione | Descrizione | Impostazione predefinita |
       |-----------------------------|------------------------|-------------------------------|    
       | Attivare l'euristica | La protezione euristica disabiliterà o blocleverà le attività sospette immediatamente prima che al motore di Microsoft Defender Antivirus venga richiesto di rilevare l'attività. | Abilitato |

    1. Configurare l'impostazione in base alle esigenze e fare clic su **OK.**
    
6. Chiudere **Editor Criteri di gruppo locali**.


## <a name="disable-real-time-protection-in-group-policy"></a>Disabilitare la protezione in tempo reale in Criteri di gruppo

> [!WARNING]
> La disabilitazione della protezione in tempo reale riduce drasticamente la protezione degli endpoint e non è consigliata.

La funzionalità principale di protezione in tempo reale è abilitata per impostazione predefinita, ma è possibile disabilitarla utilizzando Editor **Criteri di gruppo locali.**

Per disabilitare la protezione in tempo reale in Criteri di gruppo:

1. Aprire **Editor Criteri di gruppo locali.**

   1. Nella casella di ricerca della barra delle applicazioni di Windows 10 digita **gpedit.**
   
   1. In **Corrispondenza ottimale** fare clic su Modifica Criteri di **gruppo** per avviare Editor Criteri di **gruppo locali.**

2.  Nel riquadro sinistro dell'Editor Criteri di **gruppo locali** espandere l'albero fino a Configurazione **computer** Modelli amministrativi Componenti  >    >  **di**  >  **Windows Microsoft Defender Antivirus**  >  **Real-time Protection**.

3. Nel riquadro **dei dettagli protezione** in tempo reale a destra fare doppio clic su Disattiva protezione in tempo **reale.**

   ![Disattivare la protezione in tempo reale](images/gpedit-turn-off-real-time-protection.png)

4. Nella finestra **di impostazione Disattiva protezione in tempo** reale imposta l'opzione su **Abilitato.**

   ![Disattivare la protezione in tempo reale abilitata](images/gpedit-turn-off-real-time-protection-enabled.png)
   
5. Fare clic su **OK**.

6. Chiudere **Editor Criteri di gruppo locali**.

## <a name="related-articles"></a>Articoli correlati

- [Configurare la protezione comportamentale, euristica e in tempo reale](configure-protection-features-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)