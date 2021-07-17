---
title: Abilitare l'ambiente di valutazione per Microsoft Defender per Office 365 nell'ambiente di produzione, attivare la valutazione, l'attivazione
description: Passaggi per attivare la valutazione di Microsoft Defender per Office365, con licenze di valutazione, gestione dei record MX, & controllo dei domini accettati e delle connessioni in ingresso.
keywords: Microsoft 365 Defender prova, provare Microsoft 365 Defender, valutare Microsoft 365 Defender, laboratorio di valutazione Microsoft 365 Defender, pilota di Microsoft 365 Defender, sicurezza informatica, minaccia persistente avanzata, sicurezza aziendale, dispositivi, dispositivo, identità, utenti, dati, applicazioni, incidenti, analisi e correzione automatizzate, ricerca avanzata
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: c0736b93c314c3086f8a52477622c6bcfa4096a0
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458367"
---
# <a name="enable-the-evaluation-environment"></a>Abilitare l'ambiente di valutazione

**Si applica a:**
- Microsoft 365 Defender

Questo articolo è [il passaggio 2 di 3 nel](eval-defender-office-365-overview.md) processo di configurazione dell'ambiente di valutazione per Microsoft Defender per Office 365. Per ulteriori informazioni su questo processo, vedere [l'articolo di panoramica](eval-defender-office-365-overview.md).

Usa la procedura seguente per abilitare la valutazione per Microsoft Defender per Office 365.


