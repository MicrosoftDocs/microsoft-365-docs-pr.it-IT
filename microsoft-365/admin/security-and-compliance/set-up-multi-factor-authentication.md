---
title: Configurare l'autenticazione a più fattori per gli utenti di Office 365
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
description: Informazioni su come usare le impostazioni predefinite per la sicurezza per configurare l'autenticazione a più fattori per gli utenti di Office 365.
monikerRange: o365-worldwide
ms.openlocfilehash: bc906299e42929dd4dd09b94502a6d463a5971b4
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42257195"
---
# <a name="set-up-multi-factor-authentication"></a>Configurare l'autenticazione a più fattori
  
Nei nuovi abbonamenti a Office 365 per le aziende o Microsoft 365 Business le impostazioni predefinite per la sicurezza sono attivate automaticamente. Ciò significa che ogni utente dovrà configurare l'autenticazione a più fattori e installare l'app Authenticator nel proprio dispositivo mobile. Per altre informazioni, vedere [Configurare la verifica in due passaggi per Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).  

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

Tutti gli altri utenti dovranno eseguire l'autenticazione aggiuntiva quando necessario. Per altre informazioni, vedere [Che cosa sono le impostazioni predefinite per la sicurezza?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

> [!NOTE]
> Per configurare o modificare l'autenticazione a più fattori è necessario essere un amministratore globale di Office 365. <br><br>
> Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.

Se in precedenza è stata configurata l'autenticazione a più fattori con criteri di base [è necessario disattivare quest'ultimi e attivare le impostazioni predefinite per la sicurezza](#move-from-baseline-policies-to-security-defaults). Tuttavia, se si dispone di Microsoft 365 Business o il proprio abbonamento include [Azure Active Directory Premium 1 o Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/) è possibile inoltre configurare i criteri di [accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/overview). Per usare i criteri di accesso condizionale, è necessario assicurarsi che sia [abilitata l'autenticazione moderna](#enable-multi-factor-authentication-for-your-organization).

## <a name="manage-security-defaults"></a>Gestire le impostazioni predefinite per la sicurezza.

1. Accedere all'[interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=834822) con le credenziali di amministratore globale.
2. Passare alle [Proprietà di Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).

3. Nella parte inferiore della pagina scegliere **Gestire le impostazioni predefinite per la sicurezza**.
4. Scegliere **Sì** per abilitare le impostazioni predefinite di sicurezza e **No** per disabilitare le impostazioni predefinite per la sicurezza.

## <a name="move-from-baseline-policies-to-security-defaults"></a>Passare dai criteri di base alle impostazioni predefinite per la sicurezza

1. Nell'[interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=834822) selezionare **Configurazione**.

2. Accanto a **Accesso e sicurezza**, in **Rendi l’accesso più sicuro**, selezionare **Visualizzazione**.

3. In **Rendi l’accesso più sicuro**, selezionare **Gestisci**. 

4. Nella pagina **Criteri di accesso condizionale al portale di Azure** selezionare ogni criterio di base **Attivato** e impostarlo su **Disattivato**.
5. Passare alla pagina [Proprietà di Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
6. Nella parte inferiore della pagina scegliere **Gestire le impostazioni predefinite per la sicurezza**e nel riquadro **Abilitare le impostazioni predefinite per la sicurezza** impostare **Abilita le impostazioni predefinite per la sicurezza** su **Sì**. 

## <a name="enable-modern-authentication-for-your-organization"></a>Abilitare l'autenticazione moderna per l'organizzazione

Tutte le applicazioni client di Office 2016 supportano MFA con ADAL (Active Directory Authentication Library). Questo significa che le password dell'app non sono necessarie per i client di Office 2016. Tuttavia, è necessario assicurarsi che l'abbonamento a Office 365 sia abilitato per ADAL o per l'autenticazione moderna.

1. Per abilitare l'autenticazione moderna, nell'[interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=834822) selezionare **Impostazioni** \> **Impostazioni** e quindi nella scheda **Servizi** scegliere **Autenticazione moderna** dall'elenco.

2. Selezionare la casella **Abilita l'autenticazione moderna** nel pannello **Autenticazione moderna**. 

    ![Pannello Autenticazione moderna con casella di controllo Abilita selezionata.](../media/enablemodernauth.png)
    
## <a name="enable-multi-factor-authentication-for-your-organization"></a>Abilitare l'autenticazione a più fattori per l'organizzazione
    
1. Nell'interfaccia di [Amministrazione](https://go.microsoft.com/fwlink/p/?linkid=834822)selezionare **utenti** e **utenti attivi**.

2. Nella sezione **utenti attivi** fare clic su autenticazione a più **fattori**.

3. Nella pagina **autenticazione** a più fattori selezionare **utente** se si sta abilitando questa operazione per un utente oppure è possibile peform un **aggiornamento in blocco**.

4. Fare clic su **Abilita** in **passaggi rapidi**.

5. Nella finestra popup, CLickc **attiva l'autenticazione**a più fattori.

Dopo aver configurato l'autenticazione a più fattori per l’organizzazione, agli utenti verrà richiesto di impostare la verifica in due passaggi sui loro dispositivi. Per altre informazioni, vedere [Configurare la verifica in due passaggi per Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).
    
> [!TIP]
> Per spiegare agli utenti come configurare l'app Authenticator, visitare [Usare Microsoft Authenticator con Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).


> [!IMPORTANT]
> Dal mese di agosto 2017 tutti i nuovi tenant di Office 365 che includono Skype for Business Online ed Exchange Online hanno l'autenticazione moderna abilitata per impostazione predefinita. Per controllare lo stato di autenticazione moderna di Skype for Business Online, è possibile usare PowerShell per Skype for Business Online con credenziali di amministratore globale. Eseguire Get-CsOAuthConfiguration per controllare l'output di -ClientADALAuthOverride. Se -ClientADALAuthOverride è "Allowed" (Consentito), l'autenticazione moderna è attiva.
Per controllare lo stato di autenticazione moderna per Exchange Online, vedere [Abilitare l'autenticazione moderna in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).

## <a name="related-articles"></a>Articoli correlati

[I 10 principali modi per proteggere i piani di Office 365 e Microsoft 365 Business](secure-your-business-data.md)

[Abilitare l'autenticazione moderna per Office 2013 nei dispositivi Windows](enable-modern-authentication.md)
