---
title: Informazioni sulla dashboard degli avvisi per la prevenzione delle perdita dei dati
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Informazioni sugli avvisi di prevenzione della perdita di dati e sul dashboard degli avvisi.
ms.openlocfilehash: b6fd698e535e006149f6ce3a2a5bc57d0c92c7e2
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760783"
---
# <a name="learn-about-the-data-loss-prevention-alerts-dashboard"></a>Informazioni sulla dashboard degli avvisi per la prevenzione delle perdita dei dati

Quando i criteri in un criterio di prevenzione della perdita dei dati (DLP) vengono soddisfatti dalle azioni intraprese da un utente su un elemento sensibile, il criterio può generare un avviso. Ciò può comportare un volume elevato di avvisi. Gli avvisi DLP vengono raccolti nel dashboard degli avvisi. Il dashboard degli avvisi offre un'unica posizione in cui eseguire un'analisi approfondita di tutti i dettagli relativi alla corrispondenza dei criteri.  

<!-- [Microsoft 365 compliance center](https://compliance.microsoft.com/)-->

## <a name="workloads"></a>Carichi di lavoro

Il dashboard di gestione degli avvisi [DLP,](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts)nel Centro conformità [Microsoft 365,](https://compliance.microsoft.com/)mostra gli avvisi per i criteri DLP su questi carichi di lavoro:

- Exchange
- SharePoint
- OneDrive
- Teams
- Dispositivi Windows 10 

> [!TIP]
> I clienti che usano [ENDPOINT DLP](endpoint-dlp-learn-about.md) idonei per DLP di [Teams](dlp-microsoft-teams.md) visualizzano gli avvisi dei criteri DLP degli endpoint e gli avvisi dei criteri DLP di Teams nel dashboard di gestione degli avvisi DLP.

## <a name="single-alert-and-aggregate-alert"></a>Avviso singolo e avviso aggregato

Esistono due tipi di avvisi che possono essere configurati nei criteri DLP.

Gli **avvisi** a evento singolo vengono in genere utilizzati nei criteri che monitorano gli eventi estremamente sensibili che si verificano in un volume ridotto, ad esempio un singolo messaggio di posta elettronica con 10 o più numeri di carta di credito dei clienti inviati all'esterno dell'organizzazione.

**Gli avvisi di aggregazione** degli eventi vengono in genere utilizzati nei criteri che monitorano gli eventi che si verificano in un volume superiore in un periodo di tempo. Ad esempio, un avviso aggregato può essere attivato quando 10 messaggi di posta elettronica individuali ognuno con un numero di carta di credito del cliente viene inviato all'esterno dell'organizzazione per più di 48 ore.

## <a name="types-of-events"></a>Tipi di eventi

Ecco alcuni degli eventi associati a un avviso. Nell'interfaccia utente puoi scegliere un evento specifico per visualizzarne i dettagli. 

### <a name="event-details"></a>Dettagli evento

|Nome della proprietà  |Descrizione  |Tipi di evento  |
|---------|---------|---------|
|ID |ID univoco associato all'evento |tutti gli eventi |
|Posizione |carico di lavoro in cui è stato rilevato l'evento|tutti gli eventi |
|ora dell'attività     |ora dell'attività utente corrispondente ai criteri del criterio DLP |

### <a name="impacted-entities"></a>Entità influenzate

|Nome della proprietà |Descrizione| Tipi di evento|
|---------|---------|---------|
|utente | utente che ha evaso l'azione che ha causato la corrispondenza dei criteri | tutti gli eventi|
|hostname | nome host del computer in cui si è verificata la corrispondenza del criterio DLP | eventi dispositivo|
|Indirizzo IP | Indirizzo IP del computer in cui si è verificata la corrispondenza del criterio DLP | eventi dispositivo|
|sha1 |Hash SHA-1 del file | eventi dispositivo|
|sha256 | Hash SHA-256 del file | eventi dispositivo|
|ID dispositivo MDATP | ID MDATP dispositivo endpoint|
|dimensioni del file | dimensioni del file| Eventi di SharePoint, OneDrive e dispositivi|
|percorso file | il percorso assoluto dell'elemento coinvolto nella corrispondenza del criterio DLP | Eventi di SharePoint, OneDrive e dispositivi|
|destinatari di posta elettronica |se un messaggio di posta elettronica era l'elemento sensibile corrispondente al criterio DLP, questo campo include i destinatari del messaggio di posta elettronica| Eventi di Exchange|
|oggetto della posta elettronica |oggetto del messaggio di posta elettronica corrispondente al criterio DLP |Eventi di Exchange|
|allegati di posta elettronica | nomi degli allegati nel messaggio di posta elettronica corrispondenti al criterio DLP| Eventi di Exchange|
|proprietario del sito |nome del proprietario del sito| Eventi di SharePoint e OneDrive|
|URL sito |completo dell'URL del sito di SharePoint o OneDrive in cui si è verificata la corrispondenza del criterio DLP |Eventi di SharePoint e OneDrive|
|file creato |ora di creazione del file corrispondente al criterio DLP |Eventi di SharePoint e OneDrive|
|ultima modifica del file | l'ultima volta che il file corrispondente al criterio DLP è stato modificato | Eventi di SharePoint e OneDrive|
|dimensioni del file | dimensioni del file corrispondente al criterio DLP |Eventi di SharePoint e OneDrive|
|proprietario del file |proprietario del file corrispondente al criterio DLP |Eventi di SharePoint e OneDrive|  

### <a name="policy-details"></a>Dettagli criteri

|Nome della proprietà |Descrizione |Tipi di evento |
|---------|---------|---------|
|Criteri DLP corrispondenti |nome del criterio DLP corrispondente |tutti gli eventi|
|regola corrispondente |nome della regola dei criteri DLP corrispondente |tutti gli eventi|
|rilevati tipi di informazioni riservate (SIT)|SIT rilevati come parte della corrispondenza dei criteri DLP |tutti gli eventi|
|azioni intraprese |azioni intraprese che hanno causato la corrispondenza del criterio DLP| tutti gli eventi|
|violazione dell'azione | azione nel dispositivo endpoint che ha generato l'avviso DLP| eventi dispositivo | 
|criterio di overrode dell'utente |l'utente ha eseguito l'override del criterio tramite un suggerimento per i criteri | tutti gli eventi|
|giustificazione dell'override dell'utilizzo |il testo del motivo fornito dall'utente per la sostituzione | tutti gli eventi|   

## <a name="see-also"></a>Vedere anche

- [Introduzione alla dashboard degli avvisi per la prevenzione delle perdita dei dati](dlp-alerts-dashboard-get-started.md)
- [Da dove iniziare con la prevenzione della perdita di dati](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)