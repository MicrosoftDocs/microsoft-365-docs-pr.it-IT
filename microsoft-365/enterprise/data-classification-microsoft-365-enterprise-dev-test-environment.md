---
title: Classificazione dei dati per l'ambiente di testing Microsoft 365 Enterprise
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
description: Utilizzare questa guida del laboratorio di testing per creare e utilizzare etichette di conservazione nei documenti dell'ambiente di testing di Microsoft 365 Enterprise.
ms.openlocfilehash: 41873eba8f2d6168d68d771c6feb17a44c775f6a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636093"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a>Classificazione dei dati per l'ambiente di testing Microsoft 365 Enterprise

*Questa guida al lab di test può essere usata sia per ambienti di testing di Microsoft 365 Enterprise che Office 365 Enterprise.*

Con le istruzioni riportate in questo articolo, è possibile configurare la classificazione dei dati utilizzando le etichette di conservazione nell'ambiente di testing Microsoft 365 Enterprise.

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Fare clic [qui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Creare l'ambiente di testing di Microsoft 365 Enterprise

Se si desidera solo configurare le etichette di conservazione in modo semplice con i requisiti minimi, seguire le istruzioni in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera configurare le etichette di conservazione in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La verifica delle etichette di conservazione non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS). Viene fornito come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica. 

## <a name="phase-2-create-retention-labels"></a>Fase 2: creare etichette di conservazione

In questa fase, vengono create le etichette di conservazione per i diversi livelli di conservazione per le cartelle di documenti di SharePoint Online.

1. Accedere al [Centro sicurezza Microsoft 365](https://security.microsoft.com/homepage) con l'account di amministratore globale.
    
2. Dalla scheda **sicurezza Home-Microsoft 365** del browser, fare clic su **classificazione > etichette di conservazione**.
    
3. Fare clic su **Crea un'etichetta**.
    
4. Nel riquadro **Name Your label** , digitare **Public Internal** in **Name Your label**, quindi fare clic su **Next**.

5. Nel riquadro dei **descrittori del piano file** fare clic su **Avanti**.
    
6. Nel riquadro **Impostazioni etichetta** , se necessario, impostare la **conservazione** **su**attivato e quindi fare clic su **Avanti**.
    
7. Nel riquadro **Verifica le impostazioni** fare clic su **crea l'etichetta**.
    
8. Ripetere i passaggi da 3 a 7 per altre etichette con i nomi seguenti:
    
  - Private
    
  - Dati sensibili
    
  - Highly Confidential (Riservatezza elevata)
  
9. Nel riquadro **etichette di conservazione** fare clic su **pubblica etichette**.
    
10. Nel riquadro **Scegli etichette** da pubblicare, fare clic su **Scegli etichette da pubblicare**.
    
11. Nel riquadro **Scegli etichette** , fare clic su **Aggiungi** e selezionare le quattro etichette.
    
12. Fare clic su **Aggiungi**e quindi su **fine**.
    
13. Nel riquadro **Choose labels to publish** (Scegli etichette da pubblicare) fare clic su **Avanti**.
    
14. Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Avanti**.
    
15. Nel riquadro **Denomina il criterio** digitare **Example organization** in **Nome**, quindi fare clic su **Avanti**.
    
16. Nel riquadro **Verifica le impostazioni** fare clic su **pubblica etichette**.
 
Tenere presente che potrebbero essere necessari alcuni minuti per la pubblicazione delle etichette di conservazione.

## <a name="phase-3-apply-retention-labels-to-documents"></a>Fase 3: applicare le etichette di conservazione ai documenti

In questa fase, viene individuato il comportamento predefinito dell'etichetta di conservazione per i file nella cartella documenti di un sito di SharePoint Online e viene modificata manualmente l'etichetta di conservazione di un documento.

Per prima cosa, creare un sito del team di SharePoint Online a livello di riserva:
  
1. Se si utilizza un'istanza privata del browser, accedere al [portale di Office 365](https://portal.office.com) utilizzando l'account di amministratore globale.
    
2. Nell'elenco dei riquadri fare clic su **SharePoint**.
    
3. Nella nuova scheda **SharePoint** del browser fare clic su **Crea sito**.
    
4. Nella pagina **Crea sito** fare clic su **Sito del team**.
    
5. In **nome sito del team**digitare **SensitiveFiles**.
    
6. In **Descrizione sito del team**, digitare **sito di SharePoint per i file riservati**.
    
7.  In **Impostazioni privacy** selezionare **Private - only members can access this site** (Privato: solo i membri possono accedere a questo sito) e quindi fare clic su **Avanti**.
    
8. Nel riquadro **chi si desidera aggiungere?** , fare clic su **fine**.
    
Successivamente, configurare la cartella dei documenti del sito del team di SensitiveFiles per l'etichetta di conservazione riservata.
  
1. Nella scheda **SensitiveFiles** del browser fare clic su **documenti**.
    
2. Fare clic sull'icona delle impostazioni e selezionare **Impostazioni libreria**.
    
3. In **autorizzazioni e gestione**fare clic su **Applica etichetta agli elementi contenuti nell'elenco o nella raccolta**. Se questa opzione non viene visualizzata, le etichette di conservazione non vengono ancora pubblicate. Provare questo passaggio in un secondo momento.
    
4. In **impostazioni-Applica etichetta**, selezionare **sensibile** nell'elenco a discesa e quindi fare clic su **Salva**.

Successivamente, creare un nuovo documento nel sito di SensitiveFiles e modificarne l'etichetta di conservazione.
    
1. Nella cartella documenti fare clic su **nuovo > documento di Word**.
    
2. Digitare del testo nel documento vuoto. Attendere che il testo venga salvato.
    
3. Nella barra dei menu fare clic su **documenti condivisi**.
    
4. Fare clic sul pulsante con i puntini di sospensione verticali accanto al nome del file **Document. docx** e quindi fare clic su **Dettagli**.
    
5. Nel riquadro di destra, nella sezione **Proprietà** , in **Apply Retention label**, tenere presente che il documento ha l'etichetta di conservazione **riservata** applicata automaticamente.
    
6. Fare clic su **modifica tutto**.
    
7. Nel riquadro **Document. docx** , in **Apply Retention label**, selezionare l'etichetta **estremamente riservata** , quindi fare clic su **Salva**.

Per informazioni e collegamenti su come distribuire le etichette di conservazione in produzione, vedere la pagina [Configura classificazione per il](infoprotect-configure-classification.md) passaggio dell'ambiente nella fase di **protezione delle informazioni** .

## <a name="next-step"></a>Passaggio successivo

Esplorare le funzionalità e le funzionalità di [protezione delle informazioni](m365-enterprise-test-lab-guides.md#information-protection) aggiuntive nell'ambiente di testing.

## <a name="see-also"></a>Vedere anche

[Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentazione di Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)

 
