---
title: Le 12 attività principali per i team di sicurezza per supportare il lavoro da casa
f1.keywords:
- CSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- remotework
description: Proteggere la posta elettronica aziendale e i dati da minacce informatiche, inclusi ransomware, phishing e allegati dannosi.
ms.openlocfilehash: 67a882aed34ef60e1f06ab6e304e6611d3ca0600
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922305"
---
# <a name="top-12-tasks-for-security-teams-to-support-working-from-home"></a>Le 12 attività principali per i team di sicurezza per supportare il lavoro da casa

Se sei come [Microsoft](https://www.microsoft.com/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/) e improvvisamente ti trovi a supportare una forza lavoro principalmente basata su casa, vogliamo aiutarti a garantire che l'organizzazione funzioni nel modo più sicuro possibile. In questo articolo vengono assegnate priorità alle attività per consentire ai team di sicurezza di implementare le funzionalità di sicurezza più importanti nel più breve tempo possibile.

![Eseguire queste attività principali per supportare il lavoro da casa.](../media/security/security-support-remote-work.png)

Se si è un'organizzazione di piccole o medie dimensioni che utilizza uno dei piani aziendali di Microsoft, vedere queste risorse:

- [10 modi principali per proteggere i piani di Office 365 e Microsoft 365 per le aziende](../admin/security-and-compliance/secure-your-business-data.md)
- [Microsoft 365 for Campaigns](../campaigns/index.md) (include una configurazione di sicurezza consigliata per Microsoft 365 Business)

Per i clienti che usano i piani aziendali, Microsoft consiglia di completare le attività elencate nella tabella seguente che si applicano al piano di servizio. Se invece di acquistare un piano aziendale di Microsoft 365, si combinano sottoscrizioni, tenere presente quanto segue:

- Microsoft 365 E3 include Enterprise Mobility + Security (EMS) E3 e Azure AD P1
- Microsoft 365 E5 include EMS E5 e Azure AD P2

****

|Passaggio|Attività|Tutti i piani di Office 365 Enterprise|Microsoft 365 E3|Microsoft 365 E5|
|---|---|---|---|---|
|1|[Abilitare Azure AD Multi-Factor Authentication (MFA)](#1-enable-azure-ad-multi-factor-authentication-mfa)|![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|2 |[Protezione contro le minacce](#2-protect-against-threats)|![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|3 |[Configurare Microsoft Defender per Office 365](#3-configure-microsoft-defender-for-office-365)|||![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|4 |[Configurare Microsoft Defender per l'identità](#4-configure-microsoft-defender-for-identity)|||![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|5 |[Attivare Microsoft 365 Defender](#5-turn-on-microsoft-365-defender)|||![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|6 |[Configurare la protezione delle app per dispositivi mobili di Intune per telefoni e tablet](#6-configure-intune-mobile-app-protection-for-phones-and-tablets)||![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|7 |[Configurare L'autenticazione a più fattori e l'accesso condizionale per gli utenti guest, inclusa la protezione delle app di Intune](#7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection)||![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|8 |[Registrare i PC nella gestione dei dispositivi e richiedere PC conformi](#8-enroll-pcs-into-device-management-and-require-compliant-pcs)||![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|9 |[Ottimizzare la rete per la connettività cloud](#9-optimize-your-network-for-cloud-connectivity)|![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|10  |[Formare gli utenti](#10-train-users)|![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|11 |[Introduzione a Microsoft Cloud App Security](#11-get-started-with-microsoft-cloud-app-security)|||![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|12 |[Monitorare le minacce ed eseguire azioni](#12-monitor-for-threats-and-take-action)|![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|

Prima di iniziare, controllare il [punteggio di protezione di Microsoft 365](./mtp/microsoft-secure-score.md) nel Centro sicurezza Microsoft 365. Da un dashboard centralizzato, è possibile monitorare e migliorare la sicurezza per le identità, i dati, le app, i dispositivi e l'infrastruttura di Microsoft 365. Vengono forniti punti per la configurazione delle funzionalità di sicurezza consigliate, l'esecuzione di attività correlate alla sicurezza (ad esempio la visualizzazione di report) o la gestione di suggerimenti con un'applicazione o un software di terze parti. Le attività consigliate in questo articolo aumentano il punteggio.

![Screenshot of Microsoft Secure Score](../media/secure-score.png)

## <a name="1-enable-azure-ad-multi-factor-authentication-mfa"></a>1: abilitare Azure AD Multi-Factor Authentication (MFA)

L'unica cosa migliore che puoi fare per migliorare la sicurezza per i dipendenti che lavorano da casa è attivare la MFA. Se non hai già processi in atto, consideralo come un progetto pilota di emergenza e assicurati di avere persone di supporto pronte ad aiutare i dipendenti che si bloccano. Dato che probabilmente non puoi distribuire dispositivi di sicurezza hardware, usa la biometria di Windows Hello e le app di autenticazione degli smartphone come Microsoft Authenticator.

In genere, Microsoft consiglia di concedere agli utenti 14 giorni per registrare il dispositivo per l'autenticazione a più fattori prima di richiedere l'autenticazione a più fattori. Tuttavia, se la forza lavoro sta improvvisamente lavorando da casa, procedere e richiedere l'autenticazione a più fattori come priorità di sicurezza ed essere pronti ad aiutare gli utenti che ne hanno bisogno.

L'applicazione di questi criteri può richiedere solo pochi minuti, ma è necessario essere pronti a supportare gli utenti nei giorni successivi.

****

|Piano|Consiglio|
|---|---|
|Piani di Microsoft 365 (senza Azure AD P1 o P2)|[Abilitare le impostazioni predefinite di sicurezza in Azure AD](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Le impostazioni predefinite di sicurezza in Azure AD includono la MFA per utenti e amministratori.|
|Microsoft 365 E3 (con Azure AD P1)|Usare i [criteri comuni di accesso condizionale](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) per configurare i criteri seguenti: <br/>- [Richiedere la MFA per amministratori](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br/>- [Richiedere la MFA per tutti gli utenti](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br/> - [Bloccare l'autenticazione legacy](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)|
|Microsoft 365 E5 (con Azure AD P2)|Sfruttando Azure AD Identity Protection, iniziare a implementare il [set raccomandato di accesso condizionale e criteri correlati](./office-365-security/identity-access-policies.md) di Microsoft creando questi due criteri:<br/> - [Richiedere la MFA quando il rischio di accesso è considerato *medio* o *elevato*](./office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br/>- [Bloccare i client che non supportano l'autenticazione moderna](./office-365-security/identity-access-policies.md#block-clients-that-dont-support-multi-factor)<br/>- [Gli utenti a rischio elevato devono modificare la password](./office-365-security/identity-access-policies.md#high-risk-users-must-change-password)|
|

## <a name="2-protect-against-threats"></a>2: Proteggere dalle minacce

Tutti i piani di Microsoft 365 includono un'ampia gamma di funzionalità di protezione dalle minacce. La protezione avanzata per queste funzionalità richiede solo pochi minuti.

- Protezione anti-malware
- Protezione da URL e file dannosi
- Protezione anti-phishing
- Protezione dalla posta indesiderata

Vedere [Protezione dalle minacce in Office 365](office-365-security/protect-against-threats.md) per indicazioni che è possibile usare come punto di partenza.

## <a name="3-configure-microsoft-defender-for-office-365"></a>3: Configurare Microsoft Defender per Office 365

Microsoft Defender per Office 365, incluso in Microsoft 365 E5 e Office 365 E5, protegge l'organizzazione dalle minacce dannose poste da messaggi di posta elettronica, collegamenti (URL) e strumenti di collaborazione. La configurazione può richiedere diverse ore.

Microsoft Defender per Office 365:

- Protegge l'organizzazione da minacce di posta elettronica sconosciute in tempo reale utilizzando sistemi intelligenti che controllano allegati e collegamenti alla ricerca di contenuti dannosi. Questi sistemi automatizzati includono una solida piattaforma di detonazione, euristica e modelli di machine learning.
- Protegge l'organizzazione quando gli utenti collaborano e condividono file, identificando e bloccando file dannosi nei siti del team e nelle raccolte documenti.
- Applica modelli di machine learning e algoritmi avanzati di rilevamento della rappresentazione per evitare attacchi di phishing.

Per una panoramica, incluso un riepilogo dei piani, vedere [Defender for Office 365](office-365-security/office-365-atp.md).

L'amministratore globale può configurare queste protezioni:

- [Configurare i criteri collegamenti sicuri](office-365-security/set-up-atp-safe-links-policies.md)
- [Configurare le impostazioni globali per i collegamenti sicuri](office-365-security/configure-global-settings-for-safe-links.md)
- [Configurare i criteri allegati sicuri](office-365-security/set-up-atp-safe-attachments-policies.md)

È necessario collaborare con l'amministratore di Exchange Online e l'amministratore di SharePoint Online per configurare Defender per Office 365 per questi carichi di lavoro:

- [ATP per SharePoint, OneDrive e Microsoft Teams](office-365-security/atp-for-spo-odb-and-teams.md)

## <a name="4-configure-microsoft-defender-for-identity"></a>4: Configurare Microsoft Defender per l'identità

[Microsoft Defender per identità](/azure-advanced-threat-protection/what-is-atp) è una soluzione di sicurezza basata sul cloud che sfrutta i segnali di Active Directory locali per identificare, rilevare e analizzare minacce avanzate, identità compromesse ed azioni Insider dannose dirette all'organizzazione. Concentrarsi su questo passaggio successivo perché protegge l'infrastruttura locale e cloud, non ha dipendenze o prerequisiti e può offrire vantaggi immediati.

- Vedi [Le guide introduttive a Microsoft Defender per l'identità](/azure-advanced-threat-protection/install-atp-step1) per ottenere rapidamente la configurazione
- Video: [Introduzione a Microsoft Defender for Identity](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- Esaminare le [tre fasi della distribuzione di Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="5-turn-on-microsoft-365-defender"></a>5: Attivare Microsoft 365 Defender

Dopo aver configurato Microsoft Defender per Office 365 e Microsoft Defender for Identity, è possibile visualizzare i segnali combinati di queste funzionalità in un unico dashboard. [Microsoft 365 Defender](./mtp/microsoft-threat-protection.md) riunisce avvisi, eventi imprevisti, analisi e risposta automatizzate e ricerca avanzata tra i carichi di lavoro (Microsoft Defender for Identity, Defender per Office 365, Microsoft Defender for Endpoint e Microsoft Cloud App Security) in un singolo riquadro [in security.microsoft.com](https://security.microsoft.com).

![Illustrazione del dashboard MTP](../media/top-ten-security-remote-work-mtp-dashboard.png)

Dopo aver configurato uno o più dei servizi defender per Office 365, attivare MTP. Le nuove funzionalità vengono aggiunte continuamente a MTP; prendere in considerazione la possibilità di acconsentire esplicitamente alla ricezione delle funzionalità di anteprima.

- [Ulteriori informazioni su MTP](./mtp/microsoft-threat-protection.md)
- [Attivare MTP](./mtp/mtp-enable.md)
- [Acconsentire esplicitamente alle funzionalità di anteprima](./mtp/preview.md)

## <a name="6-configure-intune-mobile-app-protection-for-phones-and-tablets"></a>6: Configurare la protezione delle app per dispositivi mobili di Intune per telefoni e tablet

Microsoft Intune Mobile Application Management (MAM) consente di gestire e proteggere i dati dell'organizzazione su telefoni e tablet senza gestire questi dispositivi. Tenere presente quanto segue:

- Crei un criterio di protezione app (APP) che determina quali app in un dispositivo sono gestite e quali comportamenti sono consentiti (ad esempio, impedire la copia dei dati di un'app gestita in un'app non gestita). Puoi creare un criterio per ogni piattaforma (iOS, Android).
- Dopo aver creato i criteri di protezione delle app, applicali creando una regola di accesso condizionale in Azure AD per richiedere app approvate e protezione dei dati app.

I criteri di protezione app includono molte impostazioni. Fortunatamente, non è necessario conoscere tutte le impostazioni e valutare le opzioni. Microsoft semplifica l'applicazione di una configurazione delle impostazioni consigliando i punti di partenza. Il [framework di protezione dei dati che usa](/mem/intune/apps/app-protection-framework) i criteri di protezione delle app include tre livelli tra cui puoi scegliere.

Ancora meglio, Microsoft coordina questo framework di protezione delle app con un set di accesso condizionale e criteri correlati che consigliamo a tutte le organizzazioni di usare come punto di partenza. Se hai implementato L'autenticazione a più fattori usando le linee guida di questo articolo, sei a metà strada!

Per configurare la protezione delle app per dispositivi mobili, usa le indicazioni in [Criteri comuni di identità e accesso ai dispositivi:](./office-365-security/identity-access-policies.md)

 1. Usa la [guida Applica criteri di protezione dei](./office-365-security/identity-access-policies.md#apply-app-data-protection-policies) dati APP per creare criteri per iOS e Android. Il livello 2 (protezione avanzata dei dati) è consigliato per la protezione di base.
 2. Creare una regola di accesso condizionale in [Richiedi app approvate e protezione APP.](./office-365-security/identity-access-policies.md#require-approved-apps-and-app-protection)

## <a name="7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection"></a>7: Configurare L'autenticazione a più fattori e l'accesso condizionale per gli utenti guest, inclusa la protezione delle app per dispositivi mobili di Intune

Successivamente, è possibile continuare a collaborare e collaborare con gli utenti guest. Se si usa il piano Microsoft 365 E3 e si è implementata l'autenticazione a più fattori per tutti gli utenti, si è impostato.

Se si usa il piano Microsoft 365 E5 e si sfrutta Azure Identity Protection per la MFA basata sui rischi, è necessario apportare un paio di modifiche (perché Azure AD Identity Protection non si estende ai guest):

- Creare una nuova regola di accesso condizionale per richiedere L'autenticazione a più fattori sempre per gli utenti guest e esterni.
- Aggiornare la regola di accesso condizionale MFA basata sui rischi per escludere utenti guest e utenti esterni.

Usa le indicazioni disponibili in Aggiornamento dei criteri comuni per consentire e proteggere l'accesso [guest](./office-365-security/identity-access-policies-guest-access.md) ed esterno per comprendere il funzionamento dell'accesso guest con Azure AD e aggiornare i criteri interessati.

I criteri di protezione delle app per dispositivi mobili di Intune creati, insieme alla regola di accesso condizionale per richiedere app approvate e protezione app, si applicano agli account guest e consentono di proteggere i dati dell'organizzazione.

> [!NOTE]
> Se hai già registrato i PC nella gestione dei dispositivi per richiedere PC conformi, dovrai anche escludere gli account guest dalla regola di accesso condizionale che impone la conformità dei dispositivi.

## <a name="8-enroll-pcs-into-device-management-and-require-compliant-pcs"></a>8: registrare i PC nella gestione dei dispositivi e richiedere PC conformi

Esistono diversi metodi per registrare i dispositivi della forza lavoro. Ogni metodo dipende dalla proprietà del dispositivo (personale o aziendale), dal tipo di dispositivo (iOS, Windows, Android) e dai requisiti di gestione (reimpostazione, affinità, blocco). L'operazione può richiedere un po' di tempo. Vedere: [Registrare i dispositivi in Microsoft Intune](/mem/intune/enrollment/).

Il modo più rapido per iniziare è configurare [la registrazione automatica per i dispositivi Windows 10.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

Puoi anche trarre vantaggio da queste esercitazioni:

- [Usare Autopilot per registrare i dispositivi Windows in Intune](/mem/intune/enrollment/tutorial-use-autopilot-enroll-devices)
- [Usare le funzionalità di registrazione dei dispositivi aziendali di Apple in Apple Business Manager (ABM) per registrare i dispositivi iOS/iPadOS in Intune](/mem/intune/enrollment/tutorial-use-device-enrollment-program-enroll-ios)

Dopo la registrazione dei dispositivi, usa le indicazioni in [Criteri di identità](./office-365-security/identity-access-policies.md) e accesso ai dispositivi comuni per creare questi criteri:

- [Definire i criteri di conformità dei](./office-365-security/identity-access-policies.md#define-device-compliance-policies) dispositivi: le impostazioni consigliate per Windows 10 includono la richiesta di protezione antivirus. Se hai Microsoft 365 E5, usa Microsoft Defender for Endpoint per monitorare l'integrità dei dispositivi dei dipendenti. Assicurarsi che i criteri di conformità per altri sistemi operativi includano la protezione antivirus e il software di protezione end-point.
- [Richiedi PC conformi: questa](./office-365-security/identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets) è la regola di accesso condizionale in Azure AD che applica i criteri di conformità dei dispositivi.

Solo un'organizzazione può gestire un dispositivo, quindi assicurati di escludere gli account guest dalla regola di accesso condizionale in Azure AD. Se non si escludono utenti guest ed esterni dai criteri che richiedono la conformità dei dispositivi, questi criteri bloccheranno questi utenti. Per ulteriori informazioni, vedere [Aggiornamento dei criteri comuni per consentire e proteggere l'accesso guest ed esterno.](./office-365-security/identity-access-policies-guest-access.md)

## <a name="9-optimize-your-network-for-cloud-connectivity"></a>9: Ottimizzare la rete per la connettività cloud

Se si abilita rapidamente la maggior parte dei dipendenti a lavorare da casa, questo cambio improvviso di modelli di connettività può avere un impatto significativo sull'infrastruttura di rete aziendale. Molte reti sono state ridimensionate e progettate prima dell'adozione dei servizi cloud. In molti casi, le reti sono tolleranti per i lavoratori remoti, ma non sono state progettate per essere utilizzate in remoto da tutti gli utenti contemporaneamente.

Gli elementi di rete come i concentratori VPN, le apparecchiature di uscita della rete centrale (come proxy e dispositivi di prevenzione della perdita di dati), la larghezza di banda internet centrale, i circuiti MPLS di backhaul, la funzionalità NAT e così via vengono improvvisamente messi sotto pressione a causa del carico dell'intera azienda che li utilizza. Il risultato finale sono prestazioni e produttività scarse, insieme a un'esperienza utente scarsa per gli utenti che si adattano al lavoro da casa.

Alcune delle protezioni tradizionalmente fornite dal routing del traffico attraverso una rete aziendale sono fornite dalle app cloud a cui accedono gli utenti. Se hai raggiunto questo passaggio in questo articolo, hai implementato un set di controlli di sicurezza cloud sofisticati per i dati e i servizi di Microsoft 365. Con questi controlli in atto, potrebbe essere possibile instradare il traffico degli utenti remoti direttamente a Office 365. Se è ancora necessario un collegamento VPN per l'accesso ad altre applicazioni, è possibile migliorare notevolmente le prestazioni e l'esperienza utente implementando lo split tunneling. Una volta raggiunto un accordo nell'organizzazione, questo può essere ottenuto entro un giorno da un team di rete ben coordinato.

Per ulteriori informazioni, vedere queste risorse in Documenti:

- [Panoramica: ottimizzare la connettività per gli utenti remoti tramite split tunneling VPN](/Office365/Enterprise/office-365-vpn-split-tunnel)
- [Implementazione dello split tunneling per VPN per Office 365](/Office365/Enterprise/office-365-vpn-implement-split-tunnel)

Articoli di blog recenti su questo argomento:

- [Come ottimizzare rapidamente il traffico per il personale & ridurre il carico sull'infrastruttura](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571#)
- [Modi alternativi per i professionisti della sicurezza e l'IT per ottenere controlli di sicurezza moderni negli scenari di lavoro remoto unici di oggi](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

## <a name="10-train-users"></a>10: Formare gli utenti

Gli utenti della formazione possono risparmiare molto tempo e frustrazione agli utenti e al team delle operazioni di sicurezza. Gli utenti esperti hanno meno probabilità di aprire allegati o fare clic su collegamenti in messaggi di posta elettronica discutibili e sono più propensi a evitare siti Web sospetti.

Il manuale della campagna per la [cybersecurity](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) della scuola Kennedy di Harvard fornisce indicazioni eccellenti su come stabilire una forte cultura della consapevolezza della sicurezza all'interno dell'organizzazione, inclusa la formazione degli utenti per identificare gli attacchi di phishing.

Microsoft 365 fornisce le risorse seguenti per informare gli utenti dell'organizzazione:

****

|Concetti|Risorse|
|---|---|
|Microsoft 365|[Percorsi di apprendimento personalizzabili](/office365/customlearning/) <p>Queste risorse possono aiutare a mettere insieme la formazione per gli utenti finali nell'organizzazione|
|Sicurezza Microsoft 365|[Modulo di apprendimento: proteggere l'organizzazione con sicurezza intelligente integrata da Microsoft 365](/learn/modules/security-with-microsoft-365) <p>Questo modulo consente di descrivere il modo in cui le funzionalità di sicurezza di Microsoft 365 funzionano insieme e di illustrare i vantaggi di queste funzionalità di sicurezza.|
|Autenticazione a più fattori|[Verifica in due passaggi: qual è la pagina di verifica aggiuntiva?](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Questo articolo consente agli utenti finali di comprendere cos'è l'autenticazione a più fattori e perché viene utilizzata nell'organizzazione.|
|

Oltre a queste indicazioni, Microsoft consiglia agli utenti di eseguire le azioni descritte in questo articolo: Proteggere [l'account](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx)e i dispositivi da hacker e malware. Queste azioni includono:

- Utilizzo di password complesse
- Protezione dei dispositivi
- Abilitazione delle funzionalità di sicurezza nei PC Windows 10 e Mac (per dispositivi non gestiti)

Microsoft consiglia inoltre agli utenti di proteggere i propri account di posta elettronica personali seguendo le azioni consigliate negli articoli seguenti:

- [Proteggere l'account Outlook.com di posta elettronica](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [Proteggere l'account Gmail con la verifica in due passaggi](https://go.microsoft.com/fwlink/p/?linkid=2015688)

## <a name="11-get-started-with-microsoft-cloud-app-security"></a>11: Introduzione a Microsoft Cloud App Security

[Microsoft Cloud App Security](/cloud-app-security) offre visibilità avanzata, controllo sui viaggi dei dati e analisi sofisticate per identificare e contrastare le minacce informatiche in tutti i servizi cloud. Dopo aver iniziato a usare Cloud App Security, i criteri di rilevamento delle anomalie vengono abilitati automaticamente, ma Cloud App Security ha un periodo di apprendimento iniziale di sette giorni durante il quale non vengono generati tutti gli avvisi di rilevamento delle anomalie.

Introduzione a Cloud App Security. Successivamente è possibile configurare controlli e monitoraggio più sofisticati.

- [Guida introduttiva: Introduzione a Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security)
- [Ottenere analisi comportamentali istantanee e rilevamento di anomalie](/cloud-app-security/anomaly-detection-policy)
- [Altre informazioni su Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)
- [Esaminare nuove funzionalità e funzionalità](/cloud-app-security/release-notes)
- [Vedere le istruzioni di configurazione di base](/cloud-app-security/general-setup)

## <a name="12-monitor-for-threats-and-take-action"></a>12: Monitorare le minacce ed eseguire azioni

Microsoft 365 include diversi modi per monitorare lo stato ed eseguire le azioni appropriate. Il punto di partenza migliore è il Centro sicurezza Microsoft 365 ( ), in cui è possibile visualizzare il punteggio Microsoft Secure Score dell'organizzazione ed eventuali avvisi o entità che richiedono [https://security.microsoft.com](https://security.microsoft.com) l'attenzione [](./mtp/microsoft-secure-score.md)dell'utente.

- [Introduzione al Centro sicurezza Microsoft 365](./mtp/overview-security-center.md)
- [Monitorare e visualizzare i report](./mtp/overview-security-center.md)
- [Vedere i portali di sicurezza in Microsoft 365](./mtp/portals.md)

## <a name="next-steps"></a>Passaggi successivi

Congratulazioni. Sono state implementate rapidamente alcune delle protezioni di sicurezza più importanti e l'organizzazione è molto più sicura. Ora sei pronto per andare ancora oltre con le funzionalità di protezione dalle minacce (tra cui Microsoft Defender for Endpoint), le funzionalità di classificazione e protezione dei dati e la protezione degli account amministrativi. Per un set più approfondito e metodico di consigli sulla sicurezza per Microsoft 365, vedere [Microsoft 365 Security for Business Decision Makers (BDM)](Microsoft-365-security-for-bdm.md).

Visitare anche il nuovo centro sicurezza microsoft [su docs.microsoft.com/security](/security).