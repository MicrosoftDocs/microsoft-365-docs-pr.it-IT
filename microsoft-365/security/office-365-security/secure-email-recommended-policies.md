---
title: Criteri di protezione della posta elettronica consigliati-Microsoft 365 for Enterprise | Documenti Microsoft
description: Descrive i criteri consigliati da Microsoft sull'applicazione di criteri e configurazioni che riguardano la posta elettronica.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
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
ms.openlocfilehash: f2d3b9180ad5ab58e92812ed7b2d4f7ba07e2971
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357110"
---
# <a name="policy-recommendations-for-securing-email"></a>Criteri consigliati per la protezione della posta elettronica

In questo articolo viene descritto come implementare i criteri di identità e accesso ai dispositivi consigliati per proteggere la posta elettronica e i client di posta elettronica che supportano l'autenticazione moderna e l'accesso condizionale. Queste linee guida si basano sui [criteri comuni di accesso a identità e dispositivi](identity-access-policies.md) e sono inoltre disponibili alcuni suggerimenti aggiuntivi.

Questi suggerimenti si basano su tre diversi livelli di sicurezza e protezione che possono essere applicati in base alla granularità delle proprie esigenze: **linea di base**, **sensibile** e **altamente regolamentata**. Per altre informazioni su questi livelli di sicurezza e sui sistemi operativi client consigliati a cui fanno riferimento questi consigli, vedere [Recommended security policies and configurations](microsoft-365-policies-configurations.md) (Criteri di sicurezza e configurazioni consigliati).

Questi suggerimenti richiedono agli utenti di utilizzare i client di posta elettronica moderni, tra cui Outlook per iOS e Android su dispositivi mobili. Outlook per iOS e Android fornisce supporto per le migliori funzionalità di Office 365. Queste app per dispositivi mobili di Outlook sono inoltre architettate con funzionalità di sicurezza che supportano l'utilizzo dei dispositivi mobili e utilizzano altre funzionalità di sicurezza cloud Microsoft. Per ulteriori informazioni, vedere le [domande frequenti su Outlook per iOS e Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).

## <a name="update-common-policies-to-include-email"></a>Aggiornare i criteri comuni per includere messaggi di posta elettronica

Per proteggere la posta elettronica, nel diagramma seguente vengono illustrati i criteri da aggiornare dai criteri di identità e accesso ai dispositivi comuni.

