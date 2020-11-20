---
title: Impostazioni configurabili per Microsoft Managed Desktop
description: Informazioni sulle impostazioni configurabili con Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Documentation, Settings, impostazioni configurabili
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

Microsoft Managed Desktop distribuisce le impostazioni e i criteri applicati a tutti i dispositivi gestiti da Microsoft Managed Desktop. Per ulteriori informazioni, vedere [configurazione dei dispositivi](../service-description/device-policies.md).

Le impostazioni configurabili in Microsoft Managed Desktop offrono agli amministratori un modo per personalizzare e distribuire le impostazioni univoche per la propria organizzazione e le proprie esigenze aziendali. Queste impostazioni sono oltre alle impostazioni di configurazione dei dispositivi e ai criteri gestiti da Microsoft Managed Desktop.  

Le modifiche alle impostazioni configurabili vengono apportate nel cloud e applicate ai dispositivi Microsoft Managed Desktop in gruppi di distribuzione definiti. Questo processo è simile a quello in cui Microsoft Managed Desktop gestisce le modifiche apportate alle impostazioni di configurazione dei dispositivi e ai criteri definiti e gestiti dal servizio. Se si utilizza lo stesso processo utilizzato da Microsoft Managed Desktop per la distribuzione delle modifiche, è possibile continuare a spostare l'organizzazione in avanti, utilizzando le procedure moderne di gestione IT.

## <a name="when-to-use-configurable-settings"></a>Quando utilizzare le impostazioni configurabili?

Per utilizzare le impostazioni configurabili è necessario un numero limitato di volte. 

**Processo di onboarding** : Microsoft Managed Desktop consiglia di personalizzare le impostazioni configurabili quando si esegue l'onboarding di Microsoft Managed Desktop Service o quando si esegue l'onboarding di un numero elevato di dispositivi (20 o più). Le categorie di impostazioni sono configurate nel portale di amministrazione di Microsoft Managed Desktop. Dopo aver eseguito l'onboarding e aver accesso al portale di amministrazione, è possibile decidere quali categorie di impostazioni si desidera personalizzare per l'organizzazione, apportare le modifiche, eseguire la fase di distribuzione e quindi distribuire le modifiche.

**Gestione delle impostazioni** -rivedere le impostazioni regolarmente e rendere necessari gli aggiornamenti. Potrebbe essere necessario apportare modifiche per supportare una modifica all'interno dell'azienda.   

## <a name="setting-categories"></a>Categorie di impostazioni

