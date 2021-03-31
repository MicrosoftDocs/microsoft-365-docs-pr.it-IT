---
title: Localizzare l'esperienza utente
description: Come localizzare i dispositivi per gli utenti
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 20456ce837be60b707569ae07d4fb00b695b3a98
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445982"
---
# <a name="localize-the-user-experience"></a>Localizzare l'esperienza utente

Gli utenti dei dispositivi Microsoft Managed Desktop possono selezionare la lingua desiderata durante il processo di installazione (l'esperienza predefinita) o successivamente.

## <a name="during-setup-the-out-of-box-experience"></a>Durante l'installazione (l'esperienza "out-of-box")

Durante il processo di completamento dell'installazione, gli utenti possono selezionare la lingua desiderata. Questa selezione influisce su questi attributi:

- Funzionalità della lingua di Windows 10:
    - Lingua di visualizzazione
    - Lingua tastiera
    - Funzionalità correlate alla lingua su richiesta

- Funzionalità della lingua di Microsoft 365 Apps for Enterprise:
    - Lingua di visualizzazione
    - Strumenti di correzione e creazione

> [!NOTE]
> Gli utenti possono ottenere funzionalità correlate alla lingua solo su richiesta selezionando la lingua durante il processo di installazione.

## <a name="after-completing-setup"></a>Dopo aver completato l'installazione

Gli utenti possono selezionare la lingua desiderata per Windows 10 e Microsoft 365 Apps for Enterprise in qualsiasi momento al termine del processo di configurazione. In particolare:

- Funzionalità della lingua di Windows 10:
    - Lingua di visualizzazione
    - Lingua tastiera

- Funzionalità della lingua di Microsoft 365 Apps for Enterprise:
    - Lingua di visualizzazione
    - Strumenti di correzione e creazione

Per rendere disponibili [per](#supported-languages) gli utenti le lingue supportate per Microsoft 365 Apps for Enterprise, aggiungere gli utenti al gruppo **Modern Workplace-Office-Language_Packs.** Le lingue saranno disponibili nel portale aziendale intune.


## <a name="supported-languages"></a>Lingue supportate

Per i nuovi dispositivi, il produttore deve fornire immagini del dispositivo che includono le lingue necessarie. Se l'immagine del produttore include lingue diverse da quelle incluse nell'elenco delle lingue supportate, è ancora supportata dal servizio.

Se si riutilizzano dispositivi esistenti, potrebbe essere necessario collaborare con il rappresentante dell'account Microsoft per ottenere le immagini appropriate. Per altre informazioni, vedi [Immagini dispositivo.](../service-description/device-images.md)

[L'immagine universale](../service-description/device-images.md#universal-image) fornita da Microsoft Managed Desktop include queste lingue e per Windows 10:

- Inglese (US, GB, AU, CA, IN)
- Spagnolo (Spagna, Messico)
- Giapponese
- Francese (Francia, Canada)
- Tedesco
- Portoghese (Brasile)
- Italiano
- Chinese Simplified
- Olandese  
- Svedese
- Danese  
- Finlandese 
- Russo 
- Norvegese (Bokmal)
- Coreano
- Chinese Traditional
- Polacco
- Turco
- Arabo
- Ebraico
- Portoghese (Portogallo)
- Ceco
- Ungherese
- Thai
- Indonesiano
- Greco
- Slovacco
- Vietnamita
- Sloveno
- Croato
- Romeno
- Lituano
- Bulgaro
- Serbo (alfabeto latino)
- Lettone
- Ucraino
- Estone

Microsoft 365 Apps for Enterprise potrebbe supportare un elenco leggermente diverso.

Se gli utenti hanno bisogno di una lingua diversa da quella elencata qui, stendiamo una richiesta [di supporto](../working-with-managed-desktop/admin-support.md) tramite il portale [di amministrazione.](access-admin-portal.md)

## <a name="languages-for-support-and-operations"></a>Lingue per il supporto e le operazioni

### <a name="user-support"></a>Supporto agli utenti
Microsoft Managed Desktop fornisce supporto solo in inglese. Se gli utenti scelgono un'altra lingua nell'app Guida, riceveranno supporto dai canali di supporto Microsoft generali, anziché direttamente da Microsoft Managed Desktop. Per ulteriori informazioni, vedere [Ottenere assistenza per gli utenti.](../working-with-managed-desktop/end-user-support.md)

Se gli utenti necessitano di supporto in altre lingue, è necessario fornire tale supporto tramite fonti di supporto non Microsoft o dalla propria organizzazione.

### <a name="admin-support-and-operations"></a>Supporto e operazioni dell'amministratore
Microsoft Managed Desktop fornisce il supporto per gli amministratori solo in inglese. Sono inclusi il portale di amministrazione e tutte le comunicazioni con Microsoft Managed Desktop Operations. È consigliabile presupporre che tutte le interazioni e le interfacce correlate all'amministratore siano in inglese, a meno che non venga specificato diversamente.


