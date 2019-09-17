---
title: 'Passaggio 4: Configurare Windows Information Protection'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Informazioni e distribuzione di Windows Information Protection in Microsoft 365.
ms.openlocfilehash: a89d61367d3e07cabff0576f16fa359a06dc1ecc
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981817"
---
# <a name="step-4-configure-windows-information-protection"></a>Passaggio 4: Configurare Windows Information Protection

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Con più dispositivi personali usati per lavoro, aumenta il rischio per le applicazioni e i dispositivi di una perdita di dati aziendali privati. Ad esempio, un dipendente invia inavvertitamente l'immagine di un piano di marketing per un prodotto futuro attualmente in un sito di social networking o salva un file contenente informazioni strettamente riservate nel proprio sistema pubblico di archiviazione cloud. 

Windows Information Protection (WIP) consente di evitare questi tipi di perdita di dati nei dispositivi Windows 10. Per ulteriori informazioni, vedere [Proteggere i dati dell'organizzazione con WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).

In Microsoft 365 Enterprise, WIP è una combinazione di Windows 10 Enterprise e Microsoft Intune, incluso nell'abbonamento. 

Per distribuire WIP nell'organizzazione con Microsoft 365 Enterprise:

1. Registrare i dispositivi Windows Intune. È necessario farlo nella [Fase 5: gestione di dispositivi mobili](mobility-infrastructure.md).
2. Creare un [Criterio di Intune per WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).
  - Verificare che l'elenco di applicazioni protette sia stato compilato.
  - Scegliere il livello di protezione del WIP.

Si può anche usare WIP con [System Center Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm). 

Vedere [Procedure consigliate per WIP]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) per ulteriori informazioni.

Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step4) che corrispondono a questo passaggio.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[Configurare i criteri di prevenzione della perdita dei dati di Office 365](infoprotect-data-loss-prevention.md)|


