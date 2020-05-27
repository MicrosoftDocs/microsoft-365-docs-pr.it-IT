---
title: Autenticazione a più fattori per Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
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
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni sull'autenticazione a più fattori in Microsoft 365.
ms.openlocfilehash: eba9ae38dbc17a22abb5d5ef92b8cd30a827ae11
ms.sourcegitcommit: 87eff6e8a08cec3cb0464a3b765434717584a4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "44371453"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a>Autenticazione a più fattori per Microsoft 365

Le password sono il metodo più comune per l'autenticazione di un accesso a un computer o a un servizio online, ma sono anche le più vulnerabili. Gli utenti possono scegliere password facili e utilizzare le stesse password per accedere a più accessi a computer e servizi diversi.

Per fornire un ulteriore livello di sicurezza per gli accessi, è necessario utilizzare l'autenticazione a più fattori (AMF), che utilizza sia una password, che deve essere forte, sia un ulteriore metodo di verifica basato sui seguenti valori:

- Qualcosa che si ha con voi che non è facilmente duplicato, ad esempio uno Smart Phone.
- Qualcosa che si ha in modo univoco e biologicamente, ad esempio le impronte digitali, la faccia o altri attributi biometrici.

Il metodo di verifica aggiuntivo non viene utilizzato fino a quando la password dell'utente non è stata verificata. Con AMF, anche se una password utente complessa è danneggiata, l'aggressore non ha lo Smart Phone o l'impronta digitale per completare l'accesso.

## <a name="mfa-support-in-microsoft-365"></a>Supporto dell'AMF in Microsoft 365
Per impostazione predefinita, sia Microsoft 365 che Office 365 supportano AMF per gli account utente utilizzando:

- Un messaggio di testo inviato a un telefono che richiede all'utente di immettere un codice di verifica.
- Una telefonata.
- App Smart Phone Microsoft Authenticator.

In entrambi i casi, l'accesso dell'AMF utilizza il metodo "something you have with you that is not facilmente Duplicated" per la verifica aggiuntiva.
Esistono diversi modi in cui è possibile abilitare l'AMF per Microsoft 365 e Office 365:

- Con le impostazioni predefinite di sicurezza
- Con i criteri di accesso condizionale
- Per ogni singolo account utente (non consigliato)

Questi modi si basano sul piano Microsoft 365.
    
|Piano  |Consiglio  | Tipo di cliente |
|---------|---------|----------|
| Tutti i piani di Microsoft 365 | Utilizzare le impostazioni predefinite per la sicurezza, che richiedono l'AMF per tutti gli account utente. <br> È inoltre possibile richiedere l'utilizzo dell'AMF in base all'account utente, ma non è consigliabile. | Azienda di piccole dimensioni |
| Microsoft 365 Business Premium <br><br> Microsoft 365 E3 <br><br> Licenze P1 di Azure Active Directory (Azure AD) | Utilizzare i criteri di accesso condizionale per richiedere l'utilizzo dell'AMF per gli account utente in base all'appartenenza ai gruppi, alle app o ad altri criteri. | Small Business to Enterprise |
| Microsoft 365 E5 <br><br> Licenze P2 di Azure AD Premium | Usare Azure AD Identity Protection per richiedere l'utilizzo dell'AMF in base ai criteri di rischio di accesso. |  Grandi aziende |
||||

### <a name="security-defaults"></a>Impostazioni predefinite per la sicurezza

Le impostazioni predefinite di sicurezza sono una nuova funzionalità per gli abbonamenti a pagamento o di valutazione di Microsoft 365 e Office 365 creati dopo il 21 ottobre 2019. Sono state attivate le impostazioni predefinite per la sicurezza, che sono le seguenti:

- Richiede a tutti gli utenti di utilizzare il master con l'app Microsoft Authenticator.
- Blocca l'autenticazione legacy.

Gli utenti hanno 14 giorni per registrarsi per la MFA con l'app Microsoft Authenticator dai propri smartphone, periodo che inizia dalla prima volta che accedono dopo aver abilitato le impostazioni predefinite di sicurezza. Trascorsi 14 giorni, l'utente non sarà in grado di accedere fino al completamento della registrazione della MFA.

Le impostazioni di sicurezza predefinite garantiscono che tutte le organizzazioni dispongano di un livello base di sicurezza per l'accesso degli utenti abilitato per impostazione predefinita. È possibile disabilitare le impostazioni predefinite per la sicurezza in favore dell'AMF con criteri di accesso condizionale.

È possibile abilitare o disabilitare le impostazioni predefinite di sicurezza dal riquadro delle **Proprietà** di Azure ad nel portale di Azure.

