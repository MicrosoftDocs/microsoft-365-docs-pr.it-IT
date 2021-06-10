---
title: Classificazione dei dati per l'ambiente di Microsoft 365 per l'ambiente di testing aziendale
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
description: Utilizzare questa guida al laboratorio di testing per creare e usare le etichette di conservazione nei documenti nell'ambiente di Microsoft 365 per l'ambiente di testing aziendale.
ms.openlocfilehash: 613aa3713b4d72eed1bc0b2d88f70a817d0e7cff
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919189"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>Classificazione dei dati per l'ambiente di Microsoft 365 per l'ambiente di testing aziendale

*Questa guida al laboratorio di testing può essere usata sia per gli ambienti Microsoft 365 aziendali che per Office 365 Enterprise test.*

In questo articolo viene descritto come configurare la classificazione dei dati utilizzando le etichette di conservazione nell'Microsoft 365 per l'ambiente di testing aziendale.

La classificazione dei dati nell'ambiente di testing prevede tre fasi:
- [Fase 1: creare l'ambiente di testing Microsoft 365 per le aziende](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: creare etichette di conservazione](#phase-2-create-retention-labels)
- [Fase 3: applicare etichette di conservazione ai documenti](#phase-3-apply-retention-labels-to-documents)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Per una mappa visiva a tutti gli articoli dello stack Microsoft 365 per enterprise Test Lab Guide, passare a [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing Microsoft 365 per le aziende

Se si desidera solo configurare le etichette di conservazione in modo leggero con i requisiti minimi, seguire le istruzioni in [Configurazione di base lightweight](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera configurare le etichette di conservazione in un'organizzazione simulata, seguire le istruzioni in [Autenticazione pass-through.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Il test delle etichette di conservazione non richiede l'ambiente di testing aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di Servizi di dominio Active Directory. Viene fornito qui come opzione in modo da poter testare le licenze automatizzate e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.

## <a name="phase-2-create-retention-labels"></a>Fase 2: creare etichette di conservazione

In questa fase, creare le etichette di conservazione per i diversi livelli di conservazione per SharePoint cartelle documenti online:

1. Accedi al Centro sicurezza [Microsoft 365 con](https://security.microsoft.com/homepage) il tuo account amministratore globale.
1. Nella scheda **Home - Microsoft 365 sicurezza** del browser selezionare Etichette **di** conservazione  >  **classificazione.**
1. Selezionare **Crea un'etichetta**.
1. Nel riquadro **Assegnare un nome** all'etichetta immettere **Internal Public** in Name **your label** e quindi selezionare **Next.**
1. Nel riquadro **Descrittori piano file** selezionare **Avanti.**
1. Nel riquadro **Impostazioni etichetta,** se necessario, impostare **Conservazione** su **Su** e quindi selezionare **Avanti.**
1. Nel riquadro **Rivedi le impostazioni** seleziona **Crea l'etichetta.**
1. Ripetere i passaggi da 3 a 7 per altre etichette con i nomi seguenti:
  - Private
  - Dati sensibili
  - Highly Confidential (Riservatezza elevata)
1. Nel riquadro **Etichette di conservazione** selezionare Pubblica **etichette.**
1. Nel riquadro **Scegliere le etichette da pubblicare** selezionare Scegliere le etichette da **pubblicare.**
1. Nel riquadro **Scegli etichette** selezionare **Aggiungi e** selezionare tutte e quattro le etichette.
1. Selezionare **Aggiungi** e quindi Fare **clic su Fine.**
1. Nel riquadro **Scegliere le etichette da pubblicare** selezionare **Avanti.**
1. Nel riquadro **Scegli posizioni** selezionare **Avanti.**
1. Nel riquadro **Assegnare un nome al** criterio immettere **Organizzazione di esempio** in **Nome** e quindi selezionare **Avanti.**
1. Nel riquadro **Rivedere le impostazioni** selezionare Pubblica **etichette.**
 
La pubblicazione delle etichette di conservazione potrebbe richiedere alcuni minuti.

## <a name="phase-3-apply-retention-labels-to-documents"></a>Fase 3: applicare etichette di conservazione ai documenti

In questa fase si individua il comportamento predefinito delle etichette di conservazione per i file nella cartella Documenti di un sito di SharePoint Online e si modifica manualmente l'etichetta di conservazione di un documento.

Innanzitutto, creare un sito del team di SharePoint online a livello sensibile:
  
1. Usando un'istanza privata del browser, accedi [all'Microsoft 365 di amministrazione](https://admin.microsoft.com) usando il tuo account di amministratore globale.
1. Nell'elenco dei riquadri selezionare **SharePoint**.
1. Nella nuova **scheda SharePoint** nel browser selezionare Crea **sito.**
1. Nella pagina **Crea sito** selezionare Sito **del team**.
1. Nella casella **Nome sito del** team immettere **SensitiveFiles**.
1. Nella casella **Descrizione sito del** team immettere SharePoint **per i file riservati.**
1. In **Impostazioni privacy** selezionare Privato : solo i membri possono accedere al **sito** e quindi selezionare **Avanti.**
1. Nel riquadro **Who aggiungere?** selezionare **Fine.**
    
Configurare quindi la cartella Documenti del sito del team SensitiveFiles per l'etichetta di conservazione Sensitive.
  
1. Nella scheda **SensitiveFiles** del browser selezionare **Documenti**.
1. Selezionare **l Impostazioni** e quindi selezionare **Impostazioni raccolta.**
1. In **Autorizzazioni e gestione** selezionare Applica etichetta agli elementi **dell'elenco o della raccolta.** Se questa opzione non viene visualizzata, le etichette di conservazione non sono ancora state pubblicate. Provare questo passaggio in un secondo momento.
1. In **Impostazioni-Applica etichetta** selezionare **Sensibile** nella casella di riepilogo a discesa e quindi selezionare **Salva.**

Successivamente, creare un nuovo documento nel sito SensitiveFiles e modificarne l'etichetta di conservazione.
    
1. Nella cartella documenti selezionare **Nuovo documento**  >  **di Word.**
1. Immettere del testo nel documento vuoto. Attendere il salvataggio del testo.
1. Sulla barra dei menu selezionare **Documenti condivisi**.
1. Accanto al nome **Document.docx** file, selezionare i puntini di sospensione verticali e quindi selezionare **Dettagli**.
1. Nella sezione Proprietà del  riquadro destro, in Applica etichetta di **conservazione,** si noti che al documento è stata applicata automaticamente l'etichetta di conservazione Sensibile. 
1. Fare **clic su Modifica tutto.**
1. Nel riquadro **Document.docx,** in Applica etichetta **di conservazione,** selezionare l'etichetta **Estremamente riservato** e quindi selezionare **Salva**.

## <a name="next-step"></a>Passaggio successivo

Esplorare ulteriori [funzionalità e funzionalità di](m365-enterprise-test-lab-guides.md#information-protection) protezione delle informazioni nell'ambiente di testing.

## <a name="see-also"></a>Vedere anche

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Documentazione di Microsoft 365 for enterprise](/microsoft-365-enterprise/)