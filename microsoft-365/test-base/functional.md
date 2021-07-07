---
title: Test funzionali sulla base di test
description: Dettagli su come testare l'applicazione con i test funzionali automatizzati esistenti
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 7b5cb907756ec0fb746d303b3ab629e912bf9c96
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323225"
---
# <a name="functional-testing"></a>Test funzionali

In quanto fornitore di software, ora puoi eseguire test funzionali personalizzati usando il framework di test di tua scelta, tramite il portale Test Base self-service per M365. 

Quando il servizio è stato avviato inizialmente, sono stati offerti i test out-of-box, ovvero un set predefinito di test guidati tramite script standardizzati. Ciò, tuttavia, non è stato in grado di ottenere una copertura di test completa per molti fornitori di software indipendenti (ISV). 

Di conseguenza, in risposta al tuo feedback, forniamo ai nostri ISV la possibilità di caricare test funzionali automatizzati.

Per utilizzare questa funzionalità, eseguire la procedura seguente:

1. Upload file (file binari, dipendenze e script) come singolo pacchetto .zip file.
2. Scegliere se riavviare le macchine virtuali di test in diversi punti di esecuzione.
3. Gestire le opzioni disponibili per gli script.
4. Scegliere quando applicare l'aggiornamento Windows sulla macchina virtuale durante l'esecuzione.

Le descrizioni dettagliate dei passaggi precedenti sono evidenziate di seguito:

**Upload un pacchetto di test funzionale**

To get started, navigate to the Upload page, select Upload new application under Application catalog on the left-side navigation menu of the Test Base for M365 portal in Azure. Da qui:

Scheda 1: immettere le informazioni di base. Specificare il nome e la versione dell'applicazione. Nell'opzione Tipo di test selezionare ```Functional tests``` . 

*Si noti che l'opzione Out-of-Box (OOB) è obbligatoria per impostazione predefinita.*


![Selezionare la scheda test funzionale](Media/functional_testing_tab1.png)

Scheda 2: Upload i componenti del pacchetto caricando un file ZIP con l'intero test (file binari, dipendenze, script e così via). 

Vedi aka.ms/usl-package-outline per informazioni dettagliate. Nota: sia gli script di test out-of-box che il contenuto del test funzionale devono essere inseriti nello stesso file ZIP. Attualmente, le dimensioni del file sono limitate a 2 GB.

Scheda 3- Configurare le attività di test out-of-box e funzionali. Qui scegli i percorsi degli script di PowerShell che installeranno, avvieranno, chiuderanno e disinstallano l'applicazione (per Out-of-Box), nonché i percorsi di tutti gli script personalizzati per eseguire il test funzionale. **Nota: uno script per disinstallare l'applicazione è facoltativo.**

Attualmente, è possibile caricare da 1 a 8 script per i test funzionali. (Commenta gentilmente questo post se hai bisogno di più script!)

![Upload fino a 8 script con test funzionali](Media/functional_testing_tab3.png)

(Facoltativo) Configurare un riavvio dopo l'installazione. Alcune applicazioni richiedono un riavvio dopo l'installazione. 

Selezionare lo script specifico nella scheda Attività se si desidera che venga eseguito un riavvio ```Reboot After Execution``` dopo l'esecuzione dello script.

Scheda 4 - Scegliere quando installare l Windows interno: l'applicazione della patch Windows Update viene eseguita prima di qualsiasi script di propria scelta. È consigliabile installare un aggiornamento Windows dopo l'installazione dell'applicazione per imitare da vicino gli scenari di utilizzo delle applicazioni reali.

![L Windows aggiornamento può essere installato dopo uno script specifico](Media/functional_testing_tab4.png)

Scheda 5 - Rivedere e creare il pacchetto. Dopo aver completato i passaggi sopra elencati, selezionare ```Create``` per completare il processo di caricamento.

Dopo aver creato il pacchetto, puoi controllare lo stato di verifica del pacchetto.

Viene eseguito un test iniziale per installare, avviare, chiudere e disinstallare l'applicazione. Questo ci consente di verificare che il pacchetto possa essere installato nel nostro servizio senza errori.

Il processo di verifica può richiedere fino a 24 ore. Una volta completata la verifica, puoi visualizzare lo stato nel menu, che sarebbe ```Manage packages``` una delle due voci seguenti:

1. La verifica ha esito positivo: il pacchetto verrà testato automaticamente in base agli aggiornamenti Windows versione non definitiva per le build del sistema operativo selezionate.
oppure
2. La verifica non riesce: dovrai analizzare i motivi dell'errore, risolvere il problema e ricaricare il pacchetto.

Si riceverà inoltre una notifica di entrambi i risultati tramite l'icona di notifica nel portale di Azure.
