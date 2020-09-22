---
title: Procedura dettagliata-spoofing Intelligence Insight
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Gli amministratori possono sapere come funziona lo spoofing Intelligence Insight, compreso il modo in cui determinare rapidamente quali mittenti stanno inviando legalmente messaggi di posta elettronica non autenticati.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6fc934491606a53ebfb4bae4f46ab9e1ee93467b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198572"
---
# <a name="walkthrough---atp-spoof-intelligence-insight-in-microsoft-365"></a>Procedura dettagliata: analisi di intelligence su spoofing di ATP in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365 organizzazioni con Advanced Threat Protection (ATP), è possibile utilizzare lo spoofing Intelligence Insight per determinare rapidamente quali mittenti stanno inviando legalmente messaggi di posta elettronica non autenticati. Consentendo loro di inviare messaggi falsificati, è possibile ridurre il rischio di eventuali falsi positivi per gli utenti. È inoltre possibile utilizzare lo spoofing Intelligence Insight per monitorare e gestire le coppie di domini consentite per fornire un ulteriore livello di sicurezza e impedire l'arrivo di messaggi non sicuri nell'organizzazione.

Se si è nuovi per [i report e le informazioni dettagliate nel centro sicurezza & Compliance](reports-and-insights-in-security-and-compliance.md), potrebbe essere utile vedere come è possibile spostarsi facilmente da un dashboard a un'intuizione e alle azioni consigliate.

Questa procedura dettagliata è una delle numerose per il Centro sicurezza & Compliance. Per informazioni sull'esplorazione di report e approfondimenti, vedere le procedure dettagliate nella sezione Argomenti correlati.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per accedere direttamente alla pagina del **dashboard di sicurezza** , utilizzare <https://protection.office.com/searchandinvestigation/dashboard> .

  È possibile visualizzare l'Insight di intelligence di spoofing da più di un dashboard nel centro sicurezza & Compliance. Indipendentemente dal dashboard che si sta esaminando, l'Insight fornisce gli stessi dettagli e consente di eseguire rapidamente le stesse attività.

- Prima di poter eseguire le procedure descritte in questo argomento, è necessario disporre delle autorizzazioni assegnate. Per utilizzare lo spoofing Intelligence Insight, è necessario essere membri di uno dei gruppi di ruoli seguenti:

  - **Gestione organizzazione** o **Amministratore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).
  - **Gestione organizzazione** o **Gestione igiene** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).
  - **Lettore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).
  - **Gestione organizzazione in sola lettura** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- È possibile abilitare e disabilitare l'intelligence spoof nei criteri di anti-phishing ATP. Per ulteriori informazioni, vedere [configurare i criteri di anti-phishing ATP in Microsoft 365](configure-atp-anti-phishing-policies.md).

- In Microsoft 365 organizzazioni con cassette postali di Exchange Online e in standalone Exchange Online Protection (EOP) senza cassette postali di Exchange Online, è possibile utilizzare l'intelligence spoof per monitorare e gestire i mittenti che si stanno inviando messaggi non autenticati. Per altre informazioni, vedere [Configurare spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Aprire lo spoofing Intelligence Insight nel centro sicurezza & Compliance

1. Nel centro sicurezza & conformità, accedere a **Threat Management** \> **Dashboard.**

2. Nella riga **Insights** cercare uno degli elementi seguenti:

   - L' **intelligenza spoof è abilitata**: l'Insight è denominato **domini falsificati che non hanno eseguito l'autenticazione degli ultimi 30 giorni**. non vengono intraprese azioni in modalità test sul messaggio.

   - L' **intelligenza contraffatta è disattivata**: l'Insight nel nome **Abilita la protezione spoof**e facendo clic su di essa è possibile abilitare l'intelligence spoof.

