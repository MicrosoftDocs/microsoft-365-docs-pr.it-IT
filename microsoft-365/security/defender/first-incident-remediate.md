---
title: Passaggio 2. Correggere il primo evento imprevisto
description: Come iniziare a correggere il primo evento imprevisto in Microsoft 365 Defender.
keywords: incidenti, avvisi, indagare, correlazione, attacco, computer, dispositivi, utenti, identità, identità, cassetta postale, posta elettronica, 365, microsoft, m365, risposta a eventi imprevisti, cyberattacco
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ed597c55a646eb00d6e6d256c287b22c119f8148
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297345"
---
# <a name="step-2-remediate-your-first-incident"></a>Passaggio 2. Correggere il primo evento imprevisto

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- Microsoft 365 Defender

Microsoft 365 Defender non solo fornisce funzionalità di rilevamento e analisi, ma fornisce anche il contenimento e l'eliminazione di malware. Containment includes steps to reduce the impact of the attack while eradication ensures all traces of attacker activity are removed from the network.  Microsoft 365 Defender offre diverse azioni di correzione [](m365d-autoir.md) che possono essere configurate per la correzione automatica a seconda del sistema operativo e del tipo di attacco.

Microsoft 365 Defender offre diverse azioni di correzione che gli analisti possono avviare manualmente. Le azioni sono suddivise in due categorie, Azioni su dispositivi e Azioni sui file. Alcune azioni possono essere usate per arrestare immediatamente la minaccia, mentre altre azioni sono utili per un'ulteriore analisi forense.

## <a name="actions-on-devices"></a>Azioni nei dispositivi

- **Isolare il** dispositivo- Questa attività blocca immediatamente tutto il traffico di rete (Internet e interno) per ridurre al minimo la diffusione di malware e consentire agli analisti di continuare l'analisi senza che un attore malintenzionato sia in grado di continuare un attacco. L'unica connessione consentita è al cloud del servizio Microsoft Defender for Identity, in modo che Microsoft Defender for Identity possa continuare a monitorare il dispositivo. 
- **Limitare l'esecuzione dell'app:** per limitare l'esecuzione di un'applicazione, vengono applicati criteri di integrità del codice che consentono l'esecuzione dei file solo se firmati da un certificato emesso da Microsoft. Questo metodo di restrizione può aiutare a impedire a un utente malintenzionato di controllare i dispositivi compromessi ed eseguire ulteriori attività dannose.
- **Eseguire l'analisi antivirus** : un'Antivirus Microsoft Defender di analisi può essere eseguita insieme ad altre soluzioni antivirus, indipendentemente dal fatto che Defender Antivirus sia o meno la soluzione antivirus attiva. Se un altro prodotto fornitore di antivirus è la soluzione principale per la protezione degli endpoint, puoi eseguire Defender Antivirus in modalità passiva.
- **Avviare un'indagine automatizzata:** è possibile avviare una nuova indagine automatizzata di uso generale nel dispositivo. Durante l'esecuzione di un'indagine, qualsiasi altro avviso generato dal dispositivo verrà aggiunto a un'indagine automatizzata in corso fino al completamento dell'indagine. Inoltre, se la stessa minaccia viene vista su altri dispositivi, questi dispositivi vengono aggiunti all'indagine.
- **Initiate live response** - La risposta in tempo reale è una funzionalità che consente l'accesso istantaneo a un dispositivo tramite una connessione shell remota. In questo modo è possibile eseguire un lavoro di indagine approfondito e intraprendere azioni di risposta immediate per contenere prontamente le minacce identificate in tempo reale. La risposta in tempo reale è progettata per migliorare le indagini consentendoti di raccogliere dati forensi, eseguire script, inviare entità sospette per l'analisi, correggere le minacce e cercare in modo proattivo minacce emergenti.
- **Raccogli pacchetto di indagine:** nell'ambito del processo di indagine o di risposta, puoi raccogliere un pacchetto di indagine da un dispositivo. Raccogliendo il pacchetto di analisi, è possibile identificare lo stato corrente del dispositivo e comprendere ulteriormente gli strumenti e le tecniche utilizzati dall'autore dell'attacco. 
- **Consultare un esperto** di minacce (disponibile in Azioni su dispositivi e file): è possibile consultare un esperto di minacce Microsoft per ulteriori informazioni su dispositivi o dispositivi potenzialmente compromessi già compromessi. Gli esperti di minacce Microsoft possono essere coinvolti direttamente dall'Microsoft Defender Security Center per una risposta accurata e immediata. 

