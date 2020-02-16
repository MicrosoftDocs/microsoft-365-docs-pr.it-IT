---
title: Avvisi di coda e code
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Gli amministratori possono ottenere informazioni sugli avvisi e le code in coda nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance.
ms.openlocfilehash: bc777e3c9764987dc72aa0407f19618bc26f7528
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42082759"
---
# <a name="queue-alerts-and-queues"></a>Avvisi di coda e code

## <a name="queue-alerts"></a>Avvisi di coda

Quando i messaggi non possono essere inviati dall'organizzazione di Office 365 ai server di posta elettronica locali o partner utilizzando i connettori, i messaggi vengono accodati in Office 365. Esempi comuni che causano questa condizione sono:

- Il connettore non è configurato correttamente.

- Sono state apportate modifiche alla rete o al firewall nell'ambiente locale.

Office 365 continuerà a essere recapitato per 24 ore. Dopo 24 ore, i messaggi scadranno e verranno restituiti ai mittenti nei rapporti di mancato recapito (noti anche come NDR o messaggi di rimbalzo).

Se il volume della posta in coda supera la soglia predefinita (il valore predefinito è 2000 messaggi), gli avvisi saranno disponibili nel dashboard del flusso di posta in **avvisi recenti**e gli amministratori riceveranno una notifica tramite posta elettronica (per il loro indirizzo di posta elettronica alternativo). Per configurare la soglia di avviso, il limite di notifica giornaliero e/o i destinatari dell'avviso, vedere la sezione **personalizzare gli avvisi di coda** riportati di seguito.

![Avvisi di coda nell'area avvisi recenti del dashboard del flusso di posta elettronica nel centro sicurezza & conformità](../../media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a>Personalizzare gli avvisi delle code

Informazioni sul flusso di posta per creare un criterio di avviso denominato **messaggi sono stati ritardati** (la casella di controllo **Invia notifiche tramite posta elettronica** nella schermata di esempio seguente) rilevata nei **criteri di avviso** **avvisi** \> . È possibile modificare la soglia e i destinatari degli avvisi facendo clic sul criterio.

![Spostamento avvisi](../../media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

Verrà visualizzato un nuovo Blade informazioni sui criteri, è ora possibile fare clic su **modifica criterio**.

![Criterio di modifica ](../../media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

Il Blade delle informazioni verrà modificato nel **criterio di modifica**. Ora è possibile modificare i destinatari per la posta elettronica di avviso, il limite per il numero di notifiche inviate al giorno e la soglia minima per attivare l'avviso (200 o più).

![Modifica del Blade del criterio](../../media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a>Dettagli avviso coda

Quando si fa clic sull'avviso, i dettagli degli avvisi vengono visualizzati in un riquadro a comparsa.

![Selezionare un avviso di coda nell'area avvisi recenti del dashboard del flusso di posta elettronica nel centro sicurezza & conformità](../../media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![Riquadro a comparsa Dettagli avviso coda nel centro sicurezza & conformità](../../media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

È possibile fare clic su **Visualizza coda** nei dettagli degli avvisi per visualizzare i dettagli della coda, i problemi e i collegamenti alle correzioni disponibili in un nuovo riquadro a comparsa.

![Riquadro a comparsa Dettagli avviso coda nel centro sicurezza & conformità](../../media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![Visualizza coda nei dettagli degli avvisi](../../media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a>Code

Anche se il volume del messaggio in coda non ha superato la soglia, è comunque possibile utilizzare l'area **Code** del dashboard del flusso di posta per visualizzare i messaggi che sono stati accodati per più di un'ora. È possibile utilizzare l'area **Code** per monitorare il numero di messaggi in coda (il valore 0 indica che il flusso di posta è OK) ed eseguire un'azione prima che il numero di messaggi in coda diventi troppo elevato.

![Code nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance](../../media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

Quando si fa clic sul numero di messaggi in coda nelle **Code**, i dettagli della coda e le indicazioni su come risolvere il problema verranno visualizzati in un riquadro a comparsa (lo stesso riquadro a comparsa visualizzato dopo aver fatto clic su **Visualizza coda** nei dettagli di un avviso di coda).

![Dettagli coda](../../media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="see-also"></a>Vedere anche

Per ulteriori informazioni su altre comprensioni del flusso di posta nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).
