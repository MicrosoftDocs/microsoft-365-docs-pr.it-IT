---
title: Impostazioni configurabili per Microsoft Managed Desktop
description: Informazioni sulle impostazioni configurabili con Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione, impostazioni, impostazioni configurabili
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: bf8672ee6c3332ea6f8522f5086d72e58d1b9048
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371491"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>Impostazioni configurabili - Microsoft Managed Desktop

Microsoft Managed Desktop distribuisce le impostazioni e i criteri applicati a tutti i dispositivi gestiti da Microsoft Managed Desktop. Per altre informazioni, vedi [Configurazione del dispositivo.](../service-description/device-policies.md)

Le impostazioni configurabili in Microsoft Managed Desktop offrono agli amministratori IT un modo per personalizzare e distribuire impostazioni specifiche delle esigenze aziendali e dell'organizzazione. Queste impostazioni si sommano alle impostazioni e ai criteri di configurazione dei dispositivi gestiti da Microsoft Managed Desktop.  

Le modifiche alle impostazioni configurabili vengono apportate nel cloud e applicate ai dispositivi Microsoft Managed Desktop in gruppi di distribuzione definiti. Questo processo è simile al modo in cui Microsoft Managed Desktop gestisce le modifiche alle impostazioni e ai criteri di configurazione dei dispositivi definiti e gestiti dal servizio. Utilizzando lo stesso processo utilizzato da Microsoft Managed Desktop per la distribuzione delle modifiche, si continua a spostare l'organizzazione in avanti, utilizzando le moderne procedure di gestione IT.

## <a name="when-to-use-configurable-settings"></a>Quando usare le impostazioni configurabili?

L'utilizzo delle impostazioni configurabili è più volte necessario. 

**Processo di onboarding:** Microsoft Managed Desktop consiglia di personalizzare le impostazioni configurabili quando si esegue l'onboarding nel servizio Microsoft Managed Desktop o quando si esegue l'onboarding di un numero elevato di dispositivi (20 o più). Le categorie di impostazioni sono configurate nel portale di amministrazione di Microsoft Managed Desktop. Dopo l'onboarded e avere accesso al portale di amministrazione, è possibile decidere quali categorie di impostazioni personalizzare per l'organizzazione, apportare le modifiche, eseguire una distribuzione a fasi e quindi distribuire le modifiche.

**Gestire le** impostazioni: rivedere le impostazioni regolarmente e apportare gli aggiornamenti necessari. Potrebbe essere necessario apportare modifiche per supportare una modifica nell'azienda.   

## <a name="setting-categories"></a>Impostazione delle categorie

