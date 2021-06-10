---
title: Usare il controllo dell'accesso basato sui ruoli per concedere l'accesso specifico ai Microsoft Defender Security Center
description: Creare ruoli e gruppi all'interno delle operazioni di sicurezza per concedere l'accesso al portale.
keywords: rbac, role, based, access, control, groups, control, tier, aad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d95163bd7caf6e05295fc35b3f9c2bf95230dc83
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063842"
---
# <a name="manage-portal-access-using-role-based-access-control"></a>Gestire l'accesso al portale tramite il controllo di accesso basato sui ruoli

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- Azure Active Directory
- Office 365

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-rbac-abovefoldlink)

Utilizzando il controllo degli accessi in base ai ruoli (RBAC, Role-Based Access Control), è possibile creare ruoli e gruppi all'interno del team delle operazioni di sicurezza per concedere l'accesso appropriato al portale. In base ai ruoli e ai gruppi creati, si dispone di un controllo accurato sulle operazioni che gli utenti con accesso al portale possono visualizzare e fare. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bJ2a]

I team delle operazioni di sicurezza con distribuzione geografica di grandi dimensioni in genere adottano un modello basato su livelli per assegnare e autorizzare l'accesso ai portali di sicurezza. I livelli tipici includono i tre livelli seguenti:

Livello | Descrizione
:---|:---
Livello 1 | **Team delle operazioni di sicurezza locale /team IT** <br> Questo team in genere analizza e analizza gli avvisi contenuti nella georilevazione e si riassegna al livello 2 nei casi in cui è necessaria una correzione attiva.
Livello 2 | **Team operativo per la sicurezza regionale** <br> Questo team può visualizzare tutti i dispositivi per la propria area geografica ed eseguire azioni di correzione.
Livello 3    | **Team globale per le operazioni di sicurezza** <br> Questo team è costituito da esperti di sicurezza e sono autorizzati a visualizzare ed eseguire tutte le azioni dal portale.

Defender for Endpoint RBAC è progettato per supportare il modello di scelta basato sui livelli o sui ruoli e offre un controllo granulare sui ruoli che possono essere visualizzati, sui dispositivi a cui possono accedere e sulle azioni che possono eseguire. Il framework RBAC è centrato sui controlli seguenti:

- **Controllare gli utenti che possono eseguire azioni specifiche**
  - Crea ruoli personalizzati e controlla quali funzionalità di Defender for Endpoint possono accedere con granularità.
 
- **Controllare chi può visualizzare informazioni su gruppi di dispositivi o gruppi specifici**
  - [Crea gruppi di dispositivi](machine-groups.md) in base a criteri specifici, ad esempio nomi, tag, domini e altri, quindi concedi loro l'accesso ai ruoli usando un gruppo di utenti di Azure Active Directory (Azure AD).

Per implementare l'accesso basato sui ruoli, è necessario definire i ruoli di amministratore, assegnare le autorizzazioni corrispondenti e assegnare i gruppi di utenti di Azure AD assegnati ai ruoli.


### <a name="before-you-begin"></a>Prima di iniziare
Prima di utilizzare RBAC, è importante comprendere i ruoli che possono concedere le autorizzazioni e le conseguenze dell'attivazione del controllo degli accessi in base al ruolo.


> [!WARNING]
> Prima di abilitare la funzionalità, è importante disporre di un ruolo amministratore globale o amministratore della sicurezza in Azure AD e che i gruppi di Azure AD sono pronti per ridurre il rischio di essere bloccati dal portale. 

Al primo accesso a Microsoft Defender Security Center, viene concesso l'accesso completo o l'accesso in sola lettura. I diritti di accesso completo vengono concessi agli utenti con ruoli di amministratore della sicurezza o amministratore globale in Azure AD. L'accesso in sola lettura viene concesso agli utenti con un ruolo lettore di sicurezza in Azure AD. 

Un utente con un ruolo di amministratore defender per endpoint globale ha accesso illimitato a tutti i dispositivi, indipendentemente dall'associazione del gruppo di dispositivi e dalle assegnazioni dei gruppi di utenti di Azure AD

> [!WARNING]
> Inizialmente, solo gli utenti con diritti di amministratore globale o amministratore della sicurezza di Azure AD saranno in grado di creare e assegnare ruoli in Microsoft Defender Security Center, pertanto è importante disporre dei gruppi appropriati pronti in Azure AD.
>
> **Se si attiva il controllo dell'accesso basato sui ruoli, gli utenti con autorizzazioni di sola lettura (ad esempio, gli utenti assegnati al ruolo lettore di Sicurezza di Azure AD) perderanno l'accesso fino a quando non vengono assegnati a un ruolo.** 
>
>Agli utenti con autorizzazioni di amministratore viene assegnato automaticamente il ruolo predefinito predefinito di amministratore globale defender per endpoint con autorizzazioni complete. Dopo aver scelto di usare RBAC, puoi assegnare altri utenti che non sono amministratori globali o di sicurezza di Azure AD al ruolo di amministratore globale di Defender for Endpoint. 
>
> Dopo aver scelto di usare RBAC, non è possibile ripristinare i ruoli iniziali come quando si è effettuato l'accesso al portale per la prima volta. 



## <a name="related-topic"></a>Argomento correlato
- [Creare e gestire gruppi di dispositivi in Microsoft Defender for Endpoint](machine-groups.md)
