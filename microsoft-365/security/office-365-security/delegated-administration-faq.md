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
description: Gli amministratori possono visualizzare le domande frequenti e le risposte alle attività amministrative delegate in Microsoft 365 per i partner e rivenditori Microsoft.
ms.openlocfilehash: 6729f276e6afea83568ca59d3bf48c08fcd837d2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203144"
---
# <a name="delegated-administration-faq"></a>Domande frequenti sull'amministrazione delegata

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In questo articolo sono riportate le domande frequenti e le risposte relative alle attività amministrative delegate in Microsoft 365 per i partner e i rivenditori Microsoft. L'amministrazione delegata include la possibilità di gestire le impostazioni di Exchange Online Protection (EOP) per altri tenant (aziende).

## <a name="im-a-reseller-and-i-need-to-manage-my-customer-tenants-how-does-this-work"></a>Sono un rivenditore e devo gestire i tenant dei clienti. Funzionamento.

Se si è un partner o rivenditore Microsoft e si è iscritti a Microsoft Advisor, è possibile richiedere le funzionalità di _amministrazione delegata_ nell'organizzazione Microsoft 365 del cliente.

L'amministrazione delegata consente di gestire Microsoft 365 (incluse le impostazioni di EOP) come se si trattasse di un amministratore all'interno dell'organizzazione. I passaggi per configurare l'amministrazione delegata sono descritti nell'elenco seguente:

1. Iscriviti e diventa un [consulente di Microsoft Office 365](https://aka.ms/cloudbenefits).

2. Iscriversi per l'amministrazione delegata. Prima di poter avviare l'amministrazione del tenant di un cliente, è necessario autorizzarla come amministratore delegato. Per ricevere la sua approvazione, devi innanzitutto [inviargli un'offerta per l'amministrazione delegata](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e). È inoltre possibile offrire l'amministrazione delegata al cliente in un secondo momento.

3. Creare l'account amministratore delegato utilizzando la procedura descritta in [aggiungere, modificare o eliminare un partner di consulenti di sottoscrizione](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).

Visitare [i partner: creare la propria azienda e amministrare la sottoscrizione di partner](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) per ulteriori informazioni su come configurare l'amministrazione delegata.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-subtenants"></a>Sono un cliente, non un rivenditore. In che modo è possibile configurare l'amministratore delegato per i subtenant?

L'amministrazione delegata è disponibile solo per rivenditori e partner. Tuttavia, è disponibile uno script PowerShell di esempio che consentirà di applicare i criteri ai subtenant (aziende). Per ulteriori informazioni, vedi [Script di esempio per l'applicazione delle impostazioni EOP a più tenant](sample-script-for-applying-eop-settings-to-multiple-tenants.md).

## <a name="can-i-prevent-my-subtenant-admin-from-modifying-my-policy"></a>È possibile impedire all'amministratore del sottotenant di modificare i criteri?

No. Microsoft 365 attualmente non dispone di questa funzionalità.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-subtenants"></a>È possibile ottenere rapporti consolidati tra tutti i subtenant?

La creazione di rapporti consolidati tra le società gestite non è disponibile nei report dell'interfaccia di amministrazione di Microsoft 365. Tuttavia, è possibile ottenere i report utilizzando [Microsoft Graph](https://docs.microsoft.com/graph/overview).
