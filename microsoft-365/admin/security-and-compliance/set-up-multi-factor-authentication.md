---
title: Configurare l'autenticazione a più fattori per gli utenti
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Informazioni su come utilizzare le impostazioni predefinite per la sicurezza per configurare l'autenticazione a più fattori per gli utenti.
monikerRange: o365-worldwide
ms.openlocfilehash: 4c0df9198db8154c1aa748a68eff29dd9bf3bca1
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213011"
---
# <a name="set-up-multi-factor-authentication"></a>Configurare l'autenticazione a più fattori
  
> [!IMPORTANT]
> Se l'abbonamento o il processo è stato acquistato dopo il 21 ottobre 2019 e viene richiesto l'autenticazione a più fattori, le [impostazioni predefinite](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) per la sicurezza sono state abilitate automaticamente per l'abbonamento.

Ogni nuova sottoscrizione Microsoft 365 avrà automaticamente le [impostazioni predefinite](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) per la sicurezza attivate. Questo significa che ogni utente dovrà configurare l'autenticazione a più fattori e installare l'app Microsoft Authenticator sul proprio dispositivo mobile. Per ulteriori informazioni, vedere [set up Mae for a Microsoft 365 account](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).

I nove ruoli di amministratore seguenti dovranno eseguire delle autenticazioni aggiuntive ogni volta che eseguono l'accesso:

- Amministratore globale
- Amministratore di SharePoint
- Amministratore di Exchange
- Amministratore di accesso condizionale
- Amministratore della sicurezza
- Amministratore supporto tecnico o amministratore password:
- Amministratore fatturazione
- Amministratore utenti
- Amministratore dell'autenticazione

Tutti gli altri utenti dovranno eseguire l'autenticazione aggiuntiva quando necessario.

> [!NOTE]
> È necessario essere un amministratore globale per impostare o modificare il Master <br><br>
> Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.

Se in precedenza è stata configurata l'autenticazione con criteri di base, è necessario disattivarla [per abilitare le impostazioni predefinite per la sicurezza](#move-from-baseline-policies-to-security-defaults). Tuttavia, se si dispone di Microsoft 365 business o l'abbonamento include [Azure Active Directory Premium P1 o Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), è anche possibile configurare i criteri di [accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) . Per utilizzare i criteri di accesso condizionale, è necessario verificare che le impostazioni predefinite per la sicurezza siano disabilitate e che [l'autenticazione moderna](#enable-modern-authentication-for-your-organization) sia abilitata.

> [!TIP]
> Per spiegare agli utenti come configurare l'app Microsoft Authenticator, vedere [utilizzare Microsoft Authenticator con Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411).

## <a name="manage-security-defaults"></a>Gestire le impostazioni predefinite per la sicurezza.

1. Accedere al [portale di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=834822) con le credenziali di amministratore globale.
2. Passare alla [pagina Azure Active Directory-Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
3. Nella parte inferiore della pagina scegliere **Gestire le impostazioni predefinite per la sicurezza**.
4. Scegliere **Sì** per abilitare le impostazioni predefinite per la sicurezza e **No** per disabilitare le impostazioni predefinite per la sicurezza e quindi scegliere **Salva**.

## <a name="move-from-baseline-policies-to-security-defaults"></a>Passare dai criteri di base alle impostazioni predefinite per la sicurezza

1. Passare alla [pagina Criteri di accesso condizionale](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).
2. Scegliere tutti i criteri di base che **sono attivi** e impostare **Attiva criterio** su **disattivato**.
3. Passare alla [pagina Azure Active Directory-Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
4. Nella parte inferiore della pagina fare clic su **Gestisci impostazioni predefinite di sicurezza**e, nel riquadro **Attiva impostazioni di sicurezza** , impostare **Consenti impostazioni predefinite di sicurezza** su **Sì**e quindi scegliere **Salva**. 

## <a name="enable-modern-authentication-for-your-organization"></a>Abilitare l'autenticazione moderna per l'organizzazione

Tutte le applicazioni client di Office 2016 supportano MFA con ADAL (Active Directory Authentication Library). Questo significa che le password dell'app non sono necessarie per i client di Office 2016. Per ulteriori informazioni, vedere [questo articolo](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords) .

Tuttavia, è necessario assicurarsi che la sottoscrizione Microsoft 365 sia abilitata per l'autenticazione di ADAL o moderna.

1. Per abilitare l'autenticazione moderna, nell'[interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=834822) selezionare **Impostazioni** \> **Impostazioni** e quindi nella scheda **Servizi** scegliere **Autenticazione moderna** dall'elenco.

2. Selezionare la casella **Attiva autenticazione moderna (scelta consigliata)** nel pannello **autenticazione moderna** e quindi fare clic su **Salva modifiche**. 

    ![Pannello Autenticazione moderna con casella di controllo Abilita selezionata.](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> A agosto del 2017, tutte le nuove sottoscrizioni di Microsoft 365 che includono Skype for business online ed Exchange Online hanno l'autenticazione moderna abilitata per impostazione predefinita. Per controllare lo stato di autenticazione moderna di Skype for Business Online, è possibile usare PowerShell per Skype for Business Online con credenziali di amministratore globale. Eseguire Get-CsOAuthConfiguration per controllare l'output di -ClientADALAuthOverride. Se -ClientADALAuthOverride è "Allowed" (Consentito), l'autenticazione moderna è attiva.
Per controllare lo stato di autenticazione moderna per Exchange Online, vedere [Abilitare l'autenticazione moderna in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).

## <a name="related-articles"></a>Articoli correlati

[Top 10 modi per proteggere i piani Microsoft 365 for business](secure-your-business-data.md)

[Abilitare l'autenticazione moderna per Office 2013 nei dispositivi Windows](enable-modern-authentication.md)
