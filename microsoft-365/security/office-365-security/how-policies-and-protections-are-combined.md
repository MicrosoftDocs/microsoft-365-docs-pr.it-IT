---
title: Ordine e precedenza della protezione della posta elettronica in Office 365
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
description: Descrive l'ordine di applicazione di Office 365 Protections e come il valore di priorità nei criteri di protezione determina il criterio applicato.
ms.openlocfilehash: 6a95c59a5cd629b704753c6c05c9b8069d9240b1
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537414"
---
# <a name="order-and-precedence-of-email-protection-in-office-365"></a>Ordine e precedenza della protezione della posta elettronica in Office 365

In Office 365, la posta elettronica in ingresso viene valutata e pertanto potrebbe essere contrassegnata da più forme di protezione (malware, posta indesiderata, phishing e così via). A causa di tutte queste attività, può essere difficile determinare quali criteri sono stati applicati e in quale ordine.

In generale, un criterio applicato a un messaggio viene identificato nell'intestazione **X-Forefront-antispam-report** nella proprietà **Cat (categoria)** . Per ulteriori informazioni, vedere [Intestazioni messaggi della protezione da posta indesiderata](anti-spam-message-headers.md).

Esistono due fattori principali che determinano il criterio applicato a un messaggio:

- **La priorità del tipo di protezione della posta elettronica**: questo ordine non è configurabile ed è descritto nella tabella seguente:

  |||||
  |---|---|---|---|
  |**Priorità**|**Protezione della posta elettronica**|**Categoria**|**Dove gestire**|
  |1 |Malware|CAT: MALW|[Configurazione dei criteri anti-malware in Office 365](configure-anti-malware-policies.md)|
  |2 |Phishing|CAT: PHSH|[Configurare criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md)|
  |3 |Alta probabilità di posta indesiderata|CAT: HSPM|[Configurare criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md)|
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
  |Criteri A|1 |Attivato|Off|
  |Criterio B|2 |Disattivato|Attivato|
  |

1. Il messaggio viene contrassegnato e trattato come spoofing, in quanto lo spoofing ha una priorità più alta (4) rispetto alla rappresentazione utente (8).
2. Il criterio A viene applicato agli utenti perché ha una priorità più alta rispetto al criterio B.
3. In base alle impostazioni nel criterio A, non viene intrapresa alcuna azione sul messaggio, in quanto l'antispoofing è disattivata nei criteri.
4. L'elaborazione dei criteri si interrompe, quindi il criterio B non viene mai applicato agli utenti.

Poiché è possibile che gli stessi utenti siano inclusi intenzionalmente o involontariamente in più criteri personalizzati dello stesso tipo, utilizzare le linee guida di progettazione seguenti per i criteri personalizzati:

- Assegnare una priorità più elevata ai criteri che si applicano a un numero limitato di utenti e una priorità più bassa per i criteri che si applicano a un numero elevato di utenti. Tenere presente che il criterio predefinito viene sempre applicato per ultimo.
- Configurare i criteri con priorità più elevata per ottenere impostazioni più rigorose o specializzate rispetto ai criteri di priorità inferiori.
- Si consiglia di utilizzare un numero minore di criteri personalizzati (utilizzare solo criteri personalizzati per gli utenti che richiedono impostazioni più rigorose o specializzate).
