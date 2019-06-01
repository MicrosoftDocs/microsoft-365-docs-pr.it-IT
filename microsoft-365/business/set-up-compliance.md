---
title: Aumentare la protezione dalle minacce per Microsoft 365 business
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
search.appverid:
- BCS160
- MET150
description: Configurare Office 365 Advanced Threat Protection e proteggere i dati sensibili.
ms.openlocfilehash: 53741a7726222bb32329a401953be72257df95cc
ms.sourcegitcommit: 7ac06563c6ff034358e8fd3f9298fc426187ade2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668391"
---
# <a name="set-up-compliance-features"></a>Configurare le funzionalità di conformità

Microsoft 365 business è dotato di funzionalità per proteggere i dati e i dispositivi, nonché per garantire la protezione delle informazioni riservate per i propri clienti e le proprie esigenze.

## <a name="set-up-dlp-features"></a>Configurare le funzionalità DLP

Vedere [creare un criterio DLP da un modello](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) per un esempio su come impostare un criterio per proteggere le informazioni personali. 
  
DLP viene fornito con molti modelli di criteri pronti per l'uso per molte impostazioni locali diverse. Ad esempio, Australia Financial Data, Canada Personal Information Act, US Financial Data, ecc. Vedere [cosa includono i modelli di criteri DLP](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) per un elenco completo. Tutti questi modelli possono essere abilitati in modo analogo all'esempio del modello PII. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Configurare la conservazione della posta elettronica con archiviazione Exchange Online

 Le funzionalità di licenza di **archiviazione di Exchange Online** aiutano a mantenere la conformità e gli standard normativi preservando il contenuto della posta elettronica per eDiscovery. Consente inoltre di ridurre i rischi in caso di una querela e consente di recuperare i dati dopo una violazione della sicurezza o quando è necessario recuperare gli elementi eliminati. È possibile utilizzare il blocco per controversia legale per mantenere tutto il contenuto di un utente o utilizzare i criteri di conservazione per personalizzare gli elementi che si desidera conservare.
  
**Blocco per controversia legale:** È possibile mantenere tutti i contenuti delle cassette postali, compresi gli elementi eliminati, inserendo l'intera cassetta postale di un utente sul blocco per controversia legale. 
    
Per inserire una cassetta postale per il blocco per controversia legale, nell'interfaccia di amministrazione:
    
1. Nella barra di spostamento a sinistra, passare a utenti **attivi**degli **utenti** \> .
    
2. Selezionare un utente la cui cassetta postale si desidera inserire nel blocco per controversia legale e nel riquadro utente espandere **impostazioni di posta elettronica** e accanto a **altre impostazioni** scegliere **modifica proprietà di Exchange**.
    
3. Nella pagina Cassetta postale per l'utente, scegliere * * funzionalità cassetta postale * * sulla barra di spostamento sinistra e quindi scegliere il collegamento **attiva** in **blocco per controversia legale**.
    
4. Nella finestra di dialogo **blocco per controversia legale** è possibile specificare la durata del blocco per controversia legale nel campo **durata** conservazione per controversia legale, lasciare vuoto il campo se si desidera inserire un blocco infinito. È inoltre possibile aggiungere note e indirizzare il proprietario della cassetta postale a un sito Web che potrebbe essere necessario spiegare meglio il \> **salvataggio**del blocco per controversia legale.
    
**Conservazione:** È possibile abilitare i criteri di conservazione personalizzati, ad esempio per mantenere un determinato intervallo di tempo o eliminare il contenuto in modo permanente alla fine del periodo di conservazione. Per ulteriori informazioni, vedere [Overview of](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)Retention Policies.

## <a name="set-up-azure-information-protection-features"></a>Configurare le funzionalità di protezione delle informazioni di Azure

Azure Information Protection (AIP) consente di classificare e facoltativamente, proteggere i documenti e i messaggi di posta elettronica, applicando etichette. Le etichette possono essere applicate automaticamente dagli amministratori che definiscono le regole e le condizioni, manualmente dagli utenti o utilizzando una combinazione in cui gli utenti ricevono consigli.

In Outlook sul Web è possibile applicare le seguenti etichette e limitazioni predefinite ai messaggi di posta elettronica:
  
- **** Non inoltrare: i destinatari possono leggere il messaggio, ma non possono inoltrare, stampare o copiare il contenuto
    
- **Encrypt**: l'intero messaggio è crittografato. I destinatari devono confermare la propria identità prima di accedere al contenuto crittografato e non possono rimuovere la crittografia.
    
- **Riservato**: fornisce ai dipendenti dell'organizzazione autorizzazioni complete per il contenuto e gli allegati di posta elettronica, ma non per gli utenti esterni all'organizzazione. I proprietari di dati possono monitorare e revocare il contenuto in qualsiasi momento.
    
- **Estremamente riservato**: questa restrizione può essere applicata a dati estremamente riservati, consentendo ai dipendenti di visualizzare, modificare e rispondere, ma non di inoltrare, stampare o copiare i dati. I proprietari di dati possono monitorare e revocare il contenuto in qualsiasi momento.

### <a name="make-sure-azure-information-protection-is-activated"></a>Verificare che Azure Information Protection sia attivato

Per verificare che AIP sia attivato:

1. Accedere al [portale di Azure](https://portal.azure.com/).

2. Selezionare **tutti i servizi** e digitare in *Azure Information Protection* nella **casella di ricerca**.

3. Dopo la visualizzazione dei risultati, fare clic sul pulsante Start next to **Azure Information Protection** per renderlo preferito e facile da trovare in un secondo momento.

4. Selezionare **Azure Information** \> Protection **Protection Activation** e verificare che lo stato sia impostato su attivato. 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a>Visualizzare i criteri di protezione delle informazioni di Azure e le etichette predefinite 

Per visualizzare e modificare le etichette esistenti:

1. Nel dashboard di Azure Information Protection selezionare etichette **classificazioni** \> ****. <br/>![Etichette standard per Azure Information Protection.](media/AIPLabels.png)

2. È possibile scegliere qualsiasi etichetta per visualizzare le opzioni, è possibile modificare il nome visualizzato, i colori e così via.
 
3. Se si desidera creare il proprio, vedere [modificare e creare nuove etichette](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) . 

### <a name="install-the-azure-information-protection-client-manually"></a>Installare il client Azure Information Protection manualmente

Per installare manualmente il client AIP:

1. Scaricare **AzInfoProtection. exe** dall' [area download Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).
 
2. È possibile verificare che l'installazione abbia avuto esito positivo visualizzando un documento di Word e **** assicurandosi che l'opzione Proteggi sia disponibile nella scheda **Home** . <br/>![Elenco a discesa della scheda protezione in un documento di Word.](media/Word_Protect.png)

Per ulteriori informazioni, vedere [installare il client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).
