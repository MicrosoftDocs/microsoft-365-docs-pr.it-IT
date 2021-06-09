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
description: Informazioni sulla crittografia disponibile in Azure, ad esempio Crittografia dischi di Azure
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee4eb2bec814d7e06d418518bb9be272f1bd5aaa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926254"
---
# <a name="encryption-in-azure"></a>Crittografia in Azure

Le misure di sicurezza tecnologiche in Azure, come le comunicazioni crittografate e i processi operativi, consentono di proteggere i dati. Hai anche la flessibilità di implementare funzionalità di crittografia aggiuntive e gestire le tue chiavi crittografiche. Indipendentemente dalla configurazione del cliente, Microsoft applica la crittografia per proteggere i dati dei clienti in Azure. Microsoft consente inoltre di controllare i dati ospitati in Azure tramite una serie di tecnologie avanzate per crittografare, controllare e gestire le chiavi crittografiche e controllare e controllare l'accesso ai dati. Inoltre, Archiviazione di Azure offre un set completo di funzionalità di sicurezza che insieme consentono agli sviluppatori di creare applicazioni protette.

Azure offre molti meccanismi per proteggere i dati mentre si spostano da una posizione all'altra. Microsoft usa TLS per proteggere i dati in viaggio tra i servizi cloud e i clienti. I data center di Microsoft negoziano una connessione TLS con i sistemi client che si connettono ai servizi di Azure. Perfect Forward Secrecy (PFS) protegge le connessioni tra i sistemi client dei clienti e i servizi cloud di Microsoft tramite chiavi univoche. Le connessioni utilizzano anche lunghezze delle chiavi di crittografia a 2.048 bit basate su RSA. Questa combinazione rende difficile l'intercettazione e l'accesso ai dati in transito.

I dati possono essere protetti in transito tra un'applicazione e Azure utilizzando la crittografia sul [lato client,](/azure/storage/storage-client-side-encryption)HTTPS o SMB 3.0. È possibile abilitare la crittografia per il traffico tra le macchine virtuali e gli utenti. Con Reti virtuali di [Azure,](https://azure.microsoft.com/services/virtual-network/)è possibile utilizzare il protocollo IPsec standard del settore per crittografare il traffico tra il gateway VPN aziendale e Azure, nonché tra le macchine virtuali che si trovano nella rete virtuale.

Per i dati in pausa, Azure offre molte opzioni di crittografia, ad esempio il supporto per AES-256, offrendo la flessibilità di scegliere lo scenario di archiviazione dei dati più adatto alle proprie esigenze. I dati possono essere crittografati automaticamente quando vengono scritti in Archiviazione di Azure utilizzando Archiviazione [Service Encryption](/azure/storage/storage-service-encryption)e i dischi del sistema operativo e dei dati utilizzati dalle macchine virtuali possono essere crittografati. Per ulteriori informazioni, vedere [Consigli sulla sicurezza per Windows virtuali in Azure](/azure/security/azure-security-disk-encryption). Inoltre, l'accesso delegato agli oggetti dati in Archiviazione di Azure può essere concesso tramite [firme di accesso condiviso.](/azure/storage/storage-dotnet-shared-access-signature-part-1) Azure fornisce anche la crittografia per i dati in stato di [Transparent Data Encryption per database SQL di Azure e Data Warehouse.](/sql/relational-databases/security/encryption/transparent-data-encryption-azure-sql)

Per ulteriori informazioni sulla crittografia in Azure, vedere [Panoramica della crittografia di Azure](/azure/security/security-azure-encryption-overview) e Crittografia dati di Azure in [pausa.](/azure/security/azure-security-encryption-atrest)

## <a name="azure-disk-encryption"></a>Crittografia dischi di Azure

Crittografia dischi di Azure consente di crittografare i dischi delle macchine virtuali Windows e Linux Infrastructure as a Service (IaaS). Crittografia dischi di Azure sfrutta la funzionalità BitLocker di Windows e la funzionalità DM-Crypt di Linux per fornire la crittografia a livello di volume per il sistema operativo e i dischi dati. Inoltre, garantisce che tutti i dati nei dischi delle macchine virtuali siano crittografati in pausa nell'archiviazione di Azure. Crittografia dischi di Azure è integrato con Azure Key Vault per aiutarti a controllare, gestire e controllare l'uso delle chiavi di crittografia e dei segreti.

