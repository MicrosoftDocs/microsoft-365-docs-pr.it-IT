---
title: Crittografia del servizio con la chiave del cliente
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
description: Con il codice "Customer Key", è possibile controllare le chiavi di crittografia dell'organizzazione e quindi configurare Microsoft 365 per utilizzarle per crittografare i dati a riposo nei data center di Microsoft.
ms.openlocfilehash: 701dc306a81e12db7dd1062d2a840621b710abd3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635592"
---
# <a name="service-encryption-with-customer-key"></a>Crittografia del servizio con la chiave del cliente

Microsoft 365 fornisce la crittografia di base, a livello di volume abilitata tramite BitLocker e Distributed Key Manager (DKM). Microsoft 365 offre un ulteriore livello di crittografia a livello di applicazione per il contenuto. Questo contenuto include i dati di Exchange Online, Skype for business, SharePoint Online, OneDrive for business e i file dei team. Questo livello aggiunto di crittografia è denominato crittografia del servizio.

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>Come funzionano i servizi di crittografia, BitLocker e Customer Key insieme

La crittografia dei servizi garantisce che il contenuto a riposo sia crittografato a livello di applicazione. I **dati sono sempre crittografati nel servizio Microsoft 365 con BitLocker e DKM**. Per ulteriori informazioni, vedere "informazioni sulla sicurezza, la privacy e la conformità" e su [come Exchange Online protegge i segreti della posta elettronica](exchange-online-secures-email-secrets.md). La chiave del cliente fornisce ulteriore protezione contro la visualizzazione dei dati da parte di sistemi o personale non autorizzato e complementa la crittografia del disco BitLocker nei datacenter Microsoft. La crittografia del servizio non è destinata a impedire ai dipendenti di Microsoft di accedere ai dati dei clienti. Lo scopo principale è quello di assistere i clienti nell'adempimento degli obblighi normativi o di conformità per il controllo delle chiavi principali. I clienti autorizzano esplicitamente i servizi di O365 a utilizzare le chiavi di crittografia per fornire servizi cloud a valore aggiunto, ad esempio eDiscovery, anti-malware, protezione dalla posta indesiderata, indicizzazione della ricerca e così via.

