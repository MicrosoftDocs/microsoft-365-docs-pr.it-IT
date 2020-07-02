---
title: Domande frequenti sul punteggio di conformità Microsoft (anteprima)
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
description: Trovare le risposte alle domande frequenti sul punteggio di conformità di Microsoft, che consente alle organizzazioni di semplificare e automatizzare le valutazioni dei rischi.
ms.openlocfilehash: 6ba71620d689e6d028b61ff24f7c837337ef60c6
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016201"
---
# <a name="compliance-score-preview-frequently-asked-questions"></a>Punteggio di conformità (anteprima) domande frequenti

## <a name="what-is-compliance-score"></a>Che cos'è il Punteggio di conformità?

Microsoft Compliance Score è una funzionalità di anteprima del [centro conformità di microsoft 365](microsoft-365-compliance-center.md) che consente di comprendere la posizione di conformità dell'organizzazione. Calcola un punteggio basato sui rischi misurando lo stato di avanzamento del processo di completamento delle azioni che consentono di ridurre i rischi per la protezione dei dati e gli standard normativi. Il Punteggio di conformità fornisce il mapping di controllo incorporato che consente di connettere i controlli comuni tra le normative e gli standard principali. Questo mapping consente di eseguire un'azione per soddisfare più requisiti contemporaneamente, contribuendo a scalare il programma di conformità.

## <a name="whats-new-in-the-preview-version-of-compliance-score"></a>Novità nella versione di anteprima del Punteggio di conformità?

Visitare le [Note sulla versione del Punteggio di conformità](compliance-score-release-notes.md) per informazioni sugli aggiornamenti delle funzionalità e sui problemi noti.

## <a name="how-do-i-access-compliance-score"></a>Come si accede al Punteggio di conformità?

