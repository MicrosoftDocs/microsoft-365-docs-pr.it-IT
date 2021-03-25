---
title: Configurare il tenant di Microsoft 365 per una maggiore sicurezza
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
audience: ITPro
ms.topic: article
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
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 64715b026c3dcb029bea4d75697bf687559c168c
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206423"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>Configurare il tenant di Microsoft 365 per una maggiore sicurezza

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In questo argomento viene illustrata la configurazione consigliata per le impostazioni a livello di tenant che influiscono sulla sicurezza dell'ambiente Microsoft 365. Le esigenze di sicurezza potrebbero richiedere una maggiore o minore sicurezza. Usa questi suggerimenti come punto di partenza.

## <a name="check-office-365-secure-score"></a>Controllare il punteggio sicuro di Office 365

Punteggio sicuro di Office 365 analizza la sicurezza dell'organizzazione in base alle attività e alle impostazioni di sicurezza regolari e assegna un punteggio. Per iniziare, prendere nota del punteggio corrente. La regolazione di alcune impostazioni a livello di tenant aumenterà il punteggio. L'obiettivo non è raggiungere il punteggio massimo, ma essere consapevoli delle opportunità di protezione dell'ambiente che non influiscono negativamente sulla produttività degli utenti. Vedere [Microsoft Secure Score](../defender/microsoft-secure-score.md).

## <a name="tune-threat-management-policies-in-the-microsoft-365-security-center"></a>Ottimizzare i criteri di gestione delle minacce nel Centro sicurezza Microsoft 365

Il Centro sicurezza Microsoft 365 include funzionalità che proteggono l'ambiente. Include inoltre report e dashboard che è possibile utilizzare per monitorare ed eseguire azioni. Alcune aree sono associate a configurazioni dei criteri predefinite. Alcune aree non includono criteri o regole predefiniti. Visitare questi criteri in Gestione delle minacce per ottimizzare le impostazioni di gestione delle minacce per un ambiente più sicuro.

****

