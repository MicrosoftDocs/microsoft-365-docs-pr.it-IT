---
title: Ordine e precedenza della protezione della posta elettronica
keywords: sicurezza, malware, Microsoft 365, M365, Centro sicurezza, ATP, Microsoft Defender ATP, Office 365 ATP, Azure ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Informazioni sull'ordine di applicazione di Office 365 Protections e sul modo in cui il valore di priorità nei criteri di protezione determina il criterio applicato.
ms.openlocfilehash: 856b3bc39cd971e605cd9f1c0f31554a853c1b67
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036717"
---
# <a name="order-and-precedence-of-email-protection"></a>Ordine e precedenza della protezione della posta elettronica

Come utente di Microsoft 365, la posta elettronica in ingresso può essere contrassegnata da più forme di protezione. Ad esempio, i criteri di anti-phishing EOP incorporati disponibili per tutti i clienti di Microsoft 365 e i più robusti criteri di anti-phishing ATP disponibili anche per i clienti di Office 365 Advanced Threat Protection. I messaggi passano anche attraverso analisi di rilevamento multiple per malware, posta indesiderata, phishing e così via. Date tutte queste attività, è possibile che si verifichi una certa confusione sui criteri applicati.

In generale, un criterio applicato a un messaggio viene identificato nell'intestazione **X-Forefront-antispam-report** nella proprietà **Cat (categoria)** . Per ulteriori informazioni, vedere [Intestazioni messaggi della protezione da posta indesiderata](anti-spam-message-headers.md).

Esistono due fattori principali che determinano il criterio applicato a un messaggio:

- **La priorità del tipo di protezione della posta elettronica**: questo ordine non è configurabile ed è descritto nella tabella seguente:

  |||||
  |---|---|---|---|
  |**Priorità**|**Protezione della posta elettronica**|**Categoria**|**Dove gestire**|
  |1|Malware|CAT: MALW|[Configurazione dei criteri anti-malware in Office 365](configure-anti-malware-policies.md)|
  |2|Phishing|CAT: PHSH|[Configurare criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md)|
  |3|Alta probabilità di posta indesiderata|CAT: HSPM|[Configurare criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md)|
  |4 |Spoofing|CAT: SPOOFING|[Configurare l'intelligence di spoofing in Office 365](learn-about-spoof-intelligence.md)|
  |5 |Posta indesiderata|CAT: SPM|[Configurare criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md)|
  |6 |Invio in blocco|CAT: IN BLOCCO|[Configurare criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md)|
  |7<sup>\*</sup>|Rappresentazione del dominio (utenti protetti)|DIMP|[Configurazione dei criteri di anti-phishing ATP in Office 365](configure-atp-anti-phishing-policies.md)|
  |8<sup>\*</sup>|Rappresentazione utente (domini protetti)|UIMP|[Configurazione dei criteri di anti-phishing ATP in Office 365](configure-atp-anti-phishing-policies.md)|
  |

  <sup>\*</sup>Queste funzionalità sono disponibili solo nei criteri di anti-phishing ATP.

- **Priorità del criterio**: per ogni tipo di protezione (antispam, anti-malware, anti-phishing e così via), è presente un criterio predefinito che si applica a tutti, ma spesso è possibile creare criteri personalizzati che si applicano a utenti specifici. Ogni criterio personalizzato ha un valore di priorità che determina l'ordine in cui vengono applicati i criteri. Il criterio predefinito viene sempre applicato per ultimo.

  Se un utente è definito in più criteri dello stesso tipo, viene applicato solo il criterio con la priorità più alta. Tutti i criteri restanti di quel tipo non vengono valutati per l'utente (incluso il criterio predefinito).

Si consideri, ad esempio, i seguenti criteri di anti-phishing ATP **che si applicano agli stessi utenti**e un messaggio identificato come rappresentazione e spoofing degli utenti:

  |||||
  |---|---|---|---|
  |**Criteri di anti-phishing ATP**|**Priorità**|**Rappresentazione utente**|**Anti-spoofing**|
  |Criteri A|1|Attivato|Off|
  |Criterio B|2|Disattivato|Attivato|
  |

1. Il messaggio viene contrassegnato e trattato come spoofing, in quanto lo spoofing ha una priorità più alta (4) rispetto alla rappresentazione utente (8).
2. Il criterio A viene applicato agli utenti perché ha una priorità più alta rispetto al criterio B.
3. In base alle impostazioni nel criterio A, non viene intrapresa alcuna azione sul messaggio, in quanto l'antispoofing è disattivata nei criteri.
4. L'elaborazione dei criteri si interrompe, quindi il criterio B non viene mai applicato agli utenti.

Poiché è possibile che gli stessi utenti siano inclusi intenzionalmente o involontariamente in più criteri personalizzati dello stesso tipo, utilizzare le linee guida di progettazione seguenti per i criteri personalizzati:

- Assegnare una priorità più elevata ai criteri che si applicano a un numero limitato di utenti e una priorità più bassa per i criteri che si applicano a un numero elevato di utenti. Tenere presente che il criterio predefinito viene sempre applicato per ultimo.
- Configurare i criteri con priorità più elevata per ottenere impostazioni più rigorose o specializzate rispetto ai criteri di priorità inferiori.
- Si consiglia di utilizzare un numero minore di criteri personalizzati (utilizzare solo criteri personalizzati per gli utenti che richiedono impostazioni più rigorose o specializzate).
