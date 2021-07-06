---
title: Come verificare l'integrità dei servizi di Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_ServiceHealthModern
- O365M_ServiceHealthModern
- O365E_ViewStatusServices
- O365E_ServiceHealthModern
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
- IWA160
ms.assetid: 932ad3ad-533c-418a-b938-6e44e8bc33b0
description: Visualizzare lo stato di integrità dei Microsoft 365 prima di chiamare il supporto per verificare se si è verificata un'interruzione del servizio attiva.
ms.openlocfilehash: 95ab260b4950d261eed1288b8fdf1f59883ff15f
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300406"
---
# <a name="how-to-check-microsoft-365-service-health"></a>Come verificare l'integrità dei servizi di Microsoft 365

[![Etichetta per comunicare all'utente che l'interfaccia di amministrazione sta cambiando ed è possibile trovare altre informazioni alla pagina aka.ms/aboutM365preview.](../media/O365-Admin-AdminCenterChanging.png)](/office365/admin/microsoft-365-admin-center-preview?preserve-view=true&view=o365-worldwide)

È possibile visualizzare l'integrità del servizi Microsoft, inclusi Office sul web, Yammer, Microsoft Dynamics CRM e servizi cloud di gestione dei  dispositivi mobili, nella pagina Integrità dei servizi nella pagina Integrità [dei interfaccia di amministrazione di Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339). If you are experiencing problems with a cloud service, you can check the service health to determine whether this is a known issue with a resolution in progress before you call support or spend time troubleshooting.

