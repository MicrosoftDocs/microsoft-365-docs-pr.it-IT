---
title: Tag utente in Microsoft Defender per Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a identificare gruppi specifici di utenti con tag utente in Microsoft Defender per Office 365 Piano 2. Il filtro dei tag è disponibile tra avvisi, report e indagini in Microsoft Defender per Office 365 per identificare rapidamente gli utenti con tag.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 105e927e50f7b1d1217587587b8d7ee3b7d6bd4c
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904105"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a>Tag utente in Microsoft Defender per Office 365

> [!NOTE]
> La funzionalità tag utente è disponibile in Anteprima, non è disponibile per tutti gli utenti ed è soggetta a modifiche. Per informazioni sulla pianificazione dei rilasci, vedere la roadmap [Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap)

I tag utente sono identificatori per gruppi specifici di utenti in [Microsoft Defender per Office 365](defender-for-office-365.md). Esistono due tipi di tag utente:

- **Tag di** sistema: attualmente, [gli account Priority](../../admin/setup/priority-accounts.md) sono l'unico tipo di tag di sistema.
- **Tag personalizzati**: questi tag utente vengono creati manualmente.

Se l'organizzazione ha Defender per Office 365 Piano 2 (incluso nell'abbonamento o come componente aggiuntivo), puoi creare tag utente personalizzati oltre a usare il tag degli account di priorità.

> [!NOTE]
> Attualmente, è possibile applicare i tag utente solo agli utenti delle cassette postali.

Dopo aver applicato tag di sistema o tag personalizzati agli utenti, è possibile utilizzare tali tag come filtri in avvisi, report e indagini:

