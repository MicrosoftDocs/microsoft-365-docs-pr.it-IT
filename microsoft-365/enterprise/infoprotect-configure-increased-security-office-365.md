---
title: 'Passaggio 3: Configurare un livello di sicurezza maggiore per Microsoft 365'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare un livello di sicurezza maggiore per Microsoft 365.
ms.openlocfilehash: fcf023960679cf624f3ea7421ab92b1a450d2524
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400030"
---
# <a name="step-3-configure-increased-security-for-microsoft-365"></a>Passaggio 3: Configurare un livello di sicurezza maggiore per Microsoft 365

*Questo passaggio è obbligatorio e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Per assicurarsi che l'abbonamento a Microsoft 365 e i relativi dati siano protetti da minacce, configurare quanto segue:

- [Ottimizzare i criteri di gestione delle minacce](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#tune-threat-management-policies-in-the-office-365-security--compliance-center)
- [Impostazioni tenant aggiuntive di Exchange Online](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-additional-exchange-online-tenant-wide-settings)
- [Criteri di condivisione del tenant nell'interfaccia di amministrazione di SharePoint](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-tenant-wide-sharing-policies-in-sharepoint-admin-center)
- [Impostazioni di Azure Active Directory (Azure AD)](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-settings-in-azure-active-directory)

Una volta configurati questi elementi, è possibile ottenere informazioni sullo stato di sicurezza in:

- [Dashboard e report nel Centro sicurezza Microsoft](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#view-dashboards-and-reports-in-the-security--compliance-center)
- [Microsoft Secure Score](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)

Una funzionalità di sicurezza aggiuntiva è [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp), che consente all'organizzazione di collaborare in modo più sicuro attraverso:

- La protezione dei [collegamenti](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) e degli [allegati](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) nella posta elettronica. 
- La fornitura di funzionalità spoof intelligence e anti-phishing per la posta elettronica in Exchange Online e nei [file in SharePoint Online, OneDrive for Business e Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams). 

Office 365 ATP è disponibile solo con Microsoft 365 Enterprise E5.

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guida al lab di test: Configurare un livello di sicurezza maggiore per Microsoft 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step3) che corrispondono a questo passaggio.

## <a name="next-step"></a>Passaggio successivo


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[Configurare Windows Information Protection](infoprotect-deploy-windows-information-protection.md)|


