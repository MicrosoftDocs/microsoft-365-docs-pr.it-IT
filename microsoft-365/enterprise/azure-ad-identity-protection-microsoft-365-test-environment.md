---
title: Ambiente di testing di Azure Active Directory Identity protezione per la propria azienda 365 Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Configurare la protezione dell'identità di Azure Active Directory e analizzare gli account corrente nell'ambiente di testing Microsoft 365 Enterprise.
ms.openlocfilehash: 165667ad2122839336ef0790ab5661cff53ca32b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868363"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Ambiente di testing di Azure Active Directory Identity protezione per la propria azienda 365 Microsoft

Protezione Azure Active Directory Identity consente di rilevare potenziale vulnerabilità che interessano le identità dell'organizzazione, configurare risposte automatiche e analizzare i problemi. In questo articolo viene descritto come abilitare la protezione con Azure Active Directory Identity e visualizzare l'analisi dei test environment gli account di posta.

Esistono due fasi per la configurazione della protezione di identità di Azure Active Directory nell'ambiente di test Microsoft 365 aziendale:

1. Creare l'ambiente di test Microsoft 365 Enterprise.
2. Abilitare e utilizzare la protezione dell'identità di Azure Active Directory.

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Preparare l'ambiente di testing Microsoft 365 Enterprise

Se si desidera testare la protezione dell'identità di Azure Active Directory in un modo semplice con i requisiti minimi, seguire le istruzioni di [configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera testare la protezione dell'identità di Azure Active Directory in un'azienda simulata, seguire le istruzioni [nell'autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testare la protezione dell'identità di Azure Active Directory non richiede l'ambiente di testing simulato enterprise, che include una rete intranet simulata connessione a Internet e la sincronizzazione delle directory per una foresta Windows Server Active Directory. Viene fornito qui come un'opzione in modo da poter testare la protezione dell'identità di Azure Active Directory e sperimentare in un ambiente che rappresenta una tipica organizzazione. 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a>Fase 2: Abilitare e utilizzare la protezione dell'identità di Azure Active Directory

1. Aprire un'istanza privata del browser e accedere al portale di Azure al [https://portal.azure.com](https://portal.azure.com) con l'account amministratore globale dell'ambiente di testing Microsoft 365 Enterprise.
2. Nel portale di Azure, fare clic su **tutti i servizi > Marketplace**.
3. Digitare **la protezione dell'identità di Azure Active Directory** e quindi fare clic su.
4. Su blade **Introduzione** fare clic su **Onboard** in **Impostazioni**, fare clic su **Aggiungi a dashboard**e quindi fare clic su **Crea**.
5. Nel portale di Azure, fare clic su **protezione dell'identità di Azure Active Directory** nel dashboard di. 

   Verrà visualizzato un blade **Azure Active Directory Identity Protection-Panoramica** con un dashboard. Si noti che determinato il numero degli account utente senza la registrazione di autenticazione a più fattori in **vulnerabilità**. Questo numero varia in base ai precedenti Microsoft 365 Enterprise Test Lab guide che deve essere stata eseguita.

6. Fare clic su attraverso le categorie per **indagare** vedere se sono presenti utenti o gli eventi che sono stati rilevati.

Per altre attività di testing e la sperimentazione, vedere [Simulating rischio eventi](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).

Vedere il passaggio di [protezione contro i credenziali compromettere](identity-azure-ad-identity-protection.md) nella fase di identità per informazioni e collegamenti per distribuire la protezione di identità di Azure Active Directory nell'ambiente di produzione.

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Fase 2: identità](identity-infrastructure.md)

[Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentazione di Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