![Passaggi per abilitare Microsoft Defender per Office 365 nell'ambiente di valutazione di Microsoft Defender](../../media/defender/m365-defender-office-eval-enable-steps.png)

- [Passaggio 1: Attivare le licenze di valutazione](#step-1-activate-trial-licenses)
- [Passaggio 2: Controllare e verificare il record MX pubblico](#step-2-audit-and-verify-the-public-mx-record)
- [Passaggio 3: Controllare i domini accettati](#step-3-audit-accepted-domains)
- [Passaggio 4: controllare i connettori in ingresso](#step-4-audit-inbound-connectors)
- [Passaggio 5: attivare la valutazione](#step-5-activate-the-evaluation)

## <a name="step-1-activate-trial-licenses&quot;></a>Passaggio 1: Attivare le licenze di valutazione

Accedere a Microsoft Defender per l'ambiente Office 365 o al portale di amministrazione tenant esistente.

1. Passare al portale di amministrazione.
2. Seleziona Acquista servizi dalla barra di avvio veloce.

:::image type=&quot;content&quot; source=&quot;../../media/mdo-eval/1_m365-purchase-services.png&quot; alt-text=&quot;Fare clic su Acquista servizi nel riquadro di spostamento di Office 365.&quot;:::

3.  Scorri verso il basso fino alla Add-On (o cerca &quot;Defender") per individuare Microsoft Defender per Office 365 piani.
4.  Fare clic su Dettagli accanto al piano che si desidera valutare.

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="Fare clic sul pulsante Dettagli.":::

5. Fai clic sul *collegamento Avvia versione di valutazione* gratuita.

:::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="Fai clic su Avvia versione di valutazione gratuita *collegamento ipertestuale* in questo pannello.":::

6. Conferma la richiesta e fai clic *sul pulsante Prova* ora.

:::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="Ora fai clic sul pulsante Prova ora *.":::

## <a name="step-2-audit-and-verify-the-public-mx-record"></a>Passaggio 2: Controllare e verificare il record MX pubblico

Per valutare in modo efficace Microsoft Defender per Office 365, è importante che la posta elettronica esterna in ingresso sia inoltrata tramite l'istanza di Exchange Online Protection (EOP) associata al tenant.

1. Accedere al portale di amministrazione di M365, espandere Impostazioni e selezionare Domini.
2. Selezionare il dominio di posta elettronica verificato e fare clic su Gestisci DNS.
3. Prendere nota del record MX generato e assegnato al tenant EOP.
4. Accedere alla zona DNS esterna (pubblica) e controllare il record MX primario associato al dominio di posta elettronica.
    - *Se il record MX pubblico corrisponde attualmente all'indirizzo EOP assegnato (ad esempio, tenant-com.mail.protection.outlook.com),* non è necessario apportare ulteriori modifiche al routing.
    - Se il record MX pubblico attualmente si risolve in un gateway SMTP di terze parti o locale, potrebbero essere necessarie configurazioni di routing aggiuntive.
    - Se il record MX pubblico attualmente si risolve in un Exchange locale, è possibile che si sia ancora in un modello ibrido in cui alcune cassette postali del destinatario non sono ancora state migrate in EXO.

## <a name="step-3-audit-accepted-domains"></a>Passaggio 3: Controllare i domini accettati

1. Accedere al portale di Exchange Online, selezionare Posta Flow e quindi fare clic su Domini accettati.
2. Dall'elenco dei domini accettati che sono stati aggiunti e verificati nel tenant, prendere nota del tipo **di** dominio per il dominio di posta elettronica principale.
    - Se il tipo di dominio è impostato su ***Autorevole,*** si presuppone che tutte le cassette postali dei destinatari per l'organizzazione risiedano attualmente in Exchange Online.
    - Se il tipo di dominio è impostato su ***Inoltro*** interno, è possibile che si sia ancora in un modello ibrido in cui alcune cassette postali dei destinatari risiedono ancora in locale.

## <a name="step-4-audit-inbound-connectors"></a>Passaggio 4: controllare i connettori in ingresso

1. Accedere al portale di Exchange Online, selezionare Mail Flow e quindi fare clic su Connettori.
2. Nell'elenco dei connettori configurati prendere nota di tutte le voci provenienti dall'organizzazione **partner** e che possono essere correlate a un gateway SMTP di terze parti.
3. Nell'elenco dei connettori configurati prendere nota delle voci etichettate Dal server di posta elettronica **dell'organizzazione,** che potrebbero indicare che si è ancora in uno scenario ibrido.

## <a name="step-5-activate-the-evaluation"></a>Passaggio 5: attivare la valutazione

Usa le istruzioni qui per attivare Microsoft Defender per Office 365 valutazione dal portale Microsoft 365 Defender.

1. Accedere al tenant con un account che abbia accesso al Microsoft 365 Defender portale.
2. Scegli se vuoi impostare il portale **Microsoft 365 Defender come** interfaccia predefinita per Microsoft Defender per Office 365 amministrazione (scelta consigliata).

:::image type="content" source="../../media/mdo-eval/1_mdo-eval-activate-eval.png" alt-text="Fare clic sul pulsante Attiva impostazioni per usare il portale Microsoft 365 Defender centralizzato e migliorato per l'amministrazione.":::

3. Nel menu di spostamento seleziona **Criteri & regole** in Collaborazione & posta *elettronica*.

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-activate-eval.png" alt-text="Ecco un'immagine del menu Collaborazione & posta elettronica che punta a Criteri & regole. Fai clic qui.":::

4. Nel dashboard *Regole &* criteri fare clic su Criteri **di minaccia.**

:::image type="content" source="../../media/mdo-eval/3_mdo-eval-activate-eval.png" alt-text="Immagine del dashboard Regole & criteri e una freccia che punta ai criteri di minaccia. Fare clic su avanti.":::

5. Scorri verso il *basso fino a Criteri* aggiuntivi e seleziona il riquadro Valuta Defender **Office 365** sicurezza.

:::image type="content" source="../../media/mdo-eval/4_mdo-eval-activate-eval.png" alt-text="Il riquadro Eval Defender per Office 365 che indica che si tratta di una versione di valutazione di 30 giorni tra i vettori di & di collaborazione. Fare clic su.":::

6. Ora scegliere se la posta elettronica esterna Exchange Online direttamente o a un gateway o a un servizio di terze parti e fare clic su Avanti.

:::image type="content" source="../../media/mdo-eval/5_mdo-eval-activate-eval.png" alt-text="Defender for Office 365 valuterà l'invio di posta alle cassette postali Exchange Online utenti. Fornire i dettagli su come viene instradata la posta elettronica ora, incluso il nome del connettore in uscita che instrada la posta. Se si utilizza solo Exchange Online Protection (EOP) non si dispone di un connettore. Scegliere uno dei provider di terze parti o locali oppure utilizzare solo EOP.":::

7. Se si utilizza un gateway di terze parti, selezionare il nome del fornitore nell'elenco a discesa insieme al connettore in ingresso associato alla soluzione. Dopo aver elencato le risposte, fare clic su Avanti.

:::image type="content" source="../../media/mdo-eval/6-mdo-eval-activate-eval-settings.png" alt-text="In questa finestra di dialogo scegli il servizio fornitore di terze parti utilizzato dall'organizzazione oppure seleziona *Altro*. Nella finestra di dialogo successiva, selezionare il connettore in ingresso. Quindi fare clic su Avanti.":::

8. Rivedere le impostazioni e fare clic sul **pulsante Crea** valutazione.

|  |  |
|---------|---------|
|  :::image type="content" source="../../media/mdo-eval/7-mdo-eval-activate-review.png" alt-text="In questo riquadro è presente un elenco a discesa per esaminare le impostazioni. È inoltre disponibile un collegamento selezionabile per modificare il tipo di instradamento, se necessario. Quando sei pronto, fai clic sul pulsante grande blu Crea valutazione.":::   |   :::image type="content" source="../../media/mdo-eval/8-mdo-eval-activate-complete.png" alt-text="E ora la configurazione è stata completata. Il pulsante blu in questa pagina indica &quot;Vai a valutazione&quot;.":::      |

## <a name="next-steps"></a>Passaggi successivi

Passaggio 3 di 3: Configurare il progetto pilota per Microsoft Defender per Office 365

Torna alla panoramica di [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)

Tornare alla panoramica per [valutare e valutare Microsoft 365 Defender](eval-overview.md)