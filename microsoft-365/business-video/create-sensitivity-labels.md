---
title: Creare etichette di riservatezza
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come creare e gestire le etichette di riservatezza.
ms.openlocfilehash: ff3f7eb5ffddf797e254fac0ed8fc87d96940455
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703218"
---
# <a name="protect-documents-with-sensitivity-labels"></a>Proteggere i documenti con etichette di riservatezza

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3VRGT?autoplay=false]

Le etichette di riservatezza consentono di classificare e proteggere i contenuti sensibili alla propria azienda.

## <a name="try-it"></a>Perché non provarlo?

1. Nell'interfaccia di [Amministrazione](https://admin.microsoft.com), selezionare l'interfaccia di amministrazione di **conformità** .
1. Selezionare **classificazione** e quindi **etichette di riservatezza**.
1. Selezionare **Crea un'etichetta** e, quando viene visualizzato l'avviso, selezionare **Sì**.
1. Immettere un **nome di etichetta**, una descrizione **comando** e un oggetto **Description**. Selezionare **Avanti**.
1. Attiva la **crittografia**. Scegliere quando si desidera assegnare le autorizzazioni, se si desidera che l'accesso degli utenti al contenuto scada e se si desidera consentire l'accesso offline.
1. **Selezionare Assegna autorizzazioni** e quindi **aggiungere gli indirizzi di posta elettronica o i domini**.
1. Immettere un indirizzo di posta elettronica o un nome di dominio (ad esempio, Contoso.org).  Selezionare **Aggiungi** e Ripeti per ogni indirizzo di posta elettronica o dominio che si desidera aggiungere.
1. Selezionare **Choose Permissions from preset or Custom**.
1. Utilizzare l'elenco a discesa per selezionare le autorizzazioni predefinite, ad esempio il **revisore** o il **Visualizzatore**, oppure selezionare autorizzazioni **personalizzate** . Se si sceglie **personalizzato**, selezionare le autorizzazioni dall'elenco. Fare clic su **Salva**, **Salva** e quindi su **Avanti**.
1. Attiva la **marcatura del contenuto** e scegli le marcature che vuoi usare.
1. Per ogni marcatura scelta, selezionare **Personalizza testo**. Immettere il testo che si desidera visualizzare nel documento e impostare le opzioni tipo di carattere e layout. Fare clic su **Salva** e quindi ripetere la ricerca per eventuali contrassegni aggiuntivi. Selezionare **Avanti**.
1. Facoltativamente, abilitare la **prevenzione della perdita di dati di endpoint**. Selezionare **Avanti**.
1. Facoltativamente, abilitare l' **etichettatura automatica**. Aggiungere una condizione. Ad esempio, in **rileva contenuto che contiene** selezionare **Aggiungi una condizione**. Immettere la condizione. ad esempio, aggiungere una condizione che, se viene rilevato Passport, previdenza sociale o altre informazioni riservate, verrà aggiunta l'etichetta. Selezionare **Avanti**.
1. Rivedere le impostazioni e selezionare **Crea**. L'etichetta è stata creata. Ripetere questa procedura per tutte le etichette aggiuntive desiderate.
1. Per impostazione predefinita, le etichette vengono visualizzate nelle app di Office nell'ordine seguente: **riservato**, **interno** e **pubblico**. Per modificare l'ordine, per ogni etichetta selezionare **altre azioni** (i puntini di sospensione) e quindi spostare l'etichetta verso l'alto o verso il basso. In genere, le autorizzazioni sono elencate tra il livello di autorizzazioni più basso e quello più alto.
1. Per aggiungere un'etichetta secondaria a un'etichetta, selezionare **altre azioni**, quindi **Aggiungi livello secondario**.
1. Al termine, scegliere **pubblica etichette**, **scegliere etichette da pubblicare** e quindi **Aggiungi**. Selezionare le etichette che si desidera pubblicare, quindi fare clic su **Aggiungi**, **fare** e quindi su **Avanti**.
1. Per impostazione predefinita, il nuovo criterio di etichetta viene applicato a tutti gli utenti. Se si desidera limitare gli utenti a cui è stato applicato il criterio, selezionare **Choose Users or groups** e quindi **Add**. Selezionare gli utenti a cui applicare i criteri e quindi fare clic su **Aggiungi**, **fare** e quindi su **Avanti**.
1. Se si desidera un'etichetta predefinita per documenti e messaggi di posta elettronica, selezionare l'etichetta desiderata nell'elenco a discesa. Esaminare le impostazioni rimanenti, modificarle in base alle esigenze e quindi fare clic su **Avanti**.
1. Immettere un **nome** e una **Descrizione** per i criteri. Selezionare **Avanti**.
1. Rivedere le impostazioni e quindi fare clic su **pubblica**.

Affinché le etichette funzionino correttamente, ogni utente deve scaricare il client di etichettatura unificata di Azure Information Protection. Eseguire una ricerca nel Web per **AzinfoProtection_UL.exe**, quindi scaricarlo dall'area download Microsoft ed eseguirlo nei computer degli utenti.

La volta successiva che si apre un'app di Office come Word, vengono visualizzate le etichette di riservatezza che sono state create. Per modificare o applicare un'etichetta, selezionare Sensitivity e scegliere un'etichetta.

