---
title: Pianificare le esperienze degli argomenti in Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come pianificare le esperienze di argomento in Microsoft 365
ms.openlocfilehash: 153937cf6bc4a12f0a27866204b2286c343ddf55
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668226"
---
# <a name="plan-topic-experiences-in-microsoft-365"></a>Pianificare le esperienze degli argomenti in Microsoft 365

È possibile controllare il modo in cui gli argomenti sono stati sperimentati nell'organizzazione. Le decisioni di pianificazione per le esperienze di argomento garantiscono che gli argomenti di alta qualità vengano visualizzati dagli utenti e dispongano delle autorizzazioni appropriate per utilizzare e contribuire alla conoscenza.

In questo articolo verranno esaminate le decisioni di pianificazione seguenti:

- I siti di SharePoint di cui si desidera eseguire la ricerca per indicizzazione.
- Quali argomenti, se presenti, si desidera escludere da esperienze di argomento
- Gli utenti a cui si desidera rendere visibili gli argomenti.
- Gli utenti che si desidera concedere le autorizzazioni per la gestione degli argomenti nell'argomento centro.
- Gli utenti che si desidera concedere le autorizzazioni per la creazione o la modifica di argomenti nel centro argomenti.
- Il nome che si desidera assegnare al centro dell'argomento.

La sicurezza e la privacy dei dati vengono rispettate e le esperienze degli argomenti non conferiscono agli utenti un accesso supplementare ai file di cui non dispongono i diritti. Si consiglia di leggere anche [argomenti sulla sicurezza e la privacy](topic-experiences-security-privacy.md) nell'ambito del processo di pianificazione.

## <a name="requirements"></a>Requisiti

È necessario essere un amministratore globale o un amministratore di SharePoint per accedere all'interfaccia di amministrazione di Microsoft 365 e impostare le esperienze degli argomenti.

Tutti gli utenti che utilizzeranno le esperienze degli argomenti richiedono una licenza per l' **argomento experiences** . L'assegnazione delle licenze è [configurata in set up topic experiences](set-up-topic-experiences.md).

## <a name="topic-discovery"></a>Individuazione degli argomenti

L'argomento Discovery Settings specifica i siti di SharePoint utilizzati come origini per gli argomenti. È possibile scegliere di includere tutti i siti di SharePoint, un elenco specifico di siti o nessun sito. È consigliabile scegliere tutti i siti in modo che le esperienze degli argomenti possano scoprire un numero elevato di elementi validi per gli utenti.

Quando si configurano le esperienze degli argomenti, è possibile scegliere tra le opzioni seguenti:

- **Tutti i siti**: tutti i siti di SharePoint nell'organizzazione. Sono inclusi i siti correnti e futuri.
- **Tutti, tranne i siti selezionati**: tutti i siti ad eccezione di quelli specificati. I siti creati in futuro verranno inclusi come origini per l'individuazione degli argomenti. 
- **Solo i siti selezionati**: solo i siti specificati. I siti creati in futuro non verranno inclusi come origini per l'individuazione degli argomenti.
- **Nessun sito**: non includere alcun sito di SharePoint.

Se si sceglie **tutto, tranne i siti selezionati** o **solo i siti selezionati**, è possibile caricare un file con estensione CSV con un elenco di siti. Queste opzioni sono utili se si sta eseguendo un progetto pilota e si desidera includere un numero limitato di siti da avviare.

È possibile copiare il modello CSV seguente:

``` csv
Site name,URL
```

Non è consigliabile scegliere **nessun sito** perché impedisce la creazione o l'aggiornamento automatico degli argomenti. Tuttavia, è possibile scegliere questa opzione se si desidera configurare le esperienze degli argomenti e quindi aggiungere i siti in un secondo momento.

È consigliabile creare un processo per gli utenti o i responsabili della Knowledge base per richiedere la rimozione di singoli siti dall'argomento Discovery, se necessario nell'organizzazione.

## <a name="user-permissions"></a>Autorizzazioni utenti

Le autorizzazioni utente specificate determinano quali persone nell'organizzazione interagiscono con gli argomenti e cosa possono fare.

*Gestire gli argomenti*

I Knowledge Manager predispongono la qualità delle informazioni, il modo in cui le procedure consigliate sono strutturate e altre nell'organizzazione. Possono confermare e rifiutare gli argomenti.

Anche se è possibile specificare singoli responsabili degli argomenti, è consigliabile creare un gruppo di sicurezza (o utilizzarne uno esistente) che contenga le persone che si desidera siano responsabili della conoscenza. È possibile specificare questo gruppo di sicurezza durante il processo di installazione.

*Creare e modificare gli argomenti*

I collaboratori degli argomenti sono i campioni e gli esperti dell'organizzazione. Possono creare e modificare gli argomenti. 

Si consiglia di consentire a tutti gli utenti dell'organizzazione di creare e modificare gli argomenti, perché l'argomento è più adatto quando si possono condividere informazioni.

Se si desidera limitare la creazione e la modifica di argomenti a specifiche persone o gruppi, creare un gruppo di sicurezza per gli utenti e specificarlo durante il processo di installazione.

