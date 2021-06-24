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
description: In questo argomento viene illustrata la configurazione consigliata per le impostazioni a livello di tenant che influiscono sulla sicurezza dell'ambiente Microsoft 365 locale.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b1bb3f9bf6507e41d8b927137a9ab9ea8803637c
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105525"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>Configurare il tenant di Microsoft 365 per una maggiore sicurezza

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In questo argomento viene illustrata la configurazione consigliata per le impostazioni a livello di tenant che influiscono sulla sicurezza dell'ambiente Microsoft 365 locale. Le esigenze di sicurezza potrebbero richiedere una maggiore o minore sicurezza. Usa questi suggerimenti come punto di partenza.

## <a name="check-office-365-secure-score"></a>Controllare Office 365 punteggio sicuro

Office 365 Secure Score analizza la sicurezza dell'organizzazione in base alle attività e alle impostazioni di sicurezza regolari e assegna un punteggio. Per iniziare, prendere nota del punteggio corrente. La regolazione di alcune impostazioni a livello di tenant aumenterà il punteggio. L'obiettivo non è raggiungere il punteggio massimo, ma essere consapevoli delle opportunità di protezione dell'ambiente che non influiscono negativamente sulla produttività degli utenti. Vedere [Microsoft Secure Score](../defender/microsoft-secure-score.md).

## <a name="tune-threat-management-policies-in-the-microsoft-365-defender-portal"></a>Ottimizzare i criteri di gestione delle minacce nel Microsoft 365 Defender portale

Il Microsoft 365 Defender portale include funzionalità che proteggono l'ambiente. Include inoltre report e dashboard che è possibile utilizzare per monitorare ed eseguire azioni. Alcune aree sono associate a configurazioni dei criteri predefinite. Alcune aree non includono criteri o regole predefiniti. Visitare questi criteri in Criteri di **collaborazione &** posta elettronica & criteri di minaccia per ottimizzare le impostazioni di gestione delle \>  \> minacce per un ambiente più sicuro. 

<br>

****

