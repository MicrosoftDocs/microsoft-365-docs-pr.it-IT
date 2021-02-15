---
title: Limitare l'accesso agli argomenti negli argomenti di Microsoft Viva
description: Come escludere gli argomenti per impedirne l'individuare.
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
localization_priority: None
ms.openlocfilehash: 6b3d2a4b6cbfc67623cea58b73681b7af7cc4889
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107159"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a>Limitare l'accesso agli argomenti negli argomenti di Microsoft Viva

In Microsoft Viva, gli stakeholder dell'organizzazione potrebbero voler assicurarsi che argomenti specifici non siano individuati ed esposti agli utenti con licenza. Ad esempio, potresti lavorare a un progetto di cui non vuoi ancora esporre informazioni. Anche se le autorizzazioni di Office 365 per siti, file e altre risorse impediranno agli utenti di Esperienze argomento di visualizzare informazioni riservate negli argomenti, esistono ulteriori misure di sicurezza per impedire che argomenti specifici vengano mai individuati.

Mentre gli amministratori delle informazioni controllano le impostazioni della rete di conoscenze per impedire l'apprendimento degli argomenti, i responsabili della conoscenza e altri stakeholder devono sapere come vengono eseguite in modo che possano collaborare.

> [!Important] 
> In questo articolo vengono descritti i modi per impedire che gli argomenti vengano identificati tramite l'intelligenza artificiale o visualizzati nel proprio ambiente come un'ulteriore protezione della sicurezza. È importante notare che in Viva Topics gli utenti non possono visualizzare nulla in un argomento a cui non è consentito l'accesso tramite le autorizzazioni di Office 365. Anche se un utente è in grado di visualizzare un argomento, i relativi file, siti e pagine non dispongono delle autorizzazioni per la visualizzazione di Office 365 non saranno visibili. Assicurarsi che le autorizzazioni per i file sensibili siano impostate correttamente deve essere la protezione principale.

## <a name="prevent-topics-from-being-identified"></a>Impedire l'identificazione degli argomenti

L'amministratore della knowledge base può limitare l'accesso ad argomenti specifici impedendoli di essere trovati nell'indicizzazione iniziale. Esistono due modi per eseguire questa attività nelle impostazioni di amministrazione di Knowledge Network nell'interfaccia di amministrazione di Microsoft 365.
 
- [Selezionare i siti di SharePoint da escludere dall'individuazione](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)degli argomenti: è possibile utilizzare questa impostazione per impedire la ricerca per indicizzazione di siti di SharePoint specifici per gli argomenti.
- [Escludere gli argomenti in base al nome:](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name)gli amministratori possono utilizzare questa impostazione per impedire che argomenti specifici vengano individuati per nome. Nelle impostazioni di amministrazione di Knowledge Network, un amministratore può caricare un elenco di argomenti da escludere in un file CSV. È possibile escludere gli argomenti con corrispondenze esatte o parziali di un nome di argomento.

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>Impedire la visualizzazione degli argomenti da parte di utenti specifici

Gli amministratori della knowledge base possono anche [selezionare gli utenti che possono visualizzare gli argomenti nell'organizzazione.](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules) Questa impostazione consente di selezionare gli utenti con licenza che possono visualizzare tutti gli argomenti. In un ambiente pilota, ad esempio, è possibile consentire solo a un piccolo gruppo di utenti di visualizzare gli argomenti.

## <a name="remove-topics-from-being-viewed"></a>Rimuovere gli argomenti dalla visualizzazione

I responsabili della conoscenza possono [scegliere di rimuovere gli argomenti](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) in modo che gli utenti non possano più vederli. Nella pagina **Gestisci argomenti** del **Centro** argomenti i knowledge manager possono scegliere di rifiutare argomenti specifici per impedirne la visualizzazione. Gli argomenti possono essere rimossi indipendentemente dal fatto che si presentino in uno stato consigliato o confermato.

Gli argomenti rimossi possono essere successivamente aggiunti nuovamente come argomenti visualizzabili, se necessario. 


## <a name="see-also"></a>Vedere anche



  