3. L'Insight sul dashboard Visualizza informazioni di questo tipo:

   ![Schermata di Insight Intelligence spoofing](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Questa intuizione ha due modalità:

   - **Modalità Insight**. Se si dispone di un criterio di spoofing abilitato, l'Insight mostrerà il numero di messaggi che sono stati influenzati dalle funzionalità di intelligence spoof negli ultimi 30 giorni.

   - **Che cosa succede se Mode**. Se non si dispone di alcun criterio di spoofing abilitato, l'Insight mostrerà il numero di messaggi  *che sono stati*  influenzati dalle funzionalità di intelligence spoof negli ultimi 30 giorni.

   In entrambi i casi, i domini falsificati visualizzati nell'Insight sono separati in due categorie: **coppie di domini sospetti** e **coppie di domini non sospetti**. Queste categorie sono ulteriormente suddivise in tre diversi bucket che è possibile esaminare.

   Una **coppia di domini** è una combinazione dell'indirizzo mittente e dell'infrastruttura di invio:

   - L'indirizzo da è l'indirizzo di posta elettronica del mittente visualizzato nei client di posta elettronica. Questo indirizzo identifica l'autore del messaggio di posta elettronica. Vale a dire, la cassetta postale dell'utente o del sistema responsabile della creazione del messaggio. Questo indirizzo è noto anche come `5322.From` indirizzo.

   - L'infrastruttura di invio, o mittente, è il dominio dell'organizzazione del servizio di ricerca DNS inverso (record PTR) dell'indirizzo IP di invio. Se l'indirizzo IP di invio non ha un record PTR, il mittente viene identificato dall'IP di invio con la subnet mask 255.255.255.0 nella notazione CIDR (/24). Ad esempio, se l'indirizzo IP è 192.168.100.100, l'indirizzo IP completo del mittente è 192.168.100.100/24.

   Le **coppie di domini sospetti** includono:

   - **Spoof ad alta confidenza**: Microsoft 365 ha ricevuto segnali forti che questi domini sono sospetti, in base agli schemi di invio cronologici e al Punteggio di reputazione dei domini. Microsoft 365 è estremamente sicuro che i domini siano spoofing e che i messaggi inviati da questi domini siano meno probabili.

   - **Falsificazione della confidenza moderata**: Microsoft 365 ha ricevuto segnali moderati che questi domini sono sospetti, basati su modelli di invio cronologici e sul punteggio di reputazione dei domini. Office 365 è moderatamente sicuro che i domini siano spoofing e che i messaggi inviati da questi domini siano legittimi. Questo bucket ha maggiori probabilità di contenere falsi positivi (FPs) rispetto al bucket spoof con confidenza elevata.

   - **Coppie di domini non sospetti** (include **Rescued spoof**): lo spoofing salvato è un dominio che non ha superato i controlli di autenticazione espliciti [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), [DMARC](use-dmarc-to-validate-email.md)) ma ha superato i controlli di autenticazione implicita della posta elettronica ([autenticazione composita](email-validation-and-authentication.md#composite-authentication)). Di conseguenza, Microsoft 365 ha salvato la posta per conto dell'utente e non è stata eseguita alcuna azione antispoofing sul messaggio.

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>Visualizzare informazioni dettagliate sulle coppie di domini sospetti da spoofing Intelligence Insight

1. Nell'Insight Intelligence spoofing, fare clic su una qualsiasi delle coppie di domini (alto, moderato o salvato).

   Viene visualizzata la pagina di **Insight Intelligence spoof** che mostra un elenco di mittenti che inviano messaggi non autenticati all'organizzazione. Le informazioni contenute in questa pagina consentono di determinare se i messaggi falsificati sono autorizzati o se è necessario intraprendere ulteriori azioni. È possibile ordinare le informazioni in base al numero di messaggi, alla data in cui è stata rilevata l'ultima volta la parodia e altro ancora. (Ad esempio, fare clic su intestazioni di colonna, come il **numero di messaggi** o **l'ultima volta**).

2. Selezionare un elemento nella tabella per aprire un riquadro dei dettagli che contiene informazioni complete sulla coppia di domini, incluso il motivo per cui è stato rilevato ciò che è necessario fare, un riepilogo di dominio, i dati WhoIs relativi al mittente e i messaggi di posta elettronica simili che sono stati visualizzati nel tenant dallo stesso mittente. Da qui, è anche possibile scegliere di aggiungere o rimuovere la coppia di dominio dall'elenco dei mittenti attendibili di **AllowedToSpoof** .

   ![Schermata di un dominio nel riquadro dei dettagli dell'analisi di intelligence di spoofing](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a>Aggiungere o rimuovere un dominio dall'elenco dei mittenti attendibili di AllowedToSpoof

È possibile aggiungere o rimuovere un dominio dall'elenco di mittenti attendibili di AllowedToSpoof durante la revisione della coppia di dominio nel riquadro dei dettagli dell'Insight di intelligence di spoofing. È sufficiente impostare l'interruttore di conseguenza.

In questo modo viene modificata la combinazione univoca di coppie di domini del dominio contraffatto e l'infrastruttura di invio e non viene fornita alcuna copertura per l'intero dominio contraffatto o per l'infrastruttura di invio in isolamento.

Ad esempio, se si aggiunge la seguente coppia di dominio all'elenco dei mittenti consentiti ' AllowedToSpoof ': il  *dominio contraffatto*  "Gmail.com" e *l'infrastruttura di invio* "TMS *. MX.com",* sarà possibile eseguire la falsificazione solo della posta dalla coppia di dominio. Altri mittenti che tentano di falsificare "gmail.com" e altri domini che "tms.mx.com" tentano di falsificare continueranno a essere protetti dall'intelligence contraffatta.

## <a name="related-topics"></a>Argomenti correlati

[Protezione anti-spoofing in Microsoft 365](anti-spoofing-protection.md)
