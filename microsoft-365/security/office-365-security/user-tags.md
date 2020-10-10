---
title: Tag utente in Office 365 ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a identificare gruppi specifici di utenti con tag utente in Office 365 ATP piano 2. Il filtro tag è disponibile tra gli avvisi, i report e le indagini di Office 365 ATP per identificare rapidamente gli utenti contrassegnati.
ms.openlocfilehash: 475bf976a71fb688df8db9ac25f3b397c078d79a
ms.sourcegitcommit: 260c69fa31a898428d51cfdbd762c5f0213c403c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "48417281"
---
# <a name="user-tags-in-office-365-atp"></a>Tag utente in Office 365 ATP

> [!NOTE]
> La funzionalità tag utente è in anteprima, non è disponibile per tutti, ed è soggetta a modifiche. Per informazioni sulla pianificazione dei rilasci, vedere la Guida di [orientamento di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).

I tag utente sono identificatori di gruppi specifici di utenti in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md). Sono disponibili due tipi di tag utente:

- **Tag di sistema**: attualmente, gli [account di priorità](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) sono l'unico tipo di tag di sistema.
- **Tag personalizzati**: creare personalmente questi tag utente.

Se l'organizzazione dispone di Office 365 ATP piano 2 (incluso nell'abbonamento o come componente aggiuntivo), è possibile creare tag utente personalizzati oltre a utilizzare il tag account prioritari.

Dopo aver applicato i tag di sistema o i tag personalizzati agli utenti, è possibile utilizzare tali tag come filtri in avvisi, rapporti ed indagini:

- [Avvisi nel centro sicurezza & conformità](alerts.md)
- [Esplora minacce e rilevamenti in tempo reale](threat-explorer.md)
- [Report dello stato di protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report)
- [Visualizzazioni campagna](campaigns.md)

In questo articolo viene illustrato come configurare i tag utente nel centro sicurezza & Compliance. Non sono presenti cmdlet nel centro sicurezza & conformità per la gestione dei tag utente.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla pagina **tag utente** , Apri <https://protection.office.com/userTags> .

- Per creare, modificare o rimuovere **tag utente personalizzati**, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** nel centro sicurezza & conformità. Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

- Per configurare gli account prioritari (tag di sistema), è necessario essere un [amministratore globale](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) o un [amministratore di Exchange](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).

  È inoltre possibile gestire e monitorare gli account prioritari nell'interfaccia di amministrazione di Microsoft 365. Per istruzioni, vedere [Manage and monitor Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).

## <a name="use-the-security-center-to-create-user-tags"></a>Utilizzare il Centro sicurezza per creare tag utente

1. Nel centro sicurezza accedere a **Threat management** \> **tag utente**di gestione delle minacce.

2. Nella pagina **tag utente** visualizzata, fare clic su **Crea tag**.

3. La creazione guidata **tag** viene aperta in un nuovo volo. Nella pagina **Definisci Tag** configurare le seguenti impostazioni:

   - **Nome**: immettere un nome descrittivo univoco per il tag. Questo è il valore che verrà visualizzato e utilizzato.

   - **Descrizione**: immettere una descrizione facoltativa per il tag.

   Al termine dell'operazione, fare clic su **Avanti**.

4. Nella pagina **assegnare le cassette postali** , eseguire una delle operazioni seguenti:

   - Fare clic su **Aggiungi cassette postali**. Nel volo che viene visualizzato, eseguire una delle operazioni seguenti per aggiungere singoli utenti o gruppi:

     - Fare clic nella casella e scorrere l'elenco per selezionare un utente o un gruppo.
     - Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un utente o un gruppo.
     - Per aggiungere ulteriori valori, fare clic in un'area vuota nella casella.
     - Per rimuovere singole voci dalla casella, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) nell'utente o nel gruppo nella casella.
     - Per rimuovere le voci esistenti dall'elenco sotto la casella, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) la voce.

     Al termine, fare clic su **Aggiungi**.

   - Fare clic su **Importa** per selezionare un file di testo contenente gli indirizzi di posta elettronica degli utenti o dei gruppi. Verificare che il file di testo contenga una voce per riga.

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nella pagina **Revisione Tag** , esaminare le impostazioni. Per apportare modifiche, è possibile fare clic su **modifica** nella sezione specifica.

   Al termine, fare clic su **Invia**.

## <a name="use-the-security-center-to-view-user-tags"></a>Utilizzare il Centro sicurezza per visualizzare i tag utente

1. Nel centro sicurezza accedere a **Threat management** \> **tag utente**di gestione delle minacce.

2. Nella pagina **tag utente** che viene visualizzata, selezionare il tag utente che si desidera visualizzare (non fare clic sulla casella di controllo).

3. Nei dettagli di sola lettura che vengono visualizzati, esaminare le impostazioni.

   Al termine, fare clic su **Chiudi**.

## <a name="use-the-security-center-to-modify-user-tags"></a>Utilizzare il Centro sicurezza per modificare i tag utente

1. Nel centro sicurezza accedere a **Threat management** \> **tag utente**di gestione delle minacce.

2. Nella pagina **tag utente** che viene visualizzata, selezionare il tag utente che si desidera visualizzare e quindi fare clic su **Modifica tag**.

3. Verrà visualizzata la procedura guidata dei criteri in un **Tag Edit** fly out. Fare clic su **Avanti** per rivedere e modificare le impostazioni.

   Al termine, fare clic su **Invia**.

## <a name="use-the-security-center-to-remove-user-tags"></a>Utilizzare il Centro sicurezza per rimuovere i tag utente

**Nota**: non è possibile rimuovere il tag dell' **account prioritario** incorporato.

1. Nel centro sicurezza accedere a **Threat management** \> **tag utente**di gestione delle minacce.

2. Nella pagina **tag utente** che viene visualizzata, selezionare il tag utente che si desidera rimuovere, fare clic su **Elimina tag**, quindi selezionare **Sì, Rimuovi** nell'avviso che viene visualizzato.
