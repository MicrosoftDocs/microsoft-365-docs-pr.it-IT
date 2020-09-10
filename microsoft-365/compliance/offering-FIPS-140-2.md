---
title: Pubblicazione FIPS (Federal Information Processing Standard) 140-2
description: Microsoft certifica che i suoi moduli crittografici sono conformi allo standard di elaborazione delle informazioni federali degli Stati Uniti.
keywords: Microsoft 365, conformità, offerte
localization_priority: None
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: f193e1846b957a26475cdfc48add6679a951841f
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2020
ms.locfileid: "47415850"
---
# <a name="federal-information-processing-standard-fips-publication-140-2"></a>Pubblicazione FIPS (Federal Information Processing Standard) 140-2

## <a name="fips-140-2-standard-overview"></a>Standard FIPS 140-2 Overview

La pubblicazione FIPS (Federal Information Processing Standard) 140-2 è uno standard governativo statunitense che definisce i requisiti minimi di sicurezza per i moduli di crittografia nei prodotti di Information Technology, come definito nella sezione 5131 dell'Information Technology Management riforme Act del 1996.

Il [programma di convalida del modulo di crittografia](https://csrc.nist.gov/Projects/cryptographic-module-validation-program) (CMVP), uno sforzo congiunto del National Institute of Standards and Technology (NIST) e del Canadian Centre for Cyber Security (CCCS), consente di convalidare i moduli di crittografia per i *requisiti di sicurezza per i moduli di crittografia* standard (ad esempio, FIPS 140-2) e relativi standard di crittografia FIPS. I requisiti di sicurezza FIPS 140-2 coprono 11 aree correlate alla progettazione e all'implementazione di un modulo di crittografia. Il laboratorio Information Technology di NIST gestisce un programma correlato che convaliderà gli algoritmi di crittografia approvato FIPS nel modulo.

## <a name="microsofts-approach-to-fips-140-2-validation"></a>Approccio di Microsoft alla convalida FIPS 140-2

Microsoft mantiene un impegno attivo per soddisfare i requisiti di 140-2, dopo aver convalidato i moduli di crittografia fin dall'inizio dello standard nel 2001. Microsoft convalida i moduli di crittografia nell'ambito del programma CMVP (National Institute of Standards and Technology) (NIST) [Cryptographic Module Validation Program](https://csrc.nist.gov/Projects/cryptographic-module-validation-program) . Più prodotti Microsoft, tra cui numerosi servizi cloud, utilizzano questi moduli di crittografia.

Per informazioni tecniche sui moduli di crittografia di Microsoft Windows, sui criteri di sicurezza per ogni modulo e sul catalogo dei dettagli del certificato di CMVP, vedere il [contenuto di Windows e Windows Server FIPS 140-2](https://aka.ms/AA6ehud).

## <a name="microsoft-in-scope-cloud-services"></a>Servizi cloud Microsoft inclusi nell'ambito

Mentre l'attuale guida all'implementazione di CMVP FIPS 140-2 preclude una convalida FIPS 140-2 per un servizio cloud stesso; i provider di servizi cloud possono scegliere di ottenere e gestire moduli di crittografia FIPS 140 convalidati per gli elementi di elaborazione che compongono il servizio cloud. Tra gli altri servizi Microsoft online che includono componenti, che sono stati convalidati da FIPS 140-2, sono inclusi i seguenti:

- [Azure e Azure per enti pubblici](https://docs.microsoft.com/azure/azure-government/documentation-government-plan-security)
- [Government Dynamics 365 e Dynamics 365](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-microsoft-dynamics-365)
- [Office 365, Office 365 U.S. Government e Office 365 U.S. Government Defense](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-risks-and-protections)

## <a name="frequently-asked-questions"></a>Domande frequenti

**Qual è la differenza tra "FIPS 140 convalidated" e "FIPS 140 compliant"?**

"FIPS 140 convalidated" indica che il modulo di crittografia o un prodotto che incorpora il modulo è stato convalidato ("certificato") da CMVP per soddisfare i requisiti di FIPS 140-2. "FIPS 140 compliant" è un termine di settore per i prodotti IT che si basano sui prodotti convalidati FIPS 140 per la funzionalità di crittografia.

**Quando Microsoft intraprende una convalida FIPS 140?**

La cadenza per l'avvio di una convalida del modulo si allinea con gli aggiornamenti delle funzionalità di Windows 10 e Windows Server. Man mano che l'industria del software si è evoluta, i sistemi operativi vengono rilasciati più frequentemente, con aggiornamenti software mensili. Microsoft accetta la convalida per i rilasci delle caratteristiche, ma tra i rilasci, cerca di minimizzare le modifiche apportate ai moduli di crittografia.

**Quali computer sono inclusi in una convalida FIPS 140?**

Microsoft convalida i moduli di crittografia su un campione rappresentativo di configurazioni hardware che eseguono Windows 10 e Windows Server. È prassi comune accettare questo tipo di convalida FIPS 140-2 quando un ambiente utilizza l'hardware, analogo agli esempi utilizzati per il processo di convalida.

**Nel sito Web NIST sono presenti numerosi moduli. Come si fa a sapere quale si applica alla mia agenzia?**

Se è necessario utilizzare i moduli di crittografia convalidati tramite FIPS 140-2, è necessario verificare che la versione utilizzata venga visualizzata nell'elenco di convalida. CMVP e Microsoft mantengono un elenco dei moduli di crittografia convalidati, organizzati per il rilascio del prodotto, insieme alle istruzioni per identificare quali moduli sono installati in un sistema Windows. Per ulteriori informazioni sulla configurazione dei sistemi per essere conformi, vedere il [contenuto di Windows e Windows Server FIPS 140-2](https://aka.ms/AA6ehud).

**Che cosa significa "quando viene utilizzato in modalità FIPS" in un certificato?**

Questo avvertimento informa il lettore che deve essere seguita la configurazione e le regole di sicurezza necessarie per utilizzare il modulo di crittografia in modo coerente con i criteri di sicurezza FIPS 140-2. Ogni modulo dispone di un proprio criterio di sicurezza, ovvero una specifica precisa delle regole di sicurezza in base alle quali opererà, e utilizza algoritmi di crittografia approvati, la gestione delle chiavi di crittografia e le tecniche di autenticazione. Le regole di sicurezza sono definite nei criteri di sicurezza per ogni modulo. Per ulteriori informazioni, inclusi i collegamenti ai criteri di sicurezza per ogni modulo convalidato tramite CMVP, vedere il [contenuto di Windows e Windows Server FIPS 140-2](https://aka.ms/AA6ehud).

**FedRAMP richiede la convalida FIPS 140-2?**

Sì, il programma di gestione delle autorizzazioni e dei rischi federali (FedRAMP) si basa sulle linee di base dei controlli definite dalla [revisione 4 del NIST SP 800-53](https://nvd.nist.gov/800-53/Rev4/), inclusa la [protezione crittografica SC-13](https://nvd.nist.gov/800-53/Rev4/control/SC-13) che impone l'utilizzo della crittografia convalidata FIPS o della crittografia approvata dall'NSA.

**In che modo Microsoft Azure supporta FIPS 140-2?**

Azure è costituito da una combinazione di hardware, sistemi operativi disponibili commercialmente (Linux e Windows) e versione di Windows specifica di Azure. Tramite il ciclo di vita di [sviluppo della sicurezza](https://www.microsoft.com/securityengineering/sdl/) Microsoft (SDL), tutti i servizi di Azure utilizzano gli algoritmi FIPS 140-2 approvati per la protezione dei dati, poiché il sistema operativo utilizza gli algoritmi approvato da FIPS 140-2 durante l'utilizzo in un Cloud Hyper-scale.

**È possibile utilizzare la conformità di Microsoft alla FIPS 140-2 nel processo di certificazione dell'Agenzia?**

Per garantire la conformità con FIPS 140-2, è necessario configurare il sistema in modo che venga eseguito in una modalità di funzionamento approvato da FIPS, in cui viene indicato che un modulo di crittografia utilizza solo algoritmi approvati da FIPS. Per ulteriori informazioni sulla configurazione dei sistemi per essere conformi, vedere il [contenuto di Windows e Windows Server FIPS 140-2](https://aka.ms/AA6ehud).

**Qual è la relazione tra FIPS 140-2 e criteri comuni?**

Si tratta di due standard di sicurezza distinti con finalità diverse, ma complementari. FIPS 140-2 è stato progettato appositamente per la convalida dei moduli di crittografia software e hardware, mentre i criteri comuni sono progettati per valutare le funzioni di sicurezza nei prodotti software e hardware IT. Le valutazioni sui criteri comuni spesso si basano sulle convalide di FIPS 140-2 per garantire che le funzionalità di crittografia di base siano implementate correttamente.

## <a name="resources"></a>Risorse

- [Requisiti di sicurezza di FIPS Pub 140-2 per i moduli di crittografia](https://csrc.nist.gov/publications/fips/fips140-2/fips1402.pdf)
- [Programma di convalida del modulo di crittografia NIST](https://csrc.nist.gov/groups/STM/cmvp/index.html)
- [Windows, Windows Server e FIPS 140-2](https://docs.microsoft.com/windows/security/threat-protection/fips-140-validation)
- [Conformità nel Centro protezione Microsoft](https://www.microsoft.com/trust-center/compliance/compliance-overview)
