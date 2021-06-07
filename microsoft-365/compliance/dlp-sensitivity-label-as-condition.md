---
title: Usare le etichette di riservatezza come condizioni per i criteri di prevenzione della perdita dei dati
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: informazioni sui servizi e sui tipi di elementi che è possibile usare nelle etichette di riservatezza come condizioni per i criteri di prevenzione della perdita dei dati
ms.openlocfilehash: 94d5e9f53471f6113dcc755995a3f94e95a58e53
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779844"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a>Usare le etichette di riservatezza come condizioni per i criteri di prevenzione della perdita dei dati

Le [etichette di riservatezza](sensitivity-labels.md) possono essere usate come condizioni dei criteri di prevenzione della perdita dei dati in queste posizioni:

- Messaggi di posta elettronica di Exchange Online
- SharePoint Online
- Siti di OneDrive for Business
- Dispositivi Windows 10

Le etichette di riservatezza sono mostrate come opzioni dell'elenco **Il contenuto contiene**.

> [!div class="mx-imgBorder"]
> ![etichetta di riservatezza come condizione](../media/dlp-sensitivity-label-as-a-condition.png)

> [!IMPORTANT]
> **Le etichette di riservatezza** come condizione non sono disponibili se sono state selezionate **chat di Teams e i messaggi del canale** come posizione in cui applicare i criteri di prevenzione della perdita dei dati.


## <a name="supported-items-scenarios-and-policy-tips"></a>Elementi supportati, scenari e suggerimenti per i criteri

È possibile usare le etichette di riservatezza come condizioni per questi elementi e in questi scenari.

### <a name="supported-items"></a>Elementi supportati

|Servizio  |Tipo di elemento  |Disponibile per suggerimento per i criteri  |Applicabile  |
|---------|---------|---------|---------|
|Exchange    |messaggio di posta elettronica         |sì         |sì         |
|Exchange    |allegato di posta elettronica         |no         |sì*         |
|SharePoint Online     |elementi di SharePoint Online         |sì         |sì         |
|OneDrive for Business     |elementi         |sì         |sì         |
|Teams     |Messaggi di Teams e dei canali         |non applicabile         |non applicabile         |
|Teams     |allegati         |sì **         |sì **         |
|Dispositivi Windows 10     |elementi         |sì         |sì         |
|MCAS (anteprima) |elementi         |sì         |sì         |

\* Il rilevamento dei criteri di prevenzione della perdita dei dati per gli allegati di posta elettronica con etichette è supportato solo per i tipi di file di Office.

\** Gli allegati inviati in Teams tramite chat individuali o canali sono caricati automaticamente su OneDrive for Business e SharePoint. Perciò, se SharePoint Online o OneDrive for Business sono inclusi come posizioni del criteri di prevenzione della perdita dei dati, gli allegati etichettai inviati in Teams saranno inclusi automaticamente nell'ambito di questa condizione. Teams non deve essere selezionato come posizione nel criteri di prevenzione della perdita dei dati.

> [!NOTE]
> L'abilità di DLP di rilevare le etichette di riservatezza in SharePoint e OneDrive for Business è limitata. Per altre informazioni, vedere [Abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md#limitations).

### <a name="supported-scenarios"></a>Scenari supportati

- L'amministratore per la prevenzione della perdita dei dati sarà in grado di accedere a un elenco di tutte le etichette di conservazione del tenant quando sceglie di includere una o più etichette di riservatezza come condizioni.

- L'uso delle etichette di riservatezza come condizioni è supportato in tutti i carichi di lavoro, come indicato nella matrice di supporto precedente.

- I suggerimenti per i criteri di prevenzione della perdita dei dati continuano a essere visualizzati in tutti i carichi di lavoro (salvo quelli di Outlook Win32) per i criteri di prevenzione che contengono etichette di riservatezza come condizioni.

- Le etichette di riservatezza sono visualizzate anche all'interno del messaggio di posta elettronica del report degli incidenti, se c'è una corrispondenza con un criterio di prevenzione della perdita dei dati con etichette di riservatezza come condizioni. 

- I dettagli dell'etichetta di riservatezza sono mostrati anche nel log di controllo della corrispondenza delle regole di prevenzione della perdita dei dati, in caso di corrispondenza con criteri di prevenzione che contengono etichette di riservatezza come condizioni.


### <a name="support-policy-tips"></a>Supporto per i suggerimenti per i criteri


|Carico di lavoro  |Suggerimenti per criteri supportati/non supportati  |
|---------|---------|
|OWA |    supportato     |
|Outlook Win 32    |  non supportato       |
|SharePoint   |   supportato      |
|OneDrive for Business    |    supportato     |
|dispositivi endpoint   |  non supportato       |
