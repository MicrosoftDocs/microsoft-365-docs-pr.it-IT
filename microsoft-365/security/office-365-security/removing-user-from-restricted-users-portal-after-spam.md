---
title: Rimozione di un utente dal portale Utenti con restrizioni dopo l'invio di posta indesiderata
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/10/2019
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Se un utente invia continuamente messaggi di posta elettronica da Office 365 che vengono classificati come posta indesiderata, all'utente sarà impedito di inviare altri messaggi e-mail.
ms.openlocfilehash: d0409a16a8584e7561f04a30fcc4184bfa41d87c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084343"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a>Rimozione di un utente dal portale Utenti con restrizioni dopo l'invio di posta indesiderata

Se un utente invia continuamente messaggi di posta elettronica che vengono classificati come posta indesiderata da Office 365, all'utente sarà impedito di inviare messaggi di posta di posta elettronica, ma potrà continuare a riceverne. L'utente sarà indicato nel servizio come mittente in uscita non valido e riceverà il seguente rapporto di mancato recapito:

> "Non è stato possibile recapitare il messaggio perché l'utente non è stato riconosciuto come mittente valido. La causa più comune di questo problema è che l'indirizzo di posta elettronica sia sospettato di inviare posta indesiderata e che non sia più autorizzato a inviare messaggi di posta elettronica.  Contattare l'amministratore della posta elettronica per ricevere assistenza. Il server remoto ha restituito l'errore "550 5.1.8 Access denied, bad outbound sender."

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare
<a name="sectionSection0"> </a>

Tempo stimato per il completamento: 5 minuti
  
Devi disporre delle autorizzazioni per poter eseguire queste procedure.  Per sapere quali autorizzazioni sono necessarie, vedere la voce "Protezione da posta indesiderata" nell'argomento [Autorizzazioni funzionalità in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx).

La seguente procedura può essere eseguita anche tramite PowerShell remota. Utilizzare il cmdlet Get-BlockedSenderAddress per ottenere l'elenco degli utenti con restrizioni e Remove-BlockedSenderAddress per rimuovere la restrizione. Per informazioni su come usare Windows PowerShell per connettersi a Exchange Online, vedere [Connessione a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a>Rimozione delle restrizioni per un account di posta elettronica di Office 365 bloccato

Questa attività viene completata nel Centro sicurezza e conformità. [Accedere al Centro sicurezza e conformità](../../compliance/go-to-the-securitycompliance-center.md) per maggiori informazioni sul Centro sicurezza e conformità. Per eseguire queste funzioni, è necessario essere membri del gruppo di ruoli **Gestione organizzazione** o **Amministratore della protezione**. [Accedere ad Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md) per maggiori informazioni sui gruppi di ruoli del Centro sicurezza e conformità.

1. Se si utilizza un account aziendale o dell'istituto di istruzione con privilegi di amministratore globale di Office 365, accedere al Centro sicurezza e conformità di Office 365 e nell'elenco sulla sinistra espandere **Gestione delle minacce**, scegliere **Revisione**, quindi **Utenti con restrizioni**.
    
    > [!TIP]
    > Per accedere direttamente alla pagina **Utenti con restrizioni** (in precedenza nota come Centro notifiche) nel Centro sicurezza e conformità, utilizzare questo URL: > [https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. Questa pagina contiene l'elenco di utenti ai quali è stato impedito di inviare messaggi di posta elettronica.  Trovare l'utente dal quale si desidera rimuovere le restrizioni e selezionare**Sblocca**.

3. I dettagli relativi all'account al quale è stato impedito l'invio di messaggi saranno visualizzati in un menu a comparsa. Si consiglia di consultare i suggerimenti per assicurarsi di eseguire le operazioni appropriate nel caso in cui l'account sia effettivamente compromesso. Al termine, fare clic su **Avanti**.

4. La schermata successiva include suggerimenti che consentono di evitare compromissioni future. L'autenticazione a più fattori (MFA) e la modifica delle password sono buone soluzioni di difesa. Al termine, fare clic su **Sblocca utente**.

5. Fare clic su **Sì** per confermare la modifica.

    > [!NOTE]
    > La rimozione delle restrizioni potrebbe richiedere almeno 30 minuti. 

## <a name="making-sure-admins-are-alerted-when-this-happens"></a>Assicurarsi che gli amministratori vengano avvisati durante questa operazione.

L'avviso relativo a un utente al quale è stato impedito di inviare messaggi di posta elettronica è disponibile come criterio nella pagina dei criteri del Centro sicurezza e conformità di Office 365. In precedenza si trattava del criterio di posta indesiderata in uscita, ma ora è nativo nella piattaforma degli avvisi di Office 365. Per ulteriori informazioni sugli avvisi, accedere a [Criteri di avviso nel Centro sicurezza e conformità](../../compliance/alert-policies.md).

> [!IMPORTANT]
> Per il corretto funzionamento degli avvisi, la ricerca nel log di controllo deve essere attivata. Per ulteriori informazioni, vedere come [attivare o disattivare la ricerca nel log di controllo in Office 365](../../compliance/turn-audit-log-search-on-or-off.md).

I criteri per questo avviso sono predefiniti, sono inclusi in tutti i tenant di Office 365 e non è necessario configurarli. Si tratta di un avviso con livello di gravità alto e verrà recapitato un messaggio di posta elettronica al gruppo TenantAdmins configurato quando l'avviso viene attivato nel caso in cui a un utente venga impedito di inviare email. Gli amministratori possono aggiornare il gruppo notificato quando si attiva questo avviso accedendo all'avviso nel portale del Centro sicurezza e conformità > Avvisi > Criteri di avviso > Utenti ai quali è stato impedito di inviare email.

È possibile modificare l'avviso per:
- Attivare o disattivare le notifiche di posta elettronica
- Inviare messaggi di posta elettronica ai destinatari necessari
- Limitare le notifiche giornaliere

## <a name="checking-for-and-removing-restrictions-using-powershell"></a>Controllare e rimuovere eventuali restrizioni usando PowerShell
I comandi di PowerShell per utenti con restrizioni sono:
- `Get-BlockedSenderAddress`: eseguire per recuperare l'elenco di utenti ai quali è stato impedito di inviare posta elettronica
- `Remove-BlockedSenderAddress`: eseguire per rimuovere l'utente o gli utenti con restrizioni

## <a name="for-more-information"></a>Ulteriori informazioni

[Rispondere a un account di posta elettronica compromesso](../../compliance/responding-to-a-compromised-email-account.md)

[Informazioni sull'avviso relativo agli utenti ai quali è stato impedito di inviare posta elettronica](https://docs.microsoft.com/it-IT/office365/securitycompliance/alert-policies)

[Pool di recapito ad alto rischio per i messaggi in uscita](high-risk-delivery-pool-for-outbound-messages.md)

[Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md)

[Criteri di avviso nel Centro sicurezza e conformità](https://docs.microsoft.com/it-IT/office365/securitycompliance/alert-policies)
