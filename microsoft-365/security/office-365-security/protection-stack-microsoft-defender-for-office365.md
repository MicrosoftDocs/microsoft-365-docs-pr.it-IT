---
title: Stack di protezione dalle minacce dettagliate in Microsoft Defender per Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/05/2021
ms.reviewer: gigarrub
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
description: Seguire il percorso di un messaggio in arrivo tramite lo stack di filtro delle minacce in Microsoft Defender per Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0760bd7a67f175e4af114324ccc729355ad5f593
ms.sourcegitcommit: 4e05f19c00e172b65f637f19ca461db5b21dff4e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51601390"
---
# <a name="step-by-step-threat-protection-in-microsoft-defender-for-office-365"></a>Protezione dettagliata dalle minacce in Microsoft Defender per Office 365

Lo stack di protezione o filtro di Microsoft Defender per Office 365 può essere suddiviso in 4 fasi, come in questo articolo. In generale, la posta in arrivo passa attraverso tutte queste fasi prima del recapito, ma il percorso effettivo della posta elettronica è soggetto alla configurazione defender per Office 365 di un'organizzazione.

> [!TIP]
> Rimanere sintonizzati fino alla fine di questo articolo per un grafico *unificato* di tutte e 4 le fasi di Defender per la protezione di Office 365!

## <a name="phase-1---edge-protection"></a>Fase 1 - Protezione edge

Purtroppo, i blocchi edge che una volta erano *critici* sono relativamente semplici da superare per i malinti. Nel corso del tempo, qui viene bloccato meno traffico, ma rimane una parte importante dello stack.  

I blocchi perimetrali sono progettati per essere automatici. In caso di falso positivo, ai mittenti verrà notificato e verrà spiegato come risolvere il problema. I connettori di partner attendibili con reputazione limitata possono garantire il recapito o le sostituzioni temporanee possono essere messe in atto durante l'onboarding di nuovi endpoint.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase1.png" alt-text="La fase 1 del filtro in Defender per Office 365 è Edge Protection.":::

1. **La limitazione della** rete protegge l'infrastruttura di Office 365 e i clienti da attacchi DoS (Denial of Service) limitando il numero di messaggi che possono essere inviati da un set specifico di infrastrutture.

2. **La reputazione IP e la limitazione** bloccano i messaggi inviati da indirizzi IP di connessione non validi noti. Se un IP specifico invia molti messaggi in un breve periodo di tempo, verranno limitate.

3. **La reputazione del** dominio blocterà tutti i messaggi inviati da un dominio non mittente noto.

4. **Il filtro perimetrale basato su directory** blocca i tentativi di raccogliere le informazioni della directory di un'organizzazione tramite SMTP.

5. **Il rilevamento dei backscatter** impedisce a un'organizzazione di essere attaccata tramite rapporti di mancato recapito (NDR) non validi.

6. **Il filtro avanzato per i connettori** mantiene le informazioni di autenticazione anche quando il traffico passa attraverso un altro dispositivo prima che raggiunga Office 365. Ciò migliora l'accuratezza dello stack di filtro, inclusi i modelli di clustering euristico, anti-spoofing e apprendimento automatico anti-phishing, anche in scenari di routing complessi o ibridi.

## <a name="phase-2---sender-intelligence"></a>Fase 2 - Sender Intelligence

Le funzionalità dell'intelligence mittente sono fondamentali per l'intercettazione di messaggi di posta indesiderata, in blocco, di rappresentazione e spoofing non autorizzati, oltre che per il rilevamento di falsi. La maggior parte di queste funzionalità è configurabile singolarmente.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase2.png" alt-text="La fase 2 del filtro in MDO è Sender intelligence.":::

1. **I trigger e gli** avvisi di rilevamento della compromissione dell'account vengono generati quando un account ha un comportamento anomalo, coerentemente con la compromissione. In alcuni casi, l'account utente viene bloccato e non può inviare ulteriori messaggi di posta elettronica fino a quando il problema non viene risolto dal team delle operazioni di sicurezza di un'organizzazione.

2. **L'autenticazione** della posta elettronica coinvolge sia i metodi configurati dal cliente che i metodi configurati nel cloud, allo scopo di garantire che i mittenti siano autorizzati e autenticati. Questi metodi resistono allo spoofing.
    - **SPF** può rifiutare i messaggi in base ai record TXT DNS che elencano gli indirizzi IP e i server autorizzati a inviare posta per conto dell'organizzazione.
    - **DKIM fornisce** una firma crittografata che autentica il mittente.
    - **DMARC** consente agli amministratori di contrassegnare SPF e DKIM come necessari nel proprio dominio e impone l'allineamento tra i risultati di queste due tecnologie.
    - **ARC** non è configurato dal cliente, ma si basa su DMARC per funzionare con l'inoltro nelle liste di distribuzione, durante la registrazione di una catena di autenticazione.

