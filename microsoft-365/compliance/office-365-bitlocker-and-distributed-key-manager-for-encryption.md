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
description: Informazioni su come Office 365 usa la crittografia BitLocker, riducendo il rischio di furti di dati a causa di computer e dischi smarriti o rubati.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cc329a053544ba6cf1753ae07caac642546cad11
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033624"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>BitLocker e Distributed Key Manager (DKM) per la crittografia

I server Microsoft usano BitLocker per crittografare le unità disco contenenti i dati dei clienti a livello di volume. La crittografia BitLocker è una funzionalità di protezione dei dati integrata in Windows. BitLocker è una delle tecnologie usate per proteggersi dalle minacce in caso di problemi in altri processi o controlli (ad esempio, il controllo degli accessi o il riciclo dell'hardware) che potrebbero portare a un accesso fisico ai dischi contenenti i dati dei clienti. In questo caso, BitLocker elimina il rischio di furto o esposizione dei dati a causa di computer e dischi smarriti, rubati o inappropriati.

BitLocker viene distribuito con la crittografia AES (Advanced Encryption Standard) a 256 bit su dischi contenenti dati dei clienti in Exchange Online, SharePoint Online e Skype for Business. I settori del disco vengono crittografati con una chiave FVEK (Full Volume Encryption Key), crittografata con la chiave master del volume (VMK), che a sua volta è associata al TPM (Trusted Platform Module) nel server. VmK protegge direttamente FVEK e pertanto la protezione della VMK diventa fondamentale. Nella figura seguente viene illustrato un esempio della catena di protezione delle chiavi di BitLocker per un determinato server (in questo caso, utilizzando un server Exchange Online).

Nella tabella seguente viene descritta la catena di protezione delle chiavi di BitLocker per un determinato server (in questo caso, un server Exchange Online).

| KEY PROTECTOR | GRANULARITÀ | COME VIENE GENERATO? | DOVE È ARCHIVIATO? | PROTEZIONE |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| Chiave esterna AES a 256 bit | Per Server | API BitLocker | TPM o Secret Safe | Lockbox/Controllo di accesso |
|  |  |  | Registro di sistema del server Cassette postali | TPM crittografato |
| Password numerica a 48 cifre | Per disco | API BitLocker | Active Directory | Lockbox/Controllo di accesso |
| Certificato X.509 come agente di recupero dati (DRA, Data Recovery Agent) denominato anche protezione a chiave pubblica | Ambiente (ad esempio, Multitenant di Exchange Online) | Microsoft CA | Sistema di compilazione | Nessun utente ha la password completa per la chiave privata. La password è protetta fisicamente. |


La gestione delle chiavi di BitLocker implica la gestione delle chiavi di ripristino usate per sbloccare/recuperare dischi crittografati in un datacenter Microsoft. Microsoft 365 archivia le chiavi master in una condivisione protetta, accessibile solo dagli utenti che sono stati schermati e approvati. Le credenziali per le chiavi vengono archiviate in un archivio protetto per i dati di controllo di accesso (che viene chiamato "archivio segreto"), che richiede un elevato livello di approvazione dell'elevazione e della gestione per l'accesso tramite uno strumento di elevazione degli accessi just-in-time.

BitLocker supporta le chiavi che rientrano in due categorie di gestione:

- Chiavi gestite da BitLocker, generalmente di breve durata e legate alla durata di un'istanza del sistema operativo installata in un server o in un determinato disco. Queste chiavi vengono eliminate e reimpostate durante la reinstallazione del server o la formattazione del disco.

- Chiavi di ripristino di BitLocker, gestite all'esterno di BitLocker, ma usate per la decrittografia del disco. BitLocker usa le chiavi di ripristino per lo scenario in cui un sistema operativo viene reinstallato e i dischi di dati crittografati esistono già. Le chiavi di ripristino vengono utilizzate anche dai probe di monitoraggio della disponibilità gestita in Exchange Online in cui un risponditore potrebbe dover sbloccare un disco.

I volumi protetti con BitLocker vengono crittografati con una chiave di crittografia del volume completa, che a sua volta viene crittografata con una chiave master del volume. BitLocker usa algoritmi conformi a FIPS per garantire che le chiavi di crittografia non siano mai archiviate o inviate in rete in chiaro. L'implementazione di Microsoft 365 della protezione dei dati inattivi dei clienti non si discosta dall'implementazione bitlocker predefinita.
