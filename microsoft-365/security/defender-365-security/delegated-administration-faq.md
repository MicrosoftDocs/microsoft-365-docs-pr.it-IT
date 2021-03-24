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
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono visualizzare le domande frequenti e le risposte sulle attività di amministrazione delegate in Microsoft 365 per i partner e i rivenditori Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 82fa70a8025f67610032ba59368bc74789b60f84
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065290"
---
# <a name="delegated-administration-faq"></a>Domande frequenti sull'amministrazione delegata

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In questo articolo vengono fornite domande frequenti e risposte sulle attività di amministrazione delegate in Microsoft 365 per i partner e i rivenditori Microsoft. L'amministrazione delegata include la possibilità di gestire le impostazioni di Exchange Online Protection (EOP) per altri tenant (società).

## <a name="im-a-reseller-and-i-need-to-manage-my-customer-tenants-how-does-this-work"></a>Sono un rivenditore e devo gestire i tenant dei clienti. Funzionamento.

Se si è un partner o un rivenditore Microsoft e si è  effettuato l'accesso come consulente Microsoft, è possibile richiedere funzionalità di amministrazione delegate nell'organizzazione microsoft 365 del cliente.

L'amministrazione delegata consente di gestire Microsoft 365 (incluse le impostazioni EOP) come se si fosse un amministratore all'interno dell'organizzazione. I passaggi per configurare l'amministrazione delegata sono descritti nell'elenco seguente:

1. Iscriviti e diventa un [consulente di Microsoft Office 365](https://partner.microsoft.com/?cloudbenefits).

2. Iscriversi per l'amministrazione delegata. Prima di iniziare ad amministrare il tenant di un cliente, è necessario autorizzare l'utente come amministratore delegato. Per ricevere la sua approvazione, devi innanzitutto [inviargli un'offerta per l'amministrazione delegata](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e). Puoi anche offrire l'amministrazione delegata al cliente in un secondo momento.

3. Creare l'account amministratore delegato usando la procedura descritta in [Aggiungere, modificare o eliminare un partner consulente sottoscrizione.](../../admin/misc/add-partner.md)

Per ulteriori informazioni su come configurare [l'amministrazione delegata,](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) vedere Partner: Creare la propria azienda e amministrare l'abbonamento ai partner.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-subtenants"></a>Sono un cliente, non un rivenditore. In che modo è possibile configurare l'amministratore delegato per i subtenant?

L'amministrazione delegata è disponibile solo per rivenditori e partner. Tuttavia, è presente uno script di PowerShell di esempio che consente di applicare i criteri ai subtenants (società). Per ulteriori informazioni, vedi [Script di esempio per l'applicazione delle impostazioni EOP a più tenant](sample-script-for-applying-eop-settings-to-multiple-tenants.md).

## <a name="can-i-prevent-my-subtenant-admin-from-modifying-my-policy"></a>È possibile impedire all'amministratore secondario di modificare i criteri?

No. Microsoft 365 non dispone attualmente di questa funzionalità.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-subtenants"></a>È possibile ottenere report consolidati tra tutti i subtenant?

I report consolidati tra le società gestite non sono disponibili nei report dell'interfaccia di amministrazione di Microsoft 365. È tuttavia possibile ottenere report utilizzando [Microsoft Graph.](/graph/overview)