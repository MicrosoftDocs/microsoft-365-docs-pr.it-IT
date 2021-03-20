---
title: Autenticazione a più fattori per Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
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
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni sull'autenticazione a più fattori in Microsoft 365.
ms.openlocfilehash: e1635e48e3948425a6d91f80fd07d50c474b73d7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914511"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a>Autenticazione a più fattori per Microsoft 365

Le password sono il metodo più comune per autenticare un accesso a un computer o a un servizio online, ma sono anche i più vulnerabili. Gli utenti possono scegliere password semplici e utilizzare le stesse password per più account di accesso a computer e servizi diversi.

Per fornire un ulteriore livello di sicurezza per gli accesso, è necessario utilizzare l'autenticazione a più fattori (MFA), che utilizza sia una password, che dovrebbe essere complessa, sia un metodo di verifica aggiuntivo basato su:

- Qualcosa che non è facilmente duplicato, ad esempio uno smartphone.
- Qualcosa che hai in modo univoco e biologico, ad esempio le impronte digitali, il viso o un altro attributo biometrico.

Il metodo di verifica aggiuntivo viene utilizzato solo dopo la verifica della password dell'utente. Con MFA, anche se una password utente complessa è compromessa, l'autore dell'attacco non ha lo smartphone o l'impronta digitale per completare l'accesso.

## <a name="mfa-support-in-microsoft-365"></a>Supporto MFA in Microsoft 365

Per impostazione predefinita, Microsoft 365 e Office 365 supportano la MFA per gli account utente usando:

- Sms inviato a un telefono che richiede all'utente di digitare un codice di verifica.
- Una telefonata.
- App Microsoft Authenticator per smart phone.

In entrambi i casi, l'accesso MFA utilizza il metodo "qualcosa che non è facilmente duplicato" per la verifica aggiuntiva. Esistono diversi modi in cui è possibile abilitare l'autenticazione a più fattori per Microsoft 365 e Office 365:

- Con le impostazioni predefinite di sicurezza
- Con criteri di accesso condizionale
- Per ogni singolo account utente (scelta non consigliata)

Questi modi si basano sul piano di Microsoft 365.

|Piano|Consiglio|Tipo di cliente|
|---|---|---|
|Tutti i piani di Microsoft 365|Usa le impostazioni predefinite di sicurezza, che richiedono l'autenticazione a più fattori per tutti gli account utente. <p> È anche possibile configurare l'autenticazione a più fattori per utente per singoli account utente, ma questa operazione non è consigliata.|Azienda di piccole dimensioni|
|Microsoft 365 Business Premium <p> Microsoft 365 E3 <p> Licenze di Azure Active Directory (Azure AD) Premium P1|Usa i criteri di accesso condizionale per richiedere l'autenticazione a più fattori per gli account utente in base all'appartenenza a gruppi, alle app o ad altri criteri.|Da piccole aziende a imprese|
|Microsoft 365 E5 <p> Licenze di Azure AD Premium P2|Usare Azure AD Identity Protection per richiedere l'autenticazione a più fattori in base ai criteri di rischio di accesso.|Grandi aziende|
||||

### <a name="security-defaults"></a>Impostazioni predefinite per la sicurezza

Le impostazioni predefinite di sicurezza sono una nuova funzionalità per gli abbonamenti a pagamento o di valutazione di Microsoft 365 e Office 365 creati dopo il 21 ottobre 2019. Per queste sottoscrizioni sono attivate le impostazioni predefinite di sicurezza, che:

- Richiede a tutti gli utenti di usare l'autenticazione a più fattori con l'app Microsoft Authenticator.
- Blocca l'autenticazione legacy.

Gli utenti hanno 14 giorni per registrarsi per la MFA con l'app Microsoft Authenticator dai propri smartphone, periodo che inizia dalla prima volta che accedono dopo aver abilitato le impostazioni predefinite di sicurezza. Trascorsi 14 giorni, l'utente non sarà in grado di accedere fino al completamento della registrazione della MFA.

Le impostazioni di sicurezza predefinite garantiscono che tutte le organizzazioni dispongano di un livello base di sicurezza per l'accesso degli utenti abilitato per impostazione predefinita. È possibile disabilitare le impostazioni predefinite di sicurezza a favore dell'autenticazione a più fattori con i criteri di accesso condizionale.

Le impostazioni predefinite di sicurezza vengono abilitate o disabilitate dal **riquadro** Proprietà per Azure AD nel portale di Azure.

