---
title: Identità e il dispositivo configurazioni access - Microsoft 365 Enterprise
description: Vengono descritti i suggerimenti di Microsoft e concetti alla base per la distribuzione di posta elettronica protetta, documenti e App criteri e le configurazioni.
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/11/2018
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: 74378da4206c3735cd949358c6cb34b314c82b97
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868300"
---
# <a name="identity-and-device-access-configurations"></a>Configurazioni di identità e accesso dei dispositivi

In questa serie di articoli viene descritto come configurare protezione dell'accesso ai servizi cloud mediante la mobilità aziendale + prodotti per la sicurezza per l'implementazione di un ambiente consigliato e alla configurazione, incluso un insieme di criteri di accesso condizionale prescritto e funzionalità correlate. È possibile utilizzare questa guida per la protezione dell'accesso a tutti i servizi integrati con Azure Active Directory, inclusi servizi di Office 365, altri SaaS applicazioni e servizi locali pubblicati con Proxy dell'applicazione di Azure Active Directory. 

Questi suggerimenti vengono allineati con Microsoft sicura punteggio, oltre a [identity punteggio in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/identity-secure-score) e aumentano i punteggi per l'organizzazione. Questi suggerimenti inoltre consentono di implementare questi [cinque passaggi per la protezione dell'infrastruttura di identità](https://docs.microsoft.com/en-us/azure/security/azure-ad-secure-steps). 

Microsoft consapevole del fatto che alcune organizzazioni hanno requisiti dell'ambiente univoco o complessità. Se si è uno di tali organizzazioni, utilizzare i suggerimenti come punto di partenza. Tuttavia, la maggior parte delle organizzazioni possono implementare questi consigli come indicato. 

## <a name="intended-audience"></a>Destinatari

Questi suggerimenti sono destinati ai professionisti dell'IT familiarità con [Office 365](https://technet.microsoft.com/library/dn127064(v=office.14).aspx) e [Microsoft Enterprise mobilità + protezione](http://microsoft.com/ems) che include, ad esempio, Azure Active Directory (identità), Microsoft e gli architetti di Enterprise Intune (gestione di dispositivi) e la protezione delle informazioni di Azure (la protezione dei dati).

### <a name="customer-environment"></a>Ambiente cliente

I criteri consigliati sono applicabili per le organizzazioni aziendali operativo entrambi completamente nel cloud Microsoft e per l'ambiente ibrido i clienti con l'infrastruttura distribuzione locale sia nel cloud Microsoft.

Molti dei suggerimenti forniti si basano sui servizi disponibili solo con le licenze di sicurezza (EMS) E5 + mobilità aziendale. Consigli presentati presuppongono funzionalità complete di licenza EMS E5.

Per le organizzazioni che non dispongono di licenze sicurezza E5 + mobilità aziendale, si consiglia di che almeno implementano funzionalità di protezione di base Azure Active Directory inclusi in tutti i piani. Ulteriori informazioni sono disponibili nell'articolo, [che cos'è previsto protezione](/azure/active-directory/active-directory-conditional-access-baseline-protection) nella libreria di Azure Active Directory.

### <a name="caveats"></a>Avvertenze

L'organizzazione può essere soggetto a requisiti di conformità alle normative o altri, incluse indicazioni specifiche che potrebbero essere necessario applicare i criteri che si discosta da queste configurazioni consigliate. Queste configurazioni consigliabile controllare l'utilizzo non è stato passato disponibili. Questi controlli, è consigliabile poiché si ritiene che rappresentano un equilibrio tra protezione e produttività.  

Svolto ottimali per tenere conto di un'ampia gamma di requisiti di protezione dell'organizzazione, non si è in grado di account per tutti i possibili requisiti o per tutti gli aspetti univoci dell'organizzazione.

## <a name="three-tiers-of-protection"></a>Tre livelli di protezione

