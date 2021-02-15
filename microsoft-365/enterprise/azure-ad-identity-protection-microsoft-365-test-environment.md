---
title: Azure AD Identity Protection per l'ambiente di testing di Microsoft 365 per le aziende
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
description: Configurare Azure AD Identity Protection e analizzare gli account correnti nell'ambiente di testing di Microsoft 365 per le aziende.
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487709"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>Azure AD Identity Protection per l'ambiente di testing di Microsoft 365 per le aziende

*Questa guida del laboratorio di testing può essere usata solo per gli ambienti di testing di Microsoft 365 per le aziende.*

È possibile utilizzare Azure Active Directory (Azure AD) Identity Protection per rilevare potenziali vulnerabilità che influiscono sulle identità dell'organizzazione, configurare risposte automatizzate e analizzare gli eventi imprevisti. Questo articolo descrive come usare Azure AD Identity Protection per visualizzare l'analisi degli account dell'ambiente di testing.

La configurazione di Azure AD Identity Protection nell'ambiente di testing di Microsoft 365 per le aziende prevede due fasi:

- [Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: usare Azure AD Identity Protection](#phase-2-use-azure-ad-identity-protection)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Per una mappa visiva di tutti gli articoli della guida del lab di test di Microsoft 365 per le aziende, passare a [Microsoft 365 per enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende

Se si desidera testare Azure AD Identity Protection solo in modo leggero con i requisiti minimi, seguire le istruzioni in [Configurazione di base lightweight.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Se si desidera testare Azure AD Identity Protection in un'azienda simulata, seguire le istruzioni in [Autenticazione pass-through.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Il test di Azure AD Identity Protection non richiede l'ambiente di testing aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di Active Directory Domain Services (AD DS). Qui viene fornito come opzione in modo da poter testare Azure AD Identity Protection e sperimentarlo in un ambiente che rappresenta un'organizzazione tipica.
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Fase 2: usare Azure AD Identity Protection

1. Aprire un'istanza privata del browser e accedere al portale di Azure con l'account amministratore globale dell'ambiente di testing di [https://portal.azure.com](https://portal.azure.com) Microsoft 365 per le aziende.
2. Nel portale di Azure, digitare **Identity Protection** nella casella di ricerca, quindi selezionare Azure AD **Identity Protection.**
3. Nel pannello **Identity Protection - Overview** selezionare ogni report per visualizzare i report.
4. In **Notifica** selezionare **Utenti a rischio avvisi rilevati.**
5. Nel riquadro **Degli avvisi rilevati dagli** utenti a rischio selezionare **Medio.**
6. Per **i messaggi di posta elettronica vengono inviati agli** utenti seguenti, selezionare Incluso e verificare che l'account amministratore globale sia incluso nell'elenco dei membri selezionati. 
7. Selezionare **Salva**.

In **Proteggi** selezionare vari criteri per vedere come configurarli. Se si crea e si attiva un criterio, assicurarsi che non blocchi l'accesso per tutti gli utenti oppure che non sia possibile accedere. Per evitare questo problema, escludere account utente specifici, ad esempio gli amministratori globali.

Per ulteriori test e sperimentazioni, vedere [Simulazione di eventi di rischio.](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Guida di orientamento all'identità](identity-roadmap-microsoft-365.md)

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Documentazione di Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
