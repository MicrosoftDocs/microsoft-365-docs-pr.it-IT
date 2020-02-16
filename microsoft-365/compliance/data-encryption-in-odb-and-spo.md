---
title: Crittografia dei dati in OneDrive for Business e SharePoint Online
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: Informazioni sugli elementi di base della crittografia per la sicurezza dati in OneDrive for Business e SharePoint Online.
ms.openlocfilehash: c21ec4ef6b81bcf89565fd005b9a1d2068244b20
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42076353"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a><span data-ttu-id="38afe-103">Crittografia dei dati in OneDrive for Business e SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="38afe-103">Data Encryption in OneDrive for Business and SharePoint Online</span></span>

<span data-ttu-id="38afe-104">Informazioni sugli elementi di base della crittografia per la sicurezza dati in OneDrive for Business e SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="38afe-104">Understand the basic elements of encryption for data security in OneDrive for Business and SharePoint Online.</span></span>
  
## <a name="overview"></a><span data-ttu-id="38afe-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="38afe-105">Overview</span></span>

<span data-ttu-id="38afe-p101">Office 365 è un ambiente con protezione avanzata che offre una protezione estesa in più livelli: sicurezza data center fisico, sicurezza di rete, sicurezza accessi, sicurezza applicazioni e sicurezza dati. In questo articolo viene illustrato il lato della crittografia in transito e inattiva della sicurezza dati di OneDrive for Business e SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="38afe-p101">Office 365 is a highly secure environment that offers extensive protection in multiple layers: physical data center security, network security, access security, application security, and data security. This article specifically focuses on the in-transit and at-rest encryption side of data security for OneDrive for Business and SharePoint Online.</span></span>
  
<span data-ttu-id="38afe-108">Per una descrizione dell'intera sicurezza di Office 365, vedere [white paper sulla sicurezza in office 365](https://go.microsoft.com/fwlink/p/?LinkId=270895).</span><span class="sxs-lookup"><span data-stu-id="38afe-108">For a description of Office 365 security as a whole, see [Security in Office 365 White Paper](https://go.microsoft.com/fwlink/p/?LinkId=270895).</span></span>
  
<span data-ttu-id="38afe-109">Nel seguente video è possibile vedere in che modo funziona la crittografia dei dati.</span><span class="sxs-lookup"><span data-stu-id="38afe-109">Watch how data encryption works in the following video.</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a><span data-ttu-id="38afe-110">Crittografia dei dati in transito</span><span class="sxs-lookup"><span data-stu-id="38afe-110">Encryption of data in transit</span></span>

<span data-ttu-id="38afe-111">In OneDrive for Business e SharePoint Online, esistono due scenari in cui i dati entrano ed escono dai data center.</span><span class="sxs-lookup"><span data-stu-id="38afe-111">In OneDrive for Business and SharePoint Online, there are two scenarios in which data enters and exits the datacenters.</span></span>
  
- <span data-ttu-id="38afe-p102">**Comunicazione client con il server** La comunicazione con OneDrive for Business tramite Internet utilizza connessioni SSL/TLS. Tutte le connessioni SSL vengono stabilite mediante chiavi a 2048 bit.</span><span class="sxs-lookup"><span data-stu-id="38afe-p102">**Client communication with the server** Communication to OneDrive for Business across the Internet uses SSL/TLS connections. All SSL connections are established using 2048-bit keys.</span></span>

- <span data-ttu-id="38afe-p103">**Spostamento dei dati tra data center** Il motivo principale dello spostamento di dati tra data center è la replica geografica per abilitare il ripristino di emergenza. Ad esempio, i registri transazioni di SQL Server e le differenze dell'archiviazione BLOB viaggiano lungo questa pipe. Mentre questi dati vengono già trasmessi utilizzando una rete privata, sono ulteriormente protetti mediante la migliore crittografia.</span><span class="sxs-lookup"><span data-stu-id="38afe-p103">**Data movement between datacenters** The primary reason to move data between datacenters is for geo-replication to enable disaster recovery. For instance, SQL Server transaction logs and blob storage deltas travel along this pipe. While this data is already transmitted by using a private network, it is further protected with best-in-class encryption.</span></span> 

