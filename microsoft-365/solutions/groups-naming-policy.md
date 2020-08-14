---
title: Criteri di denominazione dei gruppi Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Informazioni su come creare un criterio di denominazione per i gruppi di Microsoft 365.
ms.openlocfilehash: 0072abf4f249af544e8234fdedec584a71c214a7
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662696"
---
# <a name="microsoft-365-groups-naming-policy"></a>Criteri di denominazione dei gruppi Microsoft 365

È possibile utilizzare un criterio di denominazione del gruppo per applicare una strategia di denominazione coerente per i gruppi creati dagli utenti dell'organizzazione. I criteri di denominazione consentono all'utente e agli utenti di identificare la funzione del gruppo, dell'appartenenza, dell'area geografica o di chi ha creato il gruppo. Il criterio di denominazione può anche contribuire alla categorizzazione dei gruppi nella rubrica. È possibile utilizzare il criterio per bloccare le parole specifiche che vengono utilizzate nei nomi e negli alias di gruppo.

I criteri di denominazione vengono applicati ai gruppi creati in tutti i carichi di lavoro dei gruppi (come Outlook, Microsoft teams, SharePoint, planner, Yammer e così via). Viene applicato sia al nome del gruppo sia all'alias di gruppo. Viene applicato quando un utente crea un gruppo e quando viene modificato il nome o l'alias del gruppo per un gruppo esistente.

> [!TIP]
> I criteri di denominazione di un gruppo di Microsoft 365 si applicano solo ai gruppi di Microsoft 365. Non si applica ai gruppi di distribuzione creati in Exchange Online. Per creare un criterio di denominazione per i gruppi di distribuzione, vedere [Create a Distribution Group Naming Policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).

I criteri di denominazione del gruppo sono composti dalle funzionalità seguenti:

- **Criteri di denominazione dei suffissi prefix**: è possibile utilizzare prefissi o suffissi per definire la convenzione di denominazione di gruppi (ad esempio, "US \_ My Group \_ Engineering"). I prefissi o suffissi possono essere stringhe fisse o attributi utente come [Department] che verranno sostituiti in base all'utente che crea il gruppo.

- **Parole bloccate personalizzate**: è possibile caricare una serie di parole bloccate specifiche per l'organizzazione che verrebbero bloccate nei gruppi creati dagli utenti. Ad esempio: ""CEO, Payroll, HR" (CEO, Buste paga, RU)".

## <a name="licensing-requirements"></a>Requisiti per la licenza

L'utilizzo dei criteri di denominazione di Azure AD per i gruppi di Microsoft 365 richiede che siano in possesso, ma non necessariamente, di una licenza di Azure Active Directory Premium P1 o di una licenza di Azure AD Basic EDU per ogni utente univoco (compresi gli ospiti) che sia membro di uno o più gruppi di Microsoft 365.

Questa operazione è necessaria anche per l'amministratore che crea i criteri di denominazione dei gruppi.

## <a name="prefix-suffix-naming-policy"></a>Prefisso-suffisso Naming Policy

I prefissi e i suffissi possono essere stringhe fisse o attributi utente.

### <a name="fixed-strings"></a>Stringhe fisse

È possibile utilizzare stringhe brevi che consentono di distinguere i gruppi nell'elenco indirizzi globale e la struttura di spostamento sinistra dei carichi di lavoro di gruppo. Alcuni dei suffissi comuni prefissi sono parole chiave come "GRP \_ Name", " \# Name", " \_ Name"

### <a name="attributes"></a>Attributi

È possibile utilizzare gli attributi che consentono di identificare chi ha creato il gruppo come [Department] e dove è stato creato da like [Country].

Esempi:

- Criterio = "GRP [GroupName] [Department]"
- Reparto dell'utente = Progettazione
- Nome del gruppo creato = "GRP Mio gruppo Progettazione"

Gli attributi di Azure Active Directory (Azure AD) supportati sono [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion] e [title].

- Gli attributi utente non supportati sono considerati stringhe fisse, ad esempio [postalCode].

- Gli attributi di estensione e gli attributi personalizzati non sono supportati.

