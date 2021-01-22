---
title: Pianificare la configurazione di Microsoft 365 per le aziende
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: Informazioni sui requisiti e le considerazioni per passare a Microsoft 365 per le aziende.
ms.openlocfilehash: 9158ad5a56b78fd8173ae81a2e9e4a5bd51633ca
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926823"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>Pianificare la configurazione di Microsoft 365 per le aziende

Questo articolo è per gli utenti che hanno sottoscritto un piano di Microsoft 365 per le aziende.
  
Prima di spostare l'organizzazione in Microsoft 365, è necessario soddisfare i requisiti, le informazioni necessarie e le decisioni da prendere.


  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>Informazioni da avere a portata di mano prima di eseguire la configurazione guidata

Quando si è pronti per eseguire la configurazione guidata e spostare il dominio in Microsoft 365, ecco le informazioni necessarie:
  
- Elenco di persone che si desidera aggiungere a Microsoft 365. Anche se sono già state aggiunte a Microsoft 365, se si aggiornano le informazioni sul dominio, è necessario immettere i relativi nomi qui.

- Come informare i dipendenti dell'ID utente e della password in modo che possano accedere. Si intende chiamarli e fornire le informazioni? Oppure si preferisce inviare queste informazioni al loro indirizzo di posta elettronica personale? Non hanno accesso alla loro posta elettronica, quindi non è possibile usarlo.

- Se si ha un nome di dominio per l'organizzazione (ad esempio **contoso.com)** e si prevede di usare la posta elettronica Microsoft, è necessario sapere dove è registrato il dominio e avere informazioni di accesso.

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>Cosa succede quando si esegue la configurazione guidata di Microsoft 365

La configurazione guidata illustra come installare le app di Microsoft 365 nel computer, aggiungere e verificare il dominio, aggiungere utenti e assegnare licenze e connettere il dominio.

> [!NOTE]
> Se è necessario assegnare ruoli di amministratore [in Microsoft 365 per](../add-users/assign-admin-roles.md) le aziende agli utenti aggiunti nella procedura guidata, è possibile farlo in un secondo momento nella **pagina** Utenti. 
  
Se non si completa l'installazione guidata, è possibile completare le attività di installazione in qualsiasi momento [dall'installazione dell'interfaccia di](https://go.microsoft.com/fwlink/p/?linkid=2024339)  >  **amministrazione.** Da qui è possibile eseguire la migrazione di posta elettronica e contatti da un altro servizio di posta elettronica, modificare il dominio dell'account amministratore, gestire le informazioni di fatturazione, aggiungere o rimuovere utenti, reimpostare le password ed eseguire altre funzioni aziendali. Per ulteriori informazioni sulle differenze tra  l'installazione guidata e la pagina Installazione, vedere Differenze tra l'installazione guidata di [Microsoft 365](o365-setup-wizard-and-setup-page.md)e la pagina Installazione.

