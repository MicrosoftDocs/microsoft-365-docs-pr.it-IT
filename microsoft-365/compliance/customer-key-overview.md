---
title: Crittografia del servizio con Customer Key
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
ms.custom: seo-marvel-apr2020
description: In questo articolo viene illustrato come funziona la crittografia del servizio con la chiave del cliente in Microsoft 365.
ms.openlocfilehash: efb2ba9c2532973a096c509b57639544fc2ddbe5
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058489"
---
# <a name="service-encryption-with-customer-key"></a>Crittografia del servizio con Customer Key

Microsoft 365 fornisce la crittografia di base a livello di volume abilitata tramite BitLocker e Distributed Key Manager (DKM). Microsoft 365 offre un ulteriore livello di crittografia a livello di applicazione per il contenuto. Questo contenuto include i dati dei file di Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business e Teams. Questo ulteriore livello di crittografia è denominato crittografia del servizio.

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>Modalità di collaborazione tra crittografia del servizio, BitLocker e Customer Key

La crittografia del servizio garantisce che il contenuto in stato attivo sia crittografato a livello di servizio. **I dati vengono sempre crittografati a riposo nel servizio Microsoft 365 con BitLocker e DKM.** Per ulteriori informazioni, vedere "Informazioni su sicurezza, privacy e conformità" e come Exchange Online protegge [i segreti della posta elettronica.](exchange-online-secures-email-secrets.md) Customer Key offre una protezione aggiuntiva dalla visualizzazione dei dati da parte di sistemi o personale non autorizzati e integra la crittografia del disco BitLocker nei datacenter Microsoft. La crittografia del servizio non ha lo scopo di impedire al personale Microsoft di accedere ai dati dei clienti. Lo scopo principale è quello di assistere i clienti nell'adempimento degli obblighi normativi o di conformità per il controllo delle chiavi radice. I clienti autorizzano esplicitamente i servizi di O365 a utilizzare le chiavi di crittografia per fornire servizi cloud a valore aggiunto, come eDiscovery, antimalware, protezione da posta indesiderata, indicizzazione della ricerca e così via.

