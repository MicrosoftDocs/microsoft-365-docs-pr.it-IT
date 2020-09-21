---
title: Come verificare l'integrità del servizio Microsoft 365
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
description: Visualizzare lo stato di integrità dei servizi Microsoft 365 prima di contattare il supporto per verificare se è presente un'interruzione del servizio attiva.
ms.openlocfilehash: 20e19072e1a851fba20e556be696146b8ad57a2f
ms.sourcegitcommit: 392f60efa0921c64ac1462dd63985cd156e6498a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2020
ms.locfileid: "48134076"
---
# <a name="how-to-check-microsoft-365-service-health"></a>Come verificare l'integrità del servizio Microsoft 365

[![Etichetta per comunicare all'utente che l'interfaccia di amministrazione sta cambiando ed è possibile trovare altre informazioni alla pagina aka.ms/aboutM365preview.](../media/O365-Admin-AdminCenterChanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview?view=o365-worldwide&preserve-view=true)

È possibile visualizzare l'integrità dei servizi Microsoft, tra cui Office sul Web, Yammer, Microsoft Dynamics CRM e servizi cloud per la gestione di dispositivi mobili, nella pagina **integrità del servizio** nell'interfaccia di amministrazione di [Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339). If you are experiencing problems with a cloud service, you can check the service health to determine whether this is a known issue with a resolution in progress before you call support or spend time troubleshooting.

Se non si è in grado di accedere al portale del servizio, è possibile utilizzare la [pagina stato del servizio](https://status.office365.com) per verificare la disponibilità di problemi noti che impediscono l'accesso al tenant.
  
### <a name="how-to-check-service-health"></a>Come verificare l'integrità dei servizi

1. Accedere all'interfaccia di amministrazione di Microsoft 365 [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) e accedere con un account di amministratore.

    > [!NOTE]
    > Gli utenti a cui è assegnato il ruolo di amministratore globale o amministratore del servizio possono visualizzare le informazioni sull'integrità dei servizi. Per consentire agli amministratori di Exchange, SharePoint e Skype for Business di visualizzare tali informazioni, è necessario assegnare anche a loro il ruolo di amministratore del servizio. Per ulteriori informazioni sui ruoli che possono visualizzare l'integrità del servizio, vedere [informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true#roles-available-in-the-microsoft-365-admin-center).
  
2. Se non si utilizza il nuovo interfaccia di amministrazione, nella **Home** page selezionare il pulsante **prova il nuovo** interfaccia di amministrazione nell'angolo in alto a destra.

3. Per visualizzare l'integrità del servizio, nell'interfaccia di amministrazione passare **Health**a  >  **integrità del servizio**integrità oppure selezionare la scheda integrità del **servizio** nel **dashboard principale**. La scheda del dashboard indica se esiste un problema del servizio attivo e si collega alla pagina di **integrità del servizio** dettagliato.
  
4. Nella pagina **integrità del servizio** , lo stato di integrità di ogni servizio cloud viene visualizzato in un formato di tabella.

   ![View of current issues in service health](../media/service-health-all-services.png)

La scheda **tutti i servizi** (la visualizzazione predefinita) Visualizza tutti i servizi e lo stato di integrità corrente. Un'icona e la colonna **stato** indicano lo stato di ogni servizio. 

Per filtrare la visualizzazione per i servizi che stanno vivendo un incidente, selezionare la scheda **eventi** non consentiti nella parte superiore della pagina. Selezionando la scheda **avvisi** , verranno visualizzati solo i servizi a cui è attualmente inviato un avviso. 

La scheda **cronologia** Visualizza la cronologia degli incidenti e degli avvisi risolti.

Se si verifica un problema con un servizio Microsoft 365 e non viene visualizzato nell'elenco nella pagina **integrità del servizio** , parlarne selezionando **segnala un problema**e completando la maschera breve. Verranno esaminati i dati correlati e i report di altre organizzazioni per vedere quanto è diffuso il problema e se sono stati originati dal servizio. In tal caso, verrà aggiunto come nuovo incidente o Advisory nella pagina **integrità del servizio** , in cui è possibile monitorarne la risoluzione. Se non viene visualizzato nell'elenco entro circa 30 minuti, prendere in considerazione l'eventualità di contattare il supporto tecnico per risolvere il problema.

Per personalizzare la visualizzazione dei servizi visualizzati nel dashboard, selezionare **Preferenze**  >  **visualizzazione personalizzata**e deselezionare le caselle di controllo per i servizi che si desidera escludere dalla visualizzazione del dashboard di integrità del servizio. Verificare che sia selezionata la casella di controllo per ogni servizio che si desidera monitorare.    

Per iscriversi per le notifiche di posta elettronica di nuovi incidenti che influiscono sul tenant e le modifiche dello stato per un incidente attivo, selezionare **Preferenze**di  >  **posta elettronica**, fare clic su **Invia me notifiche brughiere del servizio nella posta elettronica**e quindi specificare quanto segue:

- Fino a due indirizzi di posta elettronica.
- Se si desiderano notifiche per gli eventi o gli avvisi
- Servizi per i quali si desidera effettuare la notifica

> [!NOTE]
> Ogni amministratore può impostare le proprie preferenze e il limite massimo di due indirizzi di posta elettronica è per account di amministratore.

> [!TIP]
> È inoltre possibile utilizzare l' [app Microsoft 365 admin](https://go.microsoft.com/fwlink/p/?linkid=627216) sul dispositivo mobile per visualizzare l'integrità del servizio, che è un ottimo modo per rimanere aggiornati con le notifiche push. 
  
### <a name="view-details-of-posted-service-health"></a>Visualizzare i dettagli delle informazioni pubblicate sull'integrità dei servizi

Nella visualizzazione **tutti i servizi** , selezionando lo stato del servizio, verrà aperta una visualizzazione riepilogativa degli avvisi o degli incidenti.
  
[![Schermata che mostra l'Advisory ](../media/service-health-advisory.png) del servizio](../media/service-health-advisory.png#lightbox)

Il riepilogo dell'avviso o dell'evento imprevisto include le informazioni seguenti:

- **Title** -sintesi del problema.
- **Service** : il nome del servizio in questione.
- **ID** : identificatore numerico del problema.
- **Stato** -come questo problema influisce sul servizio.
- **Ora di inizio** : l'ora in cui è stato avviato il problema.
- **Ultimo aggiornamento** : l'ultima volta che il messaggio di integrità del servizio è stato aggiornato. Vengono inviati messaggi frequenti che consentono di conoscere i progressi compiuti nell'applicazione di una soluzione.

Selezionare il titolo del problema per visualizzare la pagina dei dettagli del problema, in cui vengono visualizzate altre informazioni sul problema, inclusa la [cronologia](#history) di tutti i messaggi inviati mentre si lavora su una soluzione.

![Schermata che mostra i dettagli del problema](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a>Tradurre le informazioni sull'integrità dei servizi

Le spiegazioni sull'integrità dei servizi vengono pubblicate in tempo reale, di conseguenza non vengono tradotte automaticamente nelle varie lingue e i dettagli di un evento del servizio sono disponibili solo in inglese. Per tradurre la spiegazione, seguire questa procedura:
  
1. Passare a [Translator](https://www.bing.com/translator/).

2. Nella pagina **Integrità dei servizi** selezionare un evento imprevisto o un avviso. In **Mostra dettagli** copiare il testo relativo al problema.

3. In Translator incollare il testo e quindi scegliere **Traduci**.

### <a name="definitions"></a>Definizioni

Per la maggior parte dei casi, i servizi verranno visualizzati come integri senza ulteriori informazioni. Un problema che si verificato in un servizio viene identificato come avviso o evento imprevisto ed è contraddistinto dallo stato corrente.
  
> [!TIP]
> Nelle informazioni sull'integrità dei servizi non vengono visualizzati gli eventi di manutenzione pianificata. Per tenere traccia degli eventi di manutenzione pianificata, è possibile consultare le informazioni aggiornate del **Centro messaggi**. Filtrare in base ai messaggi classificati come pianificati per la modifica per scoprire quando avrà luogo la modifica, quale sarà il suo effetto e come prepararsi. Per ulteriori informazioni, vedere [Message Center in Microsoft 365](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093) .
  
### <a name="incidents-and-advisories"></a>Eventi imprevisti e avvisi

| Icona | Descrizione |
|:-----|:-----|
|![Information icon for advisory](../media/a7f5fd21-c760-4948-9bc1-50f7c8070e28.png)|Se per un servizio è visualizzato un avviso, si tratta di un problema noto che interessa alcuni utenti, ma il servizio è ancora disponibile. In un avviso è spesso inclusa una soluzione alternativa del problema. Il problema potrebbe inoltre essere intermittente o limitato in termini di ambito e impatto sugli utenti.  <br/> |
|![Exclamation point icon for incident](../media/a636db57-6083-44dc-bbd5-556850804f17.png)|Se per un servizio è visualizzato un incidente attivo, si tratta di un problema critico, di conseguenza il servizio o una funzione principale del servizio risulta non disponibile. Gli utenti potrebbero, ad esempio, non riuscire a inviare e ricevere posta elettronica o a eseguire l'accesso. Gli incidenti avranno un notevole impatto sugli utenti. Quando è in corso un incidente, nel dashboard per l'integrità dei servizi vengono fornite informazioni aggiornate sullo stato dell'analisi del problema, le operazioni eseguite per contenerlo e la conferma della risoluzione.  <br/> |

### <a name="status-definitions"></a>Definizioni degli stati

| Stato | Definizione |
|:-----|:-----|
|**Indagando** | Si tratta di un potenziale problema noto per il quale il team Microsoft sta raccogliendo ulteriori informazioni sul comportamento e sulla portata dell'impatto. |
|**Riduzione del servizio** | È stato confermato che si tratta di un problema che potrebbe influire sull'uso di un servizio o di una funzionalità. Questo stato potrebbe essere visualizzato se, ad esempio, si verificano rallentamenti in un servizio, ci sono interruzioni intermittenti oppure se una funzionalità non funziona. |
|**Interruzione del servizio** | Questo stato viene visualizzato se è stato stabilito che un problema non consente agli utenti di accedere al servizio. In questo caso, il problema è importante e può essere riprodotto più volte. |
|**Ripristino del servizio in corso** | La causa del problema è stata identificata, l'azione correttiva è nota e il servizio verrà ripristinato a breve. |
|**Ripristino esteso** | Questo stato indica che è in corso un'azione correttiva per ripristinare il servizio per la maggior parte degli utenti, ma il ripristino di tutti i sistemi interessati potrebbe richiedere più tempo. Questo stato viene visualizzato anche se è stata applicata una soluzione temporanea per limitare l'impatto in attesa di una correzione permanente. |
|**Analisi sospesa** | Questo stato viene visualizzato se, in seguito all'analisi dettagliata di un potenziale problema, il team di supporto deve richiedere maggiori informazioni ai clienti. In tal caso, il team comunicherà all'utente quali dati e log sono necessari. |
|**Servizio ripristinato** | È stato verificato che l'azione correttiva ha consentito di risolvere il problema sottostante e il servizio è stato ripristinato. Per scoprire la causa dell'errore, visualizzare i dettagli del problema. |
|**Falso positivo** | Dopo un'indagine dettagliata, è stato confermato che il servizio è integro e funziona come previsto. Nessun impatto sul servizio è stato osservato o la causa dell'incidente ha avuto origine all'esterno del servizio. |
|**Rapporto post-evento pubblicato** | È stato pubblicato un rapporto post-evento per un problema specifico che include informazioni sulla causa principale e i passaggi successivi per garantire che un problema simile non venga rigenerato. |

### <a name="history"></a>Cronologia

L'integrità del servizio consente di esaminare lo stato di integrità corrente e di visualizzare la cronologia di eventuali avvisi e incidenti di servizio che hanno influenzato il tenant negli ultimi 30 giorni. Per visualizzare l'integrità passata di tutti i servizi, selezionare **Visualizza cronologia** nella pagina Dettagli problema.
  
![Show link to health history](../media/service-health-view-history.png)
  
Viene visualizzato un elenco di tutti i messaggi di integrità dei servizi pubblicati nell'intervallo di tempo selezionato, come illustrato di seguito:
  
![View service health history](../media/service-health-history.png)
  
Espandere qualsiasi riga per visualizzare ulteriori dettagli sul problema.
  
Per ulteriori informazioni sul nostro impegno per il tempo di attività, vedere [Transparent Operations from Microsoft 365](https://go.microsoft.com/fwlink/?linkid=848695).

## <a name="related-topics"></a>Argomenti correlati

[Report attività nell'interfaccia di amministrazione](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 
 di Microsoft 365 [Preferenze del centro messaggi](https://docs.microsoft.com/microsoft-365/admin/manage/message-center?view=o365-worldwide&preserve-view=true#preferences11)
