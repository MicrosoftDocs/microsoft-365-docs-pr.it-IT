---
title: Trasferire manualmente i dati tra due account
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
description: Informazioni su come trasferire manualmente i dati tra due account di Microsoft 365 quando è stato modificato il piano o il nome della società oppure sono stati combinati più abbonamenti in uno.
ms.openlocfilehash: 6e64872ad7e145b63eb71d89ea2d69e5d8697eb6
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780170"
---
# <a name="transfer-data-manually-between-two-accounts"></a>Trasferire manualmente i dati tra due account

Prepararsi a rimboccarsi le maniche e bloccare un pezzo di tempo nel calendario: il trasferimento di dati tra due account di Microsoft 365 è un processo manuale, complicato e che richiede molto tempo. Non si tratta di un processo automatizzato o supportato. Questo articolo illustra la procedura.
  
> [!CAUTION]
> Durante il processo verrà utilizzato il tempo di inattività in cui la posta elettronica, Skype for business e un sito Web pubblico ospitato su Microsoft 365 non funzioneranno. Gli utenti riceveranno nuovi nomi utente e nuove password e dovranno reimpostare Outlook.

**Trasferire i dati manualmente seguendo le istruzioni riportate in questo argomento solo nei casi seguenti:**
  
- È necessario passare a un piano in una famiglia di servizi diversa.

- Il nome dell'azienda è cambiato e si è deciso di creare un nuovo abbonamento ed eseguire la migrazione dei dati, perché si vogliono usare nomi di dominio iniziale diversi.

- È necessario combinare più abbonamenti in un unico nuovo abbonamento.

> [!IMPORTANT]
> Se è necessario [cambiare piano di abbonamento](../../commerce/subscriptions/switch-to-a-different-plan.md) e si può usare la procedura guidata Cambia piano oppure se occorre passare a un nuovo piano di abbonamento nella stessa famiglia, anche se la procedura guidata Cambia piano non funziona, non è necessario trasferire manualmente i dati e non si verificano tempi di inattività.

