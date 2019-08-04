---
title: Azure AD Identity Protection per l'ambiente di testing Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configurare Azure AD Identity Protection e analizzare gli account correnti nell'ambiente di testing di Microsoft 365 Enterprise.
ms.openlocfilehash: d267bb9dff94acfec46fa1275887f9cade2a7285
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074086"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Azure AD Identity Protection per l'ambiente di testing Microsoft 365 Enterprise

Azure AD Identity Protection consente di rilevare potenziali vulnerabilità che interessano le identità dell'organizzazione, la configurazione delle risposte automatiche e l'analisi degli incidenti. In questo articolo viene descritto come abilitare Azure AD Identity Protection e visualizzare l'analisi degli account dell'ambiente di testing.

Sono disponibili due fasi per la configurazione di Azure AD Identity Protection nell'ambiente di testing Microsoft 365 Enterprise:

1. Creare l'ambiente di testing di Microsoft 365 Enterprise.
2. Abilitazione e utilizzo di Azure AD Identity Protection.

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing di Microsoft 365 Enterprise

Se si desidera semplicemente testare Azure AD Identity Protection in modo leggero con i requisiti minimi, seguire le istruzioni in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera testare Azure AD Identity Protection in un'azienda simulata, seguire le istruzioni riportate in [pass-through authentication](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testing di Azure AD Identity Protection non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS). Viene fornito come opzione in modo che sia possibile testare Azure AD Identity Protection e sperimentarlo in un ambiente che rappresenta un'organizzazione tipica. 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a>Fase 2: abilitare e utilizzare Azure AD Identity Protection

1. Aprire un'istanza privata del browser e accedere al portale di Azure [https://portal.azure.com](https://portal.azure.com) con l'account di amministratore globale dell'ambiente di testing di Microsoft 365 Enterprise.
2. Nel portale di Azure, fare clic su **tutti i servizi > Marketplace**.
3. Digitare **Azure ad Identity Protection** e quindi fare clic su di esso.
4. Nella barra **iniziale** , fare clic su **onboard** in **Impostazioni**, fare clic su **Aggiungi a Dashboard**, quindi fare clic su **Crea**.
5. Nel portale di Azure, fare clic su **Azure ad Identity Protection** nel dashboard. 

   Si dovrebbe vedere un blade di **Azure ad Identity Protection-Overview** con un dashboard. In **vulnerabilità**, si noti che ha determinato il numero di account utente senza registrazione di autenticazione a più fattori. Questo numero può variare in base alle precedenti guide di laboratorio di testing di Microsoft 365 Enterprise eseguite.

6. Fare clic sulle categorie per **** verificare se sono presenti utenti o eventi che sono stati rilevati.

Per ulteriori test e sperimentazioni, vedere [simulazione di eventi di rischio](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).

Per informazioni e collegamenti per la distribuzione di Azure AD Identity Protection in produzione, vedere il passaggio di compromesso relativo alla protezione da [credenziali](identity-multi-factor-authentication.md#identity-ident-prot) nella fase Identity.

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Fase 2: identità](identity-infrastructure.md)

[Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md).

[Documentazione di Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
