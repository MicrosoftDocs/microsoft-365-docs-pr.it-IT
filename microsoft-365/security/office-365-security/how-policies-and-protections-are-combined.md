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
ms.openlocfilehash: 9f2033b1ec066c1f8501ce019b8f8c7f3748fd15
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895336"
---
# <a name="order-and-precedence-of-email-protection-in-office-365"></a>Ordine e precedenza della protezione della posta elettronica in Office 365

Come utente di Office 365, la posta elettronica in ingresso potrebbe essere contrassegnata da più forme di protezione. Ad esempio, i criteri di anti-phishing EOP incorporati disponibili per tutti i clienti di Office 365 e i più robusti criteri di anti-phishing ATP disponibili anche per i clienti di Office 365 Advanced Threat Protection. I messaggi passano anche attraverso analisi di rilevamento multiple per malware, posta indesiderata, phishing e così via. Date tutte queste attività, è possibile che si verifichi una certa confusione sui criteri applicati.

In generale, un criterio applicato a un messaggio viene identificato nell'intestazione **X-Forefront-antispam-report** nella proprietà **Cat (categoria)** . Per ulteriori informazioni, vedere [Intestazioni messaggi della protezione da posta indesiderata](anti-spam-message-headers.md).

Esistono due fattori principali che determinano il criterio applicato a un messaggio:

- **La priorità del tipo di protezione della posta elettronica**: questo ordine non è configurabile ed è descritto nella tabella seguente:

  |||||
  |---|---|---|---|
  |**Priorità **|**Protezione della posta elettronica**|**Categoria**|**Dove gestire**|
  |1 |Malware|CAT: MALW|[Configurazione dei criteri anti-malware in Office 365](configure-anti-malware-policies.md)|
  |2 |Phishing|CAT: PHSH|[Configurazione dei criteri di protezione da posta indesiderata in Office 365](configure-your-spam-filter-policies.md)|
  |3 |Alta probabilità di posta indesiderata|CAT: HSPM|[Configurazione dei criteri di protezione da posta indesiderata in Office 365](configure-your-spam-filter-policies.md)|
  |4 |Spoofing|CAT: SPOOFING|[Impostare i criteri di anti-phishing e l’anti-phishing di Office 365 ATP ](set-up-anti-phishing-policies.md) <Br/><br/> [Ulteriori informazioni su spoof intelligence](learn-about-spoof-intelligence.md)|
  |5 |Posta indesiderata|CAT: SPM|[Configurazione dei criteri di protezione da posta indesiderata in Office 365](configure-your-spam-filter-policies.md)|
  |6 |Invio in blocco|CAT: IN BLOCCO|[Configurazione dei criteri di protezione da posta indesiderata in Office 365](configure-your-spam-filter-policies.md)|
  |7<sup>\*</sup>|Rappresentazione del dominio|DIMP|[Impostare i criteri di anti-phishing e l’anti-phishing di Office 365 ATP ](set-up-anti-phishing-policies.md)|
  |8<sup>\*</sup>|Rappresentazione utente|UIMP|[Impostare i criteri di anti-phishing e l’anti-phishing di Office 365 ATP ](set-up-anti-phishing-policies.md)|
  |

  <sup>\*</sup>Queste funzionalità sono disponibili solo in ATP.

- **Priorità del criterio**: per ogni tipo di protezione (antispam, anti-malware, anti-phishing e così via), è presente un criterio predefinito che si applica a tutti, ma è possibile creare criteri personalizzati che si applicano a utenti specifici. Ogni criterio personalizzato ha un valore di priorità che determina l'ordine in cui vengono applicati i criteri. Il criterio predefinito viene sempre applicato per ultimo.

  Se un utente è definito in più criteri personalizzati, viene applicato solo il criterio con la priorità più alta. Tutti i criteri restanti non vengono valutati per l'utente (incluso il criterio predefinito).

Si consideri, ad esempio, i seguenti criteri di anti-phishing **che si applicano agli stessi utenti**e un messaggio identificato sia come rappresentazione utente sia come spoofing:

  |||||
  |---|---|---|---|
  |**Criteri di protezione da posta indesiderata**|**Priorità **|**Rappresentazione utente (ATP)**|**Anti-spoofing (EOP)**|
  |Criteri A|1 |Attivato|Off|
  |Criterio B|2 |Disattivato|Attivato|
  |

1. Il messaggio viene contrassegnato e trattato come spoofing, in quanto lo spoofing ha una priorità più alta (4) rispetto alla rappresentazione utente (8).
2. Il criterio A viene applicato agli utenti perché ha una priorità più alta rispetto alla priorità B.
3. In base alle impostazioni nel criterio A, non viene intrapresa alcuna azione sul messaggio, in quanto l'antispoofing è disattivata nei criteri.
4. L'elaborazione dei criteri di protezione da posta indesiderata si interrompe, quindi il criterio B non viene mai applicato agli utenti.

Poiché è possibile disporre di più utenti in molti criteri personalizzati dello stesso tipo, prendere in considerazione le seguenti linee guida per la progettazione per i criteri personalizzati:

- Assegnare una priorità più elevata ai criteri che si applicano a un numero limitato di utenti e una priorità più bassa per i criteri che si applicano a un numero elevato di utenti. Tenere presente che il criterio predefinito viene sempre applicato per ultimo.
- Configurare i criteri con priorità più elevata per ottenere impostazioni più rigorose o specializzate rispetto ai criteri di priorità inferiori.
- È consigliabile utilizzare un numero minore di criteri personalizzati (solo utilizzo dei criteri personalizzati per gli utenti che richiedono impostazioni più rigorose o specializzate).
