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
ms.openlocfilehash: 354f61284bbd95c1c7ca4cd50459a1644a89d090
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023262"
---
# <a name="localize-the-user-experience"></a>Localizzare l'esperienza utente

Gli utenti Microsoft Managed Desktop dispositivi possono selezionare la lingua desiderata durante il processo di installazione (l'esperienza predefinita) o successivamente.

## <a name="during-setup-the-out-of-box-experience"></a>Durante l'installazione (l'esperienza "out-of-box")

Durante il processo di completamento dell'installazione, gli utenti possono selezionare la lingua desiderata. Questa selezione influisce su questi attributi:

- Windows 10 delle lingue:
    - Lingua di visualizzazione
    - Lingua tastiera
    - Funzionalità correlate alla lingua su richiesta

- Microsoft 365 Apps per le Enterprise linguistiche:
    - Lingua di visualizzazione
    - Strumenti di correzione e creazione

> [!NOTE]
> Gli utenti possono ottenere funzionalità correlate alla lingua solo su richiesta selezionando la lingua durante il processo di installazione.

## <a name="after-completing-setup"></a>Dopo aver completato l'installazione

Gli utenti possono selezionare la lingua desiderata per Windows 10 e Microsoft 365 Apps per Enterprise in qualsiasi momento al termine del processo di installazione. In particolare:

- Windows 10 delle lingue:
    - Lingua di visualizzazione
    - Lingua tastiera

- Microsoft 365 Apps per le Enterprise linguistiche:
    - Lingua di visualizzazione
    - Strumenti di correzione e creazione

Per rendere disponibili [le](#supported-languages) lingue supportate per Microsoft 365 Apps per Enterprise per gli utenti, aggiungere gli utenti al gruppo **Office-Language_Packs** moderno. Le lingue saranno disponibili nella Portale aziendale Intune.


## <a name="supported-languages"></a>Lingue supportate

Per i nuovi dispositivi, il produttore deve fornire immagini del dispositivo che includono le lingue necessarie. Se l'immagine del produttore include lingue diverse da quelle incluse nell'elenco delle lingue supportate, è ancora supportata dal servizio.

Se si riutilizzano dispositivi esistenti, potrebbe essere necessario collaborare con il rappresentante dell'account Microsoft per ottenere le immagini appropriate. Per altre informazioni, vedi [Immagini dispositivo.](../service-description/device-images.md)

[L'immagine universale](../service-description/device-images.md#universal-image) fornita da Microsoft Managed Desktop include queste lingue e per Windows 10:

- Arabo
- Bulgaro
- Chinese Simplified
- Chinese Traditional
- Croato
- Ceco
- Danese  
- Olandese  
- Inglese (US, GB, AU, CA, IN)
- Estone
- Finlandese 
- Francese (Francia, Canada)
- Tedesco
- Greco
- Ebraico
- Ungherese
- Indonesiano
- Italiano
- Giapponese
- Coreano
- Lettone
- Lituano
- Norvegese (Bokmål)
- Polacco
- Portoghese (Brasile)
- Portoghese (Portogallo)
- Rumeno
- Russo 
- Serbo (alfabeto latino)
- Slovacco
- Sloveno
- Spagnolo (Spagna, Messico)
- Svedese
- Tailandese
- Turco
- Ucraino
- Vietnamita

Microsoft 365 Apps per Enterprise potrebbe supportare un elenco leggermente diverso.

Se gli utenti hanno bisogno di una lingua diversa da quella elencata qui, stendiamo una richiesta [di supporto](../working-with-managed-desktop/admin-support.md) tramite il portale [di amministrazione.](access-admin-portal.md)

## <a name="languages-for-support-and-operations"></a>Lingue per il supporto e le operazioni

### <a name="user-support"></a>Supporto agli utenti
Microsoft Managed Desktop il supporto solo in inglese. Se gli utenti scelgono un'altra lingua nell'app Richiesta supporto, riceveranno supporto dai canali di supporto Microsoft generali, anziché direttamente da Microsoft Managed Desktop. Per ulteriori informazioni, vedere [Ottenere assistenza per gli utenti.](../working-with-managed-desktop/end-user-support.md)

Se gli utenti necessitano di supporto in altre lingue, è necessario fornire tale supporto tramite fonti di supporto non Microsoft o dalla propria organizzazione.

### <a name="admin-support-and-operations"></a>Supporto e operazioni dell'amministratore
Microsoft Managed Desktop il supporto dell'amministratore solo in inglese. Sono inclusi il portale di amministrazione e tutte le comunicazioni con Microsoft Managed Desktop Operations. È consigliabile presupporre che tutte le interazioni e le interfacce correlate all'amministratore siano in inglese, a meno che non venga specificato diversamente.