![](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

È possibile utilizzare le impostazioni predefinite di sicurezza con qualsiasi piano di Microsoft 365.

Per altre informazioni, vedere questa [panoramica delle impostazioni predefinite di sicurezza](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). 

### <a name="conditional-access-policies"></a>Criteri di accesso condizionale

I criteri di accesso condizionale sono un insieme di regole che specificano le condizioni in base alle quali gli accessi vengono valutati e consentiti. Ad esempio, è possibile creare un criterio di accesso condizionale che indichi:

- Se il nome dell'account utente corrisponde a un membro di un gruppo per utenti a cui sono assegnati i ruoli di amministratore di Exchange, utenti, password, sicurezza, SharePoint o globale, richiedere la MFA prima di consentire l'accesso.

Questo criterio consente di richiedere l'autenticazione a più fattori in base all'appartenenza al gruppo, anziché configurare i singoli account utente per l'autenticazione a più fattori quando vengono assegnati o non assegnati tramite questi ruoli di amministratore.

È inoltre possibile utilizzare i criteri di accesso condizionale per funzionalità più avanzate, ad esempio l'utilizzo dell'AMF per specifiche app o l'esecuzione dell'accesso da un dispositivo compatibile, ad esempio il laptop che esegue Windows 10.

È possibile configurare i criteri di accesso condizionale dal riquadro di **sicurezza** di Azure ad nel portale di Azure.

![](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

È possibile utilizzare i criteri di accesso condizionale con:

- Microsoft 365 Business Premium
- Microsoft 365 E3 ed E5
- Licenze di Azure AD Premium P1 e Azure AD Premium P2 

Per le aziende di piccole dimensioni con Microsoft 365 Business Premium, è possibile utilizzare facilmente i criteri di accesso condizionale con i passaggi seguenti:

1. Creare un gruppo che contenga gli account utente che richiedono l'utilizzo dell'AMF.
2. Abilitare il criterio **per gli amministratori globali per** l'autenticazione obbligatoria.
3. Creare un criterio di accesso condizionale basato su gruppo con queste impostazioni:
    - Assegnazioni > utenti e gruppi: il nome del gruppo al passaggio 1.
    - Assegnazioni > app o azioni cloud: tutte le app cloud.
    - I controlli di accesso > Grant > Grant Access > richiedono l'autenticazione a più fattori.
4. Abilitazione del criterio.
5. Aggiungere un account utente al gruppo creato nel passaggio 1 sopra e testare.
6. Per richiedere l'utilizzo dell'AMF per account utente aggiuntivi, aggiungerli al gruppo creato nel passaggio 1.

Questo criterio di accesso condizionale consente di implementare il requisito dell'AMF per gli utenti a proprio piacimento.

Le aziende devono utilizzare [criteri di accesso condizionale comuni](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) per configurare i criteri seguenti:

- [Richiedere la MFA per amministratori](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [Richiedere la MFA per tutti gli utenti](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [Bloccare l'autenticazione legacy](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

Per altre informazioni, vedere questa [panoramica dell'accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).

### <a name="azure-ad-identity-protection"></a>Azure AD Identity Protection

Con Azure AD Identity Protection, è possibile creare un ulteriore criterio di accesso condizionale per richiedere il livello di sicurezza [dell'AMF quando il rischio di iscrizione è medio o elevato](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).

È possibile utilizzare i criteri di accesso condizionale di Azure AD Identity Protection e Risk-based con:

- Microsoft 365 E5
- Licenze P2 di Azure AD Premium

Per ulteriori informazioni, vedere questa [panoramica di Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).

### <a name="mfa-for-an-individual-user-account-not-recommended"></a>AMF per un singolo account utente (non consigliato)

È consigliabile utilizzare i criteri di sicurezza o di accesso condizionale per richiedere l'autenticazione per l'account utente. Tuttavia, se una di queste non può essere utilizzata, Microsoft consiglia di utilizzare l'AMF per gli account utente che dispongono di ruoli di amministratore, in particolare il ruolo di amministratore globale, per qualsiasi sottoscrizione di dimensioni. 

È possibile abilitare l'AMF per singoli account utente dal riquadro **utente attivo dell'interfaccia** di amministrazione di Microsoft 365.

![](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

Dopo essere stato abilitato, la volta successiva che l'utente accede, verrà richiesto di registrarsi per l'AMF e di scegliere e testare il metodo di verifica aggiuntivo.

### <a name="using-these-methods-together"></a>Usare questi metodi insieme

Questa tabella mostra i risultati dell'abilitazione della MFA con impostazioni predefinite di sicurezza, criteri di accesso condizionale e impostazioni dell'account per utente.

|| Abilitato | Disattivato | Metodo di autenticazione secondario |
|:-------|:-----|:-------|:-------|
| **Impostazioni predefinite per la sicurezza** | Non è possibile utilizzare i criteri di accesso condizionale |   È possibile utilizzare i criteri di accesso condizionale | App Microsoft Authenticator |
| **Criteri di accesso condizionale** |Se alcuni sono abilitati, non è possibile abilitare le impostazioni predefinite per la sicurezza | Se sono tutti disabilitati, è possibile abilitare le impostazioni predefinite per la sicurezza | Specificato dall'utente durante la registrazione della MFA |
| **Impostazione dell'account per utente (non consigliata)** | Esegue l'override delle impostazioni predefinite per la sicurezza e i criteri di accesso condizionale che richiedono l'AMF a ogni accesso | Sottoposto a override da criteri di accesso condizionale e impostazioni predefinite per la sicurezza | Specificato dall'utente durante la registrazione della MFA|
||||

Se le impostazioni predefinite per la sicurezza sono abilitate, tutti i nuovi utenti vengono richieste per la registrazione dell'AMF e per l'utilizzo dell'app Microsoft Authenticator all'accesso successivo.

## <a name="ways-to-manage-mfa-settings"></a>Modalità di gestione delle impostazioni dell'AMF

Esistono due modi per gestire le impostazioni dell'AMF.

Nel portale di Azure, è possibile:

- Abilitare e disabilitare le impostazioni predefinite per la sicurezza
- Configurare i criteri di accesso condizionale

Nell'interfaccia di amministrazione di Microsoft 365, è possibile configurare le impostazioni dell'AMF per utente e dei servizi.

## <a name="your-next-step"></a>Passaggio successivo

[Configurare l'AMF per Microsoft 365](set-up-multi-factor-authentication.md)

