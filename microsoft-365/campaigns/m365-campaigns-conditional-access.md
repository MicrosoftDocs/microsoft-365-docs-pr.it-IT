---
title: Configurare i criteri di accesso condizionale
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come richiedere l'autenticazione a più fattori e configurare i criteri di accesso condizionale per Microsoft 365 per le aziende.
ms.openlocfilehash: b13ba9f8c948d9a1209655c44871ca62cb5354dd
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044501"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a>Richiedere l'autenticazione a più fattori e configurare i criteri di accesso condizionale

È possibile proteggere l'accesso ai dati con l'autenticazione a più fattori e i criteri di accesso condizionale. Questi elementi aggiungono una sicurezza aggiuntiva sostanziale. Microsoft fornisce un set di criteri di accesso condizionale di base consigliati per tutti i clienti. I criteri di base sono un insieme di criteri predefiniti che consentono di proteggere le organizzazioni da molti attacchi comuni. Questi attacchi comuni possono includere password spray, replay e phishing.

Questi criteri richiedono ad amministratori e utenti di immettere una seconda forma di autenticazione (denominata autenticazione a più fattori o MFA) in determinate condizioni. Ad esempio, se un utente dell'organizzazione tenta di accedere a Microsoft 365 da un paese diverso o da un dispositivo sconosciuto, l'accesso potrebbe essere considerato rischioso. L'utente deve fornire una forma aggiuntiva di autenticazione ,ad esempio un'impronta digitale o un codice, per dimostrare la propria identità.

Attualmente, i criteri di base includono i criteri seguenti:

- Configurare nell'interfaccia di amministrazione di Microsoft 365:
  - **Richiedi autenticazione a più** fattori per gli amministratori: richiede l'autenticazione a più fattori per i ruoli di amministratore con privilegi più elevati, incluso l'amministratore globale.
  - **Protezione dell'utente finale:** richiede l'autenticazione a più fattori per gli utenti solo quando un accesso è rischioso. 
- Configurare nel portale di Azure Active Directory:
  - **Bloccare l'autenticazione legacy:** le app client meno recenti e alcune nuove app non usano protocolli di autenticazione più recenti e più sicuri. Queste app meno recenti possono ignorare i criteri di accesso condizionale e ottenere l'accesso non autorizzato all'ambiente. Questo criterio blocca l'accesso dai client che non supportano l'accesso condizionale. 
  - **Richiedi L'autenticazione a più** fattori per la gestione dei servizi : richiede l'autenticazione a più fattori per l'accesso agli strumenti di gestione, incluso il portale di Azure (in cui è possibile configurare i criteri di base).

È consigliabile abilitare tutti questi criteri di base. Dopo aver abilitato questi criteri, agli amministratori e agli utenti verrà richiesto di registrarsi per l'autenticazione a più fattori di Azure AD.

Per ulteriori informazioni su questi criteri, vedere [Che cosa sono i criteri di base?](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)

## <a name="require-mfa"></a>Richiedere la MFA

Per richiedere a tutti gli utenti di accedere con un secondo formato di ID:

1. Accedere all'interfaccia di amministrazione e <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> scegliere **Installazione.**

2. Nella pagina Installazione scegliere **Visualizza** nella scheda Rendi più sicuro **l'accesso.**

    ![Rendere più sicura la scheda di accesso.](../media/setupmfa.png)
3. Nella pagina Rendi più sicuro l'accesso scegliere **Introduzione.**

4. Nel riquadro Rafforzare la sicurezza di accesso selezionare  le caselle di controllo accanto a Richiedi autenticazione a più fattori per gli amministratori e Richiedi agli utenti di registrarsi per l'autenticazione a più fattori e bloccare l'accesso se vengono rilevati **rischi.**
    Assicurati di escludere [l'account](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) amministratore di emergenza o "break-glass" dal requisito MFA nella **casella Trova** utenti.

    ![Pagina Rafforzare la sicurezza del componente aggiuntivo.](../media/requiremfa.png)

5. Scegliere **Crea criterio** nella parte inferiore della pagina.

## <a name="set-up-baseline-policies"></a>Configurare i criteri di base

1. Passare al portale [di Azure](https://portal.azure.com)e quindi passare ad Accesso condizionale di Azure **Active Directory** per creare un \>  nuovo **criterio.**

Per ogni criterio, vedere le istruzioni specifiche seguenti: <br>
    - [Richiedere l'autenticazione a più fattori per gli amministratori](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [Richiedere l'autenticazione a più fattori per gli utenti](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [Bloccare l'autenticazione legacy](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [Richiedere l'autenticazione a più fattori per la gestione dei servizi](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

> [!NOTE]
> I criteri di anteprima non esistono più e gli utenti dovranno creare i propri criteri.

Puoi configurare criteri aggiuntivi, ad esempio richiedere app client approvate. Per ulteriori informazioni, vedere la [documentazione relativa all'accesso condizionale.](https://docs.microsoft.com/azure/active-directory/conditional-access/)
