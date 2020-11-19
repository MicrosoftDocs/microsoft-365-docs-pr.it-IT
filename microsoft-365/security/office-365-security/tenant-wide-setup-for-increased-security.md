---
title: Configurare il tenant Microsoft 365 per una maggiore sicurezza
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
ms.custom:
- seo-marvel-apr2020
description: In questo argomento viene illustrata la configurazione consigliata per le impostazioni a livello di tenant che influiscono sulla sicurezza dell'ambiente Microsoft 365.
ms.openlocfilehash: cc1f69663badaa7ae6590bb1d389cb15f13da79d
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357540"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>Configurare il tenant Microsoft 365 per una maggiore sicurezza

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In questo argomento viene illustrata la configurazione consigliata per le impostazioni a livello di tenant che influiscono sulla sicurezza dell'ambiente Microsoft 365. Le esigenze di sicurezza possono richiedere più o meno sicurezza. Utilizzare questi suggerimenti come punto di partenza.

## <a name="check-office-365-secure-score"></a>Controllare Office 365 Secure Score

Office 365 Secure Score analizza la sicurezza dell'organizzazione in base alle normali attività e alle impostazioni di sicurezza e assegna un punteggio. Iniziare prendendo nota del punteggio corrente. Se si modificano le impostazioni a livello di tenant, si otterrà un punteggio maggiore. L'obiettivo non è quello di ottenere il punteggio massimo, ma di essere a conoscenza delle opportunità di protezione dell'ambiente che non influiscono negativamente sulla produttività per gli utenti. Vedere [Microsoft Secure Score](../mtp/microsoft-secure-score.md).

## <a name="tune-threat-management-policies-in-the-microsoft-365-security-center"></a>Ottimizzare i criteri di gestione delle minacce nel centro sicurezza di Microsoft 365

Il Centro sicurezza Microsoft 365 include funzionalità che proteggono l'ambiente. Sono inoltre inclusi i report e i dashboard che è possibile utilizzare per monitorare e intervenire. Alcune aree sono dotate di configurazioni dei criteri predefinite. Alcune aree non includono criteri o regole predefinite. Visitare questi criteri in gestione delle minacce per ottimizzare le impostazioni di gestione delle minacce per un ambiente più sicuro.

****

