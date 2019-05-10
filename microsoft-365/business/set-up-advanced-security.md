---
title: Impostare i criteri di sicurezza avanzati per gli utenti aziendali di Microsoft 365
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
ms.openlocfilehash: 4728e11a16fdf8a461f5687632df75699923f846
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "33663642"
---
# <a name="set-up-advanced-security-policies"></a>Impostare i criteri di sicurezza avanzati

Oltre ai criteri che è possibile configurare nell'interfaccia di [Amministrazione](security-features.md#microsoft-365-business-admin-center-security-features), è possibile aggiungere ulteriore protezione dalle minacce informatiche tramite la configurazione di [Office 365 Advanced Threat Protection](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653) (ATP). È inoltre possibile proteggere le informazioni riservate mediante la configurazione di [prevenzione della perdita di dati](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e) (DLP), Azure Information Protection (AIP), l' [archiviazione Exchange Online](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)e gestire i dispositivi anche nel [portale di Intune](#go-to-intune-admin-center).

Per una panoramica dei principali modi in cui è possibile proteggere la propria azienda, è consigliabile utilizzare le [principali 10 modalità di protezione di Microsoft 365 business plan](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) , incluso l'utilizzo dell'AMF per creare una seconda forma di accesso.

Per istruzioni su come seguire le istruzioni, vedere [proteggere i video per la formazione aziendale](https://support.office.com/article/e12187b8-216a-4490-9e3b-df34a06fb787) .

## <a name="increase-email-malware-protection"></a>Aumentare la protezione antimalware della posta elettronica

Il malware è un software che può danneggiare i computer o la rete e, eventualmente, per rubare i dati da te, incluse le informazioni personali o dei clienti. Microsoft 365 business include un livello di protezione da malware di base, ma è possibile aumentare questa protezione mediante la configurazione di impostazioni aggiuntive. Per istruzioni, vedere attivazione del video per la formazione [del rilevamento di malware](https://support.office.com/article/02b5783a-eea0-42e8-8856-62440718c3f0) .

## <a name="set-up-advanced-threat-protection-features"></a>Configurare le funzionalità avanzate di protezione dalle minacce

- **Protezione da allegati non sicuri:** ATP identifica i contenuti dannosi aprendo allegati di posta elettronica in un ambiente virtuale ed eseguendo analisi del comportamento risultante. Il contenuto viene valutato per determinare l'intento (se normale o dannoso) e il trifosfato di adenosina blocca la consegna degli allegati non sicuri, contribuendo a proteggersi dagli schemi di phishing e dalle infezioni ransomware. Per attivare la protezione degli allegati, vedere Configurare la documentazione della Guida per gli [allegati di Office 365 ATP Safe](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775) e [proteggere da file dannosi video sulla](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5) formazione breve.
    
- **Proteggere l'ambiente quando gli utenti fanno clic su collegamenti dannosi:** ATP esamina anche i collegamenti nella posta elettronica al momento in cui un utente fa clic su di essi. Se un collegamento non è sicuro, l'utente viene avvisato di non visitare il sito o ha informato che il sito è stato bloccato. Ciò consente di proteggere gli schemi di phishing. Per attivare questa opzione, vedere [set up Office 365 ATP Safe Links](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-atp-safe-links-policies) Help Documentation e [Protect Against malware sites](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa) Short training video.

- **Proteggi il tuo ambiente dal tentativo di phishing:**  ATP anti-phishing applica un insieme di modelli di apprendimento automatico con gli algoritmi di rilevamento della rappresentazione ai messaggi in arrivo per garantire la protezione da attacchi di phishing in cui un utente cerca di estrarre informazioni da un utente pretendendo di essere conosciuto contatto. Per attivare questa impostazione, vedere Configurare la documentazione della Guida per il [sistema ATP anti-phishing](https://docs.microsoft.com/office365/securitycompliance/set-up-anti-phishing-policies) e [proteggere i tentativi di phishing con](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c) brevi video di formazione.

## <a name="set-up-dlp-features"></a>Configurare le funzionalità DLP

Vedere [creare un criterio DLP da un modello](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) per un esempio su come impostare un criterio per proteggere le informazioni personali. 
  
DLP viene fornito con molti modelli di criteri pronti per l'uso per molte impostazioni locali diverse. Ad esempio, Australia Financial Data, Canada Personal Information Act, US Financial Data, ecc. Vedere [cosa includono i modelli di criteri DLP](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) per un elenco completo. Tutti questi modelli possono essere abilitati in modo analogo all'esempio del modello PII. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Configurare la conservazione della posta elettronica con archiviazione Exchange Online

 Le funzionalità di licenza di **archiviazione di Exchange Online** offrono la possibilità di mantenere la conformità e gli standard normativi preservando il contenuto della posta elettronica ai fini di eDiscovery. Consente inoltre di ridurre i rischi in caso di controversia legale e consente di recuperare i dati dopo una violazione della sicurezza o quando è necessario recuperare gli elementi eliminati. Per attivare queste funzionalità, è possibile utilizzare il blocco per controversia legale per mantenere tutto il contenuto di un utente o utilizzare i criteri di conservazione per una maggiore personalizzazione. 
  
**Blocco per controversia legale:** È possibile mantenere tutti i contenuti delle cassette postali, compresi gli elementi eliminati, inserendo l'intera cassetta postale di un utente sul blocco per controversia legale. 
    
Per inserire una cassetta postale per il blocco per controversia legale, nell'interfaccia di amministrazione:
    
1. Nella barra di spostamento a sinistra, passare a utenti **attivi**degli **utenti** \> .
    
2. Selezionare un utente la cui cassetta postale si desidera inserire nel blocco per controversia legale e nel riquadro utente espandere **impostazioni di posta elettronica** e accanto a **altre impostazioni** scegliere **modifica proprietà di Exchange**.
    
3. Nella pagina Cassetta postale per l'utente, scegliere * * funzionalità cassetta postale * * sulla barra di spostamento sinistra e quindi scegliere il collegamento **attiva** in **blocco per controversia legale**.
    
4. Nella finestra di dialogo **blocco per controversia legale** è possibile specificare la durata del blocco per controversia legale nel campo **durata** conservazione per controversia legale, lasciare vuoto il campo se si desidera inserire un blocco infinito. È inoltre possibile aggiungere note e indirizzare il proprietario della cassetta postale a un sito Web che potrebbe essere necessario spiegare meglio il \> **salvataggio**del blocco per controversia legale.
    
**Conservazione:** È possibile abilitare i criteri di conservazione personalizzati, ad esempio per mantenere un determinato intervallo di tempo o eliminare il contenuto in modo permanente alla fine del periodo di conservazione. Per ulteriori informazioni, vedere [Overview of](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)Retention Policies.
## <a name="set-up-azure-information-protection-features"></a>Configurare le funzionalità di protezione delle informazioni di Azure

Azure Information Protection (AIP) è una soluzione basata su cloud che consente a un'organizzazione di classificare e facoltativamente proteggere i propri documenti e messaggi di posta elettronica applicando etichette. Le etichette possono essere applicate automaticamente dagli amministratori che definiscono regole e condizioni, manualmente dagli utenti o da una combinazione in cui gli utenti ricevono consigli.

La possibilità di applicare le restrizioni seguenti quando si inviano messaggi di posta elettronica in Outlook sul Web è abilitata automaticamente per tutti gli utenti:
  
- **** Non inoltrare: i destinatari possono leggere il messaggio, ma non possono inoltrare, stampare o copiare il contenuto
    
- **Encrypt**: l'intero messaggio è crittografato. I destinatari devono eseguire passaggi aggiuntivi per confermare la propria identità prima di accedere al contenuto crittografato e non possono rimuovere la crittografia.
    
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

## <a name="go-to-intune-admin-center"></a>Accedere all'interfaccia di amministrazione di Intune

1. Accedere al [portale di Azure](https://portal.azure.com/).

2. Selezionare **tutti i servizi** e digitare *Intune* nella **casella di ricerca**.

3. Dopo la visualizzazione dei risultati, fare clic sul pulsante Start accanto a **Microsoft Intune** per renderlo un favorito e facile da trovare in un secondo momento.

Oltre all'interfaccia di amministrazione, è possibile utilizzare Intune per registrare e gestire i dispositivi dell'organizzazione. Per ulteriori informazioni, vedere [capabilities by metodo di registrazione per i dispositivi di Windows](https://docs.microsoft.com/intune/enrollment-method-capabs) e le [Opzioni di registrazione per i dispositivi gestiti da Intune](https://docs.microsoft.com/intune/enrollment-options).

## <a name="microsoft-secure-score"></a>Microsoft Secure Score