Per qualsiasi difficoltà, siamo disponibili telefonicamente. [Opzioni di assistenza](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>Quando non è opportuno usare la configurazione guidata: Ambienti ibridi e sincronizzazione di Active Directory

Esistono due scenari che includono la migrazione di dati o utenti da ambienti locali o la configurazione di un sistema ibrido che include la sincronizzazione della directory. If you're in either category, follow the instructions in these articles:
  
- Per configurare la sincronizzazione della directory con Active Directory locale, vedere Configurare la sincronizzazione della directory per [Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)e per comprendere i diversi modelli di identità in Microsoft 365, vedere Informazioni sull'identità di [Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/about-microsoft-365-identity)e Azure Active Directory.

- Per configurare una distribuzione ibrida di Exchange, vedere il set completo di istruzioni per le diverse modalità di configurazione di una distribuzione ibrida di Exchange, inclusa la configurazione dei record DNS, disponibile qui: [Assistente per la distribuzione di Exchange Server](https://aka.ms/exdeploy)

- Per configurare una distribuzione ibrida di SharePoint, in particolare le caratteristiche relative al sito e alla ricerca ibrida, vedere [Ricerca ibrida in SharePoint](https://docs.microsoft.com/SharePoint/hybrid/hybrid-search-in-sharepoint).

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>Passare a Microsoft 365 contemporaneamente o in più fasi

- **Si desidera spostare l'organizzazione in Microsoft 365 contemporaneamente?** In tal caso, pianificare immediatamente lo spostamento del dominio in Microsoft 365. Per iniziare, eseguire la configurazione guidata di Microsoft 365; verrà richiesto di configurare il dominio.

- **Si desidera passare gradualmente a Microsoft 365?** Se si vuole passare a Microsoft 365 in più fasi, ignorare l'esecuzione della configurazione guidata di Microsoft 365 e prendere in considerazione l'adozione delle funzionalità di Microsoft 365 nell'ordine seguente:

    1. [Aggiungere i dipendenti a Microsoft 365](../add-users/add-users.md) in modo che possano scaricare e installare le app di Office.

    2. [Scaricare e installare le app di Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) per usare Word, Excel e PowerPoint nel computer e nei dispositivi.

    3. [Configurare Microsoft Teams da](#plan-for-teams) usare per le riunioni.

    4. [Spostare il contenuto nell'archiviazione cloud di Microsoft 365](set-up-file-storage-and-sharing.md) (siti di OneDrive o del team di SharePoint).

    5. Quando si è pronti, nell'interfaccia  di amministrazione [selezionare](https://go.microsoft.com/fwlink/p/?linkid=2024339)Installazione nel  riquadro di spostamento sinistro e utilizzare la pagina Configurazione per spostare il dominio e la [posta elettronica.](add-domain.md)

## <a name="check-that-your-devices-meet-system-requirements"></a>Verificare che i dispositivi soddisfino i requisiti di sistema

Ogni utente dell'organizzazione può installare la famiglia di app di Office 2016 (Word, Excel, PowerPoint e così via) su un massimo di cinque PC e Mac. Vedere i requisiti di sistema operativo e computer per installare le [applicazioni Office 2016](https://go.microsoft.com/fwlink/?LinkId=534827) per le aziende.
  
Le app per dispositivi mobili possono essere installate nei dispositivi iOS, Android e Windows. Per informazioni sui dispositivi mobili e i browser supportati, vedere [Requisiti di sistema di Office](https://go.microsoft.com/fwlink/?LinkId=534827).
  
## <a name="plan-for-email"></a>Pianificare la posta elettronica

Se si prevede di passare da un servizio di posta elettronica esistente a Microsoft 365, in genere sono necessari due giorni per eseguire il passaggio.
  
### <a name="plan-for-email-downtime"></a>Pianificare il tempo di inattività per la posta elettronica
  
Se si ha intenzione di usare Microsoft 365 per la posta elettronica:
  
- Per spostare l'indirizzo di posta elettronica aziendale (ad esempio *Rob \@ contoso.com)* da un altro servizio di posta elettronica a Microsoft 365, è necessario indirizzare la posta da recapitare alla nuova cassetta postale di Microsoft 365. A tale scopo, **selezionare** Esegui la  migrazione dei dati degli utenti nella pagina Di installazione, in cui vengono fornite istruzioni dettagliate sugli aggiornamenti da apportare all'host di dominio.

- Una volta aggiornato l'host del dominio, le modifiche diventano in genere effettive dopo una o due ore. Tuttavia, tenere presente che a volte possono essere necessarie fino a 72 ore prima che le modifiche possano essere aggiornate su Internet.

- Poiché potrebbe verificarsi un tempo di inattività della posta elettronica, è consigliabile pianificare il passaggio alla posta elettronica Microsoft durante la sera o il fine settimana quando si ricevono meno messaggi di posta elettronica.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>Pianificare il trasferimento di posta elettronica, contatti e calendario
  
Se si ha intenzione di usare Microsoft 365 per l'account di posta elettronica, è possibile portare la posta elettronica, i contatti e il calendario esistenti. La **pagina Configurazione** consente di spostare la posta elettronica e i contatti esistenti per la maggior parte degli scenari. Sono anche disponibili guide dettagliate per spostare una o più cassette postali.
  
|**Quante cassette postali?**|**Consiglio**|
|:-----|:-----|
|Poche  <br/> |Se non si desidera utilizzare  la pagina Di installazione per eseguire la migrazione delle cassette postali, è possibile consentire ai proprietari delle cassette postali di eseguire la migrazione dei propri messaggi di posta elettronica e contatti. Vedere [Eseguire la migrazione di posta elettronica e contatti a Microsoft 365 per le aziende.](migrate-email-and-contacts-admin.md)  <br/> |
|Molte  <br/> |Se si esegue la migrazione da Gmail, vedere Eseguire la migrazione delle cassette postali [di G Suite a Microsoft 365.](https://docs.microsoft.com/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes)  <br/> Se si esegue la migrazione da un altro provider di posta elettronica, incluso Exchange, vedere Modalità di migrazione di più account di posta elettronica [a Microsoft 365.](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>Pianificare l'archiviazione di file e la migrazione

Microsoft 365 fornisce spazio di archiviazione cloud per singoli utenti, piccole organizzazioni e aziende. Per indicazioni sugli elementi da archiviare, vedere Dove archiviare i documenti [in Microsoft 365.](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790)
  
- **È possibile spostare centinaia di file** in [OneDrive](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB) o in un [sito del team di SharePoint.](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242) È possibile caricare 100 file per volta. Evitare di caricare file di dimensioni maggiori di 2 GB, che sono le dimensioni massime consentite per impostazione predefinita.
  
- **Se si desidera spostare diverse migliaia di file** nell'archiviazione di Microsoft 365, esaminare i limiti di [SharePoint Online.](https://go.microsoft.com/fwlink/p/?LinkID=856113) È consigliabile usare uno strumento di migrazione o valutare se affidarsi a un [partner](https://go.microsoft.com/fwlink/?linkid=391089) per ricevere assistenza con la migrazione. Per informazioni su come eseguire la migrazione di un numero elevato di file, vedere il [Manuale dell'utente sulla migrazione di SharePoint Online e OneDrive](https://go.microsoft.com/fwlink/?LinkId=723574).
  
## <a name="plan-for-teams"></a>Pianificare Teams

È possibile utilizzare Microsoft Teams per effettuare chiamate ad altre persone dell'organizzazione che fanno parte dell'abbonamento. Ad esempio, se l'organizzazione ha 10 persone, è possibile chiamarsi e messaggistica istantanea tramite Teams senza alcuna configurazione speciale. Per altre informazioni, vedere [Introduzione a Microsoft Teams.](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-quick-start)

Per organizzazioni di grandi dimensioni o se si inizia da skype for business, distribuzioni locali o ibride, vedere [Come implementare Microsoft Teams.](https://docs.microsoft.com/MicrosoftTeams/how-to-roll-out-teams)
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Pianificare l'integrazione con Active Directory o altro software

- **Si vuole eseguire l'integrazione con Active Directory locale?** È possibile integrare Active Directory locale con Microsoft 365 usando Azure Active Directory Connect. Per istruzioni, vedere [Configurare la sincronizzazione della directory per Microsoft 365.](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)
  
- **Si desidera integrare Microsoft 365 con il software creato da altre società?** Se è necessario integrare Microsoft 365 con altri software dell'organizzazione, è consigliabile prendere in considerazione l'assunzione di un [partner](https://go.microsoft.com/fwlink/?linkid=391089) per facilitare la distribuzione.
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>Si vuole che qualcuno ti aiuti a configurare Microsoft 365?

- **Se si hanno meno di 50 dipendenti:**

  - **Richiedi assistenza e ti chiameremo**. Dopo aver acquistato Microsoft 365, è possibile accedere all'interfaccia di amministrazione (non è necessario eseguire il programma di installazione per accedervi). At the bottom of the admin center, select **Need help?** Descrivi il problema e ti chiameremo. 
  - **Chiamare [il supporto di Microsoft 365 per le](../contact-support-for-business-products.md) aziende con le proprie domande.** Microsoft è sempre pronta a offrire supporto. 
  - **Valutare se affidarsi a un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089)**. Se si ha poco tempo o se si hanno requisiti avanzati (come lo spostamento di migliaia di file nell'archiviazione cloud di Microsoft 365 o l'integrazione con altro software), un partner esperto può essere un grande aiuto. 

- **Se si hanno più di 50 dipendenti**, è disponibile il [FastTrack Onboarding Center](https://go.microsoft.com/fwlink/?LinkId=517115) per offrire assistenza con la distribuzione. 