## <a name="encryption-of-data-at-rest"></a><span data-ttu-id="38afe-117">Crittografia dei dati statici</span><span class="sxs-lookup"><span data-stu-id="38afe-117">Encryption of data at rest</span></span>

<span data-ttu-id="38afe-118">La crittografia inattiva include due componenti: Crittografia a livello di disco BitLocker e crittografia per file del contenuto cliente.</span><span class="sxs-lookup"><span data-stu-id="38afe-118">Encryption at rest includes two components: BitLocker disk-level encryption and per-file encryption of customer content.</span></span>
  
<span data-ttu-id="38afe-119">BitLocker viene distribuito per OneDrive for Business e SharePoint Online attraverso il servizio.</span><span class="sxs-lookup"><span data-stu-id="38afe-119">BitLocker is deployed for OneDrive for Business and SharePoint Online across the service.</span></span> <span data-ttu-id="38afe-120">La crittografia per file è anche in OneDrive for business e SharePoint online in Office 365 multi-tenant e nuovi ambienti dedicati che sono basati su una tecnologia multi-tenant.</span><span class="sxs-lookup"><span data-stu-id="38afe-120">Per-file encryption is also in OneDrive for Business and SharePoint Online in Office 365 multi-tenant and new dedicated environments that are built on multi-tenant technology.</span></span>
  
<span data-ttu-id="38afe-p105">Mentre BitLocker esegue la crittografia di tutti i dati su un disco, la crittografia per file è ancora più approfondita includendo un'unica chiave di crittografia per ogni file. Inoltre, ogni aggiornamento di ogni file viene crittografata mediante la relativa chiave di crittografia. Prima di essere archiviate, le chiavi del contenuto crittografato vengono archiviate in una posizione fisica separata dal contenuto. Ogni passaggio di questo tipo di crittografia utilizza Advanced Encryption Standard (AES) con chiavi a 256 bit ed è conforme ai criteri FIPS (Federal Information Processing Standard) 140-2. Il contenuto crittografato viene distribuito in una serie di contenitori in tutto il data center ed ogni contenitore ha credenziali univoche. Queste credenziali vengono archiviate in una posizione fisica separata dal contenuto o dalle chiavi del contenuto.</span><span class="sxs-lookup"><span data-stu-id="38afe-p105">While BitLocker encrypts all data on a disk, per-file encryption goes even further by including a unique encryption key for each file. Further, every update to every file is encrypted using its own encryption key. Before they're stored, the keys to the encrypted content are stored in a physically separate location from the content. Every step of this encryption uses Advanced Encryption Standard (AES) with 256-bit keys and is Federal Information Processing Standard (FIPS) 140-2 compliant. The encrypted content is distributed across a number of containers throughout the datacenter, and each container has unique credentials. These credentials are stored in a separate physical location from either the content or the content keys.</span></span>
  
