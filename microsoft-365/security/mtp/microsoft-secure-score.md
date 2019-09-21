---
title: Microsoft Secure Score
description: Descrive Microsoft Secure score in Microsoft 365 Security Center, la modalità di calcolo dei dettagli e gli amministratori della sicurezza che possono aspettarsi di usarli.
keywords: sicurezza, malware, Microsoft 365, M365, Punteggio sicuro, Centro sicurezza, azioni di miglioramento
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 17d2decc7374d9022c68cbe2f2d58da959f44a7d
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084960"
---
# <a name="microsoft-secure-score"></a>Microsoft Secure Score

>[!IMPORTANT]
>Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Con Microsoft Secure score in Microsoft 365 Security Center, è possibile avere maggiore visibilità e controllo sulla posizione di sicurezza dell'organizzazione. Da un Dashboard centralizzato è possibile monitorare e migliorare la sicurezza per le identità, i dati, le app, i dispositivi e l'infrastruttura di Microsoft 365.

Microsoft Secure Score offre una visualizzazione robusta, l'integrazione con altri prodotti Microsoft, il confronto tra la partitura e altre società, il filtraggio per categoria e molto altro ancora. Con lo strumento, è possibile completare le operazioni di miglioramento della sicurezza all'interno dell'organizzazione e monitorare la cronologia del punteggio. Il Punteggio può anche riflettere quando le soluzioni di terze parti hanno affrontato azioni di miglioramento consigliate.  

## <a name="how-it-works"></a>Funzionamento

Si ricevono punti per la configurazione delle funzionalità di sicurezza consigliate, per l'esecuzione di attività relative alla sicurezza (come la visualizzazione di report) o per l'azione di miglioramento con un'applicazione o un software di terze parti. Alcune azioni vengono segnate per il completamento parziale, come l'abilitazione dell'autenticazione a più fattori per gli utenti. La sicurezza deve essere sempre bilanciata con l'usabilità e non ogni raccomandazione funzionerà per l'ambiente in uso.

## <a name="required-permissions"></a>Autorizzazioni necessarie

Attualmente, per visualizzare il Punteggio sicuro di Microsoft, è necessario essere assegnati a uno dei ruoli seguenti in Azure Active Directory:

* Amministratore globale
* Amministratore della sicurezza
* Lettore di sicurezza

## <a name="rich-experiences--additional-security-recommendations"></a>Esperienze ricche & ulteriori suggerimenti per la sicurezza

In Microsoft Secure score, sono stati aggiunti suggerimenti da Azure AD, Intune e cloud app Security, con consigli di Azure Security Center e Microsoft Defender ATP in arrivo. Sono stati aggiunti anche altri suggerimenti per la sicurezza di Office 365. Con ulteriori intuizioni e una maggiore visibilità in un insieme più ampio di prodotti e servizi Microsoft, è possibile ottenere una relazione sicura fino alla gestione dell'integrità della sicurezza dell'organizzazione. È anche possibile ottenere il punteggio utilizzando l' [API di Microsoft Graph](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta).

Per aiutare le informazioni necessarie più rapidamente, i consigli di Microsoft sono organizzati in gruppi:

