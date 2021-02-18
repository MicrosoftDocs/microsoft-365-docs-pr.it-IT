---
title: Configurazioni di identità e accesso ai dispositivi - Microsoft 365 per le aziende
description: Descrive i suggerimenti e i concetti di base di Microsoft per la distribuzione di configurazioni e criteri di posta elettronica, documenti e app sicuri.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-overview
ms.technology: mdo
ms.openlocfilehash: e4b85091366927596a2c8f52c579c369fc9697c3
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290718"
---
# <a name="identity-and-device-access-configurations"></a>Configurazioni di identità e accesso dei dispositivi

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)

Il perimetro di sicurezza moderno dell'organizzazione ora si estende oltre la rete per includere gli utenti che accedono alle app basate su cloud da qualsiasi posizione con un'ampia gamma di dispositivi. L'infrastruttura di sicurezza deve determinare se una determinata richiesta di accesso deve essere concessa e in quali condizioni.

Questa determinazione deve basarsi sull'account utente dell'accesso, sul dispositivo in uso, sull'app usata dall'utente per l'accesso, sulla posizione da cui viene effettuata la richiesta di accesso e su una valutazione del rischio della richiesta. Questa funzionalità garantisce che solo gli utenti e i dispositivi autorizzati possano accedere alle risorse cruciali dell'utente.

Questa serie di articoli descrive un set di configurazioni dei prerequisiti per l'identità e l'accesso ai dispositivi e un set di accesso condizionale di Azure Active Directory (Azure AD), Microsoft Intune e altri criteri per proteggere l'accesso alle app e ai servizi cloud aziendali di Microsoft 365, ad altri servizi SaaS e alle applicazioni locali pubblicate con il proxy dell'applicazione Azure AD.

Le impostazioni e i criteri di identità e accesso ai dispositivi sono consigliati in tre livelli: protezione di base, protezione riservata e protezione per ambienti con dati altamente regolamentati o classificati. Questi livelli, e le loro configurazioni corrispondenti, offrono livelli costanti di protezione per tutti i dati, le identità e i dispositivi.

Queste funzionalità e le relative raccomandazioni:

- Sono supportati in Microsoft 365 E3 e Microsoft 365 E5.
- Sono allineati a [Microsoft Secure Score](../mtp/microsoft-secure-score.md) e al punteggio di identità in Azure [AD](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-secure-score)e aumenteranno questi punteggi per l'organizzazione.
- Consente di implementare questi [cinque passaggi per proteggere l'infrastruttura di gestione delle identità.](https://docs.microsoft.com/azure/security/azure-ad-secure-steps)

Se l'organizzazione ha requisiti o complessità dell'ambiente univoci, utilizzare questi suggerimenti come punto di partenza. Tuttavia, la maggior parte delle organizzazioni può implementare questi suggerimenti come prescritto.

Guardare questo video per una rapida panoramica delle configurazioni di identità e accesso ai dispositivi per Microsoft 365 per le aziende.
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxEDQ]

> [!NOTE]
> Microsoft vende anche licenze Enterprise Mobility + Security (EMS) per gli abbonamenti a Office 365. Le funzionalità di EMS E3 ed EMS E5 sono equivalenti a quelle di Microsoft 365 E3 e Microsoft 365 E5. Per [informazioni dettagliate, vedere](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing) i piani EMS.

## <a name="intended-audience"></a>Destinatario previsto

Queste raccomandazioni sono destinate agli architetti aziendali e ai professionisti IT che hanno familiarità con i servizi di sicurezza e produttività cloud di Microsoft 365, che includono Azure AD (identità), Microsoft Intune (gestione dei dispositivi) e Azure Information Protection (protezione dei dati).

### <a name="customer-environment"></a>Ambiente del cliente

I criteri consigliati sono applicabili alle organizzazioni aziendali che operano interamente all'interno del cloud Microsoft e per i clienti con un'infrastruttura di identità ibrida, ovvero una foresta di Servizi di dominio Active Directory locale sincronizzata con un tenant di Azure AD.

Molti dei consigli forniti si basano sui servizi disponibili solo con Microsoft 365 E5, Microsoft 365 E3 con il componente aggiuntivo Identity & Threat Protection, EMS E5 o Azure Premium P2.

Per le organizzazioni che non dispongono di queste licenze, Microsoft consiglia di implementare almeno le impostazioni predefinite di [sicurezza,](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)incluse in tutti i piani di Microsoft 365.

