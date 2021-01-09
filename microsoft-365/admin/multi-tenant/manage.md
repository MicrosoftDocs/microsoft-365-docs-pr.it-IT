---
title: Gestire più tenant
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come utilizzare lo switcher tenant e sulle visualizzazioni multi-tenant.
ms.openlocfilehash: 0b73665159fbc6ce2d1aa99ba1518dc257d88ec8
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790139"
---
# <a name="multi-tenant-management"></a>Gestione multi-tenant

La gestione multi-tenant offre una forma di gestione unificata che consente agli amministratori di amministrare tutti i tenant che gestiscono da un'unica posizione. Se si gestiscono più tenant, è possibile:

- Spostarsi rapidamente tra i tenant gestiti.
- Valutare l'integrità, i prodotti e la fatturazione dei servizi tra più tenant.
- Nella pagina **tutti i tenant** , è possibile visualizzare rapidamente l'integrità di tutti i servizi dei tenant, eventuali richieste di servizi aperti, prodotti e fatturazione e il numero di utenti nel tenant.


## <a name="move-between-tenants"></a>Spostarsi tra i tenant

1. Nell'interfaccia di amministrazione di Microsoft 365 selezionare il nome dell'organizzazione.

    :::image type="content" source="../../media/macorgswitcher.png" alt-text="Switcher multi-tenant.":::

- Dallo **Switcher tenant**, è possibile spostarsi rapidamente tra i tenant gestiti.

    :::image type="content" source="../../media/yourtenantslist.png" alt-text="Elenco tenant con funzionalità di ricerca.":::

## <a name="view-all-tenants-page"></a>Pagina Visualizza tutti i tenant

1. Nell'interfaccia di amministrazione di Microsoft 365, nella barra di spostamento a sinistra, selezionare **tutti i tenant**.
- Nella pagina **tutti i tenant** è possibile
  - Valutare l'integrità del servizio
  - Esaminare l'utilizzo delle licenze
  - Cercare o selezionare il tenant che si desidera gestire
  - È inoltre possibile aggiungere il tenant più visitato all'inizio dell'elenco.


Se il tenant è stato contrassegnato come preferito, viene automaticamente espanso in modo da poter visualizzare immediatamente i dettagli sullo stato.

## <a name="view-service-health-for-all-accounts"></a>Visualizzare l'integrità del servizio per tutti gli account

La visualizzazione integrità del servizio Mostra se eventuali incidenti o avvisi interessano i tenant. Verrà anche illustrato il numero di tenant gestiti coinvolti.

1. Nell'interfaccia di amministrazione di Microsoft 365, nella visualizzazione multi-tenant, selezionare **integrità del servizio**.
2. Nella visualizzazione aggregata della pagina **integrità del servizio** è inoltre possibile visualizzare il numero totale di operazioni non consentite, il numero totale di avvisi che interessano uno dei tenant gestiti e il numero di servizi con incidenti attivi. È anche possibile vedere quanti dei tuoi inquilini sono coinvolti da incidenti e avvisi.
    
    - È possibile utilizzare l'opzione filtro per visualizzare i problemi per tipo di problema o per servizio

    - È possibile esaminare i problemi in **tutti i servizi** o in **tutte le** schede dei problemi.

    :::image type="content" source="../../media/multitenant-servicehealth.png" alt-text="Pagina integrità del servizio multi-tenant.":::
1. Selezionare un evento imprevisto nella scheda **tutti i servizi** o **tutti i problemi** per ottenere ulteriori informazioni su qualsiasi evento imprevisto nella scheda **Panoramica** . Selezionare la scheda degli **inquilini coinvolti** per ottenere un elenco dei tenant coinvolti.

    :::image type="content" source="../../media/tenantsaffected.png" alt-text="Elenco dei tenant coinvolti in un problema di integrità del servizio.":::

L'elenco dei tenant coinvolti può essere esportato in formato CSV in modo che gli amministratori possano condividerlo con i team di supporto.

## <a name="view-a-single-tenant-in-the-microsoft-365-admin-center"></a>Visualizzazione di un singolo tenant nell'interfaccia di amministrazione di Microsoft 365

È possibile tornare all'interfaccia di amministrazione di Microsoft 365 per uno qualsiasi dei tenant dalla pagina **tutti i tenant** .

1. Nella pagina **tutti i tenant** selezionare il nome del tenant per il quale si desidera visualizzare l'interfaccia di amministrazione.
2. Si viene indirizzati all'interfaccia di amministrazione per il tenant.