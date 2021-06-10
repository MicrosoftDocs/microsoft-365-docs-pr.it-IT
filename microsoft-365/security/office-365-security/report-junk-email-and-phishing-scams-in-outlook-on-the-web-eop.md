---
title: Segnalare posta indesiderata e phishing in Outlook sul Web
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni sulle opzioni predefinite per la segnalazione della posta indesiderata, non della posta indesiderata e di phishing in Outlook sul Web (Outlook Web App) in Exchange Online e su come disabilitare queste opzioni di segnalazione per gli utenti.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1139871f5929ff9fef29e980b7614e5bc7b92570
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788308"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>Segnalare la posta indesiderata e il phishing Outlook sul Web in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nelle organizzazioni Microsoft 365 con cassette postali in Exchange Online o cassette postali locali che utilizzano l'autenticazione moderna [ibrida,](../../enterprise/hybrid-modern-auth-overview.md)è possibile inviare falsi positivi (buona posta elettronica contrassegnata come posta indesiderata), falsi negativi (posta elettronica non consentita) e messaggi di phishing a Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

> [!IMPORTANT]
> È consigliabile il componente aggiuntivo Segnala messaggio o Segnala phishing per gli invii degli utenti. Per ulteriori informazioni, vedere [Enable the Report Message or the Report Phishing add-ins.](./enable-the-report-message-add-in.md) Non è consigliabile l'esperienza di creazione di report incorporata in Outlook perché non può usare i criteri di invio [degli utenti.](./user-submission.md)

- Se si è un amministratore di un'organizzazione con Exchange Online cassette postali, è consigliabile utilizzare il portale invii nel Centro sicurezza & conformità. Per ulteriori informazioni, vedere [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

- Gli amministratori possono disabilitare o abilitare la possibilità per gli utenti di segnalare messaggi a Microsoft in Outlook sul Web. Per informazioni dettagliate, vedere la sezione [Disabilitare o](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) abilitare la segnalazione della posta indesiderata in Outlook sul Web più avanti in questo articolo.

- È possibile configurare i messaggi segnalati da copiare o reindirizzare a una cassetta postale specificata. Per ulteriori informazioni, vedere [Criteri di invio degli utenti.](user-submission.md)

- Per ulteriori informazioni sulla segnalazione dei messaggi a Microsoft, vedere [Segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Disabilitare o abilitare la segnalazione della posta indesiderata Outlook sul Web

Per impostazione predefinita, gli utenti possono segnalare falsi positivi, falsi negativi e messaggi di phishing di posta indesiderata a Microsoft per l'analisi in Outlook sul Web. Gli amministratori possono configurare Outlook criteri cassetta postale sul Web in Exchange Online PowerShell per impedire agli utenti di segnalare falsi positivi e falsi negativi di posta indesiderata a Microsoft. Non è possibile disabilitare la possibilità per gli utenti di segnalare messaggi di phishing a Microsoft.

### <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni Exchange Online in questo articolo. In particolare, sono necessari i **ruoli Criteri** **destinatario** o  Destinatari di posta, assegnati ai gruppi di ruoli Gestione organizzazione e Gestione destinatari per impostazione predefinita.  Per ulteriori informazioni sui gruppi di ruoli in Exchange Online, vedere [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) e Modify role groups in [Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).

- Ogni organizzazione dispone di un criterio predefinito denominato OwaMailboxPolicy-Default, ma è possibile creare criteri personalizzati. I criteri personalizzati vengono applicati agli utenti con ambito prima del criterio predefinito. Per ulteriori informazioni sulle Outlook sui criteri cassetta postale Web, vedere [Outlook sui criteri cassetta](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)postale web in Exchange Online .

- La disabilitazione della segnalazione della posta indesiderata non rimuove la possibilità di contrassegnare un messaggio come indesiderato o non indesiderato Outlook sul Web. Se si seleziona un messaggio  nella cartella Posta indesiderata e si fa clic su Non posta indesiderata, il messaggio viene comunque spostato \>  di nuovo nella cartella Posta in arrivo. Se si seleziona un messaggio  in qualsiasi altra cartella di posta elettronica e si fa clic su Posta indesiderata, il messaggio viene comunque \>  spostato nella cartella Posta indesiderata. Ciò che non è più disponibile è l'opzione per segnalare il messaggio a Microsoft.

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Usare Exchange Online PowerShell per disabilitare o abilitare la segnalazione della posta indesiderata Outlook sul Web

1. Per trovare i criteri delle cassette postali Outlook sul Web e lo stato della segnalazione della posta indesiderata, eseguire il comando seguente:

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. Per disabilitare o abilitare la segnalazione della posta indesiderata Outlook sul Web, utilizzare la sintassi seguente:

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   In questo esempio viene disabilitata la segnalazione della posta indesiderata nel criterio predefinito.

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   In questo esempio viene abilitata la segnalazione della posta indesiderata nel criterio personalizzato denominato Contoso Managers.

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) e [Set-OwaMailboxPolicy.](/powershell/module/exchange/set-owamailboxpolicy)

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare che la segnalazione della posta indesiderata sia stata abilitata o disabilitata correttamente Outlook sul Web, eseguire una delle operazioni seguenti:

- In Exchange Online PowerShell, eseguire il comando seguente e verificare il valore della proprietà **ReportJunkEmailEnabled:**

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- Aprire la cassetta postale di un utente interessato in Outlook sul Web,  selezionare un messaggio nella posta in arrivo, fare clic su Posta indesiderata e verificare che la richiesta di segnalare il messaggio a Microsoft sia o non sia \>  visualizzata.<sup>\*</sup>

- Aprire la cassetta postale di un utente interessato in Outlook sul Web, selezionare  un messaggio nella cartella Posta indesiderata, fare clic su Posta indesiderata e verificare che la richiesta di segnalare il messaggio a Microsoft sia o non sia \>  visualizzata.<sup>\*</sup>

<sup>\*</sup> Gli utenti possono nascondere la richiesta di segnalare il messaggio pur segnalando il messaggio. Per verificare questa impostazione in Outlook sul Web:

1. Fare **clic Impostazioni** Outlook sull'icona Impostazioni Web Visualizza tutte Outlook impostazioni Posta indesiderata ![ ](../../media/owa-settings-icon.png) \>  \> .
2. Nella sezione **Report** verificare il valore: **Chiedi conferma prima di inviare un report.**

   ![Outlook sul Web per la segnalazione della posta indesiderata](../../media/owa-junk-email-reporting-options.png)