Accedere al [centro conformità di microsoft 365](https://compliance.microsoft.com/) e **accedere** con un ruolo Microsoft 365 Global Admin, compliance admin o Compliance Data admin. Seleziona **Punteggio di conformità** nel riquadro di spostamento a sinistra. Sarà quindi possibile visualizzare il [Dashboard Punteggio di conformità con il Punteggio](compliance-score-setup.md#understand-the-compliance-score-dashboard). Se non si dispone dell'accesso ai ruoli appropriato, l'amministratore globale dell'organizzazione può concedere l'autorizzazione.

## <a name="what-roles-or-permissions-are-needed-to-use-compliance-score"></a>Quali ruoli o autorizzazioni sono necessari per l'utilizzo del Punteggio di conformità?

Il Punteggio di conformità utilizza un modello di autorizzazione di controllo di accesso basato sui ruoli (RBAC). Le azioni che è possibile eseguire dipendono dal tipo di ruolo assegnato all'utente. L'amministratore globale dell'organizzazione Microsoft 365 è la persona che può eseguire le funzioni di installazione e amministrare i ruoli nel punteggio di conformità. Per leggere i dati nel punteggio di conformità, è necessario che gli utenti dispongano almeno del ruolo di **Reader globale di Azure ad** . Per ulteriori informazioni sulle autorizzazioni, i ruoli e le procedure di installazione, vedere [Compliance Score Setup](compliance-score-setup.md).

## <a name="what-is-the-difference-between-compliance-score-and-compliance-manager"></a>Qual è la differenza tra Score compliance e Compliance Manager?

Il Punteggio di conformità e Compliance Manager condividono lo stesso backend. Tutto ciò che si esegue in uno strumento verrà riposto nell'altro strumento. Essi risiedono in due posizioni diverse: Il Punteggio di conformità è nel centro conformità di Microsoft 365 e Compliance Manager è in Microsoft Service Trust Portal. Considerare il Punteggio di conformità come versione semplificata di Compliance Manager, offrendo una visione più completa della posizione di conformità corrente dell'organizzazione e i passaggi che è possibile eseguire per migliorarla.

Anche se è possibile eseguire molte azioni direttamente all'interno del Punteggio di conformità, alcune funzionalità sono disponibili in Compliance Manager durante l'anteprima pubblica. Per ulteriori informazioni, vedere la [relazione tra conformità score e Compliance Manager](compliance-score.md#relationship-to-compliance-manager).

Access [Compliance Manager in Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ComplianceManager/V3). Assicurarsi di **selezionare Compliance Manager** dal menu a discesa di spostamento superiore, che include le funzionalità più recenti, e *non Compliance Manager (Classic)*, che contiene le funzionalità di rilascio anticipato.

## <a name="should-i-use-compliance-score-or-compliance-manager"></a>È consigliabile utilizzare la conformità score o Compliance Manager?

Il Punteggio di conformità è utile per tutti gli utenti dell'organizzazione che svolgono un ruolo di conformità. Con punteggio di conformità, non è necessario avere familiarità con le normative e gli standard per contribuire a migliorare la protezione dei dati dell'organizzazione. Il Punteggio di conformità è il punto di partenza ottimale per tutti gli utenti. Da qui, è possibile visualizzare il Punteggio di conformità, sapere quali azioni consigliate possono contribuire a ridurre al minimo i rischi e gestire le proprie valutazioni.

Per il momento, Compliance Manager è il luogo in cui è possibile creare modelli personalizzati per la creazione di valutazioni. Per ulteriori informazioni, vedere [quali azioni sono supportate solo da Compliance Manager](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager) durante l'anteprima pubblica.

## <a name="if-i-have-a-high-score-does-it-mean-im-fully-compliant"></a>Se si dispone di un punteggio elevato, significa che sono pienamente conforme?

No. Il Punteggio di conformità misura lo stato di avanzamento del completamento delle azioni consigliate che contribuiscono alla riduzione dei rischi per la protezione dei dati e gli standard regolatori. Non esprime una misura assoluta di conformità organizzativa rispetto a una norma o a un regolamento particolari. Il Punteggio di conformità non deve essere interpretato come garanzia in alcun modo.

## <a name="what-regulations-and-standards-does-compliance-score-monitor"></a>Quali normative e standard esegue il monitoraggio del Punteggio conformità?

Punteggio di conformità fornisce un punteggio iniziale basato sulla linea di base per la protezione dei dati di Microsoft 365, che è un insieme di controlli che include normative e standard industriali comuni. Questa linea di base estrae gli elementi principalmente dal NIST CSF (Istituto nazionale per gli standard e la tecnologia Cybersecurity Framework) e ISO (International Organization for Standardizzation), oltre che da FedRAMP (Federal Risk and Authorization Management Program) e GDPR (General Data Protection Regulation dell'Unione europea).

Le organizzazioni possono creare e aggiungere valutazioni personalizzate più rilevanti per la propria organizzazione. Utilizza uno dei [modelli](compliance-score-templates.md)pronti per l'uso del Punteggio di conformità, Personalizza un modello Microsoft con i propri controlli e le proprie azioni oppure crea un modello personalizzato. Leggere i dettagli sull' [utilizzo di valutazioni e modelli](compliance-score-assessments.md).

## <a name="how-does-compliance-score-continuously-assess-my-environment"></a>In che modo il Punteggio di conformità valuta continuamente l'ambiente?

Il Punteggio di conformità analizza automaticamente l'ambiente e utilizza il Punteggio sicuro per rilevare le impostazioni di sistema. Per ulteriori informazioni, vedere [valutazione continua](compliance-score-methodology.md#how-compliance-score-continuously-assesses-controls).

## <a name="what-is-the-difference-between-compliance-score-and-secure-score"></a>Qual è la differenza tra Punteggio di conformità e Punteggio sicuro?

Punteggio di conformità fornisce una panoramica generale delle posizioni di protezione e conformità dei dati dell'organizzazione. Il Punteggio di conformità fornisce anche strumenti di flusso di lavoro incorporati; consente alle organizzazioni di assegnare lavoro agli utenti, di tracciare l'implementazione del controllo e lo stato del test, nonché di caricare le prove e creare rapporti di controllo.

Microsoft Secure Score è uno strumento di analisi della sicurezza che aiuta a comprendere la propria posizione di sicurezza. [Per ulteriori informazioni, vedere Punteggio sicuro e modalità di funzionamento](../security/mtp/microsoft-secure-score-new.md).

## <a name="which-cloud-services-are-covered-by-compliance-score"></a>Quali servizi cloud sono coperti dal punteggio di conformità?

Il Punteggio di conformità fornisce attualmente valutazioni per Office 365 e Intune. La copertura espansa è prevista nelle versioni future e verrà annotata nelle [Note sulla versione del Punteggio di conformità](compliance-score-release-notes.md).

## <a name="can-i-use-compliance-score-for-non-microsoft-products"></a>È possibile utilizzare il Punteggio di conformità per i prodotti non Microsoft?

Mentre il Punteggio di conformità fornisce il monitoraggio continuo e le azioni consigliate solo per i servizi cloud Microsoft, è possibile aggiungere valutazioni personalizzate in Compliance Manager per i servizi di terze parti locali. In questo modo, è possibile utilizzare il Punteggio di conformità di Microsoft come strumento di gestione della conformità SaaS per gestire tutti i controlli nelle risorse digitali.

È possibile utilizzare uno dei [modelli](compliance-score-templates.md) pronti per l'uso del Punteggio di conformità per creare valutazioni per determinati standard o [creare un modello personalizzato](working-with-compliance-manager.md#create-a-template), che è necessario eseguire in Compliance Manager.

## <a name="how-do-i-delete-a-template-or-assessment-i-no-longer-need"></a>Come eliminare un modello o una valutazione che non è più necessaria?

Per eliminare una valutazione, aprire la valutazione che si desidera eliminare e selezionare **Elimina valutazione**. Si noti che l'eliminazione di una valutazione è permanente. Per ulteriori informazioni, vedere [eliminazione di valutazioni](compliance-score-assessments.md#delete-an-assessment). L'eliminazione di una valutazione non comporta l'eliminazione del modello. I modelli non possono essere eliminati, ma possono essere nascosti alla visualizzazione. Leggere [le istruzioni per nascondere i modelli](working-with-compliance-manager.md#hide-a-template-or-an-assessment).

## <a name="what-test-procedures-does-microsoft-follow-for-controls"></a>Quali procedure di test seguono Microsoft per i controlli?

Microsoft partecipa a verifiche annuali per i controlli. È possibile esaminare i report di controllo dei nostri revisori, che sono disponibili per il download da [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3).

## <a name="why-are-some-controls-tested-annually-and-others-tested-every-three-years"></a>Perché alcuni controlli sono stati testati ogni anno e altri sono stati testati ogni tre anni?

La valutazione di FedRAMP è un esempio di come potrebbe essere il caso. Viene condotto ogni anno e verifica una sezione trasversale dei controlli tra le principali famiglie di controllo. FedRAMP classifica i controlli come **Core** quando sono abbastanza importanti da richiedere un test annuale. I controlli designati come non di base vengono testati ogni tre anni. Un sottoinsieme di controlli che si estendono su tutte le famiglie di controlli principali viene testato ogni anno. In questo modo, ogni audit annuale esamina gli scenari su tutti i tavoli per garantire che la soluzione sia robusta. Per ulteriori informazioni, vedere il [processo di valutazione annuale di FedRAMP](https://www.fedramp.gov/annual-assessment-guidance/).
