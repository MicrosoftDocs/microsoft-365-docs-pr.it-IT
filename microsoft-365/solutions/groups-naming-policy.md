---
title: Criteri di denominazione dei gruppi di Microsoft 365
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
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Informazioni su come creare criteri di denominazione per i gruppi di Microsoft 365.
ms.openlocfilehash: acf660375508760bd2e9874a07454709849929b0
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759825"
---
# <a name="microsoft-365-groups-naming-policy"></a>Criteri di denominazione dei gruppi di Microsoft 365

È possibile utilizzare i criteri di denominazione dei gruppi per applicare una strategia di denominazione coerente per i gruppi creati dagli utenti dell'organizzazione. I criteri di denominazione consentono all'utente e agli utenti di identificare la funzione del gruppo, dell'appartenenza, dell'area geografica o dell'utente che ha creato il gruppo. I criteri di denominazione consentono inoltre di categorizzare i gruppi nella rubrica. È possibile utilizzare il criterio per impedire l'utilizzo di parole specifiche nei nomi di gruppo e negli alias.

I criteri di denominazione vengono applicati ai gruppi creati in tutti i carichi di lavoro dei gruppi (ad esempio Outlook, Microsoft Teams, SharePoint, Planner, Yammer e così via). Viene applicato sia al nome del gruppo che all'alias del gruppo. Viene inoltre applicato quando un utente crea un gruppo e quando il nome, l'alias, la descrizione o l'avatar del gruppo viene modificato per un gruppo esistente.

> [!TIP]
> I criteri di denominazione dei gruppi di Microsoft 365 si applicano solo ai gruppi di Microsoft 365. Non si applica ai gruppi di distribuzione creati in Exchange Online. Per creare un criterio di denominazione per i gruppi di distribuzione, vedere [Creare un criterio di denominazione dei gruppi di distribuzione.](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)

I criteri di denominazione del gruppo sono composti dalle funzionalità seguenti:

- **Criterio di denominazione prefisso-suffisso:** è possibile utilizzare prefissi o suffissi per definire la convenzione di denominazione dei gruppi (ad esempio: "US \_ My Group \_ Engineering"). I prefissi o suffissi possono essere stringhe fisse o attributi utente come [Department] che verranno sostituiti in base all'utente che crea il gruppo.

- **Parole bloccate personalizzate:** è possibile caricare un set di parole bloccate specifiche per l'organizzazione che verrebbero bloccate nei gruppi creati dagli utenti. Ad esempio: ""CEO, Payroll, HR" (CEO, Buste paga, RU)".

## <a name="licensing-requirements"></a>Requisiti per la licenza

L'uso dei criteri di denominazione di Azure AD per i gruppi di Microsoft 365 richiede che tu possieda, ma non necessariamente assegni una licenza Azure Active Directory Premium P1 o una licenza EDU di base di Azure AD per ogni utente univoco (inclusi gli utenti guest) membro di uno o più gruppi di Microsoft 365.

Questa operazione è necessaria anche per l'amministratore che crea i criteri di denominazione dei gruppi.

## <a name="prefix-suffix-naming-policy"></a>Prefix-Suffix di denominazione

I prefissi e i suffissi possono essere stringhe fisse o attributi utente.

### <a name="fixed-strings"></a>Stringhe fisse

È possibile utilizzare stringhe brevi che consentono di distinguere i gruppi nell'elenco indirizzi globale e lo spostamento a sinistra dei carichi di lavoro del gruppo. Alcuni dei suffissi prefissi comuni sono parole chiave come "Grp \_ Name", \# "Name", \_ "Name"

### <a name="attributes"></a>Attributi

È possibile utilizzare attributi che consentono di identificare chi ha creato il gruppo come [Reparto] e da dove è stato creato, ad esempio [Paese].

Esempi:

- Criterio = "GRP [GroupName] [Department]"
- Reparto dell'utente = Progettazione
- Nome del gruppo creato = "GRP Mio gruppo Progettazione"

Gli attributi di Azure Active Directory (Azure AD) supportati sono [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion] e [Title].

- Gli attributi utente non supportati vengono considerati come stringhe fisse, ad esempio [postalCode].

