---
title: Impostare i criteri di scadenza delle password per l'organizzazione
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: Informazioni su come impostare i criteri di scadenza delle password per l'organizzazione nell'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: 0280f4fd43034f9ffb70104771fa4a099943af2d
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500240"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a>Impostare i criteri di scadenza delle password per l'organizzazione

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](../microsoft-365-admin-center-preview.md?view=o365-worldwide).

::: moniker-end

## <a name="before-you-begin"></a>Prima di iniziare

Questo articolo è per le persone che impostano criteri di scadenza delle password in un'azienda, un istituto di istruzione o un'organizzazione no profit. Per completare questa procedura, è necessario accedere con l'account amministratore di Microsoft 365. [Che cos'è un account amministratore?](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview).

Gli amministratori possono fare in modo che la password di un utente scada dopo un determinato numero di giorni o che non scada mai. Per impostazione predefinita, le password sono impostate per non scadere mai per l'organizzazione.

Ricerche correnti indicano che le modifiche obbligatorie delle password sono più dannose che utili. Le modifiche frequenti inducono gli utenti a scegliere password più deboli, a riutilizzare le password o ad aggiornare le vecchie password in modi facilmente individuabili dai pirati informatici. È consigliabile abilitare l’[autenticazione a più fattori](../security-and-compliance/set-up-multi-factor-authentication.md).

Per eseguire questi passaggi, è necessario essere un [amministratore globale](../add-users/about-admin-roles.md).

Gli utenti non hanno le autorizzazioni per impostare una password in modo che non scada mai. Chiedere al supporto tecnico dell'azienda o dell'istituto di istruzione di completare la procedura descritta in questo articolo.

## <a name="set-password-expiration-policy"></a>Impostare il criterio di scadenza delle password

Seguire la procedura seguente se si vogliono impostare le password degli utenti in modo che scadano dopo un determinato periodo di tempo.

1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> **Impostazioni organizzazione**.

2. Passare alla pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Sicurezza e privacy</a>.
 Gli utenti che non sono amministratori globali non visualizzeranno l'opzione Sicurezza e privacy.
  
3. Selezionare **Criterio di scadenza delle password**.
  
4. Se non si vuole che gli utenti debbano cambiare le password, deselezionare la casella accanto a **Impostare la scadenza delle password dopo un certo numero di giorni**.
  
5. Digitare la frequenza con cui dovrebbero scadere le password. Scegliere un numero di giorni compreso tra 14 e 730.
  
6. Nella seconda casella digitare quando verranno avvisati gli utenti dell'imminente scadenza della password e poi selezionare **Salva**. Scegliere un numero di giorni compreso tra 1 e 30.
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a>Informazioni importanti sulla funzionalità di scadenza delle password
  
- Chi usa solo l'app Outlook non sarà obbligato a reimpostare la password di Microsoft 365 fino alla relativa scadenza nella cache. Questo può avvenire diversi giorni dopo la data di scadenza effettiva. Non ci sono soluzioni alternative a livello di amministratore.

## <a name="prevent-last-password-from-being-used-again"></a>Impedire il riutilizzo dell'ultima password

In Active Directory (AD) locale è possibile impedire agli utenti di riciclare le vecchie password applicando la cronologia delle password. Vedere [Creare criteri password personalizzati](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).

In Azure AD, quando l'utente modifica una password, non è possibile usare di nuovo l'ultima password. Il criterio password viene applicato a tutti gli account utente creati e gestiti direttamente in Azure AD. Questo criterio password non può essere modificato. Vedere i [criteri per le password di Azure AD](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a>Sincronizzare gli hash delle password degli utenti da un server di Active Directory locale ad Azure Active Directory (Microsoft 365)

Questo articolo spiega come configurare i criteri di scadenza per gli utenti basati solo su cloud (Azure Active Directory). Non si applica agli utenti con identità ibride che usano la sincronizzazione dell'hash delle password, l'autenticazione pass-through o la federazione locale, ad esempio ADFS.
  
Per informazioni sulla sincronizzazione degli hash delle password utente da Active Directory locale ad Azure Active Directory, vedere [Implementare la sincronizzazione degli hash delle password con il servizio di sincronizzazione di Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a>Criteri per le password e restrizioni di Azure Active Directory

È possibile configurare più criteri per le password e restrizioni in Azure Active Directory. Vedere [Criteri per le password e restrizioni di Azure Active Directory](/azure/active-directory/authentication/concept-sspr-policy) per altre informazioni.

## <a name="update-password-policy"></a>Aggiornare i criteri password

Il cmdlet Set-MsolPasswordPolicy aggiorna i criteri delle password di un dominio o di un tenant specifico. Sono necessarie due impostazioni. La prima indica il periodo di validità di una password prima che debba essere cambiata e la seconda indica il numero di giorni prima della data di scadenza della password in cui si attiverà l'invio agli utenti della prima notifica della scadenza.

Per informazioni su come aggiornare i criteri delle password per un dominio o un tenant specifico, vedere [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).

## <a name="related-content"></a>Contenuti correlati

[Consentire agli utenti di reimpostare le loro password](../add-users/let-users-reset-passwords.md)

[Reimpostare password](../add-users/reset-passwords.md)