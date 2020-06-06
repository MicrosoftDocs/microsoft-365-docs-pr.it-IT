---
title: Collegamenti sicuri ATP per Team, safelinks, collegamenti sicuri, blocca collegamenti dannosi, Office 365 ATP, collegamenti sicuri per i team, impedire agli utenti di fare clic su collegamenti non validi, collegamenti dannosi
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 02/28/2020
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: I team avranno ora accesso ai collegamenti sicuri al momento del clic. Se si utilizzano chat 1-su-1 chat, tra gruppi o in canali e tabulazioni, se si dispone di un abbonamento a Office 365 ATP, si avrà la possibilità di abilitare e utilizzare questa funzionalità di sicurezza.
ms.openlocfilehash: d7586dba86c7ec9f43457b5510a1255e06bb6bf9
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588277"
---
<!--06/21/2019-->

# <a name="safe-links-in-teams"></a>Collegamenti sicuri in Teams

> [!IMPORTANT]
> Questa funzionalità è in **anteprima pubblica** per i clienti del Microsoft teams Technology Adoption Program (TAP) del 28 febbraio 2020. Questa nota verrà rimossa dall'articolo quando i collegamenti sicuri per i team sono più diffusi.

Microsoft teams, un'applicazione basata sul cloud Microsoft per la gestione del lavoro, utilizza già gli allegati sicuri (per Office 365), ma ora avrà accesso ai collegamenti sicuri al momento del clic. Se si utilizzano chat, chat di gruppo, canali o schede, se si dispone di un abbonamento a Office 365 ATP, si avrà la possibilità di abilitare e utilizzare questa misura di sicurezza. Per altre informazioni sui requisiti di licenza, vedere [Linee guida per le licenze dei servizi a livello di tenant di Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

Tenere presente quanto segue:

1. Quando si avvia l'applicazione teams, Microsoft 365 controllerà per assicurarsi che l'utente appartenga a un'organizzazione con Office 365 ATP e che l'utente faccia parte di un criterio di collegamenti sicuri attivo con la protezione abilitata per Microsoft teams.

2. Se il valore di cui sopra è vero, gli URL verranno convalidati al momento del clic su chat, chat di gruppo, canali e in schede per tale utente.

## <a name="what-will-users-experience"></a>Che cosa useranno gli utenti?

Tutti gli utenti protetti avranno questa esperienza con gli URL pericolosi:

- Se il collegamento è stato selezionato da una conversazione di Team, da una chat di gruppo o da un canale, verrà eseguito il rendering di una pagina nel browser predefinito. Se il collegamento è stato selezionato da una scheda bloccata, la pagina verrà visualizzata nella GUI teams all'interno di tale scheda e l'opzione per l'apertura nel browser verrà disabilitata per motivi di sicurezza.

- Questo utente verrà bloccato dal procedere al sito dell'URL.

Se l'utente che ha inviato il collegamento non è protetto da Office 365 ATP, è libero di fare clic sull'URL nel computer in uso e di risolvere il problema. Questo rende doppiamente importante per gli amministratori di essere a conoscenza di chi sono gli utenti protetti e devono essere.

![Una pagina collegamenti sicuri per i team che segnalano un collegamento dannoso e bloccano il transito alla pagina.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

Se si fa clic sul pulsante *Torna indietro* in questa pagina, il team verrà chiuso (o potrebbe risultare che gli utenti di una pagina vuota possano chiudere). Tuttavia, facendo clic nuovamente sul collegamento si otterrà una rivalutazione della reputazione del sito in modo che questa pagina ricompaia.

> [!NOTE]
> Alcuni amministratori di Microsoft 365 consentiranno la **prosecuzione** del messaggio nella pagina di blocco. Tuttavia, se i collegamenti sicuri misurano la reputazione di un sito e lo trovano privo, non è necessario eseguire ulteriori clic. Non è consigliabile ignorare le misure di sicurezza. Si prega di pesare questo nelle considerazioni prima di continuare comunque.
