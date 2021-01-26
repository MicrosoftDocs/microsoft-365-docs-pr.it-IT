---
title: Limitare l'accesso agli argomenti
description: Come escludere gli argomenti per impedire che vengano scoperti.
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: f7e8406ee7090387d4500f69955330466f28c6c0
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976146"
---
# <a name="restrict-access-to-topics-in-topic-experiences"></a>Limitare l'accesso agli argomenti nelle esperienze di argomento

Nelle esperienze degli argomenti, le parti interessate nell'organizzazione possono decidere di non individuare e esporre gli utenti con licenza. Ad esempio, è possibile che si stia lavorando a un progetto di cui non si desidera esporre altre informazioni. Anche se le autorizzazioni di Office 365 per siti, file e altre risorse impediscono agli utenti di visualizzare le informazioni riservate negli argomenti, esistono ulteriori misure di salvaguardia per evitare che vengano scoperti argomenti specifici.

Mentre gli amministratori della Knowledge base controllano le impostazioni della rete di conoscenze per evitare che gli argomenti vengano scoperti, i Knowledge Manager e le altre parti interessate devono sapere come eseguire questa operazione affinché possano collaborare in questo modo.

> [!Important] 
> In questo articolo vengono illustrati i modi per evitare che gli argomenti vengano identificati tramite AI o visualizzati nell'ambiente come protezione di sicurezza aggiuntiva. È importante tenere presente che, nelle esperienze degli argomenti, gli utenti non sono autorizzati a visualizzare alcun elemento in un argomento a cui non è consentito l'accesso tramite le autorizzazioni di Office 365. Anche se un utente è in grado di visualizzare un argomento, i relativi file, siti e pagine che non dispongono delle autorizzazioni di Office 365 per la visualizzazione non saranno visibili. Assicurarsi che le autorizzazioni per i file riservati siano impostate correttamente devono essere il Safeguard di sicurezza principale.

## <a name="prevent-topics-from-being-identified"></a>Impedire l'identificazione degli argomenti

L'amministratore della Knowledge base può limitare l'accesso a argomenti specifici impedendo che vengano trovati nell'indicizzazione iniziale. Esistono due modi per eseguire questa operazione nelle impostazioni di amministrazione della rete di informazioni nell'interfaccia di amministrazione di Microsoft 365.
 
- [Selezionare i siti di SharePoint da escludere dall'individuazione](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)di un argomento: è possibile utilizzare questa impostazione per impedire la ricerca per indicizzazione di siti di SharePoint specifici per gli argomenti.
- [Escludi argomenti per nome](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): gli amministratori possono utilizzare questa impostazione per evitare che argomenti specifici vengano scoperti per nome. Nelle impostazioni di amministratore della rete della Knowledge base, un amministratore può caricare un elenco di argomenti da escludere in un file CSV. È possibile escludere gli argomenti che presentano corrispondenze esatte o parziali di un nome di argomento.

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>Impedire che gli argomenti vengano visualizzati da utenti specifici

Gli amministratori della Knowledge base possono anche [selezionare gli utenti autorizzati a visualizzare gli argomenti nell'organizzazione](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules). Questa impostazione consente di selezionare gli utenti con licenza in grado di visualizzare tutti gli argomenti. Ad esempio, in un ambiente pilota, è possibile consentire solo a un piccolo gruppo di utenti di essere in grado di visualizzare gli argomenti.

## <a name="remove-topics-from-being-viewed"></a>Rimuovere gli argomenti dalla visualizzazione

I Knowledge Manager possono scegliere di [rimuovere gli argomenti](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) in modo che gli utenti non possano più visualizzarli. Nella pagina **Gestisci argomenti** del **centro** argomenti, i responsabili della Knowledge base possono scegliere di rifiutare argomenti specifici per impedire che vengano visualizzati. Gli argomenti possono essere rimossi indipendentemente dal fatto che si trovino in uno stato suggerito o confermato.

Gli argomenti rimossi possono essere aggiunti in un secondo momento come argomenti visualizzabili, se necessario. 


## <a name="see-also"></a>Vedere anche



  






