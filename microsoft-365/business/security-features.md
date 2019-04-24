---
title: Funzionalità di sicurezza aziendale di Microsoft 365
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-security-compliance
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Informazioni sulle funzionalità di sicurezza disponibili in Microsoft 365 business.
ms.openlocfilehash: 24d4c4e79e7d8737beb82336796956774f127209
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286882"
---
# <a name="microsoft-365-business-security-features"></a>Funzionalità di sicurezza aziendale di Microsoft 365

Microsoft 365 business offre funzionalità di sicurezza semplificate per garantire la protezione dei dati su PC, telefoni e tablet.
    
## <a name="microsoft-365-business-admin-center-security-features"></a>Funzionalità di sicurezza dell'interfaccia di amministrazione di Microsoft 365 business

È possibile gestire molte delle funzionalità di sicurezza aziendale di Microsoft 365 nell'interfaccia di amministrazione, che consente di abilitare o disabilitare queste funzionalità in modo semplificato. Nell'interfaccia di amministrazione è possibile eseguire le operazioni seguenti:
  
![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
- [Impostare le impostazioni di gestione applicazioni per i dispositivi Android o iOS](app-protection-settings-for-android-and-ios.md) . 
    
    Tali impostazioni includono l'eliminazione di file da un dispositivo inattivo dopo un determinato periodo di tempo, la crittografia dei file di lavoro, la necessità di impostare un PIN e così via.
    
- [Impostare le impostazioni di protezione delle applicazioni per i dispositivi Windows 10](protection-settings-for-windows-10-devices.md) . 
    
    Queste impostazioni possono essere applicate ai dati aziendali sia su dispositivi di proprietà o personali.
    
- [Impostare le impostazioni di protezione del dispositivo per i dispositivi Windows 10](protection-settings-for-windows-10-pcs.md) . 
    
    È possibile abilitare la crittografia [BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405) per proteggere i dati in caso di perdita o di furto di un dispositivo e consentire a [Windows exploit Guard](https://go.microsoft.com/fwlink/p/?linkid=871404) di fornire una protezione avanzata contro ransomware. 
    
- [Rimuovere i dati aziendali dai dispositivi](remove-company-data.md)
    
    È possibile cancellare in remoto i dati della società se un dispositivo viene perso, rubato o un dipendente lascia la propria azienda.
    
- [Ripristinare le impostazioni di fabbrica dei dispositivi Windows 10](reset-devices-to-factory-settings.md) . 
    
    È possibile reimpostare tutti i dispositivi Windows 10 a cui sono state applicate le impostazioni di protezione dei dispositivi.
    
## <a name="additional-security-features"></a>Altre funzionalità di sicurezza 

Le funzionalità avanzate di Microsoft 365 business sono disponibili per aiutare a proteggere la propria azienda dalle minacce informatiche e salvaguardare le informazioni riservate.
  
- **[Office 365 Advanced Threat Protection](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)**
    
    Advanced Threat Protection (ATP) consente di proteggere la propria azienda da attacchi di phishing e ransomware sofisticati destinati a compromettere le informazioni relative ai dipendenti o ai clienti. Le caratteristiche includono:
    
  - Scansione avanzata degli allegati e analisi di AI per rilevare e scartare messaggi pericolosi.
    
  - Controlli automatici dei collegamenti Web nel messaggio di posta elettronica per valutare se fanno parte di uno schema di phishing. In questo modo si impedisce all'utente di accedere a siti Web non sicuri.
    
- **[Panoramica dei criteri di prevenzione della perdita di dati](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)** (DLP). 
    
    È possibile configurare DLP per rilevare automaticamente le informazioni riservate, come i numeri di carta di credito, i numeri di previdenza sociale e così via, per impedire la condivisione accidentale all'esterno dell'azienda.
    
- **[Archiviazione Exchange Online](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    La licenza di archiviazione Exchange Online consente di archiviare facilmente i messaggi con il backup dei dati continua. Archivia tutti i messaggi di posta elettronica di un utente, inclusi gli elementi eliminati, nel caso in cui siano necessari in seguito per l'individuazione o il ripristino. Inoltre, è possibile utilizzare criteri di conservazione diversi per conservare i dati della posta elettronica per controversia legale, eDiscovery, o per soddisfare i requisiti di conformità.
    
- **[Azure Information Protection](https://go.microsoft.com/fwlink/p/?linkid=871406)**
    
    La protezione delle informazioni consente di controllare l'accesso alle informazioni riservate nei messaggi di posta elettronica e nei documenti con controlli quali "non inoltrare" e "non copiare". È inoltre possibile classificare le informazioni riservate come "riservate" e specificare in che modo le informazioni classificate possono essere condivise all'esterno e all'interno dell'azienda. La crittografia di livello aziendale è facile da applicare ai messaggi di posta elettronica e ai documenti per mantenere private le informazioni. Microsoft 365 business include tutte le funzionalità di [Azure Information Protection Plan 1](https://go.microsoft.com/fwlink/p/?linkid=871407). È inoltre possibile installare il componente aggiuntivo di Azure Information Protection client per le app di Office. Per ulteriori informazioni, vedere [Guida di Admininstrator del client di Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide).
    
- **[Le funzionalità complete di Intune nel portale di Azure](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    L'accesso all'interfaccia di amministrazione di Intune nel portale di Azure consente di configurare altre funzionalità di sicurezza, ad esempio la gestione dei dispositivi MacOS, iPhone e Android insieme a Advanced Device Management per Windows, che non sono disponibili tramite Microsoft 365 Business Admin Center.
    
Nelle sezioni successive viene descritto come è possibile gestire queste funzionalità nel centro &amp; conformità sicurezza e nell'interfaccia di amministrazione di Intune. Nel corso del tempo, i controlli semplificati verranno aggiunti all'interfaccia di amministrazione di Microsoft 365 business.
  
## <a name="set-up-advanced-threat-protection-features"></a>Configurare le funzionalità avanzate di protezione dalle minacce

- **Protezione da allegati non sicuri:** ATP identifica i contenuti dannosi aprendo allegati di posta elettronica in un ambiente virtuale ed eseguendo analisi del comportamento risultante. Il contenuto viene valutato per determinare l'intento (se normale o dannoso) e il trifosfato di adenosina blocca la consegna degli allegati non sicuri, contribuendo a proteggersi dagli schemi di phishing e dalle infezioni ransomware. Per attivare la protezione degli allegati, vedere [set up Office 365 ATP SAFE Attachment Policies](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775).
    
- Proteggere l'ambiente quando gli utenti fanno clic su collegamenti dannosi: ATP esamina anche i collegamenti nella posta elettronica al momento in cui un utente fa clic su di essi. Se un collegamento non è sicuro, l'utente viene avvisato di non visitare il sito o ha informato che il sito è stato bloccato. Ciò consente di proteggere gli schemi di phishing. È possibile [configurare i criteri dei collegamenti sicuri ATP di office 365](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) o [configurare i criteri dei collegamenti sicuri atp di Office 365](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).
    
## <a name="set-up-dlp-features"></a>Configurare le funzionalità DLP

Vedere [creare un criterio DLP da un modello](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) per un esempio su come impostare un criterio per proteggere le informazioni personali. 
  
DLP viene fornito con molti modelli di criteri pronti per l'uso per molte impostazioni locali diverse. Ad esempio, Australia Financial Data, Canada Personal Information Act, US Financial Data, ecc. Vedere [cosa includono i modelli di criteri DLP](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) per un elenco completo. Tutti questi modelli possono essere abilitati in modo analogo all'esempio del modello PII. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Configurare la conservazione della posta elettronica con archiviazione Exchange Online

 Le funzionalità di licenza di **archiviazione di Exchange Online** offrono la possibilità di mantenere la conformità e gli standard normativi preservando il contenuto della posta elettronica ai fini di eDiscovery. Consente inoltre di ridurre i rischi in caso di controversia legale e consente di recuperare i dati dopo una violazione della sicurezza o quando è necessario recuperare gli elementi eliminati. Per attivare queste funzionalità, è possibile utilizzare il blocco per controversia legale per mantenere tutto il contenuto di un utente o utilizzare i criteri di conservazione per una maggiore personalizzazione. 
  
**Blocco per controversIa legale:** È possibile mantenere tutti i contenuti delle cassette postali, compresi gli elementi eliminati, inserendo l'intera cassetta postale di un utente sul blocco per controversia legale. 
    
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

Per ulteriori informazioni, vedere [installazione del client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)

## <a name="go-to-intune-admin-center"></a>Accedere all'interfaccia di amministrazione di Intune

1. Accedere al [portale di Azure](https://portal.azure.com/).

2. Selezionare **tutti i servizi** e digitare *Intune* nella **casella di ricerca**.

3. Dopo la visualizzazione dei risultati, fare clic sul pulsante Start accanto a **Microsoft Intune** per renderlo un favorito e facile da trovare in un secondo momento.
 
È possibile utilizzare Intune per registrare e gestire i dispositivi dell'organizzazione. Per ulteriori informazioni, vedere [capabilities by metodo di registrazione per i dispositivi di Windows](https://docs.microsoft.com/intune/enrollment-method-capabs) e le [Opzioni di registrazione per i dispositivi gestiti da Intune](https://docs.microsoft.com/intune/enrollment-options).
    
## <a name="faq"></a>Domande frequenti

 ### <a name="are-these-security-features-available-in-all-markets"></a>Queste funzionalità di sicurezza sono disponibili in tutti i mercati?
  
Sì, queste funzionalità sono disponibili in tutti i mercati in cui è venduto Microsoft 365 business.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>Come trovare il Centro sicurezza &amp; e conformità
  
1. [Accedere a Microsoft 365 business](https://portal.microsoft.com/) utilizzando le credenziali di amministratore. 
    
2. Nel NAV sinistro, individuare i **centri di amministrazione** ed espanderlo. 
    
    ![Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft 365, scegliere interfaccia di amministrazione.](media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Scegliere **conformità &amp; di sicurezza** per accedere al &amp; Centro sicurezza e conformità.