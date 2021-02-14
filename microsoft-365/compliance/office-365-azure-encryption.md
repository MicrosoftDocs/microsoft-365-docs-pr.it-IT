---
title: Crittografia in Azure
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
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: Informazioni sulla crittografia disponibile in Azure, ad esempio Crittografia disco di Azure
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a90f66ed7288d84785becbb4cd25c803ccf4fdbe
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198329"
---
# <a name="encryption-in-azure"></a>Crittografia in Azure

Le misure di sicurezza tecnologiche in Azure, ad esempio le comunicazioni crittografate e i processi operativi, consentono di proteggere i dati. Hai anche la flessibilità di implementare funzionalità di crittografia aggiuntive e gestire le tue chiavi crittografiche. Indipendentemente dalla configurazione del cliente, Microsoft applica la crittografia per proteggere i dati dei clienti in Azure. Microsoft consente inoltre di controllare i dati ospitati in Azure tramite una gamma di tecnologie avanzate per crittografare, controllare e gestire le chiavi crittografiche, oltre a controllare e controllare l'accesso ai dati. Archiviazione di Azure offre inoltre un set completo di funzionalità di sicurezza che insieme consentono agli sviluppatori di creare applicazioni sicure.

Azure offre molti meccanismi per proteggere i dati mentre si spostano da una posizione all'altra. Microsoft usa TLS per proteggere i dati in viaggio tra i servizi cloud e i clienti. I data center Microsoft negoziano una connessione TLS con i sistemi client che si connettono ai servizi di Azure. Perfect Forward Secrecy (PFS) protegge le connessioni tra i sistemi client dei clienti e i servizi cloud di Microsoft tramite chiavi univoche. Le connessioni utilizzano inoltre lunghezze delle chiavi di crittografia a 2.048 bit basate su RSA. Questa combinazione rende difficile l'intercettazione e l'accesso ai dati in transito.

I dati possono essere protetti in transito tra un'applicazione e Azure usando la crittografia sul lato [client,](https://docs.microsoft.com/azure/storage/storage-client-side-encryption)HTTPS o SMB 3.0. È possibile abilitare la crittografia per il traffico tra le macchine virtuali e gli utenti. Con le reti virtuali di [Azure,](https://azure.microsoft.com/services/virtual-network/)è possibile utilizzare il protocollo IPsec standard del settore per crittografare il traffico tra il gateway VPN aziendale e Azure, nonché tra le macchine virtuali presenti nella rete virtuale.

