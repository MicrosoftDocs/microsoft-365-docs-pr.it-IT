---
title: Tag utente in Microsoft Defender per Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a identificare gruppi specifici di utenti con tag utente in Microsoft Defender per Office 365 Piano 2. Il filtro tag è disponibile per avvisi, report e indagini in Microsoft Defender per Office 365 per identificare rapidamente gli utenti contrassegnati.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ed91492e652773b3a48373df49b20d97887df6ee
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931435"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Tag utente in Microsoft Defender per Office 365

> [!NOTE]
> La funzionalità tag utente è disponibile in Anteprima, non è disponibile per tutti gli utenti ed è soggetta a modifiche. Per informazioni sulla pianificazione dei rilasci, consultare la roadmap di [Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap)

I tag utente sono identificatori per gruppi specifici di utenti in [Microsoft Defender per Office 365.](office-365-atp.md) Esistono due tipi di tag utente:

- **Tag di** sistema: attualmente, [gli account Priority](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) sono l'unico tipo di tag di sistema.
- **Tag personalizzati:** questi tag utente vengono creati manualmente.

Se l'organizzazione dispone di Defender per Office 365 Piano 2 (incluso nell'abbonamento o come componente aggiuntivo), è possibile creare tag utente personalizzati oltre a usare il tag degli account con priorità.

Dopo aver applicato tag di sistema o tag personalizzati agli utenti, è possibile utilizzare tali tag come filtri in avvisi, report e indagini:

- [Avvisi nel Centro sicurezza & conformità](alerts.md)
- [Esplora minacce e rilevamenti in tempo reale](threat-explorer.md)
- [Report dello stato di protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report)
- [Visualizzazioni campagna](campaigns.md)
- Per gli account con priorità, è possibile utilizzare il report Problemi di posta elettronica per gli [account con priorità](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) nell'interfaccia di amministrazione di Exchange.

Questo articolo spiega come configurare i tag utente nel Centro sicurezza & conformità. Non sono disponibili cmdlet nel Centro sicurezza & conformità per gestire i tag utente.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Aprire il Centro sicurezza e conformità in<https://protection.office.com/>. Per passare direttamente alla **pagina Tag** utente, aprire <https://protection.office.com/userTags> .

- È necessario disporre delle autorizzazioni nel Centro sicurezza e conformità per poter eseguire le procedure contenute in questo articolo:
  - Per creare, modificare ed eliminare tag utente, è necessario essere membri dei gruppi **di** ruoli Gestione organizzazione o Amministratore **sicurezza.**
  - Per aggiungere e rimuovere membri dai tag utente esistenti, è necessario essere membri dei gruppi di ruoli **Gestione** **organizzazione,** Amministratore sicurezza **o Operatore** sicurezza
  - Per l'accesso in sola lettura ai tag utente, è necessario essere membri dei **gruppi** di ruoli Lettore globale o **Lettore** di sicurezza.

  Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

  **Note**:

  - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - La gestione dei tag utente è controllata dai **ruoli Lettore tag,** **Collaboratore** tag **e Gestione** tag.

- È inoltre possibile gestire e monitorare gli account con priorità nell'interfaccia di amministrazione di Microsoft 365. Per istruzioni, vedere [Gestire e monitorare gli account con priorità.](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)

## <a name="use-the-security-center-to-create-user-tags"></a>Utilizzare il Centro sicurezza per creare tag utente

1. Nel Centro sicurezza passare a **Tag utente per la gestione** delle \> **minacce.**

2. Nella pagina **Tag utente** visualizzata fare clic su **Crea tag.**

3. La **creazione guidata tag** si apre in un nuovo riquadro a comparsa. Nella pagina **Definisci tag** configurare le impostazioni seguenti:
   - **Nome**: immettere un nome descrittivo univoco per il tag. Questo è il valore che verrà visualizzato e utilizzato.
   - **Descrizione:** immettere una descrizione facoltativa per il tag.

   Al termine dell'operazione, fare clic su **Avanti**.

4. Nella pagina **Assegna utenti** eseguire una delle operazioni seguenti:

   - Fare **clic su Aggiungi utenti.** Nel riquadro a comparsa visualizzato, eseguire una delle operazioni seguenti per aggiungere singoli utenti o gruppi:
     - Fare clic nella casella e scorrere l'elenco per selezionare un utente o un gruppo.
     - Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un utente o un gruppo.
     - Per aggiungere ulteriori valori, fare clic in un'area vuota della casella.
     - Per rimuovere singole voci dalla casella, fare **clic** sull'icona Rimuovi ![ ](../../media/scc-remove-icon.png) dell'utente o del gruppo nella casella.
     - Per rimuovere voci esistenti dall'elenco sotto la casella, fare clic  ![ sull'icona ](../../media/scc-remove-icon.png) Rimuovi.

     Al termine, fare clic su **Aggiungi.**

   - Fare **clic su** Importa per selezionare un file di testo contenente gli indirizzi di posta elettronica degli utenti o dei gruppi. Assicurarsi che il file di testo contenga una voce per riga.

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nella pagina **Rivedi tag** esaminare le impostazioni. È possibile fare **clic su** Modifica nella sezione specifica per apportare modifiche.

   Al termine, fare clic su **Invia.**

## <a name="use-the-security-center-to-view-user-tags"></a>Utilizzare il Centro sicurezza per visualizzare i tag utente

1. Nel Centro sicurezza passare a **Tag utente per la gestione** delle \> **minacce.**

2. Nella **pagina Tag utente** visualizzata, selezionare il tag utente che si desidera visualizzare (non fare clic sulla casella di controllo).

3. Nel riquadro a comparsa dei dettagli di sola lettura visualizzato, rivedere le impostazioni.

   Al termine, fare clic su **Chiudi**.

## <a name="use-the-security-center-to-modify-user-tags"></a>Utilizzare il Centro sicurezza per modificare i tag utente

1. Nel Centro sicurezza passare a **Tag utente per la gestione** delle \> **minacce.**

2. Nella **pagina Tag utente** visualizzata selezionare il tag utente che si desidera visualizzare e quindi fare clic su **Modifica tag.**

3. La procedura guidata per i criteri si apre in **un riquadro a comparsa** Modifica tag. Fare **clic su** Avanti per rivedere e modificare le impostazioni.

   Al termine, fare clic su **Invia.**

## <a name="use-the-security-center-to-remove-user-tags"></a>Utilizzare il Centro sicurezza per rimuovere i tag utente

**Nota:** non è possibile rimuovere il tag predefinito **dell'account Priority.**

1. Nel Centro sicurezza passare a **Tag utente per la gestione** delle \> **minacce.**

2. Nella **pagina Tag utente** visualizzata selezionare il tag utente che si desidera rimuovere, fare clic su Elimina **tag** e quindi selezionare **Sì,** rimuovi nell'avviso visualizzato.
