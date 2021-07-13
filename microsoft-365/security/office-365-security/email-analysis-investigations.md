---
title: Analisi della posta elettronica nelle indagini per Microsoft Defender per Office 365
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: risposta automatica agli incidenti, indagine, correzione, protezione dalle minacce
description: Scopri come funziona l'analisi della posta elettronica nelle indagini in Microsoft Defender per Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d222e1c8b6b5ca9e111b1dbe6b7fb31138a157b2
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395119"
---
# <a name="email-analysis-in-investigations-for-microsoft-defender-for-office-365"></a>Analisi della posta elettronica nelle indagini per Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 Piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Durante l'indagine automatizzata degli avvisi, Microsoft Defender per Office 365 analizza il messaggio di posta elettronica originale alla ricerca di minacce e identifica altri messaggi di posta elettronica correlati alla posta elettronica originale e potenzialmente parte di un attacco. Questa analisi è importante perché gli attacchi di posta elettronica raramente sono costituiti da un singolo messaggio di posta elettronica.

L'analisi della posta elettronica dell'indagine automatizzata identifica i cluster di posta elettronica utilizzando gli attributi del messaggio di posta elettronica originale per eseguire query per i messaggi di posta elettronica inviati e ricevuti dall'organizzazione. Questo è simile a un analista delle operazioni di sicurezza che cerca i messaggi di posta elettronica correlati in Esplora risorse o Ricerca avanzata. Vengono utilizzate diverse query per identificare i messaggi di posta elettronica corrispondenti perché gli utenti malintenzionati in genere trasformano i parametri di posta elettronica per evitare il rilevamento della sicurezza. L'analisi del clustering esegue questi controlli per determinare come gestire i messaggi di posta elettronica coinvolti nell'indagine:

- L'analisi della posta elettronica crea query (cluster) di messaggi di posta elettronica utilizzando gli attributi del messaggio di posta elettronica originale: i valori del mittente (indirizzo IP, dominio di invio) e il contenuto (oggetto, ID cluster) per trovare i messaggi di posta elettronica correlati.
- Se l'analisi degli URL e dei file del messaggio di posta elettronica originale identifica che alcuni sono dannosi (ovvero malware o phish), creerà anche query o cluster di messaggi di posta elettronica contenenti l'URL o il file dannoso.
- L'analisi del clustering della posta elettronica conta le minacce associate ai messaggi di posta elettronica corrispondenti nel cluster per determinare se i messaggi di posta elettronica sono dannosi, sospetti o non hanno minacce chiare. Se il cluster di messaggi di posta elettronica che corrispondono alla query ha una quantità sufficiente di posta indesiderata, phish normale, minacce di phish ad alta probabilità o malware, il cluster di posta elettronica riceve tale tipo di minaccia applicato. 
- L'analisi del clustering della posta elettronica controlla anche la posizione di recapito più recente della posta elettronica originale e dei messaggi di posta elettronica nei cluster di posta elettronica per identificare se i messaggi di posta elettronica potrebbero essere ancora necessari per la rimozione o sono già stati corretti o impediti. Questa analisi è importante perché gli utenti malintenzionati trasformano il contenuto dannoso più i criteri di sicurezza e la protezione possono variare tra le cassette postali. Questa funzionalità porta a situazioni in cui il contenuto dannoso può ancora essere contenuto nelle cassette postali, anche se uno o più messaggi di posta elettronica dannosi sono stati rilevati e rimossi da Zero-hour Auto Protection (ZAP).
- I cluster di posta elettronica considerati dannosi a causa di malware, phish ad alta sicurezza, file dannosi o minacce di URL dannosi riceveranno un'azione in sospeso per eliminare i messaggi di posta elettronica quando sono ancora presenti nella cassetta postale cloud (posta in arrivo o cartella posta indesiderata). Se i messaggi di posta elettronica dannosi o i cluster di posta elettronica sono solo "Non nella cassetta postale" (bloccati, messi in quarantena, non riusciti, eliminati in modo recidiva e così via) o "Locale/Esterno" con nessuna nella cassetta postale cloud, non verrà impostata alcuna azione in sospeso per rimuoverli.
- Se uno dei cluster di posta elettronica viene determinato come dannoso, la minaccia identificata dal cluster verrà applicata di nuovo alla posta elettronica originale coinvolta nell'indagine. Questo comportamento è simile a quello di un analista delle operazioni di sicurezza che usa i risultati della ricerca di posta elettronica per determinare il verdetto di un messaggio di posta elettronica originale in base ai messaggi di posta elettronica corrispondenti. Questo risultato garantisce che, indipendentemente dal fatto che gli URL, i file o gli indicatori di posta elettronica di origine di un messaggio di posta elettronica originale siano rilevati o meno, il sistema può identificare i messaggi di posta elettronica dannosi che potrebbero elusione dal rilevamento tramite personalizzazione, morphing, evasione o altre tecniche di attacco.
- Nell'indagine sulla compromissione degli utenti, vengono creati cluster di posta elettronica aggiuntivi per identificare potenziali problemi di posta elettronica creati dalla cassetta postale. Questo processo include un cluster di posta elettronica pulito (messaggi di posta elettronica validi dall'utente, potenziale esfiltrazione dei dati e potenziali messaggi di posta elettronica di comando/controllo), cluster di posta elettronica sospetti (messaggi di posta elettronica contenenti posta indesiderata o normali phish) e cluster di posta elettronica dannosi (messaggi di posta elettronica contenenti malware o phish ad alta confidenza). Questi cluster di posta elettronica forniscono dati agli analisti delle operazioni di sicurezza per determinare quali altri problemi potrebbero essere necessari per essere affrontati da una compromissione e visibilità su quali messaggi di posta elettronica potrebbero aver attivato gli avvisi originali (ad esempio, phish/spam che hanno attivato restrizioni di invio degli utenti)

