---
title: Eseguire una versione di valutazione di Microsoft Viva Topics
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: ''
search.appverid: ''
localization_priority: Normal
description: Informazioni su come pianificare ed eseguire un programma pilota di valutazione per Microsoft Viva Topics nell'organizzazione.
ms.openlocfilehash: 128e82e7664a76baa55d37e983319c9f344624fd
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327114"
---
# <a name="run-a-trial-of-microsoft-viva-topics"></a>Eseguire una versione di valutazione di Microsoft Viva Topics

In questo articolo viene descritto come configurare ed eseguire un programma pilota di prova per distribuire Viva Topics nell'organizzazione. In questo articolo vengono inoltre consigliate le procedure consigliate per la versione di valutazione.

## <a name="sign-up-for-a-trial"></a>Iscriversi per una versione di valutazione

Le versioni di valutazione sono disponibili pubblicamente da una delle origini seguenti. Queste versioni di valutazione offrono a 25 utenti l'accesso a Viva Topics per 30 giorni.

- Pagina [del prodotto Viva Topics](https://www.microsoft.com/microsoft-viva/topics?activetab=pivot:overviewtab)

- Il [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com)
    1.  Accedere all'[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com).
    2.  Vai a **Fatturazione**  >  **Servizi di acquisto.**
    3.  Scorrere fino al pulsante **Componenti aggiuntivi**.
    4.  Nel riquadro **Esperienze argomento** seleziona **Dettagli.**
    5.  Selezionare **Ottieni una versione di valutazione gratuita**.
    6.  Segui i passaggi rimanenti della procedura guidata per confermare la versione di valutazione.

È necessario essere un amministratore Microsoft 365 globale o un amministratore di fatturazione per attivare una versione di valutazione.

> [!NOTE]
> Le versioni di valutazione pubbliche possono essere aggiunte una sola volta per ogni tenant Microsoft 365 tenant.

### <a name="who-should-be-involved-in-a-trial"></a>Who essere coinvolto in una versione di valutazione

|Ruolo  |Attività  |
|---------|---------|
|Microsoft 365 amministratore globale o amministratore fatturazione  |   Attivare la versione di valutazione e assegnare le licenze      |
|Microsoft 365 amministratore globale o SharePoint amministratore globale    |       Configurare Viva Topics e creare centri argomenti  |
|Utente aziendale     |   Eseguire ruoli di knowledge manager, collaboratore di argomenti e consumer di argomenti      |

### <a name="before-you-activate-a-trial"></a>Prima di attivare una versione di valutazione

La pianificazione è essenziale per una versione di valutazione efficace di Viva Topics. Il periodo di valutazione è limitato e deve includere l'individuazione degli argomenti e l'esplorazione della qualità, della gestione e delle esperienze degli utenti finali.

#### <a name="discovery"></a>Individuazione

Esistono due opzioni di strategia di alto livello per la configurazione dell'individuazione degli argomenti durante una versione di valutazione:

- Indicizza tutto o la maggior parte del SharePoint online.
   - I tenant di grandi dimensioni possono richiedere fino a due settimane per l'indicizzazione completa. Anche se gli argomenti verranno generati in modo incrementale durante questo periodo, l'indicizzazione completa potrebbe consumare fino alla metà del periodo di valutazione.
   - Per i tenant con un volume significativo di dati, questa opzione può produrre un numero molto elevato di argomenti, ad esempio decine di migliaia.

- Identificare un sottoinsieme dei siti SharePoint per l'indicizzazione.

La scelta di queste strategie è un equilibrio tra i due fattori seguenti:

- Dati sufficienti per generare argomenti significativi. L'IA in Viva Topics è ottimizzata per lavorare su set di dati di grandi dimensioni, idealmente con più di 10.000 documenti.
- Non generare così tanti argomenti durante il periodo di prova che valutarli durante il periodo di tempo disponibile è travolgente.

Per la maggior parte delle organizzazioni, la seconda strategia produce il risultato migliore.

> [!NOTE]
> A causa del numero di documenti richiesti dall'IA, è consigliabile eseguire le versioni di valutazione viva topics in un tenant di produzione. Non c'è alcun impatto sulle prestazioni del tenant durante questo periodo. Solo gli utenti che dispongono di una licenza di valutazione possono accedere alle esperienze utente di Viva Topics.

#### <a name="roles"></a>Ruoli

Durante la versione di valutazione, è necessario che siano attivi tre ruoli, descritti nella tabella seguente.

|Ruolo  |Attività  |
|---------|---------|
|Responsabile delle informazioni     |   Controllare le fasi del ciclo di vita degli argomenti; confermare e rimuovere argomenti; agire come community manager per i collaboratori di argomenti      |
|Collaboratore dell'argomento    |      Esperti in materia di contenuto, che possono:<br> Esaminare gli argomenti per valutare la qualità del contenuto definito dall'IA<br>Cura gli argomenti individuati con contenuto aggiuntivo<br>Creare argomenti aggiuntivi che non sono stati individuati dall'IA   |
|Consumer argomento    |     Usare gli argomenti tramite le evidenziazioni delle pagine e la ricerca<br>Fornire feedback sul valore degli argomenti presentati    |

#### <a name="expected-topics"></a>Argomenti previsti

Può essere utile documentare gli argomenti che si prevede di generare dall'IA, anche se si basa solo su presupposti. Questa attività viene completata più facilmente quando si indicizza un sottoinsieme definito dei siti SharePoint per i quali le PMI possono essere facilmente identificate.

La presenza di un elenco documentato consente di:

- Esamina l'elenco degli argomenti generati dall'IA, che potrebbero essere più grandi del previsto.
- Conoscere gli argomenti che potrebbe essere necessario creare manualmente o che sono le priorità per la curazione.

Ci sarà sempre bisogno di una combinazione di argomenti definiti dall'IA e creati dall'utente in una corretta distribuzione o prova di Viva Topics.

## <a name="activate-a-trial"></a>Attivare una versione di valutazione

Quando avvii una versione di valutazione, devi:

- Assegnare licenze agli utenti pertinenti.
- Eseguire [la configurazione aggiuntiva](set-up-topic-experiences.md) di Viva Topics.

Quando la versione di valutazione viene attivata, inizia il processo di individuazione degli argomenti.

## <a name="during-a-trial"></a>Durante una versione di valutazione

Il periodo di prova deve essere utilizzato per valutare i seguenti componenti di Viva Topics:

- Argomenti suggeriti dall'IA e contenuto degli argomenti
- Le esperienze dell'utente finale, le schede degli argomenti in SharePoint e in Microsoft Search

Prendere in considerazione questi fattori:

- Per offrire il massimo valore a Viva Topics, il contenuto degli argomenti deve essere una combinazione di contenuto definito dall'IA e contenuto curato dall'utente.
- Tutte le esperienze utente vengono "tagliate le autorizzazioni" (inclusa la visualizzazione del responsabile della conoscenza nella **pagina Gestisci** argomenti). Gli utenti potranno visualizzare un argomento solo se dispongono delle autorizzazioni per visualizzare alcune delle risorse utilizzate per generare l'argomento. Ciò significa che utenti diversi potrebbero visualizzare contenuto diverso nella stessa pagina dell'argomento.
- Gli utenti potrebbero visualizzare più argomenti con lo stesso nome nella **pagina Gestisci** argomenti. Questi argomenti non sono necessariamente duplicati, ma possono essere a causa di un singolo termine utilizzato in più contesti nei dati, ad esempio un nome di codice di progetto utilizzato da due progetti distinti.

## <a name="after-a-trial"></a>Dopo una versione di valutazione

In base al risultato della versione di valutazione, è possibile decidere se procedere con l'uso in produzione di Viva Topics.

### <a name="proceed-to-production-use"></a>Passare all'uso in produzione

Per garantire la continuità del servizio, è necessario acquistare il numero necessario di licenze e assegnarle agli utenti. Gli utenti di prova che non dispongono di una licenza completa alla fine del periodo di prova non potranno accedere ad alcuna esperienza Viva Topics.

### <a name="dont-proceed-to-production-use"></a>Non procedere con l'uso in produzione

Se non acquisti licenze dopo la versione di valutazione:

- L'individuazione degli argomenti verrà interrotta.
- Gli utenti non potranno più visualizzare le evidenziazioni o le schede degli argomenti.
- Il Centro argomenti non verrà eliminato, ma gli argomenti suggeriti e le esperienze di gestione degli argomenti non saranno disponibili.
- Tutti gli argomenti definiti dall'IA andranno persi.
- Gli argomenti modificati da un collaboratore di argomenti rimarranno nella raccolta pagine del Centro argomenti. Solo il contenuto fornito manualmente rimarrà in queste pagine, non qualsiasi contenuto suggerito dall'IA.

## <a name="see-also"></a>Vedere anche

[Introduzione all'adozione di Microsoft Viva Topics](topics-adoption-getstarted.md)

