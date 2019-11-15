---
title: Classificazione dei dati per l'ambiente di testing Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Utilizzare questa guida del laboratorio di testing per creare e utilizzare le etichette di conservazione di Office 365 nei documenti nell'ambiente di testing di Microsoft 365 Enterprise.
ms.openlocfilehash: 1bcd3ab2d8069ad85d48ecf682d3b7d49e7cf739
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639786"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a>Classificazione dei dati per l'ambiente di testing Microsoft 365 Enterprise

Con le istruzioni riportate in questo articolo, è possibile configurare la classificazione dei dati utilizzando le etichette di conservazione di Office 365 nell'ambiente di testing di Microsoft 365 Enterprise.

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Fare clic [qui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Creare l'ambiente di testing di Microsoft 365 Enterprise

Se si desidera solo configurare le etichette di conservazione di Office 365 in modo semplice con i requisiti minimi, seguire le istruzioni contenute in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera configurare le etichette di conservazione di Office 365 in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testing Office 365 le etichette di conservazione non richiedono l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS). Viene fornito come opzione in modo che sia possibile testare la licenza automatizzata e l'appartenenza ai gruppi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica. 

## <a name="phase-2-create-office-365-retention-labels"></a>Fase 2: creare etichette di conservazione di Office 365

In questa fase, vengono create le etichette di conservazione per i diversi livelli di conservazione per le cartelle di documenti di SharePoint Online.

1. Accedere al [portale Conformità Microsoft 365](https://compliance.microsoft.com) con l'account di amministratore globale.
    
2. Dalla scheda **Home: Conformità Microsoft 365** del browser fare clic su **Classificazioni > Etichette**.
    
3. Fare clic su **Etichette di conservazione > Crea un'etichetta**.
    
4. Nel riquadro **Assegnare un nome all'etichetta** digitare **Internal Public****** e quindi fare clic su **Avanti**.

5. Nel riquadro **Descrittori del piano di archiviazione** fare clic su **Avanti**.
    
6. Nel riquadro **Impostazioni etichetta** impostare **Conservazione** su **Sì**, se necessario, e quindi fare clic su **Avanti**.
    
7. Nel riquadro **Rivedere le impostazioni** fare clic su **Crea etichetta**.
    
8. Ripetere i passaggi da 3 a 7 per altre etichette con i nomi seguenti:
    
  - Private
    
  - Dati sensibili
    
  - Highly Confidential (Riservatezza elevata)
  
9. Dal riquadro **Home > Etichette** fare clic su **Publish labels** (Pubblica etichette).
    
10. Nel riquadro **Choose labels to publish** (Scegli etichette da pubblicare) fare clic su **Choose labels to publish** (Scegli etichette da pubblicare).
    
11. Nel riquadro **Choose labels** (Scegli etichette) fare clic su **Aggiungi** e selezionare le quattro etichette.
    
12. Fare clic su **Fine**.
    
13. Nel riquadro **Choose labels to publish** (Scegli etichette da pubblicare) fare clic su **Avanti**.
    
14. Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Avanti**.
    
15. Nel riquadro **Denomina il criterio** digitare **Example organization** in **Nome**, quindi fare clic su **Avanti**.
    
16. Nel riquadro **Verifica le impostazioni** fare clic su **Publish labels** (Pubblica etichette), quindi fare clic su **Chiudi**.
 
Tenere presente che potrebbero essere necessari alcuni minuti per la pubblicazione delle etichette di conservazione.

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a>Fase 3: applicare le etichette di conservazione di Office 365 ai documenti

In questa fase, viene individuato il comportamento predefinito dell'etichetta di conservazione per i file nella cartella documenti di un sito di SharePoint Online e viene modificata manualmente l'etichetta di conservazione di un documento.

Per prima cosa, creare un sito del team di SharePoint Online a livello di riserva:
  
1. Usando un browser sul computer locale, accedere al [portale di Office 365](https://portal.office.com) con il proprio account amministratore globale.
    
2. Nell'elenco dei riquadri fare clic su **SharePoint**.
    
3. Nella nuova scheda **SharePoint** del browser fare clic su **Crea sito**.
    
4. Nella pagina **Crea sito** fare clic su **Sito del team**.
    
5. In **nome sito del team**digitare **SensitiveFiles**.
    
6. In **Descrizione sito del team**, digitare **sito di SharePoint per i file riservati**.
    
7.  In **Impostazioni privacy** selezionare **Private - only members can access this site** (Privato: solo i membri possono accedere a questo sito) e quindi fare clic su **Avanti**.
    
8. Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.
    
Successivamente, configurare la cartella dei documenti del sito del team di SensitiveFiles per l'etichetta di conservazione riservata.
  
1. Nella scheda **SensitiveFiles** del browser fare clic su **documenti**.
    
2. Fare clic sull'icona delle impostazioni e selezionare **Impostazioni raccolta**.
    
3. In **Autorizzazioni e gestione** fare clic su **Apply label to items in this library** (Applica etichetta agli elementi in questa libreria).
    
4. In **impostazioni-Applica etichetta**, selezionare **sensibile** nell'elenco a discesa e quindi fare clic su **Salva**.

Successivamente, creare un nuovo documento nel sito di SensitiveFiles e modificarne l'etichetta di conservazione.
    
1. Nella cartella documenti fare clic su **nuovo > documento di Word**.
    
2. Digitare del testo nel documento vuoto. Attendere che il testo venga salvato.
    
3. Nella barra dei menu fare clic su **documenti condivisi**.
    
4. Fare clic sull'icona di Word accanto al nome del file **Document. docx** .
    
5. Nel riquadro di destra, nella sezione **Proprietà** , in **Applica etichetta di conservazione**, tenere presente che il documento ha l'etichetta **riservata** applicata automaticamente.
    
6. Fare clic su **modifica tutto**.
    
7. Nel riquadro **Document. docx** , in **Applica etichetta**, selezionare l'etichetta **estremamente riservata** , quindi fare clic su **Salva**.

Per informazioni e collegamenti su come distribuire le etichette di conservazione di Office 365 in produzione, vedere la pagina [Configura classificazione per il](infoprotect-configure-classification.md) passaggio dell'ambiente nella fase di **protezione delle informazioni** .

## <a name="next-step"></a>Passaggio successivo

Esplorare le funzionalità e le funzionalità di [protezione delle informazioni](m365-enterprise-test-lab-guides.md#information-protection) aggiuntive nell'ambiente di testing.

## <a name="see-also"></a>Vedere anche

[Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentazione di Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)

 