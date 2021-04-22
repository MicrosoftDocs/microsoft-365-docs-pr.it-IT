---
title: Ricevere notifiche di eventi imprevisti tramite posta elettronica in Microsoft 365 Defender
description: Informazioni su come creare regole per ricevere notifiche tramite posta elettronica per eventi imprevisti in Microsoft 365 Defender
keywords: incident, email, email notfications, configure, users, mailbox, email, incidents, analyze, response
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 7ba21e08f72760654993335764df00e78abc87b2
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939719"
---
# <a name="get-incident-notifications-by-email"></a>Ricevere notifiche di eventi imprevisti tramite posta elettronica

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

Puoi configurare Microsoft 365 Defender per informare il personale con un messaggio di posta elettronica di nuovi eventi imprevisti o aggiornamenti di eventi imprevisti esistenti. Puoi scegliere di ricevere notifiche in base a:

- Gravità dell'evento imprevisto.
- Gruppo di dispositivi.
- Solo al primo aggiornamento per evento imprevisto.

La notifica di posta elettronica contiene dettagli importanti sull'evento imprevisto, ad esempio il nome, la gravità e le categorie dell'evento imprevisto, tra gli altri. Puoi anche passare direttamente all'evento imprevisto e iniziare subito l'analisi. Per ulteriori informazioni, vedere [Analyze incidents](investigate-incidents.md).

È possibile aggiungere o rimuovere destinatari nelle notifiche di posta elettronica. Dopo l'aggiunta, i nuovi destinatari riceveranno una notifica sugli eventi imprevisti. 

>[!NOTE]
>È necessaria l'autorizzazione "Gestisci impostazioni di sicurezza" per configurare le impostazioni di notifica tramite posta elettronica. Se si è scelto di utilizzare la gestione delle autorizzazioni di base, gli utenti con ruoli amministratore della sicurezza o amministratore globale possono configurare automaticamente le notifiche di posta elettronica. <br> <br>
Allo stesso modo, se l'organizzazione utilizza il controllo di accesso basato sui ruoli(RBAC), è possibile creare, modificare, eliminare e ricevere notifiche in base ai gruppi di dispositivi che sono autorizzati a gestire.

## <a name="create-a-rule-for-email-notifications"></a>Creare una regola per le notifiche di posta elettronica

Seguire questa procedura per creare una nuova regola e personalizzare le impostazioni di notifica tramite posta elettronica.

1. Nel riquadro di spostamento seleziona Impostazioni > notifiche di posta elettronica di **Microsoft 365 Defender > eventi imprevisti**.
2. Selezionare **Aggiungi elemento**.
3. Nella pagina **Nozioni di** base digitare il nome della regola e una descrizione e quindi selezionare **Avanti.**
4. Nella pagina **Impostazioni notifica** configurare:
    - **Gravità avviso:** scegliere le gravità dell'avviso che attiveranno una notifica di evento imprevisto. Ad esempio, se si desidera essere informati solo su eventi imprevisti di gravità elevata, selezionare **Alta**.
    - **Ambito del gruppo di** dispositivi- È possibile specificare tutti i gruppi di dispositivi o selezionarli dall'elenco dei gruppi di dispositivi nel tenant.
    - **Notifica solo alla prima occorrenza per evento** imprevisto: selezionare se si desidera una notifica solo sul primo avviso corrispondente alle altre selezioni. Gli aggiornamenti o gli avvisi successivi correlati all'evento imprevisto non invierà notifiche aggiuntive.
    - **Includi il nome dell'organizzazione nel messaggio** di posta elettronica- Selezionare se si desidera che il nome dell'organizzazione venga visualizzato nella notifica di posta elettronica.
    - **Includi collegamento al portale specifico del** tenant: selezionare se si desidera aggiungere un collegamento con l'ID tenant nella notifica di posta elettronica per l'accesso a un tenant di Microsoft 365 specifico.

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="Impostazioni di notifica per le notifiche di posta elettronica degli eventi imprevisti":::

5. Selezionare **Avanti**. Nella pagina **Destinatari** aggiungere gli indirizzi di posta elettronica che riceveranno le notifiche degli eventi imprevisti. Selezionare **Aggiungi dopo** aver digitato ogni nuovo indirizzo di posta elettronica. Per testare le notifiche e assicurarsi che i destinatari le ricevano nelle cartelle Posta in arrivo, selezionare **Invia messaggio di posta elettronica di prova.** 
6. Selezionare **Avanti**. Nella pagina **Verifica regola** esaminare le impostazioni della regola e quindi selezionare **Crea regola.** I destinatari inizieranno a ricevere notifiche di eventi imprevisti tramite posta elettronica in base alle impostazioni.

Per modificare una regola esistente, selezionarla nell'elenco delle regole. Nel riquadro con il nome  della regola selezionare Modifica regola e apportare le modifiche nelle pagine Nozioni di **base,** Impostazioni di **notifica** **e** Destinatari.

Per modificare una regola esistente, selezionarla nell'elenco delle regole. Nel riquadro con il nome della regola selezionare **Elimina.**

## <a name="see-also"></a>Vedere anche
- [Panoramica sugli incidenti](incidents-overview.md)
- [Assegnare priorità agli incidenti](incident-queue.md)
- [Analizzare gli eventi imprevisti](investigate-incidents.md)