|Area|Include un criterio predefinito|Consiglio|
|---|---|---|
|**Anti-phishing**|Sì|Se si dispone di un dominio personalizzato, configurare il criterio anti-phishing predefinito per proteggere gli account di posta elettronica degli utenti più importanti, ad esempio il CEO, e per proteggere il dominio. <p> Esaminare [i criteri anti-phishing in Office 365](set-up-anti-phishing-policies.md) e vedere [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md) o [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).|
|**Motore antimalware**|Sì| Modificare il criterio predefinito: <ul><li>Filtro tipi di allegati comuni: selezionare On</li></ul> <p> È inoltre possibile creare criteri di filtro antimalware personalizzati e applicarli a utenti, gruppi o domini specifici nell'organizzazione. <p> Ulteriori informazioni: <ul><li>[Protezione antimalware](anti-malware-protection.md)</li><li>[Configurazione dei criteri anti-malware](configure-anti-malware-policies.md)</li></ul>|
|**Allegati sicuri in Microsoft Defender per Office 365**|No|Nella pagina principale per Allegati sicuri fare clic su **Impostazioni globali** e attivare questa impostazione: <ul><li>**Per altre informazioni, vedere Attivare Microsoft Defender per Office 365 per SharePoint, OneDrive e Microsoft Teams.**</li></ul> <p> Creare un criterio Allegati sicuri con queste impostazioni: <ul><li> **Blocca**: selezionare **Blocca** come risposta malware sconosciuta.</li><li>**Abilita reindirizzamento:** selezionare questa casella e immettere un indirizzo di posta elettronica, ad esempio un account amministratore o di quarantena.</li><li>Applica la selezione precedente se si verifica il timeout o l'errore dell'analisi **antimalware** per gli allegati: selezionare questa casella.</li><li>**_Applicato a_*: **Il dominio del destinatario è** il dominio \> selezionato.</li></ul> <p> Ulteriori informazioni: [Allegati sicuri per SharePoint, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md) e Configurare i criteri allegati [sicuri](set-up-safe-attachments-policies.md)|
|**Collegamenti sicuri in Microsoft Defender per Office 365**|Sì|Nella pagina principale per Collegamenti sicuri fare clic su **Impostazioni globali**: <ul><li>**Usare collegamenti sicuri in: Applicazioni di Office 365**: Verificare che questa impostazione sia attivata.</li><li>**Non tenere traccia quando gli utenti fanno clic su Collegamenti sicuri**: disattiva questa impostazione per tenere traccia dei clic degli utenti.</li></ul> <p> Creare un criterio collegamenti sicuri con queste impostazioni: <ul><li>**Selezionare l'azione per URL sconosciuti potenzialmente dannosi nei messaggi**: verificare che questa impostazione sia **attivata.**</li><li>**Selezionare l'azione per URL sconosciuti** o potenzialmente dannosi in Microsoft Teams: verificare che questa impostazione sia **attivata.**</li><li>**Applica l'analisi degli URL** in tempo reale per i collegamenti sospetti e i collegamenti che puntano ai file: seleziona questa casella.</li><li>**Attendere il completamento dell'analisi degli URL prima di recapitare il** messaggio: selezionare questa casella.</li><li>**Applica collegamenti sicuri ai messaggi di posta elettronica inviati all'interno dell'organizzazione**: selezionare questa casella</li><li>**Non consentire agli utenti di passare all'URL originale**: selezionare questa casella.</li><li>**Applicato a**: **Il dominio del destinatario è** il dominio \> selezionato.</li></ul> <p> Ulteriori informazioni: [Set up Safe Links policies](set-up-safe-links-policies.md).|
|**Protezione da posta indesiderata (filtro posta)**|Sì| Cosa guardare: <ul><li>Troppa posta indesiderata: scegliere le impostazioni personalizzate e modificare il criterio filtro predefinito per la posta indesiderata.</li><li>Spoof intelligence: esaminare i mittenti che effettuano lo spoofing del dominio. Bloccare o consentire questi mittenti.</li></ul> <p> Ulteriori informazioni: Protezione da posta indesiderata di [Microsoft 365](anti-spam-protection.md).|
|***Autenticazione posta elettronica***|Sì|L'autenticazione della posta elettronica utilizza un DNS (Domain Name System) per aggiungere informazioni verificabili ai messaggi di posta elettronica sul mittente di un messaggio di posta elettronica. Microsoft 365 configura l'autenticazione della posta elettronica per il relativo dominio predefinito (onmicrosoft.com), ma gli amministratori di Microsoft 365 possono anche usare l'autenticazione di posta elettronica per i domini personalizzati. Vengono utilizzati tre metodi di autenticazione: <ul><li>Sender Policy Framework (o SPF).</li><ul><li>Per la configurazione, vedere [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</li></ul> <li>DomainKeys Identified Mail (DKIM).</li><ul><li>Vedi [Usare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato.](use-dkim-to-validate-outbound-email.md)</li><li>Dopo aver configurato DKIM, abilitarlo nel Centro sicurezza.</li></ul><li>DMARC (Domain-based Message Authentication, Reporting, and Conformance).</li><ul><li>Per la configurazione DMARC [Utilizzare DMARC per convalidare la posta elettronica in Microsoft 365](use-dmarc-to-validate-email.md).</li></ul></ul>|
|

> [!NOTE]
> Per distribuzioni non standard di SPF, distribuzioni ibride e risoluzione dei problemi: utilizzo di [Sender Policy Framework (SPF) in Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md)per impedire lo spoofing.

## <a name="view-dashboards-and-reports-in-the-security-and-compliance-centers"></a>Visualizzare dashboard e report nei Centri sicurezza e conformità

Visitare questi report e dashboard per ulteriori informazioni sull'integrità dell'ambiente. I dati in questi report diventeranno più ricchi quando l'organizzazione usa i servizi di Office 365. Per il momento, acquisire familiarità con gli elementi che è possibile monitorare ed eseguire. Per ulteriori informazioni, vedere : Report nei Centri sicurezza e conformità di [Microsoft 365.](../../compliance/reports-in-security-and-compliance.md)

****

