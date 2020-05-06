---
title: BitLocker per la crittografia
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
description: Informazioni su come Office 365 utilizza la crittografia BitLocker, riducendo le potenzialità di furto dei dati a causa di computer e dischi persi o rubati.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cc329a053544ba6cf1753ae07caac642546cad11
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033624"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>BitLocker e Distributed Key Manager (DKM) per la crittografia

I server Microsoft utilizzano BitLocker per crittografare le unità disco che contengono i dati dei clienti a riposo a livello di volume. La crittografia BitLocker è una funzionalità di protezione dei dati incorporata in Windows. BitLocker è una delle tecnologie utilizzate per la salvaguardia dalle minacce, nel caso in cui si verifichino ricadute in altri processi o controlli, ad esempio il controllo dell'accesso o il riciclo dell'hardware, che potrebbero determinare un accesso fisico ai dischi che contengono i dati dei clienti. In questo caso, BitLocker Elimina le potenzialità per il furto o l'esposizione dei dati a causa di computer e dischi persi, rubati o disattivati in modo inappropriato.

BitLocker è distribuito con crittografia a 256 bit AES (Advanced Encryption Standard) su dischi contenenti dati dei clienti in Exchange Online, SharePoint Online e Skype for business. I settori del disco sono crittografati con una chiave di crittografia a volume completo (FVEK), crittografata con la chiave master del volume (VMK), che a sua sua è associata al TPM (Trusted Platform Module) nel server. La VMK protegge direttamente la FVEK e, pertanto, la protezione del VMK diventa critica. Nella figura seguente viene illustrato un esempio della catena di protezione della chiave BitLocker per un determinato server (in questo caso, utilizzando un server Exchange Online).

Nella tabella seguente viene descritta la catena di protezione della chiave BitLocker per un determinato server (in questo caso, un server Exchange Online).

| PROTEZIONE CHIAVE | GRANULARITÀ | COME VIENE GENERATO? | DOVE VIENE MEMORIZZATO? | PROTEZIONE |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| Chiave esterna AES 256 bit | Per server | API di BitLocker | TPM o cassaforte segreta | Archivio protetto/controllo di accesso |
|  |  |  | Registro di sistema del server cassette postali | TPM crittografato |
| Password numerica 48-digit | Per disco | API di BitLocker | Active Directory | Archivio protetto/controllo di accesso |
| Certificato X. 509 come agente di recupero dati (DRA) denominato anche protezione a chiave pubblica | Ambiente (ad esempio, Exchange Online multitenant) | Microsoft CA | Sistema di compilazione | Nessun utente ha la password completa per la chiave privata. La password è sotto protezione fisica. |


La gestione delle chiavi di BitLocker implica la gestione delle chiavi di ripristino che vengono utilizzate per sbloccare/recuperare dischi crittografati in un datacenter Microsoft. Microsoft 365 archivia le chiavi master in una condivisione protetta, accessibile solo dalle persone che sono state schermate e approvate. Le credenziali per le chiavi vengono archiviate in un archivio protetto per i dati di controllo di accesso (quello che viene chiamato "archivio segreto"), che richiede un elevato livello di approvazioni di gestione e elevazione per accedere utilizzando uno strumento di elevazione di accesso just-in-time.

BitLocker supporta le chiavi che rientrano in due categorie di gestione:

- Chiavi gestite da BitLocker, che in genere sono di breve durata e legate al ciclo di vita di un'istanza del sistema operativo installata su un server o su un determinato disco. Queste chiavi vengono eliminate e reimpostate durante la reinstallazione del server o la formattazione del disco.

- Chiavi di ripristino di BitLocker, gestite all'esterno di BitLocker ma utilizzate per la decrittografia del disco. BitLocker utilizza le chiavi di ripristino per lo scenario in cui viene reinstallato un sistema operativo e i dischi di dati crittografati esistono già. Le chiavi di ripristino vengono utilizzate anche dai Probe di monitoraggio della disponibilità gestita in Exchange Online, in cui potrebbe essere necessario che un risponditore sblocchi un disco.

I volumi protetti da BitLocker sono crittografati con una chiave di crittografia a volume completo, che a sua sua è crittografata con una chiave master volume. BitLocker utilizza algoritmi FIPS conformi per garantire che le chiavi di crittografia non vengano mai archiviate o inviate tramite cavo in chiaro. L'implementazione Microsoft 365 del Customer data-at-rest-Protection non si discosta dall'implementazione predefinita di BitLocker.