Ecco le categorie di impostazioni configurabili che è possibile personalizzare:
- [Immagine di sfondo del desktop:](config-setting-ref.md#desktop-background-picture) personalizzare l'immagine di sfondo del desktop per i dispositivi Microsoft Managed Desktop. 
- [Pagine di inizio del browser:](config-setting-ref.md#browser-start-pages) aggiungere le pagine di inizio da usare con Microsoft Edge. Vedere la pagina iniziale del browser
- [Elenco di siti in modalità Enterprise:](config-setting-ref.md#enterprise-mode-site-list-location) aggiungere siti e la relativa modalità di compatibilità. I siti nell'elenco inizieranno in Internet Explorer. 
- [Siti attendibili:](config-setting-ref.md#trusted-sites) aggiungere siti attendibili e impostare aree di sicurezza per ogni sito. 
- [Eccezioni al sito proxy:](config-setting-ref.md#proxy) configurare il numero di porta e il numero di indirizzo del server proxy e aggiungere le eccezioni del sito proxy.

Ogni categoria di impostazioni può essere personalizzata e distribuita da sola. È possibile distribuire le modifiche a più categorie di impostazioni contemporaneamente, tuttavia, è possibile distribuire una sola modifica alla volta in una categoria di impostazioni.

Ad esempio:
- È possibile distribuire le modifiche all'immagine di sfondo del desktop e ai siti attendibili, ognuno come distribuzione propria, contemporaneamente. 
- Non è possibile distribuire due distribuzioni nelle pagine di avvio del browser contemporaneamente. La distribuzione più recente interromperà le distribuzioni precedenti ancora in corso.

## <a name="configurable-setting-process"></a>Processo di impostazione configurabile

Microsoft Managed Desktop consiglia di seguire un processo simile al seguente quando si utilizzano impostazioni configurabili per l'organizzazione:

**Passaggio 1 - Pianificare:** informazioni sulle impostazioni configurabili e decidere quali categorie di impostazioni configurare per l'organizzazione. Creare una sequenza temporale per il momento in cui si prevede di distribuire le modifiche a ogni gruppo. Pianificare le comunicazioni con gli utenti che soddisfano i processi di gestione delle modifiche interni. Ad esempio, se si aggiungono pagine di avvio del browser, in modo che gli utenti sappiano che dopo la distribuzione nel browser sarà presente un nuovo set di pagine iniziale.  

**Passaggio 2 - Configurare e configurare in fasi la distribuzione:** apportare modifiche alle impostazioni configurabili nel portale di amministrazione di Microsoft Managed Desktop. Eseguire le modifiche in fasi in modo che siano pronte per la distribuzione. Ricorda di invii agli utenti informazioni sulle modifiche e su come le modifiche modificheranno l'esperienza del dispositivo.   

È possibile configurare e gestire le modifiche nel portale di amministrazione di Microsoft Managed Desktop. Per ulteriori informazioni, vedere [Personalizzare le impostazioni configurabili.](config-setting-ref.md) 

**Passaggio 3 - Comunicare le modifiche** Comunicare informazioni sulle modifiche future agli utenti. Per ogni distribuzione, completare la comunicazione che fa parte dei processi di gestione delle modifiche. È consigliabile comunicare chiaramente qualsiasi modifica che influisca sul funzionamento di un utente o su ciò che verrà visualizzato nei dispositivi.

**Passaggio 4: distribuire le modifiche:** distribuire le modifiche, a partire dal gruppo Test. Il gruppo Test consente di convalidare e risolvere eventuali problemi in un gruppo con un numero minore di dispositivi, prima di distribuire le modifiche a gruppi di dispositivi più grandi. Se si verificano problemi, è possibile annullare la modifica, aggiornare l'impostazione e configurare una nuova distribuzione. Microsoft Managed Desktop consiglia di seguire l'approccio strutturato e di distribuirlo ai gruppi nell'ordine seguente: Test, First, Fast e quindi Broad.   

Tutte le impostazioni configurabili vengono gestite tramite il portale di amministrazione di Microsoft Managed Desktop. Per ulteriori informazioni, vedere [Distribuire le modifiche.](config-setting-deploy.md) 

**Passaggio 5 - Tenere traccia delle modifiche:** tenere traccia dello stato di avanzamento delle modifiche sullo stato della distribuzione. Per ogni impostazione, è possibile:
- **Tenere traccia dello** stato: tenere traccia dello stato dopo la distribuzione della modifica. Lo stato verrà modificato **in In corso** e quindi sarà **Completato** o **Non riuscito.** Se una distribuzione ha esito negativo, viene aperta automaticamente una richiesta di supporto per Microsoft Managed Desktop Operations per analizzare il problema.  
- **Vedere la versione distribuita:** ogni modifica distribuita ha un numero di versione.
- **Ripristinare le modifiche:** il ripristino di una modifica interrompe la distribuzione corrente e ripristina tutti i gruppi alle ultime modifiche distribuite a tutti i gruppi. Si sta tornando all'ultimo valore di impostazione valido noto.
- **Convalida le modifiche:** al termine della distribuzione, verificare che le modifiche sono state applicate come previsto.  

Se una distribuzione non è riuscita o non è possibile annullare una modifica, aprire [una richiesta di supporto](admin-support.md) con Microsoft Managed Desktop Operations. 

Per ulteriori informazioni, vedere [Distribuire e tenere traccia delle impostazioni configurabili.](config-setting-deploy.md)

## <a name="additional-resources"></a>Risorse aggiuntive
- [Riferimento alle impostazioni configurabili](config-setting-ref.md) 
- [Distribuire impostazioni configurabili](config-setting-deploy.md) 
