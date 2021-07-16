---
title: Crittografia del servizio con Customer Key
ms.author: krowley
author: kccross
manager: laurawi
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
description: In questo articolo verranno informazioni sul funzionamento della crittografia del servizio con customer key in Microsoft 365.
ms.openlocfilehash: 9a8558a0cf36f2040614ca3ffb61e7ba9936d40f
ms.sourcegitcommit: 84e70051bb61b1171cebfbabe500b4904dfac04f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2021
ms.locfileid: "53463962"
---
# <a name="service-encryption-with-customer-key"></a>Crittografia del servizio con Customer Key

Microsoft 365 fornisce la crittografia di base a livello di volume abilitata tramite BitLocker e Distributed Key Manager (DKM). Microsoft 365 offre un ulteriore livello di crittografia per il contenuto. Questo contenuto include i dati Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business e Microsoft Teams.

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>Modalità di collaborazione tra crittografia del servizio, BitLocker e Chiave cliente

I dati vengono sempre crittografati a riposo nel servizio Microsoft 365 con BitLocker e DKM. Per ulteriori informazioni, vedere [How Exchange Online secures your email secrets](exchange-online-secures-email-secrets.md). Customer Key offre una protezione aggiuntiva dalla visualizzazione dei dati da parte di sistemi o personale non autorizzati e integra la crittografia del disco BitLocker nei data center Microsoft. La crittografia del servizio non ha lo scopo di impedire al personale Microsoft di accedere ai dati. Customer Key consente invece di soddisfare gli obblighi normativi o di conformità per il controllo delle chiavi radice. I servizi di Microsoft 365 vengono esplicitamente autorizzato a utilizzare le chiavi di crittografia per fornire servizi cloud a valore aggiunto, ad esempio eDiscovery, antimalware, protezione da posta indesiderata, indicizzazione della ricerca e così via.

