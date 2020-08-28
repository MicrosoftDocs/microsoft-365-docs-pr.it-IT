---
title: Controllo app
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 32ed3f95ebb4299796c5ad3eb71802c949701b65
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289128"
---
# <a name="app-control"></a>Controllo app

App Control è una procedura di sicurezza facoltativa in Microsoft Managed Desktop che limita l'esecuzione del codice sui dispositivi client. Questo controllo consente di ridurre il rischio di malware o script dannosi richiedendo che sia possibile eseguire solo il codice firmato da un elenco di editori approvati dal cliente. Esistono numerosi vantaggi per la sicurezza di questo controllo, ma si tratta principalmente di proteggere i dati e l'identità da exploit basati su client.

Microsoft Managed Desktop semplifica la gestione dei criteri di controllo delle app creando un criterio di base che consente di creare scenari di produttività core. È possibile estendere la relazione di trust ai firmatari aggiuntivi specifici per le app e gli script nell'ambiente in uso. 


Qualsiasi tecnologia di sicurezza richiede un equilibrio tra esperienza utente, sicurezza e costo. Il controllo app riduce la minaccia del software dannoso nell'ambiente, ma ci sono conseguenze per l'utente e altre azioni per l'amministratore IT.

**Sicurezza aggiuntiva:**

Le app o gli script che non sono considerati attendibili dai criteri di controllo dell'app sono bloccati dall'esecuzione nei dispositivi.

**Responsabilità aggiuntive:**

- L'utente è responsabile del test delle app per identificare se verrebbe bloccato dal criterio di controllo dell'applicazione.
- Se un'app è (o verrebbe) bloccata, è responsabile dell'identificazione dei dettagli del firmatario necessari e della richiesta di una modifica tramite il portale di amministrazione.

**Responsabilità di Microsoft Managed Desktop:**

- Microsoft Managed Desktop gestisce i criteri di base che consentono ai prodotti Microsoft principali come M365 Apps, Windows, teams, OneDrive e così via.
- Microsoft Managed Desktop inserisce i propri firmatari attendibili e distribuisce i criteri aggiornati ai propri dispositivi.


## <a name="managing-trust-in-applications"></a>Gestione della relazione di trust nelle applicazioni

Microsoft Managed Desktop gestisce un criterio di base che considera attendibili i componenti principali delle tecnologie Microsoft. È quindi possibile *aggiungere* attendibilità per le proprie applicazioni e gli script informando Microsoft Managed Desktop di cui si ha già fiducia.

### <a name="base-policy"></a>Criteri di base

Microsoft Managed Desktop, in collaborazione con esperti di Microsoft Cybersecurity, crea e gestisce un criterio standard che consente la maggior parte delle app distribuite tramite Microsoft Intune durante il blocco di attività pericolose come la compilazione del codice o l'esecuzione di file non attendibili.

Il criterio di base assume il seguente approccio per limitare l'esecuzione del software:

- I file eseguiti dagli amministratori saranno autorizzati a essere eseguiti.
- I file in posizioni *non* presenti nelle directory scrivibili dall'utente saranno autorizzati all'esecuzione.
- I file sono firmati da un [firmatario attendibile](#signer-requests).
- La maggior parte dei file firmati da Microsoft verrà eseguita, ma alcuni sono bloccati per impedire azioni ad alto rischio come la compilazione del codice.


Se un utente diverso da un amministratore può aver aggiunto un'app o uno script a un dispositivo (ovvero si trova in una directory scrivibile dall'utente), non è possibile eseguirne l'esecuzione, a meno che non sia stato già esplicitamente consentito da un amministratore. Se un utente è indotto a tentare di installare malware, se una vulnerabilità in un'app che l'utente esegue tenta di installare malware o se un utente tenta intenzionalmente di eseguire un'applicazione o uno script non autorizzato, il criterio interrompe l'esecuzione.

### <a name="signer-requests"></a>Richieste del firmatario

Informazioni su quali app sono fornite dai fornitori di software di cui si ha fiducia archiviando una *richiesta di firmatario*. In questo modo, si aggiungono le informazioni di attendibilità nel criterio di controllo dell'applicazione di base e si consente a qualsiasi software firmato con il certificato di tale editore di essere eseguito sui dispositivi.

## <a name="audit-and-enforced-policies"></a>Criteri di controllo e applicati

Microsoft Managed Desktop utilizza due criteri di Microsoft Intune per fornire il controllo app:

### <a name="audit-policy"></a>Criteri di controllo
Questo criterio consente di creare registri per registrare se un'app o uno script verrebbe bloccato dal criterio applicato. I criteri di controllo non applicano le regole per i controlli delle app e sono destinati ai test per identificare se un'applicazione richiede un'esenzione dall'editore. Registra gli avvisi (8003 o 8006) nel Visualizzatore eventi invece di bloccare l'esecuzione o l'installazione delle app o degli script specificati.

### <a name="enforced-policy"></a>Criteri applicati
Questo criterio blocca le app e gli script non attendibili dall'esecuzione e crea registri ogni volta che un'app o uno script è bloccato. I criteri applicati impediscono agli utenti standard di eseguire le app o gli script archiviati nelle directory scrivibili dall'utente.

I dispositivi del gruppo di test dispongono di un criterio di controllo applicato in modo che sia possibile utilizzarli per convalidare se qualsiasi applicazione provocherà problemi. Tutti gli altri gruppi (First, Fast e Broad) utilizzano un criterio applicato, in modo che gli utenti di tali gruppi non siano in grado di eseguire le app o gli script non attendibili.







