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
description: Gli amministratori possono sapere come funziona l'Insight di intelligence di spoofing. Possono determinare rapidamente quali mittenti stanno inviando messaggi di posta elettronica nelle loro organizzazioni da domini che non superano i controlli di autenticazione della posta elettronica (SPF, DKIM o DMARC).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 89a31c6df7c9b6e02f52ea414ceb6334427feab1
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920479"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>Procedura dettagliata-spoofing Intelligence Insight in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365 organizzazioni con difensore per Office 365, è possibile utilizzare la funzionalità di Insight Intelligence per determinare rapidamente quali mittenti stanno inviando legalmente la posta elettronica non autenticata (messaggi provenienti da domini che non superano i controlli SPF, DKIM o DMARC).

Consentendo ai mittenti noti di inviare messaggi falsificati da posizioni note, è possibile ridurre i falsi positivi (un buon messaggio di posta elettronica contrassegnato come cattivo). Monitorando i mittenti autorizzati falsificati, è possibile fornire un ulteriore livello di sicurezza per impedire l'arrivo di messaggi non sicuri nell'organizzazione.

Per ulteriori informazioni sui report e sulle intuizioni, vedere [Reports and Insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).

Questa procedura dettagliata è una delle numerose per il Centro sicurezza & Compliance. Per informazioni sull'esplorazione di report e approfondimenti, vedere le procedure dettagliate nella sezione [argomenti correlati](#related-topics) .

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per accedere direttamente alla pagina del **dashboard di sicurezza** , utilizzare <https://protection.office.com/searchandinvestigation/dashboard> .

  È possibile visualizzare l'Insight di intelligence di spoofing da più di un dashboard nel centro sicurezza & Compliance. Indipendentemente dal dashboard che si sta esaminando, l'Insight fornisce gli stessi dettagli e consente di eseguire rapidamente le stesse attività.

- Prima di poter eseguire le procedure descritte in questo argomento, è necessario disporre delle autorizzazioni assegnate. Per utilizzare lo spoofing Intelligence Insight, è necessario essere membri di uno dei gruppi di ruoli seguenti:

  - **Gestione organizzazione** o **Amministratore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).
  - **Gestione organizzazione** o **Gestione igiene** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).
  - **Lettore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).
  - **Gestione organizzazione in sola lettura** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- È possibile abilitare e disabilitare l'intelligence spoof nei criteri di anti-phishing in Microsoft Defender per Office 365. Per ulteriori informazioni, vedere [Configure anti-phishing Policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

- Per utilizzare l'intelligence spoof per monitorare e gestire i mittenti che inviano messaggi non autenticati, vedere [Configure Spoofing Intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Aprire lo spoofing Intelligence Insight nel centro sicurezza & Compliance

1. Nel centro sicurezza & conformità, accedere a **Threat Management** \> **Dashboard.**

2. Nella riga **Insights** cercare uno degli elementi seguenti:

   - L' **intelligenza spoof è abilitata** : l'Insight è denominato **domini falsificati che non hanno eseguito l'autenticazione degli ultimi 30 giorni**. non vengono intraprese azioni in modalità test sul messaggio.
   - L' **intelligenza contraffatta è disattivata** : l'Insight nel nome **Abilita la protezione spoof** e facendo clic su di essa è possibile abilitare l'intelligence spoof.

