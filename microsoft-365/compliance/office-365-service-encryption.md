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
ms.openlocfilehash: 89f3fbcc90cee0ad822156014ee4ac9e04fe3371
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058549"
---
# <a name="service-encryption"></a>Crittografia del servizio

Oltre a usare la crittografia a livello di volume, Exchange Online, Microsoft Teams, SharePoint Online e OneDrive for Business usano anche la crittografia del servizio per crittografare i dati dei clienti. La crittografia del servizio consente due opzioni di gestione delle chiavi:

## <a name="microsoft-managed-keys"></a>Chiavi gestite da Microsoft
Microsoft gestisce tutte le chiavi crittografiche, incluse le chiavi radice per la crittografia del servizio. Questa opzione è attualmente abilitata per impostazione predefinita per Exchange Online, SharePoint Online, OneDrive for Business. Le chiavi gestite da Microsoft forniscono la crittografia del servizio predefinita, a meno che tu non decida di eseguire l'onboard usando Customer Key. Se, in un secondo momento, decidi di smettere di usare Customer Key senza seguire il percorso di eliminazione dei dati, i dati rimangono crittografati usando le chiavi gestite da Microsoft. I dati vengono sempre crittografati almeno a questo livello predefinito. 

## <a name="customer-key"></a>Customer Key
Le chiavi radice utilizzate con la crittografia del servizio vengono fornite e gestite tramite Azure Key Vault. Microsoft gestisce tutte le altre chiavi. Questa opzione è denominata Customer Key ed è attualmente disponibile per Exchange Online, SharePoint Online e OneDrive for Business. In precedenza noto come crittografia avanzata con BYOK. Per l'annuncio originale, vedere Migliorare la trasparenza e il controllo per i clienti di [Office 365.](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)

La crittografia del servizio offre diversi vantaggi:

- Fornisce un ulteriore livello di protezione su BitLocker.

- Separa gli amministratori del sistema operativo Windows dall'accesso ai dati dell'applicazione archiviati o elaborati dal sistema operativo.

- Include un'opzione Customer Key che consente ai servizi multi-tenant di fornire la gestione delle chiavi per tenant.

- Migliora la capacità di Microsoft 365 di soddisfare le esigenze dei clienti che hanno requisiti di conformità specifici relativi alla crittografia.

Usando Customer Key, puoi generare chiavi crittografiche usando un modulo del servizio hardware (HSM) locale o Azure Key Vault (AKV). Indipendentemente da come viene generata la chiave, si usa AKV per controllare e gestire le chiavi di crittografia usate da Office 365. Una volta archiviate in AKV, le chiavi possono essere utilizzate come radice di uno dei keychains che crittografa i dati o i file della cassetta postale.

Un altro vantaggio di Customer Key è il controllo che hai sulla capacità di Microsoft di elaborare i dati. Se si desidera rimuovere i dati da Office 365, ad esempio se si desidera interrompere il servizio con Microsoft o rimuovere una parte dei dati archiviati nel cloud, è possibile farlo e usare Customer Key come controllo tecnico. La rimozione dei dati garantisce che nessuno, incluso Microsoft, possa accedere o elaborare i dati. Customer Key è in aggiunta e complementare a Customer Lockbox che usi per controllare l'accesso ai dati da parte del personale Microsoft.

Per informazioni su come configurare Customer Key per Microsoft 365 per Exchange Online, Microsoft Teams, SharePoint Online, inclusi i siti del team e OneDrive for Business, vedere questi articoli:

- [Crittografia del servizio con Customer Key](customer-key-overview.md)

- [Configurare Customer Key](customer-key-set-up.md)

- [Gestire Customer Key](customer-key-manage.md)

- [Roll o rotate a customer key or an availability key](customer-key-availability-key-roll.md)

- [Informazioni sulla chiave di disponibilità](customer-key-availability-key-understand.md)
