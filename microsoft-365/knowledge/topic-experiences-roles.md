---
title: Ruoli di Microsoft Viva Topics
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
description: Informazioni sui ruoli utente in Viva Topics.
ms.openlocfilehash: e91eda6807634ad27bf6c15c2dd0d1c9434ce299
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222768"
---
# <a name="microsoft-viva-topics-roles"></a>Ruoli di Microsoft Viva Topics 

Quando usi Viva Topics nell'ambiente Microsoft 365, gli utenti possono avere i ruoli seguenti:
-   Visualizzatore argomenti
-   Collaboratore argomento
-   Knowledge Manager
-   Amministratore della knowledge base

## <a name="topic-viewer"></a>Visualizzatore argomenti

I visualizzatori di argomenti sono utenti dell'organizzazione che possono visualizzare gli argomenti evidenziati nel sito moderno di SharePoint, Microsoft Search tramite SharePoint e Office.com e il Centro argomenti. Possono visualizzare ulteriori dettagli su un argomento nella pagina dell'argomento. 

Perché le evidenziazioni degli argomenti e le relative pagine siano visibili a un visualizzatore di argomenti, l'utente deve:
-   [L'amministratore di](./set-up-topic-experiences.md#assign-licenses) Microsoft 365 deve assegnare una licenza Viva Topics.
-   Essere autorizzati ad avere visibilità per gli argomenti. Questa attività viene eseguita dall'amministratore della knowledge base nella pagina Delle impostazioni di Viva Topics nell'interfaccia di amministrazione di Microsoft 365.


## <a name="topic-contributors"></a>Collaboratori di argomenti

I collaboratori degli argomenti sono utenti dell'organizzazione che non solo dispongono delle autorizzazioni per il visualizzatore di argomenti, ma che possono anche modificare un argomento esistente o creare un nuovo argomento. Hanno un ruolo importante nella "cura" manuale delle informazioni in una pagina dell'argomento (sia ai che forniti manualmente) per garantirne la qualità.

Gli utenti che dispongono delle  autorizzazioni di collaboratore di argomenti visualizzano un pulsante Modifica nelle pagine Argomento, che consente loro di apportare aggiornamenti e pubblicare un argomento.

Un collaboratore di argomenti può anche creare e pubblicare un nuovo argomento tramite il centro argomenti.

Per creare e modificare un argomento, l'utente deve:

-   [L'amministratore di](./set-up-topic-experiences.md#assign-licenses) Microsoft 365 deve assegnare una licenza Viva Topics.
-   [Assegnare le autorizzazioni per creare e modificare gli argomenti.](./topic-experiences-user-permissions.md) Questa attività viene eseguita dall'amministratore della knowledge base nella pagina Delle impostazioni di Viva Topics nell'interfaccia di amministrazione di Microsoft 365.

## <a name="knowledge-managers"></a>Knowledge Manager

I knowledge manager sono utenti che gestiscono gli argomenti nell'organizzazione.  La gestione degli argomenti viene eseguita tramite la pagina Gestisci argomenti nel Centro argomenti ed è visibile solo ai responsabili della knowledge base.

Nella pagina Gestisci argomenti i knowledge manager possono eseguire le attività seguenti:
-   Visualizzare gli argomenti suggeriti dall'IA.
-   Esaminare gli argomenti per verificare che siano validi.
-   Rimuovere gli argomenti che non si desidera siano visibili agli utenti.

Inoltre, un responsabile della knowledge base può modificare gli argomenti esistenti o crearne di nuovi.

Per gestire gli argomenti, l'utente deve:
-   [L'amministratore di](./set-up-topic-experiences.md#assign-licenses) Microsoft 365 deve assegnare una licenza Viva Topics.
-   [Assegnare le autorizzazioni per gestire gli argomenti](./topic-experiences-user-permissions.md). Questa attività viene eseguita dall'amministratore della knowledge base nella pagina Delle impostazioni di Viva Topics nell'interfaccia di amministrazione di Microsoft 365.

Gli utenti che hanno una buona conoscenza generale dell'azienda possono essere buoni candidati per il ruolo di knowledge manager. Tali persone potrebbero non solo avere la conoscenza di sapere se gli argomenti sono validi o meno, ma potrebbero anche conoscere le persone all'interno dell'azienda che sono correlate a tali argomenti.


## <a name="knowledge-admins"></a>Amministratori della knowledge base

Gli amministratori della knowledge base sono amministratori che configurano Viva Topics nell'ambiente Microsoft 365. Al termine della configurazione, gestiscono anche le impostazioni di Viva Topics. Il ruolo di amministratore della knowledge base richiede di essere un amministratore globale o di SharePoint di Microsoft 365 poiché l'installazione e la gestione vengono eseguite nell'interfaccia di amministrazione di Microsoft 365.
Durante l'installazione, gli amministratori della knowledge base possono configurare Viva Topics per:

-   Selezionare quali siti di SharePoint verranno sottoposti a ricerca per indicizzazione per gli argomenti.
-   Selezionare gli utenti con licenza che possono visualizzare gli argomenti (visualizzatori di argomenti).
-   Selezionare gli argomenti da escludere dall'identificazione.
-   Selezionare gli utenti con licenza che possono creare e modificare argomenti (collaboratori di argomenti).
-   Selezionare gli utenti con licenza che possono gestire gli argomenti (responsabili delle conoscenze).
-   Assegnare un nome al centro argomenti.

I knowledge manager devono essere in grado di coordinarsi con tutti gli stakeholder viva topics dell'organizzazione per sapere come configurarlo. Ad esempio, se un nuovo progetto contiene informazioni riservate, il responsabile della conoscenza deve essere informato in modo che possa assicurarsi che il sito di SharePoint non sia sottoposto a ricerca per indicizzazione per gli argomenti o che sia necessario escludere nomi di argomenti specifici.


## <a name="see-also"></a>Vedere anche