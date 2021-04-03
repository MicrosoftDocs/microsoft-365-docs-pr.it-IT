---
title: Creare etichette di riservatezza
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
ms.openlocfilehash: 997b05ba549d3dc57e1793585331dfcfae1e277b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578940"
---
# <a name="protect-documents-with-sensitivity-labels"></a>Proteggere i documenti con etichette di riservatezza

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3VRGT?autoplay=false]

Le etichette di riservatezza consentono di classificare e proteggere i contenuti sensibili all'azienda.

## <a name="try-it"></a>Perché non provarlo?

1. [Nell'interfaccia di amministrazione](https://admin.microsoft.com)selezionare l'interfaccia **di** amministrazione conformità.
1. Selezionare **Classificazione** e quindi **Etichette di riservatezza.**
1. Selezionare **Crea un'etichetta** e, quando viene visualizzato l'avviso, selezionare **Sì.**
1. Immettere un **nome etichetta,** **una descrizione comando** e una **descrizione.** Selezionare **Avanti**.
1. Attivare **Crittografia**. Scegliere quando assegnare le autorizzazioni, se si desidera che l'accesso degli utenti al contenuto scada e se si desidera consentire l'accesso offline.
1. **Selezionare Assegna autorizzazioni** e quindi **Aggiungi questi indirizzi di posta elettronica o domini**.
1. Immettere un indirizzo di posta elettronica o un nome di dominio (ad esempio Contoso.org).  Selezionare **Aggiungi** e ripetere l'operazione per ogni indirizzo di posta elettronica o dominio che si desidera aggiungere.
1. Seleziona **Scegli autorizzazioni da predefinito o personalizzato.**
1. Utilizzare l'elenco a discesa per selezionare le autorizzazioni predefinite, ad esempio **Revisore** o **Visualizzatore,** oppure selezionare **Autorizzazioni** personalizzate. Se si sceglie **Personalizzato,** selezionare le autorizzazioni dall'elenco. Selezionare **Salva,** **Salva** e quindi **Avanti.**
1. Attiva **Contrassegno contenuto** e scegli i contrassegni che vuoi usare.
1. Per ogni contrassegno scelto, selezionare **Personalizza testo.** Immettere il testo che si desidera visualizzare nel documento e impostare le opzioni relative al tipo di carattere e al layout. Selezionare **Salva** e quindi ripetere l'operazione per eventuali contrassegni aggiuntivi. Selezionare **Avanti**.
1. Facoltativamente, attivare Prevenzione della **perdita dei dati dell'endpoint.** Selezionare **Avanti**.
1. Facoltativamente, attivare **l'etichettatura automatica**. Aggiungere una condizione. Ad esempio, in **Rileva contenuto che contiene** selezionare Aggiungi una **condizione.** Immettere la condizione. Ad esempio, aggiungi una condizione che se vengono rilevati passport, social security o altre informazioni riservate, l'etichetta verrà aggiunta. Selezionare **Avanti**.
1. Rivedere le impostazioni e selezionare **Crea**. L'etichetta è stata creata. Ripetere questo processo per eventuali etichette aggiuntive desiderate.
1. Per impostazione predefinita, le etichette vengono visualizzate nelle app di Office nell'ordine seguente: **Riservato,** **Interno** e **Pubblico.** Per modificare l'ordine, per ogni etichetta seleziona **Altre** azioni (i puntini di sospensione) e quindi sposta l'etichetta verso l'alto o verso il basso. In genere, le autorizzazioni sono elencate dal livello più basso a quello più alto.
1. Per aggiungere un'etichetta secondaria a un'etichetta, selezionare **Altre azioni,** quindi **Aggiungi sottoal livello.**
1. Al termine, scegliere **Pubblica etichette,** **Scegliere le etichette da pubblicare** e quindi **Aggiungi**. Selezionare le etichette che si desidera pubblicare, quindi scegliere **Aggiungi**, **Fatto** e **quindi Avanti**.
1. Per impostazione predefinita, il nuovo criterio di etichetta viene applicato a tutti gli utenti. Se si desidera limitare l'applicazione del criterio, selezionare **Scegli utenti o gruppi** e quindi **Aggiungi**. Selezionare a chi si desidera applicare il criterio, quindi scegliere **Aggiungi**, **Fatto** e **quindi Avanti**.
1. Se si desidera un'etichetta predefinita per i documenti e la posta elettronica, selezionare l'etichetta desiderata nell'elenco a discesa. Rivedere le impostazioni rimanenti, regolare in base alle esigenze e quindi selezionare **Avanti.**
1. Immettere un **nome** e **una descrizione** per il criterio. Selezionare **Avanti**.
1. Rivedere le impostazioni, quindi selezionare **Pubblica.**

Per il corretto funzionamento delle etichette, ogni utente deve scaricare il client di etichettatura unificata di Azure Information Protection. Cercare nel Web **AzinfoProtection_UL.exe,** quindi scaricarlo dall'Area download Microsoft ed eseguirlo nei computer degli utenti.

Alla successiva apertura di un'app di Office come Word, verranno visualizzate le etichette di riservatezza create. Per modificare o applicare un'etichetta, selezionare Riservatezza e scegliere un'etichetta.