3. L'Insight sul dashboard Visualizza informazioni di questo tipo:

   ![Schermata di Insight Intelligence spoofing](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Questa intuizione ha due modalità:

   - **Modalità Insight** : se l'intelligence spoof è abilitata, l'Insight Visualizza il numero di messaggi che sono stati influenzati dalle funzionalità di intelligence spoof negli ultimi 30 giorni.

   - **Cosa succede se la modalità** : se l'intelligence di spoofing è disabilitata, l'Insight Visualizza il numero *di messaggi che* sono stati influenzati dalle funzionalità di intelligence spoof negli ultimi 30 giorni.

   In entrambi i casi, i domini falsificati visualizzati nell'Insight sono separati in due categorie: **coppie di domini sospetti** e **coppie di domini non sospetti**. Queste categorie sono ulteriormente suddivise in tre diversi bucket che è possibile esaminare.

   Una **coppia di domini** è una combinazione dell'indirizzo mittente e dell'infrastruttura di invio:

   - L'indirizzo da è l'indirizzo di posta elettronica del mittente visualizzato nella casella da nei client di posta elettronica. Questo indirizzo è noto anche come `5322.From` indirizzo.

   - L'infrastruttura di invio, o mittente, è il dominio dell'organizzazione del servizio di ricerca DNS inverso (record PTR) dell'indirizzo IP di invio. Se l'indirizzo IP di invio non ha un record PTR, il mittente viene identificato dall'IP di invio con la subnet mask 255.255.255.0 nella notazione CIDR (/24). Ad esempio, se l'indirizzo IP è 192.168.100.100, l'indirizzo IP completo del mittente è 192.168.100.100/24.

   Le **coppie di domini sospetti** includono:

   - **Spoof ad alta confidenza** : sulla base dei modelli di invio storico e del Punteggio di reputazione dei domini, è estremamente sicuro che i domini siano spoofing e che i messaggi provenienti da questi domini abbiano maggiori probabilità di essere dannosi.

   - **Falsificazione della confidenza moderata** : in base ai modelli di invio cronologici e al Punteggio di reputazione dei domini, si è certi che i domini siano spoofing e che i messaggi inviati da questi domini siano legittimi. I falsi positivi sono più probabili in questa categoria rispetto alla falsificazione con attendibilità elevata.

   - **Coppie di domini non sospetti** (include **Rescued spoof** ): il dominio non è riuscito l'autenticazione esplicita della posta elettronica controlla [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC](use-dmarc-to-validate-email.md)). Tuttavia, il dominio ha superato i controlli di autenticazione della posta elettronica impliciti ([autenticazione composita](email-validation-and-authentication.md#composite-authentication)). Di conseguenza, non è stata eseguita alcuna azione antispoofing sul messaggio.

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>Visualizzare informazioni dettagliate sulle coppie di domini sospetti da spoofing Intelligence Insight

1. Nell'Insight Intelligence spoofing, fare clic su una qualsiasi delle coppie di domini (alto, moderato o salvato).

   Viene visualizzata la pagina di **Insight Intelligence spoof** . Nella pagina viene visualizzato un elenco di mittenti che inviano messaggi di posta elettronica non autenticati nell'organizzazione.

   Queste informazioni consentono di determinare se i messaggi falsificati sono autorizzati o se è necessario intraprendere ulteriori azioni.

   È possibile ordinare le informazioni in base al numero di messaggi, alla data in cui è stata rilevata l'ultima volta la parodia e altro ancora.

2. Selezionare un elemento nella tabella per aprire un riquadro dei dettagli che contiene informazioni complete sulla coppia di domini. Le informazioni includono:
   - Perché questo è stato rilevato.
   - Cosa devi fare.
   - Riepilogo di un dominio.
   - Dati WhoIs sul mittente.
   - Messaggi simili che sono stati visualizzati nel tenant dallo stesso mittente.

   Da qui, è anche possibile scegliere di aggiungere o rimuovere la coppia di dominio dall'elenco dei mittenti attendibili di **AllowedToSpoof** .

   ![Schermata di un dominio nel riquadro dei dettagli dell'analisi di intelligence di spoofing](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-list"></a>Aggiungere o rimuovere un dominio dall'elenco AllowedToSpoof

È possibile aggiungere o rimuovere un dominio dall'elenco AllowedToSpoof (Safe sender) nel riquadro dei dettagli dell'Insight di intelligence di spoofing per la coppia di dominio. È sufficiente impostare l'interruttore di conseguenza.

La possibilità di una coppia di domini consente solo la combinazione del dominio contraffatto *e* dell'infrastruttura di invio. Non consente la posta elettronica dal dominio contraffatto da qualsiasi origine, né consente la posta elettronica dall'infrastruttura di invio per qualsiasi dominio.

Ad esempio, è possibile consentire alla coppia di domini seguente di inviare messaggi falsificati all'organizzazione:

- *Dominio contraffatto* : Gmail.com "
- *Infrastruttura di invio* `tms.mx.com` :

Solo il messaggio di posta elettronica da tale coppia di dominio sarà autorizzato allo spoofing. Gli altri mittenti che tentano di falsificare gmail.com non sono consentiti. I messaggi in altri domini di tms.mx.com vengono controllati da spoofing Intelligence.

## <a name="related-topics"></a>Argomenti correlati

[Protezione anti-spoofing in Microsoft 365](anti-spoofing-protection.md)
