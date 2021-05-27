---
title: Introduzione ai tipi di informazione sensibile personalizzati
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informazioni su come creare, modificare, rimuovere e testare tipi di informazioni riservate personalizzati per DLP nel Centro sicurezza & conformità.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 911d2dc3a4adeb79e2b41f3a450bbc446feee916
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683844"
---
# <a name="get-started-with-custom-sensitive-information-types"></a>Introduzione ai tipi di informazione sensibile personalizzati

Se i tipi di informazione sensibile preconfigurati non soddisfano le tue esigenze, puoi creare il tuoi tipi di informazione sensibile personalizzati, definendoli completamente oppure copiando e modificando uno dei tipi preconfigurati.

I tipi di informazione sensibile personalizzati creati con questo metodo vengono aggiunti al pacchetto di regole denominato `Microsoft.SCCManaged.CustomRulePack`.

È possibile creare un nuovo tipo di informazione sensibile in due modi:

- [iniziando da zero e definendo completamente tutti gli elementi](#create-a-custom-sensitive-information-type)
- [copiando e modificando un tipo di informazione sensibile esistente](#copy-and-modify-a-sensitive-information-type)


## <a name="before-you-begin"></a>Prima di iniziare

- Bisogna avere preso familiarità con i tipi di informazione sensibile e con i loro elementi. Vedere, [Informazioni sui tipi di informazione sensibile](sensitive-information-type-learn-about.md). È fondamentale comprendere i ruoli di:
    - [espressioni regolari](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/) - i tipi di informazione sensibile di Microsoft 365 usano il motore Boost.RegEx 5.1.3
    - elenchi di parole chiave - è possibile creare il proprio elenco definendo un tipo di informazione sensibile personalizzato o scegliendone uno dall'elenco delle parole chiave
    - [dizionario di parole chiave](create-a-keyword-dictionary.md)
    - [funzioni](what-the-dlp-functions-look-for.md)
    - [livello di confidenza](sensitive-information-type-learn-about.md#more-on-confidence-levels)
 
- È necessario avere le autorizzazioni di amministrazione globale o di amministrazione della conformità per creare, collaudare e distribuire un tipo personalizzato di informazione riservata tramite l'interfaccia utente. Vedere [Informazioni sui ruoli di amministratore](/office365/admin/add-users/about-admin-roles?view=o365-worldwide) di Office 365.

- L'organizzazione deve disporre di un abbonamento, ad esempio Office 365 Enterprise, che includa le funzionalità per la prevenzione della perdita dei dati (DLP). Vedere la descrizione del servizio [Criteri di messaggistica e conformità](/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc). 


> [!IMPORTANT]
> Il Supporto tecnico Microsoft non può dare assistenza con la creazione di classificazioni personalizzate o modelli di espressioni regolari. I tecnici del supporto possono fornire supporto limitato per la funzionalità, ad esempio fornire esempi di modelli di espressioni regolari a scopo di test o aiutare nella risoluzione dei problemi di un modello di espressione regolare esistente che non si attiva come previsto. Non possono garantire che qualsiasi sviluppo personalizzato di corrispondenza del contenuto soddisfi i requisiti o gli obblighi del cliente.

## <a name="create-a-custom-sensitive-information-type"></a>Creare un tipo di informazione sensibile personalizzato

Segui questa procedura per creare un nuovo tipo di informazione sensibile che puoi definire completamente. 

1. Nel Centro conformità, vai a **Classificazione dati** \> **Tipi di informazione sensibile** e scegli **Crea tipo di informazione**.
2. Compila i campi **Nome** e **Descrizione** e seleziona **Avanti**.
3. Seleziona **Crea configurazione**. Puoi creare più configurazioni, ciascuna con differenti elementi e livelli di confidenza, mentre definisci il tuo nuovo tipo di informazione sensibile.
4. Scegli il livello di confidenza predefinito per la configurazione. I valori sono **Bassa confidenza**, **Media confidenza**, e **Alta confidenza**.
5. Scegli e definisci l'**elemento primario**. L'elemento primario può essere una **espressione regolare** con una convalida facoltativa, un **elenco di parole chiave**, un **dizionario di parole chiave**, oppure una delle **funzioni** preconfigurate. Per altre informazioni sulle funzioni DLP, vedere [Elementi cercati dalle funzioni dei criteri di prevenzione della perdita dei dati](what-the-dlp-functions-look-for.md). Per ulteriori informazioni sulla data e sui validator di checksum, vedere [More information on regular expression validators](#more-information-on-regular-expression-validators).
6. Immetti un valore per **Prossimità caratteri**.
7. (Facoltativo) Aggiungi gli elementi di supporto, se disponibili. Gli elementi di supporto possono essere espressioni regolari con una convalida facoltativa, elenchi o dizionari di parole chiave, oppure una delle funzioni preconfigurate. Gli elementi di supporto possono avere una propria **configurazione di prossimità del** carattere. 
8. (Facoltativo) Aggiungi eventuali [**altri controlli**](#more-information-on-additional-checks) dall'elenco dei controlli disponibili.
9. Scegli **Crea**.
10. Scegli **Avanti**.
11. Scegli il **livello di confidenza consigliato** per questo tipo di informazione sensibile.
12. Verifica le tue impostazioni e scegli **Invia**.

> [!IMPORTANT]
> Microsoft 365 usa il crawler di ricerca per identificare e classificare le informazioni sensibili nei siti di SharePoint Online e OneDrive for Business. Per identificare il nuovo tipo di informazioni sensibili personalizzato nel contenuto esistente, è necessario ripetere la ricerca per indicizzazione del contenuto. Il contenuto viene sottoposto a ricerca per indicizzazione in base a una pianificazione, ma è possibile ripetere manualmente la ricerca per indicizzazione del contenuto per una raccolta siti, un elenco o una raccolta. Per altre informazioni, vedere [Richiedere manualmente la ricerca per indicizzazione e la reindicizzazione di un sito, di una raccolta o di un elenco](/sharepoint/crawl-site-content).

13. Nella pagina **Classificazione dati** saranno mostrate tutti i tipi di informazione sensibile inclusi nell'elenco. Scegli **Aggiorna**, quindi cerca oppure usa lo strumento di ricerca per trovare il tipo di informazione sensibili creato.

## <a name="test-a-sensitive-information-type"></a>Collaudare i tipi di informazione sensibile

Puoi collaudare qualsiasi tipo di informazione sensibile dell'elenco. Ti suggeriamo di collaudare ogni tipo di informazione sensibile che hai creato prima di usarlo in un criterio.

1. Prepara due file, come un documento Word. Uno con un contenuto che corrisponda agli elementi specificati nel tipi di informazione sensibile, e uno che non gli corrisponde.
2. Nel Centro conformità, vai a **Classificazione dati** \> **Tipi di informazione sensibile** e scegli il tipo di informazione sensibile dall'elenco per aprire il riquadro dei dettagli, e seleziona **Test**.
3. Carica un file e seleziona **Test**.
4. Nella pagina **Risultati abbinamenti**, rivedi i risultati e seleziona **Fine**.

## <a name="modify-custom-sensitive-information-types-in-the-compliance-center"></a>Modificare tipi di informazione sensibile personalizzati nel Centro conformità

1. Nel Centro conformità, vai a **Classificazione dati** \> **Tipi di informazione sensibile**, scegli il tipo di informazione sensibile che vuoi rimuovere dall'elenco e seleziona **Modifica**.
2. Puoi aggiungere altre configurazioni, con elementi principali e di supporto, livelli di confidenza, prossimità dei caratteri e [**controlli aggiuntivi specifici**](#more-information-on-additional-checks), oppure modificare/rimuovere quelle esistenti.

## <a name="remove-custom-sensitive-information-types-in-the-compliance-center"></a>Rimuovere tipi di informazione sensibile personalizzati nel Centro conformità 

> [!NOTE]
> È possibile rimuovere i tipi di informazioni sensibili personalizzati; non è possibile rimuovere quelli predefiniti.

> [!IMPORTANT]
> Prima di eliminare un tipo di informazioni sensibili personalizzato, verificare che nessun criterio DLP o regola del flusso di posta di Exchange (nota anche come regola di trasporto) faccia ancora riferimento al tipo di informazioni sensibili.

1. Nel Centro conformità, vai a **Classificazione dati** \> **Tipi di informazione sensibile** e scegli il tipo di informazione sensibile che vuoi rimuovere dall'elenco.
2. Seleziona **Elimina** nel riquadro a comparsa che si apre.

## <a name="copy-and-modify-a-sensitive-information-type"></a>Copiare e modificare un tipo di informazione sensibile

Usa questa procedura per creare un nuovo tipo di informazione sensibile basato su un tipo esistente. 

1. Nel Centro conformità, vai a **Classificazione dati** \> **Tipi di informazione sensibile**, e scegli il tipo di informazione sensibile che vuoi copiare.
2. Seleziona **Copia** nel riquadro a comparsa.
3. Seleziona **Aggiorna** nell'elenco dei tipi di informazione sensibile, e cerca la copia che hai appena creato. La ricerca di stringhe parziali funziona, perciò ti basta cercare `copy`, e la ricerca restituisce tutti i tipi di informazione sensibile che contengono la parola `copy` nel loro nome. 
4. Compila i campi **Nome** e **Descrizione** e seleziona **Avanti**.
5. Seleziona la copia del tuo tipi di informazione sensibile e fai clic su **Modifica**. 
6. Assegna al tipo di informazione sensibile un nuovo **Nome** e una nuova **Descrizione**.
7. Puoi scegliere di modificare o rimuovere le configurazioni esistenti e aggiungerne di nuove. Scegli il livello di confidenza predefinito per la nuova configurazione. I valori sono **Bassa confidenza**, **Media confidenza**, e **Alta confidenza**.
8. Scegli e definisci l'**elemento primario**. L'elemento primario può essere una **espressione regolare**, un **elenco di parole chiave**, un **dizionario di parole chiave**, oppure una delle **funzioni** preconfigurate. Vedi [Elementi cercati dalle funzioni dei criteri di prevenzione della perdita dei dati](what-the-dlp-functions-look-for.md).
9. Immetti un valore per **Prossimità caratteri**.
10. (Facoltativo) Se hai **Elementi di supporto** o [**Altri controlli**](#more-information-on-additional-checks), aggiungili. Se necessario, puoi raggruppare i tuoi **Elementi di supporto**.
11. Scegli **Crea**.
12. Scegli **Avanti**.
13. Scegli il **livello di confidenza consigliato** per questo tipo di informazione sensibile.
14. Verifica le tue impostazioni e scegli **Invia**.

È anche possibile creare tipi di informazioni sensibili personalizzati usando PowerShell e le funzionalità del classificatore Exact Data Match. Per altre informazioni su questi metodi, vedere:
- [Creare un tipo di informazioni sensibili personalizzato in PowerShell per Centro sicurezza e conformità](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Creare un tipo di informazioni sensibili personalizzato per DLP con Exact Data Match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

## <a name="more-information-on-regular-expression-validators"></a>Ulteriori informazioni sui validator delle espressioni regolari

### <a name="checksum-validator"></a>Checksum validator

Se è necessario eseguire un checksum su una cifra in un'espressione regolare, è possibile utilizzare *il validator del checksum.* Ad esempio, si supponga di dover creare un codice SIT per un numero di licenza a otto cifre in cui l'ultima cifra è una cifra di checksum convalidata utilizzando un calcolo mod 9. L'algoritmo di checksum è stato configurato in questo modo:
 
Sum = digit 1 * Weight 1 + digit 2 * weight 2 + digit 3 * weight 3 + digit 4 * weight 4 + digit 5 * weight 5 + digit 6 * weight 6 + digit 7 * weight 7 + digit 8 * weight 8 Mod value = Sum % 9 If Mod value == digit 8 Account number is valid If Mod value != digit 8 Account number is invalid

1. Definisci l'elemento primario con questa espressione regolare:

`\d{8}`

2. Aggiungi quindi il validator del checksum.
3. Aggiungi i valori di peso separati da virgole, la posizione della cifra di controllo e il valore Mod. Per ulteriori informazioni sull'operazione Modulo, vedere [Operazione modulo](https://en.wikipedia.org/wiki/Modulo_operation).

> [!NOTE]
> Se la cifra di controllo non fa parte del calcolo del checksum, utilizzare 0 come peso per la cifra di controllo. Ad esempio, nel caso precedente il peso 8 sarà uguale a 0 se la cifra di controllo non deve essere utilizzata per calcolare la cifra di controllo.  Modulo_operation).

![Screenshot of configured checksum validator](../media/checksum-validator.png)

### <a name="date-validator"></a>Convalida data

Se un valore di data incorporato nell'espressione regolare fa parte di  un nuovo modello che si sta creando, è possibile utilizzare la convalida della data per verificare che soddisfi i criteri specificati. Ad esempio, si supponga di voler creare un SIT per un numero di identificazione del dipendente di nove cifre. Le prime sei cifre sono la data di assunzione in formato DDMMYY e le ultime tre sono numeri generati casualmente. Per verificare che le prime sei cifre siano nel formato corretto. 

1. Definisci l'elemento primario con questa espressione regolare:

`\d{9}`

2. Aggiungi quindi il validator della data.
3. Selezionare il formato della data e lo scostamento iniziale. Poiché la stringa della data è la prima sei cifre, l'offset è `0` .

![Screenshot of configured date validator](../media/date-validator.png)

### <a name="functional-processors-as-validators"></a>Processori funzionali come validator

È possibile utilizzare i processori di funzioni per alcuni dei SIT più comunemente usati come validator. In questo modo è possibile definire un'espressione regolare personalizzata assicurandosi che superino i controlli aggiuntivi richiesti dal sit. Ad esempio, Func_India_Aadhar che l'espressione regolare personalizzata definita dall'utente passi la logica di convalida necessaria per la scheda Aadhar indiana. Per ulteriori informazioni sulle funzioni DLP che possono essere utilizzate come validator, vedere [What the DLP functions look for](what-the-dlp-functions-look-for.md#what-the-dlp-functions-look-for). 

### <a name="luhn-check-validator"></a>Convalida controllo Luhn

È possibile utilizzare il validator di controllo Luhn se si dispone di un tipo di informazioni riservate personalizzato che include un'espressione regolare che deve passare [l'algoritmo Luhn](https://en.wikipedia.org/wiki/Luhn_algorithm).

## <a name="more-information-on-additional-checks"></a>Maggiori informazioni sugli altri controlli

Ecco le definizioni e alcuni esempi per gli altri controlli disponibili.

**Escludi corrispondenze specifiche**: questo controllo consente di definire le parole chiave da escludere quando si rilevano le corrispondenze per i criteri che si stanno modificando. Ad esempio, è possibile escludere i numeri di carta di credito di prova come "4111111111111111" in modo che non possano corrispondere a un numero valido.

**Inizia o non inizia con caratteri**: questo controllo consente di definire i caratteri con cui gli elementi corrispondenti devono o non devono iniziare. Ad esempio, se si vuole che i criteri rilevino solo i numeri di carta di credito che iniziano con 41, 42 o 43, selezionare **Inizia con** e aggiungere 41, 42 e 43 all'elenco, separati da virgole. 

**Termina o non termina con caratteri**: questo controllo consente di definire i caratteri con cui gli elementi corrispondenti devono o non devono terminare. Ad esempio, se il numero ID del dipendente non può terminare con 0 o 1, selezionare **Non termina con** e aggiungere 0 e 1 all'elenco, separati da virgole.

**Escludi caratteri duplicati**: questo controllo consente di ignorare le corrispondenze in cui tutte le cifre sono uguali. Ad esempio, se il numero ID del dipendente a sei cifre non può avere tutte le stesse cifre uguali, è possibile selezionare **Escludi caratteri duplicati** per escludere 111111, 222222, 333333, 444444, 555555, 666666, 777777, 888888, 999999 e 000000 dall'elenco delle corrispondenze valide per l'ID dipendente.

**Includi o escludi i prefissi**: questo controllo consente di definire le parole chiave che devono o non devono trovarsi immediatamente prima dell'entità corrispondente. In base all'opzione selezionata, le entità saranno o meno considerate corrispondenze se sono precedute dai prefissi inclusi qui. Ad esempio, se si **esclude** il prefisso **GUID:**, qualsiasi entità preceduta da **GUID:** non verrà considerata una corrispondenza.

**Includi o escludi suffissi**: questo controllo consente di definire le parole chiave che devono o non devono trovarsi immediatamente dopo l'entità corrispondente. In base all'opzione selezionata, le entità saranno o meno considerate corrispondenze se sono seguite dai suffissi inclusi qui. Ad esempio, se si **esclude** il suffisso **:GUID**, qualunque testo seguito da **:GUID** non sarà considerato una corrispondenza.


> [!NOTE]
> Microsoft 365 Information Protection supporta, in anteprima, i set di caratteri a due byte nelle lingue seguenti:
> - Cinese (semplificato)
> - Cinese (tradizionale)
> - Coreano
> - Giapponese
>
>Il supporto è disponibile per i tipi di informazioni sensibili. Per altre informazioni, vedere [Note sulla versione del supporto della protezione delle informazioni per i set di caratteri a due byte (anteprima)](mip-dbcs-relnotes.md).