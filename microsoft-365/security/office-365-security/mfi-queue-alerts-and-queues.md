---
title: Informazioni dettagliate sulle code nel dashboard del flusso di posta
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Gli amministratori possono imparare a usare il widget Code nel dashboard del flusso di posta nel Centro sicurezza & conformità per monitorare il flusso di posta non riuscito per le organizzazioni locali o partner tramite connettori in uscita.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 14cadd0e8611fbbc65c3bdc9849beebf3a3eb34d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206943"
---
# <a name="queues-insight-in-the-security--compliance-center"></a>Informazioni dettagliate sulle code nel Centro sicurezza & conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Quando non è possibile inviare messaggi dall'organizzazione ai server di posta elettronica locali o partner utilizzando i connettori, i messaggi vengono accodati in Microsoft 365. Esempi comuni che causano questa condizione sono:

- Il connettore non è configurato correttamente.
- Sono state apportate modifiche alla rete o al firewall nell'ambiente locale.

Microsoft 365 continuerà a ripetere il recapito per 24 ore. Dopo 24 ore, i messaggi scadranno e verranno restituiti ai mittenti nei rapporti di mancato recapito (noti anche come rapporti di mancato recapito o messaggi di mancato recapito).

Se il volume di posta elettronica in coda supera la soglia predefinita (il valore predefinito è 200 messaggi), le informazioni sono disponibili nelle posizioni seguenti:

- Informazioni **dettagliate** sulle code nel [dashboard del flusso di](mail-flow-insights-v2.md) posta nel Centro sicurezza & [conformità](https://protection.office.com). Per ulteriori informazioni, vedere la sezione Informazioni dettagliate sulle [code nel dashboard del flusso di](#queues-insight-in-the-mail-flow-dashboard) posta in questo articolo.

- Un avviso viene visualizzato in **Avvisi** recenti nel dashboard Avvisi nel Centro [sicurezza & conformità](https://protection.office.com) ( Dashboard **avvisi** \>  o <https://protection.office.com/alertsdashboard> ).

  ![Avvisi recenti nel dashboard Avvisi nel Centro sicurezza & conformità](../../media/mfi-queued-messages-alert.png)

- Gli amministratori riceveranno una notifica tramite posta elettronica in base alla configurazione del criterio di avviso predefinito denominato **Messaggi ritardati.** Per configurare le impostazioni di notifica per questo avviso, vedere la sezione successiva.

  Per ulteriori informazioni sui criteri di avviso, vedere [Alert policies in the Security & Compliance Center.](../../compliance/alert-policies.md)

## <a name="customize-queue-alerts"></a>Personalizzare gli avvisi delle code

1. Nel Centro [sicurezza & conformità](https://protection.office.com)passare a **Avvisi** Criteri \> **di avviso** o aprire <https://protection.office.com/alertpolicies> .

2. Nella pagina **Criteri di** avviso individuare e selezionare il criterio denominato **Messaggi ritardati.**

3. Nel **riquadro a comparsa Messaggio in ritardo** che si apre, puoi attivare o disattivare l'avviso e configurare le impostazioni di notifica.

   ![I messaggi sono stati ritardati nei dettagli dei criteri di avviso nel Centro sicurezza & conformità](../../media/mfi-queued-messages-alert-policy.png)

   - **Stato:** è possibile attivare o disattivare l'avviso.

   - **Destinatari di posta** elettronica **e Limite notifiche giornaliere**: fare clic **su Modifica** per configurare le impostazioni seguenti:

4. Per configurare le impostazioni di notifica, fare clic su **Modifica.** Nel riquadro **a comparsa** Modifica criterio visualizzato configurare le impostazioni seguenti:

   - **Invia notifiche tramite posta** elettronica : il valore predefinito è on.
   - **Destinatari di posta** elettronica : il valore predefinito è **TenantAdmins.**
   - **Limite notifiche giornaliere**: il valore predefinito è **No limit**.
   - **Soglia**: il valore predefinito è 200.

   ![Le impostazioni di notifica nei criteri di avviso Messaggi sono stati ritardati nel Centro sicurezza & conformità](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. Al termine, fare clic su **Salva** e **chiudi.**

## <a name="queues-insight-in-the-mail-flow-dashboard"></a>Informazioni dettagliate sulle code nel dashboard del flusso di posta

Anche se il volume dei messaggi in coda non ha superato la  soglia e generato un avviso, è comunque possibile utilizzare le informazioni dettagliate sulle code nel [dashboard](mail-flow-insights-v2.md) del flusso di posta per visualizzare i messaggi che sono stati accodati per più di un'ora ed eseguire un'azione prima che il numero di messaggi in coda diventi troppo grande.

![Widget Code nel dashboard del flusso di posta nel Centro sicurezza & conformità](../../media/mfi-queues-widget.png)

Se si fa clic sul numero di messaggi nel widget, viene visualizzato un riquadro **a** comparsa Messaggi accodati con le informazioni seguenti:

- **Numero di messaggi in coda**
- **Nome connettore**: fare clic sul nome del connettore per gestire il connettore nell'interfaccia di amministrazione di Exchange (EAC).
- **Ora di inizio coda**
- **Messaggi meno recenti scaduti**
- **Server di destinazione**
- **Ultimo indirizzo IP**
- **Ultimo errore**
- **Come risolvere:** sono disponibili problemi e soluzioni comuni. If is a **Fix it now** link is available, click it to fix the problem. In caso contrario, fare clic sui collegamenti disponibili per ulteriori informazioni sull'errore e sulle possibili soluzioni.

![Dettagli dopo aver fatto clic su Informazioni dettagliate sulle code nel dashboard del flusso di posta](../../media/mfi-queues-details.png)

Lo stesso riquadro a comparsa viene visualizzato dopo aver fatto clic **su Visualizza** coda nei dettagli di un avviso **Messaggi ritardati.**

![I messaggi sono stati ritardati dettagli dell'avviso nel Centro sicurezza & conformità](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a>Vedere anche

Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)