La maggior parte delle organizzazioni hanno requisiti specifici relativi a sicurezza e protezione dei dati. Tali requisiti variano in base al settore e alle mansioni lavorative all'interno delle organizzazioni. Ad esempio, l'ufficio legale e gli amministratori di Office 365 potrebbero richiedere maggiore sicurezza e controlli di protezione sulle informazioni della corrispondenza tramite posta elettronica che non sono richiesti per gli utenti di altre business unit.

Ogni settore include anche i propri set di specializzate normative. Invece di fornire un elenco di tutte le opzioni di protezione o di un suggerimento per funzione di processo o segmento di settore, sono stati forniti consigli per tre diversi livelli di sicurezza e protezione che può essere applicata in base la granularità delle proprie esigenze .

- **Protezione di base** , è consigliabile definire uno standard minimo per la protezione dei dati, nonché le identità e i dispositivi che accedono ai dati. È possibile seguire i suggerimenti di base per fornire la protezione predefinita complessa che soddisfi le esigenze di molte organizzazioni.
- **Protezione dati riservati** , alcuni clienti sono un sottoinsieme di dati che devono essere protetti livelli superiori richiedano da tutti i dati da proteggere un livello superiore. È possibile applicare protezione superiori a tutti o set di dati specifici dell'ambiente Office 365. È consigliabile proteggere le identità e i dispositivi che accedono ai dati riservati con paragonabili livelli di protezione.  
- **Altamente regolamentato** , alcune organizzazioni possono disporre di una piccola quantità di dati altamente classificati, segreti commerciali o dati regolamentati. Microsoft offre funzionalità che consentono alle organizzazioni di soddisfare questi requisiti, inclusa la protezione sono state aggiunta le identità e dei dispositivi.

![Cono sicurezza - tutti i clienti > alcuni clienti > clienti specifici. Vasta gamma di applicazioni per applicazione](../images/M365-idquality-threetiers.png)

Questa guida viene illustrato come implementare la protezione per le identità e dispositivi per ognuno di questi livelli di protezione. Utilizzare questa guida come punto di partenza per l'organizzazione e modificare i criteri in base alle esigenze specifiche dell'organizzazione.

È importante utilizzare i livelli di protezione coerenti tra i dati, le identità e dispositivi. Ad esempio, se si implementa questa Guida, assicurarsi di proteggere i dati a livelli paragonabili. Questi modelli di architettura mostrano le funzionalità che sono paragonabili.