### <a name="caveats"></a>Avvertenze

L'organizzazione potrebbe essere soggetta a requisiti normativi o di altri requisiti di conformità, inclusi suggerimenti specifici che potrebbero richiedere l'applicazione di criteri diversi da queste configurazioni consigliate. Tali configurazioni consigliano controlli dell'utilizzo non disponibili in precedenza. Questi controlli sono consigliati perché riteniamo che rappresentino un equilibrio tra sicurezza e produttività.

We've done our best to account for a wide variety of organizational protection requirements, but we're not able to account for all possible requirements or for all the unique aspects of your organization.

## <a name="three-tiers-of-protection"></a>Tre livelli di protezione

La maggior parte delle organizzazioni hanno requisiti specifici relativi a sicurezza e protezione dei dati. Tali requisiti variano in base al settore e alle mansioni lavorative all'interno delle organizzazioni. Ad esempio, il reparto legale e gli amministratori potrebbero richiedere ulteriori controlli di sicurezza e protezione delle informazioni per la corrispondenza di posta elettronica che non sono necessari per altre unità aziendali.

Ogni settore ha anche il proprio set di normative specializzate. Anziché fornire un elenco di tutte le opzioni di sicurezza possibili o un consiglio per ogni segmento di settore o funzione lavorativa, sono stati forniti consigli per tre diversi livelli di sicurezza e protezione che possono essere applicati in base alla granularità delle proprie esigenze.

- **Protezione di base:** è consigliabile stabilire uno standard minimo per la protezione dei dati, nonché le identità e i dispositivi che accedono ai dati. È possibile seguire questi consigli di base per fornire una protezione predefinita avanzata che soddisfi le esigenze di molte organizzazioni.
- **Protezione dei** dati sensibili: alcuni clienti hanno un sottoinsieme di dati che devono essere protetti a livelli superiori oppure potrebbero richiedere che tutti i dati siano protetti a un livello superiore. È possibile applicare una maggiore protezione a tutti i set di dati o a set di dati specifici nell'ambiente Microsoft 365. È consigliabile proteggere le identità e i dispositivi che accedono ai dati sensibili con livelli di sicurezza analoghi.
- **Dati altamente regolamentati:** alcune organizzazioni possono avere una piccola quantità di dati altamente classificati, che costituiscono segreti commerciali o dati regolamentati. Microsoft offre funzionalità che consentono alle organizzazioni di soddisfare questi requisiti, inclusa la protezione aggiuntiva per identità e dispositivi.

![Cono di sicurezza: tutti i clienti > alcuni clienti > clienti specifici. Applicazione generale a applicazione specifica](../../media/microsoft-365-policies-configurations/M365-idquality-threetiers.png)

Questa guida illustra come implementare la protezione per identità e dispositivi per ognuno di questi livelli di protezione. Utilizzare queste indicazioni come punto di partenza per l'organizzazione e modificare i criteri per soddisfare i requisiti specifici dell'organizzazione.

È importante utilizzare livelli di protezione coerenti tra dati, identità e dispositivi. Ad esempio, se implementi questa guida, assicurati di proteggere i dati a livelli analoghi.

Il modello di identità e protezione dei dispositivi per l'architettura di **Microsoft 365** mostra quali funzionalità sono confrontabili.

[![Immagine di scorrimento per il poster identità e dispositivo di protezione per Microsoft 365](../../media/microsoft-365-policies-configurations/O365_Identity_device_protection_thumb.png)](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) <br> [Visualizzazione in formato PDF](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Download in formato PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Download come Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.vsdx)  

Inoltre, vedere la soluzione Distribuire [la protezione delle informazioni](../../solutions/information-protection-deploy.md) per le normative sulla privacy dei dati per proteggere le informazioni archiviate in Microsoft 365.

## <a name="security-and-productivity-trade-offs"></a>Compromesso tra sicurezza e produttività

L'implementazione di qualsiasi strategia di sicurezza richiede compromessi tra sicurezza e produttività. È utile valutare in che modo ogni decisione influisce sull'equilibrio tra sicurezza, funzionalità e facilità d'uso.

![Security triad balancing security, functionality, and ease of use.](../../media/microsoft-365-policies-configurations/security-triad.png)

Le raccomandazioni fornite si basano sui principi seguenti:

