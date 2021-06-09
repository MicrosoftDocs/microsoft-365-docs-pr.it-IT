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
description: Informazioni su come Office 365 la crittografia BitLocker, riducendo il rischio di furto di dati a causa di computer e dischi smarriti o rubati.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cc329a053544ba6cf1753ae07caac642546cad11
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033624"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>BitLocker e Distributed Key Manager (DKM) per la crittografia

I server Microsoft BitLocker per crittografare le unità disco contenenti i dati dei clienti in pausa a livello di volume. BitLocker è una funzionalità di protezione dei dati incorporata in Windows. BitLocker è una delle tecnologie utilizzate per la protezione dalle minacce in caso di problemi in altri processi o controlli (ad esempio, il controllo dell'accesso o il riciclo dell'hardware) che potrebbero portare a un utente che ottiene l'accesso fisico ai dischi contenenti i dati dei clienti. In questo caso, BitLocker il rischio di furto o esposizione dei dati a causa di computer e dischi smarriti, rubati o inappropriati.

BitLocker viene distribuito con la crittografia a 256 bit Advanced Encryption Standard (AES) su dischi contenenti dati dei clienti in Exchange Online, SharePoint Online e Skype for Business. I settori del disco vengono crittografati con una chiave FVEK (Full Volume Encryption Key), che viene crittografata con la chiave master del volume (VMK), che a sua volta è associata al TPM (Trusted Platform Module) nel server. VmK protegge direttamente il FVEK e pertanto, la protezione della VMK diventa fondamentale. Nella figura seguente viene illustrato un esempio della catena BitLocker di protezione delle chiavi per un determinato server (in questo caso, utilizzando un server Exchange Online).

Nella tabella seguente viene descritta la BitLocker di protezione delle chiavi per un determinato server (in questo caso, un server Exchange Online).

| PROTEZIONE DELLE CHIAVI | GRANULARITÀ | COME GENERATO? | DOVE È ARCHIVIATO? | PROTEZIONE |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| Chiave esterna AES a 256 bit | Per Server | BitLocker API | TPM o secret safe | Lockbox / Controllo di accesso |
|  |  |  | Registro di sistema del server Cassette postali | TPM crittografato |
| Password numerica a 48 cifre | Per disco | BitLocker API | Active Directory | Lockbox / Controllo di accesso |
| Certificato X.509 come agente di recupero dati (DRA, Data Recovery Agent) denominato anche protettore delle chiavi pubbliche | Ambiente (ad esempio, Exchange Online multitenant) | Microsoft CA | Build System | Nessun utente ha la password completa per la chiave privata. La password è sotto protezione fisica. |


BitLocker gestione delle chiavi implica la gestione delle chiavi di ripristino utilizzate per sbloccare/ripristinare dischi crittografati in un datacenter Microsoft. Microsoft 365 le chiavi master vengono archiviate in una condivisione protetta, accessibile solo da utenti che sono stati schermati e approvati. Le credenziali per le chiavi vengono archiviate in un archivio protetto per i dati di controllo di accesso (quello che viene chiamato "archivio segreto"), che richiede un elevato livello di elevazione e approvazione della gestione per accedere utilizzando uno strumento di elevazione degli accessi just-in-time.

BitLocker supporta le chiavi che rientrano in due categorie di gestione:

- BitLocker chiavi gestite dall'utente, generalmente di breve durata e legate alla durata di un'istanza del sistema operativo installata in un server o in un determinato disco. Queste chiavi vengono eliminate e reimpostate durante la reinstallazione del server o la formattazione del disco.

- BitLocker di ripristino, gestite all'esterno di BitLocker ma utilizzate per la decrittografia del disco. BitLocker le chiavi di ripristino per lo scenario in cui un sistema operativo viene reinstallato e i dischi dati crittografati esistono già. Le chiavi di ripristino vengono usate anche dai probe di monitoraggio della disponibilità gestita in Exchange Online in cui un risponditore potrebbe dover sbloccare un disco.

BitLocker sono crittografati con una chiave di crittografia del volume completo, che a sua volta viene crittografata con una chiave master del volume. BitLocker vengono utilizzati algoritmi conformi a FIPS per garantire che le chiavi di crittografia non siano mai archiviate o inviate in rete in chiaro. L Microsoft 365 in implementazione della protezione dei dati dei clienti inattiva non si discosta dall'implementazione BitLocker predefinita.
