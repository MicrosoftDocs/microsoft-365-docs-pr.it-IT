---
title: Ordine e precedenza della protezione della posta elettronica
keywords: sicurezza, malware, Microsoft 365, M365, centro sicurezza, ATP, Microsoft Defender ATP, Office 365 ATP, Azure ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni sull'ordine delle applicazioni di protezione in Exchange Online Protection (EOP) e su come il valore di priorità nei criteri di protezione determina quale criterio viene applicato.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b2a72420340993c027ec99820dcd3edddab1a304
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205365"
---
# <a name="order-and-precedence-of-email-protection"></a>Ordine e precedenza della protezione della posta elettronica

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o in organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, la posta elettronica in ingresso può essere contrassegnata da più forme di protezione. Ad esempio, i criteri anti-phishing incorporati in EOP disponibili per tutti i clienti di Microsoft 365 e i criteri anti-phishing più affidabili disponibili per i clienti di Microsoft Defender per Office 365. I messaggi passano anche attraverso più analisi di rilevamento alla ricerca di malware, posta indesiderata, phishing e così via. Data l'attività, può verificarsi una certa confusione sul criterio applicato.

In generale, un criterio applicato a un messaggio viene identificato nell'intestazione **X-Forefront-Antispam-Report** nella **proprietà CAT (Category).** Per ulteriori informazioni, vedere [Intestazioni messaggi della protezione da posta indesiderata](anti-spam-message-headers.md).

Esistono due fattori principali che determinano quale criterio viene applicato a un messaggio:

- **La priorità del tipo di protezione della** posta elettronica : Questo ordine non è configurabile ed è descritto nella tabella seguente:

  ****

  |Priority|Protezione della posta elettronica|Categoria|Dove gestire|
  |---|---|---|---|
  |1|Malware|CAT:MALW|[Configurare i criteri antimalware in EOP](configure-anti-malware-policies.md)|
  |2 |Phishing|CAT:PHSH|[Configurare criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md)|
  |3 |Alta probabilità di posta indesiderata|CAT:HSPM|[Configurare criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md)|
  |4 |Spoofing|CAT:SPOOF|[Configurare spoof intelligence in EOP](learn-about-spoof-intelligence.md)|
  |5<sup>\*</sup>|Rappresentazione utente (utenti protetti)|UIMP|[Configurare i criteri anti-phishing in Microsoft Defender per Office 365](configure-atp-anti-phishing-policies.md)|
  |6<sup>\*</sup>|Rappresentazione del dominio (domini protetti)|DIMP|[Configurare i criteri anti-phishing in Microsoft Defender per Office 365](configure-atp-anti-phishing-policies.md)|
  |7 |Posta indesiderata|CAT:SPM|[Configurare criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md)|
  |8 |Invio in blocco|CAT:BULK|[Configurare criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md)|
  |

  <sup>\*</sup> Queste funzionalità sono disponibili solo nei criteri anti-phishing in Microsoft Defender per Office 365.

- La **priorità** del criterio : per ogni tipo di protezione (protezione da posta indesiderata, antimalware, anti-phishing e così via), esiste un criterio predefinito che si applica a tutti gli utenti, ma è possibile creare criteri personalizzati che si applicano a utenti specifici. Ogni criterio personalizzato ha un valore di priorità che determina l'ordine in cui vengono applicati i criteri. Il criterio predefinito viene sempre applicato per ultimo.

  Se un utente è definito in più criteri dello stesso tipo, viene applicato solo il criterio con la priorità più alta. Gli eventuali criteri rimanenti di quel tipo non vengono valutati per l'utente (incluso il criterio predefinito).

Si considerino ad esempio i seguenti criteri anti-phishing in Microsoft Defender per Office 365 che si applicano agli stessi utenti e un messaggio identificato sia come rappresentazione utente che come spoofing:

  ****

  |Nome criterio|Priority|Rappresentazione utente|Anti-spoofing|
  |---|---|---|---|
  |Criterio A|1|Attivato|Disattivato|
  |Criterio B|2 |Disattivato|Attivato|
  |

1. Il messaggio viene contrassegnato e considerato spoofing, perché lo spoofing ha una priorità più alta (4) rispetto alla rappresentazione dell'utente (5).
2. Il criterio A viene applicato agli utenti perché ha una priorità più alta rispetto al criterio B.
3. In base alle impostazioni del criterio A, non viene eseguita alcuna azione sul messaggio, perché nel criterio è disattivato l'anti-spoofing.
4. L'elaborazione dei criteri si interrompe, quindi il criterio B non viene mai applicato agli utenti.

Poiché è possibile che gli stessi utenti siano inclusi intenzionalmente o involontariamente in più criteri personalizzati dello stesso tipo, utilizzare le linee guida di progettazione seguenti per i criteri personalizzati:

- Assegnare una priorità più alta ai criteri che si applicano a un numero limitato di utenti e una priorità più bassa ai criteri che si applicano a un numero elevato di utenti. Tenere presente che il criterio predefinito viene sempre applicato per ultimo.
- Configurare i criteri con priorità più alta in modo da avere impostazioni più rigide o più specializzate rispetto ai criteri con priorità inferiore.
- Prendere in considerazione l'uso di un numero minore di criteri personalizzati (utilizzare solo criteri personalizzati per gli utenti che richiedono impostazioni più rigide o più specializzate).
