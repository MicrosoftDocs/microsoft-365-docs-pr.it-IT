---
title: Proteggere gli account amministratore
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Informazioni su come configurare e proteggere gli account amministratore.
ms.openlocfilehash: 73e4b69571b1e1d0a4d1585224fe256ff135c40a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044489"
---
# <a name="protect-your-administrator-accounts"></a>Proteggere gli account amministratore

Poiché gli account amministratore dispongono di privilegi elevati, sono obiettivi importanti per hacker e cyber-criminali. In questo articolo viene descritto:

- Come configurare un account amministratore aggiuntivo per le emergenze.
- Come proteggere questi account.

Quando si effettua l'iscrizione a Microsoft 365 e si immettono le informazioni, si diventa automaticamente l'amministratore globale. Un amministratore globale ha il controllo finale degli account utente e di tutte le altre impostazioni nell'interfaccia di amministrazione di Microsoft, ma esistono molti tipi diversi di account amministratore con diversi gradi di accesso. Per [informazioni sui diversi](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) livelli di accesso per ogni tipo di ruolo di amministratore, vedere i ruoli di amministratore.

## <a name="create-additional-admin-accounts"></a>Creare account amministratore aggiuntivi

Usa gli account amministratore solo per l'amministrazione. Gli amministratori devono disporre di un account utente separato per l'uso regolare delle app di Office e utilizzare il proprio account amministrativo solo se necessario per gestire account e dispositivi e durante l'utilizzo di altre funzioni di amministratore. È anche una buona idea rimuovere la licenza di Microsoft 365 dagli account di amministratore in modo da non doverli pagare.

È necessario configurare almeno un account amministratore globale aggiuntivo per concedere l'accesso di amministratore a un altro dipendente attendibile. È inoltre possibile creare account amministratore separati per la gestione degli utenti (questo ruolo è denominato **Amministratore gestione utenti).** Per ulteriori informazioni, vedere [sui ruoli di amministratore.](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)

Per creare altri account amministratore:

 1. Passare <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">all'interfaccia di amministrazione</a> e quindi scegliere **Utenti** \> **attivi nel** riquadro di spostamento sinistro.

    ![Choose Users and then Active users in the left nav](../media/Activeusers.png)

 2. Nella pagina **Utenti attivi** selezionare Aggiungi utente nella parte superiore  della pagina e nel riquadro Nuovo utente immettere il nome e altre informazioni. 
 3. Espandere la **sezione Ruoli** e scegliere Amministratore **globale per** concedere all'utente l'accesso come amministratore globale. È inoltre possibile scegliere **Amministratore personalizzato** e scegliere uno dei ruoli visualizzati.

    Immettere un messaggio di posta elettronica alternativo nella **casella di testo Indirizzo di posta** elettronica alternativo. È possibile utilizzare questo indirizzo per recuperare le informazioni sulla password in caso di blocco. Per gli amministratori globali, a questo indirizzo verrà inviato anche un estratto conto.

    ![Scegliere il ruolo di amministratore](../media/adminroles.png)

 4. Nella sezione **Licenze di prodotto** spostare il selettore per Microsoft **365 Business** su **Disattivato** e l'opzione Crea utente senza licenza **del** prodotto su **On.**

    ![Scegliere la licenza del prodotto](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>Creare un account amministratore per gli interventi di emergenza

Devi anche creare un account di backup non configurato con l'autenticazione a più fattori (MFA) in modo da non bloccarti accidentalmente (ad esempio, se perdi il telefono che stai usando come seconda forma di verifica). Verificare che la password per questo account sia una frase o una lunghezza di almeno 16 caratteri. Questo account viene spesso definito "account break-glass".

## <a name="create-a-user-account-for-yourself"></a>Creare un account utente per se stessi

Utilizzare l'account utente per partecipare alla collaborazione con l'organizzazione, inclusa la verifica della posta. Ciò significa che le credenziali di amministratore potrebbero essere simili ad *Alice.Chavez <span></span> @Contoso.org* e il normale account utente potrebbe essere simile ad *Alice <span></span> @Contoso.com.*

Per creare un nuovo account utente:

1. Passare <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">all'interfaccia di amministrazione</a> e quindi scegliere **Utenti** \> **attivi nel** riquadro di spostamento sinistro.
2. Nella pagina **Utenti attivi** selezionare Aggiungi utente nella parte superiore  della pagina e nel riquadro Nuovo utente immettere il nome e altre informazioni. 
3. Espandere la **sezione Ruoli** e scegliere **Utente (nessun accesso amministrativo)**.
4. Nella sezione **Licenze di prodotto** spostare il selettore per Microsoft **365 Business** su **On.**

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a>Registrare ognuno di questi account per l'autenticazione a più fattori

Verificare che questi account utilizzino [l'autenticazione a più fattori.](m365-campaigns-multifactor-authenication.md)

## <a name="additional-recommendations"></a>Consigli aggiuntivi

- Assicurarsi che gli account amministratore siano impostati anche per l'autenticazione a più fattori. Verrà illustrato come eseguire questa operazione in Configurare [i criteri di accesso condizionale.](m365-campaigns-conditional-access.md)
- Prima di usare gli account amministratore, chiudi tutte le sessioni e le app del browser non correlate, inclusi gli account di posta elettronica personali. Puoi anche usare le finestre del browser private o in incognito.
- Dopo aver completato le attività di amministrazione, assicurarsi di disconnettersi dalla sessione del browser.