<span data-ttu-id="38afe-127">Per ulteriori informazioni sulla conformità FIPS 140-2, vedere [Compliance fips 140-2](https://go.microsoft.com/fwlink/?LinkId=517625).</span><span class="sxs-lookup"><span data-stu-id="38afe-127">For additional information about FIPS 140-2 compliance, see [FIPS 140-2 Compliance](https://go.microsoft.com/fwlink/?LinkId=517625).</span></span>
  
<span data-ttu-id="38afe-p106">La crittografia a livello di file inattiva sfrutta l'archiviazione BLOB per fornire una crescita di archiviazione praticamente illimitata e per consentire una protezione senza precedenti. Tutti i contenuti dei clienti in OneDrive for Business e SharePoint Online verranno migrati nell'archiviazione BLOB. Ecco come vengono protetti i dati:</span><span class="sxs-lookup"><span data-stu-id="38afe-p106">File-level encryption at rest takes advantage of blob storage to provide for virtually unlimited storage growth and to enable unprecedented protection. All customer content in OneDrive for Business and SharePoint Online will be migrated to blob storage. Here's how that data is secured:</span></span>
  
1. <span data-ttu-id="38afe-p107">Tutto il contenuto viene crittografato, potenzialmente con più chiavi e distribuito in tutto il data center. Ogni file da archiviare viene suddiviso in uno o più blocchi, a seconda delle dimensioni. Successivamente, ogni blocco viene crittografato mediante la relativa chiave univoca. Gli aggiornamenti vengono gestiti in modo analogo: il set di modifiche o delta inviato da un utente viene suddiviso in blocchi e ognuno di questi blocchi viene crittografato con la sua chiave.</span><span class="sxs-lookup"><span data-stu-id="38afe-p107">All content is encrypted, potentially with multiple keys, and distributed across the datacenter. Each file to be stored is broken into one or more chunks, depending its size. Then, each chunk is encrypted using its own unique key. Updates are handled similarly: the set of changes, or deltas, submitted by a user is broken into chunks, and each is encrypted with its own key.</span></span>

2. <span data-ttu-id="38afe-p108">Tutti questi blocchi, ovvero file, blocchi di file e aggiornamento delta, verranno archiviati come BLOB nell'archiviazione BLOB. Inoltre vengono casualmente distribuiti in più contenitori BLOB.</span><span class="sxs-lookup"><span data-stu-id="38afe-p108">All of these chunks—files, pieces of files, and update deltas—are stored as blobs in our blob store. They also are randomly distributed across multiple blob containers.</span></span>

3. <span data-ttu-id="38afe-137">La "mappa" utilizzata per riassemblare il file è memorizzata nel database del contenuto.</span><span class="sxs-lookup"><span data-stu-id="38afe-137">The "map" used to re-assemble the file from its components is stored in the Content Database.</span></span>

4. <span data-ttu-id="38afe-p109">Ogni contenitore BLOB ha credenziali univoche per ogni tipo di accesso (lettura, scrittura, enumerazione ed eliminazione). Ogni set di credenziali è conservato nell'archivio chiavi protetto e viene regolarmente aggiornato.</span><span class="sxs-lookup"><span data-stu-id="38afe-p109">Each blob container has its own unique credentials per access type (read, write, enumerate, and delete). Each set of credentials is held in the secure Key Store and is regularly refreshed.</span></span>

<span data-ttu-id="38afe-140">In altre parole, sono disponibili tre tipi diversi di archivi necessari per la crittografia per file inattiva, ognuna con una funzione distinta:</span><span class="sxs-lookup"><span data-stu-id="38afe-140">In other words, there are three different types of stores involved in per-file encryption at rest, each with a distinct function:</span></span>
  
- <span data-ttu-id="38afe-p110">Il contenuto viene archiviato come BLOB crittografati nell'archiviazione BLOB. La chiave di ogni blocco di contenuto è crittografata e conservata separatamente nel database del contenuto. Il contenuto stesso non contiene alcuna indicazione su come può essere decrittografato.</span><span class="sxs-lookup"><span data-stu-id="38afe-p110">Content is stored as encrypted blobs in the blob store. The key to each chunk of content is encrypted and stored separately in the content database. The content itself holds no clue as to how it can be decrypted.</span></span>

- <span data-ttu-id="38afe-p111">Il database del contenuto è un database SQL Server. Contiene la mappa necessaria per individuare e riunire tutti i contenuti BLOB contenuti nell'archiviazione BLOB, nonché le chiavi necessarie per decrittografare tali BLOB.</span><span class="sxs-lookup"><span data-stu-id="38afe-p111">The Content Database is a SQL Server database. It holds the map required to locate and reassemble all of the content blobs held in the blob store as well as the keys needed to decrypt those blobs.</span></span>

<span data-ttu-id="38afe-p112">Ognuno di questi tre componenti di archiviazione, ovvero l'archiviazione BLOB, il database del contenuto e l'archivio chiavi, è separato fisicamente. Le informazioni contenute in uno dei componenti sono inutilizzabili da sole. Questa funzionalità offre un livello di sicurezza senza precedenti. Senza accesso a tutti e tre non è possibile recuperare le chiavi dei blocchi, decrittografare le chiavi per renderli utilizzabili, associare le chiavi ai blocchi corrispondenti, decrittografare i blocchi né ricostruire un documento dai blocchi che lo compongono.</span><span class="sxs-lookup"><span data-stu-id="38afe-p112">Each of these three storage components—the blob store, the Content Database, and the Key Store—is physically separate. The information held in any one of the components is unusable on its own. This provides an unprecedented level of security. Without access to all three it is impossible to retrieve the keys to the chunks, decrypt the keys to make them usable, associate the keys with their corresponding chunks, decrypt any chunk, or reconstruct a document from its constituent chunks.</span></span>
