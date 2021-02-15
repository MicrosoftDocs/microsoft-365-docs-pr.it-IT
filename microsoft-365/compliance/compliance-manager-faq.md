---
title: Domande frequenti su Microsoft Compliance Manager
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Risposte alle domande frequenti su Microsoft Compliance Manager, che consentono alle organizzazioni di semplificare e automatizzare le valutazioni dei rischi.
ms.openlocfilehash: 43ecafdfe54b2baec82363ea690a5a820e031232
ms.sourcegitcommit: b8e9b2ecdc4927b67088c5fffb1585424c66fb10
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2021
ms.locfileid: "50050370"
---
# <a name="compliance-manager-frequently-asked-questions"></a>Domande frequenti su Compliance Manager

## <a name="is-compliance-manager-and-compliance-score-the-same-thing-or-are-they-different"></a>Compliance Manager e Compliance Score sono uguali o sono diversi?

Esiste ora una sola soluzione: Compliance Manager. In questa sezione viene illustrata la transizione, iniziando con una panoramica di base riportata di seguito. Potrebbe essere utile anche passare direttamente a una delle sezioni seguenti:

- [L'organizzazione ha utilizzato principalmente Compliance Manager (versioni di anteprima classica o pubblica), disponibile in Microsoft Service Trust Portal](#your-organization-regularly-used-compliance-manager-in-the-service-trust-portal)

- [L'organizzazione ha usato principalmente il punteggio di conformità (anteprima pubblica), che si trova nel Centro conformità Microsoft 365](#your-organization-used-compliance-score-public-preview-in-the-microsoft-365-compliance-center)

- [L'organizzazione è una novità di Compliance Manager](#youre-new-to-compliance-manager
)
#### <a name="the-basics"></a>Nozioni di base

Microsoft Compliance Manager è iniziato come soluzione di gestione della conformità all'interno di Microsoft Service Trust Portal.  Quando le soluzioni di conformità sono state integrate nel Centro conformità Microsoft 365, è stata sviluppata una nuova esperienza con una progettazione più semplice da usare per questa posizione. L'anteprima pubblica del punteggio di conformità è stata rilasciata nel Centro conformità Microsoft 365 a novembre 2019. Punteggio di conformità ha condiviso lo stesso back-end di Compliance Manager, consentendo ai clienti di lavorare in entrambe le posizioni. Da novembre 2019, sono stati rilasciati diversi aggiornamenti man quando abbiamo creato nuove funzionalità e abbiamo risposto al feedback dei clienti.

La disponibilità generale di Compliance Manager nel Centro conformità Microsoft 365 a settembre 2020 completa questa evoluzione. Compliance Manager è la soluzione di conformità end-to-end unificata. Il punteggio di conformità rimane un componente chiave di Compliance Manager.

Leggere questo [post di blog](https://aka.ms/compliancemanager/GAblog) per ulteriori informazioni sulle novità della versione GA di Compliance Manager.

#### <a name="your-organization-regularly-used-compliance-manager-in-the-service-trust-portal"></a>L'organizzazione ha utilizzato regolarmente Compliance Manager nel Service Trust Portal

Se è stato utilizzato Compliance Manager nel Service Trust Portal, tutti i dati dell'organizzazione ora sono presenti in Compliance Manager nel Centro conformità Microsoft 365 all'indirizzo https://compliance.microsoft.com/compliancemanager . Non è necessario eseguire alcuna operazione per riprendere il lavoro di Compliance Manager nella nuova posizione, a parte l'aggiornamento dei segnalibri alla posizione precedente. Tutte le valutazioni e altri dati sono stati per te completati.

Si noti che Compliance Manager (anteprima) non è più accessibile nel Service Trust Portal e tutti i collegamenti ad esso reindirizzano l'utente alla nuova posizione nel Centro conformità Microsoft 365. Compliance Manager (classico) rimane nel Service Trust Portal, anche se il suo uso è sconsigliato.

Tutte le operazioni eseguite nelle versioni precedenti di Compliance Manager, ad esempio il completamento delle azioni (ora denominate "azioni di miglioramento") e la creazione di valutazioni, possono essere eseguite nel nuovo Compliance Manager. Abbiamo aggiunto oltre 150 nuovi modelli di valutazione e migliorato il processo di creazione dei modelli. Verranno aggiunti ulteriori miglioramenti nelle versioni future.

Di seguito sono riportate alcune risorse utili:

- [Acquisire familiarità con la nuova esperienza di Compliance Manager](compliance-manager-setup.md#understand-the-compliance-manager-dashboard)
- [Trovare le autorizzazioni e altre informazioni di configurazione per Compliance Manager nella nuova home page](compliance-manager-setup.md#who-can-access-compliance-manager)
- [Ulteriori informazioni sul Centro conformità Microsoft 365](microsoft-365-compliance-center.md)

#### <a name="your-organization-used-compliance-score-public-preview-in-the-microsoft-365-compliance-center"></a>L'organizzazione ha usato il punteggio di conformità (anteprima pubblica) nel Centro conformità Microsoft 365

Se è stato usato punteggio di conformità in anteprima pubblica, si noterà che Compliance Manager è in gran parte lo stesso, con il punteggio in primo piano nel dashboard. Con la versione GA, non è più necessario lasciare il Centro conformità Microsoft 365 per eseguire determinate funzioni di gestione della valutazione, ad esempio la creazione e la modifica di modelli per le valutazioni. Tutte le funzionalità ora risiedono in un'unica posizione. Tutti i dati presenti nella versione di anteprima del punteggio di conformità rimangono nella versione GA di Compliance Manager.

Si noti che se è stata filtrata la visualizzazione del dashboard del punteggio di conformità, tali filtri sono stati reimpostati quando è stato distribuito il nuovo Compliance Manager a settembre. Sarà necessario riapplicare i filtri disponibili.

Compliance Manager include anche nuove condizioni di licenza. Vedi la domanda seguente sulle licenze.

#### <a name="youre-new-to-compliance-manager"></a>Sei una novità di Compliance Manager

Compliance Manager è una soluzione end-to-end nel Centro conformità Microsoft 365 per la gestione e la verifica delle attività di conformità. È un ottimo punto di inizio del percorso di conformità perché offre una valutazione iniziale della propria posizione di conformità la prima volta che si visita. Di seguito sono riportati alcuni punti per iniziare a imparare di più:

- [Panoramica di Compliance Manager](compliance-manager.md)
- [Usare la guida introduttiva per aumentare le fasi](compliance-manager-quickstart.md)
- [Ulteriori informazioni sul Centro conformità Microsoft 365](microsoft-365-compliance-center.md)

## <a name="are-there-licensing-requirements-for-using-compliance-manager"></a>Esistono requisiti di licenza per l'uso di Compliance Manager?

Sì. La versione GA di Compliance Manager contiene nuove condizioni di licenza. Tutte le organizzazioni con licenze di Office 365 e Microsoft 365 e i clienti di Us Government Community (GCC) Moderate e GCC High hanno accesso a Compliance Manager. Tuttavia, le valutazioni disponibili per l'organizzazione e la modalità di gestione dei modelli di valutazione dipendono dal contratto di licenza. Per informazioni dettagliate, visitare la guida alle licenze di [Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2132371) per la sicurezza e la conformità.

## <a name="if-i-have-a-high-score-does-it-mean-im-fully-compliant"></a>Se ho un punteggio elevato, significa che sono completamente conforme?

No. Il punteggio di conformità misura i progressi nel completamento delle azioni consigliate che consentono di ridurre i rischi relativi alla protezione dei dati e agli standard normativi. Non esprime una misura assoluta di conformità dell'organizzazione per quanto riguarda uno standard o una normativa particolare. Compliance Manager e il punteggio di conformità non devono essere interpretati come una garanzia in alcun modo.

## <a name="can-i-use-compliance-manager-for-non-microsoft-products"></a>Posso usare Compliance Manager per prodotti non Microsoft?

Anche se Compliance Manager fornisce il monitoraggio continuo e le azioni consigliate solo per i servizi cloud Microsoft, è possibile aggiungere valutazioni personalizzate in Compliance Manager per i servizi di terze parti. In questo modo, è possibile utilizzare Microsoft Compliance Manager come strumento di gestione della conformità SaaS per gestire tutti i controlli nelle risorse digitali.

## <a name="whats-happening-to-compliance-manager-classic-in-the-service-trust-portal"></a>Cosa succede a Compliance Manager (classico) nel Service Trust Portal?

La versione classica di Compliance Manager, che si trova in Microsoft Service Trust Portal, verrà presto ritirata. Un avviso del Centro messaggi di Microsoft 365 verrà inviato almeno 60 giorni prima del ritiro finale di Compliance Manager (classico). I clienti che gestiscono le attività di conformità in Compliance Manager (classico) dovranno spostare i propri dati, incluse valutazioni e controlli, nella nuova soluzione Compliance Manager nel Centro conformità Microsoft 365. I dati dei clienti non verranno trasferiti automaticamente a Compliance Manager nel Centro conformità Microsoft 365 quando Compliance Manager (classico) viene ritirato.

Per informazioni su come configurare rapidamente il nuovo Compliance Manager, leggere la guida [introduttiva di Compliance Manager.](compliance-manager-quickstart.md)