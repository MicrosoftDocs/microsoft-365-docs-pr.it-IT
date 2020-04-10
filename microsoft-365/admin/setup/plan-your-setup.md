---
title: Pianificare la configurazione di Office 365 per le aziende
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
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: Informazioni sulle operazioni necessarie per configurare Office 365 for business.
ms.openlocfilehash: bf2db70a77f6ddaf3a2bae04180f0f5be9dbaf05
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212162"
---
# <a name="plan-your-setup-of-office-365-for-business"></a>Pianificare la configurazione di Office 365 per le aziende

Questo articolo è destinato agli abbonati a un piano di Office 365 Business.
  
Prima di spostare l'organizzazione in Office 365, è necessario decidere quali sono le informazioni necessarie per l'utente.
  
## <a name="info-to-have-on-hand-before-you-run-the-office-365-setup-wizard"></a>Informazioni da avere a portata di mano prima di eseguire la configurazione guidata di Office 365

Quando si vuole eseguire la configurazione guidata di Office 365 e spostare il dominio in Office 365, ecco le informazioni che è necessario avere a disposizione:
  
- Elenco delle persone da aggiungere a Office 365. Anche se sono già state aggiunte a Office 365, se si aggiornano le informazioni del dominio, è necessario immettere qui i loro nomi.

- Come notificare ai dipendenti i rispettivi ID utente e password di Office 365 in modo che possano accedere? Si intende chiamarli e fornire le informazioni? Oppure si preferisce inviare queste informazioni al loro indirizzo di posta elettronica personale? Poiché non hanno ancora accesso alla propria posta elettronica di Office 365, questo metodo non può essere usato.

- Se si dispone di un nome di dominio per l'organizzazione (ad esempio contoso.com) **e** si prevede di utilizzare la posta elettronica di Office 365, è necessario sapere dove è registrato il dominio e disporre di informazioni di accesso.

## <a name="what-happens-when-you-run-the-office-365-setup-wizard"></a>Cosa accade quando si esegue la Configurazione guidata di Office 365

La procedura guidata di installazione illustra l'installazione delle app di Office 365 nel computer, l'aggiunta e la verifica del dominio, l'aggiunta di utenti e l'assegnazione delle licenze e la connessione del dominio.

> [!NOTE]
> Se è necessario [assegnare ruoli di amministratore in Office 365 for business](../add-users/assign-admin-roles.md) agli utenti che si aggiungono nella procedura guidata, è possibile farlo in un secondo momento nella pagina **utenti** . 
  
Se la configurazione guidata non viene completata, è possibile completare le attività di installazione in qualsiasi momento dalla**configurazione**dell'interfaccia di [Amministrazione](https://go.microsoft.com/fwlink/p/?linkid=2024339) > . Da qui è possibile migrare la posta elettronica e i contatti da un altro servizio di posta elettronica, cambiare il dominio dell'account di amministratore, gestire le informazioni di fatturazione, aggiungere o rimuovere utenti, reimpostare le password ed eseguire altre funzioni aziendali. Per ulteriori informazioni sulle differenze tra l'installazione guidata e la pagina di **installazione** , vedere [differenze tra l'installazione guidata di Office 365 e la pagina di installazione](o365-setup-wizard-and-setup-page.md).

