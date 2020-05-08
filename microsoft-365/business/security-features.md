---
title: Funzionalità di sicurezza e conformità di Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
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
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Informazioni sulle funzionalità di sicurezza disponibili in Microsoft 365 Business Premium per garantire la protezione dei dati su PC, telefoni e tablet.
ms.openlocfilehash: f6aef84afc76217161dee6b68d626128e0cc15b2
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165758"
---
# <a name="microsoft-365-business-premium-security-and-compliance-features"></a>Funzionalità di sicurezza e conformità di Microsoft 365 Business Premium

Microsoft 365 Business Premium offre funzionalità di sicurezza semplificate per garantire la protezione dei dati su PC, telefoni e tablet.
    
## <a name="microsoft-365-admin-center-security-features"></a>Funzionalità di sicurezza di Microsoft 365 Admin Center

[![Etichetta per comunicare all'utente che l'interfaccia di amministrazione sta cambiando ed è possibile trovare altre informazioni alla pagina aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

È possibile gestire molte delle funzionalità di sicurezza di Microsoft 365 Business Premium nell'interfaccia di amministrazione, che consente di abilitare o disabilitare queste funzionalità in modo semplificato. Nell'interfaccia di amministrazione, è possibile eseguire le operazioni seguenti:
  
- [Impostare le impostazioni di gestione applicazioni per i dispositivi Android o iOS](app-protection-settings-for-android-and-ios.md) . 
    
    Tali impostazioni includono l'eliminazione di file da un dispositivo inattivo dopo un determinato periodo di tempo, la crittografia dei file di lavoro, la necessità di impostare un PIN e così via.
    
- [Impostare le impostazioni di protezione delle applicazioni per i dispositivi Windows 10](protection-settings-for-windows-10-devices.md) . 
    
    Queste impostazioni possono essere applicate ai dati aziendali sia nei dispositivi di proprietà della società che di proprietà personale.
    
- [Impostare le impostazioni di protezione del dispositivo per i dispositivi Windows 10](protection-settings-for-windows-10-pcs.md) . 
    
    È possibile abilitare la crittografia [BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405) per proteggere i dati in caso di perdita o di furto di un dispositivo e consentire a [Windows exploit Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-exploit-protection) di fornire una protezione avanzata contro ransomware. 
    
- [Rimuovere i dati aziendali dai dispositivi](remove-company-data.md)
    
    È possibile cancellare in remoto i dati della società se un dispositivo viene perso, rubato o un dipendente lascia la propria azienda.
    
- [Ripristinare le impostazioni di fabbrica dei dispositivi Windows 10](reset-devices-to-factory-settings.md) . 
    
    È possibile reimpostare tutti i dispositivi Windows 10 a cui sono state applicate le impostazioni di protezione dei dispositivi.
    
## <a name="additional-security-features"></a>Altre funzionalità di sicurezza 

Le funzionalità avanzate di Microsoft 365 Business Premium sono disponibili per aiutare a proteggere la propria azienda dalle minacce informatiche e a salvaguardare le informazioni riservate.
  
- **[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)**
    
    Advanced Threat Protection (ATP) consente di proteggere la propria azienda da attacchi di phishing e ransomware sofisticati destinati a compromettere le informazioni relative ai dipendenti o ai clienti. Le caratteristiche includono:
    
  - Scansione avanzata degli allegati e analisi di AI per rilevare e scartare messaggi pericolosi.
    
  - Controlli automatici dei collegamenti nel messaggio di posta elettronica per valutare se fanno parte di uno schema di phishing. In questo modo si impedisce all'utente di accedere a siti Web non sicuri.

- **[Le funzionalità complete di Intune nel portale di Azure](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    L'accesso all'interfaccia di amministrazione di Intune nel portale di Azure consente di configurare altre funzionalità di sicurezza, ad esempio la gestione dei dispositivi MacOS, iPhone e Android, insieme a Advanced Device Management per Windows, che non sono disponibili tramite l'interfaccia di amministrazione di Microsoft 365.
- **Stesso [accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) di Azure ad Premium P1 Plan**


    L'accesso condizionale può aiutare a proteggere l'organizzazione dal rischio di accesso, a tentativi di accessi da una rete o a impostazioni locali imprevisti, a tentativi di accesso da tipi di dispositivo rischiosi e così via. I criteri di accesso condizionale vengono applicati dopo che la prima autenticazione è stata completata e utilizza i segnali del primo evento di autenticazione per determinare se l'accesso al tentativo deve essere approvato, negato o se è necessario un numero maggiore di prove, ad esempio una seconda forma di identificazione.

    Le funzionalità di accesso condizionale incluse sono:

    - Accesso basato su nome utente, gruppo e ruolo
    - Accesso [basato su un'app](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access) 
    - [Accesso basato sul percorso](https://docs.microsoft.com/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration);  Consenti l'accesso solo da intervalli IP attendibili o da paesi specifici 
    - Richiedi accesso a Mae
    - Blocca l'accesso alle app che utilizzano [l'autenticazione legacy](https://docs.microsoft.com/azure/active-directory/conditional-access/block-legacy-authentication)
    - Richiedi Apps TP utilizza la [protezione delle app di Intune](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)
    - Autenticazione personalizzata come l'AMF con provider di terze parti, ad esempio DUO.
   
    Altre caratteristiche:
    - [Reimpostazione della password self-service](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-customization) per l'ambiente ibrido di Azure ad
    
## <a name="compliance-features"></a>Funzionalità di conformità

La sottoscrizione Microsoft 365 Business Premium include funzionalità che consentono di mantenere la conformità e gli standard normativi.

- **[Panoramica dei criteri di prevenzione della perdita di dati](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)** (DLP). 
    
    È possibile configurare DLP per rilevare automaticamente le informazioni riservate, come i numeri di carta di credito, i numeri di previdenza sociale e così via, per impedire la condivisione involontaria all'esterno dell'azienda.
    
- **[Archiviazione Exchange Online](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    La licenza di archiviazione Exchange Online consente di archiviare facilmente i messaggi con il backup dei dati continua. Archivia tutti i messaggi di posta elettronica di un utente, inclusi gli elementi eliminati, nel caso in cui siano necessari in seguito per l'individuazione o il ripristino. Inoltre, è possibile utilizzare criteri di conservazione diversi per conservare i dati della posta elettronica per controversia legale, eDiscovery, o per soddisfare i requisiti di conformità.
    
- **[Etichette di riservatezza](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)**

   Microsoft 365 Business Premium include tutte le funzionalità di [Azure Information Protection Plan 1](https://go.microsoft.com/fwlink/p/?linkid=871407). Con questo piano, è possibile creare **etichette di riservatezza** che consentono di controllare l'accesso alle informazioni riservate in messaggi di posta elettronica e documenti, con controlli quali "non inoltrare" e "non copiare". È inoltre possibile classificare le informazioni riservate come "riservate" e specificare in che modo le informazioni classificate possono essere condivise all'esterno e all'interno dell'azienda. La crittografia di livello aziendale è facile da applicare ai messaggi di posta elettronica e ai documenti per mantenere private le informazioni. È inoltre possibile installare il componente aggiuntivo di Azure Information Protection client per le app di Office. Per ulteriori informazioni, vedere [Azure Information Protection Unified Labeling client](https://docs.microsoft.com/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history). Per le etichette di riservatezza, installare il **AzInfoProtection_UL. exe**.

È possibile gestire queste funzionalità nel centro conformità &amp; sicurezza e nell'interfaccia di amministrazione di Intune. Nel corso del tempo, i controlli semplificati verranno aggiunti all'interfaccia di amministrazione di Microsoft 365.
  
    
## <a name="faq"></a>Domande frequenti

 ### <a name="are-these-security-features-available-in-all-markets"></a>Queste funzionalità di sicurezza sono disponibili in tutti i mercati?
  
Sì, queste funzionalità sono disponibili in tutti i mercati in cui è venduto Microsoft 365 Business Premium.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>Come trovare il Centro sicurezza &amp; e conformità
  
1. [Accedere a Microsoft 365 Business Premium](https://portal.microsoft.com/) utilizzando le credenziali di amministratore. 
    
2. Nel NAV sinistro, individuare i **centri di amministrazione** ed espanderlo. 
    
    ![Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft 365, scegliere interfaccia di amministrazione.](../media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Scegliere **conformità &amp; di sicurezza** per accedere al &amp; Centro sicurezza e conformità.
