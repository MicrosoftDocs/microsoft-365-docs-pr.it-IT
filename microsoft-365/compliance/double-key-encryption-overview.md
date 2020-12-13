---
title: Panoramica e domande frequenti sulla crittografia a chiave doppia
description: Domande frequenti sulla crittografia a chiave doppia per Microsoft 365.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 12/11/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 32686e76018d8b6a361ea99e6b00271b9547ed95
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663061"
---
# <a name="double-key-encryption-frequently-asked-questions"></a>Domande frequenti sulla crittografia a chiave doppia

Si ha una domanda su come funziona la crittografia a chiave doppia? Controllare la risposta qui.

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a>Che cos'è la crittografia a chiave doppia per Microsoft 365 (DKE)?

La crittografia a doppio tasto per Microsoft 365 consente ai clienti di proteggere i dati estremamente riservati per soddisfare i requisiti specializzati. Aiuta i clienti a mantenere il controllo completo delle chiavi di crittografia. Vengono utilizzati due tasti per la protezione dei dati. una chiave del controllo e una seconda chiave archiviati in modo sicuro in Microsoft Azure. La visualizzazione dei dati protetti con la crittografia a chiave doppia richiede l'accesso a entrambe le chiavi. Poiché Microsoft può accedere a una sola di queste chiavi, i dati protetti rimangono inaccessibili a Microsoft, garantendo di avere il controllo completo sulla privacy e la sicurezza dei dati.  

È possibile ospitare il servizio di crittografia a chiave doppia utilizzato per richiedere la chiave, in una posizione di propria scelta (server di gestione delle chiavi locale o nel cloud). Il servizio viene gestito come se si trattasse di un'altra applicazione. La crittografia a doppio tasto consente di controllare l'accesso al servizio di crittografia a chiave doppia. È possibile archiviare i dati altamente riservati in locale o spostarli nel cloud. È possibile essere certi di impedire l'accesso di terze parti perché si mantiene il controllo completo della chiave. La crittografia a doppio tasto consente di archiviare i dati e la chiave nello stesso percorso.

DKE consente di soddisfare i requisiti normativi tra diverse normative e standard, quali il regolamento generale sulla protezione dei dati (GDPR), la portabilità e la responsabilità per l'assicurazione malattia (HIPAA), il Gramm-Leach-Bliley Act (GLBA), la legge sulla localizzazione dei dati in Russia – Federal Law No. 242-FZ, legge federale sulla privacy in Australia 1988 e legge sulla privacy della Nuova Zelanda 1993.

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a>È possibile utilizzare la crittografia a chiave doppia con l'etichetta di riservatezza integrata di Microsoft Office?

È necessario utilizzare il client Azure Information Protection Unified Labeling per proteggere i documenti con crittografia a chiave doppia. Attualmente, non è possibile utilizzare l'etichetta di riservatezza incorporata di Microsoft Office.

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a>Quali app di Microsoft 365 è possibile utilizzare con DKE?

È possibile utilizzare le etichette di DKE per proteggere i documenti utilizzando le versioni desktop di Word, Excel e PowerPoint in Windows. Assicurarsi di usare *. 12711 o versione successiva (versioni desktop di Word, PowerPoint ed Excel) in Windows.

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a>In che modo la crittografia a chiave doppia è diversa da quella esistente, ovvero la propria soluzione Key (HYOK)?

Crittografia a chiave doppia crittografa i dati con due tasti. La chiave di crittografia è nel controllo e la seconda chiave è archiviata in Microsoft Azure, consentendo di spostare i dati crittografati nel cloud. HYOK protegge i contenuti con un solo tasto e la chiave è sempre in locale.  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a>I documenti crittografati Double Key possono essere condivisi esternamente?

È possibile condividere i documenti crittografati con chiave doppia con gli utenti in un tenant separato purché tali utenti:

- Disporre dell'autorizzazione necessaria per accedere alla chiave nel servizio di crittografia a chiave doppia.

- Disporre dell'autorizzazione necessaria per accedere alla chiave in Microsoft Azure.

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a>Che cosa accade ai documenti protetti con HYOK?

La distribuzione di crittografia a chiave doppia non influirà sull'installazione di HYOK esistente. Tuttavia, si consiglia di iniziare a usare la crittografia a chiave doppia in parallelo con HYOK.

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a>È possibile eseguire la crittografia a chiave doppia nell'ambiente non Microsoft Air-gapped?

DKE non supporta questi ambienti perché il servizio richiede l'accesso a Microsoft Azure.

## <a name="where-can-i-store-double-key-encrypted-documents"></a>Dove è possibile archiviare I documenti crittografati con doppio tasto?

È possibile archiviare i documenti crittografati Double Key in locale o nel cloud. Nel cloud, è possibile spostare il contenuto crittografato in SharePoint Online e OneDrive for business. Poiché Microsoft non ha accesso alla propria chiave privata, i dati crittografati restano opachi a Microsoft. Questo significa anche che non è possibile visualizzare i documenti crittografati online in Office Web Apps.

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a>In quali aree geografiche e lingue è disponibile la crittografia a chiave doppia? La crittografia a chiave doppia è disponibile in tutto il mondo?

Le etichette di DKE sono localizzate nelle stesse lingue di altre etichette di riservatezza in Microsoft Information Protection. La crittografia a chiave doppia è disponibile in tutto il mondo.

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a>È possibile convertire un'etichetta non DKE in un'etichetta di DKE?

No. Non è possibile aggiungere DKE a un'etichetta dopo averlo creato. Al contrario, è necessario scegliere **Usa crittografia doppia chiave** e fornire l'URL del servizio di crittografia a chiave doppia quando si crea l'etichetta.

## <a name="how-do-i-roll-my-dke-keys"></a>Come si esegue il Rolling delle chiavi di DKE?

Per istruzioni su Rolling (denominato anche rotazione o reimpostazione delle chiavi) la chiave archiviata in Azure, vedere [Operations for your Azure Information Protection tenant Key](https://docs.microsoft.com/azure/information-protection/operations-customer-managed-tenant-key).

Per informazioni sulla creazione di una nuova chiave per il servizio DKE, vedere [tenant and Key Settings](double-key-encryption.md#tenant-and-key-settings) .

Quando si crea una chiave, è necessario configurare un nome e un GUID. Se quindi si ruota un tasto, si conserva il nome e il GUID precedenti, ma si aggiunge un nuovo record con lo stesso nome, ma con un GUID diverso. La nuova chiave viene impostata come attiva in modo che l'API della chiave pubblica inizi a restituirla per la nuova crittografia. Entrambe le chiavi sono disponibili per la decrittografia in modo che il nuovo contenuto e il contenuto precedente possano essere decrittografati.
