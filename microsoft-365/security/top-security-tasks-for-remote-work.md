---
title: Top 12 attività per i team di sicurezza per il supporto di lavoro da casa
f1.keywords:
- CSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.service: o365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: 'Proteggere la posta elettronica e i dati aziendali da minacce informatiche, tra cui ransomware, phishing e allegati dannosi. '
ms.openlocfilehash: b675f8abc5487dcb08324795fb1d6cc3b91592a1
ms.sourcegitcommit: 71612ef8f2f93063c2a070e8a079506362f54c58
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2020
ms.locfileid: "43037477"
---
# <a name="top-12-tasks-for-security-teams-to-support-working-from-home"></a>Top 12 attività per i team di sicurezza per il supporto di lavoro da casa

Se si è come [Microsoft](https://www.microsoft.com/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/) e improvvisamente si trova a supportare una forza lavoro principalmente basata sulla casa, si vuole garantire che l'organizzazione funzioni nel modo più sicuro possibile. In questo articolo viene attribuita la priorità alle attività che consentono ai team di sicurezza di implementare le funzionalità di sicurezza più importanti il più velocemente possibile. 

Se si è un'organizzazione di piccole o medie dimensioni che utilizza uno dei piani aziendali di Microsoft, vedere le risorse seguenti:
- [I 10 principali modi per proteggere i piani di Office 365 e Microsoft 365 Business](../admin/security-and-compliance/secure-your-business-data.md) 
- [Microsoft 365 per le campagne](https://docs.microsoft.com/microsoft-365/campaigns/?view=o365-worldwide) (include una configurazione di sicurezza consigliata per Microsoft 365 business)

  
Per i clienti che utilizzano i piani aziendali, Microsoft consiglia di completare le attività elencate nella tabella seguente che si applicano al piano di servizio. Se, invece di acquistare un piano Microsoft 365 Enterprise, si uniscono gli abbonamenti, tenere presente quanto segue:
- Microsoft 365 E3 include Enterprise Mobility + Security (EMS) E3 e Azure AD P1
- Microsoft 365 E5 include EMS E5 e Azure AD P2
  
||**Attività**| Tutti i piani di Office 365 Enterprise|**Microsoft 365 E3** |**Microsoft 365 E5**|
|:-----|:-----|:-----|:-----|:-----|
|1       |[Abilitare l'autenticazione a più fattori di Azure (AMF)](#1-enable-azure-multi-factor-authentication-mfa)   |   ![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)  |![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)   | ![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|2      | [Protezione dalle minacce in Office 365](#2-protect-against-threats-in-office-365) |![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png) |  ![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)       | ![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)       | 
|3       |  [Configurare Office 365 Advanced Threat Protection](#3-configure-office-365-advanced-threat-protection)  |   |      |  ![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)     | 
|4       | [Configurazione di Azure Advanced Threat Protection (ATP)](#4-configure-azure-advanced-threat-protection)   |   |      |  ![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)     | 
|5      |   [Abilitare Microsoft Advanced Threat Protection](#5-turn-on-microsoft-advanced-threat-protection)  |  |      | ![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|6       | [Configurare la protezione delle app per dispositivi mobili di Intune per telefoni e Tablet](#6-configure-intune-mobile-app-protection-for-phones-and-tablets) |    |  ![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)       |  ![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)       | 
|7      | [Configurare il master e l'accesso condizionale per gli utenti, inclusa la protezione delle app di Intune](#7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection)  |    |  ![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)     | ![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|8       |  [Registrare i PC nella gestione dei dispositivi e richiedere PC conformi](#8-enroll-pcs-into-device-management-and-require-compliant-pcs)   |  | ![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)        | ![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)        | 
|9       | [Ottimizzare la rete per la connettività cloud](#9-optimize-your-network-for-cloud-connectivity)  |  ![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png) |![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)      |![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)        | 
|10    | [Formazione degli utenti](#10-train-users) |    ![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png) |![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)      |![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|11  |[Introduzione a Microsoft cloud app Security](#11-get-started-with-microsoft-cloud-app-security) |![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)   |![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)   |![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)   |
|12  |[Monitorare le minacce e agire](#12-monitor-for-threats-and-take-action) |![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)   |![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)  |![Incluso](../media/d238e041-6854-4a78-9141-049224df0795.png)  |
| | | |


   
Prima di iniziare, controllare il [Punteggio microsoft 365 Secure](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) nel centro sicurezza di Microsoft 365. Da un Dashboard centralizzato, è possibile monitorare e migliorare la sicurezza per le identità, i dati, le app, i dispositivi e l'infrastruttura di Microsoft 365. Si ricevono punti per la configurazione delle funzionalità di sicurezza consigliate, per l'esecuzione di attività correlate alla sicurezza (come la visualizzazione dei report) o per l'indirizzamento di suggerimenti con un'applicazione o un software di terze parti. Le attività consigliate in questo articolo aumenteranno la partitura.
  
![Schermata di Microsoft Secure Score](../media/secure-score.png)
  
## <a name="1-enable-azure-multi-factor-authentication-mfa"></a>1: abilitare l'autenticazione a più fattori di Azure (AMF)
La cosa migliore che è possibile fare per migliorare la sicurezza per i dipendenti che lavorano da casa è l'attivazione dell'AMF. Se non si dispone già di processi, trattarlo come un pilota di emergenza e assicurarsi di disporre di personale di supporto pronto per aiutare i dipendenti che si bloccano. Poiché probabilmente non è possibile distribuire dispositivi di sicurezza hardware, utilizzare la biometria di Windows Hello e le app di autenticazione dello smartphone come Microsoft Authenticator.

In genere, Microsoft consiglia di concedere agli utenti 14 giorni per registrare il proprio dispositivo per l'autenticazione a più fattori prima di richiedere l'AMF. Tuttavia, se il personale lavora improvvisamente da casa, andare avanti e richiedere l'AMF come priorità per la sicurezza e prepararsi per aiutare gli utenti che ne hanno bisogno. 

L'applicazione di questi criteri richiederà solo pochi minuti, ma sarà pronta a supportare gli utenti nei diversi giorni successivi.  


|Piano  |Consiglio  |
|---------|---------|
|Piani di Office 365 (senza Azure AD P1 o P2)     |[Abilitare le impostazioni predefinite per la sicurezza in Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Le impostazioni predefinite per la sicurezza di Azure AD includono l'AMF per gli utenti e gli amministratori.   |
|Microsoft 365 E3 (con Azure AD P1)     | Utilizzare [criteri di accesso condizionale comuni](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) per configurare i criteri seguenti: <br>- [Richiedere l'autenticazione a master per gli amministratori](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [Richiedi l'AMF per tutti gli utenti](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Blocca l'autenticazione legacy](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (con Azure AD P2)     | Approfittando di Azure AD Identity Protection, iniziare a implementare il [set consigliato di Microsoft per l'accesso condizionale e i criteri correlati](../enterprise/identity-access-policies.md) creando questi due criteri:<br> - [Richiedere l'AMF quando il rischio di accesso è medio o elevato](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Bloccare i client che non supportano l'autenticazione moderna](../enterprise/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)<br>- [Gli utenti ad alto rischio devono modificare la password](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |


  
## <a name="2-protect-against-threats-in-office-365"></a>2: protezione dalle minacce in Office 365

Tutti i piani di Office 365 includono una vasta gamma di funzionalità di protezione dalle minacce. La protezione per queste funzionalità richiede solo alcuni minuti.
- Protezione anti-malware
- Protezione da file e URL dannosi
- Protezione anti-phishing
- Protezione dalla posta indesiderata

Vedere [Protect Against Threats in Office 365](office-365-security/protect-against-threats.md) per indicazioni che è possibile utilizzare come punto di partenza.
    

## <a name="3-configure-office-365-advanced-threat-protection"></a>3: configurare Office 365 Advanced Threat Protection

Office 365 Advanced Threat Protection (ATP), incluso in Microsoft 365 E5 e Office 365 E5, salvaguarda la propria organizzazione dalle minacce dannose poste da messaggi di posta elettronica, collegamenti (URL) e strumenti di collaborazione. Questo può richiedere diverse ore per la configurazione.

Office 365 ATP:
- Protegge la propria organizzazione dalle minacce di posta elettronica sconosciute in tempo reale utilizzando sistemi intelligenti che controllano gli allegati e i collegamenti per contenuti dannosi. Questi sistemi automatizzati includono una robusta piattaforma di detonazione, euristica e modelli di apprendimento automatico. 
- Protegge l'organizzazione quando gli utenti collaborano e condividono file, identificando e bloccando i file dannosi nei siti e nelle raccolte documenti del team. 
- Applica i modelli di apprendimento automatico e gli algoritmi avanzati di rilevamento della rappresentazione per evitare attacchi di phishing. 

Per una panoramica, tra cui un riepilogo dei piani, vedere [Office 365 Advanced Threat Protection](office-365-security/office-365-atp.md).

L'amministratore globale può configurare queste protezioni:
- [Configurare i collegamenti sicuri di ATP](office-365-security/set-up-atp-safe-links-policies.md)
- [Configurare i criteri degli allegati sicuri di ATP](office-365-security/set-up-atp-safe-attachments-policies.md)
- [Configurare un elenco personalizzato di URL da "non riscrivere"](office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
- [Configurare un elenco personalizzato di URL bloccati](office-365-security/set-up-a-custom-blocked-urls-list-wtih-atp.md)

È necessario collaborare con l'amministratore di Exchange Online e l'amministratore di SharePoint Online per configurare ATP per i carichi di lavoro seguenti:
- [Attivare ATP per SharePoint, OneDrive e Microsoft Teams](office-365-security/turn-on-atp-for-spo-odb-and-teams.md)

## <a name="4-configure-azure-advanced-threat-protection"></a>4: configurare Azure Advanced Threat Protection

[Azure Advanced Threat Protection](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) (Azure ATP) è una soluzione di sicurezza basata sul cloud che sfrutta i segnali di Active Directory locali per identificare, rilevare ed esaminare le minacce avanzate, le identità compromesse e le azioni Insider dannose indirizzate alla propria organizzazione. Si concentrerà su questo punto perché protegge l'infrastruttura di on-premi e la cloud, non ha dipendenze o prerequisiti e può fornire vantaggi immediati.


- Per ottenere rapidamente l'installazione, vedere [Guide rapide di Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) 
- [Video: Introduzione a Azure ATP](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- Esaminare le [tre fasi della distribuzione di Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="5-turn-on-microsoft-advanced-threat-protection"></a>5: attiva Microsoft Advanced Threat Protection

Dopo aver configurato Office 365 ATP e Azure ATP, è possibile visualizzare i segnali combinati da queste funzionalità in un solo dashboard. [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) (MTP) riunisce avvisi, incidenti, indagini e risposte automatiche e una ricerca avanzata tra i carichi di lavoro (Azure ATP, Office 365 ATP, Microsoft Defender ATP e Microsoft cloud app Security) in un unico riquadro di [Security.Microsoft.com](https://security.microsoft.com). 
<br>

![Illustrazione del dashboard MTP](../media/top-ten-security-remote-work-mtp-dashboard.png)
<br><br>
Dopo aver configurato uno o più servizi di protezione dalle minacce avanzate, abilitare MTP. Le nuove funzionalità vengono aggiunte continuamente a MTP; prendere in considerazione la possibilità di ricevere funzionalità di anteprima.

- [Altre informazioni su MTP](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide)
- [Attiva MTP](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide)
- [Opt-in per le funzionalità di anteprima](https://docs.microsoft.com/microsoft-365/security/mtp/preview?view=o365-worldwide)


## <a name="6-configure-intune-mobile-app-protection-for-phones-and-tablets"></a>6: configurare la protezione delle app per dispositivi mobili di Intune per telefoni e Tablet

Microsoft Intune Mobile Application Management (MAM) consente di gestire e proteggere i dati dell'organizzazione su telefoni e tablet senza gestire questi dispositivi. Tenere presente quanto segue:
- È possibile creare un criterio di protezione delle app che determina quali app in un dispositivo vengono gestite e quali comportamenti sono consentiti, ad esempio impedendo la copia dei dati di un'app gestita in un'app non gestita. È possibile creare un criterio per ogni platorm (iOS, Android).
- Dopo aver creato i criteri di protezione delle app, è necessario applicarli creando una regola di accesso condizionale in Azure AD per richiedere applicazioni approvate e protezione dei dati delle APP.

I criteri di protezione delle APP includono molte impostazioni. Fortunatamente, non è necessario conoscere tutte le impostazioni e valutare le opzioni. Microsoft rende più facile applicare una configurazione delle impostazioni suggerendo punti di partenza. Il [Framework di protezione dei dati utilizzando i criteri di protezione delle app](https://docs.microsoft.com/mem/intune/apps/app-protection-framework) include tre livelli tra cui è possibile scegliere. 

Inoltre, Microsoft coordina questo framework di protezione delle app con una serie di criteri di accesso condizionale e correlati che è consigliabile utilizzare come punto di partenza per tutte le organizzazioni. Se è stata implementata la modalità di utilizzo di Mae utilizzando le indicazioni contenute in questo articolo, si è a metà strada.

Per configurare la protezione delle app per dispositivi mobili, utilizzare le linee guida nei [criteri di identità e accesso ai dispositivi comuni](../enterprise/identity-access-policies.md):
 1. Utilizzare le istruzioni [Applica criteri di protezione dei dati di applicazione](../enterprise/identity-access-policies.md#apply-app-data-protection-policies) per creare criteri per iOS e Android. Il livello 2 (protezione avanzata dei dati) è consigliato per la protezione della linea di base. 
 2. Creare una regola di accesso condizionale per [richiedere applicazioni approvate e protezione delle app](../enterprise/identity-access-policies.md#require-approved-apps-and-app-protection). 

## <a name="7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection"></a>7: configurare l'autenticazione e l'accesso condizionale per gli utenti, tra cui Intune mobile app Protection

Successivamente, è possibile continuare a collaborare e lavorare con gli ospiti. Se si usa il piano Microsoft 365 E3 e si è implementato l'AMF per tutti gli utenti, è necessario essere impostati. 

Se si utilizza il piano Microsoft 365 E5 e si sfrutta la protezione delle identità di Azure per l'autenticazione basata sui rischi, è necessario eseguire un paio di rettifiche (poiché Azure AD Identity Protection non si estende agli ospiti):
- Creare una nuova regola di accesso condizionale per richiedere l'autenticazione Master sempre per gli utenti esterni e i clienti.
- Aggiornare la regola di accesso condizionale dell'AMF basata sui rischi per escludere ospiti e utenti esterni.

Utilizzare le linee guida per l' [aggiornamento dei criteri comuni per consentire e proteggere gli ospiti e l'accesso esterno](../enterprise/identity-access-policies-guest-access.md) per comprendere in che modo l'accesso Guest è compatibile con Azure ad e per aggiornare i criteri coinvolti. 

I criteri di protezione delle app per dispositivi mobili di Intune creati insieme alla regola di accesso condizionale per richiedere app e protezione delle applicazioni approvate, si applicano agli account Guest e aiutano a proteggere i dati dell'organizzazione. 

**Nota**: se i PC sono già stati registrati nella gestione dei dispositivi per richiedere PC conformi, è necessario escludere anche gli account Guest dalla regola di accesso condizionale che impone la conformità del dispositivo. 


## <a name="8-enroll-pcs-into-device-management-and-require-compliant-pcs"></a>8: registrare i PC nella gestione dei dispositivi e richiedere PC conformi

Esistono diversi metodi per registrare i dispositivi della forza lavoro. Ogni metodo dipende dalla proprietà del dispositivo (personale o aziendale), dal tipo di dispositivo (iOS, Windows, Android) e dai requisiti di gestione (Reimposta, affinità, blocco). Questo può richiedere un po' di tempo per l'ordinamento. Vedere: [registrare i dispositivi in Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/). 

Il modo più rapido per andare avanti consiste nel [configurare la registrazione automatica per i dispositivi Windows 10](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment). 

È inoltre possibile avvalersi di queste esercitazioni:
- [Utilizzare il pilota automatico per registrare i dispositivi Windows in Intune](https://docs.microsoft.com/mem/intune/enrollment/tutorial-use-autopilot-enroll-devices)
- [Utilizzare le funzionalità di registrazione del dispositivo Corporate di Apple in Apple Business Manager (ABM) per registrare i dispositivi iOS/iPados in Intune](https://docs.microsoft.com/mem/intune/enrollment/tutorial-use-device-enrollment-program-enroll-ios)

Dopo aver eseguito la registrazione dei dispositivi, utilizzare le linee guida nei [criteri di identità e accesso](../enterprise/identity-access-policies.md) ai dispositivi comuni per creare questi criteri:
- [Definire i criteri di conformità del dispositivo](../enterprise/identity-access-policies.md#define-device-compliance-policies)
- [Richiedi PC conformi](../enterprise/identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets) (regola di accesso condizionale)

Solo un'organizzazione può gestire un dispositivo, quindi assicuratevi di escludere gli account Guest dalla regola di accesso condizionale di Azure AD. Se non si escludono gli utenti guest e esterni dai criteri che richiedono la conformità del dispositivo, questi criteri bloccano tali utenti. Per ulteriori informazioni, vedere [updating the Common Policies to allow and Protect Guest and External Access](../enterprise/identity-access-policies-guest-access.md).

## <a name="9-optimize-your-network-for-cloud-connectivity"></a>9: ottimizzare la rete per la connettività cloud

Se si sta rapidamente consentendo la maggior parte dei dipendenti di lavorare da casa, questo improvviso passaggio di modelli di connettività può avere un impatto significativo sull'infrastruttura di rete aziendale. Molte reti sono state ridimensionate e progettate prima che i servizi cloud siano stati adottati. In molti casi, le reti sono tolleranti per i lavoratori remoti, ma non sono state progettate per essere utilizzate in remoto da tutti gli utenti contemporaneamente.

Gli elementi di rete, ad esempio i concentratori VPN, le apparecchiature di rete centrale di uscita (come i proxy e i dispositivi di prevenzione della perdita di dati), la larghezza di banda Internet centrale, i circuiti MPLS di backhaul, la capacità NAT e così via, vengono improvvisamente sottoposti a enormi tensioni grazie al carico l'intera azienda che li utilizza. Il risultato finale è una scarsità di prestazioni e produttività accoppiata a un'esperienza utente scadente per gli utenti che si adattano a lavorare da casa.

Alcune delle protezioni che sono state tradizionalmente fornite dal routing del traffico tramite una rete aziendale sono fornite dalle app cloud che gli utenti accedono. Se si è raggiunto questo passaggio in questo articolo, è stata implementata una serie di sofisticati controlli di sicurezza cloud per i servizi e i dati di Microsoft 365. Con questi controlli sul posto, potrebbe essere pronto a instradare il traffico degli utenti remoti direttamente a Office 365. Se è ancora necessario un collegamento VPN per l'accesso ad altre applicazioni, è possibile migliorare notevolmente le prestazioni e l'esperienza utente implementando il tunneling suddiviso. Una volta raggiunto un accordo in Oganization, è possibile eseguire questa operazione in un giorno da un team di rete ben coordinato.


Per ulteriori informazioni, vedere queste risorse su documenti:
- [Panoramica: ottimizzare la connettività di Office 365 per gli utenti remoti tramite il tunneling Split VPN](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
- [Implementazione del tunneling suddiviso VPN per Office 365](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-implement-split-tunnel)

Articoli di Blog recenti su questo argomento:
- [Come ottimizzare rapidamente il traffico di Office 365 per i dipendenti remoti & ridurre il carico nell'infrastruttura](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571#)
- [Modalità alternative per i professionisti della sicurezza e per ottenere moderni controlli di sicurezza negli scenari di lavoro remoto unici di oggi](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)


## <a name="10-train-users"></a>10: addestra gli utenti

Quando gli utenti non conoscono le funzionalità di protezione dalle minacce sul posto di lavoro nell'organizzazione, possono essere frustrate dalle funzionalità di protezione percepite come rallentamento o impedendo loro di svolgere il proprio lavoro. Inoltre, se sanno in anticipo cosa guardare per quanto riguarda i messaggi di posta elettronica sospetti o gli URL, è molto meno probabile che aprano artefatti discutibili. Formazione gli utenti possono salvare gli utenti e le operazioni di sicurezza del team un sacco di tempo e frustrazione.

Il [manuale della campagna](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) di Harvard Kennedy School Cybersecurity fornisce indicazioni eccellenti sulla creazione di una forte cultura della consapevolezza della sicurezza all'interno dell'organizzazione, tra cui la formazione degli utenti per identificare gli attacchi di phishing. 

Microsoft 365 fornisce le risorse seguenti per informare gli utenti nell'organizzazione:

|Concetto  |Risorse  |
|---------|---------|
|Microsoft 365     |[Percorsi di apprendimento personalizzabili](https://docs.microsoft.com/office365/customlearning/) <p>Tali risorse consentono di creare una formazione per gli utenti finali nell'organizzazione        |
|Centro sicurezza Microsoft 365 |[Modulo di apprendimento: proteggere l'organizzazione con sicurezza integrata e intelligente da Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>Questo modulo consente di descrivere in che modo le funzionalità di sicurezza di Microsoft 365 interagiscono e di articolare i vantaggi di queste funzionalità di sicurezza. |
|Autenticazione a più fattori     | [Verifica in due passaggi: che cos'è la pagina di verifica aggiuntiva?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Questo articolo aiuta gli utenti finali a capire cosa sia l'autenticazione a più fattori e il motivo per cui viene utilizzato all'interno dell'organizzazione.    |
| | |

Oltre a queste linee guida, Microsoft consiglia agli utenti di eseguire le azioni descritte in questo articolo: [proteggere l'account e i dispositivi da hacker e malware](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx). Queste azioni includono:
  
- Utilizzo di password complesse
    
- Protezione di dispositivi 
    
- Abilitazione delle funzionalità di sicurezza nei PC Windows 10 e Mac (per i dispositivi non gestiti)
    
Microsoft consiglia inoltre agli utenti di proteggere gli account di posta elettronica personali adottando le azioni consigliate negli articoli seguenti:
  
- [Proteggi il tuo account di posta elettronica di Outlook.com](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba.aspx)
    
- [Proteggi l'account di Gmail con la verifica in due passaggi](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)


## <a name="11-get-started-with-microsoft-cloud-app-security"></a>11: Introduzione a Microsoft cloud app Security

[Microsoft cloud app Security](https://docs.microsoft.com/cloud-app-security) offre una vasta visibilità, il controllo dei dati di viaggio e analisi sofisticate per identificare e combattere Cyberthreats in tutti i servizi cloud. Dopo aver avviato la sicurezza delle app Cloud, i criteri di rilevamento delle anomalie sono automaticamente abilitati, ma cloud app Security ha un periodo di apprendimento iniziale di sette giorni durante il quale non vengono generati tutti gli avvisi di rilevamento delle anomalie.

Iniziare a usare cloud app Security adesso. Successivamente, è possibile configurare monitor e controlli più sofisticati.

- [Guida introduttiva: iniziare a utilizzare cloud app Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)
- [Ottenere analisi comportamentale istantanea e rilevamento di anomalie](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy)
- [Altre informazioni su Microsoft cloud app Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Esaminare nuove caratteristiche e funzionalità](https://docs.microsoft.com/cloud-app-security/release-notes)
- [Vedere le istruzioni di base per l'installazione](https://docs.microsoft.com/cloud-app-security/general-setup)

## <a name="12-monitor-for-threats-and-take-action"></a>12: monitorare le minacce e intervenire

Microsoft 365 include diversi modi per monitorare lo stato e intraprendere le azioni appropriate. Il punto di partenza migliore è Microsoft 365 Security Center ([https://security.microsoft.com](https://security.microsoft.com)), in cui è possibile visualizzare il [Punteggio di Microsoft Secure](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score?view=o365-worldwide)dell'organizzazione e gli eventuali avvisi o entità che richiedono la propria attenzione.

- [Introduzione al centro sicurezza di Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center?view=o365-worldwide)
- [Monitorare e visualizzare i report](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting?view=o365-worldwide)
- [Vedere i portali di sicurezza in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/portals)

## <a name="next-steps"></a>Passaggi successivi

Congratulazioni! Sono state implementate rapidamente alcune delle protezioni di sicurezza più importanti e la vostra organizzazione è molto più sicura. A questo punto si è pronti per andare anche oltre con le funzionalità di protezione dalle minacce (tra cui Microsoft Defender Advanced Threat Protection), le funzionalità di classificazione e protezione dei dati e la protezione degli account amministrativi. Per un insieme più approfondito e metodico di suggerimenti per la sicurezza per Microsoft 365, vedere [microsoft 365 Security for Business Decision Makers (BDMs)](Microsoft-365-security-for-bdm.md). 

Visitare anche il nuovo Centro sicurezza di Microsoft su [docs.Microsoft.com/Security](https://docs.microsoft.com/security). 