**Identità e dispositivo di protezione per Office 365**<br/>
![Anteprima poster "identità e dispositivo di protezione per Office 365"](../images/O365_Identity_device_protection_thumb.png)<br/>
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Altre lingue](https://www.microsoft.com/download/details.aspx?id=55032)

**Soluzioni per la protezione dei file in Office 365**<br/>
![Anteprima poster "Soluzioni di protezione dei File in Office 365"](../images/24be68b5-d852-4fdb-94ad-94491a19edd8.png)<br/>
[PDF](http://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.pdf) | [Visio](http://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.vsdx)

## <a name="security-and-productivity-trade-offs"></a>Compromesso tra sicurezza e produttività

L'implementazione di qualsiasi strategia di protezione, è necessario un compromesso tra protezione e produttività. È utile valutare l'effetto dell'equilibrio tra protezione, le funzionalità e facilità di utilizzo ogni decisione.

![Triad sicurezza bilanciamento del carico di sicurezza, le funzionalità e facilità di utilizzo.](media/policies-configurations/security-triad.png)

I suggerimenti forniti si basano sui seguenti principi:

- Conoscenza dei destinatari flessibilità per la loro protezione e ai requisiti funzionali.
- Applicare criteri di sicurezza appena nel tempo e assicurarsi che sia significativa.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Servizi e i concetti relativi all'identità e dei dispositivi la protezione dell'accesso

Microsoft 365 Enterprise è progettato per organizzazioni di grandi dimensioni e sull'integrazione di Office 365 Enterprise, Windows 10 Enterprise e mobilità aziendale + sicurezza (EMS) per consentire a chiunque di essere creative e lavoro contemporaneamente, in modo protetto.

In questa sezione viene fornita una panoramica di servizi Microsoft 365 e funzionalità importanti per l'accesso di dispositivi e identità.

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Azure Active Directory fornisce una suite completa dell'identità funzionalità di gestione. I suggerimenti per la protezione dell'accesso, utilizzare le funzionalità seguenti:

- **[Programma di reimpostazione password self-service (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks.md)** : consentire agli utenti di reimpostare le password senza l'intervento dell'help desk in modo sicuro fornendo verifica più metodi di autenticazione che l'amministratore può controllare.
- **[Autenticazione a più fattori (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks.md)** , ovvero MFA richiede agli utenti di utilizzare due forme di verifica, ad esempio una password utente e una notifica da app Authenticator Microsoft o una chiamata telefonica. MFA riduce il rischio che un'identità rubata può essere utilizzato per l'accesso dell'ambiente Office 365.
- **[Accesso condizionato](/azure/active-directory/conditional-access/overview.md)** , ovvero Azure Active Directory valuta le condizioni di accesso utente e utilizza criteri di accesso condizionato creati per consentire l'accesso. Ad esempio, in questa guida viene indicato è illustrato come creare un criterio di accesso condizionale per richiesta la conformità con dispositivi per l'accesso ai dati riservati. Si riduce il rischio che un utente malintenzionato con un'identità rubato può accedere ai dati riservati. Protegge inoltre i dati riservati sui dispositivi dal momento che i dispositivi di soddisfano specifici requisiti di sicurezza e integrità.
- **[Gruppi di Azure Active Directory](/azure/active-directory/fundamentals/active-directory-manage-groups.md)** , ovvero le regole di accesso condizionato, la gestione dei dispositivi con Intune, e anche le autorizzazioni per i file e i siti all'interno dell'organizzazione si basano su assegnati agli utenti e/o gruppi di Azure Active Directory. È consigliabile che è creare gruppi di Azure Active Directory che corrispondono ai livelli di protezione che si stanno implementando. Ad esempio, staff executive sono probabilmente maggiore valore gli obiettivi per utenti malintenzionati. Di conseguenza, è opportuno assegnare i dipendenti a un gruppo di Azure Active Directory e assegnare il gruppo di criteri di accesso condizionale e altri criteri che applicano un livello maggiore di protezione per l'accesso.
- **[Registrazione periferica](/azure/active-directory/devices/overview.md)** , ovvero un dispositivo di registrazione in Azure Active Directory per fornire un'identità (identity) del dispositivo. Questo parametro identity viene utilizzata per autenticare il dispositivo, quando un utente accede e per applicare le regole di accesso condizionale che richiedono PC compatibile o dominio. Per questa guida viene utilizzata la registrazione di dispositivo per registrare automaticamente computer aggiunto al dominio di Windows. Registrazione periferica è un prerequisito per la gestione dei dispositivi con Intune. 
- **[Protezione dell'identità di Azure Active Directory](/azure/active-directory/identity-protection/overview)** , ovvero la protezione dell'identità di Azure Active Directory consente di rilevare potenziale vulnerabilità che interessano le identità dell'organizzazione e configurare i criteri di correzione automatica per utente rischi e dei rischi bassa, medio e alta accesso. Questa guida si basa sulla valutazione dei rischi per applicare criteri di accesso condizionale per l'autenticazione a più fattori. Questa guida include inoltre un criterio di accesso condizionale che richiede agli utenti di modificare la password se viene rilevata qualche attività ad alto rischio per il proprio account.

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune) è servizio di gestione di Microsoft basata su cloud dispositivo mobile. Questa guida viene consigliato di gestione dei dispositivi di PC di Windows con Intune e viene consigliato di configurazioni dei criteri di conformità di dispositivi. Intune determina se i dispositivi sono conformi e invia i dati di Azure Active Directory da utilizzare per l'applicazione di criteri di accesso condizionale.

#### <a name="intune-app-protection"></a>Protezione app Intune

Criteri di [protezione app Intune](https://docs.microsoft.com/intune/app-protection-policy) è utilizzabile per proteggere i dati dell'azienda di App per dispositivi mobili con o senza dispositivi registrazione in Gestione. Intune contribuisce a proteggere le informazioni di Office 365, assicurandosi che dipendenti possono comunque essere perdita di dati che impedisce e produttivi. Per implementare criteri a livello di applicazione, è possibile limitare l'accesso alle risorse aziendali e mantenere i dati all'interno del controllo del reparto IT.

Questa guida viene illustrato come creare criteri consigliati per imporre l'utilizzo di applicazioni approvate e determinare come è possibile utilizzare queste applicazioni con i dati business.

### <a name="office-365"></a>Office 365

Questa guida viene illustrato come implementare un set di criteri per proteggere l'accesso a Office 365, inclusi Exchange Online, SharePoint Online e OneDrive for Business. Oltre a implementare questi criteri, è consigliabile che inoltre si aumenta il livello di protezione per Office 365 tenant utilizza queste risorse:

- [Configure Office 365 tenant per una maggiore sicurezza](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355) , si applicano queste procedure consigliate per la protezione di base per il tenant di Office 365.
- [Roadmap di protezione di office 365: principali priorità per i primi 30 giorni, 90 giorni e oltre](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) , questi consigli includono registrazione, dati governance, accesso di amministrazione e protezione da minacce.
- [I file e siti di SharePoint Online sicura](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files) : questa serie di articoli viene descritto come proteggere i file e i siti livelli appropriati per la protezione di base, di importanti o altamente riservati.

### <a name="windows-10-and-office-365-proplus"></a>Windows 10 e Office 365 ProPlus

Windows 10 e Office 365 ProPlus sono l'ambiente client consigliato per PC. È consigliabile Windows 10 come Azure è progettato per garantire un'esperienza semplicità possibile per locali e di Azure Active Directory. Windows 10 include anche funzionalità di protezione avanzata che possono essere gestite tramite Intune. Office 365 ProPlus sono incluse le versioni più recenti di applicazioni di Office. Queste utilizzare l'autenticazione moderno, offre maggiore protezione e un requisito per l'accesso condizionale. Queste applicazioni includano anche gli strumenti di conformità e sicurezza avanzati.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>L'applicazione di queste funzionalità tra tre livelli di protezione

Nella tabella seguente sono riepilogati i consigli per l'utilizzo di queste funzionalità tra tre livelli di protezione.

|Meccanismo di protezione|Versione di base|Dati sensibili|Protezione per ambienti altamente regolamentati|
|:-------------------|:-------|:--------|:---------------|
|**Applicare l'autenticazione a più fattori**|A partire da rischio di accesso medio|A partire da rischio di accesso basso|Per tutte le nuove sessioni|
|**Applicare modifica password**|Per gli utenti ad alto rischio|Per gli utenti ad alto rischio|Per gli utenti ad alto rischio|
|**Applicare la protezione delle applicazioni di Intune**|Sì|Sì|Sì|
|**Applicare la registrazione di Intune**|Richiede un conforme o dominio aggiunto al PC, ma Consenti BYOD telefoni/Tablet|Richiedi un dispositivo conforme o aggiunto a un dominio|Richiedi un dispositivo conforme o aggiunto a un dominio|

## <a name="device-ownership"></a>Proprietà del dispositivo

Nella tabella precedente riflette le tendenze per molte organizzazioni supportare una combinazione dei dispositivi di proprietà dell'azienda, nonché dispositivi personali o portare in primo piano-your-proprietario (BYOD) per abilitare la produttività mobile tra le risorse umane. Criteri di protezione App Intune assicurarsi di posta elettronica è protetto da exfiltrating da Outlook mobile app e altre applicazioni per dispositivi mobili di Office, in dispositivi di proprietà dell'azienda e BYOD.  

È consigliabile aziendale e di proprietà dispositivi essere gestiti da Intune o dominio per applicare altri tipi di protezione e controllo.  A seconda di riservatezza dei dati, l'organizzazione può scegliere di consentire non BYOD per utenti specifici o App specifiche.

## <a name="next-steps"></a>Passaggi successivi

[Lavoro prerequisito per l'implementazione di criteri di accesso di identità e dei dispositivi](identity-access-prerequisites.md)