Per i dati in pausa, Azure offre molte opzioni di crittografia, ad esempio il supporto per AES-256, offrendo la flessibilità di scegliere lo scenario di archiviazione dei dati più adatto alle proprie esigenze. I dati possono essere crittografati automaticamente quando vengono scritti in Archiviazione di Azure tramite crittografia del servizio di archiviazione [e](https://docs.microsoft.com/azure/storage/storage-service-encryption)i dischi del sistema operativo e dei dati usati dalle macchine virtuali possono essere crittografati. Per ulteriori informazioni, vedere [Consigli sulla sicurezza per le macchine virtuali Windows in Azure.](https://docs.microsoft.com/azure/security/azure-security-disk-encryption) Inoltre, l'accesso delegato agli oggetti dati in Archiviazione di Azure può essere concesso tramite [firme di accesso condiviso.](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-1) Azure fornisce anche la crittografia per i dati in stato di inquieto usando [Transparent Data Encryption per Azure SQL Database e Data Warehouse.](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption-azure-sql)

Per altre informazioni sulla crittografia in Azure, vedere [Panoramica della crittografia di Azure](https://docs.microsoft.com/azure/security/security-azure-encryption-overview) e Crittografia dei dati di Azure in [rest.](https://docs.microsoft.com/azure/security/azure-security-encryption-atrest)

## <a name="azure-disk-encryption"></a>Crittografia disco di Azure

Crittografia disco di Azure consente di crittografare i dischi delle macchine virtuali Windows e Linux Infrastructure as a Service (IaaS). Crittografia disco di Azure sfrutta la funzionalità BitLocker di Windows e la funzionalità DM-Crypt di Linux per fornire la crittografia a livello di volume per il sistema operativo e i dischi dati. Garantisce inoltre che tutti i dati nei dischi della macchina virtuale siano crittografati in stato di conservazione nell'archiviazione di Azure. Crittografia disco di Azure è integrata con Azure Key Vault per consentire di controllare, gestire e controllare l'uso delle chiavi di crittografia e dei segreti.

Per ulteriori informazioni, vedere [Consigli sulla sicurezza per le macchine virtuali Windows in Azure.](https://docs.microsoft.com/azure/virtual-machines/windows/security-recommendations)

## <a name="azure-storage-service-encryption"></a>Crittografia del servizio di archiviazione di Azure

Con [crittografia del servizio di archiviazione di Azure,](https://docs.microsoft.com/azure/storage/storage-service-encryption)Archiviazione di Azure crittografa automaticamente i dati prima di persistere nell'archiviazione e decrittografa i dati prima del recupero. I processi di crittografia, decrittografia e gestione delle chiavi sono del tutto trasparenti per gli utenti. La crittografia del servizio di archiviazione di Azure può essere usata per [l'archiviazione BLOB di Azure](https://azure.microsoft.com/services/storage/blobs/) e [per i file di Azure.](https://azure.microsoft.com/services/storage/files/) È anche possibile usare le chiavi di crittografia gestite da Microsoft con crittografia del servizio di archiviazione di Azure oppure è possibile usare le proprie chiavi di crittografia. Per informazioni sull'uso delle proprie chiavi, vedere Crittografia del servizio di archiviazione tramite chiavi [gestite dal cliente in Azure Key Vault.](https://docs.microsoft.com/azure/storage/common/storage-service-encryption-customer-managed-keys) Per informazioni sull'uso delle chiavi gestite da Microsoft, vedere Crittografia del servizio di archiviazione [per i dati in pausa.](https://docs.microsoft.com/azure/storage/storage-service-encryption) Inoltre, è possibile automatizzare l'uso della crittografia. Ad esempio, è possibile abilitare o disabilitare la crittografia del servizio di archiviazione a livello di programmazione in un account di archiviazione usando l'API REST del provider di risorse di archiviazione di [Azure,](https://msdn.microsoft.com/library/azure/mt163683.aspx)la libreria client del provider di risorse di archiviazione per [.NET,](https://msdn.microsoft.com/library/azure/mt131037.aspx) [Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs)o l'interfaccia cli di [Azure.](https://docs.microsoft.com/azure/storage/storage-azure-cli)

Alcuni servizi di Microsoft 365 usano Azure per l'archiviazione dei dati. Ad esempio, SharePoint Online e OneDrive for Business archiviano i dati nell'archiviazione BLOB di Azure e Microsoft Teams archivia i dati per il servizio chat in tabelle, BLOB e code. Inoltre, la funzionalità Compliance Manager nel Centro conformità Microsoft 365 archivia i dati immessi dal cliente, archiviati in formato crittografato in [Azure Cosmos DB,](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest)un database multi-modello distribuito a livello globale, Platform as a Service (PaaS). Crittografia servizio di archiviazione di Azure crittografa i dati archiviati nell'archiviazione BLOB di Azure e nelle tabelle, mentre Crittografia disco di Azure crittografa i dati nelle code, nonché i dischi delle macchine virtuali Windows e IaaS per fornire la crittografia del volume per il sistema operativo e il disco dati. La soluzione garantisce che tutti i dati nei dischi delle macchine virtuali siano crittografati in stato di conservazione nell'archiviazione di Azure. [La crittografia in locale in Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest) viene implementata utilizzando diverse tecnologie di sicurezza, tra cui sistemi di archiviazione a chiave sicura, reti crittografate e API crittografiche.

## <a name="azure-key-vault"></a>Azure Key Vault

La gestione sicura delle chiavi non è solo la base delle procedure consigliate per la crittografia; è inoltre essenziale per proteggere i dati nel cloud. [Azure Key Vault consente](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) di crittografare chiavi e piccoli segreti come le password che usano chiavi archiviate in moduli di sicurezza hardware (HMS). Azure Key Vault è la soluzione consigliata da Microsoft per la gestione e il controllo dell'accesso alle chiavi di crittografia usate dai servizi cloud. Le autorizzazioni per le chiavi di accesso possono essere assegnate ai servizi o agli utenti con account Azure Active Directory. Azure Key Vault allevia le organizzazioni dalla necessità di configurare, applicare patch e gestire HSM e software di gestione delle chiavi. Con Azure Key Vault, Microsoft non vede mai le chiavi e le applicazioni non hanno accesso diretto; il controllo viene mantenuto. Puoi anche importare o generare chiavi in HSM. Le organizzazioni che dispongono di una sottoscrizione che include Azure Information Protection possono configurare il tenant di Azure Information Protection per usare una chiave gestita dal cliente [Bring Your Own Key](https://docs.microsoft.com/information-protection/plan-design/byok-price-restrictions) (BYOK) e registrarne [l'utilizzo.](https://docs.microsoft.com/information-protection/deploy-use/log-analyze-usage)
