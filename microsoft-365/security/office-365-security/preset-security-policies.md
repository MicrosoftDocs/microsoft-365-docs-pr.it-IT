---
title: Preimpostare i criteri di sicurezza.
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare ad applicare le impostazioni dei criteri Standard e Strict tra le funzionalità di protezione di Exchange Online Protection (EOP) e Microsoft Defender per Office 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b49b980d217d60865029c8e64ad02ed722f6b86e
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407457"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>Criteri di sicurezza preimpostati in EOP e Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

I criteri di sicurezza preimpostati forniscono una posizione centralizzata per l'applicazione di tutti i criteri di posta indesiderata, malware e phishing consigliati agli utenti contemporaneamente. Le impostazioni dei criteri non sono configurabili. Vengono invece impostati da Microsoft e si basano sulle osservazioni e sulle esperienze dei datacenter per trovare un equilibrio tra mantenere i contenuti dannosi lontano dagli utenti senza interrompere il proprio lavoro.

Il resto di questo argomento descrive i criteri di sicurezza preimpostati e come configurarli.

## <a name="what-preset-security-policies-are-made-of"></a>Quali criteri di sicurezza preimpostati sono fatti

I criteri di sicurezza preimpostati sono costituiti da:

- Profili
- Criteri
- Impostazioni dei criteri

Inoltre, l'ordine di precedenza è importante se più criteri di sicurezza preimpostati e altri criteri si applicano alla stessa persona.

### <a name="profiles-in-preset-security-policies"></a>Profili nei criteri di sicurezza preimpostati

Un profilo determina il livello di protezione. Sono disponibili i profili seguenti:

- **Protezione standard:** un profilo di protezione di base adatto alla maggior parte degli utenti.
- **Protezione rigida:** un profilo di protezione più aggressivo per gli utenti selezionati (target di alto valore o utenti con priorità).

Si utilizzano regole con condizioni ed eccezioni che determinano a chi sono o non vengono applicati i profili.

È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione. Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_). Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).

Le condizioni e le eccezioni disponibili sono:

- **I destinatari sono:** cassette postali, utenti di posta o contatti di posta nell'organizzazione.
- **I destinatari sono membri di**: Gruppi dell'organizzazione.
- **I domini dei destinatari sono:** domini accettati configurati in Microsoft 365.

### <a name="policies-in-preset-security-policies"></a>Criteri nei criteri di sicurezza preimpostati

I criteri di sicurezza preimpostati utilizzano i criteri corrispondenti delle varie funzionalità di protezione in EOP e Microsoft Defender per Office 365. Questi criteri vengono creati _dopo l'assegnazione_ dei criteri di protezione **Standard o** Strict **Protection** preimpostati agli utenti. Non è possibile modificare questi criteri.

