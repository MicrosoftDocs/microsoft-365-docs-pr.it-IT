---
title: Rimuovere utenti bloccati dal portale Utenti con restrizioni
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Gli amministratori possono scoprire come rimuovere gli utenti dal portale Utenti con restrizioni in Office 365. Gli utenti vengono aggiunti al portale Utenti con restrizioni se hanno inviato posta indesiderata in uscita, in genere in seguito a una compromissione dell'account.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 32748d717762d7af727a1583226b6d47ee7697c6
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205737"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a>Rimuovere utenti bloccati dal portale Utenti con restrizioni in Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Se un utente supera uno dei limiti di invio in uscita, come specificato nei [limiti di servizio](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) o nei [criteri di posta indesiderata in uscita](configure-the-outbound-spam-policy.md), l'utente non può inviare messaggi di posta elettronica, ma può continuare a riceverne.

L'utente viene aggiunto al portale Utenti con restrizioni nel Centro sicurezza e conformità. Quando prova a inviare messaggi di posta elettronica, il messaggio viene restituito in un rapporto di mancato recapito, noto anche come NDR o notifica di mancato recapito, con il codice di errore [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) e il testo seguente:

> "Non è stato possibile recapitare il messaggio perché l'utente non è stato riconosciuto come mittente valido. La causa più comune di questo problema è che l'indirizzo di posta elettronica sia sospettato di inviare posta indesiderata e che non sia più autorizzato a inviare messaggi di posta elettronica.  Contattare l'amministratore della posta elettronica per ricevere assistenza. Il server remoto ha restituito l'errore "550 5.1.8 Access denied, bad outbound sender."

Gli amministratori possono rimuovere gli utenti dal portale Utenti con restrizioni nel Centro sicurezza e conformità o in PowerShell per Exchange Online.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Aprire il Centro sicurezza e conformità in<https://protection.office.com/>. Per passare direttamente alla pagina **Utenti con restrizioni**, usare <https://protection.office.com/restrictedusers>.

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in **Exchange Online**:
  - Per rimuovere gli utenti dal portale Utenti con restrizioni è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **Amministratore della sicurezza**.
  - Per l'accesso in sola lettura al portale Utenti con restrizioni, è necessario essere un membro del gruppo di ruoli **Amministratore con autorizzazioni di lettura globali** o **Amministratore che legge i dati di sicurezza**.

  Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).
  >
  > - Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.

- Un mittente che supera i limiti di posta elettronica in uscita è un indicatore di account compromesso. Prima di rimuovere l'utente dal portale Utenti con restrizioni, assicurarsi di seguire i passaggi necessari per riprendere il controllo dell'account. Per altre informazioni, vedere [Rispondere a un account di posta elettronica compromesso in Office 365](responding-to-a-compromised-email-account.md).

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a>Usare il Centro sicurezza e conformità per rimuovere un utente dall'elenco Utenti con restrizioni

1. Nel Centro sicurezza e conformità, passare a **Gestione delle minacce** \> **Rivedi** \> **Utenti con restrizioni**.

2. Individuare e selezionare l’utente che si desidera sbloccare. Nella colonna **Azioni** fare clic su **Sblocca**.

3. I dettagli relativi all'account al quale è stato impedito l'invio di messaggi saranno visualizzati in un menu a comparsa. Si consiglia di consultare i suggerimenti per assicurarsi di eseguire le operazioni appropriate nel caso in cui l'account sia effettivamente compromesso. Al termine, fare clic su **Avanti**.

4. La schermata successiva include suggerimenti che consentono di evitare compromissioni future. L'autenticazione a più fattori (MFA) e la modifica delle password sono buone soluzioni di difesa. Al termine, fare clic su **Sblocca utente**.

5. Fare clic su **Sì** per confermare la modifica.

   > [!NOTE]
   > La rimozione di tutte le restrizioni utente può richiedere fino a 24 ore.

## <a name="verify-the-alert-settings-for-restricted-users"></a>Verificare le impostazioni di avviso per gli utenti con restrizioni

Il criterio di avviso predefinito denominato **Utente al quale è stato impedito di inviare messaggi di posta elettronica** invierà automaticamente una notifica agli amministratori quando gli utenti sono bloccati dall'invio di posta in uscita. È possibile verificare queste impostazioni e aggiungere altri utenti a cui inviare una notifica. Per ulteriori informazioni sui criteri di avviso, vedere [Criteri di avviso nel Centro sicurezza e conformità](../../compliance/alert-policies.md).

> [!IMPORTANT]
> Per il corretto funzionamento degli avvisi, la ricerca nel log di controllo deve essere attivata. Per altre informazioni, vedere [Attivare o disattivare la ricerca nel log di controllo](../../compliance/turn-audit-log-search-on-or-off.md).

1. Nel Centro sicurezza e conformità, passare a **Avvisi** \> **Criteri di avviso**.

2. Individuare e selezionare l'avviso relativo agli **utenti ai quali è stato impedito di inviare posta elettronica**.

3. Nel riquadro a comparsa visualizzato verificare o configurare le impostazioni seguenti:

   - **Stato**: verificare che l'avviso sia attivato ![Attiva](../../media/scc-toggle-on.png).

   - **Destinatari di posta elettronica**: fare clic su **Modifica** e verificare o configurare le impostazioni seguenti nel riquadro a comparsa **Modifica destinatari** visualizzato:

     - **Invia notifiche tramite posta elettronica**: verificare che la casella di controllo sia selezionata (**Attivato**).

     - **Destinatari di posta elettronica**: il valore predefinito è **TenantAdmins**, ossia i membri di **Amministratore globale**. Per aggiungere altri destinatari, fare clic in un'area vuota della casella. Verrà visualizzato un elenco di destinatari e si può iniziare a digitare un nome per filtrare e selezionare un destinatario. È possibile rimuovere un destinatario esistente dalla casella facendo clic sull’![icona Rimuovi](../../media/scc-remove-icon.png) accanto al nome.

     - **Limite giornaliero per le notifiche**: il valore predefinito è **Nessun limite**, ma è possibile selezionare un limite per il numero massimo di notifiche giornaliere.

     Al termine, scegliere **Salva**.

4. Nel riquadro a comparsa **relativo agli utenti ai quali è stato impedito di inviare posta elettronica** fare clic su **Chiudi**.

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a>Usare PowerShell per Exchange Online per visualizzare e rimuovere utenti dall'elenco Utenti con restrizioni

Per visualizzare l’elenco di utenti ai quali è stato impedito di inviare posta elettronica, eseguire il comando seguente:

```powershell
Get-BlockedSenderAddress
```

Per visualizzare i dettagli di un utente specifico, sostituire \<emailaddress\> con l'indirizzo di posta elettronica corrispondente ed eseguire il comando seguente:

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

Per informazioni dettagliate su sintassi e parametri, vedere [Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress).

Per rimuovere un utente dall'elenco Utenti con Restrizioni, sostituire \<emailaddress\> con l'indirizzo di posta elettronica corrispondente ed eseguire il comando seguente:

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

Per informazioni dettagliate su sintassi e parametri, vedere [Remove-BlockedSenderAddress](/powershell/module/exchange/remove-blockedsenderaddress).