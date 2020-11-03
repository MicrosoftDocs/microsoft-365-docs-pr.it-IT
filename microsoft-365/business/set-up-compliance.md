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

Microsoft 365 Business Premium è dotato di funzionalità per proteggere i dati e i dispositivi, nonché per garantire la sicurezza delle informazioni riservate e dei clienti.

## <a name="set-up-dlp-features"></a>Configurare le funzionalità DLP

Vedere [creare un criterio DLP da un modello](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) per un esempio su come impostare un criterio per proteggere la protezione dalla perdita dei dati personali. 
  
DLP viene fornito con molti modelli di criteri pronti per l'uso per molte impostazioni locali diverse. Ad esempio, Australia Financial Data, Canada Personal Information Act, US Financial Data e così via. Vedere [cosa includono i modelli di criteri DLP](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) per un elenco completo. Tutti questi modelli possono essere abilitati in modo analogo all'esempio del modello PII. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Configurare la conservazione della posta elettronica con archiviazione Exchange Online

 Le funzionalità di licenza di **archiviazione di Exchange Online** aiutano a mantenere la conformità e gli standard normativi preservando il contenuto della posta elettronica per eDiscovery. Consente inoltre di ridurre il rischio se esiste una causa legale e consente di recuperare i dati dopo una violazione della sicurezza o quando è necessario recuperare gli elementi eliminati. È possibile utilizzare il blocco per controversia legale per mantenere tutto il contenuto di un utente o utilizzare i criteri di conservazione per personalizzare gli elementi che si desidera conservare.
  
**Blocco per controversia legale:** È possibile mantenere tutti i contenuti delle cassette postali, compresi gli elementi eliminati, inserendo l'intera cassetta postale di un utente sul blocco per controversia legale. 
    
Per inserire una cassetta postale per il blocco per controversia legale, nell'interfaccia di amministrazione:
    
1. Nella barra di spostamento a sinistra, passare a utenti attivi degli **utenti** \> **Active users** .
    
2. Selezionare un utente la cui cassetta postale si desidera inserire nel blocco per controversia legale. Nel riquadro utente espandere Impostazioni di **posta elettronica** e accanto a **altre impostazioni** scegliere **modifica proprietà di Exchange** .
    
3. Nella pagina Cassetta postale per l'utente, scegliere * * funzionalità cassetta postale * * sulla barra di spostamento sinistra e quindi scegliere il collegamento **attiva** in **blocco per controversia legale** .
    
4. Nella finestra di dialogo **blocco per controversia legale** , è possibile specificare la durata del blocco per controversia legale nel campo **Durata blocco** per controversia legale. Lasciare vuoto il campo se si desidera inserire un blocco infinito. È inoltre possibile aggiungere note e indirizzare il proprietario della cassetta postale a un sito Web potrebbe essere necessario spiegarne di più sul blocco per controversia legale. \>**Save** .
    
**Conservazione:** È possibile abilitare i criteri di conservazione personalizzati, ad esempio per mantenere un determinato intervallo di tempo o eliminare il contenuto in modo permanente alla fine del periodo di conservazione. Per ulteriori informazioni, vedere [Overview of Retention Policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies).

## <a name="set-up-sensitivity-labels"></a>Configurare le etichette di riservatezza

Le etichette di riservatezza sono dotate di Azure Information Protection (AIP) piano 1 e consentono di classificare e, facoltativamente, proteggere i documenti e i messaggi di posta elettronica applicando etichette. Le etichette possono essere applicate automaticamente dagli amministratori che definiscono le regole e le condizioni, manualmente dagli utenti o utilizzando una combinazione in cui gli utenti ricevono consigli.

Per impostare le etichette di riservatezza, vedere [creare e gestire le etichette di riservatezza](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.



### <a name="install-the-azure-information-protection-client-manually"></a>Installare il client Azure Information Protection manualmente

Per installare manualmente il client AIP:

1. Scaricare **AzinfoProtection_UL.exe** dall' [area download Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).
 
2. È possibile verificare che l'installazione abbia avuto esito positivo visualizzando un documento di Word e assicurandosi che l'opzione **sensitivity** sia disponibile nella scheda **Home** .
<br/>![Elenco a discesa della scheda protezione in un documento di Word.](../media/word-sensitivity.png)

Per ulteriori informazioni, vedere [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).
