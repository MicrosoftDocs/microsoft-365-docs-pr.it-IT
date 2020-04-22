---
title: Domande frequenti sull'amministrazione delegata
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
description: In questo argomento sono riportate le domande frequenti e le risposte per i partner e i rivenditori Microsoft che desiderano eseguire attività amministrative Delegate, inclusa la possibilità di gestire Exchange Online Protection (EOP) per altri tenant (aziende).
ms.openlocfilehash: b79c0aba026a8d59aac338ceac0f1c4a60d71c4d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637653"
---
# <a name="delegated-administration-faq"></a>Domande frequenti sull'amministrazione delegata

In questo argomento sono riportate le domande frequenti e le risposte per i partner e i rivenditori Microsoft che desiderano eseguire attività amministrative Delegate, inclusa la possibilità di gestire Exchange Online Protection (EOP) per altri tenant (aziende).

**D. Sono un rivenditore e devo gestire i tenant del mio cliente. Come posso eseguire questa operazione?**

R. Se si è un partner o rivenditore Microsoft e si è iscritti a Microsoft Advisor, è possibile richiedere l'autorizzazione per l'amministrazione del tenant all'interno dell'interfaccia di amministrazione. Questa operazione è nota come amministrazione delegata e consente di gestire il tenant Microsoft 365 (incluse le impostazioni di EOP) come se si trattasse di un amministratore all'interno della propria organizzazione. Di seguito sono riportati i passaggi per l'esecuzione di un'amministrazione delegata:

1. Iscriviti e diventa un [consulente di Microsoft Office 365](https://aka.ms/cloudbenefits).

2. Iscriversi per l'amministrazione delegata. Prima di iniziare ad amministrare l'account di un cliente, il cliente stesso deve concedere al partner l'autorizzazione di amministratore delegato. Per ricevere la sua approvazione, devi innanzitutto [inviargli un'offerta per l'amministrazione delegata](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e). (Puoi anche offrire l'amministrazione delegata al cliente in un momento successivo.)

3. Creare l'account amministratore delegato utilizzando la procedura descritta in [aggiungere, modificare o eliminare un partner di consulenti di sottoscrizione](https://docs.microsoft.com/office365/admin/misc/add-partner).

Visitare [i partner: creare la propria azienda e amministrare la sottoscrizione di partner](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319) per ulteriori informazioni su come configurare l'amministrazione delegata.

**D. Sono un cliente, non un rivenditore, come posso configurare l'amministratore delegato del mio tenant secondario?**

R. Attualmente, l'amministrazione delegata è disponibile soltanto per rivenditori e partner. Tuttavia, forniamo un script di Windows PowerShell di esempio che ti consente di applicare criteri ai tenant secondari (aziende). Per ulteriori informazioni, vedi [Script di esempio per l'applicazione delle impostazioni EOP a più tenant](sample-script-for-applying-eop-settings-to-multiple-tenants.md).

**D. Posso impedire all'amministratore del tenant secondario di modificare i miei criteri?**

R. Microsoft 365 attualmente non dispone di questa funzionalità.

**D. Posso visualizzare report consolidati in tutti i miei tenant secondari?**

R. La creazione di rapporti consolidati tra le società gestite non è disponibile per i report dell'interfaccia di amministrazione di Microsoft 365 in questo momento. Tuttavia, è possibile eseguire questa operazione utilizzando [Microsoft Graph](https://docs.microsoft.com/graph/overview).
