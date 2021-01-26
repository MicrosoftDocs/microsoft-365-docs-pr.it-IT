---
title: Ruoli esperienza di argomento (anteprima)
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni sui ruoli degli utenti nelle esperienze degli argomenti.
ms.openlocfilehash: b649ea81d8e5b036e9332e9c87b67a951b5905a7
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975694"
---
# <a name="topic-experiences-roles-preview"></a>Ruoli esperienza di argomento (anteprima)

> [!Note] 
> Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex. [Altre informazioni su Project Cortex](https://aka.ms/projectcortex).


Quando si utilizza l'argomento experiences nell'ambiente Microsoft 365, è possibile che gli utenti dispongano dei ruoli seguenti:
-   Visualizzatore argomenti
-   Collaboratore dell'argomento
-   Knowledge Manager
-   Amministratore delle informazioni

## <a name="topic-viewer"></a>Visualizzatore argomenti

Gli utenti dell'argomento visualizzatori dell'organizzazione possono visualizzare gli argomenti evidenziati nel sito moderno di SharePoint e nella ricerca di SharePoint. È possibile selezionare gli argomenti evidenziati per visualizzare ulteriori dettagli su di essi in una pagina di argomento. 

Per evidenziare gli argomenti e le relative pagine di argomento per essere visibili a un visualizzatore di argomenti, l'utente deve:
-   [Essere assegnato a un argomento License experiences](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) by its Microsoft 365 admin.
-   Essere autorizzati ad avere visibilità sugli argomenti. Questa operazione viene fatta dall'amministratore della Knowledge base nella pagina relativa alle impostazioni dell'argomento experiences nell'interfaccia di amministrazione di Microsoft 365.


## <a name="topic-contributors"></a>Contributori dell'argomento

I collaboratori dell'argomento sono utenti dell'organizzazione che non solo dispongono delle autorizzazioni per il visualizzatore degli argomenti, ma possono anche modificare un argomento esistente o creare un nuovo argomento. Essi hanno un ruolo importante nella "cura" manuale delle informazioni contenute in una pagina di argomento (sia AI che fornite manualmente) per garantirne la qualità.

Gli utenti che dispongono di autorizzazioni per i collaboratori degli argomenti vedranno un pulsante **modifica** visualizzato nelle pagine degli argomenti, che consente loro di effettuare gli aggiornamenti e pubblicare un argomento.

Un collaboratore di argomento può anche creare e pubblicare un nuovo argomento tramite il relativo sito Centro tematico.

Per poter creare e modificare un argomento, l'utente deve:

-   [Essere assegnato a un argomento License experiences](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) by its Microsoft 365 admin.
-   [Essere assegnate le autorizzazioni per la creazione e la modifica degli argomenti](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions#change-who-has-permissions-to-do-tasks-on-the-topic-center). Questa operazione viene fatta dall'amministratore della Knowledge base nella pagina relativa alle impostazioni dell'argomento experiences nell'interfaccia di amministrazione di Microsoft 365.

## <a name="knowledge-managers"></a>Knowledge Manager

I Knowledge Manager sono utenti che gestiscono gli argomenti nell'organizzazione.  La gestione degli argomenti viene fatta tramite la pagina Gestisci temi nel centro argomenti ed è visibile solo ai responsabili della conoscenza.

Nella pagina Gestisci argomenti è possibile eseguire le attività seguenti per i responsabili della conoscenza:
-   Visualizza tutti gli argomenti consigliati AI.
-   Esaminare gli argomenti per verificare che siano validi.
-   Rimuovere gli argomenti che non si desidera rendere visibili agli utenti.


Inoltre, un responsabile della Knowledge base può modificare gli argomenti esistenti o crearne di nuovi.

Per poter gestire gli argomenti, l'utente deve:
-   [Essere assegnato a un argomento License experiences](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) by its Microsoft 365 admin.
-   [Essere assegnate le autorizzazioni per la gestione degli argomenti](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions#change-who-has-permissions-to-do-tasks-on-the-topic-center). Questa operazione viene fatta dall'amministratore della Knowledge base nella pagina relativa alle impostazioni dell'argomento experiences nell'interfaccia di amministrazione di Microsoft 365.

Gli utenti che dispongono di una buona conoscenza generale della propria azienda possono essere buoni candidati per il ruolo Knowledge Manager. Tali utenti potrebbero non solo sapere se gli argomenti sono validi o meno, ma potrebbero anche conoscere persone all'interno dell'azienda che sono correlate a tali argomenti.


## <a name="knowledge-admins"></a>Amministratori delle informazioni

Gli amministratori della Knowledge base sono amministratori che hanno configurato e configurato l'argomento esperienze nell'ambiente Microsoft 365. Gestiscono anche le impostazioni dell'argomento esperienze dopo il completamento della configurazione. Il ruolo Knowledge admin richiede di essere un amministratore Microsoft 365 Global o SharePoint, poiché l'installazione e la gestione vengono eseguite nell'interfaccia di amministrazione di Microsoft 365.
Durante l'installazione, gli amministratori della Knowledge base possono configurare le esperienze degli argomenti per eseguire le operazioni seguenti:

-   Selezionare i siti di SharePoint sottoposti a ricerca per indicizzazione per gli argomenti.
-   Selezionare gli utenti con licenza che saranno in grado di visualizzare gli argomenti (visualizzatori argomento).
-   Selezionare gli argomenti che verranno esclusi dall'identificazione.
-   Selezionare gli utenti con licenza che saranno in grado di creare e modificare gli argomenti (contributori dell'argomento).
-   Selezionare gli utenti con licenza che saranno in grado di gestire gli argomenti (Knowledge Manager).
-   Denominare il centro argomenti.

I Knowledge Manager devono essere in grado di coordinarsi con tutti gli argomenti coinvolti nell'organizzazione per sapere come configurarlo. Ad esempio, se un nuovo progetto contiene informazioni riservate, è necessario che il responsabile della Knowledge base venga informato per garantire che il sito di SharePoint non sia sottoposto a ricerca per indicizzazione per gli argomenti o che siano esclusi nomi di argomento specifici.


## <a name="see-also"></a>Vedere anche

