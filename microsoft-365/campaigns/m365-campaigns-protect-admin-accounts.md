---
title: Proteggere gli account di amministratore
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
description: Informazioni su come configurare e proteggere gli account di amministratore.
ms.openlocfilehash: dc5f72cda0255641d7d2407d266a6ae584560733
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527187"
---
# <a name="protect-your-administrator-accounts"></a>Proteggere gli account di amministratore

Poiché gli account di amministrazione sono dotati di privilegi elevati, sono obiettivi di valore per gli hacker e i criminali informatici. In questo articolo viene descritto:

- Informazioni su come configurare un account di amministratore aggiuntivo per le emergenze.
- Come proteggere tali account.
 
Quando ti iscrivi a Microsoft 365 e immetti le tue informazioni, diventi automaticamente l'amministratore globale. Un amministratore globale ha il controllo definitivo degli account utente e di tutte le altre impostazioni nell'interfaccia di amministrazione di Microsoft, ma esistono diversi tipi di account di amministrazione con vari gradi di accesso. Vedere [About admin Roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) per informazioni sui diversi livelli di accesso per ogni tipo di ruolo di amministratore.


## <a name="create-additional-admin-accounts"></a>Creare account di amministratore aggiuntivi

Utilizzare gli account di amministrazione solo per l'amministrazione. Gli amministratori devono disporre di un account utente separato per l'utilizzo regolare delle app di Office e utilizzare il proprio account amministrativo solo quando necessario per gestire gli account e i dispositivi e durante la lavorazione di altre funzioni di amministratore. È inoltre consigliabile rimuovere la licenza Microsoft 365 dagli account di amministrazione in modo che non sia necessario pagarli.

Sarà necessario configurare almeno un account di amministratore globale aggiuntivo per concedere l'accesso all'amministratore a un altro dipendente attendibile. È inoltre possibile creare account amministratore distinti per la gestione degli utenti (questo ruolo è denominato **amministratore Gestione utenti**). Per ulteriori informazioni, vedere [informazioni sui ruoli di amministratore](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).

Per creare account di amministratore aggiuntivi:

 1. Passare all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">Amministrazione</a> e quindi scegliere **utenti** \> **attivi utenti** nel NAV sinistro.

    ![Scegliere utenti e quindi utenti attivi nel NAV sinistro](../media/Activeusers.png)

2. Nella pagina **utenti attivi** selezionare **Aggiungi un utente** nella parte superiore della pagina e nel **nuovo pannello utente** immettere il nome e altre informazioni.
3. Espandere la sezione **ruoli** e scegliere **amministratore globale** per concedere all'utente l'accesso all'amministratore globale. È inoltre possibile scegliere **amministratore personalizzato** e scegliere uno qualsiasi dei ruoli visualizzati.

    Immettere un messaggio di posta elettronica alternativo nella casella di testo **indirizzo di posta elettronica alternativo** . È possibile utilizzare questo indirizzo per recuperare le informazioni sulla password se si viene bloccati. Per gli amministratori globali, verrà inviata anche un'istruzione di fatturazione a questo indirizzo.

    ![Scegliere il ruolo di amministratore](../media/adminroles.png)
    
4. Nella sezione **licenze di prodotto** spostare il selettore di **Microsoft 365 business** su **disattivato** e la **licenza Crea utente senza prodotto** **su**attivato.

    ![Scegliere la licenza del prodotto](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>Creare un account di amministratore di emergenza

È inoltre necessario creare un account di backup non configurato con l'autenticazione a più fattori (AMF), in modo da non bloccarsi accidentalmente (ad esempio, se si perde il telefono che si sta utilizzando come seconda forma di verifica). Verificare che la password per l'account sia una frase o almeno 16 caratteri. Questo è spesso definito come un "account break-Glass".

## <a name="create-a-user-account-for-yourself"></a>Creare un account utente autonomo

Utilizzare l'account utente per partecipare alla collaborazione con l'organizzazione, inclusa la verifica della posta. Questo significa che le credenziali di amministratore potrebbero essere simili a *Alice. Chavez <span></span> @Contoso. org* e l'account utente normale potrebbe essere simile a *Alice <span></span> @Contoso. com*.

Per creare un nuovo account utente:
1. Passare all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">Amministrazione</a> e quindi scegliere **utenti** \> **attivi utenti** nel NAV sinistro.
2. Nella pagina **utenti attivi** selezionare **Aggiungi un utente** nella parte superiore della pagina e nel **nuovo pannello utente** immettere il nome e altre informazioni.
3. Espandere la sezione **ruoli** e scegliere **utente (senza accesso amministrativo)**.
1. Nella sezione **licenze di prodotto** spostare il selettore di **Microsoft 365 business** **su**attivato. 

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a>Registrare ognuno di questi account per l'autenticazione a più fattori


## <a name="additional-recommendations"></a>Suggerimenti aggiuntivi

- Assicurarsi che anche gli account di amministrazione siano configurati per l'autenticazione a più fattori. Verrà illustrato come eseguire questa operazione in configurare i [criteri di accesso condizionale](m365-campaigns-conditional-access.md).
- Prima di utilizzare gli account di amministrazione, chiudere tutte le app e le sessioni del browser non correlate, compresi gli account di posta elettronica personali. È inoltre possibile utilizzare le finestre del browser private o in incognito.
- Dopo aver completato le attività amministrative, accertarsi di disconnettersi dalla sessione del browser.
