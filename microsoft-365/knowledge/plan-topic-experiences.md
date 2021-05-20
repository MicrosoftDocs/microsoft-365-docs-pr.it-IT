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
ms.openlocfilehash: de7534ce58a7888ac822826ef4ef1b4934ed8cb1
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583113"
---
# <a name="plan-for-microsoft-viva-topics"></a>Pianificare gli argomenti di Microsoft Viva

L'utente ha il controllo dell'esperienza degli argomenti nell'organizzazione. Le decisioni di pianificazione per Gli argomenti assicurano che gli utenti siano in grado di visualizzare argomenti di alta qualità e di disporre delle autorizzazioni appropriate per l'utilizzo e il contributo delle conoscenze.

In questo articolo verranno esaminate queste decisioni di pianificazione:

- Quali SharePoint di ricerca per indicizzazione per gli argomenti
- Quali argomenti, se presenti, si desidera escludere dalle esperienze degli argomenti
- Utenti a cui si desidera rendere visibili gli argomenti
- Quali utenti si desidera concedere le autorizzazioni per gestire gli argomenti nel Centro argomenti
- Utenti a cui si desidera concedere le autorizzazioni per creare o modificare argomenti nel Centro argomenti
- Nome da assegnare al centro argomenti

La sicurezza e la privacy dei dati vengono rispettate e le esperienze degli argomenti non concedono agli utenti l'accesso aggiuntivo ai file a cui non hanno diritti. È consigliabile leggere anche [La sicurezza e la privacy](topic-experiences-security-privacy.md) di Microsoft Viva Topics nell'ambito del processo di pianificazione.

Per saperne di più sulla tecnologia IA alla base di Viva Topics, leggi [Alessandria in Microsoft Viva Topics: dai big data alle grandi conoscenze.](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge)

## <a name="requirements"></a>Requisiti

