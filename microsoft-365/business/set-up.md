---
title: Configurare Microsoft 365 Business tramite la configurazione guidata
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Informazioni su come configurare Microsoft 365 Business completando i quattro passaggi.
ms.openlocfilehash: f57239b884bd2e186c0bc01973130a10fa4cfe84
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868285"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a>Configurare Microsoft 365 Business tramite la configurazione guidata

Completare i passaggi da 1 a 4 riportata di seguito.
  
### <a name="set-up-microsoft-365-business"></a>Configurare Microsoft 365 Business

Guardare un video viene illustrato come configurare Microsoft 365 Business quando non si dispone di un server di Active Directory locale:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
I passaggi di configurazione includono informazioni personali per le installazioni che includono Active Directory locale. Se si desidera continuare ad accedere ai dispositivi di dominio, leggere gli articoli seguenti per due diverse modalità dell'attivazione che e prima di eseguire l'installazione guidata, completare i passaggi:
  
- [Consentire ai dispositivi Windows 10 aggiunto al dominio da gestire da Microsoft 365 Business](manage-windows-devices.md)
    
    -Si tratta del metodo consigliato.
    
- [Accesso locale risorse da un dispositivo Azure Active Directory aggiunti in Microsoft 365 Business](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a>Passaggio 1: Personalizzare accesso

1. Accedere a [Microsoft 365 Business](https://portal.microsoft.com) usando le credenziali di amministratore globale. Selezionare il riquadro **Amministratore** per passare all'interfaccia di amministrazione. 
    
2. Nell'interfaccia di amministrazione scegliere **Avvia configurazione** (a seconda dello stato potrebbe invece essere visualizzato **Continua configurazione**) per avviare la procedura guidata. 
    
3. Immettere il nome del dominio che si vuole usare, ad esempio contoso.com.
    
    Proseguire e immettere il dominio, anche se è stato verificato durante l'utilizzo di Azure Active Directory Connect, ad esempio. I due passaggi seguenti non si applicano all'utente se è stato utilizzato Connetti Azure Active Directory per verificare il proprio dominio.
    
4. Seguire le istruzioni della procedura guidata per [creare record DNS presso un provider di hosting DNS per Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) che consente di verificare che si è proprietari del dominio. 
    
    È possibile visualizzare un video di esempio di [Video: installazione di Office 365 nuova interfaccia di amministrazione di](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Si noti che in questo video non sono incluse le operazioni di protezione dei dati di Microsoft 365 Business.
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a>Passaggio 2: Aggiungere utenti e assegnare licenze

1. È possibile aggiungere utenti qui oppure [aggiungere gli utenti in un secondo momento](add-users-m365b.md) nell'interfaccia di amministrazione. 
    
    A qualsiasi utente aggiunto viene automaticamente assegnata una licenza di Microsoft 365 Business.
    
2. Se l'abbonamento a Microsoft 365 Business include già degli utenti (ad esempio se si è usato Azure AD Connect), sarà disponibile un'opzione per l'assegnazione di licenze a questi utenti. Procedere con l'aggiunta di licenze anche per questi utenti.
    
3. Sarà disponibile anche un'opzione per la condivisione delle credenziali con i nuovi utenti aggiunti. È possibile scegliere se stamparle, inviarle tramite posta elettronica o scaricarle.
    
4. Ignorare il passaggio relativo alla migrazione dei messaggi di posta elettronica e scegliere **Avanti** nella pagina **Esegui la migrazione dei messaggi di posta elettronica**. 
    
    Se si passa da un altro provider di posta elettronica e si desidera copiare i dati in seguito, è possibile [eseguire la migrazione di posta elettronica e i contatti a Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a>Passaggio 3: Connettere il dominio

> [!NOTE]
> Se si sceglie di utilizzare il dominio .onmicrosoft o utilizzato Connetti Azure Active Directory, questo passaggio non verrà visualizzato. 
  
Per configurare i servizi, occorre aggiornare alcuni record presso l'host DNS o il registrar.
  
1. In genere, l'installazione guidata rileva la registrazione e offre un collegamento a istruzioni dettagliate per aggiornare i record NS nel sito Web di registrazione. In caso contrario, [nameservers modifiche alla configurazione di Office 365 con un registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).
    
2. La posta elettronica e altri servizi verranno configurati automaticamente.
    
### <a name="step-4-manage-devices-and-work-files"></a>Passaggio 4: Gestire i dispositivi e file di lavoro

1. Nel **file di lavoro Protect nei dispositivi mobili** pagina impostata **Protect lavoro file quando dispositivi sono perduti o rubati** e le impostazioni di **gestire l'accesso al file di Office su dispositivi mobili** **in**. È inoltre possibile accedere a ogni secondario impostazione facendo clic sulle virgolette acute accanto a ogni impostazione.
  
  Tutti lavoro file gli utenti con licenza sono ora protetti iOS e dispositivi Android, non appena si [installa Office apps](set-up-mobile-devices.md) (e l'autenticazione con le proprie credenziali di Microsoft 365 Business). 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. Nella pagina **Configurazione dispositivo impostare Windows 10** impostazione **Sicura Windows 10 dispositivi** di **attivato**.
  
   È inoltre possibile accedere a ogni secondario impostazione facendo clic sull'accento circonflesso accanto al nome.
  
3. Impostazione di **Installare Office su dispositivi 10 Windows** **Sì** se tutti gli utenti dispongono di computer Windows 10 e verrà installato alcun esistente Office o le installazioni di Office a portata di clic. In questo caso non è possibile impostare questa opzione su **No**. Dopo aver preparato il computer degli utenti, è possibile [installare automaticamente Office](auto-install-or-uninstall-office.md) successivamente dall'interfaccia di amministrazione. Per ulteriori informazioni, vedere [Preparazione dell'installazione client di Office](prepare-for-office-client-deployment.md).
  
    Verranno proiettare il più presto possibile man mano che i file di lavoro degli utenti con licenza nei dispositivi Windows 10 [partecipare proprio dispositivo Windows 10](set-up-windows-devices.md) a un dominio aziendale Microsoft 365 Azure Active Directory o [installare Windows 10 in un nuovo computer](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) durante l'unione contemporaneamente a Microsoft 365 Dominio di Azure Active Directory aziendale. 
  
4. Fare clic su **Avanti** per completare la configurazione. 
  
    Inviare infine il proprio feedback per aiutarci a migliorare l'esperienza utente.
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a>Impostazioni di sicurezza aggiuntive

Oltre a protezione e impostazione di conformità dell'installazione guidata, è possibile configurare impostazioni aggiuntive seguenti:
  
- Consente di impostare una protezione contro gli allegati non sicuri. **Protezione da minacce avanzate** (Degli strumenti di analisi) identifica contenuto dannoso e quindi blocca il rilascio di unsafe attachments, proteggere contro gli schemi di phishing e infezioni ransomware. Per attivare la protezione degli allegati, vedere [impostazione dei criteri di sicurezza allegati di Office 365 degli strumenti di analisi](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).
    
- Proteggere l'ambiente quando gli utenti fare clic sui collegamenti dannosi. Degli strumenti di analisi vengono esaminati i collegamenti nella posta elettronica in fase di un utente fa clic su essi. Se un collegamento non sicuro, l'utente viene avvisato non per visitare il sito o informato che il sito è stato bloccato. Consente di evitare truffe. [Impostare i criteri di Office 365 degli strumenti di analisi provvisoria collegamenti](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) o [impostare i criteri di Office 365 degli strumenti di analisi provvisoria collegamenti](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).
    
- È possibile preservare tutto il contenuto delle cassette postali inclusi gli elementi eliminati inserendo intera cassetta postale dell'utente controversia **attesa**. Per ulteriori informazioni, vedere 
- [Impostare il mantenimento di posta elettronica con archiviazione Exchange Online](security-features.md#set-up-email-retention-with-exchange-online-archiving).
    
- Configurare **i criteri di conservazione**personalizzata, ad esempio, per conservare per un determinato periodo di tempo o eliminare in modo permanente il contenuto alla fine del periodo di conservazione. È possibile abilitare i criteri di conservazione personalizzata nella titoli e centro conformità, andare alla **governance dati** \> **conservazione**, quindi seguire le istruzioni della procedura guidata. Per ulteriori informazioni, vedere [Panoramica di criteri di conservazione](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).
    
## <a name="next-steps"></a>Passaggi successivi

Per gli utenti che hanno le proprie licenze, il passaggio successivo consiste nel configurare i dispositivi.<br/> Vedere [Configurare i dispositivi Windows per utenti di Microsoft 365 Business](set-up-windows-devices.md) e [Configurare i dispositivi mobili per utenti di Microsoft 365 Business](set-up-mobile-devices.md). <br/>Vedere [Gestire Microsoft 365 Business](manage.md) per i collegamenti agli argomenti su come impostare i criteri di protezione di dispositivi e app e su come rimuovere i dati dai dispositivi degli utenti. 
  