[![Riepilogo degli aggiornamenti dei criteri per la protezione dell'accesso ai team e ai servizi dipendenti](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

[Visualizzazione di una versione più grande di questa immagine](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

Si noti l'aggiunta di un nuovo criterio per Exchange Online per bloccare i client ActiveSync. Questo impone l'utilizzo di Outlook Mobile.

Se è stato incluso Exchange Online e Outlook nell'ambito dei criteri quando vengono configurati, è necessario creare solo il nuovo criterio per bloccare i client ActiveSync. Esaminare i criteri elencati nella tabella seguente e apportare le aggiunte consigliate o confermare che sono già inclusi. Ogni criterio si collega alle istruzioni di configurazione associate nei [criteri comuni di identità e accesso ai dispositivi](identity-access-policies.md).

|Livello di protezione|Criteri|Ulteriori informazioni|
|---|---|---|
|**Protezione di base**|[Richiedere l'AMF quando il rischio di accesso è *medio* o *elevato*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere Exchange Online nell'assegnazione delle app Cloud|
||[Bloccare i client che non supportano l'autenticazione moderna](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Includere Exchange Online nell'assegnazione delle app Cloud|
||[Applicare i criteri di protezione dei dati dell'APP](identity-access-policies.md#apply-app-data-protection-policies)|Assicurarsi che Outlook sia incluso nell'elenco delle app. Assicurarsi di aggiornare i criteri per ogni piattaforma (iOS, Android, Windows)|
||[Richiedere applicazioni approvate e protezione delle APP](identity-access-policies.md#require-approved-apps-and-app-protection)|Includere Exchange Online nell'elenco delle app Cloud|
||[Richiedere computer conformi](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Includere Exchange Online nell'elenco delle app Cloud|
||[Bloccare i client ActiveSync](#block-activesync-clients)|Aggiungere il nuovo criterio|
|**Sensibili**|[Richiedere l'AMF quando il rischio di accesso è *basso*, *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere Exchange Online nell'assegnazione delle app Cloud|
||[Richiedere PC conformi *e* dispositivi mobili](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Includere Exchange Online nell'elenco delle app Cloud|
|**Riservatezza elevata**|[Richiede *sempre* l'autenticazione Master](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere Exchange Online nell'assegnazione delle app Cloud|
|

## <a name="block-activesync-clients"></a>Bloccare i client ActiveSync

Questo criterio impedisce ai client ActiveSync di ignorare altri criteri di accesso condizionale. La configurazione dei criteri si applica solo ai client ActiveSync. Selezionando **[Richiedi criteri di protezione delle app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)**, questo criterio blocca i client ActiveSync. I dettagli sulla creazione di questo criterio sono disponibili in [Richiedi criteri di protezione delle app per l'accesso alle app cloud con accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

- Seguire "passaggio 2: configurare un criterio di accesso condizionale di Azure AD per Exchange Online con ActiveSync (EAS)" nello [scenario 1: le app di Office 365 richiedono applicazioni approvate con i criteri di protezione delle app](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), che impediscono ai client di Exchange ActiveSync di sfruttare l'autenticazione di base dalla connessione a Exchange Online.

È inoltre possibile utilizzare i criteri di autenticazione per [disabilitare l'autenticazione di base](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online), che impone a tutte le richieste di accesso client di utilizzare l'autenticazione moderna.

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a>Limitare l'accesso a Exchange Online da Outlook sul Web

È possibile limitare la possibilità per gli utenti di scaricare gli allegati da Outlook sul Web sui dispositivi di umnanaged. Gli utenti di questi dispositivi possono visualizzare e modificare i file utilizzando Office Online senza perdere e archiviare i file nel dispositivo. È inoltre possibile impedire agli utenti di visualizzare gli allegati in un dispositivo non gestito.

Di seguito sono illustrati i passaggi:

1. [Connettersi a una sessione di PowerShell remota di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).
2. Se non si dispone già di un criterio cassetta postale OWA, crearne uno con il cmdlet [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) .
3. Se si desidera consentire la visualizzazione degli allegati ma non il download, utilizzare questo comando:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. Se si desidera bloccare gli allegati, utilizzare questo comando:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. Nel portale di Azure, creare un nuovo criterio di accesso condizionale con queste impostazioni:

   **Assegnazioni** \> **Utenti e gruppi**: selezionare gli utenti e i gruppi adatti da includere ed escludere.

   **Assegnazioni** \> **App o azioni cloud** \> **App Cloud** \> **Includere** \> **Selezionare le app**: selezionare **Office 365 Exchange Online**

   **Controlli** \> di accesso **Sessione**: selezionare **USA restrizioni applicate all'app**

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a>Richiedi che i dispositivi iOS e Android siano in grado di utilizzare Outlook

Per garantire che gli utenti di dispositivi iOS e Android possano accedere solo ai contenuti del lavoro o dell'Istituto di istruzione utilizzando Outlook per iOS e Android, è necessario un criterio di accesso condizionale destinato a tali potenziali utenti.

Vedere la procedura per configurare questo criterio in [gestire l'accesso alla collaborazione di messaggistica tramite Outlook per iOS e Android]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access).

## <a name="set-up-message-encryption"></a>Configurare la crittografia dei messaggi

Con le nuove funzionalità di crittografia dei messaggi di Office 365, che sfruttano le funzionalità di protezione di Azure Information Protection, l'organizzazione può facilmente condividere la posta elettronica protetta con chiunque su qualsiasi dispositivo. Gli utenti possono inviare e ricevere messaggi protetti con altre organizzazioni di Microsoft 365 e non clienti che utilizzano Outlook.com, Gmail e altri servizi di posta elettronica.

Per ulteriori informazioni, vedere [configurare le nuove funzionalità di crittografia dei messaggi di Office 365](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities).

## <a name="next-steps"></a>Passaggi successivi

![Passaggio 4: criteri per le app cloud di Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configurare i criteri di accesso condizionale per:

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
