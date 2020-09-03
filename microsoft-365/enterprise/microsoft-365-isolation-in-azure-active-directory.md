---
title: Microsoft 365 isolamento e controllo di accesso in Azure Active Directory
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In questo articolo, vengono fornite informazioni sul funzionamento dell'isolamento e del controllo di accesso per mantenere i dati per più tenant isolati tra loro all'interno di Azure Active Directory.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 198e1f37a7378d14d5a4ad28d5bce9d480b2c49e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332413"
---
# <a name="microsoft-365-isolation-and-access-control-in-azure-active-directory"></a>Microsoft 365 isolamento e controllo di accesso in Azure Active Directory

Azure Active Directory (Azure AD) è stato creato per ospitare più tenant in modo estremamente sicuro tramite l'isolamento dei dati logici. L'accesso a Azure AD è gated da un livello di autorizzazione. Azure AD isola i clienti utilizzando i contenitori tenant come limiti di sicurezza per salvaguardare il contenuto di un cliente, in modo che non sia possibile accedere ai contenuti o essere compromessi dai coinquilini. Tre controlli vengono eseguiti dal livello di autorizzazione di Azure AD:

- L'entità è abilitata per l'accesso al tenant di Azure AD?
- L'entità è abilitata per l'accesso ai dati nel tenant?
- Il ruolo dell'entità in questo tenant è autorizzato per il tipo di accesso ai dati richiesto?

Nessuna applicazione, utente, server o servizio può accedere AD Azure AD senza l'autenticazione e il token o il certificato appropriati. Le richieste vengono rifiutate se non sono accompagnate da credenziali appropriate.

In modo efficace, Azure AD ospita ogni tenant nel proprio contenitore protetto, con i criteri e le autorizzazioni per e all'interno del contenitore posseduto e gestito solo dal tenant.
 
![Contenitore di Azure](../media/office-365-isolation-azure-container.png)

Il concetto di contenitori tenant è profondamente radicato nel servizio directory a tutti i livelli, dai portali fino all'archiviazione persistente. Anche quando più metadati tenant di Azure AD sono archiviati nello stesso disco fisico, non esiste alcuna relazione tra i contenitori diversi da quelli definiti dal servizio directory, che a sua volta è dettata dall'amministratore del tenant. Non vi possono essere connessioni dirette all'archiviazione di Azure AD da qualsiasi applicazione o servizio richiedente senza prima passare attraverso il livello di autorizzazione.

Nell'esempio riportato di seguito, Contoso e Fabrikam dispongono entrambi di contenitori separati e dedicati e, sebbene tali contenitori possano condividere parte della stessa infrastruttura sottostante, ad esempio i server e l'archiviazione, rimangono separati e isolati tra loro e sono deportati da livelli di autorizzazione e controllo di accesso.
 
![Contenitori dedicati di Azure](../media/office-365-isolation-azure-dedicated-containers.png)

Inoltre, non sono presenti componenti dell'applicazione che possono essere eseguiti dall'interno di Azure AD e non è possibile che un tenant violi forzatamente l'integrità di un altro tenant, acceda alle chiavi di crittografia di un altro tenant o legga dati non elaborati dal server.

Per impostazione predefinita, Azure AD non consente tutte le operazioni emesse dalle identità in altri tenant. Ogni tenant è logicamente isolato all'interno di Azure AD tramite i controlli di accesso basati sulle attestazioni. Le letture e le scritture dei dati della directory sono limitate ai contenitori tenant e sono deportate da un livello di astrazione interno e da un livello di controllo di accesso basato sui ruoli (RBAC), che insieme impongono il tenant come limite di sicurezza. Ogni richiesta di accesso ai dati di directory viene elaborata da questi layer e ogni richiesta di accesso in Microsoft 365 è sorvegliata dalla logica precedente.

Azure AD ha il Nord America, il governo degli Stati Uniti, l'Unione europea, la Germania e le partizioni mondiali. Un tenant esiste in una singola partizione e le partizioni possono contenere più tenant. Le informazioni sulla partizione vengono sottratte agli utenti. Una determinata partizione (inclusi tutti i tenant all'interno) viene replicata in più datacenter. La partizione per un tenant viene scelta in base alle proprietà del tenant (ad esempio, il codice paese). I segreti e altre informazioni riservate in ogni partizione vengono crittografati con una chiave dedicata. Le chiavi vengono generate automaticamente quando viene creata una nuova partizione.

Le funzionalità di Azure AD System sono un'istanza univoca per ogni sessione utente. Inoltre, Azure AD utilizza tecnologie di crittografia per garantire l'isolamento delle risorse di sistema condivise a livello di rete per impedire il trasferimento non autorizzato e involontario di informazioni.
