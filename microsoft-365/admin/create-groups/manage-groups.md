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
description: Informazioni su come gestire Microsoft 365, tra cui l'aggiunta di membri del gruppo di rimozione, la modifica dell'indirizzo di posta elettronica, il nome o la descrizione del gruppo e la personalizzazione del funzionamento del gruppo.
ms.openlocfilehash: 2ec8198b7e28b47bcbbf40818fbe624b2744f0ee
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454578"
---
# <a name="manage-a-group-in-the-microsoft-365-admin-center"></a>Gestire un gruppo nella interfaccia di amministrazione di Microsoft 365

Dopo aver creato [un gruppo Microsoft 365 e](create-groups.md) aver aggiunto i membri del gruppo, è possibile configurare il gruppo. È possibile modificare il nome o la descrizione del gruppo, gestire proprietari o membri e specificare se i mittenti esterni possono inviare un messaggio di posta elettronica al gruppo e se inviare copie delle conversazioni di gruppo ai membri.

Passare al interfaccia di amministrazione di Microsoft 365 all'indirizzo [https://admin.microsoft.com](https://admin.microsoft.com) .

## <a name="edit-the-group-name-or-description"></a>Modificare il nome o la descrizione del gruppo

1. Nell'interfaccia di amministrazione espandere **Gruppi** e quindi fare clic su **Gruppi.**

2. Selezionare il gruppo che si desidera modificare e quindi fare clic **su Modifica nome e descrizione.**

3. Aggiornare il nome e la descrizione, quindi selezionare **Salva**.

## <a name="manage-group-owners-and-members"></a>Gestire i proprietari e i membri del gruppo

1. Nell'interfaccia di amministrazione espandere **Gruppi** e quindi fare clic su **Gruppi.**

2. Fare clic sul nome del gruppo che si desidera gestire per aprire il riquadro delle impostazioni.

3. Nella scheda **Membri** scegliere se si desidera gestire proprietari o membri.

4. Scegliere **Aggiungi** per aggiungere qualcuno o fare clic **su X** per rimuovere qualcuno.

5. Scegliere **Chiudi**.

## <a name="send-copies-of-conversations-to-group-members-inboxes"></a>Inviare copie delle conversazioni alle cartelle Posta in arrivo dei membri del gruppo
  
Quando si utilizza l'interfaccia di amministrazione per creare un gruppo, per impostazione predefinita gli utenti non ottengono copie dei messaggi di posta elettronica di gruppo inviati alle proprie cartelle posta in arrivo, anche se gli utenti ottengono copie degli inviti alle riunioni di gruppo inviate alle proprie cartelle Posta in arrivo. Dovranno passare al gruppo per visualizzare le conversazioni. È possibile modificare questa impostazione nell'interfaccia di amministrazione.

Quando si attiva questa impostazione, i membri del gruppo riceveranno una copia dei messaggi di posta elettronica di gruppo e degli inviti alle riunioni inviati alla posta Outlook posta in arrivo. I membri potranno leggere ed eliminare questa copia del messaggio senza influire sugli altri utenti. Nella cartella Posta in arrivo del gruppo è ancora presente una copia del messaggio di posta elettronica.

I membri del gruppo possono rifiutare esplicitamente di ricevere questi messaggi di posta elettronica scegliendo di non seguire più il gruppo in Outlook.

1. Nell'interfaccia di amministrazione espandere **Gruppi** e quindi fare clic su **Gruppi.**

2. Fare clic sul nome del gruppo che si desidera gestire per aprire il riquadro delle impostazioni.

3. Nella scheda **Impostazioni** selezionare Invia **copie** di conversazioni ed eventi di gruppo ai membri del gruppo se si desidera che i membri ricevano copie dei messaggi di gruppo e degli elementi del calendario nella propria posta in arrivo.

4. Seleziona **Salva**.

## <a name="let-people-outside-the-organization-email-the-group"></a>Consentire agli utenti esterni all'organizzazione di inviare un messaggio di posta elettronica al gruppo

Questa opzione è ideale se si desidera avere un indirizzo di posta elettronica aziendale, ad esempio info@contoso.com.
 
1. Nell'interfaccia di amministrazione espandere **Gruppi** e quindi fare clic su **Gruppi.**

2. Fare clic sul nome del gruppo che si desidera gestire per aprire il riquadro delle impostazioni.

3. Nell'elenco gruppi dell'interfaccia di amministrazione selezionare il nome del gruppo che si desidera modificare e quindi nella scheda Impostazioni selezionare Consenti ai mittenti esterni di inviare il gruppo **tramite** posta **elettronica.**
    
4. Seleziona **Salva**.

## <a name="permanently-delete-a-microsoft-365-group"></a>Eliminare definitivamente un gruppo Microsoft 365 gruppo

A volte potrebbe essere necessario eliminare definitivamente un gruppo senza attendere la scadenza del periodo di eliminazione reverssione di 30 giorni. A tale scopo, avviare PowerShell ed eseguire questo comando per ottenere l'ID oggetto del gruppo:
 
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

[Gestire l'accesso guest ai gruppi di Microsoft 365](https://support.microsoft.com/office/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Scegliere il dominio da utilizzare per la creazione Microsoft 365 gruppi](../../solutions/choose-domain-to-create-groups.md)

[Consenti ai membri di inviare come o inviare per conto di un Microsoft 365 gruppo](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)

[Aggiornare le liste di distribuzione Microsoft 365 gruppi](../manage/upgrade-distribution-lists.md)

[Gestire Microsoft 365 con PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md)
