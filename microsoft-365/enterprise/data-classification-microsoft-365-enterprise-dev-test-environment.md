---
title: Classificazione dei dati per l'ambiente di testing di Microsoft 365 per l'organizzazione
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Utilizzare questa guida del laboratorio di testing per creare e utilizzare etichette di conservazione nei documenti dell'ambiente di testing di Microsoft 365 per l'organizzazione.
ms.openlocfilehash: 5cc77167db866d99f0beea5f554a777ecf355046
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487733"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>Classificazione dei dati per l'ambiente di testing di Microsoft 365 per l'organizzazione

*Questa guida del laboratorio di testing può essere utilizzata per ambienti di testing Microsoft 365 per Enterprise e Office 365 Enterprise.*

In questo articolo viene descritto come configurare la classificazione dei dati utilizzando le etichette di conservazione nell'ambiente di testing di Microsoft 365 per l'organizzazione.

La classificazione dei dati nell'ambiente di testing comporta tre fasi:
- [Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: creare etichette di conservazione](#phase-2-create-retention-labels)
- [Fase 3: applicare le etichette di conservazione ai documenti](#phase-3-apply-retention-labels-to-documents)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Per una mappa visiva su tutti gli articoli della guida del laboratorio di testing di Microsoft 365 for Enterprise, accedere a [microsoft 365 per la guida dello stack del laboratorio di testing dell'organizzazione](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione

Se si desidera solo configurare le etichette di conservazione in modo semplice con i requisiti minimi, seguire le istruzioni in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera configurare le etichette di conservazione in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La verifica delle etichette di conservazione non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS). È disponibile come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.

## <a name="phase-2-create-retention-labels"></a>Fase 2: creare etichette di conservazione

In questa fase, creare le etichette di conservazione per i diversi livelli di conservazione per le cartelle di documenti di SharePoint Online:

1. Accedere al [Centro sicurezza Microsoft 365](https://security.microsoft.com/homepage) con l'account di amministratore globale.
1. Dalla scheda **sicurezza Home-Microsoft 365** del browser selezionare etichette di conservazione per la **classificazione**  >  **Retention labels**.
1. Selezionare **Crea un'etichetta**.
1. Nel riquadro **Name Your label** , immettere **public interno** in **nome dell'etichetta**, quindi selezionare **Avanti**.
1. Nel riquadro dei **descrittori del piano file** , selezionare **Avanti**.
1. Nel riquadro **Impostazioni etichetta** , se necessario, impostare **conservazione** **su**attivato, quindi selezionare **Avanti**.
1. Nel riquadro **Verifica le impostazioni** fare clic su **crea l'etichetta**.
1. Ripetere i passaggi da 3 a 7 per altre etichette con i nomi seguenti:
  - Private
  - Dati sensibili
  - Highly Confidential (Riservatezza elevata)
1. Nel riquadro **etichette di conservazione** , selezionare **pubblica etichette**.
1. Nel riquadro **Scegli etichette** da pubblicare, seleziona **Scegli etichette da pubblicare**.
1. Nel riquadro **Scegli etichette** , selezionare **Aggiungi** e selezionare le quattro etichette.
1. Selezionare **Aggiungi**, quindi fare clic su **fine**.
1. Nel riquadro **Scegli etichette da pubblicare** selezionare **Avanti**.
1. Nel riquadro **Scegli percorsi** scegliere **Avanti**.
1. Nel riquadro **denomina il criterio** , immettere l' **organizzazione di esempio** in **nome**e quindi fare clic su **Avanti**.
1. Nel riquadro **Verifica le impostazioni** fare clic su **pubblica etichette**.
 
Per la pubblicazione delle etichette di conservazione, potrebbero essere necessari alcuni minuti.

## <a name="phase-3-apply-retention-labels-to-documents"></a>Fase 3: applicare le etichette di conservazione ai documenti

In questa fase, viene individuato il comportamento predefinito dell'etichetta di conservazione per i file nella cartella documenti di un sito di SharePoint Online e viene modificata manualmente l'etichetta di conservazione di un documento.

Per prima cosa, creare un sito del team di SharePoint Online a livello di riserva:
  
1. Se si utilizza un'istanza privata del browser, accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando l'account di amministratore globale.
1. Nell'elenco dei riquadri selezionare **SharePoint**.
1. Nella nuova scheda **SharePoint** del browser, selezionare **Crea sito**.
1. Nella pagina **Crea sito** fare clic su **sito del team**.
1. Nella casella **nome sito del team** , immettere **SensitiveFiles**.
1. Nella casella **Descrizione sito del team** , immettere il **sito di SharePoint per i file riservati**.
1. In **impostazioni di privacy**, selezionare **membri solo privati possono accedere a questo sito**, quindi selezionare **Avanti**.
1. Nel riquadro **chi si desidera aggiungere?** , selezionare **fine**.
    
Successivamente, configurare la cartella dei documenti del sito del team di SensitiveFiles per l'etichetta di conservazione riservata.
  
1. Nella scheda **SensitiveFiles** del browser selezionare **documenti**.
1. Selezionare l'icona **Impostazioni** , quindi selezionare **Impostazioni raccolta**.
1. In **autorizzazioni e gestione**selezionare **Applica etichetta agli elementi contenuti nell'elenco o nella raccolta**. Se questa opzione non viene visualizzata, le etichette di conservazione non vengono ancora pubblicate. Provare questo passaggio in un secondo momento.
1. In **impostazioni-Applica etichetta**, selezionare **sensibile** nell'elenco a discesa e quindi fare clic su **Salva**.

Successivamente, creare un nuovo documento nel sito di SensitiveFiles e modificarne l'etichetta di conservazione.
    
1. Nella cartella documenti selezionare **nuovo**  >  **documento di Word**.
1. Immettere del testo nel documento vuoto. Attendere che il testo venga salvato.
1. Sulla barra dei menu, selezionare **documenti condivisi**.
1. Accanto al nome del file **Document.docx** , selezionare i puntini di sospensione verticali e quindi fare clic su **Dettagli**.
1. Nel riquadro a destra, nella sezione **Proprietà** , in **Apply Retention label**, tenere presente che il documento ha l'etichetta di conservazione **riservata** applicata automaticamente.
1. Fare clic su **modifica tutto**.
1. Nel riquadro **Document.docx** , in **Applica etichetta di conservazione**, selezionare l'etichetta **estremamente riservata** e quindi fare clic su **Salva**.

## <a name="next-step"></a>Passaggio successivo

Esplorare le funzionalità e le funzionalità di [protezione delle informazioni](m365-enterprise-test-lab-guides.md#information-protection) aggiuntive nell'ambiente di testing.

## <a name="see-also"></a>Vedere anche

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Microsoft 365 per la documentazione relativa all'organizzazione](https://docs.microsoft.com/microsoft-365-enterprise/)
