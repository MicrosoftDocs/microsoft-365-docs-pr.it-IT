---
title: Informazioni dettagliate sui messaggi di posta elettronica dei nuovi utenti inoltrati
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: Gli amministratori possono imparare a usare le informazioni dettagliate sui nuovi utenti che inoltrano la posta elettronica nel Centro sicurezza & conformità per analizzare quando gli utenti dell'organizzazione inoltrano i messaggi a nuovi domini.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 807df82ca80e851554db7b8f373a5ca4af02a391
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206193"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>Informazioni dettagliate sulla posta elettronica inoltrate da nuovi utenti nel Centro sicurezza & conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

È sospetto quando i nuovi account utente nell'organizzazione iniziano improvvisamente ad inoltrare i messaggi di posta elettronica ai domini esterni.

Le **informazioni dettagliate** sui nuovi domini inoltrati tramite posta elettronica nel Centro sicurezza [&](https://protection.office.com) conformità notificano quando gli utenti appena creati nell'organizzazione inoltrano i messaggi ai domini esterni. Questa condizione potrebbe indicare che sono stati utilizzati account amministratore compromessi per creare i nuovi utenti. Se si sospetta che gli account siano stati compromessi, vedere [Risposta a un account di posta elettronica compromesso.](responding-to-a-compromised-email-account.md)

Questa panoramica viene visualizzata solo quando viene rilevato il problema e viene visualizzata nella pagina [Rapporto di inoltro.](view-mail-flow-reports.md#forwarding-report)

![Informazioni dettagliate sui messaggi di posta elettronica dei nuovi utenti inoltrati](../../media/mfi-new-users-forwarding-email.png)

Quando si fa clic sul widget, viene visualizzato un riquadro a comparsa in cui è possibile trovare ulteriori dettagli sui messaggi inoltrati, incluso un collegamento al [report Modifiche](#forwarding-modifications-report) di inoltro, come descritto più avanti in questo articolo.

![Riquadro a comparsa Dettagli visualizzato dopo aver fatto clic su Informazioni dettagliate sui nuovi utenti che inoltrano la posta elettronica](../../media/mfi-new-users-forwarding-email-details.png)

È inoltre possibile accedere **a** questa pagina dei  dettagli quando si selezionano le informazioni dettagliate dopo aver fatto clic su Visualizza tutto nell'area Principali & suggerimenti su ( \> **Dashboard** report o <https://protection.office.com/insightdashboard> ).

È possibile fare clic **sul collegamento** Visualizza report associato a informazioni dettagliate per passare al **report Modifiche** di inoltro come descritto nella sezione successiva.

## <a name="forwarding-modifications-report"></a>Rapporto modifiche inoltro

Il **report Modifiche inoltro mostra i** dettagli sui messaggi che vengono inoltrati automaticamente dai mittenti dell'organizzazione:

- Account appena creati che inoltrano messaggi a domini esterni.
- Account che inoltrano messaggi a domini esterni che non sono mai stati inoltrati da altri mittenti nell'organizzazione.

Questi tipi di messaggi inoltrati possono rappresentare un rischio per la sicurezza o la conformità e possono indicare account compromessi.

Il report contiene dati per un massimo di 90 giorni. Per impostazione predefinita, il report mostra i dati degli ultimi 7 giorni.

Questo report non è disponibile direttamente nel [dashboard del flusso di posta](mail-flow-insights-v2.md) o nel dashboard [report.](view-mail-flow-reports.md) Oltre a fare clic sul collegamento Visualizza  **report** associato alle informazioni dettagliate in Informazioni dettagliate sui nuovi utenti che inoltrano la posta elettronica, è possibile accedere al report tramite:

- Facendo clic **sul collegamento Rapporto notifiche di inoltro** nei dettagli di Informazioni sui nuovi domini [inoltrati tramite posta elettronica.](mfi-new-domains-being-forwarded-email.md)
- Apertura <https://protection.office.com/reportv2?id=MailFlowNewForwarding> di .

### <a name="report-view-for-the-forwarding-modifications-report"></a>Visualizzazione report per il report Modifiche inoltro

Nella visualizzazione report sono disponibili i grafici seguenti:

- **Mostra dati per: Nuovi utenti di inoltro**:

  ![Visualizzazione Nuovi utenti di inoltro nel report Modifiche di inoltro](../../media/forwarding-modifications-report-new-forwarding-users.png)

- **Mostra dati per: Nuovi domini di inoltro**:

  ![Nuova visualizzazione dei domini inoltrati nel report Modifiche di inoltro](../../media/forwarding-modifications-report-new-forwarded-domains.png)

Se si fa **clic su Filtri** in una visualizzazione report, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>Visualizzazione tabella dettagli per il report Modifiche inoltro

Se si fa **clic su Visualizza tabella** dettagli , le informazioni visualizzate dipendono dal grafico visualizzato:

- **Mostra dati per: Nuovi utenti di inoltro**:

  - **Nome**: Indirizzo di posta elettronica del mittente.
  - **Tipo di inoltro**
  - **Indirizzo destinatario**
  - **Dettagli**
  - **Numero**
  - **Prima data di inoltro**

- **Mostra dati per: Nuovi domini di inoltro**:

  - **Name**: Il dominio di posta elettronica del mittente.
  - **Tipo di inoltro**
  - **Indirizzo destinatario**
  - **Dettagli**
  - **Numero**
  - **Prima data di inoltro**

Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**

Se si seleziona una riga dalla tabella, **verrà** visualizzato un riquadro a comparsa Dettagli con le informazioni seguenti:

- **Nome**: si tratta dell'indirizzo di posta elettronica del mittente (da Mostra dati **per:** Visualizzazione nuovi utenti di inoltro) o del dominio di posta elettronica del mittente (da Mostra dati **per: Nuova** visualizzazione domini di inoltro).
- **Tipo di inoltro**
- **Destinatario**
- **Dettagli**
- **Numero**
- **Data di inizio**
- **Suggerimento:** da qui è possibile fare clic sul collegamento per gestire l'utente nell'Microsoft 365 di amministrazione.

![Riquadro a comparsa Dettagli dalla tabella dei dettagli della visualizzazione Nuovi utenti di inoltro nel report Modifiche inoltro](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

Per tornare alla visualizzazione report, fare clic su **Visualizza report.**

## <a name="related-topics"></a>Argomenti correlati

Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)
