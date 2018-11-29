---
title: Funzionalità di sicurezza Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Informazioni sulle caratteristiche di protezione implementati con Microsoft 365 Business.
ms.openlocfilehash: bfddb419dbe5db441741a73ecb49e3d52649e382
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868591"
---
# <a name="microsoft-365-business-security-features"></a>Funzionalità di sicurezza Microsoft 365 Business

Microsoft 365 Business offre funzionalità di sicurezza semplificato per proteggere i dati su PC, telefoni e Tablet.
    
## <a name="microsoft-365-business-admin-center-security-features"></a>Caratteristiche di protezione di Microsoft Business 365 admin center

Consente di gestire molte delle funzionalità di sicurezza Microsoft 365 Business nell'interfaccia di amministrazione, che offre un modo semplificato per attivare o disattivare le queste caratteristiche. Nell'interfaccia di amministrazione è possibile eseguire le operazioni seguenti:
  
![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
- [Configurare le impostazioni di gestione applicazioni per dispositivi Android o iOS](app-protection-settings-for-android-and-ios.md) . 
    
    Queste impostazioni di eliminazione di file da un dispositivo inattivo dopo un determinato periodo, la crittografia dei file di lavoro, che richiedono che gli utenti impostare un PIN e così via.
    
- [Configurare le impostazioni di protezione dell'applicazione per i dispositivi Windows 10](protection-settings-for-windows-10-devices.md) . 
    
    Queste impostazioni possono essere applicate a dati aziendali in entrambe le situazioni appartenenti alla società o dispositivi personalmente e di proprietà.
    
- [Impostare le impostazioni di protezione di dispositivo per i dispositivi Windows 10](protection-settings-for-windows-10-pcs.md) . 
    
    È possibile attivare la crittografia [BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405) proteggere i dati in caso di un dispositivo viene perduto o rubato e abilitare [Guard sfruttare Windows](https://go.microsoft.com/fwlink/p/?linkid=871404) fornire una protezione avanzata contro ransomware. 
    
- [Rimuovere i dati aziendali dai dispositivi](remove-company-data.md)
    
    Si possono distruggere dati aziendali in modalità remota se un dispositivo verrà perso, rubato, o un utente ha lasciato l'azienda.
    
- [I dispositivi Windows 10 reimpostare le impostazioni predefinite](reset-devices-to-factory-settings.md) . 
    
    È possibile ripristinare tutti i dispositivi Windows 10 con le impostazioni di protezione dispositivo applicate alle stesse.
    
## <a name="additional-security-features"></a>Funzionalità di protezione aggiuntive 

Funzionalità avanzate di Microsoft 365 Business sono disponibili per la protezione dell'azienda contro le minacce cyber e salvaguardare informazioni riservate.
  
- **[Office 365 Advanced Threat Protection](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)**
    
    Advanced rischio degli strumenti (protezione di analisi) consente di proteggere il sistema propria azienda da phishing sofisticati e attacchi ransomware progettati per danneggiare dipendente o informazioni utente. Caratteristiche includono:
    
  - Scansione degli allegati sofisticati e tecnologia AI analisi per rilevare ed eliminare messaggi pericolosi.
    
  - Automatico verifica dei collegamenti web nella posta elettronica per valutare se fanno parte di uno schema di phishing. In questo modo si attendibili di accedere a siti Web non sicuri.
    
- **[Panoramica di criteri di prevenzione della perdita di dati](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)** (DLP). 
    
    È possibile impostare DLP per rilevare automaticamente informazioni riservate, ad esempio numeri di carta di credito, i numeri di previdenza sociale e così via, per impedire loro involontarie condivisione all'esterno della società.
    
- **[Archiviazione Exchange Online](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Archiviazione Exchange Online licenza consente di messaggi da archiviare con facilità con backup dei dati continua. Archivia tutti i messaggi di posta elettronica dell'utente, inclusi gli elementi eliminati, nel caso in cui sono necessari più avanti per l'individuazione o ripristino. Inoltre, è possibile utilizzare i criteri di conservazione diversi per conservare i dati di posta elettronica per controversia legale esenzioni, eDiscovery, o per soddisfare i requisiti di conformità.
    
- **[Azure Information Protection](https://go.microsoft.com/fwlink/p/?linkid=871406)**
    
    Consente di protezione di informazioni che controllare l'accesso alle informazioni riservate nei documenti e posta elettronica con i controlli come "Non inoltrare" e "Non vengono copiati." È anche possibile classificare le informazioni riservate come "Riservate" e specificare come informazioni classificate possono essere condivise all'esterno e all'interno dell'azienda. Crittografia di livello aziendale è facile da applicare ai documenti di mantenere le informazioni private e posta elettronica. Microsoft Business 365 include tutte le caratteristiche di [Azure Information Protection piano 1](https://go.microsoft.com/fwlink/p/?linkid=871407). È anche possibile installare il componente aggiuntivo client di Azure Information Protection per le applicazioni di Office. Per ulteriori informazioni, vedere [Guida di Azure Information Protection client dall'amministratore](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide).
    
- **[Tutte le funzionalità di Intune nel portale di Azure](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    Accesso a Intune interfaccia di amministrazione del portale Azure consente di impostare le caratteristiche di protezione aggiuntive, ad esempio la gestione di dispositivi, iPhone e i dispositivi Android e gestione avanzata dei dispositivi per Windows, Mac OS che non sono disponibili in Microsoft Interfaccia di amministrazione di 365 business.
    
Sezioni che seguono descrivono come è possibile gestire queste funzionalità per la protezione &amp; centro conformità e dell'interfaccia di amministrazione Intune. Nel corso del tempo verranno aggiunto i controlli semplificati per l'interfaccia di amministrazione di Microsoft 365 Business.
  
## <a name="set-up-advanced-threat-protection-features"></a>Impostare le funzionalità di protezione avanzata di rischio

- **Protezione contro gli allegati non sicuri:** Degli strumenti di analisi identifica contenuto dannoso aprendo gli allegati di posta elettronica in un ambiente virtuale e l'esecuzione dell'analisi del comportamento risultante. Il contenuto viene valutato per determinare lo scopo (se dannoso o normale), e degli strumenti di analisi blocca il rilascio di unsafe attachments, proteggere contro gli schemi di phishing e infezioni ransomware. Per attivare la protezione degli allegati, vedere [impostazione dei criteri di sicurezza allegati di Office 365 degli strumenti di analisi](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775).
    
- Proteggere l'ambiente quando gli utenti fare clic sui collegamenti dannosi: degli strumenti di analisi esamina inoltre collegamenti nella posta elettronica in fase di un utente fa clic su essi. Se un collegamento non sicuro, l'utente viene avvisato non per visitare il sito o informato che il sito è stato bloccato. Consente di evitare truffe. È possibile [impostare i criteri di Office 365 degli strumenti di analisi provvisoria collegamenti](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) o [impostare i criteri di Office 365 degli strumenti di analisi provvisoria collegamenti](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).
    
## <a name="set-up-dlp-features"></a>Impostare le funzionalità DLP

Per un esempio su come configurare un criterio per la protezione da personali informazioni, vedere [creare un criterio DLP da un modello](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) . 
  
DLP sono inclusi numerosi modelli pronte per l'utilizzo dei criteri per molte impostazioni internazionali diverse. Ad esempio dati finanziari Australia, Act informazioni personali in Canada, Usa dati finanziari, e così via. Per un elenco completo, vedere [modelli di criteri DLP the cosa includono](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) . Tutti i modelli possono essere attivati simile all'esempio di modello PII. 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a>Impostare il mantenimento di posta elettronica con archiviazione Exchange Online

 Funzionalità di licenza di **Archiviazione Exchange Online** consentono di mantenere gli standard normativi e conformità mantenendo posta elettronica contenuto ai fini di eDiscovery. Inoltre, consente di ridurre il rischio in caso di controversia e fornisce un modo per recuperare i dati dopo una violazione della protezione oppure quando è necessario ripristinare gli elementi eliminati. Per attivare queste funzionalità, è possibile utilizzare conservazione per controversia legale per conservare tutti i contenuti di un utente o utilizzare i criteri di conservazione per una migliore personalizzazione. 
  
**Conservazione per controversia legale:** È possibile preservare tutto il contenuto delle cassette postali inclusi gli elementi eliminati inserendo intera cassetta postale dell'utente controversia attesa. 
    
Per inserire una cassetta postale di conservazione per controversia legale, nell'interfaccia di amministrazione:
    
1. Nella barra di spostamento sinistro, passare a **utenti** \> **utenti attivi**.
    
2. Selezionare un utente la cui cassetta postale che si desidera bloccare controversia attesa e nel riquadro utente espandere **impostazioni di posta** e accanto a **ulteriori impostazioni** scegliere **Exchange Modifica proprietà**.
    
3. Nella pagina cassetta postale dell'utente, scegliere * * funzionalità delle cassette postali * * nella barra di spostamento sinistro e quindi fare clic sul collegamento **abilitare** in **conservazione per controversia legale**.
    
4. Nella **conservazione per controversia legale** la finestra di dialogo è possibile specificare la conservazione per controversia durata della conservazione nel campo di **durata della conservazione per controversia legale** , lasciare vuota se si desidera inserire un'attesa infinita. È anche possibile aggiungere note e indirizzare il proprietario della casella posta a un sito Web potrebbe essere necessario spiegare contenere informazioni su alla conservazione per controversia \> **salvare**.
    
**Conservazione:** È possibile abilitare criteri di conservazione personalizzata, ad esempio, per mantenere per un determinato periodo di tempo o eliminare in modo permanente il contenuto alla fine del periodo di conservazione. Per ulteriori informazioni, vedere [Panoramica di criteri di conservazione](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).
## <a name="set-up-azure-information-protection-features"></a>Impostare le funzionalità di protezione di informazioni di Azure

Azure Information Protection (AIP) è una soluzione basata su cloud che aiuta a un'organizzazione per classificare e, facoltativamente, proteggere relativi documenti e messaggi di posta elettronica, applicando le etichette. Le etichette possono essere applicate automaticamente per gli amministratori che definiscono regole e condizioni manualmente dagli utenti o una combinazione dove gli utenti vengono assegnati suggerimenti.

La possibilità di applicare le restrizioni seguenti per l'invio di messaggi di posta elettronica in Outlook sul web viene attivata automaticamente per tutti gli utenti:
  
- **Non inoltrare**: i destinatari possono leggere il messaggio, ma non in avanti, non è in grado di stampa o copiare il contenuto
    
- **Crittografa**: l'intero messaggio viene crittografato. I destinatari devono eseguire ulteriori passaggi per verificare la propria identità prima di accedere a contenuto crittografato e non possono rimuovere la crittografia.
    
- **Riservato**: concede i dipendenti dell'organizzazione tutte le autorizzazioni per il contenuto di posta elettronica e allegati, ma non per utenti esterni all'organizzazione. I proprietari dei dati consente di tenere traccia e revocare il contenuto in qualsiasi momento.
    
- **Altamente riservati**: questa restrizione può essere applicata ai dati altamente riservati, consentendo ai dipendenti di visualizzare, modificare e rispondere, ma non inoltrare, stampare o copiare i dati. I proprietari dei dati consente di tenere traccia e revocare il contenuto in qualsiasi momento.

### <a name="make-sure-azure-information-protection-is-activated"></a>Verificare che viene attivata la protezione delle informazioni di Azure

Per verificare che sia attivata AIP:

1. Accedere a [Centro di amministrazione di Azure Active Directory](https://portal.azure.com/).

    Può inoltre Sign il-individuando **Admin Center** \> **Azure Active Directory** nella barra di navigazione sinistra nell'interfaccia di amministrazione.

2. Selezionare **tutti i servizi** e tipo di *Protezione delle informazioni Azure* nella **Casella di ricerca**.

3. Visualizzano i risultati, fare clic su start successivo per **La protezione delle informazioni di Azure** per rendere un preferito e facile da individuare in seguito.

4. Selezionare **La protezione delle informazioni di Azure** \> marca e **attivazione di protezione** verificare lo stato è impostato su attivato. 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a>Visualizzare le etichette dei criteri e imposta come predefinito la protezione delle informazioni di Azure 

Per visualizzare e modificare, le etichette esistenti:

1. Nel dashboard di Azure Information Protection, selezionare **le classificazioni** \> * * etichette. <br/>![Etichette standard per la protezione delle informazioni di Azure.](media/AIPLabels.png)

2. È possibile scegliere qualsiasi etichetta per visualizzare le opzioni, è possibile modificare il nome visualizzato, i colori e così via.
 
3. Vedere [Modifica e creazione di nuove etichette](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) se si desidera creare. 

### <a name="install-the-azure-information-protection-client-manually"></a>Installare manualmente il client per la protezione delle informazioni di Azure

Per installare manualmente il client AIP:

1. Scaricare **AzInfoProtection.exe** [dall'area download Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).
 
2. È possibile verificare che l'installazione è stata eseguita la visualizzazione di un documento di Word e assicurandosi che l'opzione di **protezione** è disponibile nella scheda **Home** . <br/>![Scheda Protezione elenco a discesa in un documento di Word.](media/Word_Protect.png)

Per ulteriori informazioni, vedere [installazione del client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3)
    
## <a name="faq"></a>Domande frequenti

 ### <a name="are-these-security-features-available-in-all-markets"></a>Sono disponibili nei mercati tutte queste funzionalità di protezione?
  
Sì, queste caratteristiche sono disponibili nei mercati tutti in cui viene venduto Microsoft 365 Business.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>Come trovare la sicurezza &amp; centro conformità?
  
1. [Accedere a Microsoft 365 Business](https://portal.microsoft.com/) utilizzando le credenziali di amministrazione. 
    
2. Nella barra di navigazione sinistra, individuare **Admin Center** ed espanderlo. 
    
    ![Nella barra di navigazione sinistra nell'interfaccia di amministrazione di Microsoft 365, selezionare interfacce di amministrazione.](media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Scegliere **protezione &amp; conformità** per accedere alla protezione &amp; centro conformità. 
    
 ### <a name="how-do-i-find-the-intune-admin-center"></a>Come si trova l'interfaccia di amministrazione di Intune?
  
  
1. [Accedere a Microsoft 365 Business](https://portal.microsoft.com/) utilizzando le credenziali di amministrazione. 
    
2. Nella barra di navigazione sinistra, individuare **Admin Center** ed espanderlo. 
    
3. Scegliere **Intune** per accedere all'interfaccia di amministrazione Intune. 
    

