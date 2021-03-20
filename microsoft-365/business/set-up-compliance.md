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
ms.openlocfilehash: e210787718025c5df29af8d4a2283291dcecc2a8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912531"
---
# <a name="set-up-compliance-features"></a>Funzionalità di conformità della configurazione

Microsoft 365 Business Premium include funzionalità che consentono di proteggere i dati e i dispositivi e di proteggere le informazioni riservate dei clienti.

## <a name="set-up-dlp-features"></a>Configurare le funzionalità DLP

Per un esempio su come configurare un criterio per la protezione dalla perdita di dati personali, vedere Create [a DLP policy from a](../compliance/create-a-dlp-policy-from-a-template.md) template. 
  
DLP include molti modelli di criteri pronti per l'uso per molte impostazioni locali diverse. Ad esempio, Dati finanziari Australia, Canada Personal Information Act, Dati finanziari statunitensi e così via. Per un elenco completo, vedere What [the DLP policy templates include.](../compliance/what-the-dlp-policy-templates-include.md) Tutti questi modelli possono essere abilitati in modo analogo all'esempio di modello piI. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Configurare la conservazione della posta elettronica con Archiviazione Exchange Online

 **Archiviazione Exchange Online** di licenza consentono di mantenere gli standard normativi e di conformità preservando il contenuto della posta elettronica per eDiscovery. Consente inoltre di ridurre i rischi in caso di cause legali e consente di recuperare i dati dopo una violazione della sicurezza o quando è necessario recuperare gli elementi eliminati. È possibile utilizzare la conservazione per controversia legale per conservare tutto il contenuto di un utente oppure i criteri di conservazione per personalizzare ciò che si desidera conservare.
  
**Conservazione per controversia legale:** È possibile conservare tutto il contenuto della cassetta postale, inclusi gli elementi eliminati, mettendo in conservazione per controversia legale l'intera cassetta postale di un utente. 
    
Per mettere una cassetta postale in conservazione per controversia legale, nell'interfaccia di amministrazione:
    
1. Nel riquadro di spostamento sinistro passare a **Utenti** \> **Utenti attivi**.
    
2. Selezionare un utente di cui si desidera mantenere la cassetta postale per controversia legale. Nel riquadro degli utenti espandere **Impostazioni posta** e accanto a **Altre impostazioni** scegliere Modifica proprietà **di Exchange.**
    
3. Nella pagina della cassetta postale per l'utente, scegliere ** funzionalità della cassetta postale ** sul riquadro di spostamento sinistro, quindi scegliere il collegamento **Abilita** in Conservazione per **controversia legale**.
    
4. Nella finestra **di dialogo conservazione** per controversia legale è possibile specificare la durata della conservazione per controversia legale nel campo Durata conservazione per **controversia** legale. Lasciare vuoto il campo se si desidera inserire un'esenzione infinita. È inoltre possibile aggiungere note e indirizzare il proprietario della cassetta postale a un sito Web che potrebbe essere necessario spiegare di più sulla conservazione per controversia legale. \>**Salva**.
    
**Conservazione:** È possibile abilitare criteri di conservazione personalizzati, ad esempio per conservare per un periodo di tempo specifico o eliminare il contenuto in modo permanente alla fine del periodo di conservazione. Per ulteriori informazioni, vedere [Overview of retention policies](../compliance/retention.md).

## <a name="set-up-sensitivity-labels"></a>Configurare le etichette di riservatezza

Le etichette di riservatezza sono disponibili con Azure Information Protection (AIP) Piano 1 e consentono di classificare e facoltativamente proteggere i documenti e i messaggi di posta elettronica applicando etichette. Le etichette possono essere applicate automaticamente dagli amministratori che definiscono regole e condizioni, manualmente dagli utenti o utilizzando una combinazione in cui agli utenti vengono forniti suggerimenti.

Per configurare le etichette di riservatezza, visualizza il video per [creare e gestire le etichette di riservatezza.](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)



### <a name="install-the-azure-information-protection-client-manually"></a>Installare manualmente il client Azure Information Protection

Per installare manualmente il client AIP:

1. Scaricare **AzinfoProtection_UL.exe** dall'Area [download Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)
 
2. È possibile verificare che l'installazione sia stata completata  visualizzando un documento di Word e verificando che l'opzione Riservatezza sia disponibile nella **scheda Home.**
<br/>![Menu a discesa Della scheda Protezione in un documento di Word.](../media/word-sensitivity.png)

Per ulteriori informazioni, vedere [Install the client](/azure/information-protection/infoprotect-tutorial-step3).