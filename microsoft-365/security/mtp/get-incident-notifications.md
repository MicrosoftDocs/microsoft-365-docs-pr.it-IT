---
title: Ottenere notifiche degli incidenti in Microsoft 365 Defender
description: Informazioni su come creare regole per ricevere notifiche tramite posta elettronica per gli eventi non consentiti in Microsoft 365 Defender
keywords: incidente, posta elettronica, posta elettronica notfications, configurare, utenti, cassetta postale, posta elettronica, incidenti
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f25be4de3f25db869957474c3cb32b20e9f7aa53
ms.sourcegitcommit: 88d358d778804b26d5e41c53b4f725d01a78112b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49848892"
---
# <a name="get-incident-notifications-by-email"></a>Ottenere notifiche sugli incidenti tramite posta elettronica

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

È possibile configurare Microsoft 365 Defender per inviare una notifica tramite posta elettronica ogni volta che sono presenti nuovi incidenti o nuovi aggiornamenti per gli incidenti esistenti. 

È possibile scegliere di ottenere notifiche in base alla gravità degli incidenti o al gruppo di dispositivi. È anche possibile scegliere di ricevere una notifica solo sul primo aggiornamento per evento Incident.

È possibile aggiungere o rimuovere i destinatari nelle notifiche di posta elettronica. I destinatari appena aggiunti ricevono una notifica sugli incidenti dopo che sono stati aggiunti. 

La notifica di posta elettronica contiene informazioni importanti sull'incidente, ad esempio il nome, la gravità e le categorie degli incidenti. È inoltre possibile accedere direttamente agli eventi non consentiti in modo da poter avviare immediatamente l'indagine. Per ulteriori informazioni sulle indagini sugli incidenti, vedere [indagini sugli incidenti in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).

>[!NOTE]
>Per configurare le impostazioni di notifica di posta elettronica, è necessario disporre delle autorizzazioni di gestione delle impostazioni di sicurezza. Se si è scelto di utilizzare la gestione delle autorizzazioni di base, gli utenti con ruoli di amministratore di sicurezza o di amministratore globale possono configurare le notifiche di posta elettronica per l'utente. <br> <br>
Analogamente, se l'organizzazione utilizza il controllo di accesso basato sui ruoli (RBAC), è possibile creare, modificare, eliminare e ricevere notifiche solo in base ai gruppi di dispositivi che sono autorizzati a gestire.

## <a name="create-rules-for-incident-notifications"></a>Creare regole per le notifiche degli eventi non consentiti

Per impostare la prima notifica di posta elettronica per gli eventi non consentiti, creare una nuova regola e personalizzare le impostazioni di notifica di posta elettronica.

1. Nel riquadro di spostamento, selezionare **Impostazioni**  >  **notifiche di posta elettronica eventi** non consentiti.
2. Selezionare **Aggiungi elemento**.
3. Assegnare alla regola un nome in **nome** e specificare una **Descrizione**.

    ![Creare la finestra della regola per la posta elettronica notifs](../../media/incidentemailnotif1.png) 
4. Fare clic su **Avanti** per accedere alle **impostazioni di notifica**. Qui è possibile specificare:
    - **Severità degli avvisi** -scegliere la gravità degli avvisi che attiverà una notifica di emergenza. Ad esempio, se si desidera solo essere informati sugli incidenti di gravità elevata, selezionare elevato.
    - **Ambito gruppo di dispositivi** -in questo elenco a discesa vengono visualizzati tutti i gruppi di dispositivi che l'utente può accedere. Selezionare i gruppi di dispositivi in cui si stanno creando le regole per la notifica degli incidenti.
    - **Solo notifica sulla prima occorrenza per** evento: selezionando questa opzione, verrà inviata una notifica tramite posta elettronica solo sul primo avviso corrispondente alle altre selezioni. Gli aggiornamenti o gli avvisi successivi relativi all'incidente non attiveranno una notifica.
    - **Includi nome organizzazione** -indica se il nome del cliente viene visualizzato nella notifica di posta elettronica o meno.
    - **Includi collegamento portale specifico del tenant** -aggiunge un collegamento all'ID tenant per consentire l'accesso a un tenant specifico.
    
    ![Finestra delle impostazioni di Notif per la posta elettronica Incident notifs](../../media/incidentemailnotif2.png)
5. Selezionare **Avanti** per andare alla sezione **destinatari** . Qui è possibile specificare gli indirizzi di posta elettronica che riceveranno le notifiche di posta indesiderata. Selezionare **Aggiungi un destinatario** dopo aver digitato tutti gli indirizzi di posta elettronica.

    ![Finestra Aggiungi destinatari per la posta elettronica notifs](../../media/incidentemailnotif3.png) 

6. Infine, fare clic su **Avanti** per passare a **Revisione regola** in modo da poter visualizzare tutte le impostazioni associate alla nuova regola. I destinatari inizieranno a ricevere notifiche sugli incidenti tramite posta elettronica in base alle impostazioni.

## <a name="see-also"></a>Vedere anche
- [Panoramica degli incidenti in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [Assegnare la priorità agli incidenti in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [Esaminare gli incidenti in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