L'analisi del clustering della posta elettronica tramite query di entità dannose e di similarità garantisce che i problemi di posta elettronica siano completamente identificati e puliti, anche se viene identificato un solo messaggio di posta elettronica da un attacco. È possibile utilizzare i collegamenti delle visualizzazioni del riquadro laterale dei dettagli del cluster di posta elettronica per aprire le query in Esplora risorse o Ricerca avanzata per eseguire un'analisi più approfondita e modificare le query, se necessario. Questa funzionalità consente di perfezionare e correggere manualmente se le query del cluster di posta elettronica sono troppo strette o troppo ampie (inclusi i messaggi di posta elettronica non correlati).

Ecco ulteriori miglioramenti all'analisi della posta elettronica nelle indagini.

## <a name="air-investigation-ignores-advanced-delivery-items-secops-mailbox-and-phishedu-messages"></a>Analisi AIR ignora gli elementi di recapito avanzati (cassetta postale SecOps e messaggi PhishEDU)

Durante l'analisi del clustering della posta elettronica, tutte le query di clustering ignoreranno le cassette postali di sicurezza impostate come cassette postali delle operazioni di sicurezza nel criterio recapito avanzato. Analogamente, le query di clustering di posta elettronica ignoreranno i messaggi di simulazione di phish (istruzione) configurati nel criterio recapito avanzato. Nella query non vengono visualizzati né i valori di esclusione SecOps né PhishEdu per mantenere gli attributi di clustering più semplici e più facili da leggere. Questa esclusione garantisce che l'intelligence per le minacce e le cassette postali operative (cassette postali SecOps) e le simulazioni di phish (PhishEdu) vengono ignorate durante l'analisi delle minacce e non vengono rimosse durante alcuna correzione. 

>[!Note]
>Quando si apre un cluster di posta elettronica per visualizzarlo in Esplora risorse dai dettagli del cluster di posta elettronica, i filtri delle cassette postali PhishEdu e SecOps verranno applicati in Esplora risorse, ma non verranno visualizzati. Se si modificano i filtri, le date o l'aggiornamento della query all'interno della pagina, le esclusioni del filtro PhishEdu/SecOps verranno rimosse e i messaggi di posta elettronica corrispondenti verranno visualizzati di nuovo. Se si aggiorna la pagina Esplora risorse utilizzando la funzione di aggiornamento del browser, i filtri di query originali verranno ricaricati, inclusi i filtri PhishEdu/SecOps, ma rimuovendo eventuali modifiche successive apportate.
>

