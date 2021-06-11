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
ms.openlocfilehash: 24fe67a7465ec71451b649dbc5963c28e0dc7cf3
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879013"
---
# <a name="preset-security-policies-in-eop-and-microsoft-defender-for-office-365"></a>Criteri di sicurezza predefiniti in EOP e Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I criteri di sicurezza predefiniti offrono una posizione centralizzata per l'applicazione di tutti i criteri di posta indesiderata, malware e phishing consigliati agli utenti contemporaneamente. Le impostazioni dei criteri non sono configurabili. Sono invece impostati da microsoft e si basano sulle osservazioni e sulle esperienze dei datacenter per un equilibrio tra mantenere contenuti dannosi lontano dagli utenti ed evitare interruzioni non necessarie.

Il resto di questo articolo descrive i criteri di sicurezza preimpostati e come configurarli.

## <a name="what-preset-security-policies-are-made-of"></a>Quali criteri di sicurezza preimpostati sono fatti

I criteri di sicurezza predefiniti sono costituiti da elementi seguenti:

- Profili
- Criteri
- Impostazioni dei criteri

Inoltre, l'ordine di precedenza è importante se più criteri di sicurezza preimpostati e altri criteri si applicano alla stessa persona.

### <a name="profiles-in-preset-security-policies"></a>Profili nei criteri di sicurezza preimpostati

Un profilo determina il livello di protezione. Sono disponibili i profili seguenti:

- **Protezione standard:** profilo di protezione di base adatto alla maggior parte degli utenti.
- **Protezione rigorosa**: profilo di protezione più aggressivo per gli utenti selezionati (target di alto valore o utenti con priorità).

Si utilizzano regole con condizioni ed eccezioni che determinano a chi sono o non sono applicati i profili.

Le condizioni e le eccezioni disponibili sono:

- **Utenti**: la cassette postali specificate, utenti di posta o contatti di posta specificati nell'organizzazione.
- **Gruppi**: i gruppi di distribuzione specificati, gruppi di sicurezza abilitati alla posta elettronica o gruppi di Microsoft 365 nell'organizzazione.
- **Domini**: tutti i destinatari nei domini specificati [accettati](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) nell'organizzazione.

È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione. Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_). Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).

### <a name="policies-in-preset-security-policies"></a>Criteri nei criteri di sicurezza preimpostati

I criteri di sicurezza predefiniti usano i criteri corrispondenti delle varie funzionalità di protezione di EOP e Microsoft Defender per Office 365. Questi criteri vengono creati _dopo l'assegnazione_ dei criteri di protezione **Standard** o **Strict protection** preset security agli utenti. Non è possibile modificare questi criteri.

