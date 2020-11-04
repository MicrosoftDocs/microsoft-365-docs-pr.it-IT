---
title: Introduzione ai classificatori sottoponibili a training (anteprima)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Un classificatore Microsoft 365 è uno strumento che è possibile addestrare per riconoscere vari tipi di contenuto fornendo esempi da esaminare. In questo articolo viene illustrato come creare e formare un classificatore personalizzato e come riqualificarli per aumentare l'accuratezza.
ms.openlocfilehash: f0d3659c1ee03fe69a5513f24d15b295400a24dc
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906347"
---
# <a name="get-started-with-trainable-classifiers-preview"></a>Introduzione ai classificatori sottoponibili a training (anteprima)

Un classificatore addestrabile di Microsoft 365 è uno strumento che è possibile addestrare per riconoscere vari tipi di contenuto fornendo esempi da esaminare. Una volta addestrato, è possibile utilizzarlo per identificare gli elementi per l'applicazione delle etichette di sensibilità di Office, i criteri di conformità delle comunicazioni e i criteri etichette di conservazione.

La creazione di un classificatore addestrabile personalizzato comporta innanzitutto l'assegnazione di campioni che sono scelti dall'uomo e corrispondono positivamente alla categoria. Successivamente, dopo averli elaborati, è possibile testare la capacità dei classificatori di predire assegnando un insieme di esempi positivi e negativi. In questo articolo viene illustrato come creare e formare un classificatore personalizzato e come migliorare le prestazioni di classificatori addestrabili personalizzati e classificatori preformati nel corso della loro durata tramite la riqualificazione.

Per ulteriori informazioni sui diversi tipi di classificatori, vedere [informazioni sui classificatori addestrabili (Preview)](classifier-learn-about.md).

## <a name="prerequisites"></a>Prerequisiti

### <a name="licensing-requirements"></a>Requisiti per la licenza

I classificatori sono una funzionalità di conformità di Microsoft 365 E5 o E5. È necessario disporre di uno di questi abbonamenti per utilizzarli.

### <a name="permissions"></a>Autorizzazioni

Per accedere ai classificatori nell'interfaccia utente: 

- l'amministratore globale deve optare per il tenant per creare classificatori personalizzati.
- L'amministratore della conformità o il ruolo di analisi dei dati è necessario per formare un classificatore.

Sono necessari account con queste autorizzazioni per l'utilizzo dei classificatori in questi scenari:

- Scenario dei criteri per l'etichetta di conservazione: ruoli Gestione record e gestione conservazione 
- Scenario di criteri per le etichette di riservatezza: amministratore della sicurezza, amministratore conformità, amministratore dei dati di conformità
- Scenario di criteri di conformità della comunicazione: amministratore di gestione dei rischi Insider, Responsabile Revisione di supervisione 

> [!IMPORTANT]
> Per impostazione predefinita, solo l'utente che crea un classificatore personalizzato può formare ed esaminare le stime eseguite dal classificatore. Se si desidera che gli altri utenti siano in grado di formare e rivedere le stime del classificatore, vedere [Give others Train and Review Rights](#give-others-train-and-review-rights).

## <a name="prepare-for-a-custom-trainable-classifier"></a>Prepararsi per un classificatore addestrabile personalizzato 

È utile comprendere cosa è coinvolto nella creazione di un classificatore addestrabile personalizzato prima dell'immersione. 

### <a name="timeline"></a>Sequenza temporale

Questa sequenza temporale riflette una distribuzione di esempio dei classificatori addestrabili.