|Dashboard|Descrizione|
|---|---|
|[Dashboard di gestione delle minacce](security-dashboard.md)|Nella sezione **Gestione** delle minacce del Centro sicurezza usa questo dashboard per visualizzare le minacce già gestite e come utile strumento per segnalare ai decision maker aziendali quali funzionalità di indagine e risposta alle minacce hanno già fatto per proteggere la tua azienda.|
|[Esplora minacce (o rilevamenti in tempo reale)](threat-explorer.md)|Questo è anche nella sezione **Gestione delle** minacce del centro sicurezza. Se si sta analizzando o si verifica un attacco al tenant, usare Explorer (o rilevamenti in tempo reale) per analizzare le minacce. Explorer (e il report sui rilevamenti in tempo reale) mostra il volume di attacchi nel tempo ed è possibile analizzare questi dati in base alle famiglie di minacce, all'infrastruttura degli utenti malintenzionati e altro ancora. È inoltre possibile contrassegnare qualsiasi messaggio di posta elettronica sospetto per l'elenco Eventi imprevisti.|
|Report - Dashboard|Nella sezione **Report** del Centro sicurezza, visualizzare i report di controllo per le organizzazioni di SharePoint Online ed Exchange Online. È inoltre possibile accedere ai report di accesso degli utenti di Azure Active Directory (Azure AD), ai report attività utente e al log di controllo di Azure AD dalla **pagina Visualizza report.**|
|

