---
title: Domande frequenti sul punteggio di conformità Microsoft
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
description: Trovare le risposte alle domande frequenti sul punteggio di conformità di Microsoft, che consente alle organizzazioni di semplificare e automatizzare le valutazioni dei rischi.
ms.openlocfilehash: bc0ddfe71a3de2bbfa2c9c9a0fdc507a540daf90
ms.sourcegitcommit: 3eae8fe39cea912d29e211a1c9fd035d6b606f91
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "39625421"
---
# <a name="microsoft-compliance-score-preview-frequently-asked-questions"></a>Microsoft Compliance Score (Preview) domande frequenti

## <a name="what-is-compliance-score"></a>Che cos'è il Punteggio di conformità?

Microsoft Compliance Score è una funzionalità di anteprima del [centro conformità di microsoft 365](microsoft-365-compliance-center.md) che consente di comprendere la posizione di conformità dell'organizzazione. Calcola un punteggio basato sui rischi misurando lo stato di avanzamento del processo di completamento delle azioni che consentono di ridurre i rischi per la protezione dei dati e gli standard normativi. Fornisce inoltre un mapping di controllo incorporato che consente di connettere i controlli comuni tra le normative e gli standard chiave, in modo da poter eseguire un'azione per soddisfare più requisiti contemporaneamente e migliorare la scalabilità del programma di conformità.

## <a name="how-do-i-access-compliance-score"></a>Come si accede al Punteggio di conformità?

