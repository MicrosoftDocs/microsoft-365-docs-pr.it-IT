---
title: Ricevere notifiche di eventi imprevisti in Microsoft 365 Defender
description: Informazioni su come creare regole per ricevere notifiche tramite posta elettronica per gli eventi imprevisti in Microsoft 365 Defender
keywords: evento imprevisto, posta elettronica, notifica di posta elettronica, configurare, utenti, cassetta postale, posta elettronica, eventi imprevisti
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 9db025818fdd5eb2635a9a676e4a10e20f3036b6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930979"
---
# <a name="get-incident-notifications-by-email"></a>Ricevere notifiche di eventi imprevisti tramite posta elettronica

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

È possibile configurare Microsoft 365 Defender per inviare una notifica tramite posta elettronica ogni volta che sono presenti nuovi eventi imprevisti o nuovi aggiornamenti per gli eventi imprevisti esistenti. 

Puoi scegliere di ricevere notifiche in base alla gravità dell'incidente o in base al gruppo di dispositivi. Puoi anche scegliere di ricevere una notifica solo sul primo aggiornamento per ogni evento imprevisto.

È possibile aggiungere o rimuovere destinatari nelle notifiche di posta elettronica. I nuovi destinatari aggiunti vengono avvisati degli eventi imprevisti dopo l'aggiunta. 

The email notification contains important details about the incident like the incident name, severity, and categories, among others. È inoltre possibile passare direttamente agli eventi imprevisti in modo da poter avviare immediatamente l'indagine. Per altre informazioni sull'analisi degli eventi imprevisti, vedere [Analizzare gli eventi imprevisti in Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

>[!NOTE]
>Per configurare le impostazioni di notifica tramite posta elettronica, sono necessarie le autorizzazioni "Gestisci impostazioni di sicurezza". Se si è scelto di utilizzare la gestione delle autorizzazioni di base, gli utenti con ruoli amministratore della sicurezza o amministratore globale possono configurare automaticamente le notifiche tramite posta elettronica. <br> <br>
Analogamente, se l'organizzazione usa il controllo di accesso basato sui ruoli (RBAC), è possibile creare, modificare, eliminare e ricevere notifiche solo in base ai gruppi di dispositivi che è possibile gestire.

## <a name="create-rules-for-incident-notifications"></a>Creare regole per le notifiche di eventi imprevisti

Per configurare la prima notifica tramite posta elettronica per gli eventi imprevisti, creare una nuova regola e personalizzare le impostazioni di notifica tramite posta elettronica.

1. Nel riquadro di spostamento, selezionare **Impostazioni** notifiche e-mail evento  >  **imprevisto.**
2. Selezionare **Aggiungi elemento.**
3. Assegnare alla regola un nome in **Nome** e specificare una **descrizione.**

    ![Finestra delle regole di creazione per i notif di posta elettronica degli eventi imprevisti](../../media/incidentemailnotif1.png) 
4. Selezionare **Avanti** per passare alle **impostazioni di notifica.** Qui è possibile specificare:
    - **Gravità avviso: scegliere** la gravità dell'avviso che attiverà una notifica di evento imprevisto. Ad esempio, se si desidera essere informati solo su eventi imprevisti di gravità elevata, selezionare Alta.
    - **Ambito del gruppo di dispositivi:** questo elenco a discesa visualizza tutti i gruppi di dispositivi a cui l'utente può accedere. Selezionare i gruppi di dispositivi per cui si stanno creando le regole di notifica degli eventi imprevisti.
    - **Notifica solo alla prima occorrenza per** evento imprevisto: se si seleziona questa opzione, verrà inviata una notifica tramite posta elettronica solo al primo avviso corrispondente alle altre selezioni. Gli aggiornamenti o gli avvisi successivi correlati all'evento non attiverà una notifica.
    - **Includi nome organizzazione-** Indica se il nome del cliente viene visualizzato o meno nella notifica tramite posta elettronica.
    - **Includi collegamento al portale specifico del tenant:** aggiunge un collegamento con l'ID tenant per consentire l'accesso a un tenant specifico.
    
    ![Finestra delle impostazioni notif per le notifiche di posta elettronica per eventi imprevisti](../../media/incidentemailnotif2.png)
5. Selezionare **Avanti** per passare alla **sezione Destinatari.** Qui è possibile specificare gli indirizzi di posta elettronica che riceveranno le notifiche di posta elettronica degli eventi imprevisti. Selezionare **Aggiungi un destinatario dopo aver** digitato ogni indirizzo di posta elettronica.

    ![Finestra Aggiungi destinatari per notifiche di posta elettronica operazioni non consentite](../../media/incidentemailnotif3.png) 

6. Infine, selezionare **Avanti** per passare a **Revisione regola in** modo da visualizzare tutte le impostazioni associate alla nuova regola. I destinatari inizieranno a ricevere notifiche di eventi imprevisti tramite posta elettronica in base alle impostazioni.

## <a name="see-also"></a>Vedere anche
- [Panoramica degli eventi imprevisti in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [Assegnare priorità agli eventi imprevisti in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [Analizzare gli eventi imprevisti in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