- [Avvisi](alerts.md)
- [Criteri di avviso personalizzati](../../compliance/alert-policies.md#viewing-alerts)
- [Esplora minacce e rilevamenti in tempo reale](threat-explorer.md)
- [Pagina Entità posta elettronica](mdo-email-entity-page.md#other-innovations)
- [Report dello stato di protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report)
- [Visualizzazioni campagna](campaigns.md)
- Per gli account con priorità, è possibile utilizzare il [report Problemi](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) di posta elettronica per gli account di priorità nell'interfaccia di amministrazione di Exchange (EAC).

Questo articolo spiega come configurare i tag utente nel portale Microsoft 365 Defender. Non sono disponibili cmdlet in Microsoft 365 Defender Portal per gestire i tag utente.

Per informazioni su come i tag utente fanno parte della strategia per proteggere gli account utente ad alto [impatto,](security-recommendations-for-priority-accounts.md)vedere Suggerimenti per la sicurezza per gli account con priorità in Microsoft 365 .

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Per aprire il portale di Microsoft 365 Defender, andare alla pagina <https://security.microsoft.com/>. Per passare direttamente alla **pagina Tag** utente, aprire <https://security.microsoft.com/securitysettings/userTags> .

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni nel portale di Microsoft 365 Defender:
  - Per creare, modificare ed eliminare tag utente, è necessario essere membri dei gruppi **di** ruoli Gestione organizzazione o Amministratore **sicurezza.**
  - Per aggiungere e rimuovere membri dai tag utente esistenti, è necessario essere membri dei gruppi di ruoli **Gestione** **organizzazione,** Amministratore sicurezza o **Operatore** sicurezza
  - Per l'accesso in sola lettura ai tag utente, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.

  Per ulteriori informazioni, vedere [Autorizzazioni nel portale Microsoft 365 Defender.](permissions-in-the-security-and-compliance-center.md)

  > [!NOTE]
  >
  > - L'aggiunta di utenti al ruolo Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 offre  agli utenti le autorizzazioni necessarie nel portale di Microsoft 365 Defender e le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).
  >
  > - La gestione dei tag utente è controllata dai **ruoli Lettore tag** **e Gestione** tag.

- È inoltre possibile gestire e monitorare gli account di priorità nell'Microsoft 365 di amministrazione. Per istruzioni, vedere [Gestire e monitorare gli account con priorità.](../../admin/setup/priority-accounts.md)

- Per informazioni sulla protezione degli _account con privilegi_ (account amministratore), vedere questo [argomento.](/azure/architecture/framework/security/critical-impact-accounts)

## <a name="use-the-microsoft-365-defender-portal-to-create-user-tags"></a>Usare il portale Microsoft 365 Defender per creare tag utente

1. Nel portale Microsoft 365 Defender passare **a** Impostazioni \> **e-mail & collaborazione** Tag \> **utente**.

2. Nella pagina **Tag utente** fare clic su Crea icona tag ![ Crea ](../../media/m365-cc-sc-create-icon.png) **tag**.

3. La **procedura guidata Crea tag** si apre in un nuovo riquadro a comparsa. Nella pagina **Definisci tag** configurare le impostazioni seguenti:
   - **Nome**: immettere un nome descrittivo univoco per il tag. Questo è il valore che vedrai e userai. Tieni presente che non puoi rinominare un tag dopo averlo creato.
   - **Descrizione:** immettere una descrizione facoltativa per il tag.

   Al termine dell'operazione, fare clic su **Avanti**.

4. Nella pagina **Assegna membri** eseguire una delle operazioni seguenti:
   - Fare ![ clic su Aggiungi membri icona Aggiungi ](../../media/m365-cc-sc-create-icon.png) **membri**. Nel riquadro a comparsa visualizzato eseguire una delle operazioni seguenti per aggiungere singoli utenti o gruppi:
     - Fare clic nella casella e scorrere l'elenco per selezionare un utente o un gruppo.
     - Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un utente o un gruppo.
     - Per aggiungere altri valori, fare clic in un'area vuota della casella.
     - Per rimuovere singole voci, fare clic su ![Icona Rimuovi voce](../../media/m365-cc-sc-remove-selection-icon.png) accanto alla voce nella casella.
     - Per rimuovere tutte le voci, fare clic sull'icona Rimuovi voce ![ nell'elemento Utenti e gruppi ](../../media/m365-cc-sc-remove-selection-icon.png) **nn** selezionati sotto la casella.

     Al termine, fare clic su **Aggiungi**.

     Nella pagina **Assegna membri** è inoltre possibile rimuovere le voci facendo clic sull'icona Elimina accanto alla ![ ](../../media/m365-cc-sc-delete-icon.png) voce.

   - Fare **clic su** Importa per selezionare un file di testo contenente gli indirizzi di posta elettronica degli utenti o dei gruppi. Assicurarsi che il file di testo contenga una voce per riga.

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nella pagina **Rivedi tag** visualizzata rivedere le impostazioni. È possibile selezionare **Modifica** in ogni sezione per modificare le impostazioni all'interno della sezione. Oppure è possibile fare clic su **Indietro** o selezionare la pagina specifica della procedura guidata.

   Al termine, fare clic su **Invia** e quindi su **Fine.**

## <a name="use-the-microsoft-365-defender-portal-to-view-user-tags"></a>Usare il portale Microsoft 365 Defender per visualizzare i tag utente

1. Nel portale Microsoft 365 Defender passare **a** Impostazioni \> **e-mail & collaborazione** Tag \> **utente**.

2. Nella **pagina Tag utente** vengono visualizzate le proprietà seguenti nell'elenco dei tag utente:

   - **Tag**: nome del tag utente. Tieni presente che questo include il tag di **sistema dell'account Priority** incorporato.
   - **Applicato a**: Numero di membri
   - **Data ultima modifica**
   - **Creato il**

3. Quando si seleziona un tag utente facendo clic sul nome, i dettagli vengono visualizzati in un riquadro a comparsa.

## <a name="use-the-microsoft-365-defender-portal-to-modify-user-tags"></a>Usare il portale Microsoft 365 Defender per modificare i tag utente

1. Nel portale Microsoft 365 Defender passare **a** Impostazioni \> **e-mail & collaborazione** Tag \> **utente**.

2. Nella pagina **Tag utente** selezionare il tag utente nell'elenco e quindi fare clic su Modifica icona tag ![ Modifica ](../../media/m365-cc-sc-edit-icon.png) **tag**.

3. Nel riquadro a comparsa dei dettagli visualizzato, la stessa procedura guidata e le stesse impostazioni sono disponibili come descritto nella sezione Usare il portale [di Microsoft 365 Defender](#use-the-microsoft-365-defender-portal-to-create-user-tags) per creare tag utente in precedenza in questo articolo.

   **Note**:

   - La **pagina Definisci tag** non è disponibile per il tag di sistema dell'account **Priority** predefinito, quindi non puoi rinominare questo tag o modificare la descrizione.
   - Non è possibile rinominare un tag personalizzato, ma è possibile modificare la descrizione.

## <a name="use-the-microsoft-365-defender-portal-to-remove-user-tags"></a>Usare il portale Microsoft 365 Defender per rimuovere i tag utente

> [!NOTE]
> Non è possibile rimuovere il tag di sistema **dell'account Priority** predefinito.

1. Nel portale Microsoft 365 Defender passare **a** Impostazioni \> **e-mail & collaborazione** Tag \> **utente**.

2. Nella pagina **Tag utente** selezionare il tag utente nell'elenco e quindi fare clic su Elimina tag icona ![ Elimina ](../../media/m365-cc-sc-delete-icon.png) **tag**.

3. Leggere l'avviso nella finestra di dialogo di conferma visualizzata e quindi fare clic su **Sì, rimuovi**.