- Conoscere gli utenti ed essere flessibili in base ai requisiti di sicurezza e funzionalità.
- Applicare un criterio di sicurezza nel tempo e assicurarsi che sia significativo.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Servizi e concetti per la protezione dell'identità e dell'accesso ai dispositivi

Microsoft 365 per le aziende è progettato per le organizzazioni di grandi dimensioni per consentire a tutti di essere creativi e collaborare in modo sicuro.

In questa sezione viene fornita una panoramica dei servizi e delle funzionalità di Microsoft 365 importanti per l'identità e l'accesso ai dispositivi.

### <a name="azure-ad"></a>Azure AD

Azure AD offre una famiglia completa di funzionalità di gestione delle identità. È consigliabile usare queste funzionalità per proteggere l'accesso.

|Capacità o funzionalità|Descrizione|Licenze|
|---|---|---|
|[Autenticazione a più fattori (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)|L'autenticazione a più fattori richiede agli utenti di fornire due forme di verifica, ad esempio una password utente più una notifica dall'app Microsoft Authenticator o una telefonata. L'autenticazione a più fattori riduce notevolmente il rischio che le credenziali rubate possano essere usate per accedere all'ambiente. Microsoft 365 usa il servizio Azure AD Multi-Factor Authentication per gli accesso basati su MFA.|Microsoft 365 E3 o E5|
|[Accesso condizionale](/azure/active-directory/conditional-access/overview)|Azure AD valuta le condizioni di accesso dell'utente e usa i criteri di accesso condizionale per determinare l'accesso consentito. Ad esempio, in questa guida viene illustrato come creare un criterio di accesso condizionale per richiedere la conformità del dispositivo per l'accesso ai dati sensibili. In questo modo si riduce notevolmente il rischio che un pirata informatico con il proprio dispositivo e le credenziali rubate possa accedere ai dati sensibili. Protegge anche i dati sensibili nei dispositivi, perché i dispositivi devono soddisfare requisiti specifici per l'integrità e la sicurezza.|Microsoft 365 E3 o E5|
|[Gruppi di Azure AD](/azure/active-directory/fundamentals/active-directory-manage-groups)|I criteri di accesso condizionale, la gestione dei dispositivi con Intune e anche le autorizzazioni per file e siti dell'organizzazione si basano sull'assegnazione agli account utente o ai gruppi di Azure AD. Ti consigliamo di creare gruppi di Azure AD corrispondenti ai livelli di protezione che stai implementando. Ad esempio, il personale esecutiva è probabilmente un target di valore superiore per gli hacker. Pertanto, è opportuno aggiungere gli account utente di questi dipendenti a un gruppo di Azure AD e assegnare questo gruppo ai criteri di accesso condizionale e ad altri criteri che applicano un livello superiore di protezione per l'accesso.|Microsoft 365 E3 o E5|
|[Registrazione dei dispositivi](/azure/active-directory/devices/overview)|Puoi registrare un dispositivo in Azure AD per creare un'identità per il dispositivo. Questa identità viene usata per autenticare il dispositivo quando un utente esegue l'accesso e per applicare criteri di accesso condizionale che richiedono PC conformi o aggiunti a un dominio. Per queste indicazioni, usiamo la registrazione dei dispositivi per registrare automaticamente i computer Windows aggiunti a un dominio. La registrazione dei dispositivi è un prerequisito per la gestione dei dispositivi con Intune.|Microsoft 365 E3 o E5|
|[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)|Consente di rilevare potenziali vulnerabilità che influiscono sulle identità dell'organizzazione e di configurare criteri di correzione automatizzati a rischio di accesso basso, medio e alto e a rischio utente. Queste indicazioni si basano su questa valutazione dei rischi per applicare i criteri di accesso condizionale per l'autenticazione a più fattori. Queste indicazioni includono anche un criterio di accesso condizionale che richiede agli utenti di modificare la password se vengono rilevate attività ad alto rischio per il proprio account.|Microsoft 365 E5, Microsoft 365 E3 con il componente aggiuntivo Identity & Threat Protection, EMS E5 o Azure Premium P2|
|[Reimpostazione della password self-service (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)|Consentire agli utenti di reimpostare le password in modo sicuro e senza l'intervento dell'helpdesk, fornendo la verifica di più metodi di autenticazione che l'amministratore può controllare.|Microsoft 365 E3 o E5|
|[Protezione con password di Azure AD](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)|Rilevare e bloccare le password deboli note, le relative varianti e altri termini deboli specifici dell'organizzazione. Gli elenchi predefiniti di password escluse globalmente sono applicate automaticamente a tutti gli utenti dei tenant di Azure AD. È possibile definire altre voci in un elenco di password escluse personalizzato. Quando gli utenti modificano o reimpostano le loro password, gli elenchi di password escluse sono controllati per applicare l'uso di password sicure.|Microsoft 365 E3 o E5|
|

Ecco i componenti di identità e accesso ai dispositivi, inclusi oggetti, impostazioni e sottoservizi di Intune e Azure AD.

![Componenti dell'identità e dell'accesso ai dispositivi](../../media/microsoft-365-policies-configurations/identity-device-access-components.png)

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune) è il servizio di gestione dei dispositivi mobili basato sul cloud di Microsoft. Queste indicazioni consigliano la gestione dei dispositivi dei PC Windows con Intune e le configurazioni dei criteri di conformità dei dispositivi. Intune determina se i dispositivi sono conformi e invia questi dati ad Azure AD per l'uso durante l'applicazione dei criteri di accesso condizionale.

#### <a name="intune-app-protection"></a>Protezione delle app di Intune

[I criteri di protezione](https://docs.microsoft.com/intune/app-protection-policy) delle app di Intune possono essere usati per proteggere i dati dell'organizzazione nelle app per dispositivi mobili, con o senza registrare i dispositivi nella gestione. Intune consente di proteggere le informazioni, assicurando che i dipendenti possano essere ancora produttivi e impedendo la perdita di dati. Implementando criteri a livello di app, è possibile limitare l'accesso alle risorse aziendali e mantenere i dati sotto il controllo del reparto IT.

Queste indicazioni illustrano come creare criteri consigliati per applicare l'uso di app approvate e per determinare in che modo queste app possono essere usate con i dati business.

### <a name="microsoft-365"></a>Microsoft 365

Questa guida illustra come implementare un set di criteri per proteggere l'accesso ai servizi cloud di Microsoft 365, tra cui Microsoft Teams, Exchange Online, SharePoint Online e OneDrive for Business. Oltre a implementare questi criteri, è consigliabile aumentare anche il livello di protezione per il tenant usando queste risorse:

- [Configurare il tenant per una maggiore sicurezza](tenant-wide-setup-for-increased-security.md)

  Consigli che si applicano alla sicurezza di base per il tenant.

- [Roadmap della sicurezza: priorità principali per i primi 30, 90 giorni e oltre](security-roadmap.md)

  Suggerimenti che includono la registrazione, la governance dei dati, l'accesso dell'amministratore e la protezione dalle minacce.

### <a name="windows-10-and-microsoft-365-apps-for-enterprise"></a>Windows 10 e App Microsoft 365 per grandi imprese

Windows 10 con Microsoft 365 Apps for enterprise è l'ambiente client consigliato per i PC. È consigliabile Windows 10 perché Azure è progettato per offrire l'esperienza più fluida possibile sia per l'ambiente locale che per Azure AD. Windows 10 include anche funzionalità di sicurezza avanzate che possono essere gestite tramite Intune. Microsoft 365 Apps for enterprise include le versioni più recenti delle applicazioni di Office. Questi utilizzano l'autenticazione moderna, che è più sicura e un requisito per l'accesso condizionale. Queste app includono anche strumenti di sicurezza e conformità avanzati.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>Applicazione di queste funzionalità tra i tre livelli di protezione

Nella tabella seguente sono riepilogati i suggerimenti per l'utilizzo di queste funzionalità nei tre livelli di protezione.

|Meccanismo di protezione|Protezione di base|Dati sensibili|Riservatezza elevata|
|---|---|---|---|
|**Applicare l'autenticazione a più fattori**|A partire da rischio di accesso medio|A partire da rischio di accesso basso|Per tutte le nuove sessioni|
|**Applicare la modifica della password**|Per gli utenti ad alto rischio|Per gli utenti ad alto rischio|Per gli utenti ad alto rischio|
|**Applicare la protezione delle applicazioni di Intune**|Sì|Sì|Sì|
|**Applicare la registrazione di Intune per il dispositivo di proprietà dell'organizzazione**|Richiedi un PC conforme o aggiunto a un dominio, ma consenti telefoni e tablet BYOD (Bring-Your-Own Devices)|Richiedere un dispositivo conforme o aggiunto a un dominio|Richiedere un dispositivo conforme o aggiunto a un dominio|
|

## <a name="device-ownership"></a>Proprietà del dispositivo

La tabella precedente riflette la tendenza di molte organizzazioni a supportare una combinazione di dispositivi di proprietà dell'organizzazione, nonché personali o BYOD per consentire la produttività mobile tra la forza lavoro. I criteri di protezione delle app di Intune garantiscono che la posta elettronica sia protetta dall'esfiltrazione dall'app Outlook mobile e da altre app per dispositivi mobili di Office, sia nei dispositivi di proprietà dell'organizzazione che nei BYOD.

È consigliabile che i dispositivi di proprietà dell'organizzazione siano gestiti da Intune o aggiunti a un dominio per applicare protezioni e controllo aggiuntivi. A seconda della riservatezza dei dati, l'organizzazione potrebbe scegliere di non consentire BYOD per utenti specifici o app specifiche.

## <a name="deployment-and-your-apps"></a>Distribuzione e app

Prima di configurare e installare la configurazione dell'identità e dell'accesso ai dispositivi per le app integrate in Azure AD, è necessario:

- Decidi quali app usare nell'organizzazione che vuoi proteggere.
- Analizza questo elenco di app per determinare i set di criteri che forniscono livelli di protezione appropriati.

  Non devi creare set di criteri separati per ogni app, perché la gestione di questi criteri può diventare complicata. Microsoft consiglia di raggruppare le app che hanno gli stessi requisiti di protezione per gli stessi utenti.

  Ad esempio, è possibile disporre di un set di criteri che includano tutte le app di Microsoft 365 per tutti gli utenti per la protezione di base e un secondo set di criteri per tutte le app sensibili, ad esempio quelle utilizzate dalle risorse umane o dai reparti finanziari, e applicarli a tali gruppi.

Dopo aver determinato il set di criteri per le app che vuoi proteggere, implementare i criteri agli utenti in modo incrementale, indirizzando i problemi lungo il percorso.

Ad esempio, configurare i criteri che verranno utilizzati per tutte le app di Microsoft 365 solo per Exchange Online con le modifiche aggiuntive per Exchange. Implementare questi criteri agli utenti e risolvere eventuali problemi. Aggiungere quindi Teams con le modifiche aggiuntive e stenderlo agli utenti. Quindi, aggiungere SharePoint con le modifiche aggiuntive. Continua ad aggiungere il resto delle tue app fino a quando non puoi configurare con sicurezza questi criteri di base per includere tutte le app di Microsoft 365.

Analogamente, per le tue app sensibili, crea il set di criteri e aggiungi un'app alla volta e risolvere eventuali problemi finché non vengono tutti inclusi nel set di criteri per le app sensibili.

Microsoft consiglia di non creare set di criteri che si applicano a tutte le app perché possono comportare alcune configurazioni indesiderate. Ad esempio, i criteri che bloccano tutte le app potrebbero bloccare gli amministratori dal portale di Azure e le esclusioni non possono essere configurate per endpoint importanti come Microsoft Graph.

## <a name="steps-in-the-process-of-configuring-identity-and-device-access"></a>Passaggi del processo di configurazione dell'identità e dell'accesso ai dispositivi

![Passaggi per configurare l'identità e l'accesso al dispositivo.](../../media/microsoft-365-policies-configurations/identity-device-access-steps.png)

1. Configurare le funzionalità delle identità dei prerequisiti e le relative impostazioni.
2. Configurare i criteri comuni di identità e accesso condizionale.
3. Configurare i criteri di accesso condizionale per gli utenti guest ed esterni.
4. Configurare i criteri di accesso condizionale per le app cloud di Microsoft 365, ad esempio Microsoft Teams, Exchange Online e SharePoint.

Dopo aver configurato l'identità e l'accesso ai dispositivi, vedere la guida alla distribuzione delle funzionalità di [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-deployment-checklist-p2) per un elenco di controllo in più fasi delle funzionalità aggiuntive da considerare e azure AD [Identity Governance](https://docs.microsoft.com/azure/active-directory/governance/) per proteggere, monitorare e controllare l'accesso.

## <a name="next-step"></a>Passaggio successivo

[Lavoro prerequisito per l'implementazione di criteri di identità e accesso ai dispositivi](identity-access-prerequisites.md)
