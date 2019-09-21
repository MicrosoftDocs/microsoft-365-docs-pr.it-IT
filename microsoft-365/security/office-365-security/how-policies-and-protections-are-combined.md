---
title: Come vengono combinati i criteri e le protezioni quando la posta viene contrassegnata con un contrassegno rosso
description: Quali criteri si applicano e quali azioni eseguire, quando la posta elettronica è contrassegnata da malware, posta indesiderata, posta indesiderata elevata, phishing e bulk da EOP e/o ATP.
keywords: sicurezza, malware, Microsoft 365, M365, Centro sicurezza, ATP, Microsoft Defender ATP, Office 365 ATP, Azure ATP
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 03/26/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 1f1885730d1063a0c36d172f1f9d0e4ac4fb59c7
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083443"
---
# <a name="what-policy-applies-when-multiple-protection-methods-and-detection-scans-run-on-your-email"></a>Quali criteri si applicano quando più metodi di protezione e analisi di rilevamento vengono eseguiti nel messaggio di posta elettronica

Potenzialmente, la posta in arrivo può essere contrassegnata da più forme di protezione (ad esempio, sia EOP *che* ATP) e più analisi di rilevamento (come posta indesiderata *e* phishing). Ciò è possibile perché esistono criteri di anti-phishing ATP per i clienti ATP e criteri anti-phishing di EOP per i clienti di EOP. In questo modo, ad esempio, il messaggio può esplorare più analisi di rilevamento per malware, phishing e rappresentazione utente. Date tutte queste attività, è possibile che si verifichi una certa confusione sui criteri applicati.

In generale, un criterio applicato a un messaggio viene identificato nell'intestazione **X-Forefront-antispam-report** nella proprietà **Cat (categoria)** . Se si dispone di più criteri di anti-phishing, verrà applicato quello con la priorità più alta.

I criteri riportati di seguito si applicano a _tutte le organizzazioni_.

|Priority |Criteri  |Categoria  |Dove gestito |
|---------|---------|---------|---------|
|1     | Malware      | MALW      | Criteri anti-malware   |
|2     | Phishing     | PHSH     | Configurare i criteri di filtro della posta indesiderata     |
|3     | Alta probabilità di posta indesiderata      | HSPM        | Configurare i criteri di filtro della posta indesiderata        |
|4     | Spoofing        | SPOOFING        | Criteri di anti-phishing, spoofing Intelligence        |
|5     | Posta indesiderata         | SPM         | Configurare i criteri di filtro della posta indesiderata         |
|6     | Invio in blocco         | BULK        | Configurare i criteri di filtro della posta indesiderata         |

Inoltre, questi criteri si applicano alle _organizzazioni con ATP_.

|Priority |Criteri  |Categoria  |Dove gestito |
|---------|---------|---------|---------|
|7     | Rappresentazione del dominio         | DIMP         | Impostare i criteri di anti-phishing e l’anti-phishing di Office 365 ATP         |
|8      | Rappresentazione utente        | UIMP         | Impostare i criteri di anti-phishing e l’anti-phishing di Office 365 ATP          |

Ad esempio, se si dispone di due criteri con le rispettive priorità:

|Criteri  |Priority  |Rappresentazione del dominio/utente  |Anti-spoofing  |
|---------|---------|---------|---------|
|A     | 1        | Attivato        |Disattivato         |
|B     | 2        | Disattivato        | Attivato        |

Se un messaggio viene identificato come _rappresentazione utente_ e _spoofing_ (vedere anti-spoofing nella tabella precedente) e lo stesso insieme di utenti a cui si applica il criterio a ha come ambito il criterio B, il messaggio viene contrassegnato e considerato come _spoof_. Tuttavia, non viene applicata alcuna azione perché, sebbene spoofing venga eseguito con una priorità più alta (4) rispetto alla rappresentazione utente (8), l'anti-spoofing è disattivato.

Tenere presente che gli amministratori possono creare un elenco di criteri con priorità (vedere il campo priorità sopra riportato), ma verrà eseguito un solo criterio e verranno applicate le relative azioni. Questo significa che un utente in entrambi i criteri A e B avrà il criterio con priorità più alta (A è #1) e il messaggio non verrà filtrato tramite altri criteri. Se l'opzione anti-spoofiing è disattivata, non verrà eseguita alcuna azione.

Poiché è possibile disporre di numerosi gruppi di utenti in molti criteri, può behoove gli amministratori a considerare l'utilizzo di meno criteri con più funzionalità. È inoltre importante essere certi che tutti gli utenti siano coperti da un criterio globale.

Per applicare altri tipi di criteri di phishing, è necessario modificare le impostazioni a cui si applicano i vari criteri.



