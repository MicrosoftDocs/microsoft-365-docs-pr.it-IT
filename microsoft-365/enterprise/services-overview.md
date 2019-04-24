---
title: Panoramica di Microsoft 365 Enterprise Services | Documenti Microsoft
description: Questo contenuto fornisce una panoramica delle raccomandazioni sull'utilizzo di Microsoft 365 Enterprise e Enterprise.
author: jeffgilb
manager: femila
ms.prod: microsoft-365-business
ms.topic: article
ms.date: 08/23/2017
ms.author: jeffgilb
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 7772421a32abd863f4301a4bc3d8264d8fe44242
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290161"
---
# <a name="microsoft-365-enterprise-services-and-concepts"></a>Servizi e concetti di Microsoft 365 Enterprise

Microsoft 365 Enterprise è progettato per le organizzazioni di grandi dimensioni e integra Office 365 Enterprise, Windows 10 Enterprise ed Enterprise Mobility + Security per offrire a tutti gli utenti le funzionalità fondamentali per esprimere la propria creatività e collaborare in tutta sicurezza. Microsoft Enterprise 365 include un'edizione enterprise delle applicazioni di Windows 10 e Office tramite Office 365 ProPlus.

Sia Windows 10 che Office 365 ProPlus offrono nuovi aggiornamenti delle funzionalità per le aziende rilasciati in marzo e settembre tramite il canale semestrale. Un rilascio di funzionalità del canale semestrale è supportato per 18 mesi. Sia Microsoft Intune che System Center Configuration Manager includono funzionalità per distribuire e aggiornare Windows 10 e Office 365 ProPlus.

Queste sono le versioni più aggiornate di Windows 10, Office 365 ProPlus, Microsoft Intune e System Center Configuration Manager:

|     |**Canale semestrale (mirato)**|**Canale semestrale**|
|:-----|:-----|:-----|
|**Windows 10**|Windows 10 Fall Creators Update (presto disponibile)|Versione 1703|
|**Office 365 ProPlus**|Versione 1803|Versione 1708|
|**Intune**|N/D|Versione 1708|
|**System Center Configuration Manager**|Technical Preview versione 1708|Versione1706<sup>*</sup>|

<sup>*</sup> L'aggiornamento 1706 per System Center Configuration Manager (Current Branch) è disponibile come aggiornamento nella console per siti installati in precedenza che eseguono la versione 1606, 1610 o 1702.

