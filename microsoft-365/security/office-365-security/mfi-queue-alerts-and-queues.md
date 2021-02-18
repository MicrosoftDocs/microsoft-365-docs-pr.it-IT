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
description: Gli amministratori possono imparare a usare il widget Code nel dashboard del flusso di posta nel Centro sicurezza & conformità per monitorare il flusso di posta non riuscito alle organizzazioni locali o partner tramite connettori in uscita.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ca8ee5ea37fa5a63b8035572059e419c400d66f3
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289438"
---
# <a name="queues-insight-in-the-security--compliance-center"></a>Informazioni dettagliate sulle code nel Centro sicurezza & conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Quando non è possibile inviare messaggi dall'organizzazione ai server di posta elettronica locali o partner tramite connettori, i messaggi vengono accodati in Microsoft 365. Esempi comuni che causano questa condizione sono:

- Il connettore non è configurato correttamente.
- Nell'ambiente locale sono state apportate modifiche alla rete o al firewall.

Microsoft 365 continuerà a ripetere il recapito per 24 ore. Dopo 24 ore, i messaggi scadranno e verranno restituiti ai mittenti nei rapporti di mancato recapito (noti anche come rapporti di mancato recapito o notifiche di mancato recapito).

Se il volume di posta elettronica in coda supera la soglia predefinita (il valore predefinito è 200 messaggi), le informazioni sono disponibili nei percorsi seguenti:

- Informazioni **dettagliate sulle** code nel [dashboard del flusso di](mail-flow-insights-v2.md) posta nel Centro sicurezza [& conformità.](https://protection.office.com) Per ulteriori informazioni, vedere le informazioni [dettagliate sulle code nella sezione Dashboard del flusso di posta](#queues-insight-in-the-mail-flow-dashboard) in questo articolo.

- Un avviso viene visualizzato in Avvisi recenti **nel** dashboard avvisi nel Centro [sicurezza & conformità](https://protection.office.com) ( Dashboard **degli** avvisi \>  o <https://protection.office.com/alertsdashboard> ).

  ![Avvisi recenti nel dashboard avvisi nel Centro sicurezza & conformità](../../media/mfi-queued-messages-alert.png)

- Gli amministratori riceveranno una notifica tramite posta elettronica in base alla configurazione del criterio di avviso predefinito **denominato Messaggi ritardati.** Per configurare le impostazioni di notifica per questo avviso, vedi la sezione successiva.

  Per ulteriori informazioni sui criteri di avviso, vedere Criteri di avviso [nel Centro sicurezza & conformità.](../../compliance/alert-policies.md)

## <a name="customize-queue-alerts"></a>Personalizzare gli avvisi delle code

1. Nel Centro [sicurezza & conformità](https://protection.office.com)passare a Criteri **avvisi** o \>  aprire <https://protection.office.com/alertpolicies> .

2. Nella pagina **Criteri di** avviso individuare e selezionare il criterio denominato **Messaggi ritardati.**

3. Nel **riquadro a comparsa Messaggio ritardato** che si apre, puoi attivare o disattivare l'avviso e configurare le impostazioni di notifica.

   ![I messaggi sono stati ritardati nei dettagli dei criteri di avviso nel Centro sicurezza & conformità](../../media/mfi-queued-messages-alert-policy.png)

   - **Stato:** è possibile attivare o disattivare l'avviso.

   - **Destinatari di posta elettronica** **e limite di notifica giornaliero**: fare clic **su Modifica** per configurare le impostazioni seguenti:

4. Per configurare le impostazioni di notifica, fare clic su **Modifica.** Nel riquadro **a comparsa** Modifica criterio visualizzato configurare le impostazioni seguenti:

   - **Inviare notifiche tramite posta** elettronica : il valore predefinito è on.
   - **Destinatari di posta** elettronica: il valore predefinito è **TenantAdmins.**
   - **Limite di notifica giornaliero**: il valore predefinito è **No limit.**
   - **Soglia**: il valore predefinito è 200.

   ![Le impostazioni di notifica nei messaggi sono state ritardate nei dettagli dei criteri di avviso nel Centro sicurezza & conformità](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. Al termine, fare clic su **Salva** e **chiudi.**

## <a name="queues-insight-in-the-mail-flow-dashboard"></a>Informazioni dettagliate sulle code nel dashboard del flusso di posta

Anche se il volume dei messaggi in coda non ha superato la  soglia e ha generato un avviso, è comunque possibile utilizzare le informazioni dettagliate sulle code nel [dashboard](mail-flow-insights-v2.md) del flusso di posta per visualizzare i messaggi che sono stati accodati per più di un'ora ed eseguire un'azione prima che il numero di messaggi in coda diventi troppo grande.

![Widget Code nel dashboard del flusso di posta nel Centro sicurezza & conformità](../../media/mfi-queues-widget.png)

Se si fa clic sul numero di messaggi nel widget, viene visualizzato un **riquadro** a comparsa Messaggi in coda con le informazioni seguenti:

- **Numero di messaggi in coda**
- **Nome connettore**: Fare clic sul nome del connettore per gestire il connettore nell'interfaccia di amministrazione di Exchange ( EAC).
- **Ora di inizio coda**
- **Messaggi meno recenti scaduti**
- **Server di destinazione**
- **Ultimo indirizzo IP**
- **Ultimo errore**
- **Come risolvere il problema:** sono disponibili problemi comuni e soluzioni. If is a **Fix it now** link is available, click it to fix the problem. In caso contrario, fare clic sui collegamenti disponibili per ulteriori informazioni sull'errore e sulle possibili soluzioni.

![Dettagli dopo aver fatto clic su Informazioni dettagliate sulle code nel dashboard del flusso di posta](../../media/mfi-queues-details.png)

Lo stesso riquadro a comparsa viene visualizzato dopo aver fatto clic **su** Visualizza coda nei dettagli di un avviso Di messaggi **in** ritardo.

![I messaggi sono stati ritardati nei dettagli dell'avviso nel Centro sicurezza & conformità](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a>Vedere anche

Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)
