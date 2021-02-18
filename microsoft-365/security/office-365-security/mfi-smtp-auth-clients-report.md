---
title: Informazioni dettagliate e report dei client di autenticazione SMTP nel dashboard del flusso di posta
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a usare le informazioni dettagliate e il report di autenticazione SMTP nel dashboard del flusso di posta nel Centro sicurezza & conformità per monitorare i mittenti di posta elettronica nell'organizzazione che utilizzano SMTP autenticato (SMTP AUTH) per inviare messaggi di posta elettronica.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9050fd2c1bc3863a3bd78190cd5b27fda018479e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287798"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a>Informazioni dettagliate e report dei client di autenticazione SMTP nel Centro sicurezza & conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Le informazioni dettagliate sui client di autenticazione **SMTP** nel [dashboard](mail-flow-insights-v2.md) del flusso di posta e nel report dei client di autenticazione [SMTP](#smtp-auth-clients-report) associati nel Centro sicurezza [&](https://protection.office.com) conformità evidenziano l'uso del protocollo di invio al client SMTP AUTH da parte degli utenti o degli account di sistema nell'organizzazione. Questo protocollo legacy (che usa l'endpoint smtp.office365.com) offre solo l'autenticazione di base ed è soggetto all'uso da parte di account compromessi per inviare posta elettronica. Le informazioni dettagliate e il report consentono di verificare la presenza di attività insolite per gli invii di posta elettronica SMTP AUTH. Vengono inoltre mostrati i dati sull'utilizzo di TLS per client o dispositivi che utilizzano SMTP AUTH.

Il widget indica il numero di utenti o account di servizio che hanno utilizzato il protocollo di autenticazione SMTP negli ultimi 7 giorni.

![Widget Client di autenticazione SMTP nel dashboard del flusso di posta nel Centro sicurezza & conformità](../../media/mfi-smtp-auth-clients-report-widget.png)

Se si fa clic sul numero di messaggi nel widget, viene visualizzato un riquadro a comparsa **client di autenticazione SMTP.** Il riquadro a comparsa offre una visualizzazione aggregata dell'utilizzo di TLS e dei volumi dell'ultima settimana.

![Riquadro a comparsa Dettagli dopo aver fatto clic sul widget Client di autenticazione SMTP nel dashboard del flusso di posta](../../media/mfi-smtp-auth-clients-report-details.png)

È possibile fare clic sul collegamento al rapporto dei client di autenticazione **SMTP** per passare al report dei client di autenticazione SMTP, come descritto nella sezione successiva.

## <a name="smtp-auth-clients-report"></a>Report sui client di autenticazione SMTP

### <a name="report-view-for-the-smtp-auth-clients-report"></a>Visualizzazione rapporto per il report dei client di autenticazione SMTP

Per impostazione predefinita, il report mostra i dati degli ultimi 7 giorni, ma i dati sono disponibili per gli ultimi 90 giorni.

La sezione panoramica contiene i grafici seguenti:

- **Visualizzare i dati per:** Volume di invio: per impostazione predefinita, il grafico mostra il numero di messaggi del client di autenticazione SMTP inviati da tutti i domini ( Mostra dati **per:** Tutti i domini mittente è selezionato per impostazione predefinita). È possibile filtrare i risultati in un dominio del mittente specifico facendo clic su Mostra dati **per** e selezionando il dominio del mittente nell'elenco a discesa. Se si passa il mouse su un punto dati specifico (giorno), viene visualizzato il numero di messaggi.

  ![Invio della visualizzazione volume nel report dei client di autenticazione SMTP nel Centro sicurezza & conformità](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- **Visualizzare i dati in base a:** Utilizzo TLS : il grafico mostra la percentuale di utilizzo di TLS per tutti i messaggi del client di autenticazione SMTP durante il periodo di tempo selezionato. Questo grafico consente di identificare ed eseguire azioni su utenti e account di sistema che usano ancora versioni precedenti di TLS.

  ![Visualizzazione utilizzo TLS nel report dei client di autenticazione SMTP nel Centro sicurezza & conformità](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

Se si fa **clic su Filtri** in una visualizzazione report, è possibile specificare un intervallo di date con Data di inizio **e** Data **di fine.**

Fare **clic su Richiedi rapporto** per ricevere una versione più dettagliata del rapporto in un messaggio di posta elettronica. È possibile specificare l'intervallo di date e i destinatari per ricevere il rapporto.

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a>Visualizzazione della tabella dei dettagli per il report dei client di autenticazione SMTP

Se si **fa clic su Visualizza tabella dettagli,** le informazioni visualizzate dipendono dal grafico visualizzato:

- **Visualizzare i dati in base a: Volume** di invio: in una tabella vengono visualizzate le informazioni seguenti:

  - **Indirizzo del mittente**
  - **Numero messaggi**

  Se si seleziona una riga, gli stessi dettagli vengono visualizzati in un riquadro a comparsa.

- **Visualizzare i dati in base a: Utilizzo TLS**: in una tabella vengono visualizzate le informazioni seguenti:

  - **Indirizzo del mittente**
  - **TLS1.0%**<sup>\*</sup>
  - **TLS1.1%**<sup>\*</sup>
  - **TLS1.2%**<sup>\*</sup>
  - **Numero messaggi**

  <sup>\*</sup> Questa colonna mostra sia la percentuale che il numero di messaggi provenienti dal mittente.

Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di inizio **e** Data **di fine.**

Se si seleziona una riga, dettagli simili vengono visualizzati in un riquadro a comparsa:

![Riquadro a comparsa Dettagli dalla tabella dei dettagli della visualizzazione di utilizzo tls nel report dei client di autenticazione SMTP](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

Fare **clic su Richiedi rapporto** per ricevere una versione più dettagliata del rapporto in un messaggio di posta elettronica. È possibile specificare l'intervallo di date e i destinatari per ricevere il rapporto.

Per tornare alla visualizzazione report, fare clic su **Visualizza report.**

## <a name="related-topics"></a>Argomenti correlati

Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)
