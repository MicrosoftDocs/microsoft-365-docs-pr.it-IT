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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni su come applicare le impostazioni dei criteri standard e rigorosi nelle caratteristiche di protezione di Exchange Online Protection (EOP) e Microsoft Defender per Office 365
ms.openlocfilehash: e968f7ea768ac8a0b402c28f3830a52b44afa342
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572778"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>Criteri di sicurezza preimpostati in EOP e Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I criteri di sicurezza preimpostati offrono una posizione centralizzata per l'applicazione di tutti i criteri di posta indesiderata, malware e phishing consigliati agli utenti contemporaneamente. Le impostazioni dei criteri non sono configurabili. Invece, sono impostati da noi e sono basati sulle nostre osservazioni ed esperienze nei centri dati per un equilibrio tra mantenere i contenuti nocivi lontani dagli utenti senza interrompere il lavoro.

Nella parte restante di questo argomento vengono descritti i criteri di sicurezza preimpostati e come configurarli.

## <a name="what-preset-security-policies-are-made-of"></a>Quali criteri di sicurezza predefiniti sono fatti

I criteri di sicurezza preimpostati sono costituiti dagli elementi seguenti:

- Profili
- Criteri
- Impostazioni dei criteri

Inoltre, l'ordine di precedenza è importante se più criteri di sicurezza preimpostati e altri criteri si applicano alla stessa persona.

### <a name="profiles-in-preset-security-policies"></a>Profili nei criteri di sicurezza preimpostati

Un profilo determina il livello di protezione. Sono disponibili i profili seguenti:

- **Protezione standard**: un profilo di protezione di base appropriato per la maggior parte degli utenti.
- **Protezione rigorosa**: un profilo di protezione più aggressivo per gli utenti selezionati (target di valore elevato o utenti prioritari).

Le regole vengono utilizzate con condizioni ed eccezioni che determinano gli utenti a cui sono stati applicati i profili.

È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione. Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_). Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).

Le condizioni e le eccezioni disponibili sono le seguenti:

- **I destinatari sono**: cassette postali, utenti di posta elettronica o contatti di posta nell'organizzazione.
- **I destinatari sono membri di**: gruppi nell'organizzazione.
- **I domini del destinatario sono**: domini accettati configurati in Microsoft 365.

### <a name="policies-in-preset-security-policies"></a>Criteri di criteri di sicurezza preimpostati

I criteri di sicurezza preimpostati utilizzano i criteri corrispondenti delle diverse funzionalità di protezione di EOP e Microsoft Defender per Office 365. Questi criteri sono stati creati _dopo aver_ assegnato gli utenti ai criteri di protezione **standard** o **rigorosi** di protezione preimpostati. Non è possibile modificare questi criteri.

