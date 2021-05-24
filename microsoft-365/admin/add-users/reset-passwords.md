---
title: Reimpostare le password
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7a5d073b-7fae-4aa5-8f96-9ecd041aba9c
description: Accedi con il tuo account Microsoft 365 amministratore per reimpostare le password per gli utenti in Microsoft 365 per le aziende.
ms.openlocfilehash: 0cec6c7874b51c76fca60c6c237395c940c47bbe
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635571"
---
# <a name="reset-passwords"></a>Reimpostare le password

In questo articolo viene illustrato come reimpostare le password per se stessi e per gli utenti quando si dispone di un abbonamento Microsoft 365 per le aziende.

## <a name="before-you-begin"></a>Prima di iniziare

Questo articolo è per le persone che impostano criteri di scadenza delle password in un'azienda, un istituto di istruzione o un'organizzazione no profit. Per completare questa procedura, è necessario accedere con l'account amministratore di Microsoft 365. [Che cos'è un account amministratore?](../../business-video/admin-center-overview.md).

Per eseguire questa [procedura, è](about-admin-roles.md) necessario essere un amministratore globale o un amministratore delle password.

## <a name="watch-reset-a-business-password-for-a-user"></a>Watch: Reset a business password for a user

Guarda un breve video sulla reimpostazione delle password degli utenti.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FVVP]

Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](../../business-video/index.yml).
  
## <a name="steps-reset-a-business-password-for-a-user"></a>Passaggi: Reimpostare una password aziendale per un utente

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

2. Nella pagina **Utenti attivi** selezionare l'utente e quindi Reimposta **password.**

3. Seguire le istruzioni nella pagina **Reimposta password** per generare automaticamente una nuova password per l'utente o crearne una per loro, quindi selezionare **Reimposta**.  

4. Immetti un indirizzo di posta elettronica a cui l'utente può accedere in modo che riceva la nuova password e seguilo per assicurarti di ottenerla.

## <a name="let-users-reset-their-own-passwords"></a>Consentire agli utenti di reimpostare le loro password

È consigliabile configurare la reimpostazione self-service delle password, in modo da evitare di dover reimpostare manualmente le password degli utenti. Per altre informazioni, vedere [Consentire agli utenti di reimpostare le loro password in Office 365](let-users-reset-passwords.md).

## <a name="reset-my-admin-password"></a>Reimpostare la password di amministratore

Seguire questa procedura se hai dimenticato la password ma sei in grado di accedere a Microsoft 365 perché, ad esempio, la password viene salvata nel browser:

1. Seleziona il tuo nome (icona) nell'angolo in alto a destra > **Informazioni personali**  >  **account** personale .

2. In **Dettagli contatto** verificare che l'indirizzo di posta elettronica alternativo sia accurato e che sia stato fornito un numero di cellulare.  In caso contrario, modificarli ora.

3. Disconnessione: selezionare il proprio nome nell'angolo in alto a destra \> **Disconnettersi.**

4. Eseguire di nuovo l'accesso: digitare il nome utente \> **Avanti** \> e quindi selezionare Password **dimenticata.**

5. Seguire i passaggi della procedura guidata per reimpostare la password. Usa le info di contatto alternative per verificare di essere la persona giusta per reimpostare la password.

Se hai dimenticato la password e non riesci ad accedere:

- Chiedere a un altro amministratore globale dell'azienda di reimpostare la password.

- Assicurati di aver fornito informazioni di contatto alternative, incluso un numero di cellulare.

- In caso contrario, [chiamare il Supporto Tecnico Microsoft.](../../business-video/get-help-support.md)

## <a name="reset-all-business-passwords-for-everyone-in-your-organization-at-the-same-time"></a>Reimpostare tutte le password aziendali per tutti gli utenti dell'organizzazione contemporaneamente
<a name="bkmk_forgot"> </a>

Questi passaggi sono validi per un'azienda con decine di utenti. Se si dispone di centinaia o migliaia di utenti, vedere la sezione successiva sulla reimpostazione delle password in blocco (massimo 40 utenti alla volta).
  
1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

2. Seleziona l'opzione accanto a **Nome visualizzato** per selezionare tutti gli utenti dell'azienda. Deseleziona quindi te stesso. Non è possibile reimpostare la propria password contemporaneamente alla password di tutti gli altri utenti.

3. Selezionare **Reimposta password**. 

4. Seguire le istruzioni nella pagina **Reimposta password** e selezionare **Reimposta**.  Se hai scelto di generare automaticamente le password, verranno visualizzate le nuove password temporanee.

5. Immettere un indirizzo di posta elettronica in cui è possibile ricevere le password temporanee. Dovrai notificare agli utenti quali sono le password temporanee.
  
## <a name="reset-business-passwords-in-bulk"></a>Reimpostare le password aziendali in blocco
<a name="bkmk_forgot"> </a>

Usare PowerShell. Vedere questo post di Eyal Doron: [Gestire le password con PowerShell](https://go.microsoft.com/fwlink/?linkid=853696).
  
<!-- Here's a related article: [Set the passwords for multiple user accounts](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell). -->
  
Per informazioni generali, vedere [Manage Microsoft 365 with PowerShell](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md).
  
## <a name="force-a-password-change-for-all-users-in-your-business"></a>Forzare la modifica della password per tutti gli utenti dell'organizzazione

Vedere questo interessante post di blog da Vasil Michev, MVP Microsoft: [Forzare la modifica della password per tutti gli utenti in Office 365](https://go.microsoft.com/fwlink/?linkid=853693).
  
## <a name="i-dont-have-a-microsoft-365-for-business-subscription"></a>Non ho un abbonamento Microsoft 365 per le aziende

Leggere questo articolo: [Si è dimenticato l'account o la password per l'account usato con Office](https://support.microsoft.com/office/eba0b4a2-c0ae-472c-99f6-bc63ee2425a8?wt.mc_id=SCL_reset-passwords_AdmHlp).
  
## <a name="related-content"></a>Contenuto correlato
  
[Consentire agli utenti di reimpostare le proprie password](../add-users/let-users-reset-passwords.md) (articolo)\
[Reimpostare le password](../add-users/reset-passwords.md) (articolo)\
[Impostare la password di un singolo utente](set-password-to-never-expire.md) in modo che non scada mai (articolo)\
[Impostare i criteri di scadenza delle password per l'organizzazione](../manage/set-password-expiration-policy.md) (articolo)\
[video Microsoft 365 formazione su Microsoft 365](../../business-video/index.yml) per le aziende (pagina dei collegamenti)