![Dashboard del Centro sicurezza](../../media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>Configurare impostazioni aggiuntive a livello di tenant di Exchange Online

Molti dei controlli per la sicurezza e la protezione nell'interfaccia di amministrazione di Exchange sono inclusi anche nel centro sicurezza. Non è necessario configurarlo in entrambe le posizioni. Ecco un paio di impostazioni aggiuntive consigliate.

****

|Area|Include un criterio predefinito|Consiglio|
|---|---|---|
|**Flusso di posta** (regole del flusso di posta, note anche come regole di trasporto)|No|Aggiungere una regola del flusso di posta per proteggere da ransomware bloccando i tipi di file eseguibili e i tipi di file di Office che contengono macro. Per ulteriori informazioni, vedere [Use mail flow rules to inspect message attachments in Exchange Online.](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments) <p> Vedi questi argomenti aggiuntivi: <ul><li>[Proteggere l'ambiente da ransomware](../../admin/security-and-compliance/secure-your-business-data.md#5-protect-against-ransomware)</li><li>[Protezione da malware e ransomware in Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[Ripristino da un attacco ransomware in Office 365](recover-from-ransomware.md)</li></ul> <p> Creare una regola del flusso di posta per impedire l'inoltro automatico della posta elettronica ai domini esterni. Per ulteriori informazioni, vedere [Mitigating Client External Forwarding Rules with Secure Score.](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score) <p> Ulteriori informazioni: [Mail flow rules (transport rules) in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**Abilitare l'autenticazione moderna**|No|L'autenticazione moderna è un prerequisito per l'utilizzo dell'autenticazione a più fattori (MFA). L'autenticazione a più fattori è consigliata per proteggere l'accesso alle risorse cloud, inclusa la posta elettronica. <p> Vedi questi argomenti: <ul><li>[Abilitare o disabilitare l’autenticazione moderna in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype for Business online: Abilitare il tenant per l'autenticazione moderna](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> L'autenticazione moderna è abilitata per impostazione predefinita per i client di Office 2016, SharePoint Online e OneDrive for Business. <p> Ulteriori informazioni: Funzionamento dell'autenticazione moderna per le app client di [Office 2013 e Office 2016](../../enterprise/modern-auth-for-office-2013-and-2016.md)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>Configurare i criteri di condivisione a livello di tenant nell'interfaccia di amministrazione di SharePoint

Suggerimenti di Microsoft per la configurazione dei siti del team di SharePoint a livelli di protezione crescenti, a partire dalla protezione di base. Per ulteriori informazioni, vedere [Policy recommendations for securing SharePoint sites and files](sharepoint-file-access-policies.md).

I siti del team di SharePoint configurati a livello di base consentono di condividere file con utenti esterni utilizzando collegamenti di accesso anonimo. Questo approccio è consigliato invece di inviare file tramite posta elettronica.

Per supportare gli obiettivi di protezione di base, configurare i criteri di condivisione a livello di tenant come consigliato qui. Le impostazioni di condivisione per i singoli siti possono essere più restrittive rispetto a questo criterio a livello di tenant, ma non più permissivo.

****

|Area|Include un criterio predefinito|Consiglio|
|---|---|---|
|**Condivisione** (SharePoint Online e OneDrive for Business)|Sì|La condivisione esterna è abilitata per impostazione predefinita. Queste impostazioni sono consigliate: <ul><li>Consentire la condivisione a utenti esterni autenticati e l'utilizzo di collegamenti di accesso anonimo (impostazione predefinita).</li><li>I collegamenti di accesso anonimo scadono in questo numero di giorni. Immettere un numero, se lo si desidera, ad esempio 30 giorni.</li><li>Tipo di collegamento predefinito: selezionare Interno (solo utenti dell'organizzazione). Gli utenti che desiderano condividere utilizzando collegamenti anonimi devono scegliere questa opzione dal menu di condivisione.</li></ul> <p> Ulteriori informazioni: [Panoramica della condivisione esterna](/sharepoint/external-sharing-overview)|
|

L'interfaccia di amministrazione di SharePoint e l'interfaccia di amministrazione di OneDrive for Business includono le stesse impostazioni. Le impostazioni in entrambe le interfaccia di amministrazione si applicano a entrambi.

## <a name="configure-settings-in-azure-active-directory"></a>Configurare le impostazioni in Azure Active Directory

Assicurati di visitare queste due aree in Azure Active Directory per completare la configurazione a livello di tenant per ambienti più sicuri.

### <a name="configure-named-locations-under-conditional-access"></a>Configurare percorsi denominati (con accesso condizionale)

Se l'organizzazione include uffici con accesso sicuro alla rete, aggiungere gli intervalli di indirizzi IP attendibili ad Azure Active Directory come posizioni denominate. Questa funzionalità consente di ridurre il numero di falsi positivi segnalati per gli eventi di rischio di accesso.

Vedere: [Posizioni denominate in Azure Active Directory](/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>Bloccare le app che non supportano l'autenticazione moderna

L'autenticazione a più fattori richiede app che supportano l'autenticazione moderna. Le app che non supportano l'autenticazione moderna non possono essere bloccate utilizzando regole di accesso condizionale.

Per gli ambienti sicuri, assicurati di disabilitare l'autenticazione per le app che non supportano l'autenticazione moderna. È possibile eseguire questa operazione in Azure Active Directory con un controllo disponibile a breve.

Nel frattempo, utilizzare uno dei metodi seguenti per eseguire questa operazione per SharePoint Online e OneDrive for Business:

- Usare PowerShell, vedere [Bloccare le app che non usano l'autenticazione moderna (ADAL).](/mem/intune/protect/app-modern-authentication-block)

- Configurarlo nell'interfaccia di amministrazione di SharePoint nella pagina "Accesso al dispositivo", ovvero "Controllare l'accesso da app che non usano l'autenticazione moderna". Scegliere Blocca.

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Introduzione a Cloud App Security o Office 365 Cloud App Security

Usare Office 365 Cloud App Security per valutare i rischi, avvisare le attività sospette e agire automaticamente. Richiede il piano di Office 365 E5.

In caso contrario, usare Microsoft Cloud App Security per ottenere una visibilità più profonda anche dopo aver concesso l'accesso, controlli completi e una protezione migliorata per tutte le applicazioni cloud, incluso Office 365.

Poiché questa soluzione consiglia il piano EMS E5, è consigliabile iniziare con Cloud App Security in modo da poterlo usare con altre applicazioni SaaS nell'ambiente. Iniziare con le impostazioni e i criteri predefiniti.

Ulteriori informazioni:

- [Distribuzione di Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security)

- [Ulteriori informazioni su Microsoft Cloud App Security](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [Che cos'è Cloud App Security?](/cloud-app-security/what-is-cloud-app-security)

![Dashboard di Cloud App Security](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>Risorse aggiuntive

Questi articoli e guide forniscono ulteriori informazioni prescrittive per la protezione dell'ambiente Microsoft 365:

- Indicazioni sulla sicurezza Microsoft per campagne [politiche, organizzazioni no profit](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) e altre organizzazioni agile (è possibile usare queste indicazioni in qualsiasi ambiente, in particolare in ambienti solo cloud)

- [Criteri e configurazioni di sicurezza consigliati per identità e dispositivi](microsoft-365-policies-configurations.md) (questi suggerimenti includono la Guida per gli ambienti AD FS)