---
title: Domande frequenti sull'amministrazione delegata
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: In questo argomento vengono fornite le domande frequenti e le risposte per i partner e i rivenditori Microsoft che desiderano eseguire le attività amministrative di Microsoft 365 Delegate.
ms.openlocfilehash: 01781437bbc7e8fe5c035ea23e4392e734e0231f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827088"
---
# <a name="delegated-administration-faq"></a>Domande frequenti sull'amministrazione delegata

In questo argomento sono riportate le domande frequenti e le risposte per i partner e i rivenditori Microsoft che desiderano eseguire attività amministrative Delegate, inclusa la possibilità di gestire Exchange Online Protection (EOP) per altri tenant (aziende).

## <a name="im-a-reseller-and-i-need-to-manage-my-customers-tenants-how-does-this-work"></a>Sono un rivenditore e devo gestire gli inquilini del cliente; in che modo funziona?

Se si è un partner o rivenditore Microsoft e si è iscritti a Microsoft Advisor, è possibile richiedere l'autorizzazione per l'amministrazione del tenant all'interno dell'interfaccia di amministrazione. Questa operazione è nota come amministrazione delegata e consente di gestire il tenant Microsoft 365 (incluse le impostazioni di EOP) come se si trattasse di un amministratore all'interno della propria organizzazione. Di seguito sono riportati i passaggi per l'esecuzione di un'amministrazione delegata:

1. Iscriviti e diventa un [consulente di Microsoft Office 365](https://aka.ms/cloudbenefits).

2. Iscriversi per l'amministrazione delegata. Prima di iniziare ad amministrare l'account di un cliente, il cliente stesso deve concedere al partner l'autorizzazione di amministratore delegato. Per ricevere la sua approvazione, devi innanzitutto [inviargli un'offerta per l'amministrazione delegata](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e). (Puoi anche offrire l'amministrazione delegata al cliente in un momento successivo.)

3. Creare l'account amministratore delegato utilizzando la procedura descritta in [aggiungere, modificare o eliminare un partner di consulenti di sottoscrizione](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).

Visitare [i partner: creare la propria azienda e amministrare la sottoscrizione di partner](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) per ulteriori informazioni su come configurare l'amministrazione delegata.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-sub-tenants"></a>Sono un cliente, non un rivenditore, come è possibile configurare l'amministratore delegato per i tenant secondari?

Attualmente, l'amministrazione delegata è disponibile soltanto per rivenditori e partner. Tuttavia, forniamo un script di Windows PowerShell di esempio che ti consente di applicare criteri ai tenant secondari (aziende). Per ulteriori informazioni, vedi [Script di esempio per l'applicazione delle impostazioni EOP a più tenant](sample-script-for-applying-eop-settings-to-multiple-tenants.md).

## <a name="can-i-prevent-my-sub-tenant-admin-from-modifying-my-policy"></a>Posso impedire all'amministratore del tenant secondario di modificare i miei criteri?

Microsoft 365 attualmente non dispone di questa funzionalità.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-sub-tenants"></a>Posso visualizzare report consolidati in tutti i miei tenant secondari?

La creazione di rapporti consolidati tra le società gestite non è disponibile per i report dell'interfaccia di amministrazione di Microsoft 365 in questo momento. Tuttavia, è possibile eseguire questa operazione utilizzando [Microsoft Graph](https://docs.microsoft.com/graph/overview).
