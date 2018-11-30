---
title: 'Passaggio 3: configurare un livello di sicurezza maggiore per Office 365'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Capire e configurare un livello di sicurezza maggiore per Office 365, tra cui Office 365 ATP.
ms.openlocfilehash: 0344778b8d8f9940dc6267a39eac2f4cfb261f9a
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868805"
---
# <a name="step-3-configure-increased-security-for-office-365"></a>Passaggio 3: configurare un livello di sicurezza maggiore per Office 365

*Questo passaggio è obbligatorio e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Per assicurarsi che l'abbonamento a Office 365 e i relativi dati siano protetti da minacce, vedere [Configurare il tenant di Office 365 per una maggiore sicurezza](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355) e configurare la protezione aggiuntiva seguente:

- Criteri di gestione delle minacce nel Centro sicurezza e conformità di Office 365
- Impostazioni tenant aggiuntive di Exchange Online
- Criteri di condivisione del tenant nell'interfaccia di amministrazione di SharePoint
- Impostazioni di Azure Active Directory

Una volta configurato, è possibile ottenere informazioni sullo stato di sicurezza in:

- Dashboard e report nel Centro sicurezza e conformità
- [Secure Score di Office 365](https://securescore.office.com/)
 
  Per accedere a questa pagina, è necessario effettuare l'accesso come amministratore del tenant di Office 365.

È anche possibile usare Cloud App Security o Office 365 Cloud App Security per monitorare gli eventi e le azioni di sicurezza. Per ulteriori informazioni, vedere [Panoramica di Office 365 Cloud App Security](https://support.office.com/article/Overview-of-Office-365-Cloud-App-Security-81f0ee9a-9645-45ab-ba56-de9cbccab475).

Una funzionalità di sicurezza aggiuntiva è Office 365 Advanced Threat Protection (ATP), che consente all'organizzazione di collaborare in modo più sicuro attraverso:

- La protezione dei collegamenti e degli allegati nella posta elettronica. 
- La fornitura di funzionalità spoof intelligence e anti-phishing per la posta elettronica in Exchange Online e nei file in SharePoint Online, OneDrive for Business e Microsoft Teams. 

>[!Note]
>Office 365 ATP è incluso in Microsoft 365 Enterprise E5. Se si dispone di Microsoft 365 Enterprise E3, è possibile acquistare licenze singole licenze di ATP.
>

Per attivare Office 365 ATP, vedere [Attivarlo](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).

Per ulteriori informazioni, vedere [Office 365 ATP per SharePoint, OneDrive, and Microsoft Teams](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607).


|||
|:-------|:-----|
|![Guide del laboratorio di testing per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guida al laboratorio di testing: configurazione della sicurezza aumentata di Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step4) che corrispondono a questo passaggio.

## <a name="next-step"></a>Passaggio successivo


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[Configurare la gestione degli accessi con privilegi](infoprotect-configure-privileged-access-management.md)|


