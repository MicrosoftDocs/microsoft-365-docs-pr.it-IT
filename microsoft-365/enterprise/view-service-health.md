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
description: Visualizzare lo stato di integrità dei servizi di Microsoft 365 prima di chiamare il supporto per verificare se si è verificata un'interruzione del servizio attiva.
ms.openlocfilehash: b1819e455732d142c563f598433c410b0ae60882
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2020
ms.locfileid: "49072760"
---
# <a name="how-to-check-microsoft-365-service-health"></a>Come verificare l'integrità dei servizi di Microsoft 365

[![Etichetta per comunicare all'utente che l'interfaccia di amministrazione sta cambiando ed è possibile trovare altre informazioni alla pagina aka.ms/aboutM365preview.](../media/O365-Admin-AdminCenterChanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview?view=o365-worldwide&preserve-view=true)

You can view the health of your Microsoft services, including Office on the web, Yammer, Microsoft Dynamics CRM, and mobile device management cloud services, on the **Service health** page in the [Microsoft 365 admin center.](https://go.microsoft.com/fwlink/p/?linkid=2024339) If you are experiencing problems with a cloud service, you can check the service health to determine whether this is a known issue with a resolution in progress before you call support or spend time troubleshooting.

Se non è possibile accedere all'interfaccia di [](https://status.office365.com) amministrazione, è possibile utilizzare la pagina dello stato del servizio per verificare la presenza di problemi noti che impediscono l'accesso al tenant.  Iscriviti anche per seguirci [all'indirizzo @MSFT365status](https://twitter.com/MSFT365Status) su Twitter per visualizzare informazioni su determinati eventi.

  
### <a name="how-to-check-service-health"></a>Come verificare l'integrità dei servizi

1. Accedere all'interfaccia di amministrazione di Microsoft 365 all'indirizzo [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) e accedere con un account amministratore.

    > [!NOTE]
    > Gli utenti a cui è assegnato il ruolo di amministratore globale o amministratore del servizio possono visualizzare le informazioni sull'integrità dei servizi. Per consentire agli amministratori di Exchange, SharePoint e Skype for Business di visualizzare tali informazioni, è necessario assegnare anche a loro il ruolo di amministratore del servizio. Per ulteriori informazioni sui ruoli che possono visualizzare l'integrità del servizio, vedere [Informazioni sui ruoli di amministratore.](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true#roles-available-in-the-microsoft-365-admin-center)
  
2. Se non si utilizza la nuova interfaccia di amministrazione, nella **home** page selezionare l'interruttore Prova la nuova interfaccia di amministrazione nell'angolo superiore destro. 

3. Per visualizzare l'integrità dei servizi, nell'interfaccia di amministrazione passare **a** Integrità dei servizi di integrità o selezionare la scheda integrità del servizio nel  >  dashboard **principale.**  La scheda del dashboard indica se è presente un problema di servizio attivo e collegamenti alla pagina dettagliata **sull'integrità dei** servizi.
  
4. Nella pagina **Integrità dei** servizi, lo stato di integrità di ogni servizio cloud viene visualizzato in un formato di tabella.

   ![View of current issues in service health](../media/service-health-all-services.png)

Nella **scheda Tutti i** servizi (visualizzazione predefinita) vengono visualizzati tutti i servizi e il relativo stato di integrità corrente. Un'icona e **la colonna** Stato indicano lo stato di ogni servizio. 

Per filtrare la visualizzazione in base ai servizi in cui si è verificato un evento imprevisto, selezionare la scheda Eventi **imprevisti** nella parte superiore della pagina. Se si **seleziona la scheda** Avvisi, verranno visualizzati solo i servizi per cui è stato pubblicato un avviso. 

La **scheda Cronologia** mostra la cronologia degli eventi imprevisti e degli avvisi che sono stati risolti.

Se si verifica un problema con un servizio di Microsoft 365 e  non è presente nella pagina Integrità dei servizi, indicarlo selezionando Segnala un problema e completando il breve modulo. Verranno visualizzati i dati e i report correlati di altre organizzazioni per verificare la diffusione del problema e l'origine del servizio. In caso contrario, verrà aggiunto come nuovo evento imprevisto o avviso nella pagina Integrità dei servizi, in cui è possibile tenere traccia della relativa risoluzione.  Se non viene visualizzato nell'elenco entro circa 30 minuti, prendere in considerazione la possibilità di contattare il supporto tecnico per risolvere il problema.

Per personalizzare la visualizzazione dei servizi visualizzati nel dashboard, selezionare Visualizzazione personalizzata preferenze e deselezionare le caselle di controllo relative ai servizi che si desidera filtrare dalla visualizzazione dashboard integrità  >  dei servizi. Verificare che la casella di controllo sia selezionata per ogni servizio che si desidera monitorare.    

Per registrarsi per ricevere notifiche tramite posta elettronica di nuovi eventi imprevisti che influiscono sul tenant e modifiche di stato per un evento imprevisto attivo, selezionare Preferenze e-mail, fare clic su  >   **Inviami** notifiche di notifica tramite posta elettronica e quindi specificare:

- Fino a due indirizzi di posta elettronica.
- Se si desiderano notifiche per eventi imprevisti o avvisi
- Servizi per i quali si desidera notificare

> [!NOTE]
> Ogni amministratore può avere le proprie preferenze impostate e il limite di due indirizzi di posta elettronica sopra indicato è per ogni account amministratore.

> [!TIP]
> È anche possibile usare l'app Amministratore di [Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=627216) nel dispositivo mobile per visualizzare l'integrità dei servizi, un ottimo modo per rimanere al corrente delle notifiche push. 
  
### <a name="view-details-of-posted-service-health"></a>Visualizzare i dettagli delle informazioni pubblicate sull'integrità dei servizi

Nella visualizzazione **Tutti i servizi,** selezionando lo stato del servizio verrà aperta una visualizzazione di riepilogo degli avvisi o degli eventi imprevisti.
  
[![Screenshot che mostra l'avviso del servizio ](../media/service-health-advisory.png)](../media/service-health-advisory.png#lightbox)

Il riepilogo dell'avviso o dell'evento imprevisto include le informazioni seguenti:

- **Titolo:** un riepilogo del problema.
- **Service** - Nome del servizio interessato.
- **ID** - Identificatore numerico del problema.
- **Status** : in che modo questo problema influisce sul servizio.
- **Ora di** inizio - Ora in cui è stato avviato il problema.
- **Last updated-** L'ultima volta in cui il messaggio di integrità del servizio è stato aggiornato. Vengono inviati messaggi frequenti che consentono di conoscere lo stato di avanzamento dell'applicazione di una soluzione.

Selezionare il titolo del problema per visualizzare la pagina dei dettagli [](#history) del problema, che mostra ulteriori informazioni sul problema, inclusa la cronologia di tutti i messaggi inseriti mentre si lavora a una soluzione.

![Screenshot che mostra i dettagli del problema](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a>Tradurre le informazioni sull'integrità dei servizi

Le spiegazioni sull'integrità dei servizi vengono pubblicate in tempo reale, di conseguenza non vengono tradotte automaticamente nelle varie lingue e i dettagli di un evento del servizio sono disponibili solo in inglese. Per tradurre la spiegazione, seguire questa procedura:
  
1. Passare a [Translator](https://www.bing.com/translator/).

2. Nella pagina **Integrità dei servizi** selezionare un evento imprevisto o un avviso. In **Mostra dettagli** copiare il testo relativo al problema.

3. In Translator incollare il testo e quindi scegliere **Traduci**.

### <a name="definitions"></a>Definizioni

Nella maggior parte dei casi, i servizi vengono visualizzati come integri senza ulteriori informazioni. Un problema che si verificato in un servizio viene identificato come avviso o evento imprevisto ed è contraddistinto dallo stato corrente.
  
> [!TIP]
> Nelle informazioni sull'integrità dei servizi non vengono visualizzati gli eventi di manutenzione pianificata. Per tenere traccia degli eventi di manutenzione pianificata, è possibile consultare le informazioni aggiornate del **Centro messaggi**. Filtrare in base ai messaggi classificati come pianificati per la modifica per scoprire quando avrà luogo la modifica, quale sarà il suo effetto e come prepararsi. Per altri dettagli, vedere Centro messaggi [in Microsoft 365.](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093)
  
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
|**Falso positivo** | Dopo un'indagine dettagliata, abbiamo confermato che il servizio è integro e operativo come progettato. Non è stato rilevato alcun impatto sul servizio o la causa dell'incidente ha avuto origine all'esterno del servizio. |
|**Report post-evento imprevisto pubblicato** | We've published a Post Incident Report for a specific issue that includes root cause information and next steps to ensure a similar issue doesn't reoccur. |

### <a name="history"></a>Cronologia

L'integrità dei servizi consente di esaminare lo stato di integrità corrente e di visualizzare la cronologia degli avvisi e degli eventi imprevisti che hanno interessato il tenant negli ultimi 30 giorni. Per visualizzare l'integrità passata di tutti i servizi, selezionare **Visualizza cronologia** nella pagina dei dettagli del problema.
  
![Show link to health history](../media/service-health-view-history.png)
  
Viene visualizzato un elenco di tutti i messaggi di integrità dei servizi pubblicati nell'intervallo di tempo selezionato, come illustrato di seguito:
  
![View service health history](../media/service-health-history.png)
  
Espandere una riga qualsiasi per visualizzare ulteriori dettagli sul problema.
  
Per altre informazioni sul nostro impegno per il tempo di attività, vedere [Operazioni trasparenti da Microsoft 365.](https://go.microsoft.com/fwlink/?linkid=848695)

## <a name="related-topics"></a>Argomenti correlati

[Report attività nell'interfaccia di amministrazione di](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 
 Microsoft 365 [Preferenze del Centro messaggi](https://docs.microsoft.com/microsoft-365/admin/manage/message-center?view=o365-worldwide&preserve-view=true#preferences11)
