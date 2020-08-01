---
title: Pianificare la configurazione di Microsoft 365 per le aziende
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: Informazioni sui requisiti e le considerazioni per l'esecuzione del passaggio a Microsoft 365 for business.
ms.openlocfilehash: b7d815da012e1c104561d5fccfb9e1704ac5c447
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529661"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>Pianificare la configurazione di Microsoft 365 per le aziende

Questo articolo è destinato agli utenti che hanno effettuato la sottoscrizione a un piano Microsoft 365 for business.
  
Prima di spostare l'organizzazione in Microsoft 365, è necessario soddisfare i requisiti, informazioni che è necessario avere a disposizione e decisioni da prendere.


  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>Informazioni per avere a disposizione prima di eseguire l'installazione guidata

Quando si è pronti per eseguire l'installazione guidata e spostare il dominio in Microsoft 365, ecco le informazioni che è necessario avere a portata di mano:
  
- Elenco di utenti che si desidera aggiungere a Microsoft 365. Anche se sono già state aggiunte a Microsoft 365, se si stanno aggiornando le informazioni sul dominio, è necessario immettere i propri nomi qui.

- Come si intende notificare ai dipendenti l'ID utente e la password in modo che possano accedere. Si intende chiamarli e fornire le informazioni? Oppure si preferisce inviare queste informazioni al loro indirizzo di posta elettronica personale? Non avranno accesso ai messaggi di posta elettronica, quindi non è possibile utilizzarlo.

- Se si dispone di un nome di dominio per l'organizzazione (ad esempio contoso.com) **e** si prevede di utilizzare Microsoft e-mail, è necessario sapere dove è registrato il dominio e disporre di informazioni di accesso.

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>Cosa succede quando si esegue l'installazione guidata di Microsoft 365

La procedura guidata di installazione illustra l'installazione delle app Microsoft 365 nel computer, l'aggiunta e la verifica del dominio, l'aggiunta di utenti e l'assegnazione di licenze a tali applicazioni e la connessione del dominio.

> [!NOTE]
> Se è necessario [assegnare ruoli di amministratore in Microsoft 365 for business](../add-users/assign-admin-roles.md) agli utenti che si aggiungono nella procedura guidata, è possibile farlo in un secondo momento nella pagina **utenti** . 
  
Se la configurazione guidata non viene completata, è possibile completare le attività di installazione in qualsiasi momento dalla configurazione dell'interfaccia di [Amministrazione](https://go.microsoft.com/fwlink/p/?linkid=2024339)  >  **Setup**. Da qui è possibile migrare la posta elettronica e i contatti da un altro servizio di posta elettronica, cambiare il dominio dell'account di amministratore, gestire le informazioni di fatturazione, aggiungere o rimuovere utenti, reimpostare le password ed eseguire altre funzioni aziendali. Per ulteriori informazioni sulle differenze tra l'installazione guidata e la pagina di **installazione** , vedere [differenze tra l'installazione guidata di Microsoft 365 e la pagina di installazione](o365-setup-wizard-and-setup-page.md).

