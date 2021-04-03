---
title: Ricevere notifiche di eventi imprevisti in Microsoft 365 Defender
description: Informazioni su come creare regole per ricevere notifiche tramite posta elettronica per eventi imprevisti in Microsoft 365 Defender
keywords: incident, email, email notfications, configure, users, mailbox, email, incidents
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
ms.openlocfilehash: fec2263599f3ed727d3d9d70023927084eb1c094
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501066"
---
# <a name="get-incident-notifications-by-email"></a>Ricevere notifiche di eventi imprevisti tramite posta elettronica

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

È possibile configurare Microsoft 365 Defender per inviare una notifica tramite posta elettronica ogni volta che sono presenti nuovi eventi imprevisti o nuovi aggiornamenti a eventi imprevisti esistenti. 

Puoi scegliere di ricevere notifiche in base alla gravità dell'incidente o in base al gruppo di dispositivi. Puoi anche scegliere di ricevere una notifica solo al primo aggiornamento per evento imprevisto.

È possibile aggiungere o rimuovere destinatari nelle notifiche di posta elettronica. I nuovi destinatari aggiunti riceveranno una notifica sugli eventi imprevisti dopo l'aggiunta. 

La notifica di posta elettronica contiene dettagli importanti sull'evento imprevisto, ad esempio il nome, la gravità e le categorie dell'evento imprevisto, tra gli altri. È inoltre possibile passare direttamente agli eventi imprevisti in modo da poter avviare immediatamente l'indagine. Per ulteriori informazioni sull'analisi degli incidenti, vedere [Investigate incidents in Microsoft 365 Defender.](./investigate-incidents.md)

>[!NOTE]
>Per configurare le impostazioni di notifica tramite posta elettronica, è necessario disporre delle autorizzazioni "Gestisci impostazioni di sicurezza". Se si è scelto di utilizzare la gestione delle autorizzazioni di base, gli utenti con ruoli amministratore della sicurezza o amministratore globale possono configurare automaticamente le notifiche di posta elettronica. <br> <br>
Allo stesso modo, se l'organizzazione utilizza il controllo di accesso basato sui ruoli(RBAC), è possibile creare, modificare, eliminare e ricevere notifiche in base ai gruppi di dispositivi che sono autorizzati a gestire.

## <a name="create-rules-for-incident-notifications"></a>Creare regole per le notifiche di eventi imprevisti

Per configurare la prima notifica tramite posta elettronica per gli eventi imprevisti, creare una nuova regola e personalizzare le impostazioni di notifica tramite posta elettronica.

1. Nel riquadro di spostamento, selezionare **Impostazioni**  >  **Notifiche e-mail evento imprevisto.**
2. Selezionare **Aggiungi elemento**.
3. Assegnare un nome alla regola in **Nome** e specificare una **Descrizione.**

    ![Finestra crea regola per notif di posta elettronica operazioni non consentite](../../media/incidentemailnotif1.png) 
4. Selezionare **Avanti** per passare a **Impostazioni notifica.** Qui puoi specificare:
    - **Gravità avviso:** scegliere la gravità dell'avviso che attiverà una notifica di evento imprevisto. Ad esempio, se si desidera essere informati solo sugli eventi imprevisti di gravità elevata, selezionare Alta.
    - **Ambito del gruppo di dispositivi-** Questo elenco a discesa visualizza tutti i gruppi di dispositivi a cui l'utente può accedere. Seleziona i gruppi di dispositivi per cui stai creando le regole di notifica degli eventi imprevisti.
    - **Notifica solo alla prima occorrenza per evento** imprevisto: selezionando questa opzione verrà inviata una notifica tramite posta elettronica solo al primo avviso corrispondente alle altre selezioni. Gli aggiornamenti o gli avvisi successivi correlati all'evento imprevisto non attivano una notifica.
    - **Includi nome organizzazione** - Indica se il nome del cliente viene visualizzato o meno nella notifica tramite posta elettronica.
    - **Includi collegamento al portale specifico del** tenant - Aggiunge un collegamento con l'ID tenant per consentire l'accesso a un tenant specifico.
    
    ![Finestra delle impostazioni notif per i notif di posta elettronica degli eventi imprevisti](../../media/incidentemailnotif2.png)
5. Selezionare **Avanti** per passare alla **sezione** Destinatari. Qui è possibile specificare gli indirizzi di posta elettronica che riceveranno le notifiche di posta elettronica degli eventi imprevisti. Selezionare **Aggiungi un destinatario dopo** aver digitato ogni indirizzo di posta elettronica.

    ![Finestra Aggiungi destinatari per notif di posta elettronica operazioni non consentite](../../media/incidentemailnotif3.png) 

6. Infine, selezionare **Avanti** per passare a **Rivedi regola** in modo da poter visualizzare tutte le impostazioni associate alla nuova regola. I destinatari inizieranno a ricevere notifiche di eventi imprevisti tramite posta elettronica in base alle impostazioni.

## <a name="see-also"></a>Vedere anche
- [Panoramica degli incidenti in Microsoft 365 Defender](./incidents-overview.md)
- [Assegnare priorità agli incidenti in Microsoft 365 Defender](./incident-queue.md)
- [Analizzare gli incidenti in Microsoft 365 Defender](./investigate-incidents.md)