|Area|Include un criterio predefinito|Consiglio|
|---|---|---|
|**Anti-phishing**|Sì|Se si dispone di un dominio personalizzato, configurare il criterio anti-phishing predefinito per proteggere gli account di posta elettronica degli utenti più importanti, ad esempio il CEO, e per proteggere il dominio. <p> Esaminare i [criteri anti-phishing in office 365](set-up-anti-phishing-policies.md) e vedere [Configure anti-phishing policys in EOP](configure-anti-phishing-policies-eop.md) o [Configure anti-phishing Policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).|
|**Motore antimalware**|Sì| Modificare il criterio predefinito: <ul><li>Filtro tipi di allegati comuni: selezionare attivato</li></ul> <p> È inoltre possibile creare criteri di filtro antimalware personalizzati e applicarli a utenti, gruppi o domini specificati nell'organizzazione. <p> Ulteriori informazioni: <ul><li>[Protezione antimalware](anti-malware-protection.md)</li><li>[Configurazione dei criteri anti-malware](configure-anti-malware-policies.md)</li></ul>|
|**Allegati sicuri in Microsoft Defender per Office 365**|No|Nella pagina principale per gli allegati sicuri fare clic su **Impostazioni globali** e attiva questa impostazione: <ul><li>**Attivare ATP per SharePoint, OneDrive e Microsoft Teams**</li></ul> <p> Creare un criterio per gli allegati sicuri con queste impostazioni: <ul><li> **Blocca**: selezionare **blocca** come risposta malware sconosciuta.</li><li>**Attiva reindirizzamento**: selezionare questa casella e immettere un indirizzo di posta elettronica, ad esempio un account di amministratore o di quarantena.</li><li>**Applicare la selezione precedente se la ricerca di malware per gli allegati non è stata eseguita o si verifica un errore**: selezionare questa casella.</li><li>**_Applicato a_*: **il dominio del destinatario è** \> selezionare il dominio.</li></ul> <p> Ulteriori informazioni: [ATP per SharePoint, OneDrive e Microsoft teams](atp-for-spo-odb-and-teams.md) e [configurare i criteri per gli allegati sicuri](set-up-atp-safe-attachments-policies.md)|
|**Collegamenti sicuri in Microsoft Defender per Office 365**|Sì|Nella pagina principale per i collegamenti sicuri fare clic su **Impostazioni globali**: <ul><li>**Utilizzare collegamenti sicuri in: applicazioni di Office 365**: verificare che questa impostazione sia attivata.</li><li>**Non monitorare quando gli utenti fanno clic su collegamenti sicuri**: disattivare questa impostazione per monitorare i clic dell'utente.</li></ul> <p> Creare un criterio per i collegamenti sicuri con queste impostazioni: <ul><li>**Selezionare l'azione per gli URL potenzialmente dannosi sconosciuti nei messaggi**: verificare che questa impostazione sia **attiva**.</li><li>**Selezionare l'azione per gli URL sconosciuti o potenzialmente dannosi all'interno di Microsoft teams**: verificare che questa impostazione sia **attiva**.</li><li>**Applicazione dell'analisi degli URL in tempo reale per collegamenti e collegamenti sospetti che puntano a file**: selezionare questa casella.</li><li>**Attendere il completamento dell'analisi degli URL prima di recapitare il messaggio**: selezionare questa casella.</li><li>**Applicazione di collegamenti sicuri ai messaggi di posta elettronica inviati all'interno dell'organizzazione**: selezionare questa casella.</li><li>**Non consentire agli utenti di fare clic sull'URL originale**: selezionare questa casella.</li><li>**Applicato a**: **il dominio del destinatario è** \> selezionare il dominio.</li></ul> <p> Ulteriori informazioni: [configurare i criteri per i collegamenti sicuri](set-up-atp-safe-links-policies.md).|
|**Protezione dalla posta indesiderata (filtro delle E-mail)**|Sì| Cosa guardare per: <ul><li>Troppa posta indesiderata: scegliere le impostazioni personalizzate e modificare il criterio di filtro della posta indesiderata predefinito.</li><li>Intelligence di spoofing: esaminare i mittenti che eseguono lo spoofing del dominio. Blocca o Consenti tali mittenti.</li></ul> <p> Ulteriori informazioni: [Microsoft 365 protezione dalla posta indesiderata della posta elettronica](anti-spam-protection.md).|
|**_Autenticazione della posta elettronica_* _|Sì|L'autenticazione tramite posta elettronica utilizza un DNS (Domain Name System) per aggiungere informazioni verificabili ai messaggi di posta elettronica sul mittente di un messaggio di posta elettronica. Microsoft 365 configura l'autenticazione della posta elettronica per il dominio predefinito (onmicrosoft.com), ma gli amministratori di Microsoft 365 possono anche utilizzare l'autenticazione della posta elettronica per i domini personalizzati. Vengono utilizzati tre metodi di autenticazione: <ul><li>Sender Policy Framework (o SPF).</li><ul><li>Per il programma di installazione, vedere [set up SPF in Microsoft 365 per evitare lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</li></ul> <li>DomainKeys (DKIM).</li><ul><li>Vedere [use DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato](use-dkim-to-validate-outbound-email.md).</li><li>Dopo aver configurato DKIM, abilitarlo nel centro sicurezza.</li></ul><li>Autenticazione dei messaggi basata sul dominio, creazione di rapporti e conformità (DMARC).</li><ul><li>Per l'installazione di DMARC, [utilizzare DMARC per convalidare la posta elettronica in Microsoft 365](use-dmarc-to-validate-email.md).</li></ul></ul>|
|

> [!NOTE]
> Per le distribuzioni non standard di SPF, distribuzioni ibride e risoluzione dei problemi: [in che modo Microsoft 365 utilizza il Sender Policy Framework (SPF) per impedire lo spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).

## <a name="view-dashboards-and-reports-in-the-security-and-compliance-centers"></a>Visualizzare dashboard e report nei centri sicurezza e conformità

Visitare questi rapporti e dashboard per ulteriori informazioni sull'integrità dell'ambiente. I dati contenuti in questi rapporti diventeranno più ricchi man mano che l'organizzazione utilizzerà i servizi di Office 365. Per il momento, acquisire familiarità con ciò che è possibile monitorare e intraprendere un'azione. Per ulteriori informazioni, vedere: [Reports in Microsoft 365 Security and Compliance Centers](../../compliance/reports-in-security-and-compliance.md).

_***

