---
title: Criteri di sicurezza consigliati per posta elettronica -Microsoft 365 Enterprise | Microsoft Docs
description: Descrive i criteri consigliati da Microsoft sull'applicazione di criteri e configurazioni che riguardano la posta elettronica.
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 78defc7ad5da788ae49195f6c0027f3639d50f3e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291117"
---
# <a name="policy-recommendations-for-securing-email"></a>Criteri consigliati per la protezione della posta elettronica
In questo articolo viene descritto come implementare i criteri di identità e accesso ai dispositivi consigliati per proteggere la posta elettronica e i client di posta elettronica che supportano l'autenticazione moderna e l'accesso condizionale. Queste linee guida si basano sui [criteri comuni di accesso a identità e dispositivi](identity-access-policies.md) e sono inoltre disponibili alcuni suggerimenti aggiuntivi.


Questi suggerimenti si basano su tre diversi livelli di sicurezza e protezione che possono essere applicati in base alla granularità delle proprie esigenze: **linea di base**, **sensibile**e **altamente regolamentata**. Per altre informazioni su questi livelli di sicurezza e sui sistemi operativi client consigliati a cui fanno riferimento questi consigli, vedere [Recommended security policies and configurations](microsoft-365-policies-configurations.md) (Criteri di sicurezza e configurazioni consigliati).

Questi suggerimenti richiedono agli utenti di utilizzare i client di posta elettronica moderni, tra cui Outlook per iOS e Android su dispositivi mobili. Outlook per iOS e Android fornisce supporto per le migliori funzionalità di Office 365. Queste app per dispositivi mobili di Outlook sono inoltre architettate con funzionalità di sicurezza che supportano l'utilizzo dei dispositivi mobili e utilizzano altre funzionalità di sicurezza cloud Microsoft. Per ulteriori informazioni, vedere le [domande frequenti su Outlook per iOS e Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).

## <a name="updating-common-policies-to-include-email"></a>Aggiornamento di criteri comuni per includere messaggi di posta elettronica
Nel diagramma seguente vengono illustrati i criteri comuni di identità e accesso ai dispositivi e viene indicato quali criteri devono essere aggiornati per proteggere la posta elettronica. Si noti l'aggiunta di una nuova regola per Exchange Online per bloccare i client ActiveSync. Questo impone l'utilizzo di Outlook Mobile.

![Riepilogo degli aggiornamenti dei criteri per la protezione della posta elettronica](../images/identity-access-ruleset-mail.png)

Se è stato incluso Exchange Online e Outlook nell'ambito dei criteri quando vengono configurati, è necessario creare solo il nuovo criterio per bloccare i client ActiveSync. Esaminare i criteri elencati nella tabella seguente e apportare le aggiunte consigliate o confermare che sono già inclusi. Ogni regola collega le istruzioni di configurazione associate nell'articolo [Common Identity and Device Access Policies](identity-access-policies.md) . 

|Livello di protezione|Generali|Altre informazioni|
|:---------------|:-------|:----------------|
|**Base**|[Richiedere l'AMF quando il rischio di accesso è *medio* o *elevato*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere Exchange Online nell'assegnazione delle app Cloud|
|        |[Bloccare i client che non supportano l'autenticazione moderna](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Includere Exchange Online nell'assegnazione delle app Cloud|
|        |[Definire i criteri di protezione delle app](identity-access-policies.md#high-risk-users-must-change-password)|Assicurarsi che Outlook sia incluso nell'elenco delle app. Assicurarsi di aggiornare i criteri per ogni piattaforma (iOS, Android, Windows)|
|        |[Richiedere applicazioni approvate](identity-access-policies.md#require-approved-apps)|Includere Exchange Online nell'elenco delle app Cloud|
|        |[Richiedi PC conformi](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Includere Exchange Online nell'elenco delle app Cloud|
|        |[Bloccare i client ActiveSync](#block-activesync-clients)|Aggiungere il nuovo criterio| 
|**Dati sensibili**|[Richiedere l'AMF quando il rischio di accesso è *basso*, *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| Includere Exchange Online nell'assegnazione delle app Cloud|
|         |[Richiedere PC conformi *e* dispositivi mobili](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Includere Exchange Online nell'elenco delle app Cloud|
|**Altamente regolamentato**|[Richiede *sempre* l'autenticazione Master](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere Exchange Online nell'assegnazione delle app Cloud|

## <a name="block-activesync-clients"></a>Bloccare i client ActiveSync
Questo criterio impedisce ai client ActiveSync di ignorare altre regole di accesso condizionale. La configurazione della regola si applica solo ai client ActiveSync. Selezionando **Richiedi applicazione client**approvata, questo criterio blocca i client ActiveSync. Per configurare questo criterio:

1. Andare nel [portale di Azure](https://portal.azure.com) e accedere con le proprie credenziali. Dopo aver eseguito l'accesso, è possibile visualizzare il dashboard di Azure.

2. Scegliere **Azure Active Directory** dal menu a sinistra.

3. Nella sezione **Sicurezza** scegliere **Accesso condizionale**.

4. Scegliere **Nuovo criterio**.

5. Immettere un nome per i criteri, quindi in **Utenti e gruppi** scegliere gli utenti e i gruppi ai quali applicare i criteri.

6. Scegliere **App cloud**.

7. Scegliere **Seleziona app**, quindi **Office 365 Exchange Online**. Scegliere **Seleziona** e **Chiudi**.

8. Scegliere **le condizioni**, quindi fare clic su **app client**.

9. Per la **configurazione**, selezionare **Sì**. Controllare solo gli elementi seguenti: **app per dispositivi mobili e client desktop** e **client Exchange ActiveSync**. Scegliere **Done**.

10. Scegliere **Concedi** nella sezione **Controlli di accesso**.

11. Scegliere **Concedi accesso**, selezionare **Richiedi applicazione client**approvata.  Per più controlli, selezionare **Richiedi i controlli selezionati**, quindi scegliere **Seleziona**. 

12. 	Selezionare **Crea**.

## <a name="setup-office-365-message-encryption"></a>Configurazione della crittografia dei messaggi di Office 365
Con le nuove funzionalità di crittografia dei messaggi di Office 365, che sfruttano le funzionalità di protezione di Azure Information Protection, l'organizzazione può facilmente condividere la posta elettronica protetta con chiunque su qualsiasi dispositivo. Gli utenti possono inviare e ricevere messaggi protetti con altre organizzazioni di Office 365, nonché clienti non di Office 365 che utilizzano Outlook.com, Gmail e altri servizi di posta elettronica.

Per ulteriori informazioni, vedere [configurare le nuove funzionalità di crittografia dei messaggi di Office 365](https://support.office.com/article/set-up-new-office-365-message-encryption-capabilities-7ff0c040-b25c-4378-9904-b1b50210d00e). 



## <a name="next-steps"></a>Passaggi successivi

[Suggerimenti sui criteri per la protezione di siti e file di SharePoint](sharepoint-file-access-policies.md)
