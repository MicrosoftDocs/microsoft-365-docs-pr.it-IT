---
title: Sincronizzare gli utenti di dominio con Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
ms.openlocfilehash: b477b8a1f35a790d6c49937c973c141ad9f90ad4
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578408"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>Sincronizzare gli utenti di dominio con Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. Preparare la sincronizzazione della directory 

Prima di sincronizzare utenti e computer dal dominio Active Directory locale, vedere [Prepare for directory synchronization to Microsoft 365](../enterprise/prepare-for-directory-synchronization.md). In particolare:

   - Verificare che nella directory non siano presenti duplicati per gli attributi **seguenti: mail,** **proxyAddresses** e **userPrincipalName**. Questi valori devono essere univoci ed eventuali duplicati devono essere rimossi.
   
   - È consigliabile configurare l'attributo **userPrincipalName** (UPN) per ogni account utente locale in modo che corrisponda all'indirizzo di posta elettronica principale corrispondente all'utente Microsoft 365 con licenza. Ad esempio: *mary.shelley@contoso.com* anziché *mary@contoso.local*
   
   - Se il dominio di Active Directory termina con un suffisso non instradabile come *.local* o *.lan*, invece di un suffisso instradabile internet come *.com* o *.org,* regola il suffisso UPN degli account utente locali come descritto in [Prepare a non-routable domain for directory synchronization](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md). 

**L'esecuzione di IdFix** nel passaggio 4 (4) seguente assicura inoltre che Active Directory locale sia pronto per la sincronizzazione della directory.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Installare e configurare Azure AD Connessione

Per sincronizzare utenti, gruppi e contatti da Active Directory locale a Azure Active Directory, installare Azure Active Directory Connessione e configurare la sincronizzazione della directory. 

 1. [Nell'interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=2024339)seleziona **Installazione** nel riquadro di spostamento a sinistra.

 2. In **Accesso e sicurezza** scegliere Visualizza in Sincronizza utenti dalla directory **dell'organizzazione.** 

 3. Nella pagina **Sincronizza utenti dalla directory dell'organizzazione** scegliere **Introduzione.**

 4. Nel primo passaggio eseguire lo strumento IdFix per preparare la sincronizzazione della directory.

 5. Segui i passaggi della procedura guidata per scaricare Azure AD Connessione e usarlo per sincronizzare gli utenti controllati dal dominio con Microsoft 365.


Per ulteriori informazioni, vedere [Set up directory synchronization for Microsoft 365.](../enterprise/set-up-directory-synchronization.md)

Quando si configurano le opzioni per Azure AD Connessione, è consigliabile abilitare la sincronizzazione delle **password,** **l'accesso Single #A0** e la funzionalità di writeback delle **password,** supportata anche in Microsoft 365 per le aziende.

> [!NOTE]
> Esistono alcuni passaggi aggiuntivi per il writeback delle password oltre la casella di controllo in Azure AD Connessione. Per ulteriori informazioni, vedere [Procedura: configurare il writeback delle password.](/azure/active-directory/authentication/howto-sspr-writeback) 

Se vuoi anche gestire i dispositivi Windows 10 aggiunti al dominio, vedi Abilitare i dispositivi Windows 10 aggiunti [al](manage-windows-devices.md) dominio da Microsoft 365 Business Premium per configurare un'aggiunta ibrida ad Azure AD.