|**Attività**|**Passaggi**|
|:-----|:-----|
|Acquistare il piano a cui si vuole passare.  <br/> |When you sign up, you specify the company name to use in the initial domain names:  *yourcompany*  .onmicrosoft.com,  *yourcompany*  -public.sharepoint.com, and  *yourcompany*  .sharepoint.com. You need to use a different  *yourcompany*  name than you did for any existing subscriptions.  <br/> > [!NOTE]>  In genere per il rilascio da parte dei sistemi Microsoft dei nomi di dominio iniziali che usano  *nomeazienda*  dopo l'annullamento di un abbonamento occorre un minimo di diversi mesi. Anche se si prevede di salvare tutti i dati dal vecchio abbonamento a Microsoft 365 e annullare tale sottoscrizione, il vecchio valore di *yourcompany* non è immediatamente disponibile per l'utilizzo in un nuovo abbonamento.           |
|Rimuovere il dominio personalizzato dalla vecchia sottoscrizione Microsoft 365.  <br/> | Completare i [passaggi necessari prima della rimozione di un dominio](remove-a-domain.md) per rimuovere il nome di dominio dagli indirizzi di posta elettronica degli utenti e rimuovere i record DNS per la posta elettronica e Lync per il dominio personalizzato. Se si ospita il sito Web pubblico in Microsoft 365, è necessario rimuovere anche il record CNAME che punta a esso.  <br/> > [!IMPORTANT]>  After you remove the MX record that routes email to this custom domain, email will stop working until you have added the domain to your new account, set up the new MX record, and set up your users. When you remove the DNS records for Lync, Lync will stop working. And after you remove the CNAME record that points to your public website, it will not be available.           [Remove the domain](remove-a-domain.md) .  <br/> |
|Configurare il dominio personalizzato per il nuovo abbonamento e configurare gli utenti.  <br/> | Configurare il nuovo abbonamento, inclusa la creazione dei record DNS necessari per il dominio personalizzato.  <br/>  Creare gli utenti e i relativi indirizzi di posta elettronica nel dominio personalizzato  <br/> |
|Trasferire dati dal vecchio al nuovo abbonamento.  <br/> | Accedere a entrambi gli account in finestre del browser separate:  <br/>  Right-click the Internet Explorer icon, and open two InPrivate browser windows. You can use different credentials in the two windows to sign in on both accounts.  <br/> [Trasferire le impostazioni amministrative tra gli abbonamenti](#email) <br/> [Trasferire i dati e la struttura del sito del team](#transfer-team-site-structure-and-data) <br/> [Trasferire un sito Web pubblico tra abbonamenti](#transfer-a-public-website-between-subscriptions) <br/> [Trasferire le impostazioni amministrative tra gli abbonamenti](#email) <br/> |
|Annullare l'abbonamento per il piano con cui si esegue la chiamata del supporto tecnico Microsoft per Microsoft 365.  <br/> | Verificare che il nuovo abbonamento funzioni e che tutti i dati siano stati trasferiti.  <br/>  [Contattare il supporto](../contact-support-for-business-products.md) tecnico per annullare il vecchio abbonamento.  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>Trasferire le impostazioni amministrative tra gli abbonamenti

Passare alle pagine seguenti in ogni account e configurare il nuovo account in base alle impostazioni dell'account precedente.
  
Se si trasferiscono dati da Microsoft 365 a Microsoft 365 medie imprese o Microsoft 365 Enterprise, le pagine di amministrazione sono strutturate in modo diverso. Guardare un [video: Introduzione a Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365/admin/)e accedere alle seguenti posizioni per esaminare le impostazioni di amministratore.
  
Per Microsoft 365 Enterprise e Microsoft 365 medie imprese:
  
|**Posizione**|**Scopo**|
|:-----|:-----|
|**Amministratore** \> **Microsoft 365** \> **Impostazioni del servizio** <br/> |Selezionare ogni scheda per le impostazioni per la posta, i siti, Lync, il software utente, le password, la community, la gestione dei diritti e la telefonia mobile.  <br/> |
|**Amministratore** \> **Exchange** <br/> | Impostazioni di Exchange Online  <br/> |
|**Amministratore** \> **SharePoint** <br/> | Impostazioni di SharePoint Online  <br/> |
|**Amministratore** \> **Skype for business** <br/> |Altre impostazioni di Skype for business  <br/> |

Per Microsoft 365 Small Business
  
|**Posizione**|**Scopo**|
|:-----|:-----|
|**Amministratore** \> **Gestisci impostazioni a livello di organizzazione** <br/> |Impostazioni amministrative  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a>Trasferire un sito Web pubblico tra abbonamenti

Se si dispone di un sito Web pubblico ospitato in Microsoft 365, è necessario salvarlo e ricrearlo nel nuovo abbonamento.
  
> [!NOTE]
> If your public website is hosted at a DNS hosting provider, no changes are required. It will not be affected by your transition.
  
Per salvare una raccolta documenti o il contenuto di un elenco da un ambiente SharePoint Online in una condivisione file o in un computer locale, vedere [Informazioni sulla migrazione manuale del contenuto di SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=402910).
  
> [!NOTE]
> L'app di migrazione del sito Web pubblico non può trasferire i dati in un abbonamento diverso.
  
## <a name="transfer-team-site-structure-and-data"></a>Trasferire i dati e la struttura del sito del team

Esistono vari modi per salvare o trasferire i dati del sito del team:
  
- Si può salvare il vecchio sito come modello e importare il modello nel nuovo sito.

- Per trasferire documenti, prima di tutto, ricreare manualmente la gerarchia nel nuovo sito. Fatto questo, sarà possibile aprire contemporaneamente entrambi i siti del team di SharePoint, aprire entrambe le raccolte documenti con Esplora risorse e copiare e incollare i documenti. Vedere [Video: Copiare o spostare file delle raccolte tramite Apri con Esplora risorse](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790).

- Per trasferire dati di elenco, salvare un [modello di elenco](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393) e usare il modello salvato per ricreare l'elenco nel nuovo sito.

- Per salvare una raccolta documenti o un elenco di contenuto da un ambiente di SharePoint Online (OneDrive for business o siti del team) in condivisioni di file o in un computer locale, vedere [informazioni sulla migrazione manuale del contenuto di SharePoint Online](https://support.microsoft.com/kb/2783484).

## <a name="transfer-users-data-between-subscriptions"></a>Trasferire i dati degli utenti tra gli abbonamenti

### <a name="email"></a>Posta elettronica:

Ask users to [move their email, contacts, tasks, and calendar information](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc) after you set up your new subscription. They can get to their old email by using their initial user name, such as sue@contoso.onmicrosoft.com.
  
### <a name="onedrive-for-business-data"></a>Dati di OneDrive for business:

Chiedere agli utenti di copiare/sincronizzare [il contenuto di OneDrive for business nel computer](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd)e quindi aggiungerlo al nuovo abbonamento.
