---
title: Ambiente di testing di classificazione dei dati per la propria azienda 365 Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Utilizzare questa guida dei laboratori di testing per creare e utilizzare le etichette di Office 365 su documenti nell'ambiente di test Microsoft 365 aziendale.
ms.openlocfilehash: 718cf038d88f1431ec6ca6fce1554d4f44dc1cb7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868893"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a>Ambiente di testing di classificazione dei dati per la propria azienda 365 Microsoft

Con le istruzioni riportate in questo articolo, si configura la classificazione dei dati utilizzando le etichette di Office 365 nell'ambiente di test Microsoft 365 Enterprise.

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Preparare l'ambiente di testing Microsoft 365 Enterprise

Se si desidera configurare le etichette di Office 365 in un modo semplice con i requisiti minimi, seguire le istruzioni di [configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera configurare le etichette di Office 365 in un'azienda simulata, seguire le istruzioni [nell'autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testare le etichette di Office 365 non richiede l'ambiente di testing simulato enterprise, che include una rete intranet simulata connessione a Internet e la sincronizzazione delle directory per una foresta Windows Server Active Directory. Viene fornito qui come un'opzione in modo che sia possibile testare gestione automatica delle licenze e l'appartenenza al gruppo e sperimentare in un ambiente che rappresenta una tipica organizzazione. 

## <a name="phase-2-create-office-365-labels"></a>Fase 2: creare etichette di Office 365

In questa fase è creare etichette per i diversi livelli di protezione per la cartella documenti di SharePoint Online.
  
1. Se necessario, utilizzare un'istanza del browser Internet privata e accedere al portale di Office 365 con l'account di amministratore globale. Per ulteriori informazioni, vedere [la posizione in cui eseguire l'accesso a Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Dalla scheda **Microsoft Office Home** fare clic sul riquadro **Amministratore**.
    
3. Dalla nuova scheda **Interfaccia di amministrazione di Office** del browser fare clic su **Interfacce di amministrazione > Sicurezza e conformità**.
    
4. Dalla nuova scheda **Home: Sicurezza e conformità** del browser fare clic su Classificazioni > Etichette.
    
5. Dal riquadro **Home > Etichette** fare clic su **Crea un'etichetta**.
    
6. Nel riquadro **Name your label** (Denomina l'etichetta) digitare **Internal Public**, quindi fare clic su **Avanti**.
    
7. Nel riquadro **Label settings** (Importazioni etichetta) fare clic su **Avanti**.
    
8. Nel riquadro **Verifica le impostazioni** fare clic su **Crea questa etichetta** e fare clic su **Chiudi**.
    
9. Ripetere i passaggi 5-8 per queste etichette aggiuntive:
    
  - Private
    
  - Dati sensibili
    
  - Highly Confidential (Riservatezza elevata)
    
10. Dal riquadro **Home > Etichette** fare clic su **Publish labels** (Pubblica etichette).
    
11. Nel riquadro **Choose labels to publish** (Scegli etichette da pubblicare) fare clic su **Choose labels to publish** (Scegli etichette da pubblicare).
    
12. Nel riquadro **Choose labels** (Scegli etichette) fare clic su **Aggiungi** e selezionare le quattro etichette.
    
13. Fare clic su **Fine**.
    
14. Nel riquadro **Choose labels to publish** (Scegli etichette da pubblicare) fare clic su **Avanti**.
    
15. Nel riquadro **Choose locations** (Scegli posizioni) fare clic su **Avanti**.
    
16. Nel riquadro **Denomina il criterio** digitare **Example organization** in **Nome**, quindi fare clic su **Avanti**.
    
17. Nel riquadro **Verifica le impostazioni** fare clic su **Publish labels** (Pubblica etichette), quindi fare clic su **Chiudi**.

Si noti che potrebbe richiedere alcuni minuti per le etichette per la pubblicazione.

## <a name="phase-3-apply-office-365-labels-to-documents"></a>Fase 3: Applicare etichette di Office 365 ai documenti

In questa fase, individuare il comportamento di etichetta predefinito per i file nella cartella documenti di un sito di SharePoint Online e modificare manualmente l'etichetta di un documento.

Per prima cosa, creare un sito del team di SharePoint Online riservati livello:
  
1. Usando un browser sul computer locale, accedere al portale di Office 365 con il proprio account amministratore globale. Per informazioni, vedere [Dove accedere a Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Nell'elenco dei riquadri fare clic su **SharePoint**.
    
3. Nella scheda **SharePoint** nuovo nel browser, fare clic su **Crea sito**.
    
4. Nella pagina **Crea sito** fare clic su **Sito del team**.
    
5. **Nome del sito del Team**, digitare **SensitiveFiles**.
    
6. Nella **descrizione del sito del Team**, digitare **sito di SharePoint per i file riservati**.
    
7.  In **Impostazioni privacy** selezionare **Private - only members can access this site** (Privato: solo i membri possono accedere a questo sito) e quindi fare clic su **Avanti**.
    
8. Nel riquadro **Who do you want to add?** (Chi si desidera aggiungere?) fare clic su **Fine**.
    
Configurare quindi la cartella documenti del sito del team SensitiveFiles per l'etichetta riservato.
  
1. Nella scheda **SensitiveFiles** del browser fare clic su **documenti**.
    
2. Fare clic sull'icona delle impostazioni e selezionare **Impostazioni libreria**.
    
3. In **Autorizzazioni e gestione** fare clic su **Apply label to items in this library** (Applica etichetta agli elementi in questa libreria).
    
4. In **Impostazioni si applicano etichetta**, selezionare **riservati** nella casella di riepilogo a discesa e quindi fare clic su **Salva**.

Successivamente, creare un nuovo documento nel sito SensitiveFiles e modificare l'etichetta.
    
1. Nella cartella documenti fare clic su **Nuovo > documento di Word**.
    
2. Digitare un testo nel documento vuoto. Attendere il testo da salvare.
    
3. Nella barra dei menu fare clic su **Documenti condivisi**.
    
4. Fare clic sull'icona Word accanto al nome del file **Document.docx** .
    
5. Nel riquadro di destra, nella sezione **proprietà** , in **Applica etichetta**, si noti che il documento ha avuto l'etichetta **riservati** applicato automaticamente.
    
6. Fare clic su **Modifica tutte**.
    
7. Nel riquadro **Document.docx** , in **Applica etichetta**, selezionare l'etichetta **Altamente riservati** e quindi fare clic su **Salva**.

Nella fase di **protezione delle informazioni** per informazioni e collegamenti a Office 365 etichette nell'ambiente di produzione, vedere la sezione [configurare classificazione per l'ambiente](data-classification-microsoft-365-enterprise-dev-test-environment.md) .

## <a name="next-step"></a>Passaggio successivo

Esplorare le funzionalità aggiuntive [la protezione delle informazioni](m365-enterprise-test-lab-guides.md#information-protection) e le funzionalità nell'ambiente di testing.

## <a name="see-also"></a>Vedere anche

[Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentazione di Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)

 