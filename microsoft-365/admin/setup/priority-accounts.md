---
title: Gestire e monitorare gli account con priorità
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
description: Monitorare i messaggi di posta elettronica non riusciti e ritardati inviati a o da account con un impatto aziendale elevato.
ms.openlocfilehash: bc191873b3bbdcd84122a5430adeffe2b8c29fb1
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477614"
---
# <a name="manage-and-monitor-priority-accounts"></a>Gestire e monitorare gli account con priorità

In ogni organizzazione di Microsoft 365 ci sono persone essenziali, come dirigenti, dirigenti, responsabili o altri utenti che hanno accesso a informazioni sensibili, proprietarie o ad alta priorità.

Per aiutare l'organizzazione a proteggere questi account, ora puoi designare utenti specifici come account prioritari e sfruttare funzionalità specifiche dell'app che forniscono loro una protezione aggiuntiva. In futuro, più app e funzionalità supporteranno gli account con priorità e, per iniziare, abbiamo annunciato due funzionalità: protezione degli **account** prioritari e monitoraggio del flusso **di posta premium.**

- **Protezione dell'account** con priorità: Microsoft Defender per Office 365 (in precedenza Office 365 Advanced Threat Protection) supporta gli account con priorità come tag che possono essere usati nei filtri in avvisi, report e indagini. Per altre informazioni, vedere [Tag utente in Microsoft Defender per Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide)
- **Monitoraggio del flusso di** posta premium: un flusso di posta integro può essere fondamentale per il successo aziendale e i ritardi o gli errori di recapito possono avere un impatto negativo sull'azienda. È possibile scegliere una soglia per i messaggi di posta elettronica non riusciti o ritardati, ricevere avvisi quando tale soglia viene superata e visualizzare un rapporto dei problemi di posta elettronica per gli account con priorità. Per ulteriori informazioni, vedere La segnalazione dei problemi di posta elettronica [per gli account con priorità nell'interfaccia di amministrazione di Exchange moderna.](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)

## <a name="before-you-begin"></a>Informazioni preliminari

La **funzionalità di protezione dell'account** Priority descritta in questo argomento è disponibile solo per le organizzazioni che soddisfano i requisiti seguenti:

- Microsoft Defender per Office 365 Piano 2, inclusi quelli con Office 365 E3, Office 365 E5, Microsoft 365 E5 o Microsoft 365 E5 Security.

La **funzionalità di monitoraggio del** flusso di posta Premium descritta in questo argomento è disponibile solo per le organizzazioni che soddisfano i requisiti seguenti:

- L'organizzazione deve disporre di un numero di licenze di almeno 10.000, di uno dei prodotti o di una combinazione dei prodotti seguenti: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5. Ad esempio, l'organizzazione può avere 3000 licenze di Office 365 E3 e 8500 Microsoft 365 E5, per un totale di 11.500 licenze dei prodotti idonei.
- L’organizzazione deve avere almeno 50 utenti Exchange Online attivi al mese

> [!NOTE]
> È possibile monitorare fino a 250 account con priorità.

### <a name="add-priority-accounts-from-the-setup-page"></a>Aggiungere account con priorità dalla pagina Di installazione

Aggiungere account con priorità dalla **pagina Di installazione.**

1. Passare all'interfaccia di amministrazione di Microsoft 365 all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Passare a **Configurazione**  >  **conoscenze organizzative** e scegliere **Visualizza** in **Monitora gli account più importanti.**

3. Selezionare **Inizia o** **Gestisci.**

4. Nel campo di ricerca **della** pagina Aggiungi account priorità digitare il nome o l'indirizzo di posta elettronica della persona che si desidera aggiungere all'elenco degli account con priorità. È inoltre possibile impostare la soglia di posta elettronica per i messaggi di posta elettronica non riusciti o ritardati e ottenere un rapporto settimanale dei problemi per gli account con priorità.

5. Selezionare l'utente e scegliere **Salva.**

È inoltre possibile aggiungere account con priorità dalla pagina Utenti attivi.

### <a name="add-priority-accounts-from-active-users-page"></a>Aggiungere account con priorità dalla pagina Utenti attivi

Aggiungere account con priorità dalla pagina Utenti attivi.

1. Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

2. Go to **Users**  >  **Active users** and choose **...** at the top of the page. Selezionare **Gestisci account con priorità.**

3. Selezionare **Aggiungi account** e  nel campo di ricerca della pagina Aggiungi account priorità digitare il nome della persona che si desidera aggiungere all'elenco degli account con priorità.

4. Selezionare l'utente e scegliere **Salva.**

## <a name="remove-a-user-from-the-priority-accounts-list"></a>Rimuovere un utente dall'elenco degli account con priorità

1. Passare all'interfaccia di amministrazione di Microsoft 365 all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Passare a **Configurazione**  >  **conoscenze organizzative** e scegliere **Visualizza** in **Monitora gli account più importanti.**

3. Nella pagina **Monitora la maggior parte degli account** scegliere Account con **priorità** in Gestisci **questa funzionalità.**

4. Nella pagina **Account con** priorità selezionare l'utente o gli utenti che si desidera rimuovere dall'elenco e scegliere **Rimuovi account.**

## <a name="related-topics"></a>Argomenti correlati

[Uso degli account con priorità in Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)