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
description: Oltre al Centro protezione di Office 365 che fornisce informazioni sulla sicurezza, la privacy e la conformità per Office 365, è possibile che si desideri sapere in che modo Office 365 consente di proteggere i segreti forniti nei propri datacenter. Viene utilizzata una tecnologia denominata Distributed Key Manager (DKM).
ms.openlocfilehash: 6ba60616ee72a4457d81f3f9c2049007afdcbb1d
ms.sourcegitcommit: 5ff1dc62e8855be155cb2de45cf4ee5a02c321fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800076"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Modalità di protezione dei segreti di posta elettronica in Exchange Online

In questo articolo viene descritto come Microsoft garantisce la protezione della posta elettronica degli utenti nei datacenter.
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>Come vengono protette le informazioni riservate fornite dall'utente?

Oltre al Centro protezione di Office 365 che fornisce [informazioni sulla sicurezza, la privacy e la conformità per office 365](https://go.microsoft.com/fwlink/?linkid=874644), è possibile che si desideri sapere in che modo Office 365 consente di proteggere i segreti forniti nei propri datacenter. Viene utilizzata una tecnologia denominata Distributed Key Manager (DKM).
  
[Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) è una funzionalità sul retro del client che utilizza un set di chiavi segrete per crittografare e decrittografare le informazioni. Solo i membri di un gruppo di sicurezza specifico in Servizi di dominio Active Directory possono accedere a tali chiavi per decrittografare i dati crittografati da DKM. In Exchange Online, fanno parte di quel determinato gruppo di sicurezza solo determinati account di servizio nei quali sono in esecuzione i processi di Exchange. Nell'ambito della procedura operativa standard nel datacenter, le credenziali che fanno parte del gruppo di sicurezza non vengono fornite a nessuno; pertanto, nessuno ha accesso alle chiavi in grado di decrittografare le informazioni riservate.
  
Per scopi legati al debug, alla risoluzione dei problemi o al controllo, è necessario che l'amministratore di un datacenter richieda un accesso con privilegi elevati per ottenere le credenziali temporanee relative al gruppo di sicurezza. Questo processo richiede più livelli di approvazione legale. Se viene consentito l'accesso, tutta l'attività viene registrata e controllata. Inoltre, l'accesso viene consentito solo per un determinato intervallo di tempo, al termine del quale scade automaticamente.
  
Per una protezione maggiore, la tecnologia DKM include il rollover della chiave automatico e l'archiviazione. Ciò garantisce ulteriormente che l'utente possa continuare ad accedere ai contenuti meno recenti senza dover usare la stessa chiave per un periodo di tempo indeterminato.
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>Per cosa si utilizza DKM in Exchange Online?

Microsoft utilizza [Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) per crittografare i segreti nei datacenter di Exchange Online. Ad esempio:
  
- Credenziali dell'account di posta elettronica per gli account connessi. Gli account connessi sono account di terze parti, ad esempio Hotmail, Gmail e Yahoo! account di posta elettronica.

- Chiave del cliente. Se si utilizza la [crittografia del servizio con la chiave del cliente in Office 365](customer-key-overview.md), è possibile utilizzare [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) per salvaguardare i segreti.

## <a name="related-topics"></a>Argomenti correlati

[Crittografia in Office 365](encryption.md)
  
[Dettagli tecnici di riferimento sulla crittografia in Office 365](technical-reference-details-about-encryption.md)
  
[Garanzia del servizio nel centro sicurezza &amp; e conformità di Office 365](https://go.microsoft.com/fwlink/?linkid=874645)
  

