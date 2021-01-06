---
title: Condividere calendari con utenti esterni
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: Informazioni su come consentire agli utenti di condividere i propri calendari con utenti esterni per riunioni e appuntamenti.
ms.openlocfilehash: 8204dc025f843953af13cba58fa0cf2e4d76de45
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760055"
---
# <a name="share-calendars-with-external-users"></a>Condividere calendari con utenti esterni

A volte è necessario per gli utenti pianificare riunioni con persone esterne all'organizzazione. Per semplificare il processo di individuazione di orari di riunioni comuni, Microsoft 365 consente di rendere disponibili i calendari per queste persone. Si tratta di persone che hanno la necessità di visualizzare i tempi di disponibilità per gli utenti dell'organizzazione, ma non gli account utente per l'organizzazione Microsoft 365.

È possibile abilitare la condivisione del calendario per tutti gli utenti dell'organizzazione nell'interfaccia di amministrazione di Microsoft 365. Una volta abilitata la condivisione, gli utenti possono utilizzare Outlook Web App per condividere i propri calendari con chiunque sia all'interno che all'esterno dell'organizzazione. Gli utenti all'interno dell'organizzazione possono visualizzare il calendario condiviso insieme al proprio calendario. Agli utenti esterni all'organizzazione verrà inviato un URL che può essere utilizzato per visualizzare il calendario. Gli utenti dell'organizzazione decidono quando condividerli e quanto condividerli.

> [!NOTE]
> Se si desidera condividere i calendari con un'organizzazione che utilizza Exchange Server 2013 (una soluzione locale), l'amministratore di Exchange dovrà impostare una relazione di autenticazione con il cloud. Questa operazione è nota come Federazione e deve soddisfare requisiti software minimi. Per ulteriori informazioni, vedere [sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) .
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a>Abilitare la condivisione del calendario con l'interfaccia di amministrazione di Microsoft 365

1. Nell' **interfaccia di amministrazione, andare a impostazioni** \> **organizzazione org**.

2. Nella scheda **Servizi** selezionare **Calendario**.
  
3. Nella pagina **Calendario** scegliere se si desidera consentire agli utenti di condividere i propri calendari con persone esterne all'organizzazione che dispongono di Microsoft 365 o Exchange. Scegliere se si desidera consentire agli utenti anonimi (utenti senza credenziali) di accedere ai calendari tramite un invito di posta elettronica.

4. Scegliere il tipo di informazioni del calendario da rendere disponibili agli utenti. È possibile consentire l'accesso a tutte le informazioni oppure limitarlo solo al tempo, all'oggetto e alla posizione.

## <a name="invite-people-to-access-calendars"></a>Invitare utenti ad accedere ai calendari

Una volta abilitata la condivisione, i proprietari del calendario potranno estendere gli inviti a utenti specifici. Per istruzioni, vedere [Condivisione del calendario in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5).