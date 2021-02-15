---
title: Sincronizzare gli utenti di dominio con Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Sincronizzare gli utenti controllati dal dominio con Microsoft 365 per le aziende.
ms.openlocfilehash: b40a995a1723808d2fd171c534e9131a891840ba
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841360"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>Sincronizzare gli utenti di dominio con Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. Preparare la sincronizzazione della directory 

Prima di sincronizzare utenti e computer dal dominio Active Directory locale, vedere Preparare la sincronizzazione [della directory con Microsoft 365.](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization) In particolare:

   - Verificare che nella directory non siano presenti duplicati per gli attributi **seguenti: mail,** **proxyAddresses** e **userPrincipalName.** Questi valori devono essere univoci ed eventuali duplicati devono essere rimossi.
   
   - È consigliabile configurare l'attributo **userPrincipalName** (UPN) per ogni account utente locale in modo che corrisponda all'indirizzo di posta elettronica principale corrispondente all'utente con licenza di Microsoft 365. Ad esempio: *mary.shelley@contoso.com* anziché *mary@contoso.local*
   
   - Se il dominio di Active Directory termina con un suffisso non instradabile come *.local* o *.lan*, invece di un suffisso instradabile su Internet come *.com* o *.org,* regola il suffisso UPN degli account utente locali come descritto in Preparare un dominio non instradabile per la sincronizzazione [della directory.](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization) 

**L'esecuzione di IdFix** nel passaggio quattro (4) seguente, assicura inoltre che Active Directory locale sia pronto per la sincronizzazione della directory.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Installare e configurare Azure AD Connect

Per sincronizzare utenti, gruppi e contatti da Active Directory locale ad Azure Active Directory, installare Azure Active Directory Connect e configurare la sincronizzazione della directory. 

 1. [Nell'interfaccia di amministrazione,](https://go.microsoft.com/fwlink/p/?linkid=2024339)selezionare **Installazione** nel riquadro di spostamento sinistro.

 2. In **Accesso e sicurezza** scegliere Visualizza in Sincronizza utenti dalla directory **dell'organizzazione.** 

 3. Nella pagina **Sincronizza utenti dalla directory dell'organizzazione** scegliere **Introduzione.**

 4. Nel primo passaggio eseguire lo strumento IdFix per preparare la sincronizzazione della directory.

 5. Seguire i passaggi della procedura guidata per scaricare Azure AD Connect e usarlo per sincronizzare gli utenti controllati dal dominio con Microsoft 365.


Per altre informazioni, vedere Configurare la sincronizzazione della directory per [Microsoft 365.](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)

Quando si configurano le opzioni per Azure AD Connect, è consigliabile abilitare la sincronizzazione delle **password,** **l'accesso Single #A0** facile e la funzionalità di writeback delle **password,** supportata anche in Microsoft 365 per le aziende.

> [!NOTE]
> Esistono alcuni passaggi aggiuntivi per il writeback delle password oltre la casella di controllo in Azure AD Connect. Per ulteriori informazioni, vedere [Procedura: configurare il writeback delle password.](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback) 

Se vuoi anche gestire i dispositivi Windows 10 aggiunti a un dominio, vedi Abilitare i dispositivi Windows 10 aggiunti a un dominio per essere gestiti da [Microsoft 365 Business Premium](manage-windows-devices.md) per configurare un'aggiunta ad Azure AD ibrido. 