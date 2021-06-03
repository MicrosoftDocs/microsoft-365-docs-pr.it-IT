---
title: Revisione dell'amministratore per i messaggi segnalati
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Informazioni su come esaminare i messaggi segnalati e inviare commenti e suggerimenti agli utenti.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 619cd35b6a60f0d50aa6c13e4cad2b8d7ae947a8
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730965"
---
# <a name="admin-review-for-reported-messages"></a>Revisione dell'amministratore per i messaggi segnalati

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> Le informazioni contenute in questo articolo si riferiscono a un prodotto di anteprima che potrebbe essere sostanzialmente modificato prima che venga rilasciato commercialmente. Questo documento viene fornito solo a scopo di valutazione ed esplorazione.

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nelle Microsoft 365 con cassette postali di Exchange Online e Microsoft Defender per Office 365, gli amministratori possono ora inviare messaggi modello agli utenti finali dopo aver esaminato i messaggi segnalati. Questo può essere personalizzato per l'organizzazione e in base al verdetto dell'amministratore.

Questa funzionalità è progettata per fornire feedback agli utenti, ma non modifica i verdetti dei messaggi nel sistema. Per consentire a Microsoft di aggiornare e migliorare i filtri, è necessario inviare messaggi per l'analisi tramite [l'invio dell'amministratore.](admin-submission.md)

Sarà possibile contrassegnare e notificare agli utenti i risultati della revisione solo se il messaggio è stato segnalato come [falso positivo o falso negativo.](report-false-positives-and-false-negatives.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Per modificare la configurazione per gli invii di utenti, è necessario essere membri di uno dei gruppi di ruoli seguenti:
    - Gestione dell'organizzazione o amministratore della sicurezza [nel Centro sicurezza](permissions-microsoft-365-compliance-security.md).
    - Gestione organizzazione in [Exchange Online](/Exchange/permissions-exo/permissions-exo).

- Sarà inoltre necessario accedere alla Exchange Online PowerShell. Se l'account che si sta tentando di usare non ha accesso Exchange Online PowerShell, verrà visualizzato un errore che indica Specificare un indirizzo di posta elettronica nel *dominio.* Per ulteriori informazioni sull'abilitazione o disabilitazione dell'accesso Exchange Online PowerShell, vedere gli argomenti seguenti:
    - [Abilitare o disabilitare l'accesso Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell)
    - [Regole di Accesso client in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a>Configurare i messaggi utilizzati per inviare notifiche agli utenti

1. Nel centro [Microsoft 365 sicurezza](../defender/overview-security-center.md), andare a Criteri & **Criteri di** minaccia \> **Impostazioni** messaggio segnalato \> **dall'utente**.

2. Se si desidera specificare il nome visualizzato del mittente, selezionare la casella specifica l'indirizzo di posta elettronica di **Office 365** da utilizzare come mittente nella sezione **Notifiche** di posta elettronica per i risultati della revisione dell'amministratore e immettere il nome che si desidera utilizzare. Questo è l'indirizzo di posta elettronica che sarà visibile Outlook e a cui verranno indirizzate le risposte.

3. Se si desidera personalizzare uno dei modelli, fare clic su **Personalizza notifica tramite posta elettronica.** In questo riquadro a comparsa sarà possibile personalizzare solo gli elementi seguenti:
    - Phishing
    - Posta indesiderata
    - Nessuna minaccia trovata
    - Formazione sulla sensibilizzazione
    - Piè di pagina

4. Al termine, scegliere **Salva**. Per cancellare questi valori, fare clic **su Ignora** nella pagina Invii utente.