Devi essere [sottoscritto a Viva Topics](https://www.microsoft.com/microsoft-viva/topics) ed essere un amministratore globale o SharePoint amministratore per accedere all'interfaccia di amministrazione di Microsoft 365 e configurare Gli argomenti.

Tutti gli utenti che useranno Gli argomenti richiedono una **licenza esperienze di** argomento. L'assegnazione delle licenze è trattata in [Set up Microsoft Viva Topics.](set-up-topic-experiences.md)

## <a name="topic-discovery"></a>Individuazione argomenti

Le impostazioni di individuazione degli argomenti specificano i siti di SharePoint da usare come origini per gli argomenti. È possibile scegliere di includere tutti i siti di SharePoint, uno specifico elenco di siti o nessun sito. È consigliabile scegliere tutti i siti in modo che le esperienze degli argomenti possano individuare un gran numero di argomenti importanti per gli utenti.

Quando si configurano gli argomenti è possibile scegliere uno dei seguenti comandi:

- **Tutti i siti**: tutti i siti di SharePoint nell’organizzazione. Sono inclusi i siti correnti e futuri.
- **Tutti, ad eccezione dei siti specificati.**: tutti i siti ad eccezione di quelli specificati. I siti creati in futuro verranno inclusi come origini per l'individuazione degli argomenti. 
- **Solo siti selezionati:** solo i siti specificati. I siti creati in futuro non verranno inclusi come origini per l’individuazione di argomenti.
- **Nessun sito**: non includere siti di SharePoint.

Se si sceglie **Tutti,** ad eccezione dei siti selezionati o Solo i siti **selezionati,** è possibile caricare un file .csv con un elenco di siti. Queste opzioni sono utili se si sta eseguendo un progetto pilota e si desidera includere un numero limitato di siti da avviare.

Puoi copiare il modello .csv seguente:

``` csv
Site name,URL
```

Non è consigliabile scegliere **Nessun sito perché** impedisce la creazione o l'aggiornamento automatico degli argomenti. È tuttavia possibile scegliere questa opzione se si desidera configurare Gli argomenti e quindi aggiungere siti in un secondo momento.

È consigliabile creare un processo per consentire agli utenti o ai knowledge manager di richiedere la rimozione di singoli siti dall'individuazione degli argomenti, se necessario nell'organizzazione.

### <a name="multi-geo"></a>Multi-Geo

Se l'organizzazione ha distribuito [Microsoft 365 Multi-Geo,](/microsoft-365/enterprise/microsoft-365-multi-geo)viene eseguito il provisioning del Centro argomenti nella posizione centrale e solo i siti di SharePoint nella posizione centrale sono disponibili per l'utilizzo come origini per gli argomenti. Se si seleziona **Tutti i siti,** Viva Topics utilizzerà tutti i siti nella posizione centrale.

Tutte le operazioni di elaborazione e archiviazione del contenuto vengono eseguite nella posizione centrale.

## <a name="user-permissions"></a>Autorizzazioni utenti

Le autorizzazioni utente specificate determinano quali persone dell'organizzazione interagiscono con gli argomenti e cosa possono fare.

> [!Note] 
> Al momento, Viva Topics non supporta la fornitura di licenze o autorizzazioni utente per gli utenti Guest (esterni). 

*Gestisci argomenti*

I knowledge manager supervisionano la qualità delle informazioni, il modo in cui è strutturata e altre procedure consigliate nell'organizzazione. Possono confermare e rifiutare gli argomenti.

Sebbene sia possibile specificare singoli responsabili degli argomenti, è consigliabile creare un gruppo di sicurezza (o utilizzarne uno esistente) contenente le persone che si desidera siano responsabili della conoscenza. È possibile specificare questo gruppo di sicurezza durante il processo di installazione.

*Creare e modificare argomenti*

I collaboratori degli argomenti sono i campioni e gli esperti in materia nell'organizzazione. Possono creare e modificare argomenti. 

È consigliabile consentire a tutti gli utenti dell'organizzazione di creare e modificare argomenti perché le esperienze degli argomenti funzionano al meglio quando tutti gli utenti possono condividere informazioni.

Se si desidera limitare la creazione e la modifica di argomenti a utenti o gruppi specifici, creare un gruppo di sicurezza per loro e specificarlo durante il processo di installazione.

È possibile scegliere di non consentire a nessuno di contribuire agli argomenti, tuttavia non è consigliabile. Se si sceglie questa opzione, i knowledge manager potranno comunque modificare e creare argomenti.

*Visualizzatori dell'argomento*

I visualizzatori di argomenti possono visualizzare informazioni sulle pagine degli argomenti, nei risultati della ricerca e quando gli argomenti vengono evidenziati nel contenuto come SharePoint pagine. Gli utenti possono visualizzare gli argomenti individuati solo quando hanno accesso ai file e alle pagine in cui è stato individuato l'argomento.

Quando si configurano i visualizzatori di argomenti, è possibile scegliere tra:

- **Tutti gli utenti dell'organizzazione**
- **Solo utenti o gruppi di sicurezza selezionati**
- **Nessuno**

Si consiglia **a Tutti gli** utenti dell'organizzazione, ma se si sta eseguendo un progetto pilota è consigliabile scegliere solo persone o gruppi di sicurezza selezionati. È inoltre possibile scegliere **Nessuno** se si desidera configurare Gli argomenti, ma non consentire agli utenti di visualizzare gli argomenti. I knowledge manager avranno comunque accesso per consentire loro di visualizzare gli argomenti e di ottenere assistenza per la decisione di rendere gli argomenti ampiamente disponibili.

## <a name="knowledge-rules"></a>Regole della knowledge base

Gli amministratori possono escludere determinati argomenti dalle esperienze degli argomenti. Ciò è utile se si desidera evitare che i dati sensibili appaiano negli argomenti. Anche se i knowledge manager possono escludere gli argomenti nel Centro argomenti, gli argomenti esclusi dall'amministratore non sono nemmeno visibili ai knowledge manager. I responsabili della conoscenza possono anche rimuovere gli argomenti nel Centro argomenti dopo l'individuazione.

Se si desidera escludere gli argomenti a livello di amministratore, è necessario aggiungerli a un .csv file e caricare il file. È possibile eseguire questa operazione durante l'installazione o in un secondo momento.

Il .csv file deve contenere i parametri seguenti:

- **Nome**: digitare il nome dell’argomento da escludere. È possibile eseguire questa operazione in due modi:
- **MatchType-Exact/Partial**: Digitare se il nome immesso è un *tipo* di corrispondenza esatto *o* parziale.
    - Corrispondenza esatta: è possibile includere il nome esatto o l'acronimo (ad esempio, *Contoso* o *ATL).*
    - Corrispondenza parziale: è possibile escludere tutti gli argomenti che includono una parola specifica.  Ad esempio, *arco* escluderà tutti gli argomenti con la parola arco *al* suo interno, ad esempio Cerchio *arco,* *Saldatura* arco di plasma o *Arco di formazione.* Si noti che non verranno esclusi gli argomenti in cui il testo è incluso come parte di una parola, ad esempio *Architettura*.
- **Sta per (facoltativo):**(noto anche come espansione *)* Se si desidera escludere un acronimo, digitare le parole che l'acronimo sta per.

    ![Escludere gli argomenti nel modello CSV](../media/exclude-topics-csv.png) 

È possibile copiare il modello csv seguente:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a>Amministrazione

Quando si configurano gli argomenti, come parte del processo di installazione, viene creato automaticamente un centro argomenti. Pensa a cosa vuoi assegnare un nome al Centro argomenti e a cosa vuoi che sia l'URL. È possibile impostare sia il nome che l'URL come parte del processo di installazione ed è possibile modificare il nome (ma non l'URL) in un secondo momento nell'interfaccia di amministrazione di Microsoft 365. È possibile avere un solo centro argomenti.

## <a name="setup-checklist"></a>Elenco di controllo per l'installazione

Quando si configurano le esperienze degli argomenti, durante l'installazione guidata saranno necessari gli elementi seguenti:

> [!div class="checklist"]
> * Elenco dei siti da includere o escludere se non si includono tutti i siti per l'individuazione di argomenti
> * Gruppo di sicurezza per visualizzatori di argomenti se non si consente a tutti gli utenti di visualizzare gli argomenti
> * Gruppo di sicurezza per collaboratori di argomenti se non si consente a tutti gli utenti di creare e modificare gli argomenti
> * Gruppo di sicurezza per responsabili delle informazioni di argomenti se non si consente a tutti gli utenti di gestire gli argomenti
> * Elenco di argomenti sensibili da escludere dall'individuazione degli argomenti
> * Nome del sito Centro argomenti

## <a name="see-also"></a>Vedere anche

[Configurare le esperienze dell'argomento](set-up-topic-experiences.md)

[Gestire l'individuazione degli argomenti in Microsoft 365](topic-experiences-discovery.md)

[Gestire la visibilità degli argomenti in Microsoft 365](topic-experiences-knowledge-rules.md)

[Gestire le autorizzazioni per gli argomenti in Microsoft 365](topic-experiences-user-permissions.md)

[Modificare il nome del centro argomenti in Microsoft 365](topic-experiences-administration.md)