* Identity (stato di protezione dei ruoli e degli account di Azure AD)
* Data (stato di protezione dei documenti di Office 365)
* Dispositivo (stato di protezione dei dispositivi; Azioni di miglioramento di Microsoft Defender ATP prossimamente
* App (stato di protezione delle app del cloud e della posta elettronica)
* Infrastruttura (stato di protezione delle risorse di Azure; presto disponibile)

Nella pagina Panoramica di Microsoft Secure score, è possibile vedere come vengono divisi i punti tra questi gruppi e quali sono i punti disponibili. La pagina di panoramica è anche il luogo in cui ottenere una visualizzazione completa del punteggio totale, l'andamento storico del Punteggio sicuro con i confronti di benchmark e le azioni di miglioramento prioritarie che possono essere intraprese per migliorare il punteggio. È possibile utilizzare questi dati per agire e fare grandi differenze nella posizione di sicurezza.  

![Home Page](../media/secure-score/homepage-original.png)
di M365*Figura 1: pagina Panoramica di Microsoft Secure Score*

## <a name="take-action-to-improve-your-score"></a>Eseguire un'azione per migliorare il Punteggio

La scheda azioni di miglioramento elenca tutti i suggerimenti per la sicurezza applicabili al tenant insieme al relativo stato (completata, non completata, risolta tramite terze parti e ignorata). È possibile cercare, filtrare e raggruppare tutti i controlli.  La classificazione si basa sulla valutazione di Microsoft relativa al valore di sicurezza e allo sforzo per il completamento.

Le azioni contrassegnate come [non segnate] non vengono registrate da Microsoft Secure score. È comunque possibile eseguire un'azione, ma il loro completamento non influirà sul punteggio. Se un'azione viene registrata in futuro da Microsoft Secure score ed è già stata completata, il Punteggio sicuro rispecchierà automaticamente la modifica.

Quando si fa clic su un'azione di miglioramento, viene visualizzato un volo. Per completare l'azione, sono disponibili alcune opzioni:

1. Selezionare **Visualizza impostazioni** per passare alla schermata di configurazione e apportare le modifiche. Si otterrà quindi i punti che il valore dell'azione vale, visibili nella parte superiore del volo. I punti possono richiedere fino a 24 ore per l'aggiornamento.

2. Selezionare **Risolvi tramite terze parti** perché l'azione di miglioramento è già stata indirizzata da un'applicazione di terze parti o da un software. Si ottengono i punti che il valore dell'azione vale, in modo che il Punteggio sicuro rispecchi meglio la posizione di sicurezza complessiva. Se una terza parte non è più in grado di coprire il controllo, è possibile contrassegnare l'azione di miglioramento come non completata. Tenere presente che Microsoft non avrà alcuna visibilità se i requisiti del punteggio sono stati soddisfatti se l'azione di miglioramento è stata contrassegnata come risolta tramite terze parti.

3. Selezionare **Ignora** perché si è deciso di accettare il rischio e non di applicare l'azione di miglioramento. Una volta ignorata un'azione di miglioramento, il numero totale di punti di Punteggio sicuro che è possibile ottenere sarà ridotto. È possibile visualizzare questa azione nella cronologia o annullarla in qualsiasi momento.

4. Selezionare **Verifica** perché l'azione di miglioramento richiede la revisione periodica di una parte dell'ambiente per ottenere e mantenere i punti. Ad esempio, le regole di inoltro delle cassette postali devono essere riviste settimanalmente per assicurarsi che i dati non vengano exfiltrated dalla rete. Non è necessario apportare alcuna modifica, ma sarà necessario eseguire un'azione. Se si esaminano regolarmente le regole, verranno ricevuti i punti. In caso contrario, la partitura verrà ridotta.

![Home page di M365](../media/secure-score/secure-score1x450.png) ![Home page di M365](../media/secure-score/secure-score2x450.png)

*Figure 2 & 3: azione di miglioramento comparsa*

## <a name="monitor-improvements-over-time"></a>Monitorare i miglioramenti nel tempo

È possibile visualizzare un grafico del punteggio dell'organizzazione nel tempo nella scheda **cronologia** . Questa visualizzazione include la media globale, la media del settore e il numero di sedi simili, insieme a tutte le azioni eseguite nell'intervallo di tempo selezionato. È inoltre possibile personalizzare un intervallo di date e filtrare in base alla categoria.

Il Punteggio viene calcolato una volta al giorno (circa 1:00 AM PST). Se si apportano modifiche a un'azione misurata, il punteggio verrà aggiornato automaticamente il giorno successivo. È inoltre importante tenere presente che alcuni altri portali mostrano parti del Microsoft Secure Score (come Microsoft Defender Security Center). Se si completa un'azione di miglioramento e il punteggio è aumentato nei portali, potrebbero essere necessarie fino a 24 ore affinché il punteggio aggiornato venga visualizzato in Microsoft 365 Security Center.  

## <a name="how-improvement-actions-are-scored"></a>Come vengono segnate le azioni di miglioramento

La maggior parte sono segnati in modo binario: si ottiene il 100% dei punti se si implementa l'azione di miglioramento, ad esempio la creazione di un nuovo criterio o l'attivazione di un'impostazione specifica. Per altre azioni di miglioramento, i punti vengono assegnati come percentuale della configurazione totale. Ad esempio, se gli Stati di azione di miglioramento si ottengono 30 punti se si proteggono tutti gli utenti con autenticazione a più fattori e si dispone solo di 5 di 100 utenti totali protetti, si riceverebbe un punteggio parziale di circa 2 punti (5 protected/100 Total * 30 max pts = 2  Punteggio parziale PTS).

## <a name="risk-awareness"></a>Sensibilizzazione ai rischi

Microsoft Secure Score è un riepilogo numerico della postura di sicurezza in base alle configurazioni di sistema, al comportamento degli utenti e ad altre misure relative alla sicurezza. non si tratta di una misura assoluta del modo in cui il sistema o i dati verranno violati. Piuttosto, rappresenta la misura in cui sono stati adottati controlli di sicurezza nell'ambiente Microsoft, che possono contribuire a compensare il rischio di essere violati. Nessun servizio online è completamente immune dalle violazioni della sicurezza e il Punteggio sicuro non deve essere interpretato come garanzia contro la violazione della sicurezza in alcun modo.

## <a name="we-want-to-hear-from-you"></a>Si vuole sapere da voi

In caso di problemi, fatecelo sapere inviando la [sicurezza, la Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community. Si sta monitorando la community e viene fornita assistenza.