È consigliabile usare attributi contenenti valori compilati per tutti gli utenti dell'organizzazione e non usare attributi con valori lunghi.

### <a name="things-to-look-out-for"></a>Elementi di cui eseguire la ricerca

- Durante la creazione dei criteri, la lunghezza totale delle stringhe di prefisso e suffisso è limitata a 53 caratteri.

- Prefissi e suffissi possono contenere caratteri speciali supportati nel nome e nell'alias del gruppo. Quando i prefissi e i suffissi contengono caratteri speciali non consentiti nell'alias di gruppo, vengono applicati solo al nome del gruppo. In questo caso, quindi, i prefissi e suffissi applicati al nome del gruppo sarebbero diversi da quelli applicati all'alias del gruppo.

  > [!NOTE]
  > Un punto (.) o un trattino (-) è consentito in qualsiasi punto del nome del gruppo, tranne all'inizio o alla fine del nome. Un carattere di sottolineatura (_) è consentito in qualsiasi punto del nome del gruppo, incluso all'inizio o alla fine del nome.

- Se si utilizzano i gruppi connessi di Yammer Office 365, evitare di usare i seguenti caratteri nei criteri di denominazione: @, \# , \[ ,, \] \<, and \> . Se questi caratteri sono inclusi nei criteri di denominazione, gli utenti di Yammer regolari non potranno creare gruppi.

> [!Tip]
> - Utilizzare le stringhe brevi come suffisso.
> - Utilizzare gli attributi con valori.
> - Non è troppo creativo, la lunghezza totale del nome ha un massimo di 264 caratteri.
> - Caricare le parole bloccate specifiche dell'organizzazione per limitare l'utilizzo.

## <a name="custom-blocked-words"></a>Parole bloccate personalizzate

È possibile immettere un elenco separato da virgole di parole bloccate che verranno bloccate nei nomi e negli alias di gruppo.

Non vengono eseguite ricerche in una stringa secondaria. in particolare, è necessaria una corrispondenza esatta tra il nome immesso dall'utente e le parole bloccate personalizzate per attivare un errore.

**Aspetti da cercare**:

- Per le parole bloccate non viene fatta distinzione tra maiuscole e minuscole.

- Quando si immette una parola bloccata, il client del gruppo mostrerà un messaggio di errore con la parola bloccata.

- Per le parole bloccate usate non sono previste limitazioni sul limite di caratteri.

- Esiste un limite di 5000 parole che possono essere impostate come parole bloccate.

## <a name="admin-override"></a>Override per gli amministratori

Alcuni amministratori sono esonerati da questi criteri, in tutti i carichi di lavoro e gli endpoint di gruppo, in modo che possano creare gruppi con queste parole bloccate e con le convenzioni di denominazione desiderate. L'elenco seguente contiene i ruoli di amministratore non soggetti ai criteri di denominazione del gruppo.

- Amministratore globale

- Supporto partner - Livello 1

- Supporto partner - Livello 2

- Amministratore degli account utente

- Ruoli con autorizzazioni di scrittura nella directory

## <a name="how-to-set-up-the-naming-policy"></a>Come configurare i criteri di denominazione

Per impostare i criteri di denominazione:

1. In [Azure Active Directory](https://aad.portal.azure.com), in **gestione**, fare clic su **gruppi**.
2. In **Impostazioni**fare clic su **criteri di denominazione**.
3. Scegliere la scheda **criteri di denominazione dei gruppi** .
4. In **criterio corrente**scegliere se si desidera richiedere un prefisso o un suffisso o entrambi, quindi selezionare le caselle di controllo appropriate.
5. Scegliere tra l' **attributo** e la **stringa** per ogni riga e quindi specificare l'attributo o la stringa.
6. Dopo aver aggiunto i prefissi e i suffissi necessari, fare clic su **Salva**.

![Schermata delle impostazioni dei criteri di denominazione del gruppo in Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a>Argomenti correlati

[Cmdlet di Azure Active Directory per la configurazione delle impostazioni di gruppo](https://go.microsoft.com/fwlink/?linkid=868341)
