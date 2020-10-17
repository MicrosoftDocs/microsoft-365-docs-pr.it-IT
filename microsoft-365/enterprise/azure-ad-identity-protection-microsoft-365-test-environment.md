---
title: Azure AD Identity Protection per l'ambiente di testing di Microsoft 365 per l'organizzazione
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
description: Configurare Azure AD Identity Protection e analizzare gli account correnti nell'ambiente di testing di Microsoft 365 per l'organizzazione.
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487709"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>Azure AD Identity Protection per l'ambiente di testing di Microsoft 365 per l'organizzazione

*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*

È possibile utilizzare la protezione delle identità di Azure Active Directory (Azure AD) per individuare potenziali vulnerabilità che influiscono sulle identità dell'organizzazione, configurare le risposte automatiche e esaminare gli incidenti. In questo articolo viene descritto come utilizzare Azure AD Identity Protection per visualizzare l'analisi degli account dell'ambiente di testing.

La configurazione di Azure AD Identity Protection nell'ambiente di testing di Microsoft 365 per l'organizzazione prevede due fasi:

- [Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: utilizzare Azure AD Identity Protection](#phase-2-use-azure-ad-identity-protection)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Per una mappa visiva su tutti gli articoli della guida del laboratorio di testing di Microsoft 365 for Enterprise, accedere a [microsoft 365 per la guida dello stack del laboratorio di testing dell'organizzazione](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione

Se si desidera testare la protezione delle identità di Azure AD solo con i requisiti minimi, seguire le istruzioni riportate in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera testare Azure AD Identity Protection in un'azienda simulata, seguire le istruzioni riportate in [pass-through authentication](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testing di Azure AD Identity Protection non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory (AD DS). Viene fornito come opzione in modo che sia possibile testare Azure AD Identity Protection e sperimentarlo in un ambiente che rappresenta un'organizzazione tipica.
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Fase 2: utilizzare Azure AD Identity Protection

1. Aprire un'istanza privata del browser e accedere al portale di Azure [https://portal.azure.com](https://portal.azure.com) con l'account di amministratore globale dell'ambiente di testing di Microsoft 365 per l'organizzazione.
2. Nel portale di Azure, digitare **Identity Protection** nella casella di ricerca e quindi selezionare **Azure ad Identity Protection**.
3. Nel Blade **panoramica sulla protezione delle identità** , selezionare ogni rapporto per vedere cosa segnala.
4. In **notifica**selezionare **utenti a rischio avvisi rilevati**.
5. Nel riquadro **utenti a rischio individuati** selezionare **media**.
6. Per **i messaggi di posta elettronica vengono inviati agli utenti seguenti**, selezionare incluso e verificare che l'account di amministratore globale sia **presente** nell'elenco dei membri selezionati.
7. Selezionare **Salva**.

In **Proteggi**selezionare vari criteri di polizia per vedere come configurarli. Se si crea e si attiva un criterio, assicurarsi che non venga bloccato l'accesso per tutti gli utenti oppure che potrebbe non essere possibile accedere. Per evitare questo, escludere gli account utente specifici, ad esempio gli amministratori globali.

Per ulteriori test e sperimentazioni, vedere [simulazione di eventi di rischio](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Roadmap dell'identità](identity-roadmap-microsoft-365.md)

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Microsoft 365 per la documentazione relativa all'organizzazione](https://docs.microsoft.com/microsoft-365-enterprise/)
