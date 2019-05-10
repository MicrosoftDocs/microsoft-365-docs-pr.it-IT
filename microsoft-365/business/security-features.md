---
title: Funzionalità di sicurezza aziendale di Microsoft 365
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Informazioni sulle funzionalità di sicurezza disponibili in Microsoft 365 business.
ms.openlocfilehash: adf1cf183022f3d2c19364b9f60868e285f78637
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660579"
---
# <a name="microsoft-365-business-security-features"></a>Funzionalità di sicurezza aziendale di Microsoft 365

Microsoft 365 business offre funzionalità di sicurezza semplificate per garantire la protezione dei dati su PC, telefoni e tablet.
    
## <a name="microsoft-365-business-admin-center-security-features"></a>Funzionalità di sicurezza dell'interfaccia di amministrazione di Microsoft 365 business

![Banner che puntano https://aka.ms/aboutM365previewa.](media/m365admincenterchanging.png)

È possibile gestire molte delle funzionalità di sicurezza aziendale di Microsoft 365 nell'interfaccia di amministrazione, che consente di abilitare o disabilitare queste funzionalità in modo semplificato. Nell'interfaccia di amministrazione è possibile eseguire le operazioni seguenti:
  
![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
- [Impostare le impostazioni di gestione applicazioni per i dispositivi Android o iOS](app-protection-settings-for-android-and-ios.md) . 
    
    Tali impostazioni includono l'eliminazione di file da un dispositivo inattivo dopo un determinato periodo di tempo, la crittografia dei file di lavoro, la necessità di impostare un PIN e così via.
    
- [Impostare le impostazioni di protezione delle applicazioni per i dispositivi Windows 10](protection-settings-for-windows-10-devices.md) . 
    
    Queste impostazioni possono essere applicate ai dati aziendali sia su dispositivi di proprietà o personali.
    
- [Impostare le impostazioni di protezione del dispositivo per i dispositivi Windows 10](protection-settings-for-windows-10-pcs.md) . 
    
    È possibile abilitare la crittografia [BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405) per proteggere i dati in caso di perdita o di furto di un dispositivo e consentire a [Windows exploit Guard](https://go.microsoft.com/fwlink/p/?linkid=871404) di fornire una protezione avanzata contro ransomware. 
    
- [Rimuovere i dati aziendali dai dispositivi](remove-company-data.md)
    
    È possibile cancellare in remoto i dati della società se un dispositivo viene perso, rubato o un dipendente lascia la propria azienda.
    
- [Ripristinare le impostazioni di fabbrica dei dispositivi Windows 10](reset-devices-to-factory-settings.md) . 
    
    È possibile reimpostare tutti i dispositivi Windows 10 a cui sono state applicate le impostazioni di protezione dei dispositivi.
    
## <a name="additional-security-features"></a>Altre funzionalità di sicurezza 

Le funzionalità avanzate di Microsoft 365 business sono disponibili per aiutare a proteggere la propria azienda dalle minacce informatiche e salvaguardare le informazioni riservate.
  
- **[Office 365 Advanced Threat Protection](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)**
    
    Advanced Threat Protection (ATP) consente di proteggere la propria azienda da attacchi di phishing e ransomware sofisticati destinati a compromettere le informazioni relative ai dipendenti o ai clienti. Le caratteristiche includono:
    
  - Scansione avanzata degli allegati e analisi di AI per rilevare e scartare messaggi pericolosi.
    
  - Controlli automatici dei collegamenti Web nel messaggio di posta elettronica per valutare se fanno parte di uno schema di phishing. In questo modo si impedisce all'utente di accedere a siti Web non sicuri.
    
- **[Panoramica dei criteri di prevenzione della perdita di dati](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)** (DLP). 
    
    È possibile configurare DLP per rilevare automaticamente le informazioni riservate, come i numeri di carta di credito, i numeri di previdenza sociale e così via, per impedire la condivisione accidentale all'esterno dell'azienda.
    
- **[Archiviazione Exchange Online](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    La licenza di archiviazione Exchange Online consente di archiviare facilmente i messaggi con il backup dei dati continua. Archivia tutti i messaggi di posta elettronica di un utente, inclusi gli elementi eliminati, nel caso in cui siano necessari in seguito per l'individuazione o il ripristino. Inoltre, è possibile utilizzare criteri di conservazione diversi per conservare i dati della posta elettronica per controversia legale, eDiscovery, o per soddisfare i requisiti di conformità.
    
- **[Azure Information Protection](https://go.microsoft.com/fwlink/p/?linkid=871406)**
    
    La protezione delle informazioni consente di controllare l'accesso alle informazioni riservate nei messaggi di posta elettronica e nei documenti con controlli quali "non inoltrare" e "non copiare". È inoltre possibile classificare le informazioni riservate come "riservate" e specificare in che modo le informazioni classificate possono essere condivise all'esterno e all'interno dell'azienda. La crittografia di livello aziendale è facile da applicare ai messaggi di posta elettronica e ai documenti per mantenere private le informazioni. Microsoft 365 business include tutte le funzionalità di [Azure Information Protection Plan 1](https://go.microsoft.com/fwlink/p/?linkid=871407). È inoltre possibile installare il componente aggiuntivo di Azure Information Protection client per le app di Office. Per ulteriori informazioni, vedere [Guida di Admininstrator del client di Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide).
    
- **[Le funzionalità complete di Intune nel portale di Azure](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    L'accesso all'interfaccia di amministrazione di Intune nel portale di Azure consente di configurare altre funzionalità di sicurezza, ad esempio la gestione dei dispositivi MacOS, iPhone e Android insieme a Advanced Device Management per Windows, che non sono disponibili tramite Microsoft 365 Business Admin Center.
    
Nelle sezioni successive viene descritto come è possibile gestire queste funzionalità nel centro &amp; conformità sicurezza e nell'interfaccia di amministrazione di Intune. Nel corso del tempo, i controlli semplificati verranno aggiunti all'interfaccia di amministrazione di Microsoft 365 business.
  
    
## <a name="faq"></a>Domande frequenti

 ### <a name="are-these-security-features-available-in-all-markets"></a>Queste funzionalità di sicurezza sono disponibili in tutti i mercati?
  
Sì, queste funzionalità sono disponibili in tutti i mercati in cui è venduto Microsoft 365 business.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>Come trovare il Centro sicurezza &amp; e conformità
  
1. [Accedere a Microsoft 365 business](https://portal.microsoft.com/) utilizzando le credenziali di amministratore. 
    
2. Nel NAV sinistro, individuare i **centri di amministrazione** ed espanderlo. 
    
    ![Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft 365, scegliere interfaccia di amministrazione.](media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Scegliere **conformità &amp; di sicurezza** per accedere al &amp; Centro sicurezza e conformità.