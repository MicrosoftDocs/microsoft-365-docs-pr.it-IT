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
ms.openlocfilehash: d5b57e768a1de8bc0447492067371630b2d045f6
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453943"
---
# <a name="microsoft-viva-topics-roles"></a>Ruoli di Microsoft Viva Topics 

Quando si usano Viva Topics nell'ambiente Microsoft 365, gli utenti possono avere i ruoli seguenti:
-   Visualizzatore argomenti
-   Collaboratore argomento
-   Knowledge Manager
-   Amministratore della knowledge base

## <a name="topic-viewer"></a>Visualizzatore argomenti

I visualizzatori di argomenti sono utenti dell'organizzazione in grado di visualizzare gli argomenti evidenziati nel sito moderno di SharePoint, in Microsoft Search tramite SharePoint e Office.com e nel Centro argomenti. Possono visualizzare altri dettagli su un argomento nella pagina dell'argomento. 

Per fare in modo che le evidenziazioni degli argomenti e le relative pagine degli argomenti siano visibili a un visualizzatore di argomenti, l'utente deve:
-   [L'amministratore di Microsoft](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) 365 deve assegnare una licenza Viva Topics.
-   Essere autorizzati ad avere visibilità per gli argomenti. Questa attività viene eseguita dall'amministratore della knowledge base nella pagina delle impostazioni Viva Topics nell'interfaccia di amministrazione di Microsoft 365.


## <a name="topic-contributors"></a>Collaboratori di argomenti

I collaboratori agli argomenti sono utenti dell'organizzazione che non solo dispongono di autorizzazioni per il visualizzatore di argomenti, ma anche che possono modificare un argomento esistente o crearne uno nuovo. Hanno un ruolo importante nel "curare" manualmente le informazioni in una pagina dell'argomento (ai o forniti manualmente) per garantirne la qualità.

Gli utenti che dispongono delle  autorizzazioni di collaboratore per l'argomento visualizzano un pulsante Modifica nelle pagine degli argomenti, che consente loro di apportare aggiornamenti e pubblicare un argomento.

Un collaboratore di argomenti può anche creare e pubblicare un nuovo argomento tramite il relativo Centro argomenti.

Per creare e modificare un argomento, l'utente deve:

-   [L'amministratore di Microsoft](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) 365 deve assegnare una licenza Viva Topics.
-   [Assegnare le autorizzazioni per creare e modificare gli argomenti.](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions#change-who-has-permissions-to-do-tasks-on-the-topic-center) Questa attività viene eseguita dall'amministratore della knowledge base nella pagina delle impostazioni Viva Topics nell'interfaccia di amministrazione di Microsoft 365.

## <a name="knowledge-managers"></a>Responsabili della conoscenza

I knowledge manager sono utenti che gestiscono gli argomenti nell'organizzazione.  La gestione degli argomenti viene eseguita tramite la pagina Gestisci argomenti nel Centro argomenti ed è visibile solo ai knowledge manager.

Nella pagina Gestisci argomenti i knowledge manager possono eseguire le attività seguenti:
-   Visualizza gli argomenti suggeriti dall'intelligenza artificiale.
-   Esaminare gli argomenti per verificare che siano validi.
-   Rimuovere gli argomenti che non si desidera visualizzare agli utenti.

Inoltre, un responsabile della knowledge base può modificare gli argomenti esistenti o crearne di nuovi.

Per gestire gli argomenti, l'utente deve:
-   [L'amministratore di Microsoft](https://docs.microsoft.com/microsoft-365/knowledge/set-up-topic-experiences#assign-licenses) 365 deve assegnare una licenza Viva Topics.
-   [Assegnare le autorizzazioni per gestire gli argomenti](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions#change-who-has-permissions-to-do-tasks-on-the-topic-center). Questa attività viene eseguita dall'amministratore della knowledge base nella pagina delle impostazioni Viva Topics nell'interfaccia di amministrazione di Microsoft 365.

Gli utenti che hanno una buona conoscenza generale dell'azienda possono essere ottimi candidati per il ruolo di knowledge manager. Queste persone potrebbero non solo sapere se gli argomenti sono validi o meno, ma anche conoscere le persone all'interno dell'azienda correlate a tali argomenti.


## <a name="knowledge-admins"></a>Amministratori della knowledge base

Gli amministratori della knowledge base sono amministratori che configurano Viva Topics nell'ambiente Microsoft 365. Al termine della configurazione, gestiscono anche le impostazioni di Viva Topics. Il ruolo di amministratore delle informazioni richiede di essere un amministratore globale o di SharePoint di Microsoft 365 poiché la configurazione e la gestione vengono eseguite nell'interfaccia di amministrazione di Microsoft 365.
Durante l'installazione, gli amministratori della knowledge base possono configurare Viva Topics per:

-   Selezionare quali siti di SharePoint verranno sottoposti a ricerca per indicizzazione per gli argomenti.
-   Selezionare gli utenti con licenza che possono visualizzare gli argomenti (visualizzatori di argomenti).
-   Selezionare gli argomenti da escludere dall'identificazione.
-   Selezionare gli utenti con licenza che possono creare e modificare argomenti (collaboratori di argomenti).
-   Selezionare gli utenti con licenza che possono gestire gli argomenti (responsabili della knowledge base).
-   Assegnare un nome al centro argomenti.

I knowledge manager devono essere in grado di coordinarsi con tutti gli stakeholder viva topics dell'organizzazione per sapere come configurarlo. Ad esempio, se un nuovo progetto contiene informazioni riservate, il responsabile della conoscenza deve essere informato in modo che possa assicurarsi che il sito di SharePoint non sia sottoposto a ricerca per indicizzazione per argomenti o che sia necessario escludere nomi di argomenti specifici.


## <a name="see-also"></a>Vedere anche