- **Criteri di Exchange Online Protection (EOP):** sono incluse le organizzazioni di Microsoft 365 con cassette postali di Exchange Online e le organizzazioni EOP autonome senza cassette postali di Exchange Online:

  - [Criteri di protezione dalla posta indesiderata](configure-your-spam-filter-policies.md) denominati Criteri di sicurezza **preimpostati standard** e Criteri di sicurezza **preimpostati rigorosi.**
  - [Criteri antimalware denominati](configure-anti-malware-policies.md) **Criteri di sicurezza preimpostati standard** e Criteri di sicurezza **preimpostati rigorosi.**
  - [Criteri anti-phishing EOP denominati](set-up-anti-phishing-policies.md#spoof-settings) Criteri di sicurezza **preimpostati standard** e Criteri di **sicurezza preimpostati rigorosi** (impostazioni di spoofing).

- **Criteri di Microsoft Defender per Office 365:** sono incluse le organizzazioni con abbonamenti ai componenti aggiuntivi di Microsoft 365 E5 o Defender per Office 365:

  - Criteri anti-phishing in Microsoft Defender per Office 365 denominati Criteri di sicurezza preimpostati **standard** e **Criteri** di sicurezza preimpostati rigorosi, che includono:

    - Le stesse [impostazioni di spoofing](set-up-anti-phishing-policies.md#spoof-settings) disponibili nei criteri anti-phishing di EOP.
    - [Impostazioni di rappresentazione](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Soglie di phishing avanzate](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Criteri collegamenti sicuri denominati](set-up-atp-safe-links-policies.md) **Criteri di sicurezza preimpostati standard** e Criteri di sicurezza **preimpostati rigorosi.**

  - [Criteri allegati sicuri denominati](set-up-atp-safe-attachments-policies.md) **Criteri di sicurezza preimpostati standard** e Criteri di sicurezza **preimpostati rigorosi.**

Si noti che è possibile applicare protezioni EOP a utenti diversi rispetto alle protezioni di Microsoft Defender per Office 365.

### <a name="policy-settings-in-preset-security-policies"></a>Impostazioni dei criteri nei criteri di sicurezza preimpostati

Non è possibile modificare le impostazioni dei criteri nei profili di protezione. I **valori delle** impostazioni dei criteri Standard e **Strict** sono descritti in Impostazioni consigliate per [EOP e Microsoft Defender per la sicurezza di Office 365.](recommended-settings-for-eop-and-office365-atp.md)

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Ordine di precedenza per i criteri di sicurezza preimpostati e altri criteri

Quando a un utente vengono applicati più criteri, viene applicato l'ordine seguente dalla priorità più alta alla priorità più bassa:

1. **Criteri di sicurezza** preimpostati di protezione rigorosi
2. **Criteri di sicurezza** preimpostati di protezione standard
3. Criteri di sicurezza personalizzati
4. Criteri di sicurezza predefiniti

In altre parole, le  impostazioni del criterio di protezione Strict sostituiscono le impostazioni del criterio di protezione **Standard,** che sostituisce le impostazioni di un criterio personalizzato, che sostituisce le impostazioni del criterio predefinito.

## <a name="assign-preset-security-policies-to-users"></a>Assegnare criteri di sicurezza preimpostati agli utenti

### <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla pagina **Criteri di sicurezza preimpostati,** utilizzare <https://protection.office.com/presetSecurityPolicies> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in **Exchange Online:**
  - Per configurare i criteri di sicurezza preimpostati, è necessario essere membri dei **gruppi di** ruoli Gestione organizzazione o **Amministratore** sicurezza.
  - Per l'accesso in sola lettura ai criteri di sicurezza preimpostati, è necessario essere membri del gruppo di ruoli **Lettore** globale.

  Per ulteriori informazioni, vedere [Autorizzazioni in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).

  **Nota:** l'aggiunta di utenti al ruolo di Azure Active Directory corrispondente  nell'interfaccia di amministrazione di Microsoft 365 offre agli utenti le autorizzazioni e le autorizzazioni necessarie per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>Usare il Centro sicurezza & conformità per assegnare criteri di sicurezza preimpostati agli utenti

1. Nel Centro sicurezza & conformità passare a Criteri di sicurezza preimpostati per la **gestione** \>  \> **delle minacce.**

2. In **Protezione standard o** Protezione **restrittiva** fare clic su **Modifica.**

3. Verrà **avviata la procedura guidata** Applica protezione standard o Applica **protezione** restrittiva. Nelle protezioni **EOP applicabili al passaggio,** identificare i destinatari interni a cui si applicano le [protezioni EOP:](#policies-in-preset-security-policies)

   1. Fare **clic su Aggiungi condizione.** Nell'elenco a discesa visualizzato selezionare una condizione in **Applicato se:**

      - **I destinatari sono**
      - **I destinatari sono membri di**
      - **I domini dei destinatari sono**

      È possibile utilizzare una condizione una sola volta, ma è possibile specificare più valori per la condizione. Più valori della stessa condizione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_ ).

   2. La condizione selezionata viene visualizzata in una sezione ombreggiata. In tale sezione fare clic nella casella Uno **di questi** elementi. Se attendi un momento, verrà visualizzato un elenco in modo da poter selezionare un valore. In caso contrario, puoi iniziare a digitare un valore per filtrare l'elenco e selezionare un valore. Ripetere questo passaggio tutte le volte necessarie. Per rimuovere un singolo valore, fare **clic sull'icona** ![ Rimuovi sul ](../../media/scc-remove-icon.png) valore. Per rimuovere l'intera condizione, fare **clic sull'icona** ![ Rimuovi nella ](../../media/scc-remove-icon.png) condizione.

   3. Per aggiungere un'altra condizione, fare **clic su Aggiungi una condizione** e selezionare una delle condizioni rimanenti. In condizioni diverse viene utilizzata la logica AND, ad _\<recipient1\>_ esempio e _\<member of group 1\>_ .

      Ripetere il passaggio precedente per aggiungere valori alla condizione e ripetere questo passaggio tutte le volte che è necessario o fino a quando non si eseguono le condizioni.

   4. Per aggiungere un'eccezione, fare clic **su Aggiungi una condizione.** Nell'elenco a discesa visualizzato selezionare una condizione in **Tranne quando.** Impostazioni e comportamento sono equivalenti alle condizioni.

   Al termine dell'operazione, fare clic su **Avanti**.

4. Se l'organizzazione dispone di Microsoft Defender per Office 365, vengono applicate le protezioni **ATP** per identificare i destinatari interni a cui si applicano le protezioni di Microsoft Defender per [Office 365.](#policies-in-preset-security-policies)

   Le impostazioni e il comportamento sono esattamente come le protezioni **EOP applicate al** passaggio.

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nel passaggio **Conferma** verificare le selezioni e quindi fare clic su **Conferma.**

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>Utilizzare il Centro sicurezza & conformità per modificare le assegnazioni dei criteri di sicurezza preimpostati

I passaggi per modificare l'assegnazione dei criteri di protezione **Standard** o **Strict protection** sono gli stessi di quando sono stati inizialmente assegnati i criteri di sicurezza [preimpostati agli utenti.](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users)

Per disabilitare i **criteri di protezione Standard** o Strict **protection** pur mantenendo le condizioni e le eccezioni esistenti, far scorrere l'interruttore su **Disabled.** Per abilitare i criteri, far scorrere l'interruttore su **Abilitato.**

### <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare di aver correttamente assegnato i criteri di protezione **Standard** o Strict **Protection** a un utente, usa un'impostazione  di protezione in cui il valore predefinito è diverso dall'impostazione di protezione **Standard,** che è diversa dall'impostazione Di protezione strict.

Ad esempio, per la posta elettronica rilevata come posta indesiderata (non alta probabilità di posta indesiderata) verificare  che il messaggio sia recapitato nella cartella Posta indesiderata per gli utenti di protezione **Standard** e messo in quarantena per gli utenti con protezione avanzata.

Oppure, per la posta elettronica in [blocco,](bulk-complaint-level-values.md)verificare che il valore BCL 6 o superiore recapita il messaggio nella  cartella Posta indesiderata per gli utenti di protezione **standard** e che il valore BCL 4 o superiore meti in quarantena il messaggio per gli utenti con protezione strict.