![addestrare-classificatore-sequenza temporale](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> L'opzione opt-in è necessaria per la prima volta per i classificatori addestrabili. Per completare una valutazione di base del contenuto delle organizzazioni, sono necessari dodici giorni per Microsoft 365. Contattare l'amministratore globale per iniziare a utilizzare il processo di opt-in.

### <a name="overall-workflow"></a>Flusso di lavoro globale

Per ulteriori informazioni sul flusso di lavoro globale della creazione di classificatori addestrabili personalizzati, vedere [flow Process per la creazione di classificatori addestrabili per i clienti](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).

### <a name="seed-content"></a>Contenuto del seeding

Quando si desidera che un classificatore addestrabile sia in grado di identificare in modo indipendente e accurato un elemento come in particolare la categoria di contenuto, è necessario innanzitutto presentarlo con numerosi esempi del tipo di contenuto nella categoria. L'alimentazione dei campioni al classificatore addestrabile è nota come *seeding*. Il contenuto del seeding viene selezionato da un essere umano e viene giudicato per rappresentare la categoria di contenuto.

> [!TIP]
> È necessario avere almeno 50 campioni positivi e ben 500. Il classificatore addestrativo elaborerà fino a 500 campioni creati più recenti (per data e timestamp creati dal file). Più esempi vengono forniti, maggiore è la precisione delle stime che verranno apportate dal classificatore.

### <a name="testing-content"></a>Test del contenuto

Dopo che il classificatore addestratore ha elaborato campioni positivi sufficienti per creare un modello di stima, è necessario verificare le stime che consente di verificare se il classificatore può distinguere correttamente tra gli elementi che corrispondono alla categoria e gli elementi che non lo fanno. A tale scopo, selezionare un altro gruppo di contenuto umano raccolto, che è costituito da esempi che devono rientrare nella categoria e gli esempi che non sono necessari. È consigliabile eseguire il test con dati diversi rispetto ai dati di inizializzazione iniziali forniti per la prima volta. Dopo averli elaborati, si procede manualmente ai risultati e si verifica se ogni previsione è corretta, non corretta o non si è certi. Il classificatore addestrabile utilizza questi commenti e suggerimenti per migliorare il modello di stima.

> [!TIP]
> Per ottenere risultati ottimali, è necessario che almeno 200 elementi del campione di test siano distribuiti con una distribuzione uniforme di corrispondenze positive e negative.

## <a name="how-to-create-a-trainable-classifier"></a>Come creare un classificatore addestrabile

1. Raccogliere tra gli elementi di contenuto di 50-500 Seed. Questi devono essere solo campioni che rappresentano fortemente il tipo di contenuto che si desidera che il classificatore addestrabile identifichi positivamente come nella Categoria classificazione. Per i tipi di file supportati, vedere le estensioni di file sottoposte [a ricerca per indicizzazione e i tipi di file analizzati in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) .

   > [!IMPORTANT]
   > Gli elementi di esempio Seed e test non devono essere crittografati e devono essere in inglese.

   > [!IMPORTANT]
   > Verificare che gli elementi del set di Seed siano esempi **forti** della categoria. Il classificatore addestrabile crea inizialmente il modello in base alle operazioni con cui viene eseguito il seeding. Il classificatore presuppone che tutti gli esempi di sementi siano forti positivi e che non sia possibile sapere se un campione è una corrispondenza debole o negativa per la categoria.

2. Inserire il contenuto di inizializzazione in una cartella di SharePoint Online dedicata a contenere *solo il contenuto del seeding*. Prendere nota dell'URL del sito, della raccolta e della cartella.

   > [!TIP]
   > Se si crea un nuovo sito e una nuova cartella per i dati di seeding, è possibile eseguire l'indicizzazione di almeno un'ora affinché tale percorso venga indicizzato prima di creare il classificatore addestrabile che utilizzerà tali dati.

3. Accedere a Microsoft 365 Compliance Center with Compliance admin or Security admin Role Access e aprire **Microsoft 365 Compliance Center** o **Microsoft 365 Security Center**  >  **Data Classification**.

4. Scegliere la scheda **classificatori addestrabili** .

5. Scegliere **Crea classificatore addestrabile**.

6. Inserire i valori adatti per i `Name` `Description` campi e della categoria di elementi che si desidera vengano identificati dal classificatore addestrabile.

7. Scegliere il sito di SharePoint Online, la raccolta e l'URL della cartella per il sito di contenuto Seed del passaggio 2. Scegliere `Add` .

8. Rivedere le impostazioni e scegliere `Create trainable classifier` .

9. Entro 24 ore, il classificatore addestrativo elaborerà i dati di seeding e realizzerà un modello di stima. Lo stato del classificatore è `In progress` durante l'elaborazione dei dati di seeding. Quando il classificatore ha terminato di elaborare i dati di seeding, lo stato cambia in `Need test items` .

10. È ora possibile visualizzare la pagina dei dettagli scegliendo il classificatore.

    > [!div class="mx-imgBorder"]
    > ![classificatore addestrabile pronto per il testing](../media/classifier-trainable-ready-to-test-detail.png)

11. Raccogliere almeno 200 elementi di contenuto di prova (10.000 max) per ottenere risultati ottimali. Queste devono essere una combinazione di elementi che sono forti positivi, negativi forti e alcuni che sono un po' meno evidenti nella loro natura. Per i tipi di file supportati, vedere le estensioni di file sottoposte [a ricerca per indicizzazione e i tipi di file analizzati in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) .

    > [!IMPORTANT]
    > Gli elementi di esempio non devono essere crittografati e devono essere in inglese.

12. Inserire il contenuto del test in una cartella di SharePoint Online dedicata alla conservazione *del solo contenuto del test*. Prendere nota del sito, della raccolta e dell'URL della cartella di SharePoint Online.

    > [!TIP]
    > Se si crea un nuovo sito e una nuova cartella per i dati di test, è possibile che la posizione venga indicizzata per almeno un'ora prima di creare il classificatore addestrabile che utilizzerà tali dati.

13. Scegliere `Add items to test` .

14. Scegliere il sito di SharePoint Online, la raccolta e l'URL della cartella per il sito di contenuto di test dal passaggio 12. Scegliere `Add` .

15. Completare la procedura guidata scegliendo `Done` . Il classificatore addestrabile richiederà fino a un'ora per l'elaborazione dei file di test.

16. Quando si esegue l'elaborazione dei file di test da parte del classificatore addestrabile, lo stato nella pagina dei dettagli cambia `Ready to review` . Se è necessario aumentare le dimensioni del campione di test, scegliere `Add items to test` e consentire al classificatore addestrabile di elaborare gli elementi aggiuntivi.

    > [!div class="mx-imgBorder"]
    > ![pronto per la revisione dello screenshot](../media/classifier-trainable-ready-to-review-detail.png)

17. Scegliere la `Tested items to review` scheda per esaminare gli elementi.

18. Microsoft 365 presenterà 30 elementi alla volta. Verificarli e nella `We predict this item is "Relevant". Do you agree?` casella scegliere uno `Yes` o più `No` o `Not sure, skip to next item` . L'accuratezza del modello viene aggiornata automaticamente dopo ogni 30 elementi.

    > [!div class="mx-imgBorder"]
    > ![casella di controllo elementi](../media/classifier-trainable-review-detail.png)

19. Esaminare *almeno 200 elementi* . Dopo che il Punteggio di accuratezza si è stabilizzato, l'opzione **pubblicazione** diventerà disponibile e lo stato del classificatore diventerà `Ready to use` .

    > [!div class="mx-imgBorder"]
    > ![Punteggio di precisione e pronto per la pubblicazione](../media/classifier-trainable-review-ready-to-publish.png)

20. Pubblicare il classificatore.

21. Dopo aver pubblicato il classificatore sarà disponibile come condizione in [Office auto-Labeling con etichette di riservatezza](apply-sensitivity-label-automatically.md), [applicare automaticamente i criteri delle etichette di conservazione in base a una condizione](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) e in [conformità alla comunicazione](communication-compliance.md).

## <a name="give-others-train-and-review-rights"></a>Concedere a altri i diritti di treno e Revisione

Utilizzare questa procedura per concedere ad altri utenti le autorizzazioni per la formazione, la revisione e la ottimizzazione del classificatore addestrabile personalizzato.  
 
1. In qualità di creatore del classificatore, un amministratore globale o un amministratore di eDiscovery si connettono al centro conformità tramite PowerShell utilizzando le procedure descritte in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps&preserve-view=true).

2. Eseguire questo comando:

   ```powershell
   Add-ComplianceCaseMember -Case "<classifier name>" -Member "<user or role group>"
   ```
   
   Ad esempio:
   
   `Add-ComplianceCaseMember -Case "Financial Contract Classifier" -Member johnevans@contoso.com`

   È possibile eseguire questo comando più volte per aggiungere più utenti. Si noti che è possibile aggiungere solo gruppi di ruoli di Exchange Online Protection (EOP) e non gruppi di ruoli di Azure.
