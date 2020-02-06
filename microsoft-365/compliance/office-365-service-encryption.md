---
title: Servizio di crittografia di Office 365
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
ms.openlocfilehash: 5b22584e677dd4815b991b4e95b5ad59feb2fbc2
ms.sourcegitcommit: 5ff1dc62e8855be155cb2de45cf4ee5a02c321fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799546"
---
# <a name="office-365-service-encryption"></a>Servizio di crittografia di Office 365

Oltre a utilizzare la crittografia a livello di volume, Exchange Online, Skype for business, SharePoint Online e OneDrive for business utilizzano anche la crittografia del servizio per crittografare i dati dei clienti. La crittografia del servizio consente di eseguire due opzioni di gestione principali:

- Microsoft gestisce tutte le chiavi di crittografia. Questa opzione è attualmente disponibile in SharePoint Online, OneDrive for business e Skype for business.

- Il cliente fornisce le chiavi radice utilizzate con la crittografia del servizio e il cliente gestisce queste chiavi utilizzando Azure Key Vault. Microsoft gestisce tutte le altre chiavi. Questa opzione è denominata Customer Key ed è attualmente disponibile per Exchange Online, SharePoint Online e OneDrive for business. (In precedenza denominato crittografia avanzata con BYOK. Vedere [miglioramento della trasparenza e del controllo per i clienti di Office 365](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) per l'annuncio originale.

La crittografia dei servizi offre molteplici vantaggi. Ad esempio, Customer Key:

- Fornisce funzionalità di gestione e protezione dei diritti al di sopra della protezione dalla crittografia avanzata.

- Include un'opzione di chiave Customer che consente ai servizi multi-tenant di fornire la gestione delle chiavi per tenant.

- Consente di separare gli amministratori del sistema operativo Windows dall'accesso ai dati dei clienti archiviati o elaborati dal sistema operativo.

- Consente di migliorare la capacità di Office 365 di soddisfare le esigenze dei clienti con requisiti di conformità relativi alla crittografia.

## <a name="customer-key"></a>Customer Key

Se si utilizza il codice "Customer Key", è possibile generare le proprie chiavi di crittografia utilizzando un modulo di servizio hardware (HSM) locale o un Vault Key di Azure (AKV). Indipendentemente dal modo in cui viene generata la chiave, è possibile utilizzare AKV per controllare e gestire le chiavi di crittografia utilizzate da Office 365. Dopo aver memorizzato i tasti in AKV, è possibile utilizzarli come radice di uno dei portachiavi che crittografa i dati o i file delle cassette postali.

Un altro vantaggio della chiave del cliente è il controllo che si ha sulla capacità di elaborazione dei dati da parte di Microsoft. Se si desidera rimuovere i dati da Office 365, ad esempio se si desidera terminare il servizio con Microsoft o rimuovere una parte dei dati archiviati nel cloud, è possibile farlo e utilizzare la chiave del cliente come controllo tecnico. In questo modo, nessuno, incluso Microsoft, può accedere ai dati o elaborarli. La chiave del cliente è inoltre e complementare all'archivio protetto dei clienti che si utilizza per controllare l'accesso ai dati da parte del personale Microsoft.

Per informazioni su come configurare Customer Key per Office 365 per Exchange Online, Skype for business, SharePoint Online, inclusi i siti del team e OneDrive for business, vedere gli articoli seguenti:

- [Crittografia del servizio con la chiave del cliente in Office 365](customer-key-overview.md)

- [Configurare la chiave cliente per Office 365](customer-key-set-up.md)

- [Gestire la chiave del cliente per Office 365](customer-key-manage.md)

- [Eseguire il rollforward o la rotazione di una chiave del cliente o di una chiave di disponibilità](customer-key-availability-key-roll.md)

- [Comprendere il codice di disponibilità](customer-key-availability-key-understand.md)
 