Per qualsiasi difficoltà, siamo disponibili telefonicamente. [Opzioni di assistenza](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>Quando non è opportuno usare la configurazione guidata: Ambienti ibridi e sincronizzazione di Active Directory

Esistono due scenari che includono la migrazione di dati o utenti da ambienti locali o la configurazione di un sistema ibrido che include la sincronizzazione della directory. Se si è in una o più categorie, seguire le istruzioni riportate in questi articoli:
  
- Per configurare la sincronizzazione della directory con Active Directory locale, vedere Configurare la [sincronizzazione della directory per microsoft 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)e per comprendere i diversi modelli di identità in Microsoft 365, leggere [understanding Microsoft 365 Identity e Azure Active Directory](https://docs.microsoft.com/office365/enterprise/about-office-365-identity).

- Per configurare una distribuzione ibrida di Exchange, vedere il set completo di istruzioni per le diverse modalità di configurazione di una distribuzione ibrida di Exchange, inclusa la configurazione dei record DNS, disponibile qui: [Assistente per la distribuzione di Exchange Server](https://aka.ms/exdeploy)

- Per configurare una distribuzione ibrida di SharePoint, in particolare le caratteristiche relative al sito e alla ricerca ibrida, vedere [Ricerca ibrida in SharePoint](https://docs.microsoft.com/SharePoint/hybrid/hybrid-search-in-sharepoint).

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>Passare a Microsoft 365 tutti insieme o in fasi

- **Si desidera spostare l'organizzazione in Microsoft 365 tutti insieme?** In caso affermativo, quindi pianificare la trasferimento immediato del dominio a Microsoft 365. Iniziare eseguendo l'installazione guidata di Microsoft 365; verrà chiesto di configurare il dominio.

- **Si desidera passare gradualmente a Microsoft 365?** Se si desidera passare a Microsoft 365 in fasi, ignorare l'esecuzione dell'installazione guidata di Microsoft 365 e prendere in considerazione l'adozione delle funzionalità di Microsoft 365 nell'ordine seguente:

    1. [Aggiungere i dipendenti a Microsoft 365 in](../add-users/add-users.md) modo che possano scaricare e installare le app di Office.

    2. [Scaricare e installare le app di Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) per usare Word, Excel e PowerPoint nel computer e nei dispositivi.

    3. [Configurare Microsoft teams](#plan-for-teams) da utilizzare per le riunioni.

    4. [Spostare il contenuto in Microsoft 365 cloud storage](set-up-file-storage-and-sharing.md) (OneDrive o siti del team di SharePoint).

    5. Quando si è pronti, nell'interfaccia di [Amministrazione](https://go.microsoft.com/fwlink/p/?linkid=2024339)selezionare **installazione** nel riquadro di spostamento a sinistra e utilizzare la pagina di **installazione** per [spostare il dominio e la posta elettronica](add-domain.md).

## <a name="check-that-your-devices-meet-system-requirements"></a>Verificare che i dispositivi soddisfino i requisiti di sistema

Ogni persona all'interno dell'organizzazione può installare la famiglia di app di Office 2016 (Word, Excel, PowerPoint e così via) su un massimo di cinque PC e Mac. Vedere i requisiti di sistema operativo e computer per installare le [applicazioni Office 2016](https://go.microsoft.com/fwlink/?LinkId=534827) per le aziende.
  
Le app mobili possono essere installate su dispositivi iOS, Android e Windows. Per informazioni sui dispositivi mobili e i browser supportati, vedere [Requisiti di sistema di Office](https://go.microsoft.com/fwlink/?LinkId=534827).
  
## <a name="plan-for-email"></a>Pianificare la posta elettronica

Se si prevede di passare da un servizio di posta elettronica esistente a Microsoft 365, in genere sono necessari due giorni per eseguire il passaggio.
  
### <a name="plan-for-email-downtime"></a>Pianificare il tempo di inattività per la posta elettronica
  
Se si intende utilizzare Microsoft 365 per la posta elettronica:
  
- Per spostare l'indirizzo di posta elettronica aziendale, ad esempio *rob \@ contoso.com*, da un altro servizio di posta elettronica a Microsoft 365, è necessario indirizzare la posta elettronica alla nuova cassetta postale di Microsoft 365. A tale scopo, selezionare **Esegui la migrazione dei dati degli utenti** nella pagina di **installazione** , in cui vengono illustrati gli aggiornamenti che è necessario apportare all'host di dominio, passo dopo passo.

- Una volta aggiornato l'host del dominio, le modifiche diventano in genere effettive dopo una o due ore. Tuttavia, tenere presente che a volte può richiedere fino a 72 ore affinché le modifiche vengano aggiornate su Internet.

- Poiché potrebbe essere necessario un tempo di inattività della posta elettronica, si consiglia di passare alla posta elettronica Microsoft durante una serata o un fine settimana quando si ricevono meno messaggi di posta elettronica.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>Pianificare il trasferimento di posta elettronica, contatti e calendario
  
Se si intende utilizzare Microsoft 365 per l'account di posta elettronica, è possibile portare con sé la posta elettronica, i contatti e il calendario esistenti. La pagina di **installazione** consente di spostare il messaggio di posta elettronica e i contatti esistenti per la maggior parte degli scenari. Sono anche disponibili guide dettagliate per spostare una o più cassette postali.
  
|**Quante cassette postali?**|**Consiglio**|
|:-----|:-----|
|Poche  <br/> |Se non si desidera utilizzare la pagina di **installazione** per eseguire la migrazione delle cassette postali, è possibile consentire ai proprietari delle cassette postali di migrare la posta elettronica e i contatti. Vedere [eseguire la migrazione della posta elettronica e dei contatti a Microsoft 365 for business](migrate-email-and-contacts-admin.md).  <br/> |
|Molte  <br/> |Se si sta eseguendo la migrazione da Gmail, vedere [migrate le cassette postali G Suite a Microsoft 365](https://docs.microsoft.com/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes).  <br/> Se si sta eseguendo la migrazione da un altro provider di posta elettronica, incluso Exchange, vedere [modalità di migrazione di più account di posta elettronica a Microsoft 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>Pianificare l'archiviazione di file e la migrazione

Microsoft 365 fornisce archiviazione cloud per singoli utenti, organizzazioni di piccole dimensioni e aziende. Per informazioni sulle operazioni da archiviare, vedere [dove è possibile archiviare i documenti in Microsoft 365](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790).
  
- **È possibile spostare centinaia di file** in [OneDrive](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB) o in un [sito del team di SharePoint](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242). È possibile caricare 100 file per volta. Evitare di caricare file di dimensioni maggiori di 2 GB, che sono le dimensioni massime consentite per impostazione predefinita.
  
- **Se si desidera spostare diverse migliaia di file** in Microsoft 365 storage, esaminare i [limiti di SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=856113). È consigliabile usare uno strumento di migrazione o valutare se affidarsi a un [partner](https://go.microsoft.com/fwlink/?linkid=391089) per ricevere assistenza con la migrazione. Per informazioni su come eseguire la migrazione di un numero elevato di file, vedere il [Manuale dell'utente sulla migrazione di SharePoint Online e OneDrive](https://go.microsoft.com/fwlink/?LinkId=723574).
  
## <a name="plan-for-teams"></a>Pianificare i team

È possibile utilizzare Microsoft teams per effettuare chiamate ad altre persone dell'organizzazione che si trovano nell'abbonamento. Ad esempio, se l'organizzazione dispone di 10 persone, è possibile chiamare e inviare messaggi istantanei reciprocamente utilizzando Team senza alcuna configurazione speciale. Per ulteriori informazioni, vedere [Introduzione a Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-quick-start).

Per le organizzazioni di grandi dimensioni o per le distribuzioni ibride di Skype for business, locali o ibridi, vedere [How to roll out Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/how-to-roll-out-teams).
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Pianificare l'integrazione con Active Directory o altro software

- **Si vuole eseguire l'integrazione con Active Directory locale?** È possibile integrare Active Directory locale con Microsoft 365 utilizzando Azure Active Directory Connect. Per istruzioni, vedere [configurare la sincronizzazione della directory per Microsoft 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).
  
- **Si desidera integrare Microsoft 365 con software creato da altre aziende?** Se è necessario integrare Microsoft 365 con altri software nell'organizzazione, è consigliabile prendere in considerazione l' [assunzione di un partner](https://go.microsoft.com/fwlink/?linkid=391089) per aiutarvi nella distribuzione.
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>Si desidera consentire a un utente di configurare Microsoft 365?

- **Se si hanno meno di 50 dipendenti:**

  - **Chiedi aiuto e ti chiameremo**. Dopo aver acquistato Microsoft 365, è possibile accedere all'interfaccia di amministrazione (non è necessario eseguire il programma di installazione per ottenerlo). Nella parte inferiore dell'interfaccia di amministrazione, selezionare **serve assistenza?** Descrivi il tuo problema e ti chiameremo. 
  - **Chiamare il [supporto di Microsoft 365 per le aziende](../contact-support-for-business-products.md) con le proprie domande**. Microsoft è sempre pronta a offrire supporto. 
  - **Valutare se affidarsi a un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089)**. Se si ha un breve periodo di tempo o si hanno requisiti avanzati (come lo spostamento di migliaia di file in Microsoft 365 cloud storage o l'integrazione con altri software), un partner esperto può essere di grande aiuto. 

- **Se si hanno più di 50 dipendenti**, è disponibile il [FastTrack Onboarding Center](https://go.microsoft.com/fwlink/?LinkId=517115) per offrire assistenza con la distribuzione. 