## <a name="air-updates-pending-email-action-status"></a>Air updates pending email action status

L'analisi della posta elettronica di indagine calcola le minacce e le posizioni della posta elettronica al momento dell'indagine per creare le prove e le azioni dell'indagine. Questi dati possono essere obsoleti e obsoleti quando le azioni esterne all'indagine influiscono sui messaggi di posta elettronica coinvolti nell'indagine. Ad esempio, la ricerca manuale delle operazioni di sicurezza e la correzione possono pulire i messaggi di posta elettronica inclusi in un'indagine. Analogamente, le azioni di eliminazione approvate in indagini parallele o le azioni di quarantena automatica zap (Zero-hour Auto Protection) potrebbero aver rimosso i messaggi di posta elettronica. Inoltre, i rilevamenti ritardati delle minacce dopo il recapito della posta elettronica possono modificare il numero di minacce incluse nelle query o nei cluster di posta elettronica dell'indagine. 

Per garantire che le azioni di indagine siano aggiornate, qualsiasi indagine con azioni in sospeso rieseguono periodicamente le query di analisi della posta elettronica per aggiornare le posizioni e le minacce della posta elettronica. 

- Quando i dati del cluster di posta elettronica cambiano, aggiornerà i conteggi delle minacce e della posizione di recapito più recente. 
- Se nella cassetta postale non sono più presenti messaggi di posta elettronica o cluster di posta elettronica con azioni in sospeso, l'azione in sospeso verrà annullata e l'e-mail o il cluster dannoso considerato correttivo.
- Una volta che tutte le minacce dell'indagine sono state risolte o annullate come indicato in precedenza, l'indagine passa a uno stato risolto e l'avviso originale è stato risolto.

## <a name="the-display-of-incident-evidence-for-email-and-email-clusters"></a>Visualizzazione delle prove degli eventi imprevisti per i cluster di posta elettronica e di posta elettronica

Le prove basate sulla posta elettronica nella scheda Prova e risposta per un evento imprevisto ora visualizzano le informazioni seguenti.

:::image type="content" source="../../media/email-analysis-investigations/email-analysis-evidence-example.png" alt-text="Esempio di informazioni sull'analisi della posta elettronica in Prova e risposta" lightbox="../../media/email-analysis-investigations/email-analysis-evidence-example.png":::

Dai callout numerati nella figura:

1. Oltre al Centro notifiche, è possibile eseguire azioni di **correzione.**
2. È possibile eseguire un'azione di correzione per i cluster di posta elettronica con un verdetto **dannoso** (ma non **sospetto).**
3. Per il verdetto di posta indesiderata, il phishing è diviso in alta sicurezza e phish normale.

   Per un verdetto dannoso, le categorie di minacce sono malware, phish ad alta sicurezza, URL dannoso e file dannoso.

   Per un verdetto sospetto, le categorie di minacce sono posta indesiderata e phish normale.

4. Il conteggio della posta elettronica per si basa sulla posizione di recapito più recente e include contatori per la posta elettronica nelle cassette postali, non nelle cassette postali e in locale.
5. Include la data e l'ora della query, che potrebbero essere aggiornate per i dati più recenti.

Per i cluster di  posta elettronica o di posta elettronica nella scheda Entità di un evento imprevisto, **Impedisci** significa che non sono presenti messaggi di posta elettronica dannosi nella cassetta postale per questo elemento (posta o cluster). Ecco un esempio.

:::image type="content" source="../../media/email-analysis-investigations/email-analysis-evidence-example-prevented.png" alt-text="Esempio di messaggio di posta elettronica non consentito" lightbox="../../media/email-analysis-investigations/email-analysis-evidence-example-prevented.png":::

In questo esempio, il messaggio di posta elettronica è dannoso ma non in una cassetta postale.

## <a name="next-steps"></a>Passaggi successivi

- [Visualizzare le azioni di correzione in sospeso o completate](air-review-approve-pending-completed-actions.md)