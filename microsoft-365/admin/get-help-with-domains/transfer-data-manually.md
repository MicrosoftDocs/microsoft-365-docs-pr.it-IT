---
title: Trasferire manualmente i dati tra due account
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: Informazioni su come trasferire manualmente i dati tra due account di Microsoft 365 quando è stato modificato il piano o il nome della società o sono state combinate più sottoscrizioni in uno.
ms.openlocfilehash: 9916da50f4589f949d35466ca6aa8f1d79cc40ea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915507"
---
# <a name="transfer-data-manually-between-two-accounts"></a>Trasferire manualmente i dati tra due account

Prepararsi a rimboccarsi le mani e bloccare un blocco di tempo nel calendario: il trasferimento dei dati tra due account di Microsoft 365 è un processo manuale, complicato e dispendioso in termini di tempo. Non si tratta di un processo automatizzato o supportato. Questo articolo illustra la procedura.
  
> [!CAUTION]
> Durante il processo si verificano tempi di inazione in cui la posta elettronica, Skype for Business e un sito Web pubblico ospitato in Microsoft 365 non funzionano. Gli utenti riceveranno nuovi nomi utente e nuove password e dovranno reimpostare Outlook.

**Trasferire i dati manualmente seguendo le istruzioni riportate in questo argomento solo nei casi seguenti:**
  
- È necessario passare a un piano in una famiglia di servizi diversa.

- Il nome dell'azienda è cambiato e si è deciso di creare un nuovo abbonamento ed eseguire la migrazione dei dati, perché si vogliono usare nomi di dominio iniziale diversi.

- È necessario combinare più abbonamenti in un unico nuovo abbonamento.

> [!IMPORTANT]
> Se è necessario [cambiare piano di abbonamento](../../commerce/subscriptions/switch-to-a-different-plan.md) e si può usare la procedura guidata Cambia piano oppure se occorre passare a un nuovo piano di abbonamento nella stessa famiglia, anche se la procedura guidata Cambia piano non funziona, non è necessario trasferire manualmente i dati e non si verificano tempi di inattività.

|**Attività**|**Passaggi**|
|:-----|:-----|
|Acquistare il piano a cui si vuole passare.  <br/> |Al momento dell'iscrizione si specifica il nome azienda da usare nei nomi di dominio iniziali:  *nomeazienda*  .onmicrosoft.com,  *nomeazienda*  -public.sharepoint.com e  *nomeazienda*  .sharepoint.com. È necessario specificare un  *nomeazienda*  diverso da quello usato per gli abbonamenti esistenti.  <br/> > [!NOTE]>  In genere per il rilascio da parte dei sistemi Microsoft dei nomi di dominio iniziali che usano  *nomeazienda*  dopo l'annullamento di un abbonamento occorre un minimo di diversi mesi. Anche se si prevede di salvare tutti i dati dal vecchio abbonamento a Microsoft 365 e annullare tale sottoscrizione, il vecchio valore  *della*  società non è immediatamente disponibile per l'utilizzo in una nuova sottoscrizione.           |
|Rimuovere il dominio personalizzato dal vecchio abbonamento a Microsoft 365.  <br/> | Completare i [passaggi necessari prima della rimozione di un dominio](remove-a-domain.md) per rimuovere il nome di dominio dagli indirizzi di posta elettronica degli utenti e rimuovere i record DNS per la posta elettronica e Lync per il dominio personalizzato. Se si ospita il sito Web pubblico in Microsoft 365, sarà necessario rimuovere anche il record CNAME che punta a esso.  <br/> > [!IMPORTANT]>  Dopo aver rimosso il record MX che instrada la posta elettronica verso il dominio personalizzato, la posta elettronica smetterà di funzionare finché non si aggiunge il dominio al nuovo account, si configura il nuovo record MX e si configurano gli utenti. Quando si rimuovono i record DNS per Lync, Lync smetterà di funzionare. Inoltre, dopo aver rimosso il record CNAME che punta al sito Web pubblico, questo non sarà disponibile.           [Rimuovere il dominio](remove-a-domain.md) .  <br/> |
|Configurare il dominio personalizzato per il nuovo abbonamento e configurare gli utenti.  <br/> | Configurare il nuovo abbonamento, inclusa la creazione dei record DNS necessari per il dominio personalizzato.  <br/>  Creare gli utenti e i relativi indirizzi di posta elettronica nel dominio personalizzato  <br/> |
|Trasferire dati dal vecchio al nuovo abbonamento.  <br/> | Accedere a entrambi gli account in finestre del browser separate:  <br/>  Fai clic con il pulsante destro del mouse sull'icona del browser e apri due finestre private del browser. È possibile usare credenziali diverse nelle due finestre per accedere a entrambi gli account.  <br/> [Trasferire le impostazioni amministrative tra gli abbonamenti](#email) <br/> [Trasferire i dati e la struttura del sito del team](#transfer-team-site-structure-and-data) <br/> [Trasferire un sito Web pubblico tra abbonamenti](#transfer-a-public-website-between-subscriptions) <br/> [Trasferire le impostazioni amministrative tra gli abbonamenti](#email) <br/> |
|Annulla l'abbonamento per il piano con cui hai finito chiamando il supporto Microsoft per Microsoft 365.  <br/> | Verificare che il nuovo abbonamento funzioni e che tutti i dati siano stati trasferiti.  <br/>  [Contattare il supporto tecnico](../contact-support-for-business-products.md) per annullare l'abbonamento precedente.  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>Trasferire le impostazioni amministrative tra gli abbonamenti

