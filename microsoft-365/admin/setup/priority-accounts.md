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
description: Monitorare i messaggi di posta elettronica non riusciti e ritardati inviati a o da account che hanno un impatto aziendale elevato.
ms.openlocfilehash: 0bba1f87f80de9fea249ce2604e83ceeadfb79ee
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51050643"
---
# <a name="manage-and-monitor-priority-accounts"></a>Gestire e monitorare gli account con priorità

In ogni organizzazione di Microsoft 365, ci sono persone essenziali, come dirigenti, dirigenti, manager o altri utenti che hanno accesso a informazioni riservate, proprietarie o ad alta priorità.

Per aiutare l'organizzazione a proteggere questi account, ora puoi designare utenti specifici come account prioritari e sfruttare funzionalità specifiche dell'app che forniscono loro una protezione aggiuntiva. In futuro, più app e funzionalità supporteranno gli account prioritari e, per iniziare, abbiamo annunciato due funzionalità: la protezione degli **account** prioritari e il monitoraggio del flusso **di posta premium.**

- **Protezione degli account** con priorità - Microsoft Defender per Office 365 (in precedenza Office 365 Advanced Threat Protection) supporta gli account di priorità come tag che possono essere utilizzati nei filtri in avvisi, report e indagini. Per ulteriori informazioni, vedere [Tag utente in Microsoft Defender per Office 365.](../../security/defender-365-security/user-tags.md)
- **Monitoraggio del flusso di** posta premium - Un flusso di posta integro può essere fondamentale per il successo aziendale e i ritardi o gli errori di recapito possono avere un impatto negativo sull'azienda. È possibile scegliere una soglia per i messaggi di posta elettronica non riusciti o ritardati, ricevere avvisi quando tale soglia viene superata e visualizzare un rapporto dei problemi di posta elettronica per gli account con priorità. Per ulteriori informazioni, vedere [Email issues for priority accounts report in the modern EAC](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)

Per le procedure consigliate per la sicurezza per gli account con priorità, vedere [Suggerimenti per la sicurezza per gli account con priorità.](../../security/defender-365-security/security-recommendations-for-priority-accounts.md)

## <a name="before-you-begin"></a>Prima di iniziare

La **funzionalità di protezione degli account** priority descritta in questo argomento è disponibile solo per le organizzazioni che soddisfano i requisiti seguenti:

- Microsoft Defender per Office 365 Piano 2, inclusi quelli con Office 365 E3, Office 365 E5, Microsoft 365 E5 o Microsoft 365 E5 Security.

La **funzionalità di monitoraggio del** flusso di posta Premium descritta in questo argomento è disponibile solo per le organizzazioni che soddisfano i requisiti seguenti:

- L'organizzazione deve disporre di un numero di licenze di almeno 10.000, da uno dei prodotti seguenti o da una combinazione dei seguenti prodotti: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5. Ad esempio, l'organizzazione può avere 3000 licenze di Office 365 E3 e 8500 Microsoft 365 E5, per un totale di 11.500 licenze dei prodotti idonei.
- L’organizzazione deve avere almeno 50 utenti Exchange Online attivi al mese

> [!NOTE]
> È possibile monitorare fino a 250 account con priorità.

### <a name="add-priority-accounts-from-the-setup-page"></a>Aggiungere account con priorità dalla pagina Installazione

Aggiungere account di priorità dalla **pagina Installazione**.

1. Accedere all'interfaccia di amministrazione di Microsoft 365 all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Vai a **Configurazione**  >  **Conoscenza dell'organizzazione** e scegli **Visualizza** in **Monitora gli account più importanti.**

3. Selezionare **Inizia o** **Gestisci.**

4. Nel **campo di** ricerca della pagina Aggiungi account priorità digitare il nome o l'indirizzo di posta elettronica della persona che si desidera aggiungere all'elenco degli account di priorità. Puoi anche impostare la soglia della posta elettronica per i messaggi di posta elettronica non riusciti o ritardati e ottenere un rapporto settimanale dei problemi per gli account con priorità.

5. Selezionare l'utente e scegliere **Salva**.

È inoltre possibile aggiungere account con priorità dalla pagina Utenti attivi.

### <a name="add-priority-accounts-from-active-users-page"></a>Aggiungere account con priorità dalla pagina Utenti attivi

Aggiungere account con priorità dalla pagina Utenti attivi.

1. Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

2. Vai a **Utenti**  >  **Utenti attivi** e scegli **...** nella parte superiore della pagina. Selezionare **Gestisci account con priorità**.

3. Selezionare **Aggiungi account** e  nel campo di ricerca della pagina Aggiungi account priorità digitare il nome della persona che si desidera aggiungere all'elenco degli account di priorità.

4. Selezionare l'utente e scegliere **Salva**.

## <a name="remove-a-user-from-the-priority-accounts-list"></a>Rimuovere un utente dall'elenco degli account con priorità

1. Accedere all'interfaccia di amministrazione di Microsoft 365 all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Vai a **Configurazione**  >  **Conoscenza dell'organizzazione** e scegli **Visualizza** in **Monitora gli account più importanti.**

3. Nella pagina **Monitora la maggior parte degli account** scegliere Account con **priorità** in Gestisci **questa funzionalità.**

4. Nella pagina **Account di priorità** selezionare l'utente o gli utenti che si desidera rimuovere dall'elenco e scegliere Rimuovi **account.**

## <a name="related-topics"></a>Argomenti correlati

[Uso degli account con priorità in Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)