3. **L'intelligence** spoofing è in grado di filtrare gli utenti autorizzati a "spoofing" (ovvero quelli che inviano posta per conto di un altro account o inoltrano una lista di distribuzione) da spoofer dannosi che imitano un dominio esterno noto o dell'organizzazione. Separa la posta legittima "per conto di" dai mittenti che effettuano lo spoofing per recapitare messaggi di posta indesiderata e phishing. 

    **L'intelligence di spoofing tra** organizzazioni rileva e blocca i tentativi di spoofing da un dominio all'interno dell'organizzazione.

4. **L'intelligence di spoofing tra** domini rileva e blocca i tentativi di spoofing da un dominio esterno all'organizzazione.

5. **Il filtro in** blocco consente agli amministratori di configurare un livello di probabilità in blocco (BCL) che indica se il messaggio è stato inviato da un mittente in blocco. Gli amministratori possono usare il dispositivo di scorrimento In blocco nel criterio Protezione da posta indesiderata per decidere il livello di posta in blocco da considerare come posta indesiderata.

6. **L'intelligence delle** cassette postali apprende dai comportamenti di posta elettronica degli utenti standard. Sfrutta il grafico di comunicazione di un utente per rilevare quando un mittente sembra essere solo una persona con cui l'utente comunica in genere, ma in realtà è dannoso. Questo metodo rileva la rappresentazione.

7. **La rappresentazione dell'intelligence delle** cassette postali abilita o disabilita i risultati della rappresentazione avanzata in base alla mappa dei singoli mittenti di ogni utente. Se abilitata, questa funzionalità consente di identificare la rappresentazione.

8. **La rappresentazione utente** consente a un amministratore di creare un elenco di destinazioni di valore elevato che potrebbero essere rappresentate. Se arriva un messaggio di posta elettronica in cui il mittente sembra avere solo lo stesso nome e indirizzo dell'account di alto valore protetto, il messaggio viene contrassegnato o contrassegnato. (Ad esempio, *trα cye@contoso.com* per *tracye@contoso.com*).

9. **La rappresentazione del** dominio rileva i domini simili al dominio del destinatario e che tentano di apparire come un dominio interno. Ad esempio, questa rappresentazione *tracye@liw α re.com* per *tracye@litware.com*.

## <a name="phase-3---content-filtering"></a>Fase 3 - Filtro contenuto

In questa fase lo stack di filtri inizia a gestire il contenuto specifico del messaggio, inclusi i relativi collegamenti ipertestuali e allegati.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase3.png" alt-text="La fase 3 del filtro in MDO è Il filtro contenuto.":::

1. **Le regole di** trasporto (note anche come regole del flusso di posta o regole di trasporto di Exchange) consentono a un amministratore di eseguire un'ampia gamma di azioni quando viene soddisfatta una gamma altrettanto ampia di condizioni per un messaggio. Tutti i messaggi che attraversano l'organizzazione vengono valutati in base alle regole del flusso di posta abilitate/alle regole di trasporto.

2. **Microsoft Defender Antivirus** e due *motori antivirus* di terze parti vengono usati per rilevare tutto il malware noto negli allegati.

3. I motori antivirus (AV) vengono utilizzati anche per il true-type di tutti gli allegati, in modo che il blocco dei tipi possa bloccare tutti gli allegati dei tipi specificati dall'amministratore. 

4. Ogni volta che Microsoft Defender per Office 365 rileva un allegato dannoso, l'hash del file e un hash del contenuto attivo vengono aggiunti alla reputazione di Exchange Online Protection (EOP). **Il blocco della reputazione** degli allegati bloccherà il file in tutti Office 365 e sugli endpoint tramite chiamate cloud MSAV.

5. **Il clustering euristico** può determinare che un file è sospetto in base all'euristica di recapito. Quando viene trovato un allegato sospetto, l'intera campagna viene sospesa e il file viene in modalità sandbox. Se il file viene rilevato dannoso, l'intera campagna viene bloccata.

6. **I modelli di machine learning** agiscono sull'intestazione, sul contenuto del corpo e sugli URL di un messaggio per rilevare i tentativi di phishing.

7. Microsoft usa la determinazione della reputazione dal sandboxing degli URL e la reputazione url dai feed di terze parti nel blocco della reputazione **URL** per bloccare qualsiasi messaggio con un URL dannoso noto.