Customer Key è basato sulla crittografia del servizio e consente di fornire e controllare le chiavi di crittografia. Microsoft 365 quindi usa queste chiavi per crittografare i dati in stato di inaltere, come descritto nelle Condizioni per i [Servizi online (OST).](https://www.microsoft.com/licensing/product-licensing/products.aspx) Customer Key ti aiuta a rispettare gli obblighi di conformità perché controlli le chiavi di crittografia Microsoft 365 per crittografare e decrittografare i dati.
  
Customer Key migliora la capacità dell'organizzazione di soddisfare le esigenze dei requisiti di conformità che specificano accordi chiave con il provider di servizi cloud. Con Customer Key, fornisci e controlla le chiavi di crittografia radice per il tuo Microsoft 365 dati in pausa a livello di applicazione. Di conseguenza, si esercita il controllo sulle chiavi dell'organizzazione.

## <a name="customer-key-with-hybrid-deployments"></a>Customer Key con distribuzioni ibride

Customer Key crittografa solo i dati in pausa nel cloud. Customer Key non funziona per proteggere le cassette postali e i file locali. Puoi crittografare i dati locali usando un altro metodo, ad esempio BitLocker.

## <a name="about-data-encryption-policies"></a>Informazioni sui criteri di crittografia dei dati

Un criterio di crittografia dei dati definisce la gerarchia di crittografia. Questa gerarchia viene utilizzata dal servizio per crittografare i dati utilizzando ognuna delle chiavi gestite e la chiave di disponibilità protetta da Microsoft. È possibile creare criteri di decrittografazione utilizzando i cmdlet di PowerShell e quindi assegnarli per crittografare i dati dell'applicazione. Esistono tre tipi di dep supportati da Microsoft 365 Customer Key, ogni tipo di criterio utilizza cmdlet diversi e fornisce copertura per un tipo diverso di dati. I criteri di dep che è possibile definire includono:

**Protezione esecuzione programmi per più Microsoft 365 di lavoro** Questi DEP crittografano i dati in più carichi di lavoro M365 per tutti gli utenti all'interno del tenant. Questi carichi di lavoro includono:

- Teams chat (chat 1:1, chat di gruppo, chat di riunione e conversazioni di canale)
- Teams multimediali (immagini, frammenti di codice, messaggi video, messaggi audio, immagini wiki)
- Teams registrazioni di chiamate e riunioni archiviate in Teams archiviazione
- Teams chat
- Teams suggerimenti di chat da Cortana
- Teams di stato
- Informazioni sull'utente e sul segnale Exchange Online
- Exchange Online cassette postali che non sono già crittografate dai DEP delle cassette postali
- Microsoft Information Protection:

  - Dati edM (Exact Data Match), inclusi schemi di file di dati, pacchetti di regole e salt utilizzati per eseguire l'hashing dei dati sensibili. Per EDM e Microsoft Teams, protezione esecuzione programmi multi-carico di lavoro crittografa i nuovi dati dal momento in cui si assegna la protezione esecuzione programmi al tenant. Ad Exchange Online, Customer Key crittografa tutti i dati esistenti e nuovi.

  - Configurazione delle etichette per le etichette di riservatezza

I DEP multi-carico di lavoro non crittografano i tipi di dati seguenti. Al contrario, Microsoft 365 altri tipi di crittografia per proteggere questi dati.

- SharePoint e OneDrive for Business dati.
- Microsoft Teams file e alcune registrazioni Teams chiamate e riunioni salvate in OneDrive for Business e SharePoint Online vengono crittografate tramite protezione esecuzione programmi SharePoint Online.
- Altri Microsoft 365 carichi di lavoro, ad esempio Yammer e Planner, attualmente non supportati da Customer Key.
- Teams Dati degli eventi live.

È possibile creare più criteri di protezione esecuzione per tenant, ma assegnare solo una protezione esecuzione programmi alla volta. Quando si assegna Protezione esecuzione programmi, la crittografia inizia automaticamente, ma richiede del tempo a seconda delle dimensioni del tenant.

**DEP per Exchange Online cassette postali** I criteri dep delle cassette postali forniscono un controllo più preciso sulle singole cassette postali all'interno Exchange Online. Utilizzare i DEP delle cassette postali per crittografare i dati archiviati in cassette postali EXO di diversi tipi, ad esempio UserMailbox, MailUser, Group, PublicFolder e Shared mailboxes. È possibile avere fino a 50 DEP attivi per tenant e assegnarli a singole cassette postali. È possibile assegnare una protezione esecuzione programmi a più cassette postali.

Per impostazione predefinita, le cassette postali vengono crittografate utilizzando le chiavi gestite da Microsoft. Quando si assegna una protezione esecuzione programmi chiave cliente a una cassetta postale:

- Se la cassetta postale viene crittografata utilizzando protezione esecuzione programmi con più carichi di lavoro, il servizio esegue il wrapping della cassetta postale utilizzando la nuova protezione esecuzione programmi della cassetta postale, purché un utente o un'operazione di sistema accedono ai dati della cassetta postale.

- Se la cassetta postale è già crittografata utilizzando chiavi gestite da Microsoft, il servizio esegue il wrapping della cassetta postale utilizzando la nuova protezione esecuzione programmi della cassetta postale, purché un utente o un'operazione di sistema accedono ai dati della cassetta postale.

- Se la cassetta postale non è ancora crittografata utilizzando la crittografia predefinita, il servizio contrassegna la cassetta postale per uno spostamento. La crittografia avviene al termine dello spostamento. Gli spostamenti delle cassette postali vengono regolati in base alle priorità impostate per tutti i Microsoft 365. Per ulteriori informazioni, vedere [Move requests in the Microsoft 365 service](/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service). Se le cassette postali non vengono crittografate entro il tempo specificato, contattare Microsoft.

Successivamente, è possibile aggiornare La funzionalità Protezione esecuzione programmi o assegnare una protezione esecuzione programmi diversa alla cassetta postale, come descritto in [Manage Customer Key for Office 365](customer-key-manage.md). A ogni cassetta postale devono essere assegnate licenze appropriate per l'assegnazione di Protezione esecuzione programmi. Per ulteriori informazioni sulle licenze, vedere [Before you set up Customer Key.](customer-key-set-up.md#before-you-set-up-customer-key)

I criteri dep possono essere assegnati a una cassetta postale condivisa, a una cassetta postale di cartelle pubbliche e Microsoft 365 di gruppo per i tenant che soddisfano i requisiti di licenza per le cassette postali degli utenti. Non sono necessarie licenze separate per le cassette postali non specifiche dell'utente per assegnare Protezione esecuzione programmi del codice cliente.

Per i CRITERI chiave del cliente assegnati a singole cassette postali, è possibile richiedere a Microsoft di eliminare specifici DEP quando si esce dal servizio. Per informazioni sul processo di eliminazione dei dati e sulla revoca delle chiavi, vedere Revocare le chiavi e avviare il processo del percorso di eliminazione [dei dati.](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)

Quando si revoca l'accesso alle chiavi durante l'uscita dal servizio, la chiave di disponibilità viene eliminata, con conseguente eliminazione crittografica dei dati. L'eliminazione crittografica riduce il rischio di gestione dei dati, che è importante per soddisfare sia gli obblighi di sicurezza che di conformità.

**Protezione esecuzione programmi per SharePoint Online e OneDrive for Business** Questa protezione esecuzione programmi viene utilizzata per crittografare il contenuto archiviato in SpO e OneDrive for Business, inclusi Microsoft Teams file archiviati in SPO. Se si usa la funzionalità multi-geo, è possibile creare una protezione esecuzione programmi per ogni area geografica per l'organizzazione. Se non si usa la funzionalità multi-geo, è possibile creare solo una funzionalità Protezione esecuzione programmi per tenant. Fare riferimento ai dettagli in [Set up Customer Key](customer-key-set-up.md).

### <a name="encryption-ciphers-used-by-customer-key"></a>Crittografia utilizzata dalla chiave del cliente

Customer Key usa varie crittografie di crittografia per crittografare le chiavi, come illustrato nelle figure seguenti.

La gerarchia delle chiavi utilizzata per i criteri di decrittografazione che crittografa i dati per più carichi di lavoro Microsoft 365 è simile alla gerarchia utilizzata per i criteri di decrittografazione per singole cassette postali Exchange Online chiave. L'unica differenza è che la chiave della cassetta postale viene sostituita con la chiave del carico di Microsoft 365 corrispondente.

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Crittografia utilizzata per crittografare le chiavi per Exchange Online e Skype for Business

![Crittografie di crittografia per Exchange Online chiave cliente](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Crittografia utilizzata per crittografare le chiavi per SharePoint online, OneDrive for Business e Teams file

![Crittografie di crittografia per SharePoint cliente online](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Articoli correlati

- [Configurare il codice "Customer Key"](customer-key-set-up.md)

- [Gestire il codice Cliente](customer-key-manage.md)

- [Implementare o distribuire una Customer Key o una chiave di disponibilità](customer-key-availability-key-roll.md)

- [Informazioni sulla chiave di disponibilità](customer-key-availability-key-understand.md)

- [Customer Lockbox](customer-lockbox-requests.md)

- [Crittografia del servizio](office-365-service-encryption.md)