|Dashboard|Descrizione|
|---|---|
|[Dashboard di gestione delle minacce](security-dashboard.md)|Nella sezione **gestione minacce** del Centro sicurezza utilizzare questo dashboard per visualizzare le minacce che sono già state gestite e come strumento pratico per la creazione di report ai decisori aziendali su quali funzionalità di ricerca e risposta delle minacce sono già state eseguite per garantire la sicurezza dell'azienda.|
|[Esplora minacce (o rilevamenti in tempo reale)](threat-explorer.md)|Questo è anche nella sezione **gestione minacce** del Centro sicurezza. Se si sta indagando o si verifica un attacco al tenant, utilizzare Esplora risorse (o rilevamenti in tempo reale) per analizzare le minacce. Explorer (e il rapporto rilevamenti in tempo reale) mostrano il volume degli attacchi nel tempo ed è possibile analizzare questi dati in base alle famiglie di minacce, all'infrastruttura di attacco e altro ancora. È inoltre possibile contrassegnare eventuali messaggi di posta elettronica sospetti per l'elenco eventi non consentiti.|
|Report: Dashboard|Nella sezione **report** del Centro sicurezza, visualizzare i rapporti di controllo per le organizzazioni di SharePoint Online e di Exchange Online. È inoltre possibile accedere ai report di accesso dell'utente di Azure Active Directory (Azure AD), ai report sulle attività degli utenti e al log di controllo di Azure AD dalla pagina **Visualizza report** .|
|

