---
title: Sincronizzare gli utenti di dominio a Microsoft 365
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
description: Sincronizzare gli utenti controllati dal dominio con Microsoft 365 for business.
ms.openlocfilehash: a22e567fa99456b35742fcf40c07193c96c83cf0
ms.sourcegitcommit: e6e704cbd9a50fc7db1e6a0cf5d3f8c6cbb94363
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "44565688"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>Sincronizzare gli utenti di dominio a Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. preparare la sincronizzazione della directory 

Prima di sincronizzare gli utenti e i computer dal dominio Active Directory locale, esaminare [prepararsi per la sincronizzazione della directory in Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization). In particolare:

   - Verificare che nella directory non siano presenti duplicati per gli attributi seguenti: **mail**, **proxyAddresses**e **userPrincipalName**. Questi valori devono essere univoci e tutti i duplicati devono essere rimossi.
   
   - Si consiglia di configurare l'attributo **userPrincipalName** (UPN) per ogni account utente locale in modo che corrisponda all'indirizzo di posta elettronica principale corrispondente all'utente con licenza Microsoft 365. Ad esempio: *Mary.Shelley@contoso.com* anziché *Mary@contoso. local*
   
   - Se il dominio Active Directory termina con un suffisso non instradabile come *. local* o *. LAN*, invece di un suffisso instradabile su Internet, ad esempio *. com* o *. org*, modificare il suffisso UPN degli account utente locali come descritto in [preparare un dominio non instradabile per la sincronizzazione della directory](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization). 

L' **esecuzione di IdFix** nel passaggio quattro (4) seguente assicurerà inoltre che Active Directory locale sia pronto per la sincronizzazione con dir.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. installare e configurare Azure AD Connect

Per sincronizzare gli utenti, i gruppi e i contatti da Active Directory locale ad Azure Active Directory, installare Azure Active Directory Connect e configurare la sincronizzazione della directory. 

 1. Nell'interfaccia di amministrazione di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> selezionare **Setup** nella barra di spostamento a sinistra.

 2. In **accesso e sicurezza**, scegliere **Visualizza** in **Sincronizza utenti dalla directory dell'organizzazione**.

 3. Nella pagina **Sync Users from your org ' s directory** scegliere **Get Started**.

 4. Nel primo passaggio eseguire lo strumento IdFix per preparare la sincronizzazione della directory.

 5. Seguire la procedura guidata per scaricare Azure AD Connect e utilizzarlo per sincronizzare gli utenti controllati dal dominio a Microsoft 365.


Per ulteriori informazioni, vedere [configurare la sincronizzazione della directory per Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) .

Quando si configurano le opzioni per Azure AD Connect, è consigliabile abilitare la **sincronizzazione delle password**, l' **accesso Single Sign-on senza**problemi e la funzionalità writeback delle **password** , supportata anche in Microsoft 365 for business.

> [!NOTE]
> Sono disponibili ulteriori passaggi per il writeback delle password oltre la casella di controllo in Azure AD Connect. Per ulteriori informazioni, vedere [How-to: Configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). 

Se si desidera gestire anche i dispositivi Windows 10 aggiunti a un dominio, vedere [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) per configurare un join di Azure ad ibrido. 