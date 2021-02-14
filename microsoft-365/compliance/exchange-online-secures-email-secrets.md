---
title: Come viene garantita la protezione della posta elettronica in Exchange Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: Oltre al Centro protezione di Office 365 che fornisce informazioni su sicurezza, privacy e conformità per Microsoft 365, è consigliabile sapere in che modo Microsoft protegge i segreti archiviati nei relativi datacenter. Usiamo una tecnologia denominata Distributed Key Manager (DKM).
ms.openlocfilehash: 17a7fbbd54a725edcd87681f011ddc6633a1f4aa
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43615980"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Modalità di protezione dei segreti di posta elettronica in Exchange Online

In questo articolo viene descritto come Microsoft garantisce la protezione della posta elettronica degli utenti nei datacenter.
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>Come vengono protette le informazioni riservate fornite dall'utente?

Oltre al Centro protezione di Office 365 che fornisce informazioni su sicurezza, privacy e conformità per [Office 365,](https://go.microsoft.com/fwlink/?linkid=874644)è consigliabile sapere in che modo Microsoft protegge i segreti forniti nei relativi datacenter. Usiamo una tecnologia denominata Distributed Key Manager (DKM).
  
[Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) è una funzionalità sul lato client che usa un set di chiavi segrete per crittografare e decrittografare le informazioni. Solo i membri di un gruppo di sicurezza specifico in Servizi di dominio Active Directory possono accedere a tali chiavi per decrittografare i dati crittografati da DKM. In Exchange Online, fanno parte di quel determinato gruppo di sicurezza solo determinati account di servizio nei quali sono in esecuzione i processi di Exchange. Nell'ambito della procedura operativa standard nel datacenter, le credenziali che fanno parte del gruppo di sicurezza non vengono fornite a nessuno; pertanto, nessuno ha accesso alle chiavi in grado di decrittografare le informazioni riservate.
  
Per scopi legati al debug, alla risoluzione dei problemi o al controllo, è necessario che l'amministratore di un datacenter richieda un accesso con privilegi elevati per ottenere le credenziali temporanee relative al gruppo di sicurezza. Questo processo richiede più livelli di approvazione legale. Se viene consentito l'accesso, tutta l'attività viene registrata e controllata. Inoltre, l'accesso viene consentito solo per un determinato intervallo di tempo, al termine del quale scade automaticamente.
  
Per una protezione maggiore, la tecnologia DKM include il rollover della chiave automatico e l'archiviazione. Ciò garantisce ulteriormente che l'utente possa continuare ad accedere ai contenuti meno recenti senza dover usare la stessa chiave per un periodo di tempo indeterminato.
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>Per cosa si utilizza DKM in Exchange Online?

Microsoft utilizza [Distributed Key Manager per](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) crittografare i segreti nei datacenter di Exchange Online. Ad esempio:
  
- Credenziali dell'account di posta elettronica per gli account connessi. Gli account connessi sono account di terze parti come Hotmail, Gmail e Yahoo! account di posta elettronica.

- Codice cliente. Se usi la crittografia [del servizio con Customer Key,](customer-key-overview.md)userai Azure Key [Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) per proteggere i tuoi segreti.

## <a name="related-topics"></a>Argomenti correlati

[Crittografia in Office 365](encryption.md)
  
[Dettagli tecnici di riferimento sulla crittografia](technical-reference-details-about-encryption.md)
  
[Garanzia del servizio nel Centro &amp; sicurezza e conformità](https://go.microsoft.com/fwlink/?linkid=874645)
  

