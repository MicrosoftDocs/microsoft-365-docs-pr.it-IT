---
title: Gestire un gruppo nell'interfaccia di amministrazione
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 74a1ef8b-3844-4d08-9980-9f8f7a36000f
description: Informazioni su come gestire i gruppi di Microsoft 365, inclusa l'aggiunta di Rimuovi membri del gruppo, la modifica dell'indirizzo di posta elettronica, il nome del gruppo o la descrizione e la personalizzazione del funzionamento del gruppo.
ms.openlocfilehash: 8216b80ba6cd6bffe470f4fe4ace43307afba5f2
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753302"
---
# <a name="manage-a-group-in-the-microsoft-365-admin-center"></a>Gestire un gruppo nell'interfaccia di amministrazione di Microsoft 365

Dopo aver [creato un gruppo di Microsoft 365](create-groups.md) e aver aggiunto i membri del gruppo, è possibile configurare il gruppo. È possibile modificare il nome o la descrizione del gruppo, gestire i proprietari o i membri e specificare se i mittenti esterni possono inviare messaggi di posta elettronica al gruppo e se inviano copie delle conversazioni di gruppo ai membri.

Accedere all'interfaccia di amministrazione di Microsoft 365 all'indirizzo [https://admin.microsoft.com](https://admin.microsoft.com) .

## <a name="edit-the-group-name-or-description"></a>Modificare il nome o la descrizione del gruppo

1. Nell'interfaccia di Amministrazione espandere **gruppi**e quindi fare clic su **gruppi**.

2. Selezionare il gruppo che si desidera modificare, quindi fare clic su **modifica nome e descrizione**.

3. Aggiornare il nome e la descrizione e quindi fare clic su **Salva**.

## <a name="manage-group-owners-and-members"></a>Gestire i proprietari e i membri del gruppo

1. Nell'interfaccia di Amministrazione espandere **gruppi**e quindi fare clic su **gruppi**.

2. Fare clic sul nome del gruppo che si desidera gestire per aprire il riquadro Impostazioni.

3. Nella scheda **membri** scegliere se si desidera gestire i proprietari o i membri.

4. Scegliere **Aggiungi** per aggiungere un utente o fare clic su **X** per rimuovere un utente.

5. Scegliere **Chiudi**.

## <a name="send-copies-of-conversations-to-group-members-inboxes"></a>Inviare copie delle conversazioni alle cassette postali dei membri del gruppo
  
Quando si utilizza l'interfaccia di amministrazione per creare un gruppo, per impostazione predefinita gli utenti non ottengono le copie dei messaggi di posta elettronica di gruppo e gli inviti alle riunioni inviate alla posta in arrivo. Dovranno accedere al gruppo per visualizzare conversazioni e riunioni. È possibile modificare questa impostazione nell'interfaccia di amministrazione.

Quando si attiva questa impostazione, i membri del gruppo riceveranno una copia dei messaggi di posta elettronica di gruppo e gli inviti alle riunioni inviati alla posta in arrivo di Outlook. I membri potranno leggere ed eliminare questa copia del messaggio senza influire sugli altri utenti. Nella cartella Posta in arrivo del gruppo è ancora presente una copia del messaggio di posta elettronica.

I membri del gruppo possono scegliere di non ricevere i messaggi di posta elettronica scegliendo di smettere di seguire il gruppo in Outlook.

1. Nell'interfaccia di Amministrazione espandere **gruppi**e quindi fare clic su **gruppi**.

2. Fare clic sul nome del gruppo che si desidera gestire per aprire il riquadro Impostazioni.

3. Nella scheda **Impostazioni** selezionare **invia copie di conversazioni di gruppo ed eventi ai membri del gruppo** se si desidera che i membri ricevano copie dei messaggi di gruppo e degli elementi del calendario nella propria cartella posta in arrivo.

4. Selezionare **Salva**.

## <a name="let-people-outside-the-organization-email-the-group"></a>Consenti agli utenti esterni all'organizzazione di inviare messaggi di posta elettronica al gruppo

Questa opzione è ideale se si desidera disporre di un indirizzo di posta elettronica aziendale, ad esempio info@contoso.com.
 
1. Nell'interfaccia di Amministrazione espandere **gruppi**e quindi fare clic su **gruppi**.

2. Fare clic sul nome del gruppo che si desidera gestire per aprire il riquadro Impostazioni.

3. Nell'elenco gruppi dell'interfaccia di amministrazione selezionare il nome del gruppo che si desidera modificare, quindi nella scheda **Impostazioni** selezionare **Consenti ai mittenti esterni di inviare messaggi di posta elettronica a questo gruppo**.
    
4. Selezionare **Salva**.

## <a name="permanently-delete-a-microsoft-365-group"></a>Eliminare definitivamente un gruppo di Microsoft 365

A volte è possibile che si desideri eliminare definitivamente un gruppo senza attendere la scadenza del periodo di cancellazione di 30 giorni. A tale scopo, avviare PowerShell ed eseguire questo comando per ottenere l'ID oggetto del gruppo:
 
 ```powershell
`Get-AzureADMSDeletedGroup`
```

Prendere nota dell'ID oggetto del gruppo o dei gruppi che si desidera eliminare definitivamente.
  
> [!CAUTION]
> Il gruppo e i dati che contiene vengono eliminati in modo definitivo. 
  
Per eliminare il gruppo, eseguire questo comando in PowerShell:

```powershell
`Remove-AzureADMSDeletedDirectoryObject -Id <objectId>`
```

Per verificare che il gruppo sia stato eliminato correttamente, eseguire di nuovo il cmdlet  *Get-AzureADMSDeletedGroup*  per controllare che il gruppo non compaia più nell'elenco dei gruppi eliminati temporaneamente. In alcuni casi l'eliminazione definitiva del gruppo e di tutti i suoi dati può richiedere fino a 24 ore. 
  
## <a name="related-articles"></a>Articoli correlati

[Creare un gruppo di Microsoft 365](create-groups.md)

[Gestire l'accesso Guest ai gruppi di Microsoft 365](https://support.microsoft.com/office/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Scegliere il dominio da utilizzare per la creazione dei gruppi di Microsoft 365](../../solutions/choose-domain-to-create-groups.md)

[Consenti ai membri di inviare o inviare messaggi per conto di un gruppo di Microsoft 365](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)

[Aggiornare le liste di distribuzione ai gruppi di Microsoft 365](../manage/upgrade-distribution-lists.md)

[Gestire i gruppi Microsoft 365 con PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
