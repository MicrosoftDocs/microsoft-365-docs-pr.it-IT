---
title: Gestione dispositivi mobili in Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere in che modo Contoso usa Microsoft Intune in Microsoft 365 per le aziende per gestire i dispositivi e le app in esecuzione su di essi.
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753994"
---
# <a name="mobile-device-management-for-contoso"></a>Gestione dispositivi mobili in Contoso

Microsoft 365 per le aziende include Intune e un set di servizi di Azure che supportano la gestione e la sicurezza di dispositivi mobili e applicazioni.

Contoso ha molti dipendenti abilitati per dispositivi mobili. Alcuni hanno uffici nelle sedi di Contoso e altri non hanno uffici. Contoso aveva bisogno di un modo per abilitare la produttività dei dipendenti, ma mantenere protetti i dispositivi, i dati di Contoso archiviati in tali dispositivi e il comportamento delle applicazioni.

## <a name="plan"></a>Piano

Contoso ha identificato i seguenti casi d'uso di Intune per la gestione dei dispositivi mobili per Microsoft 365 per le aziende:

- Proteggere la posta elettronica e i dati di Exchange Online in modo che sia possibile accedervi in modo sicuro dai dispositivi mobili.
- Implementare un programma BYOD (Bring Your Own Device) per i dipendenti di Contoso.
- Rilasciare telefoni di proprietà dell'organizzazione e tablet condivisi di uso limitato ai dipendenti di Contoso.

Contoso non usa Intune per:

- Consentire ai dipendenti di accedere in modo sicuro a Microsoft 365 da un chiosco pubblico non gestito.
- Proteggere la posta elettronica e i dati locali in modo che sia possibile accedervi in modo sicuro dai dispositivi mobili, perché non sono presenti server Microsoft Exchange locali.

## <a name="deploy"></a>Distribuzione

Ecco come Contoso ha configurato l’infrastruttura di gestione dei dispositivi mobili:

- Impostare Intune come autorità di gestione dei dispositivi mobili (MDM) e usare Intune in Azure per amministrare il contenuto e gestire i dispositivi
- Sono stati creati gruppi di Azure Active Directory (Azure AD) per i dispositivi per le impostazioni di registrazione e Intune e i criteri di accesso condizionale basati su dispositivi

  Per ulteriori informazioni, vedere [Criteri di accesso condizionale di Contoso.](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)

- Ha abilitato la piattaforma dei dispositivi Apple per supportare i dipendenti con iPad, iMac e iPhone e iPhone di proprietà dell'azienda
- Ha creato criteri di termini e condizioni specifichi per Contoso, visualizzati durante l’installazione del Portale aziendale per i dispositivi mobili di Contoso
- Per i dispositivi non registrati, è stato implementato un set di criteri di gestione delle applicazioni mobili (MAM, Mobile Application Management) per richiedere l'autenticazione per l'accesso ai servizi di Microsoft 365
- Ha creato criteri di Intune che garantiscono:
  - App consentite.
  - Crittografia del dispositivo per impedire l'accesso non autorizzato.
  - PIN o password a sei cifre.
  - Periodo di inattività-timeout.
  - Protezione antivirus e malware e aggiornamenti delle firme con Windows Defender nei dispositivi Windows 10.
  - Aggiornamenti automatici nei dispositivi Windows 10 che includono gli aggiornamenti della sicurezza più recenti.
  - Push dei certificati nei dispositivi gestiti.
  - Una chiara separazione dei dati personali e aziendali. Gli utenti o amministratori possono cancellare in modo selettivo i dati aziendali dal dispositivo, senza modificare i dati personali, ad esempio immagini, account di posta elettronica personale e file personali.

Contoso ha registrato PC e smartphone e tablet di proprietà dell'azienda aggiungendoli ai gruppi di dispositivi Intune appropriati. Hanno inoltre creato un programma BYOD per i dipendenti per registrare i propri dispositivi personali. I dispositivi registrati ricevono i criteri di Intune, che determinano dispositivi gestiti e protetti e le relative applicazioni. I dispositivi non registrati dispongono di criteri maM (Mobile Application Management) che specificano le applicazioni consentite.

Ecco l'architettura di distribuzione della gestione dei dispositivi mobili contoso.

![Infrastruttura di distribuzione per la gestione dei dispositivi mobili contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a>Passaggio successivo

Informazioni su come Contoso usa le [funzionalità](contoso-info-protect.md) di protezione delle informazioni di Microsoft 365 per le aziende per classificare, identificare e proteggere le risorse digitali cruciali all'interno dell'organizzazione.

## <a name="see-also"></a>Vedere anche

[Gestione dei dispositivi per Microsoft 365](device-management-roadmap-microsoft-365.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Guide dei laboratori di testing](m365-enterprise-test-lab-guides.md)