Se non è possibile accedere all'interfaccia di [](https://status.office365.com) amministrazione, è possibile utilizzare la pagina dello stato del servizio per verificare la presenza di problemi noti che impediscono l'accesso al tenant.  Iscriviti anche per seguirci [all'@MSFT365status](https://twitter.com/MSFT365Status) su Twitter per visualizzare informazioni su determinati eventi.

## <a name="how-to-check-service-health"></a>Come verificare l'integrità dei servizi

1. Vai al interfaccia di amministrazione di Microsoft 365 su [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) e accedi con un account amministratore.

    > [!NOTE]
    > Gli utenti a cui è assegnato il ruolo di amministratore globale o di amministratore del supporto del servizio possono visualizzare l'integrità del servizio. Per consentire agli amministratori di Exchange, SharePoint e Skype for Business di visualizzare tali informazioni, è necessario assegnare anche a loro il ruolo di amministratore del servizio. Per ulteriori informazioni sui ruoli che possono visualizzare l'integrità del servizio, vedere [Informazioni sui ruoli di amministratore.](../admin/add-users/about-admin-roles.md?preserve-view=true&view=o365-worldwide#commonly-used-microsoft-365-admin-center-roles)

2. Per visualizzare l'integrità del servizio, nell'interfaccia di amministrazione passare **a** Integrità servizio integrità oppure selezionare la scheda Integrità servizio nel dashboard  >   **principale.**  La scheda del dashboard indica se è presente un problema di servizio attivo e collegamenti alla pagina dettagliata **sull'integrità del** servizio.

3. Nella pagina **Integrità servizio** lo stato di integrità di ogni servizio cloud viene visualizzato in formato tabella.

   ![View of current issues in service health](../media/service-health-all-services.png)

La **scheda Tutti i** servizi (visualizzazione predefinita) mostra tutti i servizi, il relativo stato di integrità corrente e gli eventuali eventi imprevisti o avvisi attivi. Un'icona e uno stato nella **colonna Integrità** indicano lo stato di ogni servizio.

Se è presente un evento imprevisto o un avviso attivo per un servizio, questi verranno elencati direttamente sotto il nome del servizio in una tabella annidata. È possibile comprimere la tabella annidata per nascondere gli eventi imprevisti o gli avvisi in questa visualizzazione facendo clic sull'icona a forma di freccia a sinistra del nome del servizio.   

Per filtrare la visualizzazione in modo da  visualizzare solo tutti gli eventi imprevisti attivi, selezionare la scheda Eventi imprevisti nella parte superiore della pagina. Selezionando la **scheda Avvisi** verranno visualizzati solo tutti gli avvisi attivi pubblicati.

La **scheda** Cronologia mostra tutti gli eventi imprevisti e gli avvisi risolti negli ultimi sette o 30 giorni.

Se si verifica un problema con un servizio Microsoft 365 e non lo si  vede nella pagina Integrità del servizio, indicarlo selezionando Segnala un problema e completando il breve modulo. Verranno visualizzati i dati e i report correlati di altre organizzazioni per verificare la diffusione del problema e se ha avuto origine con il servizio. In caso contrario, verrà aggiunto come nuovo evento imprevisto o avviso nella pagina Integrità del servizio, in cui è possibile tenere traccia della risoluzione.  Nella **pagina Problemi** segnalati verranno visualizzati tutti i problemi segnalati dal tenant da questo modulo e lo stato.

Per personalizzare la visualizzazione dei servizi visualizzati nel dashboard, selezionare Preferenze Visualizzazione personalizzata e deselezionare le caselle di controllo per i servizi che si desidera filtrare dalla visualizzazione dashboard integrità  >  dei servizi. Verificare che la casella di controllo sia selezionata per ogni servizio che si desidera monitorare.

Per iscriversi alle notifiche tramite posta elettronica di nuovi eventi imprevisti che influiscono sul tenant e sulle modifiche dello stato per un evento imprevisto attivo, selezionare Preferenze Posta elettronica, fare clic su Invia notifiche di servizio tramite posta elettronica e quindi  >  specificare: 

- Fino a due indirizzi di posta elettronica.
- Indica se si desiderano notifiche per eventi imprevisti o avvisi
- Servizi per cui si desidera notificare

È inoltre possibile sottoscrivere notifiche tramite posta elettronica per singoli eventi anziché per ogni evento per un servizio. A tale scopo, selezionare il problema attivo per cui si desidera ricevere gli aggiornamenti delle notifiche tramite posta elettronica, selezionare **Gestisci notifiche per questo** problema e quindi specificare: 
- Fino a due indirizzi di posta elettronica.

> [!NOTE]
> Ogni amministratore può avere le proprie preferenze impostate e il limite precedente di due indirizzi di posta elettronica è per ogni account amministratore.

> [!TIP]
> Puoi anche usare [l'app Amministrazione Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=627216) sul dispositivo mobile per visualizzare l'integrità del servizio, un ottimo modo per rimanere al corrente con le notifiche push.

### <a name="view-details-of-posted-service-health"></a>Visualizzare i dettagli delle informazioni pubblicate sull'integrità dei servizi

Nella visualizzazione **Tutti i** servizi selezionare il titolo del problema per visualizzare la pagina dei dettagli del problema, che mostra ulteriori informazioni sul problema, incluso un feed di tutti i messaggi pubblicati mentre si lavora a una soluzione. 

[![Screenshot che mostra l'avviso del servizio ](../media/service-health-advisory.png)](../media/service-health-advisory.png#lightbox)

Il riepilogo dell'avviso o dell'evento imprevisto include le informazioni seguenti:

- **Title** : riepilogo del problema.
- **ID** - Identificatore numerico per il problema.
- **Service** - Nome del servizio interessato.
- **Last updated** - L'ultima volta che il messaggio di integrità del servizio è stato aggiornato.
- **Tempo di inizio stimato** - Tempo stimato per l'avvio del problema.
- **Status** : in che modo questo problema influisce sul servizio.
- **Impatto utente** - Breve descrizione dell'impatto di questo problema sull'utente finale.
- **Tutti gli** aggiornamenti: vengono inviati messaggi frequenti per inserirti sullo stato di avanzamento dell'applicazione di una soluzione.

![Screenshot che mostra i dettagli del problema](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a>Tradurre le informazioni sull'integrità dei servizi

Usiamo la traduzione automatica per visualizzare automaticamente i messaggi nella lingua preferita. Per [ulteriori informazioni su come impostare la lingua,](/microsoft-365/admin/manage/language-translation-for-message-center-posts) vedere Traduzione in lingua per i post del Centro messaggi.

### <a name="definitions"></a>Definizioni

Nella maggior parte dei casi, i servizi verranno visualizzati come integri senza ulteriori informazioni. Un problema che si verificato in un servizio viene identificato come avviso o evento imprevisto ed è contraddistinto dallo stato corrente.

> [!TIP]
> Nelle informazioni sull'integrità dei servizi non vengono visualizzati gli eventi di manutenzione pianificata. Per tenere traccia degli eventi di manutenzione pianificata, è possibile consultare le informazioni aggiornate del **Centro messaggi**. Filtrare in base ai messaggi classificati come pianificati per la modifica per scoprire quando avrà luogo la modifica, quale sarà il suo effetto e come prepararsi. Per [ulteriori dettagli, vedere Message center in Microsoft 365.](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093)

### <a name="incidents-and-advisories"></a>Eventi imprevisti e avvisi

| Icona | Descrizione |
|:-----|:-----|
|![Information icon for advisory](../media/a7f5fd21-c760-4948-9bc1-50f7c8070e28.png)|Se per un servizio è visualizzato un avviso, si tratta di un problema noto che interessa alcuni utenti, ma il servizio è ancora disponibile. In un avviso è spesso inclusa una soluzione alternativa del problema. Il problema potrebbe inoltre essere intermittente o limitato in termini di ambito e impatto sugli utenti.  <br/> |
|![Exclamation point icon for incident](../media/a636db57-6083-44dc-bbd5-556850804f17.png)|Se per un servizio è visualizzato un incidente attivo, si tratta di un problema critico, di conseguenza il servizio o una funzione principale del servizio risulta non disponibile. Gli utenti potrebbero, ad esempio, non riuscire a inviare e ricevere posta elettronica o a eseguire l'accesso. Gli incidenti avranno un notevole impatto sugli utenti. Quando è in corso un incidente, nel dashboard per l'integrità dei servizi vengono fornite informazioni aggiornate sullo stato dell'analisi del problema, le operazioni eseguite per contenerlo e la conferma della risoluzione.  <br/> |

### <a name="status-definitions"></a>Definizioni degli stati

| Stato | Definizione |
|:-----|:-----|
|**Analisi** | Si tratta di un potenziale problema noto per il quale il team Microsoft sta raccogliendo ulteriori informazioni sul comportamento e sulla portata dell'impatto. |
|**Riduzione del servizio** | È stato confermato che si tratta di un problema che potrebbe influire sull'uso di un servizio o di una funzionalità. Questo stato potrebbe essere visualizzato se, ad esempio, si verificano rallentamenti in un servizio, ci sono interruzioni intermittenti oppure se una funzionalità non funziona. |
|**Interruzione del servizio** | Questo stato viene visualizzato se è stato stabilito che un problema non consente agli utenti di accedere al servizio. In questo caso, il problema è importante e può essere riprodotto più volte. |
|**Ripristino del servizio in corso** | La causa del problema è stata identificata, l'azione correttiva è nota e il servizio verrà ripristinato a breve. |
|**Ripristino esteso** | Questo stato indica che è in corso un'azione correttiva per ripristinare il servizio per la maggior parte degli utenti, ma il ripristino di tutti i sistemi interessati potrebbe richiedere più tempo. Questo stato viene visualizzato anche se è stata applicata una soluzione temporanea per limitare l'impatto in attesa di una correzione permanente. |
|**Analisi sospesa** | Questo stato viene visualizzato se, in seguito all'analisi dettagliata di un potenziale problema, il team di supporto deve richiedere maggiori informazioni ai clienti. In tal caso, il team comunicherà all'utente quali dati e log sono necessari. |
|**Servizio ripristinato** | È stato verificato che l'azione correttiva ha consentito di risolvere il problema sottostante e il servizio è stato ripristinato. Per scoprire la causa dell'errore, visualizzare i dettagli del problema. |
|**Falso positivo** | Dopo un'indagine dettagliata, abbiamo confermato che il servizio è integro e funziona come progettato. Non è stato rilevato alcun impatto sul servizio o la causa dell'incidente è stata originata all'esterno del servizio. |
|**Report post-incidente pubblicato** | È stato pubblicato un rapporto post-incidente per un problema specifico che include informazioni sulla causa radice e passaggi successivi per garantire che un problema simile non si ripresenta. |

### <a name="message-post-types"></a>Tipi di post messaggio

| Tipo | Definizione |
|:-----|:-----|
|**Aggiornamento rapido** | Aggiornamenti incrementali brevi e frequenti per eventi imprevisti a impatto generale, disponibili per tutti i clienti. |
|**Dettagli aggiuntivi** | Questi post aggiuntivi forniranno dettagli tecnici e di risoluzione più completi per offrire una maggiore visibilità nella gestione degli incidenti. Questa opzione è disponibile per i tenant che soddisfano gli stessi requisiti descritti per il [Exchange Online,](/microsoft-365/enterprise/microsoft-365-exchange-monitoring?view=o365-worldwide#requirements) |

### <a name="history"></a>Cronologia

L'integrità del servizio consente di esaminare lo stato di integrità corrente e di visualizzare la cronologia di eventuali avvisi e eventi imprevisti del servizio che hanno interessato il tenant negli ultimi 30 giorni. Per visualizzare l'integrità passata di tutti i servizi, selezionare **Visualizzazione** Cronologia.

Per ulteriori informazioni sull'impegno per il tempo di attività, vedere [Transparent operations from Microsoft 365](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity).

## <a name="related-topics"></a>Argomenti correlati

[Report attività nella interfaccia di amministrazione di Microsoft 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

[Preferenze centro messaggi](../admin/manage/message-center.md?preserve-view=true&view=o365-worldwide#preferences)

[Come verificare l'integrità Windows rilascio nell'interfaccia di amministrazione](/windows/deployment/update/check-release-health)