Accedere al [centro conformità di microsoft 365](https://compliance.microsoft.com/) e **accedere** con un ruolo Microsoft 365 Global Admin, compliance admin o Compliance Data admin. Seleziona **Punteggio di conformità** nel riquadro di spostamento a sinistra. Sarà quindi possibile visualizzare il [Dashboard Punteggio di conformità con il Punteggio](compliance-score-setup.md#understand-the-compliance-score-dashboard). Se non si dispone dell'accesso ai ruoli appropriato, l'amministratore globale dell'organizzazione può concedere l'autorizzazione.

## <a name="what-roles-or-permissions-are-needed-to-use-compliance-score"></a>Quali ruoli o autorizzazioni sono necessari per l'utilizzo del Punteggio di conformità?

Il Punteggio di conformità utilizza un modello di autorizzazione di controllo di accesso basato sui ruoli (RBAC) e le azioni che è possibile eseguire dipendono dal tipo di ruolo assegnato all'utente. L'amministratore globale dell'organizzazione Microsoft 365 è la persona che può eseguire le funzioni di installazione e amministrare i ruoli nel punteggio di conformità. Per leggere i dati nel punteggio di conformità, è necessario che gli utenti dispongano almeno del ruolo di **Reader globale di Azure ad** . Per ulteriori informazioni sulle autorizzazioni, i ruoli e le procedure di installazione, vedere [Compliance Score Setup](compliance-score-setup.md).

## <a name="what-is-the-difference-between-compliance-score-and-compliance-manager"></a>Qual è la differenza tra Score compliance e Compliance Manager?

Il Punteggio di conformità e Compliance Manager condividono lo stesso backend, ma sono in due posizioni diverse (il Punteggio di conformità è nel centro conformità di Microsoft 365 e Compliance Manager è in Microsoft Service Trust Portal). Considerare il Punteggio di conformità come versione semplificata di Compliance Manager, offrendo una visione più completa della posizione di conformità corrente dell'organizzazione e i passaggi che è possibile eseguire per migliorarla. Anche se è possibile eseguire molte azioni direttamente all'interno del Punteggio di conformità, alcune funzionalità risiedono in Compliance Manager per il momento. Per ulteriori informazioni, vedere la [relazione tra conformità score e Compliance Manager](compliance-score.md#relationship-to-compliance-manager).

## <a name="who-should-use-compliance-score-and-who-should-use-compliance-manager"></a>Chi deve utilizzare il Punteggio di conformità e chi deve utilizzare Compliance Manager?

Il Punteggio di conformità è utile per tutti gli utenti dell'organizzazione che svolgono un ruolo nel monitoraggio della conformità e nell'esecuzione di attività che consentano di rispettare gli standard normativi. Con punteggio di conformità, non è necessario avere familiarità con le normative e gli standard per contribuire a migliorare la protezione dei dati dell'organizzazione. Il Punteggio di conformità è il punto di partenza ottimale per tutti gli utenti. Da qui, è possibile visualizzare il Punteggio di conformità, sapere quali azioni consigliate possono contribuire a ridurre al minimo i rischi e, in molti casi, avviare direttamente le soluzioni per intraprendere tali azioni.

Per il momento, Compliance Manager è il luogo in cui gli utenti possono gestire le valutazioni e creare modelli personalizzati per la creazione di valutazioni. Per ulteriori informazioni, vedere [quali azioni sono supportate solo da Compliance Manager](compliance-score-release-notes.md#compliance-score-and-compliance-manager-relationship) durante l'anteprima pubblica.

## <a name="if-i-have-a-high-score-does-it-mean-im-fully-compliant"></a>Se si dispone di un punteggio elevato, significa che sono pienamente conforme?

No. Il Punteggio di conformità misura lo stato di avanzamento del completamento delle azioni consigliate che contribuiscono alla riduzione dei rischi per la protezione dei dati e gli standard regolatori. Non esprime una misura assoluta di conformità organizzativa rispetto a una norma o a un regolamento particolari. Il Punteggio di conformità non deve essere interpretato come garanzia in alcun modo.

## <a name="what-regulations-and-standards-does-compliance-score-monitor"></a>Quali normative e standard esegue il monitoraggio del Punteggio conformità?

Punteggio di conformità fornisce un punteggio iniziale basato sulla linea di base per la protezione dei dati di Microsoft 365, che è un insieme di controlli che include normative e standard industriali comuni. Questa linea di base estrae gli elementi principalmente dal NIST CSF (Istituto nazionale per gli standard e la tecnologia Cybersecurity Framework) e ISO (organizzazione internazionale per la standardizzazione), nonché da FedRAMP (gestione federale dei rischi e delle autorizzazioni Program) e GDPR (regolamentazione generale sulla protezione dei dati dell'Unione europea).

Le organizzazioni possono creare e aggiungere valutazioni personalizzate più rilevanti per la propria organizzazione. È possibile utilizzare uno dei [modelli out-of-the-box](compliance-score.md#templates) del Punteggio di conformità per creare valutazioni per determinati standard o [creare un modello personalizzato](working-with-compliance-manager.md#create-a-template-1).

Per ulteriori informazioni [, vedere come il Punteggio di conformità calcola il Punteggio](compliance-score-methodology.md).

## <a name="what-is-the-difference-between-compliance-score-and-secure-score"></a>Qual è la differenza tra Punteggio di conformità e Punteggio sicuro?

Punteggio di conformità fornisce una panoramica generale delle posizioni di protezione e conformità dei dati dell'organizzazione. Il Punteggio di conformità fornisce anche strumenti di flusso di lavoro incorporati; consente alle organizzazioni di assegnare lavoro agli utenti, di tracciare l'implementazione del controllo e lo stato del test, nonché di caricare le prove e creare rapporti di controllo.

Microsoft Secure Score è uno strumento di analisi della sicurezza che aiuta a comprendere la propria posizione di sicurezza. [Per ulteriori informazioni, vedere Punteggio sicuro e modalità di funzionamento](../security/mtp/microsoft-secure-score.md).

## <a name="which-cloud-services-are-covered-by-compliance-score"></a>Quali servizi cloud sono coperti dal punteggio di conformità?

Il Punteggio di conformità fornisce attualmente valutazioni per Office 365 e Intune. La copertura espansa è prevista nelle versioni future e verrà annotata nelle [Note sulla versione del Punteggio di conformità](compliance-score-release-notes.md).

## <a name="can-i-use-compliance-score-for-non-microsoft-products"></a>È possibile utilizzare il Punteggio di conformità per i prodotti non Microsoft?

Mentre il Punteggio di conformità fornisce il monitoraggio continuo e le azioni consigliate solo per i servizi cloud Microsoft, è possibile aggiungere valutazioni personalizzate in Compliance Manager per i servizi di terze parti locali. In questo modo, è possibile utilizzare il Punteggio di conformità di Microsoft come strumento di gestione della conformità SaaS per gestire tutti i controlli nelle risorse digitali.

È possibile utilizzare uno dei [modelli out-of-the-box](compliance-score.md#templates) del Punteggio di conformità per creare valutazioni per determinati standard o [creare un modello personalizzato](working-with-compliance-manager.md#create-a-template-1).

## <a name="how-do-i-delete-a-template-or-assessment-i-no-longer-need"></a>Come eliminare un modello o una valutazione che non è più necessaria?

Non è possibile eliminare una valutazione o un modello oppure nasconderli dalla visualizzazione. Leggere [le istruzioni per nascondere le valutazioni](working-with-compliance-manager.md#hide-a-template-or-an-assessment).