![Dashboard Centro protezione](../../media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>Configurare altre impostazioni a livello di tenant di Exchange Online

Molti dei controlli per la sicurezza e la protezione nell'interfaccia di amministrazione di Exchange sono anch ' essi inclusi nel centro sicurezza. Non è necessario configurarli in entrambe le posizioni. Di seguito sono riportate alcune impostazioni aggiuntive consigliate.

****

|Area|Include un criterio predefinito|Consiglio|
|---|---|---|
|**Flusso di posta** (regole del flusso di posta, note anche come regole di trasporto)|No|Aggiungere una regola del flusso di posta per garantire la protezione da ransomware bloccando i tipi di file eseguibili e i tipi di file di Office che contengono macro. Per ulteriori informazioni, vedere [Use Mail Flow Rules to inspect Message Attachments in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments). <p> Per ulteriori informazioni, vedere gli argomenti seguenti: <ul><li>[Proteggere l'ambiente da ransomware](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware)</li><li>[Protezione da malware e ransomware in Office 365](https://docs.microsoft.com/Office365/Enterprise/office-365-malware-and-ransomware-protection)</li><li>[Eseguire il ripristino da un attacco ransomware in Office 365](recover-from-ransomware.md)</li></ul> <p> Creare una regola del flusso di posta per impedire l'inoltro automatico dei messaggi di posta elettronica ai domini esterni. Per ulteriori informazioni, vedere [attenuazione delle regole di inoltro esterno client con Secure Score](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score). <p> Ulteriori informazioni: [regole del flusso di posta (regole di trasporto) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**Abilitare l'autenticazione moderna**|No|L'autenticazione moderna è un prerequisito per l'utilizzo dell'autenticazione a più fattori (AMF). L'AMF è consigliata per garantire l'accesso alle risorse cloud, incluso il messaggio di posta elettronica. <p> Vedere gli argomenti seguenti: <ul><li>[Abilitare o disabilitare l’autenticazione moderna in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype for business online: abilitare il tenant per l'autenticazione moderna](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> L'autenticazione moderna è abilitata per impostazione predefinita per i client di Office 2016, SharePoint Online e OneDrive for business. <p> Ulteriori informazioni: funzionamento dell' [autenticazione moderna per le app client di office 2013 e office 2016](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>Configurare i criteri di condivisione a livello di tenant nell'interfaccia di amministrazione di SharePoint

Suggerimenti Microsoft per la configurazione dei siti del team di SharePoint a livelli di protezione crescenti, a partire dalla protezione di base. Per ulteriori informazioni, vedere [proteggere siti e file di SharePoint Online](https://docs.microsoft.com/microsoft-365-enterprise/secure-sharepoint-online-sites-and-files)

I siti del team di SharePoint configurati a livello di base consentono la condivisione di file con utenti esterni tramite collegamenti di accesso anonimo. Questo approccio è consigliato anziché inviare file tramite posta elettronica.

Per supportare gli obiettivi per la protezione di base, configurare i criteri di condivisione a livello di tenant come consigliato. Le impostazioni di condivisione per i singoli siti possono essere più restrittive rispetto a quelle dei criteri a livello di tenant, ma non più permissive.

****

|Area|Include un criterio predefinito|Consiglio|
|---|---|---|
|**Condivisione** (SharePoint Online e OneDrive for business)|Sì|La condivisione esterna è abilitata per impostazione predefinita. Queste impostazioni sono consigliate: <ul><li>Consenti la condivisione per gli utenti esterni autenticati e l'utilizzo di collegamenti di accesso anonimo (impostazione predefinita).</li><li>I collegamenti di accesso anonimo scadono in questo numero di giorni. Immettere un numero, se lo si desidera, ad esempio 30 giorni.</li><li>Tipo di collegamento predefinito: selezionare interno (solo persone nell'organizzazione). Gli utenti che desiderano condividere l'utilizzo dei collegamenti anonimi devono scegliere questa opzione dal menu condivisione.</li></ul> <p> Ulteriori informazioni: [Panoramica della condivisione esterna](https://docs.microsoft.com/sharepoint/external-sharing-overview)|
|

L'interfaccia di amministrazione di SharePoint e l'interfaccia di amministrazione di OneDrive for business includono le stesse impostazioni. Le impostazioni dell'interfaccia di amministrazione sono valide per entrambi.

## <a name="configure-settings-in-azure-active-directory"></a>Configurare le impostazioni in Azure Active Directory

Assicurarsi di visitare queste due aree in Azure Active Directory per completare l'installazione a livello di tenant per ambienti più sicuri.

### <a name="configure-named-locations-under-conditional-access"></a>Configurare percorsi denominati (in accesso condizionale)

Se nell'organizzazione sono presenti uffici con accesso alla rete sicura, aggiungere gli intervalli di indirizzi IP attendibili a Azure Active Directory come percorsi denominati. Questa funzionalità consente di ridurre il numero di falsi positivi segnalati per gli eventi di rischio di accesso.

Vedere: [posizioni denominate in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>Bloccare le app che non supportano l'autenticazione moderna

L'autenticazione a più fattori richiede app che supportano l'autenticazione moderna. Le app che non supportano l'autenticazione moderna non possono essere bloccate tramite le regole di accesso condizionale.

Per gli ambienti sicuri, assicurarsi di disabilitare l'autenticazione per le app che non supportano l'autenticazione moderna. È possibile eseguire questa operazione in Azure Active Directory con un controllo che verrà presto.

Nel frattempo, utilizzare uno dei metodi seguenti per eseguire questa operazione per SharePoint Online e OneDrive for business:

- Utilizzare PowerShell, vedere [bloccare le app che non utilizzano l'autenticazione moderna (adal)](https://docs.microsoft.com/mem/intune/protect/app-modern-authentication-block).

- Configurarlo nell'interfaccia di amministrazione di SharePoint nella pagina "accesso ai dispositivi"-"controllare l'accesso da app che non utilizzano l'autenticazione moderna". Scegliere blocca.

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Iniziare a utilizzare cloud app Security o Office 365 cloud app Security

Utilizzare Office 365 cloud app Security per valutare i rischi, per allertare attività sospette e per intervenire automaticamente. Richiede un piano di Office 365 E5.

In alternativa, utilizzare Microsoft cloud app Security per ottenere una visibilità più profonda anche dopo che è stato concesso l'accesso, controlli completi e una protezione migliorata per tutte le applicazioni cloud, tra cui Office 365.

Poiché questa soluzione consiglia il piano EMS E5, è consigliabile iniziare con cloud app Security in modo che sia possibile utilizzarlo con altre applicazioni SaaS nell'ambiente in uso. Iniziare con i criteri e le impostazioni predefiniti.

Ulteriori informazioni:

- [Distribuzione di Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)

- [Ulteriori informazioni su Microsoft Cloud App Security](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [Che cos'è la sicurezza delle app Cloud?](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)

![Dashboard di Cloud App Security](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>Risorse aggiuntive

Questi articoli e guide forniscono ulteriori informazioni prescrittivi per la protezione dell'ambiente Microsoft 365:

- [Guida alla sicurezza Microsoft per campagne politiche, organizzazioni no profit e altre organizzazione agile](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) (è possibile utilizzare queste raccomandazioni in qualsiasi ambiente, in particolare ambienti solo cloud)

- [Criteri di sicurezza e configurazioni consigliate per identità e dispositivi](microsoft-365-policies-configurations.md) (questi suggerimenti includono la guida per gli ambienti ADFS)
