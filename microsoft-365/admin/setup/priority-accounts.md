---
title: Gestire e monitorare gli account prioritari
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
description: Monitorare i messaggi di posta elettronica non riusciti e in ritardo inviati o ricevuti da account che hanno un impatto elevato sulle aziende.
ms.openlocfilehash: bc191873b3bbdcd84122a5430adeffe2b8c29fb1
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477614"
---
# <a name="manage-and-monitor-priority-accounts"></a>Gestire e monitorare gli account prioritari

In ogni organizzazione Microsoft 365 esistono persone indispensabili, come i dirigenti, i leader, i Manager o gli altri utenti che hanno accesso a informazioni sensibili, proprietarie o ad alta priorità.

Per aiutare l'organizzazione a proteggere questi account, è ora possibile designare gli utenti specifici come account prioritari e sfruttare le funzionalità specifiche per le app che forniscono protezione supplementare. In futuro, altre app e funzionalità supporteranno gli account prioritari e, per iniziare, sono state annunciate due funzionalità: **protezione degli account prioritari** e **monitoraggio del flusso di posta Premium**.

- **Protezione degli account prioritari** -Microsoft Defender per Office 365 (in precedenza Office 365 Advanced Threat Protection) supporta gli account prioritari come tag che possono essere utilizzati nei filtri in avvisi, rapporti ed indagini. Per ulteriori informazioni, vedere i [tag degli utenti in Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).
- **Monitoraggio del flusso di posta Premium** -il flusso di posta integro può essere fondamentale per il successo aziendale e i ritardi o gli errori di recapito possono avere un impatto negativo sull'azienda. È possibile scegliere una soglia per i messaggi di posta elettronica non riusciti o ritardati, ricevere avvisi al termine del superamento della soglia e visualizzare un report di problemi relativi alla posta per gli account prioritari. Per ulteriori informazioni, vedere [i problemi di posta elettronica per il rapporto account prioritari nell'interfaccia di amministrazione di Exchange moderna](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).

## <a name="before-you-begin"></a>Prima di iniziare

La caratteristica di **protezione degli account prioritari** descritta in questo argomento è disponibile solo per le organizzazioni che soddisfano i requisiti seguenti:

- Microsoft Defender per Office 365 piano 2, compresi quelli con Office 365 E3, Office 365 E5, Microsoft 365 E5 o Microsoft 365 E5 Security.

La funzionalità di **monitoraggio del flusso di posta Premium** descritta in questo argomento è disponibile solo per le organizzazioni che soddisfano i requisiti seguenti:

- L'organizzazione deve disporre di un numero di licenza di almeno 10.000, da uno o da una combinazione dei prodotti seguenti: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5. Ad esempio, l'organizzazione può avere 3000 licenze Office 365 E3 e 8500 Microsoft 365 E5, per un totale di 11.500 licenze dai prodotti di qualificazione.
- L'organizzazione deve disporre di almeno 50 utenti mensili di Exchange Online attivi.

> [!NOTE]
> È possibile monitorare fino a 250 account prioritari.

### <a name="add-priority-accounts-from-the-setup-page"></a>Aggiungere gli account prioritari dalla pagina di installazione

Aggiungere gli account prioritari dalla **pagina di installazione**.

1. Accedere all'interfaccia di amministrazione di Microsoft 365 all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Andare alla pagina relativa alla **configurazione**  >  **dell'organizzazione** e scegliere **Visualizza** in **Monitor gli account più importanti**.

3. Selezionare **inizia** o **Gestisci**.

4. Nel campo di ricerca della pagina **Aggiungi account di priorità** Digitare il nome o l'indirizzo di posta elettronica della persona che si desidera aggiungere all'elenco degli account prioritari. È inoltre possibile impostare la soglia di posta elettronica per i messaggi non riusciti o in ritardo e ottenere un rapporto settimanale dei problemi per gli account prioritari.

5. Selezionare l'utente e scegliere **Salva**.

È inoltre possibile aggiungere gli account prioritari dalla pagina utenti attivi.

### <a name="add-priority-accounts-from-active-users-page"></a>Aggiungere gli account prioritari dalla pagina utenti attivi

Aggiungere gli account prioritari dalla pagina utenti attivi.

1. Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

2. Passare a **utenti**  >  **attivi** e scegliere **...** nella parte superiore della pagina. Selezionare **Gestisci account prioritari**.

3. Selezionare **Aggiungi account** e nella pagina **Aggiungi account di priorità** , nel campo di ricerca, digitare il nome della persona che si desidera aggiungere all'elenco degli account prioritari.

4. Selezionare l'utente e scegliere **Salva**.

## <a name="remove-a-user-from-the-priority-accounts-list"></a>Rimuovere un utente dall'elenco degli account prioritari

1. Accedere all'interfaccia di amministrazione di Microsoft 365 all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Andare alla pagina relativa alla **configurazione**  >  **dell'organizzazione** e scegliere **Visualizza** in **Monitor gli account più importanti**.

3. Nella pagina **monitora gli account più** fare clic su **account prioritari** in **Gestisci questa funzionalità**.

4. Nella pagina **account prioritari** selezionare l'utente o gli utenti che si desidera rimuovere dall'elenco e scegliere, rimuovere gli **account**.

## <a name="related-topics"></a>Argomenti correlati

[Utilizzo degli account prioritari in Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)