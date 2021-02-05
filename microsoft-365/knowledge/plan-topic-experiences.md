---
title: Pianificare gli argomenti di Microsoft Viva
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Informazioni su come pianificare gli argomenti relativi alla pianificazione per Microsoft Viva
ms.openlocfilehash: 65983f342b3277d33c7bfeb21d8481b1d3d5e817
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107955"
---
# <a name="plan-for-microsoft-viva-topics"></a>Pianificare gli argomenti di Microsoft Viva

È possibile controllare la modalità di utilizzo degli argomenti nell'organizzazione. Le decisioni relative alla pianificazione per gli argomenti assicurano che gli argomenti di alta qualità siano visualizzati agli utenti e che gli utenti siano autorizzati a utilizzare e contribuire alle proprie conoscenze.

In questo articolo verranno esaminate queste decisioni di pianificazione:

- Quali siti di SharePoint si desidera sotto ricercare per indicizzazione per gli argomenti
- Quali argomenti, se presenti, si desidera escludere dalle esperienze degli argomenti
- Utenti a cui si desidera rendere visibili gli argomenti
- Quali utenti si desidera concedere le autorizzazioni per gestire gli argomenti nel Centro argomenti
- Utenti a cui si desidera concedere le autorizzazioni per creare o modificare argomenti nel Centro argomenti
- Nome da assegnare al Centro argomenti

La sicurezza e la privacy dei dati vengono rispettate e le esperienze degli argomenti non concedono agli utenti ulteriori accessi ai file per cui non hanno diritti. È consigliabile leggere anche [microsoft Viva Topics sulla sicurezza e la privacy](topic-experiences-security-privacy.md) nell'ambito del processo di pianificazione.

## <a name="requirements"></a>Requisiti

È necessario essere un amministratore globale o un amministratore di SharePoint per accedere all'interfaccia di amministrazione di Microsoft 365 e configurare Gli argomenti.

Tutti gli utenti che useranno gli argomenti necessitano di **una licenza Per le esperienze di** argomento. L'assegnazione delle licenze è trattata in [Configurare Microsoft Viva Topics.](set-up-topic-experiences.md)

## <a name="topic-discovery"></a>Individuazione degli argomenti

Le impostazioni di individuazione degli argomenti specificano quali siti di SharePoint vengono utilizzati come origini per gli argomenti. È possibile scegliere di includere tutti i siti di SharePoint, un elenco specifico di siti o nessun sito. È consigliabile scegliere tutti i siti in modo che le esperienze degli argomenti possano individuare un gran numero di argomenti per gli utenti.

Quando si configurano gli argomenti, è possibile scegliere tra le opzioni seguenti:

- **Tutti i siti:** tutti i siti di SharePoint nell'organizzazione. Sono inclusi i siti correnti e futuri.
- **Tutti, ad eccezione dei siti selezionati:** tutti i siti ad eccezione di quelli specificati. I siti creati in futuro verranno inclusi come origini per l'individuazione degli argomenti. 
- **Solo i siti selezionati:** solo i siti specificati. I siti creati in futuro non verranno inclusi come origini per l'individuazione degli argomenti.
- **Nessun sito:** non includere alcun sito di SharePoint.

Se si sceglie **Tutti, ad eccezione dei** siti selezionati o Solo i siti **selezionati,** è possibile caricare un file CSV con un elenco di siti. Queste opzioni sono utili se si sta eseguendo un progetto pilota e si desidera includere un numero limitato di siti da avviare.

È possibile copiare il modello csv seguente:

``` csv
Site name,URL
```

Non è consigliabile scegliere **Nessun sito perché** impedisce la creazione o l'aggiornamento automatico degli argomenti. È tuttavia possibile scegliere questa opzione se si desidera configurare Argomenti e quindi aggiungere siti in un secondo momento.

È consigliabile creare un processo per consentire agli utenti o ai knowledge manager di richiedere la rimozione di singoli siti dall'individuazione degli argomenti, se necessario nell'organizzazione.

## <a name="user-permissions"></a>Autorizzazioni utenti

Le autorizzazioni utente specificate determinano quali persone nell'organizzazione interagiscono con gli argomenti e cosa possono fare.

*Gestire gli argomenti*

I knowledge manager supervisionano la qualità delle informazioni, il modo in cui è strutturata e altre procedure consigliate nell'organizzazione. Possono confermare e rifiutare gli argomenti.

Anche se è possibile specificare singoli responsabili degli argomenti, è consigliabile creare un gruppo di sicurezza (o utilizzarne uno esistente) contenente le persone che si desidera siano responsabili delle conoscenze. È possibile specificare questo gruppo di sicurezza durante il processo di installazione.

*Creare e modificare argomenti*

I collaboratori degli argomenti sono i campioni e gli esperti in materia nell'organizzazione. Possono creare e modificare argomenti. 

È consigliabile consentire a tutti gli utenti dell'organizzazione di creare e modificare argomenti perché le esperienze degli argomenti funzionano al meglio quando tutti gli utenti possono condividere informazioni.