> [!NOTE]
> Anche i servizi di Microsoft Azure vengono aggiornati a intervalli regolari, ma non sono contraddistinti da un numero di versione. Per controllare gli aggiornamenti più recenti e quelli previsti per il futuro per i servizi di Azure, vedere la [Guida di orientamento a Cloud Platform](https://www.microsoft.com/cloud-platform/roadmap).

Per altre informazioni sulle funzionalità disponibili in queste versioni, vedere gli articoli seguenti:
- [Novità in Windows 10](https://docs.microsoft.com/windows/whats-new/)
- [Informazioni sulla versione di Windows 10](https://technet.microsoft.com/windows/release-info)
- [Cronologia degli aggiornamenti per Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history)
- [Versioni canale aggiornamento client Office 365](https://technet.microsoft.com/office/mt465751)
- [Novità di Microsoft Intune](https://docs.microsoft.com/intune/whats-new)
- [What's new in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-incremental-versions) (Novità di System Center Configuration Manager)
- [Funzionalità di Technical Preview 1708 per System Center Configuration Manager](https://docs.microsoft.com/sccm/core/get-started/capabilities-in-technical-preview-1708)

## <a name="services-overview"></a>Panoramica dei servizi

Questa sezione offre una panoramica dei servizi EMS e Office 365 inclusi in Microsoft 365 Enterprise, oltre a un'introduzione ai concetti di base necessari per comprendere come usarli al meglio per le specifiche esigenze di ogni organizzazione. Le funzionalità offerte da questi servizi consentono agli amministratori aziendali del cloud Microsoft non solo di proteggere le identità e i dispositivi dei dipendenti della società, ma anche di controllare l'accesso ai dati aziendali, sia in transito che inattivi.

|Servizio|Descrizione|
|-------|-----------|
|[Microsoft Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)|Azure AD offre una gamma completa di funzionalità per la gestione delle identità, tra cui autenticazione a più fattori, registrazione dei dispositivi, gestione delle password self-service, gestione dei gruppi self-service, controllo degli accessi in base al ruolo, monitoraggio dell'utilizzo delle applicazioni, controllo avanzato e monitoraggio e avvisi per la sicurezza.|
|[Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)|Questo servizio consente di rilevare potenziali vulnerabilità che interessano le identità dell'organizzazione e di configurare risposte automatizzate tramite criteri di accesso condizionale per rischi di accesso e rischi utente di livello basso, medio e alto.|
|[Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)|Questo servizio consente alle organizzazioni di ridurre al minimo il numero di persone con accesso permanente a operazioni privilegiate. Azure AD Privileged Identity Management introduce il concetto di amministratore idoneo. Gli amministratori idonei devono essere utenti che necessitano dell'accesso con privilegi occasionalmente, ma non ogni giorno. Il ruolo è inattivo fino a quando l'utente deve accedere con questi requisiti, quindi occorre completare un processo di attivazione per diventare amministratore attivo per un periodo di tempo prestabilito.|
|[Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)| Azure Information Protection è una soluzione basata sul cloud, inclusa nell'offerta EMS E5, che consente alle organizzazioni di classificare, etichettare e proteggere documenti e messaggi di posta elettronica. Queste operazioni possono essere eseguite automaticamente dagli amministratori, che definiscono regole e condizioni, manualmente dagli utenti oppure da entrambi, quando gli utenti ricevono raccomandazioni dagli amministratori. Le etichette di Azure Information Protection consentono di applicare la classificazione a documenti e messaggi di posta elettronica. In questo modo, la classificazione è identificabile in qualsiasi momento, indipendentemente dalla posizione di archiviazione dei dati o dagli utenti con cui è condivisa.<br><br>Le impostazioni dei criteri di Azure Information Protection sono protette da [Azure Rights Management](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms). Analogamente alle etichette, la protezione applicata tramite Rights Management rimane associata ai documenti e ai messaggi di posta elettronica indipendentemente dalla posizione: all'interno o all'esterno dell'organizzazione, in reti, file server o applicazioni.|
|[Microsoft Intune](https://docs.microsoft.com/intune/understand-explore/introduction-to-microsoft-intune)|Intune è un servizio di gestione della mobilità aziendale (EMM) basato su cloud che consente alla forza lavoro di essere produttiva, garantendo al tempo stesso la protezione dei dati aziendali. Intune è integrato con Azure AD per il controllo delle identità e degli accessi e viene usato per la gestione di dispositivi e applicazioni. Le funzionalità di [gestione dei dispositivi di Intune](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) vengono usate per configurare e proteggere i dispositivi dell'utente, inclusi i PC Windows.<br><br>Le funzionalità di gestione dei dispositivi di Intune supportano sia la registrazione [BYOD (Bring Your Own Device)](https://docs.microsoft.com/enterprise-mobility-security/solutions/enable-byod) che consente agli utenti di registrare telefoni, tablet o PC personali, sia la registrazione di [dispositivi di proprietà dell'azienda (COD, Corporate-Owned Device)](https://docs.microsoft.com/enterprise-mobility-security/solutions/issue-corp-devices) che rende possibili scenari di gestione come la registrazione automatica, i dispositivi condivisi o configurazioni con requisiti di registrazione pre-autorizzati. Per maggiore sicurezza, è anche possibile richiedere l'autenticazione a più fattori (MFA) per registrare un dispositivo. Dopo averli registrati nel sistema di gestione, Intune può configurare le funzionalità e le impostazioni dei dispositivi per abilitare l'accesso protetto alle risorse aziendali.|

## <a name="important-concepts-to-understand"></a>Concetti importanti da comprendere
I concetti di base e le funzionalità di EMS che è necessario conoscere sono descritti nella tabella seguente.

|Concetto di base|Descrizione|
|------------|-----------|
|[Autenticazione a più fattori di Azure (AMF)](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud)|Come soluzione di verifica in due passaggi di Microsoft, Azure AMF consente di salvaguardare l'accesso ai dati e alle applicazioni durante la riunione della domanda degli utenti per un processo di accesso semplice. Offre un'autenticazione complessa tramite una serie di metodi di verifica, tra cui la chiamata telefonica, il messaggio di testo o la verifica delle app per dispositivi mobili.|
|[Accesso condizionale di Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)|Questa funzionalità di Azure AD consente di applicare i controlli sull'accesso alle app Cloud nell'ambiente in base a condizioni specifiche. Con i controlli è possibile associare ulteriori requisiti all'accesso oppure bloccarli. L'implementazione dell'accesso condizionale si basa sui criteri.|
|[Prevenzione della perdita di dati (DLP) di Exchange Online](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)|I criteri di prevenzione della perdita di dati (DLP) di Exchange Online, disponibili come funzionalità Premium per gli abbonamenti a Exchange Online piano 2 e Office 365, consentono alle organizzazioni di identificare, monitorare e proteggere automaticamente le informazioni riservate in Office 365.<br><br>Con i criteri DLP di Exchange Online è possibile identificare informazioni riservate in numerosi percorsi, ad esempio Exchange Online, SharePoint Online e OneDrive for business. Ad esempio, questi criteri consentono di identificare i documenti che contengono informazioni riservate o di impedire la condivisione accidentale di informazioni riservate con persone esterne all'organizzazione.|
|[Regole di trasporto e flusso di posta di Exchange](https://support.office.com/article/Define-mail-flow-rules-to-encrypt-or-decrypt-email-messages-9B7DAF19-D5F2-415B-BC43-A0F5F4A585E8)|Le regole del flusso di posta di Exchange, note anche come regole di trasporto, sono in grado di individuare condizioni specifiche nei messaggi che passano attraverso l'organizzazione e agiscono su di essi. Le regole del flusso di posta sono simili alle regole della posta in arrivo che sono disponibili in molti client di posta elettronica. La differenza principale tra le regole del flusso di posta e le regole che si configurano in un'applicazione client come Outlook è che le regole del flusso di posta agiscono sui messaggi mentre sono in transito anziché dopo che il messaggio è stato recapitato. Le regole del flusso di posta contengono anche un insieme più ricco di condizioni, eccezioni e azioni, che offre la flessibilità necessaria per implementare molti tipi di criteri di messaggistica.|
|[Gestione dei dispositivi mobili di Intune](https://docs.microsoft.com/intune/understand-explore/introduction-to-microsoft-intune)|Intune fornisce la gestione dei dispositivi mobili (MDM) utilizzando i protocolli o le API disponibili nei sistemi operativi per dispositivi mobili. Include attività come la registrazione di dispositivi in gestione in modo che disponga di un inventario dei dispositivi che accedono ai servizi aziendali, la configurazione di dispositivi per garantire che soddisfino gli standard di sicurezza e di integrità della società, fornendo certificati e profili Wi-Fi/VPN per accedere ai servizi aziendali, riferire e misurare la conformità del dispositivo agli standard aziendali e rimuovere i dati aziendali dai dispositivi gestiti.|
|[Criteri di protezione delle app di Intune](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)|I criteri di protezione delle app di Intune possono essere utilizzati per proteggere i dati della tua azienda nelle app per dispositivi mobili con o senza la registrazione di un dispositivo in gestione. In effetti, i dispositivi mobili degli utenti possono anche essere gestiti da un'altra soluzione MDM non Microsoft, mentre [Intune contribuisce a proteggere le informazioni di Office 365](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-company-data-without-managing-devices). Assicurandosi che i dipendenti possano continuare a essere produttivi, è anche possibile prevenire la perdita di dati, intenzionale e involontaria. Se si implementano i criteri a livello di app, è possibile limitare l'accesso alle risorse aziendali e mantenere i dati all'interno del controllo del reparto IT.|
|[Durata token di Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes)|È possibile specificare la durata di un token emesso da Azure Active Directory (Azure AD). È possibile impostare le durata dei token per tutte le app dell'organizzazione, per un'applicazione multi-tenant (multi-Organization) o per una specifica entità di servizio nell'organizzazione.|
|Broker di identità Microsoft|Microsoft fornisce applicazioni per ogni piattaforma mobile che consente di eseguire il bridging delle credenziali tra le applicazioni di fornitori diversi e consente funzionalità avanzate speciali che richiedono una singola posizione sicura da dove convalidare le credenziali. Noi chiamiamo questi broker. Su iOS e Android questi broker sono forniti tramite le app portale Microsoft Authenticator e Intune Company. In Windows 10 questa funzionalità viene fornita da un selezionatore di account integrato nel sistema operativo, noto tecnicamente come broker di autenticazione Web.|

## <a name="security-best-practices-and-recommendations"></a>Procedure consigliate e raccomandazioni per la sicurezza
Non esiste una sola procedura consigliata per tutti gli ambienti dei clienti, ma l'articolo [Configurazioni e criteri di sicurezza consigliati](microsoft-365-policies-configurations.md) presenta alcuni concetti su procedure consigliate che è importante comprendere. L'articolo descrive anche i consigli generali di Microsoft su come applicare i criteri e la configurazione nell'ambito del cloud di Microsoft per garantire la protezione e la produttività dei dipendenti.

### <a name="baseline-recommended-security-policies-and-configurations"></a>Configurazioni e criteri di sicurezza consigliati per la linea di base
[Consigli generali su identità e criteri di accesso ai dispositivi](identity-access-policies.md) vengono descritti i criteri comuni consigliati per garantire la sicurezza di Microsoft 365 Enterprise. Vengono anche presentate le configurazioni client della piattaforma predefinite consigliate per offrire un'esperienza SSO ottimale agli utenti, oltre ai prerequisiti tecnici per l'accesso condizionale.

### <a name="exchange-online-access-policies"></a>Criteri di accesso di Exchange Online
[Suggerimenti sui criteri per la protezione della posta elettronica](secure-email-recommended-policies.md) sono disponibili suggerimenti Microsoft che consentono di proteggere la posta elettronica organizzativa e i client di posta elettronica che supportano l'autenticazione moderna e l'accesso condizionale. Queste indicazioni si aggiungono a quelle contenute in [Common identity and access policy recommendations](identity-access-policies.md) (Consigli sui criteri comuni di identità e accesso).

### <a name="sharepoint-online-access-policies"></a>Criteri di accesso di SharePoint Online
Vengono forniti suggerimenti per [salvaguardare l'accesso ai file di SharePoint Online](sharepoint-file-access-policies.md) oltre ai consigli sui criteri di [identità e di accesso comuni](identity-access-policies.md) e ai consigli sui [criteri per la protezione della posta elettronica](secure-email-recommended-policies.md). In questo articolo vengono illustrati i nuovi criteri da creare e la modalità di modifica dei criteri esistenti, per proteggere la posta elettronica di Exchange Online e l'accesso ai file di SharePoint Online.

## <a name="deploy-windows-10-and-office-365-proplus"></a>Distribuire Windows 10 e Office 365 ProPlus
Informazioni su come distribuire Windows 10 e Office 365 ProPlus con integrazione in Microsoft Azure Active Directory (Azure AD) o in Active Directory Domain Services in locale. Distribuire Windows 10, Office 365 ProPlus e le altre app line-of-business nei nuovi dispositivi o aggiornare i dispositivi esistenti a Windows 10 usando Intune, System Center Configuration Manager e Criteri di gruppo per gestire i dispositivi.

Per ulteriori informazioni, vedere gli articoli seguenti:
- [Considerazioni sulla distribuzione di Windows 10](https://docs.microsoft.com/windows/deployment/planning/windows-10-deployment-considerations)
- [Guida alla distribuzione di Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/deployment-guide-for-office-365-proplus)
- [Guida alle procedure consigliate per la distribuzione di Office 365 ProPlus nell'azienda](https://docs.microsoft.com/DeployOffice/best-practices/best-practices)
- [Installare le app di Office 365 ProPlus nei dispositivi Windows 10 con Intune](https://docs.microsoft.com/intune/apps-add-office365)

Per assistenza per la distribuzione con Microsoft 365, [contattare FastTrack](https://fasttrack.microsoft.com/microsoft365).

## <a name="manage-updates-to-windows-10-and-office-365-proplus"></a>Gestire gli aggiornamenti per Windows 10 e Office 365 ProPlus
I collegamenti seguenti mostrano come ottenere il massimo controllo sugli aggiornamenti della qualità e delle funzionalità per Windows 10 e Office 365 ProPlus. Informazioni su come controllare in modo efficace l'utilizzo della larghezza di banda e mantenere aggiornati Windows e Office con le funzionalità, le caratteristiche e gli aggiornamenti della sicurezza più recenti.

Per ulteriori informazioni, vedere gli articoli seguenti:
- [Panoramica di Windows as a Service](https://docs.microsoft.com/windows/deployment/update/waas-overview)
- [Panoramica dei canali di aggiornamento per Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)
- [Gestire gli aggiornamenti software con Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure)
- [Distribuire gli aggiornamenti di Windows 10 con System Center Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)<sup>*</sup>
- [Gestire Office 365 ProPlus con Configuration Manager](https://docs.microsoft.com/sccm/sum/deploy-use/manage-office-365-proplus-updates)

<sup>*</sup> Microsoft invita le organizzazioni che attualmente usano Configuration Manager per la gestione degli aggiornamenti di Windows a continuare a farlo per i computer client Windows 10.

## <a name="next-steps"></a>Passaggi successivi
[Pagina del prodotto Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise)<br/>
[Guida di orientamento a Cloud Platform](https://www.microsoft.com/cloud-platform/roadmap)