Passare alle pagine seguenti in ogni account e configurare il nuovo account in base alle impostazioni dell'account precedente.
  
Se si trasferiscono dati da Microsoft 365 a Microsoft 365 Midsize Business o Microsoft 365 Enterprise, le pagine di amministrazione sono strutturate in modo diverso. Guarda un [video: Introduzione a Microsoft 365 Enterprise](../index.yml)e passa alle posizioni seguenti per esaminare le impostazioni di amministrazione.
  
Per Microsoft 365 Enterprise e Microsoft 365 Midsize Business:
  
|**Posizione**|**Scopo**|
|:-----|:-----|
|**Amministratore** \> **Microsoft 365** \> **Impostazioni servizio** <br/> |Selezionare ogni scheda per le impostazioni per posta, siti, Lync, software utente, password, community, rights management e dispositivi mobili.  <br/> |
|**Amministratore** \> **Exchange** <br/> | Impostazioni di Exchange Online  <br/> |
|**Amministratore** \> **SharePoint** <br/> | Impostazioni di SharePoint Online  <br/> |
|**Amministratore** \> **Skype for Business** <br/> |Impostazioni aggiuntive di Skype for Business  <br/> |

Per Microsoft 365 Small Business
  
|**Posizione**|**Scopo**|
|:-----|:-----|
|**Amministratore** \> **Gestisci impostazioni a livello di organizzazione** <br/> |Impostazioni amministrative  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a>Trasferire un sito Web pubblico tra abbonamenti

Se si dispone di un sito Web pubblico ospitato in Microsoft 365, è necessario salvarlo e crearlo di nuovo nel nuovo abbonamento.
  
> [!NOTE]
> Se il sito Web pubblico è ospitato presso un provider di hosting DNS, non sono necessarie modifiche. Non sarà interessato dalla transizione.
  
Per salvare una raccolta documenti o il contenuto di un elenco da un ambiente SharePoint Online in una condivisione file o in un computer locale, vedere [Informazioni sulla migrazione manuale del contenuto di SharePoint Online](/sharepoint/troubleshoot/migration-tool/content-manual-migration).
  
> [!NOTE]
> L'app di migrazione del sito Web pubblico non può trasferire i dati in un abbonamento diverso.
  
## <a name="transfer-team-site-structure-and-data"></a>Trasferire i dati e la struttura del sito del team

Esistono vari modi per salvare o trasferire i dati del sito del team:
  
- Si può salvare il vecchio sito come modello e importare il modello nel nuovo sito.

- Per trasferire i documenti, ricreare manualmente la gerarchia nel nuovo sito. Fatto questo, sarà possibile aprire contemporaneamente entrambi i siti del team di SharePoint, aprire entrambe le raccolte documenti con Esplora risorse e copiare e incollare i documenti. Vedere [Video: Copiare o spostare file delle raccolte tramite Apri con Esplora risorse](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790).

- Per trasferire dati di elenco, salvare un [modello di elenco](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393) e usare il modello salvato per ricreare l'elenco nel nuovo sito.

- Per salvare una raccolta documenti o il contenuto di un elenco da un ambiente SharePoint Online (OneDrive for Business o siti del team) in condivisioni file o in un computer locale, vedere Informazioni sulla migrazione manuale del contenuto di [SharePoint Online.](https://support.microsoft.com/kb/2783484)

## <a name="transfer-users-data-between-subscriptions"></a>Trasferire i dati degli utenti tra gli abbonamenti

### <a name="email"></a>Posta elettronica:

Chiedere agli utenti di [spostare posta elettronica, contatti, attività e informazioni del calendario](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc) dopo la configurazione del nuovo abbonamento. Possono accedere ai vecchi messaggi di posta elettronica usando il nome utente iniziale, ad esempio giorgia@contoso.onmicrosoft.com.
  
### <a name="onedrive-for-business-data"></a>Dati di OneDrive For Business:

Chiedere agli utenti di copiare/sincronizzare il contenuto di [OneDrive for Business](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd)nel computer e quindi aggiungerlo di nuovo al nuovo abbonamento.

### <a name="onenote"></a>OneNote 

Chiedere agli utenti [di eseguire il backup di OneNote](https://support.microsoft.com/office/back-up-notes-f58b34b0-611d-435e-87fa-7942a1767af4?ui=en-us&rs=en-us&ad=us) e di ripristinare le note da un [backup](https://support.microsoft.com/en-us/office/restore-notes-from-a-backup-5daf9cb0-6769-4998-a5de-f044fdd0d831?ui=en-us&rs=en-us&ad=us) alle nuove sottoscrizioni.