- Gli attributi di estensione e gli attributi personalizzati non sono supportati.

È consigliabile usare attributi contenenti valori compilati per tutti gli utenti dell'organizzazione e non usare attributi con valori lunghi.

### <a name="things-to-look-out-for"></a>Aspetti da cercare

- Durante la creazione dei criteri, la lunghezza totale delle stringhe di prefisso e suffisso è limitata a 53 caratteri.

- Prefissi e suffissi possono contenere caratteri speciali supportati nel nome e nell'alias del gruppo. Quando i prefissi e i suffissi contengono caratteri speciali non consentiti nell'alias di gruppo, vengono applicati solo al nome del gruppo. In questo caso, quindi, i prefissi e suffissi applicati al nome del gruppo sarebbero diversi da quelli applicati all'alias del gruppo.

  > [!NOTE]
  > Un punto (.) o un trattino (-) è consentito in qualsiasi punto del nome del gruppo, tranne all'inizio o alla fine del nome. Un carattere di sottolineatura (_) è consentito in qualsiasi punto del nome del gruppo, incluso all'inizio o alla fine del nome.

- Se si usano i gruppi connessi a Yammer Office 365, evitare di utilizzare i caratteri seguenti nei criteri di denominazione: @, \# \[ , , , \] \<, and \> . Se questi caratteri sono nel criterio di denominazione, gli utenti regolari di Yammer non saranno in grado di creare gruppi.

> [!Tip]
> - Usa stringhe brevi come suffisso.
> - Utilizzare gli attributi con i valori.
> - Non essere troppo creativo, la lunghezza totale del nome ha un massimo di 264 caratteri.
> - Caricare parole bloccate specifiche dell'organizzazione per limitare l'utilizzo.

## <a name="custom-blocked-words"></a>Parole bloccate personalizzate

È possibile immettere un elenco delimitato da virgole di parole bloccate che verranno bloccate nei nomi di gruppo e negli alias.

Non vengono eseguite ricerche di sottostringa; in particolare, è necessaria una corrispondenza esatta tra il nome immesso dall'utente e le parole bloccate personalizzate per attivare un errore.

**Aspetti da cercare:**

- Per le parole bloccate non viene fatta distinzione tra maiuscole e minuscole.

- Quando si immette una parola bloccata, il client del gruppo mostrerà un messaggio di errore con la parola bloccata.

- Per le parole bloccate usate non sono previste limitazioni sul limite di caratteri.

- Esiste un limite di 5.000 parole che possono essere impostate come parole bloccate.

## <a name="admin-override"></a>Override per gli amministratori

Alcuni amministratori sono esenti da questi criteri, in tutti i carichi di lavoro e gli endpoint di gruppo, in modo che possano creare gruppi con queste parole bloccate e con le convenzioni di denominazione desiderate. L'elenco seguente contiene i ruoli di amministratore non soggetti ai criteri di denominazione del gruppo.

- Amministratore globale

- Supporto partner - Livello 1

- Supporto partner - Livello 2

- Amministratore degli account utente

## <a name="how-to-set-up-the-naming-policy"></a>Come configurare i criteri di denominazione

Per configurare un criterio di denominazione:

1. In [Azure Active Directory,](https://aad.portal.azure.com)in **Gestisci,** fare clic su **Gruppi.**
2. In **Impostazioni** fare clic su **Criteri di denominazione.**
3. Scegliere la scheda **Criteri di denominazione dei** gruppi.
4. In **Criteri correnti** scegliere se si desidera richiedere un prefisso o un suffisso o entrambi e selezionare le caselle di controllo appropriate.
5. Scegliere tra **Attributo** e **Stringa** per ogni riga e quindi specificare l'attributo o la stringa.
6. Dopo aver aggiunto i prefissi e i suffissi necessari, fare clic su **Salva.**

![Screenshot delle impostazioni dei criteri di denominazione dei gruppi in Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a>Argomenti correlati

[Procedura dettagliata per la pianificazione della governance della collaborazione](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Creare il piano di governance della collaborazione](collaboration-governance-first.md)

[Cmdlet di Azure Active Directory per la configurazione delle impostazioni di gruppo](https://go.microsoft.com/fwlink/?linkid=868341)