|Area|Criterio predefinito?|Consiglio|
|---|---|---|
|**Anti-phishing**|Sì|Configurare il criterio anti-phishing predefinito come descritto di seguito: Configurare le impostazioni di protezione [anti-phishing in EOP](protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365)e Defender per Office 365 . <p> Ulteriori informazioni: <ul><li>[Criteri anti-phishing in Microsoft 365](set-up-anti-phishing-policies.md)</li><li>[Impostazioni dei criteri anti-phishing consigliate in Microsoft Defender per Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</li><li> [Dati analitici sull'imitazione](impersonation-insight.md)</li><li>[Informazioni di intelligence di spoofing in EOP](learn-about-spoof-intelligence.md)</li><li>[Gestire l'elenco tenant consentiti/bloccati](tenant-allow-block-list.md).</li></ul>|
|**Motore antimalware**|Sì|Configurare il criterio antimalware predefinito come descritto qui: [Configurare le impostazioni di protezione antimalware in EOP.](protect-against-threats.md#part-1---anti-malware-protection-in-eop) <p> Ulteriori informazioni: <ul><li>[Protezione antimalware](anti-malware-protection.md)</li><li>[Impostazioni dei criteri antimalware consigliate](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)</li><li>[Configurazione dei criteri anti-malware](configure-anti-malware-policies.md)</li></ul>|
|**Allegati sicuri in Defender per Office 365**|No|Configurare le impostazioni globali per Cassaforte allegati e creare un criterio allegati Cassaforte come descritto qui: Configurare le impostazioni degli allegati Cassaforte [in Microsoft Defender per Office 365](protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365). <p> Ulteriori informazioni: <ul><li>[Impostazioni Cassaforte allegati consigliati](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</li><li>[Cassaforte Allegati in Microsoft Defender per Office 365](safe-attachments.md)</li><li>[Configurare i criteri Allegati sicuri](set-up-safe-attachments-policies.md)</li><li>[Allegati sicuri per SharePoint, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md)</li><li>[Sicurezza documenti in Microsoft 365 E5](safe-docs.md)</li></ul>|
|**Cassaforte Collegamenti in Microsoft Defender per Office 365**|No|Configurare le impostazioni globali per i collegamenti Cassaforte e creare un criterio collegamenti Cassaforte come descritto qui: Configurare le impostazioni dei collegamenti di Cassaforte [in Microsoft Defender per Office 365](protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365). <p> Ulteriori informazioni: <ul><li>[Impostazioni consigliate Cassaforte collegamenti](recommended-settings-for-eop-and-office365.md#safe-links-settings)</li><li>[Configurare i criteri Collegamenti sicuri](set-up-safe-links-policies.md)</li><li>[Cassaforte Collegamenti in Microsoft Defender per Office 365](safe-links.md)</li><li>[Configurare le impostazioni globali per Cassaforte collegamenti in Microsoft Defender per Office 365](configure-global-settings-for-safe-links.md)</li></ul>|
|**Protezione da posta indesiderata (filtro posta)**|Sì|Configurare il criterio di protezione da posta indesiderata predefinito come descritto di seguito: Configurare le impostazioni di protezione da posta [indesiderata in EOP](protect-against-threats.md#part-3---anti-spam-protection-in-eop) <p> Ulteriori informazioni: <ul><li>[Impostazioni dei criteri di protezione da posta indesiderata consigliate](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)</li><li>[Protezione da posta indesiderata in EOP](anti-spam-protection.md)</li><li>[Configurare criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md)</li></ul>|
|***Autenticazione posta elettronica***|Sì|L'autenticazione della posta elettronica utilizza i record DNS per aggiungere informazioni verificabili ai messaggi di posta elettronica relativi all'origine e al mittente del messaggio. Microsoft 365 configura automaticamente l'autenticazione della posta elettronica per il relativo dominio predefinito (onmicrosoft.com), ma gli Microsoft 365 amministratori possono anche configurare l'autenticazione della posta elettronica per i domini personalizzati. Vengono utilizzati tre metodi di autenticazione: <ul><li>Sender Policy Framework (o SPF).</li><ul><li>Per la configurazione, vedere [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</li></ul> <li>DomainKeys Identified Mail (DKIM).</li><ul><li>Vedi [Usare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato.](use-dkim-to-validate-outbound-email.md)</li><li>Dopo aver configurato DKIM, abilitarlo nel Microsoft 365 Defender portale.</li></ul><li>DMARC (Domain-based Message Authentication, Reporting, and Conformance).</li><ul><li>Per la configurazione DMARC [Utilizzare DMARC per convalidare la posta elettronica in Microsoft 365](use-dmarc-to-validate-email.md).</li></ul></ul>|
|

> [!NOTE]
> Per distribuzioni non standard di SPF, distribuzioni ibride e risoluzione dei problemi: come Microsoft 365 utilizza [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md)per impedire lo spoofing .

## <a name="view-dashboards-and-reports-in-the-microsoft-365-defender-portal"></a>Visualizzare dashboard e report nel portale Microsoft 365 Defender dati

Visitare questi report e dashboard per ulteriori informazioni sull'integrità dell'ambiente. I dati in questi report diventeranno più ricchi quando l'organizzazione utilizza Office 365 servizi. Per il momento, acquisire familiarità con gli elementi che è possibile monitorare ed eseguire.

<br>

****

|Dashboard|Descrizione|
|---|---|
|Report di sicurezza della posta elettronica|Questi report sono disponibili in Exchange Online Protection. Per ulteriori informazioni, vedere [View email security reports in the Microsoft 365 Defender portal.](view-email-security-reports.md)|
|Defender per Office 365 report|I report sono disponibili solo in Defender per Office 365. Per ulteriori informazioni, vedere [View Defender for Office 365 reports in the Microsoft 365 Defender portal.](view-reports-for-mdo.md)|
|Report e informazioni dettagliate sul flusso di posta|Questi report e informazioni dettagliate sono disponibili nell Exchange ac (EAC). Per ulteriori informazioni, vedere [Mail flow reports e](/exchange/monitoring/mail-flow-reports/mail-flow-reports) Mail flow [insights.](/exchange/monitoring/mail-flow-insights/mail-flow-insights)|
|[Esplora minacce (o rilevamenti in tempo reale)](threat-explorer.md)|Se si sta analizzando o si verifica un attacco al tenant, usare Explorer (o rilevamenti in tempo reale) per analizzare le minacce. Explorer (e il report sui rilevamenti in tempo reale) mostra il volume di attacchi nel tempo ed è possibile analizzare questi dati in base alle famiglie di minacce, all'infrastruttura degli utenti malintenzionati e altro ancora. È inoltre possibile contrassegnare qualsiasi messaggio di posta elettronica sospetto per l'elenco Eventi imprevisti.|
|

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>Configurare impostazioni Exchange Online a livello di tenant

Ecco un paio di impostazioni aggiuntive consigliate.

<br>

****

|Area|Consiglio|
|---|---|
|**Regole del flusso di** posta (note anche come regole di trasporto)|Aggiungere una regola del flusso di posta per proteggere da ransomware bloccando i tipi di file eseguibili e Office file che contengono macro. Per ulteriori informazioni, vedere [Use mail flow rules to inspect message attachments in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments). <p> Vedi questi argomenti aggiuntivi: <ul><li>[Proteggere l'ambiente da ransomware](../../admin/security-and-compliance/secure-your-business-data.md#5-protect-against-ransomware)</li><li>[Protezione da malware e ransomware in Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[Ripristino da un attacco ransomware in Office 365](recover-from-ransomware.md)</li></ul> <p> Creare una regola del flusso di posta per impedire l'inoltro automatico della posta elettronica ai domini esterni. Per ulteriori informazioni, vedere [Mitigating Client External Forwarding Rules with Secure Score.](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score) <p> Ulteriori informazioni: [Regole del flusso di posta (regole di trasporto) in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**Autenticazione moderna**|L'autenticazione moderna è un prerequisito per l'utilizzo dell'autenticazione a più fattori (MFA). L'autenticazione a più fattori è consigliata per proteggere l'accesso alle risorse cloud, inclusa la posta elettronica. <p> Vedi questi argomenti: <ul><li>[Abilitare o disabilitare l’autenticazione moderna in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype for Business Online: abilitare il tenant per l'autenticazione moderna](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> L'autenticazione moderna è abilitata per impostazione Office 2016, SharePoint Online e OneDrive for Business. <p> Ulteriori informazioni: [Funzionamento dell'autenticazione moderna Office 2013 e Office 2016](../../enterprise/modern-auth-for-office-2013-and-2016.md)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>Configurare i criteri di condivisione a livello di tenant nell SharePoint di amministrazione

Suggerimenti di Microsoft per la configurazione SharePoint siti del team a livelli di protezione crescenti, a partire dalla protezione di base. Per ulteriori informazioni, vedere [Policy recommendations for securing SharePoint sites and files](sharepoint-file-access-policies.md).

SharePoint i siti del team configurati a livello di base consentono la condivisione di file con utenti esterni tramite collegamenti di accesso anonimo. Questo approccio è consigliato invece di inviare file tramite posta elettronica.

Per supportare gli obiettivi di protezione di base, configurare i criteri di condivisione a livello di tenant come consigliato qui. Le impostazioni di condivisione per i singoli siti possono essere più restrittive rispetto a questo criterio a livello di tenant, ma non più permissivo.

<br>

****

|Area|Include un criterio predefinito|Consiglio|
|---|---|---|
|**Condivisione** (SharePoint Online e OneDrive for Business)|Sì|La condivisione esterna è abilitata per impostazione predefinita. Queste impostazioni sono consigliate: <ul><li>Consentire la condivisione a utenti esterni autenticati e l'utilizzo di collegamenti di accesso anonimo (impostazione predefinita).</li><li>I collegamenti di accesso anonimo scadono in questo numero di giorni. Immettere un numero, se lo si desidera, ad esempio 30 giorni.</li><li>Tipo di collegamento predefinito: selezionare Interno (solo utenti dell'organizzazione). Gli utenti che desiderano condividere utilizzando collegamenti anonimi devono scegliere questa opzione dal menu di condivisione.</li></ul> <p> Ulteriori informazioni: [Panoramica della condivisione esterna](/sharepoint/external-sharing-overview)|
|

SharePoint'interfaccia di amministrazione e OneDrive for Business'interfaccia di amministrazione includono le stesse impostazioni. Le impostazioni in entrambe le interfaccia di amministrazione si applicano a entrambi.

## <a name="configure-settings-in-azure-active-directory"></a>Configurare le impostazioni in Azure Active Directory

Assicurati di visitare queste due aree in Azure Active Directory completare la configurazione a livello di tenant per ambienti più sicuri.

### <a name="configure-named-locations-under-conditional-access"></a>Configurare percorsi denominati (con accesso condizionale)

Se l'organizzazione include uffici con accesso sicuro alla rete, aggiungere gli intervalli di indirizzi IP attendibili Azure Active Directory come posizioni denominate. Questa funzionalità consente di ridurre il numero di falsi positivi segnalati per gli eventi di rischio di accesso.

Vedere: [Posizioni denominate in Azure Active Directory](/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>Bloccare le app che non supportano l'autenticazione moderna

L'autenticazione a più fattori richiede app che supportano l'autenticazione moderna. Le app che non supportano l'autenticazione moderna non possono essere bloccate utilizzando regole di accesso condizionale.

Per gli ambienti sicuri, assicurati di disabilitare l'autenticazione per le app che non supportano l'autenticazione moderna. È possibile eseguire questa operazione in Azure Active Directory con un controllo che sarà disponibile a breve.

Nel frattempo, utilizzare uno dei metodi seguenti per ottenere questo risultato SharePoint Online e OneDrive for Business:

- Usare PowerShell, vedere [Bloccare le app che non usano l'autenticazione moderna (ADAL).](/mem/intune/protect/app-modern-authentication-block)
- Configura questa impostazione nell'SharePoint di amministrazione nella pagina "Accesso al dispositivo", ovvero "Controlla l'accesso da app che non usano l'autenticazione moderna". Scegliere Blocca.

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Introduzione a Cloud App Security o Office 365 Cloud App Security

Utilizzare Office 365 Cloud App Security per valutare i rischi, per avvisare le attività sospette e per eseguire automaticamente un'azione. Richiede Office 365 E5 piano.

In caso contrario, Microsoft Cloud App Security per ottenere una visibilità più profonda anche dopo aver concesso l'accesso, controlli completi e una protezione migliorata per tutte le applicazioni cloud, tra cui Office 365.

Poiché questa soluzione consiglia il piano EMS E5, è consigliabile iniziare con Cloud App Security in modo da poterlo usare con altre applicazioni SaaS nell'ambiente. Iniziare con le impostazioni e i criteri predefiniti.

Ulteriori informazioni:

- [Distribuzione di Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security)
- [Ulteriori informazioni su Microsoft Cloud App Security](https://www.microsoft.com/cloud-platform/cloud-app-security)
- [Che cos'è Cloud App Security?](/cloud-app-security/what-is-cloud-app-security)

![Dashboard di Cloud App Security](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>Risorse aggiuntive

Questi articoli e guide forniscono ulteriori informazioni prescrittive per la protezione dell'Microsoft 365 ambiente:

- Indicazioni sulla sicurezza Microsoft per campagne [politiche, organizzazioni no profit](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) e altre organizzazioni agile (è possibile usare queste indicazioni in qualsiasi ambiente, in particolare in ambienti solo cloud)

- [Criteri e configurazioni di sicurezza consigliati per identità e dispositivi](microsoft-365-policies-configurations.md) (questi suggerimenti includono la Guida per gli ambienti AD FS)