- **Exchange Online Protection (EOP):** sono incluse Microsoft 365 con cassette postali Exchange Online e organizzazioni EOP autonome senza Exchange Online cassette postali:

  - [Criteri di protezione da posta indesiderata](configure-your-spam-filter-policies.md) denominati Standard Preset Security **Policy** e Strict Preset **Security Policy**.
  - [Criteri antimalware denominati](configure-anti-malware-policies.md) **Standard Preset Security Policy** e Strict Preset Security **Policy**.
  - [Criteri anti-phishing EOP](set-up-anti-phishing-policies.md#spoof-settings) denominati **Standard Preset Security Policy** e Strict Preset Security **Policy** (impostazioni spoof).

- **Microsoft Defender per Office 365** criteri : sono incluse le organizzazioni con Microsoft 365 E5 o Defender per Office 365 di componenti aggiuntivi:

  - Criteri anti-phishing in Microsoft Defender per Office 365 denominati **Standard Preset Security Policy** e Strict Preset Security **Policy**, che includono:

    - Le stesse [impostazioni di spoofing](set-up-anti-phishing-policies.md#spoof-settings) disponibili nei criteri anti-phishing di EOP.
    - [Impostazioni di rappresentazione](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Soglie di phishing avanzate](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Criteri collegamenti sicuri denominati](set-up-safe-links-policies.md) **Criteri di sicurezza predefiniti standard** e Criteri di **sicurezza preimpostati rigorosi**.

  - [Criteri allegati sicuri denominati](set-up-safe-attachments-policies.md) **Standard Preset Security Policy** e Strict Preset **Security Policy**.

Tieni presente che puoi applicare protezioni EOP a utenti diversi rispetto a Microsoft Defender per Office 365 protezione.

### <a name="policy-settings-in-preset-security-policies"></a>Impostazioni dei criteri nei criteri di sicurezza preimpostati

Non è possibile modificare le impostazioni dei criteri nei profili di protezione. I **valori delle** impostazioni dei criteri Standard e **Strict** sono descritti in Impostazioni consigliate per EOP e Microsoft Defender per [Office 365 sicurezza](recommended-settings-for-eop-and-office365.md).

### <a name="order-of-precedence-for-preset-security-policies-and-other-policies"></a>Ordine di precedenza per i criteri di sicurezza preimpostati e altri criteri

Quando vengono applicati più criteri a un utente, l'ordine seguente viene applicato dalla priorità più alta alla priorità più bassa:

1. **Criteri di sicurezza** preimpostati di protezione rigorosi
2. **Criteri di sicurezza predefiniti** di protezione standard
3. Criteri di sicurezza personalizzati
4. Criteri di sicurezza predefiniti

In altre parole, le  impostazioni del criterio di protezione Strict sostituiscono le impostazioni del criterio di protezione **Standard,** che sostituisce le impostazioni di un criterio personalizzato, che sostituisce le impostazioni del criterio predefinito.

## <a name="assign-preset-security-policies-to-users"></a>Assegnare criteri di sicurezza predefiniti agli utenti

### <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Aprire il portale Microsoft 365 Defender all'indirizzo <https://security.microsoft.com> . Per passare direttamente alla pagina **Criteri di sicurezza predefiniti,** utilizzare <https://security.microsoft.com/presetSecurityPolicies> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in **Exchange Online**:
  - Per configurare i criteri di sicurezza predefiniti, è necessario essere membri dei **gruppi di** ruoli Gestione organizzazione o Amministratore **sicurezza.**
  - Per l'accesso in sola lettura ai criteri di sicurezza preimpostati, è necessario essere membri del gruppo di ruoli **Lettore** globale.

  Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Nota:** l'aggiunta di utenti al ruolo Azure Active Directory corrispondente nell'interfaccia di  amministrazione di Microsoft 365 offre agli utenti le autorizzazioni e le autorizzazioni necessarie per altre funzionalità in Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).

### <a name="use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users"></a>Usare il portale Microsoft 365 Defender per assegnare criteri di sicurezza predefiniti agli utenti

1. Nel portale Microsoft 365 Defender passare **a** Criteri di & di collaborazione & regole Criteri di minaccia \>  \>  \> **Sezione** \> **Criteri** di sicurezza predefiniti .

2. In **Protezione standard o** Protezione **rigida** fare clic su **Modifica.**

3. Verrà **avviata la procedura guidata** Applica protezione standard o Applica **protezione** rigida. Nella pagina **Si applicano le protezioni EOP** a identificare i destinatari interni a cui si applicano le protezioni [EOP](#policies-in-preset-security-policies) (condizioni del destinatario):
   - **Utenti**
   - **Gruppi**
   - **Domini**

   Fare clic nella casella appropriata, iniziare a digitare un valore e selezionare il valore desiderato nei risultati. Ripetere questa procedura tutte le volte necessarie. Per rimuovere un valore esistente, fare clic su Rimuovi ![Icona Rimuovi](../../media/m365-cc-sc-remove-selection-icon.png) accanto al valore.

   Per utenti o gruppi è possibile usare la maggior parte degli identificatori, ad esempio nome, nome visualizzato, alias, indirizzo di posta elettronica, nome dell'account e così via, ma il nome visualizzato corrispondente viene visualizzato nei risultati. Per gli utenti, immettere un asterisco (\*) da solo per visualizzare tutti i valori disponibili.

   - **Escludere questi utenti, gruppi e domini**: per aggiungere eccezioni per i destinatari interni a cui si applicano i criteri (eccezione destinatari), selezionare questa opzione e configurare le eccezioni. Impostazioni e comportamento sono equivalenti alle condizioni.

   Al termine dell'operazione, fare clic su **Avanti**.

4. In Microsoft Defender per le organizzazioni di Office 365, viene visualizzata la pagina Defender per le protezioni **di Office 365** per identificare i destinatari interni a cui si applicano le protezioni di Microsoft Defender per [Office 365](#policies-in-preset-security-policies) (condizioni dei destinatari).

   Le impostazioni e il comportamento sono esattamente simili alle protezioni **EOP applicate alla** pagina.

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nella pagina **Rivedi e conferma le modifiche** verifica le selezioni e quindi fai clic su **Conferma.**

### <a name="use-the-microsoft-365-defender-portal-to-modify-the-assignments-of-preset-security-policies"></a>Usare il portale Microsoft 365 Defender per modificare le assegnazioni dei criteri di sicurezza preimpostati

I passaggi per modificare l'assegnazione dei criteri di protezione **Standard** o Strict **protection** sono gli stessi di quando sono stati inizialmente assegnati i criteri di sicurezza predefiniti [agli utenti.](#use-the-microsoft-365-defender-portal-to-assign-preset-security-policies-to-users)

Per disabilitare **i criteri di protezione Standard** o Strict **protection** pur mantenendo le condizioni e le eccezioni esistenti, fai scorrere l'interruttore **su Disabled** Toggle ![ ](../../media/scc-toggle-off.png) Off. Per abilitare i criteri, fai scorrere l'interruttore **su** ![ ](../../media/scc-toggle-on.png) Attiva/Disattiva.

### <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare che il criterio di protezione **Standard** o Strict **protection** sia stato assegnato correttamente a un utente, utilizzare un'impostazione di protezione in cui il valore predefinito è diverso dall'impostazione **Protezione standard,** che è diversa dall'impostazione Protezione rigida. 

Ad esempio, per la posta elettronica rilevata come posta indesiderata (non posta indesiderata con alta probabilità) verificare  che il messaggio sia recapitato nella cartella Posta indesiderata per gli utenti di protezione **standard** e messo in quarantena per gli utenti con protezione rigorosa.

In caso di posta in [blocco,](bulk-complaint-level-values.md)verificare che il valore BCL 6 o superiore recapita il messaggio nella cartella Posta  indesiderata per gli utenti di protezione **standard** e che il valore BCL 4 o superiore meti in quarantena il messaggio per gli utenti con protezione rigorosa.