Customer Key è basato sulla crittografia del servizio e consente di fornire e controllare le chiavi di crittografia. Microsoft 365 usa quindi queste chiavi per crittografare i dati in stato di inquieto, come descritto nelle Condizioni dei Servizi [Online (OST).](https://www.microsoft.com/licensing/product-licensing/products.aspx) Customer Key consente di rispettare gli obblighi di conformità perché si controllano le chiavi di crittografia utilizzate da Microsoft 365 per crittografare e decrittografare i dati.
  
Customer Key migliora la capacità dell'organizzazione di soddisfare le esigenze dei requisiti di conformità che specificano le disposizioni chiave con il provider di servizi cloud. Con Customer Key, è possibile fornire e controllare le chiavi di crittografia radice per i dati di Microsoft 365 a livello di applicazione. Di conseguenza, si esercita il controllo sulle chiavi dell'organizzazione. Se si decide di uscire dal servizio, si revoca l'accesso alle chiavi radice dell'organizzazione. Per tutti i servizi di Microsoft 365, revocare l'accesso alle chiavi è il primo passaggio del percorso verso l'eliminazione dei dati. Revocando l'accesso alle chiavi, i dati sono illeggibili per il servizio.

## <a name="customer-key-encrypts-data-at-rest-in-office-365"></a>Customer Key crittografa i dati in pausa in Office 365

Usando le chiavi fornite, Customer Key crittografa:

- File di SharePoint Online, OneDrive for Business e Teams.
- File caricati in OneDrive for Business.
- Contenuto della cassetta postale di Exchange Online, inclusi il contenuto del corpo del messaggio di posta elettronica, le voci del calendario e il contenuto all'interno degli allegati di posta elettronica.
- Conversazioni di testo da Skype for Business.

Attualmente non è disponibile il controllo dei clienti delle chiavi di crittografia per i caricamenti di contenuti di Skype Meeting Broadcast e Skype Meeting. Al contrario, questo contenuto viene crittografato insieme a tutti gli altri contenuti in Office 365.

### <a name="customer-key-with-hybrid-deployments"></a>Customer Key con distribuzioni ibride

Customer Key crittografa solo i dati in stato di inquieto nel cloud. Customer Key non funziona per proteggere le cassette postali e i file locali. Puoi crittografare i dati locali usando un altro metodo, ad esempio BitLocker.

## <a name="about-the-data-encryption-policy-dep"></a>Informazioni sui criteri di crittografia dei dati

Un criterio di crittografia dei dati definisce la gerarchia di crittografia per crittografare i dati utilizzando ognuna delle chiavi fornite e la chiave di disponibilità protetta da Microsoft. I criteri di decrittografazione vengono creati utilizzando i cmdlet di PowerShell, che sono diversi per ogni servizio, e si assegnano tali criteri per crittografare i dati dell'applicazione. Ad esempio:

**Exchange Online e Skype for Business** È possibile creare fino a 50 DEP per tenant. I criteri dep vengono associati alle chiavi dei clienti nell'insieme di credenziali delle chiavi di Azure e quindi si assegnano i criteri di protezione dei dati alle singole cassette postali. Quando si assegna protezione esecuzione programmi a una cassetta postale:

- la cassetta postale è contrassegnata per lo spostamento di una cassetta postale. In base alle priorità in Microsoft 365, come descritto qui, spostare le richieste [nel servizio Microsoft 365.](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service)

- La crittografia avviene mentre la cassetta postale viene spostata. Consentire 72 ore per la cassetta postale per essere crittografata con la nuova protezione esecuzione programmi. Se le cassette postali non vengono crittografate dopo 72 ore dall'assegnazione di Protezione esecuzione programmi, contattare Microsoft.

Successivamente, è possibile aggiornare Protezione esecuzione programmi o assegnare un'altra protezione esecuzione programmi alla cassetta postale, come descritto in [Manage Customer Key per Office 365.](customer-key-manage.md) Ogni cassetta postale deve disporre di licenze appropriate per poter assegnare protezione esecuzione programmi. Per ulteriori informazioni sulle licenze, vedere [Prima di configurare Customer Key.](customer-key-set-up.md#before-you-set-up-customer-key)

> [!NOTE]
> Protezione esecuzione programmi può essere applicato a una cassetta postale condivisa, a una cassetta postale di cartelle pubbliche e a una cassetta postale del gruppo di Microsoft 365 per i tenant che soddisfano i requisiti di licenza per le cassette postali degli utenti, anche se alcuni di questi tipi di cassette postali non possono essere una licenza assegnata (cassetta postale delle cartelle pubbliche e cassetta postale del gruppo di Microsoft 365) o avere bisogno di una licenza per aumentare lo spazio di archiviazione (cassetta postale condivisa).

**File di SharePoint Online, OneDrive for Business e Teams** Se si usa la funzionalità multi-geo, è possibile creare fino a un dep per ogni area geografica per l'organizzazione. Puoi usare chiavi cliente diverse per ogni area geografica. Se non si usa la funzionalità multi-geografico, è possibile creare solo una protezione esecuzione programmi per tenant. Quando si assegna Protezione esecuzione programmi, la crittografia viene avviata automaticamente, ma può richiedere del tempo. Fare riferimento ai dettagli in [Set up Customer Key.](customer-key-set-up.md)

## <a name="leaving-the-service"></a>Uscita dal servizio

Customer Key consente di soddisfare gli obblighi di conformità consentendo di revocare le chiavi quando si lascia il servizio Microsoft 365. Quando si revocano le chiavi durante l'uscita dal servizio, la chiave di disponibilità viene eliminata con conseguente eliminazione crittografica dei dati. L'eliminazione crittografica riduce il rischio di gestione dei dati, che è importante per soddisfare gli obblighi di sicurezza e conformità. Per informazioni sul processo di eliminazione dei dati e sulla revoca delle chiavi, vedere Revocare le chiavi e avviare il processo del percorso di eliminazione [dei dati.](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)

### <a name="encryption-ciphers-used-by-customer-key"></a>Crittografia utilizzata da Customer Key

Customer Key usa una vasta gamma di crittografie di crittografia per crittografare le chiavi, come illustrato nelle figure seguenti.

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Crittografia utilizzata per crittografare le chiavi per Exchange Online e Skype for Business

![Crittografia crittografiche per Exchange Online Customer Key](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Crittografia utilizzata per crittografare le chiavi per i file di SharePoint Online, OneDrive for Business e Teams

![Crittografia delle crittografie per la chiave del cliente di SharePoint Online](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Articoli correlati

- [Configurare Customer Key](customer-key-set-up.md)

- [Gestire Customer Key](customer-key-manage.md)

- [Implementare o distribuire una Customer Key o una chiave di disponibilità](customer-key-availability-key-roll.md)

- [Informazioni sulla chiave di disponibilità](customer-key-availability-key-understand.md)

- [Customer Lockbox](customer-lockbox-requests.md)

- [Crittografia del servizio](office-365-service-encryption.md)
