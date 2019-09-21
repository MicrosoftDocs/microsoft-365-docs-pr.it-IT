---
title: Creare elenchi di mittenti bloccati in Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/6/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: Blocca le opzioni dell'elenco dei mittenti includono i mittenti bloccati di Outlook, gli elenchi di mittenti/domini di protezione dalla posta indesiderata, gli elenchi di indirizzi IP bloccati e le regole di trasporto di Exchange (ETRs) denominate anche regole
ms.openlocfilehash: 861fa0e47980a6bc295672cf1e8e35954c6f1dfb
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084595"
---
# <a name="create-block-sender-lists-in-office-365"></a>Creare elenchi di mittenti bloccati in Office 365

A volte è necessario bloccare la posta elettronica indesiderata dai mittenti. Sono disponibili diversi metodi tra cui scegliere. Queste opzioni includono i mittenti bloccati di Outlook, gli elenchi di protezione dalla posta indesiderata/blocco dei domini, gli elenchi di indirizzi IP bloccati e le regole di trasporto di Exchange (ETRs, note anche come regole del flusso di posta).

> [!NOTE]
> Mentre gli elenchi di blocco dell'organizzazione possono essere utilizzati per risolvere i falsi negativi (posta indesiderata persa), tali candidati devono essere inviati anche a Microsoft per l'analisi. La gestione dei falsi negativi tramite gli elenchi bloccati aumenta significativamente il sovraccarico amministrativo. Se si utilizza un elenco di blocco per questo scopo, è necessario conservare anche l'articolo per [inviare messaggi di posta indesiderata, non di posta indesiderata e tentativi di phishing a Microsoft per l'analisi](https://docs.microsoft.com/en-us/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis).

Il metodo appropriato per configurare gli elenchi di mittenti bloccati varia a seconda dell'ambito dell'impatto. Per l'impatto su un singolo utente, la soluzione appropriata potrebbe essere quella di usare i mittenti bloccati di Outlook, ma se sono presenti più utenti o tutti gli utenti, una delle altre opzioni sarebbe più appropriato.

## <a name="options-from-least-to-broadest-scope"></a>Opzioni da almeno all'ambito più esteso

Quando si crea un elenco di blocco, è importante scegliere il metodo appropriato in base all'ambito dell'impatto (quante persone avranno un impatto), in modo che corrisponda all'ampiezza del metodo di blocco. Le opzioni elencate di seguito sono classificate in base all'ambito e all'ampiezza. L'elenco passa da stretto a vasto, ma *leggere le specifiche per i* suggerimenti completi.

- Mittenti bloccati di Outlook
- Criteri di protezione dalla posta indesiderata: elenchi di blocchi di mittenti/domini
- Regole di trasporto di Exchange (ETRs chiamato anche regole del flusso di posta)
- Criteri di protezione da posta indesiderata: elenchi di indirizzi IP bloccati

## <a name="use-outlook-blocked-senders"></a>Utilizzo di mittenti bloccati di Outlook

Quando si verifica un impatto solo su un numero limitato di utenti, è necessario utilizzare i mittenti bloccati di Outlook, perché ciò avrà impatto solo sulla posta inviata.

> [!IMPORTANT]
> Se i messaggi indesiderati sono newsletter provenienti da un'origine attendibile e riconoscibile, l'annullamento della sottoscrizione al messaggio di posta elettronica è un'altra opzione per impedire all'utente di ricevere i messaggi di posta elettronica in futuro.

La procedura per la configurazione di questo tipo di configurazione è diversa tra [Outlook Web App](https://support.office.com/en-us/article/block-or-allow-junk-email-settings-48c9f6f7-2309-4f95-9a4d-de987e880e46) e il [client di Outlook](https://support.office.com/en-us/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). **Quando i messaggi vengono bloccati correttamente a causa di mittenti bloccati, verrà visualizzato SFV: BLK in X-Forefront-antispam-report** che indica che il messaggio è stato bloccato.

## <a name="use-anti-spam-policy-senderdomain-block-lists"></a>Utilizzare i criteri di protezione dalla posta indesiderata e gli elenchi di blocco dei domini

Quando si verifica un impatto su più utenti, l'ambito è più ampio ed è necessario utilizzare un criterio di protezione dalla posta indesiderata a livello di mittente/dominio. La procedura dettagliata è disponibile in [configurare il documento dei criteri di filtro della posta indesiderata](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-your-spam-filter-policies) . Qualsiasi messaggio bloccato tramite questo metodo seguirà l'azione di posta indesiderata configurata nel criterio.

Il limite massimo per questi elenchi è approssimativamente pari a 1000 voci.

## <a name="use-exchange-transport-rules-etrs-to-block-specific-senders"></a>Utilizzare le regole di trasporto di Exchange (ETRs) per bloccare mittenti specifici

Se è necessario bloccare i messaggi inviati a utenti specifici o all'intera organizzazione, è possibile utilizzare ETRs (denominate anche regole del flusso di posta). ETRs sono più flessibili perché possono attivare il dominio o l'indirizzo di posta elettronica del mittente, nonché le parole chiave e altre proprietà del messaggio. Questa flessibilità consentirà di creare blocchi parziali e completi. [Fare clic sulla procedura per creare un ETR, noto anche come regole del flusso di posta elettronica](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages).

> [!IMPORTANT]
> È facile creare regole *troppo* aggressive, di conseguenza è importante che i criteri utilizzati siano i più specifici possibile. Assicurarsi inoltre di abilitare il controllo sulla regola creata e fare test per garantire che tutto funzioni come previsto.

## <a name="use-anti-spam-policy-ip-block-lists"></a>Utilizzare gli elenchi di indirizzi IP bloccati dei criteri di posta indesiderata

Quando non è possibile usare una delle altre opzioni per bloccare un mittente, è possibile utilizzare *l'elenco* indirizzi IP bloccati dei criteri di protezione da posta indesiderata. [I passaggi dettagliati sono disponibili nell'articolo Configure the Connection Filter Policy](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-the-connection-filter-policy). È importante tenere presente che l'elenco degli indirizzi IP bloccati è *minimo* e *non* è consigliabile utilizzare gli intervalli per l'indirizzo del pi.

È consigliabile *evitare di* aggiungere intervalli di indirizzi IP che appartengono a servizi consumer o infrastrutture condivise, nonché di esaminare l'elenco di indirizzi IP consentiti come parte di una manutenzione regolare. **Poiché consente l'apertura delle route per gli attacchi, è necessario gestire attentamente l'elenco e rimuovere periodicamente le voci consentite che non sono più necessarie.** Inoltre, se si vuole fare in modo che in un elenco di mittenti attendibili, leggere e comprendere i rischi e le precauzioni in *[creare elenchi di mittenti attendibili in Office 365](create-safe-sender-lists-in-office-365.md)*.
