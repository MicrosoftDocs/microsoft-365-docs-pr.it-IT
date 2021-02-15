---
title: Controllo app
description: Come usare il controllo delle app e considerare attendibile le applicazioni
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6f5cc923b5a18b1f45dd186e88228db8c3a891cc
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841304"
---
# <a name="app-control"></a>Controllo app

Il controllo delle app è una procedura di sicurezza facoltativa in Microsoft Managed Desktop che limita l'esecuzione del codice nei dispositivi client. Questo controllo riduce il rischio di malware o script dannosi richiedendo l'esecuzione solo del codice firmato da un elenco di editori approvato dal cliente. Questo controllo offre numerosi vantaggi in termini di sicurezza, ma mira principalmente a proteggere i dati e l'identità dagli exploit basati su client.

Microsoft Managed Desktop semplifica la gestione dei criteri di controllo delle app creando criteri di base che consentono scenari di produttività di base. Puoi estendere l'attendibilità ad altri firmatari specifici delle app e degli script nel tuo ambiente. 


Qualsiasi tecnologia di sicurezza richiede un equilibrio tra esperienza utente, sicurezza e costi. Il controllo delle app riduce la minaccia di software dannoso nell'ambiente, ma esistono conseguenze per l'utente e ulteriori azioni per l'amministratore IT.

**Sicurezza aggiuntiva:**

L'esecuzione di app o script non attendibili dai criteri di controllo delle app viene bloccata nei dispositivi.

**Responsabilità aggiuntive:**

- Sei responsabile del test delle tue app per determinare se verrebbero bloccate dai criteri di controllo delle applicazioni.
- Se un'app è (o verrebbe) bloccata, sei responsabile dell'identificazione dei dettagli del firmatario necessari e della richiesta di una modifica tramite il portale di amministrazione.

**Responsabilità di Microsoft Managed Desktop:**

- Microsoft Managed Desktop mantiene i criteri di base che consentono prodotti Microsoft di base come App M365, Windows, Teams, OneDrive e così via.
- Microsoft Managed Desktop inserisce i firmatari attendibili e distribuisce i criteri aggiornati nei dispositivi.


## <a name="managing-trust-in-applications"></a>Gestione dell'attendibilità nelle applicazioni

Microsoft Managed Desktop cura un criterio di base che considera attendibili i componenti principali delle tecnologie Microsoft. È quindi *possibile aggiungere* l'attendibilità per le proprie applicazioni e script informando Microsoft Managed Desktop di quali di essi si considera già attendibile.

### <a name="base-policy"></a>Criteri di base

Microsoft Managed Desktop, in collaborazione con esperti di sicurezza informatica Microsoft, crea e gestisce criteri standard che consentono la maggior parte delle app distribuite tramite Microsoft Intune, bloccando al contempo attività pericolose come la compilazione del codice o l'esecuzione di file non attendibili.

Il criterio di base adotta l'approccio seguente per limitare l'esecuzione del software:

- L'esecuzione dei file eseguiti dagli amministratori sarà consentita.
- L'esecuzione dei file in *percorsi* non presenti in directory scrivibili dall'utente sarà consentita.
- I file sono firmati da [un firmatario attendibile.](#signer-requests)
- La maggior parte dei file firmati da Microsoft verrà eseguita, ma alcuni sono bloccati per evitare azioni ad alto rischio come la compilazione del codice.


Se un utente diverso da un amministratore potrebbe aver aggiunto un'app o uno script a un dispositivo (ovvero si trova in una directory scrivibile dall'utente), l'esecuzione non verrà consentita a meno che non sia già stata espressamente consentita da un amministratore. Se un utente viene ingannato nel tentativo di installare malware, se una vulnerabilità in un'app viene eseguita tenta di installare malware o se un utente tenta intenzionalmente di eseguire un'app o uno script non autorizzato, l'esecuzione dei criteri verrà interrotta.

### <a name="signer-requests"></a>Richieste firmatario

L'utente ci informa delle app fornite da editori software di cui si considera attendibile l'utente, registrando una richiesta *di firmatario.* In questo modo, aggiungiamo queste informazioni di attendibilità ai criteri di controllo delle applicazioni di base e consentiamo l'esecuzione nei dispositivi di qualsiasi software firmato con il certificato dell'autore.

## <a name="audit-and-enforced-policies"></a>Criteri di controllo e applicati

Microsoft Managed Desktop usa due criteri di Microsoft Intune per fornire il controllo delle app:

### <a name="audit-policy"></a>Criteri di controllo
Questo criterio crea log per registrare se un'app o uno script verrebbe bloccato dal criterio Applicato. I criteri di controllo non applicano regole di controllo delle app e sono destinati a scopi di test per determinare se un'applicazione richiederà un'esenzione dell'editore. Registra gli avvisi (8003 o 8006 eventi) nel Visualizzatore eventi invece di bloccare l'esecuzione o l'installazione di app o script specificati.

### <a name="enforced-policy"></a>Criteri applicati
Questo criterio blocca l'esecuzione di app e script non attendibili e crea log ogni volta che un'app o uno script viene bloccato. I criteri applicati impediscono agli utenti standard di eseguire app o script archiviati in directory scrivibili dall'utente.

Ai dispositivi nel gruppo Test è applicato un criterio di controllo in modo da poterli usare per verificare se eventuali applicazioni causeranno problemi. Tutti gli altri gruppi (First, Fast e Broad) usano un criterio Applicato, in modo che gli utenti di tali gruppi non saranno in grado di eseguire app o script non attendibili.