- **Criteri di Exchange Online Protection (EOP)**: sono incluse le organizzazioni Microsoft 365 con le cassette postali di Exchange Online e le organizzazioni EOP autonome senza cassette postali di Exchange Online:
  
  - Criteri di protezione da [posta indesiderata](configure-your-spam-filter-policies.md) denominati criteri di **sicurezza predefiniti standard** e **criteri di sicurezza preimpostati**
  - Criteri [anti-malware](configure-anti-malware-policies.md) denominati **criteri di sicurezza predefiniti standard** e **criteri di sicurezza preimpostati rigorosi**.
  - Criteri di protezione [anti-phishing](set-up-anti-phishing-policies.md#spoof-settings) denominati criteri di **sicurezza predefiniti standard** e **criteri di sicurezza preimpostati** (impostazioni spoofing) di EOP.

- **Microsoft Defender per i criteri di office 365**: include le organizzazioni con Microsoft 365 E5 o gli abbonamenti del componente aggiuntivo Defender per Office 365:

  - I criteri anti-phishing in Microsoft Defender per Office 365 denominati **criteri di sicurezza preimpostati standard** e **criteri di sicurezza preimpostati rigorosi**, tra cui:

    - Le stesse [impostazioni di spoofing](set-up-anti-phishing-policies.md#spoof-settings) disponibili nei criteri di anti-phishing di EOP.
    - [Impostazioni di rappresentazione](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Soglie di phishing avanzate](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - Criteri [collegamenti sicuri](set-up-atp-safe-links-policies.md) denominati **criteri di sicurezza predefiniti standard** e **criteri di sicurezza preimpostati rigorosi**.

  - Criteri [allegati sicuri](set-up-atp-safe-attachments-policies.md) denominati criteri di **sicurezza predefiniti standard** e **criteri di sicurezza preimpostati rigorosi**.

Si noti che è possibile applicare Protezioni di EOP a utenti diversi rispetto a Microsoft Defender per le protezioni di Office 365.

### <a name="policy-settings-in-preset-security-policies"></a>Impostazioni di criteri per i criteri di sicurezza preimpostati

Non è possibile modificare le impostazioni dei criteri nei profili di protezione. I valori di impostazione dei criteri **standard** e **rigorosi** sono descritti in [impostazioni consigliate per EOP e Microsoft Defender per la sicurezza di Office 365](recommended-settings-for-eop-and-office365-atp.md).

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Ordine di precedenza per i criteri di sicurezza preimpostati e altri criteri

Quando più criteri vengono applicati a un utente, l'ordine seguente viene applicato dalla priorità più alta alla priorità più bassa:

1. Criteri di sicurezza preimpostati per la **protezione severi**
2. Criteri di sicurezza predefiniti per la **protezione standard**
3. Criteri di sicurezza personalizzati
4. Criteri di sicurezza predefiniti

In altre parole, le impostazioni dei criteri di **protezione rigorosi** sovrascrivono le impostazioni dei criteri di **protezione standard** , che eseguono l'override delle impostazioni di un criterio personalizzato, che sostituisce le impostazioni del criterio predefinito.

## <a name="assign-preset-security-policies-to-users"></a>Assegnare criteri di sicurezza preimpostati agli utenti

### <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla pagina **criteri di sicurezza preimpostati** , utilizzare <https://protection.office.com/presetSecurityPolicies> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Prima di poter eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni seguenti:

  - Per configurare i criteri di sicurezza preimpostati, è necessario essere membri dei ruoli **Gestione organizzazione** o **amministratore sicurezza** nel [Centro sicurezza & conformità](permissions-in-the-security-and-compliance-center.md).

  - Per l'accesso in sola lettura ai criteri di sicurezza preimpostati, è necessario essere membri del gruppo di ruoli **lettore globale** nel [Centro sicurezza & conformità](permissions-in-the-security-and-compliance-center.md).

### <a name="use-the-security--compliance-center-to-assign-preset-security-policies-to-users"></a>Utilizzare il Centro sicurezza & conformità per assegnare criteri di sicurezza preimpostati agli utenti

1. Nel centro sicurezza & conformità, accedere a criteri **Threat management** di \> **Policy** \> **protezione preimpostati** per i criteri di gestione delle minacce.

2. In **protezione standard** o **protezione rigorosa** fare clic su **modifica**.

3. Viene avviata la procedura guidata **Applica protezione standard** o **Applica protezione rigorosa** . Nelle **Protezioni di EOP si applicano al** passaggio, identificare i destinatari interni a cui si applicano le [Protezioni di EOP](#policies-in-preset-security-policies) :

   1. Fare clic su **Aggiungi condizione**. Nell'elenco a discesa che viene visualizzato, selezionare una condizione in **applicato se**:

      - **I destinatari sono**
      - **I destinatari sono membri di**
      - **I domini del destinatario sono**

      È possibile utilizzare una sola condizione una sola volta, ma è possibile specificare più valori per la condizione. Più valori della stessa condizione di utilizzo o logica (ad esempio, _\<recipient1\>_ o _\<recipient2\>_ ).

   2. La condizione selezionata viene visualizzata in una sezione ombreggiata. In questa sezione fare clic nella casella **una o più di queste** . Se si attende un momento, verrà visualizzato un elenco in modo che sia possibile selezionare un valore. In alternativa, è possibile iniziare a digitare un valore per filtrare l'elenco e selezionare un valore. Ripetere questo passaggio tutte le volte necessarie. Per rimuovere un singolo valore, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) sul valore. Per rimuovere l'intera condizione, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) sulla condizione.

   3. Per aggiungere un'altra condizione, fare clic su **Aggiungi condizione** e selezionare una delle condizioni rimanenti. Condizioni di utilizzo e logica diverse (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_ ).

      Ripetere il passaggio precedente per aggiungere valori alla condizione e ripetere questo passaggio tutte le volte che è necessario o fino a quando non si esauriscono le condizioni.

   4. Per aggiungere un'eccezione, fare clic su **Aggiungi condizione**. Nell'elenco a discesa che viene visualizzato, selezionare una condizione in **tranne quando**. Impostazioni e comportamento sono equivalenti alle condizioni.

   Al termine dell'operazione, fare clic su **Avanti**.

4. Se l'organizzazione dispone di Microsoft Defender per Office 365, è necessario eseguire la procedura di **protezione ATP** per identificare i destinatari interni a cui si applicano le [Protezioni di Microsoft defender per Office 365](#policies-in-preset-security-policies) .

   Le impostazioni e il comportamento sono esattamente come si **applicano le protezioni di EOP al** passaggio.

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nel passaggio **conferma** , verificare le selezioni, quindi fare clic su **conferma**.

### <a name="use-the-security--compliance-center-to-modify-the-assignments-of-preset-security-policies"></a>Utilizzare il Centro sicurezza & conformità per modificare le assegnazioni dei criteri di sicurezza preimpostati

La procedura per la modifica dell'assegnazione dei criteri di protezione **standard** o di protezione **rigorosi** è identica a quella in cui gli utenti hanno inizialmente [assegnato i criteri di sicurezza preimpostati](#use-the-security--compliance-center-to-assign-preset-security-policies-to-users).

Per disabilitare la **protezione standard** o i criteri di sicurezza di **protezione rigorosi** mantenendo sempre le condizioni e le eccezioni esistenti, fare scorrere l'interruttore su **disabilitato**. Per abilitare i criteri, fare scorrere l'interruttore su **attivato**.

### <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare di aver correttamente assegnato a un utente il criterio di protezione **standard** Protection o **strict Protection** , utilizzare un'impostazione di protezione in cui il valore predefinito è diverso dall'impostazione di **protezione standard** , che è diversa dall'impostazione di **protezione rigorosa** .

Ad esempio, per la posta elettronica che viene rilevata come posta indesiderata (posta indesiderata non elevata) verificare che il messaggio venga recapitato nella cartella posta indesiderata per gli utenti di **protezione standard** e in quarantena per utenti di **protezione**

In alternativa, per il messaggio di [posta elettronica in blocco](bulk-complaint-level-values.md), verificare che il valore di BCL 6 o superiore recapita il messaggio alla cartella posta indesiderata per gli utenti di **protezione standard** e che il valore di BCL 4 o versione successiva sia in quarantena per gli utenti con **protezione rigorosa** .
