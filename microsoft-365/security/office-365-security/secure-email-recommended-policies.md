---
title: Criteri consigliati per la protezione della posta elettronica - Criteri consigliati per Microsoft 365 per le | Microsoft Docs
description: Descrive i criteri consigliati da Microsoft sull'applicazione di criteri e configurazioni che riguardano la posta elettronica.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 4651f220e88bf5161a8ddfe4e2bdde03118afa15
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288480"
---
# <a name="policy-recommendations-for-securing-email"></a>Criteri consigliati per la protezione della posta elettronica

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)


In questo articolo viene descritto come implementare i criteri di identità e accesso ai dispositivi consigliati per proteggere i client di posta elettronica e di posta elettronica dell'organizzazione che supportano l'autenticazione moderna e l'accesso condizionale. Queste indicazioni si basano sui criteri [comuni di identità](identity-access-policies.md) e accesso ai dispositivi e includono anche alcuni consigli aggiuntivi.

Questi consigli si basano su tre diversi livelli di sicurezza e protezione che possono essere applicati in base alla granularità delle proprie **esigenze:** di **base,** sensibile e **altamente regolamentato.** Per altre informazioni su questi livelli di sicurezza e sui sistemi operativi client consigliati a cui fanno riferimento questi consigli, vedere [Recommended security policies and configurations](microsoft-365-policies-configurations.md) (Criteri di sicurezza e configurazioni consigliati).

Questi suggerimenti richiedono agli utenti di utilizzare client di posta elettronica moderni, tra cui Outlook per iOS e Android nei dispositivi mobili. Outlook per iOS e Android offre supporto per le migliori funzionalità di Office 365. Queste app outlook per dispositivi mobili sono inoltre progettate con funzionalità di sicurezza che supportano l'uso mobile e funzionano insieme ad altre funzionalità di sicurezza cloud Microsoft. Per ulteriori informazioni, vedere Domande [frequenti su Outlook per iOS e Android.](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)

## <a name="update-common-policies-to-include-email"></a>Aggiornare i criteri comuni per includere la posta elettronica

Per proteggere la posta elettronica, nel diagramma seguente vengono illustrati i criteri da aggiornare dai criteri comuni di identità e accesso ai dispositivi.