È possibile scegliere di non consentire a tutti di contribuire agli argomenti, ma questo non è consigliato. I Knowledge Manager saranno comunque in grado di modificare e creare argomenti.

*Visualizzatori di argomenti*

L'argomento visualizzatori può visualizzare le informazioni sulle pagine degli argomenti, nei risultati della ricerca e quando vengono evidenziati nei contenuti come pagine di SharePoint. Gli utenti possono visualizzare solo gli argomenti individuati quando hanno accesso ai file e alle pagine in cui è stato individuato l'argomento.

Quando si configurano i visualizzatori di argomenti, è possibile scegliere tra:

- **Tutti gli utenti dell'organizzazione**
- **Solo persone o gruppi di sicurezza selezionati**
- **Nessuno**

Si consiglia a tutti gli utenti **dell'organizzazione**, ma se si sta eseguendo un progetto pilota, è possibile scegliere solo persone o gruppi di sicurezza selezionati. È inoltre possibile scegliere **nessuno** se si desidera configurare le esperienze di argomento, ma non consentire agli utenti di visualizzare gli argomenti. (I Knowledge Manager avranno comunque accesso per consentire loro di visualizzare gli argomenti e aiutare con la decisione di rendere le esperienze di argomento ampiamente disponibili.)

## <a name="knowledge-rules"></a>Regole di conoscenza

In qualità di amministratore, è possibile escludere determinati argomenti dalle esperienze di argomento. Questa operazione è utile se si desidera mantenere i dati riservati che vengono visualizzati negli argomenti. Anche se i responsabili della conoscenza possono escludere gli argomenti nel centro argomenti, i soggetti esclusi dall'amministratore non sono neanche visibili ai responsabili della Knowledge base. I Knowledge Manager possono inoltre rimuovere gli argomenti nell'argomento centro dopo l'individuazione.

Se si desidera escludere gli argomenti a livello di amministratore, è necessario aggiungerli a un file. csv e caricare il file. È possibile eseguire questa operazione durante l'installazione o versione successiva.

Il file. csv deve contenere i seguenti parametri:

- **Nome**: digitare il nome dell'argomento che si desidera escludere. Questa operazione può essere eseguita in due modi:
- **MatchType-exact/partial**: digitare se il nome immesso è un tipo di corrispondenza *esatta* o *parziale* .
    - Corrispondenza esatta: è possibile includere il nome o l'acronimo esatto (ad esempio, *Contoso* o *ATL*).
    - Corrispondenza parziale: è possibile escludere tutti gli argomenti in cui è presente una parola specifica.  Ad esempio, *Arc* escluderà tutti gli argomenti con l' *arco* di parola in esso, ad esempio *cerchio arco*, *saldatura ad arco al plasma* o *arco di training*. Tenere presente che non verranno esclusi gli argomenti in cui il testo viene incluso come parte di una parola, ad esempio l' *architettura*.
- Acronimo **di (facoltativo)**: (noto anche come *espansione*) se si desidera escludere un acronimo, digitare le parole in cui si trova l'acronimo.

    ![Escludi argomenti nel modello CSV](../media/exclude-topics-csv.png) 

È possibile copiare il modello CSV seguente:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a>Amministrazione

Quando si configurano le esperienze degli argomenti, come parte del processo di installazione, viene creato automaticamente un centro argomenti. Pensate a ciò che si desidera assegnare un nome al centro argomenti e a ciò che si desidera che l'URL sia. È possibile impostare sia il nome che l'URL come parte del processo di installazione ed è possibile modificare il nome, ma non l'URL, in un secondo momento nell'interfaccia di amministrazione di Microsoft 365. È possibile disporre di un solo centro argomenti.

## <a name="setup-checklist"></a>Elenco di controllo dell'installazione

Quando si configurano le esperienze degli argomenti, sono necessari gli elementi seguenti durante la procedura guidata di installazione:

> [!div class="checklist"]
> * Elenco dei siti da includere o escludere se non sono inclusi tutti i siti per l'individuazione degli argomenti
> * Gruppo di sicurezza per i visualizzatori di argomenti se non si consente a tutti gli utenti di visualizzare l'argomento
> * Gruppo di sicurezza per i collaboratori dell'argomento se non consente a tutti gli utenti di creare e modificare argomenti
> * Gruppo di sicurezza per l'argomento Knowledge managers se non consente a tutti gli utenti di gestire gli argomenti
> * Elenco di argomenti riservati da escludere dall'individuazione di un argomento
> * Un nome per il sito Centro argomenti

## <a name="see-also"></a>Vedere anche

[Configurare le esperienze degli argomenti](set-up-topic-experiences.md)

[Gestire l'individuazione degli argomenti in Microsoft 365](topic-experiences-discovery.md)

[Gestire la visibilità degli argomenti in Microsoft 365](topic-experiences-knowledge-rules.md)

[Gestire le autorizzazioni per l'argomento in Microsoft 365](topic-experiences-user-permissions.md)

[Modificare il nome del centro argomenti in Microsoft 365](topic-experiences-administration.md)
