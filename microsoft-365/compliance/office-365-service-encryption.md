---
title: Crittografia del servizio
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 10/3/2019
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Riepilogo: informazioni sulla resilienza dei dati in Microsoft Office 365.'
ms.openlocfilehash: fbd2672986046a4f6d25c47b011eaef0a87d90e1
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777051"
---
# <a name="service-encryption"></a>Crittografia del servizio

Oltre a utilizzare la crittografia a livello di volume, Exchange Online, Skype for business, SharePoint Online e OneDrive for business utilizzano anche la crittografia del servizio per crittografare i dati dei clienti. La crittografia del servizio consente di eseguire due opzioni di gestione principali:

## <a name="microsoft-managed-keys"></a>Chiavi gestite da Microsoft
Microsoft gestisce tutte le chiavi di crittografia, incluse le chiavi radice per la crittografia del servizio. Questa opzione è attualmente abilitata per impostazione predefinita per Exchange Online, SharePoint Online, OneDrive for business. Le chiavi gestite da Microsoft forniscono la crittografia del servizio predefinita, a meno che non si decida di onboard usando la chiave del cliente. Se, in un secondo momento, si decide di non utilizzare la chiave del cliente senza seguire il percorso di eliminazione dei dati, i dati rimarranno crittografati utilizzando le chiavi gestite da Microsoft. I dati vengono sempre crittografati a questo livello predefinito almeno. 

## <a name="customer-key"></a>Customer Key
È possibile specificare le chiavi radice utilizzate con la crittografia del servizio e gestire queste chiavi utilizzando Azure Key Vault. Microsoft gestisce tutte le altre chiavi. Questa opzione è denominata Customer Key ed è attualmente disponibile per Exchange Online, SharePoint Online e OneDrive for business. (In precedenza denominato crittografia avanzata con BYOK. Vedere [miglioramento della trasparenza e del controllo per i clienti di Office 365](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) per l'annuncio originale.

La crittografia dei servizi offre molteplici vantaggi:

- Fornisce un ulteriore livello di protezione sulla parte superiore di BitLocker.

- Consente di separare gli amministratori del sistema operativo Windows dall'accesso ai dati dell'applicazione archiviati o elaborati dal sistema operativo.

- Include un'opzione di chiave Customer che consente ai servizi multi-tenant di fornire la gestione delle chiavi per tenant.

- Consente di migliorare la capacità di Microsoft 365 di soddisfare le esigenze dei clienti che hanno requisiti di conformità specifici per quanto riguarda la crittografia.

Se si utilizza il codice "Customer Key", è possibile generare le proprie chiavi di crittografia utilizzando un modulo di servizio hardware (HSM) locale o un Vault Key di Azure (AKV). Indipendentemente dal modo in cui viene generata la chiave, è possibile utilizzare AKV per controllare e gestire le chiavi di crittografia utilizzate da Office 365. Dopo aver memorizzato i tasti in AKV, è possibile utilizzarli come radice di uno dei portachiavi che crittografa i dati o i file delle cassette postali.

Un altro vantaggio della chiave del cliente è il controllo che si ha sulla capacità di elaborazione dei dati da parte di Microsoft. Se si desidera rimuovere i dati da Office 365, ad esempio se si desidera terminare il servizio con Microsoft o rimuovere una parte dei dati archiviati nel cloud, è possibile farlo e utilizzare la chiave del cliente come controllo tecnico. La rimozione dei dati garantisce che nessuno, incluso Microsoft, possa accedere ai dati o elaborarli. La chiave del cliente è inoltre e complementare all'archivio protetto dei clienti che si utilizza per controllare l'accesso ai dati da parte del personale Microsoft.

Per informazioni su come configurare la chiave del cliente per Microsoft 365 per Exchange Online, Skype for business, SharePoint Online, inclusi i siti del team e OneDrive for business, vedere gli articoli seguenti:

- [Crittografia del servizio con Customer Key](customer-key-overview.md)

- [Configurare la chiave del cliente](customer-key-set-up.md)

- [Gestione della chiave del cliente](customer-key-manage.md)

- [Eseguire il rollforward o la rotazione di una chiave del cliente o di una chiave di disponibilità](customer-key-availability-key-roll.md)

- [Comprendere il codice di disponibilità](customer-key-availability-key-understand.md)