8. **L'euristica del** contenuto può rilevare messaggi sospetti in base alla struttura e alla frequenza delle parole all'interno del corpo del messaggio, utilizzando modelli di machine learning.

9. **Allegati sicuri** consente di creare sandbox per ogni allegato per i clienti di Defender per Office 365, usando l'analisi dinamica per rilevare minacce mai viste prima.

10. **La detonazione del** contenuto collegato considera ogni URL che si collega a un file in un messaggio di posta elettronica come allegato, inviando in modo asincrono in modalità sandbox il file al momento del recapito.

11. **La detonazione dell'URL** si verifica quando la tecnologia anti-phishing a monte trova un messaggio o un URL sospetto. La detonazione dell'URL in modalità sandbox gli URL nel messaggio al momento del recapito.

## <a name="phase-4---post-delivery-protection"></a>Fase 4 - Protezione post-recapito

L'ultima fase si verifica dopo il recapito della posta o dei file, agendo sulla posta presente in diverse cassette postali, file e collegamenti visualizzati in client come Microsoft Teams.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase4.png" alt-text="La fase 4 del filtro in Defender per Office 365 è la protezione post-recapito.":::

1. **Collegamenti sicuri** è la protezione basata sul clic di MDO. Ogni URL in ogni messaggio viene racchiuso in modo che punti ai server Collegamenti sicuri Microsoft. Quando si fa clic su un URL, viene controllato rispetto alla reputazione più recente, prima che l'utente venga reindirizzato al sito di destinazione. L'URL viene in modalità sandbox asincrona per aggiornarne la reputazione.

2. **Phish Zero-Hour Auto-Purge (ZAP)** rileva e neutralizza retroattivamente i messaggi di phishing dannosi già recapitati alle cassette postali di Exchange Online.

3. **Malware ZAP** rileva e neutralizza retroattivamente i messaggi di malware dannosi già recapitati alle cassette postali di Exchange Online.

4. **Spam ZAP** rileva e neutralizza retroattivamente i messaggi di posta indesiderata dannosi già recapitati alle cassette postali di Exchange Online.

5. **Le visualizzazioni** della campagna consentono agli amministratori di vedere il quadro generale di un attacco, più velocemente e completamente, di quanto possa fare qualsiasi team senza automazione. Microsoft sfrutta le grandi quantità di dati anti-phishing, posta indesiderata e antimalware nell'intero servizio per identificare le campagne e quindi consente agli amministratori di analizzarle dall'inizio alla fine, inclusi obiettivi, impatti e flussi, disponibili anche in una scrittura di campagna scaricabile.

6. **I componenti** aggiuntivi Segnala messaggio consentono agli utenti di segnalare facilmente falsi positivi (posta elettronica buona, erroneamente contrassegnata come non *buona)* o falsi negativi (posta elettronica errata contrassegnata come *buona)* a Microsoft per ulteriori analisi.

7. **Collegamenti sicuri per i client di Office** offre la stessa protezione basata sul clic dei collegamenti sicuri, in modo nativo, all'interno di client di Office come Word, PowerPoint ed Excel.

8. **La protezione per OneDrive, SharePoint** e Teams offre la stessa protezione degli allegati sicuri da file dannosi, in modo nativo, all'interno di OneDrive, SharePoint e Microsoft Teams.

9. Quando si seleziona un URL che punta a un file dopo il recapito, la **detonazione** del contenuto collegato visualizza una pagina di avviso fino al completamento della sandbox del file e l'URL viene trovato sicuro.


## <a name="the-filtering-stack-diagram"></a>Diagramma dello stack di filtro

Il diagramma finale (come tutte le parti del diagramma che lo compone) è soggetto a modifiche man mano che il prodotto cresce *e si sviluppa.* Aggiungi un segnalibro a questa pagina e usa l'opzione **di feedback** che troverai in basso se devi chiedere dopo gli aggiornamenti. Per i record, questo è lo stack con tutte le fasi nell'ordine:

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase5.png" alt-text="Tutte le fasi del filtro in MDO nell'ordine da 1 a 4.":::

## <a name="more-information"></a>Ulteriori informazioni

È necessario configurare Microsoft Defender per Office 365 ***in questo momento** _? Usa questo stack, _now*, con questa procedura dettagliata per [iniziare](protect-against-threats.md) a proteggere l'organizzazione.

*Grazie speciali di MSFTTracyP e* del team di scrittura dei documenti a Giulian Garruba per questo contenuto.
