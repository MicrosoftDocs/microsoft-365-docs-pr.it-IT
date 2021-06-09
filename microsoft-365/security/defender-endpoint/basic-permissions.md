---
title: Usare le autorizzazioni di base per accedere Microsoft Defender Security Center
description: Scopri come usare le autorizzazioni di base per accedere al portale di Microsoft Defender for Endpoint.
keywords: assegnare ruoli utente, assegnare l'accesso in lettura e scrittura, assegnare l'accesso di sola lettura, utente, ruoli utente, ruoli
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2d022e903111c498d6f3b7411857748fcb637b64
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844659"
---
# <a name="use-basic-permissions-to-access-the-portal"></a>Usare le autorizzazioni di base per accedere al portale

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- Azure Active Directory
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

Fare riferimento alle istruzioni seguenti per utilizzare la gestione delle autorizzazioni di base.

È possibile utilizzare una delle soluzioni seguenti:
- Azure PowerShell
- Portale di Azure

Per un controllo granulare sulle autorizzazioni, [passare al controllo di accesso basato sui ruoli.](rbac.md)

## <a name="assign-user-access-using-azure-powershell"></a>Assegnare l'accesso utente Azure PowerShell
È possibile assegnare agli utenti uno dei seguenti livelli di autorizzazioni:
- Accesso completo (lettura e scrittura)
- Accesso in sola lettura

### <a name="before-you-begin"></a>Prima di iniziare

- Installare Azure PowerShell. Per ulteriori informazioni, vedere [Come installare e configurare Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).<br>

    > [!NOTE]
    > È necessario eseguire i cmdlet di PowerShell in una riga di comando con privilegi elevati.

- Connessione al Azure Active Directory. Per ulteriori informazioni, vedere [Connessione-MsolService](/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true).

**Accesso completo** <br>
Gli utenti con accesso completo possono accedere, visualizzare tutte le informazioni di sistema e risolvere gli avvisi, inviare file per l'analisi approfondita e scaricare il pacchetto di onboarding.
L'assegnazione dei diritti di accesso completi richiede l'aggiunta degli utenti ai ruoli predefiniti "Amministratore della sicurezza" o "Amministratore globale" di AAD.

**Accesso in sola lettura** <br>
Gli utenti con accesso in sola lettura possono accedere, visualizzare tutti gli avvisi e le informazioni correlate.
Non saranno in grado di modificare gli stati di avviso, inviare file per l'analisi approfondita o eseguire operazioni di modifica dello stato.
L'assegnazione dei diritti di accesso di sola lettura richiede l'aggiunta degli utenti al ruolo predefinito "Lettore di sicurezza" di Azure AD.

Per assegnare ruoli di sicurezza, eseguire la procedura seguente:

- Per **l'accesso in** lettura e scrittura, assegnare gli utenti al ruolo di amministratore della sicurezza utilizzando il comando seguente:

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- Per **l'accesso in sola** lettura, assegnare gli utenti al ruolo lettore di sicurezza utilizzando il comando seguente:

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

Per ulteriori informazioni, vedere [Add or remove group members using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).

## <a name="assign-user-access-using-the-azure-portal"></a>Assegnare l'accesso utente tramite il portale di Azure

Per ulteriori informazioni, vedere [Assegnare ruoli di amministratore](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)e non amministratore agli utenti con Azure Active Directory .

## <a name="related-topic"></a>Argomento correlato

- [Gestire l'accesso al portale con RBAC](rbac.md)