## <a name="actions-on-files"></a>Azioni sui file

- **Stop and quarantine file** - Questa azione include l'interruzione dei processi in esecuzione, la messa in quarantena dei file e l'eliminazione di dati permanenti, ad esempio le chiavi del Registro di sistema. Questa azione ha effetto sui dispositivi con Windows 10 versione 1703 o successiva, in cui il file è stato osservato negli ultimi 30 giorni. 
- **Aggiungere indicatori per bloccare o consentire i file-** Impedire l'ulteriore propagazione di un attacco nell'organizzazione vietando file potenzialmente dannosi o malware sospetto. Questa operazione impedirà la lettura, la scrittura o l'esecuzione del file nei dispositivi dell'organizzazione.
- **Scaricare o raccogliere file:** questa azione consente agli analisti di scaricare un file in un file di archivio .zip protetto da password per un'ulteriore analisi da parte dell'organizzazione.
- **Analisi approfondita:** questa azione esegue un file in un ambiente cloud sicuro e completamente instrumentato. I risultati dell'analisi approfondita mostrano le attività, i comportamenti osservati e gli artefatti associati del file, ad esempio i file eliminati, le modifiche al Registro di sistema e la comunicazione con gli indirizzi IP. 

Continuando l'esempio in [Rilevare, analizzare](first-incident-analyze.md#analyze-your-first-incident)e analizzare gli eventi imprevisti, un analista può correggere questo incidente con queste azioni:

1. Reimpostare immediatamente la password dell'account utente
2. Isolare il dispositivo in Microsoft 365 Defender fino al completamento dell'analisi approfondita
3. Verificare che il file dannoso sia stato messo in quarantena SharePoint
4. Verificare quali endpoint sono stati interessati dal malware
5. Rigenerare i sistemi
6. Verificare la presenza di avvisi Microsoft Cloud App Security simili per altri utenti
7. Creare un indicatore personalizzato in Microsoft Defender for Endpoint per bloccare un indirizzo IP Tor
8. Creare un'azione di governance in Microsoft Cloud App Security per questo tipo di avviso, ad esempio quelle mostrate nell'immagine seguente:

   :::image type="content" source="../../media/first-incident-remediate/first-incident-mcas-governance.png" alt-text="Esempio di azioni di governance nel portale Microsoft Cloud App Security governance"::: 
 
La maggior parte delle azioni di correzione può essere applicata e monitorata in Microsoft 365 Defender. 

## <a name="using-playbooks"></a>Uso di Playbook

Inoltre, è possibile creare correzioni automatizzate usando playbook. Attualmente, Microsoft dispone di [modelli Playbook GitHub](https://github.com/microsoft/Microsoft-Cloud-App-Security/tree/master/Playbooks) che forniscono playbook per gli scenari seguenti:

- Rimuovere la condivisione di file sensibili dopo aver richiesto la convalida dell'utente
- Auto-triage infrequent country alerts
- Richiedere l'azione del manager prima di disabilitare un account
- Disabilitare le regole di Posta in arrivo dannose

I playbook usano Power Automate per creare flussi di automazione dei processi robotizzati personalizzati per automatizzare determinate attività dopo l'attivazione di criteri specifici. Le organizzazioni possono creare playbook da modelli esistenti o da zero. 

Di seguito viene riportato un esempio.
 
:::image type="content" source="../../media/first-incident-remediate/first-incident-power-automate.png" alt-text="Esempio di un flusso Power Automate di automazione dei processi robot personalizzati"::: 
 
I Playbook possono essere creati anche durante la revisione [post-incidente](first-incident-post.md) per creare azioni di correzione dagli eventi imprevisti per azioni correttive più rapide. 

## <a name="next-step"></a>Passaggio successivo

[![Passaggio 3: informazioni su come eseguire una revisione post-incidente di un evento imprevisto](../../media/first-incident-overview/first-incident-path-step3.png)](first-incident-post.md)

Informazioni su come [eseguire una revisione post-incidente di un evento imprevisto.](first-incident-post.md)

## <a name="see-also"></a>Vedere anche

- [Panoramica degli eventi imprevisti](incidents-overview.md)
- [Indagare sugli eventi imprevisti](investigate-incidents.md)
- [Gestire gli eventi imprevisti](manage-incidents.md)
