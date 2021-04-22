---
title: Risolvere gli account utente compromessi con analisi e risposta automatizzate
keywords: AIR, autoIR, Microsoft Defender for Endpoint, automatizzato, indagine, risposta, correzione, minacce, avanzate, minaccia, protezione, compromessa
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Informazioni su come velocizzare il processo di rilevamento e gestione degli account utente compromessi con funzionalità di analisi e risposta automatizzate in Microsoft Defender per Office 365 Piano 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c500221a10c00cc3b8d9d99c102ce8ec54fa2a48
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934694"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>Risolvere gli account utente compromessi con analisi e risposta automatizzate

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


[Microsoft Defender per Office 365 Piano 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) include potenti funzionalità di analisi e risposta [automatizzate](office-365-air.md) (AIR). Tali funzionalità possono risparmiare tempo e fatica al team delle operazioni di sicurezza per affrontare le minacce. Microsoft continua a migliorare le funzionalità di sicurezza. Di recente, le funzionalità AIR sono state migliorate per includere un playbook di sicurezza degli utenti compromesso (attualmente in anteprima). Leggi questo articolo per altre informazioni sul playbook sulla sicurezza degli utenti compromesso. Per ulteriori dettagli, vedere il post di blog Velocizzare il tempo necessario per rilevare e rispondere alla compromissione degli utenti e limitare l'ambito di violazione con [Microsoft Defender per Office 365.](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053)

![Indagine automatizzata per un utente compromesso](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

Il playbook sulla sicurezza degli utenti compromesso consente al team di sicurezza dell'organizzazione di:

- Velocizzare il rilevamento degli account utente compromessi;

- Limitare l'ambito di una violazione quando un account viene compromesso; e

- Rispondere agli utenti compromessi in modo più efficace ed efficiente.

## <a name="compromised-user-alerts"></a>Avvisi utente compromessi

Quando un account utente viene compromesso, si verificano comportamenti atipici o anomali. Ad esempio, i messaggi di phishing e posta indesiderata potrebbero essere inviati internamente da un account utente attendibile. Defender per Office 365 è in grado di rilevare tali anomalie nei modelli di posta elettronica e nell'attività di collaborazione in Office 365. In questo caso, vengono attivati gli avvisi e inizia il processo di mitigazione delle minacce.

Ad esempio, ecco un avviso che è stato attivato a causa di un invio di posta elettronica sospetto:

![Avviso attivato a causa dell'invio di posta elettronica sospetto](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

Ecco un esempio di avviso che è stato attivato quando è stato raggiunto un limite di invio per un utente:

![Avviso attivato dal limite di invio raggiunto](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>Analizzare e rispondere a un utente compromesso

Quando un account utente viene compromesso, vengono attivati gli avvisi. In alcuni casi, l'account utente viene bloccato e non può inviare ulteriori messaggi di posta elettronica fino a quando il problema non viene risolto dal team delle operazioni di sicurezza dell'organizzazione. In altri casi, viene avviata un'indagine automatizzata che può comportare azioni consigliate da parte del team di sicurezza.

- [Visualizzare e analizzare gli utenti con restrizioni](#view-and-investigate-restricted-users)

- [Visualizzare i dettagli sulle indagini automatizzate](#view-details-about-automated-investigations)

> [!IMPORTANT]
> Per eseguire le attività seguenti, è necessario disporre delle autorizzazioni appropriate. Vedere [Autorizzazioni necessarie per l'utilizzo delle funzionalità AIR.](office-365-air.md#required-permissions-to-use-air-capabilities)

### <a name="view-and-investigate-restricted-users"></a>Visualizzare e analizzare gli utenti con restrizioni

Sono disponibili alcune opzioni per passare a un elenco di utenti con restrizioni. Ad esempio, nel Centro sicurezza & conformità, è possibile passare a **Gestione** delle minacce \> **Rivedere** Utenti \> **con restrizioni**. Nella procedura seguente viene descritto lo spostamento tramite il **dashboard** Avvisi, che rappresenta un ottimo modo per visualizzare vari tipi di avvisi che potrebbero essere stati attivati.

1. Andare su <https://protection.office.com> ed eseguire l'accesso.

2. Nel riquadro di spostamento scegliere **Dashboard** \> **avvisi.**

3. Nel widget **Altri avvisi** scegliere Utenti **con restrizioni.**

   ![Widget Altri avvisi](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   Verrà aperto l'elenco degli utenti con restrizioni.

   ![Utenti con restrizioni in Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. Selezionare un account utente nell'elenco per visualizzare i dettagli ed eseguire azioni, ad esempio [il rilascio dell'utente con restrizioni.](removing-user-from-restricted-users-portal-after-spam.md)

### <a name="view-details-about-automated-investigations"></a>Visualizzare i dettagli sulle indagini automatizzate

Una volta avviata un'indagine automatizzata, è possibile visualizzarne i dettagli e i risultati nel Centro sicurezza & conformità. Passare a **Indagini sulla gestione delle** \> **minacce** e quindi selezionare un'indagine per visualizzarne i dettagli.

Per ulteriori informazioni, vedere [Visualizzare i dettagli di un'indagine.](air-view-investigation-results.md)

## <a name="keep-the-following-points-in-mind"></a>Tenere presenti i punti seguenti

- **Tieniti al primo piano degli avvisi.** Come sai, più a lungo un compromesso non viene rilevato, maggiore è il potenziale di un impatto diffuso e dei costi per l'organizzazione, i clienti e i partner. Il rilevamento precoce e la risposta tempestiva sono fondamentali per ridurre le minacce e soprattutto quando l'account di un utente viene compromesso.

- **L'automazione assiste, ma non sostituisce, il team delle operazioni di sicurezza.** Le funzionalità di analisi e risposta automatizzate possono rilevare un utente compromesso nelle prime fasi, ma il team delle operazioni di sicurezza dovrà probabilmente impegnarsi ed eseguire alcune indagini e correzioni. Serve aiuto per questo? Vedi [Rivedere e approvare le azioni.](air-review-approve-pending-completed-actions.md)

- **Non fare affidamento su un avviso di accesso sospetto come unico indicatore.** Quando un account utente viene compromesso, potrebbe o meno attivare un avviso di accesso sospetto. A volte è la serie di attività che si verificano dopo la compromissione di un account che attiva un avviso. Per saperne di più sugli avvisi, vedere Vedere [Criteri di avviso](../../compliance/alert-policies.md).

## <a name="next-steps"></a>Passaggi successivi

- [Esaminare le autorizzazioni necessarie per l'utilizzo delle funzionalità AIR](office-365-air.md#required-permissions-to-use-air-capabilities)

- [Trovare e analizzare la posta elettronica dannosa in Office 365](investigate-malicious-email-that-was-delivered.md)

- [Informazioni su AIR in Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Visitare la roadmap di Microsoft 365 per vedere cosa sarà disponibile a breve e implementazione](https://www.microsoft.com/microsoft-365/roadmap?filters=)