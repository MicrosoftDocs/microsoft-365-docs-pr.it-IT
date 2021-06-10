---
title: Limitare l'accesso agli argomenti in Microsoft Viva Topics
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
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: d6dfb2f7f432a40c5b6e96a9437f50ba47e23387
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500874"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a>Limitare l'accesso agli argomenti in Microsoft Viva Topics

In Microsoft Viva, gli stakeholder dell'organizzazione potrebbero voler assicurarsi che argomenti specifici non siano individuati ed esposti agli utenti con licenza. Ad esempio, è possibile che si lavori a un progetto di cui non si desidera ancora esporre informazioni. Sebbene Office 365 autorizzazioni per siti, file e altre risorse impediranno agli utenti di esperienze di argomento di visualizzare informazioni riservate negli argomenti, esistono ulteriori misure di sicurezza per impedire che vengano individuati argomenti specifici.

Mentre gli amministratori delle conoscenze controllano le impostazioni per impedire l'individuare gli argomenti, i responsabili della conoscenza e altri stakeholder devono sapere come vengono eseguite in modo che possano collaborare.

> [!Important] 
> In questo articolo vengono descritti i modi per impedire che gli argomenti vengano identificati tramite l'IA o visualizzati nell'ambiente come ulteriore protezione della sicurezza. È importante notare che in Viva Topics, agli utenti non è consentito visualizzare nulla in un argomento a cui non è consentito accedere tramite Office 365 autorizzazioni. Anche se un utente è in grado di visualizzare un argomento, i relativi file, siti e pagine non dispongono delle autorizzazioni Office 365 per visualizzarlo non saranno visibili. Assicurarsi che le autorizzazioni per i file sensibili siano impostate correttamente deve essere la protezione principale.

## <a name="prevent-topics-from-being-identified"></a>Impedire l'identificazione degli argomenti

L'amministratore della knowledge base può limitare l'accesso a argomenti specifici impedendo che vengano trovati nell'indicizzazione iniziale. Esistono due modi per eseguire questa attività nelle impostazioni di amministrazione Viva Topics nell'Microsoft 365 di amministrazione.
 
- [Selezionare SharePoint siti](./topic-experiences-discovery.md#select-sharepoint-topic-sources)da escludere dall'individuazione degli argomenti: è possibile utilizzare questa impostazione per impedire la ricerca per indicizzazione di siti SharePoint specifici per gli argomenti.
- [Escludi gli argomenti](./topic-experiences-discovery.md#exclude-topics-by-name)in base al nome: gli amministratori possono utilizzare questa impostazione per impedire che argomenti specifici vengano individuati in base al nome. Nelle impostazioni di amministrazione Viva Topics, un amministratore può caricare un elenco di argomenti da escludere in un file CSV. È possibile escludere gli argomenti con corrispondenze esatte o parziali di un nome di argomento.

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>Impedire la visualizzazione di argomenti da parte di utenti specifici

Gli amministratori della knowledge base possono anche [selezionare gli utenti che possono visualizzare gli argomenti nell'organizzazione.](./topic-experiences-knowledge-rules.md) Questa impostazione consente di selezionare gli utenti con licenza che possono visualizzare tutti gli argomenti. In un ambiente pilota, ad esempio, è possibile consentire solo a un piccolo gruppo di utenti di visualizzare gli argomenti.

## <a name="remove-topics-from-being-viewed"></a>Rimuovere gli argomenti dalla visualizzazione

I responsabili della conoscenza possono scegliere [di rimuovere gli argomenti](./manage-topics.md) in modo che gli utenti non possano più vederli. Nella pagina **Gestisci argomenti** del **Centro** argomenti i responsabili delle conoscenze possono scegliere di rifiutare argomenti specifici per impedirne la visualizzazione. Gli argomenti possono essere rimossi indipendentemente dal fatto che siano in uno stato consigliato o confermato.

Se necessario, gli argomenti rimossi possono essere aggiunti nuovamente come argomenti visualizzabili. 


## <a name="see-also"></a>Vedere anche



