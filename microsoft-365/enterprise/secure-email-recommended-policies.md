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
ms.openlocfilehash: 9c289006fc1501865b0cf5529c308a0986895504
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898141"
---
# <a name="policy-recommendations-for-securing-email"></a>Criteri consigliati per la protezione della posta elettronica

In questo articolo viene descritto come implementare i criteri di identità e accesso ai dispositivi consigliati per proteggere la posta elettronica e i client di posta elettronica che supportano l'autenticazione moderna e l'accesso condizionale. Queste linee guida si basano sui [criteri comuni di accesso a identità e dispositivi](identity-access-policies.md) e sono inoltre disponibili alcuni suggerimenti aggiuntivi.

Questi suggerimenti si basano su tre diversi livelli di sicurezza e protezione che possono essere applicati in base alla granularità delle proprie esigenze: **linea di base**, **sensibile**e **altamente regolamentata**. Per altre informazioni su questi livelli di sicurezza e sui sistemi operativi client consigliati a cui fanno riferimento questi consigli, vedere [Recommended security policies and configurations](microsoft-365-policies-configurations.md) (Criteri di sicurezza e configurazioni consigliati).

Questi suggerimenti richiedono agli utenti di utilizzare i client di posta elettronica moderni, tra cui Outlook per iOS e Android su dispositivi mobili. Outlook per iOS e Android fornisce supporto per le migliori funzionalità di Office 365. Queste app per dispositivi mobili di Outlook sono inoltre architettate con funzionalità di sicurezza che supportano l'utilizzo dei dispositivi mobili e utilizzano altre funzionalità di sicurezza cloud Microsoft. Per ulteriori informazioni, vedere le [domande frequenti su Outlook per iOS e Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).

## <a name="updating-common-policies-to-include-email"></a>Aggiornamento di criteri comuni per includere messaggi di posta elettronica

Nel diagramma seguente vengono illustrati i criteri comuni di identità e accesso ai dispositivi e viene indicato quali criteri devono essere aggiornati per proteggere la posta elettronica. Si noti l'aggiunta di una nuova regola per Exchange Online per bloccare i client ActiveSync. Questo impone l'utilizzo di Outlook Mobile.

![Riepilogo degli aggiornamenti dei criteri per la protezione della posta elettronica](../media/identity-access-ruleset-mail.png)

[Visualizzazione di una versione più grande di questa immagine](https://raw.githubusercontent.com/MicrosoftDocs/microsoft-365-docs/public/microsoft-365/media/identity-access-ruleset-mail.png)

Se è stato incluso Exchange Online e Outlook nell'ambito dei criteri quando vengono configurati, è necessario creare solo il nuovo criterio per bloccare i client ActiveSync. Esaminare i criteri elencati nella tabella seguente e apportare le aggiunte consigliate o confermare che sono già inclusi. Ogni regola collega le istruzioni di configurazione associate ai [criteri comuni di identità e accesso ai dispositivi](identity-access-policies.md).

|Livello di protezione|Criteri|Ulteriori informazioni|
|:---------------|:-------|:----------------|
|**Protezione di base**|[Richiedere l'AMF quando il rischio di accesso è *medio* o *elevato*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere Exchange Online nell'assegnazione delle app Cloud|
|        |[Bloccare i client che non supportano l'autenticazione moderna](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Includere Exchange Online nell'assegnazione delle app Cloud|
|        |[Applicare i criteri di protezione dei dati dell'APP](identity-access-policies.md#apply-app-data-protection-policies)|Assicurarsi che Outlook sia incluso nell'elenco delle app. Assicurarsi di aggiornare i criteri per ogni piattaforma (iOS, Android, Windows)|
|        |[Richiedere applicazioni approvate e protezione delle APP](identity-access-policies.md#require-approved-apps-and-app-protection)|Includere Exchange Online nell'elenco delle app Cloud|
|        |[Richiedere computer conformi](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Includere Exchange Online nell'elenco delle app Cloud|
|        |[Bloccare i client ActiveSync](#block-activesync-clients)|Aggiungere il nuovo criterio| 
|**Sensibili**|[Richiedere l'AMF quando il rischio di accesso è *basso*, *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| Includere Exchange Online nell'assegnazione delle app Cloud|
|         |[Richiedere PC conformi *e* dispositivi mobili](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Includere Exchange Online nell'elenco delle app Cloud|
|**Riservatezza elevata**|[Richiede *sempre* l'autenticazione Master](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere Exchange Online nell'assegnazione delle app Cloud|

## <a name="block-activesync-clients"></a>Bloccare i client ActiveSync

Questo criterio impedisce ai client ActiveSync di ignorare altre regole di accesso condizionale. La configurazione della regola si applica solo ai client ActiveSync. Selezionando **[Richiedi criteri di protezione delle app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)**, questo criterio blocca i client ActiveSync. I dettagli sulla creazione di questo criterio sono disponibili in [Richiedi criteri di protezione delle app per l'accesso alle app cloud con accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Seguire "passaggio 2: configurare un criterio di accesso condizionale di Azure AD per Exchange Online con ActiveSync (EAS)" nello [scenario 1: le app di Office 365 richiedono applicazioni approvate con i criteri di protezione delle app](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), che impediscono ai client di Exchange ActiveSync di sfruttare l'autenticazione di base dalla connessione a Exchange Online.

## <a name="set-up-message-encryption"></a>Configurare la crittografia dei messaggi

Con le nuove funzionalità di crittografia dei messaggi di Office 365, che sfruttano le funzionalità di protezione di Azure Information Protection, l'organizzazione può facilmente condividere la posta elettronica protetta con chiunque su qualsiasi dispositivo. Gli utenti possono inviare e ricevere messaggi protetti con altre organizzazioni di Microsoft 365 e non clienti che utilizzano Outlook.com, Gmail e altri servizi di posta elettronica.

Per ulteriori informazioni, vedere [configurare le nuove funzionalità di crittografia dei messaggi di Office 365](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities).

## <a name="next-steps"></a>Passaggi successivi

[Suggerimenti sui criteri per la protezione di siti e file di SharePoint](sharepoint-file-access-policies.md)
