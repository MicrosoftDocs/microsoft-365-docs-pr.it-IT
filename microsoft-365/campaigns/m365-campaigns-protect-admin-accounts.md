---
title: Proteggere gli account di amministratore
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
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
ms.openlocfilehash: 0d687407fad1cec5da49dbc33ffeb84366f1c309
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398242"
---
# <a name="protect-your-administrator-accounts"></a>Proteggere gli account di amministratore

Poiché gli account amministratore dispongono di privilegi elevati, sono obiettivi preziosi per hacker e criminali informatici. In questo articolo viene descritto:

- Come configurare un account amministratore aggiuntivo per le emergenze.
- Come proteggere questi account.

Quando ti i sign up for Microsoft 365 e immetti le informazioni, diventi automaticamente l'amministratore globale. Un amministratore globale ha il controllo finale degli account utente e di tutte le altre impostazioni nell'interfaccia di amministrazione di Microsoft, ma esistono molti tipi diversi di account di amministratore con diversi gradi di accesso. Per informazioni sui diversi livelli di accesso per ogni tipo di ruolo di amministratore, vedere about [admin roles.](/office365/admin/add-users/about-admin-roles)

## <a name="create-additional-admin-accounts"></a>Creare altri account amministratore

Utilizzare gli account amministratore solo per l'amministrazione. Gli amministratori devono disporre di un account utente separato per l'uso regolare delle app Office e usare il proprio account amministrativo solo se necessario per gestire account e dispositivi e mentre lavorano su altre funzioni di amministratore. È anche buona idea rimuovere la licenza Microsoft 365 dagli account di amministratore in modo da non doverli pagare.

È necessario configurare almeno un altro account amministratore globale per concedere l'accesso di amministratore a un altro dipendente attendibile. È inoltre possibile creare account amministratore distinti per la gestione degli utenti (questo ruolo è denominato **Amministratore gestione utenti**). Per ulteriori informazioni, vedere [About admin roles](/office365/admin/add-users/about-admin-roles).

Per creare altri account amministratore:

 1. Passare <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">all'interfaccia di amministrazione</a> e quindi scegliere **Utenti** \> **Utenti attivi** nel riquadro di spostamento sinistro.

    ![Scegliere Utenti e quindi Utenti attivi nel riquadro di spostamento sinistro](../media/Activeusers.png)

 2. Nella pagina **Utenti attivi** seleziona **Aggiungi** utente nella parte superiore  della pagina e nel riquadro Nuovo utente immetti il nome e altre informazioni.
 3. Espandere la **sezione Ruoli** e scegliere Amministratore **globale per** concedere all'utente l'accesso di amministratore globale. È inoltre possibile **scegliere Amministratore personalizzato** e scegliere uno dei ruoli visualizzati.

    Immettere un messaggio di posta elettronica alternativo nella **casella di testo Indirizzo di posta** elettronica alternativo. È possibile utilizzare questo indirizzo per recuperare le informazioni sulla password se si viene bloccati. Per gli amministratori globali, verrà inviato anche un estratto conto a questo indirizzo.

    ![Scegliere il ruolo di amministratore](../media/adminroles.png)

 4. Nella sezione **Licenze prodotto** spostare il selettore per Microsoft 365 Business **su** **Disattivato** e l'opzione Crea utente senza licenza **del** prodotto su **Su**.

    ![Scegliere la licenza del prodotto](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>Creare un account amministratore per gli interventi di emergenza

Devi anche creare un account di backup che non sia configurato con l'autenticazione a più fattori (MFA) in modo da non bloccarti accidentalmente (ad esempio, se perdi il telefono che stai usando come seconda forma di verifica). Assicurarsi che la password per questo account sia una frase o almeno 16 caratteri. Questo viene spesso definito "account break-glass".

## <a name="create-a-user-account-for-yourself"></a>Creare un account utente per se stessi

Utilizzare l'account utente per partecipare alla collaborazione con l'organizzazione, inclusa la verifica della posta. Ciò significa che le credenziali di amministratore potrebbero essere simili  *a Alice.Chavez <span></span> @Contoso.org* e il tuo account utente normale potrebbe essere simile a *Alice <span></span> @Contoso.com*.

Per creare un nuovo account utente:

1. Passare <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">all'interfaccia di amministrazione</a> e quindi scegliere **Utenti** \> **Utenti attivi** nel riquadro di spostamento sinistro.
2. Nella pagina **Utenti attivi** seleziona **Aggiungi** utente nella parte superiore  della pagina e nel riquadro Nuovo utente immetti il nome e altre informazioni.
3. Espandere la **sezione** Ruoli e scegliere **Utente (nessun accesso amministrativo)**.
4. Nella sezione **Licenze prodotto** spostare il selettore **per** Microsoft 365 Business su **Su**.

## <a name="turn-on-security-defaults"></a>Attivare le impostazioni predefinite di sicurezza

Le impostazioni predefinite di sicurezza consentono di proteggere l'organizzazione da attacchi correlati all'identità fornendo impostazioni di sicurezza preconfigurate gestite da Microsoft per conto dell'organizzazione. Queste impostazioni includono l'abilitazione dell'autenticazione a più fattori (MFA) per tutti gli amministratori e gli account utente. Per ulteriori informazioni sulle impostazioni predefinite di sicurezza e per informazioni su come abilitarle, vedere [Attivare le impostazioni predefinite di sicurezza.](m365-campaigns-conditional-access.md)

## <a name="additional-recommendations"></a>Suggerimenti aggiuntivi

- Prima di usare gli account di amministratore, chiudi tutte le app e le sessioni del browser non correlate, inclusi gli account di posta elettronica personali. Puoi anche usare le finestre del browser private o in incognito.
- Dopo aver completato le attività di amministrazione, assicurati di disconnettersi dalla sessione del browser.
