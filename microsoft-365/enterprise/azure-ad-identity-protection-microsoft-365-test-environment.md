---
title: Azure AD Identity Protection per l'ambiente di testing Microsoft 365 Enterprise
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configurare Azure AD Identity Protection e analizzare gli account correnti nell'ambiente di testing di Microsoft 365 Enterprise.
ms.openlocfilehash: 376fc838191314e93ae37accb7fc5066456499fb
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597163"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Azure AD Identity Protection per l'ambiente di testing Microsoft 365 Enterprise

*Questa guida al lab di test può essere usata solo per ambienti di testing di Microsoft 365 Enterprise.*

Azure Active Directory (Azure AD) Identity Protection consente di rilevare potenziali vulnerabilità che interessano le identità dell'organizzazione, configurare le risposte automatiche e indagare gli incidenti. In questo articolo viene descritto come utilizzare Azure AD Identity Protection per visualizzare l'analisi degli account dell'ambiente di testing.

Sono disponibili due fasi per la configurazione di Azure AD Identity Protection nell'ambiente di testing Microsoft 365 Enterprise:

1. Creare l'ambiente di testing di Microsoft 365 Enterprise.
2. Utilizzo di Azure AD Identity Protection.

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Fare clic [qui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Creare l'ambiente di testing di Microsoft 365 Enterprise

Se si desidera semplicemente testare Azure AD Identity Protection in modo leggero con i requisiti minimi, seguire le istruzioni in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera testare Azure AD Identity Protection in un'azienda simulata, seguire le istruzioni riportate in [pass-through authentication](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testing di Azure AD Identity Protection non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS). Viene fornito come opzione in modo che sia possibile testare Azure AD Identity Protection e sperimentarlo in un ambiente che rappresenta un'organizzazione tipica. 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Fase 2: utilizzare Azure AD Identity Protection

1. Aprire un'istanza privata del browser e accedere al portale di Azure [https://portal.azure.com](https://portal.azure.com) con l'account di amministratore globale dell'ambiente di testing di Microsoft 365 Enterprise.
2. Nel portale di Azure, digitare **Identity Protection** nella casella di ricerca e quindi fare clic su **Azure ad Identity Protection**.
3. Nel Blade **panoramica sulla protezione delle identità** , fare clic su ciascuno dei rapporti per vedere cosa stanno segnalando.
4. In **notifica**fare clic su **utenti a rischio avvisi rilevati**.
5. Nel riquadro **utenti a rischio individuati** selezionare **media**.
6. Per **i messaggi di posta elettronica vengono inviati agli utenti seguenti**, fare clic su **incluso** e verificare che l'account di amministratore globale sia presente nell'elenco dei membri selezionati.
7. Fare clic su **Salva**.

Fare clic sui diversi criteri in **Protect** per vedere come configurarli. Se si crea e si attiva un criterio, assicurarsi che non sia bloccato l'accesso per un ambito troppo ampio di condizioni oppure che potrebbe non essere possibile accedere, anche come amministratore globale.

Per ulteriori test e sperimentazioni, vedere [simulazione di eventi di rischio](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).

Per informazioni e collegamenti per la distribuzione di Azure AD Identity Protection in produzione, vedere il passaggio di compromesso relativo alla protezione da [credenziali](identity-secure-user-sign-ins.md#identity-ident-prot) nella fase Identity.

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Fase 2: identità](identity-infrastructure.md)

[Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md).

[Documentazione di Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