Se si desidera limitare la creazione e la modifica di argomenti a utenti o gruppi specifici, creare un gruppo di sicurezza e specificarlo durante il processo di installazione.

È possibile scegliere di non consentire a nessuno di contribuire agli argomenti, ma non è consigliabile. Se si sceglie questa opzione, i knowledge manager potranno comunque modificare e creare argomenti.

*Visualizzatori di argomenti*

I visualizzatori di argomenti possono visualizzare informazioni sulle pagine degli argomenti, nei risultati della ricerca e quando gli argomenti vengono evidenziati nel contenuto come le pagine di SharePoint. Gli utenti possono visualizzare gli argomenti individuati solo quando hanno accesso ai file e alle pagine in cui è stato individuato l'argomento.

Quando si configurano i visualizzatori di argomenti, è possibile scegliere tra:

- **Tutti gli utenti dell'organizzazione**
- **Solo utenti o gruppi di sicurezza selezionati**
- **Nessuno**

È **consigliabile usare tutti gli** utenti dell'organizzazione, ma se si sta eseguendo un progetto pilota è consigliabile scegliere solo utenti o gruppi di sicurezza selezionati. È anche possibile scegliere **Nessuno se** si desidera configurare Gli argomenti, ma non consentire agli utenti di visualizzare ancora gli argomenti. I responsabili della conoscenza avranno comunque accesso per consentire loro di visualizzare gli argomenti e ottenere assistenza per la decisione di rendere gli argomenti disponibili su vasta gamma.

## <a name="knowledge-rules"></a>Regole di conoscenza

Gli amministratori possono escludere determinati argomenti dalle esperienze degli argomenti. Ciò è utile se si desidera evitare che i dati sensibili appaiano negli argomenti. Anche se i knowledge manager possono escludere gli argomenti nel Centro argomenti, gli argomenti esclusi dall'amministratore non sono nemmeno visibili ai knowledge manager. I knowledge manager possono anche rimuovere gli argomenti nel Centro argomenti dopo l'individuazione.

Se si desidera escludere gli argomenti a livello di amministratore, è necessario aggiungerli a un file CSV e caricarlo. È possibile eseguire questa operazione durante l'installazione o in un secondo momento.

Il file CSV deve contenere i parametri seguenti:

- **Nome**: digitare il nome dell'argomento che si desidera escludere. Questa operazione può essere eseguita in due modi:
- **MatchType-Exact/Partial:** specificare se il nome immesso è un *tipo* di corrispondenza esatto *o* parziale.
    - Corrispondenza esatta: è possibile includere il nome esatto o l'acronimo (ad esempio, *Contoso* o *ATL).*
    - Corrispondenza parziale: è possibile escludere tutti gli argomenti che includono una parola specifica.  Ad esempio, *l'arco* escluderà tutti gli argomenti con la parola arco *al* suo interno, ad esempio arco *circolare,* saldatura arco *di plasma* o arco *di formazione.* Si noti che non verranno esclusi gli argomenti in cui il testo è incluso come parte di una parola, ad esempio *Architecture.*
- **Acronimo di (facoltativo):**(noto anche come *espansione)* Se si desidera escludere un acronimo, digitare le parole che l'acronimo sta per.

    ![Escludere gli argomenti nel modello CSV](../media/exclude-topics-csv.png) 

È possibile copiare il modello csv seguente:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a>Amministrazione

Quando si configurano gli argomenti, durante il processo di configurazione viene creato automaticamente un centro argomenti. Pensa a cosa vuoi assegnare un nome al Centro argomenti e a cosa vuoi che sia l'URL. È possibile impostare sia il nome che l'URL come parte del processo di configurazione e modificare il nome (ma non l'URL) in un secondo momento nell'interfaccia di amministrazione di Microsoft 365. È possibile avere un solo centro argomenti.

## <a name="setup-checklist"></a>Elenco di controllo per l'installazione

Quando si configurano le esperienze degli argomenti, sono necessari gli elementi seguenti durante l'installazione guidata:

> [!div class="checklist"]
> * Elenco di siti da includere o escludere se non sono inclusi tutti i siti per l'individuazione degli argomenti
> * Gruppo di sicurezza per i visualizzatori di argomenti se non si consente a tutti gli utenti di visualizzare gli argomenti
> * Gruppo di sicurezza per i collaboratori di argomenti se non si consente a tutti gli utenti di creare e modificare argomenti
> * Gruppo di sicurezza per i knowledge manager degli argomenti se non si consente a tutti gli utenti di gestire gli argomenti
> * Elenco di argomenti sensibili da escludere dall'individuazione degli argomenti
> * Un nome per il sito Centro argomenti

## <a name="see-also"></a>Vedere anche

[Configurare le esperienze dell'argomento](set-up-topic-experiences.md)

[Gestire l'individuazione degli argomenti in Microsoft 365](topic-experiences-discovery.md)

[Gestire la visibilità degli argomenti in Microsoft 365](topic-experiences-knowledge-rules.md)

[Gestire le autorizzazioni per gli argomenti in Microsoft 365](topic-experiences-user-permissions.md)

[Modificare il nome del Centro argomenti in Microsoft 365](topic-experiences-administration.md)