![Immagine della pagina Proprietà directory.](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

È possibile utilizzare le impostazioni predefinite di sicurezza con qualsiasi piano di Microsoft 365.

Per altre informazioni, vedere questa [panoramica delle impostazioni predefinite di sicurezza](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).

### <a name="conditional-access-policies"></a>Criteri di accesso condizionale

I criteri di accesso condizionale sono un insieme di regole che specificano le condizioni in base alle quali gli accessi vengono valutati e consentiti. Ad esempio, è possibile creare un criterio di accesso condizionale che indichi:

- Se il nome dell'account utente corrisponde a un membro di un gruppo per utenti a cui sono assegnati i ruoli di amministratore di Exchange, utenti, password, sicurezza, SharePoint o globale, richiedere la MFA prima di consentire l'accesso.

Questo criterio consente di richiedere l'autenticazione a più fattori in base all'appartenenza al gruppo, anziché configurare i singoli account utente per l'autenticazione a più fattori quando vengono assegnati o non assegnati tramite questi ruoli di amministratore.

Puoi anche usare i criteri di accesso condizionale per funzionalità più avanzate, ad esempio la richiesta dell'autenticazione a più fattori per app specifiche o che l'accesso viene eseguito da un dispositivo conforme, ad esempio il portatile che esegue Windows 10.

È possibile configurare i criteri di accesso condizionale dal **riquadro** Sicurezza per Azure AD nel portale di Azure.

![Opzione Immagine del menu per l'accesso condizionale](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

È possibile utilizzare i criteri di accesso condizionale con:

- Microsoft 365 Business Premium
- Microsoft 365 E3 e E5
- Licenze di Azure AD Premium P1 e Azure AD Premium P2

Per le piccole imprese con Microsoft 365 Business Premium, è possibile utilizzare facilmente i criteri di accesso condizionale con i passaggi seguenti:

1. Creare un gruppo per contenere gli account utente che richiedono l'autenticazione a più fattori.
2. Abilitare il **criterio Richiedi MFA per gli amministratori** globali.
3. Creare un criterio di accesso condizionale basato su gruppo con queste impostazioni:
    - Assegnazioni > utenti e gruppi: nome del gruppo dal passaggio 1 precedente.
    - Assegnazioni > app cloud o azioni: tutte le app cloud.
    - I controlli di > concedi > l'accesso > richiedono l'autenticazione a più fattori.
4. Abilitare il criterio.
5. Aggiungere un account utente al gruppo creato nel passaggio 1 precedente e testare.
6. Per richiedere l'autenticazione a più fattori per altri account utente, aggiungerli al gruppo creato nel passaggio 1.

Questo criterio di accesso condizionale consente di implementare il requisito MFA per gli utenti in base alle proprie esigenze.

Le aziende devono utilizzare [i criteri di accesso condizionale comuni](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) per configurare i criteri seguenti:

- [Richiedere la MFA per amministratori](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [Richiedere la MFA per tutti gli utenti](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [Bloccare l'autenticazione legacy](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

Per altre informazioni, vedere questa [panoramica dell'accesso condizionale](/azure/active-directory/conditional-access/overview).

### <a name="azure-ad-identity-protection"></a>Azure AD Identity Protection

Con Azure AD Identity Protection, è possibile creare criteri di accesso condizionale aggiuntivi per richiedere [l'autenticazione](../../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)a più fattori quando il rischio di accesso è medio o elevato.

È possibile usare Azure AD Identity Protection e i criteri di accesso condizionale basati sui rischi con:

- Microsoft 365 E5
- Licenze di Azure AD Premium P2

Per ulteriori informazioni, vedere questa [panoramica di Azure AD Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection).

### <a name="legacy-per-user-mfa-not-recommended"></a>MFA legacy per utente (scelta non consigliata)

È consigliabile utilizzare le impostazioni predefinite di sicurezza o i criteri di accesso condizionale per richiedere l'autenticazione a più fattori per gli accessi dell'account utente. Tuttavia, se uno di questi non può essere utilizzato, Microsoft consiglia vivamente L'autenticazione a più fattori per gli account utente con ruoli di amministratore, in particolare il ruolo di amministratore globale, per qualsiasi sottoscrizione di dimensione.

L'autenticazione a più fattori per i singoli account utente viene abilitata dal riquadro **Utente** attivo dell'interfaccia di amministrazione di Microsoft 365.

![Immagine dell'opzione Autenticazione a più fattori nella pagina Utenti attivi](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

Dopo essere stato abilitato, al successivo accesso dell'utente verrà richiesto di registrarsi per L'autenticazione a più fattori e di scegliere e testare il metodo di verifica aggiuntivo.

### <a name="using-these-methods-together"></a>Usare questi metodi insieme

Questa tabella mostra i risultati dell'abilitazione della MFA con impostazioni predefinite di sicurezza, criteri di accesso condizionale e impostazioni dell'account per utente.

||Abilitato|Disattivato|Metodo di autenticazione secondario|
|---|---|---|---|
|**Impostazioni predefinite per la sicurezza**|Non è possibile utilizzare i criteri di accesso condizionale|È possibile utilizzare i criteri di accesso condizionale|App Microsoft Authenticator|
|**Criteri di accesso condizionale**|Se sono abilitati, non è possibile abilitare le impostazioni predefinite di sicurezza|Se sono tutti disabilitati, è possibile abilitare le impostazioni predefinite per la sicurezza|Specificato dall'utente durante la registrazione della MFA|
|**MFA legacy per utente (scelta non consigliata)**|Sostituisce le impostazioni predefinite di sicurezza e i criteri di accesso condizionale che richiedono l'autenticazione a più fattori a ogni accesso|Ignorato dalle impostazioni predefinite di sicurezza e dai criteri di accesso condizionale|Specificato dall'utente durante la registrazione della MFA|
||||

Se sono abilitate le impostazioni predefinite di sicurezza, a tutti i nuovi utenti viene richiesta la registrazione MFA e l'uso dell'app Microsoft Authenticator al successivo accesso.

## <a name="ways-to-manage-mfa-settings"></a>Modi per gestire le impostazioni MFA

Esistono due modi per gestire le impostazioni MFA.

Nel portale di Azure è possibile:

- Abilitare e disabilitare le impostazioni predefinite di sicurezza
- Configurare i criteri di accesso condizionale

Nell'interfaccia di amministrazione di Microsoft 365 è possibile configurare le impostazioni MFA per utente e servizio.

## <a name="your-next-step"></a>Passaggio successivo

[Configurare MFA per Microsoft 365](set-up-multi-factor-authentication.md)

## <a name="related-topics"></a>Argomenti correlati

[Video: Attivare l'autenticazione a più fattori](../../business-video/turn-on-mfa.md)

[Video: Attivare l'autenticazione a più fattori per il telefono](../../business-video/set-up-mfa.md)