Per ulteriori informazioni, vedere [Consigli sulla sicurezza per Windows virtuali in Azure](/azure/virtual-machines/windows/security-recommendations).

## <a name="azure-storage-service-encryption"></a>Archiviazione di Azure Crittografia del servizio

Con [Archiviazione di Azure servizio](/azure/storage/storage-service-encryption)di crittografia , Archiviazione di Azure crittografa automaticamente i dati prima di conservarlo in modo permanente e decrittografa i dati prima del recupero. I processi di crittografia, decrittografia e gestione delle chiavi sono completamente trasparenti per gli utenti. Archiviazione di Azure La crittografia del servizio può essere usata per [l'Archiviazione BLOB di Azure](https://azure.microsoft.com/services/storage/blobs/) e [i file di Azure.](https://azure.microsoft.com/services/storage/files/) Puoi anche usare le chiavi di crittografia gestite da Microsoft con Archiviazione di Azure service encryption oppure puoi usare le tue chiavi di crittografia. Per informazioni sull'uso delle proprie chiavi, vedere Archiviazione [service encryption using customer managed keys in Azure Key Vault.](/azure/storage/common/storage-service-encryption-customer-managed-keys) Per informazioni sull'utilizzo delle chiavi gestite da Microsoft, [vedere Archiviazione service encryption for Data at Rest.](/azure/storage/storage-service-encryption) Inoltre, è possibile automatizzare l'utilizzo della crittografia. Ad esempio, è possibile abilitare o disabilitare Archiviazione Service Encryption in un account di archiviazione usando l'API REST del provider di risorse [di Archiviazione di Azure,](/rest/api/storagerp/)la libreria client del provider di risorse [Archiviazione per .NET,](/dotnet/api/overview/azure/storage) [Azure PowerShell](/powershell/azureps-cmdlets-docs)o l'interfaccia di gestione delle risorse di [Azure.](/azure/storage/storage-azure-cli)

Alcuni Microsoft 365 usano Azure per l'archiviazione dei dati. Ad esempio, SharePoint Online e OneDrive for Business archiviare i dati nell'archiviazione BLOB di Azure e Microsoft Teams archivia i dati per il servizio chat in tabelle, BLOB e code. Inoltre, la funzionalità Compliance Manager nel Centro conformità di Microsoft 365 archivia i dati immessi dal cliente archiviati in forma crittografata in [Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest), un database paaS (Platform as a Service), distribuito a livello globale e multi-modello. Archiviazione di Azure La crittografia del servizio crittografa i dati archiviati nell'archiviazione BLOB di Azure e nelle tabelle e Crittografia dischi di Azure crittografa i dati nelle code, nonché i dischi delle macchine virtuali Windows e IaaS per fornire la crittografia del volume per il sistema operativo e il disco dati. La soluzione garantisce che tutti i dati nei dischi della macchina virtuale siano crittografati in pausa nell'archiviazione di Azure. [La crittografia in locale in Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest) viene implementata utilizzando diverse tecnologie di sicurezza, tra cui sistemi di archiviazione delle chiavi sicure, reti crittografate e API crittografiche.

## <a name="azure-key-vault"></a>Azure Key Vault

La gestione delle chiavi protette non è solo il fulcro delle procedure consigliate per la crittografia. è inoltre essenziale per proteggere i dati nel cloud. [Azure Key Vault](/azure/key-vault/key-vault-whatis) consente di crittografare chiavi e piccoli segreti come le password che usano chiavi archiviate nei moduli di sicurezza hardware (HMS). Azure Key Vault è la soluzione consigliata da Microsoft per la gestione e il controllo dell'accesso alle chiavi di crittografia usate dai servizi cloud. Le autorizzazioni per i tasti di scelta possono essere assegnate ai servizi o agli utenti con Azure Active Directory account. Azure Key Vault solleva le organizzazioni dalla necessità di configurare, applicare patch e gestire gli HMS e il software di gestione delle chiavi. Con Azure Key Vault, Microsoft non vede mai le chiavi e le applicazioni non hanno accesso diretto ad essi; mantenere il controllo. È inoltre possibile importare o generare chiavi in HSM. Le organizzazioni che dispongono di una sottoscrizione che include Azure Information Protection possono configurare il tenant di Azure Information Protection per usare una chiave gestita dal cliente [Bring Your Own Key](/information-protection/plan-design/byok-price-restrictions) (BYOK) e registrarne l'utilizzo. [](/information-protection/deploy-use/log-analyze-usage)