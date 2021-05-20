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
description: Accedere con l'account Microsoft 365 account amministratore per reimpostare le password per gli utenti in Microsoft 365 per l'abbonamento aziendale.
ms.openlocfilehash: 8d4666eb70b1d5349f71c906f05510a8a54ded74
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571974"
---
# <a name="reset-passwords"></a>Reimpostare le password

In questo articolo viene illustrato come reimpostare le password per se stessi e per gli utenti quando si dispone di un Microsoft 365 per l'abbonamento aziendale.

## <a name="before-you-begin"></a>Prima di iniziare

Questo articolo è per le persone che impostano criteri di scadenza delle password in un'azienda, un istituto di istruzione o un'organizzazione no profit. Per completare questa procedura, è necessario accedere con l'account amministratore di Microsoft 365. [Che cos'è un account amministratore?](../../business-video/admin-center-overview.md).

Per eseguire questa [procedura, è necessario essere un amministratore globale](about-admin-roles.md) o un amministratore di password.

## <a name="watch-reset-a-business-password-for-a-user"></a>Guarda: Reimpostare una password aziendale per un utente

Guarda un breve video sulla reimpostazione delle password utente.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FVVP]

Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](../../business-video/index.yml).
  
## <a name="steps-reset-a-business-password-for-a-user"></a>Passaggi: Reimpostare una password aziendale per un utente

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

2. Nella pagina **Utenti attivi** selezionare l'utente e quindi Reimposta **password**.

3. Seguire le istruzioni riportate nella **pagina Reimposta password** per generare automaticamente una nuova password per l'utente o crearne una per l'utente, quindi selezionare **Reimposta**.  

4. Immettere un indirizzo e-mail a cui l'utente può accedere in modo che riceva la nuova password e seguirla per assicurarsi che l'abbia ricevuta.

## <a name="let-users-reset-their-own-passwords"></a>Consentire agli utenti di reimpostare le loro password

È consigliabile configurare la reimpostazione self-service delle password, in modo da evitare di dover reimpostare manualmente le password degli utenti. Per altre informazioni, vedere [Consentire agli utenti di reimpostare le loro password in Office 365](let-users-reset-passwords.md).

## <a name="reset-my-admin-password"></a>Reimpostare la password di amministratore

Utilizzare questi passaggi se si è dimenticata la password ma si è in grado di accedere Microsoft 365 perché, ad esempio, la password viene salvata nel browser:

1. Selezionare il proprio nome (icona) nell'angolo superiore destro > **Informazioni personali**  >  **dell'account personale**.

2. In **Dettagli contatto** verificare che la posta elettronica alternativa **sia** accurata e che sia stato fornito un numero di cellulare. In caso meno, cambiali ora.

3. Disconno: selezionare il proprio nome nell'angolo in alto a \> **destra Disconnettersi**.

4. A questo punto accedere di nuovo: digitare il proprio nome \> **utente Avanti** \> e quindi selezionare Password **dimenticata**.

5. Seguire i passaggi della procedura guidata per reimpostare la password. Utilizza le tue informazioni di contatto alternative per verificare che tu sia la persona giusta per reimpostare la password.

Se hai dimenticato la password e non riesci ad accedere:

- Chiedi a un altro amministratore globale della tua azienda di reimpostare la password per te.

- Assicurati di aver fornito informazioni di contatto alternative, incluso un numero di cellulare.

- In questo [caso, chiamare il supporto Tecnico Microsoft](../../business-video/get-help-support.md).

## <a name="reset-all-business-passwords-for-everyone-in-your-organization-at-the-same-time"></a>Reimpostare contemporaneamente tutte le password aziendali per tutti gli utenti dell'organizzazione
<a name="bkmk_forgot"> </a>

Questi passaggi sono validi per un'azienda con decine di utenti. Se hai centinaia o migliaia di utenti, vedi la sezione successiva sulla reimpostazione delle password in blocco (massimo 40 utenti alla volta).
  
1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

2. Selezionare l'opzione accanto a **Nome visualizzato** per selezionare tutti gli utenti dell'azienda. Quindi deseleziona te stesso. Non è possibile reimpostare la propria password contemporaneamente alla reimpostazione della password di tutti gli altri.

3. Selezionare **Reimposta password**. 

4. Seguire le istruzioni riportate nella **pagina Reimposta password** e selezionare **Reimposta**.  Se si è optato per la generazione automatica delle password, verranno visualizzate le nuove password temporanee.

5. Immettere un indirizzo di posta elettronica in cui è possibile ricevere le password temporanee. Dovrai avvisare gli utenti quali sono le loro password temporanee.
  
## <a name="reset-business-passwords-in-bulk"></a>Reimpostare le password aziendali in blocco
<a name="bkmk_forgot"> </a>

Usare PowerShell. Vedere questo post di Eyal Doron: [Gestire le password con PowerShell](https://go.microsoft.com/fwlink/?linkid=853696).
  
<!-- Here's a related article: [Set the passwords for multiple user accounts](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell). -->
  
Per informazioni generali, vedere [Gestire Microsoft 365 con PowerShell](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md).
  
## <a name="force-a-password-change-for-all-users-in-your-business"></a>Forzare la modifica della password per tutti gli utenti dell'organizzazione

Vedere questo interessante post di blog da Vasil Michev, MVP Microsoft: [Forzare la modifica della password per tutti gli utenti in Office 365](https://go.microsoft.com/fwlink/?linkid=853693).
  
## <a name="i-dont-have-a-microsoft-365-for-business-subscription"></a>Non ho un abbonamento Microsoft 365 per le aziende

Leggere questo articolo: [Si è dimenticato l'account o la password per l'account usato con Office](https://support.microsoft.com/office/eba0b4a2-c0ae-472c-99f6-bc63ee2425a8?wt.mc_id=SCL_reset-passwords_AdmHlp).
  
## <a name="related-content"></a>Contenuti correlati
  
[Consentire agli utenti di reimpostare le loro password](../add-users/let-users-reset-passwords.md) (articolo)

[Reimpostare la password](../add-users/reset-passwords.md) (articolo)

[Impostare la password di un singolo utente in modo che non scada mai](set-password-to-never-expire.md) (articolo)

[Impostare i criteri di scadenza della password per l'organizzazione](../manage/set-password-expiration-policy.md) (articolo)

[Microsoft 365 video di formazione aziendale](../../business-video/index.yml) (pagina dei collegamenti)