---
title: Crittografia in Microsoft Dynamics 365
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
description: Informazioni su come Microsoft usa la tecnologia di crittografia per proteggere i dati dei clienti in Microsoft Dynamics 365 mentre è in attesa in un database Microsoft e in transito.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bd349890fc7fc1ae7f1f7eaf07f90c22423637cf
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44031413"
---
# <a name="encryption-in-microsoft-dynamics-365"></a>Crittografia in Microsoft Dynamics 365

Microsoft usa la tecnologia di crittografia per proteggere i dati dei clienti in Dynamics 365 mentre è in attesa in un database Microsoft e mentre è in transito tra i dispositivi degli utenti e i datacenter. Le connessioni stabilite tra i clienti e i datacenter Microsoft sono crittografate e tutti gli endpoint pubblici sono protetti tramite TLS standard del settore. TLS stabilisce in modo efficace una connessione da browser a server con sicurezza avanzata per garantire la riservatezza e l'integrità dei dati tra desktop e datacenter. Dopo l'attivazione, la crittografia dei dati non può essere disattivata. Per ulteriori informazioni, vedere [Crittografia dei dati a livello di campo.](https://msdn.microsoft.com/library/dn481562.aspx)

Dynamics 365 usa la crittografia standard Microsoft SQL Server a livello di cella per un set di attributi di entità predefiniti che contengono informazioni riservate, ad esempio nomi utente e password di posta elettronica. Questa funzionalità consente alle organizzazioni di soddisfare i requisiti di conformità associati a FIPS 140-2. La crittografia dei dati a livello di campo è particolarmente importante negli scenari che sfruttano il router di posta elettronica [Microsoft Dynamics CRM,](https://technet.microsoft.com/library/hh699800.aspx)che deve archiviare nomi utente e password per consentire l'integrazione tra un'istanza di Dynamics 365 e un servizio di posta elettronica. 

Tutte le istanze di Dynamics 365 usano [Microsoft SQL Server Transparent Data Encryption](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption?view=sql-server-2017) (TDE) per eseguire la crittografia in tempo reale dei dati quando vengono scritti su disco (in stato di inaltere). TDE crittografa SQL Server, Azure SQL Database e i file di dati di Azure SQL data warehouse. Per impostazione predefinita, Microsoft archivia e gestisce le chiavi di crittografia del database per le istanze di Dynamics 365. Le chiavi usate da Dynamics 365 for Financials sono generate dall'API di protezione dei dati di .NET Framework. 

La funzionalità di gestione delle chiavi nell'area di amministrazione di Dynamics 365 offre agli amministratori la possibilità di gestire autonomamente le chiavi di crittografia del database associate alle istanze di Dynamics 365. Le chiavi di crittografia del database auto-gestite sono disponibili solo nell'aggiornamento di gennaio 2017 per Microsoft Dynamics 365 e potrebbero non essere rese disponibili per le versioni successive. Per ulteriori informazioni, vedere [Gestire le chiavi di crittografia per l'istanza di Dynamics 365 (online).](https://docs.microsoft.com/dynamics365/customer-engagement/admin/manage-encryption-keys-instance) La funzionalità di gestione delle chiavi supporta sia i file delle chiavi di crittografia PFX che BYOK, ad esempio quelli archiviati in un HSM. Per ulteriori informazioni sulla generazione e il trasferimento di una chiave protetta tramite HSM tramite Internet, vedere Come generare e trasferire chiavi protette con HSM per [Azure Key Vault.](https://docs.microsoft.com/azure/key-vault/key-vault-hsm-protected-keys) 

Per usare l'opzione carica chiave di crittografia, è necessaria sia la chiave di crittografia pubblica che la chiave di crittografia privata.

La funzionalità di gestione delle chiavi consente di uscire dalla gestione delle chiavi di crittografia utilizzando Azure Key Vault per archiviare in modo sicuro le chiavi di crittografia. Azure Key Vault consente di proteggere le chiavi crittografiche e i segreti usati dalle applicazioni e dai servizi cloud. La funzionalità di gestione delle chiavi non richiede una sottoscrizione di Azure Key Vault e per la maggior parte delle situazioni non è necessario accedere alle chiavi di crittografia usate per Dynamics 365 all'interno dell'insieme di credenziali.
