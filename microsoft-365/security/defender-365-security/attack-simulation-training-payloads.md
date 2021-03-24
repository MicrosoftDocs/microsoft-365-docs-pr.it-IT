---
title: Creare un payload per il training della simulazione di attacco
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Gli amministratori possono imparare a creare payload personalizzati per la formazione sulla simulazione di attacchi in Microsoft Defender per Office 365.
ms.technology: mdo
ms.openlocfilehash: 6cc5dd4a48ab89193133cfaf823d0a1b1868fa79
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065485"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a>Creare un payload personalizzato per la formazione del Simulatore di attacchi

Microsoft offre un solido catalogo di payload per varie tecniche di social engineering da associare alla formazione di simulazione degli attacchi. Tuttavia, potresti voler creare payload personalizzati che funzionino meglio per la tua organizzazione. Questo articolo descrive come creare un payload nel training di simulazione degli attacchi in Microsoft Defender per Office 365.

Puoi creare un payload facendo clic su **Crea un payload** nella scheda Payload [ **dedicati**](https://security.microsoft.com/attacksimulator?viewid=payload) o nella procedura guidata di creazione [della simulazione.](attack-simulation-training.md#selecting-a-payload)

Nel primo passaggio della procedura guidata verrà selezionato un tipo di payload. **Attualmente, è disponibile solo la posta elettronica**.

Selezionare quindi una tecnica associata. Per ulteriori dettagli sulle tecniche, vedere [Selezione di una tecnica di social engineering.](attack-simulation-training.md#selecting-a-social-engineering-technique)

Nel passaggio successivo assegnare un nome al payload. Facoltativamente, è possibile fornire una descrizione.

## <a name="configure-payload"></a>Configurare il payload

Ora è il momento di creare il payload. Immettere il nome del mittente, l'indirizzo di posta elettronica e l'oggetto del messaggio nella **sezione Dettagli mittente.** Selezionare un URL di phishing nell'elenco fornito. Questo URL verrà successivamente incorporato nel corpo del messaggio.

> [!TIP]
> Puoi scegliere un messaggio di posta elettronica interno per il mittente del payload, in modo che il payload venga visualizzato come proveniente da un altro dipendente dell'azienda. Ciò aumenterà la suscettibilità al payload e aiuterà a informare i dipendenti sul rischio di minacce interne.

È disponibile un editor di testo RTF per creare il payload. È inoltre possibile importare un messaggio di posta elettronica creato in precedenza. Quando crei il corpo del messaggio di posta elettronica, sfrutta i **tag dinamici** per personalizzare il messaggio di posta elettronica in base alle tue destinazioni. Fare **clic sul collegamento Phishing** per aggiungere l'URL di phishing selezionato in precedenza nel corpo del messaggio.

![Collegamento di phishing e tag dinamici evidenziati nella creazione di payload per Microsoft Defender per Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> Per risparmiare tempo, attivare l'opzione per sostituire tutti i collegamenti nel **messaggio di posta elettronica con il collegamento di phishing.**

Dopo aver finito di creare il payload a proprio piacimento, fai clic su **Avanti.**

## <a name="adding-indicators"></a>Aggiunta di indicatori

Gli indicatori aiuteranno i dipendenti a passare attraverso la simulazione di attacco a comprendere l'indizio che possono cercare negli attacchi futuri. Per iniziare, fare clic **su Aggiungi indicatore.**

Selezionare un indicatore che si desidera utilizzare nell'elenco a discesa. Questo elenco è curato per contenere gli indizi più comuni che vengono visualizzati nei messaggi di posta elettronica di phishing. Una volta selezionato, assicurati che il posizionamento dell'indicatore sia impostato su **Dal corpo del** messaggio di posta elettronica e fai clic su Seleziona **testo.** Evidenzia la parte del payload in cui viene visualizzato l'indicatore e fai clic su **Seleziona.**

![Testo evidenziato nel corpo del messaggio da aggiungere a un indicatore nel training della simulazione di attacco](../../media/attack-sim-preview-select-text.png)

Aggiungi una descrizione personalizzata per descrivere l'indicatore e fai clic all'interno del fotogramma di anteprima dell'indicatore per visualizzare un'anteprima dell'indicatore. Al termine, fare clic **su Aggiungi**. Ripeti questi passaggi finché non hai coperto tutti gli indicatori nel payload.

## <a name="review-payload"></a>Esaminare il payload

Hai finito di creare il payload. Ora è il momento di esaminare i dettagli e visualizzare un'anteprima del payload. L'anteprima includerà tutti gli indicatori creati. Puoi modificare ogni parte del payload da questo passaggio. Una volta soddisfatto, puoi **inviare il** payload.

> [!IMPORTANT]
> I payload creati avranno **Tenant** come origine. Quando si selezionano payload, assicurarsi di non filtrare **Tenant**.

## <a name="related-links"></a>Collegamenti correlati

[Introduzione alla formazione sull’uso di Simulatore di attacchi](attack-simulation-training-get-started.md)

[Creare una simulazione di attacco di phishing](attack-simulation-training.md)

[Acquisire informazioni approfondite attraverso la formazione del Simulatore di attacchi](attack-simulation-training-insights.md)
