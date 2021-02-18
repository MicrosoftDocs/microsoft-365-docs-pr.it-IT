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
description: Gli amministratori possono visualizzare le domande frequenti e le risposte sulle attività di amministrazione delegata in Microsoft 365 per i partner e i rivenditori Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 971572f8bff80da6dd63bed8958112332292feb9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288360"
---
# <a name="delegated-administration-faq"></a>Domande frequenti sull'amministrazione delegata

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Questo articolo fornisce domande frequenti e risposte sulle attività di amministrazione delegata in Microsoft 365 per i partner e i rivenditori Microsoft. L'amministrazione delegata include la possibilità di gestire le impostazioni di Exchange Online Protection (EOP) per altri tenant (società).

## <a name="im-a-reseller-and-i-need-to-manage-my-customer-tenants-how-does-this-work"></a>Sono un rivenditore e devo gestire i tenant dei clienti. Funzionamento.

Se si è un partner o un rivenditore Microsoft e si è  effettuato l'accesso come consulente Microsoft, è possibile richiedere funzionalità di amministrazione delegata nell'organizzazione di Microsoft 365 del cliente.

L'amministrazione delegata consente di gestire Microsoft 365 (incluse le impostazioni EOP) come se si fosse un amministratore all'interno dell'organizzazione. I passaggi per configurare l'amministrazione delegata sono descritti nell'elenco seguente:

1. Iscriviti e diventa un [consulente di Microsoft Office 365](https://aka.ms/cloudbenefits).

2. Iscriversi per l'amministrazione delegata. Prima di iniziare ad amministrare il tenant di un cliente, deve autorizzarti come amministratore delegato. Per ricevere la sua approvazione, devi innanzitutto [inviargli un'offerta per l'amministrazione delegata](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e). Puoi anche offrire l'amministrazione delegata al cliente in un secondo momento.

3. Crea l'account amministratore delegato usando la procedura descritta in [Aggiungere, modificare o eliminare un partner consulente sottoscrizione.](../../admin/misc/add-partner.md)

Visita [Partner: crea la tua azienda e amministra la sottoscrizione per i partner](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) per altre informazioni su come configurare l'amministrazione delegata.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-subtenants"></a>Sono un cliente, non un rivenditore. Come configurare l'amministratore delegato per i miei subtenants?

L'amministrazione delegata è disponibile solo per rivenditori e partner. Tuttavia, esiste uno script di PowerShell di esempio che consente di applicare i criteri ai subtenants (società). Per ulteriori informazioni, vedi [Script di esempio per l'applicazione delle impostazioni EOP a più tenant](sample-script-for-applying-eop-settings-to-multiple-tenants.md).

## <a name="can-i-prevent-my-subtenant-admin-from-modifying-my-policy"></a>È possibile impedire all'amministratore secondario di modificare i criteri?

No. Microsoft 365 attualmente non dispone di questa funzionalità.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-subtenants"></a>È possibile ottenere report consolidati tra tutti i subtenant?

I report consolidati tra le società gestite non sono disponibili nei report dell'interfaccia di amministrazione di Microsoft 365. È tuttavia possibile ottenere report utilizzando [Microsoft Graph.](https://docs.microsoft.com/graph/overview)
