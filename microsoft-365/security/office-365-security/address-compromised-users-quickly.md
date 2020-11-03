---
title: Indirizzare gli account utente compromessi con indagini e risposte automatiche
keywords: ARIA, autoIR, ATP, automatizzato, investigazione, risposta, correzione, minacce, avanzato, minaccia, protezione, compromesso
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Informazioni su come velocizzare il processo di rilevamento e indirizzamento degli account utente compromessi con le funzionalità di analisi e risposta automatizzate in Microsoft Defender per Office 365 piano 2.
ms.openlocfilehash: 0da065bea17796d09de771a767991804afb5335b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844597"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>Indirizzare gli account utente compromessi con indagini e risposte automatiche

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender per Office 365 piano 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2) include potenti funzionalità [di analisi e risposta automatizzate](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (Air). Tali funzionalità sono in grado di salvare il team di operazioni di sicurezza molto tempo e lo sforzo per gestire le minacce. Microsoft continua a migliorare le funzionalità di sicurezza. Recentemente, le funzionalità AEREe sono state migliorate per includere un playbook di sicurezza degli utenti compromesso (attualmente in anteprima). Leggere questo articolo per ulteriori informazioni sul PlayBook di sicurezza degli utenti compromessi. Per ulteriori informazioni, vedere il post del Blog [velocizzare il tempo necessario per rilevare e rispondere al compromesso degli utenti e limitare l'ambito di violazione con Microsoft Defender per Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) .

![Analisi automatizzata per un utente compromesso](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

Il PlayBook di sicurezza utente compromesso consente al team di sicurezza dell'organizzazione di:

- Velocizzare il rilevamento degli account utente compromessi;

- Limitare l'ambito di una violazione quando un account è compromesso; e

- Rispondere agli utenti compromessi in modo più efficace ed efficiente.

## <a name="compromised-user-alerts"></a>Avvisi degli utenti compromessi

Quando un account utente viene compromesso, si verificano comportamenti atipici o anomali. Ad esempio, i messaggi di phishing e di posta indesiderata possono essere inviati internamente da un account utente attendibile. Defender per Office 365 è in grado di rilevare tali anomalie nei modelli di posta elettronica e attività di collaborazione all'interno di Office 365. In questo caso, gli avvisi vengono attivati e il processo di attenuazione delle minacce inizia.

Ad esempio, ecco un avviso che è stato attivato a causa dell'invio di messaggi di posta elettronica sospetti:

![Avviso attivato a causa dell'invio di messaggi di posta elettronica sospetti](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

Di seguito è riportato un esempio di avviso che è stato attivato quando è stato raggiunto un limite di invio per un utente:

![Avviso attivato tramite l'invio del limite raggiunto](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>Esaminare e rispondere a un utente compromesso

Quando un account utente viene compromesso, vengono attivati gli avvisi. In alcuni casi, l'account utente viene bloccato e impedito l'invio di ulteriori messaggi di posta elettronica fino a quando il problema non viene risolto dal team di operazioni di sicurezza dell'organizzazione. In altri casi, viene avviata un'indagine automatizzata che può provocare le azioni consigliate che il team di sicurezza deve eseguire.

- [Visualizzazione e analisi degli utenti con restrizioni](#view-and-investigate-restricted-users)

- [Visualizzare i dettagli sulle indagini automatizzate](#view-details-about-automated-investigations)

> [!IMPORTANT]
> È necessario disporre delle autorizzazioni appropriate per eseguire le attività seguenti. Vedere le [autorizzazioni necessarie per utilizzare le funzionalità aeree](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities).

### <a name="view-and-investigate-restricted-users"></a>Visualizzazione e analisi degli utenti con restrizioni

Sono disponibili alcune opzioni per l'esplorazione di un elenco di utenti con restrizioni. Ad esempio, nel centro sicurezza & conformità, è possibile accedere a utenti con restrizioni di verifica di **gestione delle minacce**  >  **Review**  >  **Restricted Users**. Nella procedura seguente viene descritta la struttura di spostamento tramite il dashboard **avvisi** , che consente di visualizzare diversi tipi di avvisi che potrebbero essere stati attivati.

1. Andare su [https://protection.office.com](https://protection.office.com) ed eseguire l'accesso.

2. Nel riquadro di spostamento, scegliere **Alerts**  >  **Dashboard** avvisi.

3. Nell' **altro widget avvisi** scegliere utenti con **restrizioni**.

   ![Altri widget avvisi](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   Verrà aperto l'elenco degli utenti con restrizioni.<br/>![Utenti con restrizioni in Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. Selezionare un account utente nell'elenco per visualizzare i dettagli e intraprendere un'azione, ad esempio [il rilascio dell'utente con restrizioni](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam).

### <a name="view-details-about-automated-investigations"></a>Visualizzare i dettagli sulle indagini automatizzate

Dopo aver avviato un'indagine automatizzata, è possibile visualizzare i dettagli e i risultati nel centro sicurezza & conformità. Andare a indagini sulla **gestione delle minacce**  >  **Investigations** e quindi selezionare un'analisi per visualizzarne i dettagli.

Per ulteriori informazioni, vedere [visualizzare i dettagli di un'indagine](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results).

## <a name="keep-the-following-points-in-mind"></a>Tenere in considerazione i seguenti punti

- **Rimanere al di sopra degli avvisi**. Come si sa, più a lungo non viene rilevato un compromesso, maggiore è il potenziale di impatto e costo diffuso per l'organizzazione, i clienti e i partner. Il rilevamento precoce e la risposta tempestiva sono fondamentali per attenuare le minacce e, soprattutto, quando l'account di un utente viene compromesso.

- **L'automazione fornisce assistenza, ma non sostituisce il team delle operazioni di sicurezza**. L'analisi automatizzata e le funzionalità di risposta possono rilevare un utente compromesso all'inizio, ma il team delle operazioni di sicurezza avrà probabilmente bisogno di intraprendere indagini e correzioni. Serve aiuto? Vedere [operazioni di revisione e approvazione](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air#review-and-approve-actions).

- **Non fare affidamento su un avviso di accesso sospetto come solo indicatore**. Quando un account utente viene compromesso, potrebbe essere attivato o meno un avviso di accesso sospetto. A volte è la serie di attività che si verificano dopo che un account è stato compromesso che attiva un avviso. Per ulteriori informazioni sugli avvisi Vedere [criteri di avviso](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).

## <a name="next-steps"></a>Passaggi successivi

- [Esaminare le autorizzazioni necessarie per l'utilizzo delle funzionalità AEREe](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities)

- [Trovare e indagare messaggi di posta elettronica dannosi in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide)

- [Informazioni su AIR in Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Visitare la Guida di orientamento di Microsoft 365 per vedere cosa succederà tra breve e in uscita](https://www.microsoft.com/microsoft-365/roadmap?filters=)