La chiave del cliente è basata sulla crittografia del servizio e consente di fornire e controllare le chiavi di crittografia. Microsoft 365 utilizza quindi queste chiavi per crittografare i dati a riposo, come descritto nelle [condizioni dei servizi online (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx). La chiave Customer consente di soddisfare gli obblighi di conformità perché si controllano le chiavi di crittografia utilizzate da Microsoft 365 per crittografare e decrittografare i dati.
  
La chiave Customer migliora la capacità dell'organizzazione di soddisfare le esigenze dei requisiti di conformità che specificano le soluzioni chiave con il provider di servizi cloud. Con la chiave del cliente, è possibile fornire e controllare le chiavi di crittografia radice per i dati di Microsoft 365 a livello di applicazione. Di conseguenza, si esercita il controllo sulle chiavi dell'organizzazione. Se si decide di uscire dal servizio, si revoca l'accesso alle chiavi radice dell'organizzazione. Per tutti i servizi Microsoft 365, la revoca dell'accesso ai tasti è il primo passaggio sul percorso verso l'eliminazione dei dati. Revocando l'accesso alle chiavi, i dati sono illeggibili per il servizio.

## <a name="customer-key-encrypts-data-at-rest-in-office-365"></a>La chiave del cliente crittografa i dati a riposo in Office 365

Utilizzando i tasti forniti, la chiave del cliente esegue la crittografia:

- File di SharePoint Online, OneDrive for business e teams.
- File caricati in OneDrive for business.
- Contenuto della cassetta postale di Exchange Online, inclusi il contenuto del corpo di posta elettronica, le voci del calendario e il contenuto all'interno degli allegati
- Conversazioni di testo da Skype for business.

Attualmente non offriamo il controllo del cliente delle chiavi di crittografia per Skype meeting broadcast e Skype meeting content uploads. Questo contenuto viene invece crittografato insieme a tutti gli altri contenuti di Office 365.

### <a name="customer-key-with-hybrid-deployments"></a>Chiave del cliente con distribuzioni ibride

La chiave del cliente Crittografa solo i dati a riposo nel cloud. La chiave Customer non è in funzione per proteggere le cassette postali e i file locali. È possibile crittografare i dati locali utilizzando un altro metodo, ad esempio BitLocker.

## <a name="about-the-data-encryption-policy-dep"></a>Informazioni sui criteri di crittografia dei dati (DEP, Data Encryption Policy)

Un criterio di crittografia dei dati definisce la gerarchia di crittografia per crittografare i dati utilizzando ognuno dei tasti forniti e la chiave di disponibilità protetta da Microsoft. È possibile creare DEPs utilizzando i cmdlet di PowerShell, che sono diversi per ogni servizio, e assegnare tali DEPs per crittografare i dati dell'applicazione. Ad esempio:

**Exchange Online e Skype for business** È possibile creare fino a 50 DEPs per tenant. È possibile associare DEPs alle chiavi dei clienti in Azure Key Vault e quindi assegnare DEPs alle singole cassette postali. Quando si assegna una funzionalità di protezione esecuzione programmi a una cassetta postale:

- la cassetta postale viene contrassegnata per lo spostamento di una cassetta postale. In base alle priorità di Microsoft 365 come descritto di seguito, [spostare le richieste nel servizio microsoft 365](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service).

- La crittografia viene eseguita quando la cassetta postale viene spostata. Consenti 72 ore per crittografare la cassetta postale con il nuovo DEP. Se le cassette postali non vengono crittografate dopo aver atteso 72 ore dal momento in cui è stata assegnata la funzionalità DEP, contattare Microsoft.

In un secondo momento, è possibile aggiornare la funzionalità DEP o assegnare un altro DEP alla cassetta postale, come descritto in [Manage Customer Key per Office 365](customer-key-manage.md). Ogni cassetta postale deve disporre di licenze appropriate per assegnare una DEP. Per ulteriori informazioni sulle licenze, vedere [prima di impostare la chiave del cliente](customer-key-set-up.md#before-you-set-up-customer-key).

**File di SharePoint Online, OneDrive for business e teams** Se si utilizza la funzionalità multi-Geo, è possibile creare fino a una DEP per Geo per la propria organizzazione. È possibile utilizzare diverse chiavi dei clienti per ogni Geo. Se non si utilizza la caratteristica multi-Geo, è possibile creare una sola funzionalità di protezione per tenant. Quando si assegna la funzionalità DEP, la crittografia inizia automaticamente ma può richiedere del tempo per il completamento. Fare riferimento ai dettagli in [set up Customer Key](customer-key-set-up.md).

## <a name="leaving-the-service"></a>Uscita dal servizio

La chiave del cliente aiuta a soddisfare gli obblighi di conformità, consentendo di revocare le chiavi quando si lascia il servizio Microsoft 365. Quando si revocano le chiavi come parte dell'uscita dal servizio, il tasto di disponibilità viene eliminato con l'eliminazione della crittografia dei dati. L'eliminazione di crittografia consente di ridurre il rischio di rimanenza di dati che è importante per soddisfare gli obblighi di sicurezza e conformità. Per informazioni sul processo di eliminazione dei dati e sulla revoca delle chiavi, vedere [Revoke Your Keys e Start the data Purge Path Process](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).

### <a name="encryption-ciphers-used-by-customer-key"></a>Crittografia cifratura utilizzata dalla chiave del cliente

La chiave Customer utilizza una vasta gamma di crittografia per crittografare le chiavi, come illustrato nelle figure seguenti.

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Crittografia cifratura utilizzata per crittografare le chiavi per Exchange Online e Skype for business

![Crittografia cifratura per la chiave del cliente di Exchange Online](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Crittografie di crittografia utilizzate per crittografare le chiavi per i file di SharePoint Online, OneDrive for business e teams

![Crittografia cifratura per la chiave del cliente di SharePoint Online](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Articoli correlati

- [Configurare la chiave del cliente](customer-key-set-up.md)

- [Gestione della chiave del cliente](customer-key-manage.md)

- [Implementare o distribuire una Customer Key o una chiave di disponibilità](customer-key-availability-key-roll.md)

- [Informazioni sulla chiave di disponibilità](customer-key-availability-key-understand.md)

- [Customer Lockbox](customer-lockbox-requests.md)

- [Crittografia del servizio](office-365-service-encryption.md)
