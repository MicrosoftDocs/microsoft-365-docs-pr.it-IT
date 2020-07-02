---
title: 'Passaggio 4: Configurare Windows Information Protection'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Informazioni e distribuzione di Windows Information Protection in Microsoft 365.
ms.openlocfilehash: c7b76ef28d41810d6e9e45e98adb7a94cf8ae2f4
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005723"
---
# <a name="step-4-configure-windows-information-protection"></a>Passaggio 4: Configurare Windows Information Protection

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![Fase 6: protezione delle informazioni](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Con più dispositivi personali usati per lavoro, aumenta il rischio per le applicazioni e i dispositivi di una perdita di dati aziendali privati. Ad esempio, un dipendente invia inavvertitamente l'immagine di un piano di marketing per un prodotto futuro attualmente in un sito di social networking o salva un file contenente informazioni strettamente riservate nel proprio sistema pubblico di archiviazione cloud. 

Windows Information Protection (WIP) consente di evitare questi tipi di perdita di dati nei dispositivi Windows 10. Per ulteriori informazioni, vedere [Proteggere i dati dell'organizzazione con WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).

In Microsoft 365 Enterprise, WIP è una combinazione di Windows 10 Enterprise e Microsoft Intune, incluso nell'abbonamento. 

Per distribuire WIP nell'organizzazione con Microsoft 365 Enterprise:

1. Registrare i dispositivi Windows Intune. È necessario farlo nella [Fase 5: gestione di dispositivi mobili](mobility-infrastructure.md).

2. Creare un [Criterio di Intune per WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).

   -    Verificare che l'elenco di applicazioni protette sia stato compilato.
  
   - Scegliere il livello di protezione del WIP.

È possibile usare WIP anche con [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-configmgr). 

Vedere [Procedure consigliate per WIP]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) per ulteriori informazioni.

Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step4) che corrispondono a questo passaggio.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![Passaggio 5](../media/stepnumbers/Step5.png)|[Configurare la prevenzione della perdita dei dati](infoprotect-data-loss-prevention.md)|


