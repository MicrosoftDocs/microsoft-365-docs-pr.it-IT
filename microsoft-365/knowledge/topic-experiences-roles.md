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
ms.openlocfilehash: 9f1d3667ee9eeb05201613c15dc360b2b006cecb
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288072"
---
# <a name="microsoft-viva-topics-roles"></a>Ruoli di Microsoft Viva Topics 

Quando usi Viva Topics nell'ambiente Microsoft 365, gli utenti possono avere i ruoli seguenti:

- Visualizzatore dell'argomento
- Collaboratore dell'argomento
- Responsabile delle informazioni
- Amministratore delle informazioni

## <a name="topic-viewer"></a>Visualizzatore dell'argomento

I visualizzatori di argomenti sono utenti dell'organizzazione che possono visualizzare gli argomenti evidenziati nel sito moderno di SharePoint, Microsoft Search tramite SharePoint e Office.com e il Centro argomenti. Possono visualizzare ulteriori dettagli su un argomento nella pagina dell'argomento. 

Affinché gli argomenti e le loro pagine e caratteristiche siano visibili a un visualizzatore di argomenti, l'utente deve:

- [Essere assegnato a una licenza Viva Topics](./set-up-topic-experiences.md#assign-licenses) dal Microsoft 365 amministratore.
- Essere autorizzati a vedere gli argomenti. Questa attività viene eseguita dall'amministratore della knowledge base nella pagina Delle impostazioni di Viva Topics nella interfaccia di amministrazione di Microsoft 365.

## <a name="topic-contributors"></a>Collaboratori dell'argomento

Gli autori di argomenti sono utenti dell'organizzazione che non solo possono vedere gli argomenti, ma possono anche modificare un argomento esistente o crearne uno nuovo. Hanno un ruolo importante nella "cura" manuale delle informazioni in una pagina dell'argomento (sia ai che forniti manualmente) per garantirne la qualità.

Gli utenti che dispongono delle  autorizzazioni di collaboratore di argomenti visualizzano un pulsante Modifica nelle pagine Argomento, che consente loro di apportare aggiornamenti e pubblicare un argomento.

Un autore di argomenti può anche creare e pubblicare un nuovo argomento tramite il proprio centro argomenti.

Per creare e modificare un argomento, l'utente deve:

- [Essere assegnato a una licenza Viva Topics](./set-up-topic-experiences.md#assign-licenses) dal Microsoft 365 amministratore.
- [Assegnare le autorizzazioni per creare e modificare gli argomenti.](./topic-experiences-user-permissions.md) Questa attività viene eseguita dall'amministratore della knowledge base nella pagina Delle impostazioni di Viva Topics nella interfaccia di amministrazione di Microsoft 365.

## <a name="knowledge-managers"></a>Responsabili delle informazioni

I responsabili delle informazioni sono utenti che gestiscono gli argomenti nell'organizzazione.  La gestione degli argomenti viene effettuata tramite la pagina Gestisci argomenti nel centro argomenti ed è visibile solo ai responsabili delle informazioni.

Nella pagina Gestisci argomenti i responsabili delle informazioni possono svolgere le attività seguenti:

- Visualizzare gli argomenti suggeriti dall'intelligenza artificiale.
- Esaminare gli argomenti per verificare che siano validi.
- Rimuovere gli argomenti che non si desidera siano visibili agli utenti.

Inoltre, un responsabile delle informazioni può modificare gli argomenti esistenti o crearne di nuovi.

Per gestire gli argomenti, l'utente deve:

- [Essere assegnato a una licenza Viva Topics](./set-up-topic-experiences.md#assign-licenses) dal Microsoft 365 amministratore.
- [Assegnare le autorizzazioni per gestire gli argomenti](./topic-experiences-user-permissions.md). Questa attività viene eseguita dall'amministratore della knowledge base nella pagina Delle impostazioni di Viva Topics nella interfaccia di amministrazione di Microsoft 365.

Gli utenti che hanno una buona conoscenza generale dell'azienda possono essere buoni candidati per il ruolo di knowledge manager. Tali persone potrebbero non solo avere la conoscenza di sapere se gli argomenti sono validi o meno, ma potrebbero anche conoscere le persone all'interno dell'azienda che sono correlate a tali argomenti.

## <a name="knowledge-admins"></a>Amministratori delle informazioni

Gli amministratori della knowledge base sono amministratori che configurano e configurano Viva Topics nel Microsoft 365 locale. Al termine della configurazione, gestiscono anche le impostazioni di Viva Topics. Il ruolo di amministratore della knowledge base richiede di essere un amministratore Microsoft 365 globale o SharePoint dal momento che l'installazione e la gestione vengono eseguite nella interfaccia di amministrazione di Microsoft 365.
Durante l'installazione, gli amministratori della knowledge base possono configurare Viva Topics per:

- Selezionare quali siti di SharePoint verranno sottoposti a ricerca per indicizzazione per identificare gli argomenti.
- Selezionare quali utenti con licenza possono visualizzare gli argomenti (visualizzatori degli argomenti).
- Selezionare quali argomenti verranno esclusi dall'identificazione.
- Selezionare quali utenti con licenza possono creare e modificare gli argomenti (autori degli argomenti).
- Selezionare quali utenti con licenza possono gestire gli argomenti (responsabili delle informazioni).
- Assegnare un nome al centro argomenti.

I responsabili delle informazioni devono essere in grado di coordinarsi con tutti gli stakeholder di Viva Topics nell'organizzazione per sapere come configurarlo. Ad esempio, se un nuovo progetto contiene informazioni riservate, il responsabile della conoscenza deve essere informato in modo che possa assicurarsi che il sito di SharePoint non sia sottoposto a ricerca per indicizzazione per gli argomenti o che sia necessario escludere nomi di argomenti specifici.
