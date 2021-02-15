---
title: Aumentare la protezione dalle minacce per Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Configurare le funzionalità di conformità per evitare la perdita di dati e proteggere le informazioni riservate dei clienti.
ms.openlocfilehash: 2c95ad3f36df28af2c68cd11192bcfe92dfe29e3
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841174"
---
# <a name="set-up-compliance-features"></a>Funzionalità di conformità della configurazione

Microsoft 365 Business Premium include funzionalità per proteggere i dati e i dispositivi e consente di proteggere le informazioni riservate dei clienti.

## <a name="set-up-dlp-features"></a>Configurare le funzionalità DLP

Vedere [Creare un criterio DLP da un modello](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) per un esempio su come configurare un criterio per la protezione dalla perdita di dati personali. 
  
DLP include molti modelli di criteri pronti all'uso per molte impostazioni locali diverse. Ad esempio, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data e così via. Vedere [Cosa includono i modelli di criteri DLP per](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) un elenco completo. Tutti questi modelli possono essere abilitati in modo simile all'esempio di modello di informazioni personali. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Configurare la conservazione della posta elettronica con Archiviazione Exchange Online

 **Archiviazione Exchange Online** licenze consentono di mantenere gli standard normativi e di conformità preservando il contenuto della posta elettronica per eDiscovery. Consente inoltre di ridurre i rischi in caso di un'azione legale e consente di recuperare i dati dopo una violazione della sicurezza o quando è necessario recuperare gli elementi eliminati. È possibile utilizzare la conservazione per controversia legale per conservare tutto il contenuto di un utente o utilizzare i criteri di conservazione per personalizzare ciò che si desidera conservare.
  
**Conservazione per controversia legale:** È possibile conservare tutto il contenuto della cassetta postale, inclusi gli elementi eliminati, inserendo l'intera cassetta postale di un utente in conservazione per controversia legale. 
    
Per impostare la conservazione per controversia legale in una cassetta postale, nell'interfaccia di amministrazione:
    
1. Nel riquadro di spostamento sinistro passare a **Utenti** \> **attivi.**
    
2. Selezionare un utente di cui si desidera mantenere la conservazione per controversia legale nella cassetta postale. Nel riquadro degli utenti espandere **Impostazioni posta** e accanto ad **Altre impostazioni** scegliere Modifica proprietà **di Exchange.**
    
3. On the mailbox page for the user, choose ** mailbox features ** on the left nav, and then choose the **Enable** link under **Litigation hold**.
    
4. Nella finestra **di dialogo di conservazione** per controversia legale è possibile specificare la durata della conservazione per controversia legale nel campo Durata blocco per **controversia** legale. Lasciare vuoto il campo se si desidera inserire un'esenzione infinita. È inoltre possibile aggiungere note e indirizzare il proprietario della cassetta postale a un sito Web che potrebbe essere necessario spiegare di più sulla conservazione per controversia legale. \>**Salva**.
    
**Conservazione:** È possibile abilitare criteri di conservazione personalizzati, ad esempio, per conservare per un periodo di tempo specifico o eliminare definitivamente il contenuto alla fine del periodo di conservazione. Per ulteriori informazioni, vedere [Panoramica dei criteri di conservazione.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

## <a name="set-up-sensitivity-labels"></a>Configurare le etichette di riservatezza

Le etichette di riservatezza sono disponibili con Azure Information Protection (AIP) Piano 1 e consentono di classificare e facoltativamente proteggere i documenti e i messaggi di posta elettronica applicando etichette. Le etichette possono essere applicate automaticamente dagli amministratori che definiscono regole e condizioni, manualmente dagli utenti o utilizzando una combinazione in cui agli utenti vengono forniti suggerimenti.

Per configurare le etichette di riservatezza, visualizzare il video [per creare e gestire le etichette di](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) riservatezza.



### <a name="install-the-azure-information-protection-client-manually"></a>Installare manualmente il client Azure Information Protection

Per installare manualmente il client AIP:

1. Scaricare **AzinfoProtection_UL.exe** dall'Area [download Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)
 
2. È possibile verificare che l'installazione sia stata completata  visualizzando un documento di Word e verificando che l'opzione Riservatezza sia disponibile nella **scheda** Home.
<br/>![Elenco a discesa Della scheda Protezione in un documento di Word.](../media/word-sensitivity.png)

Per ulteriori informazioni, vedere [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).
