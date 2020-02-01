---
title: Crittografia di Office 365 in Microsoft Dynamics 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Riepilogo: informazioni sulla crittografia in Microsoft Dynamics 365.'
ms.openlocfilehash: 288f739182f8419cf7fbbfb6dfd7ad0a2c7838a5
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597853"
---
# <a name="office-365-encryption-in-microsoft-dynamics-365"></a>Crittografia di Office 365 in Microsoft Dynamics 365

Microsoft utilizza la tecnologia di crittografia per proteggere i dati dei clienti in Dynamics 365 mentre è in fase di riposo in un database Microsoft e durante il transito tra i dispositivi utente e i datacenter. Le connessioni stabilite tra i clienti e i centri dati Microsoft vengono crittografate e tutti gli endpoint pubblici sono protetti con TLS standard del settore. TLS stabilisce efficacemente una connessione da browser a server con protezione avanzata per garantire la riservatezza e l'integrità dei dati tra desktop e Datacenter. Dopo che la crittografia dei dati è attivata, non può essere disattivata. Per ulteriori informazioni, vedere [crittografia dei dati a livello di campo](https://msdn.microsoft.com/library/dn481562.aspx).

Dynamics 365 utilizza la crittografia a livello di cella Microsoft SQL Server standard per un set di attributi di entità predefiniti che contengono informazioni riservate, ad esempio i nomi utente e le password di posta elettronica. Questa funzionalità può consentire alle organizzazioni di soddisfare i requisiti di conformità associati a FIPS 140-2. La crittografia dei dati a livello di campo è particolarmente importante in scenari che sfruttano il [router di posta elettronica di Microsoft Dynamics CRM](https://technet.microsoft.com/library/hh699800.aspx), che deve archiviare i nomi utente e le password per consentire l'integrazione tra un'istanza di Dynamics 365 e un servizio di posta elettronica. 

Tutte le istanze di Dynamics 365 utilizzano la [crittografia (Transparent Data Encryption) di Microsoft SQL Server](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption?view=sql-server-2017) per eseguire la crittografia in tempo reale dei dati quando vengono scritti su disco (a riposo). Transcript crittografa SQL Server, database SQL di Azure e file di dati di Azure SQL data warehouse. Per impostazione predefinita, Microsoft archivia e gestisce le chiavi di crittografia del database per le istanze di Dynamics 365. Le chiavi utilizzate da Dynamics 365 per gli strumenti finanziari sono generate dall'API di protezione dei dati di .NET Framework. 

La funzionalità Gestisci tasti nell'interfaccia di amministrazione di Dynamics 365 fornisce agli amministratori la possibilità di gestire autonomamente le chiavi di crittografia del database associate alle istanze di Dynamics 365. Le chiavi di crittografia self-Managed database sono disponibili solo nell'aggiornamento di gennaio 2017 per Microsoft Dynamics 365 e potrebbero non essere rese disponibili per le versioni successive. Per ulteriori informazioni, vedere [gestire le chiavi di crittografia per l'istanza di Dynamics 365 (online)](https://docs.microsoft.com/dynamics365/customer-engagement/admin/manage-encryption-keys-instance). La funzionalità di gestione delle chiavi supporta sia i file delle chiavi di crittografia PFX che BYOK, ad esempio quelli archiviati in un HSM. Per ulteriori informazioni sulla generazione e sul trasferimento di una chiave con protezione HSM su Internet, vedere [How to generate and transfer HSM-protected Keys for Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-hsm-protected-keys). 

Per utilizzare l'opzione carica crittografia chiave, è necessaria sia la chiave di crittografia pubblica che quella privata.

La funzionalità di gestione delle chiavi estrae la complessità dalla gestione delle chiavi di crittografia tramite il Vault Key di Azure per archiviare in modo sicuro i codici di crittografia. Il Vault Key di Azure consente di salvaguardare le chiavi di crittografia e i segreti utilizzati dalle applicazioni e dai servizi cloud. La funzionalità di gestione delle chiavi non richiede l'utilizzo di una sottoscrizione a Vault Key di Azure e per la maggior parte delle situazioni non è necessario accedere alle chiavi di crittografia utilizzate per Dynamics 365 all'interno del Vault.