Di seguito sono riportate le categorie di impostazioni configurabili che è possibile personalizzare:
- [Immagine di sfondo del desktop](config-setting-ref.md#desktop-background-picture) – personalizzare l'immagine di sfondo del desktop per i dispositivi Microsoft Managed Desktop. 
- [Pagine iniziali del browser](config-setting-ref.md#browser-start-pages) – aggiungere le pagine iniziali da utilizzare con Microsoft Edge. Vedere pagina iniziale del browser
- [Elenco siti in modalità Enterprise](config-setting-ref.md#enterprise-mode-site-list-location) -aggiungere siti e la modalità di compatibilità. I siti nell'elenco verranno avviati in Internet Explorer. 
- [Siti attendibili](config-setting-ref.md#trusted-sites) : aggiungere siti attendibili e impostare aree di sicurezza per ogni sito. 
- [Eccezioni dei siti proxy](config-setting-ref.md#proxy) – configurare il numero di indirizzo del server proxy e il numero di porta e aggiungere eccezioni del sito proxy.

Ogni categoria di impostazioni può essere personalizzata e distribuita autonomamente. È possibile distribuire le modifiche a più categorie di impostazioni contemporaneamente, tuttavia, è possibile distribuire una sola modifica alla volta in una categoria di impostazioni.

Ad esempio:
- È possibile distribuire le modifiche apportate all'immagine di sfondo del desktop e ai siti attendibili, ognuno come propria distribuzione, nello stesso momento. 
- Non è possibile distribuire due distribuzioni per le pagine di avvio del browser contemporaneamente. La distribuzione più recente interromperà le distribuzioni precedenti che sono ancora in corso.

## <a name="configurable-setting-process"></a>Processo di impostazione configurabile

Microsoft Managed Desktop consiglia di seguire un processo analogo al seguente quando si utilizzano le impostazioni configurabili per l'organizzazione:

**Passaggio 1-pianificare** : informazioni sulle impostazioni configurabili e decidere quali categorie di impostazioni si desidera configurare per l'organizzazione. Creare una sequenza temporale per il momento in cui si prevede di distribuire le modifiche a ogni gruppo. Pianificare la comunicazione agli utenti che soddisfano i processi di gestione delle modifiche interni. Ad esempio, se si aggiungono pagine iniziali del browser, consentire agli utenti di sapere che dopo la distribuzione avranno un nuovo set di pagine iniziali nel browser.  

**Passaggio 2-Configure and Stage Deployment** -apportare modifiche alle impostazioni configurabili nel portale di amministrazione di Microsoft Managed Desktop. Eseguire il passaggio delle modifiche in modo che siano pronte per la distribuzione. Tenere presente che gli utenti devono conoscere le modifiche e in che modo le modifiche cambiano la propria esperienza del dispositivo.   

Le modifiche vengono configurate e inscenate nel portale di amministrazione di Microsoft Managed Desktop. Per ulteriori informazioni, vedere [personalizzare le impostazioni configurabili](config-setting-ref.md). 

**Passaggio 3: comunicare le modifiche** Comunicare informazioni sulle modifiche imminenti agli utenti. Per ogni distribuzione, completare la comunicazione che fa parte dei processi di gestione delle modifiche. È necessario comunicare chiaramente eventuali modifiche che influiscono sul funzionamento di un utente o su ciò che vedranno nei propri dispositivi.

**Passaggio 4: distribuire** le modifiche – distribuire le modifiche, a partire dal gruppo di test. Il gruppo di testing consente di convalidare e risolvere i problemi di un gruppo con meno dispositivi, prima di distribuire le modifiche ai gruppi più grandi di dispositivi. Se si verificano problemi, è possibile ripristinare la modifica, aggiornare l'impostazione e avviare una nuova distribuzione. Microsoft Managed Desktop consiglia di seguire l'approccio strutturato e distribuire ai gruppi nell'ordine seguente: test, First, Fast e then Broad.   

Tutte le impostazioni configurabili vengono gestite tramite il portale di amministrazione di Microsoft Managed Desktop. Per ulteriori informazioni, vedere [Deploy Changes](config-setting-deploy.md). 

**Passaggio 5-track changes** – monitorare lo stato di avanzamento delle modifiche apportate allo stato di distribuzione. Per ogni impostazione, è possibile:
- **Track Progress** – stato del rilevamento dopo la distribuzione della modifica. Lo stato verrà modificato **in in corso** e quindi **completo** o **non riuscito**. Se una distribuzione ha esito negativo, viene aperta automaticamente una richiesta di supporto per le operazioni di Microsoft Managed Desktop per esaminare il problema.  
- **Vedere la versione distribuita** : ogni modifica distribuita ha un numero di versione.
- **Ripristina modifiche** – il ripristino di una modifica interrompe la distribuzione corrente e ripristina tutti i gruppi alle ultime modifiche che sono state distribuite a tutti i gruppi. Si sta ripristinando il valore dell'impostazione dell'ultima nota.
- **Convalidare le modifiche** -dopo aver completato la distribuzione, convalidare le modifiche sono state applicate come previsto.  

Se una distribuzione ha avuto esito negativo oppure non è possibile ripristinare una modifica, [aprire una richiesta di supporto](admin-support.md) con le operazioni di Microsoft Managed Desktop. 

Per ulteriori informazioni, vedere [deploy and Track configurable settings](config-setting-deploy.md).

## <a name="additional-resources"></a>Risorse aggiuntive
- [Riferimento alle impostazioni configurabili](config-setting-ref.md) 
- [Distribuire impostazioni configurabili](config-setting-deploy.md) 
