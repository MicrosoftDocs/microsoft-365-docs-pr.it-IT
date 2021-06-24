---
title: Revisione amministratore per i messaggi segnalati
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
ms.openlocfilehash: a9fa6c890f0fa6098a2bb712f79ab82fc1edb68b
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108560"
---
# <a name="admin-review-for-reported-messages"></a>Revisione amministratore per i messaggi segnalati

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

- Per aprire il portale di Microsoft 365 Defender, andare alla pagina <https://security.microsoft.com/>. Per passare direttamente alla **pagina Invii,** usa <https://security.microsoft.com/reportsubmission> .

- Per modificare la configurazione per gli invii di utenti, è necessario essere membri di uno dei gruppi di ruoli seguenti:
  - Gestione organizzazione o amministratore della sicurezza [nel Microsoft 365 Defender .](permissions-microsoft-365-security-center.md)
  - Gestione organizzazione in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).

- Sarà inoltre necessario accedere a Exchange Online PowerShell. Se l'account che si sta tentando di usare non ha accesso Exchange Online PowerShell, verrà visualizzato un errore che indica Specificare un indirizzo di posta elettronica nel *dominio.* Per ulteriori informazioni sull'abilitazione o disabilitazione dell'accesso Exchange Online PowerShell, vedere gli argomenti seguenti:
  - [Abilitare o disabilitare l'accesso Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [Regole di Accesso client in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a>Configurare i messaggi utilizzati per inviare notifiche agli utenti

1. Nel portale Microsoft 365 Defender, andare a **Email & Collaboration** Policies & Rules \> **Threat** \> **policies** page \> **Others** section User \> **reported message settings**.

2. Nella  pagina Invii utente, se si desidera specificare il nome visualizzato del mittente, selezionare la casella specificare l'indirizzo di posta elettronica di **Office 365** da utilizzare come mittente nella sezione **Notifiche** di posta elettronica per i risultati della revisione dell'amministratore e immettere il nome che si desidera utilizzare. Questo è l'indirizzo di posta elettronica che sarà visibile Outlook e a cui verranno indirizzate le risposte.

3. Se si desidera personalizzare uno dei modelli, fare clic su **Personalizza notifica tramite posta elettronica.** In questo riquadro a comparsa sarà possibile personalizzare solo gli elementi seguenti:
    - Phishing
    - Posta indesiderata
    - Nessuna minaccia trovata
    - Formazione sulla sensibilizzazione
    - Piè di pagina

4. Al termine, scegliere **Salva**. Per cancellare questi valori, fare clic **su Ignora** nella pagina Invii utente.
