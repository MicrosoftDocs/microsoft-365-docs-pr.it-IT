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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7a5d073b-7fae-4aa5-8f96-9ecd041aba9c
description: "Informazioni su come reimpostare la password per un utente nell'abbonamento a Microsoft 365 for business. "
ms.openlocfilehash: 14226927680c70035a01d9390f114cb0bfddbf38
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "44064810"
---
# <a name="reset-passwords"></a>Reimpostare le password

Guardare un breve video sulla reimpostazione delle password degli utenti.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FVVP] 

Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).
  
## <a name="let-users-reset-their-own-passwords"></a>Consentire agli utenti di reimpostare le loro password

È consigliabile configurare la reimpostazione self-service delle password, in modo da evitare di dover reimpostare manualmente le password degli utenti. Per altre informazioni, vedere [Consentire agli utenti di reimpostare le loro password in Office 365](let-users-reset-passwords.md).
  
## <a name="reset-a-business-password-for-someone-else"></a>Reimpostare una password aziendale per qualcun altro

Questi passaggi sono disponibili solo per gli utenti che utilizzano un piano Microsoft 365 for business. Per eseguire l'accesso, è necessario accedere con l'account di amministratore di Microsoft 365. [Che cos'è un account di amministratore?](../admin-overview/admin-overview.md)

 
::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.

::: moniker-end

2. Nella pagina **utenti attivi** selezionare l'utente e quindi selezionare **Reimposta password**.
    
3. Seguire le istruzioni riportate nella pagina **Reimposta password** per generare automaticamente una nuova password per l'utente oppure crearne una per loro, quindi selezionare **Reimposta**.  
    
4. Immettere un indirizzo di posta elettronica che l'utente può ottenere in modo che ricevano la nuova password e seguirli per assicurarsi che siano stati ottenuti.
 
  
## <a name="reset-my-admin-password"></a>Reimpostare la password di amministratore

Utilizzare questa procedura se si è dimenticato la password ma si è in grado di accedere a Microsoft 365 perché, ad esempio, la password viene salvata nel browser: 
    
1. In Microsoft 365 selezionare **Impostazioni** \> di **Office 365** \> **personal info**. 
          
2. Verificare che i dettagli dei **contatti** e il **messaggio di posta elettronica alternativo** siano accurati. In caso contrario, cambiali subito. 
        
3. Disconnettersi da Office 365: selezionare il proprio nome nell'angolo in alto a destra (nell'immagine sopra riportata come **Diane**) \> **disconnettersi**. 
        
4. Ora accedi di nuovo: digita il tuo nome \> **utente** \> e quindi seleziona **password dimenticata**. 
    
5. Seguire i passaggi della procedura guidata per reimpostare la password. Utilizza le informazioni di contatto alternative per verificare di essere la persona giusta per reimpostare la password. 
    
Se si è dimenticato la password e non si è in grado di accedere: 
    
- Chiedere a un altro amministratore globale dell'azienda di reimpostare la password per l'utente.
    
- In alternativa, [contattare il supporto tecnico Microsoft](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products). 
    
## <a name="reset-all-business-passwords-for-everyone-in-your-organization-at-the-same-time"></a>Reimpostare contemporaneamente tutte le password aziendali per tutti gli utenti dell'organizzazione
<a name="bkmk_forgot"> </a>

Questi passaggi sono validi per un'azienda con decine di utenti. Se gli utenti sono centinaia o migliaia, vedere la sezione successiva sulla reimpostazione della password in blocco.
  
1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.
    
2. Selezionare l'opzione accanto a **nome visualizzato** per selezionare tutti gli utenti dell'azienda. Quindi deseleziona te stesso. Non è possibile reimpostare la propria password nello stesso momento in cui si reimposta la password di tutti gli altri.
    
3. Selezionare **Reimposta password**. 

4. Seguire le istruzioni riportate nella pagina **Reimposta password** e selezionare **Reimposta**.  Se si è scelto di generare automaticamente le password, verranno visualizzate le nuove password temporanee.   
    
5. Immettere un indirizzo di posta elettronica in cui è possibile ricevere le password temporanee. Sarà necessario informare gli utenti su quali sono le password temporanee.
    

  
## <a name="reset-business-passwords-in-bulk"></a>Reimpostare le password aziendali in blocco
<a name="bkmk_forgot"> </a>

Usare PowerShell. Vedere questo post di Eyal Doron: [Gestire le password con PowerShell](https://go.microsoft.com/fwlink/?linkid=853696).
  
Ecco un articolo correlato: [Impostare le password per più account utente](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).
  
Per informazioni generali, vedere [PowerShell for Microsoft 365 Administrators](https://support.microsoft.com/en-us/office/powershell-for-office-365-administrators-40fdcbd4-c34f-42ab-8678-8b3751137ef1).
  
## <a name="force-a-password-change-for-all-users-in-your-business"></a>Forzare la modifica della password per tutti gli utenti dell'organizzazione
<a name="bkmk_forgot"> </a>

Vedere questo interessante post di blog da Vasil Michev, MVP Microsoft: [Forzare la modifica della password per tutti gli utenti in Office 365](https://go.microsoft.com/fwlink/?linkid=853693).
  
## <a name="im-lost"></a>Serve assistenza.
<a name="bkmk_forgot"> </a>

Leggere questo articolo: [Si è dimenticato l'account o la password per l'account usato con Office](https://support.office.com/article/eba0b4a2-c0ae-472c-99f6-bc63ee2425a8?wt.mc_id=SCL_reset-passwords_AdmHlp).
  
## <a name="related-articles"></a>Articoli correlati
<a name="bkmk_forgot"> </a>
  
[Consenti agli utenti di reimpostare le proprie password](let-users-reset-passwords.md)

[Impostare la password di un singolo utente in modo che non scada mai](set-password-to-never-expire.md)

[Impostare i criteri di scadenza delle password per l'organizzazione](../manage/set-password-expiration-policy.md)

[Ripristinare un utente](restore-user.md)

[Rimuovere un ex dipendente](remove-former-employee.md)

[Video di formazione su Microsoft 365 per le aziende](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