[![Riepilogo degli aggiornamenti dei criteri per la protezione dell'accesso a Teams e ai relativi servizi dipendenti](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

[Vedere una versione più grande di questa immagine](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

Si noti l'aggiunta di un nuovo criterio per Exchange Online per bloccare i client ActiveSync. In questo modo viene forzato l'utilizzo di Outlook Mobile.

Se Exchange Online e Outlook sono stati inclusi nell'ambito dei criteri al momento della configurazione, è necessario creare solo il nuovo criterio per bloccare i client ActiveSync. Esaminare i criteri elencati nella tabella seguente e apportare le aggiunte consigliate oppure verificare che siano già inclusi. Ogni criterio è associato alle istruzioni di configurazione in [Criteri comuni di identità e accesso ai dispositivi.](identity-access-policies.md)

|Livello di protezione|Criteri|Altre informazioni|
|---|---|---|
|**Protezione di base**|[Richiedere l'autenticazione a più fattori quando il rischio di accesso *è medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere Exchange Online nell'assegnazione delle app cloud|
||[Bloccare i client che non supportano l'autenticazione moderna](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Includere Exchange Online nell'assegnazione delle app cloud|
||[Applicare i criteri di protezione dei dati app](identity-access-policies.md#apply-app-data-protection-policies)|Assicurarsi che Outlook sia incluso nell'elenco delle app. Assicurati di aggiornare i criteri per ogni piattaforma (iOS, Android, Windows)|
||[Richiedi app approvate e protezione APP](identity-access-policies.md#require-approved-apps-and-app-protection)|Includere Exchange Online nell'elenco delle app cloud|
||[Richiedere computer conformi](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Includere Exchange Online nell'elenco delle app cloud|
||[Bloccare i client ActiveSync](#block-activesync-clients)|Aggiungere questo nuovo criterio|
|**Sensibili**|[Richiedere l'autenticazione a più fattori quando il rischio di accesso è *basso,* *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere Exchange Online nell'assegnazione delle app cloud|
||[Richiedere PC e *dispositivi* mobili conformi](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Includere Exchange Online nell'elenco delle app cloud|
|**Riservatezza elevata**|[*Richiedi sempre* L'autenticazione a più fattori](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere Exchange Online nell'assegnazione delle app cloud|
|

## <a name="block-activesync-clients"></a>Bloccare i client ActiveSync

Questo criterio impedisce ai client ActiveSync di ignorare altri criteri di accesso condizionale. La configurazione dei criteri si applica solo ai client ActiveSync. Selezionando Richiedi **[criteri di protezione delle app,](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** questo criterio blocca i client ActiveSync. I dettagli sulla creazione di questo criterio sono disponibili in Richiedi criteri di protezione delle app per [l'accesso alle app cloud con accesso condizionale.](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)

- Seguire "Passaggio 2: Configurare un criterio di accesso condizionale di Azure AD per Exchange Online con ActiveSync (EAS)" nello scenario 1: le app [di Office 365](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)richiedono app approvate con criteri di protezione delle app, che impediscono ai client Exchange ActiveSync che si connettono a Exchange Online sfruttando l'autenticazione di base.

È inoltre possibile utilizzare i criteri di autenticazione per [disabilitare l'autenticazione](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)di base, che forza tutte le richieste di accesso client a utilizzare l'autenticazione moderna.

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a>Limitare l'accesso a Exchange Online da Outlook sul Web

È possibile limitare la possibilità per gli utenti di scaricare allegati da Outlook sul Web su dispositivi umnanaged. Gli utenti di questi dispositivi possono visualizzare e modificare questi file usando Office Online senza perdita e archiviazione dei file nel dispositivo. Puoi anche impedire agli utenti di visualizzare gli allegati in un dispositivo non gestito.

Di seguito sono illustrati i passaggi:

1. [Connettersi a una sessione di PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)remota di Exchange Online.
2. Se non si dispone già di un criterio OWA cassetta postale, crearne uno con il cmdlet [New-OwaMailboxPolicy.](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy)
3. Se si desidera consentire la visualizzazione degli allegati ma non il download, utilizzare questo comando:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. Se si desidera bloccare gli allegati, utilizzare questo comando:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. Nel portale di Azure, creare un nuovo criterio di accesso condizionale con queste impostazioni:

   **Assegnazioni** \> **Utenti e gruppi:** selezionare gli utenti e i gruppi appropriati da includere ed escludere.

   **Assegnazioni** \> **App o azioni cloud** \> **App cloud** \> **Includi** \> **Select apps**: Select **Office 365 Exchange Online**

   **Controlli di accesso** \> **Sessione:** selezionare **Usa restrizioni applicate dall'app**

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a>Richiedere che i dispositivi iOS e Android utilizzino Outlook

Per garantire che gli utenti di dispositivi iOS e Android possano accedere solo ai contenuti aziendali o dell'istituto di istruzione tramite Outlook per iOS e Android, è necessario un criterio di accesso condizionale destinato a questi potenziali utenti.

Vedere la procedura per configurare questo criterio in [Gestire l'accesso di collaborazione alla messaggistica tramite Outlook per iOS e Android.]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)

## <a name="set-up-message-encryption"></a>Configurare la crittografia dei messaggi

Con le nuove funzionalità office 365 Message Encryption (OME), che sfruttano le funzionalità di protezione di Azure Information Protection, l'organizzazione può facilmente condividere la posta elettronica protetta con chiunque su qualsiasi dispositivo. Gli utenti possono inviare e ricevere messaggi protetti con altre organizzazioni di Microsoft 365 e con utenti non clienti che usano Outlook.com, Gmail e altri servizi di posta elettronica.

Per ulteriori informazioni, vedere Configurare le nuove funzionalità di crittografia dei messaggi [di Office 365.](../../compliance/set-up-new-message-encryption-capabilities.md)

## <a name="next-steps"></a>Passaggi successivi

![Passaggio 4: Criteri per le app cloud di Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configurare i criteri di accesso condizionale per:

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
