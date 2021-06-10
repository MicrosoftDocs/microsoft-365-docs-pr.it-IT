---
title: Informazioni dettagliate sul flusso di posta in uscita e in ingresso nel dashboard del flusso di posta
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Gli amministratori possono ottenere informazioni sulle informazioni dettagliate sul flusso di posta in uscita e in ingresso nel dashboard del flusso di posta nel Centro sicurezza & conformità.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4a3117223e466a4a7aad7edf25ecdbcf0a3de719
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205295"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>Informazioni dettagliate sul flusso di posta in uscita e in ingresso nel Centro sicurezza & conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Le **informazioni dettagliate** sul flusso di posta [in](https://protection.office.com) uscita e in ingresso nel [dashboard](mail-flow-insights-v2.md) del flusso di posta nel Centro sicurezza e conformità & combina le informazioni del report connettore e del precedente [report](view-mail-flow-reports.md#connector-report) di panoramica **di TLS** in un'unica posizione.

Il widget visualizza la crittografia TLS utilizzata per la connessione quando i messaggi vengono recapitati da e verso l'organizzazione. Le connessioni stabilite con altri servizi di posta elettronica vengono crittografate da TLS quando TLS viene offerto da entrambi i lati. Il widget offre uno snapshot dell'ultima settimana del flusso di posta.

![Widget Flusso di posta in uscita e in ingresso nel dashboard del flusso di posta nel Centro sicurezza & conformità](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

Le informazioni nel widget sono correlate ai connettori e alla protezione dei messaggi TLS in Microsoft 365. Per ulteriori informazioni, vedere gli argomenti riportati di seguito:

- [Configurare il flusso di posta elettronica usando i connettori](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [Modalità d'uso di TLS in Exchange Online per proteggere le connessioni di posta elettronica](../../compliance/exchange-online-uses-tls-to-secure-email-connections.md)
- [Informazioni di riferimento tecniche sulla crittografia in Microsoft 365](../../compliance/technical-reference-details-about-encryption.md)

## <a name="message-protected-in-transit-by-tls"></a>Messaggio protetto in transito (tramite TLS)

Quando fai clic **su Visualizza dettagli** nel widget, il riquadro a comparsa Messaggio protetto in transito **(tramite TLS)** mostra la protezione TLS per i messaggi che entrano e lasciano l'organizzazione.

![Riquadro a comparsa Messaggi protetti in transito (da TLS) che viene visualizzato dopo aver fatto clic su Visualizza dettagli nel widget Posta elettronica in uscita e in ingresso](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

Attualmente, TLS 1.2 è la versione più sicura di TLS offerta da Microsoft 365. Spesso, è necessario conoscere la crittografia TLS utilizzata per i controlli di conformità. È probabile che non si abbia una relazione diretta con la maggior parte dei server di posta elettronica di origine e di destinazione (non si è proprietari di tali server e nemmeno con Microsoft), quindi non sono disponibili molte opzioni per migliorare la crittografia TLS utilizzata da tali server.

Tuttavia, è possibile utilizzare [i connettori](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) per garantire la migliore protezione TLS disponibile per i messaggi inviati tra i server di posta elettronica e Microsoft 365. Il flusso di posta tra Microsoft 365 e i server o i server di posta elettronica che appartengono ai partner è spesso più importante e sensibile dei messaggi normali, quindi è necessario applicare maggiore sicurezza e vigilanza a tali messaggi.

È possibile aggiornare o correggere i propri server di posta elettronica per migliorare la crittografia TLS in uso o contattare i partner per eseguire la stessa operazione. Il **rapporto connettore** visualizza sia il volume del flusso di posta che la crittografia TLS per i messaggi che utilizzano i connettori Microsoft 365 messaggi.

È possibile fare clic sul **collegamento Rapporto** connettore per passare al [report Connettore.](view-mail-flow-reports.md#connector-report) Se la condizione associata è stata rilevata, nella pagina **del report Connettore** potrebbero essere disponibili le informazioni seguenti:

- **Connettore partner in ingresso che vede un flusso di posta TLS1.0 significativo**
- **Connettore OnPremises in ingresso che vede un flusso di posta TLS1.0 significativo**

Per le connessioni TLS 1.0, è necessario aggiornare o risolvere il server di posta elettronica o il server del partner per evitare eventuali problemi quando il supporto di TLS 1.0 è deprecato in Microsoft 365.

## <a name="see-also"></a>Vedere anche

Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)