Per qualsiasi difficoltà, siamo disponibili telefonicamente. [Opzioni di assistenza](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>Quando non è opportuno usare la configurazione guidata: Ambienti ibridi e sincronizzazione di Active Directory

Esistono due scenari che includono la migrazione di dati o utenti da ambienti locali o la configurazione di un sistema ibrido che include la sincronizzazione della directory. Se si è in una o più categorie, seguire le istruzioni riportate in questi articoli:
  
- Per configurare la sincronizzazione della directory con Active Directory locale, vedere [Configurare la sincronizzazione della directory in Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) e, per informazioni sui vari modelli di identità in Office 365, vedere [Informazioni sulla gestione delle identità di Office 365 e Azure Active Directory](https://docs.microsoft.com/office365/enterprise/about-office-365-identity).

- Per configurare una distribuzione ibrida di Exchange, vedere il set completo di istruzioni per le diverse modalità di configurazione di una distribuzione ibrida di Exchange, inclusa la configurazione dei record DNS, disponibile qui: [Assistente per la distribuzione di Exchange Server](https://aka.ms/exdeploy)

- Per configurare una distribuzione ibrida di SharePoint, in particolare le caratteristiche relative al sito e alla ricerca ibrida, vedere [Ricerca ibrida in SharePoint](https://docs.microsoft.com/SharePoint/hybrid/hybrid-search-in-sharepoint).

## <a name="move-to-office-365-all-at-once-or-in-stages"></a>Passare a Office 365 tutti insieme o in fasi

- **Si desidera spostare l'organizzazione in Office 365 tutte contemporaneamente?** In questo caso, pianificare lo spostamento immediato del dominio in Office 365. Per iniziare, eseguire la configurazione guidata di Office 365, che chiederà di configurare il dominio.

- **Si desidera passare gradualmente a Office 365?** Se si vuole passare a Office 365 in più fasi, non eseguire la configurazione guidata di Office 365, ma valutare se adottare le caratteristiche di Office 365 in questo ordine:

    1. [Aggiungere i dipendenti in Office 365](../add-users/add-users.md) in modo che possano scaricare e installare le app di Office.

    2. [Scaricare e installare le app di Office](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) per usare Word, Excel e PowerPoint nel computer e nei dispositivi.

    3. [Configurare Microsoft teams](#plan-for-teams) da utilizzare per le riunioni.

    4. [Spostare il contenuto in Office 365 cloud storage](set-up-file-storage-and-sharing.md) (OneDrive o siti del team di SharePoint).

    5. Quando si è pronti, nell'interfaccia di [Amministrazione](https://go.microsoft.com/fwlink/p/?linkid=2024339)selezionare **installazione** nel riquadro di spostamento a sinistra e utilizzare la pagina di **installazione** per [spostare il dominio e la posta elettronica](add-domain.md).

## <a name="check-that-your-devices-meet-system-requirements"></a>Verificare che i dispositivi soddisfino i requisiti di sistema

Ogni persona all'interno dell'organizzazione può installare la famiglia di app di Office 2016 (Word, Excel, PowerPoint e così via) su un massimo di cinque PC e Mac. Vedere i requisiti di sistema operativo e computer per installare le [applicazioni Office 2016](https://go.microsoft.com/fwlink/?LinkId=534827) per le aziende.
  
Le app mobili possono essere installate su dispositivi iOS, Android e Windows. Per informazioni sui dispositivi mobili e i browser supportati, vedere [Requisiti di sistema di Office](https://go.microsoft.com/fwlink/?LinkId=534827).
  
## <a name="plan-for-email"></a>Pianificare la posta elettronica

Se si prevede di passare da un servizio di posta elettronica esistente a Office 365, in genere sono necessari due giorni per effettuare il passaggio.
  
### <a name="plan-for-email-downtime"></a>Pianificare il tempo di inattività per la posta elettronica
  
Se si prevede di usare Office 365 per la posta elettronica:
  
- Per spostare l'indirizzo di posta elettronica aziendale, ad esempio *Rob@contoso.com*, da un altro servizio di posta elettronica a Office 365, è necessario indirizzare la posta elettronica alla nuova cassetta postale di Office 365. A tale scopo, selezionare **Esegui la migrazione dei dati degli utenti** nella pagina di **installazione** , in cui vengono illustrati gli aggiornamenti che è necessario apportare all'host di dominio, passo dopo passo.

- Una volta aggiornato l'host del dominio, le modifiche diventano in genere effettive dopo una o due ore. Tuttavia, tenere presente che a volte può richiedere fino a 72 ore affinché le modifiche vengano aggiornate su Internet.

- Poiché potrebbero verificarsi tempi di inattività della posta elettronica, è consigliabile pianificare il passaggio a Office 365 di sera o nel fine settimana, quando si ricevono meno messaggi.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>Pianificare il trasferimento di posta elettronica, contatti e calendario
  
Se si intende usare Office 365 per l'account di posta elettronica, è possibile trasferire anche i messaggi, i contatti e il calendario esistenti. La pagina di **installazione** consente di spostare il messaggio di posta elettronica e i contatti esistenti per la maggior parte degli scenari. Sono anche disponibili guide dettagliate per spostare una o più cassette postali.
  
|**Quante cassette postali?**|**Consiglio**|
|:-----|:-----|
|Poche  <br/> |Se non si desidera utilizzare la pagina di **installazione** per eseguire la migrazione delle cassette postali, è possibile consentire ai proprietari delle cassette postali di migrare la posta elettronica e i contatti. Vedere [Eseguire la migrazione di posta elettronica e contatti in Office 365 per le aziende](migrate-email-and-contacts-admin.md).  <br/> |
|Molte  <br/> |Se si esegue la migrazione da Gmail, vedere [eseguire la migrazione delle cassette postali G Suite a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes).  <br/> Se si esegue la migrazione da un altro provider di posta elettronica, incluso Exchange, vedere [modalità di migrazione di più account di posta elettronica a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>Pianificare l'archiviazione di file e la migrazione

Office 365 fornisce archiviazione cloud per singoli utenti, organizzazioni di piccole dimensioni e aziende. Per indicazioni su dove archiviare ogni elemento, vedere [Dove archiviare i documenti in Office 365](https://support.office.com/article/c7c20284-bc94-47f4-9728-d28e9daf0790.aspx).
  
- **È possibile spostare centinaia di file** in [OneDrive](https://support.office.com/article/45114744-6D42-45CD-8975-F9617819BDEB.aspx) o in un [sito del team di SharePoint](https://support.office.com/article/da549fb1-1fcb-4167-87d0-4693e93cb7a0.aspx#__toc384119242). È possibile caricare 100 file per volta. Evitare di caricare file di dimensioni maggiori di 2 GB, che sono le dimensioni massime consentite per impostazione predefinita.
  
- **Per spostare diverse migliaia di file** nello spazio di archiviazione di Office 365, vedere [Limiti di SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=856113). È consigliabile usare uno strumento di migrazione o valutare se affidarsi a un [partner](https://go.microsoft.com/fwlink/?linkid=391089) per ricevere assistenza con la migrazione. Per informazioni su come eseguire la migrazione di un numero elevato di file, vedere il [Manuale dell'utente sulla migrazione di SharePoint Online e OneDrive](https://go.microsoft.com/fwlink/?LinkId=723574).
  
## <a name="plan-for-teams"></a>Pianificare i team

È possibile utilizzare Microsoft teams per effettuare chiamate ad altre persone dell'organizzazione che si trovano nell'abbonamento. Ad esempio, se l'organizzazione dispone di 10 persone, è possibile chiamare e inviare messaggi istantanei reciprocamente utilizzando Team senza alcuna configurazione speciale. Per ulteriori informazioni, vedere [Introduzione a Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-quick-start).

Per le organizzazioni di grandi dimensioni o per le distribuzioni ibride di Skype for business, locali o ibridi, vedere [How to roll out Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/how-to-roll-out-teams).
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Pianificare l'integrazione con Active Directory o altro software

- **Si vuole eseguire l'integrazione con Active Directory locale?** È possibile integrare Active Directory locale con Office 365 usando Azure Active Directory Connect. Per le istruzioni, vedere [Configurare la sincronizzazione della directory in Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).
  
- **Si vuole integrare Office 365 con software di terze parti?** Se è necessario integrare Office 365 con altri software nell'organizzazione, è consigliabile prendere in considerazione l' [assunzione di un partner](https://go.microsoft.com/fwlink/?linkid=391089) per facilitare la distribuzione.
  
## <a name="do-you-want-someone-to-help-you-set-up-office-365"></a>Serve aiuto per configurare Office 365?

- **Se si hanno meno di 50 dipendenti:**

  - **Chiedi aiuto e ti chiameremo**. Dopo aver acquistato Office 365, è possibile accedere all'interfaccia di amministrazione (non è necessario eseguire il programma di installazione per ottenerlo). Nella parte inferiore dell'interfaccia di amministrazione, selezionare **serve assistenza?** Descrivi il tuo problema e ti chiameremo. 
  - **Chiamare il [supporto di Office 365 for business](../contact-support-for-business-products.md) con le proprie domande**. Microsoft è sempre pronta a offrire supporto. 
  - **Valutare se affidarsi a un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089)**. Se il tempo è poco o i requisiti sono complessi, ad esempio se è necessario spostare migliaia di file nello spazio di archiviazione cloud di Office 365 o integrare altro software, un partner qualificato può offrire un valido aiuto. 

- **Se si hanno più di 50 dipendenti**, è disponibile il [FastTrack Onboarding Center](https://go.microsoft.com/fwlink/?LinkId=517115) per offrire assistenza con la distribuzione. 
